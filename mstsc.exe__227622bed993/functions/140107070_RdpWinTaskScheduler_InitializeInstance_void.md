# RdpWinTaskScheduler::InitializeInstance(void)

- ea: `0x140107070`
- end: `0x140107296`
- name: `?InitializeInstance@RdpWinTaskScheduler@@UEAA?AW4_XResult32@@XZ`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x14000cfb0`
- `0x14001e158`
- `0x140107070`
- `0x140107998`
- `0x140112010`

## import_xrefs

- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1401071bb`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1401071bb`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1401071a7`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1401071a7`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x140107208`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x140107208`
- `KERNEL32!CreateThreadpool` at `0x140107149`
- `KERNEL32!CreateThreadpool` at `0x140107149`
- `KERNEL32!GetLastError` at `0x140107183`
- `KERNEL32!GetLastError` at `0x1401071ec`
- `KERNEL32!GetLastError` at `0x140107236`
- `KERNEL32!GetLastError` at `0x140107183`
- `KERNEL32!GetLastError` at `0x1401071ec`
- `KERNEL32!GetLastError` at `0x140107236`

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
0x140107070  mov     [rsp+arg_0], rbx
0x140107075  push    rdi
0x140107076  sub     rsp, 30h
0x14010707a  mov     rdi, rcx
0x14010707d  add     rcx, 10h
0x140107081  mov     rax, [rcx]
0x140107084  mov     rax, [rax]
0x140107087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010708c  mov     ebx, eax
0x14010708e  test    eax, eax
0x140107090  jz      short loc_1401070EE
0x140107092  mov     rcx, cs:WPP_GLOBAL_Control
0x140107099  lea     rax, WPP_GLOBAL_Control
0x1401070a0  cmp     rcx, rax
0x1401070a3  jz      loc_140107269
0x1401070a9  test    byte ptr [rcx+44h], 10h
0x1401070ad  jz      loc_140107269
0x1401070b3  cmp     byte ptr [rcx+41h], 2
0x1401070b7  jb      loc_140107269
0x1401070bd  call    RdpX_GetActivityIdPrefix
0x1401070c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1401070c9  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x1401070d0  mov     edx, 0Bh
0x1401070d5  mov     [rsp+38h+var_10], ebx
0x1401070d9  mov     r9d, eax
0x1401070dc  mov     [rsp+38h+var_18], ebx
0x1401070e0  mov     rcx, [rcx+38h]
0x1401070e4  call    WPP_SF_DLD
0x1401070e9  jmp     loc_140107269
0x1401070ee  mov     dword ptr [rdi+38h], 3
0x1401070f5  mov     qword ptr [rdi+40h], 0
0x1401070fd  mov     qword ptr [rdi+48h], 0
0x140107105  mov     qword ptr [rdi+50h], 0
0x14010710d  mov     qword ptr [rdi+58h], 0
0x140107115  mov     qword ptr [rdi+60h], 0
0x14010711d  mov     qword ptr [rdi+68h], 0
0x140107125  mov     dword ptr [rdi+70h], 0
0x14010712c  mov     dword ptr [rdi+74h], 1
0x140107133  mov     dword ptr [rdi+78h], 48h ; 'H'
0x14010713a  cmp     dword ptr [rdi+80h], 0
0x140107141  jz      loc_140107208
0x140107147  xor     ecx, ecx; reserved
0x140107149  call    cs:__imp_CreateThreadpool
0x14010714f  mov     [rdi+28h], rax
0x140107153  test    rax, rax
0x140107156  jnz     short loc_14010719A
0x140107158  mov     rcx, cs:WPP_GLOBAL_Control
0x14010715f  lea     rax, WPP_GLOBAL_Control
0x140107166  cmp     rcx, rax
0x140107169  jz      loc_140107266
0x14010716f  test    byte ptr [rcx+44h], 10h
0x140107173  jz      loc_140107266
0x140107179  cmp     byte ptr [rcx+41h], 2
0x14010717d  jb      loc_140107266
0x140107183  call    cs:__imp_GetLastError
0x140107189  mov     ebx, eax
0x14010718b  call    RdpX_GetActivityIdPrefix
0x140107190  mov     edx, 0Ch
0x140107195  jmp     loc_140107248
0x14010719a  mov     edx, [rdi+88h]; cthrdMost
0x1401071a0  test    edx, edx
0x1401071a2  jz      short loc_1401071AD
0x1401071a4  mov     rcx, rax; ptpp
0x1401071a7  call    cs:__imp_SetThreadpoolThreadMaximum
0x1401071ad  mov     edx, [rdi+84h]; cthrdMic
0x1401071b3  test    edx, edx
0x1401071b5  jz      short loc_140107200
0x1401071b7  mov     rcx, [rdi+28h]; ptpp
0x1401071bb  call    cs:__imp_SetThreadpoolThreadMinimum
0x1401071c1  test    eax, eax
0x1401071c3  jnz     short loc_140107200
0x1401071c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401071cc  lea     rax, WPP_GLOBAL_Control
0x1401071d3  cmp     rcx, rax
0x1401071d6  jz      loc_140107266
0x1401071dc  test    byte ptr [rcx+44h], 10h
0x1401071e0  jz      loc_140107266
0x1401071e6  cmp     byte ptr [rcx+41h], 2
0x1401071ea  jb      short loc_140107266
0x1401071ec  call    cs:__imp_GetLastError
0x1401071f2  mov     ebx, eax
0x1401071f4  call    RdpX_GetActivityIdPrefix
0x1401071f9  mov     edx, 0Dh
0x1401071fe  jmp     short loc_140107248
0x140107200  mov     rax, [rdi+28h]
0x140107204  mov     [rdi+40h], rax
0x140107208  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14010720e  mov     [rdi+30h], rax
0x140107212  test    rax, rax
0x140107215  jnz     short loc_14010727A
0x140107217  mov     rcx, cs:WPP_GLOBAL_Control
0x14010721e  lea     rax, WPP_GLOBAL_Control
0x140107225  cmp     rcx, rax
0x140107228  jz      short loc_140107266
0x14010722a  test    byte ptr [rcx+44h], 10h
0x14010722e  jz      short loc_140107266
0x140107230  cmp     byte ptr [rcx+41h], 2
0x140107234  jb      short loc_140107266
0x140107236  call    cs:__imp_GetLastError
0x14010723c  mov     ebx, eax
0x14010723e  call    RdpX_GetActivityIdPrefix
0x140107243  mov     edx, 0Eh
0x140107248  mov     rcx, cs:WPP_GLOBAL_Control
0x14010724f  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x140107256  mov     r9d, eax
0x140107259  mov     [rsp+38h+var_18], ebx
0x14010725d  mov     rcx, [rcx+38h]
0x140107261  call    WPP_SF_Dd
0x140107266  or      ebx, 0FFFFFFFFh
0x140107269  mov     rax, [rdi]
0x14010726c  mov     rcx, rdi
0x14010726f  mov     rax, [rax+20h]
0x140107273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140107278  jmp     short loc_140107289
0x14010727a  mov     [rdi+48h], rax
0x14010727e  lea     rax, ?staticCleanupGroupCancelCallback@RdpWinTaskScheduler@@KAXPEAX0@Z; RdpWinTaskScheduler::staticCleanupGroupCancelCallback(void *,void *)
0x140107285  mov     [rdi+50h], rax
0x140107289  mov     eax, ebx
0x14010728b  mov     rbx, [rsp+38h+arg_0]
0x140107290  add     rsp, 30h
0x140107294  pop     rdi
0x140107295  retn
```
