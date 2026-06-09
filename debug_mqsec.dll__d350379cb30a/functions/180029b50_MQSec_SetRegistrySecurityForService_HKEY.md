# MQSec_SetRegistrySecurityForService(HKEY__ *)

- ea: `0x180029b50`
- end: `0x180029faf`
- name: `?MQSec_SetRegistrySecurityForService@@YAJPEAUHKEY__@@@Z`
- size: `1119`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004074`
- `0x180013940`
- `0x18001722c`
- `0x180017430`
- `0x1800216f0`
- `0x18002934c`
- `0x180029b50`

## import_xrefs

- `msvcrt!free` at `0x180029c06`
- `msvcrt!free` at `0x180029caf`
- `msvcrt!free` at `0x180029cb9`
- `msvcrt!free` at `0x180029d59`
- `msvcrt!free` at `0x180029d63`
- `msvcrt!free` at `0x180029dc5`
- `msvcrt!free` at `0x180029dcf`
- `msvcrt!free` at `0x180029e38`
- `msvcrt!free` at `0x180029e42`
- `msvcrt!free` at `0x180029ea2`
- `msvcrt!free` at `0x180029eac`
- `msvcrt!free` at `0x180029f0c`
- `msvcrt!free` at `0x180029f16`
- `msvcrt!free` at `0x180029f6b`
- `msvcrt!free` at `0x180029f75`
- `msvcrt!free` at `0x180029f8e`
- `msvcrt!free` at `0x180029f98`
- `msvcrt!free` at `0x180029c06`
- `msvcrt!free` at `0x180029caf`
- `msvcrt!free` at `0x180029cb9`
- `msvcrt!free` at `0x180029d59`
- `msvcrt!free` at `0x180029d63`
- `msvcrt!free` at `0x180029dc5`
- `msvcrt!free` at `0x180029dcf`
- `msvcrt!free` at `0x180029e38`
- `msvcrt!free` at `0x180029e42`
- `msvcrt!free` at `0x180029ea2`
- `msvcrt!free` at `0x180029eac`
- `msvcrt!free` at `0x180029f0c`
- `msvcrt!free` at `0x180029f16`
- `msvcrt!free` at `0x180029f6b`
- `msvcrt!free` at `0x180029f75`
- `msvcrt!free` at `0x180029f8e`
- `msvcrt!free` at `0x180029f98`
- `ADVAPI32!RegSetKeySecurity` at `0x180029f2e`
- `ADVAPI32!RegSetKeySecurity` at `0x180029f2e`
- `ADVAPI32!SetEntriesInAclW` at `0x180029d88`
- `ADVAPI32!SetEntriesInAclW` at `0x180029d88`
- `ADVAPI32!RegGetKeySecurity` at `0x180029b78`
- `ADVAPI32!RegGetKeySecurity` at `0x180029bd3`
- `ADVAPI32!RegGetKeySecurity` at `0x180029b78`
- `ADVAPI32!RegGetKeySecurity` at `0x180029bd3`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180029e5d`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180029e5d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180029df3`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180029df3`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180029ec7`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180029ec7`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180029d1e`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180029d1e`
- `KERNEL32!GetLastError` at `0x180029d28`
- `KERNEL32!GetLastError` at `0x180029dfd`
- `KERNEL32!GetLastError` at `0x180029e67`
- `KERNEL32!GetLastError` at `0x180029ed1`
- `KERNEL32!GetLastError` at `0x180029d28`
- `KERNEL32!GetLastError` at `0x180029dfd`
- `KERNEL32!GetLastError` at `0x180029e67`
- `KERNEL32!GetLastError` at `0x180029ed1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MQSec_SetRegistrySecurityForService(HKEY hKey)
{
  LSTATUS KeySecurity; // eax
  signed int v3; // ebx
  void *v5; // rbx
  LSTATUS v6; // eax
  signed int v7; // esi
  unsigned int v8; // eax
  void *v9; // r14
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int LastError; // eax
  LSTATUS v15; // eax
  PACL NewAcl; // [rsp+60h] [rbp-49h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+68h] [rbp-41h] BYREF
  WINBOOL bDaclPresent; // [rsp+6Ch] [rbp-3Dh] BYREF
  void *Block; // [rsp+70h] [rbp-39h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-31h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-9h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A8h] [rbp-1h] BYREF
  void *v24; // [rsp+D8h] [rbp+2Fh]
  __int16 v25; // [rsp+118h] [rbp+6Fh] BYREF
  DWORD cbSecurityDescriptor; // [rsp+120h] [rbp+77h] BYREF
  signed int v27; // [rsp+128h] [rbp+7Fh] BYREF

  cbSecurityDescriptor = 0;
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
  v3 = KeySecurity;
  if ( !KeySecurity || KeySecurity == 122 )
  {
    v5 = MmAllocate(cbSecurityDescriptor);
    v24 = v5;
    v6 = RegGetKeySecurity(hKey, 4u, v5, &cbSecurityDescriptor);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( v7 < 0 )
        LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x6Eu);
      free(v5);
    }
    else
    {
      Block = 0;
      v7 = MQSec_CalculateServiceSid(&Block);
      if ( v7 >= 0 )
      {
        memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 28);
        pListOfExplicitEntries.grfAccessPermissions = 983103;
        pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
        pListOfExplicitEntries.grfInheritance = 3;
        v9 = Block;
        pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Block;
        pDacl = 0;
        bDaclPresent = 0;
        bDaclDefaulted = 0;
        if ( GetSecurityDescriptorDacl(v5, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          NewAcl = 0;
          v11 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
          v7 = v11;
          if ( v11 )
          {
            if ( v11 > 0 )
              v7 = (unsigned __int16)v11 | 0x80070000;
            if ( v7 < 0 )
              LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x8Cu);
          }
          else
          {
            memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
            v22 = 0;
            if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
            {
              if ( SetSecurityDescriptorControl(pSecurityDescriptor, 0x1500u, 0x500u) )
              {
                if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
                {
                  v15 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
                  v7 = v15;
                  if ( !v15 )
                  {
                    CAutoLocalFreePtr::~CAutoLocalFreePtr((CAutoLocalFreePtr *)&NewAcl);
                    free(v9);
                    free(v5);
                    return 0;
                  }
                  if ( v15 > 0 )
                    v7 = (unsigned __int16)v15 | 0x80070000;
                  if ( v7 < 0 )
                    LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0xA0u);
                }
                else
                {
                  LastError = GetLastError();
                  v7 = LastError;
                  if ( LastError > 0 )
                    v7 = (unsigned __int16)LastError | 0x80070000;
                  if ( v7 < 0 )
                    LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x96u);
                }
              }
              else
              {
                v13 = GetLastError();
                v7 = v13;
                if ( v13 > 0 )
                  v7 = (unsigned __int16)v13 | 0x80070000;
                if ( v7 < 0 )
                  LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x92u);
              }
            }
            else
            {
              v12 = GetLastError();
              v7 = v12;
              if ( v12 > 0 )
                v7 = (unsigned __int16)v12 | 0x80070000;
              if ( v7 < 0 )
                LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x91u);
            }
          }
          CAutoLocalFreePtr::~CAutoLocalFreePtr((CAutoLocalFreePtr *)&NewAcl);
          free(v9);
          free(v5);
        }
        else
        {
          v10 = GetLastError();
          v7 = v10;
          if ( v10 > 0 )
            v7 = (unsigned __int16)v10 | 0x80070000;
          if ( v7 < 0 )
            LogMsgHR(v7, (wchar_t *)L"acssctrl/privilge", 0x82u);
          free(v9);
          free(v5);
        }
      }
      else
      {
        v25 = 120;
        v27 = v7;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v8 = mqwcslen(L"acssctrl/privilge");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v8 + 1),
            L"acssctrl/privilge",
            2,
            &v25,
            4,
            &v27,
            0,
            0);
        }
        free(Block);
        free(v5);
      }
    }
    return (unsigned int)v7;
  }
  if ( KeySecurity > 0 )
    v3 = (unsigned __int16)KeySecurity | 0x80070000;
  if ( v3 < 0 )
    LogMsgHR(v3, (wchar_t *)L"acssctrl/privilge", 0x64u);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180029b50  push    rbp
0x180029b52  push    rbx
0x180029b53  push    rsi
0x180029b54  push    rdi
0x180029b55  push    r14
0x180029b57  lea     rbp, [rsp-37h]
0x180029b5c  sub     rsp, 0E0h
0x180029b63  mov     rdi, rcx
0x180029b66  mov     [rbp+57h+cbSecurityDescriptor], 0
0x180029b6d  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180029b71  xor     r8d, r8d; pSecurityDescriptor
0x180029b74  lea     edx, [r8+4]; SecurityInformation
0x180029b78  call    cs:__imp_RegGetKeySecurity
0x180029b7e  mov     ebx, eax
0x180029b80  test    eax, eax
0x180029b82  jz      short loc_180029BB5
0x180029b84  cmp     eax, 7Ah ; 'z'
0x180029b87  jz      short loc_180029BB5
0x180029b89  test    eax, eax
0x180029b8b  jle     short loc_180029B96
0x180029b8d  movzx   ebx, ax
0x180029b90  or      ebx, 80070000h
0x180029b96  test    ebx, ebx
0x180029b98  jns     short loc_180029BAE
0x180029b9a  mov     r8d, 64h ; 'd'; unsigned __int16
0x180029ba0  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029ba7  mov     ecx, ebx; int
0x180029ba9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029bae  mov     eax, ebx
0x180029bb0  jmp     loc_180029FA1
0x180029bb5  mov     ecx, [rbp+57h+cbSecurityDescriptor]; unsigned __int64
0x180029bb8  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180029bbd  mov     rbx, rax
0x180029bc0  mov     [rbp+57h+var_28], rax
0x180029bc4  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180029bc8  mov     r8, rax; pSecurityDescriptor
0x180029bcb  mov     edx, 4; SecurityInformation
0x180029bd0  mov     rcx, rdi; hKey
0x180029bd3  call    cs:__imp_RegGetKeySecurity
0x180029bd9  mov     esi, eax
0x180029bdb  test    eax, eax
0x180029bdd  jz      short loc_180029C14
0x180029bdf  jle     short loc_180029BEA
0x180029be1  movzx   esi, ax
0x180029be4  or      esi, 80070000h
0x180029bea  test    esi, esi
0x180029bec  jns     short loc_180029C03
0x180029bee  mov     r8d, 6Eh ; 'n'; unsigned __int16
0x180029bf4  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029bfb  mov     ecx, esi; int
0x180029bfd  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029c02  nop
0x180029c03  mov     rcx, rbx; Block
0x180029c06  call    cs:__imp_free
0x180029c0c  nop
0x180029c0d  mov     eax, esi
0x180029c0f  jmp     loc_180029FA1
0x180029c14  mov     [rbp+57h+Block], 0
0x180029c1c  lea     rcx, [rbp+57h+Block]; void **
0x180029c20  call    ?MQSec_CalculateServiceSid@@YAJPEAPEAX@Z; MQSec_CalculateServiceSid(void * *)
0x180029c25  mov     esi, eax
0x180029c27  test    eax, eax
0x180029c29  jns     loc_180029CC5
0x180029c2f  mov     eax, 78h ; 'x'
0x180029c34  mov     [rbp+57h+arg_8], ax
0x180029c38  mov     [rbp+57h+arg_18], esi
0x180029c3b  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180029c43  jz      short loc_180029CAB
0x180029c45  lea     rdi, aAcssctrlPrivil; "acssctrl/privilge"
0x180029c4c  mov     rcx, rdi; wchar_t *
0x180029c4f  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180029c54  lea     r9d, [rax+1]
0x180029c58  add     r9, r9
0x180029c5b  mov     [rsp+100h+var_B0], 0
0x180029c64  mov     [rsp+100h+var_B8], 0
0x180029c6d  lea     rax, [rbp+57h+arg_18]
0x180029c71  mov     [rsp+100h+var_C0], rax
0x180029c76  mov     [rsp+100h+var_C8], 4
0x180029c7f  lea     rax, [rbp+57h+arg_8]
0x180029c83  mov     [rsp+100h+var_D0], rax
0x180029c88  mov     [rsp+100h+var_D8], 2
0x180029c91  mov     [rsp+100h+var_E0], rdi
0x180029c96  mov     edx, 1
0x180029c9b  mov     r8d, edx
0x180029c9e  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180029ca5  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180029caa  nop
0x180029cab  mov     rcx, [rbp+57h+Block]; Block
0x180029caf  call    cs:__imp_free
0x180029cb5  nop
0x180029cb6  mov     rcx, rbx; Block
0x180029cb9  call    cs:__imp_free
0x180029cbf  nop
0x180029cc0  jmp     loc_180029C0D
0x180029cc5  xorps   xmm0, xmm0
0x180029cc8  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x180029ccd  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 0
0x180029cd5  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 0F003Fh
0x180029cdc  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 1
0x180029ce3  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x180029cea  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x180029cf1  mov     r14, [rbp+57h+Block]
0x180029cf5  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], r14
0x180029cf9  mov     [rbp+57h+pDacl], 0
0x180029d01  mov     [rbp+57h+bDaclPresent], 0
0x180029d08  mov     [rbp+57h+bDaclDefaulted], 0
0x180029d0f  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180029d13  lea     r8, [rbp+57h+pDacl]; pDacl
0x180029d17  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180029d1b  mov     rcx, rbx; pSecurityDescriptor
0x180029d1e  call    cs:__imp_GetSecurityDescriptorDacl
0x180029d24  test    eax, eax
0x180029d26  jnz     short loc_180029D6F
0x180029d28  call    cs:__imp_GetLastError
0x180029d2e  mov     esi, eax
0x180029d30  test    eax, eax
0x180029d32  jle     short loc_180029D3D
0x180029d34  movzx   esi, ax
0x180029d37  or      esi, 80070000h
0x180029d3d  test    esi, esi
0x180029d3f  jns     short loc_180029D56
0x180029d41  mov     r8d, 82h; unsigned __int16
0x180029d47  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029d4e  mov     ecx, esi; int
0x180029d50  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029d55  nop
0x180029d56  mov     rcx, r14; Block
0x180029d59  call    cs:__imp_free
0x180029d5f  nop
0x180029d60  mov     rcx, rbx; Block
0x180029d63  call    cs:__imp_free
0x180029d69  nop
0x180029d6a  jmp     loc_180029C0D
0x180029d6f  mov     [rbp+57h+NewAcl], 0
0x180029d77  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180029d7b  mov     r8, [rbp+57h+pDacl]; OldAcl
0x180029d7f  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180029d83  mov     ecx, 1; cCountOfExplicitEntries
0x180029d88  call    cs:__imp_SetEntriesInAclW
0x180029d8e  mov     esi, eax
0x180029d90  test    eax, eax
0x180029d92  jz      short loc_180029DDB
0x180029d94  jle     short loc_180029D9F
0x180029d96  movzx   esi, ax
0x180029d99  or      esi, 80070000h
0x180029d9f  test    esi, esi
0x180029da1  jns     short loc_180029DB8
0x180029da3  mov     r8d, 8Ch; unsigned __int16
0x180029da9  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029db0  mov     ecx, esi; int
0x180029db2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029db7  nop
0x180029db8  lea     rcx, [rbp+57h+NewAcl]; this
0x180029dbc  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x180029dc1  nop
0x180029dc2  mov     rcx, r14; Block
0x180029dc5  call    cs:__imp_free
0x180029dcb  nop
0x180029dcc  mov     rcx, rbx; Block
0x180029dcf  call    cs:__imp_free
0x180029dd5  nop
0x180029dd6  jmp     loc_180029C0D
0x180029ddb  xorps   xmm0, xmm0
0x180029dde  xor     eax, eax
0x180029de0  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180029de4  movups  [rbp+57h+var_70], xmm0
0x180029de8  mov     [rbp+57h+var_60], rax
0x180029dec  lea     edx, [rax+1]; dwRevision
0x180029def  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180029df3  call    cs:__imp_InitializeSecurityDescriptor
0x180029df9  test    eax, eax
0x180029dfb  jnz     short loc_180029E4E
0x180029dfd  call    cs:__imp_GetLastError
0x180029e03  mov     esi, eax
0x180029e05  test    eax, eax
0x180029e07  jle     short loc_180029E12
0x180029e09  movzx   esi, ax
0x180029e0c  or      esi, 80070000h
0x180029e12  test    esi, esi
0x180029e14  jns     short loc_180029E2B
0x180029e16  mov     r8d, 91h; unsigned __int16
0x180029e1c  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029e23  mov     ecx, esi; int
0x180029e25  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029e2a  nop
0x180029e2b  lea     rcx, [rbp+57h+NewAcl]; this
0x180029e2f  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x180029e34  nop
0x180029e35  mov     rcx, r14; Block
0x180029e38  call    cs:__imp_free
0x180029e3e  nop
0x180029e3f  mov     rcx, rbx; Block
0x180029e42  call    cs:__imp_free
0x180029e48  nop
0x180029e49  jmp     loc_180029C0D
0x180029e4e  mov     edx, 1500h; ControlBitsOfInterest
0x180029e53  mov     r8d, 500h; ControlBitsToSet
0x180029e59  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180029e5d  call    cs:__imp_SetSecurityDescriptorControl
0x180029e63  test    eax, eax
0x180029e65  jnz     short loc_180029EB8
0x180029e67  call    cs:__imp_GetLastError
0x180029e6d  mov     esi, eax
0x180029e6f  test    eax, eax
0x180029e71  jle     short loc_180029E7C
0x180029e73  movzx   esi, ax
0x180029e76  or      esi, 80070000h
0x180029e7c  test    esi, esi
0x180029e7e  jns     short loc_180029E95
0x180029e80  mov     r8d, 92h; unsigned __int16
0x180029e86  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029e8d  mov     ecx, esi; int
0x180029e8f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029e94  nop
0x180029e95  lea     rcx, [rbp+57h+NewAcl]; this
0x180029e99  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x180029e9e  nop
0x180029e9f  mov     rcx, r14; Block
0x180029ea2  call    cs:__imp_free
0x180029ea8  nop
0x180029ea9  mov     rcx, rbx; Block
0x180029eac  call    cs:__imp_free
0x180029eb2  nop
0x180029eb3  jmp     loc_180029C0D
0x180029eb8  xor     r9d, r9d; bDaclDefaulted
0x180029ebb  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180029ebf  lea     edx, [r9+1]; bDaclPresent
0x180029ec3  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180029ec7  call    cs:__imp_SetSecurityDescriptorDacl
0x180029ecd  test    eax, eax
0x180029ecf  jnz     short loc_180029F22
0x180029ed1  call    cs:__imp_GetLastError
0x180029ed7  mov     esi, eax
0x180029ed9  test    eax, eax
0x180029edb  jle     short loc_180029EE6
0x180029edd  movzx   esi, ax
0x180029ee0  or      esi, 80070000h
0x180029ee6  test    esi, esi
0x180029ee8  jns     short loc_180029EFF
0x180029eea  mov     r8d, 96h; unsigned __int16
0x180029ef0  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029ef7  mov     ecx, esi; int
0x180029ef9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029efe  nop
0x180029eff  lea     rcx, [rbp+57h+NewAcl]; this
0x180029f03  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x180029f08  nop
0x180029f09  mov     rcx, r14; Block
0x180029f0c  call    cs:__imp_free
0x180029f12  nop
0x180029f13  mov     rcx, rbx; Block
0x180029f16  call    cs:__imp_free
0x180029f1c  nop
0x180029f1d  jmp     loc_180029C0D
0x180029f22  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180029f26  mov     edx, 4; SecurityInformation
0x180029f2b  mov     rcx, rdi; hKey
0x180029f2e  call    cs:__imp_RegSetKeySecurity
0x180029f34  mov     esi, eax
0x180029f36  test    eax, eax
0x180029f38  jz      short loc_180029F81
0x180029f3a  jle     short loc_180029F45
0x180029f3c  movzx   esi, ax
0x180029f3f  or      esi, 80070000h
0x180029f45  test    esi, esi
0x180029f47  jns     short loc_180029F5E
0x180029f49  mov     r8d, 0A0h; unsigned __int16
0x180029f4f  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029f56  mov     ecx, esi; int
0x180029f58  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029f5d  nop
0x180029f5e  lea     rcx, [rbp+57h+NewAcl]; this
0x180029f62  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x180029f67  nop
0x180029f68  mov     rcx, r14; Block
0x180029f6b  call    cs:__imp_free
0x180029f71  nop
0x180029f72  mov     rcx, rbx; Block
0x180029f75  call    cs:__imp_free
0x180029f7b  nop
0x180029f7c  jmp     loc_180029C0D
0x180029f81  lea     rcx, [rbp+57h+NewAcl]; this
0x180029f85  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x180029f8a  nop
0x180029f8b  mov     rcx, r14; Block
0x180029f8e  call    cs:__imp_free
0x180029f94  nop
0x180029f95  mov     rcx, rbx; Block
0x180029f98  call    cs:__imp_free
0x180029f9e  nop
0x180029f9f  xor     eax, eax
0x180029fa1  add     rsp, 0E0h
0x180029fa8  pop     r14
0x180029faa  pop     rdi
0x180029fab  pop     rsi
0x180029fac  pop     rbx
0x180029fad  pop     rbp
0x180029fae  retn
```
