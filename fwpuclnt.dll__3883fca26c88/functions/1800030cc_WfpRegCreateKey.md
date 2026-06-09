# WfpRegCreateKey

- ea: `0x1800030cc`
- end: `0x180003169`
- name: `WfpRegCreateKey`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003010`

## callees

- `0x1800030cc`
- `0x1800034e0`
- `0x180007e38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003118`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003118`

## string_xrefs

- `0x180003144`: `RegCreateKeyExW`
- `0x180003158`: `WfpRegCreateKey`

## pseudocode

```c
__int64 __fastcall WfpRegCreateKey(HKEY a1, const WCHAR *a2, __int64 a3, _QWORD *a4)
{
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v9; // rax
  HKEY v10; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  v10 = 0;
  v5 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x10u, 0, &v10, 0);
  if ( v5 )
  {
    v9 = WfpReportSysErrorAsWinError(v6, "RegCreateKeyExW", v5);
    v7 = v9;
    if ( v9 )
      WfpReportError(v9, "WfpRegCreateKey");
  }
  else
  {
    v7 = 0;
    *a4 = v10;
  }
  return v7;
}

```

## disassembly

```asm
0x1800030cc  mov     r11, rsp
0x1800030cf  mov     [r11+8], rbx
0x1800030d3  push    rdi
0x1800030d4  sub     rsp, 50h
0x1800030d8  mov     qword ptr [r11-18h], 0
0x1800030e0  lea     rax, [r11+20h]
0x1800030e4  mov     [r11-20h], rax
0x1800030e8  mov     rdi, r9
0x1800030eb  mov     qword ptr [r11-28h], 0
0x1800030f3  xor     r8d, r8d; Reserved
0x1800030f6  mov     qword ptr [r9], 0
0x1800030fd  xor     r9d, r9d; lpClass
0x180003100  mov     [rsp+58h+samDesired], 10h; samDesired
0x180003108  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180003110  mov     qword ptr [r11+20h], 0
0x180003118  call    cs:__imp_RegCreateKeyExW
0x18000311f  nop     dword ptr [rax+rax+00h]
0x180003124  test    eax, eax
0x180003126  jnz     short loc_180003141
0x180003128  mov     rcx, [rsp+58h+arg_18]
0x18000312d  xor     ebx, ebx
0x18000312f  mov     [rdi], rcx
0x180003132  mov     rax, rbx
0x180003135  mov     rbx, [rsp+58h+arg_0]
0x18000313a  add     rsp, 50h
0x18000313e  pop     rdi
0x18000313f  retn
0x180003141  mov     r8d, eax
0x180003144  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18000314b  call    WfpReportSysErrorAsWinError
0x180003150  mov     rbx, rax
0x180003153  test    rax, rax
0x180003156  jz      short loc_180003132
0x180003158  lea     rdx, aWfpregcreateke; "WfpRegCreateKey"
0x18000315f  mov     rcx, rax
0x180003162  call    WfpReportError
0x180003167  jmp     short loc_180003132
```
