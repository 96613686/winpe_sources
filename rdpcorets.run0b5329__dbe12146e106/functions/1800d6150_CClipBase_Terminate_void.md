# CClipBase::Terminate(void)

- ea: `0x1800d6150`
- end: `0x1800d6508`
- name: `?Terminate@CClipBase@@MEAAJXZ`
- size: `952`
- prototype: `__int64 __fastcall(CClipBase *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180070790`

## callees

- `0x1800071c0`
- `0x1800071f0`
- `0x1800091a8`
- `0x18000a93c`
- `0x18000c8c0`
- `0x18001b3e8`
- `0x18002e600`
- `0x180032f60`
- `0x180059838`
- `0x18006df24`
- `0x1800b4c10`
- `0x1800b7840`
- `0x1800cdee4`
- `0x1800d6150`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d64e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d64e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d649a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d649a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d640c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d640c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d62aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6311`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d62aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6311`
- `USER32!UnregisterClassW` at `0x1800d61e3`
- `USER32!UnregisterClassW` at `0x1800d61e3`

## string_xrefs

- `0x1800d619d`: `RemoveNotificationSinks failed!`

## pseudocode

```c
__int64 __fastcall CClipBase::Terminate(CClipBase *this)
{
  __int64 v2; // rdx
  int v3; // edi
  __int64 v4; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  int v10; // esi
  __int64 v11; // rdi
  unsigned int v12; // eax
  int v13; // esi
  __int64 v14; // rdi
  unsigned int v15; // eax
  _QWORD *v16; // rdi
  __int64 v17; // rcx
  unsigned int i; // esi
  unsigned int v19; // eax
  int v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h] BYREF
  int v23; // [rsp+38h] [rbp-40h]

  v3 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 96LL))((char *)this - 8);
  if ( v3 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = v3;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"RemoveNotificationSinks failed!",
      v21);
  }
  if ( *((_WORD *)this + 104) )
  {
    UnregisterClassW(L"RdpClipRdrWindowClass", *((HINSTANCE *)this + 27));
    *((_WORD *)this + 104) = 0;
  }
  if ( *((_QWORD *)this + 103) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 824, v2, v4);
    *((_QWORD *)this + 103) = 0;
  }
  v6 = (_QWORD *)((char *)this + 264);
  v7 = *((_QWORD *)this + 33);
  if ( v7 )
  {
    CProxyDataObjectManager::Terminate((CProxyDataObjectManager *)(v7 + 8));
    if ( *v6 )
    {
      TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 264);
      *v6 = 0;
    }
  }
  v8 = (_QWORD *)((char *)this + 272);
  v9 = *((_QWORD *)this + 34);
  if ( v9 )
  {
    CProxyStreamManager::Terminate((CProxyStreamManager *)(v9 + 8));
    if ( *v8 )
    {
      TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 272);
      *v8 = 0;
    }
  }
  v10 = 0;
  v11 = 0;
  do
  {
    if ( *((_QWORD *)this + v11 + 9) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v12, v10);
      }
      CloseHandle(*((HANDLE *)this + v11 + 9));
      *((_QWORD *)this + v11 + 9) = 0;
    }
    ++v10;
    ++v11;
  }
  while ( v10 < 3 );
  v13 = 0;
  v14 = 0;
  do
  {
    if ( *((_QWORD *)this + v14 + 12) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v15, v13);
      }
      CloseHandle(*((HANDLE *)this + v14 + 12));
      *((_QWORD *)this + v14 + 12) = 0;
    }
    ++v13;
    ++v14;
  }
  while ( v13 < 3 );
  if ( *((_QWORD *)this + 83) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 664, v2, v4);
    *((_QWORD *)this + 83) = 0;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 664);
  }
  if ( *((_QWORD *)this + 76) )
  {
    TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 608);
    *((_QWORD *)this + 76) = 0;
  }
  if ( *((_QWORD *)this + 43) )
  {
    TCntPtr<WicSubsampler>::SafeRelease((char *)this + 344);
    *((_QWORD *)this + 43) = 0;
  }
  if ( *((_QWORD *)this + 77) )
  {
    TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 616);
    *((_QWORD *)this + 77) = 0;
  }
  if ( *((_QWORD *)this + 78) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 624, v2, v4);
    *((_QWORD *)this + 78) = 0;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 624);
  }
  v16 = (_QWORD *)((char *)this + 632);
  v17 = *((_QWORD *)this + 79);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
  if ( *v16 )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 632, v2, v4);
    *v16 = 0;
  }
  if ( *((_QWORD *)this + 84) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 672, v2, v4);
    *((_QWORD *)this + 84) = 0;
  }
  if ( *((_QWORD *)this + 105) )
  {
    TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 840);
    *((_QWORD *)this + 105) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
  if ( *((_QWORD *)this + 35) )
  {
    TCntPtr<CWppAutoTrace>::SafeRelease((char *)this + 280);
    *((_QWORD *)this + 35) = 0;
    TCntPtr<CTermInputMgr>::SafeAddRef((char *)this + 280);
  }
  for ( i = 0; i < *((_DWORD *)this + 171); ++i )
  {
    v22 = 0;
    v23 = 0;
    if ( (unsigned int)DynArray<SmartMap<CFileContentsReaderManager,unsigned long>::CCleanType,unsigned long>::GetAt(
                         (char *)this + 680,
                         i,
                         &v22)
      && v22 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v22 + 32) + 16LL))(*(_QWORD *)(v22 + 32));
      v22 = 0;
      DynArray<SmartMap<CFileContentsReaderManager,unsigned long>::CCleanType,unsigned long>::AddAt(
        (char *)this + 680,
        i,
        &v22);
    }
  }
  *((_DWORD *)this + 171) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
  if ( *((_DWORD *)this + 174) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v19);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
    *((_DWORD *)this + 174) = 0;
  }
  *((_DWORD *)this + 5) |= 4u;
  return 0;
}

```

## disassembly

```asm
0x1800d6150  push    rbx
0x1800d6152  push    rbp
0x1800d6153  push    rsi
0x1800d6154  push    rdi
0x1800d6155  push    r12
0x1800d6157  push    r14
0x1800d6159  sub     rsp, 48h
0x1800d615d  mov     rbx, rcx
0x1800d6160  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800d6164  mov     rax, [rcx]
0x1800d6167  mov     rax, [rax+60h]
0x1800d616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6170  xor     r14d, r14d
0x1800d6173  lea     r12, WPP_GLOBAL_Control
0x1800d617a  mov     edi, eax
0x1800d617c  test    eax, eax
0x1800d617e  jns     short loc_1800D61CB
0x1800d6180  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6187  cmp     rcx, r12
0x1800d618a  jz      short loc_1800D61CB
0x1800d618c  test    byte ptr [rcx+1Ch], 8
0x1800d6190  jz      short loc_1800D61CB
0x1800d6192  cmp     byte ptr [rcx+19h], 2
0x1800d6196  jb      short loc_1800D61CB
0x1800d6198  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d619d  lea     rcx, aRemovenotifica; "RemoveNotificationSinks failed!"
0x1800d61a4  mov     [rsp+78h+var_50], edi
0x1800d61a8  mov     [rsp+78h+var_58], rcx
0x1800d61ad  lea     edx, [r14+1Fh]
0x1800d61b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d61b8  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1800d61bf  mov     r9d, eax
0x1800d61c2  mov     rcx, [rcx+10h]
0x1800d61c6  call    WPP_SF_DsD
0x1800d61cb  cmp     [rbx+0D0h], r14w
0x1800d61d3  jz      short loc_1800D61F1
0x1800d61d5  mov     rdx, [rbx+0D8h]; hInstance
0x1800d61dc  lea     rcx, aRdpcliprdrwind; "RdpClipRdrWindowClass"
0x1800d61e3  call    cs:__imp_UnregisterClassW
0x1800d61e9  mov     [rbx+0D0h], r14w
0x1800d61f1  lea     rdi, [rbx+338h]
0x1800d61f8  cmp     [rdi], r14
0x1800d61fb  jz      short loc_1800D6208
0x1800d61fd  mov     rcx, rdi
0x1800d6200  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800d6205  mov     [rdi], r14
0x1800d6208  lea     rdi, [rbx+108h]
0x1800d620f  mov     rcx, [rdi]
0x1800d6212  test    rcx, rcx
0x1800d6215  jz      short loc_1800D6230
0x1800d6217  add     rcx, 8; this
0x1800d621b  call    ?Terminate@CProxyDataObjectManager@@UEAAJXZ; CProxyDataObjectManager::Terminate(void)
0x1800d6220  cmp     [rdi], r14
0x1800d6223  jz      short loc_1800D6230
0x1800d6225  mov     rcx, rdi
0x1800d6228  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x1800d622d  mov     [rdi], r14
0x1800d6230  lea     rdi, [rbx+110h]
0x1800d6237  mov     rcx, [rdi]
0x1800d623a  test    rcx, rcx
0x1800d623d  jz      short loc_1800D6258
0x1800d623f  add     rcx, 8; this
0x1800d6243  call    ?Terminate@CProxyStreamManager@@UEAAJXZ; CProxyStreamManager::Terminate(void)
0x1800d6248  cmp     [rdi], r14
0x1800d624b  jz      short loc_1800D6258
0x1800d624d  mov     rcx, rdi
0x1800d6250  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x1800d6255  mov     [rdi], r14
0x1800d6258  mov     esi, r14d
0x1800d625b  mov     rdi, r14
0x1800d625e  cmp     [rbx+rdi*8+48h], r14
0x1800d6263  jz      short loc_1800D62B5
0x1800d6265  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d626c  cmp     rcx, r12
0x1800d626f  jz      short loc_1800D62A5
0x1800d6271  test    byte ptr [rcx+1Ch], 1
0x1800d6275  jz      short loc_1800D62A5
0x1800d6277  cmp     byte ptr [rcx+19h], 5
0x1800d627b  jb      short loc_1800D62A5
0x1800d627d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d6282  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6289  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1800d6290  mov     edx, 20h ; ' '
0x1800d6295  mov     dword ptr [rsp+78h+var_58], esi
0x1800d6299  mov     r9d, eax
0x1800d629c  mov     rcx, [rcx+10h]
0x1800d62a0  call    WPP_SF_Dd
0x1800d62a5  mov     rcx, [rbx+rdi*8+48h]; hObject
0x1800d62aa  call    cs:__imp_CloseHandle
0x1800d62b0  mov     [rbx+rdi*8+48h], r14
0x1800d62b5  inc     esi
0x1800d62b7  inc     rdi
0x1800d62ba  cmp     esi, 3
0x1800d62bd  jl      short loc_1800D625E
0x1800d62bf  mov     esi, r14d
0x1800d62c2  mov     rdi, r14
0x1800d62c5  cmp     [rbx+rdi*8+60h], r14
0x1800d62ca  jz      short loc_1800D631C
0x1800d62cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d62d3  cmp     rcx, r12
0x1800d62d6  jz      short loc_1800D630C
0x1800d62d8  test    byte ptr [rcx+1Ch], 1
0x1800d62dc  jz      short loc_1800D630C
0x1800d62de  cmp     byte ptr [rcx+19h], 5
0x1800d62e2  jb      short loc_1800D630C
0x1800d62e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d62e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d62f0  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1800d62f7  mov     edx, 21h ; '!'
0x1800d62fc  mov     dword ptr [rsp+78h+var_58], esi
0x1800d6300  mov     r9d, eax
0x1800d6303  mov     rcx, [rcx+10h]
0x1800d6307  call    WPP_SF_Dd
0x1800d630c  mov     rcx, [rbx+rdi*8+60h]; hObject
0x1800d6311  call    cs:__imp_CloseHandle
0x1800d6317  mov     [rbx+rdi*8+60h], r14
0x1800d631c  inc     esi
0x1800d631e  inc     rdi
0x1800d6321  cmp     esi, 3
0x1800d6324  jl      short loc_1800D62C5
0x1800d6326  lea     rdi, [rbx+298h]
0x1800d632d  cmp     [rdi], r14
0x1800d6330  jz      short loc_1800D6345
0x1800d6332  mov     rcx, rdi
0x1800d6335  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800d633a  mov     rcx, rdi
0x1800d633d  mov     [rdi], r14
0x1800d6340  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800d6345  lea     rdi, [rbx+260h]
0x1800d634c  cmp     [rdi], r14
0x1800d634f  jz      short loc_1800D635C
0x1800d6351  mov     rcx, rdi
0x1800d6354  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x1800d6359  mov     [rdi], r14
0x1800d635c  lea     rdi, [rbx+158h]
0x1800d6363  cmp     [rdi], r14
0x1800d6366  jz      short loc_1800D6373
0x1800d6368  mov     rcx, rdi
0x1800d636b  call    ?SafeRelease@?$TCntPtr@VWicSubsampler@@@@AEAAXXZ; TCntPtr<WicSubsampler>::SafeRelease(void)
0x1800d6370  mov     [rdi], r14
0x1800d6373  lea     rdi, [rbx+268h]
0x1800d637a  cmp     [rdi], r14
0x1800d637d  jz      short loc_1800D638A
0x1800d637f  mov     rcx, rdi
0x1800d6382  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x1800d6387  mov     [rdi], r14
0x1800d638a  lea     rdi, [rbx+270h]
0x1800d6391  cmp     [rdi], r14
0x1800d6394  jz      short loc_1800D63A9
0x1800d6396  mov     rcx, rdi
0x1800d6399  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800d639e  mov     rcx, rdi
0x1800d63a1  mov     [rdi], r14
0x1800d63a4  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800d63a9  lea     rdi, [rbx+278h]
0x1800d63b0  mov     rcx, [rdi]
0x1800d63b3  test    rcx, rcx
0x1800d63b6  jz      short loc_1800D63C4
0x1800d63b8  mov     rax, [rcx]
0x1800d63bb  mov     rax, [rax+20h]
0x1800d63bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d63c4  cmp     [rdi], r14
0x1800d63c7  jz      short loc_1800D63D4
0x1800d63c9  mov     rcx, rdi
0x1800d63cc  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800d63d1  mov     [rdi], r14
0x1800d63d4  lea     rdi, [rbx+2A0h]
0x1800d63db  cmp     [rdi], r14
0x1800d63de  jz      short loc_1800D63EB
0x1800d63e0  mov     rcx, rdi
0x1800d63e3  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800d63e8  mov     [rdi], r14
0x1800d63eb  lea     rdi, [rbx+348h]
0x1800d63f2  cmp     [rdi], r14
0x1800d63f5  jz      short loc_1800D6402
0x1800d63f7  mov     rcx, rdi
0x1800d63fa  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x1800d63ff  mov     [rdi], r14
0x1800d6402  lea     rbp, [rbx+2C0h]
0x1800d6409  mov     rcx, rbp; lpCriticalSection
0x1800d640c  call    cs:__imp_EnterCriticalSection
0x1800d6412  lea     rdi, [rbx+118h]
0x1800d6419  cmp     [rdi], r14
0x1800d641c  jz      short loc_1800D6431
0x1800d641e  mov     rcx, rdi
0x1800d6421  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x1800d6426  mov     rcx, rdi
0x1800d6429  mov     [rdi], r14
0x1800d642c  call    ?SafeAddRef@?$TCntPtr@VCTermInputMgr@@@@AEAAXXZ; TCntPtr<CTermInputMgr>::SafeAddRef(void)
0x1800d6431  lea     rdi, [rbx+2A8h]
0x1800d6438  mov     esi, r14d
0x1800d643b  cmp     [rdi+4], r14d
0x1800d643f  jbe     short loc_1800D6493
0x1800d6441  lea     r8, [rsp+78h+var_48]
0x1800d6446  mov     [rsp+78h+var_48], r14
0x1800d644b  mov     edx, esi
0x1800d644d  mov     [rsp+78h+var_40], r14d
0x1800d6452  mov     rcx, rdi
0x1800d6455  call    ?GetAt@?$DynArray@VCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@K@@QEAAHKPEAVCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@@Z; DynArray<SmartMap<CFileContentsReaderManager,ulong>::CCleanType,ulong>::GetAt(ulong,SmartMap<CFileContentsReaderManager,ulong>::CCleanType *)
0x1800d645a  test    eax, eax
0x1800d645c  jz      short loc_1800D648C
0x1800d645e  mov     rcx, [rsp+78h+var_48]
0x1800d6463  test    rcx, rcx
0x1800d6466  jz      short loc_1800D648C
0x1800d6468  mov     rcx, [rcx+20h]
0x1800d646c  mov     rax, [rcx]
0x1800d646f  mov     rax, [rax+10h]
0x1800d6473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6478  lea     r8, [rsp+78h+var_48]
0x1800d647d  mov     [rsp+78h+var_48], r14
0x1800d6482  mov     edx, esi
0x1800d6484  mov     rcx, rdi
0x1800d6487  call    ?AddAt@?$DynArray@VCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@K@@QEAAHKAEAVCCleanType@?$SmartMap@VCFileContentsReaderManager@@K@@@Z; DynArray<SmartMap<CFileContentsReaderManager,ulong>::CCleanType,ulong>::AddAt(ulong,SmartMap<CFileContentsReaderManager,ulong>::CCleanType &)
0x1800d648c  inc     esi
0x1800d648e  cmp     esi, [rdi+4]
0x1800d6491  jb      short loc_1800D6441
0x1800d6493  mov     rcx, rbp; lpCriticalSection
0x1800d6496  mov     [rdi+4], r14d
0x1800d649a  call    cs:__imp_LeaveCriticalSection
0x1800d64a0  cmp     [rbx+2B8h], r14d
0x1800d64a7  jz      short loc_1800D64F5
0x1800d64a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800d64b0  cmp     rax, r12
0x1800d64b3  jz      short loc_1800D64E5
0x1800d64b5  test    byte ptr [rax+1Ch], 1
0x1800d64b9  jz      short loc_1800D64E5
0x1800d64bb  cmp     byte ptr [rax+19h], 5
0x1800d64bf  jb      short loc_1800D64E5
0x1800d64c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d64c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d64cd  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1800d64d4  mov     edx, 22h ; '"'
0x1800d64d9  mov     r9d, eax
0x1800d64dc  mov     rcx, [rcx+10h]
0x1800d64e0  call    WPP_SF_d
0x1800d64e5  mov     rcx, rbp; lpCriticalSection
0x1800d64e8  call    cs:__imp_DeleteCriticalSection
0x1800d64ee  mov     [rbx+2B8h], r14d
0x1800d64f5  or      dword ptr [rbx+14h], 4
0x1800d64f9  xor     eax, eax
0x1800d64fb  add     rsp, 48h
0x1800d64ff  pop     r14
0x1800d6501  pop     r12
0x1800d6503  pop     rdi
0x1800d6504  pop     rsi
0x1800d6505  pop     rbp
0x1800d6506  pop     rbx
0x1800d6507  retn
```
