# CreatePcClock(IReferenceClock * *,CMasterClock *)

- ea: `0x180015a60`
- end: `0x180015b49`
- name: `?CreatePcClock@@YAJPEAPEAUIReferenceClock@@PEAVCMasterClock@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct IReferenceClock **, struct CMasterClock *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800012c4`
- `0x180015a1c`
- `0x180015a60`
- `0x180015b50`
- `0x180016140`
- `0x1800217b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015a76`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015a76`

## pseudocode

```c
__int64 __fastcall CreatePcClock(struct IReferenceClock **a1, struct CMasterClock *a2)
{
  volatile signed __int32 *v3; // rax
  CPcClock *v4; // rcx
  volatile signed __int32 *v5; // rbx
  int PcClockShared; // esi
  unsigned int v8; // edi

  v3 = (volatile signed __int32 *)malloc(0x10u);
  v5 = v3;
  if ( !v3 )
    return 2147942414LL;
  *((_DWORD *)v3 + 2) = 1;
  *(_QWORD *)v3 = &CPcClock::`vftable';
  if ( _InterlockedIncrement(&CPcClock::m_lSharedMemoryInitialized) == 1
    && (PcClockShared = CPcClock::CreatePcClockShared(v4), PcClockShared < 0) )
  {
    CPcClock::~CPcClock((CPcClock *)v5);
    operator delete((void *)v5);
    return (unsigned int)PcClockShared;
  }
  else
  {
    if ( a1 )
    {
      *a1 = 0;
      if ( !memcmp_0(&IID_IReferenceClock, &IID_IUnknown, 0x10u)
        || !memcmp_0(&IID_IReferenceClock, &IID_IReferenceClock, 0x10u) )
      {
        *a1 = (struct IReferenceClock *)v5;
        _InterlockedIncrement(v5 + 2);
        v8 = 0;
      }
      else
      {
        v8 = -2147467262;
      }
    }
    else
    {
      v8 = -2147467261;
    }
    CPcClock::Release((CPcClock *)v5);
    return v8;
  }
}

```

## disassembly

```asm
0x180015a60  push    rbx
0x180015a62  push    rsi
0x180015a63  push    rdi
0x180015a64  push    r14
0x180015a66  sub     rsp, 28h
0x180015a6a  mov     rdi, rcx
0x180015a6d  mov     r14d, 10h
0x180015a73  mov     ecx, r14d; Size
0x180015a76  call    cs:__imp_malloc
0x180015a7c  mov     [rsp+48h+arg_10], rax
0x180015a81  mov     rbx, rax
0x180015a84  test    rax, rax
0x180015a87  jz      loc_180015B3A
0x180015a8d  mov     dword ptr [rbx+8], 1
0x180015a94  lea     rax, ??_7CPcClock@@6B@; const CPcClock::`vftable'
0x180015a9b  mov     [rbx], rax
0x180015a9e  test    rbx, rbx
0x180015aa1  jz      loc_180015B3A
0x180015aa7  lea     eax, [r14-0Fh]
0x180015aab  lock xadd cs:?m_lSharedMemoryInitialized@CPcClock@@0JA, eax; long CPcClock::m_lSharedMemoryInitialized
0x180015ab3  inc     eax
0x180015ab5  cmp     eax, 1
0x180015ab8  jnz     short loc_180015ADC
0x180015aba  call    ?CreatePcClockShared@CPcClock@@AEAAJXZ; CPcClock::CreatePcClockShared(void)
0x180015abf  mov     esi, eax
0x180015ac1  test    eax, eax
0x180015ac3  jns     short loc_180015ADC
0x180015ac5  mov     rcx, rbx; this
0x180015ac8  call    ??1CPcClock@@QEAA@XZ; CPcClock::~CPcClock(void)
0x180015acd  mov     edx, r14d; unsigned __int64
0x180015ad0  mov     rcx, rbx; void *
0x180015ad3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015ad8  mov     eax, esi
0x180015ada  jmp     short loc_180015B3F
0x180015adc  test    rdi, rdi
0x180015adf  jnz     short loc_180015AE8
0x180015ae1  mov     edi, 80004003h
0x180015ae6  jmp     short loc_180015B2E
0x180015ae8  lea     rsi, IID_IReferenceClock
0x180015aef  mov     qword ptr [rdi], 0
0x180015af6  mov     rcx, rsi; Buf1
0x180015af9  lea     rdx, IID_IUnknown; Buf2
0x180015b00  mov     r8, r14; Size
0x180015b03  call    memcmp_0
0x180015b08  test    eax, eax
0x180015b0a  jz      short loc_180015B25
0x180015b0c  mov     r8, r14; Size
0x180015b0f  mov     rdx, rsi; Buf2
0x180015b12  mov     rcx, rsi; Buf1
0x180015b15  call    memcmp_0
0x180015b1a  test    eax, eax
0x180015b1c  jz      short loc_180015B25
0x180015b1e  mov     edi, 80004002h
0x180015b23  jmp     short loc_180015B2E
0x180015b25  mov     [rdi], rbx
0x180015b28  lock inc dword ptr [rbx+8]
0x180015b2c  xor     edi, edi
0x180015b2e  mov     rcx, rbx; this
0x180015b31  call    ?Release@CPcClock@@UEAAKXZ; CPcClock::Release(void)
0x180015b36  mov     eax, edi
0x180015b38  jmp     short loc_180015B3F
0x180015b3a  mov     eax, 8007000Eh
0x180015b3f  add     rsp, 28h
0x180015b43  pop     r14
0x180015b45  pop     rdi
0x180015b46  pop     rsi
0x180015b47  pop     rbx
0x180015b48  retn
```
