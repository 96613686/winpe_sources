# CWiGigDAFProviderAssociation::CWiGigDAFProviderAssociation(DockingProviders *,DockCache *)

- ea: `0x180008510`
- end: `0x18000866c`
- name: `??0CWiGigDAFProviderAssociation@@QEAA@PEAVDockingProviders@@PEAVDockCache@@@Z`
- size: `348`
- prototype: `CWiGigDAFProviderAssociation *__fastcall(CWiGigDAFProviderAssociation *__hidden this, struct DockingProviders *, struct DockCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ce20`

## callees

- `0x180008510`
- `0x18000c308`
- `0x18001ca3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008558`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008558`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008536`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008536`

## pseudocode

```c
CWiGigDAFProviderAssociation *__fastcall CWiGigDAFProviderAssociation::CWiGigDAFProviderAssociation(
        CWiGigDAFProviderAssociation *this,
        struct DockingProviders *a2,
        struct DockCache *a3)
{
  *(_QWORD *)this = &CWiGigDAFProviderAssociation::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = CreateEventW(0, 1, 0, 0);
  *((_WORD *)this + 36) = 0;
  *((_DWORD *)this + 23) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 334) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)this + 335) = 0;
  *((_QWORD *)this + 410) = a3;
  if ( a3 )
    _InterlockedIncrement((volatile signed __int32 *)a3 + 24);
  *((_BYTE *)this + 3288) = 0;
  *((_QWORD *)this + 412) = 0;
  *((_DWORD *)this + 826) = 0;
  *(GUID *)((char *)this + 76) = GUID_NULL;
  memset_0((char *)this + 96, 0, 0xFFu);
  memset_0((char *)this + 360, 0, 0x480u);
  memset_0((char *)this + 1512, 0, 0x488u);
  memset_0((char *)this + 2688, 0, 0x24Au);
  _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  return this;
}

```

## disassembly

```asm
0x180008510  mov     [rsp+arg_8], rbx
0x180008515  mov     [rsp+arg_10], rsi
0x18000851a  push    rdi
0x18000851b  sub     rsp, 20h
0x18000851f  mov     rdi, r8
0x180008522  mov     rsi, rdx
0x180008525  mov     rbx, rcx
0x180008528  lea     rax, ??_7CWiGigDAFProviderAssociation@@6B@; const CWiGigDAFProviderAssociation::`vftable'
0x18000852f  mov     [rcx], rax
0x180008532  add     rcx, 8; lpCriticalSection
0x180008536  call    cs:__imp_InitializeCriticalSection
0x18000853c  nop
0x18000853d  mov     dword ptr [rbx+30h], 0
0x180008544  mov     qword ptr [rbx+38h], 0
0x18000854c  xor     r9d, r9d; lpName
0x18000854f  xor     r8d, r8d; bInitialState
0x180008552  lea     edx, [r9+1]; bManualReset
0x180008556  xor     ecx, ecx; lpEventAttributes
0x180008558  call    cs:__imp_CreateEventW
0x18000855e  mov     [rbx+40h], rax
0x180008562  mov     word ptr [rbx+48h], 0
0x180008568  mov     dword ptr [rbx+5Ch], 0
0x18000856f  mov     qword ptr [rbx+160h], 0
0x18000857a  mov     [rbx+0A70h], rsi
0x180008581  test    rsi, rsi
0x180008584  jz      short loc_18000858A
0x180008586  lock inc dword ptr [rsi+8]
0x18000858a  mov     qword ptr [rbx+0A78h], 0
0x180008595  mov     [rbx+0CD0h], rdi
0x18000859c  test    rdi, rdi
0x18000859f  jz      short loc_1800085A5
0x1800085a1  lock inc dword ptr [rdi+60h]
0x1800085a5  mov     byte ptr [rbx+0CD8h], 0
0x1800085ac  mov     qword ptr [rbx+0CE0h], 0
0x1800085b7  mov     dword ptr [rbx+0CE8h], 0
0x1800085c1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800085c8  movdqu  xmmword ptr [rbx+4Ch], xmm0
0x1800085cd  lea     rcx, [rbx+60h]; void *
0x1800085d1  xor     edx, edx; Val
0x1800085d3  mov     r8d, 0FFh; Size
0x1800085d9  call    memset_0
0x1800085de  lea     rcx, [rbx+168h]; void *
0x1800085e5  xor     edx, edx; Val
0x1800085e7  mov     r8d, 480h; Size
0x1800085ed  call    memset_0
0x1800085f2  lea     rcx, [rbx+5E8h]; void *
0x1800085f9  xor     edx, edx; Val
0x1800085fb  mov     r8d, 488h; Size
0x180008601  call    memset_0
0x180008606  lea     rcx, [rbx+0A80h]; void *
0x18000860d  xor     edx, edx; Val
0x18000860f  mov     r8d, 24Ah; Size
0x180008615  call    memset_0
0x18000861a  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x180008621  lea     rax, WPP_GLOBAL_Control
0x180008628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000862f  cmp     rcx, rax
0x180008632  jz      short loc_180008659
0x180008634  cmp     byte ptr [rcx+19h], 4
0x180008638  jb      short loc_180008659
0x18000863a  test    byte ptr [rcx+1Ch], 1
0x18000863e  jz      short loc_180008659
0x180008640  mov     edx, 1Dh
0x180008645  mov     r9, rbx
0x180008648  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000864f  mov     rcx, [rcx+10h]
0x180008653  call    WPP_SF_q
0x180008658  nop
0x180008659  mov     rax, rbx
0x18000865c  mov     rbx, [rsp+28h+arg_8]
0x180008661  mov     rsi, [rsp+28h+arg_10]
0x180008666  add     rsp, 20h
0x18000866a  pop     rdi
0x18000866b  retn
```
