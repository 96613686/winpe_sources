# ReplaceAllSBVars(wistd::unique_ptr<uchar,wil::process_heap_deleter> &,uint &,ushort,ushort,PPF_TRANSFORM_CONTEXT *,unsigned __int64 *)

- ea: `0x180017458`
- end: `0x18001764a`
- name: `?ReplaceAllSBVars@@YAJAEAV?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@AEAIGGPEAUPPF_TRANSFORM_CONTEXT@@PEA_K@Z`
- size: `498`
- prototype: `__int64 __fastcall(void **, _DWORD *, __int16, __int16, char *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800107e8`

## callees

- `0x180009c64`
- `0x180013e6c`
- `0x180017458`
- `0x180017a80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017517`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800175d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017517`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800175d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001752b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800175a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800175ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001752b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800175a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800175ea`

## string_xrefs

- `0x180017562`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017617`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180017553`: `Failed to replace SB var '%ws'`

## pseudocode

```c
__int64 __fastcall ReplaceAllSBVars(void **a1, _DWORD *a2, __int16 a3, __int16 a4, char *a5, _QWORD *a6)
{
  __int16 v6; // ax
  int v9; // ebx
  __int64 i; // rdi
  int v11; // esi
  void *v12; // r14
  HANDLE ProcessHeap; // rax
  LPVOID v14; // rax
  void *v15; // rsi
  HANDLE v16; // rax
  void *v17; // rsi
  HANDLE v18; // rax
  int v20; // [rsp+20h] [rbp-60h]
  __int64 v21; // [rsp+50h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-28h] BYREF
  LPVOID *p_lpMem; // [rsp+60h] [rbp-20h]
  size_t Size; // [rsp+68h] [rbp-18h] BYREF
  char v25; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int16 v27; // [rsp+D0h] [rbp+50h]

  v27 = a3;
  v6 = a4;
  v9 = 0;
  for ( i = 0; i != 4; ++i )
  {
    lpMem = 0;
    LODWORD(v21) = 0;
    p_lpMem = &lpMem;
    Size = 0;
    v25 = 1;
    v11 = ReplaceSBVarInPpfEventLogIfPresent(*a1, (unsigned int)*a2, a3, v6, a5, (size_t)&Size, (__int64)&v21);
    if ( v25 )
    {
      v12 = *p_lpMem;
      *p_lpMem = (LPVOID)Size;
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
    }
    if ( v11 >= 0 )
    {
      v14 = lpMem;
      lpMem = 0;
      v15 = *a1;
      *a1 = v14;
      if ( v15 )
      {
        v16 = GetProcessHeap();
        HeapFree(v16, 0, v15);
      }
      *a2 = v21;
      *a6 |= (unsigned __int64)(&g_sbVarPredictedStates)[i];
    }
    else
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v11,
        (int)"Failed to replace SB var '%ws'",
        (const char *)(&g_sbVarNames)[i]);
      if ( v9 >= 0 )
        v9 = v11;
    }
    v17 = lpMem;
    lpMem = 0;
    if ( v17 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v17);
    }
    v6 = a4;
    a3 = v27;
  }
  if ( v9 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x94,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
    (const char *)(unsigned int)v9,
    v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180017458  mov     [rsp-38h+arg_0], rbx
0x18001745d  mov     [rsp-38h+arg_18], r9w
0x180017463  mov     [rsp-38h+arg_10], r8w
0x180017469  push    rbp
0x18001746a  push    rsi
0x18001746b  push    rdi
0x18001746c  push    r12
0x18001746e  push    r13
0x180017470  push    r14
0x180017472  push    r15
0x180017474  mov     rbp, rsp
0x180017477  sub     rsp, 80h
0x18001747e  movzx   eax, r9w
0x180017482  mov     r13, rdx
0x180017485  mov     r15, rcx
0x180017488  xor     ebx, ebx
0x18001748a  xor     edi, edi
0x18001748c  lea     r14, __ImageBase
0x180017493  mov     r12, [rbp+arg_28]
0x180017497  mov     [rbp+lpMem], 0
0x18001749f  mov     dword ptr [rbp+var_30], 0
0x1800174a6  lea     rcx, [rbp+lpMem]
0x1800174aa  mov     [rbp+var_20], rcx
0x1800174ae  mov     [rbp+var_18], 0
0x1800174b6  mov     [rbp+var_10], 1
0x1800174ba  lea     rcx, [rbp+var_30]
0x1800174be  mov     [rsp+80h+var_40], rcx; __int64
0x1800174c3  lea     rcx, [rbp+var_18]
0x1800174c7  mov     [rsp+80h+Size], rcx; Size
0x1800174cc  mov     rcx, [rbp+arg_20]
0x1800174d0  mov     [rsp+80h+var_50], rcx; char *
0x1800174d5  mov     word ptr [rsp+80h+var_58], ax; __int16
0x1800174da  mov     [rsp+80h+var_60], r8w; int
0x1800174e0  mov     r9, ds:rva ?g_sbVarNames@@3PAPEBGA[r14+rdi*8]; ushort const * near * g_sbVarNames ...
0x1800174e8  mov     r8, qword ptr ds:rva ?g_sbVarNamespaces@@3PAPEAU_GUID@@A.Data1[r14+rdi*8]; _GUID * near * g_sbVarNamespaces ...
0x1800174f0  mov     edx, [r13+0]; dwBytes
0x1800174f4  mov     rcx, [r15]; Src
0x1800174f7  call    ReplaceSBVarInPpfEventLogIfPresent
0x1800174fc  mov     esi, eax
0x1800174fe  cmp     [rbp+var_10], 0
0x180017502  jz      short loc_18001753E
0x180017504  mov     rcx, [rbp+var_20]
0x180017508  mov     r14, [rcx]
0x18001750b  mov     rax, [rbp+var_18]
0x18001750f  mov     [rcx], rax
0x180017512  test    r14, r14
0x180017515  jz      short loc_180017537
0x180017517  call    cs:__imp_GetProcessHeap
0x18001751e  nop     dword ptr [rax+rax+00h]
0x180017523  mov     rcx, rax; hHeap
0x180017526  mov     r8, r14; lpMem
0x180017529  xor     edx, edx; dwFlags
0x18001752b  call    cs:__imp_HeapFree
0x180017532  nop     dword ptr [rax+rax+00h]
0x180017537  lea     r14, __ImageBase
0x18001753e  test    esi, esi
0x180017540  jns     short loc_18001757B
0x180017542  mov     rcx, [rbp+38h]; this
0x180017546  mov     rax, ds:rva ?g_sbVarNames@@3PAPEBGA[r14+rdi*8]; ushort const * near * g_sbVarNames ...
0x18001754e  mov     [rsp+80h+var_58], rax; char *
0x180017553  lea     rax, aFailedToReplac; "Failed to replace SB var '%ws'"
0x18001755a  mov     qword ptr [rsp+80h+var_60], rax; int
0x18001755f  mov     r9d, esi; char *
0x180017562  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180017569  mov     edx, 87h; void *
0x18001756e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017573  test    ebx, ebx
0x180017575  js      short loc_1800175C5
0x180017577  mov     ebx, esi
0x180017579  jmp     short loc_1800175C5
0x18001757b  mov     rax, [rbp+lpMem]
0x18001757f  mov     [rbp+lpMem], 0
0x180017587  mov     rsi, [r15]
0x18001758a  mov     [r15], rax
0x18001758d  test    rsi, rsi
0x180017590  jz      short loc_1800175B2
0x180017592  call    cs:__imp_GetProcessHeap
0x180017599  nop     dword ptr [rax+rax+00h]
0x18001759e  mov     rcx, rax; hHeap
0x1800175a1  mov     r8, rsi; lpMem
0x1800175a4  xor     edx, edx; dwFlags
0x1800175a6  call    cs:__imp_HeapFree
0x1800175ad  nop     dword ptr [rax+rax+00h]
0x1800175b2  mov     eax, dword ptr [rbp+var_30]
0x1800175b5  mov     [r13+0], eax
0x1800175b9  mov     rax, ds:rva ?g_sbVarPredictedStates@@3PA_KA[r14+rdi*8]; unsigned __int64 near * g_sbVarPredictedStates ...
0x1800175c1  or      [r12], rax
0x1800175c5  mov     rsi, [rbp+lpMem]
0x1800175c9  mov     [rbp+lpMem], 0
0x1800175d1  test    rsi, rsi
0x1800175d4  jz      short loc_1800175F6
0x1800175d6  call    cs:__imp_GetProcessHeap
0x1800175dd  nop     dword ptr [rax+rax+00h]
0x1800175e2  mov     rcx, rax; hHeap
0x1800175e5  mov     r8, rsi; lpMem
0x1800175e8  xor     edx, edx; dwFlags
0x1800175ea  call    cs:__imp_HeapFree
0x1800175f1  nop     dword ptr [rax+rax+00h]
0x1800175f6  inc     rdi
0x1800175f9  cmp     rdi, 4
0x1800175fd  movzx   eax, [rbp+arg_18]
0x180017601  movzx   r8d, [rbp+arg_10]
0x180017606  jnz     loc_180017497
0x18001760c  test    ebx, ebx
0x18001760e  jns     short loc_18001762C
0x180017610  mov     rcx, [rbp+38h]; this
0x180017614  mov     r9d, ebx; char *
0x180017617  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001761e  mov     edx, 94h; void *
0x180017623  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017628  mov     eax, ebx
0x18001762a  jmp     short loc_18001762E
0x18001762c  xor     eax, eax
0x18001762e  mov     rbx, [rsp+80h+arg_0]
0x180017636  add     rsp, 80h
0x18001763d  pop     r15
0x18001763f  pop     r14
0x180017641  pop     r13
0x180017643  pop     r12
0x180017645  pop     rdi
0x180017646  pop     rsi
0x180017647  pop     rbp
0x180017648  retn
```
