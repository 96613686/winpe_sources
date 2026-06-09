# SEND_QUEUE::Empty(int,int)

- ea: `0x180001d84`
- end: `0x180001e73`
- name: `?Empty@SEND_QUEUE@@QEAAJHH@Z`
- size: `239`
- prototype: `__int64 __fastcall(SEND_QUEUE *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001cc4`
- `0x180004b90`
- `0x180005068`

## callees

- `0x180001d84`
- `0x180009128`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001e36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001e36`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001e47`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001e47`

## pseudocode

```c
__int64 __fastcall SEND_QUEUE::Empty(SEND_QUEUE *this, int a2, int a3)
{
  _QWORD **v6; // rbx
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  FCGI_BUFFER *v9; // rcx
  bool v10; // zf
  unsigned int v11; // ebx
  signed int LastError; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( a3 )
  {
    if ( *((_DWORD *)this + 29) )
      *((_DWORD *)this + 30) = 1;
    else
      a3 = 0;
  }
  v6 = (_QWORD **)((char *)this + 24);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( (_QWORD **)v7[1] != v6 || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    v9 = (FCGI_BUFFER *)(v7 - 4);
    v8[1] = v6;
    *((_DWORD *)this + 5) -= *((_DWORD *)v9 + 2);
    FCGI_BUFFER::Free(v9);
  }
  v10 = *((_DWORD *)this + 21) == 0;
  *((_DWORD *)this + 25) = 0;
  if ( v10 )
  {
    v11 = 0;
    if ( a2 )
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
  }
  else
  {
    v11 = -2147023901;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( a3 && (WaitForSingleObject(*((HANDLE *)this + 16), 0xFFFFFFFF) || !ResetEvent(*((HANDLE *)this + 16))) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v11;
}

```

## disassembly

```asm
0x180001d84  push    rbx
0x180001d86  push    rbp
0x180001d87  push    rsi
0x180001d88  push    rdi
0x180001d89  push    r14
0x180001d8b  sub     rsp, 20h
0x180001d8f  mov     rdi, rcx
0x180001d92  mov     esi, r8d
0x180001d95  add     rcx, 28h ; '('; lpCriticalSection
0x180001d99  mov     r14d, edx
0x180001d9c  call    cs:__imp_EnterCriticalSection
0x180001da2  test    esi, esi
0x180001da4  jz      short loc_180001DB7
0x180001da6  cmp     dword ptr [rdi+74h], 0
0x180001daa  jz      short loc_180001DB5
0x180001dac  mov     dword ptr [rdi+78h], 1
0x180001db3  jmp     short loc_180001DB7
0x180001db5  xor     esi, esi
0x180001db7  lea     rbx, [rdi+18h]
0x180001dbb  mov     rcx, [rbx]
0x180001dbe  cmp     rcx, rbx
0x180001dc1  jz      short loc_180001DF1
0x180001dc3  cmp     [rcx+8], rbx
0x180001dc7  jnz     short loc_180001DEA
0x180001dc9  mov     rax, [rcx]
0x180001dcc  cmp     [rax+8], rcx
0x180001dd0  jnz     short loc_180001DEA
0x180001dd2  mov     [rbx], rax
0x180001dd5  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x180001dd9  mov     [rax+8], rbx
0x180001ddd  mov     eax, [rcx+8]
0x180001de0  sub     [rdi+14h], eax
0x180001de3  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180001de8  jmp     short loc_180001DBB
0x180001dea  mov     ecx, 3
0x180001def  int     29h; Win8: RtlFailFast(ecx)
0x180001df1  cmp     dword ptr [rdi+54h], 0
0x180001df5  mov     dword ptr [rdi+64h], 0
0x180001dfc  jz      short loc_180001E05
0x180001dfe  mov     ebx, 800703E3h
0x180001e03  jmp     short loc_180001E1E
0x180001e05  xor     ebx, ebx
0x180001e07  test    r14d, r14d
0x180001e0a  jz      short loc_180001E1E
0x180001e0c  mov     rcx, [rdi+8]
0x180001e10  mov     rax, [rcx]
0x180001e13  mov     rax, [rax+8]
0x180001e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e1c  mov     ebx, eax
0x180001e1e  lea     rcx, [rdi+28h]; lpCriticalSection
0x180001e22  call    cs:__imp_LeaveCriticalSection
0x180001e28  test    esi, esi
0x180001e2a  jz      short loc_180001E66
0x180001e2c  mov     rcx, [rdi+80h]; hHandle
0x180001e33  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180001e36  call    cs:__imp_WaitForSingleObject
0x180001e3c  test    eax, eax
0x180001e3e  jnz     short loc_180001E51
0x180001e40  mov     rcx, [rdi+80h]; hEvent
0x180001e47  call    cs:__imp_ResetEvent
0x180001e4d  test    eax, eax
0x180001e4f  jnz     short loc_180001E66
0x180001e51  call    cs:__imp_GetLastError
0x180001e57  mov     ebx, eax
0x180001e59  test    eax, eax
0x180001e5b  jle     short loc_180001E66
0x180001e5d  movzx   ebx, ax
0x180001e60  or      ebx, 80070000h
0x180001e66  mov     eax, ebx
0x180001e68  add     rsp, 20h
0x180001e6c  pop     r14
0x180001e6e  pop     rdi
0x180001e6f  pop     rsi
0x180001e70  pop     rbp
0x180001e71  pop     rbx
0x180001e72  retn
```
