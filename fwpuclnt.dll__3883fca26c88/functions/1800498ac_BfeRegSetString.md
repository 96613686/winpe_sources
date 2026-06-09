# BfeRegSetString

- ea: `0x1800498ac`
- end: `0x18004993c`
- name: `BfeRegSetString`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001dc80`

## callees

- `0x1800030a8`
- `0x1800034e0`
- `0x180007e38`
- `0x1800498ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800498f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800498f0`

## string_xrefs

- `0x180049903`: `RegSetValueExW`
- `0x18004991e`: `BfeRegSetString`

## pseudocode

```c
__int64 BfeRegSetString(HKEY a1, _QWORD a2, const WCHAR *a3, const BYTE *lpData, ...)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  DWORD cbData; // eax
  unsigned int v7; // eax
  __int64 v8; // rcx

  v4 = 0;
  if ( lpData )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&lpData[2 * v5] );
    cbData = 2 * v5 + 2;
  }
  else
  {
    cbData = 0;
  }
  v7 = RegSetValueExW(a1, a3, 0, 1u, lpData, cbData);
  if ( v7 )
    v4 = WfpReportSysErrorAsWinError(v8, "RegSetValueExW", v7);
  BfeRegCloseKey(0);
  if ( v4 )
    WfpReportError(v4, "BfeRegSetString");
  return v4;
}

```

## disassembly

```asm
0x1800498ac  mov     [rsp+arg_0], rbx
0x1800498b1  push    rdi
0x1800498b2  sub     rsp, 30h
0x1800498b6  xor     edi, edi
0x1800498b8  mov     r10, r8
0x1800498bb  mov     ebx, edi
0x1800498bd  test    r9, r9
0x1800498c0  jz      short loc_1800498D9
0x1800498c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800498c6  inc     rax
0x1800498c9  cmp     [r9+rax*2], di
0x1800498ce  jnz     short loc_1800498C6
0x1800498d0  lea     eax, ds:2[rax*2]
0x1800498d7  jmp     short loc_1800498DB
0x1800498d9  mov     eax, edi
0x1800498db  mov     [rsp+38h+cbData], eax; cbData
0x1800498df  xor     r8d, r8d; Reserved
0x1800498e2  mov     [rsp+38h+lpData], r9; lpData
0x1800498e7  mov     rdx, r10; lpValueName
0x1800498ea  mov     r9d, 1; dwType
0x1800498f0  call    cs:__imp_RegSetValueExW
0x1800498f7  nop     dword ptr [rax+rax+00h]
0x1800498fc  test    eax, eax
0x1800498fe  jz      short loc_180049912
0x180049900  mov     r8d, eax
0x180049903  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x18004990a  call    WfpReportSysErrorAsWinError
0x18004990f  mov     rbx, rax
0x180049912  xor     ecx, ecx
0x180049914  call    BfeRegCloseKey
0x180049919  test    rbx, rbx
0x18004991c  jz      short loc_18004992D
0x18004991e  lea     rdx, aBferegsetstrin; "BfeRegSetString"
0x180049925  mov     rcx, rbx
0x180049928  call    WfpReportError
0x18004992d  mov     rax, rbx
0x180049930  mov     rbx, [rsp+38h+arg_0]
0x180049935  add     rsp, 30h
0x180049939  pop     rdi
0x18004993a  retn
```
