# RealtimeProtection::DlpEngineUtils::CleanUpPauseResumeRegkeys(void)

- ea: `0x1801a9888`
- end: `0x1801a99b8`
- name: `?CleanUpPauseResumeRegkeys@DlpEngineUtils@RealtimeProtection@@YAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18019ad7c`

## callees

- `0x1800809d0`
- `0x18010cb40`
- `0x1801a9888`

## import_xrefs

- `MpClient!MpConfigClose` at `0x1801a98c8`
- `MpClient!MpConfigClose` at `0x1801a999d`
- `MpClient!MpConfigClose` at `0x1801a98c8`
- `MpClient!MpConfigClose` at `0x1801a999d`
- `MpClient!MpConfigDelValue` at `0x1801a98dc`
- `MpClient!MpConfigDelValue` at `0x1801a992c`
- `MpClient!MpConfigDelValue` at `0x1801a9964`
- `MpClient!MpConfigDelValue` at `0x1801a98dc`
- `MpClient!MpConfigDelValue` at `0x1801a992c`
- `MpClient!MpConfigDelValue` at `0x1801a9964`
- `MpClient!MpConfigOpen` at `0x1801a98b2`
- `MpClient!MpConfigOpen` at `0x1801a98b2`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::CleanUpPauseResumeRegkeys(
        RealtimeProtection::DlpEngineUtils *this)
{
  int v1; // eax
  PVOID *v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  int v6; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // [rsp+20h] [rbp-18h] BYREF

  v11 = 0;
  v1 = MpConfigOpen(L"Features", &v11);
  v5 = v11;
  v6 = v1;
  if ( v1 < 0 )
  {
LABEL_2:
    if ( v5 )
      MpConfigClose(v5, v2, v3, v4);
    return (unsigned int)v6;
  }
  v6 = MpConfigDelValue(v11, L"MpFC_Dlp_PauseResume_Enable", v3, v4);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v9 = 159;
LABEL_9:
    WPP_SF_d(v8[2], v9, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, (unsigned int)v6);
LABEL_10:
    v5 = v11;
    goto LABEL_2;
  }
  v6 = MpConfigDelValue(v11, L"MpFC_Dlp_PauseResume_WaitTime", v3, v4);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v9 = 160;
    goto LABEL_9;
  }
  v6 = MpConfigDelValue(v11, L"MpFC_Dlp_PauseResume_ActionType", v3, v4);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    v2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v9 = 161;
    goto LABEL_9;
  }
  if ( v11 )
    MpConfigClose(v11, v10, v3, v4);
  return 0;
}

```

## disassembly

```asm
0x1801a9888  push    rbx
0x1801a988a  sub     rsp, 30h
0x1801a988e  mov     rax, cs:__security_cookie
0x1801a9895  xor     rax, rsp
0x1801a9898  mov     [rsp+38h+var_10], rax
0x1801a989d  lea     rdx, [rsp+38h+var_18]
0x1801a98a2  mov     [rsp+38h+var_18], 0
0x1801a98ab  lea     rcx, aFeatures_0; "Features"
0x1801a98b2  call    cs:__imp_MpConfigOpen
0x1801a98b8  mov     rcx, [rsp+38h+var_18]
0x1801a98bd  mov     ebx, eax
0x1801a98bf  test    eax, eax
0x1801a98c1  jns     short loc_1801A98D5
0x1801a98c3  test    rcx, rcx
0x1801a98c6  jz      short loc_1801A98CE
0x1801a98c8  call    cs:__imp_MpConfigClose
0x1801a98ce  mov     eax, ebx
0x1801a98d0  jmp     loc_1801A99A5
0x1801a98d5  lea     rdx, aMpfcDlpPausere_0; "MpFC_Dlp_PauseResume_Enable"
0x1801a98dc  call    cs:__imp_MpConfigDelValue
0x1801a98e2  mov     ebx, eax
0x1801a98e4  test    eax, eax
0x1801a98e6  jns     short loc_1801A9920
0x1801a98e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a98ef  lea     rdx, WPP_GLOBAL_Control
0x1801a98f6  cmp     rcx, rdx
0x1801a98f9  jz      short loc_1801A9919
0x1801a98fb  test    byte ptr [rcx+1Ch], 1
0x1801a98ff  jz      short loc_1801A9919
0x1801a9901  mov     edx, 9Fh
0x1801a9906  mov     rcx, [rcx+10h]
0x1801a990a  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9911  mov     r9d, ebx
0x1801a9914  call    WPP_SF_d
0x1801a9919  mov     rcx, [rsp+38h+var_18]
0x1801a991e  jmp     short loc_1801A98C3
0x1801a9920  mov     rcx, [rsp+38h+var_18]
0x1801a9925  lea     rdx, aMpfcDlpPausere_1; "MpFC_Dlp_PauseResume_WaitTime"
0x1801a992c  call    cs:__imp_MpConfigDelValue
0x1801a9932  mov     ebx, eax
0x1801a9934  test    eax, eax
0x1801a9936  jns     short loc_1801A9958
0x1801a9938  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a993f  lea     rdx, WPP_GLOBAL_Control
0x1801a9946  cmp     rcx, rdx
0x1801a9949  jz      short loc_1801A9919
0x1801a994b  test    byte ptr [rcx+1Ch], 1
0x1801a994f  jz      short loc_1801A9919
0x1801a9951  mov     edx, 0A0h
0x1801a9956  jmp     short loc_1801A9906
0x1801a9958  mov     rcx, [rsp+38h+var_18]
0x1801a995d  lea     rdx, aMpfcDlpPausere; "MpFC_Dlp_PauseResume_ActionType"
0x1801a9964  call    cs:__imp_MpConfigDelValue
0x1801a996a  mov     ebx, eax
0x1801a996c  test    eax, eax
0x1801a996e  jns     short loc_1801A9993
0x1801a9970  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9977  lea     rdx, WPP_GLOBAL_Control
0x1801a997e  cmp     rcx, rdx
0x1801a9981  jz      short loc_1801A9919
0x1801a9983  test    byte ptr [rcx+1Ch], 1
0x1801a9987  jz      short loc_1801A9919
0x1801a9989  mov     edx, 0A1h
0x1801a998e  jmp     loc_1801A9906
0x1801a9993  mov     rcx, [rsp+38h+var_18]
0x1801a9998  test    rcx, rcx
0x1801a999b  jz      short loc_1801A99A3
0x1801a999d  call    cs:__imp_MpConfigClose
0x1801a99a3  xor     eax, eax
0x1801a99a5  mov     rcx, [rsp+38h+var_10]
0x1801a99aa  xor     rcx, rsp; StackCookie
0x1801a99ad  call    __security_check_cookie
0x1801a99b2  add     rsp, 30h
0x1801a99b6  pop     rbx
0x1801a99b7  retn
```
