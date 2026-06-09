# CReadMap::ReadRecord(ulong,ulong,ulong *,_LOGRECHEADER * *,_LOGREC *,int,ulong *)

- ea: `0x18000cec8`
- end: `0x18000d159`
- name: `?ReadRecord@CReadMap@@QEAAHKKPEAKPEAPEAU_LOGRECHEADER@@PEAU_LOGREC@@H0@Z`
- size: `657`
- prototype: `__int64 __fastcall(CLogStorage **this, __int64, unsigned int, unsigned int *, struct _LOGRECHEADER **, struct _LOGREC *, int, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180002bf0`
- `0x180002ea0`
- `0x180007d7c`

## callees

- `0x180005a7c`
- `0x180005b64`
- `0x180005c04`
- `0x18000aa50`
- `0x18000b974`
- `0x18000cec8`
- `0x18001266c`

## pseudocode

```c
__int64 __fastcall CReadMap::ReadRecord(
        CLogStorage **this,
        __int64 a2,
        unsigned int a3,
        unsigned int *a4,
        struct _LOGRECHEADER **a5,
        struct _LOGREC *a6,
        int a7,
        unsigned int *a8)
{
  int v9; // r14d
  unsigned int i; // esi
  __int64 v12; // rdi
  struct _RECORDPAGE *FirstPage; // rax
  struct _RECORDPAGE *v14; // rsi
  __int64 result; // rax
  __int64 v16; // r15
  struct _LOGRECHEADER *v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // r14d
  struct _LOGREC *v20; // r13
  __int64 v21; // rdi
  unsigned int *v22; // rdx
  CBuffer *v23; // rcx
  struct _RECORDPAGE *ReadPage; // rax
  unsigned int v25; // r8d
  struct CBuffer *v26; // r9
  struct _RECORDPAGE *v27; // rax
  struct _LOGREC *v28; // r8
  unsigned int v29; // ecx
  __int64 v30; // r9
  unsigned int pExceptionObject; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v32; // [rsp+80h] [rbp+50h]

  v32 = a3;
  *a4 = 0;
  v9 = a2;
  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v12 = 4LL * i;
    if ( !*(CLogStorage **)((char *)&this[v12 + 8] + 4) )
      *(CLogStorage **)((char *)&this[v12 + 8] + 4) = CLogStorage::_MapBuffer(
                                                        this[22],
                                                        (unsigned int)this[v12 + 7],
                                                        HIDWORD(this[v12 + 7]),
                                                        1,
                                                        0);
  }
  if ( !v9 )
    v9 = *(_DWORD *)this[22];
  FirstPage = CBuffer::GetFirstPage(*(CLogStorage **)((char *)this + 68), a2, v9, 0, 0);
  v14 = FirstPage;
  if ( !FirstPage )
    return 0;
  v16 = *((unsigned int *)this + 12);
  v17 = (struct _RECORDPAGE *)((char *)FirstPage + v16 + 32);
  v18 = *(unsigned int *)v17;
  if ( (unsigned int)(v16 + *((_DWORD *)this + 14)) + 32LL != v18 )
  {
    *a5 = 0;
    return 0;
  }
  if ( !(_DWORD)v18 && !*((_DWORD *)v17 + 1) && !*((_DWORD *)v17 + 2) )
  {
    pExceptionObject = -2147479510;
    *a5 = 0;
    throw &pExceptionObject;
  }
  v19 = 0;
  v20 = a6;
  *a5 = v17;
  *((_DWORD *)this + 13) -= 24;
  *((_DWORD *)this + 12) += 24;
  if ( *((_DWORD *)this + 2) )
  {
    do
    {
      v21 = 4LL * v19;
      if ( LODWORD(this[v21 + 6]) != 8160 )
      {
        while ( 1 )
        {
          v22 = (unsigned int *)this[22];
          v23 = *(CLogStorage **)((char *)&this[v21 + 8] + 4);
          pExceptionObject = 0;
          ReadPage = CBuffer::GetReadPage(v23, *v22, &pExceptionObject);
          v25 = LODWORD(this[v21 + 7]) + pExceptionObject;
          pExceptionObject = v25;
          if ( !ReadPage )
          {
            v26 = *(CLogStorage **)((char *)&this[v21 + 8] + 4);
            if ( *((_DWORD *)v26 + 16) )
              break;
            if ( !(unsigned int)CLogStorage::SetLastPage(this[22], *(_DWORD *)this[22], v25, v26) )
            {
              pExceptionObject = -2147479510;
              throw &pExceptionObject;
            }
          }
          v27 = CBuffer::GetReadPage(
                  *(CLogStorage **)((char *)&this[v21 + 8] + 4),
                  (unsigned int)this[v21 + 8],
                  &pExceptionObject);
          if ( !v27 )
            break;
          v28 = a6;
          *(_QWORD *)a6 = (char *)v27 + LODWORD(this[v21 + 6]) + 32;
          v29 = HIDWORD(this[v21 + 6]);
          if ( v29 >= 8160 - LODWORD(this[v21 + 6]) )
            v29 = 8160 - LODWORD(this[v21 + 6]);
          *((_DWORD *)v28 + 2) = v29;
          ++*a4;
          v30 = *(__int64 *)((char *)&this[v21 + 8] + 4);
          a6 = (struct _LOGREC *)((char *)v28 + 16);
          if ( a7 )
            CBuffer::FreePage((struct _RECORDPAGE **)v30, v27, 1, v30);
          else
            *(_DWORD *)(v30 + 64) = *(_QWORD *)(v30 + 56) + *(unsigned int *)(v30 + 8) == *(_QWORD *)(v30 + 32);
        }
      }
      ++v19;
    }
    while ( v19 < *((_DWORD *)this + 2) );
  }
  if ( *a4 > v32 )
  {
    pExceptionObject = -2147024809;
    throw &pExceptionObject;
  }
  if ( a8 )
    *a8 = *((_DWORD *)v14 + 2);
  result = 1;
  *((_WORD *)v20 + 6) = *(_WORD *)((char *)v14 + v16 + 44);
  *((_WORD *)v20 + 7) = *(_WORD *)((char *)v14 + v16 + 46);
  return result;
}

```

## disassembly

```asm
0x18000cec8  mov     [rsp-38h+arg_0], rbx
0x18000cecd  mov     [rsp-38h+arg_10], r8d
0x18000ced2  push    rbp
0x18000ced3  push    rsi
0x18000ced4  push    rdi
0x18000ced5  push    r12
0x18000ced7  push    r13
0x18000ced9  push    r14
0x18000cedb  push    r15
0x18000cedd  mov     rbp, rsp
0x18000cee0  sub     rsp, 30h
0x18000cee4  xor     edi, edi
0x18000cee6  mov     r12, r9
0x18000cee9  mov     [r9], edi
0x18000ceec  mov     r14d, edx
0x18000ceef  mov     rbx, rcx
0x18000cef2  mov     esi, edi
0x18000cef4  cmp     [rcx+8], edi
0x18000cef7  jbe     short loc_18000CF38
0x18000cef9  mov     edi, esi
0x18000cefb  shl     rdi, 5
0x18000ceff  cmp     qword ptr [rdi+rbx+44h], 0
0x18000cf05  jnz     short loc_18000CF2F
0x18000cf07  mov     r8d, [rdi+rbx+3Ch]; unsigned int
0x18000cf0c  mov     r9d, 1; int
0x18000cf12  mov     edx, [rdi+rbx+38h]; unsigned int
0x18000cf16  mov     rcx, [rbx+0B0h]; this
0x18000cf1d  mov     dword ptr [rsp+30h+var_10], 0; unsigned int
0x18000cf25  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000cf2a  mov     [rdi+rbx+44h], rax
0x18000cf2f  inc     esi
0x18000cf31  cmp     esi, [rbx+8]
0x18000cf34  jb      short loc_18000CEF9
0x18000cf36  xor     edi, edi
0x18000cf38  test    r14d, r14d
0x18000cf3b  jnz     short loc_18000CF47
0x18000cf3d  mov     rax, [rbx+0B0h]
0x18000cf44  mov     r14d, [rax]
0x18000cf47  mov     rcx, [rbx+44h]; this
0x18000cf4b  xor     r9d, r9d; unsigned int *
0x18000cf4e  mov     r8d, r14d; unsigned int
0x18000cf51  mov     [rsp+30h+var_10], rdi; unsigned int *
0x18000cf56  call    ?GetFirstPage@CBuffer@@QEAAPEAU_RECORDPAGE@@HKPEAK0@Z; CBuffer::GetFirstPage(int,ulong,ulong *,ulong *)
0x18000cf5b  mov     rsi, rax
0x18000cf5e  test    rax, rax
0x18000cf61  jnz     short loc_18000CF6A
0x18000cf63  xor     eax, eax
0x18000cf65  jmp     loc_18000D0F5
0x18000cf6a  mov     r15d, [rbx+30h]
0x18000cf6e  mov     ecx, [rbx+38h]
0x18000cf71  add     ecx, r15d
0x18000cf74  add     rcx, 20h ; ' '
0x18000cf78  lea     rdx, [r15+20h]
0x18000cf7c  add     rdx, rsi
0x18000cf7f  mov     r8d, [rdx]
0x18000cf82  cmp     rcx, r8
0x18000cf85  jz      short loc_18000CF90
0x18000cf87  mov     rax, [rbp+arg_20]
0x18000cf8b  mov     [rax], rdi
0x18000cf8e  jmp     short loc_18000CF63
0x18000cf90  test    r8d, r8d
0x18000cf93  jnz     short loc_18000CFA3
0x18000cf95  cmp     [rdx+4], edi
0x18000cf98  jnz     short loc_18000CFA3
0x18000cf9a  cmp     [rdx+8], edi
0x18000cf9d  jz      loc_18000D10A
0x18000cfa3  mov     rax, [rbp+arg_20]
0x18000cfa7  mov     r14d, edi
0x18000cfaa  mov     r13, [rbp+arg_28]
0x18000cfae  mov     [rbp+arg_28], r13
0x18000cfb2  mov     [rax], rdx
0x18000cfb5  add     dword ptr [rbx+34h], 0FFFFFFE8h
0x18000cfb9  add     dword ptr [rbx+30h], 18h
0x18000cfbd  cmp     [rbx+8], edi
0x18000cfc0  jbe     loc_18000D0C3
0x18000cfc6  mov     edi, r14d
0x18000cfc9  shl     rdi, 5
0x18000cfcd  cmp     dword ptr [rdi+rbx+30h], 1FE0h
0x18000cfd5  jz      loc_18000D0B6
0x18000cfdb  mov     rdx, [rbx+0B0h]
0x18000cfe2  lea     r8, [rbp+pExceptionObject]; unsigned int *
0x18000cfe6  mov     rcx, [rdi+rbx+44h]; this
0x18000cfeb  mov     [rbp+pExceptionObject], 0
0x18000cff2  mov     edx, [rdx]; unsigned int
0x18000cff4  call    ?GetReadPage@CBuffer@@QEAAPEAU_RECORDPAGE@@KPEAK@Z; CBuffer::GetReadPage(ulong,ulong *)
0x18000cff9  mov     r8d, [rbp+pExceptionObject]
0x18000cffd  add     r8d, [rdi+rbx+38h]; unsigned int
0x18000d002  mov     [rbp+pExceptionObject], r8d
0x18000d006  test    rax, rax
0x18000d009  jnz     short loc_18000D030
0x18000d00b  mov     r9, [rdi+rbx+44h]; struct CBuffer *
0x18000d010  cmp     [r9+40h], eax
0x18000d014  jnz     loc_18000D0B6
0x18000d01a  mov     rcx, [rbx+0B0h]; this
0x18000d021  mov     edx, [rcx]; unsigned int
0x18000d023  call    ?SetLastPage@CLogStorage@@QEAAHKKPEAVCBuffer@@@Z; CLogStorage::SetLastPage(ulong,ulong,CBuffer *)
0x18000d028  test    eax, eax
0x18000d02a  jz      loc_18000D141
0x18000d030  mov     edx, [rdi+rbx+40h]; unsigned int
0x18000d034  lea     r8, [rbp+pExceptionObject]; unsigned int *
0x18000d038  mov     rcx, [rdi+rbx+44h]; this
0x18000d03d  call    ?GetReadPage@CBuffer@@QEAAPEAU_RECORDPAGE@@KPEAK@Z; CBuffer::GetReadPage(ulong,ulong *)
0x18000d042  test    rax, rax
0x18000d045  jz      short loc_18000D0B6
0x18000d047  mov     edx, [rdi+rbx+30h]
0x18000d04b  mov     r8, [rbp+arg_28]
0x18000d04f  add     rdx, 20h ; ' '
0x18000d053  add     rdx, rax
0x18000d056  mov     [r8], rdx
0x18000d059  mov     edx, 1FE0h
0x18000d05e  sub     edx, [rdi+rbx+30h]
0x18000d062  mov     ecx, [rdi+rbx+34h]
0x18000d066  cmp     ecx, edx
0x18000d068  cmovnb  ecx, edx
0x18000d06b  mov     [r8+8], ecx
0x18000d06f  add     r8, 10h
0x18000d073  inc     dword ptr [r12]
0x18000d077  cmp     [rbp+arg_30], 0
0x18000d07b  mov     r9, [rdi+rbx+44h]; unsigned int
0x18000d080  mov     [rbp+arg_28], r8
0x18000d084  jz      short loc_18000D09C
0x18000d086  mov     r8d, 1; int
0x18000d08c  mov     rdx, rax; struct _RECORDPAGE *
0x18000d08f  mov     rcx, r9; this
0x18000d092  call    ?FreePage@CBuffer@@QEAAXPEAU_RECORDPAGE@@HK@Z; CBuffer::FreePage(_RECORDPAGE *,int,ulong)
0x18000d097  jmp     loc_18000CFDB
0x18000d09c  mov     eax, [r9+8]
0x18000d0a0  xor     ecx, ecx
0x18000d0a2  add     rax, [r9+38h]
0x18000d0a6  cmp     rax, [r9+20h]
0x18000d0aa  setz    cl
0x18000d0ad  mov     [r9+40h], ecx
0x18000d0b1  jmp     loc_18000CFDB
0x18000d0b6  inc     r14d
0x18000d0b9  cmp     r14d, [rbx+8]
0x18000d0bd  jb      loc_18000CFC6
0x18000d0c3  mov     eax, [rbp+arg_10]
0x18000d0c6  cmp     [r12], eax
0x18000d0ca  ja      short loc_18000D129
0x18000d0cc  mov     rdx, [rbp+arg_38]
0x18000d0d0  test    rdx, rdx
0x18000d0d3  jz      short loc_18000D0DA
0x18000d0d5  mov     ecx, [rsi+8]
0x18000d0d8  mov     [rdx], ecx
0x18000d0da  movzx   ecx, word ptr [r15+rsi+2Ch]
0x18000d0e0  mov     eax, 1
0x18000d0e5  mov     [r13+0Ch], cx
0x18000d0ea  movzx   ecx, word ptr [r15+rsi+2Eh]
0x18000d0f0  mov     [r13+0Eh], cx
0x18000d0f5  mov     rbx, [rsp+30h+arg_0]
0x18000d0fa  add     rsp, 30h
0x18000d0fe  pop     r15
0x18000d100  pop     r14
0x18000d102  pop     r13
0x18000d104  pop     r12
0x18000d106  pop     rdi
0x18000d107  pop     rsi
0x18000d108  pop     rbp
0x18000d109  retn
0x18000d10a  mov     rax, [rbp+arg_20]
0x18000d10e  lea     rdx, _TI1K; pThrowInfo
0x18000d115  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d119  mov     [rbp+pExceptionObject], 8000102Ah
0x18000d120  mov     [rax], rdi
0x18000d123  call    _CxxThrowException_0
0x18000d129  lea     rdx, _TI1K; pThrowInfo
0x18000d130  mov     [rbp+pExceptionObject], 80070057h
0x18000d137  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d13b  call    _CxxThrowException_0
0x18000d141  lea     rdx, _TI1K; pThrowInfo
0x18000d148  mov     [rbp+pExceptionObject], 8000102Ah
0x18000d14f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d153  call    _CxxThrowException_0
```
