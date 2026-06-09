# CAdoSecurityHack::GetSite(_GUID const &,void * *)

- ea: `0x1800378f0`
- end: `0x180037a2b`
- name: `?GetSite@CAdoSecurityHack@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `315`
- prototype: `int(CAdoSecurityHack *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180013870`
- `0x180029560`
- `0x1800378f0`
- `0x180087010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180037910`
- `KERNEL32!GetCurrentThreadId` at `0x180037910`
- `ole32!CoUnmarshalInterface` at `0x1800379b9`
- `ole32!CoUnmarshalInterface` at `0x1800379b9`

## string_xrefs

- `0x18003794c`: `<CAdoSecurityHack::GetSite|OLEDB|ERR> `
- `0x1800379d4`: `<CAdoSecurityHack::GetSite|OLEDB|ERR> `
- `0x180037973`: `<CAdoSecurityHack::GetSite|Trace|HR> `
- `0x180037a0a`: `<CAdoSecurityHack::GetSite|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CAdoSecurityHack::GetSite(CAdoSecurityHack *this, const struct _GUID *a2, void **a3)
{
  int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  IStream *v10; // rdi

  if ( *((_QWORD *)this + 2) )
  {
    v6 = *((_DWORD *)this + 8);
    if ( v6 == GetCurrentThreadId() )
    {
      v7 = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 2))(
             *((_QWORD *)this + 2),
             a2,
             a3);
      v8 = v7;
      if ( v7 >= 0 )
        goto LABEL_15;
      if ( (bidGblFlags & 2) == 0 )
        return v8;
      OLEDBTraceErr(v7, L"<CAdoSecurityHack::GetSite|OLEDB|ERR> ", 0x89u);
      if ( (bidGblFlags & 2) == 0 )
        return v8;
      v9 = 140297;
    }
    else
    {
      v10 = (IStream *)*((_QWORD *)this + 3);
      v8 = -2147024809;
      *a3 = 0;
      if ( v10 )
      {
        (*(void (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 40LL))(v10, 0, 0, 0);
        v8 = CoUnmarshalInterface(v10, a2, a3);
      }
      if ( (v8 & 0x80000000) == 0 )
        goto LABEL_15;
      if ( (bidGblFlags & 2) == 0 )
        return v8;
      OLEDBTraceErr(v8, L"<CAdoSecurityHack::GetSite|OLEDB|ERR> ", 0x8Du);
      if ( (bidGblFlags & 2) == 0 )
        return v8;
      v9 = 144393;
    }
    bidTraceHR(`CAdoSecurityHack::GetSite'::`2'::_bidSrcFile2A[0], v9, L"<CAdoSecurityHack::GetSite|Trace|HR> ", v8);
  }
  else
  {
    v8 = -2147467259;
  }
LABEL_15:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `CAdoSecurityHack::GetSite'::`2'::_bidSrcFile2A[0],
                           152585,
                           L"<CAdoSecurityHack::GetSite|Trace|HR> ",
                           v8);
  return v8;
}

```

## disassembly

```asm
0x1800378f0  push    rbx
0x1800378f2  push    rbp
0x1800378f3  push    rsi
0x1800378f4  push    rdi
0x1800378f5  sub     rsp, 38h
0x1800378f9  cmp     qword ptr [rcx+10h], 0
0x1800378fe  mov     rsi, r8
0x180037901  mov     rbp, rdx
0x180037904  mov     rdi, rcx
0x180037907  jz      loc_1800379F5
0x18003790d  mov     ebx, [rcx+20h]
0x180037910  call    cs:__imp_GetCurrentThreadId
0x180037916  cmp     ebx, eax
0x180037918  jnz     short loc_180037984
0x18003791a  mov     rcx, [rdi+10h]
0x18003791e  mov     r8, rsi
0x180037921  mov     rdx, rbp
0x180037924  mov     rax, [rcx]
0x180037927  mov     rax, [rax]
0x18003792a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003792f  mov     ebx, eax
0x180037931  test    eax, eax
0x180037933  jns     loc_1800379FA
0x180037939  test    byte ptr cs:_bidGblFlags, 2
0x180037940  jz      loc_180037A20
0x180037946  mov     r8d, 89h; unsigned int
0x18003794c  lea     rdx, aCadosecurityha_5; "<CAdoSecurityHack::GetSite|OLEDB|ERR> "
0x180037953  mov     ecx, eax; int
0x180037955  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003795a  test    byte ptr cs:_bidGblFlags, 2
0x180037961  jz      loc_180037A20
0x180037967  mov     edx, 22409h
0x18003796c  mov     rcx, cs:?_bidSrcFile2A@?1??GetSite@CAdoSecurityHack@@UEAAJAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `CAdoSecurityHack::GetSite(_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180037973  lea     r8, aCadosecurityha_0; "<CAdoSecurityHack::GetSite|Trace|HR> "
0x18003797a  mov     r9d, ebx
0x18003797d  call    _bidTraceHR
0x180037982  jmp     short loc_1800379FA
0x180037984  mov     rdi, [rdi+18h]
0x180037988  mov     ebx, 80070057h
0x18003798d  mov     qword ptr [rsi], 0
0x180037994  test    rdi, rdi
0x180037997  jz      short loc_1800379C1
0x180037999  mov     rax, [rdi]
0x18003799c  xor     edx, edx
0x18003799e  xor     r9d, r9d
0x1800379a1  xor     r8d, r8d
0x1800379a4  mov     rcx, rdi
0x1800379a7  mov     rax, [rax+28h]
0x1800379ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379b0  mov     r8, rsi; ppv
0x1800379b3  mov     rdx, rbp; riid
0x1800379b6  mov     rcx, rdi; pStm
0x1800379b9  call    cs:__imp_CoUnmarshalInterface
0x1800379bf  mov     ebx, eax
0x1800379c1  test    ebx, ebx
0x1800379c3  jns     short loc_1800379FA
0x1800379c5  test    byte ptr cs:_bidGblFlags, 2
0x1800379cc  jz      short loc_180037A20
0x1800379ce  mov     r8d, 8Dh; unsigned int
0x1800379d4  lea     rdx, aCadosecurityha_5; "<CAdoSecurityHack::GetSite|OLEDB|ERR> "
0x1800379db  mov     ecx, ebx; int
0x1800379dd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800379e2  test    byte ptr cs:_bidGblFlags, 2
0x1800379e9  jz      short loc_180037A20
0x1800379eb  mov     edx, 23409h
0x1800379f0  jmp     loc_18003796C
0x1800379f5  mov     ebx, 80004005h
0x1800379fa  test    byte ptr cs:_bidGblFlags, 2
0x180037a01  jz      short loc_180037A20
0x180037a03  mov     rcx, cs:?_bidSrcFile2A@?1??GetSite@CAdoSecurityHack@@UEAAJAEBU_GUID@@PEAPEAX@Z@4REBDEB; char const * const `CAdoSecurityHack::GetSite(_GUID const &,void * *)'::`2'::_bidSrcFile2A
0x180037a0a  lea     r8, aCadosecurityha_0; "<CAdoSecurityHack::GetSite|Trace|HR> "
0x180037a11  mov     r9d, ebx
0x180037a14  mov     edx, 25409h
0x180037a19  call    _bidTraceHR
0x180037a1e  mov     ebx, eax
0x180037a20  mov     eax, ebx
0x180037a22  add     rsp, 38h
0x180037a26  pop     rdi
0x180037a27  pop     rsi
0x180037a28  pop     rbp
0x180037a29  pop     rbx
0x180037a2a  retn
```
