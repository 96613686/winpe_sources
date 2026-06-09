# NtService::Connect(void)

- ea: `0x1402120c0`
- end: `0x140212296`
- name: `?Connect@NtService@@QEAAPEAVFrsStatus@@XZ`
- size: `470`
- prototype: `struct FrsStatus *__fastcall(NtService *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1401f9e68`
- `0x1401fdadc`
- `0x1401fdf10`
- `0x1401fe65c`
- `0x140200460`

## callees

- `0x14001c31c`
- `0x1401b9494`
- `0x1402120c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14021216f`
- `KERNEL32!GetLastError` at `0x1402121ea`
- `KERNEL32!GetLastError` at `0x14021216f`
- `KERNEL32!GetLastError` at `0x1402121ea`
- `KERNEL32!GetCurrentThreadId` at `0x140212161`
- `KERNEL32!GetCurrentThreadId` at `0x1402121dc`
- `KERNEL32!GetCurrentThreadId` at `0x14021223e`
- `KERNEL32!GetCurrentThreadId` at `0x140212161`
- `KERNEL32!GetCurrentThreadId` at `0x1402121dc`
- `KERNEL32!GetCurrentThreadId` at `0x14021223e`
- `ADVAPI32!OpenSCManagerW` at `0x140212139`
- `ADVAPI32!OpenSCManagerW` at `0x140212139`
- `ADVAPI32!OpenServiceW` at `0x1402121bf`
- `ADVAPI32!OpenServiceW` at `0x1402121bf`
- `ADVAPI32!CloseServiceHandle` at `0x14021222d`
- `ADVAPI32!CloseServiceHandle` at `0x14021222d`

## string_xrefs

- `0x140212148`: `NtService::Connect`
- `0x140212152`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x1402120f7`: `NtService::Connect`
- `0x14021211d`: `Connect to service %?`

## pseudocode

```c
struct FrsStatus *__fastcall NtService::Connect(NtService *this)
{
  __int64 v1; // rdi
  unsigned int *v3; // rbx
  SC_HANDLE v4; // rsi
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v7; // rcx
  DWORD v8; // ebx
  DWORD v9; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  __int64 v12; // rcx
  const wchar_t *v14; // [rsp+50h] [rbp-38h] BYREF
  int v15; // [rsp+58h] [rbp-30h]
  int v16; // [rsp+5Ch] [rbp-2Ch]
  const wchar_t *v17; // [rsp+60h] [rbp-28h]

  v1 = 0;
  v3 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v14 = L"NtService::Connect";
    v15 = 57;
    v16 = 4;
    v17 = L"SRVC";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(
      &v14,
      L"Connect to service %?",
      (char *)this + 8);
  }
  v4 = OpenSCManagerW(0, 0, 1u);
  if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || (CurrentThreadId = GetCurrentThreadId(),
        LastError = GetLastError(),
        (v3 = (unsigned int *)FrsStatusList::PushNewError(
                                v7,
                                LastError,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                                "NtService::Connect",
                                65,
                                CurrentThreadId,
                                0)) == 0) )
  {
    *(_QWORD *)this = OpenServiceW(v4, (LPCWSTR)(*((_QWORD *)this + 1) + 18LL), 0xF7u);
  }
  if ( ((*(_QWORD *)this + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v8 = GetCurrentThreadId();
    v9 = GetLastError();
    v3 = (unsigned int *)FrsStatusList::PushNewError(
                           v10,
                           v9,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                           "NtService::Connect",
                           85,
                           v8,
                           0);
  }
  if ( v4 != (SC_HANDLE)-1LL )
    CloseServiceHandle(v4);
  if ( v3 )
  {
    v11 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v12,
                                 v3[1],
                                 v3[2],
                                 *v3,
                                 "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                                 "NtService::Connect",
                                 93,
                                 v11,
                                 v3);
  }
  return (struct FrsStatus *)v1;
}

```

## disassembly

```asm
0x1402120c0  mov     r11, rsp
0x1402120c3  mov     [r11+8], rbx
0x1402120c7  mov     [r11+10h], rsi
0x1402120cb  mov     [r11+18h], rdi
0x1402120cf  push    r12
0x1402120d1  push    r14
0x1402120d3  push    r15
0x1402120d5  sub     rsp, 70h
0x1402120d9  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402120e0  xor     edi, edi
0x1402120e2  mov     r14, rcx
0x1402120e5  mov     ebx, edi
0x1402120e7  test    rax, rax
0x1402120ea  jz      short loc_140212131
0x1402120ec  cmp     [rax+40h], edi
0x1402120ef  jz      short loc_140212131
0x1402120f1  cmp     dword ptr [rax+38h], 4
0x1402120f5  jl      short loc_140212131
0x1402120f7  lea     rax, aNtserviceConne; "NtService::Connect"
0x1402120fe  mov     [r11-38h], rax
0x140212102  lea     r8, [rcx+8]
0x140212106  lea     rax, aSrvc; "SRVC"
0x14021210d  mov     [rsp+88h+var_30], 39h ; '9'
0x140212115  mov     [rsp+88h+var_2C], 4
0x14021211d  lea     rdx, aConnectToServi; "Connect to service %?"
0x140212124  lea     rcx, [r11-38h]
0x140212128  mov     [r11-28h], rax
0x14021212c  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x140212131  xor     edx, edx; lpDatabaseName
0x140212133  xor     ecx, ecx; lpMachineName
0x140212135  lea     r8d, [rdx+1]; dwDesiredAccess
0x140212139  call    cs:__imp_OpenSCManagerW
0x140212140  nop     dword ptr [rax+rax+00h]
0x140212145  mov     rsi, rax
0x140212148  lea     r15, aNtserviceConne_0; "NtService::Connect"
0x14021214f  inc     rax
0x140212152  lea     r12, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212159  test    rax, 0FFFFFFFFFFFFFFFEh
0x14021215f  jnz     short loc_1402121AE
0x140212161  call    cs:__imp_GetCurrentThreadId
0x140212168  nop     dword ptr [rax+rax+00h]
0x14021216d  mov     ebx, eax
0x14021216f  call    cs:__imp_GetLastError
0x140212176  nop     dword ptr [rax+rax+00h]
0x14021217b  mov     [rsp+88h+var_48], rdi
0x140212180  mov     r9d, 1
0x140212186  mov     [rsp+88h+var_50], ebx
0x14021218a  xor     r8d, r8d
0x14021218d  mov     [rsp+88h+var_58], 41h ; 'A'
0x140212195  mov     edx, eax
0x140212197  mov     [rsp+88h+var_60], r15
0x14021219c  mov     [rsp+88h+var_68], r12
0x1402121a1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1402121a6  mov     rbx, rax
0x1402121a9  test    rax, rax
0x1402121ac  jnz     short loc_1402121CE
0x1402121ae  mov     rdx, [r14+8]
0x1402121b2  mov     r8d, 0F7h; dwDesiredAccess
0x1402121b8  add     rdx, 12h; lpServiceName
0x1402121bc  mov     rcx, rsi; hSCManager
0x1402121bf  call    cs:__imp_OpenServiceW
0x1402121c6  nop     dword ptr [rax+rax+00h]
0x1402121cb  mov     [r14], rax
0x1402121ce  mov     rax, [r14]
0x1402121d1  inc     rax
0x1402121d4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1402121da  jnz     short loc_140212224
0x1402121dc  call    cs:__imp_GetCurrentThreadId
0x1402121e3  nop     dword ptr [rax+rax+00h]
0x1402121e8  mov     ebx, eax
0x1402121ea  call    cs:__imp_GetLastError
0x1402121f1  nop     dword ptr [rax+rax+00h]
0x1402121f6  mov     [rsp+88h+var_48], rdi
0x1402121fb  mov     r9d, 1
0x140212201  mov     [rsp+88h+var_50], ebx
0x140212205  xor     r8d, r8d
0x140212208  mov     [rsp+88h+var_58], 55h ; 'U'
0x140212210  mov     edx, eax
0x140212212  mov     [rsp+88h+var_60], r15
0x140212217  mov     [rsp+88h+var_68], r12
0x14021221c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212221  mov     rbx, rax
0x140212224  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140212228  jz      short loc_140212239
0x14021222a  mov     rcx, rsi; hSCObject
0x14021222d  call    cs:__imp_CloseServiceHandle
0x140212234  nop     dword ptr [rax+rax+00h]
0x140212239  test    rbx, rbx
0x14021223c  jz      short loc_140212277
0x14021223e  call    cs:__imp_GetCurrentThreadId
0x140212245  nop     dword ptr [rax+rax+00h]
0x14021224a  mov     r9d, [rbx]
0x14021224d  mov     r8d, [rbx+8]
0x140212251  mov     edx, [rbx+4]
0x140212254  mov     [rsp+88h+var_48], rbx
0x140212259  mov     [rsp+88h+var_50], eax
0x14021225d  mov     [rsp+88h+var_58], 5Dh ; ']'
0x140212265  mov     [rsp+88h+var_60], r15
0x14021226a  mov     [rsp+88h+var_68], r12
0x14021226f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212274  mov     rdi, rax
0x140212277  lea     r11, [rsp+88h+var_18]
0x14021227c  mov     rax, rdi
0x14021227f  mov     rbx, [r11+20h]
0x140212283  mov     rsi, [r11+28h]
0x140212287  mov     rdi, [r11+30h]
0x14021228b  mov     rsp, r11
0x14021228e  pop     r15
0x140212290  pop     r14
0x140212292  pop     r12
0x140212294  retn
```
