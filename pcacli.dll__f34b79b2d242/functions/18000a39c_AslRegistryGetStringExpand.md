# AslRegistryGetStringExpand

- ea: `0x18000a39c`
- end: `0x18000a5b0`
- name: `AslRegistryGetStringExpand`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180005620`

## callees

- `0x180006880`
- `0x180006c80`
- `0x180007738`
- `0x18000a39c`
- `0x18000b6dc`
- `0x18000b8dc`

## import_xrefs

- `msvcrt!wcschr` at `0x18000a3e6`
- `msvcrt!wcschr` at `0x18000a3e6`
- `ntdll!RtlAllocateHeap` at `0x18000a456`
- `ntdll!RtlAllocateHeap` at `0x18000a4f4`
- `ntdll!RtlAllocateHeap` at `0x18000a456`
- `ntdll!RtlAllocateHeap` at `0x18000a4f4`

## string_xrefs

- `0x18000a41f`: `AslRegistryGetStringExpand`
- `0x18000a476`: `AslRegistryGetStringExpand`
- `0x18000a54f`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, __int64 a4)
{
  wchar_t *Heap; // rdi
  NTSTATUS String; // eax
  wchar_t *v8; // rsi
  int v9; // ebx
  int ProcessWowInfo; // eax
  __int64 v11; // r8
  __int16 v12; // r15
  __int16 v13; // r12
  wchar_t *v14; // rbx
  __int64 v16; // [rsp+28h] [rbp-30h]
  int v17; // [rsp+30h] [rbp-28h]
  __int16 v18[2]; // [rsp+40h] [rbp-18h] BYREF
  __int16 v19; // [rsp+44h] [rbp-14h] BYREF
  wchar_t *Str[2]; // [rsp+48h] [rbp-10h] BYREF

  Heap = 0;
  v18[0] = -1;
  Str[0] = 0;
  v19 = -1;
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
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v19, v18);
  v9 = ProcessWowInfo;
  if ( ProcessWowInfo >= 0 )
  {
    Str[0] = (wchar_t *)260;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    if ( !Heap )
    {
      v11 = 1476;
LABEL_8:
      AslLogCallPrintf(1, "AslRegistryGetStringExpand", v11, "Out of memory");
      v9 = -1073741801;
      goto LABEL_16;
    }
    v12 = v18[0];
    v13 = v19;
    v9 = AslEnvExpandStrings2(a4, v8, Heap, 260, Str, v19, v18[0]);
    if ( v9 == -1073741789 )
    {
      AslFree(NtCurrentPeb()->ProcessHeap, Heap);
      v14 = Str[0];
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (__int64)Str[0]);
      if ( !Heap )
      {
        v11 = 1494;
        goto LABEL_8;
      }
      LOWORD(v17) = v12;
      LOWORD(v16) = v13;
      v9 = AslEnvExpandStrings2(a4, v8, Heap, v14, Str, v16, v17);
    }
    if ( v9 >= 0 )
    {
      *a1 = Heap;
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
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a39c  push    rbp
0x18000a39e  push    rbx
0x18000a39f  push    rsi
0x18000a3a0  push    rdi
0x18000a3a1  push    r12
0x18000a3a3  push    r13
0x18000a3a5  push    r14
0x18000a3a7  push    r15
0x18000a3a9  mov     rbp, rsp
0x18000a3ac  sub     rsp, 58h
0x18000a3b0  mov     eax, 0FFFFh
0x18000a3b5  mov     r14, rcx
0x18000a3b8  xor     edi, edi
0x18000a3ba  mov     [rbp+var_18], ax
0x18000a3be  lea     rcx, [rbp+Str]
0x18000a3c2  mov     [rbp+Str], rdi
0x18000a3c6  mov     [rbp+var_14], ax
0x18000a3ca  mov     r13, r9
0x18000a3cd  call    AslRegistryGetString
0x18000a3d2  mov     rsi, [rbp+Str]
0x18000a3d6  mov     ebx, eax
0x18000a3d8  test    eax, eax
0x18000a3da  js      loc_18000A569
0x18000a3e0  lea     edx, [rdi+25h]; Ch
0x18000a3e3  mov     rcx, rsi; Str
0x18000a3e6  call    cs:__imp_wcschr
0x18000a3ec  test    rax, rax
0x18000a3ef  jnz     short loc_18000A3FB
0x18000a3f1  mov     [r14], rsi
0x18000a3f4  xor     ebx, ebx
0x18000a3f6  jmp     loc_18000A59D
0x18000a3fb  lea     rdx, [rbp+var_18]
0x18000a3ff  lea     rcx, [rbp+var_14]
0x18000a403  call    AslEnvGetProcessWowInfo
0x18000a408  mov     ebx, eax
0x18000a40a  test    eax, eax
0x18000a40c  jns     short loc_18000A435
0x18000a40e  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x18000a415  mov     dword ptr [rsp+58h+var_38], eax
0x18000a419  mov     r8d, 5B8h
0x18000a41f  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18000a426  mov     ecx, 1
0x18000a42b  call    AslLogCallPrintf
0x18000a430  jmp     loc_18000A569
0x18000a435  mov     rcx, gs:60h
0x18000a43e  mov     ebx, 104h
0x18000a443  mov     edx, 8; Flags
0x18000a448  mov     [rbp+Str], rbx
0x18000a44c  mov     r8d, 208h; Size
0x18000a452  mov     rcx, [rcx+30h]; HeapHandle
0x18000a456  call    cs:__imp_RtlAllocateHeap
0x18000a45c  mov     rdi, rax
0x18000a45f  test    rax, rax
0x18000a462  jnz     short loc_18000A48C
0x18000a464  mov     r8d, 5C4h
0x18000a46a  lea     r9, aOutOfMemory; "Out of memory"
0x18000a471  mov     ecx, 1
0x18000a476  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18000a47d  call    AslLogCallPrintf
0x18000a482  mov     ebx, 0C0000017h
0x18000a487  jmp     loc_18000A569
0x18000a48c  movzx   r15d, [rbp+var_18]
0x18000a491  lea     rax, [rbp+Str]
0x18000a495  movzx   r12d, [rbp+var_14]
0x18000a49a  mov     r9, rbx
0x18000a49d  mov     word ptr [rsp+58h+var_28], r15w
0x18000a4a3  mov     r8, rdi
0x18000a4a6  mov     word ptr [rsp+58h+var_30], r12w
0x18000a4ac  mov     rdx, rsi
0x18000a4af  mov     rcx, r13
0x18000a4b2  mov     [rsp+58h+var_38], rax
0x18000a4b7  call    AslEnvExpandStrings2
0x18000a4bc  mov     ebx, eax
0x18000a4be  cmp     eax, 0C0000023h
0x18000a4c3  jnz     short loc_18000A535
0x18000a4c5  mov     rcx, gs:60h
0x18000a4ce  mov     rdx, rdi
0x18000a4d1  mov     rcx, [rcx+30h]
0x18000a4d5  call    AslFree
0x18000a4da  mov     rcx, gs:60h
0x18000a4e3  mov     edx, 8; Flags
0x18000a4e8  mov     rbx, [rbp+Str]
0x18000a4ec  mov     rcx, [rcx+30h]; HeapHandle
0x18000a4f0  lea     r8, [rbx+rbx]; Size
0x18000a4f4  call    cs:__imp_RtlAllocateHeap
0x18000a4fa  mov     rdi, rax
0x18000a4fd  test    rax, rax
0x18000a500  jnz     short loc_18000A50D
0x18000a502  mov     r8d, 5D6h
0x18000a508  jmp     loc_18000A46A
0x18000a50d  mov     word ptr [rsp+58h+var_28], r15w
0x18000a513  lea     rax, [rbp+Str]
0x18000a517  mov     word ptr [rsp+58h+var_30], r12w
0x18000a51d  mov     r9, rbx
0x18000a520  mov     r8, rdi
0x18000a523  mov     [rsp+58h+var_38], rax
0x18000a528  mov     rdx, rsi
0x18000a52b  mov     rcx, r13
0x18000a52e  call    AslEnvExpandStrings2
0x18000a533  mov     ebx, eax
0x18000a535  test    ebx, ebx
0x18000a537  jns     short loc_18000A562
0x18000a539  mov     dword ptr [rsp+58h+var_30], ebx
0x18000a53d  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x18000a544  mov     r8d, 5E5h
0x18000a54a  mov     [rsp+58h+var_38], rsi
0x18000a54f  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x18000a556  mov     ecx, 1
0x18000a55b  call    AslLogCallPrintf
0x18000a560  jmp     short loc_18000A569
0x18000a562  mov     [r14], rdi
0x18000a565  xor     edi, edi
0x18000a567  xor     ebx, ebx
0x18000a569  test    rsi, rsi
0x18000a56c  jz      short loc_18000A583
0x18000a56e  mov     rcx, gs:60h
0x18000a577  mov     rdx, rsi
0x18000a57a  mov     rcx, [rcx+30h]
0x18000a57e  call    AslFree
0x18000a583  test    rdi, rdi
0x18000a586  jz      short loc_18000A59D
0x18000a588  mov     rcx, gs:60h
0x18000a591  mov     rdx, rdi
0x18000a594  mov     rcx, [rcx+30h]
0x18000a598  call    AslFree
0x18000a59d  mov     eax, ebx
0x18000a59f  add     rsp, 58h
0x18000a5a3  pop     r15
0x18000a5a5  pop     r14
0x18000a5a7  pop     r13
0x18000a5a9  pop     r12
0x18000a5ab  pop     rdi
0x18000a5ac  pop     rsi
0x18000a5ad  pop     rbx
0x18000a5ae  pop     rbp
0x18000a5af  retn
```
