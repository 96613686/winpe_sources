# BfeRegDeleteAllValues

- ea: `0x1800492c8`
- end: `0x18004939b`
- name: `BfeRegDeleteAllValues`
- size: `211`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800493a4`

## callees

- `0x1800030a8`
- `0x1800034e0`
- `0x18000438c`
- `0x180007e38`
- `0x1800492c8`
- `0x18004959c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004931d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004931d`

## string_xrefs

- `0x180049333`: `RegDeleteValueW`
- `0x18004934e`: `BfeRegDeleteValue`
- `0x180049378`: `BfeRegDeleteAllValues`

## pseudocode

```c
__int64 __fastcall BfeRegDeleteAllValues(HKEY hKey, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  int v5; // edi
  unsigned int v6; // eax
  __int64 v7; // rcx
  LPCWSTR lpValueName; // [rsp+38h] [rbp+10h] BYREF
  int v10; // [rsp+40h] [rbp+18h]
  int v11; // [rsp+44h] [rbp+1Ch]

  v11 = HIDWORD(a3);
  v3 = 0;
  lpValueName = 0;
  v5 = 1;
  v10 = 1;
  do
  {
    if ( !v5 )
      break;
    v3 = BfeRegEnumValueName(hKey);
    if ( v3 )
      break;
    v5 = v10;
    if ( !v10 )
      break;
    v6 = RegDeleteValueW(hKey, lpValueName);
    if ( (v6 & 0xFFFFFFFD) != 0 )
      v3 = WfpReportSysErrorAsWinError(v7, "RegDeleteValueW", v6);
    BfeRegCloseKey(0);
    if ( v3 )
      WfpReportError(v3, "BfeRegDeleteValue");
    WfpMemFree(&lpValueName);
  }
  while ( !v3 );
  BfeRegCloseKey(0);
  if ( v3 )
    WfpReportError(v3, "BfeRegDeleteAllValues");
  return v3;
}

```

## disassembly

```asm
0x1800492c8  mov     rax, rsp
0x1800492cb  mov     [rax+8], rbx
0x1800492cf  mov     [rax+20h], rsi
0x1800492d3  mov     [rax+18h], r8
0x1800492d7  mov     [rax+10h], rdx
0x1800492db  push    rdi
0x1800492dc  sub     rsp, 20h
0x1800492e0  xor     ebx, ebx
0x1800492e2  mov     rsi, rcx
0x1800492e5  mov     [rax+10h], rbx
0x1800492e9  lea     edi, [rbx+1]
0x1800492ec  mov     [rax+18h], edi
0x1800492ef  test    edi, edi
0x1800492f1  jz      short loc_18004936C
0x1800492f3  lea     r9, [rsp+28h+arg_10]
0x1800492f8  mov     rcx, rsi; hKey
0x1800492fb  lea     r8, [rsp+28h+lpValueName]
0x180049300  call    BfeRegEnumValueName
0x180049305  mov     rbx, rax
0x180049308  test    rax, rax
0x18004930b  jnz     short loc_18004936C
0x18004930d  mov     edi, [rsp+28h+arg_10]
0x180049311  test    edi, edi
0x180049313  jz      short loc_18004936C
0x180049315  mov     rdx, [rsp+28h+lpValueName]; lpValueName
0x18004931a  mov     rcx, rsi; hKey
0x18004931d  call    cs:__imp_RegDeleteValueW
0x180049324  nop     dword ptr [rax+rax+00h]
0x180049329  test    eax, 0FFFFFFFDh
0x18004932e  jz      short loc_180049342
0x180049330  mov     r8d, eax
0x180049333  lea     rdx, aRegdeletevalue; "RegDeleteValueW"
0x18004933a  call    WfpReportSysErrorAsWinError
0x18004933f  mov     rbx, rax
0x180049342  xor     ecx, ecx
0x180049344  call    BfeRegCloseKey
0x180049349  test    rbx, rbx
0x18004934c  jz      short loc_18004935D
0x18004934e  lea     rdx, aBferegdeleteva; "BfeRegDeleteValue"
0x180049355  mov     rcx, rbx
0x180049358  call    WfpReportError
0x18004935d  lea     rcx, [rsp+28h+lpValueName]
0x180049362  call    WfpMemFree
0x180049367  test    rbx, rbx
0x18004936a  jz      short loc_1800492EF
0x18004936c  xor     ecx, ecx
0x18004936e  call    BfeRegCloseKey
0x180049373  test    rbx, rbx
0x180049376  jz      short loc_180049387
0x180049378  lea     rdx, aBferegdeleteal; "BfeRegDeleteAllValues"
0x18004937f  mov     rcx, rbx
0x180049382  call    WfpReportError
0x180049387  mov     rsi, [rsp+28h+arg_18]
0x18004938c  mov     rax, rbx
0x18004938f  mov     rbx, [rsp+28h+arg_0]
0x180049394  add     rsp, 20h
0x180049398  pop     rdi
0x180049399  retn
```
