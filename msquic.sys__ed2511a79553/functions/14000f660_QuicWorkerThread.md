# QuicWorkerThread

- ea: `0x14000f660`
- end: `0x14000f814`
- name: `QuicWorkerThread`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000f660`
- `0x140010820`
- `0x1400291f0`
- `0x14002e380`
- `0x14002e7f0`
- `0x14003e884`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f685`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f685`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f740`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f740`
- `ntoskrnl!PsTerminateSystemThread` at `0x14000f801`
- `ntoskrnl!PsTerminateSystemThread` at `0x14000f801`

## pseudocode

```c
NTSTATUS __fastcall QuicWorkerThread(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  signed __int8 v5; // al
  signed __int8 v6; // tt
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int64 i; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+40h] [rbp-38h]
  int v16; // [rsp+48h] [rbp-30h]
  int v17; // [rsp+4Ch] [rbp-2Ch]
  HANDLE CurrentThreadId; // [rsp+50h] [rbp-28h]

  v16 = -1;
  v14 = 0;
  v15 = 0;
  CurrentThreadId = PsGetCurrentThreadId();
  if ( Microsoft_QuicEnableBits < 0 )
    McTemplateU0p_EtwWriteTransfer(v2, QuicWorkerStart);
  v17 = 1;
  v3 = QuicTimePlat();
  for ( i = QuicTimePlatToUs64(v3); (unsigned __int8)QuicWorkerLoop(a1, &i); i = QuicTimePlatToUs64(v11) )
  {
    _m_prefetchw(a1 + 5);
    v5 = *((_BYTE *)a1 + 40);
    do
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange8((volatile signed __int8 *)a1 + 40, 0, v5);
    }
    while ( v6 != v5 );
    v7 = i;
    if ( !v5 )
    {
      v8 = a1[4];
      if ( v8 == -1 )
      {
        KeWaitForSingleObject(a1 + 16, Executive, 0, 0, 0);
      }
      else if ( v8 > i )
      {
        v9 = (v8 - i) / 0x3E8 + 1;
        if ( v9 >= 0xFFFFFFFF )
          LODWORD(v9) = -2;
        CxPlatEventWaitWithTimeout(a1 + 16, (unsigned int)v9);
      }
    }
    v10 = v14;
    if ( !v17 )
      v10 = v7;
    ++v17;
    v14 = v10;
    v11 = QuicTimePlat();
  }
  if ( Microsoft_QuicEnableBits < 0 )
    McTemplateU0p_EtwWriteTransfer(v4, QuicWorkerStop);
  return PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14000f660  mov     rax, rsp
0x14000f663  push    rbx
0x14000f664  sub     rsp, 70h
0x14000f668  mov     [rax+8], rbp
0x14000f66c  mov     rbx, rcx
0x14000f66f  mov     [rax+10h], rsi
0x14000f673  mov     ebp, 0FFFFFFFFh
0x14000f678  xor     esi, esi
0x14000f67a  mov     [rax-30h], ebp
0x14000f67d  mov     [rax-40h], rsi
0x14000f681  mov     [rax-38h], rsi
0x14000f685  call    cs:__imp_PsGetCurrentThreadId
0x14000f68c  nop     dword ptr [rax+rax+00h]
0x14000f691  mov     [rsp+78h+var_28], rax
0x14000f696  movzx   eax, cs:Microsoft_QuicEnableBits
0x14000f69d  test    al, al
0x14000f69f  jns     short loc_14000F6B0
0x14000f6a1  mov     r8, rbx
0x14000f6a4  lea     rdx, QuicWorkerStart
0x14000f6ab  call    McTemplateU0p_EtwWriteTransfer
0x14000f6b0  mov     [rsp+78h+var_2C], 1
0x14000f6b8  call    QuicTimePlat
0x14000f6bd  mov     rcx, rax
0x14000f6c0  call    QuicTimePlatToUs64
0x14000f6c5  lea     rdx, [rsp+78h+var_48]
0x14000f6ca  mov     [rsp+78h+var_48], rax
0x14000f6cf  mov     rcx, rbx
0x14000f6d2  call    QuicWorkerLoop
0x14000f6d7  test    al, al
0x14000f6d9  jz      loc_14000F7D5
0x14000f6df  mov     [rsp+78h+arg_10], rdi
0x14000f6e7  mov     [rsp+78h+var_10], r14
0x14000f6ec  mov     r14, 624DD2F1A9FBE77h
0x14000f6f6  mov     [rsp+78h+var_18], r15
0x14000f6fb  mov     r15d, 0FFFFFFFEh
0x14000f701  prefetchw byte ptr [rbx+28h]
0x14000f705  movzx   eax, byte ptr [rbx+28h]
0x14000f709  nop     dword ptr [rax+00000000h]
0x14000f710  xor     ecx, ecx
0x14000f712  lock cmpxchg [rbx+28h], cl
0x14000f717  jnz     short loc_14000F710
0x14000f719  mov     rdi, [rsp+78h+var_48]
0x14000f71e  test    al, al
0x14000f720  jnz     short loc_14000F782
0x14000f722  mov     r8, [rbx+20h]
0x14000f726  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000f72a  jnz     short loc_14000F74E
0x14000f72c  lea     rcx, [rbx+80h]; Object
0x14000f733  mov     [rsp+78h+Timeout], rsi; Timeout
0x14000f738  xor     r9d, r9d; Alertable
0x14000f73b  xor     r8d, r8d; WaitMode
0x14000f73e  xor     edx, edx; WaitReason
0x14000f740  call    cs:__imp_KeWaitForSingleObject
0x14000f747  nop     dword ptr [rax+rax+00h]
0x14000f74c  jmp     short loc_14000F782
0x14000f74e  cmp     r8, rdi
0x14000f751  jbe     short loc_14000F782
0x14000f753  sub     r8, rdi
0x14000f756  lea     rcx, [rbx+80h]
0x14000f75d  mov     rax, r14
0x14000f760  mul     r8
0x14000f763  sub     r8, rdx
0x14000f766  shr     r8, 1
0x14000f769  add     r8, rdx
0x14000f76c  shr     r8, 9
0x14000f770  inc     r8
0x14000f773  cmp     r8, rbp
0x14000f776  cmovnb  r8, r15
0x14000f77a  mov     edx, r8d
0x14000f77d  call    _CxPlatEventWaitWithTimeout
0x14000f782  mov     ecx, [rsp+78h+var_2C]
0x14000f786  test    ecx, ecx
0x14000f788  mov     rax, [rsp+78h+var_40]
0x14000f78d  cmovz   rax, rdi
0x14000f791  inc     ecx
0x14000f793  mov     [rsp+78h+var_2C], ecx
0x14000f797  mov     [rsp+78h+var_40], rax
0x14000f79c  call    QuicTimePlat
0x14000f7a1  mov     rcx, rax
0x14000f7a4  call    QuicTimePlatToUs64
0x14000f7a9  lea     rdx, [rsp+78h+var_48]
0x14000f7ae  mov     [rsp+78h+var_48], rax
0x14000f7b3  mov     rcx, rbx
0x14000f7b6  call    QuicWorkerLoop
0x14000f7bb  test    al, al
0x14000f7bd  jnz     loc_14000F701
0x14000f7c3  mov     r15, [rsp+78h+var_18]
0x14000f7c8  mov     r14, [rsp+78h+var_10]
0x14000f7cd  mov     rdi, [rsp+78h+arg_10]
0x14000f7d5  movzx   eax, cs:Microsoft_QuicEnableBits
0x14000f7dc  mov     rsi, [rsp+78h+arg_8]
0x14000f7e4  mov     rbp, [rsp+78h+arg_0]
0x14000f7ec  test    al, al
0x14000f7ee  jns     short loc_14000F7FF
0x14000f7f0  mov     r8, rbx
0x14000f7f3  lea     rdx, QuicWorkerStop
0x14000f7fa  call    McTemplateU0p_EtwWriteTransfer
0x14000f7ff  xor     ecx, ecx; ExitStatus
0x14000f801  call    cs:__imp_PsTerminateSystemThread
0x14000f808  nop     dword ptr [rax+rax+00h]
0x14000f80d  add     rsp, 70h
0x14000f811  pop     rbx
0x14000f812  retn
```
