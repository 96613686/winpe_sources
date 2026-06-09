# Connection::ReadConfigTree(HKEY__ *,char const *)

- ea: `0x10018990`
- end: `0x10018b6f`
- name: `?ReadConfigTree@Connection@@AAEXPAUHKEY__@@PBD@Z`
- size: `479`
- prototype: `void __thiscall(Connection *__hidden this, HKEY hKey, LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100277d0`

## callees

- `0x10018900`
- `0x10018990`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018aa4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018ae2`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018afb`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018b2f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018b48`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018aa4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018ae2`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018afb`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018b2f`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x10018b48`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x10018ab5`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x10018ab5`

## string_xrefs

- `0x100189ed`: `Threads`
- `0x10018acd`: `UserCommitSync`
- `0x10018b1a`: `ImplicitCommitSync`
- `0x10018a72`: `CompatibilityMode`

## pseudocode

```c
void __thiscall Connection::ReadConfigTree(Connection *this, HKEY hKey, LPCSTR lpSubKey)
{
  Connection *v4; // ecx
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
  int v16; // eax
  Connection *v17; // ecx
  char String1[80]; // [esp+Ch] [ebp-54h] BYREF

  Connection::ReadConfigEntry(this, hKey, lpSubKey, "PageTimeout", (unsigned int)this, (LPBYTE)this + 52, 4u);
  Connection::ReadConfigEntry(v4, hKey, lpSubKey, "LockRetry", (unsigned int)v4, (LPBYTE)this + 56, 4u);
  Connection::ReadConfigEntry(v5, hKey, lpSubKey, "MaxBufferSize", (unsigned int)v5, (LPBYTE)this + 60, 4u);
  Connection::ReadConfigEntry(v6, hKey, lpSubKey, "Threads", (unsigned int)v6, (LPBYTE)this + 64, 4u);
  Connection::ReadConfigEntry(v7, hKey, lpSubKey, "ExclusiveAsyncDelay", (unsigned int)v7, (LPBYTE)this + 76, 4u);
  Connection::ReadConfigEntry(v8, hKey, lpSubKey, "SharedAsyncDelay", (unsigned int)v8, (LPBYTE)this + 80, 4u);
  Connection::ReadConfigEntry(v9, hKey, lpSubKey, "FlushTransactionTimeout", (unsigned int)v9, (LPBYTE)this + 84, 4u);
  Connection::ReadConfigEntry(v10, hKey, lpSubKey, "MaxLocksPerFile", (unsigned int)v10, (LPBYTE)this + 88, 4u);
  Connection::ReadConfigEntry(v11, hKey, lpSubKey, "LockDelay", (unsigned int)v11, (LPBYTE)this + 92, 4u);
  Connection::ReadConfigEntry(v12, hKey, lpSubKey, "RecycleLVs", (unsigned int)v12, (LPBYTE)this + 96, 4u);
  Connection::ReadConfigEntry(v13, hKey, lpSubKey, "CompatibilityMode", (unsigned int)v13, (LPBYTE)this + 104, 4u);
  String1[0] = 0;
  Connection::ReadConfigEntry(v14, hKey, lpSubKey, "ForceCp", (unsigned int)v14, (LPBYTE)String1, 0x50u);
  if ( String1[0] )
  {
    v16 = __stricmp(String1, "ANSI");
    if ( v16 )
      LOWORD(v16) = __o_atoi(String1);
    *((_WORD *)this + 50) = v16;
  }
  String1[0] = 0;
  Connection::ReadConfigEntry(v15, hKey, lpSubKey, "UserCommitSync", (unsigned int)v15, (LPBYTE)String1, 0x50u);
  if ( !__stricmp(String1, "yes") )
    *((_DWORD *)this + 17) = 0;
  if ( !__stricmp(String1, "no") )
    *((_DWORD *)this + 17) = 1;
  String1[0] = 0;
  Connection::ReadConfigEntry(v17, hKey, lpSubKey, "ImplicitCommitSync", (unsigned int)v17, (LPBYTE)String1, 0x50u);
  if ( !__stricmp(String1, "yes") )
    *((_DWORD *)this + 18) = 0;
  if ( !__stricmp(String1, "no") )
    *((_DWORD *)this + 18) = 1;
}

```

## disassembly

```asm
0x10018990  mov     edi, edi
0x10018992  push    ebp
0x10018993  mov     ebp, esp
0x10018995  sub     esp, 54h
0x10018998  mov     eax, ___security_cookie
0x1001899d  xor     eax, ebp
0x1001899f  mov     [ebp+var_4], eax
0x100189a2  push    ebx
0x100189a3  mov     ebx, [ebp+lpSubKey]
0x100189a6  push    esi
0x100189a7  push    edi
0x100189a8  mov     edi, [ebp+hKey]
0x100189ab  mov     esi, ecx
0x100189ad  push    4; unsigned int
0x100189af  lea     eax, [esi+34h]
0x100189b2  push    eax; lpData
0x100189b3  push    ecx; unsigned int
0x100189b4  push    offset aPagetimeout; "PageTimeout"
0x100189b9  push    ebx; lpSubKey
0x100189ba  push    edi; hKey
0x100189bb  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x100189c0  push    4; unsigned int
0x100189c2  lea     eax, [esi+38h]
0x100189c5  push    eax; lpData
0x100189c6  push    ecx; unsigned int
0x100189c7  push    offset aLockretry; "LockRetry"
0x100189cc  push    ebx; lpSubKey
0x100189cd  push    edi; hKey
0x100189ce  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x100189d3  push    4; unsigned int
0x100189d5  lea     eax, [esi+3Ch]
0x100189d8  push    eax; lpData
0x100189d9  push    ecx; unsigned int
0x100189da  push    offset aMaxbuffersize; "MaxBufferSize"
0x100189df  push    ebx; lpSubKey
0x100189e0  push    edi; hKey
0x100189e1  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x100189e6  push    4; unsigned int
0x100189e8  lea     eax, [esi+40h]
0x100189eb  push    eax; lpData
0x100189ec  push    ecx; unsigned int
0x100189ed  push    offset aThreads; "Threads"
0x100189f2  push    ebx; lpSubKey
0x100189f3  push    edi; hKey
0x100189f4  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x100189f9  push    4; unsigned int
0x100189fb  lea     eax, [esi+4Ch]
0x100189fe  push    eax; lpData
0x100189ff  push    ecx; unsigned int
0x10018a00  push    offset aExclusiveasync; "ExclusiveAsyncDelay"
0x10018a05  push    ebx; lpSubKey
0x10018a06  push    edi; hKey
0x10018a07  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a0c  push    4; unsigned int
0x10018a0e  lea     eax, [esi+50h]
0x10018a11  push    eax; lpData
0x10018a12  push    ecx; unsigned int
0x10018a13  push    offset aSharedasyncdel; "SharedAsyncDelay"
0x10018a18  push    ebx; lpSubKey
0x10018a19  push    edi; hKey
0x10018a1a  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a1f  push    4; unsigned int
0x10018a21  lea     eax, [esi+54h]
0x10018a24  push    eax; lpData
0x10018a25  push    ecx; unsigned int
0x10018a26  push    offset aFlushtransacti; "FlushTransactionTimeout"
0x10018a2b  push    ebx; lpSubKey
0x10018a2c  push    edi; hKey
0x10018a2d  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a32  push    4; unsigned int
0x10018a34  lea     eax, [esi+58h]
0x10018a37  push    eax; lpData
0x10018a38  push    ecx; unsigned int
0x10018a39  push    offset aMaxlocksperfil; "MaxLocksPerFile"
0x10018a3e  push    ebx; lpSubKey
0x10018a3f  push    edi; hKey
0x10018a40  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a45  push    4; unsigned int
0x10018a47  lea     eax, [esi+5Ch]
0x10018a4a  push    eax; lpData
0x10018a4b  push    ecx; unsigned int
0x10018a4c  push    offset aLockdelay; "LockDelay"
0x10018a51  push    ebx; lpSubKey
0x10018a52  push    edi; hKey
0x10018a53  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a58  push    4; unsigned int
0x10018a5a  lea     eax, [esi+60h]
0x10018a5d  push    eax; lpData
0x10018a5e  push    ecx; unsigned int
0x10018a5f  push    offset aRecyclelvs; "RecycleLVs"
0x10018a64  push    ebx; lpSubKey
0x10018a65  push    edi; hKey
0x10018a66  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a6b  push    4; unsigned int
0x10018a6d  lea     eax, [esi+68h]
0x10018a70  push    eax; lpData
0x10018a71  push    ecx; unsigned int
0x10018a72  push    offset aCompatibilitym; "CompatibilityMode"
0x10018a77  push    ebx; lpSubKey
0x10018a78  push    edi; hKey
0x10018a79  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a7e  push    50h ; 'P'; unsigned int
0x10018a80  lea     eax, [ebp+String1]
0x10018a83  mov     [ebp+String1], 0
0x10018a87  push    eax; lpData
0x10018a88  push    ecx; unsigned int
0x10018a89  push    offset aForcecp; "ForceCp"
0x10018a8e  push    ebx; lpSubKey
0x10018a8f  push    edi; hKey
0x10018a90  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018a95  cmp     [ebp+String1], 0
0x10018a99  jz      short loc_10018AC2
0x10018a9b  lea     eax, [ebp+String1]
0x10018a9e  push    offset String2; "ANSI"
0x10018aa3  push    eax; String1
0x10018aa4  call    ds:__imp___stricmp
0x10018aaa  add     esp, 8
0x10018aad  test    eax, eax
0x10018aaf  jz      short loc_10018ABE
0x10018ab1  lea     eax, [ebp+String1]
0x10018ab4  push    eax
0x10018ab5  call    ds:__imp___o_atoi
0x10018abb  add     esp, 4
0x10018abe  mov     [esi+64h], ax
0x10018ac2  push    50h ; 'P'; unsigned int
0x10018ac4  lea     eax, [ebp+String1]
0x10018ac7  mov     [ebp+String1], 0
0x10018acb  push    eax; lpData
0x10018acc  push    ecx; unsigned int
0x10018acd  push    offset aUsercommitsync; "UserCommitSync"
0x10018ad2  push    ebx; lpSubKey
0x10018ad3  push    edi; hKey
0x10018ad4  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018ad9  lea     eax, [ebp+String1]
0x10018adc  push    offset aYes; "yes"
0x10018ae1  push    eax; String1
0x10018ae2  call    ds:__imp___stricmp
0x10018ae8  add     esp, 8
0x10018aeb  test    eax, eax
0x10018aed  jnz     short loc_10018AF2
0x10018aef  mov     [esi+44h], eax
0x10018af2  lea     eax, [ebp+String1]
0x10018af5  push    offset aNo; "no"
0x10018afa  push    eax; String1
0x10018afb  call    ds:__imp___stricmp
0x10018b01  add     esp, 8
0x10018b04  test    eax, eax
0x10018b06  jnz     short loc_10018B0F
0x10018b08  mov     dword ptr [esi+44h], 1
0x10018b0f  push    50h ; 'P'; unsigned int
0x10018b11  lea     eax, [ebp+String1]
0x10018b14  mov     [ebp+String1], 0
0x10018b18  push    eax; lpData
0x10018b19  push    ecx; unsigned int
0x10018b1a  push    offset aImplicitcommit; "ImplicitCommitSync"
0x10018b1f  push    ebx; lpSubKey
0x10018b20  push    edi; hKey
0x10018b21  call    ?ReadConfigEntry@Connection@@AAEJPAUHKEY__@@PBD1KPAEI@Z; Connection::ReadConfigEntry(HKEY__ *,char const *,char const *,ulong,uchar *,uint)
0x10018b26  lea     eax, [ebp+String1]
0x10018b29  push    offset aYes; "yes"
0x10018b2e  push    eax; String1
0x10018b2f  call    ds:__imp___stricmp
0x10018b35  add     esp, 8
0x10018b38  test    eax, eax
0x10018b3a  jnz     short loc_10018B3F
0x10018b3c  mov     [esi+48h], eax
0x10018b3f  lea     eax, [ebp+String1]
0x10018b42  push    offset aNo; "no"
0x10018b47  push    eax; String1
0x10018b48  call    ds:__imp___stricmp
0x10018b4e  add     esp, 8
0x10018b51  test    eax, eax
0x10018b53  jnz     short loc_10018B5C
0x10018b55  mov     dword ptr [esi+48h], 1
0x10018b5c  mov     ecx, [ebp+var_4]
0x10018b5f  pop     edi
0x10018b60  pop     esi
0x10018b61  xor     ecx, ebp; StackCookie
0x10018b63  pop     ebx
0x10018b64  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10018b69  mov     esp, ebp
0x10018b6b  pop     ebp
0x10018b6c  retn    8
```
