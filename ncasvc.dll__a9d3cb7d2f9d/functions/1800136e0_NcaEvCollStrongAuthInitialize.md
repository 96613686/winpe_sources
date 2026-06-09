# NcaEvCollStrongAuthInitialize

- ea: `0x1800136e0`
- end: `0x180013987`
- name: `NcaEvCollStrongAuthInitialize`
- size: `679`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x18000df10`
- `0x18000e984`
- `0x1800136e0`
- `0x180013990`
- `0x180018ffc`
- `0x18001cc3e`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800137d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800137d7`

## pseudocode

```c
__int64 NcaEvCollStrongAuthInitialize()
{
  int v0; // edi
  PVOID v1; // rcx
  int v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  PVOID *v5; // rcx
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _QWORD v10[3]; // [rsp+20h] [rbp-39h] BYREF
  int v11; // [rsp+38h] [rbp-21h]
  int v12; // [rsp+3Ch] [rbp-1Dh]
  _DWORD v13[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v14; // [rsp+48h] [rbp-11h]
  void (__fastcall *v15)(void *, void *, void *, void *); // [rsp+50h] [rbp-9h]
  __int64 v16; // [rsp+58h] [rbp-1h]
  int v17; // [rsp+60h] [rbp+7h]
  int v18; // [rsp+64h] [rbp+Bh]
  _DWORD *v19; // [rsp+68h] [rbp+Fh]
  _DWORD v20[4]; // [rsp+70h] [rbp+17h] BYREF

  v0 = 0;
  v20[0] = 13908;
  v13[1] = 0;
  v18 = 0;
  v12 = 0;
  v20[1] = 13906;
  v20[2] = 13907;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer((__int64)v1, (const EVENT_DESCRIPTOR *)ModuleInitializeStart, L"EvCollStrongAuth");
  memset_0(&gNcaEvCollStrongAuth, 0, 0x58u);
  v2 = NcaCriticalSectionCreate(&stru_1800290E8);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_b3aa15e3641333918320d88489d2b829_Traceguids,
        (unsigned int)v2);
      NcaEvCollStrongAuthShutdown();
LABEL_30:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    goto LABEL_17;
  }
  if ( ConvertStringSidToSidW(L"S-1-5-65-1", &hMem) )
  {
    v13[0] = 0;
    v15 = NcaEvCollStrongAuthCollect;
    v14 = 0;
    v19 = v20;
    v16 = 0;
    v17 = 3;
    v6 = NcaWfpNetEventTriggerRegisterWait(v13, &gNcaEvCollStrongAuth);
    v0 = v6;
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_17;
      v8 = 13;
    }
    else
    {
      v10[0] = 0;
      v10[1] = NcaEvCollStrongAuthLockUnlockCollect;
      v10[2] = 0;
      v11 = 3;
      v6 = NcaWtsSessionChangeTriggerRegisterWait(v10, &qword_1800290D8);
      v0 = v6;
      if ( !v6 )
        goto LABEL_30;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_17:
        NcaEvCollStrongAuthShutdown();
        if ( !v0 )
          goto LABEL_30;
LABEL_18:
        if ( v0 > 0 )
          v3 = (unsigned __int16)v0 | 0x80070000;
        else
          v3 = v0;
        goto LABEL_30;
      }
      v8 = 14;
    }
    WPP_SF_d(v7[2], v8, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids, v6);
    NcaEvCollStrongAuthShutdown();
    goto LABEL_18;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids, v3);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v3 & 0x80000000) != 0 )
    goto LABEL_17;
LABEL_31:
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
  {
    McTemplateU0zx_EventWriteTransfer(
      (__int64)v5,
      (const EVENT_DESCRIPTOR *)ModuleInitializeEnd,
      L"EvCollStrongAuth",
      (int)v3);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(v5[2], 16, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800136e0  push    rbp
0x1800136e2  push    rbx
0x1800136e3  push    rdi
0x1800136e4  push    r12
0x1800136e6  push    r15
0x1800136e8  lea     rbp, [rsp-37h]
0x1800136ed  sub     rsp, 90h
0x1800136f4  mov     rax, cs:__security_cookie
0x1800136fb  xor     rax, rsp
0x1800136fe  mov     [rbp+57h+var_30], rax
0x180013702  xor     edi, edi
0x180013704  mov     [rbp+57h+var_40], 3654h
0x18001370b  mov     [rbp+57h+var_6C], edi
0x18001370e  mov     [rbp+57h+var_4C], edi
0x180013711  mov     [rbp+57h+var_74], edi
0x180013714  mov     [rbp+57h+var_3C], 3652h
0x18001371b  mov     [rbp+57h+var_38], 3653h
0x180013722  mov     rcx, cs:WPP_GLOBAL_Control
0x180013729  lea     r15, WPP_GLOBAL_Control
0x180013730  lea     r12, WPP_b3aa15e3641333918320d88489d2b829_Traceguids
0x180013737  cmp     rcx, r15
0x18001373a  jz      short loc_180013751
0x18001373c  test    byte ptr [rcx+1Ch], 8
0x180013740  jz      short loc_180013751
0x180013742  mov     rcx, [rcx+10h]
0x180013746  lea     edx, [rdi+0Ah]
0x180013749  mov     r8, r12
0x18001374c  call    WPP_SF_
0x180013751  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180013758  jz      short loc_18001376D
0x18001375a  lea     r8, aEvcollstrongau; "EvCollStrongAuth"
0x180013761  lea     rdx, ModuleInitializeStart
0x180013768  call    McTemplateU0z_EventWriteTransfer
0x18001376d  xor     edx, edx; Val
0x18001376f  lea     rcx, ?gNcaEvCollStrongAuth@@3UNCA_EVCOLL_STRONGAUTH_COMPONENT_@@A; void *
0x180013776  lea     r8d, [rdx+58h]; Size
0x18001377a  call    memset_0
0x18001377f  lea     rcx, stru_1800290E8; lpCriticalSection
0x180013786  call    NcaCriticalSectionCreate
0x18001378b  mov     ebx, eax
0x18001378d  test    eax, eax
0x18001378f  jns     short loc_1800137C9
0x180013791  mov     rcx, cs:WPP_GLOBAL_Control
0x180013798  cmp     rcx, r15
0x18001379b  jz      loc_180013837
0x1800137a1  test    byte ptr [rcx+1Ch], 1
0x1800137a5  jz      loc_180013837
0x1800137ab  mov     rcx, [rcx+10h]
0x1800137af  mov     edx, 0Bh
0x1800137b4  mov     r9d, eax
0x1800137b7  mov     r8, r12
0x1800137ba  call    WPP_SF_d
0x1800137bf  call    NcaEvCollStrongAuthShutdown
0x1800137c4  jmp     loc_18001391D
0x1800137c9  lea     rdx, hMem; Sid
0x1800137d0  lea     rcx, aS15651; "S-1-5-65-1"
0x1800137d7  call    cs:__imp_ConvertStringSidToSidW
0x1800137de  nop     dword ptr [rax+rax+00h]
0x1800137e3  test    eax, eax
0x1800137e5  jnz     short loc_180013853
0x1800137e7  call    cs:__imp_GetLastError
0x1800137ee  nop     dword ptr [rax+rax+00h]
0x1800137f3  mov     ebx, eax
0x1800137f5  test    eax, eax
0x1800137f7  jle     short loc_180013802
0x1800137f9  movzx   ebx, ax
0x1800137fc  or      ebx, 80070000h
0x180013802  mov     rcx, cs:WPP_GLOBAL_Control
0x180013809  cmp     rcx, r15
0x18001380c  jz      short loc_18001382F
0x18001380e  test    byte ptr [rcx+1Ch], 1
0x180013812  jz      short loc_18001382F
0x180013814  mov     rcx, [rcx+10h]
0x180013818  mov     edx, 0Ch
0x18001381d  mov     r9d, ebx
0x180013820  mov     r8, r12
0x180013823  call    WPP_SF_d
0x180013828  mov     rcx, cs:WPP_GLOBAL_Control
0x18001382f  test    ebx, ebx
0x180013831  jns     loc_180013924
0x180013837  call    NcaEvCollStrongAuthShutdown
0x18001383c  test    edi, edi
0x18001383e  jz      loc_18001391D
0x180013844  test    edi, edi
0x180013846  jg      loc_180013914
0x18001384c  mov     ebx, edi
0x18001384e  jmp     loc_18001391D
0x180013853  lea     rax, ?NcaEvCollStrongAuthCollect@@YAXPEAX000@Z; NcaEvCollStrongAuthCollect(void *,void *,void *,void *)
0x18001385a  mov     [rbp+57h+var_70], edi
0x18001385d  mov     [rbp+57h+var_60], rax
0x180013861  lea     rdx, ?gNcaEvCollStrongAuth@@3UNCA_EVCOLL_STRONGAUTH_COMPONENT_@@A; NCA_EVCOLL_STRONGAUTH_COMPONENT_ gNcaEvCollStrongAuth
0x180013868  lea     rax, [rbp+57h+var_40]
0x18001386c  mov     [rbp+57h+var_68], rdi
0x180013870  lea     rcx, [rbp+57h+var_70]
0x180013874  mov     [rbp+57h+var_48], rax
0x180013878  mov     [rbp+57h+var_58], rdi
0x18001387c  mov     [rbp+57h+var_50], 3
0x180013883  call    NcaWfpNetEventTriggerRegisterWait
0x180013888  mov     edi, eax
0x18001388a  test    eax, eax
0x18001388c  jz      short loc_1800138BB
0x18001388e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013895  cmp     rcx, r15
0x180013898  jz      short loc_180013837
0x18001389a  test    byte ptr [rcx+1Ch], 1
0x18001389e  jz      short loc_180013837
0x1800138a0  mov     edx, 0Dh
0x1800138a5  mov     rcx, [rcx+10h]
0x1800138a9  mov     r9d, eax
0x1800138ac  mov     r8, r12
0x1800138af  call    WPP_SF_d
0x1800138b4  call    NcaEvCollStrongAuthShutdown
0x1800138b9  jmp     short loc_180013844
0x1800138bb  lea     rax, ?NcaEvCollStrongAuthLockUnlockCollect@@YAXPEAX000@Z; NcaEvCollStrongAuthLockUnlockCollect(void *,void *,void *,void *)
0x1800138c2  mov     [rbp+57h+var_90], 0
0x1800138ca  lea     rdx, qword_1800290D8
0x1800138d1  mov     [rbp+57h+var_88], rax
0x1800138d5  lea     rcx, [rbp+57h+var_90]
0x1800138d9  mov     [rbp+57h+var_80], 0
0x1800138e1  mov     [rbp+57h+var_78], 3
0x1800138e8  call    NcaWtsSessionChangeTriggerRegisterWait
0x1800138ed  mov     edi, eax
0x1800138ef  test    eax, eax
0x1800138f1  jz      short loc_18001391D
0x1800138f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138fa  cmp     rcx, r15
0x1800138fd  jz      loc_180013837
0x180013903  test    byte ptr [rcx+1Ch], 1
0x180013907  jz      loc_180013837
0x18001390d  mov     edx, 0Eh
0x180013912  jmp     short loc_1800138A5
0x180013914  movzx   ebx, di
0x180013917  or      ebx, 80070000h
0x18001391d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013924  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x18001392b  jz      short loc_18001394A
0x18001392d  movsxd  r9, ebx
0x180013930  lea     r8, aEvcollstrongau; "EvCollStrongAuth"
0x180013937  lea     rdx, ModuleInitializeEnd
0x18001393e  call    McTemplateU0zx_EventWriteTransfer
0x180013943  mov     rcx, cs:WPP_GLOBAL_Control
0x18001394a  cmp     rcx, r15
0x18001394d  jz      short loc_180013969
0x18001394f  test    byte ptr [rcx+1Ch], 8
0x180013953  jz      short loc_180013969
0x180013955  mov     rcx, [rcx+10h]
0x180013959  mov     edx, 10h
0x18001395e  mov     r9d, ebx
0x180013961  mov     r8, r12
0x180013964  call    WPP_SF_d
0x180013969  mov     eax, ebx
0x18001396b  mov     rcx, [rbp+57h+var_30]
0x18001396f  xor     rcx, rsp; StackCookie
0x180013972  call    __security_check_cookie
0x180013977  add     rsp, 90h
0x18001397e  pop     r15
0x180013980  pop     r12
0x180013982  pop     rdi
0x180013983  pop     rbx
0x180013984  pop     rbp
0x180013985  retn
```
