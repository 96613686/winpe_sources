# PpfTxfIntGenerateBootMgFwTransform

- ea: `0x18001bd00`
- end: `0x18001be53`
- name: `PpfTxfIntGenerateBootMgFwTransform`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800181fc`
- `0x18001bd00`
- `0x180027eb0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bdc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001be25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bd73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bdc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001be25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bdd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001be39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bd87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bdd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001be39`

## string_xrefs

- `0x18001bd9b`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall PpfTxfIntGenerateBootMgFwTransform(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // edi
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v11; // eax
  void *v12; // rbx
  unsigned int v13; // edi
  HANDLE v14; // rax
  unsigned int v16; // eax
  void *v17; // rdi
  unsigned int v18; // ebx
  HANDLE v19; // rax
  unsigned int v20; // [rsp+40h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-28h] BYREF
  LPVOID *p_lpMem; // [rsp+50h] [rbp-20h]
  void *v23; // [rsp+58h] [rbp-18h] BYREF
  char v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  lpMem = 0;
  v20 = 0;
  v23 = 0;
  v24 = 1;
  p_lpMem = &lpMem;
  v8 = PpfEvtLogCreateFromTcgLog(a2, a3, &v23, &v20, 0);
  if ( v24 )
  {
    v9 = *p_lpMem;
    *p_lpMem = v23;
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  if ( v8 >= 0 )
  {
    v16 = ((__int64 (__fastcall *)(_QWORD, LPVOID, _QWORD, __int64, __int64, __int64))off_180072050)(
            a1,
            lpMem,
            v20,
            a4,
            a5,
            a6);
    v17 = lpMem;
    v18 = v16;
    lpMem = 0;
    if ( v17 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v17);
    }
    return v18;
  }
  else
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x695,
            (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
            (const char *)(unsigned int)v8);
    v12 = lpMem;
    v13 = v11;
    lpMem = 0;
    if ( v12 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v12);
    }
    return v13;
  }
}

```

## disassembly

```asm
0x18001bd00  push    rbp
0x18001bd02  push    rbx
0x18001bd03  push    rsi
0x18001bd04  push    rdi
0x18001bd05  push    r14
0x18001bd07  mov     rbp, rsp
0x18001bd0a  sub     rsp, 70h
0x18001bd0e  mov     r14d, ecx
0x18001bd11  mov     [rbp+lpMem], 0
0x18001bd19  mov     eax, r8d
0x18001bd1c  mov     [rbp+var_30], 0
0x18001bd23  mov     r10, rdx
0x18001bd26  mov     [rbp+var_18], 0
0x18001bd2e  lea     rcx, [rbp+lpMem]
0x18001bd32  mov     [rbp+var_10], 1
0x18001bd36  mov     [rbp+var_20], rcx
0x18001bd3a  lea     r8, [rbp+var_18]
0x18001bd3e  mov     rsi, r9
0x18001bd41  mov     qword ptr [rsp+70h+var_50], 0; int
0x18001bd4a  mov     rcx, r10
0x18001bd4d  lea     r9, [rbp+var_30]
0x18001bd51  mov     edx, eax
0x18001bd53  call    PpfEvtLogCreateFromTcgLog
0x18001bd58  cmp     [rbp+var_10], 0
0x18001bd5c  mov     edi, eax
0x18001bd5e  jz      short loc_18001BD93
0x18001bd60  mov     rdx, [rbp+var_20]
0x18001bd64  mov     rcx, [rbp+var_18]
0x18001bd68  mov     rbx, [rdx]
0x18001bd6b  mov     [rdx], rcx
0x18001bd6e  test    rbx, rbx
0x18001bd71  jz      short loc_18001BD93
0x18001bd73  call    cs:__imp_GetProcessHeap
0x18001bd7a  nop     dword ptr [rax+rax+00h]
0x18001bd7f  mov     r8, rbx; lpMem
0x18001bd82  xor     edx, edx; dwFlags
0x18001bd84  mov     rcx, rax; hHeap
0x18001bd87  call    cs:__imp_HeapFree
0x18001bd8e  nop     dword ptr [rax+rax+00h]
0x18001bd93  test    edi, edi
0x18001bd95  jns     short loc_18001BDE6
0x18001bd97  mov     rcx, [rbp+28h]; this
0x18001bd9b  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001bda2  mov     r9d, edi; char *
0x18001bda5  mov     edx, 695h; void *
0x18001bdaa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001bdaf  mov     rbx, [rbp+lpMem]
0x18001bdb3  mov     edi, eax
0x18001bdb5  mov     [rbp+lpMem], 0
0x18001bdbd  test    rbx, rbx
0x18001bdc0  jz      short loc_18001BDE2
0x18001bdc2  call    cs:__imp_GetProcessHeap
0x18001bdc9  nop     dword ptr [rax+rax+00h]
0x18001bdce  mov     r8, rbx; lpMem
0x18001bdd1  xor     edx, edx; dwFlags
0x18001bdd3  mov     rcx, rax; hHeap
0x18001bdd6  call    cs:__imp_HeapFree
0x18001bddd  nop     dword ptr [rax+rax+00h]
0x18001bde2  mov     eax, edi
0x18001bde4  jmp     short loc_18001BE47
0x18001bde6  mov     rcx, [rbp+arg_28]
0x18001bdea  mov     r9, rsi
0x18001bded  mov     r8d, [rbp+var_30]
0x18001bdf1  mov     rdx, [rbp+lpMem]
0x18001bdf5  mov     rax, cs:off_180072050
0x18001bdfc  mov     [rsp+70h+var_48], rcx
0x18001be01  mov     rcx, [rbp+arg_20]
0x18001be05  mov     qword ptr [rsp+70h+var_50], rcx
0x18001be0a  mov     ecx, r14d
0x18001be0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be12  mov     rdi, [rbp+lpMem]
0x18001be16  mov     ebx, eax
0x18001be18  mov     [rbp+lpMem], 0
0x18001be20  test    rdi, rdi
0x18001be23  jz      short loc_18001BE45
0x18001be25  call    cs:__imp_GetProcessHeap
0x18001be2c  nop     dword ptr [rax+rax+00h]
0x18001be31  mov     r8, rdi; lpMem
0x18001be34  xor     edx, edx; dwFlags
0x18001be36  mov     rcx, rax; hHeap
0x18001be39  call    cs:__imp_HeapFree
0x18001be40  nop     dword ptr [rax+rax+00h]
0x18001be45  mov     eax, ebx
0x18001be47  add     rsp, 70h
0x18001be4b  pop     r14
0x18001be4d  pop     rdi
0x18001be4e  pop     rsi
0x18001be4f  pop     rbx
0x18001be50  pop     rbp
0x18001be51  retn
```
