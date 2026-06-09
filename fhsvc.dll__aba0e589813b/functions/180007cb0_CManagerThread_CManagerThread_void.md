# CManagerThread::~CManagerThread(void)

- ea: `0x180007cb0`
- end: `0x180007f49`
- name: `??1CManagerThread@@QEAA@XZ`
- size: `665`
- prototype: `void __fastcall(CManagerThread *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800126a0`

## callees

- `0x180007cb0`
- `0x18000b614`
- `0x18000b6a8`
- `0x18000b73c`
- `0x18000b7a4`

## import_xrefs

- `msvcrt!free` at `0x180007eda`
- `msvcrt!free` at `0x180007eff`
- `msvcrt!free` at `0x180007f12`
- `msvcrt!free` at `0x180007f20`
- `msvcrt!free` at `0x180007f33`
- `msvcrt!free` at `0x180007f3e`
- `msvcrt!free` at `0x180007eda`
- `msvcrt!free` at `0x180007eff`
- `msvcrt!free` at `0x180007f12`
- `msvcrt!free` at `0x180007f20`
- `msvcrt!free` at `0x180007f33`
- `msvcrt!free` at `0x180007f3e`
- `ADVAPI32!RegCloseKey` at `0x180007ec9`
- `ADVAPI32!RegCloseKey` at `0x180007ec9`
- `KERNEL32!CloseHandle` at `0x180007eb7`
- `KERNEL32!CloseHandle` at `0x180007eed`
- `KERNEL32!CloseHandle` at `0x180007eb7`
- `KERNEL32!CloseHandle` at `0x180007eed`
- `KERNEL32!DeleteCriticalSection` at `0x180007d7c`
- `KERNEL32!DeleteCriticalSection` at `0x180007d86`
- `KERNEL32!DeleteCriticalSection` at `0x180007d7c`
- `KERNEL32!DeleteCriticalSection` at `0x180007d86`
- `KERNEL32!FreeLibrary` at `0x180007d98`
- `KERNEL32!FreeLibrary` at `0x180007d98`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180007e71`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180007e71`
- `KERNEL32!CloseThreadpoolWait` at `0x180007e7e`
- `KERNEL32!CloseThreadpoolWait` at `0x180007e7e`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180007e98`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180007e98`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180007ea5`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180007ea5`

## pseudocode

```c
void __fastcall CManagerThread::~CManagerThread(CManagerThread *this)
{
  struct _TP_WAIT *v2; // rcx
  struct _TP_CLEANUP_GROUP *v3; // rcx
  void *v4; // rcx
  HKEY v5; // rcx
  _QWORD *v6; // rsi
  _QWORD *v7; // rcx
  void *v8; // rcx
  HMODULE v9; // rcx
  _QWORD *v10; // rcx
  void *v11; // rcx
  _QWORD *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  _QWORD *v15; // rdi
  _QWORD *v16; // rdi
  _QWORD *v17; // rdi

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 28);
  if ( v2 )
  {
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 28));
    *((_QWORD *)this + 28) = 0;
  }
  v3 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 16);
  if ( v3 )
  {
    CloseThreadpoolCleanupGroupMembers(v3, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 16));
    *((_QWORD *)this + 16) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 31);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 31) = 0;
  }
  v5 = *(HKEY *)this;
  *((_QWORD *)this + 32) = 0;
  if ( v5 )
  {
    RegCloseKey(v5);
    *(_QWORD *)this = 0;
  }
  v6 = (_QWORD *)((char *)this + 16);
  *((_DWORD *)this + 2) = 0;
  if ( *((_QWORD *)this + 2) != *((_QWORD *)this + 7) )
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder((char *)this + 16);
  v7 = (_QWORD *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
  {
    do
    {
      v15 = (_QWORD *)*v7;
      free(v7);
      v7 = v15;
    }
    while ( v15 );
  }
  *v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 4) = 0;
  v8 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 13) = 0;
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 14) = 0;
  }
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 26) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v9 = (HMODULE)*((_QWORD *)this + 52);
  if ( v9 )
  {
    FreeLibrary(v9);
    *((_QWORD *)this + 52) = 0;
  }
  if ( *((_QWORD *)this + 45) != *((_QWORD *)this + 50) )
    ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RemovePostOrder((char *)this + 360);
  v10 = (_QWORD *)*((_QWORD *)this + 48);
  *((_QWORD *)this + 46) = 0;
  if ( v10 )
  {
    do
    {
      v16 = (_QWORD *)*v10;
      free(v10);
      v10 = v16;
    }
    while ( v16 );
  }
  v11 = (void *)*((_QWORD *)this + 50);
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 45) = v11;
  if ( v11 )
    free(v11);
  if ( *((_QWORD *)this + 39) != *((_QWORD *)this + 44) )
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RemovePostOrder((char *)this + 312);
  v12 = (_QWORD *)*((_QWORD *)this + 42);
  *((_QWORD *)this + 40) = 0;
  if ( v12 )
  {
    do
    {
      v17 = (_QWORD *)*v12;
      free(v12);
      v12 = v17;
    }
    while ( v17 );
  }
  v13 = (void *)*((_QWORD *)this + 44);
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 39) = v13;
  if ( v13 )
    free(v13);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemoveAll(v6);
  v14 = (void *)*((_QWORD *)this + 7);
  if ( v14 )
    free(v14);
}

```

## disassembly

```asm
0x180007cb0  sub     rsp, 28h
0x180007cb4  mov     [rsp+28h+arg_0], rbx
0x180007cb9  mov     rbx, rcx
0x180007cbc  mov     rcx, [rcx+0E0h]; pwa
0x180007cc3  mov     [rsp+28h+arg_8], rbp
0x180007cc8  xor     ebp, ebp
0x180007cca  mov     [rsp+28h+arg_10], rsi
0x180007ccf  mov     [rsp+28h+var_8], r14
0x180007cd4  test    rcx, rcx
0x180007cd7  jnz     loc_180007E6C
0x180007cdd  mov     rcx, [rbx+80h]; ptpcg
0x180007ce4  test    rcx, rcx
0x180007ce7  jnz     loc_180007E90
0x180007ced  mov     rcx, [rbx+0F8h]; hObject
0x180007cf4  test    rcx, rcx
0x180007cf7  jnz     loc_180007EB7
0x180007cfd  mov     rcx, [rbx]; hKey
0x180007d00  mov     [rbx+100h], rbp
0x180007d07  test    rcx, rcx
0x180007d0a  jnz     loc_180007EC9
0x180007d10  lea     rsi, [rbx+10h]
0x180007d14  mov     [rbx+8], ebp
0x180007d17  mov     rdx, [rsi]
0x180007d1a  cmp     rdx, [rsi+28h]
0x180007d1e  jz      short loc_180007D28
0x180007d20  mov     rcx, rsi
0x180007d23  call    ?RemovePostOrder@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x180007d28  mov     rcx, [rsi+18h]; Block
0x180007d2c  mov     [rsp+28h+arg_18], rdi
0x180007d31  mov     [rsi+8], rbp
0x180007d35  test    rcx, rcx
0x180007d38  jnz     loc_180007ED7
0x180007d3e  mov     rax, [rbx+38h]
0x180007d42  mov     [rsi], rax
0x180007d45  mov     [rbx+28h], rbp
0x180007d49  mov     [rbx+20h], rbp
0x180007d4d  mov     rcx, [rbx+70h]; hObject
0x180007d51  mov     [rbx+68h], rbp
0x180007d55  test    rcx, rcx
0x180007d58  jnz     loc_180007EED
0x180007d5e  lea     rcx, [rbx+110h]; lpCriticalSection
0x180007d65  mov     [rbx+78h], ebp
0x180007d68  mov     [rbx+0D8h], rbp
0x180007d6f  mov     [rbx+0E8h], ebp
0x180007d75  mov     [rbx+0D0h], rbp
0x180007d7c  call    cs:__imp_DeleteCriticalSection
0x180007d82  lea     rcx, [rbx+40h]; lpCriticalSection
0x180007d86  call    cs:__imp_DeleteCriticalSection
0x180007d8c  mov     rcx, [rbx+1A0h]; hLibModule
0x180007d93  test    rcx, rcx
0x180007d96  jz      short loc_180007DA5
0x180007d98  call    cs:__imp_FreeLibrary
0x180007d9e  mov     [rbx+1A0h], rbp
0x180007da5  lea     r14, [rbx+168h]
0x180007dac  mov     rdx, [r14]
0x180007daf  cmp     rdx, [r14+28h]
0x180007db3  jz      short loc_180007DBD
0x180007db5  mov     rcx, r14
0x180007db8  call    ?RemovePostOrder@?$CRBTree@PEAXV?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@PEAX@ATL@@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@3@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RemovePostOrder(ATL::CRBTree<void *,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<void *>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x180007dbd  mov     rcx, [r14+18h]; Block
0x180007dc1  mov     [r14+8], rbp
0x180007dc5  test    rcx, rcx
0x180007dc8  jnz     loc_180007EFC
0x180007dce  mov     rcx, [rbx+190h]; Block
0x180007dd5  mov     [rbx+180h], rbp
0x180007ddc  mov     [rbx+178h], rbp
0x180007de3  mov     [r14], rcx
0x180007de6  test    rcx, rcx
0x180007de9  jnz     loc_180007F12
0x180007def  lea     r14, [rbx+138h]
0x180007df6  mov     rdx, [r14]
0x180007df9  cmp     rdx, [r14+28h]
0x180007dfd  jz      short loc_180007E07
0x180007dff  mov     rcx, r14
0x180007e02  call    ?RemovePostOrder@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::RemovePostOrder(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::CNode *)
0x180007e07  mov     rcx, [r14+18h]; Block
0x180007e0b  mov     [r14+8], rbp
0x180007e0f  test    rcx, rcx
0x180007e12  jnz     loc_180007F1D
0x180007e18  mov     rcx, [rbx+160h]; Block
0x180007e1f  mov     rdi, [rsp+28h+arg_18]
0x180007e24  mov     [rbx+150h], rbp
0x180007e2b  mov     [rbx+148h], rbp
0x180007e32  mov     rbp, [rsp+28h+arg_8]
0x180007e37  mov     rbx, [rsp+28h+arg_0]
0x180007e3c  mov     [r14], rcx
0x180007e3f  mov     r14, [rsp+28h+var_8]
0x180007e44  test    rcx, rcx
0x180007e47  jnz     loc_180007F33
0x180007e4d  mov     rcx, rsi
0x180007e50  call    ?RemoveAll@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@QEAAXXZ; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemoveAll(void)
0x180007e55  mov     rcx, [rsi+28h]; Block
0x180007e59  mov     rsi, [rsp+28h+arg_10]
0x180007e5e  test    rcx, rcx
0x180007e61  jnz     loc_180007F3E
0x180007e67  add     rsp, 28h
0x180007e6b  retn
0x180007e6c  mov     edx, 1; fCancelPendingCallbacks
0x180007e71  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180007e77  mov     rcx, [rbx+0E0h]; pwa
0x180007e7e  call    cs:__imp_CloseThreadpoolWait
0x180007e84  mov     [rbx+0E0h], rbp
0x180007e8b  jmp     loc_180007CDD
0x180007e90  xor     r8d, r8d; pvCleanupContext
0x180007e93  mov     edx, 1; fCancelPendingCallbacks
0x180007e98  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180007e9e  mov     rcx, [rbx+80h]; ptpcg
0x180007ea5  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180007eab  mov     [rbx+80h], rbp
0x180007eb2  jmp     loc_180007CED
0x180007eb7  call    cs:__imp_CloseHandle
0x180007ebd  mov     [rbx+0F8h], rbp
0x180007ec4  jmp     loc_180007CFD
0x180007ec9  call    cs:__imp_RegCloseKey
0x180007ecf  mov     [rbx], rbp
0x180007ed2  jmp     loc_180007D10
0x180007ed7  mov     rdi, [rcx]
0x180007eda  call    cs:__imp_free
0x180007ee0  mov     rcx, rdi
0x180007ee3  test    rdi, rdi
0x180007ee6  jnz     short loc_180007ED7
0x180007ee8  jmp     loc_180007D3E
0x180007eed  call    cs:__imp_CloseHandle
0x180007ef3  mov     [rbx+70h], rbp
0x180007ef7  jmp     loc_180007D5E
0x180007efc  mov     rdi, [rcx]
0x180007eff  call    cs:__imp_free
0x180007f05  mov     rcx, rdi
0x180007f08  test    rdi, rdi
0x180007f0b  jnz     short loc_180007EFC
0x180007f0d  jmp     loc_180007DCE
0x180007f12  call    cs:__imp_free
0x180007f18  jmp     loc_180007DEF
0x180007f1d  mov     rdi, [rcx]
0x180007f20  call    cs:__imp_free
0x180007f26  mov     rcx, rdi
0x180007f29  test    rdi, rdi
0x180007f2c  jnz     short loc_180007F1D
0x180007f2e  jmp     loc_180007E18
0x180007f33  call    cs:__imp_free
0x180007f39  jmp     loc_180007E4D
0x180007f3e  call    cs:__imp_free
0x180007f44  jmp     loc_180007E67
```
