# Microsoft::Resources::Build::PriFileMerger::SaveAutoMergedFilePathToRegistry(ushort const *,ushort const *)

- ea: `0x180073a14`
- end: `0x180073bdc`
- name: `?SaveAutoMergedFilePathToRegistry@PriFileMerger@Build@Resources@Microsoft@@QEBAXPEBG0@Z`
- size: `456`
- prototype: `void(Microsoft::Resources::Build::PriFileMerger *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009b2f0`

## callees

- `0x180017960`
- `0x180019570`
- `0x18002cfd0`
- `0x18003c030`
- `0x180073a14`
- `0x180073be4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073b69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073b69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073ba6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073ba6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073b9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073b9c`

## pseudocode

```c
void __fastcall Microsoft::Resources::Build::PriFileMerger::SaveAutoMergedFilePathToRegistry(
        Microsoft::Resources::Build::PriFileMerger *this,
        const unsigned __int16 *a2,
        const BYTE *a3)
{
  __int64 v4; // r8
  const unsigned __int16 *v5; // rdx
  Microsoft::Resources::Build::PriFileMerger *v6; // r9
  int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  const WCHAR *v11; // rcx
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  __int64 *v14; // [rsp+50h] [rbp-9h] BYREF
  __int64 v15; // [rsp+58h] [rbp-1h] BYREF
  __int64 v16; // [rsp+60h] [rbp+7h]
  const WCHAR *v17; // [rsp+68h] [rbp+Fh]
  _BYTE *v18; // [rsp+70h] [rbp+17h] BYREF
  _BYTE v19[56]; // [rsp+78h] [rbp+1Fh] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !(unsigned __int8)DefString_IsEmpty(a2) && !(unsigned __int8)DefString_IsEmpty(v4) )
  {
    DefStringResult_InitBuf(v19);
    v18 = v19;
    if ( (int)Microsoft::Resources::Build::PriFileMerger::GetPriFileComponentName(
                v6,
                v5,
                (struct Microsoft::Resources::StringResult *)&v18) >= 0 )
    {
      DefStringResult_InitBuf(&v15);
      v14 = &v15;
      if ( (v15 || !(_DWORD)v16) && ((_DWORD)v16 || !v15) )
        v17 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Mrt\\_Merged";
      v7 = -2147024809;
      if ( v18 && (*(_QWORD *)v18 || !*((_DWORD *)v18 + 2)) && (*((_DWORD *)v18 + 2) || !*(_QWORD *)v18) )
      {
        v8 = *((_QWORD *)v18 + 2);
        v9 = 0;
      }
      else
      {
        v8 = 0;
        v9 = -2147024809;
      }
      v10 = 0;
      if ( v9 >= 0 )
        v10 = v8;
      if ( (int)DefStringResult_ConcatPathElement(&v15, v10, 92) >= 0 )
      {
        hKey = 0;
        if ( v14 && (*v14 || !*((_DWORD *)v14 + 2)) && (*((_DWORD *)v14 + 2) || !*v14) )
        {
          v11 = (const WCHAR *)v14[2];
          v7 = 0;
        }
        else
        {
          v11 = 0;
        }
        v12 = 0;
        if ( v7 >= 0 )
          v12 = v11;
        if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0, 1u, 0x2001Fu, 0, &hKey, 0) )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&a3[2 * v13] );
          RegSetValueExW(hKey, 0, 0, 1u, a3, 2 * v13 + 2);
          RegCloseKey(hKey);
        }
      }
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v14);
    }
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v18);
  }
}

```

## disassembly

```asm
0x180073a14  push    rbp
0x180073a16  push    rbx
0x180073a17  push    rsi
0x180073a18  push    rdi
0x180073a19  lea     rbp, [rsp-3Fh]
0x180073a1e  sub     rsp, 98h
0x180073a25  mov     r9, rcx
0x180073a28  mov     rdi, r8
0x180073a2b  mov     rcx, rdx
0x180073a2e  call    DefString_IsEmpty
0x180073a33  xor     esi, esi
0x180073a35  test    al, al
0x180073a37  jnz     loc_180073BBE
0x180073a3d  mov     rcx, r8
0x180073a40  call    DefString_IsEmpty
0x180073a45  test    al, al
0x180073a47  jnz     loc_180073BBE
0x180073a4d  lea     rcx, [rbp+57h+var_38]
0x180073a51  call    DefStringResult_InitBuf
0x180073a56  lea     rcx, [rbp+57h+var_38]
0x180073a5a  mov     [rbp+57h+var_40], rcx
0x180073a5e  lea     r8, [rbp+57h+var_40]; struct Microsoft::Resources::StringResult *
0x180073a62  mov     rcx, r9; this
0x180073a65  call    ?GetPriFileComponentName@PriFileMerger@Build@Resources@Microsoft@@QEBAJPEBGAEAVStringResult@34@@Z; Microsoft::Resources::Build::PriFileMerger::GetPriFileComponentName(ushort const *,Microsoft::Resources::StringResult &)
0x180073a6a  test    eax, eax
0x180073a6c  js      loc_180073BB5
0x180073a72  lea     rcx, [rbp+57h+var_58]
0x180073a76  call    DefStringResult_InitBuf
0x180073a7b  mov     rax, [rbp+57h+var_50]
0x180073a7f  lea     rcx, [rbp+57h+var_58]
0x180073a83  mov     [rbp+57h+var_60], rcx
0x180073a87  mov     rcx, [rbp+57h+var_58]
0x180073a8b  test    rcx, rcx
0x180073a8e  jnz     short loc_180073A94
0x180073a90  test    eax, eax
0x180073a92  jnz     short loc_180073AA8
0x180073a94  test    eax, eax
0x180073a96  jnz     short loc_180073A9D
0x180073a98  test    rcx, rcx
0x180073a9b  jnz     short loc_180073AA8
0x180073a9d  lea     rax, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180073aa4  mov     [rbp+57h+var_48], rax
0x180073aa8  mov     rax, [rbp+57h+var_40]
0x180073aac  mov     ebx, 80070057h
0x180073ab1  test    rax, rax
0x180073ab4  jz      loc_180073BCA
0x180073aba  cmp     [rax], rsi
0x180073abd  jnz     short loc_180073AC8
0x180073abf  cmp     [rax+8], esi
0x180073ac2  ja      loc_180073BCA
0x180073ac8  cmp     [rax+8], esi
0x180073acb  jnz     short loc_180073AD6
0x180073acd  cmp     [rax], rsi
0x180073ad0  jnz     loc_180073BCA
0x180073ad6  mov     rcx, [rax+10h]
0x180073ada  mov     eax, esi
0x180073adc  test    eax, eax
0x180073ade  mov     rdx, rsi
0x180073ae1  mov     r8d, 5Ch ; '\'
0x180073ae7  cmovns  rdx, rcx
0x180073aeb  lea     rcx, [rbp+57h+var_58]
0x180073aef  call    DefStringResult_ConcatPathElement
0x180073af4  test    eax, eax
0x180073af6  js      loc_180073BAC
0x180073afc  mov     rax, [rbp+57h+var_60]
0x180073b00  mov     [rbp+57h+hKey], rsi
0x180073b04  test    rax, rax
0x180073b07  jz      loc_180073BD4
0x180073b0d  cmp     [rax], rsi
0x180073b10  jnz     short loc_180073B1B
0x180073b12  cmp     [rax+8], esi
0x180073b15  ja      loc_180073BD4
0x180073b1b  cmp     [rax+8], esi
0x180073b1e  jnz     short loc_180073B29
0x180073b20  cmp     [rax], rsi
0x180073b23  jnz     loc_180073BD4
0x180073b29  mov     rcx, [rax+10h]
0x180073b2d  mov     ebx, esi
0x180073b2f  mov     [rsp+0B0h+lpdwDisposition], rsi; lpdwDisposition
0x180073b34  lea     rax, [rbp+57h+hKey]
0x180073b38  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180073b3d  test    ebx, ebx
0x180073b3f  mov     [rsp+0B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180073b44  mov     rdx, rsi
0x180073b47  cmovns  rdx, rcx; lpSubKey
0x180073b4b  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x180073b53  mov     ebx, 1
0x180073b58  xor     r9d, r9d; lpClass
0x180073b5b  xor     r8d, r8d; Reserved
0x180073b5e  mov     [rsp+0B0h+dwOptions], ebx; dwOptions
0x180073b62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073b69  call    cs:__imp_RegCreateKeyExW
0x180073b6f  test    eax, eax
0x180073b71  jnz     short loc_180073BAC
0x180073b73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180073b77  inc     rax
0x180073b7a  cmp     [rdi+rax*2], si
0x180073b7e  jnz     short loc_180073B77
0x180073b80  mov     rcx, [rbp+57h+hKey]; hKey
0x180073b84  lea     eax, ds:2[rax*2]
0x180073b8b  mov     [rsp+0B0h+samDesired], eax; cbData
0x180073b8f  mov     r9d, ebx; dwType
0x180073b92  xor     r8d, r8d; Reserved
0x180073b95  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x180073b9a  xor     edx, edx; lpValueName
0x180073b9c  call    cs:__imp_RegSetValueExW
0x180073ba2  mov     rcx, [rbp+57h+hKey]; hKey
0x180073ba6  call    cs:__imp_RegCloseKey
0x180073bac  lea     rcx, [rbp+57h+var_60]; this
0x180073bb0  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180073bb5  lea     rcx, [rbp+57h+var_40]; this
0x180073bb9  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180073bbe  add     rsp, 98h
0x180073bc5  pop     rdi
0x180073bc6  pop     rsi
0x180073bc7  pop     rbx
0x180073bc8  pop     rbp
0x180073bc9  retn
0x180073bca  mov     rcx, rsi
0x180073bcd  mov     eax, ebx
0x180073bcf  jmp     loc_180073ADC
0x180073bd4  mov     rcx, rsi
0x180073bd7  jmp     loc_180073B2F
```
