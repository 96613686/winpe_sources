# WimDeinit(void)

- ea: `0x18000fc34`
- end: `0x18000fda6`
- name: `?WimDeinit@@YAKXZ`
- size: `370`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b9fc`

## callees

- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000f440`
- `0x18000f47c`
- `0x18000fc34`
- `0x1800178cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd5c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd5c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fca1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fca1`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000fd2f`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18000fd2f`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000fd07`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000fd07`

## pseudocode

```c
__int64 WimDeinit(void)
{
  unsigned int v0; // edi
  _QWORD *v1; // rbx
  __int64 v2; // rax
  struct _LAN_INTERFACE_CONTEXT *v4; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
  }
  v0 = LockLanIntfmgrState((struct LAN_INTFMGR_CONTEXT *)&g_IntfMgrContext);
  if ( !v0 )
  {
    _InterlockedExchange((volatile __int32 *)&g_IntfMgrContext, 3);
    while ( dword_180052E64 > 1 )
      Sleep(0x64u);
    while ( 1 )
    {
      v1 = lpMem;
      if ( lpMem == &lpMem )
        break;
      if ( *((void ***)lpMem + 1) != &lpMem || (v2 = *(_QWORD *)lpMem, *(void **)(*(_QWORD *)lpMem + 8LL) != lpMem) )
        __fastfail(3u);
      lpMem = *(void **)lpMem;
      *(_QWORD *)(v2 + 8) = &lpMem;
      if ( !(unsigned int)HtReferenceHandleWithTag(g_hHandleTable, v1[2], 0, 1448036676, 0, &v4) )
        IntfDeinitContext(v4);
      HtDereferenceHandleWithTag(g_hHandleTable, v1[2], 0, 1);
      Dot3Free(v1);
    }
    UnlockLanIntfmgrState((struct LAN_INTFMGR_CONTEXT *)&g_IntfMgrContext);
    DeleteCriticalSection(&stru_180052E90);
    _InterlockedExchange((volatile __int32 *)&g_IntfMgrContext, 0);
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 19, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x18000fc34  push    rbx
0x18000fc36  push    rbp
0x18000fc37  push    rdi
0x18000fc38  push    r15
0x18000fc3a  sub     rsp, 38h
0x18000fc3e  mov     [rsp+58h+arg_0], 0
0x18000fc47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc4e  lea     r15, WPP_GLOBAL_Control
0x18000fc55  cmp     rcx, r15
0x18000fc58  jz      short loc_18000FC7B
0x18000fc5a  cmp     byte ptr [rcx+19h], 4
0x18000fc5e  jb      short loc_18000FC7B
0x18000fc60  test    byte ptr [rcx+1Ch], 1
0x18000fc64  jz      short loc_18000FC7B
0x18000fc66  mov     rcx, [rcx+10h]
0x18000fc6a  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x18000fc71  mov     edx, 12h
0x18000fc76  call    WPP_SF_
0x18000fc7b  lea     rcx, ?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; struct LAN_INTFMGR_CONTEXT *
0x18000fc82  call    ?LockLanIntfmgrState@@YAKAEAULAN_INTFMGR_CONTEXT@@@Z; LockLanIntfmgrState(LAN_INTFMGR_CONTEXT &)
0x18000fc87  mov     edi, eax
0x18000fc89  test    eax, eax
0x18000fc8b  jnz     loc_18000FD6A
0x18000fc91  lea     ecx, [rax+3]
0x18000fc94  xchg    ecx, cs:?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; LAN_INTFMGR_CONTEXT g_IntfMgrContext
0x18000fc9a  jmp     short loc_18000FCA7
0x18000fc9c  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000fca1  call    cs:__imp_Sleep
0x18000fca7  cmp     cs:dword_180052E64, 1
0x18000fcae  jg      short loc_18000FC9C
0x18000fcb0  lea     rbp, lpMem
0x18000fcb7  mov     rbx, cs:lpMem
0x18000fcbe  cmp     rbx, rbp
0x18000fcc1  jz      loc_18000FD49
0x18000fcc7  cmp     [rbx+8], rbp
0x18000fccb  jnz     short loc_18000FD42
0x18000fccd  mov     rax, [rbx]
0x18000fcd0  cmp     [rax+8], rbx
0x18000fcd4  jnz     short loc_18000FD42
0x18000fcd6  mov     cs:lpMem, rax
0x18000fcdd  mov     r9d, 564F4944h
0x18000fce3  mov     [rax+8], rbp
0x18000fce7  xor     r8d, r8d
0x18000fcea  mov     rdx, [rbx+10h]
0x18000fcee  lea     rax, [rsp+58h+arg_0]
0x18000fcf3  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18000fcfa  mov     [rsp+58h+var_30], rax
0x18000fcff  mov     [rsp+58h+var_38], 0
0x18000fd07  call    cs:__imp_HtReferenceHandleWithTag
0x18000fd0d  test    eax, eax
0x18000fd0f  jnz     short loc_18000FD1B
0x18000fd11  mov     rcx, [rsp+58h+arg_0]; struct _LAN_INTERFACE_CONTEXT *
0x18000fd16  call    ?IntfDeinitContext@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfDeinitContext(_LAN_INTERFACE_CONTEXT *)
0x18000fd1b  mov     rdx, [rbx+10h]
0x18000fd1f  mov     r9d, 1
0x18000fd25  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18000fd2c  xor     r8d, r8d
0x18000fd2f  call    cs:__imp_HtDereferenceHandleWithTag
0x18000fd35  mov     rcx, rbx; lpMem
0x18000fd38  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18000fd3d  jmp     loc_18000FCB7
0x18000fd42  mov     ecx, 3
0x18000fd47  int     29h; Win8: RtlFailFast(ecx)
0x18000fd49  lea     rcx, ?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; struct LAN_INTFMGR_CONTEXT *
0x18000fd50  call    ?UnlockLanIntfmgrState@@YAXAEAULAN_INTFMGR_CONTEXT@@@Z; UnlockLanIntfmgrState(LAN_INTFMGR_CONTEXT &)
0x18000fd55  lea     rcx, stru_180052E90; lpCriticalSection
0x18000fd5c  call    cs:__imp_DeleteCriticalSection
0x18000fd62  xor     eax, eax
0x18000fd64  xchg    eax, cs:?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; LAN_INTFMGR_CONTEXT g_IntfMgrContext
0x18000fd6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd71  cmp     rcx, r15
0x18000fd74  jz      short loc_18000FD9A
0x18000fd76  cmp     byte ptr [rcx+19h], 4
0x18000fd7a  jb      short loc_18000FD9A
0x18000fd7c  test    byte ptr [rcx+1Ch], 1
0x18000fd80  jz      short loc_18000FD9A
0x18000fd82  mov     rcx, [rcx+10h]
0x18000fd86  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x18000fd8d  mov     edx, 13h
0x18000fd92  mov     r9d, edi
0x18000fd95  call    WPP_SF_d
0x18000fd9a  mov     eax, edi
0x18000fd9c  add     rsp, 38h
0x18000fda0  pop     r15
0x18000fda2  pop     rdi
0x18000fda3  pop     rbp
0x18000fda4  pop     rbx
0x18000fda5  retn
```
