# CRATicket::CreateTicket(void)

- ea: `0x14003af44`
- end: `0x14003b329`
- name: `?CreateTicket@CRATicket@@QEAAJXZ`
- size: `997`
- prototype: `__int64 __fastcall(CRATicket *__hidden this)`
- caller_count: `6`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013f4c`
- `0x140027ce0`
- `0x140029418`
- `0x140030460`
- `0x140032274`
- `0x140032f7c`

## callees

- `0x1400044f8`
- `0x140034ce4`
- `0x140035b20`
- `0x14003af44`
- `0x14003c2dc`
- `0x1400475f8`
- `0x140047768`
- `0x1400478b4`
- `0x14004aa20`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003b0eb`
- `KERNEL32!GetLastError` at `0x14003b0fb`
- `KERNEL32!GetLastError` at `0x14003b0eb`
- `KERNEL32!GetLastError` at `0x14003b0fb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14003b281`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14003b281`
- `ole32!CoCreateInstance` at `0x14003b00b`
- `ole32!CoCreateInstance` at `0x14003b00b`
- `OLEAUT32!__imp_SysAllocString` at `0x14003af9e`
- `OLEAUT32!__imp_SysAllocString` at `0x14003afcf`
- `OLEAUT32!__imp_SysAllocString` at `0x14003af9e`
- `OLEAUT32!__imp_SysAllocString` at `0x14003afcf`
- `OLEAUT32!__imp_SysFreeString` at `0x14003af8b`
- `OLEAUT32!__imp_SysFreeString` at `0x14003afbc`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b2ad`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b2bd`
- `OLEAUT32!__imp_SysFreeString` at `0x14003af8b`
- `OLEAUT32!__imp_SysFreeString` at `0x14003afbc`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b2ad`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b2bd`

## string_xrefs

- `0x14003b023`: `CRATicket::CreateTicket`
- `0x14003b0b9`: `CRATicket::CreateTicket`
- `0x14003b155`: `MaxCompressionLevel`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRATicket::CreateTicket(LPVOID *this)
{
  OLECHAR *v2; // rdi
  OLECHAR *v3; // rbx
  _QWORD *v4; // r13
  signed int Instance; // eax
  CEventLogger *v6; // rcx
  unsigned int v7; // esi
  unsigned int v8; // r9d
  unsigned __int16 *v9; // rdx
  __int16 v10; // r8
  int v11; // esi
  CEventLogger *v12; // rcx
  signed int LastError; // eax
  unsigned __int16 *v14; // r8
  signed int v15; // eax
  CEventLogger *v16; // rcx
  unsigned int v17; // r9d
  __int64 v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  OLECHAR *v21; // [rsp+50h] [rbp-10h]
  OLECHAR *v22; // [rsp+58h] [rbp-8h]
  struct IRDPSRAPISessionProperties *v23; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int16 *v24; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+58h] BYREF

  v20 = 0;
  v19 = 0;
  v25 = 0;
  v23 = 0;
  v21 = 0;
  v24 = 0;
  SysFreeString(0);
  v2 = SysAllocString(L"RemoteAssistance");
  v22 = v2;
  if ( !v2 || (SysFreeString(0), v3 = SysAllocString(L"*"), (v21 = v3) == 0) )
    ATL::AtlThrowImpl(-2147024882);
  v4 = this + 26;
  Instance = CoCreateInstance(&CLSID_RDPSession, 0, 1u, &GUID_eeb20886_e470_4cf6_842b_2739c0ec5cfb, this + 26);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = 2443;
LABEL_5:
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      v8,
      L"CRATicket::CreateTicket",
      Instance);
    goto LABEL_38;
  }
  Instance = CRATicket::InitializeAllVC((RAXferWorker **)this);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = 2445;
    goto LABEL_5;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 88LL))(*v4, &v25);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = 2446;
    goto LABEL_5;
  }
  Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IRDPSRAPISessionProperties **))v25)(
               v25,
               &GUID_339b24f2_9bc0_4f16_9aac_f165433d13d4,
               &v23);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = 2449;
    goto LABEL_5;
  }
  Instance = SetCollabProp(v23, v9, v10);
  v7 = Instance;
  if ( Instance < 0 )
  {
    v8 = 2458;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 34) == 3 )
  {
    v11 = 0;
  }
  else
  {
    v11 = 5000;
    if ( !(unsigned int)IsTeredoQualified((unsigned int)v6) )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2147467259;
      }
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
        0x9ABu,
        L"CRATicket::CreateTicket",
        LastError);
    }
  }
  SetCollabProp(v23, L"SATWaitTimeout", v11);
  SetCollabProp(v23, L"MaxCompressionLevel", 3);
  if ( (int)GetRegistryValue(L"BindAddress", (BYTE **)&v24, 2) >= 0 )
    SetCollabProp(v23, L"BindAddress", v24);
  v14 = (unsigned __int16 *)this[68];
  if ( v14 )
    SetCollabProp(v23, L"ActivityID", v14);
  v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 56LL))(*v4);
  v7 = v15;
  if ( v15 < 0 )
  {
    v17 = 2521;
LABEL_28:
    CEventLogger::LogError(
      v16,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      v17,
      L"CRATicket::CreateTicket",
      v15);
    goto LABEL_36;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 104LL))(*v4, &v20);
  v7 = v15;
  if ( v15 < 0 )
  {
    v17 = 2523;
    goto LABEL_28;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, LPVOID, OLECHAR *, OLECHAR *, int, __int64 *))(*(_QWORD *)v20 + 80LL))(
          v20,
          this[6],
          v2,
          v3,
          1,
          &v19);
  v7 = v15;
  if ( v15 < 0 )
  {
    v17 = 2529;
    goto LABEL_28;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 56LL))(v19, (char *)this + 24);
  v7 = v15;
  if ( v15 < 0 )
  {
    v17 = 2531;
    goto LABEL_28;
  }
  *((_DWORD *)this + 133) = 1;
LABEL_36:
  if ( v24 )
    operator delete[](v24);
LABEL_38:
  if ( v23 )
  {
    ((void (__fastcall *)(struct IRDPSRAPISessionProperties *))v23->lpVtbl->Release)(v23);
    v23 = 0;
  }
  SysFreeString(v3);
  SysFreeString(v2);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return v7;
}

```

## disassembly

```asm
0x14003af44  push    rbp
0x14003af46  push    rbx
0x14003af47  push    rsi
0x14003af48  push    rdi
0x14003af49  push    r13
0x14003af4b  push    r14
0x14003af4d  push    r15
0x14003af4f  mov     rbp, rsp
0x14003af52  sub     rsp, 60h
0x14003af56  mov     r15, rcx
0x14003af59  mov     [rbp+var_18], 0
0x14003af61  mov     [rbp+var_20], 0
0x14003af69  mov     [rbp+arg_18], 0
0x14003af71  mov     [rbp+arg_8], 0
0x14003af79  mov     [rbp+var_10], 0
0x14003af81  mov     [rbp+arg_10], 0
0x14003af89  xor     ecx, ecx; bstrString
0x14003af8b  call    cs:__imp_SysFreeString
0x14003af92  nop     dword ptr [rax+rax+00h]
0x14003af97  lea     rcx, aRemoteassistan; "RemoteAssistance"
0x14003af9e  call    cs:__imp_SysAllocString
0x14003afa5  nop     dword ptr [rax+rax+00h]
0x14003afaa  mov     rdi, rax
0x14003afad  mov     [rbp+var_8], rax
0x14003afb1  test    rax, rax
0x14003afb4  jz      loc_14003B31E
0x14003afba  xor     ecx, ecx; bstrString
0x14003afbc  call    cs:__imp_SysFreeString
0x14003afc3  nop     dword ptr [rax+rax+00h]
0x14003afc8  lea     rcx, asc_140057CE0; "*"
0x14003afcf  call    cs:__imp_SysAllocString
0x14003afd6  nop     dword ptr [rax+rax+00h]
0x14003afdb  mov     rbx, rax
0x14003afde  mov     [rbp+var_10], rax
0x14003afe2  test    rax, rax
0x14003afe5  jz      loc_14003B31E
0x14003afeb  lea     r13, [r15+0D0h]
0x14003aff2  mov     [rsp+60h+ppv], r13; ppv
0x14003aff7  lea     r9, _GUID_eeb20886_e470_4cf6_842b_2739c0ec5cfb; riid
0x14003affe  xor     edx, edx; pUnkOuter
0x14003b000  lea     r8d, [rdx+1]; dwClsContext
0x14003b004  lea     rcx, CLSID_RDPSession; rclsid
0x14003b00b  call    cs:__imp_CoCreateInstance
0x14003b012  nop     dword ptr [rax+rax+00h]
0x14003b017  mov     esi, eax
0x14003b019  test    eax, eax
0x14003b01b  jns     short loc_14003B04B
0x14003b01d  mov     r9d, 98Bh; unsigned int
0x14003b023  lea     r14, aCraticketCreat; "CRATicket::CreateTicket"
0x14003b02a  mov     [rsp+60h+var_38], eax; unsigned int
0x14003b02e  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003b033  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003b03a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003b041  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003b046  jmp     loc_14003B28D
0x14003b04b  mov     rcx, r15; this
0x14003b04e  call    ?InitializeAllVC@CRATicket@@AEAAJXZ; CRATicket::InitializeAllVC(void)
0x14003b053  mov     esi, eax
0x14003b055  test    eax, eax
0x14003b057  jns     short loc_14003B061
0x14003b059  mov     r9d, 98Dh
0x14003b05f  jmp     short loc_14003B023
0x14003b061  mov     rcx, [r13+0]
0x14003b065  mov     rax, [rcx]
0x14003b068  lea     rdx, [rbp+arg_18]
0x14003b06c  mov     rax, [rax+58h]
0x14003b070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b075  mov     esi, eax
0x14003b077  test    eax, eax
0x14003b079  jns     short loc_14003B083
0x14003b07b  mov     r9d, 98Eh
0x14003b081  jmp     short loc_14003B023
0x14003b083  mov     rcx, [rbp+arg_18]
0x14003b087  mov     rax, [rcx]
0x14003b08a  lea     r8, [rbp+arg_8]
0x14003b08e  lea     rdx, _GUID_339b24f2_9bc0_4f16_9aac_f165433d13d4
0x14003b095  mov     rax, [rax]
0x14003b098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b09d  mov     esi, eax
0x14003b09f  test    eax, eax
0x14003b0a1  jns     short loc_14003B0AE
0x14003b0a3  mov     r9d, 991h
0x14003b0a9  jmp     loc_14003B023
0x14003b0ae  mov     rcx, [rbp+arg_8]; struct IRDPSRAPISessionProperties *
0x14003b0b2  call    ?SetCollabProp@@YAJPEAUIRDPSRAPISessionProperties@@PEAGF@Z; SetCollabProp(IRDPSRAPISessionProperties *,ushort *,short)
0x14003b0b7  mov     esi, eax
0x14003b0b9  lea     r14, aCraticketCreat; "CRATicket::CreateTicket"
0x14003b0c0  test    eax, eax
0x14003b0c2  jns     short loc_14003B0CF
0x14003b0c4  mov     r9d, 99Ah
0x14003b0ca  jmp     loc_14003B02A
0x14003b0cf  cmp     dword ptr [r15+88h], 3
0x14003b0d7  jnz     short loc_14003B0DD
0x14003b0d9  xor     esi, esi
0x14003b0db  jmp     short loc_14003B13C
0x14003b0dd  mov     esi, 1388h
0x14003b0e2  call    ?IsTeredoQualified@@YAHK@Z; IsTeredoQualified(ulong)
0x14003b0e7  test    eax, eax
0x14003b0e9  jnz     short loc_14003B13C
0x14003b0eb  call    cs:__imp_GetLastError
0x14003b0f2  nop     dword ptr [rax+rax+00h]
0x14003b0f7  test    eax, eax
0x14003b0f9  jz      short loc_14003B115
0x14003b0fb  call    cs:__imp_GetLastError
0x14003b102  nop     dword ptr [rax+rax+00h]
0x14003b107  test    eax, eax
0x14003b109  jle     short loc_14003B11A
0x14003b10b  movzx   eax, ax
0x14003b10e  or      eax, 80070000h
0x14003b113  jmp     short loc_14003B11A
0x14003b115  mov     eax, 80004005h
0x14003b11a  mov     [rsp+60h+var_38], eax; unsigned int
0x14003b11e  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003b123  mov     r9d, 9ABh; unsigned int
0x14003b129  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003b130  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003b137  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003b13c  mov     r8d, esi; int
0x14003b13f  lea     rdx, aSatwaittimeout; "SATWaitTimeout"
0x14003b146  mov     rcx, [rbp+arg_8]; struct IRDPSRAPISessionProperties *
0x14003b14a  call    ?SetCollabProp@@YAJPEAUIRDPSRAPISessionProperties@@PEAGJ@Z; SetCollabProp(IRDPSRAPISessionProperties *,ushort *,long)
0x14003b14f  mov     r8d, 3; int
0x14003b155  lea     rdx, aMaxcompression; "MaxCompressionLevel"
0x14003b15c  mov     rcx, [rbp+arg_8]; struct IRDPSRAPISessionProperties *
0x14003b160  call    ?SetCollabProp@@YAJPEAUIRDPSRAPISessionProperties@@PEAGJ@Z; SetCollabProp(IRDPSRAPISessionProperties *,ushort *,long)
0x14003b165  mov     r8d, 2
0x14003b16b  lea     rdx, [rbp+arg_10]
0x14003b16f  lea     rcx, aBindaddress; "BindAddress"
0x14003b176  call    ?GetRegistryValue@@YAJPEAGPEAPEAGW4_RAREGHIVE@@@Z; GetRegistryValue(ushort *,ushort * *,_RAREGHIVE)
0x14003b17b  test    eax, eax
0x14003b17d  js      short loc_14003B193
0x14003b17f  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x14003b183  lea     rdx, aBindaddress; "BindAddress"
0x14003b18a  mov     rcx, [rbp+arg_8]; struct IRDPSRAPISessionProperties *
0x14003b18e  call    ?SetCollabProp@@YAJPEAUIRDPSRAPISessionProperties@@PEAG1@Z; SetCollabProp(IRDPSRAPISessionProperties *,ushort *,ushort *)
0x14003b193  mov     r8, [r15+220h]; unsigned __int16 *
0x14003b19a  test    r8, r8
0x14003b19d  jz      short loc_14003B1AF
0x14003b19f  lea     rdx, aActivityid; "ActivityID"
0x14003b1a6  mov     rcx, [rbp+arg_8]; struct IRDPSRAPISessionProperties *
0x14003b1aa  call    ?SetCollabProp@@YAJPEAUIRDPSRAPISessionProperties@@PEAG1@Z; SetCollabProp(IRDPSRAPISessionProperties *,ushort *,ushort *)
0x14003b1af  mov     rcx, [r13+0]
0x14003b1b3  mov     rax, [rcx]
0x14003b1b6  mov     rax, [rax+38h]
0x14003b1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b1bf  mov     esi, eax
0x14003b1c1  test    eax, eax
0x14003b1c3  jns     short loc_14003B1EC
0x14003b1c5  mov     r9d, 9D9h; unsigned int
0x14003b1cb  mov     [rsp+60h+var_38], eax; unsigned int
0x14003b1cf  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003b1d4  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003b1db  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003b1e2  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003b1e7  jmp     loc_14003B276
0x14003b1ec  mov     rcx, [r13+0]
0x14003b1f0  mov     rax, [rcx]
0x14003b1f3  lea     rdx, [rbp+var_18]
0x14003b1f7  mov     rax, [rax+68h]
0x14003b1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b200  mov     esi, eax
0x14003b202  test    eax, eax
0x14003b204  jns     short loc_14003B20E
0x14003b206  mov     r9d, 9DBh
0x14003b20c  jmp     short loc_14003B1CB
0x14003b20e  mov     rcx, [rbp+var_18]
0x14003b212  mov     rax, [rcx]
0x14003b215  lea     rdx, [rbp+var_20]
0x14003b219  mov     qword ptr [rsp+60h+var_38], rdx
0x14003b21e  mov     r13d, 1
0x14003b224  mov     dword ptr [rsp+60h+ppv], r13d
0x14003b229  mov     r9, rbx
0x14003b22c  mov     r8, rdi
0x14003b22f  mov     rdx, [r15+30h]
0x14003b233  mov     rax, [rax+50h]
0x14003b237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b23c  mov     esi, eax
0x14003b23e  test    eax, eax
0x14003b240  jns     short loc_14003B24A
0x14003b242  mov     r9d, 9E1h
0x14003b248  jmp     short loc_14003B1CB
0x14003b24a  mov     rcx, [rbp+var_20]
0x14003b24e  mov     rax, [rcx]
0x14003b251  lea     rdx, [r15+18h]
0x14003b255  mov     rax, [rax+38h]
0x14003b259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b25e  mov     esi, eax
0x14003b260  test    eax, eax
0x14003b262  jns     short loc_14003B26F
0x14003b264  mov     r9d, 9E3h
0x14003b26a  jmp     loc_14003B1CB
0x14003b26f  mov     [r15+214h], r13d
0x14003b276  cmp     [rbp+arg_10], 0
0x14003b27b  jz      short loc_14003B28D
0x14003b27d  mov     rcx, [rbp+arg_10]
0x14003b281  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14003b288  nop     dword ptr [rax+rax+00h]
0x14003b28d  mov     rcx, [rbp+arg_8]
0x14003b291  test    rcx, rcx
0x14003b294  jz      short loc_14003B2AA
0x14003b296  mov     rax, [rcx]
0x14003b299  mov     rax, [rax+10h]
0x14003b29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b2a2  mov     [rbp+arg_8], 0
0x14003b2aa  mov     rcx, rbx; bstrString
0x14003b2ad  call    cs:__imp_SysFreeString
0x14003b2b4  nop     dword ptr [rax+rax+00h]
0x14003b2b9  nop
0x14003b2ba  mov     rcx, rdi; bstrString
0x14003b2bd  call    cs:__imp_SysFreeString
0x14003b2c4  nop     dword ptr [rax+rax+00h]
0x14003b2c9  nop
0x14003b2ca  mov     rcx, [rbp+arg_18]
0x14003b2ce  test    rcx, rcx
0x14003b2d1  jz      short loc_14003B2E0
0x14003b2d3  mov     rax, [rcx]
0x14003b2d6  mov     rax, [rax+10h]
0x14003b2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b2df  nop
0x14003b2e0  mov     rcx, [rbp+var_20]
0x14003b2e4  test    rcx, rcx
0x14003b2e7  jz      short loc_14003B2F6
0x14003b2e9  mov     rax, [rcx]
0x14003b2ec  mov     rax, [rax+10h]
0x14003b2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b2f5  nop
0x14003b2f6  mov     rcx, [rbp+var_18]
0x14003b2fa  test    rcx, rcx
0x14003b2fd  jz      short loc_14003B30C
0x14003b2ff  mov     rax, [rcx]
0x14003b302  mov     rax, [rax+10h]
0x14003b306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b30b  nop
0x14003b30c  mov     eax, esi
0x14003b30e  add     rsp, 60h
0x14003b312  pop     r15
0x14003b314  pop     r14
0x14003b316  pop     r13
0x14003b318  pop     rdi
0x14003b319  pop     rsi
0x14003b31a  pop     rbx
0x14003b31b  pop     rbp
0x14003b31c  retn
0x14003b31e  mov     ecx, 8007000Eh; int
0x14003b323  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
