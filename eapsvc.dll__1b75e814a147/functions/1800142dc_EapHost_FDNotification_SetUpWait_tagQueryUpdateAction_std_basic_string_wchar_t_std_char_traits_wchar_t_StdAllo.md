# EapHost::FDNotification::SetUpWait(tagQueryUpdateAction,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x1800142dc`
- end: `0x1800147ab`
- name: `?SetUpWait@FDNotification@EapHost@@QEAAXW4tagQueryUpdateAction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `1231`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011cb0`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c40c`
- `0x18000d338`
- `0x18000d3b8`
- `0x18000ea5c`
- `0x1800142dc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014407`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014407`
- `ntdll!EtwEventEnabled` at `0x18001446b`
- `ntdll!EtwEventEnabled` at `0x180014561`
- `ntdll!EtwEventEnabled` at `0x1800145f7`
- `ntdll!EtwEventEnabled` at `0x18001468d`
- `ntdll!EtwEventEnabled` at `0x180014723`
- `ntdll!EtwEventEnabled` at `0x18001446b`
- `ntdll!EtwEventEnabled` at `0x180014561`
- `ntdll!EtwEventEnabled` at `0x1800145f7`
- `ntdll!EtwEventEnabled` at `0x18001468d`
- `ntdll!EtwEventEnabled` at `0x180014723`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014340`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014340`

## string_xrefs

- `0x18001456e`: `Cannote create FunctionDiscovery object when setting up Function Discovery wait, 0x%x`
- `0x180014604`: `CreateInstanceCollectionQuery failed while setting up Function Discovery wait, 0x%x`

## pseudocode

```c
__int64 __fastcall EapHost::FDNotification::SetUpWait(__int64 a1, __int64 a2, __int64 *a3)
{
  HRESULT v5; // edi
  _QWORD *v6; // r14
  int v7; // edi
  int v8; // edi
  int v9; // edi
  _QWORD *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 result; // rax
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rax
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-B0h] BYREF
  char *v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+6Ch] [rbp-94h]
  char v23[2048]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  v18 = 0;
  v5 = CoCreateInstance(
         &GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc,
         0,
         0x17u,
         &GUID_4df99b70_e148_4432_b004_4c9eeb535a5e,
         &ppv);
  if ( v5 < 0 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v23,
                0x800u,
                "Cannote create FunctionDiscovery object when setting up Function Discovery wait, 0x%x",
                v5) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v23);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids,
        (unsigned int)v5);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v5);
  }
  v6 = (_QWORD *)(a1 + 32);
  v7 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD, __int64, _QWORD, __int64))(*(_QWORD *)ppv + 40LL))(
         ppv,
         L"Provider\\Microsoft.Base.PnP",
         0,
         0,
         a1,
         0,
         a1 + 32);
  if ( v7 < 0 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v23,
                0x800u,
                "CreateInstanceCollectionQuery failed while setting up Function Discovery wait, 0x%x",
                v7) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v23);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids,
        (unsigned int)v7);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v7);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)*v6 + 24LL))(
         *v6,
         L"InterfaceClass",
         L"{65A9A6CF-64CD-480b-843E-32C86E1BA19F}");
  if ( v8 < 0 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v23,
                0x800u,
                "AddQueryConstraint failed while setting up Function Discovery wait, 0x%x",
                v8) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v23);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids,
        (unsigned int)v8);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v8);
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v6 + 40LL))(*v6, &v18);
  if ( v9 < 0 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v23,
                0x800u,
                "Execute FunctionDiscovery query failed while setting up Function Discovery wait, 0x%x",
                v9) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v23);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids,
        (unsigned int)v9);
    SystemError::Throw<long>((__int64)&byte_180018CBC, v9);
  }
  *(_DWORD *)(a1 + 40) = 0;
  v10 = a3 + 3;
  if ( (__int64 *)(a1 + 48) != a3 )
  {
    if ( *v10 <= 7u )
      v11 = (__int64)a3;
    else
      v11 = *a3;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(a1 + 48, v11, a3[2]);
  }
  *(_BYTE *)(a1 + 44) = 1;
  if ( !ResetEvent(*(HANDLE *)(a1 + 24)) )
    SystemError::Throw(L"ResetEvent");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v10 = a3 + 3;
    if ( (unsigned __int64)a3[3] <= 7 )
      v12 = (__int64)a3;
    else
      v12 = *a3;
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids,
      0,
      v12);
  }
  result = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
  if ( (_BYTE)result )
  {
    if ( *v10 > 7u )
      a3 = (__int64 *)*a3;
    result = StringCchPrintfA(
               v23,
               0x800u,
               "Successfully set up wait for FD notification of action %u for key value %S",
               0,
               (const wchar_t *)a3);
    if ( (int)result >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v23[v16] );
      v20 = v23;
      v21 = v16 + 1;
      v22 = 0;
      result = McGenEventWrite_EtwEventWriteTransfer(
                 (unsigned int)&eaphost_Context,
                 (unsigned int)DebugInfoEvent,
                 v14,
                 v15,
                 (__int64)v19);
    }
  }
  if ( v18 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( ppv )
    return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return result;
}

```

## disassembly

```asm
0x1800142dc  mov     [rsp-8+arg_8], rbx
0x1800142e1  mov     [rsp-8+arg_18], rsi
0x1800142e6  push    rbp
0x1800142e7  push    rdi
0x1800142e8  push    r14
0x1800142ea  lea     rbp, [rsp-780h]
0x1800142f2  sub     rsp, 880h
0x1800142f9  mov     rax, cs:__security_cookie
0x180014300  xor     rax, rsp
0x180014303  mov     [rbp+790h+var_20], rax
0x18001430a  mov     rbx, r8
0x18001430d  mov     rsi, rcx
0x180014310  mov     [rsp+890h+var_850], 0
0x180014319  mov     [rsp+890h+var_848], 0
0x180014322  lea     rax, [rsp+890h+var_850]
0x180014327  mov     [rsp+890h+ppv], rax; ppv
0x18001432c  lea     r9, _GUID_4df99b70_e148_4432_b004_4c9eeb535a5e; riid
0x180014333  xor     edx, edx; pUnkOuter
0x180014335  lea     r8d, [rdx+17h]; dwClsContext
0x180014339  lea     rcx, _GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc; rclsid
0x180014340  call    cs:__imp_CoCreateInstance
0x180014346  mov     edi, eax
0x180014348  test    eax, eax
0x18001434a  js      loc_180014553
0x180014350  mov     rcx, [rsp+890h+var_850]
0x180014355  lea     r14, [rsi+20h]
0x180014359  mov     rax, [rcx]
0x18001435c  mov     [rsp+890h+var_860], r14
0x180014361  mov     [rsp+890h+var_868], 0
0x18001436a  mov     [rsp+890h+ppv], rsi
0x18001436f  xor     r9d, r9d
0x180014372  xor     r8d, r8d
0x180014375  lea     rdx, aProviderMicros; "Provider\\Microsoft.Base.PnP"
0x18001437c  mov     rax, [rax+28h]
0x180014380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014385  mov     edi, eax
0x180014387  test    eax, eax
0x180014389  js      loc_1800145E9
0x18001438f  mov     rcx, [r14]
0x180014392  mov     rax, [rcx]
0x180014395  lea     r8, a65a9a6cf64cd48; "{65A9A6CF-64CD-480b-843E-32C86E1BA19F}"
0x18001439c  lea     rdx, aInterfaceclass; "InterfaceClass"
0x1800143a3  mov     rax, [rax+18h]
0x1800143a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ac  mov     edi, eax
0x1800143ae  test    eax, eax
0x1800143b0  js      loc_18001467F
0x1800143b6  mov     rcx, [r14]
0x1800143b9  mov     rax, [rcx]
0x1800143bc  lea     rdx, [rsp+890h+var_848]
0x1800143c1  mov     rax, [rax+28h]
0x1800143c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ca  mov     edi, eax
0x1800143cc  test    eax, eax
0x1800143ce  js      loc_180014715
0x1800143d4  mov     dword ptr [rsi+28h], 0
0x1800143db  lea     rcx, [rsi+30h]
0x1800143df  lea     rdi, [rbx+18h]
0x1800143e3  cmp     rcx, rbx
0x1800143e6  jz      short loc_1800143FF
0x1800143e8  cmp     qword ptr [rdi], 7
0x1800143ec  jbe     short loc_1800143F3
0x1800143ee  mov     rdx, [rbx]
0x1800143f1  jmp     short loc_1800143F6
0x1800143f3  mov     rdx, rbx
0x1800143f6  mov     r8, [rbx+10h]
0x1800143fa  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x1800143ff  mov     byte ptr [rsi+2Ch], 1
0x180014403  mov     rcx, [rsi+18h]; hEvent
0x180014407  call    cs:__imp_ResetEvent
0x18001440d  test    eax, eax
0x18001440f  jz      loc_180014546
0x180014415  lea     rax, WPP_GLOBAL_Control
0x18001441c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014423  cmp     rcx, rax
0x180014426  jz      short loc_18001445D
0x180014428  test    byte ptr [rcx+1Ch], 4
0x18001442c  jz      short loc_18001445D
0x18001442e  lea     rdi, [rbx+18h]
0x180014432  cmp     qword ptr [rdi], 7
0x180014436  jbe     short loc_18001443D
0x180014438  mov     rax, [rbx]
0x18001443b  jmp     short loc_180014440
0x18001443d  mov     rax, rbx
0x180014440  mov     edx, 0Fh
0x180014445  mov     [rsp+890h+ppv], rax
0x18001444a  xor     r9d, r9d
0x18001444d  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180014454  mov     rcx, [rcx+10h]
0x180014458  call    WPP_SF_DS
0x18001445d  lea     rdx, DebugInfoEvent
0x180014464  mov     rcx, cs:eaphost_Context
0x18001446b  call    cs:__imp_EtwEventEnabled
0x180014471  test    al, al
0x180014473  jz      short loc_1800144F1
0x180014475  cmp     qword ptr [rdi], 7
0x180014479  jbe     short loc_18001447E
0x18001447b  mov     rbx, [rbx]
0x18001447e  mov     [rsp+890h+ppv], rbx
0x180014483  xor     r9d, r9d
0x180014486  lea     r8, aSuccessfullySe; "Successfully set up wait for FD notific"...
0x18001448d  mov     edx, 800h; unsigned __int64
0x180014492  lea     rcx, [rsp+890h+var_820]; char *
0x180014497  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001449c  test    eax, eax
0x18001449e  js      short loc_1800144F1
0x1800144a0  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800144a7  jge     short loc_1800144F1
0x1800144a9  lea     rcx, [rsp+890h+var_820]
0x1800144ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800144b2  inc     rax
0x1800144b5  cmp     byte ptr [rcx+rax], 0
0x1800144b9  jnz     short loc_1800144B2
0x1800144bb  inc     eax
0x1800144bd  lea     rcx, [rsp+890h+var_820]
0x1800144c2  mov     [rsp+890h+var_830], rcx
0x1800144c7  mov     [rsp+890h+var_828], eax
0x1800144cb  mov     [rsp+890h+var_824], 0
0x1800144d3  lea     rax, [rsp+890h+var_840]
0x1800144d8  mov     [rsp+890h+ppv], rax
0x1800144dd  lea     rdx, DebugInfoEvent
0x1800144e4  lea     rcx, eaphost_Context
0x1800144eb  call    McGenEventWrite_EtwEventWriteTransfer
0x1800144f0  nop
0x1800144f1  mov     rcx, [rsp+890h+var_848]
0x1800144f6  test    rcx, rcx
0x1800144f9  jz      short loc_180014508
0x1800144fb  mov     rax, [rcx]
0x1800144fe  mov     rax, [rax+10h]
0x180014502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014507  nop
0x180014508  mov     rcx, [rsp+890h+var_850]
0x18001450d  test    rcx, rcx
0x180014510  jz      short loc_18001451F
0x180014512  mov     rax, [rcx]
0x180014515  mov     rax, [rax+10h]
0x180014519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001451e  nop
0x18001451f  mov     rcx, [rbp+790h+var_20]
0x180014526  xor     rcx, rsp; StackCookie
0x180014529  call    __security_check_cookie
0x18001452e  lea     r11, [rsp+890h+var_10]
0x180014536  mov     rbx, [r11+28h]
0x18001453a  mov     rsi, [r11+38h]
0x18001453e  mov     rsp, r11
0x180014541  pop     r14
0x180014543  pop     rdi
0x180014544  pop     rbp
0x180014545  retn
0x180014546  lea     rcx, aResetevent; "ResetEvent"
0x18001454d  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x180014553  lea     rdx, DebugErrorEvent
0x18001455a  mov     rcx, cs:eaphost_Context
0x180014561  call    cs:__imp_EtwEventEnabled
0x180014567  test    al, al
0x180014569  jz      short loc_1800145A9
0x18001456b  mov     r9d, edi
0x18001456e  lea     r8, aCannoteCreateF; "Cannote create FunctionDiscovery object"...
0x180014575  mov     edx, 800h; unsigned __int64
0x18001457a  lea     rcx, [rsp+890h+var_820]; char *
0x18001457f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014584  test    eax, eax
0x180014586  js      short loc_1800145A9
0x180014588  test    cs:byte_180020AC1, 8
0x18001458f  jz      short loc_1800145A9
0x180014591  lea     r8, [rsp+890h+var_820]
0x180014596  lea     rdx, DebugErrorEvent
0x18001459d  lea     rcx, eaphost_Context
0x1800145a4  call    McTemplateU0s_EtwEventWriteTransfer
0x1800145a9  lea     rax, WPP_GLOBAL_Control
0x1800145b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145b7  cmp     rcx, rax
0x1800145ba  jz      short loc_1800145DA
0x1800145bc  test    byte ptr [rcx+1Ch], 1
0x1800145c0  jz      short loc_1800145DA
0x1800145c2  mov     edx, 0Bh
0x1800145c7  mov     r9d, edi
0x1800145ca  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x1800145d1  mov     rcx, [rcx+10h]
0x1800145d5  call    WPP_SF_d
0x1800145da  mov     edx, edi
0x1800145dc  lea     rcx, byte_180018CBC
0x1800145e3  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x1800145e9  lea     rdx, DebugErrorEvent
0x1800145f0  mov     rcx, cs:eaphost_Context
0x1800145f7  call    cs:__imp_EtwEventEnabled
0x1800145fd  test    al, al
0x1800145ff  jz      short loc_18001463F
0x180014601  mov     r9d, edi
0x180014604  lea     r8, aCreateinstance; "CreateInstanceCollectionQuery failed wh"...
0x18001460b  mov     edx, 800h; unsigned __int64
0x180014610  lea     rcx, [rsp+890h+var_820]; char *
0x180014615  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001461a  test    eax, eax
0x18001461c  js      short loc_18001463F
0x18001461e  test    cs:byte_180020AC1, 8
0x180014625  jz      short loc_18001463F
0x180014627  lea     r8, [rsp+890h+var_820]
0x18001462c  lea     rdx, DebugErrorEvent
0x180014633  lea     rcx, eaphost_Context
0x18001463a  call    McTemplateU0s_EtwEventWriteTransfer
0x18001463f  lea     rax, WPP_GLOBAL_Control
0x180014646  mov     rcx, cs:WPP_GLOBAL_Control
0x18001464d  cmp     rcx, rax
0x180014650  jz      short loc_180014670
0x180014652  test    byte ptr [rcx+1Ch], 1
0x180014656  jz      short loc_180014670
0x180014658  mov     edx, 0Ch
0x18001465d  mov     r9d, edi
0x180014660  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180014667  mov     rcx, [rcx+10h]
0x18001466b  call    WPP_SF_d
0x180014670  mov     edx, edi
0x180014672  lea     rcx, byte_180018CBC
0x180014679  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x18001467f  lea     rdx, DebugErrorEvent
0x180014686  mov     rcx, cs:eaphost_Context
0x18001468d  call    cs:__imp_EtwEventEnabled
0x180014693  test    al, al
0x180014695  jz      short loc_1800146D5
0x180014697  mov     r9d, edi
0x18001469a  lea     r8, aAddqueryconstr; "AddQueryConstraint failed while setting"...
0x1800146a1  mov     edx, 800h; unsigned __int64
0x1800146a6  lea     rcx, [rsp+890h+var_820]; char *
0x1800146ab  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800146b0  test    eax, eax
0x1800146b2  js      short loc_1800146D5
0x1800146b4  test    cs:byte_180020AC1, 8
0x1800146bb  jz      short loc_1800146D5
0x1800146bd  lea     r8, [rsp+890h+var_820]
0x1800146c2  lea     rdx, DebugErrorEvent
0x1800146c9  lea     rcx, eaphost_Context
0x1800146d0  call    McTemplateU0s_EtwEventWriteTransfer
0x1800146d5  lea     rax, WPP_GLOBAL_Control
0x1800146dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146e3  cmp     rcx, rax
0x1800146e6  jz      short loc_180014706
0x1800146e8  test    byte ptr [rcx+1Ch], 1
0x1800146ec  jz      short loc_180014706
0x1800146ee  mov     edx, 0Dh
0x1800146f3  mov     r9d, edi
0x1800146f6  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x1800146fd  mov     rcx, [rcx+10h]
0x180014701  call    WPP_SF_d
0x180014706  mov     edx, edi
0x180014708  lea     rcx, byte_180018CBC
0x18001470f  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x180014715  lea     rdx, DebugErrorEvent
0x18001471c  mov     rcx, cs:eaphost_Context
0x180014723  call    cs:__imp_EtwEventEnabled
0x180014729  test    al, al
0x18001472b  jz      short loc_18001476B
0x18001472d  mov     r9d, edi
0x180014730  lea     r8, aExecuteFunctio; "Execute FunctionDiscovery query failed "...
0x180014737  mov     edx, 800h; unsigned __int64
0x18001473c  lea     rcx, [rsp+890h+var_820]; char *
0x180014741  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180014746  test    eax, eax
0x180014748  js      short loc_18001476B
0x18001474a  test    cs:byte_180020AC1, 8
0x180014751  jz      short loc_18001476B
0x180014753  lea     r8, [rsp+890h+var_820]
0x180014758  lea     rdx, DebugErrorEvent
0x18001475f  lea     rcx, eaphost_Context
0x180014766  call    McTemplateU0s_EtwEventWriteTransfer
0x18001476b  lea     rax, WPP_GLOBAL_Control
0x180014772  mov     rcx, cs:WPP_GLOBAL_Control
0x180014779  cmp     rcx, rax
0x18001477c  jz      short loc_18001479C
0x18001477e  test    byte ptr [rcx+1Ch], 1
0x180014782  jz      short loc_18001479C
0x180014784  mov     edx, 0Eh
0x180014789  mov     r9d, edi
0x18001478c  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180014793  mov     rcx, [rcx+10h]
0x180014797  call    WPP_SF_d
0x18001479c  mov     edx, edi
0x18001479e  lea     rcx, byte_180018CBC
0x1800147a5  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
```
