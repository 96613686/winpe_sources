# CClfsMarshallingContext::ReadLogRecord(_CLS_LSN const &,_CLFS_CONTEXT_MODE,_CLFS_RECORD_HEADER * &,void * &,_OVERLAPPED *)

- ea: `0x18001195c`
- end: `0x180011cf6`
- name: `?ReadLogRecord@CClfsMarshallingContext@@QEAAKAEBT_CLS_LSN@@W4_CLFS_CONTEXT_MODE@@AEAPEAU_CLFS_RECORD_HEADER@@AEAPEAXPEAU_OVERLAPPED@@@Z`
- size: `922`
- prototype: `unsigned int __usercall@<eax>(CClfsMarshallingContext *__hidden this@<rcx>, const union _CLS_LSN *@<rdx>, enum _CLFS_CONTEXT_MODE@<r8d>, struct _CLFS_RECORD_HEADER **@<r9>, void **, struct _OVERLAPPED *)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000aec0`
- `0x18000c4e0`
- `0x1800136a0`
- `0x180014008`

## callees

- `0x180008ca0`
- `0x18000e534`
- `0x18000f60c`
- `0x1800101c8`
- `0x18001067c`
- `0x18001195c`
- `0x180011cfc`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::ReadLogRecord(
        CClfsMarshallingContext *this,
        const union _CLS_LSN *a2,
        enum _CLFS_CONTEXT_MODE a3,
        struct _CLFS_RECORD_HEADER **a4,
        void **a5,
        struct _OVERLAPPED *a6)
{
  CLFS_RECORD_INDEX v9; // r9d
  CLFS_RECORD_INDEX v10; // edx
  CLFS_RECORD_INDEX v11; // eax
  __int64 v12; // rdx
  CLogIocb *v13; // rbx
  unsigned __int64 v14; // r12
  __int64 v15; // r8
  unsigned int i; // edx
  signed __int32 v17; // r9d
  signed __int32 v18; // eax
  unsigned int LogRecordInternal; // edi
  __int16 v20; // ax
  __int16 v21; // ax
  __int64 v22; // r8
  unsigned int k; // edx
  signed __int32 v24; // r9d
  signed __int32 v25; // eax
  __int64 v26; // r8
  unsigned int j; // edx
  signed __int32 v28; // r9d
  signed __int32 v29; // eax
  struct _OVERLAPPED *v30; // r9
  unsigned __int8 *v31; // r11
  unsigned int v33[5]; // [rsp+54h] [rbp-54h] BYREF
  CLogIocb *v34; // [rsp+68h] [rbp-40h] BYREF
  union _CLS_LSN v35; // [rsp+70h] [rbp-38h] BYREF
  unsigned __int8 v36; // [rsp+B8h] [rbp+10h] BYREF
  struct _CLFS_RECORD_HEADER **v37; // [rsp+C8h] [rbp+20h]

  v37 = a4;
  v35 = CLFS_LSN_INVALID;
  v34 = 0;
  v33[0] = 0;
  v36 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = -1;
  v10 = -1;
  if ( a2 )
    v10 = a2->offset.idxRecord & 0xFFFFFE00;
  v11 = -1;
  if ( a2 )
    v11 = a2->offset.idxRecord & 0x1FF;
  if ( *((_QWORD *)this + 21) < (v10 | (unsigned __int64)v11) )
    return 87;
  if ( a2 )
    v9 = a2->offset.idxRecord & 0xFFFFFE00;
  v12 = v9 % *((_DWORD *)this + 34);
  if ( (_DWORD)v12 || (unsigned int)(a3 - 1) > 2 )
    return 87;
  if ( (unsigned int)CClfsMarshallingContext::AllocateIocb(this, (unsigned int)v12, &v34) )
    return 6605;
  v13 = v34;
  if ( !v34 )
    return 6605;
  v14 = 0;
  *((_DWORD *)v34 + 32) = a3;
  *((union _CLS_LSN *)v13 + 18) = *a2;
  *((union _CLS_LSN *)v13 + 20) = *a2;
  *((_WORD *)v13 + 14) |= 4u;
  *((CLFS_LSN *)v13 + 17) = CLFS_LSN_INVALID;
  v15 = *((_QWORD *)v13 + 8) + *(unsigned int *)(*((_QWORD *)v13 + 24) + 128LL);
  for ( i = 0; ; ++i )
  {
    v33[3] = i;
    v17 = *(_DWORD *)(v15 - 16);
    v18 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 - 16), v17 | 0x80, v17);
    if ( (v18 & 0x80) != 0 || v18 == v17 || i > 5 )
      break;
  }
  LogRecordInternal = CClfsMarshallingContext::ReadMarshalledLogRecord(this, v13, v33, &v36);
  if ( LogRecordInternal )
  {
    if ( LogRecordInternal != 1168 )
    {
      v26 = *((_QWORD *)v13 + 8) + *(unsigned int *)(*((_QWORD *)v13 + 24) + 128LL);
      for ( j = 0; ; ++j )
      {
        v33[2] = j;
        v28 = *(_DWORD *)(v26 - 16);
        v29 = _InterlockedCompareExchange((volatile signed __int32 *)(v26 - 16), v28 & 0xFFFFFF7F, v28);
        if ( (v29 & 0x80u) == 0 || v29 == v28 || j > 5 )
          break;
      }
    }
  }
  else
  {
    *((_WORD *)v13 + 14) |= 0x100u;
    v20 = *((_WORD *)v13 + 14);
    if ( v36 )
      v21 = v20 & 0xFDFF;
    else
      v21 = v20 | 0x200;
    *((_WORD *)v13 + 14) = v21;
    v22 = *((_QWORD *)v13 + 8) + *(unsigned int *)(*((_QWORD *)v13 + 24) + 128LL);
    for ( k = 0; ; ++k )
    {
      v33[1] = k;
      v24 = *(_DWORD *)(v22 - 16);
      v25 = _InterlockedCompareExchange((volatile signed __int32 *)(v22 - 16), v24 & 0xFFFFFF7F, v24);
      if ( (v25 & 0x80u) == 0 || v25 == v24 || k > 5 )
        break;
    }
  }
  if ( LogRecordInternal == 1168 )
  {
    v30 = a6;
    if ( !a6 )
      v14 = *((_QWORD *)v13 + 7);
    *((_WORD *)v13 + 14) |= 0x100u;
    *((_QWORD *)v13 + 21) = *((_QWORD *)v13 + 20);
    LogRecordInternal = NtReadLogRecordInternal(
                          *((void **)this + 6),
                          (union _CLS_LSN *)v13 + 20,
                          (unsigned int)(a3 == ClfsContextForward) + 1,
                          *((char **)v13 + 8),
                          *((_DWORD *)this + 32),
                          (unsigned int *)v13 + 18,
                          v14,
                          (*((_DWORD *)this + 39) & 0x20) == 0,
                          v30);
  }
  if ( !LogRecordInternal )
  {
    *((_QWORD *)v13 + 14) = *((_QWORD *)v13 + 8);
    *((_QWORD *)v13 + 13) = CLogIocb::GetFirstRecord(v13);
    *((CLFS_LSN *)v13 + 21) = CLFS_LSN_INVALID;
    *((_WORD *)v13 + 14) &= ~0x100u;
    LogRecordInternal = ClfsFindLsnInBlock(a2, v31, (struct _CLFS_RECORD_HEADER **)v13 + 13, &v35);
    if ( a2 && v35.ullOffset == a2->ullOffset )
      *v37 = (struct _CLFS_RECORD_HEADER *)*((_QWORD *)v13 + 13);
    else
      LogRecordInternal = 1168;
  }
  if ( LogRecordInternal == 997 )
  {
    *((_WORD *)v13 + 14) |= 0x80u;
  }
  else if ( LogRecordInternal )
  {
    CClfsMarshallingContext::FreeIocb(this, v13);
    v13 = 0;
  }
  *a5 = v13;
  return LogRecordInternal;
}

```

## disassembly

```asm
0x18001195c  mov     r11, rsp
0x18001195f  mov     [r11+18h], rbx
0x180011963  mov     [r11+20h], r9
0x180011967  mov     [r11+8], rcx
0x18001196b  push    rsi
0x18001196c  push    rdi
0x18001196d  push    r12
0x18001196f  push    r13
0x180011971  push    r15
0x180011973  sub     rsp, 80h
0x18001197a  mov     r13d, r8d
0x18001197d  mov     rsi, rdx
0x180011980  mov     r15, rcx
0x180011983  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001198a  mov     [r11-38h], rax
0x18001198e  mov     qword ptr [r11-40h], 0
0x180011996  mov     [rsp+0A8h+var_54], 0
0x18001199e  mov     byte ptr [r11+10h], 0
0x1800119a3  mov     qword ptr [r9], 0
0x1800119aa  mov     rax, [rsp+0A8h+arg_20]
0x1800119b2  mov     qword ptr [rax], 0
0x1800119b9  or      r9d, 0FFFFFFFFh
0x1800119bd  mov     edx, r9d
0x1800119c0  test    rsi, rsi
0x1800119c3  jz      short loc_1800119CD
0x1800119c5  mov     edx, [rsi]
0x1800119c7  and     edx, 0FFFFFE00h
0x1800119cd  mov     eax, r9d
0x1800119d0  test    rsi, rsi
0x1800119d3  jz      short loc_1800119DC
0x1800119d5  mov     eax, [rsi]
0x1800119d7  and     eax, 1FFh
0x1800119dc  mov     ecx, eax
0x1800119de  mov     eax, edx
0x1800119e0  or      rcx, rax
0x1800119e3  cmp     [r15+0A8h], rcx
0x1800119ea  jb      loc_180011CD8
0x1800119f0  test    rsi, rsi
0x1800119f3  jz      short loc_1800119FF
0x1800119f5  mov     r9d, [rsi]
0x1800119f8  and     r9d, 0FFFFFE00h
0x1800119ff  xor     edx, edx
0x180011a01  mov     eax, r9d
0x180011a04  div     dword ptr [r15+88h]
0x180011a0b  test    edx, edx
0x180011a0d  jnz     loc_180011CD8
0x180011a13  lea     eax, [r8-1]
0x180011a17  cmp     eax, 2
0x180011a1a  ja      loc_180011CD8
0x180011a20  lea     r8, [rsp+0A8h+var_40]
0x180011a25  mov     rcx, r15
0x180011a28  call    ?AllocateIocb@CClfsMarshallingContext@@AEAAKW4_LOGIOCB_TYPE@1@AEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocb(CClfsMarshallingContext::_LOGIOCB_TYPE,CLogIocb * &)
0x180011a2d  mov     [rsp+0A8h+var_58], eax
0x180011a31  test    eax, eax
0x180011a33  jnz     loc_180011CD1
0x180011a39  mov     rbx, [rsp+0A8h+var_40]
0x180011a3e  test    rbx, rbx
0x180011a41  jz      loc_180011CD1
0x180011a47  xor     r12d, r12d
0x180011a4a  mov     [rbx+80h], r13d
0x180011a51  mov     rax, [rsi]
0x180011a54  mov     [rbx+90h], rax
0x180011a5b  mov     rax, [rsi]
0x180011a5e  mov     [rbx+0A0h], rax
0x180011a65  or      word ptr [rbx+1Ch], 4
0x180011a6a  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180011a71  mov     [rbx+88h], rax
0x180011a78  mov     rax, [rbx+0C0h]
0x180011a7f  mov     r8d, [rax+80h]
0x180011a86  add     r8, [rbx+40h]
0x180011a8a  xor     edx, edx
0x180011a8c  mov     r10d, 80h
0x180011a92  mov     [rsp+0A8h+var_48], edx
0x180011a96  mov     r9d, [r8-10h]
0x180011a9a  mov     ecx, r9d
0x180011a9d  or      ecx, r10d
0x180011aa0  mov     eax, r9d
0x180011aa3  lock cmpxchg [r8-10h], ecx
0x180011aa9  test    r10b, al
0x180011aac  jnz     short loc_180011AC0
0x180011aae  cmp     eax, r9d
0x180011ab1  jnz     short loc_180011AB7
0x180011ab3  xor     eax, eax
0x180011ab5  jmp     short loc_180011AC5
0x180011ab7  cmp     edx, 5
0x180011aba  jbe     loc_180011CCA
0x180011ac0  mov     eax, 0AAh
0x180011ac5  mov     [rsp+0A8h+var_58], eax
0x180011ac9  lea     r9, [rsp+0A8h+arg_8]; unsigned __int8 *
0x180011ad1  lea     r8, [rsp+0A8h+var_54]; unsigned int *
0x180011ad6  mov     rdx, rbx; struct CLogIocb *
0x180011ad9  mov     rcx, r15; this
0x180011adc  call    ?ReadMarshalledLogRecord@CClfsMarshallingContext@@AEAAKAEAVCLogIocb@@AEAKAEAE@Z; CClfsMarshallingContext::ReadMarshalledLogRecord(CLogIocb &,ulong &,uchar &)
0x180011ae1  mov     edi, eax
0x180011ae3  mov     [rsp+0A8h+var_58], eax
0x180011ae7  test    eax, eax
0x180011ae9  jnz     short loc_180011B58
0x180011aeb  mov     r10d, 100h
0x180011af1  or      [rbx+1Ch], r10w
0x180011af6  movzx   eax, word ptr [rbx+1Ch]
0x180011afa  cmp     [rsp+0A8h+arg_8], dil
0x180011b02  jz      short loc_180011B0E
0x180011b04  mov     ecx, 0FDFFh
0x180011b09  and     ax, cx
0x180011b0c  jmp     short loc_180011B16
0x180011b0e  mov     ecx, 200h
0x180011b13  or      ax, cx
0x180011b16  mov     [rbx+1Ch], ax
0x180011b1a  mov     rax, [rbx+0C0h]
0x180011b21  mov     r8d, [rax+80h]
0x180011b28  add     r8, [rbx+40h]
0x180011b2c  xor     edx, edx
0x180011b2e  mov     [rsp+0A8h+var_50], edx
0x180011b32  mov     r9d, [r8-10h]
0x180011b36  mov     ecx, r9d
0x180011b39  btr     ecx, 7
0x180011b3d  mov     eax, r9d
0x180011b40  lock cmpxchg [r8-10h], ecx
0x180011b46  test    al, al
0x180011b48  jns     short loc_180011BA4
0x180011b4a  cmp     eax, r9d
0x180011b4d  jz      short loc_180011BA4
0x180011b4f  cmp     edx, 5
0x180011b52  ja      short loc_180011BA4
0x180011b54  inc     edx
0x180011b56  jmp     short loc_180011B2E
0x180011b58  cmp     edi, 490h
0x180011b5e  jz      short loc_180011B9E
0x180011b60  mov     rax, [rbx+0C0h]
0x180011b67  mov     r8d, [rax+80h]
0x180011b6e  add     r8, [rbx+40h]
0x180011b72  xor     edx, edx
0x180011b74  mov     [rsp+0A8h+var_4C], edx
0x180011b78  mov     r9d, [r8-10h]
0x180011b7c  mov     ecx, r9d
0x180011b7f  btr     ecx, 7
0x180011b83  mov     eax, r9d
0x180011b86  lock cmpxchg [r8-10h], ecx
0x180011b8c  test    al, al
0x180011b8e  jns     short loc_180011B9E
0x180011b90  cmp     eax, r9d
0x180011b93  jz      short loc_180011B9E
0x180011b95  cmp     edx, 5
0x180011b98  ja      short loc_180011B9E
0x180011b9a  inc     edx
0x180011b9c  jmp     short loc_180011B74
0x180011b9e  mov     r10d, 100h
0x180011ba4  cmp     edi, 490h
0x180011baa  jnz     short loc_180011C25
0x180011bac  mov     r9, [rsp+0A8h+arg_28]
0x180011bb4  test    r9, r9
0x180011bb7  jnz     short loc_180011BBD
0x180011bb9  mov     r12, [rbx+38h]
0x180011bbd  or      [rbx+1Ch], r10w
0x180011bc2  lea     rdx, [rbx+0A0h]; union _CLS_LSN *
0x180011bc9  mov     rax, [rdx]
0x180011bcc  mov     [rbx+0A8h], rax
0x180011bd3  mov     ecx, [r15+9Ch]
0x180011bda  shr     ecx, 5
0x180011bdd  not     cl
0x180011bdf  and     cl, 1
0x180011be2  lea     rax, [rbx+48h]
0x180011be6  xor     r8d, r8d
0x180011be9  cmp     r13d, 3
0x180011bed  setz    r8b
0x180011bf1  inc     r8d; unsigned int
0x180011bf4  mov     [rsp+0A8h+var_68], r9; struct _OVERLAPPED *
0x180011bf9  mov     [rsp+0A8h+var_70], cl; unsigned __int8
0x180011bfd  mov     [rsp+0A8h+var_78], r12; void *
0x180011c02  mov     [rsp+0A8h+var_80], rax; unsigned int *
0x180011c07  mov     eax, [r15+80h]
0x180011c0e  mov     [rsp+0A8h+var_88], eax; unsigned int
0x180011c12  mov     r9, [rbx+40h]; void *
0x180011c16  mov     rcx, [r15+30h]; void *
0x180011c1a  call    ?NtReadLogRecordInternal@@YAKPEAXPEAT_CLS_LSN@@K0KPEAK0EPEAU_OVERLAPPED@@@Z; NtReadLogRecordInternal(void *,_CLS_LSN *,ulong,void *,ulong,ulong *,void *,uchar,_OVERLAPPED *)
0x180011c1f  mov     edi, eax
0x180011c21  mov     [rsp+0A8h+var_58], eax
0x180011c25  test    edi, edi
0x180011c27  jnz     short loc_180011C97
0x180011c29  mov     r11, [rbx+40h]
0x180011c2d  mov     [rbx+70h], r11
0x180011c31  mov     rcx, rbx; this
0x180011c34  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x180011c39  mov     [rbx+68h], rax
0x180011c3d  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180011c44  mov     [rbx+0A8h], rax
0x180011c4b  mov     eax, 0FEFFh
0x180011c50  and     [rbx+1Ch], ax
0x180011c54  lea     r9, [rsp+0A8h+var_38]; union _CLS_LSN *
0x180011c59  lea     r8, [rbx+68h]; struct _CLFS_RECORD_HEADER **
0x180011c5d  mov     rdx, r11; unsigned __int8 *
0x180011c60  mov     rcx, rsi; union _CLS_LSN *
0x180011c63  call    ?ClfsFindLsnInBlock@@YAKAEBT_CLS_LSN@@PEAEAEAPEAU_CLFS_RECORD_HEADER@@AEAT1@@Z; ClfsFindLsnInBlock(_CLS_LSN const &,uchar *,_CLFS_RECORD_HEADER * &,_CLS_LSN &)
0x180011c68  mov     edi, eax
0x180011c6a  mov     [rsp+0A8h+var_58], eax
0x180011c6e  test    rsi, rsi
0x180011c71  jz      short loc_180011C8E
0x180011c73  mov     rax, qword ptr [rsp+0A8h+var_38]
0x180011c78  cmp     rax, [rsi]
0x180011c7b  jnz     short loc_180011C8E
0x180011c7d  mov     rax, [rbx+68h]
0x180011c81  mov     rcx, [rsp+0A8h+arg_18]
0x180011c89  mov     [rcx], rax
0x180011c8c  jmp     short loc_180011C97
0x180011c8e  mov     edi, 490h
0x180011c93  mov     [rsp+0A8h+var_58], edi
0x180011c97  cmp     edi, 3E5h
0x180011c9d  jnz     short loc_180011CAA
0x180011c9f  mov     eax, 80h
0x180011ca4  or      [rbx+1Ch], ax
0x180011ca8  jmp     short loc_180011CBB
0x180011caa  test    edi, edi
0x180011cac  jz      short loc_180011CBB
0x180011cae  mov     rdx, rbx; struct CLogIocb *
0x180011cb1  mov     rcx, r15; this
0x180011cb4  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x180011cb9  xor     ebx, ebx
0x180011cbb  mov     rax, [rsp+0A8h+arg_20]
0x180011cc3  mov     [rax], rbx
0x180011cc6  mov     eax, edi
0x180011cc8  jmp     short loc_180011CDD
0x180011cca  inc     edx
0x180011ccc  jmp     loc_180011A92
0x180011cd1  mov     eax, 19CDh
0x180011cd6  jmp     short loc_180011CDD
0x180011cd8  mov     eax, 57h ; 'W'
0x180011cdd  mov     rbx, [rsp+0A8h+arg_10]
0x180011ce5  add     rsp, 80h
0x180011cec  pop     r15
0x180011cee  pop     r13
0x180011cf0  pop     r12
0x180011cf2  pop     rdi
0x180011cf3  pop     rsi
0x180011cf4  retn
0x1800159bb  push    rbp
0x1800159bd  sub     rsp, 50h
0x1800159c1  mov     rbp, rdx
0x1800159c4  mov     eax, [rbp+50h]
0x1800159c7  cmp     eax, 3E5h
0x1800159cc  jnz     short loc_1800159DD
0x1800159ce  mov     ecx, 80h
0x1800159d3  mov     rax, [rbp+68h]
0x1800159d7  or      [rax+1Ch], cx
0x1800159db  jmp     short loc_1800159F9
0x1800159dd  test    eax, eax
0x1800159df  jz      short loc_1800159F9
0x1800159e1  mov     rdx, [rbp+68h]; struct CLogIocb *
0x1800159e5  mov     rcx, [rbp+0B0h]; this
0x1800159ec  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x1800159f1  mov     qword ptr [rbp+68h], 0
0x1800159f9  mov     rcx, [rbp+0D0h]
0x180015a00  mov     rax, [rbp+68h]
0x180015a04  mov     [rcx], rax
0x180015a07  add     rsp, 50h
0x180015a0b  pop     rbp
0x180015a0c  retn
```
