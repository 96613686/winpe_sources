# CClassPart::CopyParentProperty(CClassPart &,ushort const *)

- ea: `0x1800733d0`
- end: `0x180073709`
- name: `?CopyParentProperty@CClassPart@@QEAAJAEAV1@PEBG@Z`
- size: `825`
- prototype: `int(CClassPart *__hidden this, struct CClassPart *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180073a70`

## callees

- `0x1800067a0`
- `0x18000d230`
- `0x180013ae0`
- `0x180013cd0`
- `0x180021820`
- `0x180021850`
- `0x180022c70`
- `0x180037120`
- `0x18005d568`
- `0x18005f7c0`
- `0x180060640`
- `0x1800733d0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180073449`
- `wbemcomn!GetMemLogObject` at `0x1800734f9`
- `wbemcomn!GetMemLogObject` at `0x18007355d`
- `wbemcomn!GetMemLogObject` at `0x1800735c4`
- `wbemcomn!GetMemLogObject` at `0x1800736b1`
- `wbemcomn!GetMemLogObject` at `0x180073449`
- `wbemcomn!GetMemLogObject` at `0x1800734f9`
- `wbemcomn!GetMemLogObject` at `0x18007355d`
- `wbemcomn!GetMemLogObject` at `0x1800735c4`
- `wbemcomn!GetMemLogObject` at `0x1800736b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073457`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073507`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007356b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800735cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800736bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073457`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073507`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007356b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800735cf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800736bf`

## pseudocode

```c
__int64 __fastcall CClassPart::CopyParentProperty(CClassPart *this, struct CClassPart *a2, const unsigned __int16 *a3)
{
  struct CPropertyInformation *PropertyInfo; // rax
  int v8; // r13d
  unsigned int v9; // eax
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // r12d
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  int inserted; // ebx
  CMemoryLog *v20; // rax
  int Bit; // eax
  __int64 v22; // rcx
  CMemoryLog *v23; // rax
  unsigned int v24; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-65h]
  unsigned int v26[2]; // [rsp+38h] [rbp-61h] BYREF
  struct CFastHeap *v27; // [rsp+40h] [rbp-59h]
  _QWORD v28[2]; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v29; // [rsp+58h] [rbp-41h]
  _QWORD v30[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v31; // [rsp+70h] [rbp-29h]
  __int64 (__fastcall **v32[2])(_QWORD); // [rsp+78h] [rbp-21h] BYREF
  int v33; // [rsp+88h] [rbp-11h]
  __int64 (__fastcall **v34[2])(_QWORD); // [rsp+90h] [rbp-9h] BYREF
  int v35; // [rsp+A0h] [rbp+7h]
  unsigned __int16 v36; // [rsp+118h] [rbp+7Fh]

  PropertyInfo = CClassPart::FindPropertyInfo(a2, a3);
  if ( !PropertyInfo )
    return 2147749890LL;
  v8 = *(_DWORD *)((char *)PropertyInfo + 6);
  v36 = *((_WORD *)PropertyInfo + 2);
  v25 = *(_DWORD *)PropertyInfo;
  v24 = 0;
  v9 = CBasicQualifierSet::ComputeNecessarySpaceForPropagation((unsigned __int8 *)PropertyInfo + 14, 2u);
  if ( !(unsigned int)CFastHeap::Allocate((CClassPart *)((char *)this + 200), v9 + 14, &v24) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749894LL;
    }
    v12 = 28;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    return 2147749894LL;
  }
  v13 = (unsigned int)CClassPart::FindPropertyInfo(a2, a3);
  v14 = v24;
  v15 = v13;
  CFastHeap::ResolveHeapPointer((CClassPart *)((char *)this + 200), v24);
  v16 = v15 - *((_DWORD *)a2 + 12);
  v30[0] = &CClassPartPtr::`vftable';
  v30[1] = a2;
  v28[0] = &CHeapPtr::`vftable';
  v31 = v16;
  v28[1] = (char *)this + 200;
  v29 = v14;
  v27 = (struct CClassPart *)((char *)a2 + 200);
  if ( !CPropertyInformation::WritePropagatedVersion(
          (struct CPtrSource *)v30,
          (struct CPtrSource *)v28,
          (struct CClassPart *)((char *)a2 + 200),
          (CClassPart *)((char *)this + 200)) )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217402);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749894LL;
    }
    v12 = 29;
    goto LABEL_32;
  }
  *(_QWORD *)v26 = 0;
  if ( !(unsigned int)CFastHeap::CreateNoCaseStringHeapPtr((CClassPart *)((char *)this + 200), a3, v26) )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147217402);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749894LL;
    }
    v12 = 30;
    goto LABEL_32;
  }
  v26[1] = v14;
  inserted = CPropertyLookupTable::InsertProperty(
               (CClassPart *)((char *)this + 152),
               (const struct CPropertyLookup *)v26,
               (int *)&v24);
  if ( inserted >= 0 )
  {
    Bit = CBitBlockTable<2>::GetBit(*((_QWORD *)a2 + 21), v36, 0);
    v22 = *((_QWORD *)this + 21);
    if ( Bit )
    {
      CBitBlockTable<2>::SetBit(v22, v36, 0);
    }
    else
    {
      CBitBlockTable<2>::SetBit(v22, v36, 0);
      v34[0] = (__int64 (__fastcall **)(_QWORD))&CDataTablePtr::`vftable';
      v32[0] = (__int64 (__fastcall **)(_QWORD))&CDataTablePtr::`vftable';
      v34[1] = (__int64 (__fastcall **)(_QWORD))((char *)a2 + 168);
      v35 = v8;
      v32[1] = (__int64 (__fastcall **)(_QWORD))((char *)this + 168);
      v33 = v8;
      if ( !(unsigned int)CUntypedValue::CopyTo(v34, v25, v32, v27, (CClassPart *)((char *)this + 200)) )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, -2147217402);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 2147749894LL;
        }
        v12 = 32;
        goto LABEL_32;
      }
    }
    CBitBlockTable<2>::SetBit(*((_QWORD *)this + 21), v36, 1);
    return 0;
  }
  v20 = GetMemLogObject();
  CMemoryLog::Write(v20, inserted);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
      (unsigned int)inserted);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800733d0  push    rbp
0x1800733d2  push    rbx
0x1800733d3  push    rsi
0x1800733d4  push    rdi
0x1800733d5  push    r12
0x1800733d7  push    r13
0x1800733d9  push    r14
0x1800733db  push    r15
0x1800733dd  lea     rbp, [rsp-1Fh]
0x1800733e2  sub     rsp, 0B8h
0x1800733e9  mov     rdi, rdx
0x1800733ec  mov     r14, rcx
0x1800733ef  mov     rcx, rdi; this
0x1800733f2  mov     rdx, r8; unsigned __int16 *
0x1800733f5  mov     rsi, r8
0x1800733f8  call    ?FindPropertyInfo@CClassPart@@QEAAPEAVCPropertyInformation@@PEBG@Z; CClassPart::FindPropertyInfo(ushort const *)
0x1800733fd  test    rax, rax
0x180073400  jnz     short loc_18007340C
0x180073402  mov     eax, 80041002h
0x180073407  jmp     loc_180073659
0x18007340c  movzx   ecx, word ptr [rax+4]
0x180073410  lea     r15, [r14+0C8h]
0x180073417  mov     r13d, [rax+6]
0x18007341b  mov     dl, 2; unsigned __int8
0x18007341d  mov     [rbp+57h+arg_18], cx
0x180073421  mov     ecx, [rax]
0x180073423  mov     [rbp+57h+var_BC], ecx
0x180073426  lea     rcx, [rax+0Eh]; unsigned __int8 *
0x18007342a  mov     [rbp+57h+var_C0], 0
0x180073431  call    ?ComputeNecessarySpaceForPropagation@CBasicQualifierSet@@SAKPEAEE@Z; CBasicQualifierSet::ComputeNecessarySpaceForPropagation(uchar *,uchar)
0x180073436  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x18007343a  mov     rcx, r15; this
0x18007343d  lea     edx, [rax+0Eh]; unsigned int
0x180073440  call    ?Allocate@CFastHeap@@QEAAHKAEFAK@Z; CFastHeap::Allocate(ulong,ulong &)
0x180073445  test    eax, eax
0x180073447  jnz     short loc_180073492
0x180073449  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007344f  mov     rcx, rax
0x180073452  mov     edx, 80041006h
0x180073457  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007345d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073464  lea     rax, WPP_GLOBAL_Control
0x18007346b  cmp     rcx, rax
0x18007346e  jz      loc_1800736FF
0x180073474  test    byte ptr [rcx+1Ch], 1
0x180073478  jz      loc_1800736FF
0x18007347e  cmp     byte ptr [rcx+19h], 2
0x180073482  jb      loc_1800736FF
0x180073488  mov     edx, 1Ch
0x18007348d  jmp     loc_1800736E9
0x180073492  mov     rdx, rsi; unsigned __int16 *
0x180073495  mov     rcx, rdi; this
0x180073498  call    ?FindPropertyInfo@CClassPart@@QEAAPEAVCPropertyInformation@@PEBG@Z; CClassPart::FindPropertyInfo(ushort const *)
0x18007349d  mov     r12d, [rbp+57h+var_C0]
0x1800734a1  mov     rcx, r15; this
0x1800734a4  mov     edx, r12d; unsigned int
0x1800734a7  mov     rbx, rax
0x1800734aa  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x1800734af  sub     ebx, [rdi+30h]
0x1800734b2  lea     rax, ??_7CClassPartPtr@@6B@; const CClassPartPtr::`vftable'
0x1800734b9  mov     [rbp+57h+var_90], rax
0x1800734bd  lea     rdx, [rbp+57h+var_A8]; struct CPtrSource *
0x1800734c1  lea     rax, ??_7CHeapPtr@@6B@; const CHeapPtr::`vftable'
0x1800734c8  mov     [rbp+57h+var_88], rdi
0x1800734cc  mov     [rbp+57h+var_A8], rax
0x1800734d0  lea     rcx, [rbp+57h+var_90]; struct CPtrSource *
0x1800734d4  lea     rax, [rdi+0C8h]
0x1800734db  mov     [rbp+57h+var_80], ebx
0x1800734de  mov     r8, rax; struct CFastHeap *
0x1800734e1  mov     [rbp+57h+var_A0], r15
0x1800734e5  mov     r9, r15; struct CFastHeap *
0x1800734e8  mov     [rbp+57h+var_98], r12d
0x1800734ec  mov     [rbp+57h+var_B0], rax
0x1800734f0  call    ?WritePropagatedVersion@CPropertyInformation@@SAHPEAVCPtrSource@@0PEAVCFastHeap@@1@Z; CPropertyInformation::WritePropagatedVersion(CPtrSource *,CPtrSource *,CFastHeap *,CFastHeap *)
0x1800734f5  test    eax, eax
0x1800734f7  jnz     short loc_180073542
0x1800734f9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800734ff  mov     rcx, rax
0x180073502  mov     edx, 80041006h
0x180073507  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007350d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073514  lea     rax, WPP_GLOBAL_Control
0x18007351b  cmp     rcx, rax
0x18007351e  jz      loc_1800736FF
0x180073524  test    byte ptr [rcx+1Ch], 1
0x180073528  jz      loc_1800736FF
0x18007352e  cmp     byte ptr [rcx+19h], 2
0x180073532  jb      loc_1800736FF
0x180073538  mov     edx, 1Dh
0x18007353d  jmp     loc_1800736E9
0x180073542  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x180073546  mov     qword ptr [rbp+57h+var_B8], 0
0x18007354e  mov     rdx, rsi; unsigned __int16 *
0x180073551  mov     rcx, r15; this
0x180073554  call    ?CreateNoCaseStringHeapPtr@CFastHeap@@QEAAHPEBGAEFAK@Z; CFastHeap::CreateNoCaseStringHeapPtr(ushort const *,ulong &)
0x180073559  test    eax, eax
0x18007355b  jnz     short loc_1800735A6
0x18007355d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073563  mov     rcx, rax
0x180073566  mov     edx, 80041006h
0x18007356b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073571  mov     rcx, cs:WPP_GLOBAL_Control
0x180073578  lea     rax, WPP_GLOBAL_Control
0x18007357f  cmp     rcx, rax
0x180073582  jz      loc_1800736FF
0x180073588  test    byte ptr [rcx+1Ch], 1
0x18007358c  jz      loc_1800736FF
0x180073592  cmp     byte ptr [rcx+19h], 2
0x180073596  jb      loc_1800736FF
0x18007359c  mov     edx, 1Eh
0x1800735a1  jmp     loc_1800736E9
0x1800735a6  lea     rcx, [r14+98h]; this
0x1800735ad  mov     [rbp+57h+var_B8+4], r12d
0x1800735b1  lea     r8, [rbp+57h+var_C0]; int *
0x1800735b5  lea     rdx, [rbp+57h+var_B8]; struct CPropertyLookup *
0x1800735b9  call    ?InsertProperty@CPropertyLookupTable@@QEAAJAEBUCPropertyLookup@@AEAH@Z; CPropertyLookupTable::InsertProperty(CPropertyLookup const &,int &)
0x1800735be  mov     ebx, eax
0x1800735c0  test    eax, eax
0x1800735c2  jns     short loc_180073610
0x1800735c4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800735ca  mov     rcx, rax
0x1800735cd  mov     edx, ebx
0x1800735cf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800735d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800735dc  lea     rax, WPP_GLOBAL_Control
0x1800735e3  cmp     rcx, rax
0x1800735e6  jz      short loc_18007360C
0x1800735e8  test    byte ptr [rcx+1Ch], 1
0x1800735ec  jz      short loc_18007360C
0x1800735ee  cmp     byte ptr [rcx+19h], 2
0x1800735f2  jb      short loc_18007360C
0x1800735f4  mov     rcx, [rcx+10h]
0x1800735f8  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800735ff  mov     edx, 1Fh
0x180073604  mov     r9d, ebx
0x180073607  call    WPP_SF_d
0x18007360c  mov     eax, ebx
0x18007360e  jmp     short loc_180073659
0x180073610  movzx   ebx, [rbp+57h+arg_18]
0x180073614  lea     rsi, [rdi+0A8h]
0x18007361b  mov     rcx, [rsi]
0x18007361e  lea     rdi, [r14+0A8h]
0x180073625  mov     edx, ebx
0x180073627  xor     r8d, r8d
0x18007362a  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x18007362f  mov     rcx, [rdi]
0x180073632  xor     r8d, r8d
0x180073635  mov     edx, ebx
0x180073637  test    eax, eax
0x180073639  jz      short loc_18007366D
0x18007363b  lea     r9d, [r8+1]
0x18007363f  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x180073644  mov     rcx, [rdi]
0x180073647  mov     r9d, 1
0x18007364d  mov     r8d, r9d
0x180073650  mov     edx, ebx
0x180073652  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x180073657  xor     eax, eax
0x180073659  add     rsp, 0B8h
0x180073660  pop     r15
0x180073662  pop     r14
0x180073664  pop     r13
0x180073666  pop     r12
0x180073668  pop     rdi
0x180073669  pop     rsi
0x18007366a  pop     rbx
0x18007366b  pop     rbp
0x18007366c  retn
0x18007366d  xor     r9d, r9d
0x180073670  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x180073675  mov     r9, [rbp+57h+var_B0]
0x180073679  lea     rax, ??_7CDataTablePtr@@6B@; const CDataTablePtr::`vftable'
0x180073680  mov     edx, [rbp+57h+var_BC]
0x180073683  lea     r8, [rbp+57h+var_78]
0x180073687  lea     rcx, [rbp+57h+var_60]
0x18007368b  mov     [rbp+57h+var_60], rax
0x18007368f  mov     [rbp+57h+var_78], rax
0x180073693  mov     [rbp+57h+var_58], rsi
0x180073697  mov     [rbp+57h+var_50], r13d
0x18007369b  mov     [rbp+57h+var_70], rdi
0x18007369f  mov     [rbp+57h+var_68], r13d
0x1800736a3  mov     [rsp+0F0h+var_D0], r15
0x1800736a8  call    ?CopyTo@CUntypedValue@@SAHPEAVCPtrSource@@VCType@@0PEAVCFastHeap@@2@Z; CUntypedValue::CopyTo(CPtrSource *,CType,CPtrSource *,CFastHeap *,CFastHeap *)
0x1800736ad  test    eax, eax
0x1800736af  jnz     short loc_180073644
0x1800736b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800736b7  mov     rcx, rax
0x1800736ba  mov     edx, 80041006h
0x1800736bf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800736c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736cc  lea     rax, WPP_GLOBAL_Control
0x1800736d3  cmp     rcx, rax
0x1800736d6  jz      short loc_1800736FF
0x1800736d8  test    byte ptr [rcx+1Ch], 1
0x1800736dc  jz      short loc_1800736FF
0x1800736de  cmp     byte ptr [rcx+19h], 2
0x1800736e2  jb      short loc_1800736FF
0x1800736e4  mov     edx, 20h ; ' '
0x1800736e9  mov     rcx, [rcx+10h]
0x1800736ed  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800736f4  mov     r9d, 80041006h
0x1800736fa  call    WPP_SF_d
0x1800736ff  mov     eax, 80041006h
0x180073704  jmp     loc_180073659
```
