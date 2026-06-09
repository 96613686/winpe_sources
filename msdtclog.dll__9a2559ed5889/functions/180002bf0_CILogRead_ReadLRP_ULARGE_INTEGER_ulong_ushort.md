# CILogRead::ReadLRP(_ULARGE_INTEGER,ulong *,ushort *)

- ea: `0x180002bf0`
- end: `0x180002e90`
- name: `?ReadLRP@CILogRead@@UEAAJT_ULARGE_INTEGER@@PEAKPEAG@Z`
- size: `672`
- prototype: `__int64 __fastcall(CILogRead *__hidden this, union _ULARGE_INTEGER, unsigned int *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x180001300`
- `0x18000130c`
- `0x180002bf0`
- `0x180009178`
- `0x18000ce68`
- `0x18000cec8`
- `0x18000d160`
- `0x18000d2f0`
- `0x18001280a`

## pseudocode

```c
__int64 __fastcall CILogRead::ReadLRP(
        CILogRead *this,
        union _ULARGE_INTEGER a2,
        unsigned int *a3,
        unsigned __int16 *a4)
{
  unsigned int v8; // esi
  __int64 v9; // rcx
  CReadMap *v10; // rcx
  void *v11; // rcx
  size_t v12; // rax
  __int64 v13; // rax
  void *v14; // rcx
  int v16; // r12d
  union _ULARGE_INTEGER *v17; // rdx
  struct _LOGRECHEADER *v18; // rcx
  __int64 v19; // rax
  void *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v24; // [rsp+44h] [rbp-54h] BYREF
  ulong v25; // [rsp+48h] [rbp-50h] BYREF
  struct _LOGRECHEADER *v26; // [rsp+50h] [rbp-48h] BYREF
  unsigned int; // [rsp+A0h] [rbp+8h]
  ulong; // [rsp+A0h] [rbp+8h]
  DWORD HighPart; // [rsp+ACh] [rbp+14h]

  HighPart = a2.HighPart;
  if ( !*(_QWORD *)(*((_QWORD *)this + 2) + 392LL) || !*((_QWORD *)this + 1) )
    return 2147549183LL;
  if ( !a2.QuadPart )
    return 2147942487LL;
  v8 = 0;
  if ( !a3 )
    return 2147942487LL;
  v9 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)(v9 + 544) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      CReadMap::ReleaseAndSet((CReadMap *)(v9 + 352), 0, 0);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v24) )
      {
        *a3 = 0;
        if ( a4 )
          *a4 = 0;
        v21 = *((_QWORD *)this + 1);
        if ( *(_QWORD *)(v21 + 584) )
          operator delete(*(void **)(v21 + 584));
        CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
         = v24;
        v8 = ;
        __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_180002E6A);
        return v8;
      }
      if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', &v25) )
      {
        *a3 = 0;
        if ( a4 )
          *a4 = 0;
        v22 = *((_QWORD *)this + 1);
        if ( *(_QWORD *)(v22 + 584) )
          operator delete(*(void **)(v22 + 584));
        CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
         = v25;
        v8 = ;
        __eh34_try_continuation(0, &unsigned long `RTTI Type Descriptor', &loc_180002E6A);
        return v8;
      }
    }
  }
  v10 = (CReadMap *)(*((_QWORD *)this + 1) + 352LL);
  *(_DWORD *)v10 = a2.LowPart;
  CReadMap::_SetUpResidue(v10, HighPart);
  CLogState::AttemptRead(
    *(CLogState **)(*((_QWORD *)this + 2) + 400LL),
    (struct CReadMap *)(*((_QWORD *)this + 1) + 352LL),
    0);
  *(_DWORD *)(*((_QWORD *)this + 1) + 576LL) = CReadMap::GetBufCount((CReadMap *)(*((_QWORD *)this + 1) + 352LL));
  v23 = 0;
  v26 = 0;
  v11 = *(void **)(*((_QWORD *)this + 1) + 584LL);
  if ( v11 )
    operator delete(v11);
  v12 = 16LL * *(unsigned int *)(*((_QWORD *)this + 1) + 576LL);
  if ( !is_mul_ok(*(unsigned int *)(*((_QWORD *)this + 1) + 576LL), 0x10u) )
    v12 = -1;
  *(_QWORD *)(*((_QWORD *)this + 1) + 584LL) = operator new[](v12);
  v13 = *((_QWORD *)this + 1);
  v14 = *(void **)(v13 + 584);
  if ( v14 )
  {
    memset_0(v14, 0, 16LL * *(unsigned int *)(v13 + 576));
    v16 = ((int (__stdcall *)(CReadMap *, unsigned int, unsigned int, unsigned int *, struct _LOGRECHEADER **, struct _LOGREC *, int, unsigned int *))CReadMap::ReadRecord)(
            (CReadMap *)(*((_QWORD *)this + 1) + 352LL),
            HighPart,
            *(_DWORD *)(*((_QWORD *)this + 1) + 576LL),
            &v23,
            &v26,
            *(struct _LOGREC **)(*((_QWORD *)this + 1) + 584LL),
            0,
            0);
    if ( v16
      && (v17 = (union _ULARGE_INTEGER *)*((_QWORD *)this + 1), v18 = v26, *((_DWORD *)v26 + 4) == v17[41].LowPart)
      && *((_WORD *)v26 + 7) == 1 )
    {
      v17[68] = a2;
      v19 = *((_QWORD *)this + 1);
      *(_OWORD *)(v19 + 552) = *(_OWORD *)v18;
      *(_QWORD *)(v19 + 568) = *((_QWORD *)v18 + 2);
      *a3 = *((_DWORD *)v18 + 2);
      if ( a4 )
        *a4 = *((_WORD *)v18 + 6);
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)this + 1) + 544LL) = 0;
      CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
      *a3 = 0;
      if ( a4 )
        *a4 = 0;
      v20 = *(void **)(*((_QWORD *)this + 1) + 584LL);
      if ( v20 )
        operator delete(v20);
      return v16 != 0 ? -1073737670 : -2147479509;
    }
    return v8;
  }
  *(_QWORD *)(v13 + 544) = 0;
  CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  return 2147942414LL;
}

```

## disassembly

```asm
0x180002bf0  mov     rax, rsp
0x180002bf3  mov     [rax+20h], r9
0x180002bf7  mov     [rax+18h], r8
0x180002bfb  mov     [rax+10h], rdx
0x180002bff  mov     [rax+8], rcx
0x180002c03  push    rbx
0x180002c04  push    rsi
0x180002c05  push    rdi
0x180002c06  push    r12
0x180002c08  push    r14
0x180002c0a  push    r15
0x180002c0c  sub     rsp, 68h
0x180002c10  mov     r14, r9
0x180002c13  mov     r15, r8
0x180002c16  mov     rbx, rdx
0x180002c19  mov     rdi, rcx
0x180002c1c  mov     rax, [rcx+10h]
0x180002c20  cmp     qword ptr [rax+188h], 0
0x180002c28  jz      loc_180002E7C
0x180002c2e  cmp     qword ptr [rcx+8], 0
0x180002c33  jz      loc_180002E7C
0x180002c39  test    rdx, rdx
0x180002c3c  jz      loc_180002E75
0x180002c42  xor     esi, esi
0x180002c44  test    r8, r8
0x180002c47  jz      loc_180002E75
0x180002c4d  mov     rcx, [rcx+8]
0x180002c51  cmp     [rcx+220h], rsi
0x180002c58  jz      short loc_180002C6B
0x180002c5a  add     rcx, 160h; this
0x180002c61  xor     r8d, r8d; unsigned int
0x180002c64  xor     edx, edx; unsigned int
0x180002c66  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180002c6b  mov     rcx, [rdi+8]
0x180002c6f  add     rcx, 160h; this
0x180002c76  mov     [rcx], ebx
0x180002c78  mov     edx, [rsp+98h+arg_C]; unsigned int
0x180002c7f  call    ?_SetUpResidue@CReadMap@@AEAAXK@Z; CReadMap::_SetUpResidue(ulong)
0x180002c84  mov     rdx, [rdi+8]
0x180002c88  mov     r12d, 160h
0x180002c8e  add     rdx, r12; struct CReadMap *
0x180002c91  mov     rcx, [rdi+10h]
0x180002c95  xor     r8d, r8d; int
0x180002c98  mov     rcx, [rcx+190h]; this
0x180002c9f  call    ?AttemptRead@CLogState@@QEAAXAEAVCReadMap@@H@Z; CLogState::AttemptRead(CReadMap &,int)
0x180002ca4  mov     rcx, [rdi+8]
0x180002ca8  add     rcx, r12; this
0x180002cab  call    ?GetBufCount@CReadMap@@QEAAKXZ; CReadMap::GetBufCount(void)
0x180002cb0  mov     ecx, eax
0x180002cb2  mov     rax, [rdi+8]
0x180002cb6  mov     [rax+240h], ecx
0x180002cbc  mov     [rsp+98h+var_58], 0
0x180002cc4  mov     [rsp+98h+var_48], 0
0x180002ccd  mov     rax, [rdi+8]
0x180002cd1  mov     rcx, [rax+248h]; Block
0x180002cd8  test    rcx, rcx
0x180002cdb  jz      short loc_180002CE2
0x180002cdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ce2  mov     rax, [rdi+8]
0x180002ce6  mov     ecx, [rax+240h]
0x180002cec  mov     eax, 10h
0x180002cf1  mul     rcx
0x180002cf4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002cfb  cmovb   rax, rcx
0x180002cff  mov     rcx, rax; unsigned __int64
0x180002d02  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002d07  mov     rcx, rax
0x180002d0a  mov     rax, [rdi+8]
0x180002d0e  mov     [rax+248h], rcx
0x180002d15  mov     rax, [rdi+8]
0x180002d19  mov     rcx, [rax+248h]; void *
0x180002d20  xor     edx, edx; unsigned int
0x180002d22  test    rcx, rcx
0x180002d25  jnz     short loc_180002D59
0x180002d27  mov     [rax+220h], rdx
0x180002d2e  mov     rcx, [rdi+8]
0x180002d32  add     rcx, r12; this
0x180002d35  xor     r8d, r8d; unsigned int
0x180002d38  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180002d3d  mov     dword ptr [r15], 0
0x180002d44  test    r14, r14
0x180002d47  jz      short loc_180002D4F
0x180002d49  xor     eax, eax
0x180002d4b  mov     [r14], ax
0x180002d4f  mov     eax, 8007000Eh
0x180002d54  jmp     loc_180002E81
0x180002d59  mov     r8d, [rax+240h]
0x180002d60  shl     r8, 4; Size
0x180002d64  call    memset_0
0x180002d69  mov     r8, [rdi+8]
0x180002d6d  lea     rcx, [r8+160h]; this
0x180002d74  mov     [rsp+98h+var_60], 0; unsigned int *
0x180002d7d  mov     [rsp+98h+var_68], 0; int
0x180002d85  mov     rax, [r8+248h]
0x180002d8c  mov     [rsp+98h+var_70], rax; struct _LOGREC *
0x180002d91  lea     rax, [rsp+98h+var_48]
0x180002d96  mov     [rsp+98h+var_78], rax; struct _LOGRECHEADER **
0x180002d9b  lea     r9, [rsp+98h+var_58]; unsigned int *
0x180002da0  mov     r8d, [r8+240h]; unsigned int
0x180002da7  mov     edx, [rsp+98h+arg_C]; unsigned int
0x180002dae  call    ?ReadRecord@CReadMap@@QEAAHKKPEAKPEAPEAU_LOGRECHEADER@@PEAU_LOGREC@@H0@Z; CReadMap::ReadRecord(ulong,ulong,ulong *,_LOGRECHEADER * *,_LOGREC *,int,ulong *)
0x180002db3  mov     r12d, eax
0x180002db6  test    eax, eax
0x180002db8  jz      short loc_180002E0C
0x180002dba  mov     rdx, [rdi+8]
0x180002dbe  mov     eax, [rdx+148h]
0x180002dc4  mov     rcx, [rsp+98h+var_48]
0x180002dc9  cmp     [rcx+10h], eax
0x180002dcc  jnz     short loc_180002E0C
0x180002dce  cmp     word ptr [rcx+0Eh], 1
0x180002dd3  jnz     short loc_180002E0C
0x180002dd5  mov     [rdx+220h], rbx
0x180002ddc  mov     rax, [rdi+8]
0x180002de0  movups  xmm0, xmmword ptr [rcx]
0x180002de3  movups  xmmword ptr [rax+228h], xmm0
0x180002dea  movsd   xmm1, qword ptr [rcx+10h]
0x180002def  movsd   qword ptr [rax+238h], xmm1
0x180002df7  mov     eax, [rcx+8]
0x180002dfa  mov     [r15], eax
0x180002dfd  test    r14, r14
0x180002e00  jz      short loc_180002E68
0x180002e02  movzx   eax, word ptr [rcx+0Ch]
0x180002e06  mov     [r14], ax
0x180002e0a  jmp     short loc_180002E68
0x180002e0c  mov     rax, [rdi+8]
0x180002e10  mov     qword ptr [rax+220h], 0
0x180002e1b  mov     rcx, [rdi+8]
0x180002e1f  add     rcx, 160h; this
0x180002e26  xor     r8d, r8d; unsigned int
0x180002e29  xor     edx, edx; unsigned int
0x180002e2b  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180002e30  mov     dword ptr [r15], 0
0x180002e37  test    r14, r14
0x180002e3a  jz      short loc_180002E42
0x180002e3c  xor     eax, eax
0x180002e3e  mov     [r14], ax
0x180002e42  mov     rax, [rdi+8]
0x180002e46  mov     rcx, [rax+248h]; Block
0x180002e4d  test    rcx, rcx
0x180002e50  jz      short loc_180002E57
0x180002e52  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e57  neg     r12d
0x180002e5a  sbb     esi, esi
0x180002e5c  and     esi, 4000000Fh
0x180002e62  add     esi, 8000102Bh
0x180002e68  jmp     short loc_180002E71
0x180002e6a  mov     esi, [rsp+98h+arg_0]
0x180002e71  mov     eax, esi
0x180002e73  jmp     short loc_180002E81
0x180002e75  mov     eax, 80070057h
0x180002e7a  jmp     short loc_180002E81
0x180002e7c  mov     eax, 8000FFFFh
0x180002e81  add     rsp, 68h
0x180002e85  pop     r15
0x180002e87  pop     r14
0x180002e89  pop     r12
0x180002e8b  pop     rdi
0x180002e8c  pop     rsi
0x180002e8d  pop     rbx
0x180002e8e  retn
```
