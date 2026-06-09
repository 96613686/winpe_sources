# APPLICATION::SendFcgiStdIn(FCGI_BUFFER *,int *)

- ea: `0x180006bcc`
- end: `0x180006c55`
- name: `?SendFcgiStdIn@APPLICATION@@QEAAJPEAVFCGI_BUFFER@@PEAH@Z`
- size: `137`
- prototype: `__int64 __fastcall(SEND_QUEUE **this, struct FCGI_BUFFER *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b3ac`
- `0x18000cfa0`

## callees

- `0x180001e7c`
- `0x180006bcc`
- `0x180009128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c36`

## pseudocode

```c
__int64 __fastcall APPLICATION::SendFcgiStdIn(SEND_QUEUE **this, struct FCGI_BUFFER *a2, int *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  int v8; // eax
  int *v9; // r9

  v3 = (struct _RTL_CRITICAL_SECTION *)(this + 14);
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 14));
  if ( *((_DWORD *)this + 26) )
  {
    v7 = -2147023901;
  }
  else if ( *((_DWORD *)this + 11) == 2 )
  {
    v7 = -2147024858;
  }
  else
  {
    v8 = *((_DWORD *)a2 + 6);
    v9 = 0;
    if ( v8 )
      v9 = a3;
    v7 = SEND_QUEUE::Enqueue(this[8], a2, v8 == 0, v9);
    a2 = 0;
  }
  LeaveCriticalSection(v3);
  if ( a2 )
    FCGI_BUFFER::Free(a2);
  return v7;
}

```

## disassembly

```asm
0x180006bcc  push    rbx
0x180006bce  push    rsi
0x180006bcf  push    rdi
0x180006bd0  push    r14
0x180006bd2  sub     rsp, 28h
0x180006bd6  lea     rsi, [rcx+70h]
0x180006bda  mov     dword ptr [r8], 0
0x180006be1  mov     rbx, rcx
0x180006be4  mov     r14, r8
0x180006be7  mov     rcx, rsi; lpCriticalSection
0x180006bea  mov     rdi, rdx
0x180006bed  call    cs:__imp_EnterCriticalSection
0x180006bf3  mov     eax, [rbx+68h]
0x180006bf6  test    eax, eax
0x180006bf8  jz      short loc_180006C01
0x180006bfa  mov     ebx, 800703E3h
0x180006bff  jmp     short loc_180006C33
0x180006c01  cmp     dword ptr [rbx+2Ch], 2
0x180006c05  jnz     short loc_180006C0E
0x180006c07  mov     ebx, 80070026h
0x180006c0c  jmp     short loc_180006C33
0x180006c0e  mov     eax, [rdi+18h]
0x180006c11  xor     r9d, r9d
0x180006c14  mov     rcx, [rbx+40h]; this
0x180006c18  test    eax, eax
0x180006c1a  mov     rdx, rdi; struct FCGI_BUFFER *
0x180006c1d  cmovnz  r9, r14; int *
0x180006c21  xor     r8d, r8d
0x180006c24  test    eax, eax
0x180006c26  setz    r8b; int
0x180006c2a  call    ?Enqueue@SEND_QUEUE@@QEAAJPEAVFCGI_BUFFER@@HPEAH@Z; SEND_QUEUE::Enqueue(FCGI_BUFFER *,int,int *)
0x180006c2f  mov     ebx, eax
0x180006c31  xor     edi, edi
0x180006c33  mov     rcx, rsi; lpCriticalSection
0x180006c36  call    cs:__imp_LeaveCriticalSection
0x180006c3c  test    rdi, rdi
0x180006c3f  jz      short loc_180006C49
0x180006c41  mov     rcx, rdi; this
0x180006c44  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180006c49  mov     eax, ebx
0x180006c4b  add     rsp, 28h
0x180006c4f  pop     r14
0x180006c51  pop     rdi
0x180006c52  pop     rsi
0x180006c53  pop     rbx
0x180006c54  retn
```
