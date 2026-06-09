# RdpWinTaskScheduler::InitializeInstance(void)

- ea: `0x1401091e0`
- end: `0x140109406`
- name: `?InitializeInstance@RdpWinTaskScheduler@@UEAA?AW4_XResult32@@XZ`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x14000cfb0`
- `0x14001e158`
- `0x1401091e0`
- `0x140109b08`
- `0x140114010`

## import_xrefs

- `KERNEL32!SetThreadpoolThreadMinimum` at `0x14010932b`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x14010932b`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x140109317`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x140109317`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x140109378`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x140109378`
- `KERNEL32!CreateThreadpool` at `0x1401092b9`
- `KERNEL32!CreateThreadpool` at `0x1401092b9`
- `KERNEL32!GetLastError` at `0x1401092f3`
- `KERNEL32!GetLastError` at `0x14010935c`
- `KERNEL32!GetLastError` at `0x1401093a6`
- `KERNEL32!GetLastError` at `0x1401092f3`
- `KERNEL32!GetLastError` at `0x14010935c`
- `KERNEL32!GetLastError` at `0x1401093a6`

## pseudocode

```c
__int64 __fastcall RdpWinTaskScheduler::InitializeInstance(__int64 a1)
{
  __int64 v2; // rdx
  unsigned int v3; // ebx
  __int64 v4; // r8
  unsigned int ActivityIdPrefix; // eax
  struct _TP_POOL *Threadpool; // rax
  DWORD LastError; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // eax
  __int64 v12; // rdx
  DWORD v13; // edx
  DWORD v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8

  v3 = (**(__int64 (__fastcall ***)(__int64))(a1 + 16))(a1 + 16);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v2, v4);
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        11,
        WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids,
        ActivityIdPrefix,
        v3,
        v3);
    }
    goto LABEL_28;
  }
  *(_DWORD *)(a1 + 56) = 3;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 116) = 1;
  *(_DWORD *)(a1 + 120) = 72;
  if ( !*(_DWORD *)(a1 + 128) )
  {
LABEL_21:
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *(_QWORD *)(a1 + 48) = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      *(_QWORD *)(a1 + 72) = ThreadpoolCleanupGroup;
      *(_QWORD *)(a1 + 80) = RdpWinTaskScheduler::staticCleanupGroupCancelCallback;
      return v3;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_27;
    }
    LastError = GetLastError();
    v11 = RdpX_GetActivityIdPrefix(v20, v19, v21);
    v12 = 14;
    goto LABEL_26;
  }
  Threadpool = CreateThreadpool(0);
  *(_QWORD *)(a1 + 40) = Threadpool;
  if ( Threadpool )
  {
    v13 = *(_DWORD *)(a1 + 136);
    if ( v13 )
      SetThreadpoolThreadMaximum(Threadpool, v13);
    v14 = *(_DWORD *)(a1 + 132);
    if ( v14 && !SetThreadpoolThreadMinimum(*(PTP_POOL *)(a1 + 40), v14) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
      {
        goto LABEL_27;
      }
      LastError = GetLastError();
      v11 = RdpX_GetActivityIdPrefix(v16, v15, v17);
      v12 = 13;
      goto LABEL_26;
    }
    *(_QWORD *)(a1 + 64) = *(_QWORD *)(a1 + 40);
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
  {
    goto LABEL_27;
  }
  LastError = GetLastError();
  v11 = RdpX_GetActivityIdPrefix(v9, v8, v10);
  v12 = 12;
LABEL_26:
  WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 7), v12, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids, v11, LastError);
LABEL_27:
  v3 = -1;
LABEL_28:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x1401091e0  mov     [rsp+arg_0], rbx
0x1401091e5  push    rdi
0x1401091e6  sub     rsp, 30h
0x1401091ea  mov     rdi, rcx
0x1401091ed  add     rcx, 10h
0x1401091f1  mov     rax, [rcx]
0x1401091f4  mov     rax, [rax]
0x1401091f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401091fc  mov     ebx, eax
0x1401091fe  test    eax, eax
0x140109200  jz      short loc_14010925E
0x140109202  mov     rcx, cs:WPP_GLOBAL_Control
0x140109209  lea     rax, WPP_GLOBAL_Control
0x140109210  cmp     rcx, rax
0x140109213  jz      loc_1401093D9
0x140109219  test    byte ptr [rcx+44h], 10h
0x14010921d  jz      loc_1401093D9
0x140109223  cmp     byte ptr [rcx+41h], 2
0x140109227  jb      loc_1401093D9
0x14010922d  call    RdpX_GetActivityIdPrefix
0x140109232  mov     rcx, cs:WPP_GLOBAL_Control
0x140109239  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x140109240  mov     edx, 0Bh
0x140109245  mov     [rsp+38h+var_10], ebx
0x140109249  mov     r9d, eax
0x14010924c  mov     [rsp+38h+var_18], ebx
0x140109250  mov     rcx, [rcx+38h]
0x140109254  call    WPP_SF_DLD
0x140109259  jmp     loc_1401093D9
0x14010925e  mov     dword ptr [rdi+38h], 3
0x140109265  mov     qword ptr [rdi+40h], 0
0x14010926d  mov     qword ptr [rdi+48h], 0
0x140109275  mov     qword ptr [rdi+50h], 0
0x14010927d  mov     qword ptr [rdi+58h], 0
0x140109285  mov     qword ptr [rdi+60h], 0
0x14010928d  mov     qword ptr [rdi+68h], 0
0x140109295  mov     dword ptr [rdi+70h], 0
0x14010929c  mov     dword ptr [rdi+74h], 1
0x1401092a3  mov     dword ptr [rdi+78h], 48h ; 'H'
0x1401092aa  cmp     dword ptr [rdi+80h], 0
0x1401092b1  jz      loc_140109378
0x1401092b7  xor     ecx, ecx; reserved
0x1401092b9  call    cs:__imp_CreateThreadpool
0x1401092bf  mov     [rdi+28h], rax
0x1401092c3  test    rax, rax
0x1401092c6  jnz     short loc_14010930A
0x1401092c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1401092cf  lea     rax, WPP_GLOBAL_Control
0x1401092d6  cmp     rcx, rax
0x1401092d9  jz      loc_1401093D6
0x1401092df  test    byte ptr [rcx+44h], 10h
0x1401092e3  jz      loc_1401093D6
0x1401092e9  cmp     byte ptr [rcx+41h], 2
0x1401092ed  jb      loc_1401093D6
0x1401092f3  call    cs:__imp_GetLastError
0x1401092f9  mov     ebx, eax
0x1401092fb  call    RdpX_GetActivityIdPrefix
0x140109300  mov     edx, 0Ch
0x140109305  jmp     loc_1401093B8
0x14010930a  mov     edx, [rdi+88h]; cthrdMost
0x140109310  test    edx, edx
0x140109312  jz      short loc_14010931D
0x140109314  mov     rcx, rax; ptpp
0x140109317  call    cs:__imp_SetThreadpoolThreadMaximum
0x14010931d  mov     edx, [rdi+84h]; cthrdMic
0x140109323  test    edx, edx
0x140109325  jz      short loc_140109370
0x140109327  mov     rcx, [rdi+28h]; ptpp
0x14010932b  call    cs:__imp_SetThreadpoolThreadMinimum
0x140109331  test    eax, eax
0x140109333  jnz     short loc_140109370
0x140109335  mov     rcx, cs:WPP_GLOBAL_Control
0x14010933c  lea     rax, WPP_GLOBAL_Control
0x140109343  cmp     rcx, rax
0x140109346  jz      loc_1401093D6
0x14010934c  test    byte ptr [rcx+44h], 10h
0x140109350  jz      loc_1401093D6
0x140109356  cmp     byte ptr [rcx+41h], 2
0x14010935a  jb      short loc_1401093D6
0x14010935c  call    cs:__imp_GetLastError
0x140109362  mov     ebx, eax
0x140109364  call    RdpX_GetActivityIdPrefix
0x140109369  mov     edx, 0Dh
0x14010936e  jmp     short loc_1401093B8
0x140109370  mov     rax, [rdi+28h]
0x140109374  mov     [rdi+40h], rax
0x140109378  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14010937e  mov     [rdi+30h], rax
0x140109382  test    rax, rax
0x140109385  jnz     short loc_1401093EA
0x140109387  mov     rcx, cs:WPP_GLOBAL_Control
0x14010938e  lea     rax, WPP_GLOBAL_Control
0x140109395  cmp     rcx, rax
0x140109398  jz      short loc_1401093D6
0x14010939a  test    byte ptr [rcx+44h], 10h
0x14010939e  jz      short loc_1401093D6
0x1401093a0  cmp     byte ptr [rcx+41h], 2
0x1401093a4  jb      short loc_1401093D6
0x1401093a6  call    cs:__imp_GetLastError
0x1401093ac  mov     ebx, eax
0x1401093ae  call    RdpX_GetActivityIdPrefix
0x1401093b3  mov     edx, 0Eh
0x1401093b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1401093bf  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x1401093c6  mov     r9d, eax
0x1401093c9  mov     [rsp+38h+var_18], ebx
0x1401093cd  mov     rcx, [rcx+38h]
0x1401093d1  call    WPP_SF_Dd
0x1401093d6  or      ebx, 0FFFFFFFFh
0x1401093d9  mov     rax, [rdi]
0x1401093dc  mov     rcx, rdi
0x1401093df  mov     rax, [rax+20h]
0x1401093e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401093e8  jmp     short loc_1401093F9
0x1401093ea  mov     [rdi+48h], rax
0x1401093ee  lea     rax, ?staticCleanupGroupCancelCallback@RdpWinTaskScheduler@@KAXPEAX0@Z; RdpWinTaskScheduler::staticCleanupGroupCancelCallback(void *,void *)
0x1401093f5  mov     [rdi+50h], rax
0x1401093f9  mov     eax, ebx
0x1401093fb  mov     rbx, [rsp+38h+arg_0]
0x140109400  add     rsp, 30h
0x140109404  pop     rdi
0x140109405  retn
```
