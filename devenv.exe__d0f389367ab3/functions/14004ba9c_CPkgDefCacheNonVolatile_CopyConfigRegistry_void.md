# CPkgDefCacheNonVolatile::CopyConfigRegistry(void)

- ea: `0x14004ba9c`
- end: `0x14004bcc4`
- name: `?CopyConfigRegistry@CPkgDefCacheNonVolatile@@IEAAJXZ`
- size: `552`
- prototype: `__int64 __fastcall(CPkgDefCacheNonVolatile *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14004bd10`
- `0x14004bd40`

## callees

- `0x1400084f4`
- `0x1400095f4`
- `0x14004ab74`
- `0x14004ba9c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004bc9b`
- `ADVAPI32!RegCloseKey` at `0x14004bcaa`
- `ADVAPI32!RegCloseKey` at `0x14004bc9b`
- `ADVAPI32!RegCloseKey` at `0x14004bcaa`
- `ADVAPI32!RegCreateKeyExW` at `0x14004bb7d`
- `ADVAPI32!RegCreateKeyExW` at `0x14004bb7d`
- `ADVAPI32!RegOpenKeyExW` at `0x14004bbd9`
- `ADVAPI32!RegOpenKeyExW` at `0x14004bbd9`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004bb17`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004bb17`
- `ADVAPI32!RevertToSelf` at `0x14004bc8c`
- `ADVAPI32!RevertToSelf` at `0x14004bc8c`

## string_xrefs

- `0x14004bae5`: `Copying from HKEY_CURRENT_USER to PkgDefManagement`
- `0x14004baec`: `Copying from HKEY_LOCAL_MACHINE to PkgDefManagement`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPkgDefCacheNonVolatile::CopyConfigRegistry(CPkgDefCacheNonVolatile *this)
{
  HKEY v2; // r15
  HKEY v3; // r12
  const unsigned __int16 *v4; // rcx
  bool v5; // bl
  const WCHAR *v6; // rsi
  HKEY v7; // rdi
  DWORD dwOptions; // eax
  LSTATUS v9; // eax
  signed int v10; // edi
  LSTATUS v11; // eax
  bool v12; // di
  struct IRegistryFilter *v13; // rdi
  DWORD v14; // eax
  int v15; // eax
  HKEY dwDisposition; // [rsp+C8h] [rbp+48h] BYREF
  HKEY phkResult; // [rsp+D0h] [rbp+50h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = L"Copying from HKEY_LOCAL_MACHINE to PkgDefManagement";
  if ( *((_QWORD *)this + 48) == -2147483647 )
    v4 = L"Copying from HKEY_CURRENT_USER to PkgDefManagement";
  CLogger::LogInfo(v4, 0, *((const unsigned __int16 **)this + 49));
  v5 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
  v6 = (const WCHAR *)*((_QWORD *)this + 20);
  v7 = hKey;
  if ( *((_QWORD *)this + 29) )
    v7 = (HKEY)*((_QWORD *)this + 29);
  dwOptions = (*(__int64 (__fastcall **)(CPkgDefCacheNonVolatile *))(*(_QWORD *)this + 32LL))(this);
  phkResult = 0;
  v9 = RegCreateKeyExW(v7, v6, 0, 0, dwOptions, 0x2001Fu, 0, &phkResult, (LPDWORD)&dwDisposition);
  if ( !v9 )
    v2 = phkResult;
  v10 = (unsigned __int16)(v9 != 0 ? v9 : 0) | 0x80070000;
  if ( (v9 != 0 ? v9 : 0) <= 0 )
    v10 = v9 != 0 ? v9 : 0;
  if ( v10 >= 0 )
  {
    _mm_lfence();
    dwDisposition = 0;
    v11 = RegOpenKeyExW(*((HKEY *)this + 48), *((LPCWSTR *)this + 49), 0, 0x20019u, &dwDisposition);
    if ( !v11 )
      v3 = dwDisposition;
    v10 = (unsigned __int16)(v11 != 0 ? v11 : 0) | 0x80070000;
    if ( (v11 != 0 ? v11 : 0) <= 0 )
      v10 = v11 != 0 ? v11 : 0;
    if ( v10 >= 0 )
    {
      _mm_lfence();
      v12 = (unsigned int)(*((_DWORD *)this + 94) - 4) <= 2;
      CodeMarker(9203);
      if ( v12 )
      {
        _mm_lfence();
        v13 = (struct IRegistryFilter *)*((_QWORD *)this + 26);
      }
      else
      {
        v13 = 0;
      }
      v14 = (*(__int64 (__fastcall **)(CPkgDefCacheNonVolatile *))(*(_QWORD *)this + 32LL))(this);
      v15 = VsRegCopyTree(v3, 0, v2, v14, *((HANDLE *)this + 28), v13, *((const unsigned __int16 **)this + 20));
      v10 = (unsigned __int16)v15 | 0x80070000;
      if ( v15 <= 0 )
        v10 = v15;
      if ( v10 >= 0 )
        CodeMarker(9204);
    }
  }
  if ( v5 )
    RevertToSelf();
  if ( v3 )
    RegCloseKey(v3);
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14004ba9c  push    rbp
0x14004ba9e  push    rbx
0x14004ba9f  push    rsi
0x14004baa0  push    rdi
0x14004baa1  push    r12
0x14004baa3  push    r14
0x14004baa5  push    r15
0x14004baa7  mov     rbp, rsp
0x14004baaa  sub     rsp, 80h
0x14004bab1  mov     r14, rcx
0x14004bab4  xorps   xmm0, xmm0
0x14004bab7  xor     eax, eax
0x14004bab9  movups  [rbp+var_30], xmm0
0x14004babd  mov     [rbp+var_20], rax
0x14004bac1  xor     r15d, r15d
0x14004bac4  mov     qword ptr [rbp+var_30], r15
0x14004bac8  and     dword ptr [rbp+var_30+8], eax
0x14004bacb  and     [rbp+var_20], rax
0x14004bacf  movups  [rbp+var_18], xmm0
0x14004bad3  mov     [rbp+var_8], rax
0x14004bad7  xor     r12d, r12d
0x14004bada  mov     qword ptr [rbp+var_18], r12
0x14004bade  and     dword ptr [rbp+var_18+8], eax
0x14004bae1  and     [rbp+var_8], rax
0x14004bae5  lea     rax, aCopyingFromHke_0; "Copying from HKEY_CURRENT_USER to PkgDe"...
0x14004baec  lea     rcx, aCopyingFromHke; "Copying from HKEY_LOCAL_MACHINE to PkgD"...
0x14004baf3  cmp     qword ptr [r14+180h], 0FFFFFFFF80000001h
0x14004bafe  cmovz   rcx, rax; unsigned __int16 *
0x14004bb02  mov     r8, [r14+188h]; unsigned __int16 *
0x14004bb09  xor     edx, edx; int
0x14004bb0b  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14004bb10  mov     rcx, [r14+0E0h]; hToken
0x14004bb17  call    cs:__imp_ImpersonateLoggedOnUser
0x14004bb1d  test    eax, eax
0x14004bb1f  setnz   bl
0x14004bb22  mov     [rbp+arg_0], bl
0x14004bb25  mov     rsi, [r14+0A0h]
0x14004bb2c  mov     rax, [r14+0E8h]
0x14004bb33  mov     rdi, cs:hKey
0x14004bb3a  test    rax, rax
0x14004bb3d  cmovnz  rdi, rax
0x14004bb41  mov     rax, [r14]
0x14004bb44  mov     rcx, r14
0x14004bb47  call    qword ptr [rax+20h]
0x14004bb4a  and     [rbp+arg_10], r12
0x14004bb4e  lea     rcx, [rbp+dwDisposition]
0x14004bb52  mov     [rsp+80h+lpdwDisposition], rcx; lpdwDisposition
0x14004bb57  lea     rcx, [rbp+arg_10]
0x14004bb5b  mov     [rsp+80h+phkResult], rcx; phkResult
0x14004bb60  and     [rsp+80h+var_50], r12
0x14004bb65  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x14004bb6d  mov     [rsp+80h+dwOptions], eax; dwOptions
0x14004bb71  xor     r9d, r9d; lpClass
0x14004bb74  xor     r8d, r8d; Reserved
0x14004bb77  mov     rdx, rsi; lpSubKey
0x14004bb7a  mov     rcx, rdi; hKey
0x14004bb7d  call    cs:__imp_RegCreateKeyExW
0x14004bb83  test    eax, eax
0x14004bb85  jnz     short loc_14004BB92
0x14004bb87  mov     r15, [rbp+arg_10]
0x14004bb8b  mov     qword ptr [rbp+var_30], r15
0x14004bb8f  and     dword ptr [rbp+var_30+8], eax
0x14004bb92  mov     ecx, eax
0x14004bb94  neg     ecx
0x14004bb96  sbb     edx, edx
0x14004bb98  and     edx, eax
0x14004bb9a  movzx   edi, dx
0x14004bb9d  mov     esi, 80070000h
0x14004bba2  or      edi, esi
0x14004bba4  test    edx, edx
0x14004bba6  cmovle  edi, edx
0x14004bba9  test    edi, edi
0x14004bbab  js      loc_14004BC88
0x14004bbb1  lfence
0x14004bbb4  and     [rbp+dwDisposition], 0
0x14004bbb9  lea     rax, [rbp+dwDisposition]
0x14004bbbd  mov     qword ptr [rsp+80h+dwOptions], rax; phkResult
0x14004bbc2  mov     r9d, 20019h; samDesired
0x14004bbc8  xor     r8d, r8d; ulOptions
0x14004bbcb  mov     rdx, [r14+188h]; lpSubKey
0x14004bbd2  mov     rcx, [r14+180h]; hKey
0x14004bbd9  call    cs:__imp_RegOpenKeyExW
0x14004bbdf  test    eax, eax
0x14004bbe1  jnz     short loc_14004BBEE
0x14004bbe3  mov     r12, [rbp+dwDisposition]
0x14004bbe7  mov     qword ptr [rbp+var_18], r12
0x14004bbeb  and     dword ptr [rbp+var_18+8], eax
0x14004bbee  mov     ecx, eax
0x14004bbf0  neg     ecx
0x14004bbf2  sbb     edx, edx
0x14004bbf4  and     edx, eax
0x14004bbf6  movzx   edi, dx
0x14004bbf9  or      edi, esi
0x14004bbfb  test    edx, edx
0x14004bbfd  cmovle  edi, edx
0x14004bc00  test    edi, edi
0x14004bc02  js      loc_14004BC88
0x14004bc08  lfence
0x14004bc0b  mov     eax, [r14+178h]
0x14004bc12  sub     eax, 4
0x14004bc15  cmp     eax, 2
0x14004bc18  setbe   dil
0x14004bc1c  mov     ecx, 23F3h
0x14004bc21  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x14004bc26  test    dil, dil
0x14004bc29  jz      short loc_14004BC37
0x14004bc2b  lfence
0x14004bc2e  mov     rdi, [r14+0D0h]
0x14004bc35  jmp     short loc_14004BC39
0x14004bc37  xor     edi, edi
0x14004bc39  mov     rax, [r14]
0x14004bc3c  mov     rcx, r14
0x14004bc3f  call    qword ptr [rax+20h]
0x14004bc42  mov     r9d, eax; unsigned int
0x14004bc45  mov     rax, [r14+0A0h]
0x14004bc4c  mov     [rsp+80h+var_50], rax; unsigned __int16 *
0x14004bc51  mov     qword ptr [rsp+80h+samDesired], rdi; struct IRegistryFilter *
0x14004bc56  mov     rax, [r14+0E0h]
0x14004bc5d  mov     qword ptr [rsp+80h+dwOptions], rax; hToken
0x14004bc62  mov     r8, r15; HKEY
0x14004bc65  xor     edx, edx; unsigned __int16 *
0x14004bc67  mov     rcx, r12; HKEY
0x14004bc6a  call    ?VsRegCopyTree@@YA_JPEAUHKEY__@@PEBG0KPEAXPEAUIRegistryFilter@@1@Z; VsRegCopyTree(HKEY__ *,ushort const *,HKEY__ *,ulong,void *,IRegistryFilter *,ushort const *)
0x14004bc6f  movzx   edi, ax
0x14004bc72  or      edi, esi
0x14004bc74  test    eax, eax
0x14004bc76  cmovle  edi, eax
0x14004bc79  test    edi, edi
0x14004bc7b  js      short loc_14004BC88
0x14004bc7d  mov     ecx, 23F4h
0x14004bc82  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x14004bc87  nop
0x14004bc88  test    bl, bl
0x14004bc8a  jz      short loc_14004BC93
0x14004bc8c  call    cs:__imp_RevertToSelf
0x14004bc92  nop
0x14004bc93  test    r12, r12
0x14004bc96  jz      short loc_14004BCA2
0x14004bc98  mov     rcx, r12; hKey
0x14004bc9b  call    cs:__imp_RegCloseKey
0x14004bca1  nop
0x14004bca2  test    r15, r15
0x14004bca5  jz      short loc_14004BCB0
0x14004bca7  mov     rcx, r15; hKey
0x14004bcaa  call    cs:__imp_RegCloseKey
0x14004bcb0  mov     eax, edi
0x14004bcb2  add     rsp, 80h
0x14004bcb9  pop     r15
0x14004bcbb  pop     r14
0x14004bcbd  pop     r12
0x14004bcbf  pop     rdi
0x14004bcc0  pop     rsi
0x14004bcc1  pop     rbx
0x14004bcc2  pop     rbp
0x14004bcc3  retn
```
