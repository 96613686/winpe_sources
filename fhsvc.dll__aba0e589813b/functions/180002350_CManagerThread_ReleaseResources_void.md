# CManagerThread::ReleaseResources(void)

- ea: `0x180002350`
- end: `0x18000247a`
- name: `?ReleaseResources@CManagerThread@@QEAAXXZ`
- size: `298`
- prototype: `void __fastcall(CManagerThread *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001690`
- `0x1800017c0`

## callees

- `0x180002350`
- `0x18000b7a4`

## import_xrefs

- `msvcrt!free` at `0x180002419`
- `msvcrt!free` at `0x180002419`
- `ADVAPI32!RegCloseKey` at `0x1800023e5`
- `ADVAPI32!RegCloseKey` at `0x1800023e5`
- `KERNEL32!CloseHandle` at `0x1800023c9`
- `KERNEL32!CloseHandle` at `0x18000244e`
- `KERNEL32!CloseHandle` at `0x1800023c9`
- `KERNEL32!CloseHandle` at `0x18000244e`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180002375`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180002375`
- `KERNEL32!CloseThreadpoolWait` at `0x180002382`
- `KERNEL32!CloseThreadpoolWait` at `0x180002382`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800023a3`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800023a3`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800023b0`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800023b0`

## pseudocode

```c
void __fastcall CManagerThread::ReleaseResources(CManagerThread *this)
{
  struct _TP_WAIT *v2; // rcx
  struct _TP_CLEANUP_GROUP *v3; // rcx
  void *v4; // rcx
  HKEY v5; // rcx
  _QWORD *v6; // rcx
  _QWORD *v7; // rdi
  void *v8; // rcx

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
  *((_DWORD *)this + 2) = 0;
  if ( *((_QWORD *)this + 2) != *((_QWORD *)this + 7) )
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder((char *)this + 16);
  v6 = (_QWORD *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 3) = 0;
  if ( v6 )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      free(v6);
      v6 = v7;
    }
    while ( v7 );
  }
  *((_QWORD *)this + 2) = *((_QWORD *)this + 7);
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
}

```

## disassembly

```asm
0x180002350  mov     [rsp+arg_10], rbx
0x180002355  push    rbp
0x180002356  sub     rsp, 20h
0x18000235a  mov     rbx, rcx
0x18000235d  mov     [rsp+28h+arg_0], rsi
0x180002362  mov     rcx, [rcx+0E0h]; pwa
0x180002369  xor     ebp, ebp
0x18000236b  test    rcx, rcx
0x18000236e  jz      short loc_18000238F
0x180002370  mov     edx, 1; fCancelPendingCallbacks
0x180002375  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000237b  mov     rcx, [rbx+0E0h]; pwa
0x180002382  call    cs:__imp_CloseThreadpoolWait
0x180002388  mov     [rbx+0E0h], rbp
0x18000238f  mov     rcx, [rbx+80h]; ptpcg
0x180002396  test    rcx, rcx
0x180002399  jz      short loc_1800023BD
0x18000239b  xor     r8d, r8d; pvCleanupContext
0x18000239e  mov     edx, 1; fCancelPendingCallbacks
0x1800023a3  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800023a9  mov     rcx, [rbx+80h]; ptpcg
0x1800023b0  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800023b6  mov     [rbx+80h], rbp
0x1800023bd  mov     rcx, [rbx+0F8h]; hObject
0x1800023c4  test    rcx, rcx
0x1800023c7  jz      short loc_1800023D6
0x1800023c9  call    cs:__imp_CloseHandle
0x1800023cf  mov     [rbx+0F8h], rbp
0x1800023d6  mov     rcx, [rbx]; hKey
0x1800023d9  mov     [rbx+100h], rbp
0x1800023e0  test    rcx, rcx
0x1800023e3  jz      short loc_1800023EE
0x1800023e5  call    cs:__imp_RegCloseKey
0x1800023eb  mov     [rbx], rbp
0x1800023ee  mov     [rbx+8], ebp
0x1800023f1  mov     rdx, [rbx+10h]
0x1800023f5  cmp     rdx, [rbx+38h]
0x1800023f9  jz      short loc_180002404
0x1800023fb  lea     rcx, [rbx+10h]
0x1800023ff  call    ?RemovePostOrder@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::RemovePostOrder(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x180002404  mov     rcx, [rbx+28h]; Block
0x180002408  mov     [rbx+18h], rbp
0x18000240c  test    rcx, rcx
0x18000240f  jz      short loc_18000242C
0x180002411  mov     [rsp+28h+arg_8], rdi
0x180002416  mov     rdi, [rcx]
0x180002419  call    cs:__imp_free
0x18000241f  mov     rcx, rdi
0x180002422  test    rdi, rdi
0x180002425  jnz     short loc_180002416
0x180002427  mov     rdi, [rsp+28h+arg_8]
0x18000242c  mov     rax, [rbx+38h]
0x180002430  mov     rsi, [rsp+28h+arg_0]
0x180002435  mov     [rbx+10h], rax
0x180002439  mov     [rbx+28h], rbp
0x18000243d  mov     [rbx+20h], rbp
0x180002441  mov     rcx, [rbx+70h]; hObject
0x180002445  mov     [rbx+68h], rbp
0x180002449  test    rcx, rcx
0x18000244c  jz      short loc_180002458
0x18000244e  call    cs:__imp_CloseHandle
0x180002454  mov     [rbx+70h], rbp
0x180002458  mov     [rbx+78h], ebp
0x18000245b  mov     [rbx+0D8h], rbp
0x180002462  mov     [rbx+0E8h], ebp
0x180002468  mov     [rbx+0D0h], rbp
0x18000246f  mov     rbx, [rsp+28h+arg_10]
0x180002474  add     rsp, 20h
0x180002478  pop     rbp
0x180002479  retn
```
