# GetPooledSemaphore

- ea: `0x180043ad4`
- end: `0x180043b9f`
- name: `GetPooledSemaphore`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180043934`

## callees

- `0x180043ad4`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180043b88`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180043b88`

## pseudocode

```c
HANDLE GetPooledSemaphore()
{
  signed __int64 v0; // rcx
  __int64 *v1; // roff
  __int64 v2; // rdx
  signed __int64 v3; // rax
  bool v4; // zf
  HANDLE result; // rax
  _QWORD v6[2]; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+40h] [rbp-18h]
  int v8; // [rsp+44h] [rbp-14h]

  while ( 1 )
  {
    v3 = qword_18006E400;
    v4 = qword_18006E400 == 0;
    _m_prefetchw(&qword_18006E400);
    if ( v4 )
      break;
    v0 = qword_18006E400 - 1;
    v1 = &qword_18006E200[qword_18006E400 - 1];
    _m_prefetchw(v1);
    if ( *v1 )
    {
      v2 = _InterlockedExchange64(&qword_18006E200[v0], 0);
      if ( v2 )
      {
        if ( v3 == _InterlockedCompareExchange64(&qword_18006E400, v0, v3) )
          return (HANDLE)v2;
        qword_18006E200[v0] = v2;
      }
    }
  }
  if ( NITS_PRESENCE_STUB != 1 )
  {
    v7 = 101;
    v6[0] = "GetPooledSemaphore";
    v8 = -1;
    v6[1] = "onecore\\admin\\wmi\\winomi\\pal\\condlockatomic.c";
    if ( ((unsigned int (__fastcall *)(_QWORD *, _QWORD))NITS_STUB[0])(v6, 0) )
      return 0;
  }
  result = CreateSemaphoreExW(0, 0, 0xFFFF, 0, 0, 0x1F0003u);
  if ( !result )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180043ad4  sub     rsp, 58h
0x180043ad8  jmp     short loc_180043B0F
0x180043ada  lea     rcx, [rax-1]
0x180043ade  lea     r8, qword_18006E200
0x180043ae5  prefetchw byte ptr [r8+rcx*8]
0x180043aea  cmp     qword ptr [r8+rcx*8], 0
0x180043aef  jz      short loc_180043B0F
0x180043af1  xor     edx, edx
0x180043af3  xchg    rdx, [r8+rcx*8]
0x180043af7  test    rdx, rdx
0x180043afa  jz      short loc_180043B0F
0x180043afc  lock cmpxchg cs:qword_18006E400, rcx
0x180043b05  jz      loc_180043B9A
0x180043b0b  mov     [r8+rcx*8], rdx
0x180043b0f  mov     rax, cs:qword_18006E400
0x180043b16  test    rax, rax
0x180043b19  prefetchw byte ptr cs:qword_18006E400
0x180043b20  jnz     short loc_180043ADA
0x180043b22  cmp     cs:NITS_PRESENCE_STUB, 1
0x180043b2a  jz      short loc_180043B6B
0x180043b2c  lea     rax, aGetpooledsemap; "GetPooledSemaphore"
0x180043b33  mov     [rsp+58h+var_18], 65h ; 'e'
0x180043b3b  mov     [rsp+58h+var_28], rax
0x180043b40  lea     rcx, [rsp+58h+var_28]
0x180043b45  lea     rax, aOnecoreAdminWm; "onecore\\admin\\wmi\\winomi\\pal\\condl"...
0x180043b4c  mov     [rsp+58h+var_14], 0FFFFFFFFh
0x180043b54  mov     [rsp+58h+var_20], rax
0x180043b59  xor     edx, edx
0x180043b5b  mov     rax, cs:NITS_STUB
0x180043b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b67  test    eax, eax
0x180043b69  jnz     short loc_180043B93
0x180043b6b  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180043b73  xor     r9d, r9d; lpName
0x180043b76  xor     edx, edx; lInitialCount
0x180043b78  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180043b80  xor     ecx, ecx; lpSemaphoreAttributes
0x180043b82  mov     r8d, 0FFFFh; lMaximumCount
0x180043b88  call    cs:__imp_CreateSemaphoreExW
0x180043b8e  test    rax, rax
0x180043b91  jnz     short loc_180043B95
0x180043b93  xor     eax, eax
0x180043b95  add     rsp, 58h
0x180043b99  retn
0x180043b9a  mov     rax, rdx
0x180043b9d  jmp     short loc_180043B95
```
