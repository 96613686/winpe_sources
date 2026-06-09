# CSessionBaseRW::RemoveNamespaceRecord(SmartPtr<CNamespaceRecord>,int,long)

- ea: `0x180010914`
- end: `0x180010b12`
- name: `?RemoveNamespaceRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCNamespaceRecord@@@@HJ@Z`
- size: `510`
- prototype: `__int64 __fastcall(CSessionBaseRW *this, CNamespaceRecord ***, int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d4f4`
- `0x18000de68`
- `0x180010b18`

## callees

- `0x180007818`
- `0x180007d5c`
- `0x180007f98`
- `0x18000935c`
- `0x1800094d0`
- `0x180009528`
- `0x18000a818`
- `0x18000de68`
- `0x18000f728`
- `0x180010914`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::RemoveNamespaceRecord(CSessionBaseRW *this, CNamespaceRecord ***a2, int a3, int a4)
{
  CNamespaceRecord **v8; // r11
  int v9; // eax
  CNamespaceRecord **v10; // rax
  int PreviousNamespaceRecord; // eax
  int v12; // edi
  _QWORD *v13; // rcx
  CNamespaceRecord *v14; // r9
  __int64 v15; // rdx
  CNamespaceRecord **v16; // rbx
  CNamespaceRecord *v17; // rax
  int v18; // eax
  CNamespaceRecord **v20; // [rsp+70h] [rbp+8h] BYREF
  CNamespaceRecord **v21; // [rsp+78h] [rbp+10h] BYREF

  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v20);
  v8 = *a2;
  if ( (*((_BYTE *)**a2 + 40) & 3) == 1 )
  {
    v21 = *a2;
    if ( v8 )
      ++*((_DWORD *)v8 + 2);
    v9 = CSessionBaseRW::NotifySearch(this);
    if ( v9 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        (unsigned int)v9);
  }
  v10 = *a2;
  v21 = v10;
  if ( v10 )
    ++*((_DWORD *)v10 + 2);
  PreviousNamespaceRecord = CSessionBaseRO::GetPreviousNamespaceRecord((char *)this + 8, &v21, &v20, 0);
  v12 = PreviousNamespaceRecord;
  if ( PreviousNamespaceRecord < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        *((unsigned int *)**a2 + 4),
        PreviousNamespaceRecord);
    goto LABEL_31;
  }
  v12 = CNamespaceRecord::Delete(**a2);
  if ( v12 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v14 = **a2;
    v15 = 50;
LABEL_30:
    WPP_SF_dd(v13[2], v15, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, *((unsigned int *)v14 + 4), v12);
    goto LABEL_31;
  }
  v16 = v20;
  if ( v20 && *v20 )
  {
    if ( a3 || (v17 = **a2, (*((_BYTE *)v17 + 40) & 1) != 0) )
    {
      v21 = v20;
      if ( v20 )
        ++*((_DWORD *)v20 + 2);
      v18 = CSessionBaseRW::FinalizeNamespaceRecord(this, a4);
    }
    else
    {
      *((_DWORD *)*v20 + 20) = *((_DWORD *)v17 + 20);
      v18 = CNamespaceRecord::Commit(*v16);
    }
    v12 = v18;
    if ( v18 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = *v16;
        v15 = 51;
        goto LABEL_30;
      }
    }
  }
LABEL_31:
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v20);
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(a2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180010914  mov     [rsp+arg_10], rbx
0x180010919  push    rbp
0x18001091a  push    rsi
0x18001091b  push    rdi
0x18001091c  push    r12
0x18001091e  push    r13
0x180010920  push    r14
0x180010922  push    r15
0x180010924  sub     rsp, 30h
0x180010928  mov     r15d, r9d
0x18001092b  mov     r14d, r8d
0x18001092e  mov     rsi, rdx
0x180010931  mov     rbp, rcx
0x180010934  lea     rcx, [rsp+68h+arg_0]
0x180010939  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18001093e  mov     r11, [rsi]
0x180010941  mov     rax, [r11]
0x180010944  mov     r10b, [rax+28h]
0x180010948  and     r10b, 3
0x18001094c  lea     rbx, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x180010953  lea     r13, WPP_GLOBAL_Control
0x18001095a  mov     r12d, 1
0x180010960  cmp     r10b, r12b
0x180010963  jnz     short loc_1800109AD
0x180010965  mov     [rsp+68h+arg_8], r11
0x18001096a  test    r11, r11
0x18001096d  jz      short loc_180010973
0x18001096f  add     [r11+8], r12d
0x180010973  lea     r8, [rsp+68h+arg_8]
0x180010978  mov     edx, r12d
0x18001097b  mov     rcx, rbp; this
0x18001097e  call    ?NotifySearch@CSessionBaseRW@@IEAAJW4NotifySearchActions@1@V?$SmartPtr@VCNamespaceRecord@@@@@Z; CSessionBaseRW::NotifySearch(CSessionBaseRW::NotifySearchActions,SmartPtr<CNamespaceRecord>)
0x180010983  test    eax, eax
0x180010985  jns     short loc_1800109AD
0x180010987  mov     rcx, cs:WPP_GLOBAL_Control
0x18001098e  cmp     rcx, r13
0x180010991  jz      short loc_1800109AD
0x180010993  test    [rcx+1Ch], r12b
0x180010997  jz      short loc_1800109AD
0x180010999  mov     edx, 30h ; '0'
0x18001099e  mov     r9d, eax
0x1800109a1  mov     r8, rbx
0x1800109a4  mov     rcx, [rcx+10h]
0x1800109a8  call    WPP_SF_d
0x1800109ad  mov     rax, [rsi]
0x1800109b0  mov     [rsp+68h+arg_8], rax
0x1800109b5  test    rax, rax
0x1800109b8  jz      short loc_1800109BE
0x1800109ba  add     [rax+8], r12d
0x1800109be  lea     rcx, [rbp+8]
0x1800109c2  xor     r9d, r9d
0x1800109c5  lea     r8, [rsp+68h+arg_0]
0x1800109ca  lea     rdx, [rsp+68h+arg_8]
0x1800109cf  call    ?GetPreviousNamespaceRecord@CSessionBaseRO@@IEAAJV?$SmartPtr@VCNamespaceRecord@@@@AEAV2@H@Z; CSessionBaseRO::GetPreviousNamespaceRecord(SmartPtr<CNamespaceRecord>,SmartPtr<CNamespaceRecord> &,int)
0x1800109d4  mov     edi, eax
0x1800109d6  test    eax, eax
0x1800109d8  jns     short loc_180010A0B
0x1800109da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109e1  cmp     rcx, r13
0x1800109e4  jz      loc_180010AE6
0x1800109ea  test    [rcx+1Ch], r12b
0x1800109ee  jz      loc_180010AE6
0x1800109f4  mov     rdx, [rsi]
0x1800109f7  mov     r9, [rdx]
0x1800109fa  mov     edx, 31h ; '1'
0x1800109ff  mov     [rsp+68h+var_48], eax
0x180010a03  mov     r8, rbx
0x180010a06  jmp     loc_180010AD9
0x180010a0b  mov     rcx, [rsi]
0x180010a0e  mov     rcx, [rcx]; this
0x180010a11  call    ?Delete@CNamespaceRecord@@QEAAJXZ; CNamespaceRecord::Delete(void)
0x180010a16  mov     edi, eax
0x180010a18  test    eax, eax
0x180010a1a  jns     short loc_180010A49
0x180010a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a23  cmp     rcx, r13
0x180010a26  jz      loc_180010AE6
0x180010a2c  test    [rcx+1Ch], r12b
0x180010a30  jz      loc_180010AE6
0x180010a36  mov     rax, [rsi]
0x180010a39  mov     r9, [rax]
0x180010a3c  mov     edx, 32h ; '2'
0x180010a41  mov     r8, rbx
0x180010a44  jmp     loc_180010AD5
0x180010a49  mov     rbx, [rsp+68h+arg_0]
0x180010a4e  test    rbx, rbx
0x180010a51  jz      loc_180010AE6
0x180010a57  cmp     qword ptr [rbx], 0
0x180010a5b  jz      loc_180010AE6
0x180010a61  test    r14d, r14d
0x180010a64  jnz     short loc_180010A85
0x180010a66  mov     rax, [rsi]
0x180010a69  mov     rax, [rax]
0x180010a6c  test    [rax+28h], r12b
0x180010a70  jnz     short loc_180010A85
0x180010a72  mov     rcx, [rbx]
0x180010a75  mov     eax, [rax+50h]
0x180010a78  mov     [rcx+50h], eax
0x180010a7b  mov     rcx, [rbx]; this
0x180010a7e  call    ?Commit@CNamespaceRecord@@QEAAJXZ; CNamespaceRecord::Commit(void)
0x180010a83  jmp     short loc_180010AAE
0x180010a85  mov     [rsp+68h+arg_8], rbx
0x180010a8a  test    rbx, rbx
0x180010a8d  jz      short loc_180010A93
0x180010a8f  add     [rbx+8], r12d
0x180010a93  mov     [rsp+68h+var_48], r15d
0x180010a98  mov     r9d, 2
0x180010a9e  mov     r8d, r12d
0x180010aa1  lea     rdx, [rsp+68h+arg_8]
0x180010aa6  mov     rcx, rbp
0x180010aa9  call    ?FinalizeNamespaceRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCNamespaceRecord@@@@HW4ParentRefreshType@1@J@Z; CSessionBaseRW::FinalizeNamespaceRecord(SmartPtr<CNamespaceRecord>,int,CSessionBaseRW::ParentRefreshType,long)
0x180010aae  mov     edi, eax
0x180010ab0  test    eax, eax
0x180010ab2  jns     short loc_180010AE6
0x180010ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010abb  cmp     rcx, r13
0x180010abe  jz      short loc_180010AE6
0x180010ac0  test    [rcx+1Ch], r12b
0x180010ac4  jz      short loc_180010AE6
0x180010ac6  mov     r9, [rbx]
0x180010ac9  mov     edx, 33h ; '3'
0x180010ace  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x180010ad5  mov     [rsp+68h+var_48], edi
0x180010ad9  mov     r9d, [r9+10h]
0x180010add  mov     rcx, [rcx+10h]
0x180010ae1  call    WPP_SF_dd
0x180010ae6  lea     rcx, [rsp+68h+arg_0]
0x180010aeb  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
0x180010af0  mov     rcx, rsi
0x180010af3  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
0x180010af8  mov     eax, edi
0x180010afa  mov     rbx, [rsp+68h+arg_10]
0x180010b02  add     rsp, 30h
0x180010b06  pop     r15
0x180010b08  pop     r14
0x180010b0a  pop     r13
0x180010b0c  pop     r12
0x180010b0e  pop     rdi
0x180010b0f  pop     rsi
0x180010b10  pop     rbp
0x180010b11  retn
```
