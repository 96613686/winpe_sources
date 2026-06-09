# CCsrMgr::~CCsrMgr(void)

- ea: `0x18004c0ec`
- end: `0x18004c2e5`
- name: `??1CCsrMgr@@UEAA@XZ`
- size: `505`
- prototype: `void __fastcall(CCsrMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073e50`

## callees

- `0x1800129d0`
- `0x180014a80`
- `0x180014b20`
- `0x180026198`
- `0x180029c00`
- `0x18002c074`
- `0x18004c0ec`
- `0x18004c2ec`
- `0x18009c010`

## import_xrefs

- `ntdll!TpReleaseAlpcCompletion` at `0x18004c25a`
- `ntdll!TpReleaseAlpcCompletion` at `0x18004c25a`
- `ntdll!TpWaitForAlpcCompletion` at `0x18004c247`
- `ntdll!TpWaitForAlpcCompletion` at `0x18004c247`
- `ntdll!NtAlpcDisconnectPort` at `0x18004c1d0`
- `ntdll!NtAlpcDisconnectPort` at `0x18004c1d0`
- `ntdll!NtAlpcQueryInformation` at `0x18004c1f9`
- `ntdll!NtAlpcQueryInformation` at `0x18004c1f9`
- `ntdll!RtlDeleteResource` at `0x18004c27a`
- `ntdll!RtlDeleteResource` at `0x18004c2a5`
- `ntdll!RtlDeleteResource` at `0x18004c27a`
- `ntdll!RtlDeleteResource` at `0x18004c2a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c1b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c22f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c1b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c22f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004c210`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004c210`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCsrMgr::~CCsrMgr(CCsrMgr *this)
{
  struct _RTL_RESOURCE *v2; // rbp
  unsigned int i; // esi
  CCsrPipe *v4; // rbx
  void *v5; // rcx
  __int64 v6; // rcx
  __int128 v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[16]; // [rsp+40h] [rbp-28h] BYREF
  CCsrPipe *v9; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)this = &CCsrMgr::`vftable';
  v7 = 0;
  v2 = (struct _RTL_RESOURCE *)((char *)this + 1720);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v8, (CCsrMgr *)((char *)this + 1720));
  for ( i = 0; (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 212) + 24LL))((char *)this + 1696) != i; ++i )
  {
    v9 = 0;
    if ( (unsigned int)SmartArray<CCsrPipe,long>::GetAt((char *)this + 1696, i, &v9) )
    {
      v4 = v9;
      CCsrPipe::OnConnectionClosed(v9);
      CSessionTerminateHandler::StopWait((CCsrPipe *)((char *)v4 + 1608), 1);
      (*(void (__fastcall **)(CCsrPipe *))(*(_QWORD *)v4 + 16LL))(v4);
      (*(void (__fastcall **)(CCsrPipe *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  CAutoLock::Unlock((CAutoLock *)v8);
  v5 = (void *)*((_QWORD *)this + 229);
  if ( v5 )
    CloseHandle(v5);
  v6 = *((_QWORD *)this + 228);
  if ( v6 )
  {
    NtAlpcDisconnectPort(v6, 0);
    if ( (int)NtAlpcQueryInformation(*((_QWORD *)this + 228), 0, &v7, 16, 0) >= 0 )
    {
      while ( DWORD1(v7) != *((_DWORD *)this + 464) )
        Sleep(0xAu);
    }
    CloseHandle(*((HANDLE *)this + 228));
  }
  if ( *((_QWORD *)this + 231) )
  {
    TpWaitForAlpcCompletion();
    TpReleaseAlpcCompletion(*((_QWORD *)this + 231));
    *((_QWORD *)this + 231) = 0;
  }
  if ( LODWORD(v2[1].Lock.DebugInfo) )
    RtlDeleteResource(v2);
  LODWORD(v2[1].Lock.DebugInfo) = 0;
  SmartArray<CCsrPipe,long>::~SmartArray<CCsrPipe,long>((char *)this + 1696);
  if ( *((_DWORD *)this + 422) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1592));
  *((_DWORD *)this + 422) = 0;
  *(_QWORD *)this = &CTSPrivateObject<ICsrMgr>::`vftable';
  RemoveTrackingObject((struct _LIST_ENTRY *)((char *)this + 1576));
}

```

## disassembly

```asm
0x18004c0ec  mov     [rsp+arg_8], rbx
0x18004c0f1  mov     [rsp+arg_10], rbp
0x18004c0f6  push    rsi
0x18004c0f7  push    rdi
0x18004c0f8  push    r14
0x18004c0fa  sub     rsp, 50h
0x18004c0fe  mov     rdi, rcx
0x18004c101  lea     rax, ??_7CCsrMgr@@6B@; const CCsrMgr::`vftable'
0x18004c108  mov     [rcx], rax
0x18004c10b  xorps   xmm0, xmm0
0x18004c10e  movups  [rsp+68h+var_38], xmm0
0x18004c113  lea     rbp, [rcx+6B8h]
0x18004c11a  mov     rdx, rbp; struct CResource *
0x18004c11d  lea     rcx, [rsp+68h+var_28]; this
0x18004c122  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18004c127  xor     esi, esi
0x18004c129  lea     r14, [rdi+6A0h]
0x18004c130  mov     rax, [r14]
0x18004c133  mov     rcx, r14
0x18004c136  mov     rax, [rax+18h]
0x18004c13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c13f  cmp     eax, esi
0x18004c141  jz      short loc_18004C19F
0x18004c143  mov     [rsp+68h+arg_0], 0
0x18004c14c  lea     r8, [rsp+68h+arg_0]
0x18004c151  mov     edx, esi
0x18004c153  mov     rcx, r14
0x18004c156  call    ?GetAt@?$SmartArray@VCCsrPipe@@J@@QEAAHJPEAPEAVCCsrPipe@@@Z; SmartArray<CCsrPipe,long>::GetAt(long,CCsrPipe * *)
0x18004c15b  test    eax, eax
0x18004c15d  jz      short loc_18004C19B
0x18004c15f  mov     rbx, [rsp+68h+arg_0]
0x18004c164  mov     rcx, rbx; this
0x18004c167  call    ?OnConnectionClosed@CCsrPipe@@QEAAJXZ; CCsrPipe::OnConnectionClosed(void)
0x18004c16c  lea     rcx, [rbx+648h]; this
0x18004c173  mov     edx, 1; int
0x18004c178  call    ?StopWait@CSessionTerminateHandler@@QEAAXH@Z; CSessionTerminateHandler::StopWait(int)
0x18004c17d  mov     rax, [rbx]
0x18004c180  mov     rcx, rbx
0x18004c183  mov     rax, [rax+10h]
0x18004c187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c18c  mov     rax, [rbx]
0x18004c18f  mov     rcx, rbx
0x18004c192  mov     rax, [rax+10h]
0x18004c196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c19b  inc     esi
0x18004c19d  jmp     short loc_18004C130
0x18004c19f  lea     rcx, [rsp+68h+var_28]; this
0x18004c1a4  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18004c1a9  nop
0x18004c1aa  mov     rcx, [rdi+728h]; hObject
0x18004c1b1  test    rcx, rcx
0x18004c1b4  jz      short loc_18004C1C2
0x18004c1b6  call    cs:__imp_CloseHandle
0x18004c1bd  nop     dword ptr [rax+rax+00h]
0x18004c1c2  mov     rcx, [rdi+720h]
0x18004c1c9  test    rcx, rcx
0x18004c1cc  jz      short loc_18004C23B
0x18004c1ce  xor     edx, edx
0x18004c1d0  call    cs:__imp_NtAlpcDisconnectPort
0x18004c1d7  nop     dword ptr [rax+rax+00h]
0x18004c1dc  mov     [rsp+68h+var_48], 0
0x18004c1e5  mov     r9d, 10h
0x18004c1eb  lea     r8, [rsp+68h+var_38]
0x18004c1f0  xor     edx, edx
0x18004c1f2  mov     rcx, [rdi+720h]
0x18004c1f9  call    cs:__imp_NtAlpcQueryInformation
0x18004c200  nop     dword ptr [rax+rax+00h]
0x18004c205  test    eax, eax
0x18004c207  js      short loc_18004C228
0x18004c209  jmp     short loc_18004C21C
0x18004c20b  mov     ecx, 0Ah; dwMilliseconds
0x18004c210  call    cs:__imp_Sleep
0x18004c217  nop     dword ptr [rax+rax+00h]
0x18004c21c  mov     eax, [rdi+740h]
0x18004c222  cmp     dword ptr [rsp+68h+var_38+4], eax
0x18004c226  jnz     short loc_18004C20B
0x18004c228  mov     rcx, [rdi+720h]; hObject
0x18004c22f  call    cs:__imp_CloseHandle
0x18004c236  nop     dword ptr [rax+rax+00h]
0x18004c23b  mov     rcx, [rdi+738h]
0x18004c242  test    rcx, rcx
0x18004c245  jz      short loc_18004C271
0x18004c247  call    cs:__imp_TpWaitForAlpcCompletion
0x18004c24e  nop     dword ptr [rax+rax+00h]
0x18004c253  mov     rcx, [rdi+738h]
0x18004c25a  call    cs:__imp_TpReleaseAlpcCompletion
0x18004c261  nop     dword ptr [rax+rax+00h]
0x18004c266  mov     qword ptr [rdi+738h], 0
0x18004c271  cmp     dword ptr [rbp+60h], 0
0x18004c275  jz      short loc_18004C286
0x18004c277  mov     rcx, rbp; Resource
0x18004c27a  call    cs:__imp_RtlDeleteResource
0x18004c281  nop     dword ptr [rax+rax+00h]
0x18004c286  mov     dword ptr [rbp+60h], 0
0x18004c28d  mov     rcx, r14
0x18004c290  call    ??1?$SmartArray@VCCsrPipe@@J@@QEAA@XZ; SmartArray<CCsrPipe,long>::~SmartArray<CCsrPipe,long>(void)
0x18004c295  lea     rbx, [rdi+638h]
0x18004c29c  cmp     dword ptr [rbx+60h], 0
0x18004c2a0  jz      short loc_18004C2B1
0x18004c2a2  mov     rcx, rbx; Resource
0x18004c2a5  call    cs:__imp_RtlDeleteResource
0x18004c2ac  nop     dword ptr [rax+rax+00h]
0x18004c2b1  mov     dword ptr [rbx+60h], 0
0x18004c2b8  lea     rax, ??_7?$CTSPrivateObject@VICsrMgr@@@@6B@; const CTSPrivateObject<ICsrMgr>::`vftable'
0x18004c2bf  mov     [rdi], rax
0x18004c2c2  lea     rcx, [rdi+628h]; struct _LIST_ENTRY *
0x18004c2c9  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x18004c2ce  nop
0x18004c2cf  lea     r11, [rsp+68h+var_18]
0x18004c2d4  mov     rbx, [r11+28h]
0x18004c2d8  mov     rbp, [r11+30h]
0x18004c2dc  mov     rsp, r11
0x18004c2df  pop     r14
0x18004c2e1  pop     rdi
0x18004c2e2  pop     rsi
0x18004c2e3  retn
```
