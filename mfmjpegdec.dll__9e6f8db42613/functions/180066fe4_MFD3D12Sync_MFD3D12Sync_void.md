# MFD3D12Sync::~MFD3D12Sync(void)

- ea: `0x180066fe4`
- end: `0x18006722e`
- name: `??1MFD3D12Sync@@UEAA@XZ`
- size: `586`
- prototype: `void __fastcall(MFD3D12Sync *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180067320`

## callees

- `0x180020598`
- `0x18002312c`
- `0x1800245f0`
- `0x180045060`
- `0x18004a11c`
- `0x180056638`
- `0x180066fe4`
- `0x180067264`
- `0x180067380`
- `0x180068e34`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067204`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180067204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006717c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006717c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067159`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067159`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MFD3D12Sync::~MFD3D12Sync(MFD3D12Sync *this)
{
  void **v2; // rbx
  __int64 v3; // r9
  __int64 i; // rcx
  unsigned int v5; // edx
  _QWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  const struct std::nothrow_t *v10; // rdx
  HANDLE ProcessHeap; // r15
  _QWORD *v12; // r8
  _QWORD *v13; // rsi
  __int64 v14; // rcx
  __int128 v15; // [rsp+30h] [rbp-10h] BYREF
  MFD3D12Sync::QueuedFreeWait *v16; // [rsp+70h] [rbp+30h] BYREF
  __int64 v17; // [rsp+78h] [rbp+38h] BYREF

  *(_QWORD *)this = &MFD3D12Sync::`vftable';
  *((_QWORD *)this + 1) = &MFD3D12Sync::`vftable'{for `IMFD3D12SynchronizationObject'};
  *((_QWORD *)this + 2) = &MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &MFD3D12Sync::`vftable'{for `IMFD3D11SynchronizationObjectCommands'};
  *((_QWORD *)this + 4) = &MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "MFD3D12Sync::~MFD3D12Sync", 79);
  if ( g_wppLevels >= 0x10u )
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids,
      this,
      *((_DWORD *)this + 47));
  v2 = (void **)((char *)this + 176);
  v15 = 0;
  v3 = *((_QWORD *)this + 22);
  if ( v3 && *((_DWORD *)this + 47) )
  {
    for ( i = 0; (unsigned int)i < (*((_DWORD *)this + 46) & 0x7FFFFFFFu); i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(v3 + 8 * i) )
      {
        *(_QWORD *)&v15 = *(_QWORD *)(v3 + 8 * i);
        break;
      }
    }
  }
  v17 = 0;
  v16 = 0;
  while ( (unsigned int)CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::GetNext(
                          (char *)this + 176,
                          &v15,
                          &v17,
                          &v16) )
  {
    if ( v16 )
      MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(v16, v5);
  }
  v6 = *v2;
  if ( *v2 )
  {
    if ( *((_DWORD *)this + 47) )
    {
      v7 = 0;
      if ( (*((_DWORD *)this + 46) & 0x7FFFFFFF) != 0 )
      {
        do
        {
          v8 = v6[v7];
          if ( v8 )
          {
            v6[v7] = 0;
            do
            {
              v9 = *(_QWORD *)(v8 + 16);
              *(_QWORD *)(v8 + 16) = *((_QWORD *)this + 25);
              *((_QWORD *)this + 25) = v8;
              v8 = v9;
            }
            while ( v9 );
            v6 = *v2;
          }
          v7 = (unsigned int)(v7 + 1);
        }
        while ( (unsigned int)v7 < (*((_DWORD *)this + 46) & 0x7FFFFFFFu) );
      }
    }
    *((_DWORD *)this + 47) = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  SharedFenceManager::~SharedFenceManager((MFD3D12Sync *)((char *)this + 432));
  ProcessHeap = GetProcessHeap();
  v12 = (_QWORD *)*((_QWORD *)this + 26);
  if ( v12 )
  {
    do
    {
      v13 = (_QWORD *)*v12;
      if ( v12 != (_QWORD *)((char *)this + 224) )
        HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 26) = v13;
      v12 = v13;
    }
    while ( v13 );
  }
  if ( *((int *)this + 46) >= 0 && *v2 )
  {
    operator delete(*v2, v10);
    *v2 = 0;
  }
  *((_DWORD *)this + 46) &= 0x80000000;
  *(_QWORD *)((char *)this + 188) = 0;
  v14 = *((_QWORD *)this + 18);
  if ( v14 )
  {
    *((_QWORD *)this + 18) = 0;
    (*(void (__fastcall **)(__int64, const struct std::nothrow_t *, _QWORD *))(*(_QWORD *)v14 + 16LL))(v14, v10, v12);
  }
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((char *)this + 136);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 128);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 120);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  *((_DWORD *)this + 17) = -1073741823;
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((char *)this + 56);
}

```

## disassembly

```asm
0x180066fe4  mov     [rsp-28h+arg_10], rbx
0x180066fe9  push    rbp
0x180066fea  push    rsi
0x180066feb  push    rdi
0x180066fec  push    r14
0x180066fee  push    r15
0x180066ff0  mov     rbp, rsp
0x180066ff3  sub     rsp, 40h
0x180066ff7  mov     rdi, rcx
0x180066ffa  lea     rax, ??_7MFD3D12Sync@@6B@; const MFD3D12Sync::`vftable'
0x180067001  mov     [rcx], rax
0x180067004  lea     rax, ??_7MFD3D12Sync@@6BIMFD3D12SynchronizationObject@@@; const MFD3D12Sync::`vftable'{for `IMFD3D12SynchronizationObject'}
0x18006700b  mov     [rcx+8], rax
0x18006700f  lea     rax, ??_7MFD3D12Sync@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>'}
0x180067016  mov     [rcx+10h], rax
0x18006701a  lea     rax, ??_7MFD3D12Sync@@6BIMFD3D11SynchronizationObjectCommands@@@; const MFD3D12Sync::`vftable'{for `IMFD3D11SynchronizationObjectCommands'}
0x180067021  mov     [rcx+18h], rax
0x180067025  lea     rax, ??_7MFD3D12Sync@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006702c  mov     [rcx+20h], rax
0x180067030  mov     r8d, 4Fh ; 'O'; int
0x180067036  lea     rdx, aMfd3d12syncMfd; "MFD3D12Sync::~MFD3D12Sync"
0x18006703d  lea     rcx, [rbp+arg_0]; this
0x180067041  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067046  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x18006704d  jb      short loc_180067078
0x18006704f  mov     edx, 15h
0x180067054  mov     eax, [rdi+0BCh]
0x18006705a  mov     [rsp+40h+var_20], eax
0x18006705e  mov     r9, rdi
0x180067061  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x180067068  mov     rcx, cs:WPP_GLOBAL_Control
0x18006706f  mov     rcx, [rcx+10h]
0x180067073  call    WPP_SF_qd
0x180067078  lea     rbx, [rdi+0B0h]
0x18006707f  xorps   xmm0, xmm0
0x180067082  movdqu  [rbp+var_10], xmm0
0x180067087  mov     r9, [rbx]
0x18006708a  mov     esi, 7FFFFFFFh
0x18006708f  test    r9, r9
0x180067092  jz      short loc_1800670B6
0x180067094  cmp     dword ptr [rbx+0Ch], 0
0x180067098  jz      short loc_1800670B6
0x18006709a  xor     ecx, ecx
0x18006709c  mov     edx, [rbx+8]
0x18006709f  and     edx, esi
0x1800670a1  cmp     ecx, edx
0x1800670a3  jnb     short loc_1800670B6
0x1800670a5  mov     r8, [r9+rcx*8]
0x1800670a9  test    r8, r8
0x1800670ac  jnz     short loc_1800670B2
0x1800670ae  inc     ecx
0x1800670b0  jmp     short loc_1800670A1
0x1800670b2  mov     qword ptr [rbp+var_10], r8
0x1800670b6  mov     [rbp+arg_8], 0
0x1800670be  mov     [rbp+arg_0], 0
0x1800670c6  jmp     short loc_1800670D6
0x1800670c8  mov     rcx, [rbp+arg_0]; this
0x1800670cc  test    rcx, rcx
0x1800670cf  jz      short loc_1800670D6
0x1800670d1  call    ??_GQueuedFreeWait@MFD3D12Sync@@QEAAPEAXI@Z; MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(uint)
0x1800670d6  lea     r9, [rbp+arg_0]
0x1800670da  lea     r8, [rbp+arg_8]
0x1800670de  lea     rdx, [rbp+var_10]
0x1800670e2  mov     rcx, rbx
0x1800670e5  call    ?GetNext@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEAU_POSITION@1@AEAPEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::GetNext(CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::_POSITION &,ID3D12Fence * &,MFD3D12Sync::QueuedFreeWait * &)
0x1800670ea  test    eax, eax
0x1800670ec  jnz     short loc_1800670C8
0x1800670ee  mov     rcx, [rbx]
0x1800670f1  test    rcx, rcx
0x1800670f4  jz      short loc_180067143
0x1800670f6  cmp     [rbx+0Ch], eax
0x1800670f9  jz      short loc_18006713C
0x1800670fb  xor     r8d, r8d
0x1800670fe  test    [rbx+8], esi
0x180067101  jbe     short loc_18006713C
0x180067103  mov     rdx, [rcx+r8*8]
0x180067107  test    rdx, rdx
0x18006710a  jz      short loc_18006712F
0x18006710c  mov     qword ptr [rcx+r8*8], 0
0x180067114  mov     rcx, [rdx+10h]
0x180067118  mov     rax, [rbx+18h]
0x18006711c  mov     [rdx+10h], rax
0x180067120  mov     [rbx+18h], rdx
0x180067124  mov     rdx, rcx
0x180067127  test    rcx, rcx
0x18006712a  jnz     short loc_180067114
0x18006712c  mov     rcx, [rbx]
0x18006712f  inc     r8d
0x180067132  mov     eax, [rbx+8]
0x180067135  and     eax, esi
0x180067137  cmp     r8d, eax
0x18006713a  jb      short loc_180067103
0x18006713c  mov     dword ptr [rbx+0Ch], 0
0x180067143  lea     rcx, [rbp+arg_0]; this
0x180067147  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006714c  lea     rcx, [rdi+1B0h]; this
0x180067153  call    ??1SharedFenceManager@@QEAA@XZ; SharedFenceManager::~SharedFenceManager(void)
0x180067158  nop
0x180067159  call    cs:__imp_GetProcessHeap
0x18006715f  mov     r15, rax
0x180067162  mov     r8, [rbx+20h]; lpMem
0x180067166  test    r8, r8
0x180067169  jz      short loc_18006718E
0x18006716b  lea     r14, [rbx+30h]
0x18006716f  mov     rsi, [r8]
0x180067172  cmp     r8, r14
0x180067175  jz      short loc_180067182
0x180067177  xor     edx, edx; dwFlags
0x180067179  mov     rcx, r15; hHeap
0x18006717c  call    cs:__imp_HeapFree
0x180067182  mov     [rbx+20h], rsi
0x180067186  mov     r8, rsi
0x180067189  test    rsi, rsi
0x18006718c  jnz     short loc_18006716F
0x18006718e  test    dword ptr [rbx+8], 80000000h
0x180067195  jnz     short loc_1800671AB
0x180067197  mov     rcx, [rbx]; void *
0x18006719a  test    rcx, rcx
0x18006719d  jz      short loc_1800671AB
0x18006719f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800671a4  mov     qword ptr [rbx], 0
0x1800671ab  and     dword ptr [rbx+8], 80000000h
0x1800671b2  mov     qword ptr [rbx+0Ch], 0
0x1800671ba  mov     rcx, [rdi+90h]
0x1800671c1  test    rcx, rcx
0x1800671c4  jz      short loc_1800671DE
0x1800671c6  mov     qword ptr [rdi+90h], 0
0x1800671d1  mov     rax, [rcx]
0x1800671d4  mov     rax, [rax+10h]
0x1800671d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671dd  nop
0x1800671de  lea     rcx, [rdi+88h]
0x1800671e5  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800671ea  lea     rcx, [rdi+80h]
0x1800671f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800671f6  lea     rcx, [rdi+78h]
0x1800671fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800671ff  nop
0x180067200  lea     rcx, [rdi+50h]; lpCriticalSection
0x180067204  call    cs:__imp_DeleteCriticalSection
0x18006720a  nop
0x18006720b  mov     dword ptr [rdi+44h], 0C0000001h
0x180067212  lea     rcx, [rdi+38h]
0x180067216  mov     rbx, [rsp+40h+arg_10]
0x18006721e  add     rsp, 40h
0x180067222  pop     r15
0x180067224  pop     r14
0x180067226  pop     rdi
0x180067227  pop     rsi
0x180067228  pop     rbp
0x180067229  jmp     ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
```
