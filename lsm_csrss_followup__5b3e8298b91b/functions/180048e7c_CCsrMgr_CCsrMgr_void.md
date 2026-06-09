# CCsrMgr::~CCsrMgr(void)

- ea: `0x180048e7c`
- end: `0x18004903e`
- name: `??1CCsrMgr@@UEAA@XZ`
- size: `450`
- prototype: `void __fastcall(CCsrMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006fe00`

## callees

- `0x180010f20`
- `0x180010fb0`
- `0x18001ce00`
- `0x180024364`
- `0x180027a38`
- `0x18002a074`
- `0x180048e7c`
- `0x180049044`
- `0x180097010`

## import_xrefs

- `ntdll!TpReleaseAlpcCompletion` at `0x180048fc6`
- `ntdll!TpReleaseAlpcCompletion` at `0x180048fc6`
- `ntdll!TpWaitForAlpcCompletion` at `0x180048fb9`
- `ntdll!TpWaitForAlpcCompletion` at `0x180048fb9`
- `ntdll!NtAlpcDisconnectPort` at `0x180048f5a`
- `ntdll!NtAlpcDisconnectPort` at `0x180048f5a`
- `ntdll!NtAlpcQueryInformation` at `0x180048f7d`
- `ntdll!NtAlpcQueryInformation` at `0x180048f7d`
- `ntdll!RtlDeleteResource` at `0x180048fe0`
- `ntdll!RtlDeleteResource` at `0x180049005`
- `ntdll!RtlDeleteResource` at `0x180048fe0`
- `ntdll!RtlDeleteResource` at `0x180049005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048fa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048fa7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048f8e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048f8e`

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
0x180048e7c  mov     [rsp+arg_8], rbx
0x180048e81  mov     [rsp+arg_10], rbp
0x180048e86  push    rsi
0x180048e87  push    rdi
0x180048e88  push    r14
0x180048e8a  sub     rsp, 50h
0x180048e8e  mov     rdi, rcx
0x180048e91  lea     rax, ??_7CCsrMgr@@6B@; const CCsrMgr::`vftable'
0x180048e98  mov     [rcx], rax
0x180048e9b  xorps   xmm0, xmm0
0x180048e9e  movups  [rsp+68h+var_38], xmm0
0x180048ea3  lea     rbp, [rcx+6B8h]
0x180048eaa  mov     rdx, rbp; struct CResource *
0x180048ead  lea     rcx, [rsp+68h+var_28]; this
0x180048eb2  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180048eb7  xor     esi, esi
0x180048eb9  lea     r14, [rdi+6A0h]
0x180048ec0  mov     rax, [r14]
0x180048ec3  mov     rcx, r14
0x180048ec6  mov     rax, [rax+18h]
0x180048eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ecf  cmp     eax, esi
0x180048ed1  jz      short loc_180048F2F
0x180048ed3  mov     [rsp+68h+arg_0], 0
0x180048edc  lea     r8, [rsp+68h+arg_0]
0x180048ee1  mov     edx, esi
0x180048ee3  mov     rcx, r14
0x180048ee6  call    ?GetAt@?$SmartArray@VCCsrPipe@@J@@QEAAHJPEAPEAVCCsrPipe@@@Z; SmartArray<CCsrPipe,long>::GetAt(long,CCsrPipe * *)
0x180048eeb  test    eax, eax
0x180048eed  jz      short loc_180048F2B
0x180048eef  mov     rbx, [rsp+68h+arg_0]
0x180048ef4  mov     rcx, rbx; this
0x180048ef7  call    ?OnConnectionClosed@CCsrPipe@@QEAAJXZ; CCsrPipe::OnConnectionClosed(void)
0x180048efc  lea     rcx, [rbx+648h]; this
0x180048f03  mov     edx, 1; int
0x180048f08  call    ?StopWait@CSessionTerminateHandler@@QEAAXH@Z; CSessionTerminateHandler::StopWait(int)
0x180048f0d  mov     rax, [rbx]
0x180048f10  mov     rcx, rbx
0x180048f13  mov     rax, [rax+10h]
0x180048f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f1c  mov     rax, [rbx]
0x180048f1f  mov     rcx, rbx
0x180048f22  mov     rax, [rax+10h]
0x180048f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f2b  inc     esi
0x180048f2d  jmp     short loc_180048EC0
0x180048f2f  lea     rcx, [rsp+68h+var_28]; this
0x180048f34  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180048f39  nop
0x180048f3a  mov     rcx, [rdi+728h]; hObject
0x180048f41  test    rcx, rcx
0x180048f44  jz      short loc_180048F4C
0x180048f46  call    cs:__imp_CloseHandle
0x180048f4c  mov     rcx, [rdi+720h]
0x180048f53  test    rcx, rcx
0x180048f56  jz      short loc_180048FAD
0x180048f58  xor     edx, edx
0x180048f5a  call    cs:__imp_NtAlpcDisconnectPort
0x180048f60  mov     [rsp+68h+var_48], 0
0x180048f69  mov     r9d, 10h
0x180048f6f  lea     r8, [rsp+68h+var_38]
0x180048f74  xor     edx, edx
0x180048f76  mov     rcx, [rdi+720h]
0x180048f7d  call    cs:__imp_NtAlpcQueryInformation
0x180048f83  test    eax, eax
0x180048f85  js      short loc_180048FA0
0x180048f87  jmp     short loc_180048F94
0x180048f89  mov     ecx, 0Ah; dwMilliseconds
0x180048f8e  call    cs:__imp_Sleep
0x180048f94  mov     eax, [rdi+740h]
0x180048f9a  cmp     dword ptr [rsp+68h+var_38+4], eax
0x180048f9e  jnz     short loc_180048F89
0x180048fa0  mov     rcx, [rdi+720h]; hObject
0x180048fa7  call    cs:__imp_CloseHandle
0x180048fad  mov     rcx, [rdi+738h]
0x180048fb4  test    rcx, rcx
0x180048fb7  jz      short loc_180048FD7
0x180048fb9  call    cs:__imp_TpWaitForAlpcCompletion
0x180048fbf  mov     rcx, [rdi+738h]
0x180048fc6  call    cs:__imp_TpReleaseAlpcCompletion
0x180048fcc  mov     qword ptr [rdi+738h], 0
0x180048fd7  cmp     dword ptr [rbp+60h], 0
0x180048fdb  jz      short loc_180048FE6
0x180048fdd  mov     rcx, rbp; Resource
0x180048fe0  call    cs:__imp_RtlDeleteResource
0x180048fe6  mov     dword ptr [rbp+60h], 0
0x180048fed  mov     rcx, r14
0x180048ff0  call    ??1?$SmartArray@VCCsrPipe@@J@@QEAA@XZ; SmartArray<CCsrPipe,long>::~SmartArray<CCsrPipe,long>(void)
0x180048ff5  lea     rbx, [rdi+638h]
0x180048ffc  cmp     dword ptr [rbx+60h], 0
0x180049000  jz      short loc_18004900B
0x180049002  mov     rcx, rbx; Resource
0x180049005  call    cs:__imp_RtlDeleteResource
0x18004900b  mov     dword ptr [rbx+60h], 0
0x180049012  lea     rax, ??_7?$CTSPrivateObject@VICsrMgr@@@@6B@; const CTSPrivateObject<ICsrMgr>::`vftable'
0x180049019  mov     [rdi], rax
0x18004901c  lea     rcx, [rdi+628h]; struct _LIST_ENTRY *
0x180049023  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x180049028  nop
0x180049029  lea     r11, [rsp+68h+var_18]
0x18004902e  mov     rbx, [r11+28h]
0x180049032  mov     rbp, [r11+30h]
0x180049036  mov     rsp, r11
0x180049039  pop     r14
0x18004903b  pop     rdi
0x18004903c  pop     rsi
0x18004903d  retn
```
