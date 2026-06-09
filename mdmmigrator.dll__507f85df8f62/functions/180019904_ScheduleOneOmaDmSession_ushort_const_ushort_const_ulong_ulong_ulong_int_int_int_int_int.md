# ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)

- ea: `0x180019904`
- end: `0x180019ab5`
- name: `?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z`
- size: `433`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, int, int, unsigned int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c054`
- `0x18001c61c`

## callees

- `0x1800022e0`
- `0x180006c98`
- `0x180012a70`
- `0x180019904`
- `0x180019abc`
- `0x180019e58`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019a90`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019a90`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001994f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001994f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019987`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019a26`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019987`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180019a26`

## string_xrefs

- `0x180019a0e`: `21CoCreateTaskScheduler`

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSession(
        unsigned __int16 *a1,
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
  __int64 v16; // rdx
  __int64 v17; // rcx
  HRESULT v18; // eax
  unsigned int v19; // ebx
  int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h]
  HRESULT Data; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v27[264]; // [rsp+70h] [rbp-90h] BYREF

  Data = 0;
  if ( !a4 )
    return 0;
  Data = CoInitializeEx(0, 0);
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
    Data = StringCchPrintfW(v27, 0x104u, v15, a1);
    if ( Data >= 0 )
    {
      v26 = 0;
      Data = CoCreateTaskScheduler(v17, v16, &v26);
      if ( Data >= 0 )
      {
        if ( a6 )
          v18 = ScheduleOneOmaDmSessionMaintenanceCycle(a2, a1, lpData, cbData);
        else
          v18 = ScheduleOneOmaDmSessionClient(a2, a1, a5, cbData, v27, v22, v23, v24, a9);
        Data = v18;
      }
      else
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"21CoCreateTaskScheduler", 4u, &Data, 4u);
      }
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v19 = Data;
    CoUninitialize();
    return v19;
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"CoInitializeEx", 4u, &Data, 4u);
    return (unsigned int)Data;
  }
}

```

## disassembly

```asm
0x180019904  push    rbp
0x180019906  push    rbx
0x180019907  push    rsi
0x180019908  push    rdi
0x180019909  push    r14
0x18001990b  lea     rbp, [rsp-190h]
0x180019913  sub     rsp, 290h
0x18001991a  mov     rax, cs:__security_cookie
0x180019921  xor     rax, rsp
0x180019924  mov     [rbp+1B0h+var_30], rax
0x18001992b  mov     [rsp+2B0h+Data], 0
0x180019933  mov     r14d, r9d
0x180019936  mov     edi, r8d
0x180019939  mov     rsi, rdx
0x18001993c  mov     rbx, rcx
0x18001993f  test    r9d, r9d
0x180019942  jnz     short loc_18001994B
0x180019944  xor     eax, eax
0x180019946  jmp     loc_180019A98
0x18001994b  xor     edx, edx; dwCoInit
0x18001994d  xor     ecx, ecx; pvReserved
0x18001994f  call    cs:__imp_CoInitializeEx
0x180019955  mov     [rsp+2B0h+Data], eax
0x180019959  test    eax, eax
0x18001995b  jns     short loc_180019996
0x18001995d  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180019964  lea     rax, [rsp+2B0h+Data]
0x180019969  mov     r9d, 4; dwType
0x18001996f  lea     r8, aCoinitializeex; "CoInitializeEx"
0x180019976  mov     [rsp+2B0h+cbData], r9d; cbData
0x18001997b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019982  mov     [rsp+2B0h+lpData], rax; lpData
0x180019987  call    cs:__imp_RegSetKeyValueW
0x18001998d  mov     eax, [rsp+2B0h+Data]
0x180019991  jmp     loc_180019A98
0x180019996  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x18001999b  mov     r9, rbx
0x18001999e  mov     edx, 104h; unsigned __int64
0x1800199a3  test    edi, edi
0x1800199a5  jz      short loc_1800199B7
0x1800199a7  lea     rax, aOSCBu; "/o \"%s\" /c /bu"
0x1800199ae  lea     r8, aOSC; "/o \"%s\" /c"
0x1800199b5  jmp     short loc_1800199C5
0x1800199b7  lea     rax, aOSCMu; "/o \"%s\" /c /mu"
0x1800199be  lea     r8, aOSCB; "/o \"%s\" /c /b"
0x1800199c5  cmp     [rbp+1B0h+arg_48], 0
0x1800199cc  cmovnz  r8, rax; unsigned __int16 *
0x1800199d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800199d5  mov     [rsp+2B0h+Data], eax
0x1800199d9  test    eax, eax
0x1800199db  js      loc_180019A8C
0x1800199e1  lea     r8, [rsp+2B0h+var_248]
0x1800199e6  mov     [rsp+2B0h+var_248], 0
0x1800199ef  call    CoCreateTaskScheduler
0x1800199f4  mov     [rsp+2B0h+Data], eax
0x1800199f8  test    eax, eax
0x1800199fa  jns     short loc_180019A2E
0x1800199fc  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180019a03  lea     rax, [rsp+2B0h+Data]
0x180019a08  mov     r9d, 4; dwType
0x180019a0e  lea     r8, a21cocreatetask; "21CoCreateTaskScheduler"
0x180019a15  mov     [rsp+2B0h+cbData], r9d; cbData
0x180019a1a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019a21  mov     [rsp+2B0h+lpData], rax; lpData
0x180019a26  call    cs:__imp_RegSetKeyValueW
0x180019a2c  jmp     short loc_180019A76
0x180019a2e  cmp     [rbp+1B0h+arg_28], 0
0x180019a35  mov     rdx, rbx; unsigned __int16 *
0x180019a38  mov     rcx, rsi; unsigned __int16 *
0x180019a3b  jz      short loc_180019A49
0x180019a3d  lea     r9, [rsp+2B0h+var_240]
0x180019a42  call    ScheduleOneOmaDmSessionMaintenanceCycle
0x180019a47  jmp     short loc_180019A72
0x180019a49  mov     eax, [rbp+1B0h+arg_40]
0x180019a4f  mov     r9d, r14d
0x180019a52  mov     [rsp+2B0h+var_260], eax; int
0x180019a56  mov     r8d, edi
0x180019a59  lea     rax, [rsp+2B0h+var_240]
0x180019a5e  mov     [rsp+2B0h+var_280], rax; unsigned __int16 *
0x180019a63  mov     eax, [rbp+1B0h+arg_20]
0x180019a69  mov     dword ptr [rsp+2B0h+lpData], eax; int
0x180019a6d  call    ScheduleOneOmaDmSessionClient
0x180019a72  mov     [rsp+2B0h+Data], eax
0x180019a76  mov     rcx, [rsp+2B0h+var_248]
0x180019a7b  test    rcx, rcx
0x180019a7e  jz      short loc_180019A8C
0x180019a80  mov     rax, [rcx]
0x180019a83  mov     rax, [rax+10h]
0x180019a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a8c  mov     ebx, [rsp+2B0h+Data]
0x180019a90  call    cs:__imp_CoUninitialize
0x180019a96  mov     eax, ebx
0x180019a98  mov     rcx, [rbp+1B0h+var_30]
0x180019a9f  xor     rcx, rsp; StackCookie
0x180019aa2  call    __security_check_cookie
0x180019aa7  add     rsp, 290h
0x180019aae  pop     r14
0x180019ab0  pop     rdi
0x180019ab1  pop     rsi
0x180019ab2  pop     rbx
0x180019ab3  pop     rbp
0x180019ab4  retn
```
