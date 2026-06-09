# PROTOCOL::EndOfRequestCleanup(void)

- ea: `0x180003480`
- end: `0x1800034f9`
- name: `?EndOfRequestCleanup@PROTOCOL@@QEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(PROTOCOL *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005068`
- `0x180005294`

## callees

- `0x180003480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003496`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003496`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034e1`

## pseudocode

```c
__int64 __fastcall PROTOCOL::EndOfRequestCleanup(PROTOCOL *this)
{
  unsigned int v2; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 27) )
  {
    v2 = -2147023901;
  }
  else
  {
    ++*((_WORD *)this + 20);
    v2 = 0;
    if ( (unsigned __int16)(*((_WORD *)this + 20) - 1) > 0xFEu )
      *((_WORD *)this + 20) = 1;
    *(_QWORD *)((char *)this + 52) = 0;
    *((_QWORD *)this + 19) = 0;
    *(_QWORD *)((char *)this + 44) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v2;
}

```

## disassembly

```asm
0x180003480  mov     [rsp+arg_0], rbx
0x180003485  mov     [rsp+arg_8], rsi
0x18000348a  push    rdi
0x18000348b  sub     rsp, 20h
0x18000348f  mov     rbx, rcx
0x180003492  add     rcx, 40h ; '@'; lpCriticalSection
0x180003496  call    cs:__imp_EnterCriticalSection
0x18000349c  xor     edx, edx
0x18000349e  cmp     [rbx+6Ch], edx
0x1800034a1  jz      short loc_1800034AA
0x1800034a3  mov     edi, 800703E3h
0x1800034a8  jmp     short loc_1800034DD
0x1800034aa  mov     r8d, 1
0x1800034b0  mov     ecx, 0FEh
0x1800034b5  add     [rbx+28h], r8w
0x1800034ba  mov     edi, edx
0x1800034bc  movzx   eax, word ptr [rbx+28h]
0x1800034c0  sub     ax, r8w
0x1800034c4  cmp     ax, cx
0x1800034c7  jbe     short loc_1800034CE
0x1800034c9  mov     [rbx+28h], r8w
0x1800034ce  mov     [rbx+34h], rdx
0x1800034d2  mov     [rbx+98h], rdx
0x1800034d9  mov     [rbx+2Ch], rdx
0x1800034dd  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800034e1  call    cs:__imp_LeaveCriticalSection
0x1800034e7  mov     rbx, [rsp+28h+arg_0]
0x1800034ec  mov     eax, edi
0x1800034ee  mov     rsi, [rsp+28h+arg_8]
0x1800034f3  add     rsp, 20h
0x1800034f7  pop     rdi
0x1800034f8  retn
```
