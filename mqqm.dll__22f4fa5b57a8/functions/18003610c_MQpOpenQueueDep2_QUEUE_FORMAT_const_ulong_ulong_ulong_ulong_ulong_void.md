# MQpOpenQueueDep2(QUEUE_FORMAT const *,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x18003610c`
- end: `0x18003628f`
- name: `?MQpOpenQueueDep2@@YAJPEBUQUEUE_FORMAT@@KKKKKPEAPEAX@Z`
- size: `387`
- prototype: `__int64 __fastcall(const struct QUEUE_FORMAT *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022b10`

## callees

- `0x180013468`
- `0x1800169e8`
- `0x1800202e4`
- `0x18002c61c`
- `0x18003610c`
- `0x1800364fc`
- `0x18004ca7c`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180036250`
- `KERNEL32!WaitForSingleObject` at `0x180036250`
- `ntdll!NtClose` at `0x1800361e6`
- `ntdll!NtClose` at `0x18003625e`
- `ntdll!NtClose` at `0x1800361e6`
- `ntdll!NtClose` at `0x18003625e`
- `RPCRT4!UuidCreate` at `0x180036167`
- `RPCRT4!UuidCreate` at `0x180036167`

## string_xrefs

- `0x180036179`: `qmcommnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MQpOpenQueueDep2(
        const struct QUEUE_FORMAT *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        void **a7)
{
  RPC_STATUS v11; // ebx
  unsigned int v12; // r8d
  unsigned __int16 v13; // r8
  HANDLE v15; // rbx
  CQueueMgr *v16; // rcx
  int v17; // edi
  void **v18; // [rsp+58h] [rbp-39h]
  HANDLE Handle; // [rsp+60h] [rbp-31h] BYREF
  struct _OVERLAPPED v20; // [rsp+68h] [rbp-29h] BYREF
  UUID Uuid; // [rsp+88h] [rbp-9h] BYREF

  Handle = 0;
  Uuid = 0;
  memset(&v20, 0, sizeof(v20));
  GetThreadEvent(&v20.hEvent);
  v11 = UuidCreate(&Uuid);
  if ( v11 < 0 )
  {
    v13 = 45;
LABEL_3:
    LogMsgHR(v11, (wchar_t *)L"qmcommnd", v13);
    return (unsigned int)v11;
  }
  v11 = ACCreateHandle(&Handle, (struct _SECURITY_ATTRIBUTES *)a2, v12);
  if ( v11 < 0 )
  {
    v13 = 44;
    goto LABEL_3;
  }
  v15 = Handle;
  if ( MQpDeviceIoControl(Handle, 0x19650117u, &Uuid, 0x10u, 0, 0, (struct _IO_STATUS_BLOCK *)&v20) != 259 )
  {
    NtClose(v15);
    v13 = 43;
    v11 = -1072824319;
    goto LABEL_3;
  }
  Handle = 0;
  v17 = CQueueMgr::OpenRRQueue(v16, a1, &Uuid, a2, a3, a4, a5, a6, 0, 0, (struct CBindHandle *)&Handle, v18);
  if ( v17 < 0 )
  {
    NtClose(v15);
  }
  else
  {
    WaitForSingleObject(v20.hEvent, 0xFFFFFFFF);
    *a7 = v15;
  }
  CBindHandle::free((CBindHandle *)&Handle);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18003610c  push    rbp
0x18003610e  push    rbx
0x18003610f  push    rsi
0x180036110  push    rdi
0x180036111  push    r12
0x180036113  push    r14
0x180036115  push    r15
0x180036117  lea     rbp, [rsp-0Fh]
0x18003611c  sub     rsp, 0A0h
0x180036123  mov     rax, cs:__security_cookie
0x18003612a  xor     rax, rsp
0x18003612d  mov     [rbp+3Fh+var_38], rax
0x180036131  mov     r14d, r9d
0x180036134  mov     r12d, r8d
0x180036137  mov     edi, edx
0x180036139  mov     r15, rcx
0x18003613c  mov     rsi, [rbp+3Fh+arg_30]
0x180036140  mov     [rbp+3Fh+Handle], 0
0x180036148  xorps   xmm0, xmm0
0x18003614b  movups  xmmword ptr [rbp+3Fh+Uuid.Data1], xmm0
0x18003614f  xorps   xmm1, xmm1
0x180036152  movups  xmmword ptr [rbp+3Fh+var_68.Internal], xmm1
0x180036156  movups  xmmword ptr [rbp+3Fh+var_68.10h], xmm1
0x18003615a  lea     rcx, [rbp+3Fh+var_68.hEvent]; void **
0x18003615e  call    ?GetThreadEvent@@YAJAEAPEAX@Z; GetThreadEvent(void * &)
0x180036163  lea     rcx, [rbp+3Fh+Uuid]; Uuid
0x180036167  call    cs:__imp_UuidCreate
0x18003616d  mov     ebx, eax
0x18003616f  test    eax, eax
0x180036171  jns     short loc_18003618E
0x180036173  mov     r8d, 2Dh ; '-'; unsigned __int16
0x180036179  lea     rdx, aQmcommnd; "qmcommnd"
0x180036180  mov     ecx, ebx; int
0x180036182  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036187  mov     eax, ebx
0x180036189  jmp     loc_180036271
0x18003618e  mov     edx, edi; struct _SECURITY_ATTRIBUTES *
0x180036190  lea     rcx, [rbp+3Fh+Handle]; void **
0x180036194  call    ?ACCreateHandle@@YAJPEAPEAXKK@Z; ACCreateHandle(void * *,ulong,ulong)
0x180036199  mov     ebx, eax
0x18003619b  test    eax, eax
0x18003619d  jns     short loc_1800361A7
0x18003619f  mov     r8d, 2Ch ; ','
0x1800361a5  jmp     short loc_180036179
0x1800361a7  lea     rax, [rbp+3Fh+var_68]
0x1800361ab  mov     [rsp+0D0h+var_A0], rax; struct _OVERLAPPED *
0x1800361b0  mov     [rsp+0D0h+var_A8], 0; unsigned int
0x1800361b8  mov     [rsp+0D0h+var_B0], 0; void *
0x1800361c1  mov     r9d, 10h; unsigned int
0x1800361c7  lea     r8, [rbp+3Fh+Uuid]; void *
0x1800361cb  mov     edx, 19650117h; unsigned int
0x1800361d0  mov     rbx, [rbp+3Fh+Handle]
0x1800361d4  mov     rcx, rbx; void *
0x1800361d7  call    ?MQpDeviceIoControl@@YAJPEAXK0K0KPEAU_OVERLAPPED@@@Z; MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,_OVERLAPPED *)
0x1800361dc  cmp     eax, 103h
0x1800361e1  jz      short loc_1800361F9
0x1800361e3  mov     rcx, rbx; Handle
0x1800361e6  call    cs:__imp_NtClose
0x1800361ec  mov     r8d, 2Bh ; '+'
0x1800361f2  mov     ebx, 0C00E0001h
0x1800361f7  jmp     short loc_180036179
0x1800361f9  mov     [rbp+3Fh+Handle], 0
0x180036201  lea     rax, [rbp+3Fh+Handle]
0x180036205  mov     [rsp+0D0h+var_80], rax; struct CBindHandle *
0x18003620a  mov     [rsp+0D0h+var_88], 0; struct CAutoCloseNewRemoteReadCtxAndBind *
0x180036213  mov     [rsp+0D0h+var_90], 0; unsigned __int64
0x18003621c  mov     eax, [rbp+3Fh+arg_28]
0x18003621f  mov     [rsp+0D0h+var_98], eax; unsigned int
0x180036223  mov     eax, [rbp+3Fh+arg_20]
0x180036226  mov     dword ptr [rsp+0D0h+var_A0], eax; unsigned int
0x18003622a  mov     [rsp+0D0h+var_A8], r14d; unsigned int
0x18003622f  mov     dword ptr [rsp+0D0h+var_B0], r12d; unsigned int
0x180036234  mov     r9d, edi; unsigned int
0x180036237  lea     r8, [rbp+3Fh+Uuid]; struct _GUID *
0x18003623b  mov     rdx, r15; struct QUEUE_FORMAT *
0x18003623e  call    ?OpenRRQueue@CQueueMgr@@QEAAJPEBUQUEUE_FORMAT@@AEBU_GUID@@KKKKK_KPEAVCAutoCloseNewRemoteReadCtxAndBind@@AEAVCBindHandle@@PEAPEAX@Z; CQueueMgr::OpenRRQueue(QUEUE_FORMAT const *,_GUID const &,ulong,ulong,ulong,ulong,ulong,unsigned __int64,CAutoCloseNewRemoteReadCtxAndBind *,CBindHandle &,void * *)
0x180036243  mov     edi, eax
0x180036245  test    eax, eax
0x180036247  js      short loc_18003625B
0x180036249  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003624c  mov     rcx, [rbp+3Fh+var_68.hEvent]; hHandle
0x180036250  call    cs:__imp_WaitForSingleObject
0x180036256  mov     [rsi], rbx
0x180036259  jmp     short loc_180036265
0x18003625b  mov     rcx, rbx; Handle
0x18003625e  call    cs:__imp_NtClose
0x180036264  nop
0x180036265  lea     rcx, [rbp+3Fh+Handle]; this
0x180036269  call    ?free@CBindHandle@@QEAAXXZ; CBindHandle::free(void)
0x18003626e  nop
0x18003626f  mov     eax, edi
0x180036271  mov     rcx, [rbp+3Fh+var_38]
0x180036275  xor     rcx, rsp; StackCookie
0x180036278  call    __security_check_cookie
0x18003627d  add     rsp, 0A0h
0x180036284  pop     r15
0x180036286  pop     r14
0x180036288  pop     r12
0x18003628a  pop     rdi
0x18003628b  pop     rsi
0x18003628c  pop     rbx
0x18003628d  pop     rbp
0x18003628e  retn
```
