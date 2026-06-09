# CSettingsManager::Initialize(void)

- ea: `0x180015bb0`
- end: `0x180015c1f`
- name: `?Initialize@CSettingsManager@@QEAAJXZ`
- size: `111`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011170`
- `0x180011af8`

## callees

- `0x180015bb0`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180015bd7`
- `KERNEL32!CreateMutexW` at `0x180015bd7`
- `KERNEL32!OpenMutexW` at `0x180015bfe`
- `KERNEL32!OpenMutexW` at `0x180015bfe`
- `KERNEL32!GetLastError` at `0x180015be5`
- `KERNEL32!GetLastError` at `0x180015be5`

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
0x180015bb0  mov     [rsp+arg_0], rbx
0x180015bb5  push    rdi
0x180015bb6  sub     rsp, 20h
0x180015bba  cmp     qword ptr [rcx], 0
0x180015bbe  mov     rdi, rcx
0x180015bc1  jz      short loc_180015BCA
0x180015bc3  mov     eax, 8000FFFFh
0x180015bc8  jmp     short loc_180015C14
0x180015bca  lea     r8, Name; "Local\\RemoteAssistanceSettingLockS"
0x180015bd1  xor     edx, edx; bInitialOwner
0x180015bd3  xor     ecx, ecx; lpMutexAttributes
0x180015bd5  xor     ebx, ebx
0x180015bd7  call    cs:__imp_CreateMutexW
0x180015bdd  mov     [rdi], rax
0x180015be0  test    rax, rax
0x180015be3  jnz     short loc_180015C12
0x180015be5  call    cs:__imp_GetLastError
0x180015beb  cmp     eax, 5
0x180015bee  jnz     short loc_180015C12
0x180015bf0  lea     r8, Name; "Local\\RemoteAssistanceSettingLockS"
0x180015bf7  xor     edx, edx; bInheritHandle
0x180015bf9  mov     ecx, 1F0001h; dwDesiredAccess
0x180015bfe  call    cs:__imp_OpenMutexW
0x180015c04  test    rax, rax
0x180015c07  mov     [rdi], rax
0x180015c0a  mov     ecx, 80004005h
0x180015c0f  cmovz   ebx, ecx
0x180015c12  mov     eax, ebx
0x180015c14  mov     rbx, [rsp+28h+arg_0]
0x180015c19  add     rsp, 20h
0x180015c1d  pop     rdi
0x180015c1e  retn
```
