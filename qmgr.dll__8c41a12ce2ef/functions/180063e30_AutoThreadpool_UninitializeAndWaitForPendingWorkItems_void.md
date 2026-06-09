# AutoThreadpool::UninitializeAndWaitForPendingWorkItems(void)

- ea: `0x180063e30`
- end: `0x180063f95`
- name: `?UninitializeAndWaitForPendingWorkItems@AutoThreadpool@@QEAAXXZ`
- size: `357`
- prototype: `void __fastcall(AutoThreadpool *__hidden this)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e7fc`
- `0x180053260`
- `0x180063c98`
- `0x180063da0`
- `0x180094a3c`
- `0x18009d9e0`
- `0x1800bb4d8`
- `0x1800e9390`
- `0x180102a00`

## callees

- `0x180033480`
- `0x180063e30`
- `0x18009d024`
- `0x1800ab7fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063e88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063e88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063f7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180063ef3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180063ef3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180063ee6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180063ee6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180063f3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180063f3b`

## pseudocode

```c
void __fastcall AutoThreadpool::UninitializeAndWaitForPendingWorkItems(AutoThreadpool *this)
{
  bool v1; // zf
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  EVENT_LOG *v4; // rax
  struct _TP_POOL *v5; // rcx
  char v6[8]; // [rsp+20h] [rbp-18h] BYREF
  char *v7; // [rsp+28h] [rbp-10h]

  v1 = *((_BYTE *)this + 48) == 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v7 = (char *)this + 8;
  if ( !v1
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v2);
  }
  EnterCriticalSection(v2);
  v1 = *((_QWORD *)this + 7) == 0;
  v6[0] = 1;
  if ( v1 )
  {
    HoldCritSec::~HoldCritSec((HoldCritSec *)v6);
    return;
  }
  if ( *((_QWORD *)this + 17) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_7a43e90641713c5942580354798d2ea8_Traceguids);
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 17), 0, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 17));
    *((_QWORD *)this + 17) = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_7a43e90641713c5942580354798d2ea8_Traceguids);
  }
  v4 = WPP_GLOBAL_Control;
LABEL_15:
  v5 = (struct _TP_POOL *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    CloseThreadpool(v5);
    *((_QWORD *)this + 7) = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( LOBYTE(v2[1].DebugInfo) && v4 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)v4 + 2), 16, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v2);
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180063e30  mov     [rsp+arg_0], rbx
0x180063e35  mov     [rsp+arg_8], rsi
0x180063e3a  push    rdi
0x180063e3b  sub     rsp, 30h
0x180063e3f  cmp     byte ptr [rcx+30h], 0
0x180063e43  lea     rbx, [rcx+8]
0x180063e47  mov     rdi, rcx
0x180063e4a  mov     [rsp+38h+var_10], rbx
0x180063e4f  lea     rsi, WPP_GLOBAL_Control
0x180063e56  jz      short loc_180063E85
0x180063e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e5f  cmp     rcx, rsi
0x180063e62  jz      short loc_180063E85
0x180063e64  test    dword ptr [rcx+1Ch], 100h
0x180063e6b  jz      short loc_180063E85
0x180063e6d  mov     rcx, [rcx+10h]
0x180063e71  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180063e78  mov     edx, 0Fh
0x180063e7d  mov     r9, rbx
0x180063e80  call    WPP_SF_q
0x180063e85  mov     rcx, rbx; lpCriticalSection
0x180063e88  call    cs:__imp_EnterCriticalSection
0x180063e8e  cmp     qword ptr [rdi+38h], 0
0x180063e93  mov     [rsp+38h+var_18], 1
0x180063e98  jnz     short loc_180063EA9
0x180063e9a  lea     rcx, [rsp+38h+var_18]; this
0x180063e9f  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x180063ea4  jmp     loc_180063F85
0x180063ea9  cmp     qword ptr [rdi+88h], 0
0x180063eb1  jz      short loc_180063F2B
0x180063eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180063eba  cmp     rcx, rsi
0x180063ebd  jz      short loc_180063EDA
0x180063ebf  test    byte ptr [rcx+1Ch], 1
0x180063ec3  jz      short loc_180063EDA
0x180063ec5  mov     rcx, [rcx+10h]
0x180063ec9  lea     r8, WPP_7a43e90641713c5942580354798d2ea8_Traceguids
0x180063ed0  mov     edx, 0Ch
0x180063ed5  call    WPP_SF_
0x180063eda  mov     rcx, [rdi+88h]; ptpcg
0x180063ee1  xor     r8d, r8d; pvCleanupContext
0x180063ee4  xor     edx, edx; fCancelPendingCallbacks
0x180063ee6  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180063eec  mov     rcx, [rdi+88h]; ptpcg
0x180063ef3  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180063ef9  mov     qword ptr [rdi+88h], 0
0x180063f04  mov     rax, cs:WPP_GLOBAL_Control
0x180063f0b  cmp     rax, rsi
0x180063f0e  jz      short loc_180063F32
0x180063f10  test    byte ptr [rax+1Ch], 1
0x180063f14  jz      short loc_180063F32
0x180063f16  mov     rcx, [rax+10h]
0x180063f1a  lea     r8, WPP_7a43e90641713c5942580354798d2ea8_Traceguids
0x180063f21  mov     edx, 0Dh
0x180063f26  call    WPP_SF_
0x180063f2b  mov     rax, cs:WPP_GLOBAL_Control
0x180063f32  mov     rcx, [rdi+38h]; ptpp
0x180063f36  test    rcx, rcx
0x180063f39  jz      short loc_180063F50
0x180063f3b  call    cs:__imp_CloseThreadpool
0x180063f41  mov     qword ptr [rdi+38h], 0
0x180063f49  mov     rax, cs:WPP_GLOBAL_Control
0x180063f50  cmp     byte ptr [rbx+28h], 0
0x180063f54  jz      short loc_180063F7C
0x180063f56  cmp     rax, rsi
0x180063f59  jz      short loc_180063F7C
0x180063f5b  test    dword ptr [rax+1Ch], 100h
0x180063f62  jz      short loc_180063F7C
0x180063f64  mov     rcx, [rax+10h]
0x180063f68  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180063f6f  mov     edx, 10h
0x180063f74  mov     r9, rbx
0x180063f77  call    WPP_SF_q
0x180063f7c  mov     rcx, rbx; lpCriticalSection
0x180063f7f  call    cs:__imp_LeaveCriticalSection
0x180063f85  mov     rbx, [rsp+38h+arg_0]
0x180063f8a  mov     rsi, [rsp+38h+arg_8]
0x180063f8f  add     rsp, 30h
0x180063f93  pop     rdi
0x180063f94  retn
```
