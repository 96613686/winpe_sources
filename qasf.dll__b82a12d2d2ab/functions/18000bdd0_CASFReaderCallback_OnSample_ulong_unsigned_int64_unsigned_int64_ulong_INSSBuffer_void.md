# CASFReaderCallback::OnSample(ulong,unsigned __int64,unsigned __int64,ulong,INSSBuffer *,void *)

- ea: `0x18000bdd0`
- end: `0x18000c296`
- name: `?OnSample@CASFReaderCallback@@UEAAJK_K0KPEAUINSSBuffer@@PEAX@Z`
- size: `1222`
- prototype: `__int64 __fastcall(CASFReaderCallback *this, int, __int64, __int64, char, struct INSSBuffer *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001460`
- `0x18000bdd0`
- `0x18000cc78`
- `0x18000cd48`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReaderCallback::OnSample(
        CASFReaderCallback *this,
        int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        struct INSSBuffer *a6)
{
  __int64 v7; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdi
  struct INSSBufferVtbl *lpVtbl; // rsi
  struct INSSBufferVtbl *v13; // rax
  __int64 v14; // rax
  unsigned int v15; // edx
  struct INSSBufferVtbl *v16; // rax
  __int64 v17; // rax
  int v18; // r8d
  struct INSSBufferVtbl *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  bool v23; // cc
  _QWORD *v24; // rcx
  unsigned int v25; // r14d
  BOOL v26; // r12d
  int v27; // eax
  struct INSSBufferVtbl *v28; // rax
  __int64 v29; // rcx
  int v31; // ebx
  IID v32; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v33; // [rsp+40h] [rbp-40h] BYREF
  char v34[4]; // [rsp+48h] [rbp-38h] BYREF
  int v35; // [rsp+4Ch] [rbp-34h] BYREF
  __int64 v36; // [rsp+50h] [rbp-30h] BYREF
  __int64 v37; // [rsp+58h] [rbp-28h] BYREF
  __int128 v38; // [rsp+60h] [rbp-20h] BYREF
  __int64 v39; // [rsp+70h] [rbp-10h]

  v7 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v7 + 456) )
    return 0;
  v10 = *(_QWORD *)(v7 + 280);
  if ( !v10 )
    return 0;
  do
  {
    v11 = *(_QWORD *)(v10 + 16);
    if ( *(_DWORD *)(v11 + 304) == a2 )
      break;
    v10 = *(_QWORD *)(v10 + 8);
  }
  while ( v10 );
  if ( !*(_QWORD *)(v11 + 48) )
    return 0;
  lpVtbl = a6[9].lpVtbl;
  (*((void (__fastcall **)(struct INSSBufferVtbl *))lpVtbl->QueryInterface + 1))(lpVtbl);
  v37 = 0;
  v36 = 0;
  if ( !*(_DWORD *)(v11 + 332) )
  {
    if ( *(_DWORD *)(v11 + 408) )
    {
      v13 = a6->lpVtbl;
      v33 = 0;
      if ( ((__int64 (__fastcall *)(struct INSSBuffer *, GUID *, __int64 **))v13->QueryInterface)(
             a6,
             &IID_INSSBuffer3,
             &v33) >= 0 )
      {
        v34[0] = 0;
        v35 = 1;
        v14 = *v33;
        v32 = WM_SampleExtensionGUID_ContentType;
        if ( (*(int (__fastcall **)(__int64 *, IID *, char *, int *))(v14 + 88))(v33, &v32, v34, &v35) >= 0 && v35 == 1 )
        {
          v15 = 0;
          if ( v34[0] < 0 )
          {
            v15 = 1;
            if ( (v34[0] & 0x40) != 0 )
              v15 = 5;
          }
          SetInterlaceFlagsInMediaType((struct _AMMediaType *)(v11 + 104), v15);
        }
        (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
      }
    }
    if ( *(_DWORD *)(v11 + 412) )
    {
      v16 = a6->lpVtbl;
      v33 = 0;
      if ( ((__int64 (__fastcall *)(struct INSSBuffer *, GUID *, __int64 **))v16->QueryInterface)(
             a6,
             &IID_INSSBuffer3,
             &v33) >= 0 )
      {
        *(_WORD *)v34 = 0;
        v35 = 2;
        v17 = *v33;
        v32 = WM_SampleExtensionGUID_PixelAspectRatio;
        if ( (*(int (__fastcall **)(__int64 *, IID *, char *, int *))(v17 + 88))(v33, &v32, v34, &v35) >= 0 && v35 == 2 )
        {
          v18 = HIBYTE(*(unsigned __int16 *)v34);
          if ( (unsigned __int8)v34[0] != *(unsigned __int8 *)(v11 + 416) || v18 != *(unsigned __int8 *)(v11 + 417) )
          {
            CASFOutput::SetImageAspectRatio((CASFOutput *)v11, (unsigned __int8)v34[0], v18);
            *(_DWORD *)(v11 + 292) = 1;
          }
        }
        (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
      }
    }
  }
  if ( *(_DWORD *)(v11 + 328) )
  {
    v35 = 0;
    v39 = 0;
    v19 = a6->lpVtbl;
    v33 = 0;
    v38 = 0;
    if ( ((__int64 (__fastcall *)(struct INSSBuffer *, GUID *, __int64 **))v19->QueryInterface)(
           a6,
           &IID_INSSBuffer3,
           &v33) >= 0 )
    {
      v35 = 24;
      v20 = *v33;
      v32 = (IID)INSSBuffer3Prop_DShowAttributes;
      if ( (*(int (__fastcall **)(__int64 *, IID *, __int128 *, int *))(v20 + 88))(v33, &v32, &v38, &v35) >= 0
        && (_QWORD)v38 != -1 )
      {
        v37 = v38;
        v21 = 0;
        if ( *((_QWORD *)&v38 + 1) != -1 )
          v21 = *((_QWORD *)&v38 + 1);
        v36 = v21;
      }
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    }
    v22 = *((_QWORD *)this + 2);
    if ( *(_QWORD *)(v22 + 384) )
    {
      v23 = v37 < *(_QWORD *)(v22 + 264);
LABEL_34:
      if ( !v23
        && (*(_QWORD *)&MEDIATYPE_Video.Data1 != *(_QWORD *)(v11 + 104)
         || *(_QWORD *)MEDIATYPE_Video.Data4 != *(_QWORD *)(v11 + 112)
         || *(_DWORD *)(v11 + 320)) )
      {
        goto LABEL_38;
      }
    }
  }
  else
  {
    v24 = (_QWORD *)*((_QWORD *)this + 2);
    v37 = a3 - v24[32];
    v36 = a4 + v37;
    if ( v24[48] )
    {
      v23 = a3 < v24[33];
      goto LABEL_34;
    }
  }
  v25 = 1;
  ++*(_DWORD *)(v11 + 316);
  (*((void (__fastcall **)(struct INSSBufferVtbl *, __int64 *, __int64 *))lpVtbl->QueryInterface + 6))(
    lpVtbl,
    &v37,
    &v36);
  v26 = v36 <= 0;
  if ( *(_DWORD *)(v11 + 288) )
  {
    if ( (a5 & 1) == 0 )
    {
LABEL_38:
      (*((void (__fastcall **)(struct INSSBufferVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
      return 0;
    }
    *(_DWORD *)(v11 + 288) = 0;
    v27 = 1;
  }
  else
  {
    v27 = 0;
  }
  if ( !v26 )
    *(_DWORD *)(v11 + 320) = 1;
  if ( !v27 || (a5 & 1) == 0 )
    v25 = 0;
  (*((void (__fastcall **)(struct INSSBufferVtbl *))lpVtbl->QueryInterface + 8))(lpVtbl);
  (*((void (__fastcall **)(struct INSSBufferVtbl *, _QWORD))lpVtbl->QueryInterface + 16))(lpVtbl, v25);
  (*((void (__fastcall **)(struct INSSBufferVtbl *, BOOL))lpVtbl->QueryInterface + 10))(lpVtbl, v26);
  if ( *(_QWORD *)(v11 + 400) )
  {
    v28 = a6->lpVtbl;
    v33 = 0;
    if ( ((__int64 (__fastcall *)(struct INSSBuffer *, GUID *, __int64 **))v28->QueryInterface)(
           a6,
           &IID_INSSBuffer3,
           &v33) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, __int64 *, __int64, __int64 *, __int64 *))(**(_QWORD **)(v11 + 400) + 24LL))(
        *(_QWORD *)(v11 + 400),
        v33,
        (v11 + 24) & -(__int64)(v11 != 0),
        &v37,
        &v36);
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    }
  }
  if ( *(_DWORD *)(v11 + 292)
    && (*((int (__fastcall **)(struct INSSBufferVtbl *, __int64))lpVtbl->QueryInterface + 14))(lpVtbl, v11 + 104) < 0 )
  {
    (*((void (__fastcall **)(struct INSSBufferVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
  }
  else
  {
    v31 = (*(__int64 (__fastcall **)(__int64, struct INSSBufferVtbl *))(*(_QWORD *)v11 + 136LL))(v11, lpVtbl);
    (*((void (__fastcall **)(struct INSSBufferVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
    if ( !v31 )
    {
      *(_DWORD *)(v11 + 292) = 0;
      return 0;
    }
  }
  v29 = *((_QWORD *)this + 2);
  if ( !_InterlockedIncrement((volatile signed __int32 *)(v29 + 444)) )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v29 + 344) + 88LL))(*(_QWORD *)(v29 + 344));
  return 0;
}

```

## disassembly

```asm
0x18000bdd0  mov     [rsp-38h+arg_8], rbx
0x18000bdd5  push    rbp
0x18000bdd6  push    rsi
0x18000bdd7  push    rdi
0x18000bdd8  push    r12
0x18000bdda  push    r13
0x18000bddc  push    r14
0x18000bdde  push    r15
0x18000bde0  mov     rbp, rsp
0x18000bde3  sub     rsp, 80h
0x18000bdea  mov     rax, cs:__security_cookie
0x18000bdf1  xor     rax, rsp
0x18000bdf4  mov     [rbp+var_8], rax
0x18000bdf8  mov     rbx, [rbp+arg_28]
0x18000bdfc  mov     r15, rcx
0x18000bdff  mov     rcx, [rcx+10h]
0x18000be03  xor     r13d, r13d
0x18000be06  mov     r12, r9
0x18000be09  mov     r14, r8
0x18000be0c  cmp     [rcx+1C8h], r13d
0x18000be13  jnz     loc_18000C23A
0x18000be19  mov     rcx, [rcx+118h]
0x18000be20  test    rcx, rcx
0x18000be23  jz      loc_18000C23A
0x18000be29  mov     rdi, [rcx+10h]
0x18000be2d  cmp     [rdi+130h], edx
0x18000be33  jz      short loc_18000BE41
0x18000be35  mov     rax, [rcx+8]
0x18000be39  mov     rcx, rax
0x18000be3c  test    rax, rax
0x18000be3f  jnz     short loc_18000BE29
0x18000be41  cmp     [rdi+30h], r13
0x18000be45  jz      loc_18000C23A
0x18000be4b  mov     rsi, [rbx+48h]
0x18000be4f  mov     rcx, rsi
0x18000be52  mov     rax, [rsi]
0x18000be55  mov     rax, [rax+8]
0x18000be59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be5e  mov     [rbp+var_28], r13
0x18000be62  mov     [rbp+var_30], r13
0x18000be66  cmp     [rdi+14Ch], r13d
0x18000be6d  jnz     loc_18000BFC5
0x18000be73  cmp     [rdi+198h], r13d
0x18000be7a  jz      loc_18000BF0E
0x18000be80  mov     rax, [rbx]
0x18000be83  lea     r8, [rbp+var_40]
0x18000be87  lea     rdx, IID_INSSBuffer3
0x18000be8e  mov     [rbp+var_40], r13
0x18000be92  mov     rcx, rbx
0x18000be95  mov     rax, [rax]
0x18000be98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be9d  test    eax, eax
0x18000be9f  js      short loc_18000BF0E
0x18000bea1  mov     rcx, [rbp+var_40]
0x18000bea5  lea     r9, [rbp+var_34]
0x18000bea9  movups  xmm0, xmmword ptr cs:WM_SampleExtensionGUID_ContentType.Data1
0x18000beb0  mov     [rbp+var_38], r13b
0x18000beb4  lea     r8, [rbp+var_38]
0x18000beb8  mov     [rbp+var_34], 1
0x18000bebf  lea     rdx, [rbp+var_50]
0x18000bec3  mov     rax, [rcx]
0x18000bec6  movdqu  [rbp+var_50], xmm0
0x18000becb  mov     rax, [rax+58h]
0x18000becf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bed4  test    eax, eax
0x18000bed6  js      short loc_18000BEFE
0x18000bed8  cmp     [rbp+var_34], 1
0x18000bedc  jnz     short loc_18000BEFE
0x18000bede  mov     al, [rbp+var_38]
0x18000bee1  mov     edx, r13d
0x18000bee4  test    al, al
0x18000bee6  jns     short loc_18000BEF5
0x18000bee8  mov     edx, 1
0x18000beed  test    al, 40h
0x18000beef  lea     eax, [rdx+4]
0x18000bef2  cmovnz  edx, eax; unsigned int
0x18000bef5  lea     rcx, [rdi+68h]; struct _AMMediaType *
0x18000bef9  call    ?SetInterlaceFlagsInMediaType@@YAJPEAU_AMMediaType@@K@Z; SetInterlaceFlagsInMediaType(_AMMediaType *,ulong)
0x18000befe  mov     rcx, [rbp+var_40]
0x18000bf02  mov     rax, [rcx]
0x18000bf05  mov     rax, [rax+10h]
0x18000bf09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf0e  cmp     [rdi+19Ch], r13d
0x18000bf15  jz      loc_18000BFC5
0x18000bf1b  mov     rax, [rbx]
0x18000bf1e  lea     r8, [rbp+var_40]
0x18000bf22  lea     rdx, IID_INSSBuffer3
0x18000bf29  mov     [rbp+var_40], r13
0x18000bf2d  mov     rcx, rbx
0x18000bf30  mov     rax, [rax]
0x18000bf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf38  test    eax, eax
0x18000bf3a  js      loc_18000BFC5
0x18000bf40  mov     rcx, [rbp+var_40]
0x18000bf44  lea     r9, [rbp+var_34]
0x18000bf48  movups  xmm0, xmmword ptr cs:WM_SampleExtensionGUID_PixelAspectRatio.Data1
0x18000bf4f  mov     word ptr [rbp+var_38], r13w
0x18000bf54  lea     r8, [rbp+var_38]
0x18000bf58  mov     [rbp+var_34], 2
0x18000bf5f  lea     rdx, [rbp+var_50]
0x18000bf63  mov     rax, [rcx]
0x18000bf66  movdqu  [rbp+var_50], xmm0
0x18000bf6b  mov     rax, [rax+58h]
0x18000bf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf74  test    eax, eax
0x18000bf76  js      short loc_18000BFB5
0x18000bf78  cmp     [rbp+var_34], 2
0x18000bf7c  jnz     short loc_18000BFB5
0x18000bf7e  movzx   eax, word ptr [rbp+var_38]
0x18000bf82  mov     r8d, eax
0x18000bf85  movzx   edx, al; int
0x18000bf88  movzx   eax, byte ptr [rdi+1A0h]
0x18000bf8f  shr     r8d, 8; int
0x18000bf93  cmp     edx, eax
0x18000bf95  jnz     short loc_18000BFA3
0x18000bf97  movzx   eax, byte ptr [rdi+1A1h]
0x18000bf9e  cmp     r8d, eax
0x18000bfa1  jz      short loc_18000BFB5
0x18000bfa3  mov     rcx, rdi; this
0x18000bfa6  call    ?SetImageAspectRatio@CASFOutput@@QEAAJJJ@Z; CASFOutput::SetImageAspectRatio(long,long)
0x18000bfab  mov     dword ptr [rdi+124h], 1
0x18000bfb5  mov     rcx, [rbp+var_40]
0x18000bfb9  mov     rax, [rcx]
0x18000bfbc  mov     rax, [rax+10h]
0x18000bfc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc5  cmp     [rdi+148h], r13d
0x18000bfcc  jz      loc_18000C0B2
0x18000bfd2  xor     eax, eax
0x18000bfd4  mov     [rbp+var_34], r13d
0x18000bfd8  mov     [rbp+var_10], rax
0x18000bfdc  lea     r8, [rbp+var_40]
0x18000bfe0  mov     rax, [rbx]
0x18000bfe3  lea     rdx, IID_INSSBuffer3
0x18000bfea  xorps   xmm0, xmm0
0x18000bfed  mov     [rbp+var_40], r13
0x18000bff1  mov     rcx, rbx
0x18000bff4  movups  [rbp+var_20], xmm0
0x18000bff8  mov     rax, [rax]
0x18000bffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c000  test    eax, eax
0x18000c002  js      short loc_18000C066
0x18000c004  mov     rcx, [rbp+var_40]
0x18000c008  lea     r9, [rbp+var_34]
0x18000c00c  movups  xmm0, cs:INSSBuffer3Prop_DShowAttributes
0x18000c013  mov     [rbp+var_34], 18h
0x18000c01a  lea     r8, [rbp+var_20]
0x18000c01e  lea     rdx, [rbp+var_50]
0x18000c022  mov     rax, [rcx]
0x18000c025  movdqu  [rbp+var_50], xmm0
0x18000c02a  mov     rax, [rax+58h]
0x18000c02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c033  test    eax, eax
0x18000c035  js      short loc_18000C056
0x18000c037  mov     rax, qword ptr [rbp+var_20]
0x18000c03b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c03f  jz      short loc_18000C056
0x18000c041  cmp     qword ptr [rbp+var_20+8], 0FFFFFFFFFFFFFFFFh
0x18000c046  mov     [rbp+var_28], rax
0x18000c04a  mov     rax, r13
0x18000c04d  cmovnz  rax, qword ptr [rbp+var_20+8]
0x18000c052  mov     [rbp+var_30], rax
0x18000c056  mov     rcx, [rbp+var_40]
0x18000c05a  mov     rax, [rcx]
0x18000c05d  mov     rax, [rax+10h]
0x18000c061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c066  mov     rax, [r15+10h]
0x18000c06a  cmp     [rax+180h], r13
0x18000c071  jz      short loc_18000C0DD
0x18000c073  mov     rax, [rax+108h]
0x18000c07a  cmp     [rbp+var_28], rax
0x18000c07e  jl      short loc_18000C0DD
0x18000c080  mov     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x18000c087  cmp     rax, [rdi+68h]
0x18000c08b  jnz     short loc_18000C0A3
0x18000c08d  mov     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x18000c094  cmp     rax, [rdi+70h]
0x18000c098  jnz     short loc_18000C0A3
0x18000c09a  cmp     [rdi+140h], r13d
0x18000c0a1  jz      short loc_18000C0DD
0x18000c0a3  mov     rax, [rsi]
0x18000c0a6  mov     rcx, rsi
0x18000c0a9  mov     rax, [rax+10h]
0x18000c0ad  jmp     loc_18000C235
0x18000c0b2  mov     rcx, [r15+10h]
0x18000c0b6  mov     rax, r14
0x18000c0b9  sub     rax, [rcx+100h]
0x18000c0c0  mov     [rbp+var_28], rax
0x18000c0c4  add     rax, r12
0x18000c0c7  mov     [rbp+var_30], rax
0x18000c0cb  cmp     [rcx+180h], r13
0x18000c0d2  jz      short loc_18000C0DD
0x18000c0d4  cmp     r14, [rcx+108h]
0x18000c0db  jmp     short loc_18000C07E
0x18000c0dd  mov     r14d, 1
0x18000c0e3  lea     r8, [rbp+var_30]
0x18000c0e7  add     [rdi+13Ch], r14d
0x18000c0ee  lea     rdx, [rbp+var_28]
0x18000c0f2  mov     rax, [rsi]
0x18000c0f5  mov     rcx, rsi
0x18000c0f8  mov     rax, [rax+30h]
0x18000c0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c101  mov     eax, dword ptr [rbp+arg_20]
0x18000c104  mov     r12d, r13d
0x18000c107  mov     edx, eax
0x18000c109  and     edx, r14d
0x18000c10c  cmp     [rbp+var_30], r13
0x18000c110  setle   r12b
0x18000c114  cmp     [rdi+120h], r13d
0x18000c11b  jz      short loc_18000C12D
0x18000c11d  test    edx, edx
0x18000c11f  jz      short loc_18000C0A3
0x18000c121  mov     [rdi+120h], r13d
0x18000c128  mov     eax, r14d
0x18000c12b  jmp     short loc_18000C130
0x18000c12d  mov     eax, r13d
0x18000c130  test    r12d, r12d
0x18000c133  jnz     short loc_18000C13C
0x18000c135  mov     [rdi+140h], r14d
0x18000c13c  test    eax, eax
0x18000c13e  jz      short loc_18000C144
0x18000c140  test    edx, edx
0x18000c142  jnz     short loc_18000C147
0x18000c144  mov     r14d, r13d
0x18000c147  mov     rax, [rsi]
0x18000c14a  mov     rcx, rsi
0x18000c14d  mov     rax, [rax+40h]
0x18000c151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c156  mov     rax, [rsi]
0x18000c159  mov     edx, r14d
0x18000c15c  mov     rcx, rsi
0x18000c15f  mov     rax, [rax+80h]
0x18000c166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c16b  mov     rax, [rsi]
0x18000c16e  mov     edx, r12d
0x18000c171  mov     rcx, rsi
0x18000c174  mov     rax, [rax+50h]
0x18000c178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17d  cmp     [rdi+190h], r13
0x18000c184  jz      short loc_18000C1EB
0x18000c186  mov     rax, [rbx]
0x18000c189  lea     r8, [rbp+var_40]
0x18000c18d  lea     rdx, IID_INSSBuffer3
0x18000c194  mov     [rbp+var_40], r13
0x18000c198  mov     rcx, rbx
0x18000c19b  mov     rax, [rax]
0x18000c19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a3  test    eax, eax
0x18000c1a5  js      short loc_18000C1EB
0x18000c1a7  mov     rcx, [rdi+190h]
0x18000c1ae  lea     rdx, [rdi+18h]
0x18000c1b2  mov     rax, rdi
0x18000c1b5  neg     rax
0x18000c1b8  mov     r9, [rcx]
0x18000c1bb  sbb     r8, r8
0x18000c1be  and     r8, rdx
0x18000c1c1  lea     rdx, [rbp+var_30]
0x18000c1c5  mov     [rsp+80h+var_60], rdx
0x18000c1ca  mov     rdx, [rbp+var_40]
0x18000c1ce  mov     rax, [r9+18h]
0x18000c1d2  lea     r9, [rbp+var_28]
0x18000c1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1db  mov     rcx, [rbp+var_40]
0x18000c1df  mov     rax, [rcx]
0x18000c1e2  mov     rax, [rax+10h]
0x18000c1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1eb  cmp     [rdi+124h], r13d
0x18000c1f2  jz      short loc_18000C263
0x18000c1f4  mov     rax, [rsi]
0x18000c1f7  lea     rdx, [rdi+68h]
0x18000c1fb  mov     rcx, rsi
0x18000c1fe  mov     rax, [rax+70h]
0x18000c202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c207  test    eax, eax
0x18000c209  jns     short loc_18000C263
0x18000c20b  mov     rax, [rsi]
0x18000c20e  mov     rcx, rsi
0x18000c211  mov     rax, [rax+10h]
0x18000c215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c21a  mov     rcx, [r15+10h]
0x18000c21e  lock inc dword ptr [rcx+1BCh]
0x18000c225  jnz     short loc_18000C23A
0x18000c227  mov     rcx, [rcx+158h]
0x18000c22e  mov     rax, [rcx]
0x18000c231  mov     rax, [rax+58h]
0x18000c235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23a  xor     eax, eax
0x18000c23c  mov     rcx, [rbp+var_8]
0x18000c240  xor     rcx, rsp; StackCookie
0x18000c243  call    __security_check_cookie
0x18000c248  mov     rbx, [rsp+80h+arg_8]
0x18000c250  add     rsp, 80h
0x18000c257  pop     r15
0x18000c259  pop     r14
0x18000c25b  pop     r13
0x18000c25d  pop     r12
0x18000c25f  pop     rdi
0x18000c260  pop     rsi
0x18000c261  pop     rbp
0x18000c262  retn
0x18000c263  mov     rax, [rdi]
  ... truncated ...
```
