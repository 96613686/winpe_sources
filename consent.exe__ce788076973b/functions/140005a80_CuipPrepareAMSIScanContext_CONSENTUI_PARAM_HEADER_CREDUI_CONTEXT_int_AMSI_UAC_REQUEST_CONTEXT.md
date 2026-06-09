# CuipPrepareAMSIScanContext(_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,int,AMSI_UAC_REQUEST_CONTEXT *)

- ea: `0x140005a80`
- end: `0x140005d39`
- name: `?CuipPrepareAMSIScanContext@@YAXPEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@HPEAUAMSI_UAC_REQUEST_CONTEXT@@@Z`
- size: `697`
- prototype: `void __fastcall(struct _CONSENTUI_PARAM_HEADER *, struct _CREDUI_CONTEXT *, BOOL, struct AMSI_UAC_REQUEST_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000af70`

## callees

- `0x140005a80`
- `0x14000fbec`

## pseudocode

```c
void __fastcall CuipPrepareAMSIScanContext(
        struct _CONSENTUI_PARAM_HEADER *a1,
        struct _CREDUI_CONTEXT *a2,
        BOOL a3,
        struct AMSI_UAC_REQUEST_CONTEXT *a4)
{
  __int64 v5; // r9
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rdx

  a4->ulLength = 104;
  a4->bAutoElevateRequest = a3;
  v5 = *(unsigned int *)a2;
  switch ( (_DWORD)v5 )
  {
    case 3:
      goto LABEL_2;
    case 0:
      a4->UACTrustState = AMSI_UAC_TRUST_STATE_BLOCKED;
      goto LABEL_3;
    case 1:
      goto LABEL_11;
    case 2:
LABEL_2:
      a4->UACTrustState = AMSI_UAC_TRUST_STATE_TRUSTED;
LABEL_3:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_4;
    case 4:
LABEL_11:
      a4->UACTrustState = AMSI_UAC_TRUST_STATE_UNTRUSTED;
      goto LABEL_3;
  }
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids, v5);
    goto LABEL_3;
  }
LABEL_4:
  v8 = *((unsigned int *)a1 + 1);
  switch ( (_DWORD)v8 )
  {
    case 0:
      a4->ulRequestorProcessId = *((_DWORD *)a1 + 60);
      a4->Type = AMSI_UAC_REQUEST_TYPE_EXE;
      a4->RequestType.ExeInfo.ulLength = 32;
      a4->RequestType.ExeInfo.lpwszApplicationName = (LPWSTR)*((_QWORD *)a1 + 27);
      a4->RequestType.ExeInfo.lpwszCommandLine = (LPWSTR)*((_QWORD *)a1 + 28);
      a4->RequestType.ExeInfo.lpwszDLLParameter = (LPWSTR)*((_QWORD *)a1 + 29);
      return;
    case 1:
      a4->Type = AMSI_UAC_REQUEST_TYPE_COM;
      a4->RequestType.ExeInfo.ulLength = 40;
      *(_OWORD *)&a4->RequestType.PackagedAppInfo.lpPackageFamilyName = *(_OWORD *)((char *)a1 + 232);
      a4->RequestType.ExeInfo.lpwszApplicationName = (LPWSTR)*((_QWORD *)a1 + 26);
      a4->RequestType.ExeInfo.lpwszCommandLine = (LPWSTR)*((_QWORD *)a1 + 28);
      return;
    case 2:
      a4->Type = AMSI_UAC_REQUEST_TYPE_MSI;
      a4->RequestType.ExeInfo.ulLength = 80;
      a4->RequestType.ExeInfo.lpwszDLLParameter = (LPWSTR)*((_QWORD *)a1 + 28);
      a4->RequestType.MsiInfo.lpwszManufacturer = (LPWSTR)*((_QWORD *)a1 + 29);
      a4->RequestType.MsiInfo.lpwszPackagePath = (LPWSTR)*((_QWORD *)a1 + 30);
      a4->RequestType.MsiInfo.lpwszPackageSource = (LPWSTR)*((_QWORD *)a1 + 31);
      a4->RequestType.ExeInfo.lpwszApplicationName = (LPWSTR)*((_QWORD *)a1 + 26);
      a4->RequestType.ExeInfo.lpwszCommandLine = (LPWSTR)*((_QWORD *)a1 + 27);
      a4->RequestType.MsiInfo.ulUpdates = *((_DWORD *)a1 + 64);
      a4->RequestType.MsiInfo.ppwszUpdates = (LPWSTR *)*((_QWORD *)a1 + 33);
      a4->RequestType.MsiInfo.ppwszUpdateSources = (LPWSTR *)*((_QWORD *)a1 + 34);
      v8 = *((unsigned int *)a1 + 50);
      switch ( (_DWORD)v8 )
      {
        case 0:
          a4->RequestType.MsiInfo.MsiAction = AMSI_UAC_MSI_ACTION_INSTALL;
          return;
        case 1:
          a4->RequestType.MsiInfo.MsiAction = AMSI_UAC_MSI_ACTION_UNINSTALL;
          return;
        case 2:
          a4->RequestType.MsiInfo.MsiAction = AMSI_UAC_MSI_ACTION_UPDATE;
          return;
      }
      if ( (unsigned int)(v8 - 3) < 2 )
      {
        a4->RequestType.MsiInfo.MsiAction = AMSI_UAC_MSI_ACTION_MAINTENANCE;
        return;
      }
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v9 = 22;
        goto LABEL_24;
      }
      break;
    case 3:
      a4->Type = AMSI_UAC_REQUEST_TYPE_AX;
      a4->RequestType.ExeInfo.ulLength = 24;
      a4->RequestType.ExeInfo.lpwszApplicationName = (LPWSTR)*((_QWORD *)a1 + 25);
      a4->RequestType.ExeInfo.lpwszCommandLine = (LPWSTR)*((_QWORD *)a1 + 26);
      return;
    case 5:
      a4->ulRequestorProcessId = *((_DWORD *)a1 + 58);
      a4->Type = AMSI_UAC_REQUEST_TYPE_PACKAGED_APP;
      a4->RequestType.ExeInfo.ulLength = 40;
      a4->RequestType.ExeInfo.lpwszApplicationName = (LPWSTR)*((_QWORD *)a1 + 25);
      a4->RequestType.ExeInfo.lpwszCommandLine = (LPWSTR)*((_QWORD *)a1 + 26);
      a4->RequestType.ExeInfo.lpwszDLLParameter = (LPWSTR)*((_QWORD *)a1 + 27);
      a4->RequestType.MsiInfo.lpwszManufacturer = (LPWSTR)*((_QWORD *)a1 + 28);
      return;
    default:
      if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
      {
        v9 = 23;
LABEL_24:
        WPP_SF_D(*(_QWORD *)(v7 + 16), v9, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids, v8);
      }
      break;
  }
}

```

## disassembly

```asm
0x140005a80  push    rbx
0x140005a82  push    rbp
0x140005a83  push    rsi
0x140005a84  push    rdi
0x140005a85  sub     rsp, 28h
0x140005a89  mov     rbx, r9
0x140005a8c  mov     dword ptr [r9], 68h ; 'h'
0x140005a93  mov     [r9+60h], r8d
0x140005a97  lea     rbp, WPP_GLOBAL_Control
0x140005a9e  mov     r9d, [rdx]
0x140005aa1  xor     esi, esi
0x140005aa3  mov     rdi, rcx
0x140005aa6  cmp     r9d, 3
0x140005aaa  jnz     short loc_140005AFC
0x140005aac  mov     [rbx+8], esi
0x140005aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ab6  mov     r9d, [rdi+4]
0x140005aba  test    r9d, r9d
0x140005abd  jnz     short loc_140005B20
0x140005abf  mov     eax, [rdi+0F0h]
0x140005ac5  mov     [rbx+4], eax
0x140005ac8  mov     [rbx+0Ch], esi
0x140005acb  mov     dword ptr [rbx+10h], 20h ; ' '
0x140005ad2  mov     rax, [rdi+0D8h]
0x140005ad9  mov     [rbx+18h], rax
0x140005add  mov     rax, [rdi+0E0h]
0x140005ae4  mov     [rbx+20h], rax
0x140005ae8  mov     rax, [rdi+0E8h]
0x140005aef  mov     [rbx+28h], rax
0x140005af3  add     rsp, 28h
0x140005af7  pop     rdi
0x140005af8  pop     rsi
0x140005af9  pop     rbp
0x140005afa  pop     rbx
0x140005afb  retn
0x140005afc  mov     ecx, r9d
0x140005aff  test    r9d, r9d
0x140005b02  jz      loc_140005B94
0x140005b08  sub     ecx, 1
0x140005b0b  jz      short loc_140005B17
0x140005b0d  sub     ecx, 1
0x140005b10  jz      short loc_140005AAC
0x140005b12  cmp     ecx, 2
0x140005b15  jnz     short loc_140005B60
0x140005b17  mov     dword ptr [rbx+8], 1
0x140005b1e  jmp     short loc_140005AAF
0x140005b20  mov     edx, r9d
0x140005b23  sub     edx, 1
0x140005b26  jnz     short loc_140005BA0
0x140005b28  mov     dword ptr [rbx+0Ch], 1
0x140005b2f  mov     dword ptr [rbx+10h], 28h ; '('
0x140005b36  movups  xmm0, xmmword ptr [rdi+0E8h]
0x140005b3d  movups  xmmword ptr [rbx+28h], xmm0
0x140005b41  mov     rax, [rdi+0D0h]
0x140005b48  mov     [rbx+18h], rax
0x140005b4c  mov     rax, [rdi+0E0h]
0x140005b53  mov     [rbx+20h], rax
0x140005b57  add     rsp, 28h
0x140005b5b  pop     rdi
0x140005b5c  pop     rsi
0x140005b5d  pop     rbp
0x140005b5e  pop     rbx
0x140005b5f  retn
0x140005b60  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b67  cmp     rcx, rbp
0x140005b6a  jz      loc_140005AB6
0x140005b70  test    byte ptr [rcx+1Ch], 2
0x140005b74  jz      loc_140005AB6
0x140005b7a  mov     rcx, [rcx+10h]
0x140005b7e  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x140005b85  mov     edx, 15h
0x140005b8a  call    WPP_SF_D
0x140005b8f  jmp     loc_140005AAF
0x140005b94  mov     dword ptr [rbx+8], 2
0x140005b9b  jmp     loc_140005AAF
0x140005ba0  sub     edx, 1
0x140005ba3  jz      loc_140005C5C
0x140005ba9  sub     edx, 1
0x140005bac  jz      loc_140005C33
0x140005bb2  cmp     edx, 2
0x140005bb5  jz      short loc_140005BEB
0x140005bb7  cmp     rcx, rbp
0x140005bba  jz      loc_140005AF3
0x140005bc0  test    byte ptr [rcx+1Ch], 2
0x140005bc4  jz      loc_140005AF3
0x140005bca  mov     edx, 17h
0x140005bcf  jmp     short loc_140005BD6
0x140005bd1  mov     edx, 16h
0x140005bd6  mov     rcx, [rcx+10h]
0x140005bda  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x140005be1  call    WPP_SF_D
0x140005be6  jmp     loc_140005AF3
0x140005beb  mov     eax, [rdi+0E8h]
0x140005bf1  mov     [rbx+4], eax
0x140005bf4  mov     dword ptr [rbx+0Ch], 4
0x140005bfb  mov     dword ptr [rbx+10h], 28h ; '('
0x140005c02  mov     rax, [rdi+0C8h]
0x140005c09  mov     [rbx+18h], rax
0x140005c0d  mov     rax, [rdi+0D0h]
0x140005c14  mov     [rbx+20h], rax
0x140005c18  mov     rax, [rdi+0D8h]
0x140005c1f  mov     [rbx+28h], rax
0x140005c23  mov     rax, [rdi+0E0h]
0x140005c2a  mov     [rbx+30h], rax
0x140005c2e  jmp     loc_140005AF3
0x140005c33  mov     dword ptr [rbx+0Ch], 3
0x140005c3a  mov     dword ptr [rbx+10h], 18h
0x140005c41  mov     rax, [rdi+0C8h]
0x140005c48  mov     [rbx+18h], rax
0x140005c4c  mov     rax, [rdi+0D0h]
0x140005c53  mov     [rbx+20h], rax
0x140005c57  jmp     loc_140005AF3
0x140005c5c  mov     dword ptr [rbx+0Ch], 2
0x140005c63  mov     dword ptr [rbx+10h], 50h ; 'P'
0x140005c6a  mov     rax, [rdi+0E0h]
0x140005c71  mov     [rbx+28h], rax
0x140005c75  mov     rax, [rdi+0E8h]
0x140005c7c  mov     [rbx+30h], rax
0x140005c80  mov     rax, [rdi+0F0h]
0x140005c87  mov     [rbx+38h], rax
0x140005c8b  mov     rax, [rdi+0F8h]
0x140005c92  mov     [rbx+40h], rax
0x140005c96  mov     rax, [rdi+0D0h]
0x140005c9d  mov     [rbx+18h], rax
0x140005ca1  mov     rax, [rdi+0D8h]
0x140005ca8  mov     [rbx+20h], rax
0x140005cac  mov     eax, [rdi+100h]
0x140005cb2  mov     [rbx+48h], eax
0x140005cb5  mov     rax, [rdi+108h]
0x140005cbc  mov     [rbx+50h], rax
0x140005cc0  mov     rax, [rdi+110h]
0x140005cc7  mov     [rbx+58h], rax
0x140005ccb  mov     r9d, [rdi+0C8h]
0x140005cd2  mov     eax, r9d
0x140005cd5  test    r9d, r9d
0x140005cd8  jz      short loc_140005D31
0x140005cda  sub     eax, 1
0x140005cdd  jz      short loc_140005D25
0x140005cdf  sub     eax, 1
0x140005ce2  jz      short loc_140005D19
0x140005ce4  sub     eax, 1
0x140005ce7  jz      short loc_140005D0D
0x140005ce9  cmp     eax, 1
0x140005cec  jz      short loc_140005D0D
0x140005cee  mov     rcx, cs:WPP_GLOBAL_Control
0x140005cf5  cmp     rcx, rbp
0x140005cf8  jz      loc_140005AF3
0x140005cfe  test    byte ptr [rcx+1Ch], 2
0x140005d02  jz      loc_140005AF3
0x140005d08  jmp     loc_140005BD1
0x140005d0d  mov     dword ptr [rbx+14h], 3
0x140005d14  jmp     loc_140005AF3
0x140005d19  mov     dword ptr [rbx+14h], 2
0x140005d20  jmp     loc_140005AF3
0x140005d25  mov     dword ptr [rbx+14h], 1
0x140005d2c  jmp     loc_140005AF3
0x140005d31  mov     [rbx+14h], esi
0x140005d34  jmp     loc_140005AF3
```
