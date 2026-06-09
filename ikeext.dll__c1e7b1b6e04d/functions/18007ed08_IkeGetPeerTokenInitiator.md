# IkeGetPeerTokenInitiator

- ea: `0x18007ed08`
- end: `0x18007efd4`
- name: `IkeGetPeerTokenInitiator`
- size: `716`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082710`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x18007ed08`
- `0x180080ed8`
- `0x180093eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ed7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ed7b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007ef67`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18007ef67`

## string_xrefs

- `0x18007ed3d`: `IkeGetPeerTokenInitiator`
- `0x18007ef91`: `IkeGetPeerTokenInitiator`
- `0x18007ef9d`: `IkeGetPeerTokenInitiator`
- `0x18007ef7d`: `DuplicateToken`
- `0x18007ee4b`: `Calling IkeObtainPeerKerberosTokenOnInitiator`

## pseudocode

```c
__int64 __fastcall IkeGetPeerTokenInitiator(__int64 a1, __int64 a2)
{
  __int64 v4; // r12
  HANDLE *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v9; // rcx
  int TlsMmLuid; // eax
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  const WCHAR *v20; // rax
  __int64 v21; // r8
  DWORD LastError; // eax
  __int64 v23; // rcx
  _QWORD v25[2]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v26[32]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v27; // [rsp+60h] [rbp-9h]
  __int64 v28; // [rsp+68h] [rbp-1h]
  _BYTE v29[16]; // [rsp+70h] [rbp+7h] BYREF
  const char *v30; // [rsp+80h] [rbp+17h]
  __int64 v31; // [rsp+88h] [rbp+1Fh]

  v4 = 0;
  TraceLogHelper("IkeGetPeerTokenInitiator", 1);
  if ( (*(_DWORD *)(a2 + 72) & 0x100000) != 0 )
    v5 = (HANDLE *)(*(_QWORD *)(*(_QWORD *)(a1 + 1096) + 24LL) + 232LL);
  else
    v5 = (HANDLE *)(a1 + 984);
  if ( *v5 )
  {
    CloseHandle(*v5);
    *v5 = 0;
  }
  v6 = (unsigned int)(*(_DWORD *)(a2 + 88) - 2);
  if ( *(_DWORD *)(a2 + 88) == 2 )
  {
    if ( (*(_BYTE *)(a2 + 40) & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        TlsPeerAddr = IkeGetTlsPeerAddr(v6);
        TlsMmLuid = IkeGetTlsMmLuid(v9);
        WPP_SF_iS(v7, 33, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v25[0] = IkeGetTlsMmLuid(v6);
        v27 = v25;
        v28 = 8;
        v12 = (const WCHAR *)IkeGetTlsPeerAddr(v11);
        tlgCreate1Sz_wchar_t((__int64)v29, v12);
        v31 = 46;
        v30 = "Calling IkeObtainPeerKerberosTokenOnInitiator";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)&byte_18015589F,
          v13,
          v14,
          5,
          (__int64)v26);
      }
      IkeObtainPeerKerberosTokenOnInitiator(a1, a2, v5);
    }
  }
  else if ( *(_DWORD *)(a2 + 88) == 4 || (v6 = (unsigned int)(*(_DWORD *)(a2 + 88) - 9), (unsigned int)v6 <= 1) )
  {
    v6 = *(_QWORD *)(a2 + 104);
    if ( (*(_BYTE *)(v6 + 84) & 1) != 0 )
      IkeVerifyCertMapping(*(_QWORD *)(v6 + 16), v5);
  }
  if ( !*v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v16 = IkeGetTlsPeerAddr(v6);
      v18 = IkeGetTlsMmLuid(v17);
      WPP_SF_iS(v15, 34, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v18, v16);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v25[0] = IkeGetTlsMmLuid(v6);
      v27 = v25;
      v28 = 8;
      v20 = (const WCHAR *)IkeGetTlsPeerAddr(v19);
      tlgCreate1Sz_wchar_t((__int64)v29, v20);
      v31 = 22;
      v30 = "Calling DuplicateToke";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_180155861,
        v21,
        (__int64)"Calling DuplicateToke",
        5,
        (__int64)v26);
    }
    if ( !DuplicateToken(gIkeExtGlobals[86].OwningThread, SecurityImpersonation, v5) )
    {
      LastError = GetLastError();
      v4 = WfpReportSysErrorAsWinError(v23, "DuplicateToken", LastError, 1);
    }
  }
  TraceLogHelper("IkeGetPeerTokenInitiator", 0);
  return IkeReturnError(v4, "IkeGetPeerTokenInitiator");
}

```

## disassembly

```asm
0x18007ed08  mov     [rsp-8+arg_10], rbx
0x18007ed0d  mov     [rsp-8+arg_18], rsi
0x18007ed12  push    rbp
0x18007ed13  push    rdi
0x18007ed14  push    r12
0x18007ed16  push    r14
0x18007ed18  push    r15
0x18007ed1a  lea     rbp, [rsp-37h]
0x18007ed1f  sub     rsp, 0A0h
0x18007ed26  mov     rax, cs:__security_cookie
0x18007ed2d  xor     rax, rsp
0x18007ed30  mov     [rbp+57h+var_30], rax
0x18007ed34  mov     r14, rdx
0x18007ed37  mov     r15, rcx
0x18007ed3a  xor     r12d, r12d
0x18007ed3d  lea     rcx, aIkegetpeertoke_1; "IkeGetPeerTokenInitiator"
0x18007ed44  lea     edx, [r12+1]
0x18007ed49  call    TraceLogHelper
0x18007ed4e  test    dword ptr [r14+48h], 100000h
0x18007ed56  jz      short loc_18007ED6C
0x18007ed58  mov     rax, [r15+448h]
0x18007ed5f  mov     rsi, [rax+18h]
0x18007ed63  add     rsi, 0E8h
0x18007ed6a  jmp     short loc_18007ED73
0x18007ed6c  lea     rsi, [r15+3D8h]
0x18007ed73  mov     rcx, [rsi]; hObject
0x18007ed76  test    rcx, rcx
0x18007ed79  jz      short loc_18007ED84
0x18007ed7b  call    cs:__imp_CloseHandle
0x18007ed81  mov     [rsi], r12
0x18007ed84  mov     ecx, [r14+58h]
0x18007ed88  lea     rax, WPP_GLOBAL_Control
0x18007ed8f  sub     ecx, 2
0x18007ed92  jz      short loc_18007EDC6
0x18007ed94  sub     ecx, 2
0x18007ed97  jz      short loc_18007EDA7
0x18007ed99  sub     ecx, 5
0x18007ed9c  jz      short loc_18007EDA7
0x18007ed9e  cmp     ecx, 1
0x18007eda1  jnz     loc_18007EE97
0x18007eda7  mov     rcx, [r14+68h]
0x18007edab  test    byte ptr [rcx+54h], 1
0x18007edaf  jz      loc_18007EE97
0x18007edb5  mov     rcx, [rcx+10h]
0x18007edb9  mov     rdx, rsi
0x18007edbc  call    IkeVerifyCertMapping
0x18007edc1  jmp     loc_18007EE90
0x18007edc6  test    byte ptr [r14+28h], 2
0x18007edcb  jz      loc_18007EE97
0x18007edd1  mov     rdi, cs:WPP_GLOBAL_Control
0x18007edd8  cmp     rdi, rax
0x18007eddb  jz      short loc_18007EE16
0x18007eddd  cmp     byte ptr [rdi+19h], 4
0x18007ede1  jb      short loc_18007EE16
0x18007ede3  test    byte ptr [rdi+1Ch], 10h
0x18007ede7  jz      short loc_18007EE16
0x18007ede9  mov     rdi, [rdi+10h]
0x18007eded  call    IkeGetTlsPeerAddr
0x18007edf2  mov     rbx, rax
0x18007edf5  call    IkeGetTlsMmLuid
0x18007edfa  mov     r9, rax
0x18007edfd  mov     [rsp+0C0h+var_A0], rbx
0x18007ee02  mov     edx, 21h ; '!'
0x18007ee07  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007ee0e  mov     rcx, rdi
0x18007ee11  call    WPP_SF_iS
0x18007ee16  mov     eax, cs:dword_180173278
0x18007ee1c  cmp     eax, 4
0x18007ee1f  jbe     short loc_18007EE82
0x18007ee21  call    IkeGetTlsMmLuid
0x18007ee26  mov     [rbp+57h+var_90], rax
0x18007ee2a  lea     rax, [rbp+57h+var_90]
0x18007ee2e  mov     [rbp+57h+var_60], rax
0x18007ee32  mov     [rbp+57h+var_58], 8
0x18007ee3a  call    IkeGetTlsPeerAddr
0x18007ee3f  mov     rdx, rax
0x18007ee42  lea     rcx, [rbp+57h+var_50]
0x18007ee46  call    _tlgCreate1Sz_wchar_t
0x18007ee4b  lea     rcx, aCallingIkeobta; "Calling IkeObtainPeerKerberosTokenOnIni"...
0x18007ee52  mov     [rbp+57h+var_38], 2Eh ; '.'
0x18007ee5a  lea     rax, [rbp+57h+var_80]
0x18007ee5e  mov     [rbp+57h+var_40], rcx
0x18007ee62  mov     [rsp+0C0h+var_98], rax
0x18007ee67  lea     rcx, dword_180173278
0x18007ee6e  lea     rdx, byte_18015589F
0x18007ee75  mov     dword ptr [rsp+0C0h+var_A0], 5
0x18007ee7d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007ee82  mov     r8, rsi
0x18007ee85  mov     rdx, r14
0x18007ee88  mov     rcx, r15
0x18007ee8b  call    IkeObtainPeerKerberosTokenOnInitiator
0x18007ee90  lea     rax, WPP_GLOBAL_Control
0x18007ee97  cmp     [rsi], r12
0x18007ee9a  jnz     loc_18007EF8F
0x18007eea0  mov     rdi, cs:WPP_GLOBAL_Control
0x18007eea7  cmp     rdi, rax
0x18007eeaa  jz      short loc_18007EEE5
0x18007eeac  cmp     byte ptr [rdi+19h], 4
0x18007eeb0  jb      short loc_18007EEE5
0x18007eeb2  test    byte ptr [rdi+1Ch], 10h
0x18007eeb6  jz      short loc_18007EEE5
0x18007eeb8  mov     rdi, [rdi+10h]
0x18007eebc  call    IkeGetTlsPeerAddr
0x18007eec1  mov     rbx, rax
0x18007eec4  call    IkeGetTlsMmLuid
0x18007eec9  mov     r9, rax
0x18007eecc  mov     [rsp+0C0h+var_A0], rbx
0x18007eed1  mov     edx, 22h ; '"'
0x18007eed6  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007eedd  mov     rcx, rdi
0x18007eee0  call    WPP_SF_iS
0x18007eee5  mov     eax, cs:dword_180173278
0x18007eeeb  cmp     eax, 4
0x18007eeee  jbe     short loc_18007EF51
0x18007eef0  call    IkeGetTlsMmLuid
0x18007eef5  mov     [rbp+57h+var_90], rax
0x18007eef9  lea     rax, [rbp+57h+var_90]
0x18007eefd  mov     [rbp+57h+var_60], rax
0x18007ef01  mov     [rbp+57h+var_58], 8
0x18007ef09  call    IkeGetTlsPeerAddr
0x18007ef0e  mov     rdx, rax
0x18007ef11  lea     rcx, [rbp+57h+var_50]
0x18007ef15  call    _tlgCreate1Sz_wchar_t
0x18007ef1a  lea     rax, [rbp+57h+var_80]
0x18007ef1e  mov     [rbp+57h+var_38], 16h
0x18007ef26  lea     r9, aCallingDuplica; "Calling DuplicateToke"
0x18007ef2d  mov     [rsp+0C0h+var_98], rax
0x18007ef32  lea     rdx, byte_180155861
0x18007ef39  mov     dword ptr [rsp+0C0h+var_A0], 5
0x18007ef41  lea     rcx, dword_180173278
0x18007ef48  mov     [rbp+57h+var_40], r9
0x18007ef4c  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007ef51  mov     rcx, cs:gIkeExtGlobals
0x18007ef58  mov     r8, rsi; DuplicateTokenHandle
0x18007ef5b  mov     edx, 2; ImpersonationLevel
0x18007ef60  mov     rcx, [rcx+0D80h]; ExistingTokenHandle
0x18007ef67  call    cs:__imp_DuplicateToken
0x18007ef6d  test    eax, eax
0x18007ef6f  jnz     short loc_18007EF8F
0x18007ef71  call    cs:__imp_GetLastError
0x18007ef77  mov     r9d, 1
0x18007ef7d  lea     rdx, aDuplicatetoken; "DuplicateToken"
0x18007ef84  mov     r8d, eax
0x18007ef87  call    WfpReportSysErrorAsWinError
0x18007ef8c  mov     r12, rax
0x18007ef8f  xor     edx, edx
0x18007ef91  lea     rcx, aIkegetpeertoke_1; "IkeGetPeerTokenInitiator"
0x18007ef98  call    TraceLogHelper
0x18007ef9d  lea     rdx, aIkegetpeertoke_1; "IkeGetPeerTokenInitiator"
0x18007efa4  mov     rcx, r12
0x18007efa7  call    IkeReturnError
0x18007efac  mov     rcx, [rbp+57h+var_30]
0x18007efb0  xor     rcx, rsp; StackCookie
0x18007efb3  call    __security_check_cookie
0x18007efb8  lea     r11, [rsp+0C0h+var_20]
0x18007efc0  mov     rbx, [r11+40h]
0x18007efc4  mov     rsi, [r11+48h]
0x18007efc8  mov     rsp, r11
0x18007efcb  pop     r15
0x18007efcd  pop     r14
0x18007efcf  pop     r12
0x18007efd1  pop     rdi
0x18007efd2  pop     rbp
0x18007efd3  retn
```
