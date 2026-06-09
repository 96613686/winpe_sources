# COutputQueue::ThreadProc(void)

- ea: `0x18001c730`
- end: `0x18001c951`
- name: `?ThreadProc@COutputQueue@@IEAAKXZ`
- size: `545`
- prototype: `unsigned int __fastcall(COutputQueue *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001c360`

## callees

- `0x180001008`
- `0x180007004`
- `0x18001c28c`
- `0x18001c730`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001c746`
- `KERNEL32!EnterCriticalSection` at `0x18001c86d`
- `KERNEL32!EnterCriticalSection` at `0x18001c746`
- `KERNEL32!EnterCriticalSection` at `0x18001c86d`
- `KERNEL32!LeaveCriticalSection` at `0x18001c819`
- `KERNEL32!LeaveCriticalSection` at `0x18001c886`
- `KERNEL32!LeaveCriticalSection` at `0x18001c93c`
- `KERNEL32!LeaveCriticalSection` at `0x18001c819`
- `KERNEL32!LeaveCriticalSection` at `0x18001c886`
- `KERNEL32!LeaveCriticalSection` at `0x18001c93c`
- `KERNEL32!SetEvent` at `0x18001c768`
- `KERNEL32!SetEvent` at `0x18001c789`
- `KERNEL32!SetEvent` at `0x18001c7fd`
- `KERNEL32!SetEvent` at `0x18001c8ec`
- `KERNEL32!SetEvent` at `0x18001c768`
- `KERNEL32!SetEvent` at `0x18001c789`
- `KERNEL32!SetEvent` at `0x18001c7fd`
- `KERNEL32!SetEvent` at `0x18001c8ec`
- `KERNEL32!WaitForSingleObject` at `0x18001c82b`
- `KERNEL32!WaitForSingleObject` at `0x18001c82b`

## pseudocode

```c
__int64 __fastcall COutputQueue::ThreadProc(COutputQueue *this)
{
  _QWORD *v2; // r15
  __int64 v3; // rax
  void *v4; // rcx
  unsigned __int64 v5; // rsi
  unsigned int *v6; // rdi
  __int64 v7; // rax
  bool v8; // zf
  __int64 v9; // rax
  void *v10; // rcx
  unsigned int v11; // ebp
  int v12; // r14d
  int v13; // eax
  int v14; // edi
  __int64 v15; // rcx
  void *v16; // rcx
  int v18; // [rsp+70h] [rbp+8h] BYREF

LABEL_1:
  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  while ( !*((_DWORD *)this + 31) )
  {
    if ( *((_DWORD *)this + 28) )
    {
      COutputQueue::FreeSamples(this);
      SetEvent(*((HANDLE *)this + 10));
    }
    v3 = CBaseList::RemoveI(*((CBaseList **)this + 8), **((struct __POSITION ***)this + 8));
    v4 = (void *)*((_QWORD *)this + 17);
    v5 = v3;
    if ( v4 )
      SetEvent(v4);
    if ( v5 )
    {
      v6 = (unsigned int *)((char *)this + 104);
      if ( v5 > 0xFFFFFFFFFFFFFFF0uLL )
        goto LABEL_15;
      v7 = (int)*v6;
      v8 = (_DWORD)v7 == *((_DWORD *)this + 15);
      if ( (int)v7 < *((_DWORD *)this + 15) )
      {
        *(_QWORD *)(*((_QWORD *)this + 12) + 8 * v7) = v5;
        v8 = ++*v6 == *((_DWORD *)this + 15);
      }
      if ( v8 )
        goto LABEL_21;
    }
    else
    {
      if ( *((_DWORD *)this + 14) || (v6 = (unsigned int *)((char *)this + 104), !*((_DWORD *)this + 26)) )
      {
        ++*((_DWORD *)this + 27);
        v11 = 0;
        v12 = 1;
        goto LABEL_23;
      }
LABEL_15:
      if ( v5 != -2 )
      {
        if ( v5 == -5 )
        {
          v9 = CBaseList::RemoveI(*((CBaseList **)this + 8), **((struct __POSITION ***)this + 8));
          v10 = (void *)*((_QWORD *)this + 17);
          v2 = (_QWORD *)v9;
          if ( v10 )
            SetEvent(v10);
        }
LABEL_21:
        v11 = *v6;
        v12 = 0;
        *v6 = 0;
LABEL_23:
        LeaveCriticalSection((LPCRITICAL_SECTION)this);
        if ( v12 )
        {
          WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF);
        }
        else
        {
          if ( v11 )
          {
            v13 = *((_DWORD *)this + 33);
            v18 = 0;
            if ( !v13 )
            {
              v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 6) + 56LL))(
                      *((_QWORD *)this + 6),
                      *((_QWORD *)this + 12),
                      v11,
                      &v18);
              EnterCriticalSection((LPCRITICAL_SECTION)this);
              if ( !*((_DWORD *)this + 33) )
                *((_DWORD *)this + 33) = v14;
              LeaveCriticalSection((LPCRITICAL_SECTION)this);
            }
            do
            {
              v15 = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * (int)--v11);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            }
            while ( v11 );
          }
          switch ( v5 )
          {
            case 0xFFFFFFFFFFFFFFFDuLL:
              if ( !*((_DWORD *)this + 33) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 112LL))(*((_QWORD *)this + 5));
              break;
            case 0xFFFFFFFFFFFFFFFCuLL:
              v16 = (void *)*((_QWORD *)this + 10);
              *((_DWORD *)this + 33) = 0;
              SetEvent(v16);
              break;
            case 0xFFFFFFFFFFFFFFFBuLL:
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 136LL))(
                *((_QWORD *)this + 5),
                *v2,
                v2[1]);
              operator delete(v2);
              break;
          }
        }
        goto LABEL_1;
      }
      if ( *v6 )
        goto LABEL_21;
    }
  }
  COutputQueue::FreeSamples(this);
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  return 0;
}

```

## disassembly

```asm
0x18001c730  push    rbx
0x18001c732  push    rbp
0x18001c733  push    rsi
0x18001c734  push    rdi
0x18001c735  push    r14
0x18001c737  push    r15
0x18001c739  sub     rsp, 38h
0x18001c73d  mov     rbx, rcx
0x18001c740  xor     r15d, r15d
0x18001c743  mov     rcx, rbx; lpCriticalSection
0x18001c746  call    cs:__imp_EnterCriticalSection
0x18001c74c  cmp     [rbx+7Ch], r15d
0x18001c750  jnz     loc_18001C931
0x18001c756  cmp     [rbx+70h], r15d
0x18001c75a  jz      short loc_18001C76E
0x18001c75c  mov     rcx, rbx; this
0x18001c75f  call    ?FreeSamples@COutputQueue@@IEAAXXZ; COutputQueue::FreeSamples(void)
0x18001c764  mov     rcx, [rbx+50h]; hEvent
0x18001c768  call    cs:__imp_SetEvent
0x18001c76e  mov     rcx, [rbx+40h]; this
0x18001c772  mov     rdx, [rcx]; struct __POSITION *
0x18001c775  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18001c77a  mov     rcx, [rbx+88h]; hEvent
0x18001c781  mov     rsi, rax
0x18001c784  test    rcx, rcx
0x18001c787  jz      short loc_18001C78F
0x18001c789  call    cs:__imp_SetEvent
0x18001c78f  test    rsi, rsi
0x18001c792  jz      short loc_18001C7BC
0x18001c794  lea     rdi, [rbx+68h]
0x18001c798  cmp     rsi, 0FFFFFFFFFFFFFFF0h
0x18001c79c  ja      short loc_18001C7CB
0x18001c79e  movsxd  rax, dword ptr [rdi]
0x18001c7a1  cmp     eax, [rbx+3Ch]
0x18001c7a4  jge     short loc_18001C7B8
0x18001c7a6  mov     rcx, rax
0x18001c7a9  mov     rax, [rbx+60h]
0x18001c7ad  mov     [rax+rcx*8], rsi
0x18001c7b1  inc     dword ptr [rdi]
0x18001c7b3  mov     eax, [rdi]
0x18001c7b5  cmp     eax, [rbx+3Ch]
0x18001c7b8  jnz     short loc_18001C74C
0x18001c7ba  jmp     short loc_18001C803
0x18001c7bc  cmp     [rbx+38h], r15d
0x18001c7c0  jnz     short loc_18001C80D
0x18001c7c2  lea     rdi, [rbx+68h]
0x18001c7c6  cmp     [rdi], r15d
0x18001c7c9  jz      short loc_18001C80D
0x18001c7cb  cmp     rsi, 0FFFFFFFFFFFFFFFEh
0x18001c7cf  jnz     short loc_18001C7DC
0x18001c7d1  cmp     [rdi], r15d
0x18001c7d4  jz      loc_18001C74C
0x18001c7da  jmp     short loc_18001C803
0x18001c7dc  cmp     rsi, 0FFFFFFFFFFFFFFFBh
0x18001c7e0  jnz     short loc_18001C803
0x18001c7e2  mov     rcx, [rbx+40h]; this
0x18001c7e6  mov     rdx, [rcx]; struct __POSITION *
0x18001c7e9  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18001c7ee  mov     rcx, [rbx+88h]; hEvent
0x18001c7f5  mov     r15, rax
0x18001c7f8  test    rcx, rcx
0x18001c7fb  jz      short loc_18001C803
0x18001c7fd  call    cs:__imp_SetEvent
0x18001c803  mov     ebp, [rdi]
0x18001c805  xor     r14d, r14d
0x18001c808  mov     [rdi], r14d
0x18001c80b  jmp     short loc_18001C816
0x18001c80d  inc     dword ptr [rbx+6Ch]
0x18001c810  xor     ebp, ebp
0x18001c812  lea     r14d, [rbp+1]
0x18001c816  mov     rcx, rbx; lpCriticalSection
0x18001c819  call    cs:__imp_LeaveCriticalSection
0x18001c81f  test    r14d, r14d
0x18001c822  jz      short loc_18001C836
0x18001c824  mov     rcx, [rbx+48h]; hHandle
0x18001c828  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c82b  call    cs:__imp_WaitForSingleObject
0x18001c831  jmp     loc_18001C740
0x18001c836  test    ebp, ebp
0x18001c838  jz      short loc_18001C8AF
0x18001c83a  mov     eax, [rbx+84h]
0x18001c840  mov     [rsp+68h+arg_0], 0
0x18001c848  test    eax, eax
0x18001c84a  jnz     short loc_18001C88C
0x18001c84c  mov     rcx, [rbx+30h]
0x18001c850  lea     r9, [rsp+68h+arg_0]
0x18001c855  mov     rdx, [rbx+60h]
0x18001c859  mov     r8d, ebp
0x18001c85c  mov     rax, [rcx]
0x18001c85f  mov     rax, [rax+38h]
0x18001c863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c868  mov     rcx, rbx; lpCriticalSection
0x18001c86b  mov     edi, eax
0x18001c86d  call    cs:__imp_EnterCriticalSection
0x18001c873  mov     ecx, [rbx+84h]
0x18001c879  test    ecx, ecx
0x18001c87b  jnz     short loc_18001C883
0x18001c87d  mov     [rbx+84h], edi
0x18001c883  mov     rcx, rbx; lpCriticalSection
0x18001c886  call    cs:__imp_LeaveCriticalSection
0x18001c88c  mov     rax, [rbx+60h]
0x18001c890  dec     ebp
0x18001c892  movsxd  rcx, ebp
0x18001c895  mov     rcx, [rax+rcx*8]
0x18001c899  mov     rax, [rcx]
0x18001c89c  mov     rax, [rax+10h]
0x18001c8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8a5  test    ebp, ebp
0x18001c8a7  jnz     short loc_18001C88C
0x18001c8a9  mov     eax, [rbx+84h]
0x18001c8af  cmp     rsi, 0FFFFFFFFFFFFFFFDh
0x18001c8b3  jnz     short loc_18001C8D8
0x18001c8b5  mov     eax, [rbx+84h]
0x18001c8bb  test    eax, eax
0x18001c8bd  jnz     loc_18001C740
0x18001c8c3  mov     rcx, [rbx+28h]
0x18001c8c7  mov     rax, [rcx]
0x18001c8ca  mov     rax, [rax+70h]
0x18001c8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d3  jmp     loc_18001C740
0x18001c8d8  cmp     rsi, 0FFFFFFFFFFFFFFFCh
0x18001c8dc  jnz     short loc_18001C8F7
0x18001c8de  mov     rcx, [rbx+50h]; hEvent
0x18001c8e2  mov     dword ptr [rbx+84h], 0
0x18001c8ec  call    cs:__imp_SetEvent
0x18001c8f2  jmp     loc_18001C740
0x18001c8f7  cmp     rsi, 0FFFFFFFFFFFFFFFBh
0x18001c8fb  jnz     loc_18001C740
0x18001c901  mov     rcx, [rbx+28h]
0x18001c905  movsd   xmm3, qword ptr [r15+10h]
0x18001c90b  mov     r8, [r15+8]
0x18001c90f  mov     rdx, [r15]
0x18001c912  mov     rax, [rcx]
0x18001c915  mov     rax, [rax+88h]
0x18001c91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c921  lea     edx, [rsi+1Dh]; unsigned __int64
0x18001c924  mov     rcx, r15; void *
0x18001c927  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c92c  jmp     loc_18001C740
0x18001c931  mov     rcx, rbx; this
0x18001c934  call    ?FreeSamples@COutputQueue@@IEAAXXZ; COutputQueue::FreeSamples(void)
0x18001c939  mov     rcx, rbx; lpCriticalSection
0x18001c93c  call    cs:__imp_LeaveCriticalSection
0x18001c942  xor     eax, eax
0x18001c944  add     rsp, 38h
0x18001c948  pop     r15
0x18001c94a  pop     r14
0x18001c94c  pop     rdi
0x18001c94d  pop     rsi
0x18001c94e  pop     rbp
0x18001c94f  pop     rbx
0x18001c950  retn
```
