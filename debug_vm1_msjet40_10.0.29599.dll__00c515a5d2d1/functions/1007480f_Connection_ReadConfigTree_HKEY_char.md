# Connection::ReadConfigTree(HKEY__ *,char *)

- ea: `0x1007480f`
- end: `0x100749e9`
- name: `?ReadConfigTree@Connection@@AAEXPAUHKEY__@@PAD@Z`
- size: `474`
- prototype: `void __thiscall(Connection *__hidden this, HKEY hKey, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10027a90`

## callees

- `0x100747ba`
- `0x1007480f`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10074959`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10074971`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100749a4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100749bd`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10074959`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10074971`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100749a4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x100749bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10074843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x10074843`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100749d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100749d3`

## string_xrefs

- `0x10074893`: `Threads`
- `0x10074942`: `UserCommitSync`
- `0x1007498d`: `ImplicitCommitSync`

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
0x1007480f  mov     edi, edi
0x10074811  push    ebp
0x10074812  mov     ebp, esp
0x10074814  sub     esp, 10h
0x10074817  mov     eax, ___security_cookie
0x1007481c  xor     eax, ebp
0x1007481e  mov     [ebp+var_4], eax
0x10074821  mov     edx, [ebp+hKey]
0x10074824  mov     eax, [ebp+lpSubKey]
0x10074827  push    ebx
0x10074828  push    esi
0x10074829  mov     esi, ecx
0x1007482b  xor     ebx, ebx
0x1007482d  lea     ecx, [ebp+phkResult]
0x10074830  test    edx, edx
0x10074832  push    ecx; phkResult
0x10074833  push    20019h; samDesired
0x10074838  push    ebx; ulOptions
0x10074839  push    eax; lpSubKey
0x1007483a  mov     eax, 80000002h
0x1007483f  cmovnz  eax, edx
0x10074842  push    eax; hKey
0x10074843  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x10074849  test    eax, eax
0x1007484b  jnz     loc_100749D9
0x10074851  push    edi
0x10074852  push    4
0x10074854  pop     edi
0x10074855  push    edi; unsigned int
0x10074856  lea     eax, [esi+34h]
0x10074859  push    eax; lpData
0x1007485a  push    offset aPagetimeout; "PageTimeout"
0x1007485f  push    ecx; char *
0x10074860  push    [ebp+phkResult]; hKey
0x10074863  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074868  push    edi; unsigned int
0x10074869  lea     eax, [esi+38h]
0x1007486c  push    eax; lpData
0x1007486d  push    offset aLockretry; "LockRetry"
0x10074872  push    ecx; char *
0x10074873  push    [ebp+phkResult]; hKey
0x10074876  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x1007487b  push    edi; unsigned int
0x1007487c  lea     eax, [esi+3Ch]
0x1007487f  push    eax; lpData
0x10074880  push    offset aMaxbuffersize; "MaxBufferSize"
0x10074885  push    ecx; char *
0x10074886  push    [ebp+phkResult]; hKey
0x10074889  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x1007488e  push    edi; unsigned int
0x1007488f  lea     eax, [esi+40h]
0x10074892  push    eax; lpData
0x10074893  push    offset aThreads; "Threads"
0x10074898  push    ecx; char *
0x10074899  push    [ebp+phkResult]; hKey
0x1007489c  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100748a1  push    edi; unsigned int
0x100748a2  lea     eax, [esi+4Ch]
0x100748a5  push    eax; lpData
0x100748a6  push    offset aExclusiveasync; "ExclusiveAsyncDelay"
0x100748ab  push    ecx; char *
0x100748ac  push    [ebp+phkResult]; hKey
0x100748af  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100748b4  push    edi; unsigned int
0x100748b5  lea     eax, [esi+50h]
0x100748b8  push    eax; lpData
0x100748b9  push    offset aSharedasyncdel; "SharedAsyncDelay"
0x100748be  push    ecx; char *
0x100748bf  push    [ebp+phkResult]; hKey
0x100748c2  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100748c7  push    edi; unsigned int
0x100748c8  lea     eax, [esi+54h]
0x100748cb  push    eax; lpData
0x100748cc  push    offset aFlushtransacti; "FlushTransactionTimeout"
0x100748d1  push    ecx; char *
0x100748d2  push    [ebp+phkResult]; hKey
0x100748d5  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100748da  push    edi; unsigned int
0x100748db  lea     eax, [esi+58h]
0x100748de  push    eax; lpData
0x100748df  push    offset aMaxlocksperfil; "MaxLocksPerFile"
0x100748e4  push    ecx; char *
0x100748e5  push    [ebp+phkResult]; hKey
0x100748e8  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x100748ed  push    edi; unsigned int
0x100748ee  lea     eax, [esi+5Ch]
0x100748f1  push    eax; lpData
0x100748f2  push    offset aLockdelay; "LockDelay"
0x100748f7  push    ecx; char *
0x100748f8  push    [ebp+phkResult]; hKey
0x100748fb  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074900  push    edi; unsigned int
0x10074901  lea     eax, [esi+60h]
0x10074904  push    eax; lpData
0x10074905  push    offset aRecyclelvs; "RecycleLVs"
0x1007490a  push    ecx; char *
0x1007490b  push    [ebp+phkResult]; hKey
0x1007490e  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074913  push    edi; unsigned int
0x10074914  lea     eax, [esi+64h]
0x10074917  push    eax; lpData
0x10074918  push    offset aPageslockedtot; "PagesLockedToTableLock"
0x1007491d  push    ecx; char *
0x1007491e  push    [ebp+phkResult]; hKey
0x10074921  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074926  push    edi; unsigned int
0x10074927  lea     eax, [esi+68h]
0x1007492a  push    eax; lpData
0x1007492b  push    offset aRecyclepagesti; "RecyclePagesTimeout"
0x10074930  push    ecx; char *
0x10074931  push    [ebp+phkResult]; hKey
0x10074934  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074939  push    5; unsigned int
0x1007493b  lea     eax, [ebp+String1]
0x1007493e  mov     [ebp+String1], bl
0x10074941  push    eax; lpData
0x10074942  push    offset ValueName; "UserCommitSync"
0x10074947  push    ecx; char *
0x10074948  push    [ebp+phkResult]; hKey
0x1007494b  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x10074950  lea     eax, [ebp+String1]
0x10074953  push    offset String2; "yes"
0x10074958  push    eax; String1
0x10074959  call    ds:__imp___stricmp
0x1007495f  pop     ecx
0x10074960  pop     ecx
0x10074961  test    eax, eax
0x10074963  jnz     short loc_10074968
0x10074965  mov     [esi+44h], ebx
0x10074968  lea     eax, [ebp+String1]
0x1007496b  push    offset aNo; "no"
0x10074970  push    eax; String1
0x10074971  call    ds:__imp___stricmp
0x10074977  pop     ecx
0x10074978  pop     ecx; this
0x10074979  test    eax, eax
0x1007497b  jnz     short loc_10074984
0x1007497d  mov     dword ptr [esi+44h], 1
0x10074984  push    5; unsigned int
0x10074986  lea     eax, [ebp+String1]
0x10074989  mov     [ebp+String1], bl
0x1007498c  push    eax; lpData
0x1007498d  push    offset aImplicitcommit; "ImplicitCommitSync"
0x10074992  push    ecx; char *
0x10074993  push    [ebp+phkResult]; hKey
0x10074996  call    ?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)
0x1007499b  lea     eax, [ebp+String1]
0x1007499e  push    offset String2; "yes"
0x100749a3  push    eax; String1
0x100749a4  call    ds:__imp___stricmp
0x100749aa  pop     ecx
0x100749ab  pop     ecx
0x100749ac  pop     edi
0x100749ad  test    eax, eax
0x100749af  jnz     short loc_100749B4
0x100749b1  mov     [esi+48h], ebx
0x100749b4  lea     eax, [ebp+String1]
0x100749b7  push    offset aNo; "no"
0x100749bc  push    eax; String1
0x100749bd  call    ds:__imp___stricmp
0x100749c3  pop     ecx
0x100749c4  pop     ecx
0x100749c5  test    eax, eax
0x100749c7  jnz     short loc_100749D0
0x100749c9  mov     dword ptr [esi+48h], 1
0x100749d0  push    [ebp+phkResult]; hKey
0x100749d3  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100749d9  mov     ecx, [ebp+var_4]
0x100749dc  pop     esi
0x100749dd  xor     ecx, ebp; StackCookie
0x100749df  pop     ebx
0x100749e0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100749e5  leave
0x100749e6  retn    8
```
