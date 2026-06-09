# CMsiCustomAction::CMsiCustomAction(void)

- ea: `0x1801a9880`
- end: `0x1801a9a96`
- name: `??0CMsiCustomAction@@QEAA@XZ`
- size: `534`
- prototype: `CMsiCustomAction *__fastcall(CMsiCustomAction *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1801aa4d0`

## callees

- `0x1800a9d48`
- `0x1800b00f4`
- `0x1801a9880`
- `0x1801a9c7c`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1801a998d`
- `ADVAPI32!OpenProcessToken` at `0x1801a998d`
- `KERNEL32!InitializeCriticalSection` at `0x1801a9937`
- `KERNEL32!InitializeCriticalSection` at `0x1801a9944`
- `KERNEL32!InitializeCriticalSection` at `0x1801a9951`
- `KERNEL32!InitializeCriticalSection` at `0x1801a995e`
- `KERNEL32!InitializeCriticalSection` at `0x1801a9937`
- `KERNEL32!InitializeCriticalSection` at `0x1801a9944`
- `KERNEL32!InitializeCriticalSection` at `0x1801a9951`
- `KERNEL32!InitializeCriticalSection` at `0x1801a995e`
- `KERNEL32!CloseHandle` at `0x1801a99c8`
- `KERNEL32!CloseHandle` at `0x1801a99c8`
- `KERNEL32!GetCurrentThreadId` at `0x1801a992a`
- `KERNEL32!GetCurrentThreadId` at `0x1801a992a`
- `KERNEL32!GetCurrentProcess` at `0x1801a997c`
- `KERNEL32!GetCurrentProcess` at `0x1801a997c`
- `KERNEL32!CreateEventW` at `0x1801a991b`
- `KERNEL32!CreateEventW` at `0x1801a991b`

## pseudocode

```c
CMsiCustomAction *__fastcall CMsiCustomAction::CMsiCustomAction(CMsiCustomAction *this)
{
  HANDLE CurrentProcess; // rax
  int v3; // eax
  unsigned int i; // edx
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int j; // edx
  __int64 v8; // rax
  __int64 v9; // rcx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  IMsiCustomActionLocalConfig::IMsiCustomActionLocalConfig(this);
  *((_DWORD *)this + 3) = 1;
  *((_BYTE *)this + 8) = 0;
  *(_QWORD *)this = &CMsiCustomAction::`vftable';
  *((_BYTE *)this + 16) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_BYTE *)this + 104) = 0;
  *((_DWORD *)this + 27) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 15) = -1;
  *((_QWORD *)this + 22) = (char *)this + 192;
  *((_DWORD *)this + 46) = 4;
  *((_QWORD *)this + 41) = (char *)this + 344;
  *((_DWORD *)this + 84) = 10;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 10) = CreateEventW(0, 1, 0, 0);
  InitializeMsiMalloc();
  *((_DWORD *)this + 5) = GetCurrentThreadId();
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 1);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
  *((_BYTE *)this + 24) = 0;
  *((_DWORD *)this + 25) = g_fWoW;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( g_fWoW )
      v3 = 2 * IsLocalSystemToken(TokenHandle) + 1;
    else
      v3 = 2 * IsLocalSystemToken(TokenHandle);
    *((_DWORD *)this + 25) = v3;
    CloseHandle(TokenHandle);
  }
  for ( i = 0; i < *((_DWORD *)this + 46); *(_QWORD *)(*((_QWORD *)this + 22) + 8 * v6 + 16) = 0 )
  {
    v5 = i++;
    v6 = 3 * v5;
    *(_DWORD *)(*((_QWORD *)this + 22) + 8 * v6) = 0;
    *(_QWORD *)(*((_QWORD *)this + 22) + 8 * v6 + 8) = -1;
  }
  for ( j = 0; j < *((_DWORD *)this + 84); *(_QWORD *)(*((_QWORD *)this + 41) + 8 * v9 + 32) = 0 )
  {
    v8 = j++;
    v9 = 5 * v8;
    *(_QWORD *)(*((_QWORD *)this + 41) + 8 * v9) = 0;
    *(_QWORD *)(*((_QWORD *)this + 41) + 8 * v9 + 8) = 0;
    *(_QWORD *)(*((_QWORD *)this + 41) + 8 * v9 + 16) = 0;
    *(_DWORD *)(*((_QWORD *)this + 41) + 8 * v9 + 24) = 0;
  }
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 98) = 0;
  if ( *((_QWORD *)this + 10) )
    *((_BYTE *)this + 8) = 1;
  return this;
}

```

## disassembly

```asm
0x1801a9880  mov     [rsp+arg_8], rbx
0x1801a9885  push    rdi
0x1801a9886  sub     rsp, 20h
0x1801a988a  mov     rbx, rcx
0x1801a988d  call    ??0IMsiCustomActionLocalConfig@@QEAA@XZ; IMsiCustomActionLocalConfig::IMsiCustomActionLocalConfig(void)
0x1801a9892  xor     edi, edi
0x1801a9894  mov     dword ptr [rbx+0Ch], 1
0x1801a989b  mov     [rbx+8], dil
0x1801a989f  lea     rcx, ??_7CMsiCustomAction@@6B@; const CMsiCustomAction::`vftable'
0x1801a98a6  mov     [rbx], rcx
0x1801a98a9  lea     rax, [rbx+0C0h]
0x1801a98b0  mov     [rbx+10h], dil
0x1801a98b4  xor     r9d, r9d; lpName
0x1801a98b7  mov     [rbx+50h], rdi
0x1801a98bb  lea     edx, [rdi+1]; bManualReset
0x1801a98be  mov     [rbx+58h], rdi
0x1801a98c2  xor     r8d, r8d; bInitialState
0x1801a98c5  mov     [rbx+60h], edi
0x1801a98c8  xor     ecx, ecx; lpEventAttributes
0x1801a98ca  mov     [rbx+68h], dil
0x1801a98ce  mov     [rbx+6Ch], edi
0x1801a98d1  mov     [rbx+70h], rdi
0x1801a98d5  mov     [rbx+80h], rdi
0x1801a98dc  mov     qword ptr [rbx+78h], 0FFFFFFFFFFFFFFFFh
0x1801a98e4  mov     [rbx+0B0h], rax
0x1801a98eb  lea     rax, [rbx+158h]
0x1801a98f2  mov     dword ptr [rbx+0B8h], 4
0x1801a98fc  mov     [rbx+148h], rax
0x1801a9903  mov     dword ptr [rbx+150h], 0Ah
0x1801a990d  mov     [rbx+2E8h], rdi
0x1801a9914  mov     [rbx+2F0h], rdi
0x1801a991b  call    cs:__imp_CreateEventW
0x1801a9921  mov     [rbx+50h], rax
0x1801a9925  call    ?InitializeMsiMalloc@@YAXXZ; InitializeMsiMalloc(void)
0x1801a992a  call    cs:__imp_GetCurrentThreadId
0x1801a9930  lea     rcx, [rbx+28h]; lpCriticalSection
0x1801a9934  mov     [rbx+14h], eax
0x1801a9937  call    cs:__imp_InitializeCriticalSection
0x1801a993d  lea     rcx, [rbx+88h]; lpCriticalSection
0x1801a9944  call    cs:__imp_InitializeCriticalSection
0x1801a994a  lea     rcx, [rbx+120h]; lpCriticalSection
0x1801a9951  call    cs:__imp_InitializeCriticalSection
0x1801a9957  lea     rcx, [rbx+318h]; lpCriticalSection
0x1801a995e  call    cs:__imp_InitializeCriticalSection
0x1801a9964  mov     [rbx+18h], dil
0x1801a9968  mov     eax, edi
0x1801a996a  cmp     cs:?g_fWoW@@3_NA, dil; bool g_fWoW
0x1801a9971  setnz   al
0x1801a9974  mov     [rbx+64h], eax
0x1801a9977  mov     [rsp+28h+TokenHandle], rdi
0x1801a997c  call    cs:__imp_GetCurrentProcess
0x1801a9982  mov     rcx, rax; ProcessHandle
0x1801a9985  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1801a998a  lea     edx, [rdi+8]; DesiredAccess
0x1801a998d  call    cs:__imp_OpenProcessToken
0x1801a9993  test    eax, eax
0x1801a9995  jz      short loc_1801A99CE
0x1801a9997  cmp     cs:?g_fWoW@@3_NA, dil; bool g_fWoW
0x1801a999e  mov     rcx, [rsp+28h+TokenHandle]; void *
0x1801a99a3  jz      short loc_1801A99B6
0x1801a99a5  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1801a99aa  movzx   eax, al
0x1801a99ad  lea     eax, ds:1[rax*2]
0x1801a99b4  jmp     short loc_1801A99C0
0x1801a99b6  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1801a99bb  movzx   eax, al
0x1801a99be  add     eax, eax
0x1801a99c0  mov     [rbx+64h], eax
0x1801a99c3  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1801a99c8  call    cs:__imp_CloseHandle
0x1801a99ce  mov     edx, edi
0x1801a99d0  cmp     [rbx+0B8h], edi
0x1801a99d6  jbe     short loc_1801A9A0E
0x1801a99d8  mov     eax, edx
0x1801a99da  inc     edx
0x1801a99dc  lea     rcx, [rax+rax*2]
0x1801a99e0  mov     rax, [rbx+0B0h]
0x1801a99e7  mov     [rax+rcx*8], edi
0x1801a99ea  mov     rax, [rbx+0B0h]
0x1801a99f1  mov     qword ptr [rax+rcx*8+8], 0FFFFFFFFFFFFFFFFh
0x1801a99fa  mov     rax, [rbx+0B0h]
0x1801a9a01  mov     [rax+rcx*8+10h], rdi
0x1801a9a06  cmp     edx, [rbx+0B8h]
0x1801a9a0c  jb      short loc_1801A99D8
0x1801a9a0e  mov     edx, edi
0x1801a9a10  cmp     [rbx+150h], edi
0x1801a9a16  jbe     short loc_1801A9A62
0x1801a9a18  mov     eax, edx
0x1801a9a1a  inc     edx
0x1801a9a1c  lea     rcx, [rax+rax*4]
0x1801a9a20  mov     rax, [rbx+148h]
0x1801a9a27  mov     [rax+rcx*8], rdi
0x1801a9a2b  mov     rax, [rbx+148h]
0x1801a9a32  mov     [rax+rcx*8+8], rdi
0x1801a9a37  mov     rax, [rbx+148h]
0x1801a9a3e  mov     [rax+rcx*8+10h], rdi
0x1801a9a43  mov     rax, [rbx+148h]
0x1801a9a4a  mov     [rax+rcx*8+18h], edi
0x1801a9a4e  mov     rax, [rbx+148h]
0x1801a9a55  mov     [rax+rcx*8+20h], rdi
0x1801a9a5a  cmp     edx, [rbx+150h]
0x1801a9a60  jb      short loc_1801A9A18
0x1801a9a62  mov     [rbx+2F8h], rdi
0x1801a9a69  mov     [rbx+300h], rdi
0x1801a9a70  mov     [rbx+308h], rdi
0x1801a9a77  mov     [rbx+310h], rdi
0x1801a9a7e  cmp     [rbx+50h], rdi
0x1801a9a82  jz      short loc_1801A9A88
0x1801a9a84  mov     byte ptr [rbx+8], 1
0x1801a9a88  mov     rax, rbx
0x1801a9a8b  mov     rbx, [rsp+28h+arg_8]
0x1801a9a90  add     rsp, 20h
0x1801a9a94  pop     rdi
0x1801a9a95  retn
```
