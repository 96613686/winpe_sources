# NOTIFICATION_THREAD::ProcessPollingList(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180051090`
- end: `0x180051188`
- name: `?ProcessPollingList@NOTIFICATION_THREAD@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `248`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180051414`

## callees

- `0x18004f600`
- `0x180050f6c`
- `0x18005104c`
- `0x180051090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800510d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005116e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800510d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005116e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800510ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051158`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800510ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051158`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18005112b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18005112b`

## pseudocode

```c
void __fastcall NOTIFICATION_THREAD::ProcessPollingList(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rsi
  _LIST_ENTRY *Flink; // rbx
  _LIST_ENTRY *v6; // rdi
  CONFIG_CACHE *v7; // rcx
  struct _LIST_ENTRY *v8; // rcx
  _LIST_ENTRY *Blink; // rax
  _LIST_ENTRY v10; // [rsp+20h] [rbp-18h] BYREF
  int v11; // [rsp+78h] [rbp+40h] BYREF

  v10.Blink = &v10;
  v4 = (RTL_SRWLOCK *)(Context + 8);
  v10.Flink = &v10;
  AcquireSRWLockExclusive((PSRWLOCK)Context + 1);
  NOTIFICATION_THREAD::MoveAndAppendList((struct _LIST_ENTRY *)Context + 1, &v10);
  ReleaseSRWLockExclusive(v4);
  Flink = v10.Flink;
  if ( v10.Flink != &v10 )
  {
    do
    {
      v6 = Flink - 6;
      if ( HIDWORD(Flink[-1].Flink)
        || (v7 = (CONFIG_CACHE *)*((_QWORD *)Context + 4),
            v11 = 0,
            (int)CONFIG_CACHE::HandleChangeNotification(v7, (struct CONFIG_MONITOR *)&Flink[-6], &v11) < 0)
        || v11 )
      {
        v8 = Flink->Flink;
        if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
          __fastfail(3u);
        Blink->Flink = v8;
        Flink = Blink;
        v8->Blink = Blink;
        CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&v6[5].Blink);
        NOTIFICATION_THREAD::FreeMonitor((NOTIFICATION_THREAD *)Context, (struct CONFIG_MONITOR *)v6);
      }
      Flink = Flink->Flink;
    }
    while ( Flink != &v10 );
    Flink = v10.Flink;
  }
  if ( Flink != &v10 )
  {
    AcquireSRWLockExclusive(v4);
    NOTIFICATION_THREAD::MoveAndAppendList(&v10, (struct _LIST_ENTRY *)Context + 1);
    ReleaseSRWLockExclusive(v4);
  }
}

```

## disassembly

```asm
0x180051090  push    rbp
0x180051092  push    rbx
0x180051093  push    rsi
0x180051094  push    rdi
0x180051095  push    r14
0x180051097  push    r15
0x180051099  mov     rbp, rsp
0x18005109c  sub     rsp, 38h
0x1800510a0  lea     rax, [rbp+var_18]
0x1800510a4  mov     r14, rdx
0x1800510a7  mov     [rbp+var_18.Blink], rax
0x1800510ab  lea     rsi, [rdx+8]
0x1800510af  lea     rax, [rbp+var_18]
0x1800510b3  mov     rcx, rsi; SRWLock
0x1800510b6  mov     [rbp+var_18.Flink], rax
0x1800510ba  call    cs:__imp_AcquireSRWLockExclusive
0x1800510c0  lea     rdx, [rbp+var_18]; struct _LIST_ENTRY *
0x1800510c4  lea     rcx, [r14+10h]; struct _LIST_ENTRY *
0x1800510c8  call    ?MoveAndAppendList@NOTIFICATION_THREAD@@CAXPEAU_LIST_ENTRY@@0@Z; NOTIFICATION_THREAD::MoveAndAppendList(_LIST_ENTRY *,_LIST_ENTRY *)
0x1800510cd  mov     rcx, rsi; SRWLock
0x1800510d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800510d6  mov     rbx, [rbp+var_18.Flink]
0x1800510da  lea     rax, [rbp+var_18]
0x1800510de  cmp     rbx, rax
0x1800510e1  jz      short loc_18005114C
0x1800510e3  lea     rdi, [rbx-60h]
0x1800510e7  mov     eax, [rdi+54h]
0x1800510ea  test    eax, eax
0x1800510ec  jnz     short loc_18005110B
0x1800510ee  mov     rcx, [r14+20h]; this
0x1800510f2  lea     r8, [rbp+arg_8]; int *
0x1800510f6  mov     rdx, rdi; struct CONFIG_MONITOR *
0x1800510f9  mov     [rbp+arg_8], eax
0x1800510fc  call    ?HandleChangeNotification@CONFIG_CACHE@@QEAAJPEAUCONFIG_MONITOR@@PEAH@Z; CONFIG_CACHE::HandleChangeNotification(CONFIG_MONITOR *,int *)
0x180051101  test    eax, eax
0x180051103  js      short loc_18005110B
0x180051105  cmp     [rbp+arg_8], 0
0x180051109  jz      short loc_18005113C
0x18005110b  mov     rcx, [rbx]
0x18005110e  cmp     [rcx+8], rbx
0x180051112  jnz     short loc_180051181
0x180051114  mov     rax, [rbx+8]
0x180051118  cmp     [rax], rbx
0x18005111b  jnz     short loc_180051181
0x18005111d  mov     [rax], rcx
0x180051120  mov     rbx, rax
0x180051123  mov     [rcx+8], rax
0x180051127  lea     rcx, [rdi+58h]
0x18005112b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180051131  mov     rdx, rdi; struct CONFIG_MONITOR *
0x180051134  mov     rcx, r14; this
0x180051137  call    ?FreeMonitor@NOTIFICATION_THREAD@@QEAAXPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::FreeMonitor(CONFIG_MONITOR *)
0x18005113c  mov     rbx, [rbx]
0x18005113f  lea     rax, [rbp+var_18]
0x180051143  cmp     rbx, rax
0x180051146  jnz     short loc_1800510E3
0x180051148  mov     rbx, [rbp+var_18.Flink]
0x18005114c  lea     rax, [rbp+var_18]
0x180051150  cmp     rbx, rax
0x180051153  jz      short loc_180051174
0x180051155  mov     rcx, rsi; SRWLock
0x180051158  call    cs:__imp_AcquireSRWLockExclusive
0x18005115e  lea     rdx, [r14+10h]; struct _LIST_ENTRY *
0x180051162  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x180051166  call    ?MoveAndAppendList@NOTIFICATION_THREAD@@CAXPEAU_LIST_ENTRY@@0@Z; NOTIFICATION_THREAD::MoveAndAppendList(_LIST_ENTRY *,_LIST_ENTRY *)
0x18005116b  mov     rcx, rsi; SRWLock
0x18005116e  call    cs:__imp_ReleaseSRWLockExclusive
0x180051174  add     rsp, 38h
0x180051178  pop     r15
0x18005117a  pop     r14
0x18005117c  pop     rdi
0x18005117d  pop     rsi
0x18005117e  pop     rbx
0x18005117f  pop     rbp
0x180051180  retn
0x180051181  mov     ecx, 3
0x180051186  int     29h; Win8: RtlFailFast(ecx)
```
