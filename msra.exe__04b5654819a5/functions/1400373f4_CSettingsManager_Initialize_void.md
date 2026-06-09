# CSettingsManager::Initialize(void)

- ea: `0x1400373f4`
- end: `0x140037476`
- name: `?Initialize@CSettingsManager@@QEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000a858`
- `0x1400194c8`
- `0x140022c68`
- `0x14002981c`
- `0x14002b9d8`

## callees

- `0x1400373f4`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x14003741b`
- `KERNEL32!CreateMutexW` at `0x14003741b`
- `KERNEL32!GetLastError` at `0x14003742f`
- `KERNEL32!GetLastError` at `0x14003742f`
- `KERNEL32!OpenMutexW` at `0x14003744e`
- `KERNEL32!OpenMutexW` at `0x14003744e`

## pseudocode

```c
__int64 __fastcall CSettingsManager::Initialize(CSettingsManager *this)
{
  unsigned int v3; // ebx
  HANDLE MutexW; // rax
  HANDLE v5; // rax

  if ( *(_QWORD *)this )
    return 2147549183LL;
  v3 = 0;
  MutexW = CreateMutexW(0, 0, L"Local\\RemoteAssistanceSettingLockS");
  *(_QWORD *)this = MutexW;
  if ( !MutexW && GetLastError() == 5 )
  {
    v5 = OpenMutexW(0x1F0001u, 0, L"Local\\RemoteAssistanceSettingLockS");
    *(_QWORD *)this = v5;
    if ( !v5 )
      return (unsigned int)-2147467259;
  }
  return v3;
}

```

## disassembly

```asm
0x1400373f4  mov     [rsp+arg_0], rbx
0x1400373f9  push    rdi
0x1400373fa  sub     rsp, 20h
0x1400373fe  cmp     qword ptr [rcx], 0
0x140037402  mov     rdi, rcx
0x140037405  jz      short loc_14003740E
0x140037407  mov     eax, 8000FFFFh
0x14003740c  jmp     short loc_14003746A
0x14003740e  lea     r8, aLocalRemoteass_0; "Local\\RemoteAssistanceSettingLockS"
0x140037415  xor     edx, edx; bInitialOwner
0x140037417  xor     ecx, ecx; lpMutexAttributes
0x140037419  xor     ebx, ebx
0x14003741b  call    cs:__imp_CreateMutexW
0x140037422  nop     dword ptr [rax+rax+00h]
0x140037427  mov     [rdi], rax
0x14003742a  test    rax, rax
0x14003742d  jnz     short loc_140037468
0x14003742f  call    cs:__imp_GetLastError
0x140037436  nop     dword ptr [rax+rax+00h]
0x14003743b  cmp     eax, 5
0x14003743e  jnz     short loc_140037468
0x140037440  lea     r8, aLocalRemoteass_0; "Local\\RemoteAssistanceSettingLockS"
0x140037447  xor     edx, edx; bInheritHandle
0x140037449  mov     ecx, 1F0001h; dwDesiredAccess
0x14003744e  call    cs:__imp_OpenMutexW
0x140037455  nop     dword ptr [rax+rax+00h]
0x14003745a  test    rax, rax
0x14003745d  mov     [rdi], rax
0x140037460  mov     ecx, 80004005h
0x140037465  cmovz   ebx, ecx
0x140037468  mov     eax, ebx
0x14003746a  mov     rbx, [rsp+28h+arg_0]
0x14003746f  add     rsp, 20h
0x140037473  pop     rdi
0x140037474  retn
```
