# DWriteCore::Binding::Windows::GetRenderingParamsFromMonitor(HMONITOR__ *)

- ea: `0x1802933fc`
- end: `0x180293571`
- name: `?GetRenderingParamsFromMonitor@Windows@Binding@DWriteCore@@YA?AUClientRenderingParams@3@PEAUHMONITOR__@@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18028e580`

## callees

- `0x180212490`
- `0x180212f4c`
- `0x1802933fc`
- `0x180293578`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18029346a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1802934a9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1802934ce`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180293542`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18029346a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1802934a9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1802934ce`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180293542`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x18029350b`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x18029350b`

## pseudocode

```c
__int64 __fastcall DWriteCore::Binding::Windows::GetRenderingParamsFromMonitor(__int64 a1, HMONITOR a2)
{
  char v4; // di
  float v5; // xmm0_4
  DWriteCore::Binding::Windows *v6; // rdi
  struct DWriteCore::ClientRenderingParams *v7; // r8
  BOOL MonitorInfoW; // eax
  DWriteCore::Binding::Windows *v9; // rdx
  int pvParam; // [rsp+20h] [rbp-59h] BYREF
  _DWORD v12[3]; // [rsp+24h] [rbp-55h] BYREF
  struct tagMONITORINFO mi; // [rsp+30h] [rbp-49h] BYREF
  char v14; // [rsp+58h] [rbp-21h] BYREF

  *(_DWORD *)(a1 + 16) = 1067030938;
  *(_DWORD *)(a1 + 20) = 65537;
  *(_DWORD *)(a1 + 8) = 1065353216;
  *(_DWORD *)(a1 + 12) = 1065353216;
  *(_DWORD *)a1 = 1072064102;
  *(_DWORD *)(a1 + 4) = 1056964608;
  *(_BYTE *)(a1 + 24) = 3;
  *(_WORD *)(a1 + 25) = 0;
  v4 = 1;
  *(_BYTE *)(a1 + 27) = 0;
  pvParam = 0;
  if ( SystemParametersInfoW(0x200Cu, 0, &pvParam, 0) )
    v5 = (float)pvParam * 0.001;
  else
    v5 = FLOAT_1_2;
  *(float *)(a1 + 16) = v5;
  pvParam = 0;
  if ( !SystemParametersInfoW(0x4Au, 0, &pvParam, 0) || pvParam )
  {
    v12[0] = 0;
    if ( !SystemParametersInfoW(0x200Au, 0, v12, 0) || (v4 = 2, v12[0] != 1) )
      v4 = 3;
  }
  *(_BYTE *)(a1 + 24) = v4;
  v6 = 0;
  memset_0(&mi, 0, 0x68u);
  if ( a2 )
  {
    mi.cbSize = 104;
    MonitorInfoW = GetMonitorInfoW(a2, &mi);
    v9 = (DWriteCore::Binding::Windows *)&v14;
    if ( !MonitorInfoW )
      v9 = 0;
    v6 = v9;
  }
  if ( !DWriteCore::Binding::Windows::InitializeRenderingParamsFromDeviceName(v6, (const wchar_t *)a1, v7) )
  {
    v12[0] = 0;
    if ( SystemParametersInfoW(0x2012u, 0, v12, 0) )
    {
      if ( !v12[0] )
        *(_BYTE *)(a1 + 20) = 2;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1802933fc  push    rbp
0x1802933fe  push    rbx
0x1802933ff  push    rsi
0x180293400  push    rdi
0x180293401  lea     rbp, [rsp-3Fh]
0x180293406  sub     rsp, 0B8h
0x18029340d  mov     rax, cs:__security_cookie
0x180293414  xor     rax, rsp
0x180293417  mov     [rbp+57h+var_30], rax
0x18029341b  mov     dword ptr [rcx+10h], 3F99999Ah
0x180293422  lea     r8, [rbp+57h+pvParam]; pvParam
0x180293426  mov     dword ptr [rcx+14h], 10001h
0x18029342d  mov     eax, 3F800000h
0x180293432  mov     [rcx+8], eax
0x180293435  mov     rsi, rdx
0x180293438  mov     [rcx+0Ch], eax
0x18029343b  mov     rbx, rcx
0x18029343e  xor     eax, eax
0x180293440  mov     dword ptr [rcx], 3FE66666h
0x180293446  mov     dword ptr [rcx+4], 3F000000h
0x18029344d  xor     r9d, r9d; fWinIni
0x180293450  mov     byte ptr [rcx+18h], 3
0x180293454  xor     edx, edx; uiParam
0x180293456  mov     [rcx+19h], ax
0x18029345a  mov     edi, 1
0x18029345f  mov     [rcx+1Bh], al
0x180293462  mov     ecx, 200Ch; uiAction
0x180293467  mov     [rbp+57h+pvParam], eax
0x18029346a  call    cs:__imp_SystemParametersInfoW
0x180293470  test    eax, eax
0x180293472  jz      short loc_180293489
0x180293474  mov     eax, [rbp+57h+pvParam]
0x180293477  xorps   xmm0, xmm0
0x18029347a  cvtsi2ss xmm0, rax
0x18029347f  mulss   xmm0, cs:__real@3a83126f
0x180293487  jmp     short loc_180293491
0x180293489  movss   xmm0, cs:__real@3f99999a
0x180293491  xor     edx, edx; uiParam
0x180293493  movss   dword ptr [rbx+10h], xmm0
0x180293498  xor     r9d, r9d; fWinIni
0x18029349b  mov     [rbp+57h+pvParam], 0
0x1802934a2  lea     r8, [rbp+57h+pvParam]; pvParam
0x1802934a6  lea     ecx, [rdx+4Ah]; uiAction
0x1802934a9  call    cs:__imp_SystemParametersInfoW
0x1802934af  test    eax, eax
0x1802934b1  jz      short loc_1802934B9
0x1802934b3  cmp     [rbp+57h+pvParam], 0
0x1802934b7  jz      short loc_1802934E3
0x1802934b9  xor     r9d, r9d; fWinIni
0x1802934bc  mov     [rbp+57h+var_AC], 0
0x1802934c3  lea     r8, [rbp+57h+var_AC]; pvParam
0x1802934c7  xor     edx, edx; uiParam
0x1802934c9  mov     ecx, 200Ah; uiAction
0x1802934ce  call    cs:__imp_SystemParametersInfoW
0x1802934d4  test    eax, eax
0x1802934d6  jz      short loc_1802934E0
0x1802934d8  cmp     [rbp+57h+var_AC], edi
0x1802934db  mov     dil, 2
0x1802934de  jz      short loc_1802934E3
0x1802934e0  mov     dil, 3
0x1802934e3  mov     [rbx+18h], dil
0x1802934e7  lea     rcx, [rbp+57h+mi]; void *
0x1802934eb  xor     edi, edi
0x1802934ed  xor     edx, edx; Val
0x1802934ef  lea     r8d, [rdi+68h]; Size
0x1802934f3  call    memset_0
0x1802934f8  test    rsi, rsi
0x1802934fb  jz      short loc_18029351E
0x1802934fd  lea     rdx, [rbp+57h+mi]; lpmi
0x180293501  mov     [rbp+57h+mi.cbSize], 68h ; 'h'
0x180293508  mov     rcx, rsi; hMonitor
0x18029350b  call    cs:__imp_GetMonitorInfoW
0x180293511  test    eax, eax
0x180293513  lea     rdx, [rbp+57h+var_78]
0x180293517  cmovz   rdx, rdi
0x18029351b  mov     rdi, rdx
0x18029351e  mov     rdx, rbx; wchar_t *
0x180293521  mov     rcx, rdi; this
0x180293524  call    ?InitializeRenderingParamsFromDeviceName@Windows@Binding@DWriteCore@@YA_NPEB_WAEAUClientRenderingParams@3@@Z; DWriteCore::Binding::Windows::InitializeRenderingParamsFromDeviceName(wchar_t const *,DWriteCore::ClientRenderingParams &)
0x180293529  test    al, al
0x18029352b  jnz     short loc_180293556
0x18029352d  xor     r9d, r9d; fWinIni
0x180293530  mov     [rbp+57h+var_AC], 0
0x180293537  lea     r8, [rbp+57h+var_AC]; pvParam
0x18029353b  xor     edx, edx; uiParam
0x18029353d  mov     ecx, 2012h; uiAction
0x180293542  call    cs:__imp_SystemParametersInfoW
0x180293548  test    eax, eax
0x18029354a  jz      short loc_180293556
0x18029354c  cmp     [rbp+57h+var_AC], 0
0x180293550  jnz     short loc_180293556
0x180293552  mov     byte ptr [rbx+14h], 2
0x180293556  mov     rax, rbx
0x180293559  mov     rcx, [rbp+57h+var_30]
0x18029355d  xor     rcx, rsp; StackCookie
0x180293560  call    __security_check_cookie
0x180293565  add     rsp, 0B8h
0x18029356c  pop     rdi
0x18029356d  pop     rsi
0x18029356e  pop     rbx
0x18029356f  pop     rbp
0x180293570  retn
```
