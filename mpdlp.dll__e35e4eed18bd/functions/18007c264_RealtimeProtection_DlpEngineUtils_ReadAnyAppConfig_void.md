# RealtimeProtection::DlpEngineUtils::ReadAnyAppConfig(void)

- ea: `0x18007c264`
- end: `0x18007c37e`
- name: `?ReadAnyAppConfig@DlpEngineUtils@RealtimeProtection@@YAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18007a790`

## callees

- `0x180079dc0`
- `0x18007aebc`
- `0x18007c264`
- `0x1800809d0`
- `0x180089510`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18007c317`
- `MpClient!MpConfigSetValue` at `0x18007c317`
- `MpClient!MpConfigClose` at `0x18007c2f2`
- `MpClient!MpConfigClose` at `0x18007c35e`
- `MpClient!MpConfigClose` at `0x18007c2f2`
- `MpClient!MpConfigClose` at `0x18007c35e`
- `MpClient!MpConfigOpen` at `0x18007c2dc`
- `MpClient!MpConfigOpen` at `0x18007c2dc`

## string_xrefs

- `0x18007c2bb`: `DLP::ReadAnyAppConfig:  GetFcValues done. AnyAppEnable %lx`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::ReadAnyAppConfig(
        RealtimeProtection::DlpEngineUtils *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  unsigned int FcValue; // [rsp+38h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  FcValue = RealtimeProtection::DlpPlugin::GetFcValue(78, a2, a3, a4);
  RealtimeProtection::MpLogMessageImpl(
    (RealtimeProtection *)L"DLP::ReadAnyAppConfig:  GetFcValues done. AnyAppEnable %lx",
    (const wchar_t *)FcValue);
  v11 = 0;
  v5 = MpConfigOpen(L"Features", &v11);
  v8 = v11;
  if ( v5 < 0 )
    goto LABEL_5;
  v10 = MpConfigSetValue(v11, L"DlpAnyAppEnabled", 1, 4, &FcValue);
  v5 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v10);
    v8 = v11;
LABEL_5:
    if ( v8 )
      MpConfigClose(v8, v4, v6, v7);
    return (unsigned int)v5;
  }
  if ( v11 )
    MpConfigClose(v11, v4, v6, v7);
  return 0;
}

```

## disassembly

```asm
0x18007c264  mov     [rsp+arg_0], rbx
0x18007c269  push    rdi
0x18007c26a  sub     rsp, 50h
0x18007c26e  mov     rax, cs:__security_cookie
0x18007c275  xor     rax, rsp
0x18007c278  mov     [rsp+58h+var_18], rax
0x18007c27d  lea     rdi, WPP_GLOBAL_Control
0x18007c284  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c28b  cmp     rcx, rdi
0x18007c28e  jz      short loc_18007C2AB
0x18007c290  test    byte ptr [rcx+1Ch], 4
0x18007c294  jz      short loc_18007C2AB
0x18007c296  mov     edx, 93h
0x18007c29b  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c2a2  mov     rcx, [rcx+10h]
0x18007c2a6  call    WPP_SF_
0x18007c2ab  mov     ecx, 4Eh ; 'N'
0x18007c2b0  call    ?GetFcValue@DlpPlugin@RealtimeProtection@@YAKW4FeatureControlEnum@@@Z; RealtimeProtection::DlpPlugin::GetFcValue(FeatureControlEnum)
0x18007c2b5  mov     [rsp+58h+var_20], eax
0x18007c2b9  mov     edx, eax; wchar_t *
0x18007c2bb  lea     rcx, aDlpReadanyappc; "DLP::ReadAnyAppConfig:  GetFcValues don"...
0x18007c2c2  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007c2c7  mov     [rsp+58h+var_28], 0
0x18007c2d0  lea     rdx, [rsp+58h+var_28]
0x18007c2d5  lea     rcx, aFeatures_0; "Features"
0x18007c2dc  call    cs:__imp_MpConfigOpen
0x18007c2e2  mov     ebx, eax
0x18007c2e4  mov     rcx, [rsp+58h+var_28]
0x18007c2e9  test    eax, eax
0x18007c2eb  jns     short loc_18007C2FC
0x18007c2ed  test    rcx, rcx
0x18007c2f0  jz      short loc_18007C2F8
0x18007c2f2  call    cs:__imp_MpConfigClose
0x18007c2f8  mov     eax, ebx
0x18007c2fa  jmp     short loc_18007C366
0x18007c2fc  lea     rax, [rsp+58h+var_20]
0x18007c301  mov     [rsp+58h+var_38], rax
0x18007c306  mov     r9d, 4
0x18007c30c  lea     r8d, [r9-3]
0x18007c310  lea     rdx, aDlpanyappenabl; "DlpAnyAppEnabled"
0x18007c317  call    cs:__imp_MpConfigSetValue
0x18007c31d  mov     ebx, eax
0x18007c31f  test    eax, eax
0x18007c321  jns     short loc_18007C354
0x18007c323  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c32a  cmp     rcx, rdi
0x18007c32d  jz      short loc_18007C34D
0x18007c32f  test    byte ptr [rcx+1Ch], 1
0x18007c333  jz      short loc_18007C34D
0x18007c335  mov     edx, 94h
0x18007c33a  mov     r9d, eax
0x18007c33d  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c344  mov     rcx, [rcx+10h]
0x18007c348  call    WPP_SF_d
0x18007c34d  mov     rcx, [rsp+58h+var_28]
0x18007c352  jmp     short loc_18007C2ED
0x18007c354  mov     rcx, [rsp+58h+var_28]
0x18007c359  test    rcx, rcx
0x18007c35c  jz      short loc_18007C364
0x18007c35e  call    cs:__imp_MpConfigClose
0x18007c364  xor     eax, eax
0x18007c366  mov     rcx, [rsp+58h+var_18]
0x18007c36b  xor     rcx, rsp; StackCookie
0x18007c36e  call    __security_check_cookie
0x18007c373  mov     rbx, [rsp+58h+arg_0]
0x18007c378  add     rsp, 50h
0x18007c37c  pop     rdi
0x18007c37d  retn
```
