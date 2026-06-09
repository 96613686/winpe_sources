# WcmProvisioningUtil::CreateStreamFromArray<char>(char const *,uint,IStream * *)

- ea: `0x180060d40`
- end: `0x180060de0`
- name: `??$CreateStreamFromArray@D@WcmProvisioningUtil@@YAJPEBDIPEAPEAUIStream@@@Z`
- size: `160`
- prototype: `HRESULT __fastcall(const char *Array, unsigned int NumElements, IStream **ppStream)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180061e10`

## callees

- `0x1800032c4`
- `0x1800071d4`
- `0x180060d40`
- `0x180062c98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180060db5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180060db5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180060d5a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180060d5a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180060d6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180060d6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180060d8a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180060d8a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180060d9b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180060d9b`

## string_xrefs

- `0x180060dc0`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
HRESULT __fastcall WcmProvisioningUtil::CreateStreamFromArray<char>(
        const char *Array,
        unsigned int NumElements,
        IStream **ppStream)
{
  HGLOBAL v6; // rax
  void *v7; // rbx
  void *v8; // rax
  void *v9; // rdi
  int StreamOnHGlobal; // eax
  unsigned int v11; // edx
  const char *v12; // r8
  void *retaddr; // [rsp+48h] [rbp+0h]

  v6 = GlobalAlloc(0x42u, NumElements);
  v7 = v6;
  if ( v6 )
  {
    v8 = GlobalLock(v6);
    v9 = v8;
    if ( !v8 )
    {
LABEL_5:
      GlobalFree(v7);
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               0x26u,
               "onecoreuap\\private\\net\\inc\\common\\utils\\WcmProvisioningUtil.h");
    }
    memcpy_0(v8, Array, NumElements);
    GlobalUnlock(v9);
    StreamOnHGlobal = CreateStreamOnHGlobal(v7, 1, ppStream);
    if ( StreamOnHGlobal < 0 )
    {
      wil::details::in1diag3::_Log_Hr(retaddr, v11, v12, StreamOnHGlobal);
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180060d40  push    rbx
0x180060d42  push    rbp
0x180060d43  push    rsi
0x180060d44  push    rdi
0x180060d45  push    r14
0x180060d47  sub     rsp, 20h
0x180060d4b  mov     r14, Array
0x180060d4e  mov     esi, NumElements
0x180060d50  mov     NumElements, NumElements; dwBytes
0x180060d52  mov     ecx, 42h ; 'B'; uFlags
0x180060d57  mov     rbp, ppStream
0x180060d5a  call    cs:__imp_GlobalAlloc
0x180060d60  mov     rbx, rax
0x180060d63  test    rax, rax
0x180060d66  jz      short loc_180060DD3
0x180060d68  mov     Array, rax; hMem
0x180060d6b  call    cs:__imp_GlobalLock
0x180060d71  mov     rdi, rax
0x180060d74  test    rax, rax
0x180060d77  jz      short loc_180060DB2
0x180060d79  mov     r8d, esi; Size
0x180060d7c  mov     rdx, r14; Src
0x180060d7f  mov     Array, rax; void *
0x180060d82  call    memcpy_0
0x180060d87  mov     Array, rdi; hMem
0x180060d8a  call    cs:__imp_GlobalUnlock
0x180060d90  mov     ppStream, rbp; ppstm
0x180060d93  mov     NumElements, 1; fDeleteOnRelease
0x180060d98  mov     Array, rbx; hGlobal
0x180060d9b  call    cs:__imp_CreateStreamOnHGlobal
0x180060da1  test    eax, eax
0x180060da3  jns     short loc_180060DD3
0x180060da5  mov     Array, [rsp+48h]; callerReturnAddress
0x180060daa  mov     r9d, eax; lineNumber
0x180060dad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060db2  mov     Array, rbx; hMem
0x180060db5  call    cs:__imp_GlobalFree
0x180060dbb  mov     Array, [rsp+48h]; callerReturnAddress
0x180060dc0  lea     ppStream, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\common\\"...
0x180060dc7  mov     NumElements, 26h ; '&'; lineNumber
0x180060dcc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180060dd1  jmp     short loc_180060DD5
0x180060dd3  xor     eax, eax
0x180060dd5  add     rsp, 20h
0x180060dd9  pop     r14
0x180060ddb  pop     rdi
0x180060ddc  pop     rsi
0x180060ddd  pop     rbp
0x180060dde  pop     rbx
0x180060ddf  retn
```
