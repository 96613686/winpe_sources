# CExposedDocFile::CopySStreamToIStream(PSStream *,IStream *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18002268c`
- end: `0x180022996`
- name: `?CopySStreamToIStream@CExposedDocFile@@AEAAJPEAVPSStream@@PEAUIStream@@PEA_K2@Z`
- size: `778`
- prototype: `int(CExposedDocFile *__hidden this, struct PSStream *, struct IStream *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180021860`

## callees

- `0x180010cf0`
- `0x18002268c`
- `0x18003e378`
- `0x18004aa40`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800226e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800226e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002280d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002280d`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::CopySStreamToIStream(
        CExposedDocFile *this,
        struct PSStream *a2,
        struct IStream *a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5)
{
  unsigned int v8; // esi
  __int64 v9; // r8
  __int64 v10; // r9
  void *v11; // r15
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  unsigned __int64 v14; // rbx
  struct IStream *v15; // r14
  int v16; // edi
  unsigned __int64 i; // rbx
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // r8
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  _QWORD *v25; // rdx
  unsigned __int64 *v26; // r12
  unsigned __int64 *v27; // r8
  _QWORD *v28; // rcx
  _QWORD *v29; // rdx
  __int64 v30; // rax
  unsigned int v31; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v32[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v33; // [rsp+80h] [rbp+8h] BYREF
  struct IStream *v34; // [rsp+90h] [rbp+18h]

  v34 = a3;
  v33 = 0;
  v31 = 0;
  v8 = (*(_DWORD *)(*((_QWORD *)this + 21) + 56LL) & 0x80000) != 0 ? 0x40000 : 0x2000;
  while ( 1 )
  {
    v11 = CoTaskMemAlloc(v8);
    if ( v11 )
      break;
    v8 >>= 1;
    if ( v8 < 0x2000 )
    {
      v16 = -2147287032;
      goto LABEL_17;
    }
  }
  if ( *a4 == -2 )
  {
    LOBYTE(v9) = 0;
    goto LABEL_5;
  }
  LOBYTE(v9) = 1;
  if ( *a4 == -1 )
  {
LABEL_5:
    LOBYTE(v10) = 0;
    goto LABEL_6;
  }
  LOBYTE(v10) = 1;
LABEL_6:
  v12 = (_QWORD *)*((_QWORD *)this + 22);
  v13 = (_QWORD *)*((_QWORD *)this + 21);
  v13[4] = v12[2];
  v13[5] = v12[3];
  v13[6] = v12[4];
  if ( *(_DWORD *)a2 == 1381258052 )
  {
    v14 = *((_QWORD *)a2 + 22);
  }
  else
  {
    v14 = 0;
    if ( *(_DWORD *)a2 == 1381258068 )
      v14 = *((_QWORD *)a2 + 14);
  }
  if ( (_BYTE)v9 )
  {
    if ( v14 > 0xFFFFFFFA000LL )
    {
LABEL_32:
      v16 = -2147286775;
      goto LABEL_17;
    }
    if ( !(_BYTE)v10 && v14 > 0x100000 )
    {
      v24 = (_QWORD *)*((_QWORD *)this + 22);
      v25 = (_QWORD *)*((_QWORD *)this + 21);
      v26 = a5;
      v27 = a5;
      v25[4] = v24[2];
      v25[5] = v24[3];
      v25[6] = v24[4];
      v16 = CExposedDocFile::CalculateReasonableMaxStreamSize(this, a4, v27);
      if ( v16 < 0 )
        goto LABEL_17;
      if ( v14 > *a4 )
      {
        v28 = (_QWORD *)*((_QWORD *)this + 22);
        v29 = (_QWORD *)*((_QWORD *)this + 21);
        v29[4] = v28[2];
        v29[5] = v28[3];
        v29[6] = v28[4];
        v30 = *((_QWORD *)this + 21);
        v32[0] = 0;
        if ( (***(int (__fastcall ****)(_QWORD, GUID *, _QWORD *))(v30 + 32))(
               *(_QWORD *)(v30 + 32),
               &IID_IDfReserved1,
               v32) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32[0] + 16LL))(v32[0]);
          goto LABEL_32;
        }
        v21 = *((_QWORD *)this + 21);
        v22 = v14 - *v26;
        v23 = *(unsigned int *)(v21 + 84);
        if ( v23 + v22 > 0x7FFFFF00 && v22 <= 0x7FFFFFE3 )
          v22 += v23;
        if ( (int)VerifySectorAvailableAtOffset(*(struct ILockBytes **)(v21 + 32), v23, v22) < 0 )
          goto LABEL_32;
        *a4 = v14;
      }
    }
  }
  v15 = v34;
  v16 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64, __int64, __int64))(*(_QWORD *)v34 + 48LL))(
          v34,
          v14,
          v9,
          v10);
  if ( v16 >= 0 )
  {
    for ( i = 0; ; i += v31 )
    {
      v18 = (_QWORD *)*((_QWORD *)this + 22);
      v19 = (_QWORD *)*((_QWORD *)this + 21);
      v19[4] = v18[2];
      v19[5] = v18[3];
      v19[6] = v18[4];
      v16 = PSStream::ReadAt(a2, i, v11, v8, &v33);
      if ( v16 < 0 )
        break;
      if ( !v33 )
      {
        v16 = 0;
        break;
      }
      v16 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, unsigned int *))(*(_QWORD *)v15 + 32LL))(
              v15,
              v11,
              v33,
              &v31);
      if ( v16 < 0 )
        break;
      if ( v33 != v31 )
      {
        v16 = -2147287011;
        break;
      }
    }
  }
LABEL_17:
  CoTaskMemFree(v11);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18002268c  mov     rax, rsp
0x18002268f  mov     [rax+10h], rbx
0x180022693  mov     [rax+18h], r8
0x180022697  push    rbp
0x180022698  push    rsi
0x180022699  push    rdi
0x18002269a  push    r12
0x18002269c  push    r13
0x18002269e  push    r14
0x1800226a0  push    r15
0x1800226a2  sub     rsp, 40h
0x1800226a6  mov     dword ptr [rax+8], 0
0x1800226ad  mov     ebx, 2000h
0x1800226b2  mov     dword ptr [rax-48h], 0
0x1800226b9  mov     r14, r9
0x1800226bc  mov     rax, [rcx+0A8h]
0x1800226c3  mov     r13, rdx
0x1800226c6  mov     rbp, rcx
0x1800226c9  mov     r10d, [rax+38h]
0x1800226cd  and     r10d, 80000h
0x1800226d4  neg     r10d
0x1800226d7  sbb     esi, esi
0x1800226d9  and     esi, 3E000h
0x1800226df  add     esi, ebx
0x1800226e1  mov     ecx, esi; cb
0x1800226e3  call    cs:__imp_CoTaskMemAlloc
0x1800226e9  mov     r15, rax
0x1800226ec  test    rax, rax
0x1800226ef  jz      loc_1800228A8
0x1800226f5  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFEh
0x1800226f9  jz      loc_180022846
0x1800226ff  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180022703  mov     r8b, 1
0x180022706  jnz     loc_1800228BC
0x18002270c  xor     r9b, r9b
0x18002270f  mov     rcx, [rbp+0B0h]
0x180022716  mov     rdx, [rbp+0A8h]
0x18002271d  mov     rax, [rcx+10h]
0x180022721  mov     [rdx+20h], rax
0x180022725  mov     rax, [rcx+18h]
0x180022729  mov     [rdx+28h], rax
0x18002272d  mov     rax, [rcx+20h]
0x180022731  mov     [rdx+30h], rax
0x180022735  cmp     dword ptr [r13+0], 52545344h
0x18002273d  jnz     loc_180022852
0x180022743  mov     rbx, [r13+0B0h]
0x18002274a  test    r8b, r8b
0x18002274d  jz      short loc_180022774
0x18002274f  mov     rax, 0FFFFFFFA000h
0x180022759  cmp     rbx, rax
0x18002275c  ja      loc_1800228D5
0x180022762  test    r9b, r9b
0x180022765  jnz     short loc_180022774
0x180022767  cmp     rbx, 100000h
0x18002276e  ja      loc_1800228DF
0x180022774  mov     r14, [rsp+78h+arg_10]
0x18002277c  mov     rdx, rbx
0x18002277f  mov     rcx, r14
0x180022782  mov     rax, [r14]
0x180022785  mov     rax, [rax+30h]
0x180022789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002278e  mov     edi, eax
0x180022790  test    eax, eax
0x180022792  js      short loc_18002280A
0x180022794  xor     ebx, ebx
0x180022796  mov     rcx, [rbp+0B0h]
0x18002279d  mov     r9d, esi; unsigned int
0x1800227a0  mov     rdx, [rbp+0A8h]
0x1800227a7  mov     r8, r15; void *
0x1800227aa  mov     rax, [rcx+10h]
0x1800227ae  mov     [rdx+20h], rax
0x1800227b2  mov     rax, [rcx+18h]
0x1800227b6  mov     [rdx+28h], rax
0x1800227ba  mov     rax, [rcx+20h]
0x1800227be  mov     rcx, r13; this
0x1800227c1  mov     [rdx+30h], rax
0x1800227c5  lea     rax, [rsp+78h+arg_0]
0x1800227cd  mov     rdx, rbx; unsigned __int64
0x1800227d0  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800227d5  call    ?ReadAt@PSStream@@QEAAJ_KPEAXKPEAK@Z; PSStream::ReadAt(unsigned __int64,void *,ulong,ulong *)
0x1800227da  mov     edi, eax
0x1800227dc  test    eax, eax
0x1800227de  js      short loc_18002280A
0x1800227e0  mov     r8d, [rsp+78h+arg_0]
0x1800227e8  test    r8d, r8d
0x1800227eb  jz      short loc_18002284E
0x1800227ed  mov     rax, [r14]
0x1800227f0  lea     r9, [rsp+78h+var_48]
0x1800227f5  mov     rdx, r15
0x1800227f8  mov     rcx, r14
0x1800227fb  mov     rax, [rax+20h]
0x1800227ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022804  mov     edi, eax
0x180022806  test    eax, eax
0x180022808  jns     short loc_18002282D
0x18002280a  mov     rcx, r15; pv
0x18002280d  call    cs:__imp_CoTaskMemFree
0x180022813  mov     rbx, [rsp+78h+arg_8]
0x18002281b  mov     eax, edi
0x18002281d  add     rsp, 40h
0x180022821  pop     r15
0x180022823  pop     r14
0x180022825  pop     r13
0x180022827  pop     r12
0x180022829  pop     rdi
0x18002282a  pop     rsi
0x18002282b  pop     rbp
0x18002282c  retn
0x18002282d  mov     eax, [rsp+78h+var_48]
0x180022831  cmp     [rsp+78h+arg_0], eax
0x180022838  jnz     loc_18002298C
0x18002283e  add     rbx, rax
0x180022841  jmp     loc_180022796
0x180022846  xor     r8b, r8b
0x180022849  jmp     loc_18002270C
0x18002284e  xor     edi, edi
0x180022850  jmp     short loc_18002280A
0x180022852  xor     ebx, ebx
0x180022854  cmp     dword ptr [r13+0], 52545354h
0x18002285c  jnz     loc_18002274A
0x180022862  mov     rbx, [r13+70h]
0x180022866  jmp     loc_18002274A
0x18002286b  mov     rcx, [rbp+0A8h]
0x180022872  mov     r8, rbx
0x180022875  sub     r8, [r12]
0x180022879  mov     edx, [rcx+54h]; unsigned int
0x18002287c  lea     rax, [rdx+r8]
0x180022880  cmp     rax, 7FFFFF00h
0x180022886  jbe     short loc_180022893
0x180022888  cmp     r8, 7FFFFFE3h
0x18002288f  cmovbe  r8, rax; unsigned __int64
0x180022893  mov     rcx, [rcx+20h]; struct ILockBytes *
0x180022897  call    ?VerifySectorAvailableAtOffset@@YAJPEAUILockBytes@@K_K@Z; VerifySectorAvailableAtOffset(ILockBytes *,ulong,unsigned __int64)
0x18002289c  test    eax, eax
0x18002289e  js      short loc_1800228D5
0x1800228a0  mov     [r14], rbx
0x1800228a3  jmp     loc_180022774
0x1800228a8  shr     esi, 1
0x1800228aa  cmp     esi, ebx
0x1800228ac  jnb     loc_1800226E1
0x1800228b2  mov     edi, 80030008h
0x1800228b7  jmp     loc_18002280A
0x1800228bc  mov     r9b, r8b
0x1800228bf  jmp     loc_18002270F
0x1800228c4  mov     rcx, [rsp+78h+var_40]
0x1800228c9  mov     rax, [rcx]
0x1800228cc  mov     rax, [rax+10h]
0x1800228d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228d5  mov     edi, 80030109h
0x1800228da  jmp     loc_18002280A
0x1800228df  mov     rcx, [rbp+0B0h]
0x1800228e6  mov     rdx, [rbp+0A8h]
0x1800228ed  mov     r12, [rsp+78h+arg_20]
0x1800228f5  mov     r8, r12; unsigned __int64 *
0x1800228f8  mov     rax, [rcx+10h]
0x1800228fc  mov     [rdx+20h], rax
0x180022900  mov     rax, [rcx+18h]
0x180022904  mov     [rdx+28h], rax
0x180022908  mov     rax, [rcx+20h]
0x18002290c  mov     rcx, rbp; this
0x18002290f  mov     [rdx+30h], rax
0x180022913  mov     rdx, r14; unsigned __int64 *
0x180022916  call    ?CalculateReasonableMaxStreamSize@CExposedDocFile@@AEAAJPEA_K0@Z; CExposedDocFile::CalculateReasonableMaxStreamSize(unsigned __int64 *,unsigned __int64 *)
0x18002291b  mov     edi, eax
0x18002291d  test    eax, eax
0x18002291f  js      loc_18002280A
0x180022925  cmp     rbx, [r14]
0x180022928  jbe     loc_180022774
0x18002292e  mov     rcx, [rbp+0B0h]
0x180022935  lea     r8, [rsp+78h+var_40]
0x18002293a  mov     rdx, [rbp+0A8h]
0x180022941  mov     rax, [rcx+10h]
0x180022945  mov     [rdx+20h], rax
0x180022949  mov     rax, [rcx+18h]
0x18002294d  mov     [rdx+28h], rax
0x180022951  mov     rax, [rcx+20h]
0x180022955  mov     [rdx+30h], rax
0x180022959  lea     rdx, IID_IDfReserved1
0x180022960  mov     rax, [rbp+0A8h]
0x180022967  mov     [rsp+78h+var_40], 0
0x180022970  mov     rcx, [rax+20h]
0x180022974  mov     rax, [rcx]
0x180022977  mov     rax, [rax]
0x18002297a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002297f  test    eax, eax
0x180022981  js      loc_18002286B
0x180022987  jmp     loc_1800228C4
0x18002298c  mov     edi, 8003001Dh
0x180022991  jmp     loc_18002280A
```
