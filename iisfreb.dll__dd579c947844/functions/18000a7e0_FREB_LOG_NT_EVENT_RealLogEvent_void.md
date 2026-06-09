# FREB_LOG_NT_EVENT::RealLogEvent(void)

- ea: `0x18000a7e0`
- end: `0x18000a8c8`
- name: `?RealLogEvent@FREB_LOG_NT_EVENT@@QEAAXXZ`
- size: `232`
- prototype: `void __fastcall(FREB_LOG_NT_EVENT *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003a10`
- `0x18000a2c0`
- `0x18000a4dc`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000a7e0`
- `0x18000ac46`
- `0x18000ac90`

## import_xrefs

- `msvcrt!_ultow` at `0x18000a817`
- `msvcrt!_ultow` at `0x18000a82a`
- `msvcrt!_ultow` at `0x18000a817`
- `msvcrt!_ultow` at `0x18000a82a`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000a899`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000a899`

## pseudocode

```c
void __fastcall FREB_LOG_NT_EVENT::RealLogEvent(FREB_LOG_NT_EVENT *this)
{
  unsigned int v2; // ebx
  wchar_t **v3; // rax
  wchar_t **v4; // rbx
  wchar_t Buffer[40]; // [rsp+30h] [rbp-B8h] BYREF
  wchar_t v6[40]; // [rsp+80h] [rbp-68h] BYREF

  v2 = _InterlockedExchange((volatile __int32 *)this + 1, 0);
  _ultow(5u, v6, 10);
  _ultow(v2, Buffer, 10);
  v3 = (wchar_t **)operator new(saturated_mul(*((unsigned __int16 *)this + 34), 8u));
  v4 = v3;
  if ( v3 )
  {
    memcpy_0(v3, *((const void **)this + 9), 8LL * *((unsigned __int16 *)this + 34));
    *v4 = Buffer;
    v4[1] = v6;
    EVENT_LOG::LogEvent(
      (EVENT_LOG *)FREB_LOG_NT_EVENT::sm_pEventLog,
      *((_DWORD *)this + 16),
      *((_WORD *)this + 34),
      (const unsigned __int16 **const)v4,
      *((_DWORD *)this + 20));
    operator delete(v4);
  }
}

```

## disassembly

```asm
0x18000a7e0  mov     r11, rsp
0x18000a7e3  mov     [r11+10h], rbx
0x18000a7e7  push    rdi
0x18000a7e8  sub     rsp, 0E0h
0x18000a7ef  mov     rax, cs:__security_cookie
0x18000a7f6  xor     rax, rsp
0x18000a7f9  mov     [rsp+0E8h+var_18], rax
0x18000a801  mov     r8d, 0Ah; Radix
0x18000a807  lea     rdx, [r11-68h]; Buffer
0x18000a80b  mov     rdi, rcx
0x18000a80e  xor     ebx, ebx
0x18000a810  xchg    ebx, [rcx+4]
0x18000a813  lea     ecx, [r8-5]; Value
0x18000a817  call    cs:__imp__ultow
0x18000a81d  mov     r8d, 0Ah; Radix
0x18000a823  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x18000a828  mov     ecx, ebx; Value
0x18000a82a  call    cs:__imp__ultow
0x18000a830  movzx   ecx, word ptr [rdi+44h]
0x18000a834  mov     eax, 8
0x18000a839  mul     rcx
0x18000a83c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a843  cmovb   rax, rcx
0x18000a847  mov     rcx, rax; Size
0x18000a84a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a84f  mov     rbx, rax
0x18000a852  test    rax, rax
0x18000a855  jz      short loc_18000A8A7
0x18000a857  movzx   r8d, word ptr [rdi+44h]
0x18000a85c  mov     rcx, rax; void *
0x18000a85f  mov     rdx, [rdi+48h]; Src
0x18000a863  shl     r8, 3; Size
0x18000a867  call    memcpy_0
0x18000a86c  lea     rax, [rsp+0E8h+Buffer]
0x18000a871  mov     r9, rbx
0x18000a874  mov     [rbx], rax
0x18000a877  lea     rax, [rsp+0E8h+var_68]
0x18000a87f  mov     [rbx+8], rax
0x18000a883  mov     ecx, [rdi+50h]
0x18000a886  movzx   r8d, word ptr [rdi+44h]
0x18000a88b  mov     edx, [rdi+40h]
0x18000a88e  mov     [rsp+0E8h+var_C8], ecx
0x18000a892  mov     rcx, cs:?sm_pEventLog@FREB_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA; EVENT_LOG * FREB_LOG_NT_EVENT::sm_pEventLog
0x18000a899  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000a89f  mov     rcx, rbx; Block
0x18000a8a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a8a7  mov     rcx, [rsp+0E8h+var_18]
0x18000a8af  xor     rcx, rsp; StackCookie
0x18000a8b2  call    __security_check_cookie
0x18000a8b7  mov     rbx, [rsp+0E8h+arg_8]
0x18000a8bf  add     rsp, 0E0h
0x18000a8c6  pop     rdi
0x18000a8c7  retn
```
