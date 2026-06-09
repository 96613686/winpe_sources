# NOTIFY_CONTEXT::NotifyThreadProc(void *)

- ea: `0x180007c20`
- end: `0x180007ed1`
- name: `?NotifyThreadProc@NOTIFY_CONTEXT@@CAKPEAX@Z`
- size: `689`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800010a4`
- `0x1800010b0`
- `0x180001c3c`
- `0x1800078ac`
- `0x180007c20`
- `0x18000cfd4`
- `0x18000d180`
- `0x180010010`

## import_xrefs

- `ole32!CoUninitialize` at `0x180007ebd`
- `ole32!CoUninitialize` at `0x180007ebd`
- `ole32!CoInitializeEx` at `0x180007c34`
- `ole32!CoInitializeEx` at `0x180007c34`
- `KERNEL32!WaitForMultipleObjects` at `0x180007ce9`
- `KERNEL32!WaitForMultipleObjects` at `0x180007ce9`
- `KERNEL32!LeaveCriticalSection` at `0x180007cb9`
- `KERNEL32!LeaveCriticalSection` at `0x180007d4c`
- `KERNEL32!LeaveCriticalSection` at `0x180007cb9`
- `KERNEL32!LeaveCriticalSection` at `0x180007d4c`
- `KERNEL32!EnterCriticalSection` at `0x180007c67`
- `KERNEL32!EnterCriticalSection` at `0x180007cfe`
- `KERNEL32!EnterCriticalSection` at `0x180007c67`
- `KERNEL32!EnterCriticalSection` at `0x180007cfe`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007d72`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007d72`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007d5e`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007d5e`

## pseudocode

```c
__int64 __fastcall NOTIFY_CONTEXT::NotifyThreadProc(PVOID Parameter)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY **p_Blink; // rdi
  struct _LIST_ENTRY *v4; // rcx
  struct _LIST_ENTRY *v5; // rax
  struct _LIST_ENTRY *v6; // rcx
  struct _LIST_ENTRY *v7; // rsi
  bool v8; // zf
  int v9; // r12d
  struct _MD_CHANGE_OBJECT_W *v10; // r13
  int v11; // eax
  struct IMSAdminBaseSinkW **v12; // r14
  __int64 v13; // r15
  unsigned int v14; // edi
  __int64 i; // rbx
  struct IMSAdminBaseSinkW *v16; // rcx
  void *Block; // [rsp+30h] [rbp-58h] BYREF
  HANDLE Handles[10]; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+18h]
  struct _LIST_ENTRY **v21; // [rsp+A8h] [rbp+20h]

  if ( CoInitializeEx(0, 0) < 0 )
    return 0xFFFFFFFFLL;
LABEL_3:
  *(_OWORD *)Handles = 0;
  EnterCriticalSection(&NOTIFY_CONTEXT::s_critSec);
  Flink = NOTIFY_CONTEXT::s_listEntry.Flink;
  if ( NOTIFY_CONTEXT::s_listEntry.Flink == &NOTIFY_CONTEXT::s_listEntry )
  {
    p_Blink = 0;
  }
  else
  {
    if ( NOTIFY_CONTEXT::s_listEntry.Flink->Blink != &NOTIFY_CONTEXT::s_listEntry
      || (v4 = NOTIFY_CONTEXT::s_listEntry.Flink->Flink,
          NOTIFY_CONTEXT::s_listEntry.Flink->Flink->Blink != NOTIFY_CONTEXT::s_listEntry.Flink) )
    {
LABEL_31:
      __fastfail(3u);
    }
    NOTIFY_CONTEXT::s_listEntry.Flink = NOTIFY_CONTEXT::s_listEntry.Flink->Flink;
    p_Blink = &Flink[-3].Blink;
    v4->Blink = &NOTIFY_CONTEXT::s_listEntry;
    Flink->Blink = Flink;
    Flink->Flink = Flink;
  }
  v21 = p_Blink;
  LeaveCriticalSection(&NOTIFY_CONTEXT::s_critSec);
  Handles[0] = NOTIFY_CONTEXT::s_hDataAvailable;
  Handles[1] = NOTIFY_CONTEXT::s_hShutdown;
  while ( 1 )
  {
    if ( p_Blink )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
      NOTIFY_CONTEXT::s_pCurrentlyWorkingOn = (struct NOTIFY_CONTEXT *)p_Blink;
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
      v7 = p_Blink[1];
      ((void (__fastcall *)(struct _LIST_ENTRY *))v7->Flink->Blink)(v7);
      v8 = HIDWORD(v7->Blink) == 0;
      Block = 0;
      v19 = 0;
      if ( v8 )
      {
        v9 = *((_DWORD *)p_Blink + 8);
        v10 = (struct _MD_CHANGE_OBJECT_W *)p_Blink[3];
        v20 = *((_DWORD *)p_Blink + 4);
        if ( !(unsigned int)COConnectionPoint::ListenersPresent((COConnectionPoint *)&v7[52].Blink) )
        {
          v11 = COConnectionPoint::InternalEnumSinks(
                  (COConnectionPoint *)&v7[52].Blink,
                  (struct IMSAdminBaseSinkW ***)&Block,
                  &v19);
          v12 = (struct IMSAdminBaseSinkW **)Block;
          if ( v11 >= 0 && v19 )
          {
            v13 = 0;
            v14 = v20;
            do
            {
              CADMCOMW::NotifySinkHelper((CADMCOMW *)v7, v12[v13], v14, v10, v9);
              ((void (__fastcall *)(struct IMSAdminBaseSinkW *))v12[v13]->lpVtbl->Release)(v12[v13]);
              v12[v13] = 0;
              v13 = (unsigned int)(v13 + 1);
            }
            while ( (unsigned int)v13 < v19 );
            p_Blink = v21;
          }
          if ( v12 )
          {
            for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
            {
              v16 = v12[i];
              if ( v16 )
              {
                ((void (__fastcall *)(struct IMSAdminBaseSinkW *))v16->lpVtbl->Release)(v16);
                v12[i] = 0;
              }
            }
            operator delete[](v12);
          }
        }
      }
      NOTIFY_CONTEXT::~NOTIFY_CONTEXT((NOTIFY_CONTEXT *)p_Blink);
      operator delete(p_Blink);
      ((void (__fastcall *)(struct _LIST_ENTRY *))v7->Flink[1].Flink)(v7);
      goto LABEL_3;
    }
    if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
      break;
    EnterCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    v5 = NOTIFY_CONTEXT::s_listEntry.Flink;
    if ( NOTIFY_CONTEXT::s_listEntry.Flink != &NOTIFY_CONTEXT::s_listEntry )
    {
      if ( NOTIFY_CONTEXT::s_listEntry.Flink->Blink != &NOTIFY_CONTEXT::s_listEntry )
        goto LABEL_31;
      v6 = NOTIFY_CONTEXT::s_listEntry.Flink->Flink;
      if ( NOTIFY_CONTEXT::s_listEntry.Flink->Flink->Blink != NOTIFY_CONTEXT::s_listEntry.Flink )
        goto LABEL_31;
      NOTIFY_CONTEXT::s_listEntry.Flink = NOTIFY_CONTEXT::s_listEntry.Flink->Flink;
      p_Blink = &v5[-3].Blink;
      v6->Blink = &NOTIFY_CONTEXT::s_listEntry;
      v5->Blink = v5;
      v5->Flink = v5;
      v21 = &v5[-3].Blink;
    }
    LeaveCriticalSection(&NOTIFY_CONTEXT::s_critSec);
  }
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180007c20  push    rbx
0x180007c22  push    rsi
0x180007c23  push    rdi
0x180007c24  push    r12
0x180007c26  push    r13
0x180007c28  push    r14
0x180007c2a  push    r15
0x180007c2c  sub     rsp, 50h
0x180007c30  xor     edx, edx; dwCoInit
0x180007c32  xor     ecx, ecx; pvReserved
0x180007c34  call    cs:__imp_CoInitializeEx
0x180007c3a  test    eax, eax
0x180007c3c  jns     short loc_180007C51
0x180007c3e  or      eax, 0FFFFFFFFh
0x180007c41  add     rsp, 50h
0x180007c45  pop     r15
0x180007c47  pop     r14
0x180007c49  pop     r13
0x180007c4b  pop     r12
0x180007c4d  pop     rdi
0x180007c4e  pop     rsi
0x180007c4f  pop     rbx
0x180007c50  retn
0x180007c51  lea     rbx, ?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180007c58  xorps   xmm0, xmm0
0x180007c5b  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007c62  movups  xmmword ptr [rsp+88h+Handles], xmm0
0x180007c67  call    cs:__imp_EnterCriticalSection
0x180007c6d  mov     rax, cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180007c74  cmp     rax, rbx
0x180007c77  jnz     short loc_180007C7D
0x180007c79  xor     edi, edi
0x180007c7b  jmp     short loc_180007CAA
0x180007c7d  cmp     [rax+8], rbx
0x180007c81  jnz     loc_180007ECA
0x180007c87  mov     rcx, [rax]
0x180007c8a  cmp     [rcx+8], rax
0x180007c8e  jnz     loc_180007ECA
0x180007c94  mov     cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A, rcx; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180007c9b  lea     rdi, [rax-28h]
0x180007c9f  mov     [rcx+8], rbx
0x180007ca3  mov     [rax+8], rax
0x180007ca7  mov     [rax], rax
0x180007caa  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007cb1  mov     [rsp+88h+arg_18], rdi
0x180007cb9  call    cs:__imp_LeaveCriticalSection
0x180007cbf  mov     rax, cs:?s_hDataAvailable@NOTIFY_CONTEXT@@0PEAXEA; void * NOTIFY_CONTEXT::s_hDataAvailable
0x180007cc6  mov     [rsp+88h+Handles], rax
0x180007ccb  mov     rax, cs:?s_hShutdown@NOTIFY_CONTEXT@@0PEAXEA; void * NOTIFY_CONTEXT::s_hShutdown
0x180007cd2  mov     [rsp+88h+Handles+8], rax
0x180007cd7  jmp     short loc_180007D52
0x180007cd9  xor     r8d, r8d; bWaitAll
0x180007cdc  lea     rdx, [rsp+88h+Handles]; lpHandles
0x180007ce1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180007ce5  lea     ecx, [r8+2]; nCount
0x180007ce9  call    cs:__imp_WaitForMultipleObjects
0x180007cef  test    eax, eax
0x180007cf1  jnz     loc_180007EBD
0x180007cf7  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007cfe  call    cs:__imp_EnterCriticalSection
0x180007d04  mov     rax, cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180007d0b  cmp     rax, rbx
0x180007d0e  jz      short loc_180007D45
0x180007d10  cmp     [rax+8], rbx
0x180007d14  jnz     loc_180007ECA
0x180007d1a  mov     rcx, [rax]
0x180007d1d  cmp     [rcx+8], rax
0x180007d21  jnz     loc_180007ECA
0x180007d27  mov     cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A, rcx; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180007d2e  lea     rdi, [rax-28h]
0x180007d32  mov     [rcx+8], rbx
0x180007d36  mov     [rax+8], rax
0x180007d3a  mov     [rax], rax
0x180007d3d  mov     [rsp+88h+arg_18], rdi
0x180007d45  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007d4c  call    cs:__imp_LeaveCriticalSection
0x180007d52  test    rdi, rdi
0x180007d55  jz      short loc_180007CD9
0x180007d57  lea     rcx, ?s_LockCurrentlyWorkingOn@NOTIFY_CONTEXT@@0VCReaderWriterLock3@@A; CReaderWriterLock3 NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn
0x180007d5e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180007d64  lea     rcx, ?s_LockCurrentlyWorkingOn@NOTIFY_CONTEXT@@0VCReaderWriterLock3@@A; CReaderWriterLock3 NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn
0x180007d6b  mov     cs:?s_pCurrentlyWorkingOn@NOTIFY_CONTEXT@@0PEAV1@EA, rdi; NOTIFY_CONTEXT * NOTIFY_CONTEXT::s_pCurrentlyWorkingOn
0x180007d72  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180007d78  mov     rsi, [rdi+8]
0x180007d7c  mov     rcx, rsi
0x180007d7f  mov     rax, [rsi]
0x180007d82  mov     rax, [rax+8]
0x180007d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8b  cmp     dword ptr [rsi+0Ch], 0
0x180007d8f  mov     [rsp+88h+Block], 0
0x180007d98  mov     [rsp+88h+arg_8], 0
0x180007da3  jnz     loc_180007E99
0x180007da9  mov     eax, [rdi+10h]
0x180007dac  lea     rbx, [rsi+348h]
0x180007db3  mov     r12d, [rdi+20h]
0x180007db7  mov     rcx, rbx; this
0x180007dba  mov     r13, [rdi+18h]
0x180007dbe  mov     [rsp+88h+arg_10], eax
0x180007dc5  call    ?ListenersPresent@COConnectionPoint@@QEAAJXZ; COConnectionPoint::ListenersPresent(void)
0x180007dca  test    eax, eax
0x180007dcc  jnz     loc_180007E92
0x180007dd2  lea     r8, [rsp+88h+arg_8]; unsigned int *
0x180007dda  mov     rcx, rbx; this
0x180007ddd  lea     rdx, [rsp+88h+Block]; struct IMSAdminBaseSinkW ***
0x180007de2  call    ?InternalEnumSinks@COConnectionPoint@@QEAAJPEAPEAPEAUIMSAdminBaseSinkW@@PEAK@Z; COConnectionPoint::InternalEnumSinks(IMSAdminBaseSinkW * * *,ulong *)
0x180007de7  mov     r14, [rsp+88h+Block]
0x180007dec  test    eax, eax
0x180007dee  js      short loc_180007E52
0x180007df0  cmp     [rsp+88h+arg_8], 0
0x180007df8  jz      short loc_180007E52
0x180007dfa  xor     r15d, r15d
0x180007dfd  cmp     [rsp+88h+arg_8], r15d
0x180007e05  jbe     short loc_180007E52
0x180007e07  mov     edi, [rsp+88h+arg_10]
0x180007e0e  mov     rdx, [r14+r15*8]; struct IMSAdminBaseSinkW *
0x180007e12  mov     r9, r13; struct _MD_CHANGE_OBJECT_W *
0x180007e15  mov     r8d, edi; unsigned int
0x180007e18  mov     [rsp+88h+var_68], r12d; int
0x180007e1d  mov     rcx, rsi; this
0x180007e20  call    ?NotifySinkHelper@CADMCOMW@@AEAAJPEAUIMSAdminBaseSinkW@@KQEAU_MD_CHANGE_OBJECT_W@@H@Z; CADMCOMW::NotifySinkHelper(IMSAdminBaseSinkW *,ulong,_MD_CHANGE_OBJECT_W * const,int)
0x180007e25  mov     rcx, [r14+r15*8]
0x180007e29  mov     rax, [rcx]
0x180007e2c  mov     rax, [rax+10h]
0x180007e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e35  mov     qword ptr [r14+r15*8], 0
0x180007e3d  inc     r15d
0x180007e40  cmp     r15d, [rsp+88h+arg_8]
0x180007e48  jb      short loc_180007E0E
0x180007e4a  mov     rdi, [rsp+88h+arg_18]
0x180007e52  test    r14, r14
0x180007e55  jz      short loc_180007E92
0x180007e57  xor     ebx, ebx
0x180007e59  cmp     [rsp+88h+arg_8], ebx
0x180007e60  jbe     short loc_180007E8A
0x180007e62  mov     rcx, [r14+rbx*8]
0x180007e66  test    rcx, rcx
0x180007e69  jz      short loc_180007E7F
0x180007e6b  mov     rax, [rcx]
0x180007e6e  mov     rax, [rax+10h]
0x180007e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e77  mov     qword ptr [r14+rbx*8], 0
0x180007e7f  inc     ebx
0x180007e81  cmp     ebx, [rsp+88h+arg_8]
0x180007e88  jb      short loc_180007E62
0x180007e8a  mov     rcx, r14; Block
0x180007e8d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180007e92  lea     rbx, ?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x180007e99  mov     rcx, rdi; this
0x180007e9c  call    ??1NOTIFY_CONTEXT@@AEAA@XZ; NOTIFY_CONTEXT::~NOTIFY_CONTEXT(void)
0x180007ea1  mov     rcx, rdi; Block
0x180007ea4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007ea9  mov     rax, [rsi]
0x180007eac  mov     rcx, rsi
0x180007eaf  mov     rax, [rax+10h]
0x180007eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb8  jmp     loc_180007C58
0x180007ebd  call    cs:__imp_CoUninitialize
0x180007ec3  xor     eax, eax
0x180007ec5  jmp     loc_180007C41
0x180007eca  mov     ecx, 3
0x180007ecf  int     29h; Win8: RtlFailFast(ecx)
```
