# FwRegSetString

- ea: `0x1800027a0`
- end: `0x1800028da`
- name: `FwRegSetString`
- size: `314`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800027a0`
- `0x1800028e0`
- `0x1800031a0`
- `0x180004750`
- `0x1800047e0`
- `0x18001f6a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000281b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000281b`

## string_xrefs

- `0x1800028c0`: `RegSetValueExW`
- `0x180002890`: `FwRegSetString`
- `0x1800028a8`: `FwRegSetString`
- `0x1800028c7`: `FwRegSetString`

## pseudocode

```c
__int64 __fastcall FwRegSetString(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)
{
  unsigned int v4; // esi
  __int64 v9; // rax
  DWORD cbData; // eax
  unsigned int v12; // eax
  int Key; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)lpSubKey,
      (_DWORD)lpValueName,
      (_DWORD)lpSubKey,
      (__int64)lpValueName,
      (__int64)lpData);
  if ( lpSubKey )
  {
    Key = FwRegCreateKey(hKey, lpSubKey, 2u);
    v4 = Key;
    if ( Key < 0 )
    {
      FwReportReturnError("FwRegSetString", (unsigned int)Key);
      FwRegCloseKey(0);
      return FwReportReturnError("FwRegSetString", v4);
    }
    hKey = 0;
  }
  if ( lpData )
  {
    v9 = -1;
    while ( *(_WORD *)&lpData[2 * v9++ + 2] != 0 )
      ;
    cbData = 2 * v9 + 2;
  }
  else
  {
    cbData = 0;
  }
  v12 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, cbData);
  if ( v12 )
    v4 = FwReportErrorAsWinError("FwRegSetString", "RegSetValueExW", v12);
  FwRegCloseKey(0);
  if ( (v4 & 0x80000000) == 0 )
    return v4;
  return FwReportReturnError("FwRegSetString", v4);
}

```

## disassembly

```asm
0x1800027a0  push    rbx
0x1800027a2  push    rbp
0x1800027a3  push    rsi
0x1800027a4  push    rdi
0x1800027a5  push    r14
0x1800027a7  push    r15
0x1800027a9  sub     rsp, 38h
0x1800027ad  xor     esi, esi
0x1800027af  mov     rbx, r9
0x1800027b2  xor     ebp, ebp
0x1800027b4  mov     r15, r8
0x1800027b7  mov     [rsp+68h+arg_8], rbp
0x1800027bc  mov     rdi, rdx
0x1800027bf  mov     r14, rcx
0x1800027c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027c9  lea     rax, WPP_GLOBAL_Control
0x1800027d0  cmp     rcx, rax
0x1800027d3  jnz     short loc_180002844
0x1800027d5  test    rdi, rdi
0x1800027d8  jnz     loc_180002865
0x1800027de  test    rbx, rbx
0x1800027e1  jz      loc_1800028B6
0x1800027e7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800027ee  xchg    ax, ax
0x1800027f0  cmp     word ptr [rbx+rax*2+2], 0
0x1800027f6  lea     rax, [rax+1]
0x1800027fa  jnz     short loc_1800027F0
0x1800027fc  lea     eax, ds:2[rax*2]
0x180002803  mov     [rsp+68h+cbData], eax; cbData
0x180002807  mov     r9d, 1; dwType
0x18000280d  xor     r8d, r8d; Reserved
0x180002810  mov     [rsp+68h+lpData], rbx; lpData
0x180002815  mov     rdx, r15; lpValueName
0x180002818  mov     rcx, r14; hKey
0x18000281b  call    cs:__imp_RegSetValueExW
0x180002821  test    eax, eax
0x180002823  jnz     loc_1800028BD
0x180002829  mov     rcx, rbp
0x18000282c  call    FwRegCloseKey
0x180002831  test    esi, esi
0x180002833  js      short loc_1800028A6
0x180002835  mov     eax, esi
0x180002837  add     rsp, 38h
0x18000283b  pop     r15
0x18000283d  pop     r14
0x18000283f  pop     rdi
0x180002840  pop     rsi
0x180002841  pop     rbp
0x180002842  pop     rbx
0x180002843  retn
0x180002844  test    byte ptr [rcx+1Ch], 8
0x180002848  jz      short loc_1800027D5
0x18000284a  mov     rcx, [rcx+10h]
0x18000284e  mov     r9, rdi
0x180002851  mov     qword ptr [rsp+68h+cbData], rbx
0x180002856  mov     [rsp+68h+lpData], r15
0x18000285b  call    WPP_SF_SSS
0x180002860  jmp     loc_1800027D5
0x180002865  lea     r9, [rsp+68h+arg_8]
0x18000286a  mov     r8d, 2; samDesired
0x180002870  mov     rdx, rdi; lpSubKey
0x180002873  mov     rcx, r14; hKey
0x180002876  call    FwRegCreateKey
0x18000287b  mov     esi, eax
0x18000287d  test    eax, eax
0x18000287f  js      short loc_18000288E
0x180002881  mov     rbp, [rsp+68h+arg_8]
0x180002886  mov     r14, rbp
0x180002889  jmp     loc_1800027DE
0x18000288e  mov     edx, eax
0x180002890  lea     rcx, aFwregsetstring_0; "FwRegSetString"
0x180002897  call    FwReportReturnError
0x18000289c  mov     rcx, [rsp+68h+arg_8]
0x1800028a1  call    FwRegCloseKey
0x1800028a6  mov     edx, esi
0x1800028a8  lea     rcx, aFwregsetstring_0; "FwRegSetString"
0x1800028af  call    FwReportReturnError
0x1800028b4  jmp     short loc_180002837
0x1800028b6  xor     eax, eax
0x1800028b8  jmp     loc_180002803
0x1800028bd  mov     r8d, eax
0x1800028c0  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x1800028c7  lea     rcx, aFwregsetstring_0; "FwRegSetString"
0x1800028ce  call    FwReportErrorAsWinError
0x1800028d3  mov     esi, eax
0x1800028d5  jmp     loc_180002829
```
