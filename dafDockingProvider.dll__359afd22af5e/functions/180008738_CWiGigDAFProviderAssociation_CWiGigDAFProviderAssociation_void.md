# CWiGigDAFProviderAssociation::~CWiGigDAFProviderAssociation(void)

- ea: `0x180008738`
- end: `0x18000891f`
- name: `??1CWiGigDAFProviderAssociation@@AEAA@XZ`
- size: `487`
- prototype: `void __fastcall(CWiGigDAFProviderAssociation *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000a790`

## callees

- `0x1800014d0`
- `0x180008738`
- `0x1800090a8`
- `0x18000c308`
- `0x18001134c`
- `0x180012cd4`
- `0x180016e2c`
- `0x18001ca3e`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800087c2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800087c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088e6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800087e0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800087e0`

## pseudocode

```c
void __fastcall CWiGigDAFProviderAssociation::~CWiGigDAFProviderAssociation(CWiGigDAFProviderAssociation *this)
{
  _QWORD *v2; // rcx
  void *v3; // rcx
  unsigned __int64 v4; // rdx
  volatile signed __int32 *v5; // rdi
  DockingProviders *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx

  *(_QWORD *)this = &CWiGigDAFProviderAssociation::`vftable';
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_BYTE *)v2 + 28) & 1) != 0 )
      WPP_SF_q(v2[2], 31, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  CWiGigDAFProviderAssociation::CancelPairing(this);
  if ( !ResetEvent(*((HANDLE *)this + 8)) )
    GetLastError();
  v3 = (void *)*((_QWORD *)this + 335);
  if ( v3 )
  {
    BCryptCloseAlgorithmProvider(v3, 0);
    *((_QWORD *)this + 335) = 0;
  }
  *((_QWORD *)this + 44) = 0;
  *((_BYTE *)this + 3288) = 0;
  v4 = *((_QWORD *)this + 412);
  if ( v4 )
  {
    DockCache::UnregisterDeviceStatusNotif(*((LPCRITICAL_SECTION *)this + 410), v4);
    *((_QWORD *)this + 412) = 0;
  }
  *((_DWORD *)this + 23) = 0;
  *(GUID *)((char *)this + 76) = GUID_NULL;
  memset_0((char *)this + 96, 0, 0xFFu);
  memset_0((char *)this + 360, 0, 0x480u);
  memset_0((char *)this + 1512, 0, 0x488u);
  memset_0((char *)this + 2688, 0, 0x24Au);
  _InterlockedDecrement((volatile signed __int32 *)&g_cLockCount);
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 410);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 24, 0xFFFFFFFF) == 1 )
    {
      DockCache::~DockCache((DockCache *)v5);
      operator delete((void *)v5);
    }
    *((_QWORD *)this + 410) = 0;
  }
  v6 = (DockingProviders *)*((_QWORD *)this + 334);
  if ( v6 )
  {
    DockingProviders::Release(v6);
    *((_QWORD *)this + 334) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 8);
  if ( v7 )
    CloseHandle(v7);
  v8 = *((_QWORD *)this + 7);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 7) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180008738  mov     [rsp+arg_8], rbx
0x18000873d  push    rdi
0x18000873e  sub     rsp, 20h
0x180008742  mov     rbx, rcx
0x180008745  lea     rax, ??_7CWiGigDAFProviderAssociation@@6B@; const CWiGigDAFProviderAssociation::`vftable'
0x18000874c  mov     [rcx], rax
0x18000874f  lea     rdi, WPP_GLOBAL_Control
0x180008756  mov     rcx, cs:WPP_GLOBAL_Control
0x18000875d  cmp     rcx, rdi
0x180008760  jz      short loc_1800087B6
0x180008762  cmp     byte ptr [rcx+19h], 4
0x180008766  jb      short loc_18000878D
0x180008768  test    byte ptr [rcx+1Ch], 1
0x18000876c  jz      short loc_18000878D
0x18000876e  mov     edx, 1Eh
0x180008773  mov     r9, rbx
0x180008776  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000877d  mov     rcx, [rcx+10h]
0x180008781  call    WPP_SF_q
0x180008786  mov     rcx, cs:WPP_GLOBAL_Control
0x18000878d  cmp     rcx, rdi
0x180008790  jz      short loc_1800087B6
0x180008792  cmp     byte ptr [rcx+19h], 4
0x180008796  jb      short loc_1800087B6
0x180008798  test    byte ptr [rcx+1Ch], 1
0x18000879c  jz      short loc_1800087B6
0x18000879e  mov     edx, 1Fh
0x1800087a3  mov     r9, rbx
0x1800087a6  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x1800087ad  mov     rcx, [rcx+10h]
0x1800087b1  call    WPP_SF_q
0x1800087b6  mov     rcx, rbx; this
0x1800087b9  call    ?CancelPairing@CWiGigDAFProviderAssociation@@AEAAXXZ; CWiGigDAFProviderAssociation::CancelPairing(void)
0x1800087be  mov     rcx, [rbx+40h]; hEvent
0x1800087c2  call    cs:__imp_ResetEvent
0x1800087c8  test    eax, eax
0x1800087ca  jnz     short loc_1800087D2
0x1800087cc  call    cs:__imp_GetLastError
0x1800087d2  mov     rcx, [rbx+0A78h]; hAlgorithm
0x1800087d9  test    rcx, rcx
0x1800087dc  jz      short loc_1800087F1
0x1800087de  xor     edx, edx; dwFlags
0x1800087e0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800087e6  mov     qword ptr [rbx+0A78h], 0
0x1800087f1  mov     qword ptr [rbx+160h], 0
0x1800087fc  mov     byte ptr [rbx+0CD8h], 0
0x180008803  mov     rdx, [rbx+0CE0h]; unsigned __int64
0x18000880a  test    rdx, rdx
0x18000880d  jz      short loc_180008826
0x18000880f  mov     rcx, [rbx+0CD0h]; lpCriticalSection
0x180008816  call    ?UnregisterDeviceStatusNotif@DockCache@@QEAAJ_K@Z; DockCache::UnregisterDeviceStatusNotif(unsigned __int64)
0x18000881b  mov     qword ptr [rbx+0CE0h], 0
0x180008826  mov     dword ptr [rbx+5Ch], 0
0x18000882d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180008834  movdqu  xmmword ptr [rbx+4Ch], xmm0
0x180008839  lea     rcx, [rbx+60h]; void *
0x18000883d  xor     edx, edx; Val
0x18000883f  mov     r8d, 0FFh; Size
0x180008845  call    memset_0
0x18000884a  lea     rcx, [rbx+168h]; void *
0x180008851  xor     edx, edx; Val
0x180008853  mov     r8d, 480h; Size
0x180008859  call    memset_0
0x18000885e  lea     rcx, [rbx+5E8h]; void *
0x180008865  xor     edx, edx; Val
0x180008867  mov     r8d, 488h; Size
0x18000886d  call    memset_0
0x180008872  lea     rcx, [rbx+0A80h]; void *
0x180008879  xor     edx, edx; Val
0x18000887b  mov     r8d, 24Ah; Size
0x180008881  call    memset_0
0x180008886  lock dec cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18000888d  mov     rdi, [rbx+0CD0h]
0x180008894  test    rdi, rdi
0x180008897  jz      short loc_1800088C1
0x180008899  or      eax, 0FFFFFFFFh
0x18000889c  lock xadd [rdi+60h], eax
0x1800088a1  cmp     eax, 1
0x1800088a4  jnz     short loc_1800088B6
0x1800088a6  mov     rcx, rdi; this
0x1800088a9  call    ??1DockCache@@AEAA@XZ; DockCache::~DockCache(void)
0x1800088ae  mov     rcx, rdi; Block
0x1800088b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800088b6  mov     qword ptr [rbx+0CD0h], 0
0x1800088c1  mov     rcx, [rbx+0A70h]; this
0x1800088c8  test    rcx, rcx
0x1800088cb  jz      short loc_1800088DD
0x1800088cd  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x1800088d2  mov     qword ptr [rbx+0A70h], 0
0x1800088dd  mov     rcx, [rbx+40h]; hObject
0x1800088e1  test    rcx, rcx
0x1800088e4  jz      short loc_1800088ED
0x1800088e6  call    cs:__imp_CloseHandle
0x1800088ec  nop
0x1800088ed  mov     rcx, [rbx+38h]
0x1800088f1  test    rcx, rcx
0x1800088f4  jz      short loc_18000890A
0x1800088f6  mov     rax, [rcx]
0x1800088f9  mov     rax, [rax+10h]
0x1800088fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008902  mov     qword ptr [rbx+38h], 0
0x18000890a  lea     rcx, [rbx+8]
0x18000890e  mov     rbx, [rsp+28h+arg_8]
0x180008913  add     rsp, 20h
0x180008917  pop     rdi
0x180008918  jmp     cs:__imp_DeleteCriticalSection
```
