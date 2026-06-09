# CRtMove::MoveMessage(void *,void *,unsigned __int64,ITransaction *)

- ea: `0x18001d224`
- end: `0x18001d339`
- name: `?MoveMessage@CRtMove@@QEAAJPEAX0_KPEAUITransaction@@@Z`
- size: `277`
- prototype: `__int64 __usercall@<rax>(CRtMove *__hidden this@<rcx>, void *@<rdx>, void *@<r8>, unsigned __int64@<r9>, struct ITransaction *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000aa6c`

## callees

- `0x18000a6c4`
- `0x180013c74`
- `0x180017ce0`
- `0x18001a990`
- `0x18001ab8c`
- `0x18001d138`
- `0x18001d224`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001d300`
- `KERNEL32!WaitForSingleObject` at `0x18001d300`

## string_xrefs

- `0x18001d320`: `rt/CRtMove`

## pseudocode

```c
__int64 __fastcall CRtMove::MoveMessage(
        CRtMove *this,
        void *a2,
        void *a3,
        unsigned __int64 a4,
        struct ITransaction *a5)
{
  int ThreadEvent; // ebx
  unsigned __int16 v9; // r8
  int v10; // eax
  struct _OVERLAPPED v12; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  ThreadEvent = CRtTransactedOperation::SetITransaction(this, a5, 0);
  if ( ThreadEvent < 0 )
  {
    v9 = 110;
LABEL_13:
    LogMsgHR(ThreadEvent, (wchar_t *)L"rt/CRtMove", v9);
    return (unsigned int)ThreadEvent;
  }
  if ( *(_QWORD *)this )
  {
    ThreadEvent = CRtTransactedOperation::EnlistTransaction(this, a2, 1, 0);
    if ( ThreadEvent < 0 )
    {
      v9 = 120;
      goto LABEL_13;
    }
  }
  memset(&v12, 0, sizeof(v12));
  ThreadEvent = GetThreadEvent(&v12.hEvent);
  if ( ThreadEvent < 0 )
  {
    v9 = 130;
    goto LABEL_13;
  }
  v10 = ACMoveToSubqueue(a2, a3, &v13, (struct BOID *)((char *)this + 12), *(_QWORD *)this != 0, &v12);
  ThreadEvent = RTpConvertToMQCode(v10, 1u);
  if ( ThreadEvent < 0 )
  {
    v9 = 140;
    goto LABEL_13;
  }
  if ( ThreadEvent == 1074659334 )
  {
    WaitForSingleObject(v12.hEvent, 0xFFFFFFFF);
    ThreadEvent = RTpConvertToMQCode(v12.Internal, 1u);
    if ( ThreadEvent < 0 )
    {
      v9 = 150;
      goto LABEL_13;
    }
  }
  return (unsigned int)ThreadEvent;
}

```

## disassembly

```asm
0x18001d224  mov     [rsp+arg_18], r9
0x18001d229  push    rbx
0x18001d22a  push    rbp
0x18001d22b  push    rsi
0x18001d22c  push    rdi
0x18001d22d  sub     rsp, 58h
0x18001d231  mov     rbp, r8
0x18001d234  mov     rsi, rdx
0x18001d237  mov     rdx, [rsp+78h+arg_20]; struct ITransaction *
0x18001d23f  xor     r8d, r8d; int
0x18001d242  mov     rdi, rcx
0x18001d245  call    ?SetITransaction@CRtTransactedOperation@@QEAAJPEAUITransaction@@H@Z; CRtTransactedOperation::SetITransaction(ITransaction *,int)
0x18001d24a  mov     ebx, eax
0x18001d24c  test    eax, eax
0x18001d24e  jns     short loc_18001D25B
0x18001d250  mov     r8d, 6Eh ; 'n'
0x18001d256  jmp     loc_18001D320
0x18001d25b  cmp     qword ptr [rdi], 0
0x18001d25f  jz      short loc_18001D284
0x18001d261  xor     r9d, r9d; int
0x18001d264  mov     rdx, rsi; void *
0x18001d267  mov     rcx, rdi; this
0x18001d26a  lea     r8d, [r9+1]; int
0x18001d26e  call    ?EnlistTransaction@CRtTransactedOperation@@QEAAJPEAXHH@Z; CRtTransactedOperation::EnlistTransaction(void *,int,int)
0x18001d273  mov     ebx, eax
0x18001d275  test    eax, eax
0x18001d277  jns     short loc_18001D284
0x18001d279  mov     r8d, 78h ; 'x'
0x18001d27f  jmp     loc_18001D320
0x18001d284  xorps   xmm0, xmm0
0x18001d287  lea     rcx, [rsp+78h+var_48.hEvent]; void **
0x18001d28c  movups  xmmword ptr [rsp+78h+var_48.Internal], xmm0
0x18001d291  movups  xmmword ptr [rsp+40h], xmm0
0x18001d296  call    ?GetThreadEvent@@YAJAEAPEAX@Z; GetThreadEvent(void * &)
0x18001d29b  mov     ebx, eax
0x18001d29d  test    eax, eax
0x18001d29f  jns     short loc_18001D2A9
0x18001d2a1  mov     r8d, 82h
0x18001d2a7  jmp     short loc_18001D320
0x18001d2a9  xor     eax, eax
0x18001d2ab  lea     rcx, [rsp+78h+var_48]
0x18001d2b0  cmp     [rdi], rax
0x18001d2b3  lea     r9, [rdi+0Ch]; struct BOID *
0x18001d2b7  mov     [rsp+78h+var_50], rcx; struct _OVERLAPPED *
0x18001d2bc  lea     r8, [rsp+78h+arg_18]; unsigned __int64 *
0x18001d2c4  setnz   al
0x18001d2c7  mov     rdx, rbp; void *
0x18001d2ca  mov     rcx, rsi; void *
0x18001d2cd  mov     [rsp+78h+var_58], eax; int
0x18001d2d1  call    ?ACMoveToSubqueue@@YAJPEAX0PEA_KPEAUBOID@@HPEAU_OVERLAPPED@@@Z; ACMoveToSubqueue(void *,void *,unsigned __int64 *,BOID *,int,_OVERLAPPED *)
0x18001d2d6  mov     edx, 1; unsigned int
0x18001d2db  mov     ecx, eax; int
0x18001d2dd  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18001d2e2  mov     ebx, eax
0x18001d2e4  test    eax, eax
0x18001d2e6  jns     short loc_18001D2F0
0x18001d2e8  mov     r8d, 8Ch
0x18001d2ee  jmp     short loc_18001D320
0x18001d2f0  cmp     ebx, 400E0006h
0x18001d2f6  jnz     short loc_18001D32E
0x18001d2f8  mov     rcx, [rsp+78h+var_48.hEvent]; hHandle
0x18001d2fd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001d300  call    cs:__imp_WaitForSingleObject
0x18001d306  mov     ecx, dword ptr [rsp+78h+var_48.Internal]; int
0x18001d30a  mov     edx, 1; unsigned int
0x18001d30f  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18001d314  mov     ebx, eax
0x18001d316  test    eax, eax
0x18001d318  jns     short loc_18001D32E
0x18001d31a  mov     r8d, 96h; unsigned __int16
0x18001d320  lea     rdx, aRtCrtmove; "rt/CRtMove"
0x18001d327  mov     ecx, ebx; int
0x18001d329  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001d32e  mov     eax, ebx
0x18001d330  add     rsp, 58h
0x18001d334  pop     rdi
0x18001d335  pop     rsi
0x18001d336  pop     rbp
0x18001d337  pop     rbx
0x18001d338  retn
```
