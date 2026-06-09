# CRestoreSession::GetBackupPath(long,ushort * *)

- ea: `0x180024170`
- end: `0x180024409`
- name: `?GetBackupPath@CRestoreSession@@UEAAJJPEAPEAG@Z`
- size: `665`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180007818`
- `0x180007a9c`
- `0x180007bac`
- `0x18000935c`
- `0x1800094d0`
- `0x180009a80`
- `0x180009d70`
- `0x18000a2f8`
- `0x180021b7c`
- `0x180024170`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800241a5`
- `KERNEL32!EnterCriticalSection` at `0x1800241a5`
- `KERNEL32!LeaveCriticalSection` at `0x1800243ec`
- `KERNEL32!LeaveCriticalSection` at `0x1800243ec`

## pseudocode

```c
__int64 __fastcall CRestoreSession::GetBackupPath(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // esi
  struct _RTL_CRITICAL_SECTION *v5; // r14
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  int FileRecord; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  int v11; // r8d
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rdx
  int v17; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-54h] BYREF
  __int64 v19; // [rsp+38h] [rbp-50h] BYREF
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+40h] [rbp-48h]
  _QWORD v21[8]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+20h] BYREF

  v4 = a2;
  v5 = this;
  v6 = this + 5;
  v20 = this + 5;
  v21[1] = this + 5;
  EnterCriticalSection(this + 5);
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(v21);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v19);
  FileRecord = CSessionBaseRO::GetFileRecord(&v5[1].LockSemaphore, v4, v21);
  if ( FileRecord < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 17;
LABEL_5:
      WPP_SF_d(v8[2], v9, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, (unsigned int)FileRecord);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  if ( !v21[0] || !*(_QWORD *)v21[0] )
  {
    FileRecord = -2147023728;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_30;
    v15 = 18;
    v14 = v4;
    goto LABEL_29;
  }
  v10 = *(_QWORD *)v21[0];
  if ( *(_WORD *)(*(_QWORD *)v21[0] + 40LL) != 4 )
  {
    if ( *(_WORD *)(v10 + 40) == 3 )
    {
      v12 = *(unsigned int *)(v10 + 60);
      v26 = v21[0];
      ++*(_DWORD *)(v21[0] + 8LL);
      FileRecord = CSessionBaseRO::ConstructStagingPath((__int64)&v5[1].LockSemaphore, (__int64)&v26, v12, &v19);
      LODWORD(v26) = FileRecord;
      if ( FileRecord < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 20;
          goto LABEL_5;
        }
        goto LABEL_30;
      }
      goto LABEL_42;
    }
    FileRecord = -2147024894;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_30;
    v14 = *(unsigned __int16 *)(v10 + 40);
    v15 = 21;
LABEL_29:
    WPP_SF_dd(v13[2], v15, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, v14, FileRecord);
    goto LABEL_30;
  }
  v11 = *(_DWORD *)(v10 + 60);
  v26 = v21[0];
  ++*(_DWORD *)(v21[0] + 8LL);
  FileRecord = CSessionBaseRO::ConstructTargetPath((int)v5 + 64, (_QWORD **)(int)&v26, v11, (int)&v19, 0);
  LODWORD(v26) = FileRecord;
  if ( FileRecord < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 19;
      goto LABEL_5;
    }
    goto LABEL_30;
  }
LABEL_42:
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    *a3 = (unsigned __int16 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AllocSysString(&v19);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v17) )
    {
      LODWORD(v26) = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids,
            (unsigned int)v17);
        FileRecord = v26;
        v6 = v20;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180024325);
        goto LABEL_30;
      }
      v5 = this;
      v4 = a2;
      FileRecord = v26;
      v6 = v20;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180024336);
    }
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    ATL::CRBMap<long,int,ATL::CElementTraits<long>,ATL::CElementTraits<int>>::SetAt(&v5[9].LockSemaphore, v4, 1);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v18) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, v18);
      FileRecord = v26;
      v6 = v20;
      __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_180024368);
    }
  }
LABEL_30:
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(v21);
  LeaveCriticalSection(v6);
  return (unsigned int)FileRecord;
}

```

## disassembly

```asm
0x180024170  mov     rax, rsp
0x180024173  mov     [rax+18h], rbx
0x180024177  mov     [rax+10h], edx
0x18002417a  mov     [rax+8], rcx
0x18002417e  push    rsi
0x18002417f  push    rdi
0x180024180  push    r12
0x180024182  push    r14
0x180024184  push    r15
0x180024186  sub     rsp, 60h
0x18002418a  mov     r12, r8
0x18002418d  mov     esi, edx
0x18002418f  mov     r14, rcx
0x180024192  lea     rdi, [rcx+0C8h]
0x180024199  mov     [rsp+88h+var_48], rdi
0x18002419e  mov     [rax-38h], rdi
0x1800241a2  mov     rcx, rdi; lpCriticalSection
0x1800241a5  call    cs:__imp_EnterCriticalSection
0x1800241ab  nop
0x1800241ac  lea     rcx, [rsp+88h+var_40]
0x1800241b1  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x1800241b6  nop
0x1800241b7  lea     rcx, [rsp+88h+var_50]
0x1800241bc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800241c1  nop
0x1800241c2  lea     r15, [r14+40h]
0x1800241c6  lea     r8, [rsp+88h+var_40]
0x1800241cb  mov     edx, esi
0x1800241cd  mov     rcx, r15
0x1800241d0  call    ?GetFileRecord@CSessionBaseRO@@IEAAJKAEAV?$SmartPtr@VCFileRecord@@@@@Z; CSessionBaseRO::GetFileRecord(ulong,SmartPtr<CFileRecord> &)
0x1800241d5  mov     ebx, eax
0x1800241d7  test    eax, eax
0x1800241d9  jns     short loc_180024219
0x1800241db  lea     rax, WPP_GLOBAL_Control
0x1800241e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241e9  cmp     rcx, rax
0x1800241ec  jz      loc_1800243CF
0x1800241f2  test    byte ptr [rcx+1Ch], 1
0x1800241f6  jz      loc_1800243CF
0x1800241fc  mov     edx, 11h
0x180024201  mov     r9d, ebx
0x180024204  lea     r8, WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids
0x18002420b  mov     rcx, [rcx+10h]
0x18002420f  call    WPP_SF_d
0x180024214  jmp     loc_1800243CF
0x180024219  mov     rax, [rsp+88h+var_40]
0x18002421e  test    rax, rax
0x180024221  jz      loc_180024394
0x180024227  cmp     qword ptr [rax], 0
0x18002422b  jz      loc_180024394
0x180024231  mov     rdx, [rax]
0x180024234  cmp     word ptr [rdx+28h], 4
0x180024239  jnz     short loc_1800242A9
0x18002423b  mov     r8d, [rdx+3Ch]
0x18002423f  mov     [rsp+88h+arg_18], rax
0x180024247  test    rax, rax
0x18002424a  jz      short loc_18002424F
0x18002424c  inc     dword ptr [rax+8]
0x18002424f  mov     [rsp+88h+var_68], 0
0x180024258  lea     r9, [rsp+88h+var_50]
0x18002425d  lea     rdx, [rsp+88h+arg_18]
0x180024265  mov     rcx, r15
0x180024268  call    ?ConstructTargetPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; CSessionBaseRO::ConstructTargetPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002426d  mov     ebx, eax
0x18002426f  mov     dword ptr [rsp+88h+arg_18], eax
0x180024276  test    eax, eax
0x180024278  jns     loc_180024315
0x18002427e  lea     rax, WPP_GLOBAL_Control
0x180024285  mov     rcx, cs:WPP_GLOBAL_Control
0x18002428c  cmp     rcx, rax
0x18002428f  jz      loc_1800243CF
0x180024295  test    byte ptr [rcx+1Ch], 1
0x180024299  jz      loc_1800243CF
0x18002429f  mov     edx, 13h
0x1800242a4  jmp     loc_180024201
0x1800242a9  cmp     word ptr [rdx+28h], 3
0x1800242ae  jnz     loc_18002436A
0x1800242b4  mov     r8d, [rdx+3Ch]
0x1800242b8  mov     [rsp+88h+arg_18], rax
0x1800242c0  test    rax, rax
0x1800242c3  jz      short loc_1800242C8
0x1800242c5  inc     dword ptr [rax+8]
0x1800242c8  lea     r9, [rsp+88h+var_50]
0x1800242cd  lea     rdx, [rsp+88h+arg_18]
0x1800242d5  mov     rcx, r15
0x1800242d8  call    ?ConstructStagingPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSessionBaseRO::ConstructStagingPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800242dd  mov     ebx, eax
0x1800242df  mov     dword ptr [rsp+88h+arg_18], eax
0x1800242e6  test    eax, eax
0x1800242e8  jns     short loc_180024315
0x1800242ea  lea     rax, WPP_GLOBAL_Control
0x1800242f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242f8  cmp     rcx, rax
0x1800242fb  jz      loc_1800243CF
0x180024301  test    byte ptr [rcx+1Ch], 1
0x180024305  jz      loc_1800243CF
0x18002430b  mov     edx, 14h
0x180024310  jmp     loc_180024201
0x180024315  lea     rcx, [rsp+88h+var_50]
0x18002431a  call    ?AllocSysString@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAGXZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AllocSysString(void)
0x18002431f  mov     [r12], rax
0x180024323  jmp     short loc_180024351
0x180024325  mov     ebx, dword ptr [rsp+88h+arg_18]
0x18002432c  mov     rdi, [rsp+88h+var_48]
0x180024331  jmp     loc_1800243CF
0x180024336  mov     r14, [rsp+88h+arg_0]
0x18002433e  mov     esi, [rsp+88h+arg_8]
0x180024345  mov     ebx, dword ptr [rsp+88h+arg_18]
0x18002434c  mov     rdi, [rsp+88h+var_48]
0x180024351  lea     rcx, [r14+180h]
0x180024358  mov     r8d, 1
0x18002435e  mov     edx, esi
0x180024360  call    ?SetAt@?$CRBMap@JHV?$CElementTraits@J@ATL@@V?$CElementTraits@H@2@@ATL@@QEAAPEAU__POSITION@@JH@Z; ATL::CRBMap<long,int,ATL::CElementTraits<long>,ATL::CElementTraits<int>>::SetAt(long,int)
0x180024365  nop
0x180024366  jmp     short loc_1800243CF
0x180024368  jmp     short loc_180024325
0x18002436a  mov     ebx, 80070002h
0x18002436f  lea     rax, WPP_GLOBAL_Control
0x180024376  mov     rcx, cs:WPP_GLOBAL_Control
0x18002437d  cmp     rcx, rax
0x180024380  jz      short loc_1800243CF
0x180024382  test    byte ptr [rcx+1Ch], 1
0x180024386  jz      short loc_1800243CF
0x180024388  movzx   r9d, word ptr [rdx+28h]
0x18002438d  mov     edx, 15h
0x180024392  jmp     short loc_1800243BA
0x180024394  mov     ebx, 80070490h
0x180024399  lea     rax, WPP_GLOBAL_Control
0x1800243a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243a7  cmp     rcx, rax
0x1800243aa  jz      short loc_1800243CF
0x1800243ac  test    byte ptr [rcx+1Ch], 1
0x1800243b0  jz      short loc_1800243CF
0x1800243b2  mov     edx, 12h
0x1800243b7  mov     r9d, esi
0x1800243ba  mov     dword ptr [rsp+88h+var_68], ebx
0x1800243be  lea     r8, WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids
0x1800243c5  mov     rcx, [rcx+10h]
0x1800243c9  call    WPP_SF_dd
0x1800243ce  nop
0x1800243cf  mov     rcx, [rsp+88h+var_50]
0x1800243d4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800243d8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800243dd  nop
0x1800243de  lea     rcx, [rsp+88h+var_40]
0x1800243e3  call    ??1?$SmartPtr@VCFileRecord@@@@QEAA@XZ; SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(void)
0x1800243e8  nop
0x1800243e9  mov     rcx, rdi; lpCriticalSection
0x1800243ec  call    cs:__imp_LeaveCriticalSection
0x1800243f2  mov     eax, ebx
0x1800243f4  mov     rbx, [rsp+88h+arg_10]
0x1800243fc  add     rsp, 60h
0x180024400  pop     r15
0x180024402  pop     r14
0x180024404  pop     r12
0x180024406  pop     rdi
0x180024407  pop     rsi
0x180024408  retn
```
