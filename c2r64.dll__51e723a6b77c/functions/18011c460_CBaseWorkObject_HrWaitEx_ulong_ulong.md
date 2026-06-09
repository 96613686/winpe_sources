# CBaseWorkObject::HrWaitEx(ulong,ulong)

- ea: `0x18011c460`
- end: `0x18011c6f8`
- name: `?HrWaitEx@CBaseWorkObject@@UEAAJKK@Z`
- size: `664`
- prototype: `__int64 __fastcall(CBaseWorkObject *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180118e20`
- `0x18011d820`

## callees

- `0x1800264b4`
- `0x1801156f0`
- `0x18011b650`
- `0x18011befc`
- `0x18011c32c`
- `0x18011c460`
- `0x180146090`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x18011c65c`
- `KERNEL32!ResetEvent` at `0x18011c65c`
- `KERNEL32!GetCurrentThreadId` at `0x18011c522`
- `KERNEL32!GetCurrentThreadId` at `0x18011c565`
- `KERNEL32!GetCurrentThreadId` at `0x18011c522`
- `KERNEL32!GetCurrentThreadId` at `0x18011c565`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18011c5e4`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18011c5e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c67f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c67f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBaseWorkObject::HrWaitEx(CThreadManager **this, int a2, int a3)
{
  void *v6; // rbx
  char v8; // bp
  char *v9; // rcx
  int v10; // edx
  _BYTE *v11; // r14
  struct CThreadState *ThreadState; // rsi
  __int64 v13; // rax
  CThreadManager *v14; // rax
  struct CBaseWorkObject *v15; // rdx
  int v16; // esi
  void *v17; // rcx
  __int16 v18; // [rsp+20h] [rbp-48h] BYREF
  void *v19; // [rsp+28h] [rbp-40h]
  int v20; // [rsp+34h] [rbp-34h]

  v6 = 0;
  if ( (a3 & 0xFFFFFFFC) != 0 )
  {
    MsoShipAssertTagProc(507552538);
    return 2147500037LL;
  }
  v8 = a3 & 1;
  if ( !a2 )
    goto LABEL_37;
  v9 = (char *)this + 60;
  if ( (*((_DWORD *)this + 15) & 0x1000000) != 0 )
  {
    if ( (*((_DWORD *)CBaseWorkObject::GetOwnerWorker((CBaseWorkObject *)this) + 15) & 0x8002) == 2 )
    {
      MsoShipAssertTagProc(507552537);
      return 2147500065LL;
    }
    v9 = (char *)this + 60;
  }
  v10 = *((_DWORD *)this + 15);
  v11 = (char *)this + 60;
  if ( (v10 & 0x8002) == 2 )
  {
    v11 = v9;
    if ( (v10 & 0x40000) != 0 )
    {
      MsoShipAssertTagProc(507552536);
      return 2147500065LL;
    }
  }
  if ( GetCurrentThreadId() == Mso::Threadpool::details::vdwTidMain && (*((_BYTE *)this + 60) & 2) != 0 )
  {
    MsoShipAssertTagProc(507552535);
    return 2147500037LL;
  }
  ThreadState = CThreadManager::GetThreadState(this[5]);
  if ( ThreadState )
  {
    if ( (*v11 & 2) != 0 && GetCurrentThreadId() == Mso::Threadpool::details::vdwTidMain )
    {
      MsoShipAssertTagProc(507552531);
      return 2147500037LL;
    }
    if ( (*((_DWORD *)ThreadState + 12)
       || (v13 = *((_QWORD *)ThreadState + 1)) == 0
       || (*(_DWORD *)(v13 + 60) & 0x600000) == 0)
      && (*((_DWORD *)this + 15) & 0x600000) != 0 )
    {
      MsoShipAssertTagProc(507552530);
    }
    if ( *((_QWORD *)ThreadState + 2) && (*((unsigned int (__fastcall **)(CThreadManager **))*this + 15))(this) )
    {
      MsoShipAssertTagProc(507552527);
      return 2147500037LL;
    }
  }
  v6 = malloc(0x38u);
  if ( v6 )
  {
    v14 = this[5];
    *((_QWORD *)v6 + 3) = 0;
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = v14;
    *((_DWORD *)v6 + 11) = 1;
    *((_BYTE *)v6 + 52) = 0;
    *((_DWORD *)v6 + 10) = a2;
    *((_DWORD *)v6 + 12) = a3;
    *((_QWORD *)v6 + 4) = this;
    v15 = 0;
    if ( ThreadState )
      v15 = (struct CBaseWorkObject *)*((_QWORD *)ThreadState + 1);
    v16 = CWaitObj::HrInit((CWaitObj *)v6, v15);
    if ( v16 < 0 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 11, 0xFFFFFFFF) == 1 )
      {
        v17 = (void *)*((_QWORD *)v6 + 1);
        if ( v17 )
        {
          if ( *((_BYTE *)v6 + 52) )
            ResetEvent(v17);
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)v6 + 2) + 80LL) + 32LL))(
            *(_QWORD *)(*((_QWORD *)v6 + 2) + 80LL),
            *((_QWORD *)v6 + 1));
        }
        free(v6);
      }
      return (unsigned int)v16;
    }
LABEL_37:
    if ( v8 )
      (*((void (__fastcall **)(CThreadManager **))*this + 32))(this);
    v18 = 256;
    v20 = 0;
    v19 = v6;
    CBaseWorkObject::AdjustBarrier(
      (CBaseWorkObject *)this,
      -(v8 != 0),
      (struct CBaseWorkObject::AdjustBarrierInOut *)&v18);
    return v20 != 0;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18011c460  mov     [rsp+arg_0], rbx
0x18011c465  mov     [rsp+arg_8], rbp
0x18011c46a  mov     [rsp+arg_18], rsi
0x18011c46f  push    rdi
0x18011c470  push    r12
0x18011c472  push    r13
0x18011c474  push    r14
0x18011c476  push    r15
0x18011c478  sub     rsp, 40h
0x18011c47c  mov     r15d, r8d
0x18011c47f  mov     r12d, edx
0x18011c482  mov     rdi, rcx
0x18011c485  xor     r13d, r13d
0x18011c488  mov     ebx, r13d
0x18011c48b  test    r8d, 0FFFFFFFCh
0x18011c492  jz      short loc_18011C4A8
0x18011c494  mov     ecx, 1E40A31Ah
0x18011c499  call    MsoShipAssertTagProc
0x18011c49e  mov     eax, 80004005h
0x18011c4a3  jmp     loc_18011C6D8
0x18011c4a8  mov     ebp, r15d
0x18011c4ab  and     ebp, 1
0x18011c4ae  test    r12d, r12d
0x18011c4b1  jz      loc_18011C68F
0x18011c4b7  add     rcx, 3Ch ; '<'
0x18011c4bb  test    dword ptr [rdi+3Ch], 1000000h
0x18011c4c2  jz      short loc_18011C4F2
0x18011c4c4  mov     rcx, rdi; this
0x18011c4c7  call    ?GetOwnerWorker@CBaseWorkObject@@IEBAPEAV1@XZ; CBaseWorkObject::GetOwnerWorker(void)
0x18011c4cc  mov     ecx, [rax+3Ch]
0x18011c4cf  and     ecx, 8002h
0x18011c4d5  cmp     ecx, 2
0x18011c4d8  jnz     short loc_18011C4EE
0x18011c4da  mov     ecx, 1E40A319h
0x18011c4df  call    MsoShipAssertTagProc
0x18011c4e4  mov     eax, 80004021h
0x18011c4e9  jmp     loc_18011C6D8
0x18011c4ee  lea     rcx, [rdi+3Ch]
0x18011c4f2  mov     edx, [rdi+3Ch]
0x18011c4f5  lea     r14, [rdi+3Ch]
0x18011c4f9  mov     eax, edx
0x18011c4fb  and     eax, 8002h
0x18011c500  cmp     eax, 2
0x18011c503  jnz     short loc_18011C522
0x18011c505  mov     r14, rcx
0x18011c508  bt      edx, 12h
0x18011c50c  jnb     short loc_18011C522
0x18011c50e  mov     ecx, 1E40A318h
0x18011c513  call    MsoShipAssertTagProc
0x18011c518  mov     eax, 80004021h
0x18011c51d  jmp     loc_18011C6D8
0x18011c522  call    cs:__imp_GetCurrentThreadId
0x18011c528  cmp     eax, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; ulong Mso::Threadpool::details::vdwTidMain
0x18011c52e  jnz     short loc_18011C54A
0x18011c530  test    byte ptr [rdi+3Ch], 2
0x18011c534  jz      short loc_18011C54A
0x18011c536  mov     ecx, 1E40A317h
0x18011c53b  call    MsoShipAssertTagProc
0x18011c540  mov     eax, 80004005h
0x18011c545  jmp     loc_18011C6D8
0x18011c54a  mov     rcx, [rdi+28h]; this
0x18011c54e  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x18011c553  mov     rsi, rax
0x18011c556  test    rax, rax
0x18011c559  jz      loc_18011C5DF
0x18011c55f  test    byte ptr [r14], 2
0x18011c563  jz      short loc_18011C587
0x18011c565  call    cs:__imp_GetCurrentThreadId
0x18011c56b  cmp     eax, cs:?vdwTidMain@details@Threadpool@Mso@@3KA; ulong Mso::Threadpool::details::vdwTidMain
0x18011c571  jnz     short loc_18011C587
0x18011c573  mov     ecx, 1E40A313h
0x18011c578  call    MsoShipAssertTagProc
0x18011c57d  mov     eax, 80004005h
0x18011c582  jmp     loc_18011C6D8
0x18011c587  cmp     [rsi+30h], ebx
0x18011c58a  jnz     short loc_18011C59E
0x18011c58c  mov     rax, [rsi+8]
0x18011c590  test    rax, rax
0x18011c593  jz      short loc_18011C59E
0x18011c595  test    dword ptr [rax+3Ch], 600000h
0x18011c59c  jnz     short loc_18011C5B1
0x18011c59e  test    dword ptr [rdi+3Ch], 600000h
0x18011c5a5  jz      short loc_18011C5B1
0x18011c5a7  mov     ecx, 1E40A312h
0x18011c5ac  call    MsoShipAssertTagProc
0x18011c5b1  cmp     [rsi+10h], rbx
0x18011c5b5  jz      short loc_18011C5DF
0x18011c5b7  mov     rax, [rdi]
0x18011c5ba  mov     rcx, rdi
0x18011c5bd  mov     rax, [rax+78h]
0x18011c5c1  call    cs:__guard_dispatch_icall_fptr
0x18011c5c7  test    eax, eax
0x18011c5c9  jz      short loc_18011C5DF
0x18011c5cb  mov     ecx, 1E40A30Fh
0x18011c5d0  call    MsoShipAssertTagProc
0x18011c5d5  mov     eax, 80004005h
0x18011c5da  jmp     loc_18011C6D8
0x18011c5df  mov     ecx, 38h ; '8'; Size
0x18011c5e4  call    cs:__imp_malloc
0x18011c5ea  mov     rbx, rax
0x18011c5ed  test    rax, rax
0x18011c5f0  jz      loc_18011C688
0x18011c5f6  mov     rax, [rdi+28h]
0x18011c5fa  mov     [rbx+18h], r13
0x18011c5fe  mov     [rbx], r13
0x18011c601  mov     [rbx+8], r13
0x18011c605  mov     [rbx+10h], rax
0x18011c609  mov     dword ptr [rbx+2Ch], 1
0x18011c610  mov     byte ptr [rbx+34h], 0
0x18011c614  mov     [rbx+28h], r12d
0x18011c618  mov     [rbx+30h], r15d
0x18011c61c  mov     [rbx+20h], rdi
0x18011c620  test    rsi, rsi
0x18011c623  mov     rdx, r13
0x18011c626  jz      short loc_18011C62C
0x18011c628  mov     rdx, [rsi+8]; struct CBaseWorkObject *
0x18011c62c  mov     rcx, rbx; this
0x18011c62f  call    ?HrInit@CWaitObj@@QEAAJPEAVCBaseWorkObject@@@Z; CWaitObj::HrInit(CBaseWorkObject *)
0x18011c634  mov     esi, eax
0x18011c636  test    eax, eax
0x18011c638  jns     short loc_18011C68F
0x18011c63a  mov     ecx, 0FFFFFFFFh
0x18011c63f  lock xadd [rbx+2Ch], ecx
0x18011c644  cmp     ecx, 1
0x18011c647  jnz     loc_18011C6D6
0x18011c64d  mov     rcx, [rbx+8]; hEvent
0x18011c651  test    rcx, rcx
0x18011c654  jz      short loc_18011C67C
0x18011c656  cmp     byte ptr [rbx+34h], 0
0x18011c65a  jz      short loc_18011C662
0x18011c65c  call    cs:__imp_ResetEvent
0x18011c662  mov     rax, [rbx+10h]
0x18011c666  mov     rcx, [rax+50h]
0x18011c66a  mov     rax, [rcx]
0x18011c66d  mov     rdx, [rbx+8]
0x18011c671  mov     rax, [rax+20h]
0x18011c675  call    cs:__guard_dispatch_icall_fptr
0x18011c67b  nop
0x18011c67c  mov     rcx, rbx; Block
0x18011c67f  call    cs:__imp_free
0x18011c685  nop
0x18011c686  jmp     short loc_18011C6D6
0x18011c688  mov     esi, 8007000Eh
0x18011c68d  jmp     short loc_18011C6D6
0x18011c68f  test    bpl, bpl
0x18011c692  jz      short loc_18011C6A7
0x18011c694  mov     rax, [rdi]
0x18011c697  mov     rcx, rdi
0x18011c69a  mov     rax, [rax+100h]
0x18011c6a1  call    cs:__guard_dispatch_icall_fptr
0x18011c6a7  mov     [rsp+68h+var_48], 100h
0x18011c6ae  mov     [rsp+68h+var_34], r13d
0x18011c6b3  mov     [rsp+68h+var_40], rbx
0x18011c6b8  neg     bpl
0x18011c6bb  sbb     edx, edx; unsigned int
0x18011c6bd  lea     r8, [rsp+68h+var_48]; struct CBaseWorkObject::AdjustBarrierInOut *
0x18011c6c2  mov     rcx, rdi; this
0x18011c6c5  call    ?AdjustBarrier@CBaseWorkObject@@QEAAXKPEAUAdjustBarrierInOut@1@@Z; CBaseWorkObject::AdjustBarrier(ulong,CBaseWorkObject::AdjustBarrierInOut *)
0x18011c6ca  mov     esi, r13d
0x18011c6cd  cmp     [rsp+68h+var_34], r13d
0x18011c6d2  setnz   sil
0x18011c6d6  mov     eax, esi
0x18011c6d8  mov     rbx, [rsp+68h+arg_0]
0x18011c6dd  mov     rbp, [rsp+68h+arg_8]
0x18011c6e2  mov     rsi, [rsp+68h+arg_18]
0x18011c6ea  add     rsp, 40h
0x18011c6ee  pop     r15
0x18011c6f0  pop     r14
0x18011c6f2  pop     r13
0x18011c6f4  pop     r12
0x18011c6f6  pop     rdi
0x18011c6f7  retn
```
