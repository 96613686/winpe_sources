# MFD3D12Sync::~MFD3D12Sync(void)

- ea: `0x1800cb06c`
- end: `0x1800cb2b8`
- name: `??1MFD3D12Sync@@UEAA@XZ`
- size: `588`
- prototype: `void __fastcall(MFD3D12Sync *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cb3a0`

## callees

- `0x18000a09c`
- `0x18000c9d0`
- `0x18000ecf0`
- `0x18003639c`
- `0x180053c3c`
- `0x180061e00`
- `0x1800cb06c`
- `0x1800cb2f4`
- `0x1800cb3fc`
- `0x1800cc4ec`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cb28d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cb28d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb207`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb207`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb1e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb1e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall MFD3D12Sync::~MFD3D12Sync(MFD3D12Sync *this)
{
  void **v2; // rbx
  __int64 v3; // r8
  __int64 v4; // rax
  unsigned int v5; // edx
  _QWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
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
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids,
      this,
      *((_DWORD *)this + 47));
  v2 = (void **)((char *)this + 176);
  v15 = 0;
  v3 = *((_QWORD *)this + 22);
  if ( v3 )
  {
    if ( *((_DWORD *)this + 47) )
    {
      v4 = 0;
      if ( (*((_DWORD *)this + 46) & 0x7FFFFFFF) != 0 )
      {
        while ( !*(_QWORD *)(v3 + 8 * v4) )
        {
          v4 = (unsigned int)(v4 + 1);
          if ( (unsigned int)v4 >= (*((_DWORD *)this + 46) & 0x7FFFFFFFu) )
            goto LABEL_10;
        }
        *(_QWORD *)&v15 = *(_QWORD *)(v3 + 8 * v4);
      }
    }
  }
LABEL_10:
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
    operator delete(*v2);
    *v2 = 0;
  }
  *((_DWORD *)this + 46) &= 0x80000000;
  *(_QWORD *)((char *)this + 188) = 0;
  v14 = *((_QWORD *)this + 18);
  if ( v14 )
  {
    *((_QWORD *)this + 18) = 0;
    (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v14 + 16LL))(v14, v10, v12);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 136);
  Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease((char *)this + 128);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 120);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  *((_DWORD *)this + 17) = -1073741823;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 56);
}

```

## disassembly

```asm
0x1800cb06c  mov     [rsp-28h+arg_10], rbx
0x1800cb071  push    rbp
0x1800cb072  push    rsi
0x1800cb073  push    rdi
0x1800cb074  push    r14
0x1800cb076  push    r15
0x1800cb078  mov     rbp, rsp
0x1800cb07b  sub     rsp, 40h
0x1800cb07f  mov     rdi, rcx
0x1800cb082  lea     rax, ??_7MFD3D12Sync@@6B@; const MFD3D12Sync::`vftable'
0x1800cb089  mov     [rcx], rax
0x1800cb08c  lea     rax, ??_7MFD3D12Sync@@6BIMFD3D12SynchronizationObject@@@; const MFD3D12Sync::`vftable'{for `IMFD3D12SynchronizationObject'}
0x1800cb093  mov     [rcx+8], rax
0x1800cb097  lea     rax, ??_7MFD3D12Sync@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@WRL@Microsoft@@@; const MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>'}
0x1800cb09e  mov     [rcx+10h], rax
0x1800cb0a2  lea     rax, ??_7MFD3D12Sync@@6BIMFD3D11SynchronizationObjectCommands@@@; const MFD3D12Sync::`vftable'{for `IMFD3D11SynchronizationObjectCommands'}
0x1800cb0a9  mov     [rcx+18h], rax
0x1800cb0ad  lea     rax, ??_7MFD3D12Sync@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const MFD3D12Sync::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800cb0b4  mov     [rcx+20h], rax
0x1800cb0b8  mov     r8d, 4Fh ; 'O'; int
0x1800cb0be  lea     rdx, aMfd3d12syncMfd; "MFD3D12Sync::~MFD3D12Sync"
0x1800cb0c5  lea     rcx, [rbp+arg_0]; this
0x1800cb0c9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cb0ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1800cb0d5  jb      short loc_1800CB100
0x1800cb0d7  mov     edx, 15h
0x1800cb0dc  mov     eax, [rdi+0BCh]
0x1800cb0e2  mov     [rsp+40h+var_20], eax
0x1800cb0e6  mov     r9, rdi
0x1800cb0e9  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cb0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb0f7  mov     rcx, [rcx+10h]
0x1800cb0fb  call    WPP_SF_qD
0x1800cb100  lea     rbx, [rdi+0B0h]
0x1800cb107  xorps   xmm0, xmm0
0x1800cb10a  movdqu  [rbp+var_10], xmm0
0x1800cb10f  mov     r8, [rbx]
0x1800cb112  mov     esi, 7FFFFFFFh
0x1800cb117  test    r8, r8
0x1800cb11a  jz      short loc_1800CB142
0x1800cb11c  cmp     dword ptr [rbx+0Ch], 0
0x1800cb120  jz      short loc_1800CB142
0x1800cb122  xor     eax, eax
0x1800cb124  mov     ecx, [rbx+8]
0x1800cb127  and     ecx, esi
0x1800cb129  jbe     short loc_1800CB142
0x1800cb12b  cmp     qword ptr [r8+rax*8], 0
0x1800cb130  jnz     short loc_1800CB13A
0x1800cb132  inc     eax
0x1800cb134  cmp     eax, ecx
0x1800cb136  jb      short loc_1800CB12B
0x1800cb138  jmp     short loc_1800CB142
0x1800cb13a  mov     rcx, [r8+rax*8]
0x1800cb13e  mov     qword ptr [rbp+var_10], rcx
0x1800cb142  mov     [rbp+arg_8], 0
0x1800cb14a  mov     [rbp+arg_0], 0
0x1800cb152  jmp     short loc_1800CB162
0x1800cb154  mov     rcx, [rbp+arg_0]; this
0x1800cb158  test    rcx, rcx
0x1800cb15b  jz      short loc_1800CB162
0x1800cb15d  call    ??_GQueuedFreeWait@MFD3D12Sync@@QEAAPEAXI@Z; MFD3D12Sync::QueuedFreeWait::`scalar deleting destructor'(uint)
0x1800cb162  lea     r9, [rbp+arg_0]
0x1800cb166  lea     r8, [rbp+arg_8]
0x1800cb16a  lea     rdx, [rbp+var_10]
0x1800cb16e  mov     rcx, rbx
0x1800cb171  call    ?GetNext@?$CTBucketHash@PEAUID3D12Fence@@PEAVQueuedFreeWait@MFD3D12Sync@@@@QEAAHAEAU_POSITION@1@AEAPEAUID3D12Fence@@AEAPEAVQueuedFreeWait@MFD3D12Sync@@@Z; CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::GetNext(CTBucketHash<ID3D12Fence *,MFD3D12Sync::QueuedFreeWait *>::_POSITION &,ID3D12Fence * &,MFD3D12Sync::QueuedFreeWait * &)
0x1800cb176  test    eax, eax
0x1800cb178  jnz     short loc_1800CB154
0x1800cb17a  mov     rcx, [rbx]
0x1800cb17d  test    rcx, rcx
0x1800cb180  jz      short loc_1800CB1CF
0x1800cb182  cmp     [rbx+0Ch], eax
0x1800cb185  jz      short loc_1800CB1C8
0x1800cb187  xor     r8d, r8d
0x1800cb18a  test    [rbx+8], esi
0x1800cb18d  jbe     short loc_1800CB1C8
0x1800cb18f  mov     rdx, [rcx+r8*8]
0x1800cb193  test    rdx, rdx
0x1800cb196  jz      short loc_1800CB1BB
0x1800cb198  mov     qword ptr [rcx+r8*8], 0
0x1800cb1a0  mov     rcx, [rdx+10h]
0x1800cb1a4  mov     rax, [rbx+18h]
0x1800cb1a8  mov     [rdx+10h], rax
0x1800cb1ac  mov     [rbx+18h], rdx
0x1800cb1b0  mov     rdx, rcx
0x1800cb1b3  test    rcx, rcx
0x1800cb1b6  jnz     short loc_1800CB1A0
0x1800cb1b8  mov     rcx, [rbx]
0x1800cb1bb  inc     r8d
0x1800cb1be  mov     eax, [rbx+8]
0x1800cb1c1  and     eax, esi
0x1800cb1c3  cmp     r8d, eax
0x1800cb1c6  jb      short loc_1800CB18F
0x1800cb1c8  mov     dword ptr [rbx+0Ch], 0
0x1800cb1cf  lea     rcx, [rbp+arg_0]; this
0x1800cb1d3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cb1d8  lea     rcx, [rdi+1B0h]; this
0x1800cb1df  call    ??1SharedFenceManager@@QEAA@XZ; SharedFenceManager::~SharedFenceManager(void)
0x1800cb1e4  call    cs:__imp_GetProcessHeap
0x1800cb1ea  mov     r15, rax
0x1800cb1ed  mov     r8, [rbx+20h]; lpMem
0x1800cb1f1  test    r8, r8
0x1800cb1f4  jz      short loc_1800CB219
0x1800cb1f6  lea     r14, [rbx+30h]
0x1800cb1fa  mov     rsi, [r8]
0x1800cb1fd  cmp     r8, r14
0x1800cb200  jz      short loc_1800CB20D
0x1800cb202  xor     edx, edx; dwFlags
0x1800cb204  mov     rcx, r15; hHeap
0x1800cb207  call    cs:__imp_HeapFree
0x1800cb20d  mov     [rbx+20h], rsi
0x1800cb211  mov     r8, rsi
0x1800cb214  test    rsi, rsi
0x1800cb217  jnz     short loc_1800CB1FA
0x1800cb219  test    dword ptr [rbx+8], 80000000h
0x1800cb220  jnz     short loc_1800CB236
0x1800cb222  mov     rcx, [rbx]; Block
0x1800cb225  test    rcx, rcx
0x1800cb228  jz      short loc_1800CB236
0x1800cb22a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cb22f  mov     qword ptr [rbx], 0
0x1800cb236  and     dword ptr [rbx+8], 80000000h
0x1800cb23d  mov     qword ptr [rbx+0Ch], 0
0x1800cb245  mov     rcx, [rdi+90h]
0x1800cb24c  test    rcx, rcx
0x1800cb24f  jz      short loc_1800CB268
0x1800cb251  mov     qword ptr [rdi+90h], 0
0x1800cb25c  mov     rax, [rcx]
0x1800cb25f  mov     rax, [rax+10h]
0x1800cb263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb268  lea     rcx, [rdi+88h]
0x1800cb26f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cb274  lea     rcx, [rdi+80h]
0x1800cb27b  call    ?InternalRelease@?$ComPtr@UIMFDXGISchedulerRegistration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFDXGISchedulerRegistration>::InternalRelease(void)
0x1800cb280  lea     rcx, [rdi+78h]
0x1800cb284  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cb289  lea     rcx, [rdi+50h]; lpCriticalSection
0x1800cb28d  call    cs:__imp_DeleteCriticalSection
0x1800cb293  mov     dword ptr [rdi+44h], 0C0000001h
0x1800cb29a  lea     rcx, [rdi+38h]
0x1800cb29e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cb2a3  nop
0x1800cb2a4  mov     rbx, [rsp+40h+arg_10]
0x1800cb2ac  add     rsp, 40h
0x1800cb2b0  pop     r15
0x1800cb2b2  pop     r14
0x1800cb2b4  pop     rdi
0x1800cb2b5  pop     rsi
0x1800cb2b6  pop     rbp
0x1800cb2b7  retn
```
