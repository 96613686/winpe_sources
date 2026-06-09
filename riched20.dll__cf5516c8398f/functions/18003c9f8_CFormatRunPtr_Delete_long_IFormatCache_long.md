# CFormatRunPtr::Delete(long,IFormatCache *,long)

- ea: `0x18003c9f8`
- end: `0x18003cd7e`
- name: `?Delete@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@J@Z`
- size: `902`
- prototype: `void __fastcall(CFormatRunPtr *__hidden this, int, struct IFormatCache *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800194c0`

## callees

- `0x1800064d0`
- `0x180010510`
- `0x18001aa50`
- `0x18001dfd0`
- `0x180026e20`
- `0x180027f70`
- `0x18003c9f8`
- `0x18003ffd4`
- `0x180092010`

## pseudocode

```c
void __fastcall CFormatRunPtr::Delete(CFormatRunPtr *this, int a2, struct IFormatCache *a3, int a4)
{
  __int64 v6; // rcx
  int v7; // r9d
  __int64 v8; // rdi
  struct IFormatCache *v9; // r13
  int v10; // ebx
  int v11; // eax
  int *v12; // r12
  __int128 v13; // xmm1
  int v14; // r10d
  __int64 v15; // rcx
  int v16; // r14d
  int v17; // r8d
  __int16 v18; // di
  int v19; // eax
  int v20; // eax
  int v21; // r10d
  int v22; // r14d
  _DWORD *v23; // rax
  int v24; // ecx
  bool v25; // zf
  int v26; // r9d
  int v27; // r13d
  int v28; // r12d
  int v29; // r9d
  CArrayBase *v30; // r10
  __int16 *v31; // rax
  CArrayBase *v32; // rcx
  int v33; // r9d
  __int64 v34; // r10
  __int16 v35; // bx
  int v36; // eax
  __int16 *v37; // rax
  __int64 v38; // r9
  int v39; // r11d
  _DWORD *v40; // rax
  _DWORD *v41; // rax
  int v42; // edx
  CArrayBase *v43; // rcx
  _DWORD *v44; // rax
  int v45; // edx
  CArrayBase *v46; // rcx
  int v47; // r9d
  int v48; // [rsp+24h] [rbp-1Ch]
  int v49; // [rsp+28h] [rbp-18h]
  CArrayBase *v50[2]; // [rsp+30h] [rbp-10h] BYREF
  __int16 v51; // [rsp+88h] [rbp+48h]

  v6 = *(_QWORD *)this;
  v7 = a2;
  v8 = 0;
  v9 = a3;
  v10 = *((_DWORD *)this + 2);
  v11 = *(_DWORD *)(v6 + 8);
  v48 = v11 - 1;
  if ( v11 > 0 && v10 < v11 && *(_QWORD *)v6 && v10 >= 0 )
    v12 = (int *)(*(_QWORD *)v6 + *(_DWORD *)(v6 + 16) * v10);
  else
    v12 = 0;
  v13 = *(_OWORD *)this;
  v14 = *v12;
  v15 = *((_QWORD *)this + 1);
  v16 = *v12 - *((_DWORD *)this + 3);
  v49 = *((_DWORD *)this + 3);
  v51 = 0;
  *(_OWORD *)v50 = *(_OWORD *)this;
  if ( HIDWORD(v15) || !(_QWORD)v13 )
  {
    LODWORD(v15) = v50[1];
  }
  else if ( (int)v15 > 0 )
  {
    LODWORD(v15) = v15 - 1;
  }
  v17 = *(_DWORD *)(v13 + 8);
  if ( v17 > 0 && (int)v15 < v17 && *(_QWORD *)v13 && (int)v15 >= 0 )
    v8 = *(_QWORD *)v13 + *(_DWORD *)(v13 + 16) * (int)v15;
  v18 = *(_WORD *)(v8 + 6);
  v19 = v11 - 1;
  *(_OWORD *)v50 = v13;
  if ( v10 == v48 )
  {
    v20 = v16;
    if ( a2 < v16 )
      v20 = a2;
    v7 = v20;
    v19 = v48;
  }
  if ( v7 > v16 )
  {
    CRunPtrBase::AdvanceCp((CRunPtrBase *)v50, v7);
    v23 = CArrayBase::Elem(v50[0], (int)v50[1]);
    v24 = HIDWORD(v50[1]);
    v25 = HIDWORD(v50[1]) == *v23;
    *v12 = v49;
    *v23 -= v24;
    HIDWORD(v50[1]) = 0;
    v22 = v26 + v25 - v10;
    goto LABEL_30;
  }
  v21 = v14 - v7;
  *v12 = v21;
  if ( !a4 )
  {
    if ( v21 )
      return;
    if ( !*((_DWORD *)this + 2) || (v22 = 1, v10 == v19) )
    {
      CRunPtrBase::AdjustBackward(this);
      v22 = (*((_DWORD *)this + 3) != 0) + 1;
    }
    CRunPtrBase::NextRun((CRunPtrBase *)v50);
LABEL_30:
    v27 = 0;
    v28 = -3;
    if ( (unsigned int)CRunPtrBase::IsValid((CRunPtrBase *)v50) )
    {
      v31 = (__int16 *)CArrayBase::Elem(v30, v29);
      if ( *(_DWORD *)v31 )
      {
LABEL_32:
        v35 = v31[3];
        v28 = v31[2];
        v27 = *(_DWORD *)v31;
        v51 = v35;
        goto LABEL_36;
      }
      if ( v33 != *(_DWORD *)(v34 + 8) - 1 )
      {
        v31 = (__int16 *)CArrayBase::Elem(v32, v33 + 1);
        goto LABEL_32;
      }
    }
    v35 = 0;
LABEL_36:
    v36 = *((_DWORD *)this + 3);
    *(_OWORD *)v50 = *(_OWORD *)this;
    if ( v36 )
    {
      if ( !(a4 + v36) )
      {
        (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))a3)(a3, (unsigned int)v28);
        v37 = (__int16 *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2));
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(v38 + 8))(a3, (unsigned int)v37[2]);
        *((_WORD *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2)) + 2) = v28;
        a4 = 0;
        *((_WORD *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2)) + 3) = v35;
      }
      CRunPtrBase::NextRun((CRunPtrBase *)v50);
      --v22;
    }
    CRunPtrBase::AdjustBackward(this);
    if ( v28 >= 0 && v28 == v39 && (_BYTE)v18 == (_BYTE)v51 && ((HIBYTE(v18) ^ HIBYTE(v51)) & 1) == 0 )
    {
      v40 = CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2));
      *v40 += v27;
      ++v22;
    }
    v9 = a3;
    if ( v22 > 0 )
    {
      CFormatRunPtr::Remove((CFormatRunPtr *)v50, v22, a3);
      if ( !*(_DWORD *)(*(_QWORD *)this + 8LL) )
        *((_QWORD *)this + 1) = 0;
    }
    if ( !a4 )
      goto LABEL_56;
    goto LABEL_49;
  }
  CRunPtrBase::AdjustForward((CRunPtrBase *)v50);
LABEL_49:
  v41 = CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2));
  v42 = (int)v50[1];
  v43 = v50[0];
  *v41 += a4;
  v44 = CArrayBase::Elem(v43, v42);
  v45 = (int)v50[1];
  *v44 -= a4;
  if ( !*(_DWORD *)CArrayBase::Elem(v46, v45) )
    CFormatRunPtr::Remove((CFormatRunPtr *)v50, 1, v9);
  if ( a4 < 0 )
  {
    if ( *(_DWORD *)CArrayBase::Elem(*(CArrayBase **)this, *((_DWORD *)this + 2)) )
      *((_DWORD *)this + 2) = v47 + 1;
    else
      CFormatRunPtr::Remove(this, 1, v9);
    *((_DWORD *)this + 3) = -a4;
  }
LABEL_56:
  CRunPtrBase::AdjustForward(this);
}

```

## disassembly

```asm
0x18003c9f8  mov     [rsp-38h+arg_18], rbx
0x18003c9fd  mov     [rsp-38h+arg_10], r8
0x18003ca02  push    rbp
0x18003ca03  push    rsi
0x18003ca04  push    rdi
0x18003ca05  push    r12
0x18003ca07  push    r13
0x18003ca09  push    r14
0x18003ca0b  push    r15
0x18003ca0d  mov     rbp, rsp
0x18003ca10  sub     rsp, 40h
0x18003ca14  mov     rsi, rcx
0x18003ca17  mov     r15d, r9d
0x18003ca1a  mov     rcx, [rcx]
0x18003ca1d  mov     r9d, edx
0x18003ca20  xor     edi, edi
0x18003ca22  mov     r13, r8
0x18003ca25  mov     ebx, [rsi+8]
0x18003ca28  mov     eax, [rcx+8]
0x18003ca2b  lea     edx, [rax-1]
0x18003ca2e  mov     [rbp+var_1C], edx
0x18003ca31  test    eax, eax
0x18003ca33  jle     short loc_18003CA50
0x18003ca35  cmp     ebx, eax
0x18003ca37  jge     short loc_18003CA50
0x18003ca39  cmp     [rcx], rdi
0x18003ca3c  jz      short loc_18003CA50
0x18003ca3e  test    ebx, ebx
0x18003ca40  js      short loc_18003CA50
0x18003ca42  mov     eax, ebx
0x18003ca44  imul    eax, [rcx+10h]
0x18003ca48  movsxd  r12, eax
0x18003ca4b  add     r12, [rcx]
0x18003ca4e  jmp     short loc_18003CA53
0x18003ca50  mov     r12, rdi
0x18003ca53  mov     eax, [rsi+0Ch]
0x18003ca56  movups  xmm1, xmmword ptr [rsi]
0x18003ca59  mov     r10d, [r12]
0x18003ca5d  mov     r14d, r10d
0x18003ca60  mov     rcx, [rsi+8]
0x18003ca64  sub     r14d, eax
0x18003ca67  mov     [rbp+var_18], eax
0x18003ca6a  movq    rdx, xmm1
0x18003ca6f  mov     rax, rcx
0x18003ca72  mov     [rbp+arg_8], di
0x18003ca76  shr     rax, 20h
0x18003ca7a  movups  xmmword ptr [rbp+var_10], xmm1
0x18003ca7e  test    eax, eax
0x18003ca80  jnz     short loc_18003CA8F
0x18003ca82  test    rdx, rdx
0x18003ca85  jz      short loc_18003CA8F
0x18003ca87  test    ecx, ecx
0x18003ca89  jle     short loc_18003CA92
0x18003ca8b  dec     ecx
0x18003ca8d  jmp     short loc_18003CA92
0x18003ca8f  mov     ecx, dword ptr [rbp+var_10+8]
0x18003ca92  mov     r8d, [rdx+8]
0x18003ca96  test    r8d, r8d
0x18003ca99  jle     short loc_18003CAB7
0x18003ca9b  cmp     ecx, r8d
0x18003ca9e  jge     short loc_18003CAB7
0x18003caa0  cmp     [rdx], rdi
0x18003caa3  jz      short loc_18003CAB7
0x18003caa5  test    ecx, ecx
0x18003caa7  js      short loc_18003CAB7
0x18003caa9  mov     eax, ecx
0x18003caab  imul    eax, [rdx+10h]
0x18003caaf  movsxd  r11, eax
0x18003cab2  add     r11, [rdx]
0x18003cab5  jmp     short loc_18003CABA
0x18003cab7  mov     r11, rdi
0x18003caba  movsx   r11d, word ptr [r11+4]
0x18003cabf  mov     [rbp+var_20], r11d
0x18003cac3  test    r8d, r8d
0x18003cac6  jle     short loc_18003CAE0
0x18003cac8  cmp     ecx, r8d
0x18003cacb  jge     short loc_18003CAE0
0x18003cacd  cmp     [rdx], rdi
0x18003cad0  jz      short loc_18003CAE0
0x18003cad2  test    ecx, ecx
0x18003cad4  js      short loc_18003CAE0
0x18003cad6  imul    ecx, [rdx+10h]
0x18003cada  movsxd  rdi, ecx
0x18003cadd  add     rdi, [rdx]
0x18003cae0  movzx   edi, word ptr [rdi+6]
0x18003cae4  mov     eax, [rbp+var_1C]
0x18003cae7  mov     [rbp+arg_0], di
0x18003caeb  movdqu  xmmword ptr [rbp+var_10], xmm1
0x18003caf0  cmp     ebx, eax
0x18003caf2  jnz     short loc_18003CB04
0x18003caf4  cmp     r9d, r14d
0x18003caf7  mov     eax, r14d
0x18003cafa  cmovl   eax, r9d
0x18003cafe  mov     r9d, eax
0x18003cb01  mov     eax, [rbp+var_1C]
0x18003cb04  cmp     r9d, r14d
0x18003cb07  jg      short loc_18003CB6C
0x18003cb09  sub     r10d, r9d
0x18003cb0c  mov     [r12], r10d
0x18003cb10  xor     r12d, r12d
0x18003cb13  test    r15d, r15d
0x18003cb16  jz      short loc_18003CB26
0x18003cb18  lea     rcx, [rbp+var_10]; this
0x18003cb1c  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18003cb21  jmp     loc_18003CCEA
0x18003cb26  test    r10d, r10d
0x18003cb29  jnz     loc_18003CD66
0x18003cb2f  cmp     [rsi+8], r12d
0x18003cb33  jz      short loc_18003CB3D
0x18003cb35  lea     r14d, [r10+1]
0x18003cb39  cmp     ebx, eax
0x18003cb3b  jnz     short loc_18003CB59
0x18003cb3d  mov     rcx, rsi; this
0x18003cb40  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x18003cb45  mov     eax, [rsi+0Ch]
0x18003cb48  mov     r11d, 0FFFFFFFEh
0x18003cb4e  neg     eax
0x18003cb50  sbb     r14d, r14d
0x18003cb53  neg     r14d
0x18003cb56  inc     r14d
0x18003cb59  lea     rcx, [rbp+var_10]; this
0x18003cb5d  call    ?NextRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::NextRun(void)
0x18003cb62  mov     r9d, dword ptr [rbp+var_10+8]
0x18003cb66  mov     r10, [rbp+var_10]
0x18003cb6a  jmp     short loc_18003CBC0
0x18003cb6c  mov     edx, r9d; int
0x18003cb6f  lea     rcx, [rbp+var_10]; this
0x18003cb73  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18003cb78  mov     r10, [rbp+var_10]
0x18003cb7c  mov     r9d, dword ptr [rbp+var_10+8]
0x18003cb80  mov     rcx, r10; this
0x18003cb83  mov     edx, r9d; int
0x18003cb86  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cb8b  mov     ecx, dword ptr [rbp+var_10+0Ch]
0x18003cb8e  xor     r14d, r14d
0x18003cb91  mov     edx, [rbp+var_18]
0x18003cb94  cmp     ecx, [rax]
0x18003cb96  mov     [r12], edx
0x18003cb9a  setz    r14b
0x18003cb9e  sub     [rax], ecx
0x18003cba0  mov     eax, [rbp+var_20]
0x18003cba3  xor     r12d, r12d
0x18003cba6  sub     r14d, ebx
0x18003cba9  mov     dword ptr [rbp+var_10+0Ch], r12d
0x18003cbad  add     r14d, r9d
0x18003cbb0  cmp     [rsi+8], r12d
0x18003cbb4  lea     r11d, [r12-2]
0x18003cbb9  cmovz   eax, r11d
0x18003cbbd  mov     r11d, eax
0x18003cbc0  mov     r13d, r12d
0x18003cbc3  lea     rcx, [rbp+var_10]; this
0x18003cbc7  mov     r12d, 0FFFFFFFDh
0x18003cbcd  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x18003cbd2  test    eax, eax
0x18003cbd4  jz      short loc_18003CC0E
0x18003cbd6  mov     edx, r9d; int
0x18003cbd9  mov     rcx, r10; this
0x18003cbdc  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cbe1  cmp     dword ptr [rax], 0
0x18003cbe4  jz      short loc_18003CBF8
0x18003cbe6  movzx   ebx, word ptr [rax+6]
0x18003cbea  movsx   r12d, word ptr [rax+4]
0x18003cbef  mov     r13d, [rax]
0x18003cbf2  mov     [rbp+arg_8], bx
0x18003cbf6  jmp     short loc_18003CC12
0x18003cbf8  mov     eax, [r10+8]
0x18003cbfc  dec     eax
0x18003cbfe  cmp     r9d, eax
0x18003cc01  jz      short loc_18003CC0E
0x18003cc03  lea     edx, [r9+1]; int
0x18003cc07  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cc0c  jmp     short loc_18003CBE6
0x18003cc0e  movzx   ebx, [rbp+arg_8]
0x18003cc12  movups  xmm0, xmmword ptr [rsi]
0x18003cc15  mov     eax, [rsi+0Ch]
0x18003cc18  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18003cc1d  test    eax, eax
0x18003cc1f  jz      short loc_18003CC8A
0x18003cc21  add     eax, r15d
0x18003cc24  jnz     short loc_18003CC7E
0x18003cc26  mov     r15, [rbp+arg_10]
0x18003cc2a  mov     edx, r12d
0x18003cc2d  mov     rcx, r15
0x18003cc30  mov     rax, [r15]
0x18003cc33  mov     rax, [rax]
0x18003cc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc3b  mov     edx, [rsi+8]; int
0x18003cc3e  mov     rcx, [rsi]; this
0x18003cc41  mov     r9, [r15]
0x18003cc44  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cc49  mov     rcx, r15
0x18003cc4c  movsx   edx, word ptr [rax+4]
0x18003cc50  mov     rax, [r9+8]
0x18003cc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc59  mov     edx, [rsi+8]; int
0x18003cc5c  mov     rcx, [rsi]; this
0x18003cc5f  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cc64  mov     [rax+4], r12w
0x18003cc69  mov     edx, [rsi+8]; int
0x18003cc6c  mov     rcx, [rsi]; this
0x18003cc6f  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cc74  xor     r15d, r15d
0x18003cc77  mov     r11d, r12d
0x18003cc7a  mov     [rax+6], bx
0x18003cc7e  lea     rcx, [rbp+var_10]; this
0x18003cc82  call    ?NextRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::NextRun(void)
0x18003cc87  dec     r14d
0x18003cc8a  mov     rcx, rsi; this
0x18003cc8d  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x18003cc92  test    r12d, r12d
0x18003cc95  js      short loc_18003CCBD
0x18003cc97  cmp     r12d, r11d
0x18003cc9a  jnz     short loc_18003CCBD
0x18003cc9c  cmp     dil, byte ptr [rbp+arg_8]
0x18003cca0  jnz     short loc_18003CCBD
0x18003cca2  mov     al, byte ptr [rbp+arg_8+1]
0x18003cca5  xor     al, byte ptr [rbp+arg_0+1]
0x18003cca8  test    al, 1
0x18003ccaa  jnz     short loc_18003CCBD
0x18003ccac  mov     edx, [rsi+8]; int
0x18003ccaf  mov     rcx, [rsi]; this
0x18003ccb2  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003ccb7  add     [rax], r13d
0x18003ccba  inc     r14d
0x18003ccbd  mov     r13, [rbp+arg_10]
0x18003ccc1  xor     r12d, r12d
0x18003ccc4  test    r14d, r14d
0x18003ccc7  jle     short loc_18003CCE5
0x18003ccc9  mov     r8, r13; struct IFormatCache *
0x18003cccc  lea     rcx, [rbp+var_10]; this
0x18003ccd0  mov     edx, r14d; int
0x18003ccd3  call    ?Remove@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@@Z; CFormatRunPtr::Remove(long,IFormatCache *)
0x18003ccd8  mov     rax, [rsi]
0x18003ccdb  cmp     [rax+8], r12d
0x18003ccdf  jnz     short loc_18003CCE5
0x18003cce1  mov     [rsi+8], r12
0x18003cce5  test    r15d, r15d
0x18003cce8  jz      short loc_18003CD5E
0x18003ccea  mov     edx, [rsi+8]; int
0x18003cced  mov     rcx, [rsi]; this
0x18003ccf0  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003ccf5  mov     edx, dword ptr [rbp+var_10+8]; int
0x18003ccf8  mov     rcx, [rbp+var_10]; this
0x18003ccfc  add     [rax], r15d
0x18003ccff  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cd04  mov     edx, dword ptr [rbp+var_10+8]; int
0x18003cd07  sub     [rax], r15d
0x18003cd0a  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cd0f  cmp     [rax], r12d
0x18003cd12  jnz     short loc_18003CD25
0x18003cd14  mov     r8, r13; struct IFormatCache *
0x18003cd17  lea     rcx, [rbp+var_10]; this
0x18003cd1b  mov     edx, 1; int
0x18003cd20  call    ?Remove@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@@Z; CFormatRunPtr::Remove(long,IFormatCache *)
0x18003cd25  test    r15d, r15d
0x18003cd28  jns     short loc_18003CD5E
0x18003cd2a  mov     r9d, [rsi+8]
0x18003cd2e  mov     edx, r9d; int
0x18003cd31  mov     rcx, [rsi]; this
0x18003cd34  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18003cd39  cmp     [rax], r12d
0x18003cd3c  jnz     short loc_18003CD50
0x18003cd3e  mov     r8, r13; struct IFormatCache *
0x18003cd41  mov     edx, 1; int
0x18003cd46  mov     rcx, rsi; this
0x18003cd49  call    ?Remove@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@@Z; CFormatRunPtr::Remove(long,IFormatCache *)
0x18003cd4e  jmp     short loc_18003CD57
0x18003cd50  lea     eax, [r9+1]
0x18003cd54  mov     [rsi+8], eax
0x18003cd57  neg     r15d
0x18003cd5a  mov     [rsi+0Ch], r15d
0x18003cd5e  mov     rcx, rsi; this
0x18003cd61  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18003cd66  mov     rbx, [rsp+40h+arg_18]
0x18003cd6e  add     rsp, 40h
0x18003cd72  pop     r15
0x18003cd74  pop     r14
0x18003cd76  pop     r13
0x18003cd78  pop     r12
0x18003cd7a  pop     rdi
0x18003cd7b  pop     rsi
0x18003cd7c  pop     rbp
0x18003cd7d  retn
```
