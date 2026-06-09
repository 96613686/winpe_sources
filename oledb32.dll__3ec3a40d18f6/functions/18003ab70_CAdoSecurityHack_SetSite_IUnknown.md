# CAdoSecurityHack::SetSite(IUnknown *)

- ea: `0x18003ab70`
- end: `0x18003acf1`
- name: `?SetSite@CAdoSecurityHack@@UEAAJPEAUIUnknown@@@Z`
- size: `385`
- prototype: `int(CAdoSecurityHack *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180013870`
- `0x180029560`
- `0x18003204c`
- `0x18003ab70`
- `0x180087010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003acb6`
- `KERNEL32!GetCurrentThreadId` at `0x18003acb6`
- `ole32!CoMarshalInterface` at `0x18003abca`
- `ole32!CoMarshalInterface` at `0x18003abca`
- `ole32!CreateStreamOnHGlobal` at `0x18003ab9e`
- `ole32!CreateStreamOnHGlobal` at `0x18003ab9e`

## string_xrefs

- `0x18003ac0d`: `<CAdoSecurityHack::SetSite|OLEDB|ERR> `
- `0x18003ac2f`: `<CAdoSecurityHack::SetSite|Trace|HR> `
- `0x18003accf`: `<CAdoSecurityHack::SetSite|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CAdoSecurityHack::SetSite(CAdoSecurityHack *this, struct IUnknown *a2)
{
  unsigned int v2; // esi
  HRESULT v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  LPSTREAM ppstm; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  ppstm = 0;
  if ( !a2 )
    goto LABEL_9;
  v5 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v5 >= 0 )
  {
    v5 = CoMarshalInterface(ppstm, &IID_IUnknown, a2, 3u, 0, 1u);
    if ( v5 < 0 )
    {
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      ppstm = 0;
      v2 = v5;
      goto LABEL_6;
    }
  }
  v2 = v5;
  if ( v5 >= 0 )
  {
LABEL_9:
    v6 = *((_QWORD *)this + 2);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 3);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, 0, 0, 0);
      ATL::AtlFreeMarshalStream(*((struct IStream **)this + 3));
      *((_QWORD *)this + 3) = 0;
    }
    if ( a2 )
    {
      *((_QWORD *)this + 2) = a2;
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
      *((_QWORD *)this + 3) = ppstm;
      *((_DWORD *)this + 8) = GetCurrentThreadId();
    }
    goto LABEL_15;
  }
LABEL_6:
  if ( (bidGblFlags & 2) == 0 )
    return v2;
  OLEDBTraceErr(v5, L"<CAdoSecurityHack::SetSite|OLEDB|ERR> ", 0x5Cu);
  if ( (bidGblFlags & 2) == 0 )
    return v2;
  bidTraceHR(
    `CAdoSecurityHack::SetSite'::`2'::_bidSrcFile2A[0],
    94217,
    L"<CAdoSecurityHack::SetSite|Trace|HR> ",
    (unsigned int)v5);
LABEL_15:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `CAdoSecurityHack::SetSite'::`2'::_bidSrcFile2A[0],
                           122889,
                           L"<CAdoSecurityHack::SetSite|Trace|HR> ",
                           v2);
  return v2;
}

```

## disassembly

```asm
0x18003ab70  push    rbx
0x18003ab72  push    rsi
0x18003ab73  push    rdi
0x18003ab74  push    r14
0x18003ab76  sub     rsp, 38h
0x18003ab7a  xor     esi, esi
0x18003ab7c  mov     r14, rdx
0x18003ab7f  mov     [rsp+58h+ppstm], rsi
0x18003ab84  mov     rdi, rcx
0x18003ab87  test    rdx, rdx
0x18003ab8a  jz      loc_18003AC45
0x18003ab90  mov     esi, 1
0x18003ab95  lea     r8, [rsp+58h+ppstm]; ppstm
0x18003ab9a  mov     edx, esi; fDeleteOnRelease
0x18003ab9c  xor     ecx, ecx; hGlobal
0x18003ab9e  call    cs:__imp_CreateStreamOnHGlobal
0x18003aba4  mov     ebx, eax
0x18003aba6  test    eax, eax
0x18003aba8  js      short loc_18003ABF4
0x18003abaa  mov     rcx, [rsp+58h+ppstm]; pStm
0x18003abaf  lea     r9d, [rsi+2]; dwDestContext
0x18003abb3  mov     [rsp+58h+mshlflags], esi; mshlflags
0x18003abb7  lea     rdx, IID_IUnknown; riid
0x18003abbe  mov     r8, r14; pUnk
0x18003abc1  mov     [rsp+58h+pvDestContext], 0; pvDestContext
0x18003abca  call    cs:__imp_CoMarshalInterface
0x18003abd0  mov     ebx, eax
0x18003abd2  test    eax, eax
0x18003abd4  jns     short loc_18003ABF4
0x18003abd6  mov     rcx, [rsp+58h+ppstm]
0x18003abdb  mov     rax, [rcx]
0x18003abde  mov     rax, [rax+10h]
0x18003abe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abe7  mov     [rsp+58h+ppstm], 0
0x18003abf0  mov     esi, ebx
0x18003abf2  jmp     short loc_18003ABFA
0x18003abf4  mov     esi, ebx
0x18003abf6  test    ebx, ebx
0x18003abf8  jns     short loc_18003AC45
0x18003abfa  test    byte ptr cs:_bidGblFlags, 2
0x18003ac01  jz      loc_18003ACE5
0x18003ac07  mov     r8d, 5Ch ; '\'; unsigned int
0x18003ac0d  lea     rdx, aCadosecurityha_2; "<CAdoSecurityHack::SetSite|OLEDB|ERR> "
0x18003ac14  mov     ecx, ebx; int
0x18003ac16  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003ac1b  test    byte ptr cs:_bidGblFlags, 2
0x18003ac22  jz      loc_18003ACE5
0x18003ac28  mov     rcx, cs:?_bidSrcFile2A@?1??SetSite@CAdoSecurityHack@@UEAAJPEAUIUnknown@@@Z@4REBDEB; char const * const `CAdoSecurityHack::SetSite(IUnknown *)'::`2'::_bidSrcFile2A
0x18003ac2f  lea     r8, aCadosecurityha_3; "<CAdoSecurityHack::SetSite|Trace|HR> "
0x18003ac36  mov     r9d, ebx
0x18003ac39  mov     edx, 17009h
0x18003ac3e  call    _bidTraceHR
0x18003ac43  jmp     short loc_18003ACBF
0x18003ac45  mov     rcx, [rdi+10h]
0x18003ac49  test    rcx, rcx
0x18003ac4c  jz      short loc_18003AC62
0x18003ac4e  mov     rax, [rcx]
0x18003ac51  mov     rax, [rax+10h]
0x18003ac55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac5a  mov     qword ptr [rdi+10h], 0
0x18003ac62  mov     rcx, [rdi+18h]
0x18003ac66  test    rcx, rcx
0x18003ac69  jz      short loc_18003AC95
0x18003ac6b  mov     rax, [rcx]
0x18003ac6e  xor     r9d, r9d
0x18003ac71  mov     rdx, cs:qword_180091F18
0x18003ac78  xor     r8d, r8d
0x18003ac7b  mov     rax, [rax+28h]
0x18003ac7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac84  mov     rcx, [rdi+18h]; struct IStream *
0x18003ac88  call    ?AtlFreeMarshalStream@ATL@@YAJPEAUIStream@@@Z; ATL::AtlFreeMarshalStream(IStream *)
0x18003ac8d  mov     qword ptr [rdi+18h], 0
0x18003ac95  test    r14, r14
0x18003ac98  jz      short loc_18003ACBF
0x18003ac9a  mov     [rdi+10h], r14
0x18003ac9e  mov     rcx, r14
0x18003aca1  mov     rax, [r14]
0x18003aca4  mov     rax, [rax+8]
0x18003aca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acad  mov     rax, [rsp+58h+ppstm]
0x18003acb2  mov     [rdi+18h], rax
0x18003acb6  call    cs:__imp_GetCurrentThreadId
0x18003acbc  mov     [rdi+20h], eax
0x18003acbf  test    byte ptr cs:_bidGblFlags, 2
0x18003acc6  jz      short loc_18003ACE5
0x18003acc8  mov     rcx, cs:?_bidSrcFile2A@?1??SetSite@CAdoSecurityHack@@UEAAJPEAUIUnknown@@@Z@4REBDEB; char const * const `CAdoSecurityHack::SetSite(IUnknown *)'::`2'::_bidSrcFile2A
0x18003accf  lea     r8, aCadosecurityha_3; "<CAdoSecurityHack::SetSite|Trace|HR> "
0x18003acd6  mov     r9d, esi
0x18003acd9  mov     edx, 1E009h
0x18003acde  call    _bidTraceHR
0x18003ace3  mov     esi, eax
0x18003ace5  mov     eax, esi
0x18003ace7  add     rsp, 38h
0x18003aceb  pop     r14
0x18003aced  pop     rdi
0x18003acee  pop     rsi
0x18003acef  pop     rbx
0x18003acf0  retn
```
