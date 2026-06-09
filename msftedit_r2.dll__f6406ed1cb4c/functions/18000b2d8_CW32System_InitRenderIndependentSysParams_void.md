# CW32System::InitRenderIndependentSysParams(void)

- ea: `0x18000b2d8`
- end: `0x18000b461`
- name: `?InitRenderIndependentSysParams@CW32System@@SAXXZ`
- size: `393`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a680`
- `0x18000b20c`

## callees

- `0x18000b188`
- `0x18000b2d8`
- `0x18000bc9c`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b316`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b32b`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b33f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b34e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b35d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b372`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b316`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b32b`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b33f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b34e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b35d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000b372`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000b3dd`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000b412`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000b438`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000b3dd`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000b412`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000b438`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x18000b384`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x18000b384`

## pseudocode

```c
void CW32System::InitRenderIndependentSysParams(void)
{
  bool v0; // cl
  bool v1; // al
  int pvParam; // [rsp+30h] [rbp+8h] BYREF
  int v3; // [rsp+38h] [rbp+10h] BYREF
  int v4; // [rsp+40h] [rbp+18h] BYREF

  CW32System::_nScrollInset = 11;
  CW32System::_nDragDelay = 200;
  CW32System::_nDragMinDist = 2;
  CW32System::_nScrollDelay = 50;
  CW32System::_nScrollInterval = 50;
  CW32System::_cxBorder = GetSystemMetrics(5);
  CW32System::_cyBorder = GetSystemMetrics(6);
  GetSystemMetrics(2);
  GetSystemMetrics(3);
  CW32System::_cxDoubleClk = GetSystemMetrics(36);
  CW32System::_cyDoubleClk = GetSystemMetrics(37);
  CW32System::_DCT = GetDoubleClickTime();
  CW32System::_sysiniflags = 0;
  CW32System::_bDigitSubstMode = CW32System::ReadRegDigitSubstitutionMode();
  if ( !CW32System::_draftModeFontInfo )
    word_1802E41CA = 0;
  CW32System::_dupCaret = CW32System::GetSystemCaretWidth(v0);
  pvParam = 0;
  SystemParametersInfoW(0x1Bu, 0, &pvParam, 0);
  v3 = 0;
  CW32System::_fRightHanded = pvParam != 0;
  v4 = 0;
  v1 = SystemParametersInfoW(0x4Au, 0, &v3, 0) && v3 && SystemParametersInfoW(0x200Au, 0, &v4, 0) && v4 == 2;
  CW32System::_fClearTypeIsOn = v1;
}

```

## disassembly

```asm
0x18000b2d8  push    rdi
0x18000b2da  sub     rsp, 20h
0x18000b2de  mov     eax, 0Bh
0x18000b2e3  mov     edi, 2
0x18000b2e8  mov     cs:?_nScrollInset@CW32System@@0GA, ax; ushort CW32System::_nScrollInset
0x18000b2ef  mov     eax, 0C8h
0x18000b2f4  mov     cs:?_nDragDelay@CW32System@@0GA, ax; ushort CW32System::_nDragDelay
0x18000b2fb  mov     cs:?_nDragMinDist@CW32System@@0GA, di; ushort CW32System::_nDragMinDist
0x18000b302  lea     eax, [rdi+30h]
0x18000b305  lea     ecx, [rdi+3]; nIndex
0x18000b308  mov     cs:?_nScrollDelay@CW32System@@0GA, ax; ushort CW32System::_nScrollDelay
0x18000b30f  mov     cs:?_nScrollInterval@CW32System@@0GA, ax; ushort CW32System::_nScrollInterval
0x18000b316  call    cs:__imp_GetSystemMetrics
0x18000b31d  nop     dword ptr [rax+rax+00h]
0x18000b322  lea     ecx, [rdi+4]; nIndex
0x18000b325  mov     cs:?_cxBorder@CW32System@@0HA, eax; int CW32System::_cxBorder
0x18000b32b  call    cs:__imp_GetSystemMetrics
0x18000b332  nop     dword ptr [rax+rax+00h]
0x18000b337  mov     ecx, edi; nIndex
0x18000b339  mov     cs:?_cyBorder@CW32System@@0HA, eax; int CW32System::_cyBorder
0x18000b33f  call    cs:__imp_GetSystemMetrics
0x18000b346  nop     dword ptr [rax+rax+00h]
0x18000b34b  lea     ecx, [rdi+1]; nIndex
0x18000b34e  call    cs:__imp_GetSystemMetrics
0x18000b355  nop     dword ptr [rax+rax+00h]
0x18000b35a  lea     ecx, [rdi+22h]; nIndex
0x18000b35d  call    cs:__imp_GetSystemMetrics
0x18000b364  nop     dword ptr [rax+rax+00h]
0x18000b369  lea     ecx, [rdi+23h]; nIndex
0x18000b36c  mov     cs:?_cxDoubleClk@CW32System@@0HA, eax; int CW32System::_cxDoubleClk
0x18000b372  call    cs:__imp_GetSystemMetrics
0x18000b379  nop     dword ptr [rax+rax+00h]
0x18000b37e  mov     cs:?_cyDoubleClk@CW32System@@0HA, eax; int CW32System::_cyDoubleClk
0x18000b384  call    cs:__imp_GetDoubleClickTime
0x18000b38b  nop     dword ptr [rax+rax+00h]
0x18000b390  mov     cs:?_DCT@CW32System@@0HA, eax; int CW32System::_DCT
0x18000b396  mov     cs:?_sysiniflags@CW32System@@0HA, 0; int CW32System::_sysiniflags
0x18000b3a0  call    ?ReadRegDigitSubstitutionMode@CW32System@@SAEXZ; CW32System::ReadRegDigitSubstitutionMode(void)
0x18000b3a5  cmp     cs:?_draftModeFontInfo@CW32System@@0UDraftModeFontInfo@1@A, 0; CW32System::DraftModeFontInfo CW32System::_draftModeFontInfo
0x18000b3ac  mov     cs:?_bDigitSubstMode@CW32System@@0EA, al; uchar CW32System::_bDigitSubstMode
0x18000b3b2  jnz     short loc_18000B3BD
0x18000b3b4  xor     eax, eax
0x18000b3b6  mov     cs:word_1802E41CA, ax
0x18000b3bd  call    ?GetSystemCaretWidth@CW32System@@SAE_N@Z; CW32System::GetSystemCaretWidth(bool)
0x18000b3c2  xor     edx, edx; uiParam
0x18000b3c4  mov     cs:?_dupCaret@CW32System@@2EA, al; uchar CW32System::_dupCaret
0x18000b3ca  xor     r9d, r9d; fWinIni
0x18000b3cd  mov     [rsp+28h+pvParam], 0
0x18000b3d5  lea     r8, [rsp+28h+pvParam]; pvParam
0x18000b3da  lea     ecx, [rdx+1Bh]; uiAction
0x18000b3dd  call    cs:__imp_SystemParametersInfoW
0x18000b3e4  nop     dword ptr [rax+rax+00h]
0x18000b3e9  cmp     [rsp+28h+pvParam], 0
0x18000b3ee  lea     r8, [rsp+28h+arg_8]; pvParam
0x18000b3f3  mov     [rsp+28h+arg_8], 0
0x18000b3fb  setnz   cs:?_fRightHanded@CW32System@@0EA; uchar CW32System::_fRightHanded
0x18000b402  mov     [rsp+28h+arg_10], 0
0x18000b40a  xor     edx, edx; uiParam
0x18000b40c  xor     r9d, r9d; fWinIni
0x18000b40f  lea     ecx, [rdx+4Ah]; uiAction
0x18000b412  call    cs:__imp_SystemParametersInfoW
0x18000b419  nop     dword ptr [rax+rax+00h]
0x18000b41e  test    eax, eax
0x18000b420  jz      short loc_18000B448
0x18000b422  cmp     [rsp+28h+arg_8], 0
0x18000b427  jz      short loc_18000B448
0x18000b429  xor     r9d, r9d; fWinIni
0x18000b42c  lea     r8, [rsp+28h+arg_10]; pvParam
0x18000b431  xor     edx, edx; uiParam
0x18000b433  mov     ecx, 200Ah; uiAction
0x18000b438  call    cs:__imp_SystemParametersInfoW
0x18000b43f  nop     dword ptr [rax+rax+00h]
0x18000b444  test    eax, eax
0x18000b446  jnz     short loc_18000B457
0x18000b448  xor     al, al
0x18000b44a  mov     cs:?_fClearTypeIsOn@CW32System@@2EA, al; uchar CW32System::_fClearTypeIsOn
0x18000b450  add     rsp, 20h
0x18000b454  pop     rdi
0x18000b455  retn
0x18000b457  cmp     [rsp+28h+arg_10], edi
0x18000b45b  jnz     short loc_18000B448
0x18000b45d  mov     al, 1
0x18000b45f  jmp     short loc_18000B44A
```
