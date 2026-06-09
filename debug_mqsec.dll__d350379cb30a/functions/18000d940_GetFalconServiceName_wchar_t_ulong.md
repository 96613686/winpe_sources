# GetFalconServiceName(wchar_t *,ulong)

- ea: `0x18000d940`
- end: `0x18000da4c`
- name: `?GetFalconServiceName@@YAJPEA_WK@Z`
- size: `268`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000bb80`
- `0x18000dde0`
- `0x1800216f0`

## callees

- `0x180003df0`
- `0x180004074`
- `0x18000ce2c`
- `0x18000d940`
- `0x180013940`
- `0x180017430`
- `0x180017be8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFalconServiceName(wchar_t *a1, unsigned int a2)
{
  unsigned __int64 v2; // rbx
  int v4; // ebx
  unsigned int v5; // eax
  __int16 v7; // [rsp+78h] [rbp+10h] BYREF
  int v8; // [rsp+80h] [rbp+18h] BYREF
  int *v9; // [rsp+88h] [rbp+20h] BYREF

  v2 = a2;
  v9 = dword_1800425B8;
  CReadWriteLock::LockRead((CReadWriteLock *)dword_1800425B8);
  if ( mqwcslen(L"MSMQ") < (unsigned int)v2 )
  {
    v4 = StringCchCopyW(a1, v2, L"MSMQ");
    if ( v4 < 0 )
    {
      v7 = 300;
      v8 = v4;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v5 = mqwcslen(L"mqsec/register");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v5 + 1),
          L"mqsec/register",
          2,
          &v7,
          4,
          &v8,
          0,
          0);
      }
    }
  }
  else
  {
    v4 = -2147024774;
    LogMsgHR(-2147024774, (wchar_t *)L"mqsec/register", 0x122u);
  }
  CSR::~CSR((CSR *)&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d940  mov     rax, rsp
0x18000d943  mov     [rax+8], rbx
0x18000d947  push    rdi
0x18000d948  sub     rsp, 60h
0x18000d94c  mov     ebx, edx
0x18000d94e  mov     rdi, rcx
0x18000d951  lea     rcx, dword_1800425B8; this
0x18000d958  mov     [rax+20h], rcx
0x18000d95c  call    ?LockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockRead(void)
0x18000d961  nop
0x18000d962  lea     rcx, aMsmq; "MSMQ"
0x18000d969  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000d96e  cmp     eax, ebx
0x18000d970  jb      short loc_18000D990
0x18000d972  mov     r8d, 122h; unsigned __int16
0x18000d978  lea     rdx, aMqsecRegister; "mqsec/register"
0x18000d97f  mov     ebx, 8007007Ah
0x18000d984  mov     ecx, ebx; int
0x18000d986  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000d98b  jmp     loc_18000DA32
0x18000d990  mov     rdx, rbx; unsigned __int64
0x18000d993  lea     r8, aMsmq; "MSMQ"
0x18000d99a  mov     rcx, rdi; wchar_t *
0x18000d99d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000d9a2  mov     ebx, eax
0x18000d9a4  test    eax, eax
0x18000d9a6  jns     loc_18000DA32
0x18000d9ac  mov     eax, 12Ch
0x18000d9b1  mov     [rsp+68h+arg_8], ax
0x18000d9b6  mov     [rsp+68h+arg_10], ebx
0x18000d9bd  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000d9c5  jz      short loc_18000DA32
0x18000d9c7  lea     rdi, aMqsecRegister; "mqsec/register"
0x18000d9ce  mov     rcx, rdi; wchar_t *
0x18000d9d1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000d9d6  mov     edx, 1
0x18000d9db  lea     r9d, [rdx+rax]
0x18000d9df  add     r9, r9
0x18000d9e2  mov     [rsp+68h+var_18], 0
0x18000d9eb  mov     [rsp+68h+var_20], 0
0x18000d9f4  lea     rax, [rsp+68h+arg_10]
0x18000d9fc  mov     [rsp+68h+var_28], rax
0x18000da01  mov     [rsp+68h+var_30], 4
0x18000da0a  lea     rax, [rsp+68h+arg_8]
0x18000da0f  mov     [rsp+68h+var_38], rax
0x18000da14  mov     [rsp+68h+var_40], 2
0x18000da1d  mov     [rsp+68h+var_48], rdi
0x18000da22  mov     r8d, edx
0x18000da25  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000da2c  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000da31  nop
0x18000da32  lea     rcx, [rsp+68h+arg_18]; this
0x18000da3a  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x18000da3f  mov     eax, ebx
0x18000da41  mov     rbx, [rsp+68h+arg_0]
0x18000da46  add     rsp, 60h
0x18000da4a  pop     rdi
0x18000da4b  retn
```
