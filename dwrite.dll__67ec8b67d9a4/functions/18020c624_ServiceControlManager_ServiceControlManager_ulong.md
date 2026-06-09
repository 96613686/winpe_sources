# ServiceControlManager::ServiceControlManager(ulong)

- ea: `0x18020c624`
- end: `0x18020c670`
- name: `??0ServiceControlManager@@QEAA@K@Z`
- size: `76`
- prototype: `ServiceControlManager *__fastcall(ServiceControlManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1801ebf2c`

## callees

- `0x18020c624`

## import_xrefs

- `kernel32!GetLastError` at `0x18020c649`
- `kernel32!GetLastError` at `0x18020c649`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18020c63b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18020c63b`

## pseudocode

```c
ServiceControlManager *__fastcall ServiceControlManager::ServiceControlManager(ServiceControlManager *this)
{
  SC_HANDLE v2; // rax
  signed int LastError; // eax

  *((_DWORD *)this + 2) = 0;
  v2 = OpenSCManagerW(0, 0, 0);
  *(_QWORD *)this = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147467259;
    }
    *((_DWORD *)this + 2) = LastError;
  }
  return this;
}

```

## disassembly

```asm
0x18020c624  push    rbx
0x18020c626  sub     rsp, 20h
0x18020c62a  mov     rbx, rcx
0x18020c62d  mov     dword ptr [rcx+8], 0
0x18020c634  xor     ecx, ecx; lpMachineName
0x18020c636  xor     r8d, r8d; dwDesiredAccess
0x18020c639  xor     edx, edx; lpDatabaseName
0x18020c63b  call    cs:__imp_OpenSCManagerW
0x18020c641  mov     [rbx], rax
0x18020c644  test    rax, rax
0x18020c647  jnz     short loc_18020C667
0x18020c649  call    cs:__imp_GetLastError
0x18020c64f  test    eax, eax
0x18020c651  jz      short loc_18020C65F
0x18020c653  jle     short loc_18020C664
0x18020c655  movzx   eax, ax
0x18020c658  or      eax, 80070000h
0x18020c65d  jmp     short loc_18020C664
0x18020c65f  mov     eax, 80004005h
0x18020c664  mov     [rbx+8], eax
0x18020c667  mov     rax, rbx
0x18020c66a  add     rsp, 20h
0x18020c66e  pop     rbx
0x18020c66f  retn
```
