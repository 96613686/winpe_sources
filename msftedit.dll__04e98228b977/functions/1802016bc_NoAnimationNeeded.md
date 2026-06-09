# NoAnimationNeeded

- ea: `0x1802016bc`
- end: `0x180201716`
- name: `NoAnimationNeeded`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800091dc`

## callees

- `0x1802016bc`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1802016fb`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1802016fb`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1802016de`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1802016de`

## pseudocode

```c
char NoAnimationNeeded()
{
  char v0; // bl
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  pvParam = 0;
  LODWORD(pvParam) = 16;
  v0 = 1;
  if ( (!SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) || (BYTE4(pvParam) & 1) == 0) && !GetSystemMetrics(4096) )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x1802016bc  push    rbx
0x1802016be  sub     rsp, 30h
0x1802016c2  mov     edx, 10h; uiParam
0x1802016c7  lea     r8, [rsp+38h+pvParam]; pvParam
0x1802016cc  xorps   xmm0, xmm0
0x1802016cf  xor     r9d, r9d; fWinIni
0x1802016d2  movups  [rsp+38h+pvParam], xmm0
0x1802016d7  mov     dword ptr [rsp+38h+pvParam], edx
0x1802016db  lea     ecx, [rdx+32h]; uiAction
0x1802016de  call    cs:__imp_SystemParametersInfoW
0x1802016e5  nop     dword ptr [rax+rax+00h]
0x1802016ea  mov     bl, 1
0x1802016ec  test    eax, eax
0x1802016ee  jz      short loc_1802016F6
0x1802016f0  test    byte ptr [rsp+38h+pvParam+4], bl
0x1802016f4  jnz     short loc_18020170D
0x1802016f6  mov     ecx, 1000h; nIndex
0x1802016fb  call    cs:__imp_GetSystemMetrics
0x180201702  nop     dword ptr [rax+rax+00h]
0x180201707  test    eax, eax
0x180201709  jnz     short loc_18020170D
0x18020170b  xor     bl, bl
0x18020170d  mov     al, bl
0x18020170f  add     rsp, 30h
0x180201713  pop     rbx
0x180201714  retn
```
