# UnregisterCspAlerts(_GUID const &)

- ea: `0x1800385f8`
- end: `0x180038779`
- name: `?UnregisterCspAlerts@@YAJAEBU_GUID@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800361b8`

## callees

- `0x1800098dc`
- `0x1800385f8`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038632`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003864b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003864b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038685`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038685`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall UnregisterCspAlerts(const struct _GUID *a1)
{
  int ActivationFactory; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10[4]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  HSTRING v12; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER v13; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)v10 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.AlertDispatcher.DeviceManagementMessageStatics",
         0x4Au,
         &v13,
         &v12) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_fc22b90b_0c41_4808_9bb8_481d4a7898ba, v10);
  v3 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v11 = (__int128)*a1;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v10 + 56LL))(*(_QWORD *)v10, &v11);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v9 = *(_QWORD *)v10;
      if ( *(_QWORD *)v10 )
      {
        *(_QWORD *)v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\asyncalerts.cpp",
        (const char *)(unsigned int)v6,
        v10[0]);
      v8 = *(_QWORD *)v10;
      if ( *(_QWORD *)v10 )
      {
        *(_QWORD *)v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\asyncalerts.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v10[0]);
    v4 = *(_QWORD *)v10;
    if ( *(_QWORD *)v10 )
    {
      *(_QWORD *)v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v3;
  }
}

```

## disassembly

```asm
0x1800385f8  mov     r11, rsp
0x1800385fb  mov     [r11+10h], rbx
0x1800385ff  push    rdi
0x180038600  sub     rsp, 70h
0x180038604  mov     rax, cs:__security_cookie
0x18003860b  xor     rax, rsp
0x18003860e  mov     [rsp+78h+var_18], rax
0x180038613  mov     rdi, rcx
0x180038616  mov     qword ptr [r11-58h], 0
0x18003861e  lea     r9, [r11-38h]; string
0x180038622  lea     r8, [r11-30h]; hstringHeader
0x180038626  mov     edx, 4Ah ; 'J'; length
0x18003862b  lea     rcx, ?RuntimeClass_Windows_Internal_Management_AlertDispatcher_DeviceManagementMessageStatics@@3QBGB; "Windows.Internal.Management.AlertDispat"...
0x180038632  call    cs:__imp_WindowsCreateStringReference
0x180038638  test    eax, eax
0x18003863a  jns     short loc_180038651
0x18003863c  xor     r9d, r9d; lpArguments
0x18003863f  xor     r8d, r8d; nNumberOfArguments
0x180038642  lea     edx, [r9+1]; dwExceptionFlags
0x180038646  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003864b  call    cs:__imp_RaiseException
0x180038651  mov     rbx, [rsp+78h+var_38]
0x180038656  mov     rcx, qword ptr [rsp+78h+var_58]
0x18003865b  test    rcx, rcx
0x18003865e  jz      short loc_180038676
0x180038660  mov     qword ptr [rsp+78h+var_58], 0; int
0x180038669  mov     rax, [rcx]
0x18003866c  mov     rax, [rax+10h]
0x180038670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038675  nop
0x180038676  lea     r8, [rsp+78h+var_58]
0x18003867b  lea     rdx, _GUID_fc22b90b_0c41_4808_9bb8_481d4a7898ba
0x180038682  mov     rcx, rbx
0x180038685  call    cs:__imp_RoGetActivationFactory
0x18003868b  mov     ebx, eax
0x18003868d  test    eax, eax
0x18003868f  jns     short loc_1800386D2
0x180038691  mov     rcx, [rsp+78h]; this
0x180038696  mov     r9d, eax; char *
0x180038699  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\asyncaler"...
0x1800386a0  mov     edx, 28h ; '('; void *
0x1800386a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800386aa  nop
0x1800386ab  mov     rcx, qword ptr [rsp+78h+var_58]
0x1800386b0  test    rcx, rcx
0x1800386b3  jz      short loc_1800386CB
0x1800386b5  mov     qword ptr [rsp+78h+var_58], 0
0x1800386be  mov     rax, [rcx]
0x1800386c1  mov     rax, [rax+10h]
0x1800386c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386ca  nop
0x1800386cb  mov     eax, ebx
0x1800386cd  jmp     loc_18003875D
0x1800386d2  mov     rcx, qword ptr [rsp+78h+var_58]
0x1800386d7  movups  xmm0, xmmword ptr [rdi]
0x1800386da  movdqu  [rsp+78h+var_48], xmm0
0x1800386e0  mov     rax, [rcx]
0x1800386e3  lea     rdx, [rsp+78h+var_48]
0x1800386e8  mov     rax, [rax+38h]
0x1800386ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386f1  mov     ebx, eax
0x1800386f3  test    eax, eax
0x1800386f5  jns     short loc_180038735
0x1800386f7  mov     rcx, [rsp+78h]; this
0x1800386fc  mov     r9d, eax; char *
0x1800386ff  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\asyncaler"...
0x180038706  mov     edx, 29h ; ')'; void *
0x18003870b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038710  nop
0x180038711  mov     rcx, qword ptr [rsp+78h+var_58]
0x180038716  test    rcx, rcx
0x180038719  jz      short loc_180038731
0x18003871b  mov     qword ptr [rsp+78h+var_58], 0
0x180038724  mov     rax, [rcx]
0x180038727  mov     rax, [rax+10h]
0x18003872b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038730  nop
0x180038731  mov     eax, ebx
0x180038733  jmp     short loc_18003875D
0x180038735  mov     rcx, qword ptr [rsp+78h+var_58]
0x18003873a  test    rcx, rcx
0x18003873d  jz      short loc_180038755
0x18003873f  mov     qword ptr [rsp+78h+var_58], 0
0x180038748  mov     rax, [rcx]
0x18003874b  mov     rax, [rax+10h]
0x18003874f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038754  nop
0x180038755  xor     eax, eax
0x180038757  jmp     short loc_18003875D
0x180038759  mov     eax, [rsp+78h+var_58]
0x18003875d  mov     rcx, [rsp+78h+var_18]
0x180038762  xor     rcx, rsp; StackCookie
0x180038765  call    __security_check_cookie
0x18003876a  mov     rbx, [rsp+78h+arg_8]
0x180038772  add     rsp, 70h
0x180038776  pop     rdi
0x180038777  retn
```
