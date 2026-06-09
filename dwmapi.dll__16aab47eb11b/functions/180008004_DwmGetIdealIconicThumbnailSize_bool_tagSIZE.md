# DwmGetIdealIconicThumbnailSize(bool,tagSIZE *)

- ea: `0x180008004`
- end: `0x1800080d1`
- name: `?DwmGetIdealIconicThumbnailSize@@YAH_NPEAUtagSIZE@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(bool, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013ed0`

## callees

- `0x180008004`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180008038`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800080b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800080c7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180008038`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800080b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800080c7`
- `USER32!SystemParametersInfoW` at `0x180008058`
- `USER32!SystemParametersInfoW` at `0x180008058`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x180008022`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x180008022`

## pseudocode

```c
__int64 __fastcall DwmGetIdealIconicThumbnailSize(__int64 a1, struct tagSIZE *a2)
{
  unsigned int v3; // edi
  int DpiForSystem; // eax
  LONG v5; // eax
  int v7; // ecx
  int v8; // r10d
  __int128 pvParam; // [rsp+20h] [rbp-28h] BYREF

  v3 = 0;
  DpiForSystem = GetDpiForSystem();
  a2->cy = 200;
  a2->cx = 200;
  v5 = MulDiv(200, DpiForSystem, 96);
  a2->cx = v5;
  a2->cy = v5;
  pvParam = 0;
  if ( SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
  {
    v7 = 0;
    v8 = 0;
    if ( HIDWORD(pvParam) - DWORD1(pvParam) >= 0 )
      v7 = HIDWORD(pvParam) - DWORD1(pvParam);
    if ( DWORD2(pvParam) - (int)pvParam >= 0 )
      v8 = DWORD2(pvParam) - pvParam;
    if ( v7 * a2->cx >= v8 * a2->cy )
      a2->cx = MulDiv(v8, a2->cy, v7);
    else
      a2->cy = MulDiv(v7, a2->cx, v8);
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180008004  mov     [rsp+arg_0], rbx
0x180008009  push    rdi
0x18000800a  sub     rsp, 40h
0x18000800e  mov     rax, cs:__security_cookie
0x180008015  xor     rax, rsp
0x180008018  mov     [rsp+48h+var_18], rax
0x18000801d  mov     rbx, rdx
0x180008020  xor     edi, edi
0x180008022  call    cs:__imp_GetDpiForSystem
0x180008028  mov     ecx, 0C8h; nNumber
0x18000802d  lea     r8d, [rdi+60h]; nDenominator
0x180008031  mov     edx, eax; nNumerator
0x180008033  mov     [rbx+4], ecx
0x180008036  mov     [rbx], ecx
0x180008038  call    cs:__imp_MulDiv
0x18000803e  xorps   xmm0, xmm0
0x180008041  lea     r8, [rsp+48h+pvParam]; pvParam
0x180008046  lea     ecx, [rdi+30h]; uiAction
0x180008049  mov     [rbx], eax
0x18000804b  xor     r9d, r9d; fWinIni
0x18000804e  mov     [rbx+4], eax
0x180008051  xor     edx, edx; uiParam
0x180008053  movups  [rsp+48h+pvParam], xmm0
0x180008058  call    cs:__imp_SystemParametersInfoW
0x18000805e  test    eax, eax
0x180008060  jnz     short loc_18000807C
0x180008062  mov     eax, edi
0x180008064  mov     rcx, [rsp+48h+var_18]
0x180008069  xor     rcx, rsp; StackCookie
0x18000806c  call    __security_check_cookie
0x180008071  mov     rbx, [rsp+48h+arg_0]
0x180008076  add     rsp, 40h
0x18000807a  pop     rdi
0x18000807b  retn
0x18000807c  mov     eax, dword ptr [rsp+48h+pvParam+0Ch]
0x180008080  mov     ecx, edi
0x180008082  sub     eax, dword ptr [rsp+48h+pvParam+4]
0x180008086  mov     r10d, edi
0x180008089  mov     edx, [rbx+4]; nNumerator
0x18000808c  mov     r9d, edx
0x18000808f  cmovns  ecx, eax; nNumber
0x180008092  mov     eax, dword ptr [rsp+48h+pvParam+8]
0x180008096  sub     eax, dword ptr [rsp+48h+pvParam]
0x18000809a  cmovns  r10d, eax
0x18000809e  mov     eax, [rbx]
0x1800080a0  imul    eax, ecx
0x1800080a3  imul    r9d, r10d
0x1800080a7  cmp     eax, r9d
0x1800080aa  jge     short loc_1800080C1
0x1800080ac  mov     edx, [rbx]; nNumerator
0x1800080ae  mov     r8d, r10d; nDenominator
0x1800080b1  call    cs:__imp_MulDiv
0x1800080b7  mov     [rbx+4], eax
0x1800080ba  mov     edi, 1
0x1800080bf  jmp     short loc_180008062
0x1800080c1  mov     r8d, ecx; nDenominator
0x1800080c4  mov     ecx, r10d; nNumber
0x1800080c7  call    cs:__imp_MulDiv
0x1800080cd  mov     [rbx], eax
0x1800080cf  jmp     short loc_1800080BA
```
