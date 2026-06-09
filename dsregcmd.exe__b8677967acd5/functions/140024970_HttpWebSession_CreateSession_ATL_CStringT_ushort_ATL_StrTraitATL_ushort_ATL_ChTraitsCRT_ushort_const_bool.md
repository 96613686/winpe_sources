# HttpWebSession::CreateSession(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)

- ea: `0x140024970`
- end: `0x1400249ea`
- name: `?CreateSession@HttpWebSession@@MEAAPEAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z`
- size: `122`
- prototype: `HINTERNET __fastcall(__int64, const WCHAR **, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400054e8`
- `0x140023430`
- `0x140024970`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400249c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400249c3`
- `WINHTTP!WinHttpOpen` at `0x14002499e`
- `WINHTTP!WinHttpOpen` at `0x14002499e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HINTERNET __fastcall HttpWebSession::CreateSession(__int64 a1, const WCHAR **a2, unsigned __int8 a3)
{
  DWORD dwFlags; // eax
  const WCHAR *v4; // r8
  DWORD v5; // edx
  HINTERNET result; // rax
  _QWORD *v7; // rbx
  DWORD LastError; // eax
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  dwFlags = a3 << 28;
  v4 = *a2;
  if ( *((_DWORD *)*a2 - 4) )
  {
    v5 = 3;
  }
  else
  {
    v4 = 0;
    v5 = 4;
  }
  result = WinHttpOpen(0, v5, v4, 0, dwFlags);
  if ( !result )
  {
    v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v10,
           (__int64)&dword_14003353C);
    LastError = GetLastError();
    HttpException::HttpException(pExceptionObject, LastError, v7);
    throw (HttpException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x140024970  push    rbx
0x140024972  sub     rsp, 50h
0x140024976  movzx   eax, r8b
0x14002497a  shl     eax, 1Ch
0x14002497d  mov     r8, [rdx]; pszProxyW
0x140024980  cmp     dword ptr [r8-10h], 0
0x140024985  jnz     short loc_140024990
0x140024987  xor     r8d, r8d
0x14002498a  lea     edx, [r8+4]
0x14002498e  jmp     short loc_140024995
0x140024990  mov     edx, 3; dwAccessType
0x140024995  mov     [rsp+58h+dwFlags], eax; dwFlags
0x140024999  xor     r9d, r9d; pszProxyBypassW
0x14002499c  xor     ecx, ecx; pszAgentW
0x14002499e  call    cs:__imp_WinHttpOpen
0x1400249a4  test    rax, rax
0x1400249a7  jz      short loc_1400249AF
0x1400249a9  add     rsp, 50h
0x1400249ad  pop     rbx
0x1400249ae  retn
0x1400249af  lea     rdx, dword_14003353C
0x1400249b6  lea     rcx, [rsp+58h+arg_8]
0x1400249bb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400249c0  mov     rbx, rax
0x1400249c3  call    cs:__imp_GetLastError
0x1400249c9  mov     r8, rbx
0x1400249cc  mov     edx, eax
0x1400249ce  lea     rcx, [rsp+58h+pExceptionObject]
0x1400249d3  call    ??0HttpException@@QEAA@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; HttpException::HttpException(ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400249d8  lea     rdx, _TI2?AVHttpException@@; pThrowInfo
0x1400249df  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1400249e4  call    _CxxThrowException_0
```
