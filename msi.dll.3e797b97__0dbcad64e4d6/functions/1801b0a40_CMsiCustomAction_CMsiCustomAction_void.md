# CMsiCustomAction::CMsiCustomAction(void)

- ea: `0x1801b0a40`
- end: `0x1801b0c8d`
- name: `??0CMsiCustomAction@@QEAA@XZ`
- size: `589`
- prototype: `CMsiCustomAction *__fastcall(CMsiCustomAction *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1801b1780`

## callees

- `0x180045ba4`
- `0x1800b9b4c`
- `0x1801b0a40`
- `0x1801b0e84`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1801b0b77`
- `ADVAPI32!OpenProcessToken` at `0x1801b0b77`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b03`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b16`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b29`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b3c`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b03`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b16`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b29`
- `KERNEL32!InitializeCriticalSection` at `0x1801b0b3c`
- `KERNEL32!CloseHandle` at `0x1801b0bb8`
- `KERNEL32!CloseHandle` at `0x1801b0bb8`
- `KERNEL32!GetCurrentThreadId` at `0x1801b0af0`
- `KERNEL32!GetCurrentThreadId` at `0x1801b0af0`
- `KERNEL32!GetCurrentProcess` at `0x1801b0b60`
- `KERNEL32!GetCurrentProcess` at `0x1801b0b60`
- `KERNEL32!CreateEventW` at `0x1801b0adb`
- `KERNEL32!CreateEventW` at `0x1801b0adb`

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
0x1801b0a40  mov     [rsp+arg_8], rbx
0x1801b0a45  push    rdi
0x1801b0a46  sub     rsp, 20h
0x1801b0a4a  mov     rbx, rcx
0x1801b0a4d  call    ??0IMsiCustomActionLocalConfig@@QEAA@XZ; IMsiCustomActionLocalConfig::IMsiCustomActionLocalConfig(void)
0x1801b0a52  xor     edi, edi
0x1801b0a54  mov     dword ptr [rbx+0Ch], 1
0x1801b0a5b  mov     [rbx+8], dil
0x1801b0a5f  lea     rcx, ??_7CMsiCustomAction@@6B@; const CMsiCustomAction::`vftable'
0x1801b0a66  mov     [rbx], rcx
0x1801b0a69  lea     rax, [rbx+0C0h]
0x1801b0a70  mov     [rbx+10h], dil
0x1801b0a74  xor     r9d, r9d; lpName
0x1801b0a77  mov     [rbx+50h], rdi
0x1801b0a7b  lea     edx, [rdi+1]; bManualReset
0x1801b0a7e  mov     [rbx+58h], rdi
0x1801b0a82  xor     r8d, r8d; bInitialState
0x1801b0a85  mov     [rbx+60h], edi
0x1801b0a88  xor     ecx, ecx; lpEventAttributes
0x1801b0a8a  mov     [rbx+68h], dil
0x1801b0a8e  mov     [rbx+6Ch], edi
0x1801b0a91  mov     [rbx+70h], rdi
0x1801b0a95  mov     [rbx+80h], rdi
0x1801b0a9c  mov     qword ptr [rbx+78h], 0FFFFFFFFFFFFFFFFh
0x1801b0aa4  mov     [rbx+0B0h], rax
0x1801b0aab  lea     rax, [rbx+158h]
0x1801b0ab2  mov     dword ptr [rbx+0B8h], 4
0x1801b0abc  mov     [rbx+148h], rax
0x1801b0ac3  mov     dword ptr [rbx+150h], 0Ah
0x1801b0acd  mov     [rbx+2E8h], rdi
0x1801b0ad4  mov     [rbx+2F0h], rdi
0x1801b0adb  call    cs:__imp_CreateEventW
0x1801b0ae2  nop     dword ptr [rax+rax+00h]
0x1801b0ae7  mov     [rbx+50h], rax
0x1801b0aeb  call    ?InitializeMsiMalloc@@YAXXZ; InitializeMsiMalloc(void)
0x1801b0af0  call    cs:__imp_GetCurrentThreadId
0x1801b0af7  nop     dword ptr [rax+rax+00h]
0x1801b0afc  lea     rcx, [rbx+28h]; lpCriticalSection
0x1801b0b00  mov     [rbx+14h], eax
0x1801b0b03  call    cs:__imp_InitializeCriticalSection
0x1801b0b0a  nop     dword ptr [rax+rax+00h]
0x1801b0b0f  lea     rcx, [rbx+88h]; lpCriticalSection
0x1801b0b16  call    cs:__imp_InitializeCriticalSection
0x1801b0b1d  nop     dword ptr [rax+rax+00h]
0x1801b0b22  lea     rcx, [rbx+120h]; lpCriticalSection
0x1801b0b29  call    cs:__imp_InitializeCriticalSection
0x1801b0b30  nop     dword ptr [rax+rax+00h]
0x1801b0b35  lea     rcx, [rbx+318h]; lpCriticalSection
0x1801b0b3c  call    cs:__imp_InitializeCriticalSection
0x1801b0b43  nop     dword ptr [rax+rax+00h]
0x1801b0b48  mov     [rbx+18h], dil
0x1801b0b4c  mov     eax, edi
0x1801b0b4e  cmp     cs:?g_fWoW@@3_NA, dil; bool g_fWoW
0x1801b0b55  setnz   al
0x1801b0b58  mov     [rbx+64h], eax
0x1801b0b5b  mov     [rsp+28h+TokenHandle], rdi
0x1801b0b60  call    cs:__imp_GetCurrentProcess
0x1801b0b67  nop     dword ptr [rax+rax+00h]
0x1801b0b6c  mov     rcx, rax; ProcessHandle
0x1801b0b6f  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1801b0b74  lea     edx, [rdi+8]; DesiredAccess
0x1801b0b77  call    cs:__imp_OpenProcessToken
0x1801b0b7e  nop     dword ptr [rax+rax+00h]
0x1801b0b83  test    eax, eax
0x1801b0b85  jz      short loc_1801B0BC4
0x1801b0b87  cmp     cs:?g_fWoW@@3_NA, dil; bool g_fWoW
0x1801b0b8e  mov     rcx, [rsp+28h+TokenHandle]; void *
0x1801b0b93  jz      short loc_1801B0BA6
0x1801b0b95  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1801b0b9a  movzx   eax, al
0x1801b0b9d  lea     eax, ds:1[rax*2]
0x1801b0ba4  jmp     short loc_1801B0BB0
0x1801b0ba6  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1801b0bab  movzx   eax, al
0x1801b0bae  add     eax, eax
0x1801b0bb0  mov     [rbx+64h], eax
0x1801b0bb3  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1801b0bb8  call    cs:__imp_CloseHandle
0x1801b0bbf  nop     dword ptr [rax+rax+00h]
0x1801b0bc4  mov     edx, edi
0x1801b0bc6  cmp     [rbx+0B8h], edi
0x1801b0bcc  jbe     short loc_1801B0C04
0x1801b0bce  mov     eax, edx
0x1801b0bd0  inc     edx
0x1801b0bd2  lea     rcx, [rax+rax*2]
0x1801b0bd6  mov     rax, [rbx+0B0h]
0x1801b0bdd  mov     [rax+rcx*8], edi
0x1801b0be0  mov     rax, [rbx+0B0h]
0x1801b0be7  mov     qword ptr [rax+rcx*8+8], 0FFFFFFFFFFFFFFFFh
0x1801b0bf0  mov     rax, [rbx+0B0h]
0x1801b0bf7  mov     [rax+rcx*8+10h], rdi
0x1801b0bfc  cmp     edx, [rbx+0B8h]
0x1801b0c02  jb      short loc_1801B0BCE
0x1801b0c04  mov     edx, edi
0x1801b0c06  cmp     [rbx+150h], edi
0x1801b0c0c  jbe     short loc_1801B0C58
0x1801b0c0e  mov     eax, edx
0x1801b0c10  inc     edx
0x1801b0c12  lea     rcx, [rax+rax*4]
0x1801b0c16  mov     rax, [rbx+148h]
0x1801b0c1d  mov     [rax+rcx*8], rdi
0x1801b0c21  mov     rax, [rbx+148h]
0x1801b0c28  mov     [rax+rcx*8+8], rdi
0x1801b0c2d  mov     rax, [rbx+148h]
0x1801b0c34  mov     [rax+rcx*8+10h], rdi
0x1801b0c39  mov     rax, [rbx+148h]
0x1801b0c40  mov     [rax+rcx*8+18h], edi
0x1801b0c44  mov     rax, [rbx+148h]
0x1801b0c4b  mov     [rax+rcx*8+20h], rdi
0x1801b0c50  cmp     edx, [rbx+150h]
0x1801b0c56  jb      short loc_1801B0C0E
0x1801b0c58  mov     [rbx+2F8h], rdi
0x1801b0c5f  mov     [rbx+300h], rdi
0x1801b0c66  mov     [rbx+308h], rdi
0x1801b0c6d  mov     [rbx+310h], rdi
0x1801b0c74  cmp     [rbx+50h], rdi
0x1801b0c78  jz      short loc_1801B0C7E
0x1801b0c7a  mov     byte ptr [rbx+8], 1
0x1801b0c7e  mov     rax, rbx
0x1801b0c81  mov     rbx, [rsp+28h+arg_8]
0x1801b0c86  add     rsp, 20h
0x1801b0c8a  pop     rdi
0x1801b0c8b  retn
```
