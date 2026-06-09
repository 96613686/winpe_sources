# SetAcctInfoHelper

- ea: `0x18001268c`
- end: `0x1800128b7`
- name: `SetAcctInfoHelper`
- size: `555`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e5d4`
- `0x180015120`
- `0x18001ac30`

## callees

- `0x18000c814`
- `0x18000d3ec`
- `0x18000f47c`
- `0x18001268c`
- `0x18001ba40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012876`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012886`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012886`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012896`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800127ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012842`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800127ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012842`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001278a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001278a`
- `DMCmnUtils!CopyString` at `0x1800126eb`
- `DMCmnUtils!CopyString` at `0x1800126eb`

## pseudocode

```c
__int64 __fastcall SetAcctInfoHelper(const unsigned __int16 *a1, int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  signed int AccountIDFromLookupID; // ebx
  char IsStateSeparationEnabled; // al
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  bool v10; // cc
  HKEY v11; // rcx
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+10h] BYREF
  int v17; // [rsp+98h] [rbp+28h] BYREF

  phkResult = 0;
  hKey = 0;
  dwDisposition = 0;
  lpSubKey = 0;
  v17 = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( !a2 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, &lpSubKey);
LABEL_8:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_22;
    goto LABEL_9;
  }
  if ( a2 != 1 )
  {
LABEL_2:
    AccountIDFromLookupID = -2147024809;
    goto LABEL_22;
  }
  AccountIDFromLookupID = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&lpSubKey);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_8;
LABEL_9:
  if ( (unsigned int)GetAccountKey(lpSubKey, 1, 131334, &phkResult, 0) != -2147024894 )
    goto LABEL_20;
  if ( (*(_DWORD *)(a3 + 120) & 0x400000) != 0 && (*(_DWORD *)(a3 + 4) & 0x100000) != 0 )
  {
    v17 = *(_DWORD *)(a3 + 456);
  }
  else
  {
    v17 = 2;
    AccountIDFromLookupID = OmaDmSetValueInStruct(41, a3, -1, 0, (__int64)&v17);
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_22;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v8 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
  if ( !IsStateSeparationEnabled )
    v8 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
  v9 = RegCreateKeyExW((HKEY)qword_18002A510[v17], v8, 0, 0, 0, 0x20106u, 0, &hKey, &dwDisposition);
  AccountIDFromLookupID = v9;
  v10 = v9 <= 0;
  if ( v9
    || (v9 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20106u, 0, &phkResult, &dwDisposition),
        AccountIDFromLookupID = v9,
        v10 = v9 <= 0,
        v9) )
  {
    if ( !v10 )
      AccountIDFromLookupID = (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
LABEL_20:
    v11 = phkResult;
    *a5 = 1;
    AccountIDFromLookupID = InternalSaveAcctInfoToKey(v11, (struct tagOMADMACCTINFO *)a3);
    if ( AccountIDFromLookupID >= 0 )
      AccountIDFromLookupID = 0;
  }
LABEL_22:
  LocalFree((HLOCAL)lpSubKey);
  RegCloseKey(phkResult);
  RegCloseKey(hKey);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x18001268c  mov     [rsp-8+arg_8], rbx
0x180012691  mov     [rsp-8+arg_10], rdi
0x180012696  mov     [rsp-8+arg_18], r9d
0x18001269b  push    rbp
0x18001269c  mov     rbp, rsp
0x18001269f  sub     rsp, 70h
0x1800126a3  mov     [rbp+var_18], 0
0x1800126ab  mov     rdi, r8
0x1800126ae  mov     [rbp+hKey], 0
0x1800126b6  mov     [rbp+dwDisposition], 0
0x1800126bd  mov     [rbp+lpSubKey], 0
0x1800126c5  mov     [rbp+arg_18], 0
0x1800126cc  test    rcx, rcx
0x1800126cf  jnz     short loc_1800126DB
0x1800126d1  mov     ebx, 80070057h
0x1800126d6  jmp     loc_180012872
0x1800126db  test    edx, edx
0x1800126dd  jz      short loc_1800126FF
0x1800126df  cmp     edx, 1
0x1800126e2  jnz     short loc_1800126D1
0x1800126e4  lea     r8, [rbp+lpSubKey]
0x1800126e8  or      edx, 0FFFFFFFFh
0x1800126eb  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800126f2  nop     dword ptr [rax+rax+00h]
0x1800126f7  mov     ebx, eax
0x1800126f9  test    eax, eax
0x1800126fb  js      short loc_18001270C
0x1800126fd  jmp     short loc_180012714
0x1800126ff  lea     r8, [rbp+lpSubKey]
0x180012703  xor     edx, edx
0x180012705  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x18001270a  mov     ebx, eax
0x18001270c  test    ebx, ebx
0x18001270e  js      loc_180012872
0x180012714  mov     rcx, [rbp+lpSubKey]
0x180012718  lea     r9, [rbp+var_18]
0x18001271c  mov     edx, 1
0x180012721  mov     qword ptr [rsp+70h+dwOptions], 0
0x18001272a  mov     r8d, 20106h
0x180012730  call    GetAccountKey
0x180012735  cmp     eax, 80070002h
0x18001273a  jnz     loc_180012854
0x180012740  test    dword ptr [rdi+78h], 400000h
0x180012747  jz      short loc_18001275D
0x180012749  test    dword ptr [rdi+4], 100000h
0x180012750  jz      short loc_18001275D
0x180012752  mov     eax, [rdi+1C8h]
0x180012758  mov     [rbp+arg_18], eax
0x18001275b  jmp     short loc_18001278A
0x18001275d  xor     r9d, r9d
0x180012760  mov     [rbp+arg_18], 2
0x180012767  lea     rax, [rbp+arg_18]
0x18001276b  or      r8d, 0FFFFFFFFh
0x18001276f  mov     rdx, rdi
0x180012772  mov     qword ptr [rsp+70h+dwOptions], rax
0x180012777  lea     ecx, [r9+29h]
0x18001277b  call    OmaDmSetValueInStruct
0x180012780  mov     ebx, eax
0x180012782  test    eax, eax
0x180012784  js      loc_180012872
0x18001278a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180012791  nop     dword ptr [rax+rax+00h]
0x180012796  test    al, al
0x180012798  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18001279f  lea     rax, [rbp+dwDisposition]
0x1800127a3  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1800127a8  lea     r10, qword_18002A510
0x1800127af  lea     rax, [rbp+hKey]
0x1800127b3  mov     [rsp+70h+phkResult], rax; phkResult
0x1800127b8  lea     rdx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800127bf  cmovz   rdx, rcx; lpSubKey
0x1800127c3  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800127cc  movsxd  rcx, [rbp+arg_18]
0x1800127d0  xor     r9d, r9d; lpClass
0x1800127d3  mov     [rsp+70h+samDesired], 20106h; samDesired
0x1800127db  xor     r8d, r8d; Reserved
0x1800127de  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1800127e6  mov     rcx, [r10+rcx*8]; hKey
0x1800127ea  call    cs:__imp_RegCreateKeyExW
0x1800127f1  nop     dword ptr [rax+rax+00h]
0x1800127f6  mov     ebx, eax
0x1800127f8  test    eax, eax
0x1800127fa  jz      short loc_180012809
0x1800127fc  jle     short loc_180012872
0x1800127fe  movzx   ebx, ax
0x180012801  or      ebx, 80070000h
0x180012807  jmp     short loc_180012872
0x180012809  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001280d  lea     rax, [rbp+dwDisposition]
0x180012811  mov     rcx, [rbp+hKey]; hKey
0x180012815  xor     r9d, r9d; lpClass
0x180012818  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18001281d  xor     r8d, r8d; Reserved
0x180012820  lea     rax, [rbp+var_18]
0x180012824  mov     [rsp+70h+phkResult], rax; phkResult
0x180012829  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180012832  mov     [rsp+70h+samDesired], 20106h; samDesired
0x18001283a  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180012842  call    cs:__imp_RegCreateKeyExW
0x180012849  nop     dword ptr [rax+rax+00h]
0x18001284e  mov     ebx, eax
0x180012850  test    eax, eax
0x180012852  jnz     short loc_1800127FC
0x180012854  mov     rax, [rbp+arg_20]
0x180012858  mov     rdx, rdi; struct tagOMADMACCTINFO *
0x18001285b  mov     rcx, [rbp+var_18]; hKey
0x18001285f  mov     dword ptr [rax], 1
0x180012865  call    InternalSaveAcctInfoToKey
0x18001286a  mov     ebx, eax
0x18001286c  test    eax, eax
0x18001286e  js      short loc_180012872
0x180012870  xor     ebx, ebx
0x180012872  mov     rcx, [rbp+lpSubKey]; hMem
0x180012876  call    cs:__imp_LocalFree
0x18001287d  nop     dword ptr [rax+rax+00h]
0x180012882  mov     rcx, [rbp+var_18]; hKey
0x180012886  call    cs:__imp_RegCloseKey
0x18001288d  nop     dword ptr [rax+rax+00h]
0x180012892  mov     rcx, [rbp+hKey]; hKey
0x180012896  call    cs:__imp_RegCloseKey
0x18001289d  nop     dword ptr [rax+rax+00h]
0x1800128a2  lea     r11, [rsp+70h+var_s0]
0x1800128a7  mov     eax, ebx
0x1800128a9  mov     rbx, [r11+18h]
0x1800128ad  mov     rdi, [r11+20h]
0x1800128b1  mov     rsp, r11
0x1800128b4  pop     rbp
0x1800128b5  retn
```
