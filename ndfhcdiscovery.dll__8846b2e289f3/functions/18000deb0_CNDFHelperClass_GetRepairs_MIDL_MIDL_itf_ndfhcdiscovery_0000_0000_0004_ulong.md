# CNDFHelperClass::GetRepairs(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 * *,ulong *)

- ea: `0x18000deb0`
- end: `0x18000df6f`
- name: `?GetRepairs@CNDFHelperClass@@UEAAJPEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEAK@Z`
- size: `191`
- prototype: `__int64 __fastcall(CNDFHelperClass *__hidden this, struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000bb4c`
- `0x18000bdf4`
- `0x18000ca20`
- `0x18000deb0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000dece`
- `KERNEL32!EnterCriticalSection` at `0x18000dece`
- `KERNEL32!LeaveCriticalSection` at `0x18000df36`
- `KERNEL32!LeaveCriticalSection` at `0x18000df49`
- `KERNEL32!LeaveCriticalSection` at `0x18000df36`
- `KERNEL32!LeaveCriticalSection` at `0x18000df49`

## string_xrefs

- `0x18000defb`: `Repairs`

## pseudocode

```c
__int64 __fastcall CNDFHelperClass::GetRepairs(struct _RTL_CRITICAL_SECTION *this, LPVOID **a2, unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 *p_OwningThread; // rsi
  HANDLE LockSemaphore; // rdx
  ULONG_PTR SpinCount; // rcx
  int v10; // ebx
  int v12; // [rsp+28h] [rbp-60h]
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF
  __int64 v14; // [rsp+50h] [rbp-38h]

  v3 = this + 8;
  EnterCriticalSection(this + 8);
  p_OwningThread = (__int64 *)&this[4].OwningThread;
  if ( this[4].LockCount
    || (LockSemaphore = this->LockSemaphore,
        SpinCount = this->SpinCount,
        v13 = 0,
        v14 = 0,
        v10 = TKeyIteratorInitializer<std::vector<GUIDVarInfo>>(
                SpinCount,
                (int)LockSemaphore,
                (int)L"Repairs",
                (int)this + 168,
                (__int64)&this[4].OwningThread,
                v12,
                &v13),
        std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>(&v13),
        v10 >= 0) )
  {
    LeaveCriticalSection(v3);
    return TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004,GUIDVarInfo const,std::vector<GUIDVarInfo>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<GUIDVarInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&void FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,unsigned long,int)>,&long TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)>(
             a2,
             a3,
             p_OwningThread);
  }
  else
  {
    LeaveCriticalSection(v3);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x18000deb0  push    rbx
0x18000deb2  push    rbp
0x18000deb3  push    rsi
0x18000deb4  push    rdi
0x18000deb5  push    r14
0x18000deb7  sub     rsp, 60h
0x18000debb  lea     rdi, [rcx+140h]
0x18000dec2  mov     rbx, rcx
0x18000dec5  mov     rcx, rdi; lpCriticalSection
0x18000dec8  mov     rbp, r8
0x18000decb  mov     r14, rdx
0x18000dece  call    cs:__imp_EnterCriticalSection
0x18000ded5  nop     dword ptr [rax+rax+00h]
0x18000deda  lea     r9, [rbx+0A8h]; int
0x18000dee1  cmp     dword ptr [r9], 0
0x18000dee5  lea     rsi, [rbx+0B0h]
0x18000deec  jnz     short loc_18000DF46
0x18000deee  mov     rdx, [rbx+18h]; int
0x18000def2  lea     rax, [rsp+88h+var_48]
0x18000def7  mov     rcx, [rbx+20h]; int
0x18000defb  lea     r8, aRepairs; "Repairs"
0x18000df02  xorps   xmm0, xmm0
0x18000df05  mov     [rsp+88h+var_58], rax; void *
0x18000df0a  mov     [rsp+88h+var_68], rsi; __int64
0x18000df0f  movdqu  [rsp+88h+var_48], xmm0
0x18000df15  mov     [rsp+88h+var_38], 0
0x18000df1e  call    ??$TKeyIteratorInitializer@V?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@@@YAJPEAUHKEY__@@PEBG1PEAHPEAV?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@P6AJAEAVCRegKey@ATL@@11PEAX@ZPEAU?$TInitListKeyContext@V?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@@@@Z; TKeyIteratorInitializer<std::vector<GUIDVarInfo>>(HKEY__ *,ushort const *,ushort const *,int *,std::vector<GUIDVarInfo> *,long (*)(ATL::CRegKey &,ushort const *,ushort const *,void *),TInitListKeyContext<std::vector<GUIDVarInfo>> *)
0x18000df23  lea     rcx, [rsp+88h+var_48]
0x18000df28  mov     ebx, eax
0x18000df2a  call    ??1?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAA@XZ; std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>(void)
0x18000df2f  test    ebx, ebx
0x18000df31  jns     short loc_18000DF46
0x18000df33  mov     rcx, rdi; lpCriticalSection
0x18000df36  call    cs:__imp_LeaveCriticalSection
0x18000df3d  nop     dword ptr [rax+rax+00h]
0x18000df42  mov     eax, ebx
0x18000df44  jmp     short loc_18000DF63
0x18000df46  mov     rcx, rdi; lpCriticalSection
0x18000df49  call    cs:__imp_LeaveCriticalSection
0x18000df50  nop     dword ptr [rax+rax+00h]
0x18000df55  mov     r8, rsi
0x18000df58  mov     rdx, rbp
0x18000df5b  mov     rcx, r14
0x18000df5e  call    ??$TDataGetter@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@$$CBUGUIDVarInfo@@V?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UGUIDVarInfo@@@std@@@std@@@4@V?$TNDFDeallocator@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@$1?FreeHelperBasicRootCauseInfos@@YAXPEAU1@KH@Z@@$1??$TCopyAndAllocateGUIDVarInfo@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@@@YAJPEAU1@PEBU2@@Z@@YAJPEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEAKAEAV?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@@Z; TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004,GUIDVarInfo const,std::vector<GUIDVarInfo>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<GUIDVarInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)>,&TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 * *,ulong *,std::vector<GUIDVarInfo> &)
0x18000df63  add     rsp, 60h
0x18000df67  pop     r14
0x18000df69  pop     rdi
0x18000df6a  pop     rsi
0x18000df6b  pop     rbp
0x18000df6c  pop     rbx
0x18000df6d  retn
```
