# AslRegistryGetStringExpand

- ea: `0x18000e8e8`
- end: `0x18000eb05`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b8e8`

## callees

- `0x18000cd8c`
- `0x18000cfa4`
- `0x18000e240`
- `0x18000e71c`
- `0x18000e8e8`

## import_xrefs

- `msvcrt!wcschr` at `0x18000e932`
- `msvcrt!wcschr` at `0x18000e932`
- `ntdll!RtlFreeHeap` at `0x18000ea23`
- `ntdll!RtlFreeHeap` at `0x18000eacf`
- `ntdll!RtlFreeHeap` at `0x18000eaec`
- `ntdll!RtlFreeHeap` at `0x18000ea23`
- `ntdll!RtlFreeHeap` at `0x18000eacf`
- `ntdll!RtlFreeHeap` at `0x18000eaec`
- `ntdll!RtlAllocateHeap` at `0x18000e9a2`
- `ntdll!RtlAllocateHeap` at `0x18000ea43`
- `ntdll!RtlAllocateHeap` at `0x18000e9a2`
- `ntdll!RtlAllocateHeap` at `0x18000ea43`

## string_xrefs

- `0x18000e96b`: `AslRegistryGetStringExpand`
- `0x18000e9c2`: `AslRegistryGetStringExpand`
- `0x18000ea9e`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, int a4)
{
  PVOID Heap; // rdi
  int String; // eax
  wchar_t *v8; // rsi
  int v9; // ebx
  int ProcessWowInfo; // eax
  __int64 v11; // r8
  __int16 v12; // r15
  __int16 v13; // r12
  int v14; // ebx
  __int64 v16; // [rsp+28h] [rbp-30h]
  __int16 v17[2]; // [rsp+40h] [rbp-18h] BYREF
  __int16 v18; // [rsp+44h] [rbp-14h] BYREF
  wchar_t *Str[2]; // [rsp+48h] [rbp-10h] BYREF

  Heap = 0;
  v17[0] = -1;
  Str[0] = 0;
  v18 = -1;
  String = AslRegistryGetString(Str, a2, a3);
  v8 = Str[0];
  v9 = String;
  if ( String < 0 )
    goto LABEL_16;
  if ( !wcschr(Str[0], 0x25u) )
  {
    *a1 = v8;
    return 0;
  }
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v18, v17);
  v9 = ProcessWowInfo;
  if ( ProcessWowInfo >= 0 )
  {
    Str[0] = (wchar_t *)260;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    if ( !Heap )
    {
      v11 = 1476;
LABEL_8:
      AslLogCallPrintf(1, "AslRegistryGetStringExpand", v11, "Out of memory");
      v9 = -1073741801;
      goto LABEL_16;
    }
    v12 = v17[0];
    v13 = v18;
    v9 = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, 260, (__int64)Str, v18, v17[0]);
    if ( v9 == -1073741789 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v14 = (int)Str[0];
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (__int64)Str[0]);
      if ( !Heap )
      {
        v11 = 1494;
        goto LABEL_8;
      }
      v9 = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, v14, (__int64)Str, v13, v12);
    }
    if ( v9 >= 0 )
    {
      *a1 = (wchar_t *)Heap;
      Heap = 0;
      v9 = 0;
    }
    else
    {
      LODWORD(v16) = v9;
      AslLogCallPrintf(
        1,
        "AslRegistryGetStringExpand",
        1509,
        "AslEnvExpandStrings2 failed to expand strings for %ws [%x]",
        v8,
        v16);
    }
    goto LABEL_16;
  }
  AslLogCallPrintf(1, "AslRegistryGetStringExpand", 1464, "AslEnvGetProcessWowInfo failed [%x]", ProcessWowInfo);
LABEL_16:
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e8e8  push    rbp
0x18000e8ea  push    rbx
0x18000e8eb  push    rsi
0x18000e8ec  push    rdi
0x18000e8ed  push    r12
0x18000e8ef  push    r13
0x18000e8f1  push    r14
0x18000e8f3  push    r15
0x18000e8f5  mov     rbp, rsp
0x18000e8f8  sub     rsp, 58h
0x18000e8fc  mov     eax, 0FFFFh
0x18000e901  mov     r14, rcx
0x18000e904  xor     edi, edi
0x18000e906  mov     [rbp+var_18], ax
0x18000e90a  lea     rcx, [rbp+Str]
0x18000e90e  mov     [rbp+Str], rdi
0x18000e912  mov     [rbp+var_14], ax
0x18000e916  mov     r13, r9
0x18000e919  call    AslRegistryGetString
0x18000e91e  mov     rsi, [rbp+Str]
0x18000e922  mov     ebx, eax
0x18000e924  test    eax, eax
0x18000e926  js      loc_18000EAB8
0x18000e92c  lea     edx, [rdi+25h]; Ch
0x18000e92f  mov     rcx, rsi; Str
0x18000e932  call    cs:__imp_wcschr
0x18000e938  test    rax, rax
0x18000e93b  jnz     short loc_18000E947
0x18000e93d  mov     [r14], rsi
0x18000e940  xor     ebx, ebx
0x18000e942  jmp     loc_18000EAF2
0x18000e947  lea     rdx, [rbp+var_18]
0x18000e94b  lea     rcx, [rbp+var_14]
0x18000e94f  call    AslEnvGetProcessWowInfo
0x18000e954  mov     ebx, eax
0x18000e956  test    eax, eax
0x18000e958  jns     short loc_18000E981
0x18000e95a  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x18000e961  mov     dword ptr [rsp+58h+var_38], eax
0x18000e965  mov     r8d, 5B8h
0x18000e96b  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18000e972  mov     ecx, 1
0x18000e977  call    AslLogCallPrintf
0x18000e97c  jmp     loc_18000EAB8
0x18000e981  mov     rcx, gs:60h
0x18000e98a  mov     ebx, 104h
0x18000e98f  mov     edx, 8; Flags
0x18000e994  mov     [rbp+Str], rbx
0x18000e998  mov     r8d, 208h; Size
0x18000e99e  mov     rcx, [rcx+30h]; HeapHandle
0x18000e9a2  call    cs:__imp_RtlAllocateHeap
0x18000e9a8  mov     rdi, rax
0x18000e9ab  test    rax, rax
0x18000e9ae  jnz     short loc_18000E9D8
0x18000e9b0  mov     r8d, 5C4h
0x18000e9b6  lea     r9, aOutOfMemory; "Out of memory"
0x18000e9bd  mov     ecx, 1
0x18000e9c2  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18000e9c9  call    AslLogCallPrintf
0x18000e9ce  mov     ebx, 0C0000017h
0x18000e9d3  jmp     loc_18000EAB8
0x18000e9d8  movzx   r15d, [rbp+var_18]
0x18000e9dd  lea     rax, [rbp+Str]
0x18000e9e1  movzx   r12d, [rbp+var_14]
0x18000e9e6  mov     r9, rbx
0x18000e9e9  mov     [rsp+58h+var_28], r15w
0x18000e9ef  mov     r8, rdi
0x18000e9f2  mov     word ptr [rsp+58h+var_30], r12w
0x18000e9f8  mov     rdx, rsi
0x18000e9fb  mov     rcx, r13
0x18000e9fe  mov     [rsp+58h+var_38], rax
0x18000ea03  call    AslEnvExpandStrings2
0x18000ea08  mov     ebx, eax
0x18000ea0a  cmp     eax, 0C0000023h
0x18000ea0f  jnz     short loc_18000EA84
0x18000ea11  mov     rcx, gs:60h
0x18000ea1a  mov     r8, rdi; P
0x18000ea1d  xor     edx, edx; Flags
0x18000ea1f  mov     rcx, [rcx+30h]; HeapHandle
0x18000ea23  call    cs:__imp_RtlFreeHeap
0x18000ea29  mov     rcx, gs:60h
0x18000ea32  mov     edx, 8; Flags
0x18000ea37  mov     rbx, [rbp+Str]
0x18000ea3b  mov     rcx, [rcx+30h]; HeapHandle
0x18000ea3f  lea     r8, [rbx+rbx]; Size
0x18000ea43  call    cs:__imp_RtlAllocateHeap
0x18000ea49  mov     rdi, rax
0x18000ea4c  test    rax, rax
0x18000ea4f  jnz     short loc_18000EA5C
0x18000ea51  mov     r8d, 5D6h
0x18000ea57  jmp     loc_18000E9B6
0x18000ea5c  mov     [rsp+58h+var_28], r15w
0x18000ea62  lea     rax, [rbp+Str]
0x18000ea66  mov     word ptr [rsp+58h+var_30], r12w
0x18000ea6c  mov     r9, rbx
0x18000ea6f  mov     r8, rdi
0x18000ea72  mov     [rsp+58h+var_38], rax
0x18000ea77  mov     rdx, rsi
0x18000ea7a  mov     rcx, r13
0x18000ea7d  call    AslEnvExpandStrings2
0x18000ea82  mov     ebx, eax
0x18000ea84  test    ebx, ebx
0x18000ea86  jns     short loc_18000EAB1
0x18000ea88  mov     dword ptr [rsp+58h+var_30], ebx
0x18000ea8c  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x18000ea93  mov     r8d, 5E5h
0x18000ea99  mov     [rsp+58h+var_38], rsi
0x18000ea9e  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18000eaa5  mov     ecx, 1
0x18000eaaa  call    AslLogCallPrintf
0x18000eaaf  jmp     short loc_18000EAB8
0x18000eab1  mov     [r14], rdi
0x18000eab4  xor     edi, edi
0x18000eab6  xor     ebx, ebx
0x18000eab8  test    rsi, rsi
0x18000eabb  jz      short loc_18000EAD5
0x18000eabd  mov     rcx, gs:60h
0x18000eac6  mov     r8, rsi; P
0x18000eac9  xor     edx, edx; Flags
0x18000eacb  mov     rcx, [rcx+30h]; HeapHandle
0x18000eacf  call    cs:__imp_RtlFreeHeap
0x18000ead5  test    rdi, rdi
0x18000ead8  jz      short loc_18000EAF2
0x18000eada  mov     rcx, gs:60h
0x18000eae3  mov     r8, rdi; P
0x18000eae6  xor     edx, edx; Flags
0x18000eae8  mov     rcx, [rcx+30h]; HeapHandle
0x18000eaec  call    cs:__imp_RtlFreeHeap
0x18000eaf2  mov     eax, ebx
0x18000eaf4  add     rsp, 58h
0x18000eaf8  pop     r15
0x18000eafa  pop     r14
0x18000eafc  pop     r13
0x18000eafe  pop     r12
0x18000eb00  pop     rdi
0x18000eb01  pop     rsi
0x18000eb02  pop     rbx
0x18000eb03  pop     rbp
0x18000eb04  retn
```
