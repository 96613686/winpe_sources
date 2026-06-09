# AfxOleInprocRegisterHelper(HKEY__ *,HKEY__ *,int)

- ea: `0x1802700b0`
- end: `0x1802702ba`
- name: `?AfxOleInprocRegisterHelper@@YAHPEAUHKEY__@@0H@Z`
- size: `522`
- prototype: `int __fastcall(HKEY__ *hkeyProgID, HKEY__ *hkeyClassID, int nRegFlags)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1801fdad0`
- `0x1801fe1f0`
- `0x180267460`

## callees

- `0x180139860`
- `0x1802700b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18027018d`
- `ADVAPI32!RegCloseKey` at `0x18027019b`
- `ADVAPI32!RegCloseKey` at `0x18027025d`
- `ADVAPI32!RegCloseKey` at `0x18027018d`
- `ADVAPI32!RegCloseKey` at `0x18027019b`
- `ADVAPI32!RegCloseKey` at `0x18027025d`
- `ADVAPI32!RegCreateKeyExW` at `0x180270110`
- `ADVAPI32!RegCreateKeyExW` at `0x180270164`
- `ADVAPI32!RegCreateKeyExW` at `0x180270110`
- `ADVAPI32!RegCreateKeyExW` at `0x180270164`
- `ADVAPI32!RegSetValueExW` at `0x180270248`
- `ADVAPI32!RegSetValueExW` at `0x180270248`
- `ADVAPI32!RegOpenKeyExW` at `0x180270206`
- `ADVAPI32!RegOpenKeyExW` at `0x180270206`
- `ADVAPI32!RegDeleteKeyW` at `0x180270282`
- `ADVAPI32!RegDeleteKeyW` at `0x180270292`
- `ADVAPI32!RegDeleteKeyW` at `0x180270282`
- `ADVAPI32!RegDeleteKeyW` at `0x180270292`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18027021a`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18027021a`

## string_xrefs

- `0x180270239`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AfxOleInprocRegisterHelper(HKEY hkeyProgID, HKEY hkeyClassID, char nRegFlags)
{
  int v6; // ebp
  HKEY v7; // rdi
  LSTATUS v8; // eax
  HKEY v9; // r14
  LSTATUS v10; // eax
  BOOL v11; // ebx
  const wchar_t *v12; // rdi
  LSTATUS v13; // eax
  int v14; // eax
  HKEY phkResult; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF
  DWORD lpdwDisposition; // [rsp+A0h] [rbp+18h] BYREF
  HKEY__ *hkeyInprocServer32; // [rsp+A8h] [rbp+20h] BYREF

  v6 = nRegFlags & 1;
  if ( (nRegFlags & 1) != 0 )
  {
    v7 = 0;
    phkResult = 0;
    v8 = RegCreateKeyExW(hkeyProgID, L"Insertable", 0, 0, 0, 0x2001Fu, 0, &phkResult, &lpdwDisposition);
    v9 = 0;
    if ( !v8 )
      v9 = phkResult;
    if ( (v8 != 0 ? v8 : 0) != 0 )
      goto LABEL_9;
    hKey = 0;
    v10 = RegCreateKeyExW(hkeyClassID, L"Insertable", 0, 0, 0, 0x2001Fu, 0, &hKey, (LPDWORD)&hkeyInprocServer32);
    if ( !v10 )
      v7 = hKey;
    if ( (v10 != 0 ? v10 : 0) != 0 )
LABEL_9:
      v11 = 0;
    else
      v11 = 1;
    if ( v7 )
      RegCloseKey(v7);
    if ( v9 )
      RegCloseKey(v9);
    if ( !v11 )
      goto LABEL_25;
  }
  v12 = szFree;
  if ( (nRegFlags & 4) == 0 )
    v12 = (const wchar_t *)((unsigned __int64)szApartment & -(__int64)((nRegFlags & 2) != 0));
  if ( (nRegFlags & 6) == 6 )
  {
    v12 = (const wchar_t *)&szBoth;
  }
  else if ( !v12 )
  {
    return 1;
  }
  v13 = RegOpenKeyExW(hkeyClassID, L"InprocServer32", 0, 0x20006u, &hkeyInprocServer32);
  v11 = v13 == 0;
  if ( v13 )
  {
    if ( !AfxGetModuleState()->m_bDLL )
      return 1;
  }
  else
  {
    v14 = wcslen(v12);
    v11 = RegSetValueExW(hkeyInprocServer32, L"ThreadingModel", 0, 1u, (const BYTE *)v12, 2 * v14 + 2) == 0;
    RegCloseKey(hkeyInprocServer32);
  }
  if ( !v11 )
  {
    if ( !v6 )
      return v11;
LABEL_25:
    RegDeleteKeyW(hkeyClassID, L"Insertable");
    RegDeleteKeyW(hkeyProgID, L"Insertable");
    return v11;
  }
  return 1;
}

```

## disassembly

```asm
0x1802700b0  mov     r11, rsp
0x1802700b3  mov     [r11+8], rbx
0x1802700b7  mov     [r11+10h], rbp
0x1802700bb  push    rsi
0x1802700bc  push    rdi
0x1802700bd  push    r12
0x1802700bf  push    r14
0x1802700c1  push    r15
0x1802700c3  sub     rsp, 60h
0x1802700c7  mov     esi, nRegFlags
0x1802700ca  mov     r15, hkeyClassID
0x1802700cd  mov     r12, hkeyProgID
0x1802700d0  mov     ebp, nRegFlags
0x1802700d3  and     ebp, 1
0x1802700d6  jz      loc_1802701A9
0x1802700dc  xor     edi, edi
0x1802700de  and     [r11-38h], rdi
0x1802700e2  lea     rax, [r11+18h]
0x1802700e6  mov     [r11-48h], rax
0x1802700ea  lea     rax, [r11-38h]
0x1802700ee  mov     [r11-50h], rax
0x1802700f2  and     [r11-58h], rdi
0x1802700f6  mov     ebx, 2001Fh
0x1802700fb  mov     [rsp+88h+samDesired], ebx; samDesired
0x1802700ff  and     dword ptr [rsp+88h+var_68], edi
0x180270103  xor     r9d, r9d; lpClass
0x180270106  xor     nRegFlags, nRegFlags; Reserved
0x180270109  lea     hkeyClassID, aInsertable; "Insertable"
0x180270110  call    cs:__imp_RegCreateKeyExW
0x180270116  mov     edx, eax
0x180270118  xor     r14d, r14d
0x18027011b  test    eax, eax
0x18027011d  cmovz   r14, [rsp+88h+var_38]
0x180270123  neg     eax
0x180270125  sbb     ecx, ecx
0x180270127  test    edx, ecx
0x180270129  jnz     short loc_180270183
0x18027012b  and     [rsp+88h+hKey], rdi
0x180270130  lea     rax, [rsp+88h+hkeyInprocServer32]
0x180270138  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x18027013d  lea     rax, [rsp+88h+hKey]
0x180270142  mov     [rsp+88h+phkResult], rax; phkResult
0x180270147  and     [rsp+88h+var_58], rdi
0x18027014c  mov     [rsp+88h+samDesired], ebx; samDesired
0x180270150  and     dword ptr [rsp+88h+var_68], edi
0x180270154  xor     r9d, r9d; lpClass
0x180270157  xor     nRegFlags, nRegFlags; Reserved
0x18027015a  lea     hkeyClassID, aInsertable; "Insertable"
0x180270161  mov     hkeyProgID, r15; hKey
0x180270164  call    cs:__imp_RegCreateKeyExW
0x18027016a  mov     edx, eax
0x18027016c  test    eax, eax
0x18027016e  cmovz   rdi, [rsp+88h+hKey]
0x180270174  neg     eax
0x180270176  sbb     ecx, ecx
0x180270178  test    edx, ecx
0x18027017a  jnz     short loc_180270183
0x18027017c  mov     ebx, 1
0x180270181  jmp     short loc_180270185
0x180270183  xor     ebx, ebx
0x180270185  test    rdi, rdi
0x180270188  jz      short loc_180270193
0x18027018a  mov     hkeyProgID, rdi; hKey
0x18027018d  call    cs:__imp_RegCloseKey
0x180270193  test    r14, r14
0x180270196  jz      short loc_1802701A1
0x180270198  mov     hkeyProgID, r14; hKey
0x18027019b  call    cs:__imp_RegCloseKey
0x1802701a1  test    ebx, ebx
0x1802701a3  jz      loc_180270278
0x1802701a9  mov     eax, esi
0x1802701ab  and     al, 2
0x1802701ad  lea     hkeyClassID, szApartment
0x1802701b4  neg     al
0x1802701b6  sbb     hkeyProgID, hkeyProgID
0x1802701b9  and     hkeyProgID, hkeyClassID
0x1802701bc  test    sil, 4
0x1802701c0  lea     rdi, szFree
0x1802701c7  cmovz   rdi, hkeyProgID
0x1802701cb  and     esi, 6
0x1802701ce  cmp     sil, 6
0x1802701d2  jnz     short loc_1802701DD
0x1802701d4  lea     rdi, szBoth
0x1802701db  jmp     short loc_1802701E6
0x1802701dd  test    rdi, rdi
0x1802701e0  jz      loc_18027029C
0x1802701e6  lea     rax, [rsp+88h+hkeyInprocServer32]
0x1802701ee  mov     [rsp+88h+var_68], rax; phkResult
0x1802701f3  mov     r9d, 20006h; samDesired
0x1802701f9  xor     nRegFlags, nRegFlags; ulOptions
0x1802701fc  lea     hkeyClassID, aInprocserver32; "InprocServer32"
0x180270203  mov     hkeyProgID, r15; hKey
0x180270206  call    cs:__imp_RegOpenKeyExW
0x18027020c  xor     ebx, ebx
0x18027020e  test    eax, eax
0x180270210  setz    bl
0x180270213  test    eax, eax
0x180270215  jnz     short loc_180270265
0x180270217  mov     hkeyProgID, rdi; String
0x18027021a  call    cs:__imp_wcslen
0x180270220  lea     eax, ds:2[rax*2]
0x180270227  mov     [rsp+88h+samDesired], eax; cbData
0x18027022b  mov     [rsp+88h+var_68], rdi; lpData
0x180270230  mov     r9d, 1; dwType
0x180270236  xor     nRegFlags, nRegFlags; Reserved
0x180270239  lea     hkeyClassID, aThreadingmodel; "ThreadingModel"
0x180270240  mov     hkeyProgID, [rsp+88h+hkeyInprocServer32]; hKey
0x180270248  call    cs:__imp_RegSetValueExW
0x18027024e  xor     ebx, ebx
0x180270250  test    eax, eax
0x180270252  setz    bl
0x180270255  mov     hkeyProgID, [rsp+88h+hkeyInprocServer32]; hKey
0x18027025d  call    cs:__imp_RegCloseKey
0x180270263  jmp     short loc_180270270
0x180270265  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18027026a  cmp     byte ptr [rax+28h], 0
0x18027026e  jz      short loc_18027029C
0x180270270  test    ebx, ebx
0x180270272  jnz     short loc_18027029C
0x180270274  test    ebp, ebp
0x180270276  jz      short loc_180270298
0x180270278  lea     hkeyClassID, aInsertable; "Insertable"
0x18027027f  mov     hkeyProgID, r15; hKey
0x180270282  call    cs:__imp_RegDeleteKeyW
0x180270288  lea     hkeyClassID, aInsertable; "Insertable"
0x18027028f  mov     hkeyProgID, r12; hKey
0x180270292  call    cs:__imp_RegDeleteKeyW
0x180270298  mov     eax, ebx
0x18027029a  jmp     short loc_1802702A1
0x18027029c  mov     eax, 1
0x1802702a1  lea     r11, [rsp+88h+var_28]
0x1802702a6  mov     rbx, [r11+30h]
0x1802702aa  mov     rbp, [r11+38h]
0x1802702ae  mov     rsp, r11
0x1802702b1  pop     r15
0x1802702b3  pop     r14
0x1802702b5  pop     r12
0x1802702b7  pop     rdi
0x1802702b8  pop     rsi
0x1802702b9  retn
```
