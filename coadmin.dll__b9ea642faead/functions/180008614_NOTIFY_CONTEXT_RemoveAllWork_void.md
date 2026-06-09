# NOTIFY_CONTEXT::RemoveAllWork(void)

- ea: `0x180008614`
- end: `0x1800087e4`
- name: `?RemoveAllWork@NOTIFY_CONTEXT@@SAXXZ`
- size: `464`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000dc5c`

## callees

- `0x1800010a4`
- `0x180001c3c`
- `0x180008614`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800086ca`
- `KERNEL32!LeaveCriticalSection` at `0x180008765`
- `KERNEL32!LeaveCriticalSection` at `0x1800086ca`
- `KERNEL32!LeaveCriticalSection` at `0x180008765`
- `KERNEL32!EnterCriticalSection` at `0x180008646`
- `KERNEL32!EnterCriticalSection` at `0x180008743`
- `KERNEL32!EnterCriticalSection` at `0x180008646`
- `KERNEL32!EnterCriticalSection` at `0x180008743`
- `KERNEL32!Sleep` at `0x180008736`
- `KERNEL32!Sleep` at `0x1800087ca`
- `KERNEL32!Sleep` at `0x180008736`
- `KERNEL32!Sleep` at `0x1800087ca`
- `KERNEL32!GetCurrentThreadId` at `0x1800087ae`
- `KERNEL32!GetCurrentThreadId` at `0x1800087ae`

## pseudocode

```c
void NOTIFY_CONTEXT::RemoveAllWork(void)
{
  int v0; // esi
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v2; // rcx
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY **p_Flink; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _QWORD *v7; // rcx
  _QWORD *v8; // rdi
  struct _LIST_ENTRY *v9; // rbx
  struct _LIST_ENTRY *v10; // rdi
  struct _LIST_ENTRY *v11; // rax
  NOTIFY_CONTEXT *p_Blink; // rbx
  _QWORD *v13; // [rsp+20h] [rbp-38h] BYREF
  struct _LIST_ENTRY *v14; // [rsp+28h] [rbp-30h]

  if ( NOTIFY_CONTEXT::s_fInitializedCritSec )
  {
    v0 = 0;
    v14 = (struct _LIST_ENTRY *)&v13;
    v13 = &v13;
    EnterCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    Flink = NOTIFY_CONTEXT::s_listEntry.Flink;
    if ( NOTIFY_CONTEXT::s_listEntry.Flink != &NOTIFY_CONTEXT::s_listEntry )
    {
      do
      {
        v2 = Flink->Flink;
        if ( LODWORD(Flink[-1].Blink) )
        {
          if ( v2->Blink != Flink )
            goto LABEL_26;
          Blink = Flink->Blink;
          if ( Blink->Flink != Flink )
            goto LABEL_26;
          Blink->Flink = v2;
          v2->Blink = Blink;
          Flink->Blink = Flink;
          Flink->Flink = Flink;
          p_Flink = &v14->Flink;
          if ( v14->Flink != (struct _LIST_ENTRY *)&v13 )
            goto LABEL_26;
          Flink->Blink = v14;
          Flink->Flink = (struct _LIST_ENTRY *)&v13;
          *p_Flink = Flink;
          v14 = Flink;
        }
        else
        {
          v0 = 1;
        }
        Flink = v2;
      }
      while ( v2 != &NOTIFY_CONTEXT::s_listEntry );
    }
    LeaveCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    v5 = v13;
    if ( v13 != &v13 )
    {
      while ( 1 )
      {
        v6 = (_QWORD *)*v5;
        if ( *(_QWORD **)(*v5 + 8LL) != v5 )
          break;
        v7 = (_QWORD *)v5[1];
        if ( (_QWORD *)*v7 != v5 )
          break;
        *v7 = v6;
        v8 = v5 - 5;
        v6[1] = v7;
        v5[1] = v5;
        *v5 = v5;
        if ( v5 != (_QWORD *)40 )
        {
          NOTIFY_CONTEXT::~NOTIFY_CONTEXT((NOTIFY_CONTEXT *)(v5 - 5));
          operator delete(v8);
        }
        v5 = v6;
        if ( v6 == &v13 )
          goto LABEL_16;
      }
LABEL_26:
      __fastfail(3u);
    }
LABEL_16:
    if ( v0 )
      Sleep(0x3E8u);
    EnterCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    v9 = NOTIFY_CONTEXT::s_listEntry.Flink;
    qword_180016ED8 = (__int64)&NOTIFY_CONTEXT::s_listEntry;
    NOTIFY_CONTEXT::s_listEntry.Flink = &NOTIFY_CONTEXT::s_listEntry;
    LeaveCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    if ( v9 != &NOTIFY_CONTEXT::s_listEntry )
    {
      do
      {
        v10 = v9->Flink;
        if ( v9->Flink->Blink != v9 )
          goto LABEL_26;
        v11 = v9->Blink;
        if ( v11->Flink != v9 )
          goto LABEL_26;
        v11->Flink = v10;
        v10->Blink = v11;
        v9->Blink = v9;
        v9->Flink = v9;
        p_Blink = (NOTIFY_CONTEXT *)&v9[-3].Blink;
        if ( p_Blink )
        {
          NOTIFY_CONTEXT::~NOTIFY_CONTEXT(p_Blink);
          operator delete(p_Blink);
        }
        v9 = v10;
      }
      while ( v10 != &NOTIFY_CONTEXT::s_listEntry );
    }
    if ( NOTIFY_CONTEXT::s_dwThreadId != GetCurrentThreadId() )
    {
      while ( NOTIFY_CONTEXT::s_pCurrentlyWorkingOn )
        Sleep(0x64u);
    }
  }
}

```

## disassembly

```asm
0x180008614  mov     r11, rsp
0x180008617  push    rbx
0x180008618  push    rsi
0x180008619  push    rdi
0x18000861a  push    r14
0x18000861c  sub     rsp, 38h
0x180008620  cmp     cs:?s_fInitializedCritSec@NOTIFY_CONTEXT@@0HA, 0; int NOTIFY_CONTEXT::s_fInitializedCritSec
0x180008627  jz      loc_1800087DA
0x18000862d  lea     rax, [r11-38h]
0x180008631  xor     esi, esi
0x180008633  mov     [r11-30h], rax
0x180008637  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000863e  lea     rax, [r11-38h]
0x180008642  mov     [r11-38h], rax
0x180008646  call    cs:__imp_EnterCriticalSection
0x18000864c  mov     rax, cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180008653  lea     r14, ?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x18000865a  cmp     rax, r14
0x18000865d  jz      short loc_1800086C3
0x18000865f  cmp     dword ptr [rax-8], 0
0x180008663  mov     rcx, [rax]
0x180008666  jz      short loc_1800086B6
0x180008668  cmp     [rcx+8], rax
0x18000866c  jnz     loc_1800087BE
0x180008672  mov     rdx, [rax+8]
0x180008676  cmp     [rdx], rax
0x180008679  jnz     loc_1800087BE
0x18000867f  mov     [rdx], rcx
0x180008682  lea     r8, [rsp+58h+var_38]
0x180008687  mov     [rcx+8], rdx
0x18000868b  mov     [rax+8], rax
0x18000868f  mov     [rax], rax
0x180008692  mov     rdx, [rsp+58h+var_30]
0x180008697  cmp     [rdx], r8
0x18000869a  jnz     loc_1800087BE
0x1800086a0  mov     [rax+8], rdx
0x1800086a4  lea     r8, [rsp+58h+var_38]
0x1800086a9  mov     [rax], r8
0x1800086ac  mov     [rdx], rax
0x1800086af  mov     [rsp+58h+var_30], rax
0x1800086b4  jmp     short loc_1800086BB
0x1800086b6  mov     esi, 1
0x1800086bb  mov     rax, rcx
0x1800086be  cmp     rcx, r14
0x1800086c1  jnz     short loc_18000865F
0x1800086c3  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800086ca  call    cs:__imp_LeaveCriticalSection
0x1800086d0  mov     rax, [rsp+58h+var_38]
0x1800086d5  lea     rcx, [rsp+58h+var_38]
0x1800086da  cmp     rax, rcx
0x1800086dd  jz      short loc_18000872D
0x1800086df  mov     rbx, [rax]
0x1800086e2  cmp     [rbx+8], rax
0x1800086e6  jnz     loc_1800087BE
0x1800086ec  mov     rcx, [rax+8]
0x1800086f0  cmp     [rcx], rax
0x1800086f3  jnz     loc_1800087BE
0x1800086f9  mov     [rcx], rbx
0x1800086fc  lea     rdi, [rax-28h]
0x180008700  mov     [rbx+8], rcx
0x180008704  mov     [rax+8], rax
0x180008708  mov     [rax], rax
0x18000870b  test    rdi, rdi
0x18000870e  jz      short loc_180008720
0x180008710  mov     rcx, rdi; this
0x180008713  call    ??1NOTIFY_CONTEXT@@AEAA@XZ; NOTIFY_CONTEXT::~NOTIFY_CONTEXT(void)
0x180008718  mov     rcx, rdi; Block
0x18000871b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008720  lea     rcx, [rsp+58h+var_38]
0x180008725  mov     rax, rbx
0x180008728  cmp     rbx, rcx
0x18000872b  jnz     short loc_1800086DF
0x18000872d  test    esi, esi
0x18000872f  jz      short loc_18000873C
0x180008731  mov     ecx, 3E8h; dwMilliseconds
0x180008736  call    cs:__imp_Sleep
0x18000873c  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008743  call    cs:__imp_EnterCriticalSection
0x180008749  mov     rbx, cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180008750  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008757  mov     cs:qword_180016ED8, r14
0x18000875e  mov     cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A, r14; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180008765  call    cs:__imp_LeaveCriticalSection
0x18000876b  cmp     rbx, r14
0x18000876e  jz      short loc_1800087AE
0x180008770  mov     rdi, [rbx]
0x180008773  cmp     [rdi+8], rbx
0x180008777  jnz     short loc_1800087BE
0x180008779  mov     rax, [rbx+8]
0x18000877d  cmp     [rax], rbx
0x180008780  jnz     short loc_1800087BE
0x180008782  mov     [rax], rdi
0x180008785  mov     [rdi+8], rax
0x180008789  mov     [rbx+8], rbx
0x18000878d  mov     [rbx], rbx
0x180008790  add     rbx, 0FFFFFFFFFFFFFFD8h
0x180008794  jz      short loc_1800087A6
0x180008796  mov     rcx, rbx; this
0x180008799  call    ??1NOTIFY_CONTEXT@@AEAA@XZ; NOTIFY_CONTEXT::~NOTIFY_CONTEXT(void)
0x18000879e  mov     rcx, rbx; Block
0x1800087a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800087a6  mov     rbx, rdi
0x1800087a9  cmp     rdi, r14
0x1800087ac  jnz     short loc_180008770
0x1800087ae  call    cs:__imp_GetCurrentThreadId
0x1800087b4  cmp     cs:?s_dwThreadId@NOTIFY_CONTEXT@@0KA, eax; ulong NOTIFY_CONTEXT::s_dwThreadId
0x1800087ba  jz      short loc_1800087DA
0x1800087bc  jmp     short loc_1800087D0
0x1800087be  mov     ecx, 3
0x1800087c3  int     29h; Win8: RtlFailFast(ecx)
0x1800087c5  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800087ca  call    cs:__imp_Sleep
0x1800087d0  cmp     cs:?s_pCurrentlyWorkingOn@NOTIFY_CONTEXT@@0PEAV1@EA, 0; NOTIFY_CONTEXT * NOTIFY_CONTEXT::s_pCurrentlyWorkingOn
0x1800087d8  jnz     short loc_1800087C5
0x1800087da  add     rsp, 38h
0x1800087de  pop     r14
0x1800087e0  pop     rdi
0x1800087e1  pop     rsi
0x1800087e2  pop     rbx
0x1800087e3  retn
```
