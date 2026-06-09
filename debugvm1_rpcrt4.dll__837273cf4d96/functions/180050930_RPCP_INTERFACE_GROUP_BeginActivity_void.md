# RPCP_INTERFACE_GROUP::BeginActivity(void)

- ea: `0x180050930`
- end: `0x1800509c2`
- name: `?BeginActivity@RPCP_INTERFACE_GROUP@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(RPCP_INTERFACE_GROUP *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004ec54`
- `0x18005384c`

## callees

- `0x180021ce0`
- `0x180050930`
- `0x180099760`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800509bb`
- `ntdll!RtlEnterCriticalSection` at `0x180050947`
- `ntdll!RtlEnterCriticalSection` at `0x180050947`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180050997`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180050997`

## pseudocode

```c
void __fastcall RPCP_INTERFACE_GROUP::BeginActivity(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  PTP_TIMER *v3; // rcx
  int v4; // [rsp+28h] [rbp-20h]
  int v5; // [rsp+30h] [rbp-18h]

  v1 = this + 6;
  RtlEnterCriticalSection(this + 6);
  LogEvent(0x67u, 0x2Bu, this, 0, (int)++LODWORD(this[7].DebugInfo), v4, v5);
  if ( LODWORD(this[7].DebugInfo) == 1 && LODWORD(this[5].SpinCount) != 3 )
  {
    v3 = *(PTP_TIMER **)&this[7].LockCount;
    if ( v3 )
      SetThreadpoolTimer(*v3, 0, 0, 0);
    if ( LODWORD(this[7].OwningThread) )
      RPCP_INTERFACE_GROUP::PostIdleChangeNotification((RPCP_INTERFACE_GROUP *)this);
  }
  RtlLeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180050930  mov     [rsp+arg_0], rbx
0x180050935  push    rdi
0x180050936  sub     rsp, 40h
0x18005093a  lea     rdi, [rcx+0F0h]
0x180050941  mov     rbx, rcx
0x180050944  mov     rcx, rdi; CriticalSection
0x180050947  call    cs:__imp_RtlEnterCriticalSection
0x18005094d  inc     dword ptr [rbx+118h]
0x180050953  xor     r9d, r9d; void *
0x180050956  movsxd  rax, dword ptr [rbx+118h]
0x18005095d  mov     r8, rbx; void *
0x180050960  mov     dl, 2Bh ; '+'; unsigned __int8
0x180050962  mov     [rsp+48h+var_28], rax; unsigned __int64
0x180050967  mov     cl, 67h ; 'g'; unsigned __int8
0x180050969  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18005096e  cmp     dword ptr [rbx+118h], 1
0x180050975  jnz     short loc_1800509AE
0x180050977  cmp     dword ptr [rbx+0E8h], 3
0x18005097e  jz      short loc_1800509AE
0x180050980  mov     rcx, [rbx+120h]
0x180050987  test    rcx, rcx
0x18005098a  jz      short loc_18005099D
0x18005098c  mov     rcx, [rcx]; pti
0x18005098f  xor     r9d, r9d; msWindowLength
0x180050992  xor     r8d, r8d; msPeriod
0x180050995  xor     edx, edx; pftDueTime
0x180050997  call    cs:__imp_SetThreadpoolTimer
0x18005099d  cmp     dword ptr [rbx+128h], 0
0x1800509a4  jz      short loc_1800509AE
0x1800509a6  mov     rcx, rbx; this
0x1800509a9  call    ?PostIdleChangeNotification@RPCP_INTERFACE_GROUP@@AEAAXXZ; RPCP_INTERFACE_GROUP::PostIdleChangeNotification(void)
0x1800509ae  mov     rcx, rdi
0x1800509b1  mov     rbx, [rsp+48h+arg_0]
0x1800509b6  add     rsp, 40h
0x1800509ba  pop     rdi
0x1800509bb  jmp     cs:__imp_RtlLeaveCriticalSection
```
