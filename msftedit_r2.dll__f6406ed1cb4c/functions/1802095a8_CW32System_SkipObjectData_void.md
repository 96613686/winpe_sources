# CW32System::SkipObjectData(void)

- ea: `0x1802095a8`
- end: `0x180209834`
- name: `?SkipObjectData@CW32System@@SAHXZ`
- size: `652`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008ebf4`

## callees

- `0x18013ce80`
- `0x18013d2c0`
- `0x1801498dc`
- `0x1802095a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1802095f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1802095f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020969f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180209780`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020969f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180209780`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802097ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802097ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802097ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802097ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802096e9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802096e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802097c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802097c8`

## string_xrefs

- `0x180209691`: `Software\Microsoft\Office\12.0\Common\ObjectBlocking`

## pseudocode

```c
__int64 CW32System::SkipObjectData(void)
{
  DWORD ModuleFileNameW; // eax
  int v1; // ebx
  WCHAR *v2; // rdi
  DWORD i; // esi
  __int64 v5; // r8
  __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( CW32System::_fCheckExe )
    return CW32System::_fSkipObjectData;
  CW32System::_fCheckExe = 1;
  CW32System::_fSkipObjectData = 0;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return CW32System::_fSkipObjectData;
  v1 = 1;
  v2 = &Filename[ModuleFileNameW];
  if ( 2LL * ModuleFileNameW )
  {
    while ( *v2 != 92 )
    {
      --v2;
      ++v1;
      if ( v2 == Filename )
        goto LABEL_6;
    }
    goto LABEL_7;
  }
LABEL_6:
  if ( *v2 == 92 )
  {
LABEL_7:
    --v1;
    ++v2;
  }
  if ( v1 == 12 )
  {
    if ( !CW32System::lstrcmpi(v2, L"OUTLOOK.EXE") )
    {
      CW32System::_fSkipObjectData = 1;
      return 1;
    }
    goto LABEL_12;
  }
  if ( v1 )
  {
LABEL_12:
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Office\\12.0\\Common\\ObjectBlocking", 0, 9u, &hKey) )
    {
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        Name[0] = 0;
        if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
          break;
        v6 = cchName;
        if ( !cchName )
          break;
        if ( cchName > 0x103 )
        {
          v6 = 259;
          cchName = 259;
        }
        v7 = 2LL * (unsigned int)v6;
        if ( v7 >= 0x208 )
          _report_rangecheckfailure(v6, v7, v5);
        Name[(unsigned int)v6] = 0;
        if ( (_DWORD)v6 + 1 == v1 && !CW32System::lstrcmpi(v2, Name) )
        {
          phkResult = 0;
          CW32System::_fSkipObjectData = 1;
          if ( !RegOpenKeyExW(hKey, Name, 0, 1u, &phkResult) )
          {
            Type = 0;
            *(_DWORD *)Data = 0;
            cbData = 4;
            if ( !RegQueryValueExW(phkResult, L"SkipObjects", 0, &Type, Data, &cbData) )
              CW32System::_fSkipObjectData = Data[0] & 1;
          }
          if ( phkResult )
            RegCloseKey(phkResult);
          break;
        }
      }
      RegCloseKey(hKey);
    }
  }
  return CW32System::_fSkipObjectData;
}

```

## disassembly

```asm
0x1802095a8  push    rbp
0x1802095aa  push    rbx
0x1802095ab  push    rsi
0x1802095ac  push    rdi
0x1802095ad  lea     rbp, [rsp-398h]
0x1802095b5  sub     rsp, 498h
0x1802095bc  mov     rax, cs:__security_cookie
0x1802095c3  xor     rax, rsp
0x1802095c6  mov     [rbp+3B0h+var_30], rax
0x1802095cd  cmp     cs:?_fCheckExe@CW32System@@2EA, 0; uchar CW32System::_fCheckExe
0x1802095d4  jnz     loc_18020980B
0x1802095da  mov     r8d, 104h; nSize
0x1802095e0  mov     cs:?_fCheckExe@CW32System@@2EA, 1; uchar CW32System::_fCheckExe
0x1802095e7  lea     rdx, [rbp+3B0h+Filename]; lpFilename
0x1802095ee  mov     cs:?_fSkipObjectData@CW32System@@2EA, 0; uchar CW32System::_fSkipObjectData
0x1802095f5  xor     ecx, ecx; hModule
0x1802095f7  call    cs:__imp_GetModuleFileNameW
0x1802095fe  nop     dword ptr [rax+rax+00h]
0x180209603  test    eax, eax
0x180209605  jz      loc_18020980B
0x18020960b  mov     eax, eax
0x18020960d  lea     rdi, [rbp+3B0h+Filename]
0x180209614  add     rax, rax
0x180209617  mov     ebx, 1
0x18020961c  lea     rdi, [rdi+rax]
0x180209620  jz      short loc_18020963A
0x180209622  cmp     word ptr [rdi], 5Ch ; '\'
0x180209626  jz      short loc_180209640
0x180209628  sub     rdi, 2
0x18020962c  lea     rax, [rbp+3B0h+Filename]
0x180209633  inc     ebx
0x180209635  cmp     rdi, rax
0x180209638  jnz     short loc_180209622
0x18020963a  cmp     word ptr [rdi], 5Ch ; '\'
0x18020963e  jnz     short loc_180209646
0x180209640  dec     ebx
0x180209642  add     rdi, 2
0x180209646  cmp     ebx, 0Ch
0x180209649  jnz     short loc_18020966D
0x18020964b  lea     rdx, aOutlookExe; "OUTLOOK.EXE"
0x180209652  mov     rcx, rdi; unsigned __int16 *
0x180209655  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x18020965a  test    eax, eax
0x18020965c  jnz     short loc_180209675
0x18020965e  mov     cs:?_fSkipObjectData@CW32System@@2EA, 1; uchar CW32System::_fSkipObjectData
0x180209665  lea     eax, [rbx-0Bh]
0x180209668  jmp     loc_180209812
0x18020966d  test    ebx, ebx
0x18020966f  jz      loc_18020980B
0x180209675  lea     rax, [rsp+4B0h+hKey]
0x18020967a  mov     [rsp+4B0h+hKey], 0
0x180209683  mov     r9d, 9; samDesired
0x180209689  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18020968e  xor     r8d, r8d; ulOptions
0x180209691  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Office\\12.0\\Comm"...
0x180209698  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18020969f  call    cs:__imp_RegOpenKeyExW
0x1802096a6  nop     dword ptr [rax+rax+00h]
0x1802096ab  test    eax, eax
0x1802096ad  jnz     loc_18020980B
0x1802096b3  xor     esi, esi
0x1802096b5  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1802096ba  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x1802096bf  xor     eax, eax
0x1802096c1  mov     [rsp+4B0h+cchName], 104h
0x1802096c9  mov     [rsp+4B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1802096ce  lea     r8, [rsp+4B0h+Name]; lpName
0x1802096d3  mov     [rsp+4B0h+lpcchClass], rax; lpcchClass
0x1802096d8  mov     edx, esi; dwIndex
0x1802096da  mov     [rsp+4B0h+lpClass], rax; lpClass
0x1802096df  mov     [rsp+4B0h+phkResult], rax; lpReserved
0x1802096e4  mov     [rsp+4B0h+Name], ax
0x1802096e9  call    cs:__imp_RegEnumKeyExW
0x1802096f0  nop     dword ptr [rax+rax+00h]
0x1802096f5  test    eax, eax
0x1802096f7  jnz     loc_1802097FA
0x1802096fd  mov     ecx, [rsp+4B0h+cchName]
0x180209701  test    ecx, ecx
0x180209703  jz      loc_1802097FA
0x180209709  cmp     ecx, 103h
0x18020970f  jbe     short loc_18020971A
0x180209711  mov     ecx, 103h
0x180209716  mov     [rsp+4B0h+cchName], ecx
0x18020971a  mov     eax, ecx
0x18020971c  lea     rdx, [rax+rax]
0x180209720  cmp     rdx, 208h
0x180209727  jnb     loc_18020982E
0x18020972d  xor     eax, eax
0x18020972f  mov     [rsp+rdx+4B0h+Name], ax
0x180209734  lea     eax, [rcx+1]
0x180209737  cmp     eax, ebx
0x180209739  jnz     short loc_18020974C
0x18020973b  lea     rdx, [rsp+4B0h+Name]; unsigned __int16 *
0x180209740  mov     rcx, rdi; unsigned __int16 *
0x180209743  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180209748  test    eax, eax
0x18020974a  jz      short loc_180209753
0x18020974c  inc     esi
0x18020974e  jmp     loc_1802096B5
0x180209753  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180209758  lea     rax, [rsp+4B0h+var_458]
0x18020975d  mov     r9d, 1; samDesired
0x180209763  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180209768  xor     r8d, r8d; ulOptions
0x18020976b  mov     [rsp+4B0h+var_458], 0
0x180209774  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x180209779  mov     cs:?_fSkipObjectData@CW32System@@2EA, 1; uchar CW32System::_fSkipObjectData
0x180209780  call    cs:__imp_RegOpenKeyExW
0x180209787  nop     dword ptr [rax+rax+00h]
0x18020978c  test    eax, eax
0x18020978e  jnz     short loc_1802097E4
0x180209790  mov     rcx, [rsp+4B0h+var_458]; hKey
0x180209795  lea     r9, [rsp+4B0h+Type]; lpType
0x18020979a  mov     [rsp+4B0h+Type], eax
0x18020979e  lea     rdx, aSkipobjects; "SkipObjects"
0x1802097a5  mov     dword ptr [rsp+4B0h+Data], eax
0x1802097a9  xor     r8d, r8d; lpReserved
0x1802097ac  lea     rax, [rsp+4B0h+cbData]
0x1802097b1  mov     [rsp+4B0h+cbData], 4
0x1802097b9  mov     [rsp+4B0h+lpClass], rax; lpcbData
0x1802097be  lea     rax, [rsp+4B0h+Data]
0x1802097c3  mov     [rsp+4B0h+phkResult], rax; lpData
0x1802097c8  call    cs:__imp_RegQueryValueExW
0x1802097cf  nop     dword ptr [rax+rax+00h]
0x1802097d4  test    eax, eax
0x1802097d6  jnz     short loc_1802097E4
0x1802097d8  mov     al, [rsp+4B0h+Data]
0x1802097dc  and     al, 1
0x1802097de  mov     cs:?_fSkipObjectData@CW32System@@2EA, al; uchar CW32System::_fSkipObjectData
0x1802097e4  mov     rcx, [rsp+4B0h+var_458]; hKey
0x1802097e9  test    rcx, rcx
0x1802097ec  jz      short loc_1802097FA
0x1802097ee  call    cs:__imp_RegCloseKey
0x1802097f5  nop     dword ptr [rax+rax+00h]
0x1802097fa  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1802097ff  call    cs:__imp_RegCloseKey
0x180209806  nop     dword ptr [rax+rax+00h]
0x18020980b  movzx   eax, cs:?_fSkipObjectData@CW32System@@2EA; uchar CW32System::_fSkipObjectData
0x180209812  mov     rcx, [rbp+3B0h+var_30]
0x180209819  xor     rcx, rsp; StackCookie
0x18020981c  call    __security_check_cookie
0x180209821  add     rsp, 498h
0x180209828  pop     rdi
0x180209829  pop     rsi
0x18020982a  pop     rbx
0x18020982b  pop     rbp
0x18020982c  retn
0x18020982e  call    __report_rangecheckfailure
```
