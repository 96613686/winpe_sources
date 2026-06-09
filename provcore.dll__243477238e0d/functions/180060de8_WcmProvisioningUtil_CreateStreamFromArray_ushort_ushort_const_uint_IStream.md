# WcmProvisioningUtil::CreateStreamFromArray<ushort>(ushort const *,uint,IStream * *)

- ea: `0x180060de8`
- end: `0x180060e8c`
- name: `??$CreateStreamFromArray@G@WcmProvisioningUtil@@YAJPEBGIPEAPEAUIStream@@@Z`
- size: `164`
- prototype: `HRESULT __fastcall(const wchar_t *Array, unsigned int NumElements, IStream **ppStream)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180061e10`

## callees

- `0x1800032c4`
- `0x1800071d4`
- `0x180060de8`
- `0x180062c98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180060e61`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180060e61`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180060e06`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180060e06`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180060e17`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180060e17`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180060e36`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180060e36`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180060e47`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180060e47`

## string_xrefs

- `0x180060e6c`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
HRESULT __fastcall WcmProvisioningUtil::CreateStreamFromArray<unsigned short>(
        const wchar_t *Array,
        unsigned int NumElements,
        IStream **ppStream)
{
  SIZE_T v4; // rsi
  HGLOBAL v6; // rax
  void *v7; // rbx
  void *v8; // rax
  void *v9; // rdi
  int StreamOnHGlobal; // eax
  unsigned int v11; // edx
  const char *v12; // r8
  void *retaddr; // [rsp+48h] [rbp+0h]

  v4 = 2LL * NumElements;
  v6 = GlobalAlloc(0x42u, v4);
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
    memcpy_0(v8, Array, v4);
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
0x180060de8  push    rbx
0x180060dea  push    rbp
0x180060deb  push    rsi
0x180060dec  push    rdi
0x180060ded  push    r14
0x180060def  sub     rsp, 20h
0x180060df3  mov     esi, NumElements
0x180060df5  mov     r14, Array
0x180060df8  add     rsi, rsi
0x180060dfb  mov     ecx, 42h ; 'B'; uFlags
0x180060e00  mov     rdx, rsi; dwBytes
0x180060e03  mov     rbp, ppStream
0x180060e06  call    cs:__imp_GlobalAlloc
0x180060e0c  mov     rbx, rax
0x180060e0f  test    rax, rax
0x180060e12  jz      short loc_180060E7F
0x180060e14  mov     Array, rax; hMem
0x180060e17  call    cs:__imp_GlobalLock
0x180060e1d  mov     rdi, rax
0x180060e20  test    rax, rax
0x180060e23  jz      short loc_180060E5E
0x180060e25  mov     ppStream, rsi; Size
0x180060e28  mov     rdx, r14; Src
0x180060e2b  mov     Array, rax; void *
0x180060e2e  call    memcpy_0
0x180060e33  mov     Array, rdi; hMem
0x180060e36  call    cs:__imp_GlobalUnlock
0x180060e3c  mov     ppStream, rbp; ppstm
0x180060e3f  mov     NumElements, 1; fDeleteOnRelease
0x180060e44  mov     Array, rbx; hGlobal
0x180060e47  call    cs:__imp_CreateStreamOnHGlobal
0x180060e4d  test    eax, eax
0x180060e4f  jns     short loc_180060E7F
0x180060e51  mov     Array, [rsp+48h]; callerReturnAddress
0x180060e56  mov     r9d, eax; lineNumber
0x180060e59  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060e5e  mov     Array, rbx; hMem
0x180060e61  call    cs:__imp_GlobalFree
0x180060e67  mov     Array, [rsp+48h]; callerReturnAddress
0x180060e6c  lea     ppStream, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\common\\"...
0x180060e73  mov     NumElements, 26h ; '&'; lineNumber
0x180060e78  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180060e7d  jmp     short loc_180060E81
0x180060e7f  xor     eax, eax
0x180060e81  add     rsp, 20h
0x180060e85  pop     r14
0x180060e87  pop     rdi
0x180060e88  pop     rsi
0x180060e89  pop     rbp
0x180060e8a  pop     rbx
0x180060e8b  retn
```
