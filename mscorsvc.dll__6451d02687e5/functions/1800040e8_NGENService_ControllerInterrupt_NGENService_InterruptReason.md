# NGENService::ControllerInterrupt(NGENService::InterruptReason)

- ea: `0x1800040e8`
- end: `0x180004165`
- name: `?ControllerInterrupt@NGENService@@YAXW4InterruptReason@1@@Z`
- size: `125`
- prototype: `BOOL __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004170`

## callees

- `0x1800040e8`
- `0x18002e1d0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000415e`
- `KERNEL32!ResetEvent` at `0x18000414d`
- `KERNEL32!ResetEvent` at `0x18000414d`

## string_xrefs

- `0x180004133`: `SERVICE_INTERRUPT`
- `0x18000410f`: `SERVICEWORKER_INTERRUPT`

## pseudocode

```c
BOOL __fastcall NGENService::ControllerInterrupt(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx

  NGENService::g_InterruptMask |= a1;
  v1 = a1 - 1;
  if ( v1 )
  {
    v2 = v1 - 1;
    if ( v2 )
    {
      v3 = v2 - 2;
      if ( v3 )
      {
        v4 = v3 - 4;
        if ( v4 )
        {
          if ( v4 == 8 )
            NGENService::DebugLog(
              (NGENService *)L"InterruptController(): Interrupt requested. Reason = %s\n",
              L"SERVICEWORKER_INTERRUPT");
          else
            NGENService::DebugLog((NGENService *)L"InterruptController(): Interrupt requested. Reason = %s\n", 0);
        }
        else
        {
          NGENService::DebugLog(
            (NGENService *)L"InterruptController(): Interrupt requested. Reason = %s\n",
            L"DIRTY_ROOTSTORE_INTERRUPT");
        }
      }
      else
      {
        NGENService::DebugLog(
          (NGENService *)L"InterruptController(): Interrupt requested. Reason = %s\n",
          L"USER_INTERRUPT");
      }
    }
    else
    {
      NGENService::DebugLog(
        (NGENService *)L"InterruptController(): Interrupt requested. Reason = %s\n",
        L"CLIENT_INTERRUPT");
    }
  }
  else
  {
    NGENService::DebugLog(
      (NGENService *)L"InterruptController(): Interrupt requested. Reason = %s\n",
      L"SERVICE_INTERRUPT");
  }
  ResetEvent(NGENService::g_hInterruptProcessedEvent);
  return SetEvent(NGENService::g_hInterruptEvent);
}

```

## disassembly

```asm
0x1800040e8  sub     rsp, 28h
0x1800040ec  or      cs:?g_InterruptMask@NGENService@@3KA, ecx; ulong NGENService::g_InterruptMask
0x1800040f2  sub     ecx, 1
0x1800040f5  jz      short loc_180004133
0x1800040f7  sub     ecx, 1
0x1800040fa  jz      short loc_18000412A
0x1800040fc  sub     ecx, 2
0x1800040ff  jz      short loc_180004121
0x180004101  sub     ecx, 4
0x180004104  jz      short loc_180004118
0x180004106  cmp     ecx, 8
0x180004109  jz      short loc_18000410F
0x18000410b  xor     edx, edx
0x18000410d  jmp     short loc_18000413A
0x18000410f  lea     rdx, aServiceworkerI; "SERVICEWORKER_INTERRUPT"
0x180004116  jmp     short loc_18000413A
0x180004118  lea     rdx, aDirtyRootstore; "DIRTY_ROOTSTORE_INTERRUPT"
0x18000411f  jmp     short loc_18000413A
0x180004121  lea     rdx, aUserInterrupt; "USER_INTERRUPT"
0x180004128  jmp     short loc_18000413A
0x18000412a  lea     rdx, aClientInterrup; "CLIENT_INTERRUPT"
0x180004131  jmp     short loc_18000413A
0x180004133  lea     rdx, aServiceInterru; "SERVICE_INTERRUPT"
0x18000413a  lea     rcx, aInterruptcontr; "InterruptController(): Interrupt reques"...
0x180004141  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004146  mov     rcx, cs:?g_hInterruptProcessedEvent@NGENService@@3PEAXEA; hEvent
0x18000414d  call    cs:__imp_ResetEvent
0x180004153  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; void * NGENService::g_hInterruptEvent
0x18000415a  add     rsp, 28h
0x18000415e  jmp     cs:__imp_SetEvent
```
