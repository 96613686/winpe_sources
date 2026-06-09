# CDispatchInterfaceProxy::CreateObjectFromProgID(wchar_t *)

- ea: `0x180004fc4`
- end: `0x180005072`
- name: `?CreateObjectFromProgID@CDispatchInterfaceProxy@@QEAAJPEA_W@Z`
- size: `174`
- prototype: `__int64 __fastcall(struct IDispatch **this, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800084d0`

## callees

- `0x180004d20`
- `0x180004e84`
- `0x180004fc4`
- `0x180014d30`

## pseudocode

```c
__int64 __fastcall CDispatchInterfaceProxy::CreateObjectFromProgID(struct IDispatch **this, wchar_t *a2)
{
  int Object; // ebx
  unsigned int v3; // eax
  __int16 v5; // [rsp+70h] [rbp+8h] BYREF
  int v6; // [rsp+80h] [rbp+18h] BYREF

  Object = CDispatchInterfaceProxy::CreateObject((CDispatchInterfaceProxy *)this, a2, this);
  if ( Object < 0 )
  {
    v5 = 10;
    v6 = Object;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v3 = mqwcslen(L"trigobjs/idspprxy");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v3 + 1),
        L"trigobjs/idspprxy",
        2,
        &v5,
        4,
        &v6,
        0,
        0);
    }
  }
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180004fc4  mov     [rsp+arg_8], rbx
0x180004fc9  push    rdi
0x180004fca  sub     rsp, 60h
0x180004fce  mov     r8, rcx; struct IDispatch **
0x180004fd1  call    ?CreateObject@CDispatchInterfaceProxy@@AEAAJPEB_WPEAPEAUIDispatch@@@Z; CDispatchInterfaceProxy::CreateObject(wchar_t const *,IDispatch * *)
0x180004fd6  mov     ebx, eax
0x180004fd8  test    eax, eax
0x180004fda  jns     loc_180005065
0x180004fe0  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180004fe8  mov     eax, 0Ah
0x180004fed  mov     [rsp+68h+arg_0], ax
0x180004ff2  mov     [rsp+68h+arg_10], ebx
0x180004ff9  jz      short loc_180005065
0x180004ffb  lea     rdi, aTrigobjsIdsppr; "trigobjs/idspprxy"
0x180005002  mov     rcx, rdi; wchar_t *
0x180005005  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000500a  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180005011  mov     edx, 1
0x180005016  mov     [rsp+68h+var_18], 0
0x18000501f  mov     r8d, edx
0x180005022  mov     [rsp+68h+var_20], 0
0x18000502b  lea     r9d, [rdx+rax]
0x18000502f  lea     rax, [rsp+68h+arg_10]
0x180005037  add     r9, r9
0x18000503a  mov     [rsp+68h+var_28], rax
0x18000503f  lea     rax, [rsp+68h+arg_0]
0x180005044  mov     [rsp+68h+var_30], 4
0x18000504d  mov     [rsp+68h+var_38], rax
0x180005052  mov     [rsp+68h+var_40], 2
0x18000505b  mov     [rsp+68h+var_48], rdi
0x180005060  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180005065  mov     eax, ebx
0x180005067  mov     rbx, [rsp+68h+arg_8]
0x18000506c  add     rsp, 60h
0x180005070  pop     rdi
0x180005071  retn
```
