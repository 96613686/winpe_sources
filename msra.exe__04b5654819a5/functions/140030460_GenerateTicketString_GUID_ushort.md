# GenerateTicketString(_GUID,ushort * *)

- ea: `0x140030460`
- end: `0x1400306ee`
- name: `?GenerateTicketString@@YAJU_GUID@@PEAPEAG@Z`
- size: `654`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400311b8`

## callees

- `0x140001cc4`
- `0x14000c224`
- `0x140030460`
- `0x140034ce4`
- `0x140038650`
- `0x1400387e0`
- `0x14003894c`
- `0x140039e2c`
- `0x14003a16c`
- `0x14003af44`
- `0x14003fb64`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140030696`
- `msvcrt!??3@YAXPEAX@Z` at `0x140030696`
- `ole32!CoTaskMemFree` at `0x1400306b9`
- `ole32!CoTaskMemFree` at `0x1400306b9`
- `ole32!StringFromIID` at `0x1400304db`
- `ole32!StringFromIID` at `0x1400304db`
- `OLEAUT32!__imp_SysAllocString` at `0x1400305e1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400305e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400305c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400305c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GenerateTicketString(IID *rclsid, unsigned __int16 **a2)
{
  unsigned int v4; // esi
  HRESULT v5; // eax
  CEventLogger *v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // r9d
  CRATicket *v9; // rax
  CEventLogger *v10; // rcx
  CRATicket *v11; // rdi
  signed int Ticket; // eax
  CEventLogger *v13; // rcx
  unsigned int v14; // r9d
  const OLECHAR *v15; // rbx
  OLECHAR *v16; // rcx
  BSTR v17; // rax
  CEventLogger *v18; // rcx
  CEventLogger *v19; // rcx
  unsigned int v21; // [rsp+30h] [rbp-30h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-28h] BYREF
  __int64 v23; // [rsp+40h] [rbp-20h] BYREF
  __int128 v24; // [rsp+48h] [rbp-18h]
  CRATicket *v25; // [rsp+58h] [rbp-8h]

  v23 = 0;
  v24 = 0;
  v4 = 0;
  v21 = 0;
  lpsz = 0;
  *a2 = 0;
  v5 = CReadWriteLock::Initialize((CReadWriteLock *)&v23);
  v7 = v5;
  if ( v5 < 0 )
  {
    v8 = 1304;
LABEL_3:
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      v8,
      L"GenerateTicketString",
      v5);
    goto LABEL_28;
  }
  v5 = StringFromIID(rclsid, &lpsz);
  v7 = v5;
  if ( v5 < 0 )
  {
    v8 = 1310;
    goto LABEL_3;
  }
  v9 = (CRATicket *)operator new(0x230u, (const struct std::nothrow_t *)&std::nothrow);
  v25 = v9;
  if ( v9 )
    v11 = CRATicket::CRATicket(v9);
  else
    v11 = 0;
  if ( !v11 )
  {
    v7 = -2147024882;
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x524u,
      L"GenerateTicketString",
      0x8007000E);
    goto LABEL_26;
  }
  Ticket = CReadWriteLock::GetWriteLock((CReadWriteLock *)&v23, (int *)&v21);
  v7 = Ticket;
  v4 = v21;
  if ( Ticket < 0 )
  {
    v14 = 1321;
LABEL_24:
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      v14,
      L"GenerateTicketString",
      Ticket);
    goto LABEL_25;
  }
  if ( v21 )
  {
    v15 = lpsz;
    v16 = (OLECHAR *)*((_QWORD *)v11 + 68);
    if ( v16 )
    {
      SysFreeString(v16);
      *((_QWORD *)v11 + 68) = 0;
    }
    if ( !v15 || (v17 = SysAllocString(v15), (*((_QWORD *)v11 + 68) = v17) != 0) )
    {
      Ticket = CRATicket::CreateTicket((LPVOID *)v11);
      v7 = Ticket;
      if ( Ticket < 0 )
      {
        v14 = 1332;
        goto LABEL_24;
      }
      Ticket = CRATicket::get_RATicketString(v11, a2);
      v7 = Ticket;
      if ( Ticket < 0 )
      {
        v14 = 1337;
        goto LABEL_24;
      }
    }
    else
    {
      CEventLogger::LogError(
        v18,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
        0x8E3u,
        L"CRATicket::put_ActivityID",
        0x8007000E);
      v7 = -2147024882;
      CEventLogger::LogError(
        v19,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
        0x52Fu,
        L"GenerateTicketString",
        0x8007000E);
    }
  }
  else
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x52Au,
      L"GenerateTicketString",
      0);
    v7 = -2147467259;
  }
LABEL_25:
  CRATicket::~CRATicket(v11);
  operator delete(v11);
LABEL_26:
  if ( v4 == 1 )
    CReadWriteLock::ReleaseWriteLock((CReadWriteLock *)&v23);
LABEL_28:
  if ( lpsz )
  {
    CoTaskMemFree(lpsz);
    lpsz = 0;
  }
  CReadWriteLock::~CReadWriteLock((CReadWriteLock *)&v23);
  return v7;
}

```

## disassembly

```asm
0x140030460  mov     [rsp-18h+arg_10], rbx
0x140030465  mov     [rsp-18h+arg_18], rsi
0x14003046a  push    rbp
0x14003046b  push    rdi
0x14003046c  push    r14
0x14003046e  mov     rbp, rsp
0x140030471  sub     rsp, 60h
0x140030475  mov     r14, rdx
0x140030478  mov     rdi, rcx
0x14003047b  mov     [rbp+var_20], 0
0x140030483  xorps   xmm0, xmm0
0x140030486  movdqu  [rbp+var_18], xmm0
0x14003048b  xor     esi, esi
0x14003048d  mov     [rbp+var_30], esi
0x140030490  mov     [rbp+lpsz], rsi
0x140030494  mov     [rdx], rsi
0x140030497  lea     rcx, [rbp+var_20]; this
0x14003049b  call    ?Initialize@CReadWriteLock@@QEAAJXZ; CReadWriteLock::Initialize(void)
0x1400304a0  mov     ebx, eax
0x1400304a2  test    eax, eax
0x1400304a4  jns     short loc_1400304D4
0x1400304a6  mov     r9d, 518h; unsigned int
0x1400304ac  mov     [rsp+60h+var_38], eax; unsigned int
0x1400304b0  lea     rax, aGenerateticket; "GenerateTicketString"
0x1400304b7  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x1400304bc  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x1400304c3  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400304ca  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400304cf  jmp     loc_1400306B0
0x1400304d4  lea     rdx, [rbp+lpsz]; lplpsz
0x1400304d8  mov     rcx, rdi; rclsid
0x1400304db  call    cs:__imp_StringFromIID
0x1400304e2  nop     dword ptr [rax+rax+00h]
0x1400304e7  mov     ebx, eax
0x1400304e9  test    eax, eax
0x1400304eb  jns     short loc_1400304F5
0x1400304ed  mov     r9d, 51Eh
0x1400304f3  jmp     short loc_1400304AC
0x1400304f5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400304fc  mov     ecx, 230h; unsigned __int64
0x140030501  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140030506  mov     [rbp+var_8], rax
0x14003050a  test    rax, rax
0x14003050d  jz      short loc_14003051C
0x14003050f  mov     rcx, rax; this
0x140030512  call    ??0CRATicket@@QEAA@XZ; CRATicket::CRATicket(void)
0x140030517  mov     rdi, rax
0x14003051a  jmp     short loc_14003051E
0x14003051c  xor     edi, edi
0x14003051e  test    rdi, rdi
0x140030521  jnz     short loc_14003055A
0x140030523  mov     ebx, 8007000Eh
0x140030528  mov     [rsp+60h+var_38], 8007000Eh; unsigned int
0x140030530  lea     rax, aGenerateticket; "GenerateTicketString"
0x140030537  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x14003053c  mov     r9d, 524h; unsigned int
0x140030542  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030549  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030550  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030555  jmp     loc_1400306A2
0x14003055a  lea     rdx, [rbp+var_30]; int *
0x14003055e  lea     rcx, [rbp+var_20]; this
0x140030562  call    ?GetWriteLock@CReadWriteLock@@QEAAJPEAH@Z; CReadWriteLock::GetWriteLock(int *)
0x140030567  mov     ebx, eax
0x140030569  mov     esi, [rbp+var_30]
0x14003056c  test    eax, eax
0x14003056e  jns     short loc_14003057B
0x140030570  mov     r9d, 529h
0x140030576  jmp     loc_140030668
0x14003057b  test    esi, esi
0x14003057d  jnz     short loc_1400305B2
0x14003057f  mov     [rsp+60h+var_38], esi; unsigned int
0x140030583  lea     rax, aGenerateticket; "GenerateTicketString"
0x14003058a  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x14003058f  mov     r9d, 52Ah; unsigned int
0x140030595  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14003059c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400305a3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400305a8  mov     ebx, 80004005h
0x1400305ad  jmp     loc_14003068B
0x1400305b2  mov     rbx, [rbp+lpsz]
0x1400305b6  mov     rcx, [rdi+220h]; bstrString
0x1400305bd  test    rcx, rcx
0x1400305c0  jz      short loc_1400305D9
0x1400305c2  call    cs:__imp_SysFreeString
0x1400305c9  nop     dword ptr [rax+rax+00h]
0x1400305ce  mov     qword ptr [rdi+220h], 0
0x1400305d9  test    rbx, rbx
0x1400305dc  jz      short loc_14003063B
0x1400305de  mov     rcx, rbx; psz
0x1400305e1  call    cs:__imp_SysAllocString
0x1400305e8  nop     dword ptr [rax+rax+00h]
0x1400305ed  mov     [rdi+220h], rax
0x1400305f4  test    rax, rax
0x1400305f7  jnz     short loc_14003063B
0x1400305f9  mov     [rsp+60h+var_38], 8007000Eh; unsigned int
0x140030601  lea     rax, aCraticketPutAc; "CRATicket::put_ActivityID"
0x140030608  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x14003060d  mov     r9d, 8E3h; unsigned int
0x140030613  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003061a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030621  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030626  mov     ebx, 8007000Eh
0x14003062b  mov     [rsp+60h+var_38], 8007000Eh
0x140030633  mov     r9d, 52Fh
0x140030639  jmp     short loc_14003066C
0x14003063b  mov     rcx, rdi; this
0x14003063e  call    ?CreateTicket@CRATicket@@QEAAJXZ; CRATicket::CreateTicket(void)
0x140030643  mov     ebx, eax
0x140030645  test    eax, eax
0x140030647  jns     short loc_140030651
0x140030649  mov     r9d, 534h
0x14003064f  jmp     short loc_140030668
0x140030651  mov     rdx, r14; unsigned __int16 **
0x140030654  mov     rcx, rdi; this
0x140030657  call    ?get_RATicketString@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_RATicketString(ushort * *)
0x14003065c  mov     ebx, eax
0x14003065e  test    eax, eax
0x140030660  jns     short loc_14003068B
0x140030662  mov     r9d, 539h; unsigned int
0x140030668  mov     [rsp+60h+var_38], eax; unsigned int
0x14003066c  lea     rax, aGenerateticket; "GenerateTicketString"
0x140030673  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x140030678  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14003067f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030686  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003068b  mov     rcx, rdi; this
0x14003068e  call    ??1CRATicket@@QEAA@XZ; CRATicket::~CRATicket(void)
0x140030693  mov     rcx, rdi
0x140030696  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14003069d  nop     dword ptr [rax+rax+00h]
0x1400306a2  cmp     esi, 1
0x1400306a5  jnz     short loc_1400306B0
0x1400306a7  lea     rcx, [rbp+var_20]; this
0x1400306ab  call    ?ReleaseWriteLock@CReadWriteLock@@QEAAJXZ; CReadWriteLock::ReleaseWriteLock(void)
0x1400306b0  mov     rcx, [rbp+lpsz]; pv
0x1400306b4  test    rcx, rcx
0x1400306b7  jz      short loc_1400306CD
0x1400306b9  call    cs:__imp_CoTaskMemFree
0x1400306c0  nop     dword ptr [rax+rax+00h]
0x1400306c5  mov     [rbp+lpsz], 0
0x1400306cd  lea     rcx, [rbp+var_20]; this
0x1400306d1  call    ??1CReadWriteLock@@QEAA@XZ; CReadWriteLock::~CReadWriteLock(void)
0x1400306d6  mov     eax, ebx
0x1400306d8  lea     r11, [rsp+60h+var_s0]
0x1400306dd  mov     rbx, [r11+30h]
0x1400306e1  mov     rsi, [r11+38h]
0x1400306e5  mov     rsp, r11
0x1400306e8  pop     r14
0x1400306ea  pop     rdi
0x1400306eb  pop     rbp
0x1400306ec  retn
```
