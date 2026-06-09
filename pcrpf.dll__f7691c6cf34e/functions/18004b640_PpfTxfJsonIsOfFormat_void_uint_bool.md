# PpfTxfJsonIsOfFormat(void *,uint,bool *)

- ea: `0x18004b640`
- end: `0x18004b705`
- name: `?PpfTxfJsonIsOfFormat@@YAJPEAXIPEA_N@Z`
- size: `197`
- prototype: `__int64 __fastcall(_BYTE *, int, bool *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18002d5ec`
- `0x180043bc4`
- `0x18004b640`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b6a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b6a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b6bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b6bd`

## string_xrefs

- `0x18004b652`: `PpfTxfJsonIsOfFormat`

## pseudocode

```c
__int64 __fastcall PpfTxfJsonIsOfFormat(_BYTE *a1, int a2, bool *a3)
{
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  const char *v8; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID lpMem; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x84u,
      "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
      "Entering %hs",
      "PpfTxfJsonIsOfFormat");
    *a3 = 0;
    GetJsonStrFromTransform(&lpMem, a1, a2, (char *)a3);
    v6 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTxfJsonIsOfFormat");
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6A,
                           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfjson\\ppftxfjson.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18004b640  push    rbx
0x18004b642  push    rsi
0x18004b643  push    rdi
0x18004b644  push    r14
0x18004b646  sub     rsp, 48h
0x18004b64a  mov     rbx, r8
0x18004b64d  mov     edi, edx
0x18004b64f  mov     rsi, rcx
0x18004b652  lea     r14, aPpftxfjsonisof; "PpfTxfJsonIsOfFormat"
0x18004b659  mov     [rsp+68h+var_38], r14
0x18004b65e  mov     [rsp+68h+var_48], r14
0x18004b663  lea     r9, aEnteringHs; "Entering %hs"
0x18004b66a  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18004b671  mov     edx, 84h; unsigned int
0x18004b676  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18004b67d  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004b682  nop
0x18004b683  mov     byte ptr [rbx], 0
0x18004b686  mov     r9, rbx
0x18004b689  mov     r8d, edi
0x18004b68c  mov     rdx, rsi
0x18004b68f  lea     rcx, [rsp+68h+lpMem]
0x18004b697  call    ?GetJsonStrFromTransform@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXIPEA_N@Z; GetJsonStrFromTransform(void *,uint,bool *)
0x18004b69c  mov     rbx, [rsp+68h+lpMem]
0x18004b6a4  test    rbx, rbx
0x18004b6a7  jz      short loc_18004B6CA
0x18004b6a9  call    cs:__imp_GetProcessHeap
0x18004b6b0  nop     dword ptr [rax+rax+00h]
0x18004b6b5  mov     rcx, rax; hHeap
0x18004b6b8  mov     r8, rbx; lpMem
0x18004b6bb  xor     edx, edx; dwFlags
0x18004b6bd  call    cs:__imp_HeapFree
0x18004b6c4  nop     dword ptr [rax+rax+00h]
0x18004b6c9  nop
0x18004b6ca  mov     [rsp+68h+var_48], r14
0x18004b6cf  lea     r9, aLeavingHs; "Leaving %hs"
0x18004b6d6  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18004b6dd  mov     edx, 89h; unsigned int
0x18004b6e2  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18004b6e9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004b6ee  nop
0x18004b6ef  xor     eax, eax
0x18004b6f1  jmp     short loc_18004B6FA
0x18004b6f3  mov     eax, dword ptr [rsp+68h+lpMem]
0x18004b6fa  add     rsp, 48h
0x18004b6fe  pop     r14
0x18004b700  pop     rdi
0x18004b701  pop     rsi
0x18004b702  pop     rbx
0x18004b703  retn
```
