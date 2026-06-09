# CsvtaskHandler::_IncrementRetryCount(ushort *)

- ea: `0x180002728`
- end: `0x180002866`
- name: `?_IncrementRetryCount@CsvtaskHandler@@AEAAEPEAG@Z`
- size: `318`
- prototype: `bool __fastcall(CsvtaskHandler *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001e98`

## callees

- `0x180002728`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000280a`
- `ADVAPI32!RegCloseKey` at `0x180002853`
- `ADVAPI32!RegCloseKey` at `0x18000280a`
- `ADVAPI32!RegCloseKey` at `0x180002853`
- `ADVAPI32!RegCreateKeyExW` at `0x1800027ca`
- `ADVAPI32!RegCreateKeyExW` at `0x1800027ca`
- `ADVAPI32!RegSetValueExW` at `0x180002847`
- `ADVAPI32!RegSetValueExW` at `0x180002847`
- `ADVAPI32!RegQueryValueExW` at `0x1800027f9`
- `ADVAPI32!RegQueryValueExW` at `0x1800027f9`

## pseudocode

```c
bool __fastcall CsvtaskHandler::_IncrementRetryCount(CsvtaskHandler *this, unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r9
  unsigned __int16 *v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int16 *v6; // rax
  bool v7; // zf
  const WCHAR *v8; // rbx
  unsigned int v10; // eax
  LSTATUS v11; // ebx
  unsigned int Data; // [rsp+70h] [rbp+20h] BYREF
  int v13; // [rsp+74h] [rbp+24h]
  DWORD dwDisposition; // [rsp+78h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  v13 = HIDWORD(this);
  cbData = 4;
  Data = 0;
  v2 = -1;
  hKey = 0;
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
  v7 = *v4 == 92;
  v8 = 0;
  dwDisposition = 0;
  if ( !v7 )
    v8 = v4;
  if ( !v8
    || RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Chkdsk\\Scan",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    return 0;
  }
  if ( dwDisposition == 2 )
  {
    if ( (RegQueryValueExW(hKey, v8, 0, 0, (LPBYTE)&Data, &cbData) & 0xFFFFFFFD) != 0 )
    {
      RegCloseKey(hKey);
      return 0;
    }
    v10 = Data;
  }
  else
  {
    v10 = 0;
  }
  Data = v10 + 1;
  v11 = RegSetValueExW(hKey, v8, 0, 4u, (const BYTE *)&Data, 4u);
  RegCloseKey(hKey);
  if ( Data >= 3 )
    return 0;
  return v11 == 0;
}

```

## disassembly

```asm
0x180002728  mov     qword ptr [rsp-18h+Data], rcx
0x18000272d  push    rbp
0x18000272e  push    rbx
0x18000272f  push    rdi
0x180002730  mov     rbp, rsp
0x180002733  sub     rsp, 50h
0x180002737  xor     edi, edi
0x180002739  mov     [rbp+cbData], 4
0x180002740  mov     [rbp+Data], edi
0x180002743  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002747  mov     [rbp+hKey], rdi
0x18000274b  inc     rax
0x18000274e  cmp     [rdx+rax*2], di
0x180002752  jnz     short loc_18000274B
0x180002754  lea     r9, [rax-2]
0x180002758  mov     rcx, rdx
0x18000275b  mov     r8, rdi
0x18000275e  test    r9, r9
0x180002761  jz      short loc_180002780
0x180002763  cmp     word ptr [rdx+r8*2], 5Ch ; '\'
0x180002769  lea     rax, [rdx+2]
0x18000276d  lea     rax, [rax+r8*2]
0x180002771  cmovnz  rax, rcx
0x180002775  inc     r8
0x180002778  mov     rcx, rax
0x18000277b  cmp     r8, r9
0x18000277e  jb      short loc_180002763
0x180002780  cmp     word ptr [rcx], 5Ch ; '\'
0x180002784  mov     rbx, rdi
0x180002787  mov     [rbp+dwDisposition], edi
0x18000278a  cmovnz  rbx, rcx
0x18000278e  test    rbx, rbx
0x180002791  jz      short loc_180002810
0x180002793  lea     rax, [rbp+dwDisposition]
0x180002797  xor     r9d, r9d; lpClass
0x18000279a  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18000279f  lea     rdx, SubKey; "Software\\Microsoft\\Chkdsk\\Scan"
0x1800027a6  lea     rax, [rbp+hKey]
0x1800027aa  xor     r8d, r8d; Reserved
0x1800027ad  mov     [rsp+50h+phkResult], rax; phkResult
0x1800027b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800027b9  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800027be  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x1800027c6  mov     [rsp+50h+dwOptions], edi; dwOptions
0x1800027ca  call    cs:__imp_RegCreateKeyExW
0x1800027d0  test    eax, eax
0x1800027d2  jnz     short loc_180002810
0x1800027d4  cmp     [rbp+dwDisposition], 2
0x1800027d8  jnz     short loc_18000281F
0x1800027da  mov     rcx, [rbp+hKey]; hKey
0x1800027de  lea     rax, [rbp+cbData]
0x1800027e2  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x1800027e7  xor     r9d, r9d; lpType
0x1800027ea  lea     rax, [rbp+Data]
0x1800027ee  xor     r8d, r8d; lpReserved
0x1800027f1  mov     rdx, rbx; lpValueName
0x1800027f4  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800027f9  call    cs:__imp_RegQueryValueExW
0x1800027ff  test    eax, 0FFFFFFFDh
0x180002804  jz      short loc_18000281A
0x180002806  mov     rcx, [rbp+hKey]; hKey
0x18000280a  call    cs:__imp_RegCloseKey
0x180002810  xor     al, al
0x180002812  add     rsp, 50h
0x180002816  pop     rdi
0x180002817  pop     rbx
0x180002818  pop     rbp
0x180002819  retn
0x18000281a  mov     eax, [rbp+Data]
0x18000281d  jmp     short loc_180002821
0x18000281f  mov     eax, edi
0x180002821  mov     rcx, [rbp+hKey]; hKey
0x180002825  inc     eax
0x180002827  mov     [rbp+Data], eax
0x18000282a  mov     r9d, 4; dwType
0x180002830  lea     rax, [rbp+Data]
0x180002834  mov     [rsp+50h+samDesired], 4; cbData
0x18000283c  xor     r8d, r8d; Reserved
0x18000283f  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180002844  mov     rdx, rbx; lpValueName
0x180002847  call    cs:__imp_RegSetValueExW
0x18000284d  mov     rcx, [rbp+hKey]; hKey
0x180002851  mov     ebx, eax
0x180002853  call    cs:__imp_RegCloseKey
0x180002859  cmp     [rbp+Data], 3
0x18000285d  jnb     short loc_180002810
0x18000285f  test    ebx, ebx
0x180002861  setz    al
0x180002864  jmp     short loc_180002812
```
