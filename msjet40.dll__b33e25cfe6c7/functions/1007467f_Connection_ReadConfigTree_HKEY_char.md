# Connection::ReadConfigTree(HKEY__ *,char *)

- ea: `0x1007467f`
- end: `0x10074859`
- name: `?ReadConfigTree@Connection@@AAEXPAUHKEY__@@PAD@Z`
- size: `474`
- prototype: `void __thiscall(Connection *__hidden this, HKEY hKey, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10027930`

## callees

- `0x1007462a`
- `0x1007467f`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100747c9`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100747e1`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10074814`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1007482d`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100747c9`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100747e1`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10074814`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1007482d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100746b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x100746b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10074843`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10074843`

## string_xrefs

- `0x10074703`: `Threads`
- `0x100747b2`: `UserCommitSync`
- `0x100747fd`: `ImplicitCommitSync`

## pseudocode

```c
void __thiscall Connection::ReadConfigTree(BYTE *this, HKEY hKey, char *lpSubKey)
{
  HKEY v4; // eax
  Connection *v5; // ecx
  Connection *v6; // ecx
  Connection *v7; // ecx
  Connection *v8; // ecx
  Connection *v9; // ecx
  Connection *v10; // ecx
  Connection *v11; // ecx
  Connection *v12; // ecx
  Connection *v13; // ecx
  Connection *v14; // ecx
  Connection *v15; // ecx
  Connection *v16; // ecx
  Connection *v17; // ecx
  Connection *v18; // [esp-8h] [ebp-20h]
  HKEY phkResult; // [esp+8h] [ebp-10h] BYREF
  char String1[8]; // [esp+Ch] [ebp-Ch] BYREF

  v4 = HKEY_LOCAL_MACHINE;
  if ( hKey )
    v4 = hKey;
  if ( !RegOpenKeyExA(v4, lpSubKey, 0, 0x20019u, &phkResult) )
  {
    Connection::ReadConfigEntry(v5, phkResult, (char *)v5, "PageTimeout", this + 52, 4u);
    Connection::ReadConfigEntry(v6, phkResult, (char *)v6, "LockRetry", this + 56, 4u);
    Connection::ReadConfigEntry(v7, phkResult, (char *)v7, "MaxBufferSize", this + 60, 4u);
    Connection::ReadConfigEntry(v8, phkResult, (char *)v8, "Threads", this + 64, 4u);
    Connection::ReadConfigEntry(v9, phkResult, (char *)v9, "ExclusiveAsyncDelay", this + 76, 4u);
    Connection::ReadConfigEntry(v10, phkResult, (char *)v10, "SharedAsyncDelay", this + 80, 4u);
    Connection::ReadConfigEntry(v11, phkResult, (char *)v11, "FlushTransactionTimeout", this + 84, 4u);
    Connection::ReadConfigEntry(v12, phkResult, (char *)v12, "MaxLocksPerFile", this + 88, 4u);
    Connection::ReadConfigEntry(v13, phkResult, (char *)v13, "LockDelay", this + 92, 4u);
    Connection::ReadConfigEntry(v14, phkResult, (char *)v14, "RecycleLVs", this + 96, 4u);
    Connection::ReadConfigEntry(v15, phkResult, (char *)v15, "PagesLockedToTableLock", this + 100, 4u);
    Connection::ReadConfigEntry(v16, phkResult, (char *)v16, "RecyclePagesTimeout", this + 104, 4u);
    String1[0] = 0;
    Connection::ReadConfigEntry(v17, phkResult, (char *)v17, "UserCommitSync", (LPBYTE)String1, 5u);
    if ( !__stricmp(String1, "yes") )
      *((_DWORD *)this + 17) = 0;
    if ( !__stricmp(String1, "no") )
      *((_DWORD *)this + 17) = 1;
    String1[0] = 0;
    Connection::ReadConfigEntry(v18, phkResult, (char *)v18, "ImplicitCommitSync", (LPBYTE)String1, 5u);
    if ( !__stricmp(String1, "yes") )
      *((_DWORD *)this + 18) = 0;
    if ( !__stricmp(String1, "no") )
      *((_DWORD *)this + 18) = 1;
    RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x1007467f  mov     edi, edi
0x10074681  push    ebp
0x10074682  mov     ebp, esp
0x10074684  sub     esp, 10h
0x10074687  mov     eax, ___security_cookie
0x1007468c  xor     eax, ebp
0x1007468e  mov     [ebp+var_4], eax
0x10074691  mov     edx, [ebp+hKey]
0x10074694  mov     eax, [ebp+lpSubKey]
0x10074697  push    ebx
0x10074698  push    esi
0x10074699  mov     esi, ecx
0x1007469b  xor     ebx, ebx
0x1007469d  lea     ecx, [ebp+phkResult]
0x100746a0  test    edx, edx
0x100746a2  push    ecx; phkResult
0x100746a3  push    20019h; samDesired
0x100746a8  push    ebx; ulOptions
0x100746a9  push    eax; lpSubKey
0x100746aa  mov     eax, 80000002h
0x100746af  cmovnz  eax, edx
0x100746b2  push    eax; hKey
0x100746b3  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x100746b9  test    eax, eax
0x100746bb  jnz     loc_10074849
0x100746c1  push    edi
0x100746c2  push    4
0x100746c4  pop     edi
0x100746c5  push    edi; unsigned int
0x100746c6  lea     eax, [esi+34h]
0x100746c9  push    eax; lpData
0x100746ca  push    offset aPagetimeout; "PageTimeout"
0x100746cf  push    ecx; char *
0x100746d0  push    [ebp+phkResult]; hKey
0x100746d3  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100746d8  push    edi; unsigned int
0x100746d9  lea     eax, [esi+38h]
0x100746dc  push    eax; lpData
0x100746dd  push    offset aLockretry; "LockRetry"
0x100746e2  push    ecx; char *
0x100746e3  push    [ebp+phkResult]; hKey
0x100746e6  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100746eb  push    edi; unsigned int
0x100746ec  lea     eax, [esi+3Ch]
0x100746ef  push    eax; lpData
0x100746f0  push    offset aMaxbuffersize; "MaxBufferSize"
0x100746f5  push    ecx; char *
0x100746f6  push    [ebp+phkResult]; hKey
0x100746f9  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100746fe  push    edi; unsigned int
0x100746ff  lea     eax, [esi+40h]
0x10074702  push    eax; lpData
0x10074703  push    offset aThreads; "Threads"
0x10074708  push    ecx; char *
0x10074709  push    [ebp+phkResult]; hKey
0x1007470c  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074711  push    edi; unsigned int
0x10074712  lea     eax, [esi+4Ch]
0x10074715  push    eax; lpData
0x10074716  push    offset aExclusiveasync; "ExclusiveAsyncDelay"
0x1007471b  push    ecx; char *
0x1007471c  push    [ebp+phkResult]; hKey
0x1007471f  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074724  push    edi; unsigned int
0x10074725  lea     eax, [esi+50h]
0x10074728  push    eax; lpData
0x10074729  push    offset aSharedasyncdel; "SharedAsyncDelay"
0x1007472e  push    ecx; char *
0x1007472f  push    [ebp+phkResult]; hKey
0x10074732  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074737  push    edi; unsigned int
0x10074738  lea     eax, [esi+54h]
0x1007473b  push    eax; lpData
0x1007473c  push    offset aFlushtransacti; "FlushTransactionTimeout"
0x10074741  push    ecx; char *
0x10074742  push    [ebp+phkResult]; hKey
0x10074745  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x1007474a  push    edi; unsigned int
0x1007474b  lea     eax, [esi+58h]
0x1007474e  push    eax; lpData
0x1007474f  push    offset aMaxlocksperfil; "MaxLocksPerFile"
0x10074754  push    ecx; char *
0x10074755  push    [ebp+phkResult]; hKey
0x10074758  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x1007475d  push    edi; unsigned int
0x1007475e  lea     eax, [esi+5Ch]
0x10074761  push    eax; lpData
0x10074762  push    offset aLockdelay; "LockDelay"
0x10074767  push    ecx; char *
0x10074768  push    [ebp+phkResult]; hKey
0x1007476b  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074770  push    edi; unsigned int
0x10074771  lea     eax, [esi+60h]
0x10074774  push    eax; lpData
0x10074775  push    offset aRecyclelvs; "RecycleLVs"
0x1007477a  push    ecx; char *
0x1007477b  push    [ebp+phkResult]; hKey
0x1007477e  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074783  push    edi; unsigned int
0x10074784  lea     eax, [esi+64h]
0x10074787  push    eax; lpData
0x10074788  push    offset aPageslockedtot; "PagesLockedToTableLock"
0x1007478d  push    ecx; char *
0x1007478e  push    [ebp+phkResult]; hKey
0x10074791  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074796  push    edi; unsigned int
0x10074797  lea     eax, [esi+68h]
0x1007479a  push    eax; lpData
0x1007479b  push    offset aRecyclepagesti; "RecyclePagesTimeout"
0x100747a0  push    ecx; char *
0x100747a1  push    [ebp+phkResult]; hKey
0x100747a4  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100747a9  push    5; unsigned int
0x100747ab  lea     eax, [ebp+String1]
0x100747ae  mov     [ebp+String1], bl
0x100747b1  push    eax; lpData
0x100747b2  push    offset ValueName; "UserCommitSync"
0x100747b7  push    ecx; char *
0x100747b8  push    [ebp+phkResult]; hKey
0x100747bb  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100747c0  lea     eax, [ebp+String1]
0x100747c3  push    offset String2; "yes"
0x100747c8  push    eax; String1
0x100747c9  call    ds:__imp___stricmp
0x100747cf  pop     ecx
0x100747d0  pop     ecx
0x100747d1  test    eax, eax
0x100747d3  jnz     short loc_100747D8
0x100747d5  mov     [esi+44h], ebx
0x100747d8  lea     eax, [ebp+String1]
0x100747db  push    offset aNo; "no"
0x100747e0  push    eax; String1
0x100747e1  call    ds:__imp___stricmp
0x100747e7  pop     ecx
0x100747e8  pop     ecx; this
0x100747e9  test    eax, eax
0x100747eb  jnz     short loc_100747F4
0x100747ed  mov     dword ptr [esi+44h], 1
0x100747f4  push    5; unsigned int
0x100747f6  lea     eax, [ebp+String1]
0x100747f9  mov     [ebp+String1], bl
0x100747fc  push    eax; lpData
0x100747fd  push    offset aImplicitcommit; "ImplicitCommitSync"
0x10074802  push    ecx; char *
0x10074803  push    [ebp+phkResult]; hKey
0x10074806  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x1007480b  lea     eax, [ebp+String1]
0x1007480e  push    offset String2; "yes"
0x10074813  push    eax; String1
0x10074814  call    ds:__imp___stricmp
0x1007481a  pop     ecx
0x1007481b  pop     ecx
0x1007481c  pop     edi
0x1007481d  test    eax, eax
0x1007481f  jnz     short loc_10074824
0x10074821  mov     [esi+48h], ebx
0x10074824  lea     eax, [ebp+String1]
0x10074827  push    offset aNo; "no"
0x1007482c  push    eax; String1
0x1007482d  call    ds:__imp___stricmp
0x10074833  pop     ecx
0x10074834  pop     ecx
0x10074835  test    eax, eax
0x10074837  jnz     short loc_10074840
0x10074839  mov     dword ptr [esi+48h], 1
0x10074840  push    [ebp+phkResult]; hKey
0x10074843  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10074849  mov     ecx, [ebp+var_4]
0x1007484c  pop     esi
0x1007484d  xor     ecx, ebp; StackCookie
0x1007484f  pop     ebx
0x10074850  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10074855  leave
0x10074856  retn    8
```
