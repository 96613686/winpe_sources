# Url::CreateUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14000f1b8`
- end: `0x14000f200`
- name: `?CreateUrl@Url@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `72`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140009b24`
- `0x14000d134`
- `0x14001088c`
- `0x14002266c`

## callees

- `0x140007bf8`
- `0x14000f1b8`
- `0x14000f254`
- `0x1400234dc`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f1dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f1dc`

## pseudocode

```c
__int64 __fastcall Url::CreateUrl(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-18h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)a1,
    a2);
  result = Url::Parse(*(LPURL_COMPONENTS *)(a1 + 8));
  if ( !(_BYTE)result )
  {
    LastError = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
    throw (Win32Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x14000f1b8  push    rbx
0x14000f1ba  sub     rsp, 30h
0x14000f1be  mov     rbx, rcx
0x14000f1c1  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000f1c6  mov     rcx, [rbx+8]; lpUrlComponents
0x14000f1ca  mov     rdx, rbx
0x14000f1cd  call    ?Parse@Url@@CA_NAEAUURLParts@1@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::Parse(Url::URLParts &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000f1d2  test    al, al
0x14000f1d4  jz      short loc_14000F1DC
0x14000f1d6  add     rsp, 30h
0x14000f1da  pop     rbx
0x14000f1db  retn
0x14000f1dc  call    cs:__imp_GetLastError
0x14000f1e2  mov     edx, eax; unsigned int
0x14000f1e4  lea     rcx, [rsp+38h+pExceptionObject]; this
0x14000f1e9  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14000f1ee  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14000f1f5  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x14000f1fa  call    _CxxThrowException_0
```
