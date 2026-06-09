# WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__NHM::NhmNetReadyMonitor::DebounceTimerCallback_::_3_::_lambda_1___

- ea: `0x180022204`
- end: `0x180022312`
- name: `WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__NHM::NhmNetReadyMonitor::DebounceTimerCallback_::_3_::_lambda_1___`
- size: `270`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800221a0`

## callees

- `0x180022204`
- `0x180022318`
- `0x180022758`
- `0x1800472d8`
- `0x180047f78`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800222ea`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800222ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800222db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002230a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800222db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002230a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022224`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022224`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__NHM::NhmNetReadyMonitor::DebounceTimerCallback_::_3_::_lambda_1___(
        LPCRITICAL_SECTION lpCriticalSection,
        _QWORD *a2)
{
  bool v4; // si
  _QWORD *v5; // rax
  _BYTE *v6; // rcx
  _BYTE v7[40]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE *v8; // [rsp+50h] [rbp-48h]
  __int64 (__fastcall **v9)(void *); // [rsp+58h] [rbp-40h]
  char *v10; // [rsp+60h] [rbp-38h]
  _QWORD *v11; // [rsp+68h] [rbp-30h]

  if ( !(unsigned __int8)WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady() )
  {
    EnterCriticalSection(lpCriticalSection);
    if ( LOBYTE(lpCriticalSection[5].OwningThread) )
    {
      LeaveCriticalSection(lpCriticalSection);
      return;
    }
    v4 = *(_QWORD *)&lpCriticalSection[5].LockCount == 0;
    memset_0(v7, 0, 0x40u);
    v5 = operator new(0x40u);
    v11 = v5;
    v5[7] = 0;
    *v5 = off_18007D198;
    v5[1] = *a2;
    v5[7] = v5;
    v8 = v5;
    v9 = &std::_Any_big_RTTI_obj<std::function<void (void)>>;
    v10 = (char *)&std::function<void (void)> `RTTI Type Descriptor' + 1;
    std::any::operator=(&lpCriticalSection[3].SpinCount, v7);
    if ( ((unsigned __int8)v10 & 3) == 1 )
    {
      v6 = v8;
    }
    else
    {
      if ( ((unsigned __int8)v10 & 3) != 2 )
      {
LABEL_6:
        LeaveCriticalSection(lpCriticalSection);
        if ( v4 )
          SubmitThreadpoolWork((PTP_WORK)lpCriticalSection[3].DebugInfo);
        return;
      }
      v6 = v7;
    }
    (*v9)(v6);
    goto LABEL_6;
  }
}

```

## disassembly

```asm
0x180022204  push    rbx
0x180022206  push    rsi
0x180022207  push    rdi
0x180022208  push    r14
0x18002220a  sub     rsp, 78h
0x18002220e  mov     r14, rdx
0x180022211  mov     rdi, rcx
0x180022214  call    ?BackoffTimerNotReady@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@AEAA_NXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady(void)
0x180022219  test    al, al
0x18002221b  jnz     loc_1800222F0
0x180022221  mov     rcx, rdi; lpCriticalSection
0x180022224  call    cs:__imp_EnterCriticalSection
0x18002222a  mov     [rsp+98h+var_78], rdi
0x18002222f  cmp     byte ptr [rdi+0D8h], 0
0x180022236  jnz     loc_180022307
0x18002223c  lea     rbx, [rdi+98h]
0x180022243  cmp     qword ptr [rbx+38h], 0
0x180022248  setz    sil
0x18002224c  xor     edx, edx; Val
0x18002224e  lea     r8d, [rdx+40h]; Size
0x180022252  lea     rcx, [rsp+98h+var_70]; void *
0x180022257  call    memset_0
0x18002225c  mov     ecx, 40h ; '@'; Size
0x180022261  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022266  mov     [rsp+98h+var_30], rax
0x18002226b  mov     qword ptr [rax+38h], 0
0x180022273  lea     rcx, off_18007D198
0x18002227a  mov     [rax], rcx
0x18002227d  mov     rdx, [r14]
0x180022280  mov     [rax+8], rdx
0x180022284  mov     [rax+38h], rax
0x180022288  mov     [rsp+98h+var_48], rax
0x18002228d  lea     rax, ??$_Any_big_RTTI_obj@V?$function@$$A6AXXZ@std@@@std@@3U_Any_big_RTTI@1@B; _Any_big_RTTI::_Any_big_RTTI const std::_Any_big_RTTI_obj<std::function<void (void)>>
0x180022294  mov     [rsp+98h+var_40], rax
0x180022299  lea     rax, ??_R0?AV?$function@$$A6AXXZ@std@@@8; std::function<void (void)> `RTTI Type Descriptor'
0x1800222a0  or      rax, 1
0x1800222a4  mov     [rsp+98h+var_38], rax
0x1800222a9  lea     rdx, [rsp+98h+var_70]
0x1800222ae  mov     rcx, rbx
0x1800222b1  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x1800222b6  nop
0x1800222b7  mov     rax, [rsp+98h+var_38]
0x1800222bc  and     eax, 3
0x1800222bf  sub     rax, 1
0x1800222c3  jnz     short loc_1800222FA
0x1800222c5  mov     rcx, [rsp+98h+var_48]
0x1800222ca  mov     rax, [rsp+98h+var_40]
0x1800222cf  mov     rax, [rax]
0x1800222d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222d7  nop
0x1800222d8  mov     rcx, rdi; lpCriticalSection
0x1800222db  call    cs:__imp_LeaveCriticalSection
0x1800222e1  test    sil, sil
0x1800222e4  jz      short loc_1800222F0
0x1800222e6  mov     rcx, [rdi+78h]; pwk
0x1800222ea  call    cs:__imp_SubmitThreadpoolWork
0x1800222f0  add     rsp, 78h
0x1800222f4  pop     r14
0x1800222f6  pop     rdi
0x1800222f7  pop     rsi
0x1800222f8  pop     rbx
0x1800222f9  retn
0x1800222fa  cmp     rax, 1
0x1800222fe  jnz     short loc_1800222D8
0x180022300  lea     rcx, [rsp+98h+var_70]
0x180022305  jmp     short loc_1800222CA
0x180022307  mov     rcx, rdi; lpCriticalSection
0x18002230a  call    cs:__imp_LeaveCriticalSection
0x180022310  jmp     short loc_1800222F0
```
