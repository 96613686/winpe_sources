# RegisterForCspAlerts(_GUID const &)

- ea: `0x180038424`
- end: `0x1800385f1`
- name: `?RegisterForCspAlerts@@YAJAEBU_GUID@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001240c`

## callees

- `0x1800098dc`
- `0x180038424`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038464`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038499`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003847d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800384b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003847d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800384b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800384ec`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800384ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RegisterForCspAlerts(const struct _GUID *a1)
{
  int ActivationFactory; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10[4]; // [rsp+20h] [rbp-78h] BYREF
  __int128 v11; // [rsp+30h] [rbp-68h] BYREF
  HSTRING v12; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER v13; // [rsp+48h] [rbp-50h] BYREF
  HSTRING string; // [rsp+60h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_QWORD *)v10 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.AlertDispatcher.DeviceManagementMessageStatics",
         0x4Au,
         &v13,
         &v12) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.AlertListener.ProvAlertListener",
         0x3Bu,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_fc22b90b_0c41_4808_9bb8_481d4a7898ba, v10);
  v3 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v11 = (__int128)*a1;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, HSTRING))(**(_QWORD **)v10 + 48LL))(
           *(_QWORD *)v10,
           &v11,
           string);
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
        (void *)0x1A,
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
      (void *)0x19,
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
0x180038424  mov     r11, rsp
0x180038427  mov     [r11+10h], rbx
0x18003842b  push    rdi
0x18003842c  sub     rsp, 90h
0x180038433  mov     rax, cs:__security_cookie
0x18003843a  xor     rax, rsp
0x18003843d  mov     [rsp+98h+var_18], rax
0x180038445  mov     rdi, rcx
0x180038448  mov     qword ptr [r11-78h], 0
0x180038450  lea     r9, [r11-58h]; string
0x180038454  lea     r8, [r11-50h]; hstringHeader
0x180038458  mov     edx, 4Ah ; 'J'; length
0x18003845d  lea     rcx, ?RuntimeClass_Windows_Internal_Management_AlertDispatcher_DeviceManagementMessageStatics@@3QBGB; "Windows.Internal.Management.AlertDispat"...
0x180038464  call    cs:__imp_WindowsCreateStringReference
0x18003846a  test    eax, eax
0x18003846c  jns     short loc_180038483
0x18003846e  xor     r9d, r9d; lpArguments
0x180038471  xor     r8d, r8d; nNumberOfArguments
0x180038474  lea     edx, [r9+1]; dwExceptionFlags
0x180038478  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003847d  call    cs:__imp_RaiseException
0x180038483  lea     r9, [rsp+98h+string]; string
0x180038488  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18003848d  mov     edx, 3Bh ; ';'; length
0x180038492  lea     rcx, sourceString; "Windows.Internal.Management.AlertListen"...
0x180038499  call    cs:__imp_WindowsCreateStringReference
0x18003849f  test    eax, eax
0x1800384a1  jns     short loc_1800384B8
0x1800384a3  xor     r9d, r9d; lpArguments
0x1800384a6  xor     r8d, r8d; nNumberOfArguments
0x1800384a9  lea     edx, [r9+1]; dwExceptionFlags
0x1800384ad  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800384b2  call    cs:__imp_RaiseException
0x1800384b8  mov     rbx, [rsp+98h+var_58]
0x1800384bd  mov     rcx, qword ptr [rsp+98h+var_78]
0x1800384c2  test    rcx, rcx
0x1800384c5  jz      short loc_1800384DD
0x1800384c7  mov     qword ptr [rsp+98h+var_78], 0; int
0x1800384d0  mov     rax, [rcx]
0x1800384d3  mov     rax, [rax+10h]
0x1800384d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384dc  nop
0x1800384dd  lea     r8, [rsp+98h+var_78]
0x1800384e2  lea     rdx, _GUID_fc22b90b_0c41_4808_9bb8_481d4a7898ba
0x1800384e9  mov     rcx, rbx
0x1800384ec  call    cs:__imp_RoGetActivationFactory
0x1800384f2  mov     ebx, eax
0x1800384f4  test    eax, eax
0x1800384f6  jns     short loc_18003853C
0x1800384f8  mov     rcx, [rsp+98h]; this
0x180038500  mov     r9d, eax; char *
0x180038503  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\asyncaler"...
0x18003850a  mov     edx, 19h; void *
0x18003850f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038514  nop
0x180038515  mov     rcx, qword ptr [rsp+98h+var_78]
0x18003851a  test    rcx, rcx
0x18003851d  jz      short loc_180038535
0x18003851f  mov     qword ptr [rsp+98h+var_78], 0
0x180038528  mov     rax, [rcx]
0x18003852b  mov     rax, [rax+10h]
0x18003852f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038534  nop
0x180038535  mov     eax, ebx
0x180038537  jmp     loc_1800385CF
0x18003853c  mov     rcx, qword ptr [rsp+98h+var_78]
0x180038541  movups  xmm0, xmmword ptr [rdi]
0x180038544  movdqu  [rsp+98h+var_68], xmm0
0x18003854a  mov     rax, [rcx]
0x18003854d  mov     r8, [rsp+98h+string]
0x180038552  lea     rdx, [rsp+98h+var_68]
0x180038557  mov     rax, [rax+30h]
0x18003855b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038560  mov     ebx, eax
0x180038562  test    eax, eax
0x180038564  jns     short loc_1800385A7
0x180038566  mov     rcx, [rsp+98h]; this
0x18003856e  mov     r9d, eax; char *
0x180038571  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\asyncaler"...
0x180038578  mov     edx, 1Ah; void *
0x18003857d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038582  nop
0x180038583  mov     rcx, qword ptr [rsp+98h+var_78]
0x180038588  test    rcx, rcx
0x18003858b  jz      short loc_1800385A3
0x18003858d  mov     qword ptr [rsp+98h+var_78], 0
0x180038596  mov     rax, [rcx]
0x180038599  mov     rax, [rax+10h]
0x18003859d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385a2  nop
0x1800385a3  mov     eax, ebx
0x1800385a5  jmp     short loc_1800385CF
0x1800385a7  mov     rcx, qword ptr [rsp+98h+var_78]
0x1800385ac  test    rcx, rcx
0x1800385af  jz      short loc_1800385C7
0x1800385b1  mov     qword ptr [rsp+98h+var_78], 0
0x1800385ba  mov     rax, [rcx]
0x1800385bd  mov     rax, [rax+10h]
0x1800385c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385c6  nop
0x1800385c7  xor     eax, eax
0x1800385c9  jmp     short loc_1800385CF
0x1800385cb  mov     eax, [rsp+98h+var_78]
0x1800385cf  mov     rcx, [rsp+98h+var_18]
0x1800385d7  xor     rcx, rsp; StackCookie
0x1800385da  call    __security_check_cookie
0x1800385df  mov     rbx, [rsp+98h+arg_8]
0x1800385e7  add     rsp, 90h
0x1800385ee  pop     rdi
0x1800385ef  retn
```
