# GetCurrentSessionDword(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort const *,ulong *)

- ea: `0x1400083a4`
- end: `0x1400084fc`
- name: `?GetCurrentSessionDword@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@0PEAK@Z`
- size: `344`
- prototype: `int __high(const unsigned __int16 *, enum tagDMACCOUNTLOOKUPTYPE, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d860`

## callees

- `0x1400083a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000845c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000845c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008499`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400084c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400084c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400084d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400084e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400084d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400084e2`
- `DMCmnUtils!BigStrcat` at `0x140008425`
- `DMCmnUtils!BigStrcat` at `0x140008425`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1400083dc`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1400083dc`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400083f6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400083f6`

## pseudocode

```c
__int64 __fastcall GetCurrentSessionDword(__int64 a1, __int64 a2, const WCHAR *a3, BYTE *a4)
{
  WCHAR *v6; // rbx
  __int64 v7; // rcx
  signed int InternalAcctID; // edi
  HLOCAL v9; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v11; // rdx
  LSTATUS v12; // eax
  bool v13; // cc
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  hMem[0] = 0;
  v6 = 0;
  InternalAcctID = OmaDmGetInternalAcctID(a1, a2, hMem);
  if ( InternalAcctID >= 0 )
  {
    v9 = hMem[0];
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v7);
    v11 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
    if ( !IsStateSeparationEnabled )
      v11 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
    v6 = BigStrcat(3u, v11, L"\\", v9);
    if ( v6 )
    {
      v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
      v13 = v12 <= 0;
      if ( v12 || (v12 = RegQueryValueExW(hKey, a3, 0, &Type, a4, &cbData), v13 = v12 <= 0, v12) )
      {
        if ( v13 )
          InternalAcctID = v12;
        else
          InternalAcctID = (unsigned __int16)v12 | 0x80070000;
      }
      else if ( Type != 4 || cbData != 4 )
      {
        InternalAcctID = -2147418113;
      }
    }
    else
    {
      InternalAcctID = -2147024882;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v6);
  LocalFree(hMem[0]);
  return (unsigned int)InternalAcctID;
}

```

## disassembly

```asm
0x1400083a4  push    rbp
0x1400083a6  push    rbx
0x1400083a7  push    rsi
0x1400083a8  push    rdi
0x1400083a9  push    r14
0x1400083ab  mov     rbp, rsp
0x1400083ae  sub     rsp, 50h
0x1400083b2  mov     r14, r8
0x1400083b5  mov     [rbp+hKey], 0
0x1400083bd  lea     r8, [rbp+hMem]
0x1400083c1  mov     [rbp+Type], 0
0x1400083c8  mov     rsi, r9
0x1400083cb  mov     [rbp+cbData], 4
0x1400083d2  mov     [rbp+hMem], 0
0x1400083da  xor     ebx, ebx
0x1400083dc  call    cs:__imp_OmaDmGetInternalAcctID
0x1400083e3  nop     dword ptr [rax+rax+00h]
0x1400083e8  mov     edi, eax
0x1400083ea  test    eax, eax
0x1400083ec  js      loc_1400084BA
0x1400083f2  mov     rbx, [rbp+hMem]
0x1400083f6  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400083fd  nop     dword ptr [rax+rax+00h]
0x140008402  lea     rcx, aSoftwareMicros_10; "Software\\Microsoft\\Provisioning\\OMAD"...
0x140008409  mov     r9, rbx
0x14000840c  test    al, al
0x14000840e  lea     rdx, aOsdataSoftware_4; "OSData\\Software\\Microsoft\\Provisioni"...
0x140008415  lea     r8, pszSrc; "\\"
0x14000841c  cmovz   rdx, rcx
0x140008420  mov     ecx, 3
0x140008425  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x14000842c  nop     dword ptr [rax+rax+00h]
0x140008431  mov     rbx, rax
0x140008434  test    rax, rax
0x140008437  jnz     short loc_140008440
0x140008439  mov     edi, 8007000Eh
0x14000843e  jmp     short loc_1400084BA
0x140008440  lea     rax, [rbp+hKey]
0x140008444  mov     r9d, 20019h; samDesired
0x14000844a  xor     r8d, r8d; ulOptions
0x14000844d  mov     [rsp+50h+phkResult], rax; phkResult
0x140008452  mov     rdx, rbx; lpSubKey
0x140008455  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000845c  call    cs:__imp_RegOpenKeyExW
0x140008463  nop     dword ptr [rax+rax+00h]
0x140008468  test    eax, eax
0x14000846a  jz      short loc_14000847D
0x14000846c  jg      short loc_140008472
0x14000846e  mov     edi, eax
0x140008470  jmp     short loc_1400084BA
0x140008472  movzx   edi, ax
0x140008475  or      edi, 80070000h
0x14000847b  jmp     short loc_1400084BA
0x14000847d  mov     rcx, [rbp+hKey]; hKey
0x140008481  lea     rax, [rbp+cbData]
0x140008485  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000848a  lea     r9, [rbp+Type]; lpType
0x14000848e  xor     r8d, r8d; lpReserved
0x140008491  mov     [rsp+50h+phkResult], rsi; lpData
0x140008496  mov     rdx, r14; lpValueName
0x140008499  call    cs:__imp_RegQueryValueExW
0x1400084a0  nop     dword ptr [rax+rax+00h]
0x1400084a5  test    eax, eax
0x1400084a7  jnz     short loc_14000846C
0x1400084a9  cmp     [rbp+Type], 4
0x1400084ad  jnz     short loc_1400084B5
0x1400084af  cmp     [rbp+cbData], 4
0x1400084b3  jz      short loc_1400084BA
0x1400084b5  mov     edi, 8000FFFFh
0x1400084ba  mov     rcx, [rbp+hKey]; hKey
0x1400084be  test    rcx, rcx
0x1400084c1  jz      short loc_1400084CF
0x1400084c3  call    cs:__imp_RegCloseKey
0x1400084ca  nop     dword ptr [rax+rax+00h]
0x1400084cf  mov     rcx, rbx; hMem
0x1400084d2  call    cs:__imp_LocalFree
0x1400084d9  nop     dword ptr [rax+rax+00h]
0x1400084de  mov     rcx, [rbp+hMem]; hMem
0x1400084e2  call    cs:__imp_LocalFree
0x1400084e9  nop     dword ptr [rax+rax+00h]
0x1400084ee  mov     eax, edi
0x1400084f0  add     rsp, 50h
0x1400084f4  pop     r14
0x1400084f6  pop     rdi
0x1400084f7  pop     rsi
0x1400084f8  pop     rbx
0x1400084f9  pop     rbp
0x1400084fa  retn
```
