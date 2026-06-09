# RealtimeProtection::DlpEngineUtils::ReadFileEvidenceConfig(ulong &)

- ea: `0x18007c86c`
- end: `0x18007ca1a`
- name: `?ReadFileEvidenceConfig@DlpEngineUtils@RealtimeProtection@@YAJAEAK@Z`
- size: `430`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18007a790`
- `0x18019d7f8`

## callees

- `0x18007c86c`
- `0x18007d494`
- `0x1800809d0`
- `0x180089510`
- `0x1800a7df0`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18007c9a2`
- `MpClient!MpConfigSetValue` at `0x18007c9a2`
- `MpClient!MpConfigClose` at `0x18007c96f`
- `MpClient!MpConfigClose` at `0x18007c97e`
- `MpClient!MpConfigClose` at `0x18007c9e7`
- `MpClient!MpConfigClose` at `0x18007c9f6`
- `MpClient!MpConfigClose` at `0x18007c96f`
- `MpClient!MpConfigClose` at `0x18007c97e`
- `MpClient!MpConfigClose` at `0x18007c9e7`
- `MpClient!MpConfigClose` at `0x18007c9f6`
- `MpClient!MpConfigOpen` at `0x18007c90e`
- `MpClient!MpConfigOpen` at `0x18007c95a`
- `MpClient!MpConfigOpen` at `0x18007c90e`
- `MpClient!MpConfigOpen` at `0x18007c95a`

## string_xrefs

- `0x18007c907`: `Miscellaneous Configuration`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::ReadFileEvidenceConfig(
        RealtimeProtection::DlpEngineUtils *this,
        unsigned int *a2)
{
  int FileEvidenceSettingsFromEngine; // eax
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int v10; // ebx
  int v12; // eax
  int v13; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  v14 = 0;
  FileEvidenceSettingsFromEngine = anonymous_namespace_::GetFileEvidenceSettingsFromEngine(&v14, a2);
  if ( FileEvidenceSettingsFromEngine < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      133,
      &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
      (unsigned int)FileEvidenceSettingsFromEngine);
  }
  v16 = 0;
  if ( (int)MpConfigOpen(L"Miscellaneous Configuration", &v16) < 0
    || (v13 = 0, (int)MpConfigGetValueDword(v16, L"DlpFileEvidenceEnabled", &v13, 0) < 0) )
  {
    v4 = v14;
  }
  else
  {
    v4 = v13;
    v14 = v13;
  }
  *(_DWORD *)this = v4;
  v15 = 0;
  v5 = MpConfigOpen(L"Features", &v15);
  v9 = v15;
  v10 = v5;
  if ( v5 < 0 )
    goto LABEL_13;
  v12 = MpConfigSetValue(v15, L"DlpFileEvidenceEnabled", 1, 4, &v14);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v12);
    v9 = v15;
LABEL_13:
    if ( v9 )
      MpConfigClose(v9, v6, v7, v8);
    if ( v16 )
      MpConfigClose(v16, v6, v7, v8);
    return v10;
  }
  if ( v15 )
    MpConfigClose(v15, v6, v7, v8);
  if ( v16 )
    MpConfigClose(v16, v6, v7, v8);
  return 0;
}

```

## disassembly

```asm
0x18007c86c  mov     [rsp-8+arg_8], rbx
0x18007c871  mov     [rsp-8+arg_10], rsi
0x18007c876  push    rbp
0x18007c877  mov     rbp, rsp
0x18007c87a  sub     rsp, 50h
0x18007c87e  mov     rax, cs:__security_cookie
0x18007c885  xor     rax, rsp
0x18007c888  mov     [rbp+var_8], rax
0x18007c88c  mov     rbx, rcx
0x18007c88f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c896  lea     rsi, WPP_GLOBAL_Control
0x18007c89d  cmp     rcx, rsi
0x18007c8a0  jz      short loc_18007C8BD
0x18007c8a2  test    byte ptr [rcx+1Ch], 4
0x18007c8a6  jz      short loc_18007C8BD
0x18007c8a8  mov     rcx, [rcx+10h]
0x18007c8ac  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c8b3  mov     edx, 84h
0x18007c8b8  call    WPP_SF_
0x18007c8bd  lea     rcx, [rbp+var_1C]
0x18007c8c1  mov     [rbp+var_1C], 0
0x18007c8c8  call    _anonymous_namespace___GetFileEvidenceSettingsFromEngine
0x18007c8cd  test    eax, eax
0x18007c8cf  jns     short loc_18007C8FB
0x18007c8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c8d8  cmp     rcx, rsi
0x18007c8db  jz      short loc_18007C8FB
0x18007c8dd  test    byte ptr [rcx+1Ch], 1
0x18007c8e1  jz      short loc_18007C8FB
0x18007c8e3  mov     rcx, [rcx+10h]
0x18007c8e7  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c8ee  mov     edx, 85h
0x18007c8f3  mov     r9d, eax
0x18007c8f6  call    WPP_SF_d
0x18007c8fb  lea     rdx, [rbp+var_10]
0x18007c8ff  mov     [rbp+var_10], 0
0x18007c907  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18007c90e  call    cs:__imp_MpConfigOpen
0x18007c914  test    eax, eax
0x18007c916  js      short loc_18007C942
0x18007c918  mov     rcx, [rbp+var_10]
0x18007c91c  lea     r8, [rbp+var_20]
0x18007c920  xor     r9d, r9d
0x18007c923  mov     [rbp+var_20], 0
0x18007c92a  lea     rdx, aDlpfileevidenc_2; "DlpFileEvidenceEnabled"
0x18007c931  call    MpConfigGetValueDword
0x18007c936  test    eax, eax
0x18007c938  js      short loc_18007C942
0x18007c93a  mov     eax, [rbp+var_20]
0x18007c93d  mov     [rbp+var_1C], eax
0x18007c940  jmp     short loc_18007C945
0x18007c942  mov     eax, [rbp+var_1C]
0x18007c945  lea     rdx, [rbp+var_18]
0x18007c949  mov     [rbx], eax
0x18007c94b  lea     rcx, aFeatures_0; "Features"
0x18007c952  mov     [rbp+var_18], 0
0x18007c95a  call    cs:__imp_MpConfigOpen
0x18007c960  mov     rcx, [rbp+var_18]
0x18007c964  mov     ebx, eax
0x18007c966  test    eax, eax
0x18007c968  jns     short loc_18007C988
0x18007c96a  test    rcx, rcx
0x18007c96d  jz      short loc_18007C975
0x18007c96f  call    cs:__imp_MpConfigClose
0x18007c975  mov     rcx, [rbp+var_10]
0x18007c979  test    rcx, rcx
0x18007c97c  jz      short loc_18007C984
0x18007c97e  call    cs:__imp_MpConfigClose
0x18007c984  mov     eax, ebx
0x18007c986  jmp     short loc_18007C9FE
0x18007c988  mov     r9d, 4
0x18007c98e  lea     rax, [rbp+var_1C]
0x18007c992  lea     rdx, aDlpfileevidenc_2; "DlpFileEvidenceEnabled"
0x18007c999  mov     [rsp+50h+var_30], rax
0x18007c99e  lea     r8d, [r9-3]
0x18007c9a2  call    cs:__imp_MpConfigSetValue
0x18007c9a8  mov     ebx, eax
0x18007c9aa  test    eax, eax
0x18007c9ac  jns     short loc_18007C9DE
0x18007c9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c9b5  cmp     rcx, rsi
0x18007c9b8  jz      short loc_18007C9D8
0x18007c9ba  test    byte ptr [rcx+1Ch], 1
0x18007c9be  jz      short loc_18007C9D8
0x18007c9c0  mov     rcx, [rcx+10h]
0x18007c9c4  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c9cb  mov     edx, 86h
0x18007c9d0  mov     r9d, eax
0x18007c9d3  call    WPP_SF_d
0x18007c9d8  mov     rcx, [rbp+var_18]
0x18007c9dc  jmp     short loc_18007C96A
0x18007c9de  mov     rcx, [rbp+var_18]
0x18007c9e2  test    rcx, rcx
0x18007c9e5  jz      short loc_18007C9ED
0x18007c9e7  call    cs:__imp_MpConfigClose
0x18007c9ed  mov     rcx, [rbp+var_10]
0x18007c9f1  test    rcx, rcx
0x18007c9f4  jz      short loc_18007C9FC
0x18007c9f6  call    cs:__imp_MpConfigClose
0x18007c9fc  xor     eax, eax
0x18007c9fe  mov     rcx, [rbp+var_8]
0x18007ca02  xor     rcx, rsp; StackCookie
0x18007ca05  call    __security_check_cookie
0x18007ca0a  mov     rbx, [rsp+50h+arg_8]
0x18007ca0f  mov     rsi, [rsp+50h+arg_10]
0x18007ca14  add     rsp, 50h
0x18007ca18  pop     rbp
0x18007ca19  retn
```
