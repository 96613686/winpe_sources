# MvKeyFromSecuredCore

- ea: `0x180022448`
- end: `0x1800226d9`
- name: `MvKeyFromSecuredCore`
- size: `657`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017d04`

## callees

- `0x1800076a4`
- `0x180015270`
- `0x1800186c8`
- `0x180018788`
- `0x180022448`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002253a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002253a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022576`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800224a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800224a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800224b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800224b3`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x180022530`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x180022530`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18002256a`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x18002256a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800224f9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800224f9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800224ca`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800224ca`

## string_xrefs

- `0x1800224c1`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MvKeyFromSecuredCore(const unsigned __int16 **a1, __int64 a2, _QWORD *a3)
{
  signed int v6; // ebx
  DWORD FirmwareEnvironmentVariableW; // edi
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  const unsigned __int16 *v10; // rcx
  signed int LastError; // eax
  const unsigned __int16 *v12; // rcx
  bool v13; // bl
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int PreviousState; // [rsp+20h] [rbp-50h]
  _BYTE pBuffer[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  void *TokenHandle[2]; // [rsp+40h] [rbp-30h] BYREF
  _LUID Luid[2]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  *a3 = 0;
  pBuffer[0] = 0;
  TokenHandle[1] = &NvRam::`vftable';
  v6 = 0;
  if ( `NvRam::Initialize'::`2'::s_fIsInitialized )
  {
LABEL_11:
    pBuffer[0] = 0;
    FirmwareEnvironmentVariableW = GetFirmwareEnvironmentVariableW(
                                     L"BuiltAsSecuredCorePC",
                                     L"{77FA9ABD-0359-4D32-BD60-28F4E78F784B}",
                                     pBuffer,
                                     1u);
    if ( !FirmwareEnvironmentVariableW )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_14;
  }
  FirmwareEnvironmentVariableW = 0;
  TokenHandle[0] = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, L"SeSystemEnvironmentPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      if ( AdjustTokenPrivileges(TokenHandle[0], 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
        goto LABEL_9;
    }
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_9:
    if ( SetFirmwareEnvironmentVariableW(&Src, L"{00000000-0000-0000-0000-000000000000}", 0, 0) || GetLastError() == 1 )
    {
      v6 = -2147418113;
      goto LABEL_14;
    }
    `NvRam::Initialize'::`2'::s_fIsInitialized = 1;
    goto LABEL_11;
  }
LABEL_14:
  LogNvRamGetVariable(v10, v6);
  if ( v6 >= 0 )
  {
    v13 = 0;
    if ( FirmwareEnvironmentVariableW )
      v13 = pBuffer[0] != 0;
    LogIsSecuredCore(v12, v13);
    if ( v13 )
    {
      v21 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)a2 + 24LL))(
              a2,
              0,
              &GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0,
              &v21);
      v6 = v14;
      if ( v14 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v21 + 24LL))(
                v21,
                *a1,
                a1[1]);
        v6 = v16;
        if ( v16 >= 0 )
        {
          LogHandlerKeysReturned(L"SystemHandler", L"SecuredCore", *a1, a1[1]);
          *a3 = v21;
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13C,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\system\\systemhandler.cpp",
            (const char *)(unsigned int)v16,
            PreviousState);
          v17 = v21;
          if ( v21 )
          {
            v21 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13B,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\system\\systemhandler.cpp",
          (const char *)(unsigned int)v14,
          PreviousState);
        v15 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\system\\systemhandler.cpp",
      (const char *)(unsigned int)v6,
      PreviousState);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022448  mov     [rsp-28h+arg_18], rbx
0x18002244d  push    rbp
0x18002244e  push    rsi
0x18002244f  push    rdi
0x180022450  push    r14
0x180022452  push    r15
0x180022454  mov     rbp, rsp
0x180022457  sub     rsp, 70h
0x18002245b  mov     rax, cs:__security_cookie
0x180022462  xor     rax, rsp
0x180022465  mov     [rbp+var_10], rax
0x180022469  mov     r14, r8
0x18002246c  mov     r15, rdx
0x18002246f  mov     rsi, rcx
0x180022472  mov     qword ptr [r8], 0
0x180022479  mov     [rbp+pBuffer], 0
0x18002247d  lea     rax, ??_7NvRam@@6B@; const NvRam::`vftable'
0x180022484  mov     [rbp+var_28], rax
0x180022488  xor     ebx, ebx
0x18002248a  cmp     cs:?s_fIsInitialized@?1??Initialize@NvRam@@AEAAJXZ@4HA, ebx; int `NvRam::Initialize(void)'::`2'::s_fIsInitialized
0x180022490  jnz     loc_18002254F
0x180022496  xor     edi, edi
0x180022498  mov     [rbp+TokenHandle], rbx
0x18002249c  xorps   xmm0, xmm0
0x18002249f  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x1800224a3  call    cs:__imp_GetCurrentProcess
0x1800224a9  mov     rcx, rax; ProcessHandle
0x1800224ac  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800224b0  lea     edx, [rbx+28h]; DesiredAccess
0x1800224b3  call    cs:__imp_OpenProcessToken
0x1800224b9  test    eax, eax
0x1800224bb  jz      short loc_180022503
0x1800224bd  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x1800224c1  lea     rdx, Name; "SeSystemEnvironmentPrivilege"
0x1800224c8  xor     ecx, ecx; lpSystemName
0x1800224ca  call    cs:__imp_LookupPrivilegeValueW
0x1800224d0  test    eax, eax
0x1800224d2  jz      short loc_180022503
0x1800224d4  mov     [rbp+Luid.LowPart], 1
0x1800224db  mov     [rbp+Luid.HighPart+8], 2
0x1800224e2  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x1800224e7  mov     [rsp+70h+PreviousState], rbx; int
0x1800224ec  xor     r9d, r9d; BufferLength
0x1800224ef  lea     r8, [rbp+Luid]; NewState
0x1800224f3  xor     edx, edx; DisableAllPrivileges
0x1800224f5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800224f9  call    cs:__imp_AdjustTokenPrivileges
0x1800224ff  test    eax, eax
0x180022501  jnz     short loc_18002251C
0x180022503  call    cs:__imp_GetLastError
0x180022509  mov     ebx, eax
0x18002250b  test    eax, eax
0x18002250d  jle     short loc_180022518
0x18002250f  movzx   ebx, ax
0x180022512  or      ebx, 80070000h
0x180022518  test    ebx, ebx
0x18002251a  js      short loc_18002258B
0x18002251c  xor     r9d, r9d; nSize
0x18002251f  xor     r8d, r8d; pValue
0x180022522  lea     rdx, Guid; "{00000000-0000-0000-0000-000000000000}"
0x180022529  lea     rcx, Src; lpName
0x180022530  call    cs:__imp_SetFirmwareEnvironmentVariableW
0x180022536  test    eax, eax
0x180022538  jnz     short loc_1800225B3
0x18002253a  call    cs:__imp_GetLastError
0x180022540  cmp     eax, 1
0x180022543  jz      short loc_1800225B3
0x180022545  mov     cs:?s_fIsInitialized@?1??Initialize@NvRam@@AEAAJXZ@4HA, 1; int `NvRam::Initialize(void)'::`2'::s_fIsInitialized
0x18002254f  xor     eax, eax
0x180022551  mov     [rbp+pBuffer], al
0x180022554  lea     r9d, [rax+1]; nSize
0x180022558  lea     r8, [rbp+pBuffer]; pBuffer
0x18002255c  lea     rdx, a77fa9abd03594d; "{77FA9ABD-0359-4D32-BD60-28F4E78F784B}"
0x180022563  lea     rcx, aBuiltassecured; "BuiltAsSecuredCorePC"
0x18002256a  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180022570  mov     edi, eax
0x180022572  test    eax, eax
0x180022574  jnz     short loc_18002258B
0x180022576  call    cs:__imp_GetLastError
0x18002257c  mov     ebx, eax
0x18002257e  test    eax, eax
0x180022580  jle     short loc_18002258B
0x180022582  movzx   ebx, ax
0x180022585  or      ebx, 80070000h
0x18002258b  mov     edx, ebx; int
0x18002258d  call    ?LogNvRamGetVariable@@YAXPEBGJ@Z; LogNvRamGetVariable(ushort const *,long)
0x180022592  test    ebx, ebx
0x180022594  jns     short loc_1800225BA
0x180022596  mov     rcx, [rbp+28h]; this
0x18002259a  mov     r9d, ebx; char *
0x18002259d  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800225a4  mov     edx, 12Bh; void *
0x1800225a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800225ae  jmp     loc_1800226B7
0x1800225b3  mov     ebx, 8000FFFFh
0x1800225b8  jmp     short loc_18002258B
0x1800225ba  xor     bl, bl
0x1800225bc  test    edi, edi
0x1800225be  jz      short loc_1800225C6
0x1800225c0  cmp     [rbp+pBuffer], bl
0x1800225c3  setnz   bl
0x1800225c6  mov     dl, bl; bool
0x1800225c8  call    ?LogIsSecuredCore@@YAXPEBG_N@Z; LogIsSecuredCore(ushort const *,bool)
0x1800225cd  test    bl, bl
0x1800225cf  jnz     short loc_1800225DB
0x1800225d1  mov     ebx, 80004005h
0x1800225d6  jmp     loc_1800226B7
0x1800225db  mov     [rbp+var_38], 0
0x1800225e3  mov     rax, [r15]
0x1800225e6  lea     r9, [rbp+var_38]
0x1800225ea  lea     r8, _GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0
0x1800225f1  xor     edx, edx
0x1800225f3  mov     rcx, r15
0x1800225f6  mov     rax, [rax+18h]
0x1800225fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225ff  mov     ebx, eax
0x180022601  test    eax, eax
0x180022603  jns     short loc_18002263E
0x180022605  mov     rcx, [rbp+28h]; this
0x180022609  mov     r9d, eax; char *
0x18002260c  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180022613  mov     edx, 13Bh; void *
0x180022618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002261d  nop
0x18002261e  mov     rcx, [rbp+var_38]
0x180022622  test    rcx, rcx
0x180022625  jz      short loc_18002263C
0x180022627  mov     [rbp+var_38], 0
0x18002262f  mov     rax, [rcx]
0x180022632  mov     rax, [rax+10h]
0x180022636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002263b  nop
0x18002263c  jmp     short loc_1800226B7
0x18002263e  mov     rcx, [rbp+var_38]
0x180022642  mov     rax, [rcx]
0x180022645  mov     r8, [rsi+8]
0x180022649  mov     rdx, [rsi]
0x18002264c  mov     rax, [rax+18h]
0x180022650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022655  mov     ebx, eax
0x180022657  test    eax, eax
0x180022659  jns     short loc_180022694
0x18002265b  mov     rcx, [rbp+28h]; this
0x18002265f  mov     r9d, eax; char *
0x180022662  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180022669  mov     edx, 13Ch; void *
0x18002266e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022673  nop
0x180022674  mov     rcx, [rbp+var_38]
0x180022678  test    rcx, rcx
0x18002267b  jz      short loc_180022692
0x18002267d  mov     [rbp+var_38], 0
0x180022685  mov     rax, [rcx]
0x180022688  mov     rax, [rax+10h]
0x18002268c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022691  nop
0x180022692  jmp     short loc_1800226B7
0x180022694  mov     r9, [rsi+8]; unsigned __int16 *
0x180022698  mov     r8, [rsi]; unsigned __int16 *
0x18002269b  lea     rdx, aSecuredcore; "SecuredCore"
0x1800226a2  lea     rcx, ?c_szSystemHandler@@3QBGB; "SystemHandler"
0x1800226a9  call    ?LogHandlerKeysReturned@@YAXPEBG000@Z; LogHandlerKeysReturned(ushort const *,ushort const *,ushort const *,ushort const *)
0x1800226ae  mov     rax, [rbp+var_38]
0x1800226b2  mov     [r14], rax
0x1800226b5  xor     ebx, ebx
0x1800226b7  mov     eax, ebx
0x1800226b9  mov     rcx, [rbp+var_10]
0x1800226bd  xor     rcx, rsp; StackCookie
0x1800226c0  call    __security_check_cookie
0x1800226c5  mov     rbx, [rsp+70h+arg_18]
0x1800226cd  add     rsp, 70h
0x1800226d1  pop     r15
0x1800226d3  pop     r14
0x1800226d5  pop     rdi
0x1800226d6  pop     rsi
0x1800226d7  pop     rbp
0x1800226d8  retn
```
