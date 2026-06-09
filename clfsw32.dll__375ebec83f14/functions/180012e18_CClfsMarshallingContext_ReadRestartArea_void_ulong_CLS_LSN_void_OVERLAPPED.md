# CClfsMarshallingContext::ReadRestartArea(void * &,ulong &,_CLS_LSN &,void * &,_OVERLAPPED *)

- ea: `0x180012e18`
- end: `0x180013051`
- name: `?ReadRestartArea@CClfsMarshallingContext@@QEAAKAEAPEAXAEAKAEAT_CLS_LSN@@0PEAU_OVERLAPPED@@@Z`
- size: `569`
- prototype: `unsigned int __usercall@<eax>(CClfsMarshallingContext *__hidden this@<rcx>, void **@<rdx>, unsigned int *@<r8>, union _CLS_LSN *@<r9>, void **, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c640`
- `0x180013cc0`

## callees

- `0x180008eb0`
- `0x18000e534`
- `0x1800101c8`
- `0x18001067c`
- `0x1800106f8`
- `0x180012e18`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::ReadRestartArea(
        CClfsMarshallingContext *this,
        void **a2,
        unsigned int *a3,
        union _CLS_LSN *a4,
        void **a5,
        struct _OVERLAPPED *a6)
{
  __int64 result; // rax
  unsigned __int64 v11; // r10
  CLogIocb *v12; // rbx
  __int64 v13; // r8
  unsigned int i; // edx
  signed __int32 v15; // r9d
  signed __int32 v16; // eax
  unsigned int LogRestartAreaInternal; // eax
  unsigned int LastRecord; // edi
  struct _CLFS_RECORD_HEADER *v19; // rdx
  CLogIocb *v20; // [rsp+88h] [rbp+10h] BYREF
  struct _CLFS_RECORD_HEADER *v21; // [rsp+90h] [rbp+18h] BYREF

  v20 = 0;
  v21 = 0;
  *a3 = 0;
  *a2 = 0;
  *a4 = CLFS_LSN_INVALID;
  result = CClfsMarshallingContext::AllocateIocb(this, 0, &v20);
  if ( (_DWORD)result )
    return result;
  v11 = 0;
  v12 = v20;
  if ( !v20 )
    return result;
  *((_DWORD *)v20 + 32) = 2;
  *((union _CLS_LSN *)v12 + 18) = *a4;
  *((_WORD *)v12 + 14) |= 0x110u;
  v13 = *((_QWORD *)v12 + 8) + *(unsigned int *)(*((_QWORD *)v12 + 24) + 128LL);
  for ( i = 0; ; ++i )
  {
    v15 = *(_DWORD *)(v13 - 16);
    v16 = _InterlockedCompareExchange((volatile signed __int32 *)(v13 - 16), v15 | 0x80, v15);
    if ( (v16 & 0x80) != 0 || v16 == v15 || i > 5 )
      break;
  }
  if ( !a6 )
    v11 = *((_QWORD *)v12 + 7);
  LogRestartAreaInternal = NtReadLogRestartAreaInternal(
                             *((void **)this + 6),
                             (union _CLS_LSN *)v12 + 18,
                             *((char **)v12 + 8),
                             *((_DWORD *)this + 32),
                             (unsigned int *)v12 + 18,
                             v11,
                             (*((_DWORD *)this + 39) & 0x20) == 0,
                             a6);
  LastRecord = LogRestartAreaInternal;
  switch ( LogRestartAreaInternal )
  {
    case 0u:
      LastRecord = CLogIocb::GetLastRecord(v12, &v21);
      v19 = v21;
      if ( v21 )
      {
        if ( (*((_BYTE *)v21 + 36) & 2) != 0 )
        {
          *((_QWORD *)v12 + 13) = v21;
          *((_QWORD *)v12 + 20) = *(_QWORD *)(*((_QWORD *)v12 + 8) + 32LL);
          *a4 = *(union _CLS_LSN *)v19;
          *a2 = (char *)v19 + *((unsigned __int16 *)v19 + 17);
          *a3 = *((_DWORD *)v19 + 6) - *((unsigned __int16 *)v19 + 17);
          *((_WORD *)v12 + 14) &= ~0x100u;
          *((_QWORD *)v12 + 14) = *((_QWORD *)v12 + 8);
          if ( v19 )
            *((_QWORD *)v12 + 13) = v19;
          else
            *((_QWORD *)v12 + 13) = CLogIocb::GetFirstRecord(v12);
        }
        else
        {
          LastRecord = 6607;
        }
        break;
      }
LABEL_12:
      LastRecord = 6611;
      break;
    case 0x3E5u:
      *((_WORD *)v12 + 14) |= 0x80u;
      break;
    case 0x19D3u:
      goto LABEL_12;
  }
  if ( LastRecord )
  {
    if ( LastRecord != 997 )
    {
      CClfsMarshallingContext::FreeIocb(this, v12);
      v12 = 0;
    }
  }
  *a5 = v12;
  return LastRecord;
}

```

## disassembly

```asm
0x180012e18  mov     r11, rsp
0x180012e1b  mov     [r11+20h], rbx
0x180012e1f  mov     [r11+8], rcx
0x180012e23  push    rsi
0x180012e24  push    rdi
0x180012e25  push    r12
0x180012e27  push    r14
0x180012e29  push    r15
0x180012e2b  sub     rsp, 50h
0x180012e2f  mov     r14, r9
0x180012e32  mov     r15, r8
0x180012e35  mov     r12, rdx
0x180012e38  mov     rsi, rcx
0x180012e3b  mov     qword ptr [r11+10h], 0
0x180012e43  mov     qword ptr [r11+18h], 0
0x180012e4b  mov     dword ptr [r8], 0
0x180012e52  mov     qword ptr [rdx], 0
0x180012e59  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180012e60  mov     [r9], rax
0x180012e63  lea     r8, [r11+10h]
0x180012e67  xor     edx, edx
0x180012e69  call    ?AllocateIocb@CClfsMarshallingContext@@AEAAKW4_LOGIOCB_TYPE@1@AEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocb(CClfsMarshallingContext::_LOGIOCB_TYPE,CLogIocb * &)
0x180012e6e  mov     [rsp+78h+var_38], eax
0x180012e72  test    eax, eax
0x180012e74  jnz     loc_180013033
0x180012e7a  xor     r10d, r10d
0x180012e7d  mov     rbx, [rsp+78h+arg_8]
0x180012e85  test    rbx, rbx
0x180012e88  jz      loc_180013033
0x180012e8e  mov     dword ptr [rbx+80h], 2
0x180012e98  mov     rax, [r14]
0x180012e9b  mov     [rbx+90h], rax
0x180012ea2  mov     eax, 110h
0x180012ea7  or      [rbx+1Ch], ax
0x180012eab  mov     rax, [rbx+0C0h]
0x180012eb2  mov     r8d, [rax+80h]
0x180012eb9  add     r8, [rbx+40h]
0x180012ebd  xor     edx, edx
0x180012ebf  mov     r11d, 80h
0x180012ec5  mov     [rsp+78h+var_34], edx
0x180012ec9  mov     r9d, [r8-10h]
0x180012ecd  mov     ecx, r9d
0x180012ed0  or      ecx, r11d
0x180012ed3  mov     eax, r9d
0x180012ed6  lock cmpxchg [r8-10h], ecx
0x180012edc  test    r11b, al
0x180012edf  jnz     short loc_180012EF3
0x180012ee1  cmp     eax, r9d
0x180012ee4  jnz     short loc_180012EEA
0x180012ee6  xor     eax, eax
0x180012ee8  jmp     short loc_180012EF8
0x180012eea  cmp     edx, 5
0x180012eed  jbe     loc_180013049
0x180012ef3  mov     eax, 0AAh
0x180012ef8  mov     [rsp+78h+var_38], eax
0x180012efc  mov     r8, [rsp+78h+arg_28]
0x180012f04  test    r8, r8
0x180012f07  jnz     short loc_180012F0D
0x180012f09  mov     r10, [rbx+38h]
0x180012f0d  mov     ecx, [rsi+9Ch]
0x180012f13  shr     ecx, 5
0x180012f16  not     cl
0x180012f18  and     cl, 1
0x180012f1b  lea     rax, [rbx+48h]
0x180012f1f  lea     rdx, [rbx+90h]; union _CLS_LSN *
0x180012f26  mov     [rsp+78h+var_40], r8; struct _OVERLAPPED *
0x180012f2b  mov     [rsp+78h+var_48], cl; unsigned __int8
0x180012f2f  mov     [rsp+78h+var_50], r10; void *
0x180012f34  mov     [rsp+78h+var_58], rax; unsigned int *
0x180012f39  mov     r9d, [rsi+80h]; unsigned int
0x180012f40  mov     r8, [rbx+40h]; void *
0x180012f44  mov     rcx, [rsi+30h]; void *
0x180012f48  call    ?NtReadLogRestartAreaInternal@@YAKPEAXPEAT_CLS_LSN@@0KPEAK0EPEAU_OVERLAPPED@@@Z; NtReadLogRestartAreaInternal(void *,_CLS_LSN *,void *,ulong,ulong *,void *,uchar,_OVERLAPPED *)
0x180012f4d  mov     edi, eax
0x180012f4f  mov     [rsp+78h+var_38], eax
0x180012f53  test    eax, eax
0x180012f55  jz      short loc_180012F85
0x180012f57  cmp     eax, 3E5h
0x180012f5c  jz      short loc_180012F77
0x180012f5e  cmp     eax, 19D3h
0x180012f63  jnz     loc_18001300D
0x180012f69  mov     edi, 19D3h
0x180012f6e  mov     [rsp+78h+var_38], edi
0x180012f72  jmp     loc_18001300D
0x180012f77  mov     eax, 80h
0x180012f7c  or      [rbx+1Ch], ax
0x180012f80  jmp     loc_18001300D
0x180012f85  lea     rdx, [rsp+78h+arg_10]; struct _CLFS_RECORD_HEADER **
0x180012f8d  mov     rcx, rbx; this
0x180012f90  call    ?GetLastRecord@CLogIocb@@QEAAKAEAPEAU_CLFS_RECORD_HEADER@@@Z; CLogIocb::GetLastRecord(_CLFS_RECORD_HEADER * &)
0x180012f95  mov     edi, eax
0x180012f97  mov     [rsp+78h+var_38], eax
0x180012f9b  mov     rdx, [rsp+78h+arg_10]
0x180012fa3  test    rdx, rdx
0x180012fa6  jz      short loc_180012F69
0x180012fa8  test    byte ptr [rdx+24h], 2
0x180012fac  jnz     short loc_180012FB5
0x180012fae  mov     edi, 19CFh
0x180012fb3  jmp     short loc_180012F6E
0x180012fb5  mov     [rbx+68h], rdx
0x180012fb9  mov     rax, [rbx+40h]
0x180012fbd  mov     rcx, [rax+20h]
0x180012fc1  mov     [rbx+0A0h], rcx
0x180012fc8  mov     rax, [rdx]
0x180012fcb  mov     [r14], rax
0x180012fce  movzx   eax, word ptr [rdx+22h]
0x180012fd2  add     rax, rdx
0x180012fd5  mov     [r12], rax
0x180012fd9  movzx   eax, word ptr [rdx+22h]
0x180012fdd  mov     ecx, [rdx+18h]
0x180012fe0  sub     ecx, eax
0x180012fe2  mov     [r15], ecx
0x180012fe5  mov     eax, 0FEFFh
0x180012fea  and     [rbx+1Ch], ax
0x180012fee  mov     rax, [rbx+40h]
0x180012ff2  mov     [rbx+70h], rax
0x180012ff6  test    rdx, rdx
0x180012ff9  jnz     short loc_180013009
0x180012ffb  mov     rcx, rbx; this
0x180012ffe  call    ?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ; CLogIocb::GetFirstRecord(void)
0x180013003  mov     [rbx+68h], rax
0x180013007  jmp     short loc_18001300D
0x180013009  mov     [rbx+68h], rdx
0x18001300d  test    edi, edi
0x18001300f  jz      short loc_180013026
0x180013011  cmp     edi, 3E5h
0x180013017  jz      short loc_180013026
0x180013019  mov     rdx, rbx; struct CLogIocb *
0x18001301c  mov     rcx, rsi; this
0x18001301f  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x180013024  xor     ebx, ebx
0x180013026  mov     rax, [rsp+78h+arg_20]
0x18001302e  mov     [rax], rbx
0x180013031  mov     eax, edi
0x180013033  mov     rbx, [rsp+78h+arg_18]
0x18001303b  add     rsp, 50h
0x18001303f  pop     r15
0x180013041  pop     r14
0x180013043  pop     r12
0x180013045  pop     rdi
0x180013046  pop     rsi
0x180013047  retn
0x180013049  inc     edx
0x18001304b  jmp     loc_180012EC5
0x180015ab8  push    rbp
0x180015aba  sub     rsp, 40h
0x180015abe  mov     rbp, rdx
0x180015ac1  mov     eax, [rbp+40h]
0x180015ac4  test    eax, eax
0x180015ac6  jz      short loc_180015AED
0x180015ac8  cmp     eax, 3E5h
0x180015acd  jz      short loc_180015AED
0x180015acf  mov     rdx, [rbp+88h]; struct CLogIocb *
0x180015ad6  mov     rcx, [rbp+80h]; this
0x180015add  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x180015ae2  mov     qword ptr [rbp+88h], 0
0x180015aed  mov     rcx, [rbp+0A0h]
0x180015af4  mov     rax, [rbp+88h]
0x180015afb  mov     [rcx], rax
0x180015afe  add     rsp, 40h
0x180015b02  pop     rbp
0x180015b03  retn
```
