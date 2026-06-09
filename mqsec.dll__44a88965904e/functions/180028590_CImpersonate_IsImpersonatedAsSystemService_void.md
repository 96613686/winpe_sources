# CImpersonate::IsImpersonatedAsSystemService(void * *)

- ea: `0x180028590`
- end: `0x180028676`
- name: `?IsImpersonatedAsSystemService@CImpersonate@@UEAAHPEAPEAX@Z`
- size: `230`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x18000c39c`
- `0x180028590`
- `0x180031010`

## import_xrefs

- `msvcrt!free` at `0x1800285f8`
- `msvcrt!free` at `0x180028626`
- `msvcrt!free` at `0x180028659`
- `msvcrt!free` at `0x180028667`
- `msvcrt!free` at `0x1800285f8`
- `msvcrt!free` at `0x180028626`
- `msvcrt!free` at `0x180028659`
- `msvcrt!free` at `0x180028667`
- `ADVAPI32!EqualSid` at `0x18002860d`
- `ADVAPI32!EqualSid` at `0x180028640`
- `ADVAPI32!EqualSid` at `0x18002860d`
- `ADVAPI32!EqualSid` at `0x180028640`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CImpersonate::IsImpersonatedAsSystemService(CImpersonate *this, void **a2)
{
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  Block = 0;
  if ( !(*(unsigned int (__fastcall **)(CImpersonate *, void **))(*(_QWORD *)this + 16LL))(this, &Block) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 22, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids);
    goto LABEL_11;
  }
  if ( EqualSid(Block, g_pSystemSid) )
  {
    *a2 = g_pSystemSid;
    free(Block);
    return 1;
  }
  if ( EqualSid(Block, g_pNetworkServiceSid) )
  {
    *a2 = g_pNetworkServiceSid;
    free(Block);
    return 1;
  }
LABEL_11:
  free(Block);
  return 0;
}

```

## disassembly

```asm
0x180028590  push    rbx
0x180028592  sub     rsp, 20h
0x180028596  mov     rbx, rdx
0x180028599  mov     qword ptr [rdx], 0
0x1800285a0  mov     [rsp+28h+Block], 0
0x1800285a9  mov     rax, [rcx]
0x1800285ac  lea     rdx, [rsp+28h+Block]
0x1800285b1  mov     rax, [rax+10h]
0x1800285b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285ba  test    eax, eax
0x1800285bc  jnz     short loc_180028601
0x1800285be  lea     rax, WPP_GLOBAL_Control
0x1800285c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285cc  cmp     rcx, rax
0x1800285cf  jz      short loc_1800285F3
0x1800285d1  test    byte ptr [rcx+10Ch], 1
0x1800285d8  jz      short loc_1800285F3
0x1800285da  mov     edx, 16h
0x1800285df  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x1800285e6  mov     rcx, [rcx+100h]
0x1800285ed  call    WPP_SF_
0x1800285f2  nop
0x1800285f3  mov     rcx, [rsp+28h+Block]; Block
0x1800285f8  call    cs:__imp_free
0x1800285fe  nop
0x1800285ff  jmp     short loc_18002866E
0x180028601  mov     rdx, cs:?g_pSystemSid@@3PEAXEA; pSid2
0x180028608  mov     rcx, [rsp+28h+Block]; pSid1
0x18002860d  call    cs:__imp_EqualSid
0x180028613  test    eax, eax
0x180028615  jz      short loc_180028634
0x180028617  mov     rax, cs:?g_pSystemSid@@3PEAXEA; void * g_pSystemSid
0x18002861e  mov     [rbx], rax
0x180028621  mov     rcx, [rsp+28h+Block]; Block
0x180028626  call    cs:__imp_free
0x18002862c  nop
0x18002862d  mov     eax, 1
0x180028632  jmp     short loc_180028670
0x180028634  mov     rdx, cs:?g_pNetworkServiceSid@@3PEAXEA; pSid2
0x18002863b  mov     rcx, [rsp+28h+Block]; pSid1
0x180028640  call    cs:__imp_EqualSid
0x180028646  test    eax, eax
0x180028648  jz      short loc_180028662
0x18002864a  mov     rax, cs:?g_pNetworkServiceSid@@3PEAXEA; void * g_pNetworkServiceSid
0x180028651  mov     [rbx], rax
0x180028654  mov     rcx, [rsp+28h+Block]; Block
0x180028659  call    cs:__imp_free
0x18002865f  nop
0x180028660  jmp     short loc_18002862D
0x180028662  mov     rcx, [rsp+28h+Block]; Block
0x180028667  call    cs:__imp_free
0x18002866d  nop
0x18002866e  xor     eax, eax
0x180028670  add     rsp, 20h
0x180028674  pop     rbx
0x180028675  retn
```
