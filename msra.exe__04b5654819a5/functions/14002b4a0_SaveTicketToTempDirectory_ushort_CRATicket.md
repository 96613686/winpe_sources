# SaveTicketToTempDirectory(ushort * *,CRATicket *)

- ea: `0x14002b4a0`
- end: `0x14002b675`
- name: `?SaveTicketToTempDirectory@@YAJPEAPEAGPEAVCRATicket@@@Z`
- size: `469`
- prototype: `int(unsigned __int16 **, struct CRATicket *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140027964`

## callees

- `0x14002981c`
- `0x140029978`
- `0x14002b4a0`
- `0x14002ceb0`
- `0x140034ce4`
- `0x140035888`
- `0x14003db44`
- `0x14003ff50`

## import_xrefs

- `msvcrt!_time64` at `0x14002b5cc`
- `msvcrt!_time64` at `0x14002b5cc`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b645`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b655`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b645`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b655`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14002b527`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14002b527`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14002b538`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14002b538`

## string_xrefs

- `0x14002b58f`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002b604`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002b57d`: `SaveTicketToTempDirectory`
- `0x14002b5f8`: `SaveTicketToTempDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SaveTicketToTempDirectory(unsigned __int16 **a1, struct CRATicket *a2)
{
  OLECHAR *v4; // rdi
  signed int DirectoryAsBSTR; // eax
  CEventLogger *v6; // rcx
  unsigned int v7; // esi
  CHAR *v8; // rbx
  unsigned int v9; // r9d
  UINT v10; // eax
  unsigned __int16 *v11; // rax
  signed int UserInfoAsBSTR; // eax
  CEventLogger *v13; // rcx
  unsigned int v14; // eax
  int v15; // eax
  BSTR bstr; // [rsp+30h] [rbp-10h] BYREF
  __time64_t Time; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+48h] BYREF

  v4 = 0;
  bstrString = 0;
  bstr = 0;
  Time = 0;
  v19 = 0;
  DirectoryAsBSTR = GetDirectoryAsBSTR(0, &bstr, L"Invitation.msrcincident");
  v7 = DirectoryAsBSTR;
  v8 = (CHAR *)bstr;
  if ( DirectoryAsBSTR < 0 )
  {
    v9 = 785;
LABEL_17:
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v9,
      L"SaveTicketToTempDirectory",
      DirectoryAsBSTR);
    goto LABEL_21;
  }
  if ( !bstr )
  {
    v7 = -2147024882;
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x313u,
      L"SaveTicketToTempDirectory",
      0x8007000E);
    goto LABEL_21;
  }
  if ( !a1 )
  {
    v7 = -2147467261;
LABEL_10:
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x319u,
      L"SaveTicketToTempDirectory",
      v7);
    goto LABEL_21;
  }
  v10 = SysStringByteLen(bstr);
  v11 = SysAllocStringByteLen(v8, v10);
  *a1 = v11;
  if ( !v11 && v8 )
  {
    v7 = -2147024882;
    goto LABEL_10;
  }
  UserInfoAsBSTR = GetUserInfoAsBSTR(1, &bstrString);
  v7 = UserInfoAsBSTR;
  if ( UserInfoAsBSTR >= 0 )
  {
    v4 = bstrString;
    DirectoryAsBSTR = CRATicket::put_NoviceName(a2, bstrString);
    v7 = DirectoryAsBSTR;
    if ( DirectoryAsBSTR < 0 )
    {
      v9 = 795;
      goto LABEL_17;
    }
    _time64(&Time);
    *((_DWORD *)a2 + 4) = Time;
    DirectoryAsBSTR = GetTicketDurationAsDWORD(&v19);
    v7 = DirectoryAsBSTR;
    if ( DirectoryAsBSTR < 0 )
    {
      v9 = 809;
      goto LABEL_17;
    }
    v14 = v19;
    if ( !v19 )
      v14 = 60;
    *((_DWORD *)a2 + 36) = v14;
    v15 = VistaOnlyTicket();
    v7 = CRATicket::SaveRATicket((OLECHAR **)a2, (unsigned __int16 *)v8, v15);
  }
  else
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x31Au,
      L"SaveTicketToTempDirectory",
      UserInfoAsBSTR);
    v4 = bstrString;
  }
LABEL_21:
  SysFreeString((BSTR)v8);
  SysFreeString(v4);
  return v7;
}

```

## disassembly

```asm
0x14002b4a0  mov     [rsp-28h+arg_0], rbx
0x14002b4a5  push    rbp
0x14002b4a6  push    rsi
0x14002b4a7  push    rdi
0x14002b4a8  push    r14
0x14002b4aa  push    r15
0x14002b4ac  mov     rbp, rsp
0x14002b4af  sub     rsp, 40h
0x14002b4b3  mov     r15, rdx
0x14002b4b6  mov     r14, rcx
0x14002b4b9  xor     edi, edi
0x14002b4bb  mov     [rbp+bstrString], rdi
0x14002b4bf  mov     [rbp+bstr], rdi
0x14002b4c3  mov     [rbp+Time], rdi
0x14002b4c7  mov     [rbp+arg_10], edi
0x14002b4ca  lea     r8, aInvitationMsrc; "Invitation.msrcincident"
0x14002b4d1  lea     rdx, [rbp+bstr]; unsigned __int16 **
0x14002b4d5  xor     ecx, ecx; csidl
0x14002b4d7  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x14002b4dc  mov     esi, eax
0x14002b4de  mov     rbx, [rbp+bstr]
0x14002b4e2  test    eax, eax
0x14002b4e4  jns     short loc_14002B4F1
0x14002b4e6  mov     r9d, 311h
0x14002b4ec  jmp     loc_14002B5F4
0x14002b4f1  test    rbx, rbx
0x14002b4f4  jnz     short loc_14002B50E
0x14002b4f6  mov     esi, 8007000Eh
0x14002b4fb  mov     [rsp+40h+var_18], 8007000Eh
0x14002b503  mov     r9d, 313h
0x14002b509  jmp     loc_14002B5F8
0x14002b50e  test    r14, r14
0x14002b511  jnz     short loc_14002B51A
0x14002b513  mov     esi, 80004003h
0x14002b518  jmp     short loc_14002B556
0x14002b51a  test    rbx, rbx
0x14002b51d  jnz     short loc_14002B524
0x14002b51f  mov     [r14], rbx
0x14002b522  jmp     short loc_14002B54C
0x14002b524  mov     rcx, rbx; bstr
0x14002b527  call    cs:__imp_SysStringByteLen
0x14002b52e  nop     dword ptr [rax+rax+00h]
0x14002b533  mov     edx, eax; len
0x14002b535  mov     rcx, rbx; psz
0x14002b538  call    cs:__imp_SysAllocStringByteLen
0x14002b53f  nop     dword ptr [rax+rax+00h]
0x14002b544  mov     [r14], rax
0x14002b547  test    rax, rax
0x14002b54a  jnz     short loc_14002B565
0x14002b54c  test    rbx, rbx
0x14002b54f  jz      short loc_14002B565
0x14002b551  mov     esi, 8007000Eh
0x14002b556  mov     [rsp+40h+var_18], esi
0x14002b55a  mov     r9d, 319h
0x14002b560  jmp     loc_14002B5F8
0x14002b565  lea     rdx, [rbp+bstrString]
0x14002b569  mov     ecx, 1
0x14002b56e  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x14002b573  mov     esi, eax
0x14002b575  test    eax, eax
0x14002b577  jns     short loc_14002B5AB
0x14002b579  mov     [rsp+40h+var_18], eax; unsigned int
0x14002b57d  lea     rax, aSavetickettote; "SaveTicketToTempDirectory"
0x14002b584  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x14002b589  mov     r9d, 31Ah; unsigned int
0x14002b58f  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002b596  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002b59d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002b5a2  mov     rdi, [rbp+bstrString]
0x14002b5a6  jmp     loc_14002B642
0x14002b5ab  mov     rdi, [rbp+bstrString]
0x14002b5af  mov     rdx, rdi; unsigned __int16 *
0x14002b5b2  mov     rcx, r15; this
0x14002b5b5  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x14002b5ba  mov     esi, eax
0x14002b5bc  test    eax, eax
0x14002b5be  jns     short loc_14002B5C8
0x14002b5c0  mov     r9d, 31Bh
0x14002b5c6  jmp     short loc_14002B5F4
0x14002b5c8  lea     rcx, [rbp+Time]; Time
0x14002b5cc  call    cs:__imp__time64
0x14002b5d3  nop     dword ptr [rax+rax+00h]
0x14002b5d8  mov     eax, dword ptr [rbp+Time]
0x14002b5db  mov     [r15+10h], eax
0x14002b5df  lea     rcx, [rbp+arg_10]; unsigned int *
0x14002b5e3  call    ?GetTicketDurationAsDWORD@@YAJPEAK@Z; GetTicketDurationAsDWORD(ulong *)
0x14002b5e8  mov     esi, eax
0x14002b5ea  test    eax, eax
0x14002b5ec  jns     short loc_14002B619
0x14002b5ee  mov     r9d, 329h; unsigned int
0x14002b5f4  mov     [rsp+40h+var_18], eax; unsigned int
0x14002b5f8  lea     rax, aSavetickettote; "SaveTicketToTempDirectory"
0x14002b5ff  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x14002b604  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002b60b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002b612  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002b617  jmp     short loc_14002B642
0x14002b619  mov     eax, [rbp+arg_10]
0x14002b61c  mov     ecx, 3Ch ; '<'
0x14002b621  test    eax, eax
0x14002b623  cmovz   eax, ecx
0x14002b626  mov     [r15+90h], eax
0x14002b62d  call    ?VistaOnlyTicket@@YAHXZ; VistaOnlyTicket(void)
0x14002b632  mov     r8d, eax; int
0x14002b635  mov     rdx, rbx; unsigned __int16 *
0x14002b638  mov     rcx, r15; this
0x14002b63b  call    ?SaveRATicket@CRATicket@@QEAAJPEAGH@Z; CRATicket::SaveRATicket(ushort *,int)
0x14002b640  mov     esi, eax
0x14002b642  mov     rcx, rbx; bstrString
0x14002b645  call    cs:__imp_SysFreeString
0x14002b64c  nop     dword ptr [rax+rax+00h]
0x14002b651  nop
0x14002b652  mov     rcx, rdi; bstrString
0x14002b655  call    cs:__imp_SysFreeString
0x14002b65c  nop     dword ptr [rax+rax+00h]
0x14002b661  mov     eax, esi
0x14002b663  mov     rbx, [rsp+40h+arg_0]
0x14002b668  add     rsp, 40h
0x14002b66c  pop     r15
0x14002b66e  pop     r14
0x14002b670  pop     rdi
0x14002b671  pop     rsi
0x14002b672  pop     rbp
0x14002b673  retn
```
