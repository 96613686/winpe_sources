# ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)

- ea: `0x180021b88`
- end: `0x180021d39`
- name: `?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z`
- size: `433`
- prototype: `__int64 __usercall@<rax>(OLECHAR *@<rcx>, OLECHAR *psz@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f5fc`
- `0x18001ffb4`

## callees

- `0x1800039f0`
- `0x18000c63c`
- `0x18001d8f4`
- `0x180021b88`
- `0x180021d40`
- `0x180022164`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021d14`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180021d14`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021bd3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180021bd3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021c0b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021caa`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021c0b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021caa`

## string_xrefs

- `0x180021c92`: `21CoCreateTaskScheduler`

## pseudocode

```c
__int64 __fastcall ScheduleOneOmaDmSession(
        OLECHAR *a1,
        OLECHAR *psz,
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
  int v18; // eax
  unsigned int v19; // ebx
  int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h]
  int Data; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v26; // [rsp+68h] [rbp-98h] BYREF
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
          v18 = ScheduleOneOmaDmSessionMaintenanceCycle(psz, a1, lpData, cbData);
        else
          v18 = ScheduleOneOmaDmSessionClient(psz, a1, a5, cbData, v27, v22, v23, v24, a9);
        Data = v18;
      }
      else
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"21CoCreateTaskScheduler", 4u, &Data, 4u);
      }
      if ( v26 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
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
0x180021b88  push    rbp
0x180021b8a  push    rbx
0x180021b8b  push    rsi
0x180021b8c  push    rdi
0x180021b8d  push    r14
0x180021b8f  lea     rbp, [rsp-190h]
0x180021b97  sub     rsp, 290h
0x180021b9e  mov     rax, cs:__security_cookie
0x180021ba5  xor     rax, rsp
0x180021ba8  mov     [rbp+1B0h+var_30], rax
0x180021baf  mov     [rsp+2B0h+Data], 0
0x180021bb7  mov     r14d, r9d
0x180021bba  mov     edi, r8d
0x180021bbd  mov     rsi, rdx
0x180021bc0  mov     rbx, rcx
0x180021bc3  test    r9d, r9d
0x180021bc6  jnz     short loc_180021BCF
0x180021bc8  xor     eax, eax
0x180021bca  jmp     loc_180021D1C
0x180021bcf  xor     edx, edx; dwCoInit
0x180021bd1  xor     ecx, ecx; pvReserved
0x180021bd3  call    cs:__imp_CoInitializeEx
0x180021bd9  mov     [rsp+2B0h+Data], eax
0x180021bdd  test    eax, eax
0x180021bdf  jns     short loc_180021C1A
0x180021be1  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180021be8  lea     rax, [rsp+2B0h+Data]
0x180021bed  mov     r9d, 4; dwType
0x180021bf3  lea     r8, aCoinitializeex; "CoInitializeEx"
0x180021bfa  mov     [rsp+2B0h+cbData], r9d; cbData
0x180021bff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021c06  mov     [rsp+2B0h+lpData], rax; lpData
0x180021c0b  call    cs:__imp_RegSetKeyValueW
0x180021c11  mov     eax, [rsp+2B0h+Data]
0x180021c15  jmp     loc_180021D1C
0x180021c1a  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x180021c1f  mov     r9, rbx
0x180021c22  mov     edx, 104h; unsigned __int64
0x180021c27  test    edi, edi
0x180021c29  jz      short loc_180021C3B
0x180021c2b  lea     rax, aOSCBu; "/o \"%s\" /c /bu"
0x180021c32  lea     r8, aOSC; "/o \"%s\" /c"
0x180021c39  jmp     short loc_180021C49
0x180021c3b  lea     rax, aOSCMu; "/o \"%s\" /c /mu"
0x180021c42  lea     r8, aOSCB; "/o \"%s\" /c /b"
0x180021c49  cmp     [rbp+1B0h+arg_48], 0
0x180021c50  cmovnz  r8, rax; unsigned __int16 *
0x180021c54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021c59  mov     [rsp+2B0h+Data], eax
0x180021c5d  test    eax, eax
0x180021c5f  js      loc_180021D10
0x180021c65  lea     r8, [rsp+2B0h+var_248]
0x180021c6a  mov     [rsp+2B0h+var_248], 0
0x180021c73  call    CoCreateTaskScheduler
0x180021c78  mov     [rsp+2B0h+Data], eax
0x180021c7c  test    eax, eax
0x180021c7e  jns     short loc_180021CB2
0x180021c80  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180021c87  lea     rax, [rsp+2B0h+Data]
0x180021c8c  mov     r9d, 4; dwType
0x180021c92  lea     r8, a21cocreatetask; "21CoCreateTaskScheduler"
0x180021c99  mov     [rsp+2B0h+cbData], r9d; cbData
0x180021c9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021ca5  mov     [rsp+2B0h+lpData], rax; lpData
0x180021caa  call    cs:__imp_RegSetKeyValueW
0x180021cb0  jmp     short loc_180021CFA
0x180021cb2  cmp     [rbp+1B0h+arg_28], 0
0x180021cb9  mov     rdx, rbx; OLECHAR *
0x180021cbc  mov     rcx, rsi; psz
0x180021cbf  jz      short loc_180021CCD
0x180021cc1  lea     r9, [rsp+2B0h+var_240]
0x180021cc6  call    ScheduleOneOmaDmSessionMaintenanceCycle
0x180021ccb  jmp     short loc_180021CF6
0x180021ccd  mov     eax, [rbp+1B0h+arg_40]
0x180021cd3  mov     r9d, r14d
0x180021cd6  mov     [rsp+2B0h+var_260], eax; int
0x180021cda  mov     r8d, edi
0x180021cdd  lea     rax, [rsp+2B0h+var_240]
0x180021ce2  mov     [rsp+2B0h+var_280], rax; unsigned __int16 *
0x180021ce7  mov     eax, [rbp+1B0h+arg_20]
0x180021ced  mov     dword ptr [rsp+2B0h+lpData], eax; int
0x180021cf1  call    ScheduleOneOmaDmSessionClient
0x180021cf6  mov     [rsp+2B0h+Data], eax
0x180021cfa  mov     rcx, [rsp+2B0h+var_248]
0x180021cff  test    rcx, rcx
0x180021d02  jz      short loc_180021D10
0x180021d04  mov     rax, [rcx]
0x180021d07  mov     rax, [rax+10h]
0x180021d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d10  mov     ebx, [rsp+2B0h+Data]
0x180021d14  call    cs:__imp_CoUninitialize
0x180021d1a  mov     eax, ebx
0x180021d1c  mov     rcx, [rbp+1B0h+var_30]
0x180021d23  xor     rcx, rsp; StackCookie
0x180021d26  call    __security_check_cookie
0x180021d2b  add     rsp, 290h
0x180021d32  pop     r14
0x180021d34  pop     rdi
0x180021d35  pop     rsi
0x180021d36  pop     rbx
0x180021d37  pop     rbp
0x180021d38  retn
```
