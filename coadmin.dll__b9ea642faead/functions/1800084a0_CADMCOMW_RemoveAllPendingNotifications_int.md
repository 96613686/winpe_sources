# CADMCOMW::RemoveAllPendingNotifications(int)

- ea: `0x1800084a0`
- end: `0x18000860e`
- name: `?RemoveAllPendingNotifications@CADMCOMW@@QEAAJH@Z`
- size: `366`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800097e4`
- `0x18000d890`

## callees

- `0x1800010a4`
- `0x180001c3c`
- `0x1800084a0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008551`
- `KERNEL32!LeaveCriticalSection` at `0x180008551`
- `KERNEL32!EnterCriticalSection` at `0x1800084d4`
- `KERNEL32!EnterCriticalSection` at `0x1800084d4`
- `KERNEL32!Sleep` at `0x1800085fb`
- `KERNEL32!Sleep` at `0x1800085fb`
- `KERNEL32!GetCurrentThreadId` at `0x1800085b0`
- `KERNEL32!GetCurrentThreadId` at `0x1800085b0`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800085eb`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800085eb`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800085c5`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800085c5`

## pseudocode

```c
__int64 __fastcall CADMCOMW::RemoveAllPendingNotifications(CADMCOMW *this, int a2)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v5; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY **p_Flink; // r8
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rcx
  _QWORD *v11; // rdi
  CADMCOMW *v12; // rbx
  _QWORD *v14; // [rsp+20h] [rbp-38h] BYREF
  struct _LIST_ENTRY *v15; // [rsp+28h] [rbp-30h]

  if ( NOTIFY_CONTEXT::s_fInitializedCritSec )
  {
    v15 = (struct _LIST_ENTRY *)&v14;
    v14 = &v14;
    EnterCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    Flink = NOTIFY_CONTEXT::s_listEntry.Flink;
    if ( NOTIFY_CONTEXT::s_listEntry.Flink != &NOTIFY_CONTEXT::s_listEntry )
    {
      do
      {
        v5 = Flink->Flink;
        if ( (CADMCOMW *)Flink[-2].Flink == this )
        {
          if ( v5->Blink != Flink )
            goto LABEL_19;
          Blink = Flink->Blink;
          if ( Blink->Flink != Flink )
            goto LABEL_19;
          Blink->Flink = v5;
          v5->Blink = Blink;
          Flink->Blink = Flink;
          Flink->Flink = Flink;
          p_Flink = &v15->Flink;
          if ( v15->Flink != (struct _LIST_ENTRY *)&v14 )
            goto LABEL_19;
          Flink->Blink = v15;
          Flink->Flink = (struct _LIST_ENTRY *)&v14;
          *p_Flink = Flink;
          v15 = Flink;
        }
        Flink = v5;
      }
      while ( v5 != &NOTIFY_CONTEXT::s_listEntry );
    }
    LeaveCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    v8 = v14;
    if ( v14 != &v14 )
    {
      while ( 1 )
      {
        v9 = (_QWORD *)*v8;
        if ( *(_QWORD **)(*v8 + 8LL) != v8 )
          break;
        v10 = (_QWORD *)v8[1];
        if ( (_QWORD *)*v10 != v8 )
          break;
        *v10 = v9;
        v11 = v8 - 5;
        v9[1] = v10;
        v8[1] = v8;
        *v8 = v8;
        if ( v8 != (_QWORD *)40 )
        {
          NOTIFY_CONTEXT::~NOTIFY_CONTEXT((NOTIFY_CONTEXT *)(v8 - 5));
          operator delete(v11);
        }
        v8 = v9;
        if ( v9 == &v14 )
          goto LABEL_15;
      }
LABEL_19:
      __fastfail(3u);
    }
LABEL_15:
    if ( a2 && NOTIFY_CONTEXT::s_dwThreadId != GetCurrentThreadId() )
    {
      while ( 1 )
      {
        CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
        v12 = NOTIFY_CONTEXT::s_pCurrentlyWorkingOn;
        if ( NOTIFY_CONTEXT::s_pCurrentlyWorkingOn )
          v12 = (CADMCOMW *)*((_QWORD *)NOTIFY_CONTEXT::s_pCurrentlyWorkingOn + 1);
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
        if ( this != v12 )
          break;
        Sleep(0x64u);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800084a0  mov     r11, rsp
0x1800084a3  push    rbx
0x1800084a4  push    rbp
0x1800084a5  push    rsi
0x1800084a6  push    rdi
0x1800084a7  sub     rsp, 38h
0x1800084ab  cmp     cs:?s_fInitializedCritSec@NOTIFY_CONTEXT@@0HA, 0; int NOTIFY_CONTEXT::s_fInitializedCritSec
0x1800084b2  mov     ebp, edx
0x1800084b4  mov     rsi, rcx
0x1800084b7  jz      loc_180008603
0x1800084bd  lea     rax, [r11-38h]
0x1800084c1  mov     [r11-30h], rax
0x1800084c5  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800084cc  lea     rax, [r11-38h]
0x1800084d0  mov     [r11-38h], rax
0x1800084d4  call    cs:__imp_EnterCriticalSection
0x1800084da  mov     rax, cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x1800084e1  lea     r10, ?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x1800084e8  cmp     rax, r10
0x1800084eb  jz      short loc_18000854A
0x1800084ed  mov     rdx, [rax]
0x1800084f0  cmp     [rax-20h], rsi
0x1800084f4  jnz     short loc_180008542
0x1800084f6  cmp     [rdx+8], rax
0x1800084fa  jnz     loc_1800085DD
0x180008500  mov     rcx, [rax+8]
0x180008504  cmp     [rcx], rax
0x180008507  jnz     loc_1800085DD
0x18000850d  mov     [rcx], rdx
0x180008510  mov     [rdx+8], rcx
0x180008514  lea     rcx, [rsp+58h+var_38]
0x180008519  mov     [rax+8], rax
0x18000851d  mov     [rax], rax
0x180008520  mov     r8, [rsp+58h+var_30]
0x180008525  cmp     [r8], rcx
0x180008528  jnz     loc_1800085DD
0x18000852e  mov     [rax+8], r8
0x180008532  lea     r9, [rsp+58h+var_38]
0x180008537  mov     [rax], r9
0x18000853a  mov     [r8], rax
0x18000853d  mov     [rsp+58h+var_30], rax
0x180008542  mov     rax, rdx
0x180008545  cmp     rdx, r10
0x180008548  jnz     short loc_1800084ED
0x18000854a  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008551  call    cs:__imp_LeaveCriticalSection
0x180008557  mov     rax, [rsp+58h+var_38]
0x18000855c  lea     rcx, [rsp+58h+var_38]
0x180008561  cmp     rax, rcx
0x180008564  jz      short loc_1800085AC
0x180008566  mov     rbx, [rax]
0x180008569  cmp     [rbx+8], rax
0x18000856d  jnz     short loc_1800085DD
0x18000856f  mov     rcx, [rax+8]
0x180008573  cmp     [rcx], rax
0x180008576  jnz     short loc_1800085DD
0x180008578  mov     [rcx], rbx
0x18000857b  lea     rdi, [rax-28h]
0x18000857f  mov     [rbx+8], rcx
0x180008583  mov     [rax+8], rax
0x180008587  mov     [rax], rax
0x18000858a  test    rdi, rdi
0x18000858d  jz      short loc_18000859F
0x18000858f  mov     rcx, rdi; this
0x180008592  call    ??1NOTIFY_CONTEXT@@AEAA@XZ; NOTIFY_CONTEXT::~NOTIFY_CONTEXT(void)
0x180008597  mov     rcx, rdi; Block
0x18000859a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000859f  lea     rcx, [rsp+58h+var_38]
0x1800085a4  mov     rax, rbx
0x1800085a7  cmp     rbx, rcx
0x1800085aa  jnz     short loc_180008566
0x1800085ac  test    ebp, ebp
0x1800085ae  jz      short loc_180008603
0x1800085b0  call    cs:__imp_GetCurrentThreadId
0x1800085b6  cmp     cs:?s_dwThreadId@NOTIFY_CONTEXT@@0KA, eax; ulong NOTIFY_CONTEXT::s_dwThreadId
0x1800085bc  jz      short loc_180008603
0x1800085be  lea     rcx, ?s_LockCurrentlyWorkingOn@NOTIFY_CONTEXT@@0VCReaderWriterLock3@@A; CReaderWriterLock3 NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn
0x1800085c5  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800085cb  mov     rbx, cs:?s_pCurrentlyWorkingOn@NOTIFY_CONTEXT@@0PEAV1@EA; NOTIFY_CONTEXT * NOTIFY_CONTEXT::s_pCurrentlyWorkingOn
0x1800085d2  test    rbx, rbx
0x1800085d5  jz      short loc_1800085E4
0x1800085d7  mov     rbx, [rbx+8]
0x1800085db  jmp     short loc_1800085E4
0x1800085dd  mov     ecx, 3
0x1800085e2  int     29h; Win8: RtlFailFast(ecx)
0x1800085e4  lea     rcx, ?s_LockCurrentlyWorkingOn@NOTIFY_CONTEXT@@0VCReaderWriterLock3@@A; CReaderWriterLock3 NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn
0x1800085eb  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800085f1  cmp     rsi, rbx
0x1800085f4  jnz     short loc_180008603
0x1800085f6  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800085fb  call    cs:__imp_Sleep
0x180008601  jmp     short loc_1800085BE
0x180008603  xor     eax, eax
0x180008605  add     rsp, 38h
0x180008609  pop     rdi
0x18000860a  pop     rsi
0x18000860b  pop     rbp
0x18000860c  pop     rbx
0x18000860d  retn
```
