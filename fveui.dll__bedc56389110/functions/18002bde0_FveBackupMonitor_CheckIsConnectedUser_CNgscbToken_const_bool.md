# FveBackupMonitor::CheckIsConnectedUser(CNgscbToken const *,bool *)

- ea: `0x18002bde0`
- end: `0x18002bfad`
- name: `?CheckIsConnectedUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEA_N@Z`
- size: `461`
- prototype: `__int64 __fastcall(HANDLE *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028380`

## callees

- `0x1800037a0`
- `0x18002b858`
- `0x18002bde0`
- `0x18002c034`
- `0x18002d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002bf93`
- `KERNEL32!GetLastError` at `0x18002bf93`
- `ADVAPI32!RevertToSelf` at `0x18002bf89`
- `ADVAPI32!RevertToSelf` at `0x18002bf89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bef0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bef0`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::CheckIsConnectedUser(HANDLE *a1, bool *a2)
{
  int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  char v10; // [rsp+58h] [rbp+10h] BYREF
  int v11; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  v11 = 0;
  ppv = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( a1 )
    {
      *a2 = 0;
      v6 = CScopedImpersonation::ImpersonateUser((CScopedImpersonation *)&v10, a1);
      v3 = v6;
      if ( !v6 )
        goto LABEL_15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_929186be452536e5252128d48ffaedab_Traceguids, v6);
      if ( v3 >= 0 )
      {
LABEL_15:
        Microsoft::WRL::ComPtr<IIdentityStore2>::InternalRelease(&ppv);
        v7 = CoCreateInstance(
               &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
               0,
               1u,
               &GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa,
               &ppv);
        v3 = v7;
        if ( !v7 )
          goto LABEL_20;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_929186be452536e5252128d48ffaedab_Traceguids, v7);
        if ( v3 >= 0 )
        {
LABEL_20:
          v8 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 48LL))(ppv, &v11);
          v3 = v8;
          if ( !v8 )
            goto LABEL_25;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_929186be452536e5252128d48ffaedab_Traceguids, v8);
          if ( v3 >= 0 )
LABEL_25:
            *a2 = (unsigned int)(v11 - 1) <= 1;
        }
      }
      if ( v10 && !RevertToSelf() )
        GetLastError();
    }
    else
    {
      v3 = -2147024809;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v5 = 78;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = -2147467261;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v5 = 77;
LABEL_5:
      WPP_SF_d(v4[2], v5, WPP_929186be452536e5252128d48ffaedab_Traceguids, (unsigned int)v3);
    }
  }
  Microsoft::WRL::ComPtr<IIdentityStore2>::InternalRelease(&ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002bde0  push    rbx
0x18002bde2  push    rsi
0x18002bde3  push    rdi
0x18002bde4  sub     rsp, 30h
0x18002bde8  mov     [rsp+48h+arg_10], 0
0x18002bdf0  mov     rsi, rdx
0x18002bdf3  mov     [rsp+48h+arg_18], 0
0x18002bdfc  mov     [rsp+48h+arg_8], 0
0x18002be01  test    rdx, rdx
0x18002be04  jnz     short loc_18002BE47
0x18002be06  mov     ebx, 80004003h
0x18002be0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be12  lea     rdi, WPP_GLOBAL_Control
0x18002be19  cmp     rcx, rdi
0x18002be1c  jz      loc_18002BF99
0x18002be22  test    byte ptr [rcx+1Ch], 40h
0x18002be26  jz      loc_18002BF99
0x18002be2c  lea     edx, [rsi+4Dh]
0x18002be2f  mov     rcx, [rcx+10h]
0x18002be33  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18002be3a  mov     r9d, ebx
0x18002be3d  call    WPP_SF_d
0x18002be42  jmp     loc_18002BF99
0x18002be47  test    rcx, rcx
0x18002be4a  jnz     short loc_18002BE79
0x18002be4c  mov     ebx, 80070057h
0x18002be51  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be58  lea     rdi, WPP_GLOBAL_Control
0x18002be5f  cmp     rcx, rdi
0x18002be62  jz      loc_18002BF99
0x18002be68  test    byte ptr [rcx+1Ch], 40h
0x18002be6c  jz      loc_18002BF99
0x18002be72  mov     edx, 4Eh ; 'N'
0x18002be77  jmp     short loc_18002BE2F
0x18002be79  mov     byte ptr [rdx], 0
0x18002be7c  mov     rdx, rcx; struct CNgscbToken *
0x18002be7f  lea     rcx, [rsp+48h+arg_8]; this
0x18002be84  call    ?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z; CScopedImpersonation::ImpersonateUser(CNgscbToken const &)
0x18002be89  lea     rdi, WPP_GLOBAL_Control
0x18002be90  mov     ebx, eax
0x18002be92  test    eax, eax
0x18002be94  jz      short loc_18002BEC8
0x18002be96  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be9d  cmp     rcx, rdi
0x18002bea0  jz      short loc_18002BEC0
0x18002bea2  test    byte ptr [rcx+1Ch], 40h
0x18002bea6  jz      short loc_18002BEC0
0x18002bea8  mov     rcx, [rcx+10h]
0x18002beac  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18002beb3  mov     edx, 4Fh ; 'O'
0x18002beb8  mov     r9d, eax
0x18002bebb  call    WPP_SF_d
0x18002bec0  test    ebx, ebx
0x18002bec2  js      loc_18002BF82
0x18002bec8  lea     rcx, [rsp+48h+arg_18]
0x18002becd  call    ?InternalRelease@?$ComPtr@UIIdentityStore2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IIdentityStore2>::InternalRelease(void)
0x18002bed2  xor     edx, edx; pUnkOuter
0x18002bed4  lea     rax, [rsp+48h+arg_18]
0x18002bed9  lea     r9, _GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa; riid
0x18002bee0  mov     [rsp+48h+ppv], rax; ppv
0x18002bee5  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x18002beec  lea     r8d, [rdx+1]; dwClsContext
0x18002bef0  call    cs:__imp_CoCreateInstance
0x18002bef6  mov     ebx, eax
0x18002bef8  test    eax, eax
0x18002befa  jz      short loc_18002BF2A
0x18002befc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf03  cmp     rcx, rdi
0x18002bf06  jz      short loc_18002BF26
0x18002bf08  test    byte ptr [rcx+1Ch], 40h
0x18002bf0c  jz      short loc_18002BF26
0x18002bf0e  mov     rcx, [rcx+10h]
0x18002bf12  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18002bf19  mov     edx, 50h ; 'P'
0x18002bf1e  mov     r9d, eax
0x18002bf21  call    WPP_SF_d
0x18002bf26  test    ebx, ebx
0x18002bf28  js      short loc_18002BF82
0x18002bf2a  mov     rcx, [rsp+48h+arg_18]
0x18002bf2f  lea     rdx, [rsp+48h+arg_10]
0x18002bf34  mov     rax, [rcx]
0x18002bf37  mov     rax, [rax+30h]
0x18002bf3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf40  mov     ebx, eax
0x18002bf42  test    eax, eax
0x18002bf44  jz      short loc_18002BF74
0x18002bf46  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf4d  cmp     rcx, rdi
0x18002bf50  jz      short loc_18002BF70
0x18002bf52  test    byte ptr [rcx+1Ch], 40h
0x18002bf56  jz      short loc_18002BF70
0x18002bf58  mov     rcx, [rcx+10h]
0x18002bf5c  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x18002bf63  mov     edx, 51h ; 'Q'
0x18002bf68  mov     r9d, eax
0x18002bf6b  call    WPP_SF_d
0x18002bf70  test    ebx, ebx
0x18002bf72  js      short loc_18002BF82
0x18002bf74  mov     eax, [rsp+48h+arg_10]
0x18002bf78  dec     eax
0x18002bf7a  cmp     eax, 1
0x18002bf7d  setbe   al
0x18002bf80  mov     [rsi], al
0x18002bf82  cmp     [rsp+48h+arg_8], 0
0x18002bf87  jz      short loc_18002BF99
0x18002bf89  call    cs:__imp_RevertToSelf
0x18002bf8f  test    eax, eax
0x18002bf91  jnz     short loc_18002BF99
0x18002bf93  call    cs:__imp_GetLastError
0x18002bf99  lea     rcx, [rsp+48h+arg_18]
0x18002bf9e  call    ?InternalRelease@?$ComPtr@UIIdentityStore2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IIdentityStore2>::InternalRelease(void)
0x18002bfa3  mov     eax, ebx
0x18002bfa5  add     rsp, 30h
0x18002bfa9  pop     rdi
0x18002bfaa  pop     rsi
0x18002bfab  pop     rbx
0x18002bfac  retn
```
