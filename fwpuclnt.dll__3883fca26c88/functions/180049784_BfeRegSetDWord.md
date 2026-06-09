# BfeRegSetDWord

- ea: `0x180049784`
- end: `0x18004980e`
- name: `BfeRegSetDWord`
- size: `138`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001dc80`
- `0x18001df08`
- `0x18001f9a0`

## callees

- `0x1800030a8`
- `0x1800034e0`
- `0x180007e38`
- `0x180012bd0`
- `0x180049784`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800497ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800497ba`

## string_xrefs

- `0x1800497cd`: `RegSetValueExW`
- `0x1800497e8`: `BfeRegSetDWord`

## pseudocode

```c
__int64 __fastcall BfeRegSetDWord(HKEY a1, __int64 a2, const WCHAR *a3, int a4)
{
  __int64 v4; // rbx
  unsigned int v5; // eax
  __int64 v6; // rcx
  BYTE v8[8]; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)v8 = a4;
  v4 = 0;
  v5 = RegSetValueExW(a1, a3, 0, 4u, v8, 4u);
  if ( v5 )
    v4 = WfpReportSysErrorAsWinError(v6, "RegSetValueExW", v5);
  BfeRegCloseKey(0);
  if ( v4 )
    WfpReportError(v4, "BfeRegSetDWord");
  return v4;
}

```

## disassembly

```asm
0x180049784  mov     r11, rsp
0x180049787  push    rbx
0x180049788  sub     rsp, 40h
0x18004978c  mov     rax, cs:__security_cookie
0x180049793  xor     rax, rsp
0x180049796  mov     [rsp+48h+var_10], rax
0x18004979b  lea     rdx, [r11-18h]
0x18004979f  mov     [r11-18h], r9d
0x1800497a3  mov     rax, r8
0x1800497a6  xor     ebx, ebx
0x1800497a8  xor     r8d, r8d; Reserved
0x1800497ab  lea     r9d, [rbx+4]; dwType
0x1800497af  mov     [r11-20h], r9d
0x1800497b3  mov     [r11-28h], rdx
0x1800497b7  mov     rdx, rax; lpValueName
0x1800497ba  call    cs:__imp_RegSetValueExW
0x1800497c1  nop     dword ptr [rax+rax+00h]
0x1800497c6  test    eax, eax
0x1800497c8  jz      short loc_1800497DC
0x1800497ca  mov     r8d, eax
0x1800497cd  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x1800497d4  call    WfpReportSysErrorAsWinError
0x1800497d9  mov     rbx, rax
0x1800497dc  xor     ecx, ecx
0x1800497de  call    BfeRegCloseKey
0x1800497e3  test    rbx, rbx
0x1800497e6  jz      short loc_1800497F7
0x1800497e8  lea     rdx, aBferegsetdword; "BfeRegSetDWord"
0x1800497ef  mov     rcx, rbx
0x1800497f2  call    WfpReportError
0x1800497f7  mov     rax, rbx
0x1800497fa  mov     rcx, [rsp+48h+var_10]
0x1800497ff  xor     rcx, rsp; StackCookie
0x180049802  call    __security_check_cookie
0x180049807  add     rsp, 40h
0x18004980b  pop     rbx
0x18004980c  retn
```
