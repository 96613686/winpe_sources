# STTABLE::Iterate(void (*)(STTABLE_ITEM *,unsigned __int64,int *),unsigned __int64)

- ea: `0x180006074`
- end: `0x1800061b8`
- name: `?Iterate@STTABLE@@QEAAXP6AXPEAVSTTABLE_ITEM@@_KPEAH@Z1@Z`
- size: `324`
- prototype: `void __fastcall(STTABLE *__hidden this, void (*)(struct STTABLE_ITEM *, unsigned __int64, int *), unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004630`

## callees

- `0x180006074`
- `0x18000658c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000619d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000619d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000609a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000609a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800060bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800060bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006185`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006185`

## pseudocode

```c
void __fastcall STTABLE::Iterate(STTABLE *this, void (*a2)(struct STTABLE_ITEM *, unsigned __int64, int *), __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r13
  volatile signed __int32 *v5; // rdi
  __int64 v6; // rbp
  __int64 v7; // r13
  __int64 **v8; // r15
  __int64 *v9; // r14
  __int64 *v10; // r12
  volatile signed __int32 *v11; // rsi
  __int64 *v12; // rax
  __int64 v13; // rcx
  _DWORD *v14; // rcx
  int v15; // eax
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  v16 = a3;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  *((_DWORD *)this + 29) = 1;
  v5 = (volatile signed __int32 *)((char *)this + 120);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 30, 0) > 0 )
    WaitForSingleObject(*((HANDLE *)this + 21), 0xFFFFFFFF);
  *v5 = -1;
  v6 = 0;
  if ( *((_DWORD *)this + 26) )
  {
    v7 = *((_QWORD *)this + 2);
    do
    {
      v8 = (__int64 **)(*(_QWORD *)(v7 + 8 * v6) + 8LL);
      LODWORD(v16) = 0;
      v9 = *v8;
      while ( v9 != (__int64 *)v8 )
      {
        v10 = v9;
        v11 = (volatile signed __int32 *)(v9 - 1);
        v9 = (__int64 *)*v9;
        _InterlockedIncrement(v11 + 6);
        IP_MODULE::TableIterator((struct STTABLE_ITEM *)v11, 0, (int *)&v16);
        if ( (_DWORD)v16 )
        {
          v12 = (__int64 *)v10[1];
          v13 = *v10;
          *v12 = *v10;
          *(_QWORD *)(v13 + 8) = v12;
          if ( _InterlockedExchangeAdd(v11 + 6, 0xFFFFFFFF) == 1 )
          {
            if ( v11 )
              (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v11)(v11, 1);
          }
        }
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < *((_DWORD *)this + 26) );
    v14 = (_DWORD *)((char *)this + 120);
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  }
  else
  {
    v14 = (_DWORD *)((char *)this + 120);
  }
  v15 = _InterlockedDecrement(v5);
  if ( v15 < 0 )
  {
    *v14 = 0;
    *((_DWORD *)this + 29) = 0;
    LeaveCriticalSection(v3);
  }
  else if ( *((_DWORD *)this + 29) )
  {
    if ( !v15 )
      SetEvent(*((HANDLE *)this + 21));
  }
}

```

## disassembly

```asm
0x180006074  mov     [rsp+arg_0], rbx
0x180006079  mov     [rsp+arg_10], r8
0x18000607e  push    rbp
0x18000607f  push    rsi
0x180006080  push    rdi
0x180006081  push    r12
0x180006083  push    r13
0x180006085  push    r14
0x180006087  push    r15
0x180006089  sub     rsp, 20h
0x18000608d  lea     r13, [rcx+80h]
0x180006094  mov     rbx, rcx
0x180006097  mov     rcx, r13; lpCriticalSection
0x18000609a  call    cs:__imp_EnterCriticalSection
0x1800060a0  xor     eax, eax
0x1800060a2  mov     dword ptr [rbx+74h], 1
0x1800060a9  lea     rdi, [rbx+78h]
0x1800060ad  lock xadd [rdi], eax
0x1800060b1  test    eax, eax
0x1800060b3  jle     short loc_1800060C5
0x1800060b5  mov     rcx, [rbx+0A8h]; hHandle
0x1800060bc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800060bf  call    cs:__imp_WaitForSingleObject
0x1800060c5  mov     dword ptr [rdi], 0FFFFFFFFh
0x1800060cb  xor     ebp, ebp
0x1800060cd  mov     rax, [rbx+10h]
0x1800060d1  cmp     [rbx+68h], ebp
0x1800060d4  jbe     loc_180006165
0x1800060da  mov     r13, rax
0x1800060dd  mov     r15, [r13+rbp*8+0]
0x1800060e2  add     r15, 8
0x1800060e6  mov     dword ptr [rsp+58h+arg_10], 0
0x1800060ee  mov     r14, [r15]
0x1800060f1  jmp     short loc_18000614C
0x1800060f3  lea     r12, [r14]
0x1800060f6  lea     rsi, [r14-8]
0x1800060fa  mov     r14, [r14]
0x1800060fd  lock inc dword ptr [rsi+18h]
0x180006101  lea     r8, [rsp+58h+arg_10]; int *
0x180006106  xor     edx, edx; unsigned __int64
0x180006108  mov     rcx, rsi; struct STTABLE_ITEM *
0x18000610b  call    ?TableIterator@IP_MODULE@@CAXPEAVSTTABLE_ITEM@@_KPEAH@Z; IP_MODULE::TableIterator(STTABLE_ITEM *,unsigned __int64,int *)
0x180006110  cmp     dword ptr [rsp+58h+arg_10], 0
0x180006115  jz      short loc_18000614C
0x180006117  mov     rax, [r12+8]
0x18000611c  mov     rcx, [r12]
0x180006120  mov     [rax], rcx
0x180006123  mov     [rcx+8], rax
0x180006127  or      eax, 0FFFFFFFFh
0x18000612a  lock xadd [rsi+18h], eax
0x18000612f  cmp     eax, 1
0x180006132  jnz     short loc_18000614C
0x180006134  test    rsi, rsi
0x180006137  jz      short loc_18000614C
0x180006139  mov     rax, [rsi]
0x18000613c  mov     edx, 1
0x180006141  mov     rcx, rsi
0x180006144  mov     rax, [rax]
0x180006147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000614c  cmp     r14, r15
0x18000614f  jnz     short loc_1800060F3
0x180006151  inc     ebp
0x180006153  cmp     ebp, [rbx+68h]
0x180006156  jb      short loc_1800060DD
0x180006158  lea     rcx, [rbx+78h]
0x18000615c  lea     r13, [rbx+80h]
0x180006163  jmp     short loc_180006168
0x180006165  mov     rcx, rdi
0x180006168  or      eax, 0FFFFFFFFh
0x18000616b  lock xadd [rdi], eax
0x18000616f  sub     eax, 1
0x180006172  js      short loc_18000618D
0x180006174  cmp     dword ptr [rbx+74h], 0
0x180006178  jz      short loc_1800061A3
0x18000617a  test    eax, eax
0x18000617c  jnz     short loc_1800061A3
0x18000617e  mov     rcx, [rbx+0A8h]; hEvent
0x180006185  call    cs:__imp_SetEvent
0x18000618b  jmp     short loc_1800061A3
0x18000618d  mov     dword ptr [rcx], 0
0x180006193  mov     rcx, r13; lpCriticalSection
0x180006196  mov     dword ptr [rbx+74h], 0
0x18000619d  call    cs:__imp_LeaveCriticalSection
0x1800061a3  mov     rbx, [rsp+58h+arg_0]
0x1800061a8  add     rsp, 20h
0x1800061ac  pop     r15
0x1800061ae  pop     r14
0x1800061b0  pop     r13
0x1800061b2  pop     r12
0x1800061b4  pop     rdi
0x1800061b5  pop     rsi
0x1800061b6  pop     rbp
0x1800061b7  retn
```
