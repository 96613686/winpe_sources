# HttpWebRequest::OpenRequest(void)

- ea: `0x140028860`
- end: `0x14002894b`
- name: `?OpenRequest@HttpWebRequest@@MEAAXXZ`
- size: `235`
- prototype: `void __fastcall(HttpWebRequest *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path`

## callees

- `0x14000f058`
- `0x1400234dc`
- `0x140028860`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028927`
- `WINHTTP!WinHttpOpenRequest` at `0x1400288dd`
- `WINHTTP!WinHttpOpenRequest` at `0x1400288dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HttpWebRequest::OpenRequest(HttpWebRequest *this)
{
  int v2; // ebx
  DWORD dwFlags; // eax
  bool v4; // zf
  LPCWSTR v5; // rbx
  DWORD LastError; // eax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-18h] BYREF
  LPCWSTR pwszObjectName; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(*((_QWORD *)this + 13) + 20LL);
  _InterlockedExchange((volatile __int32 *)this + 22, 13);
  if ( *((_QWORD *)this + 19) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &pwszObjectName,
      *(_QWORD *)(*((_QWORD *)this + 13) + 72LL),
      (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 13) + 80LL) + *(_DWORD *)(*((_QWORD *)this + 13) + 96LL)));
    dwFlags = 0;
    v4 = v2 == 2;
    v5 = pwszObjectName;
    if ( v4 )
      dwFlags = 0x800000;
    *((_QWORD *)this + 20) = WinHttpOpenRequest(
                               *((HINTERNET *)this + 19),
                               *((LPCWSTR *)this + 4),
                               pwszObjectName,
                               0,
                               0,
                               0,
                               dwFlags);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
    if ( !*((_QWORD *)this + 20) )
    {
      LastError = GetLastError();
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
      throw (Win32Exception *)pExceptionObject;
    }
    _InterlockedExchange((volatile __int32 *)this + 22, 14);
  }
}

```

## disassembly

```asm
0x140028860  mov     [rsp+arg_8], rbx
0x140028865  push    rdi
0x140028866  sub     rsp, 50h
0x14002886a  mov     rax, [rcx+68h]
0x14002886e  mov     rdi, rcx
0x140028871  mov     ebx, [rax+14h]
0x140028874  mov     eax, 0Dh
0x140028879  xchg    eax, [rcx+58h]
0x14002887c  cmp     qword ptr [rcx+98h], 0
0x140028884  jz      loc_14002891C
0x14002888a  mov     rdx, [rcx+68h]
0x14002888e  lea     rcx, [rsp+58h+pwszObjectName]
0x140028893  mov     r8d, [rdx+60h]
0x140028897  add     r8d, [rdx+50h]
0x14002889b  mov     rdx, [rdx+48h]
0x14002889f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x1400288a4  mov     rdx, [rdi+20h]; pwszVerb
0x1400288a8  xor     eax, eax
0x1400288aa  cmp     ebx, 2
0x1400288ad  mov     ecx, 800000h
0x1400288b2  mov     rbx, [rsp+58h+pwszObjectName]
0x1400288b7  cmovz   eax, ecx
0x1400288ba  mov     r8, rbx; pwszObjectName
0x1400288bd  mov     rcx, [rdi+98h]; hConnect
0x1400288c4  xor     r9d, r9d; pwszVersion
0x1400288c7  mov     [rsp+58h+dwFlags], eax; dwFlags
0x1400288cb  mov     [rsp+58h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x1400288d4  mov     [rsp+58h+pwszReferrer], 0; pwszReferrer
0x1400288dd  call    cs:__imp_WinHttpOpenRequest
0x1400288e3  mov     [rdi+0A0h], rax
0x1400288ea  lea     rdx, [rbx-18h]
0x1400288ee  or      eax, 0FFFFFFFFh
0x1400288f1  lock xadd [rdx+10h], eax
0x1400288f6  sub     eax, 1
0x1400288f9  jg      short loc_14002890A
0x1400288fb  mov     rcx, [rdx]
0x1400288fe  mov     rax, [rcx]
0x140028901  mov     rax, [rax+8]
0x140028905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002890a  cmp     qword ptr [rdi+0A0h], 0
0x140028912  jz      short loc_140028927
0x140028914  mov     eax, 0Eh
0x140028919  xchg    eax, [rdi+58h]
0x14002891c  mov     rbx, [rsp+58h+arg_8]
0x140028921  add     rsp, 50h
0x140028925  pop     rdi
0x140028926  retn
0x140028927  call    cs:__imp_GetLastError
0x14002892d  mov     edx, eax; unsigned int
0x14002892f  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140028934  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x140028939  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x140028940  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140028945  call    _CxxThrowException_0
```
