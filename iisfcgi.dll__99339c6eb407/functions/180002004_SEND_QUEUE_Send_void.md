# SEND_QUEUE::Send(void)

- ea: `0x180002004`
- end: `0x180002120`
- name: `?Send@SEND_QUEUE@@AEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(SEND_QUEUE *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e7c`
- `0x180002128`
- `0x180002250`

## callees

- `0x180001d50`
- `0x180002004`
- `0x180009128`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000201f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000201f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000210f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800020d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000210f`

## pseudocode

```c
__int64 __fastcall SEND_QUEUE::Send(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  SEND_QUEUE **p_LockSemaphore; // rdi
  SEND_QUEUE *LockSemaphore; // rdx
  unsigned int v5; // ebp
  SEND_QUEUE *v6; // rax
  SEND_QUEUE **v7; // rax
  int v8; // edi
  _OWORD v10[3]; // [rsp+20h] [rbp-38h] BYREF

  v1 = this + 1;
  v10[0] = 0;
  EnterCriticalSection(this + 1);
  if ( !HIDWORD(this[2].LockSemaphore)
    || (p_LockSemaphore = (SEND_QUEUE **)&this->LockSemaphore,
        LockSemaphore = (SEND_QUEUE *)this->LockSemaphore,
        LockSemaphore == (SEND_QUEUE *)&this->LockSemaphore) )
  {
    v8 = 0;
    LeaveCriticalSection(v1);
  }
  else
  {
    v5 = 0;
    *((_QWORD *)&v10[0] + 1) = v10;
    *(_QWORD *)&v10[0] = v10;
    do
    {
      if ( *((SEND_QUEUE ***)LockSemaphore + 1) != p_LockSemaphore
        || (v6 = *(SEND_QUEUE **)LockSemaphore, *(SEND_QUEUE **)(*(_QWORD *)LockSemaphore + 8LL) != LockSemaphore) )
      {
LABEL_12:
        __fastfail(3u);
      }
      *p_LockSemaphore = v6;
      *((_QWORD *)v6 + 1) = p_LockSemaphore;
      HIDWORD(this->OwningThread) -= *((_DWORD *)LockSemaphore - 6);
      if ( *((_DWORD *)LockSemaphore - 1) == 6 )
      {
        FCGI_BUFFER::Free((SEND_QUEUE *)((char *)LockSemaphore - 32));
        v5 = 1;
        HIDWORD(this[2].OwningThread) = 0;
      }
      else
      {
        v7 = (SEND_QUEUE **)*((_QWORD *)&v10[0] + 1);
        if ( **((_OWORD ***)&v10[0] + 1) != v10 )
          goto LABEL_12;
        *((_QWORD *)LockSemaphore + 1) = *((_QWORD *)&v10[0] + 1);
        *(_QWORD *)LockSemaphore = v10;
        *v7 = LockSemaphore;
        *((_QWORD *)&v10[0] + 1) = LockSemaphore;
      }
      if ( !this[2].RecursionCount )
        break;
      LockSemaphore = *p_LockSemaphore;
    }
    while ( *p_LockSemaphore != (SEND_QUEUE *)p_LockSemaphore );
    HIDWORD(this[2].SpinCount) = 1;
    _InterlockedIncrement(&this[2].LockCount);
    LeaveCriticalSection(v1);
    v8 = (***(__int64 (__fastcall ****)(_QWORD, _OWORD *, _QWORD))&this->LockCount)(
           *(_QWORD *)&this->LockCount,
           v10,
           v5);
    if ( v8 < 0 )
    {
      HIDWORD(this[2].SpinCount) = 0;
      SEND_QUEUE::DereferenceSendQueue((SEND_QUEUE *)this);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002004  push    rbx
0x180002006  push    rbp
0x180002007  push    rsi
0x180002008  push    rdi
0x180002009  sub     rsp, 38h
0x18000200d  lea     rsi, [rcx+28h]
0x180002011  mov     rbx, rcx
0x180002014  xorps   xmm0, xmm0
0x180002017  mov     rcx, rsi; lpCriticalSection
0x18000201a  movups  [rsp+58h+var_38], xmm0
0x18000201f  call    cs:__imp_EnterCriticalSection
0x180002025  cmp     dword ptr [rbx+6Ch], 0
0x180002029  jz      loc_18000210A
0x18000202f  lea     rdi, [rbx+18h]
0x180002033  mov     rdx, [rdi]
0x180002036  cmp     rdx, rdi
0x180002039  jz      loc_18000210A
0x18000203f  lea     rax, [rsp+58h+var_38]
0x180002044  xor     ebp, ebp
0x180002046  mov     qword ptr [rsp+58h+var_38+8], rax
0x18000204b  lea     rax, [rsp+58h+var_38]
0x180002050  mov     qword ptr [rsp+58h+var_38], rax
0x180002055  jmp     short loc_1800020BB
0x180002057  mov     rax, [rdx]
0x18000205a  cmp     [rax+8], rdx
0x18000205e  jnz     short loc_1800020C1
0x180002060  mov     [rdi], rax
0x180002063  lea     rcx, [rdx-20h]; this
0x180002067  mov     [rax+8], rdi
0x18000206b  mov     eax, [rcx+8]
0x18000206e  sub     [rbx+14h], eax
0x180002071  cmp     dword ptr [rcx+1Ch], 6
0x180002075  jnz     short loc_18000208A
0x180002077  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000207c  mov     ebp, 1
0x180002081  mov     dword ptr [rbx+64h], 0
0x180002088  jmp     short loc_1800020AD
0x18000208a  mov     rax, qword ptr [rsp+58h+var_38+8]
0x18000208f  lea     rcx, [rsp+58h+var_38]
0x180002094  cmp     [rax], rcx
0x180002097  jnz     short loc_1800020C1
0x180002099  mov     [rdx+8], rax
0x18000209d  lea     rcx, [rsp+58h+var_38]
0x1800020a2  mov     [rdx], rcx
0x1800020a5  mov     [rax], rdx
0x1800020a8  mov     qword ptr [rsp+58h+var_38+8], rdx
0x1800020ad  cmp     dword ptr [rbx+5Ch], 0
0x1800020b1  jz      short loc_1800020C8
0x1800020b3  mov     rdx, [rdi]
0x1800020b6  cmp     rdx, rdi
0x1800020b9  jz      short loc_1800020C8
0x1800020bb  cmp     [rdx+8], rdi
0x1800020bf  jz      short loc_180002057
0x1800020c1  mov     ecx, 3
0x1800020c6  int     29h; Win8: RtlFailFast(ecx)
0x1800020c8  mov     dword ptr [rbx+74h], 1
0x1800020cf  lock inc dword ptr [rbx+58h]
0x1800020d3  mov     rcx, rsi; lpCriticalSection
0x1800020d6  call    cs:__imp_LeaveCriticalSection
0x1800020dc  mov     rcx, [rbx+8]
0x1800020e0  lea     rdx, [rsp+58h+var_38]
0x1800020e5  mov     r8d, ebp
0x1800020e8  mov     rax, [rcx]
0x1800020eb  mov     rax, [rax]
0x1800020ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f3  mov     edi, eax
0x1800020f5  test    eax, eax
0x1800020f7  jns     short loc_180002115
0x1800020f9  mov     rcx, rbx; this
0x1800020fc  mov     dword ptr [rbx+74h], 0
0x180002103  call    ?DereferenceSendQueue@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::DereferenceSendQueue(void)
0x180002108  jmp     short loc_180002115
0x18000210a  xor     edi, edi
0x18000210c  mov     rcx, rsi; lpCriticalSection
0x18000210f  call    cs:__imp_LeaveCriticalSection
0x180002115  mov     eax, edi
0x180002117  add     rsp, 38h
0x18000211b  pop     rdi
0x18000211c  pop     rsi
0x18000211d  pop     rbp
0x18000211e  pop     rbx
0x18000211f  retn
```
