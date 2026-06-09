# SecPsCalloutInitialize

- ea: `0x14002f410`
- end: `0x14002f4cb`
- name: `SecPsCalloutInitialize`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14002a1d4`

## callees

- `0x140011610`
- `0x14002f0fc`
- `0x14002f410`
- `0x14002f8e4`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14002f44c`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14002f44c`
- `ntoskrnl!PsSetCreateThreadNotifyRoutine` at `0x14002f497`
- `ntoskrnl!PsSetCreateThreadNotifyRoutine` at `0x14002f497`
- `ntoskrnl!PsSetLoadImageNotifyRoutine` at `0x14002f47e`
- `ntoskrnl!PsSetLoadImageNotifyRoutine` at `0x14002f47e`

## pseudocode

```c
__int64 SecPsCalloutInitialize()
{
  int v0; // ecx
  int v1; // eax
  NTSTATUS ImageNotifyRoutine; // eax
  NTSTATUS ThreadNotifyRoutine; // eax
  int ProcessContexts; // eax

  v0 = SecPsInitializeWorkingThread();
  if ( v0 >= 0 )
  {
    v1 = qword_140020010
       ? qword_140020010(0, SecPsCreateProcessNotify, 0)
       : PsSetCreateProcessNotifyRoutineEx(SecPsCreateProcessNotify, 0);
    v0 = v1;
    if ( v1 >= 0 )
    {
      if ( qword_140020018 )
        ImageNotifyRoutine = qword_140020018(SecPsLoadImageNotify, 1);
      else
        ImageNotifyRoutine = PsSetLoadImageNotifyRoutine(SecPsLoadImageNotify);
      v0 = ImageNotifyRoutine;
      if ( ImageNotifyRoutine >= 0 )
      {
        ThreadNotifyRoutine = PsSetCreateThreadNotifyRoutine(SecCreateThreadNotifyProxyRoutine);
        v0 = ThreadNotifyRoutine;
        if ( ThreadNotifyRoutine >= 0 )
        {
          ProcessContexts = SecGenerateProcessContexts((unsigned int)ThreadNotifyRoutine);
          *((_BYTE *)SecData + 1268) = 1;
          v0 = 0;
          if ( ProcessContexts >= 0 )
            return (unsigned int)ProcessContexts;
        }
      }
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14002f410  sub     rsp, 28h
0x14002f414  call    SecPsInitializeWorkingThread
0x14002f419  mov     ecx, eax
0x14002f41b  test    eax, eax
0x14002f41d  js      loc_14002F4C3
0x14002f423  mov     rax, cs:qword_140020010
0x14002f42a  test    rax, rax
0x14002f42d  jz      short loc_14002F443
0x14002f42f  xor     r8d, r8d
0x14002f432  lea     rdx, SecPsCreateProcessNotify
0x14002f439  xor     ecx, ecx
0x14002f43b  call    cs:__guard_dispatch_icall_fptr
0x14002f441  jmp     short loc_14002F458
0x14002f443  xor     edx, edx; Remove
0x14002f445  lea     rcx, SecPsCreateProcessNotify; NotifyRoutine
0x14002f44c  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x14002f453  nop     dword ptr [rax+rax+00h]
0x14002f458  mov     ecx, eax
0x14002f45a  test    eax, eax
0x14002f45c  js      short loc_14002F4C3
0x14002f45e  mov     rax, cs:qword_140020018
0x14002f465  lea     rcx, SecPsLoadImageNotify; NotifyRoutine
0x14002f46c  test    rax, rax
0x14002f46f  jz      short loc_14002F47E
0x14002f471  mov     edx, 1
0x14002f476  call    cs:__guard_dispatch_icall_fptr
0x14002f47c  jmp     short loc_14002F48A
0x14002f47e  call    cs:__imp_PsSetLoadImageNotifyRoutine
0x14002f485  nop     dword ptr [rax+rax+00h]
0x14002f48a  mov     ecx, eax
0x14002f48c  test    eax, eax
0x14002f48e  js      short loc_14002F4C3
0x14002f490  lea     rcx, SecCreateThreadNotifyProxyRoutine; NotifyRoutine
0x14002f497  call    cs:__imp_PsSetCreateThreadNotifyRoutine
0x14002f49e  nop     dword ptr [rax+rax+00h]
0x14002f4a3  mov     ecx, eax
0x14002f4a5  test    eax, eax
0x14002f4a7  js      short loc_14002F4C3
0x14002f4a9  call    SecGenerateProcessContexts
0x14002f4ae  mov     rcx, cs:SecData
0x14002f4b5  mov     byte ptr [rcx+4F4h], 1
0x14002f4bc  xor     ecx, ecx
0x14002f4be  test    eax, eax
0x14002f4c0  cmovns  ecx, eax
0x14002f4c3  mov     eax, ecx
0x14002f4c5  add     rsp, 28h
0x14002f4c9  retn
```
