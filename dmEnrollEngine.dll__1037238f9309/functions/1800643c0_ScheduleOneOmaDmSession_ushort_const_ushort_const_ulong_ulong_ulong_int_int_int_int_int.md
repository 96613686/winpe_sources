# ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)

- ea: `0x1800643c0`
- end: `0x180064570`
- name: `?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z`
- size: `432`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001208c`
- `0x180012370`

## callees

- `0x1800067a0`
- `0x18001788c`
- `0x18002e1a0`
- `0x18003708c`
- `0x180060974`
- `0x1800643c0`
- `0x180064578`
- `0x180064938`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006454b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006454b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006444b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800644e6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006444b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800644e6`

## string_xrefs

- `0x1800644ce`: `21CoCreateTaskScheduler`

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
      ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v27);
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
0x1800643c0  push    rbp
0x1800643c2  push    rbx
0x1800643c3  push    rsi
0x1800643c4  push    rdi
0x1800643c5  push    r14
0x1800643c7  lea     rbp, [rsp-190h]
0x1800643cf  sub     rsp, 290h
0x1800643d6  mov     rax, cs:__security_cookie
0x1800643dd  xor     rax, rsp
0x1800643e0  mov     [rbp+1B0h+var_30], rax
0x1800643e7  mov     [rsp+2B0h+Data], 0
0x1800643ef  mov     r14d, r9d
0x1800643f2  mov     [rsp+2B0h+var_24C], 0
0x1800643fa  mov     edi, r8d
0x1800643fd  mov     rsi, rdx
0x180064400  mov     rbx, rcx
0x180064403  test    r9d, r9d
0x180064406  jnz     short loc_18006440F
0x180064408  xor     eax, eax
0x18006440a  jmp     loc_180064553
0x18006440f  lea     rcx, [rsp+2B0h+var_24C]; this
0x180064414  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x180064419  mov     [rsp+2B0h+Data], eax
0x18006441d  test    eax, eax
0x18006441f  jns     short loc_180064456
0x180064421  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180064428  lea     rax, [rsp+2B0h+Data]
0x18006442d  mov     r9d, 4; dwType
0x180064433  lea     r8, aCoinitializeex; "CoInitializeEx"
0x18006443a  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x18006443f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180064446  mov     [rsp+2B0h+lpData], rax; lpData
0x18006444b  call    cs:__imp_RegSetKeyValueW
0x180064451  jmp     loc_180064540
0x180064456  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x18006445b  mov     r9, rbx
0x18006445e  mov     edx, 104h; unsigned __int64
0x180064463  test    edi, edi
0x180064465  jz      short loc_180064477
0x180064467  lea     rax, aOSCBu; "/o \"%s\" /c /bu"
0x18006446e  lea     r8, aOSC; "/o \"%s\" /c"
0x180064475  jmp     short loc_180064485
0x180064477  lea     rax, aOSCMu; "/o \"%s\" /c /mu"
0x18006447e  lea     r8, aOSCB; "/o \"%s\" /c /b"
0x180064485  cmp     [rbp+1B0h+arg_48], 0
0x18006448c  cmovnz  r8, rax; unsigned __int16 *
0x180064490  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064495  mov     [rsp+2B0h+Data], eax
0x180064499  test    eax, eax
0x18006449b  js      loc_180064540
0x1800644a1  lea     r8, [rsp+2B0h+var_248]
0x1800644a6  mov     [rsp+2B0h+var_248], 0
0x1800644af  call    CoCreateTaskScheduler
0x1800644b4  mov     [rsp+2B0h+Data], eax
0x1800644b8  test    eax, eax
0x1800644ba  jns     short loc_1800644EE
0x1800644bc  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800644c3  lea     rax, [rsp+2B0h+Data]
0x1800644c8  mov     r9d, 4; dwType
0x1800644ce  lea     r8, a21cocreatetask; "21CoCreateTaskScheduler"
0x1800644d5  mov     dword ptr [rsp+2B0h+cbData], r9d; cbData
0x1800644da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800644e1  mov     [rsp+2B0h+lpData], rax; lpData
0x1800644e6  call    cs:__imp_RegSetKeyValueW
0x1800644ec  jmp     short loc_180064536
0x1800644ee  cmp     [rbp+1B0h+arg_28], 0
0x1800644f5  mov     rdx, rbx
0x1800644f8  mov     rcx, rsi; unsigned __int16 *
0x1800644fb  jz      short loc_180064509
0x1800644fd  lea     r9, [rsp+2B0h+var_240]
0x180064502  call    ScheduleOneOmaDmSessionMaintenanceCycle
0x180064507  jmp     short loc_180064532
0x180064509  mov     eax, [rbp+1B0h+arg_40]
0x18006450f  mov     r9d, r14d
0x180064512  mov     [rsp+2B0h+var_260], eax; int
0x180064516  mov     r8d, edi
0x180064519  lea     rax, [rsp+2B0h+var_240]
0x18006451e  mov     [rsp+2B0h+var_280], rax; __int64
0x180064523  mov     eax, [rbp+1B0h+arg_20]
0x180064529  mov     dword ptr [rsp+2B0h+lpData], eax; int
0x18006452d  call    ScheduleOneOmaDmSessionClient
0x180064532  mov     [rsp+2B0h+Data], eax
0x180064536  lea     rcx, [rsp+2B0h+var_248]
0x18006453b  call    ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
0x180064540  cmp     [rsp+2B0h+var_24C], 0
0x180064545  mov     ebx, [rsp+2B0h+Data]
0x180064549  jz      short loc_180064551
0x18006454b  call    cs:__imp_CoUninitialize
0x180064551  mov     eax, ebx
0x180064553  mov     rcx, [rbp+1B0h+var_30]
0x18006455a  xor     rcx, rsp; StackCookie
0x18006455d  call    __security_check_cookie
0x180064562  add     rsp, 290h
0x180064569  pop     r14
0x18006456b  pop     rdi
0x18006456c  pop     rsi
0x18006456d  pop     rbx
0x18006456e  pop     rbp
0x18006456f  retn
```
