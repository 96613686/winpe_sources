# OSKDuiFrame::InitPressAndHoldTimers(void)

- ea: `0x14000eff0`
- end: `0x14000f092`
- name: `?InitPressAndHoldTimers@OSKDuiFrame@@AEAAXXZ`
- size: `162`
- prototype: `void __fastcall(OSKDuiFrame *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000eb90`

## callees

- `0x14000eff0`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x14000f01a`
- `USER32!SystemParametersInfoW` at `0x14000f039`
- `USER32!SystemParametersInfoW` at `0x14000f01a`
- `USER32!SystemParametersInfoW` at `0x14000f039`

## pseudocode

```c
void __fastcall OSKDuiFrame::InitPressAndHoldTimers(OSKDuiFrame *this)
{
  int v1; // ebx
  double v3; // xmm1_8
  int v4; // [rsp+30h] [rbp+8h] BYREF
  int pvParam; // [rsp+38h] [rbp+10h] BYREF

  v1 = 31;
  v4 = 3;
  pvParam = 31;
  if ( !SystemParametersInfoW(0x16u, 0, &v4, 0) )
    v4 = 3;
  if ( SystemParametersInfoW(0xAu, 0, &pvParam, 0) )
    v1 = pvParam;
  *((_DWORD *)this + 72) = 250 * (v4 + 1);
  if ( v1 )
    v3 = (double)v1;
  else
    v3 = DOUBLE_2_5;
  *((_DWORD *)this + 73) = (int)(1000.0 / v3);
}

```

## disassembly

```asm
0x14000eff0  mov     rax, rsp
0x14000eff3  mov     [rax+18h], rbx
0x14000eff7  push    rdi
0x14000eff8  sub     rsp, 20h
0x14000effc  mov     ebx, 1Fh
0x14000f001  mov     dword ptr [rax+8], 3
0x14000f008  mov     rdi, rcx
0x14000f00b  mov     [rax+10h], ebx
0x14000f00e  xor     r9d, r9d; fWinIni
0x14000f011  lea     r8, [rax+8]; pvParam
0x14000f015  xor     edx, edx; uiParam
0x14000f017  lea     ecx, [rbx-9]; uiAction
0x14000f01a  call    cs:__imp_SystemParametersInfoW
0x14000f020  test    eax, eax
0x14000f022  jnz     short loc_14000F02C
0x14000f024  mov     [rsp+28h+arg_0], 3
0x14000f02c  xor     edx, edx; uiParam
0x14000f02e  lea     r8, [rsp+28h+pvParam]; pvParam
0x14000f033  xor     r9d, r9d; fWinIni
0x14000f036  lea     ecx, [rdx+0Ah]; uiAction
0x14000f039  call    cs:__imp_SystemParametersInfoW
0x14000f03f  test    eax, eax
0x14000f041  jz      short loc_14000F047
0x14000f043  mov     ebx, [rsp+28h+pvParam]
0x14000f047  mov     eax, [rsp+28h+arg_0]
0x14000f04b  inc     eax
0x14000f04d  imul    ecx, eax, 0FAh
0x14000f053  mov     [rdi+120h], ecx
0x14000f059  test    ebx, ebx
0x14000f05b  jnz     short loc_14000F067
0x14000f05d  movsd   xmm1, cs:__real@4004000000000000
0x14000f065  jmp     short loc_14000F071
0x14000f067  mov     eax, ebx
0x14000f069  xorps   xmm1, xmm1
0x14000f06c  cvtsi2sd xmm1, rax
0x14000f071  movsd   xmm0, cs:__real@408f400000000000
0x14000f079  mov     rbx, [rsp+28h+arg_10]
0x14000f07e  divsd   xmm0, xmm1
0x14000f082  cvttsd2si eax, xmm0
0x14000f086  mov     [rdi+124h], eax
0x14000f08c  add     rsp, 20h
0x14000f090  pop     rdi
0x14000f091  retn
```
