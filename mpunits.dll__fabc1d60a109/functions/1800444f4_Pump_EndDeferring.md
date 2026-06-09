# __Pump_EndDeferring

- ea: `0x1800444f4`
- end: `0x180044626`
- name: `__Pump_EndDeferring`
- size: `306`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019420`
- `0x180019ee0`
- `0x18002bda0`
- `0x18003b020`
- `0x18003b110`
- `0x18003b200`
- `0x18003f000`
- `0x18003f0e0`
- `0x18003f270`
- `0x18003f470`

## callees

- `0x180042ecc`
- `0x180043120`
- `0x1800431f0`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044551`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044551`

## string_xrefs

- `0x1800445c2`: `admin\wmi\winomi\mp\common\pump.c`

## pseudocode

```c
__int64 __fastcall _Pump_EndDeferring(__int64 a1)
{
  unsigned int v2; // edi
  _QWORD *v4; // rsi
  _QWORD *v5; // rcx
  int ResultCallback; // eax
  _QWORD v8[2]; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+40h] [rbp-18h]
  int v10; // [rsp+44h] [rbp-14h]

  if ( !(unsigned int)TryAcquireWrite(a1) )
    QueueAcquireWrite(a1);
  do
  {
    v2 = _Pump_EndDeferringHelper(a1);
    if ( !v2 )
    {
      ReadWriteLock_ReleaseWrite(a1);
      return 0;
    }
  }
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), 3, 7) != 7 );
  *(_QWORD *)(a1 + 40) = GetCurrentThreadId();
  _m_prefetchw((const void *)(a1 + 8));
  v4 = *(_QWORD **)(a1 + 16);
  while ( v4 )
  {
    v5 = v4;
    v4 = (_QWORD *)*v4;
    *v5 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD *, _QWORD))(a1 + 24))(v5, *(_QWORD *)(a1 + 32)) )
    {
      if ( NITS_PRESENCE_STUB != 1 )
      {
        ResultCallback = JobQueryResultCallback();
        v8[0] = 0;
        v9 = 201;
        v10 = -1;
        v8[1] = "admin\\wmi\\winomi\\mp\\common\\pump.c";
        AssertW_Checked(
          ResultCallback == 0,
          (int)"!((NITS_PRESENCE_STUB != NitsStubbedOut) ? NITS_STUB.DidFault() : NitsFalse)",
          (int)L"Ignoring error deliberately",
          (int)v8,
          0);
      }
    }
  }
  *(_QWORD *)(a1 + 16) = 0;
  _InterlockedExchange64((volatile __int64 *)(a1 + 8), 0);
  *(_QWORD *)(a1 + 40) = 0;
  ReadWriteLock_ReleaseWrite(a1);
  return v2;
}

```

## disassembly

```asm
0x1800444f4  mov     [rsp+arg_8], rbx
0x1800444f9  mov     [rsp+arg_10], rsi
0x1800444fe  push    rdi
0x1800444ff  sub     rsp, 50h
0x180044503  mov     rbx, rcx
0x180044506  call    TryAcquireWrite
0x18004450b  test    eax, eax
0x18004450d  jnz     short loc_180044529
0x18004450f  mov     rcx, rbx
0x180044512  call    QueueAcquireWrite
0x180044517  jmp     short loc_180044529
0x180044519  mov     ecx, 3
0x18004451e  lea     eax, [rcx+4]
0x180044521  lock cmpxchg [rbx+8], rcx
0x180044527  jz      short loc_180044551
0x180044529  mov     rcx, rbx
0x18004452c  call    __Pump_EndDeferringHelper
0x180044531  mov     edi, eax
0x180044533  test    eax, eax
0x180044535  jnz     short loc_180044519
0x180044537  mov     rcx, rbx
0x18004453a  call    ReadWriteLock_ReleaseWrite
0x18004453f  xor     eax, eax
0x180044541  mov     rbx, [rsp+58h+arg_8]
0x180044546  mov     rsi, [rsp+58h+arg_10]
0x18004454b  add     rsp, 50h
0x18004454f  pop     rdi
0x180044550  retn
0x180044551  call    cs:__imp_GetCurrentThreadId
0x180044557  mov     eax, eax
0x180044559  mov     [rbx+28h], rax
0x18004455d  prefetchw byte ptr [rbx+8]
0x180044561  mov     rax, [rbx+8]
0x180044565  mov     rsi, [rbx+10h]
0x180044569  jmp     loc_180044600
0x18004456e  mov     rcx, rsi
0x180044571  mov     rax, rsi
0x180044574  mov     rsi, [rsi]
0x180044577  mov     qword ptr [rcx], 0
0x18004457e  mov     rdx, [rbx+20h]
0x180044582  mov     rax, [rbx+18h]
0x180044586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004458b  test    eax, eax
0x18004458d  jz      short loc_180044600
0x18004458f  test    edi, edi
0x180044591  jnz     short loc_180044597
0x180044593  mov     edi, eax
0x180044595  jmp     short loc_180044600
0x180044597  cmp     cs:NITS_PRESENCE_STUB, 1
0x18004459f  jz      short loc_180044600
0x1800445a1  mov     rax, cs:off_180047AB8
0x1800445a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445ad  xor     ecx, ecx
0x1800445af  mov     [rsp+58h+var_28], 0
0x1800445b8  test    eax, eax
0x1800445ba  mov     [rsp+58h+var_18], 0C9h
0x1800445c2  lea     rax, aAdminWmiWinomi_10; "admin\\wmi\\winomi\\mp\\common\\pump.c"
0x1800445c9  mov     [rsp+58h+var_14], 0FFFFFFFFh
0x1800445d1  mov     [rsp+58h+var_20], rax
0x1800445d6  lea     r9, [rsp+58h+var_28]
0x1800445db  mov     rax, cs:off_180047A80
0x1800445e2  lea     r8, aIgnoringErrorD; "Ignoring error deliberately"
0x1800445e9  setz    cl
0x1800445ec  mov     [rsp+58h+var_38], 0
0x1800445f4  lea     rdx, aNitsPresenceSt_0; "!((NITS_PRESENCE_STUB != NitsStubbedOut"...
0x1800445fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044600  test    rsi, rsi
0x180044603  jnz     loc_18004456E
0x180044609  xor     eax, eax
0x18004460b  mov     [rbx+10h], rsi
0x18004460f  xchg    rax, [rbx+8]
0x180044613  mov     rcx, rbx
0x180044616  mov     [rbx+28h], rsi
0x18004461a  call    ReadWriteLock_ReleaseWrite
0x18004461f  mov     eax, edi
0x180044621  jmp     loc_180044541
```
