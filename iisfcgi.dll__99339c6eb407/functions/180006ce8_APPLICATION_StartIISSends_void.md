# APPLICATION::StartIISSends(void)

- ea: `0x180006ce8`
- end: `0x180006d38`
- name: `?StartIISSends@APPLICATION@@QEAAJXZ`
- size: `80`
- prototype: `__int64 __fastcall(APPLICATION *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cb30`
- `0x18000cfa0`
- `0x18000e3b0`

## callees

- `0x180002250`
- `0x180006ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006cfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006d25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006d25`

## pseudocode

```c
__int64 __fastcall APPLICATION::StartIISSends(APPLICATION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  unsigned int started; // ebx
  SEND_QUEUE *v4; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 26) )
  {
    started = -2147023901;
  }
  else
  {
    v4 = (SEND_QUEUE *)*((_QWORD *)this + 9);
    *((_DWORD *)this + 10) = 2;
    started = SEND_QUEUE::StartSends(v4);
  }
  LeaveCriticalSection(v1);
  return started;
}

```

## disassembly

```asm
0x180006ce8  mov     [rsp+arg_0], rbx
0x180006ced  push    rdi
0x180006cee  sub     rsp, 20h
0x180006cf2  lea     rdi, [rcx+70h]
0x180006cf6  mov     rbx, rcx
0x180006cf9  mov     rcx, rdi; lpCriticalSection
0x180006cfc  call    cs:__imp_EnterCriticalSection
0x180006d02  mov     eax, [rbx+68h]
0x180006d05  test    eax, eax
0x180006d07  jz      short loc_180006D10
0x180006d09  mov     ebx, 800703E3h
0x180006d0e  jmp     short loc_180006D22
0x180006d10  mov     rcx, [rbx+48h]; this
0x180006d14  mov     dword ptr [rbx+28h], 2
0x180006d1b  call    ?StartSends@SEND_QUEUE@@QEAAJXZ; SEND_QUEUE::StartSends(void)
0x180006d20  mov     ebx, eax
0x180006d22  mov     rcx, rdi; lpCriticalSection
0x180006d25  call    cs:__imp_LeaveCriticalSection
0x180006d2b  mov     eax, ebx
0x180006d2d  mov     rbx, [rsp+28h+arg_0]
0x180006d32  add     rsp, 20h
0x180006d36  pop     rdi
0x180006d37  retn
```
