# CsvtaskHandler::_ClearRetryCount(ushort *)

- ea: `0x1800025d4`
- end: `0x18000269b`
- name: `?_ClearRetryCount@CsvtaskHandler@@AEAAXPEAG@Z`
- size: `199`
- prototype: `void __fastcall(CsvtaskHandler *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001e98`

## callees

- `0x1800025d4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000268a`
- `ADVAPI32!RegCloseKey` at `0x18000268a`
- `ADVAPI32!RegSetValueExW` at `0x18000267f`
- `ADVAPI32!RegSetValueExW` at `0x18000267f`
- `ADVAPI32!RegOpenKeyExW` at `0x180002657`
- `ADVAPI32!RegOpenKeyExW` at `0x180002657`

## pseudocode

```c
void __fastcall CsvtaskHandler::_ClearRetryCount(CsvtaskHandler *this, unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r9
  unsigned __int16 *v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int16 *v6; // rax
  const WCHAR *v7; // rbx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v9 = HIDWORD(this);
  Data = 0;
  hKey = 0;
  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  v3 = v2 - 2;
  v4 = a2;
  v5 = 0;
  if ( v2 != 2 )
  {
    do
    {
      v6 = &a2[v5 + 1];
      if ( a2[v5] != 92 )
        v6 = v4;
      ++v5;
      v4 = v6;
    }
    while ( v5 < v3 );
  }
  v7 = 0;
  if ( *v4 != 92 )
    v7 = v4;
  if ( v7 )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Chkdsk\\Scan", 0, 0x2001Fu, &hKey) )
    {
      RegSetValueExW(hKey, v7, 0, 4u, (const BYTE *)&Data, 4u);
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x1800025d4  mov     rax, rsp
0x1800025d7  mov     [rax+18h], rbx
0x1800025db  mov     [rax+8], rcx
0x1800025df  push    rdi
0x1800025e0  sub     rsp, 30h
0x1800025e4  xor     edi, edi
0x1800025e6  mov     [rax+8], edi
0x1800025e9  mov     [rax+10h], rdi
0x1800025ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800025f1  inc     rax
0x1800025f4  cmp     [rdx+rax*2], di
0x1800025f8  jnz     short loc_1800025F1
0x1800025fa  lea     r9, [rax-2]
0x1800025fe  mov     rcx, rdx
0x180002601  mov     r8, rdi
0x180002604  test    r9, r9
0x180002607  jz      short loc_180002626
0x180002609  cmp     word ptr [rdx+r8*2], 5Ch ; '\'
0x18000260f  lea     rax, [rdx+2]
0x180002613  lea     rax, [rax+r8*2]
0x180002617  cmovnz  rax, rcx
0x18000261b  inc     r8
0x18000261e  mov     rcx, rax
0x180002621  cmp     r8, r9
0x180002624  jb      short loc_180002609
0x180002626  cmp     word ptr [rcx], 5Ch ; '\'
0x18000262a  mov     rbx, rdi
0x18000262d  cmovnz  rbx, rcx
0x180002631  test    rbx, rbx
0x180002634  jz      short loc_180002690
0x180002636  lea     rax, [rsp+38h+hKey]
0x18000263b  mov     r9d, 2001Fh; samDesired
0x180002641  xor     r8d, r8d; ulOptions
0x180002644  mov     [rsp+38h+phkResult], rax; phkResult
0x180002649  lea     rdx, SubKey; "Software\\Microsoft\\Chkdsk\\Scan"
0x180002650  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002657  call    cs:__imp_RegOpenKeyExW
0x18000265d  test    eax, eax
0x18000265f  jnz     short loc_180002690
0x180002661  mov     rcx, [rsp+38h+hKey]; hKey
0x180002666  lea     r9d, [rax+4]; dwType
0x18000266a  lea     rax, [rsp+38h+Data]
0x18000266f  mov     [rsp+38h+cbData], r9d; cbData
0x180002674  xor     r8d, r8d; Reserved
0x180002677  mov     [rsp+38h+phkResult], rax; lpData
0x18000267c  mov     rdx, rbx; lpValueName
0x18000267f  call    cs:__imp_RegSetValueExW
0x180002685  mov     rcx, [rsp+38h+hKey]; hKey
0x18000268a  call    cs:__imp_RegCloseKey
0x180002690  mov     rbx, [rsp+38h+arg_10]
0x180002695  add     rsp, 30h
0x180002699  pop     rdi
0x18000269a  retn
```
