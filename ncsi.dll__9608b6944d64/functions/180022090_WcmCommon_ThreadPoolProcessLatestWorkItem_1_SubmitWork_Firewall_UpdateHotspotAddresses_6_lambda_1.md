# WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__Firewall::UpdateHotspotAddresses_::_6_::_lambda_1___

- ea: `0x180022090`
- end: `0x180022198`
- name: `WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__Firewall::UpdateHotspotAddresses_::_6_::_lambda_1___`
- size: `264`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180043d7c`

## callees

- `0x180022090`
- `0x180022318`
- `0x180022758`
- `0x1800472d8`
- `0x180047f78`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022180`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800220c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022171`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800220c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022171`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800220b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800220b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem_1_::SubmitWork__Firewall::UpdateHotspotAddresses_::_6_::_lambda_1___(
        LPCRITICAL_SECTION lpCriticalSection)
{
  bool v2; // si
  _QWORD *v3; // rax
  _BYTE *v4; // rcx
  _BYTE v5[40]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE *v6; // [rsp+50h] [rbp-28h]
  __int64 (__fastcall **v7)(void *); // [rsp+58h] [rbp-20h]
  char *v8; // [rsp+60h] [rbp-18h]
  _QWORD *v9; // [rsp+68h] [rbp-10h]

  if ( !(unsigned __int8)WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady() )
  {
    EnterCriticalSection(lpCriticalSection);
    if ( LOBYTE(lpCriticalSection[5].OwningThread) )
    {
      LeaveCriticalSection(lpCriticalSection);
      return;
    }
    v2 = *(_QWORD *)&lpCriticalSection[5].LockCount == 0;
    memset_0(v5, 0, 0x40u);
    v3 = operator new(0x40u);
    v9 = v3;
    *v3 = off_18007D1D8;
    v3[7] = v3;
    v6 = v3;
    v7 = &std::_Any_big_RTTI_obj<std::function<void (void)>>;
    v8 = (char *)&std::function<void (void)> `RTTI Type Descriptor' + 1;
    std::any::operator=(&lpCriticalSection[3].SpinCount, v5);
    if ( ((unsigned __int8)v8 & 3) == 1 )
    {
      v4 = v6;
    }
    else
    {
      if ( ((unsigned __int8)v8 & 3) != 2 )
        goto LABEL_9;
      v4 = v5;
    }
    (*v7)(v4);
LABEL_9:
    LeaveCriticalSection(lpCriticalSection);
    if ( v2 )
      SubmitThreadpoolWork((PTP_WORK)lpCriticalSection[3].DebugInfo);
  }
}

```

## disassembly

```asm
0x180022090  mov     [rsp+arg_8], rbx
0x180022095  mov     [rsp+arg_10], rsi
0x18002209a  push    rdi
0x18002209b  sub     rsp, 70h
0x18002209f  mov     rdi, rcx
0x1800220a2  call    ?BackoffTimerNotReady@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@AEAA_NXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady(void)
0x1800220a7  test    al, al
0x1800220a9  jnz     loc_180022186
0x1800220af  mov     rcx, rdi; lpCriticalSection
0x1800220b2  call    cs:__imp_EnterCriticalSection
0x1800220b8  mov     [rsp+78h+var_58], rdi
0x1800220bd  cmp     byte ptr [rdi+0D8h], 0
0x1800220c4  jz      short loc_1800220D4
0x1800220c6  mov     rcx, rdi; lpCriticalSection
0x1800220c9  call    cs:__imp_LeaveCriticalSection
0x1800220cf  jmp     loc_180022186
0x1800220d4  lea     rbx, [rdi+98h]
0x1800220db  cmp     qword ptr [rbx+38h], 0
0x1800220e0  setz    sil
0x1800220e4  xor     edx, edx; Val
0x1800220e6  lea     r8d, [rdx+40h]; Size
0x1800220ea  lea     rcx, [rsp+78h+var_50]; void *
0x1800220ef  call    memset_0
0x1800220f4  mov     ecx, 40h ; '@'; Size
0x1800220f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800220fe  mov     [rsp+78h+var_10], rax
0x180022103  lea     rcx, off_18007D1D8
0x18002210a  mov     [rax], rcx
0x18002210d  mov     [rax+38h], rax
0x180022111  mov     [rsp+78h+var_28], rax
0x180022116  lea     rax, ??$_Any_big_RTTI_obj@V?$function@$$A6AXXZ@std@@@std@@3U_Any_big_RTTI@1@B; _Any_big_RTTI::_Any_big_RTTI const std::_Any_big_RTTI_obj<std::function<void (void)>>
0x18002211d  mov     [rsp+78h+var_20], rax
0x180022122  lea     rax, ??_R0?AV?$function@$$A6AXXZ@std@@@8; std::function<void (void)> `RTTI Type Descriptor'
0x180022129  or      rax, 1
0x18002212d  mov     [rsp+78h+var_18], rax
0x180022132  lea     rdx, [rsp+78h+var_50]
0x180022137  mov     rcx, rbx
0x18002213a  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x18002213f  nop
0x180022140  mov     rax, [rsp+78h+var_18]
0x180022145  and     eax, 3
0x180022148  sub     rax, 1
0x18002214c  jz      short loc_18002215B
0x18002214e  cmp     rax, 1
0x180022152  jnz     short loc_18002216E
0x180022154  lea     rcx, [rsp+78h+var_50]
0x180022159  jmp     short loc_180022160
0x18002215b  mov     rcx, [rsp+78h+var_28]
0x180022160  mov     rax, [rsp+78h+var_20]
0x180022165  mov     rax, [rax]
0x180022168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002216d  nop
0x18002216e  mov     rcx, rdi; lpCriticalSection
0x180022171  call    cs:__imp_LeaveCriticalSection
0x180022177  test    sil, sil
0x18002217a  jz      short loc_180022186
0x18002217c  mov     rcx, [rdi+78h]; pwk
0x180022180  call    cs:__imp_SubmitThreadpoolWork
0x180022186  lea     r11, [rsp+78h+var_8]
0x18002218b  mov     rbx, [r11+18h]
0x18002218f  mov     rsi, [r11+20h]
0x180022193  mov     rsp, r11
0x180022196  pop     rdi
0x180022197  retn
```
