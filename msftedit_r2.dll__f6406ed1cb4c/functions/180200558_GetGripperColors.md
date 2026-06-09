# GetGripperColors

- ea: `0x180200558`
- end: `0x1802005dc`
- name: `GetGripperColors`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180200500`
- `0x1802005e4`

## callees

- `0x180200558`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180200593`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180200593`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1802005af`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1802005c2`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1802005af`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1802005c2`

## pseudocode

```c
DWORD __fastcall GetGripperColors(DWORD *a1, DWORD *a2)
{
  DWORD result; // eax
  int pvParam; // [rsp+20h] [rbp-18h] BYREF
  __int64 v6; // [rsp+24h] [rbp-14h]
  int v7; // [rsp+2Ch] [rbp-Ch]

  *a2 = 0xFFFFFF;
  *a1 = 2171169;
  v6 = 0;
  v7 = 0;
  pvParam = 16;
  result = SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0);
  if ( result )
  {
    if ( (v6 & 1) != 0 )
    {
      *a2 = GetSysColor(5);
      result = GetSysColor(26);
      *a1 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180200558  mov     [rsp+arg_0], rbx
0x18020055d  push    rdi
0x18020055e  sub     rsp, 30h
0x180200562  mov     dword ptr [rdx], 0FFFFFFh
0x180200568  lea     r8, [rsp+38h+pvParam]; pvParam
0x18020056d  xor     eax, eax
0x18020056f  mov     dword ptr [rcx], 212121h
0x180200575  mov     rbx, rdx
0x180200578  mov     [rsp+38h+var_14], rax
0x18020057d  mov     edx, 10h; uiParam
0x180200582  mov     [rsp+38h+var_C], eax
0x180200586  mov     rdi, rcx
0x180200589  mov     [rsp+38h+pvParam], edx
0x18020058d  xor     r9d, r9d; fWinIni
0x180200590  lea     ecx, [rdx+32h]; uiAction
0x180200593  call    cs:__imp_SystemParametersInfoW
0x18020059a  nop     dword ptr [rax+rax+00h]
0x18020059f  test    eax, eax
0x1802005a1  jz      short loc_1802005D0
0x1802005a3  test    byte ptr [rsp+38h+var_14], 1
0x1802005a8  jz      short loc_1802005D0
0x1802005aa  mov     ecx, 5; nIndex
0x1802005af  call    cs:__imp_GetSysColor
0x1802005b6  nop     dword ptr [rax+rax+00h]
0x1802005bb  mov     ecx, 1Ah; nIndex
0x1802005c0  mov     [rbx], eax
0x1802005c2  call    cs:__imp_GetSysColor
0x1802005c9  nop     dword ptr [rax+rax+00h]
0x1802005ce  mov     [rdi], eax
0x1802005d0  mov     rbx, [rsp+38h+arg_0]
0x1802005d5  add     rsp, 30h
0x1802005d9  pop     rdi
0x1802005da  retn
```
