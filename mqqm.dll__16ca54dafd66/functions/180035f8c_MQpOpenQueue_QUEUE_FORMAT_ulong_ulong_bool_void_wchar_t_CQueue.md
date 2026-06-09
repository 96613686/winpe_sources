# MQpOpenQueue(QUEUE_FORMAT *,ulong,ulong,bool,void * *,wchar_t * *,CQueue * *)

- ea: `0x180035f8c`
- end: `0x180036103`
- name: `?MQpOpenQueue@@YAJPEAUQUEUE_FORMAT@@KK_NPEAPEAXPEAPEA_WPEAPEAVCQueue@@@Z`
- size: `375`
- prototype: `int(struct QUEUE_FORMAT *, unsigned int, unsigned int, bool, void **, wchar_t **, struct CQueue **)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022b10`
- `0x180041dd0`
- `0x18008a8b0`

## callees

- `0x180013468`
- `0x1800169e8`
- `0x18002c61c`
- `0x180035f8c`
- `0x180036298`
- `0x18004ca7c`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800360c5`
- `KERNEL32!WaitForSingleObject` at `0x1800360c5`
- `ntdll!NtClose` at `0x180036074`
- `ntdll!NtClose` at `0x1800360d4`
- `ntdll!NtClose` at `0x180036074`
- `ntdll!NtClose` at `0x1800360d4`
- `RPCRT4!UuidCreate` at `0x180035ff5`
- `RPCRT4!UuidCreate` at `0x180035ff5`

## string_xrefs

- `0x180036007`: `qmcommnd`

## pseudocode

```c
__int64 __fastcall MQpOpenQueue(
        struct QUEUE_FORMAT *a1,
        unsigned int a2,
        unsigned int a3,
        bool a4,
        void **a5,
        wchar_t **a6,
        struct CQueue **a7)
{
  RPC_STATUS v10; // ebx
  unsigned int v11; // r8d
  unsigned __int16 v12; // r8
  HANDLE v14; // rbx
  int v15; // edi
  HANDLE Handle; // [rsp+48h] [rbp-39h] BYREF
  struct _OVERLAPPED v18; // [rsp+50h] [rbp-31h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-11h] BYREF

  Uuid = 0;
  memset(&v18, 0, sizeof(v18));
  Handle = 0;
  GetThreadEvent(&v18.hEvent);
  v10 = UuidCreate(&Uuid);
  if ( v10 < 0 )
  {
    v12 = 48;
LABEL_3:
    LogMsgHR(v10, (wchar_t *)L"qmcommnd", v12);
    return (unsigned int)v10;
  }
  v10 = ACCreateHandle(&Handle, (struct _SECURITY_ATTRIBUTES *)a2, v11);
  if ( v10 < 0 )
  {
    v12 = 47;
    goto LABEL_3;
  }
  v14 = Handle;
  if ( MQpDeviceIoControl(Handle, 0x19650117u, &Uuid, 0x10u, 0, 0, &v18) != 259 )
  {
    NtClose(v14);
    v12 = 46;
    v10 = -1072824319;
    goto LABEL_3;
  }
  v15 = OpenQueueForRequest(a1, a2, a3, &Uuid, a4, a6, a7);
  if ( a4 && a6 && !*a7 || v15 < 0 )
  {
    NtClose(v14);
  }
  else
  {
    WaitForSingleObject(v18.hEvent, 0xFFFFFFFF);
    *a5 = v14;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180035f8c  mov     [rsp-8+arg_18], rbx
0x180035f91  push    rbp
0x180035f92  push    rsi
0x180035f93  push    rdi
0x180035f94  push    r12
0x180035f96  push    r13
0x180035f98  push    r14
0x180035f9a  push    r15
0x180035f9c  lea     rbp, [rsp-0Fh]
0x180035fa1  sub     rsp, 90h
0x180035fa8  mov     rax, cs:__security_cookie
0x180035faf  xor     rax, rsp
0x180035fb2  mov     [rbp+3Fh+var_40], rax
0x180035fb6  mov     r12, [rbp+3Fh+arg_20]
0x180035fba  xorps   xmm1, xmm1
0x180035fbd  mov     r14, [rbp+3Fh+arg_28]
0x180035fc1  mov     r13, rcx
0x180035fc4  mov     rsi, [rbp+3Fh+arg_30]
0x180035fc8  lea     rcx, [rbp+3Fh+var_70.hEvent]; void **
0x180035fcc  xorps   xmm0, xmm0
0x180035fcf  mov     [rbp+3Fh+var_80], r8d
0x180035fd3  movups  xmmword ptr [rbp+3Fh+Uuid.Data1], xmm0
0x180035fd7  mov     r15b, r9b
0x180035fda  mov     edi, edx
0x180035fdc  movups  xmmword ptr [rbp+3Fh+var_70.Internal], xmm1
0x180035fe0  mov     [rbp+3Fh+Handle], 0
0x180035fe8  movups  xmmword ptr [rbp-21h], xmm1
0x180035fec  call    ?GetThreadEvent@@YAJAEAPEAX@Z; GetThreadEvent(void * &)
0x180035ff1  lea     rcx, [rbp+3Fh+Uuid]; Uuid
0x180035ff5  call    cs:__imp_UuidCreate
0x180035ffb  mov     ebx, eax
0x180035ffd  test    eax, eax
0x180035fff  jns     short loc_18003601C
0x180036001  mov     r8d, 30h ; '0'; unsigned __int16
0x180036007  lea     rdx, aQmcommnd; "qmcommnd"
0x18003600e  mov     ecx, ebx; int
0x180036010  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180036015  mov     eax, ebx
0x180036017  jmp     loc_1800360DC
0x18003601c  mov     edx, edi; struct _SECURITY_ATTRIBUTES *
0x18003601e  lea     rcx, [rbp+3Fh+Handle]; void **
0x180036022  call    ?ACCreateHandle@@YAJPEAPEAXKK@Z; ACCreateHandle(void * *,ulong,ulong)
0x180036027  mov     ebx, eax
0x180036029  test    eax, eax
0x18003602b  jns     short loc_180036035
0x18003602d  mov     r8d, 2Fh ; '/'
0x180036033  jmp     short loc_180036007
0x180036035  mov     rbx, [rbp+3Fh+Handle]
0x180036039  lea     rax, [rbp+3Fh+var_70]
0x18003603d  mov     [rsp+0C0h+var_90], rax; struct _OVERLAPPED *
0x180036042  lea     r8, [rbp+3Fh+Uuid]; void *
0x180036046  mov     dword ptr [rsp+0C0h+var_98], 0; unsigned int
0x18003604e  mov     r9d, 10h; unsigned int
0x180036054  mov     edx, 19650117h; unsigned int
0x180036059  mov     [rsp+0C0h+var_A0], 0; void *
0x180036062  mov     rcx, rbx; void *
0x180036065  call    ?MQpDeviceIoControl@@YAJPEAXK0K0KPEAU_OVERLAPPED@@@Z; MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,_OVERLAPPED *)
0x18003606a  cmp     eax, 103h
0x18003606f  jz      short loc_180036087
0x180036071  mov     rcx, rbx; Handle
0x180036074  call    cs:__imp_NtClose
0x18003607a  mov     r8d, 2Eh ; '.'
0x180036080  mov     ebx, 0C00E0001h
0x180036085  jmp     short loc_180036007
0x180036087  mov     r8d, [rbp+3Fh+var_80]; unsigned int
0x18003608b  lea     r9, [rbp+3Fh+Uuid]; struct _GUID *
0x18003608f  mov     [rsp+0C0h+var_90], rsi; struct CQueue **
0x180036094  mov     edx, edi; unsigned int
0x180036096  mov     [rsp+0C0h+var_98], r14; wchar_t **
0x18003609b  mov     rcx, r13; struct QUEUE_FORMAT *
0x18003609e  mov     byte ptr [rsp+0C0h+var_A0], r15b; bool
0x1800360a3  call    ?OpenQueueForRequest@@YAJPEAUQUEUE_FORMAT@@KKAEBU_GUID@@_NPEAPEA_WPEAPEAVCQueue@@@Z; OpenQueueForRequest(QUEUE_FORMAT *,ulong,ulong,_GUID const &,bool,wchar_t * *,CQueue * *)
0x1800360a8  mov     edi, eax
0x1800360aa  test    r15b, r15b
0x1800360ad  jz      short loc_1800360BA
0x1800360af  test    r14, r14
0x1800360b2  jz      short loc_1800360BA
0x1800360b4  cmp     qword ptr [rsi], 0
0x1800360b8  jz      short loc_1800360D1
0x1800360ba  test    edi, edi
0x1800360bc  js      short loc_1800360D1
0x1800360be  mov     rcx, [rbp+3Fh+var_70.hEvent]; hHandle
0x1800360c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800360c5  call    cs:__imp_WaitForSingleObject
0x1800360cb  mov     [r12], rbx
0x1800360cf  jmp     short loc_1800360DA
0x1800360d1  mov     rcx, rbx; Handle
0x1800360d4  call    cs:__imp_NtClose
0x1800360da  mov     eax, edi
0x1800360dc  mov     rcx, [rbp+3Fh+var_40]
0x1800360e0  xor     rcx, rsp; StackCookie
0x1800360e3  call    __security_check_cookie
0x1800360e8  mov     rbx, [rsp+0C0h+arg_18]
0x1800360f0  add     rsp, 90h
0x1800360f7  pop     r15
0x1800360f9  pop     r14
0x1800360fb  pop     r13
0x1800360fd  pop     r12
0x1800360ff  pop     rdi
0x180036100  pop     rsi
0x180036101  pop     rbp
0x180036102  retn
```
