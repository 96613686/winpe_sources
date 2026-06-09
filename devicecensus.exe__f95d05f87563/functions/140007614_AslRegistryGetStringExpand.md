# AslRegistryGetStringExpand

- ea: `0x140007614`
- end: `0x140007831`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: `__int64 __fastcall(wchar_t **, void *, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140009c7c`

## callees

- `0x140007074`
- `0x140007448`
- `0x140007614`
- `0x14000b1f0`
- `0x14000b408`

## import_xrefs

- `msvcrt!wcschr` at `0x14000765e`
- `msvcrt!wcschr` at `0x14000765e`
- `ntdll!RtlFreeHeap` at `0x14000774f`
- `ntdll!RtlFreeHeap` at `0x1400077fb`
- `ntdll!RtlFreeHeap` at `0x140007818`
- `ntdll!RtlFreeHeap` at `0x14000774f`
- `ntdll!RtlFreeHeap` at `0x1400077fb`
- `ntdll!RtlFreeHeap` at `0x140007818`
- `ntdll!RtlAllocateHeap` at `0x1400076ce`
- `ntdll!RtlAllocateHeap` at `0x14000776f`
- `ntdll!RtlAllocateHeap` at `0x1400076ce`
- `ntdll!RtlAllocateHeap` at `0x14000776f`

## string_xrefs

- `0x140007697`: `AslRegistryGetStringExpand`
- `0x1400076ee`: `AslRegistryGetStringExpand`
- `0x1400077ca`: `AslRegistryGetStringExpand`

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
0x140007614  push    rbp
0x140007616  push    rbx
0x140007617  push    rsi
0x140007618  push    rdi
0x140007619  push    r12
0x14000761b  push    r13
0x14000761d  push    r14
0x14000761f  push    r15
0x140007621  mov     rbp, rsp
0x140007624  sub     rsp, 58h
0x140007628  mov     eax, 0FFFFh
0x14000762d  mov     r14, rcx
0x140007630  xor     edi, edi
0x140007632  mov     [rbp+var_18], ax
0x140007636  lea     rcx, [rbp+Str]
0x14000763a  mov     [rbp+Str], rdi
0x14000763e  mov     [rbp+var_14], ax
0x140007642  mov     r13, r9
0x140007645  call    AslRegistryGetString
0x14000764a  mov     rsi, [rbp+Str]
0x14000764e  mov     ebx, eax
0x140007650  test    eax, eax
0x140007652  js      loc_1400077E4
0x140007658  lea     edx, [rdi+25h]; Ch
0x14000765b  mov     rcx, rsi; Str
0x14000765e  call    cs:__imp_wcschr
0x140007664  test    rax, rax
0x140007667  jnz     short loc_140007673
0x140007669  mov     [r14], rsi
0x14000766c  xor     ebx, ebx
0x14000766e  jmp     loc_14000781E
0x140007673  lea     rdx, [rbp+var_18]
0x140007677  lea     rcx, [rbp+var_14]
0x14000767b  call    AslEnvGetProcessWowInfo
0x140007680  mov     ebx, eax
0x140007682  test    eax, eax
0x140007684  jns     short loc_1400076AD
0x140007686  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x14000768d  mov     dword ptr [rsp+58h+var_38], eax
0x140007691  mov     r8d, 5B8h
0x140007697  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x14000769e  mov     ecx, 1
0x1400076a3  call    AslLogCallPrintf
0x1400076a8  jmp     loc_1400077E4
0x1400076ad  mov     rcx, gs:60h
0x1400076b6  mov     ebx, 104h
0x1400076bb  mov     edx, 8; Flags
0x1400076c0  mov     [rbp+Str], rbx
0x1400076c4  mov     r8d, 208h; Size
0x1400076ca  mov     rcx, [rcx+30h]; HeapHandle
0x1400076ce  call    cs:__imp_RtlAllocateHeap
0x1400076d4  mov     rdi, rax
0x1400076d7  test    rax, rax
0x1400076da  jnz     short loc_140007704
0x1400076dc  mov     r8d, 5C4h
0x1400076e2  lea     r9, aOutOfMemory; "Out of memory"
0x1400076e9  mov     ecx, 1
0x1400076ee  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x1400076f5  call    AslLogCallPrintf
0x1400076fa  mov     ebx, 0C0000017h
0x1400076ff  jmp     loc_1400077E4
0x140007704  movzx   r15d, [rbp+var_18]
0x140007709  lea     rax, [rbp+Str]
0x14000770d  movzx   r12d, [rbp+var_14]
0x140007712  mov     r9, rbx
0x140007715  mov     [rsp+58h+var_28], r15w
0x14000771b  mov     r8, rdi
0x14000771e  mov     word ptr [rsp+58h+var_30], r12w
0x140007724  mov     rdx, rsi
0x140007727  mov     rcx, r13
0x14000772a  mov     [rsp+58h+var_38], rax
0x14000772f  call    AslEnvExpandStrings2
0x140007734  mov     ebx, eax
0x140007736  cmp     eax, 0C0000023h
0x14000773b  jnz     short loc_1400077B0
0x14000773d  mov     rcx, gs:60h
0x140007746  mov     r8, rdi; P
0x140007749  xor     edx, edx; Flags
0x14000774b  mov     rcx, [rcx+30h]; HeapHandle
0x14000774f  call    cs:__imp_RtlFreeHeap
0x140007755  mov     rcx, gs:60h
0x14000775e  mov     edx, 8; Flags
0x140007763  mov     rbx, [rbp+Str]
0x140007767  mov     rcx, [rcx+30h]; HeapHandle
0x14000776b  lea     r8, [rbx+rbx]; Size
0x14000776f  call    cs:__imp_RtlAllocateHeap
0x140007775  mov     rdi, rax
0x140007778  test    rax, rax
0x14000777b  jnz     short loc_140007788
0x14000777d  mov     r8d, 5D6h
0x140007783  jmp     loc_1400076E2
0x140007788  mov     [rsp+58h+var_28], r15w
0x14000778e  lea     rax, [rbp+Str]
0x140007792  mov     word ptr [rsp+58h+var_30], r12w
0x140007798  mov     r9, rbx
0x14000779b  mov     r8, rdi
0x14000779e  mov     [rsp+58h+var_38], rax
0x1400077a3  mov     rdx, rsi
0x1400077a6  mov     rcx, r13
0x1400077a9  call    AslEnvExpandStrings2
0x1400077ae  mov     ebx, eax
0x1400077b0  test    ebx, ebx
0x1400077b2  jns     short loc_1400077DD
0x1400077b4  mov     dword ptr [rsp+58h+var_30], ebx
0x1400077b8  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x1400077bf  mov     r8d, 5E5h
0x1400077c5  mov     [rsp+58h+var_38], rsi
0x1400077ca  lea     rdx, aAslregistryget_3; "AslRegistryGetStringExpand"
0x1400077d1  mov     ecx, 1
0x1400077d6  call    AslLogCallPrintf
0x1400077db  jmp     short loc_1400077E4
0x1400077dd  mov     [r14], rdi
0x1400077e0  xor     edi, edi
0x1400077e2  xor     ebx, ebx
0x1400077e4  test    rsi, rsi
0x1400077e7  jz      short loc_140007801
0x1400077e9  mov     rcx, gs:60h
0x1400077f2  mov     r8, rsi; P
0x1400077f5  xor     edx, edx; Flags
0x1400077f7  mov     rcx, [rcx+30h]; HeapHandle
0x1400077fb  call    cs:__imp_RtlFreeHeap
0x140007801  test    rdi, rdi
0x140007804  jz      short loc_14000781E
0x140007806  mov     rcx, gs:60h
0x14000780f  mov     r8, rdi; P
0x140007812  xor     edx, edx; Flags
0x140007814  mov     rcx, [rcx+30h]; HeapHandle
0x140007818  call    cs:__imp_RtlFreeHeap
0x14000781e  mov     eax, ebx
0x140007820  add     rsp, 58h
0x140007824  pop     r15
0x140007826  pop     r14
0x140007828  pop     r13
0x14000782a  pop     r12
0x14000782c  pop     rdi
0x14000782d  pop     rsi
0x14000782e  pop     rbx
0x14000782f  pop     rbp
0x140007830  retn
```
