# CKsProxy::StartIoThread(void)

- ea: `0x180024e3c`
- end: `0x180024eb1`
- name: `?StartIoThread@CKsProxy@@QEAAJXZ`
- size: `117`
- prototype: `signed int __fastcall(CKsProxy *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180028584`

## callees

- `0x180024e3c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180024e84`
- `KERNEL32!GetLastError` at `0x180024e84`
- `KERNEL32!CreateThread` at `0x180024e71`
- `KERNEL32!CreateThread` at `0x180024e71`

## pseudocode

```c
signed int __fastcall CKsProxy::StartIoThread(CKsProxy *this)
{
  signed int result; // eax

  if ( this->m_IoThreadHandle )
    return 0;
  this->m_IoThreadHandle = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CKsProxy::IoThread, this, 0, &this->m_IoThreadId);
  result = GetLastError();
  if ( this->m_IoThreadHandle )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180024e3c  push    rbx
0x180024e3e  sub     rsp, 30h
0x180024e42  cmp     qword ptr [rcx+188h], 0
0x180024e4a  mov     rbx, rcx
0x180024e4d  jnz     short loc_180024EA8
0x180024e4f  lea     rax, [rcx+190h]
0x180024e56  mov     r9, rcx; lpParameter
0x180024e59  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180024e5e  lea     r8, ?IoThread@CKsProxy@@SAKPEAV1@@Z; lpStartAddress
0x180024e65  xor     edx, edx; dwStackSize
0x180024e67  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180024e6f  xor     ecx, ecx; lpThreadAttributes
0x180024e71  call    cs:__imp_CreateThread
0x180024e78  nop     dword ptr [rax+rax+00h]
0x180024e7d  mov     [rbx+188h], rax
0x180024e84  call    cs:__imp_GetLastError
0x180024e8b  nop     dword ptr [rax+rax+00h]
0x180024e90  cmp     qword ptr [rbx+188h], 0
0x180024e98  jnz     short loc_180024EA8
0x180024e9a  test    eax, eax
0x180024e9c  jle     short loc_180024EAA
0x180024e9e  movzx   eax, ax
0x180024ea1  or      eax, 80070000h
0x180024ea6  jmp     short loc_180024EAA
0x180024ea8  xor     eax, eax
0x180024eaa  add     rsp, 30h
0x180024eae  pop     rbx
0x180024eaf  retn
```
