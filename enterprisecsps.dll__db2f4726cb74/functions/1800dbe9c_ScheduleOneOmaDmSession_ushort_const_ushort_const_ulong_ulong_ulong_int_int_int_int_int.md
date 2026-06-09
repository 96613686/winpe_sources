# ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)

- ea: `0x1800dbe9c`
- end: `0x1800dc05f`
- name: `?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z`
- size: `451`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800de394`
- `0x1800de864`

## callees

- `0x180008de0`
- `0x18000db4c`
- `0x18001a4fc`
- `0x1800d7d5c`
- `0x1800d7e58`
- `0x1800dbe9c`
- `0x1800dc068`
- `0x1800dc828`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dbf27`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dbfc8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dbf27`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800dbfc8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800dc033`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800dc033`

## string_xrefs

- `0x1800dbfb0`: `21CoCreateTaskScheduler`

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSession(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  const wchar_t *v14; // rax
  const unsigned __int16 *v15; // r8
  char *v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  LPCVOID lpData; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h]
  int Data; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  LPVOID v27; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v28[264]; // [rsp+70h] [rbp-90h] BYREF

  Data = 0;
  v26 = 0;
  if ( !a4 )
    return 0;
  Data = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v26, (unsigned int)a2);
  if ( Data >= 0 )
  {
    if ( a3 )
    {
      v14 = L"/o \"%s\" /c /bu";
      v15 = L"/o \"%s\" /c";
    }
    else
    {
      v14 = L"/o \"%s\" /c /mu";
      v15 = L"/o \"%s\" /c /b";
    }
    if ( a10 )
      v15 = v14;
    Data = StringCchPrintfW(v28, 0x104u, v15, a1);
    if ( Data >= 0 )
    {
      v27 = 0;
      Data = CoCreateTaskScheduler(v17, v16, &v27);
      if ( Data >= 0 )
      {
        if ( a6 )
          v18 = ScheduleOneOmaDmSessionMaintenanceCycle(a2, (__int64)lpData, cbData);
        else
          v18 = ScheduleOneOmaDmSessionClient(a2, a5, cbData, (__int64)v28, v22, v23, v24, a9);
        Data = v18;
      }
      else
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"21CoCreateTaskScheduler", 4u, &Data, 4u);
      }
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v27);
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"CoInitializeEx", 4u, &Data, 4u);
  }
  v19 = Data;
  if ( v26 )
    CoUninitialize();
  return v19;
}

```

## disassembly

```asm
0x1800dbe9c  push    rbp
0x1800dbe9e  push    rbx
0x1800dbe9f  push    rsi
0x1800dbea0  push    rdi
0x1800dbea1  push    r14
0x1800dbea3  lea     rbp, [rsp-190h]
0x1800dbeab  sub     rsp, 290h
0x1800dbeb2  mov     rax, cs:__security_cookie
0x1800dbeb9  xor     rax, rsp
0x1800dbebc  mov     [rbp+1B0h+var_30], rax
0x1800dbec3  mov     [rsp+2B0h+Data], 0
0x1800dbecb  mov     r14d, r9d
0x1800dbece  mov     [rsp+2B0h+var_24C], 0
0x1800dbed6  mov     edi, r8d
0x1800dbed9  mov     rsi, rdx
0x1800dbedc  mov     rbx, rcx
0x1800dbedf  test    r9d, r9d
0x1800dbee2  jnz     short loc_1800DBEEB
0x1800dbee4  xor     eax, eax
0x1800dbee6  jmp     loc_1800DC041
0x1800dbeeb  lea     rcx, [rsp+2B0h+var_24C]; this
0x1800dbef0  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800dbef5  mov     [rsp+2B0h+Data], eax
0x1800dbef9  test    eax, eax
0x1800dbefb  jns     short loc_1800DBF38
0x1800dbefd  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800dbf04  lea     rax, [rsp+2B0h+Data]
0x1800dbf09  mov     r9d, 4; dwType
0x1800dbf0f  lea     r8, aCoinitializeex_0; "CoInitializeEx"
0x1800dbf16  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x1800dbf1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dbf22  mov     [rsp+2B0h+lpData], rax; lpData
0x1800dbf27  call    cs:__imp_RegSetKeyValueW
0x1800dbf2e  nop     dword ptr [rax+rax+00h]
0x1800dbf33  jmp     loc_1800DC028
0x1800dbf38  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x1800dbf3d  mov     r9, rbx
0x1800dbf40  mov     edx, 104h; unsigned __int64
0x1800dbf45  test    edi, edi
0x1800dbf47  jz      short loc_1800DBF59
0x1800dbf49  lea     rax, aOSCBu; "/o \"%s\" /c /bu"
0x1800dbf50  lea     r8, aOSC; "/o \"%s\" /c"
0x1800dbf57  jmp     short loc_1800DBF67
0x1800dbf59  lea     rax, aOSCMu; "/o \"%s\" /c /mu"
0x1800dbf60  lea     r8, aOSCB; "/o \"%s\" /c /b"
0x1800dbf67  cmp     [rbp+1B0h+arg_48], 0
0x1800dbf6e  cmovnz  r8, rax; unsigned __int16 *
0x1800dbf72  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800dbf77  mov     [rsp+2B0h+Data], eax
0x1800dbf7b  test    eax, eax
0x1800dbf7d  js      loc_1800DC028
0x1800dbf83  lea     r8, [rsp+2B0h+var_248]
0x1800dbf88  mov     [rsp+2B0h+var_248], 0
0x1800dbf91  call    CoCreateTaskScheduler
0x1800dbf96  mov     [rsp+2B0h+Data], eax
0x1800dbf9a  test    eax, eax
0x1800dbf9c  jns     short loc_1800DBFD6
0x1800dbf9e  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800dbfa5  lea     rax, [rsp+2B0h+Data]
0x1800dbfaa  mov     r9d, 4; dwType
0x1800dbfb0  lea     r8, a21cocreatetask; "21CoCreateTaskScheduler"
0x1800dbfb7  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x1800dbfbc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dbfc3  mov     [rsp+2B0h+lpData], rax; lpData
0x1800dbfc8  call    cs:__imp_RegSetKeyValueW
0x1800dbfcf  nop     dword ptr [rax+rax+00h]
0x1800dbfd4  jmp     short loc_1800DC01E
0x1800dbfd6  cmp     [rbp+1B0h+arg_28], 0
0x1800dbfdd  mov     rdx, rbx
0x1800dbfe0  mov     rcx, rsi; unsigned __int16 *
0x1800dbfe3  jz      short loc_1800DBFF1
0x1800dbfe5  lea     r9, [rsp+2B0h+var_240]
0x1800dbfea  call    ScheduleOneOmaDmSessionMaintenanceCycle
0x1800dbfef  jmp     short loc_1800DC01A
0x1800dbff1  mov     eax, [rbp+1B0h+arg_40]
0x1800dbff7  mov     r9d, r14d
0x1800dbffa  mov     [rsp+2B0h+var_260], eax; int
0x1800dbffe  mov     r8d, edi
0x1800dc001  lea     rax, [rsp+2B0h+var_240]
0x1800dc006  mov     [rsp+2B0h+var_280], rax; __int64
0x1800dc00b  mov     eax, [rbp+1B0h+arg_20]
0x1800dc011  mov     dword ptr [rsp+2B0h+lpData], eax; int
0x1800dc015  call    ScheduleOneOmaDmSessionClient
0x1800dc01a  mov     [rsp+2B0h+Data], eax
0x1800dc01e  lea     rcx, [rsp+2B0h+var_248]
0x1800dc023  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800dc028  cmp     [rsp+2B0h+var_24C], 0
0x1800dc02d  mov     ebx, [rsp+2B0h+Data]
0x1800dc031  jz      short loc_1800DC03F
0x1800dc033  call    cs:__imp_CoUninitialize
0x1800dc03a  nop     dword ptr [rax+rax+00h]
0x1800dc03f  mov     eax, ebx
0x1800dc041  mov     rcx, [rbp+1B0h+var_30]
0x1800dc048  xor     rcx, rsp; StackCookie
0x1800dc04b  call    __security_check_cookie
0x1800dc050  add     rsp, 290h
0x1800dc057  pop     r14
0x1800dc059  pop     rdi
0x1800dc05a  pop     rsi
0x1800dc05b  pop     rbx
0x1800dc05c  pop     rbp
0x1800dc05d  retn
```
