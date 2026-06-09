# CGatherPropertyBag::AddProperty(tagFULLPROPSPEC const *,tagGATHER_CHUNK_ATTRIBUTES const *,tagPROPVARIANT const *)

- ea: `0x180008d9c`
- end: `0x1800091ae`
- name: `?AddProperty@CGatherPropertyBag@@QEAAJPEBUtagFULLPROPSPEC@@PEBUtagGATHER_CHUNK_ATTRIBUTES@@PEBUtagPROPVARIANT@@@Z`
- size: `1042`
- prototype: `int(CGatherPropertyBag *__hidden this, const struct tagFULLPROPSPEC *, const struct tagGATHER_CHUNK_ATTRIBUTES *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800071a0`

## callees

- `0x180008d9c`
- `0x1800091b4`
- `0x18002751c`
- `0x180094d3c`
- `0x18009dd4c`
- `0x1800e2374`
- `0x180124d80`
- `0x1801b1f98`
- `0x1801b2368`
- `0x1801b2424`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000903b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000903b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090f5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008ec5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008f80`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008ec5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180008f80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008f32`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008f32`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGatherPropertyBag::AddProperty(
        CGatherPropertyBag *this,
        const struct tagFULLPROPSPEC *a2,
        const struct tagGATHER_CHUNK_ATTRIBUTES *a3,
        const PROPVARIANT *a4)
{
  char *v8; // r13
  __int64 v9; // rdi
  unsigned int v10; // ebx
  _QWORD *v11; // rdi
  _QWORD *v12; // rbx
  __int64 *v13; // rbx
  __int64 v14; // rbx
  GUID *v15; // rax
  __int64 v16; // rdx
  GUID *v17; // rbx
  ULONG ulKind; // eax
  HRESULT v19; // eax
  signed int v20; // edi
  _OWORD *v22; // rsi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // edx
  bool v28; // zf
  int v29; // eax
  signed int v30; // eax
  signed int LastError; // eax
  __int64 v32; // rsi
  unsigned int v33; // edi
  unsigned int v34; // eax
  __int64 v35; // rax
  CGatherResourceProperty *v36; // rsi
  signed int v37; // eax
  int v38; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v8 = (char *)this + 24;
  if ( *((_DWORD *)this + 13) >= 0x400u )
    return 2147749296LL;
  v9 = *((_QWORD *)this + 9);
  v10 = *((_DWORD *)this + 12);
  v11 = (_QWORD *)(32LL * ((*((unsigned int (__fastcall **)(const struct tagFULLPROPSPEC *))this + 5))(a2) % v10) + v9);
  if ( v11 )
  {
    v12 = v11;
    while ( 1 )
    {
      while ( 1 )
      {
        v12 = (_QWORD *)*v12;
        if ( v12 == v11 + 1 || !v12 )
          goto LABEL_5;
        v24 = v12[2];
        v25 = *(_QWORD *)&a2->guidPropSet.Data1 - *(_QWORD *)v24;
        if ( *(_QWORD *)&a2->guidPropSet.Data1 == *(_QWORD *)v24 )
          v25 = *(_QWORD *)a2->guidPropSet.Data4 - *(_QWORD *)(v24 + 8);
        if ( !v25 )
        {
          v26 = *(_DWORD *)(v24 + 16);
          if ( a2->psProperty.ulKind == v26 )
            break;
        }
      }
      if ( !v26 )
        break;
      if ( v26 == 1 )
      {
        v27 = 0;
        v28 = *(_DWORD *)(v24 + 24) == LODWORD(a2->psProperty.propid);
LABEL_38:
        LOBYTE(v27) = v28;
        if ( v27 )
        {
          v13 = v12 + 1;
          goto LABEL_6;
        }
      }
    }
    v29 = _o__wcsicmp(*(_QWORD *)(v24 + 24), a2->psProperty.propid);
    v27 = 0;
    v28 = v29 == 0;
    goto LABEL_38;
  }
LABEL_5:
  v13 = (__int64 *)&`CTPtrKPtrSList<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Lookup'::`2'::pNULL;
LABEL_6:
  v14 = *v13;
  if ( v14 )
  {
    v22 = (_OWORD *)(v14 + 32);
    if ( *(_DWORD *)(v14 + 56) != 3 )
      PropVariantClear((PROPVARIANT *)(v14 + 32));
    *(_DWORD *)(v14 + 56) = *(_DWORD *)a3;
    *(_DWORD *)(v14 + 72) = *((_DWORD *)a3 + 4);
    *(_DWORD *)(v14 + 76) = *((_DWORD *)a3 + 5);
    *(_DWORD *)(v14 + 80) = *((_DWORD *)a3 + 6);
    *(_QWORD *)(v14 + 64) = 0;
    v23 = *((_QWORD *)a3 + 1);
    if ( v23 )
    {
      CLMString::operator=(v14 + 88, v23);
      *(_QWORD *)(v14 + 64) = *(_QWORD *)(v14 + 96);
    }
    if ( *(_DWORD *)(v14 + 56) == 3 )
    {
      v20 = 0;
      *v22 = *(_OWORD *)a4;
      *(PROPVARIANT *)(v14 + 48) = a4[2];
    }
    else
    {
      *v22 = 0;
      *(_QWORD *)(v14 + 48) = 0;
      return (unsigned int)PropVariantCopy((PROPVARIANT *)(v14 + 32), a4);
    }
  }
  else
  {
    v15 = (GUID *)operator new(0x138u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v15;
    if ( v15 )
    {
      *v15 = a2->guidPropSet;
      ulKind = a2->psProperty.ulKind;
      if ( ulKind )
      {
        v17[1].Data1 = ulKind;
        *(_DWORD *)v17[1].Data4 = a2->psProperty.propid;
      }
      else
      {
        v17[1].Data1 = 1;
        CFullPropSpecWrapper::SetProperty((CFullPropSpecWrapper *)v17, a2->psProperty.lpwstr);
      }
      *(_QWORD *)&v17[6].Data1 = v17 + 7;
      *(_QWORD *)v17[6].Data4 = 97;
      LOWORD(v17[7].Data1) = 0;
      *(_QWORD *)v17[5].Data4 = &TLMString<96,96,1024>::`vftable';
      *(_DWORD *)v17[3].Data4 = *(_DWORD *)a3;
      *(_DWORD *)v17[4].Data4 = *((_DWORD *)a3 + 4);
      *(_DWORD *)&v17[4].Data4[4] = *((_DWORD *)a3 + 5);
      v17[5].Data1 = *((_DWORD *)a3 + 6);
      *(_QWORD *)&v17[4].Data1 = 0;
      v16 = *((_QWORD *)a3 + 1);
      if ( v16 )
      {
        CLMString::operator=(v17[5].Data4, v16);
        *(_QWORD *)&v17[4].Data1 = *(_QWORD *)&v17[6].Data1;
      }
      if ( *(_DWORD *)v17[3].Data4 == 3 )
      {
        v17[2] = *(GUID *)a4;
        *(PROPVARIANT *)&v17[3].Data1 = a4[2];
      }
      else
      {
        v17[2] = 0;
        *(_QWORD *)&v17[3].Data1 = 0;
        v19 = PropVariantCopy((PROPVARIANT *)&v17[2], a4);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x20,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\gthrpropbag.hxx",
            (const char *)(unsigned int)v19,
            v38);
      }
    }
    else
    {
      v17 = 0;
    }
    if ( v17 )
    {
      if ( (unsigned int)CTPtrKPtrHashMap<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Insert(
                           v8,
                           v17,
                           v17) )
      {
        v20 = 0;
        if ( !*(_DWORD *)&v17[6].Data4[4]
          || (unsigned int)CTPtrKPtrHashMap<TLMString<96,96,1024>,CGatherResourceProperty,CLMSubStr>::Insert(
                             (char *)this + 80,
                             v17[5].Data4,
                             v17) )
        {
          goto LABEL_17;
        }
        LastError = GetLastError();
        v20 = LastError;
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        if ( v20 == -2147024713 )
        {
          v32 = *((_QWORD *)this + 16);
          v33 = *((_DWORD *)this + 26);
          v34 = (*((__int64 (__fastcall **)(unsigned __int8 *))this + 11))(v17[5].Data4);
          v35 = CTPtrKPtrSList<TLMString<96,96,1024>,CGatherResourceProperty,CLMSubStr>::Remove(
                  v32 + 32LL * (v34 % v33),
                  v17[5].Data4);
          v36 = (CGatherResourceProperty *)v35;
          if ( v35 )
            --*((_DWORD *)this + 27);
          CTPtrKPtrHashMap<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Remove(v8, v35);
          if ( (unsigned int)CTPtrKPtrHashMap<TLMString<96,96,1024>,CGatherResourceProperty,CLMSubStr>::Insert(
                               (char *)this + 80,
                               v17[5].Data4,
                               v17) )
          {
            v20 = 0;
          }
          else
          {
            v37 = GetLastError();
            v20 = v37;
            if ( v37 > 0 )
              v20 = (unsigned __int16)v37 | 0x80070000;
          }
          if ( v36 )
            CGatherResourceProperty::`scalar deleting destructor'(v36, v16);
        }
        if ( v20 >= 0 )
LABEL_17:
          v17 = 0;
        else
          CTPtrKPtrHashMap<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Remove(v8, v17);
      }
      else
      {
        v30 = GetLastError();
        v20 = v30;
        if ( v30 > 0 )
          v20 = (unsigned __int16)v30 | 0x80070000;
      }
    }
    else
    {
      v20 = -2147024882;
    }
    if ( v17 )
      CGatherResourceProperty::`scalar deleting destructor'((CGatherResourceProperty *)v17, v16);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180008d9c  push    rbx
0x180008d9e  push    rbp
0x180008d9f  push    rsi
0x180008da0  push    rdi
0x180008da1  push    r12
0x180008da3  push    r13
0x180008da5  push    r14
0x180008da7  push    r15
0x180008da9  sub     rsp, 38h
0x180008dad  mov     rbp, r9
0x180008db0  mov     r14, r8
0x180008db3  mov     rsi, rdx
0x180008db6  mov     r15, rcx
0x180008db9  lea     r13, [rcx+18h]
0x180008dbd  cmp     dword ptr [r13+1Ch], 400h
0x180008dc5  jnb     loc_18000912B
0x180008dcb  mov     rdi, [rcx+48h]
0x180008dcf  mov     ebx, [rcx+30h]
0x180008dd2  mov     rcx, rdx
0x180008dd5  mov     rax, [r15+28h]
0x180008dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dde  xor     edx, edx
0x180008de0  div     ebx
0x180008de2  mov     ecx, edx
0x180008de4  shl     rcx, 5
0x180008de8  add     rdi, rcx
0x180008deb  jz      short loc_180008E05
0x180008ded  mov     rbx, rdi
0x180008df0  test    rbx, rbx
0x180008df3  jz      short loc_180008E05
0x180008df5  mov     rbx, [rbx]
0x180008df8  lea     rax, [rdi+8]
0x180008dfc  cmp     rbx, rax
0x180008dff  jnz     loc_180008FD1
0x180008e05  lea     rbx, ?pNULL@?1??Lookup@?$CTPtrKPtrSList@VCFullPropSpecWrapper@@VCGatherResourceProperty@@UtagFULLPROPSPEC@@@@QEAAAEAPEAVCGatherResourceProperty@@PEBUtagFULLPROPSPEC@@@Z@4PEAV3@EA; CGatherResourceProperty * `CTPtrKPtrSList<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Lookup(tagFULLPROPSPEC const *)'::`2'::pNULL
0x180008e0c  mov     rbx, [rbx]
0x180008e0f  test    rbx, rbx
0x180008e12  jnz     loc_180008F25
0x180008e18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008e1f  mov     ecx, 138h; unsigned __int64
0x180008e24  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008e29  mov     rbx, rax
0x180008e2c  mov     [rsp+78h+arg_0], rax
0x180008e34  test    rax, rax
0x180008e37  jz      loc_18000902C
0x180008e3d  movups  xmm0, xmmword ptr [rsi]
0x180008e40  movdqu  xmmword ptr [rax], xmm0
0x180008e44  mov     eax, [rsi+10h]
0x180008e47  test    eax, eax
0x180008e49  jz      loc_180008FA1
0x180008e4f  mov     [rbx+10h], eax
0x180008e52  mov     eax, [rsi+18h]
0x180008e55  mov     [rbx+18h], eax
0x180008e58  lea     rcx, [rbx+70h]
0x180008e5c  mov     [rbx+60h], rcx
0x180008e60  mov     qword ptr [rbx+68h], 61h ; 'a'
0x180008e68  xor     eax, eax
0x180008e6a  mov     [rcx], ax
0x180008e6d  lea     rax, ??_7?$TLMString@$0GA@$0GA@$0EAA@@@6B@; const TLMString<96,96,1024>::`vftable'
0x180008e74  mov     [rbx+58h], rax
0x180008e78  mov     eax, [r14]
0x180008e7b  mov     [rbx+38h], eax
0x180008e7e  mov     eax, [r14+10h]
0x180008e82  mov     [rbx+48h], eax
0x180008e85  mov     eax, [r14+14h]
0x180008e89  mov     [rbx+4Ch], eax
0x180008e8c  mov     eax, [r14+18h]
0x180008e90  mov     [rbx+50h], eax
0x180008e93  mov     qword ptr [rbx+40h], 0
0x180008e9b  mov     rdx, [r14+8]
0x180008e9f  test    rdx, rdx
0x180008ea2  jnz     loc_18000914B
0x180008ea8  cmp     dword ptr [rbx+38h], 3
0x180008eac  jz      loc_180008F8A
0x180008eb2  lea     rcx, [rbx+20h]; pvarDest
0x180008eb6  xorps   xmm0, xmm0
0x180008eb9  xor     eax, eax
0x180008ebb  movups  xmmword ptr [rcx], xmm0
0x180008ebe  mov     [rcx+10h], rax
0x180008ec2  mov     rdx, rbp; pvarSrc
0x180008ec5  call    cs:__imp_PropVariantCopy
0x180008ecb  test    eax, eax
0x180008ecd  js      loc_180009161
0x180008ed3  mov     qword ptr [rsp+78h+var_58], rbx
0x180008ed8  test    rbx, rbx
0x180008edb  jz      loc_18000917B
0x180008ee1  mov     r8, rbx
0x180008ee4  mov     rdx, rbx
0x180008ee7  mov     rcx, r13
0x180008eea  call    ?Insert@?$CTPtrKPtrHashMap@VCFullPropSpecWrapper@@VCGatherResourceProperty@@UtagFULLPROPSPEC@@@@QEAAHPEBVCFullPropSpecWrapper@@PEAVCGatherResourceProperty@@@Z; CTPtrKPtrHashMap<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Insert(CFullPropSpecWrapper const *,CGatherResourceProperty *)
0x180008eef  test    eax, eax
0x180008ef1  jz      loc_180009047
0x180008ef7  xor     edi, edi
0x180008ef9  lea     r14, [rbx+58h]
0x180008efd  cmp     [r14+14h], edi
0x180008f01  jnz     loc_180009185
0x180008f07  xor     ebx, ebx
0x180008f09  test    rbx, rbx
0x180008f0c  jnz     loc_1800091A1
0x180008f12  mov     eax, edi
0x180008f14  add     rsp, 38h
0x180008f18  pop     r15
0x180008f1a  pop     r14
0x180008f1c  pop     r13
0x180008f1e  pop     r12
0x180008f20  pop     rdi
0x180008f21  pop     rsi
0x180008f22  pop     rbp
0x180008f23  pop     rbx
0x180008f24  retn
0x180008f25  lea     rsi, [rbx+20h]
0x180008f29  cmp     dword ptr [rbx+38h], 3
0x180008f2d  jz      short loc_180008F38
0x180008f2f  mov     rcx, rsi; pvar
0x180008f32  call    cs:__imp_PropVariantClear
0x180008f38  mov     eax, [r14]
0x180008f3b  mov     [rbx+38h], eax
0x180008f3e  mov     eax, [r14+10h]
0x180008f42  mov     [rbx+48h], eax
0x180008f45  mov     eax, [r14+14h]
0x180008f49  mov     [rbx+4Ch], eax
0x180008f4c  mov     eax, [r14+18h]
0x180008f50  mov     [rbx+50h], eax
0x180008f53  mov     qword ptr [rbx+40h], 0
0x180008f5b  mov     rdx, [r14+8]
0x180008f5f  test    rdx, rdx
0x180008f62  jnz     loc_180009135
0x180008f68  cmp     dword ptr [rbx+38h], 3
0x180008f6c  jz      short loc_180008FB9
0x180008f6e  xorps   xmm0, xmm0
0x180008f71  xor     eax, eax
0x180008f73  movups  xmmword ptr [rsi], xmm0
0x180008f76  mov     [rsi+10h], rax
0x180008f7a  mov     rdx, rbp; pvarSrc
0x180008f7d  mov     rcx, rsi; pvarDest
0x180008f80  call    cs:__imp_PropVariantCopy
0x180008f86  mov     edi, eax
0x180008f88  jmp     short loc_180008F12
0x180008f8a  movups  xmm0, xmmword ptr [rbp+0]
0x180008f8e  movups  xmmword ptr [rbx+20h], xmm0
0x180008f92  movsd   xmm1, qword ptr [rbp+10h]
0x180008f97  movsd   qword ptr [rbx+30h], xmm1
0x180008f9c  jmp     loc_180008ED3
0x180008fa1  mov     dword ptr [rbx+10h], 1
0x180008fa8  mov     rdx, [rsi+18h]; wchar_t *
0x180008fac  mov     rcx, rbx; this
0x180008faf  call    ?SetProperty@CFullPropSpecWrapper@@AEAAHPEB_W@Z; CFullPropSpecWrapper::SetProperty(wchar_t const *)
0x180008fb4  jmp     loc_180008E58
0x180008fb9  xor     edi, edi
0x180008fbb  movups  xmm0, xmmword ptr [rbp+0]
0x180008fbf  movups  xmmword ptr [rsi], xmm0
0x180008fc2  movsd   xmm1, qword ptr [rbp+10h]
0x180008fc7  movsd   qword ptr [rsi+10h], xmm1
0x180008fcc  jmp     loc_180008F12
0x180008fd1  test    rbx, rbx
0x180008fd4  jz      loc_180008E05
0x180008fda  mov     rcx, [rbx+10h]
0x180008fde  mov     rax, [rsi]
0x180008fe1  sub     rax, [rcx]
0x180008fe4  jnz     short loc_180008FEE
0x180008fe6  mov     rax, [rsi+8]
0x180008fea  sub     rax, [rcx+8]
0x180008fee  test    rax, rax
0x180008ff1  jnz     loc_180008DF0
0x180008ff7  mov     eax, [rcx+10h]
0x180008ffa  cmp     [rsi+10h], eax
0x180008ffd  jnz     loc_180008DF0
0x180009003  test    eax, eax
0x180009005  jz      short loc_180009033
0x180009007  cmp     eax, 1
0x18000900a  jnz     loc_180008DF0
0x180009010  xor     edx, edx
0x180009012  mov     eax, [rsi+18h]
0x180009015  cmp     [rcx+18h], eax
0x180009018  setz    dl
0x18000901b  test    edx, edx
0x18000901d  jz      loc_180008DF0
0x180009023  add     rbx, 8
0x180009027  jmp     loc_180008E0C
0x18000902c  xor     ebx, ebx
0x18000902e  jmp     loc_180008ED3
0x180009033  mov     rdx, [rsi+18h]
0x180009037  mov     rcx, [rcx+18h]
0x18000903b  call    cs:__imp__o__wcsicmp
0x180009041  xor     edx, edx
0x180009043  test    eax, eax
0x180009045  jmp     short loc_180009018
0x180009047  call    cs:__imp_GetLastError
0x18000904d  mov     edi, eax
0x18000904f  test    eax, eax
0x180009051  jle     loc_180008F09
0x180009057  movzx   edi, ax
0x18000905a  or      edi, 80070000h
0x180009060  jmp     loc_180008F09
0x180009065  call    cs:__imp_GetLastError
0x18000906b  mov     edi, eax
0x18000906d  mov     ebp, 80070000h
0x180009072  test    eax, eax
0x180009074  jle     short loc_18000907B
0x180009076  movzx   edi, ax
0x180009079  or      edi, ebp
0x18000907b  cmp     edi, 800700B7h
0x180009081  jnz     loc_180009113
0x180009087  mov     [rsp+78h+arg_0], 0
0x180009093  mov     rsi, [r15+80h]
0x18000909a  mov     edi, [r15+68h]
0x18000909e  mov     rcx, r14
0x1800090a1  mov     rax, [r15+58h]
0x1800090a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090aa  xor     edx, edx
0x1800090ac  div     edi
0x1800090ae  mov     ecx, edx
0x1800090b0  shl     rcx, 5
0x1800090b4  add     rcx, rsi
0x1800090b7  mov     rdx, r14
0x1800090ba  call    ?Remove@?$CTPtrKPtrSList@V?$TLMString@$0GA@$0GA@$0EAA@@@VCGatherResourceProperty@@VCLMSubStr@@@@QEAAPEAVCGatherResourceProperty@@PEBV?$TLMString@$0GA@$0GA@$0EAA@@@@Z; CTPtrKPtrSList<TLMString<96,96,1024>,CGatherResourceProperty,CLMSubStr>::Remove(TLMString<96,96,1024> const *)
0x1800090bf  mov     rsi, rax
0x1800090c2  test    rax, rax
0x1800090c5  jz      short loc_1800090CB
0x1800090c7  dec     dword ptr [r15+6Ch]
0x1800090cb  mov     [rsp+78h+arg_0], rsi
0x1800090d3  mov     rdx, rsi
0x1800090d6  mov     rcx, r13
0x1800090d9  call    ?Remove@?$CTPtrKPtrHashMap@VCFullPropSpecWrapper@@VCGatherResourceProperty@@UtagFULLPROPSPEC@@@@QEAAPEAVCGatherResourceProperty@@PEBVCFullPropSpecWrapper@@@Z; CTPtrKPtrHashMap<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Remove(CFullPropSpecWrapper const *)
0x1800090de  mov     r8, rbx
0x1800090e1  mov     rdx, r14
0x1800090e4  lea     rcx, [r15+50h]
0x1800090e8  call    ?Insert@?$CTPtrKPtrHashMap@V?$TLMString@$0GA@$0GA@$0EAA@@@VCGatherResourceProperty@@VCLMSubStr@@@@QEAAHPEBV?$TLMString@$0GA@$0GA@$0EAA@@@PEAVCGatherResourceProperty@@@Z; CTPtrKPtrHashMap<TLMString<96,96,1024>,CGatherResourceProperty,CLMSubStr>::Insert(TLMString<96,96,1024> const *,CGatherResourceProperty *)
0x1800090ed  test    eax, eax
0x1800090ef  jz      short loc_1800090F5
0x1800090f1  xor     edi, edi
0x1800090f3  jmp     short loc_180009106
0x1800090f5  call    cs:__imp_GetLastError
0x1800090fb  mov     edi, eax
0x1800090fd  test    eax, eax
0x1800090ff  jle     short loc_180009106
0x180009101  movzx   edi, ax
0x180009104  or      edi, ebp
0x180009106  test    rsi, rsi
0x180009109  jz      short loc_180009113
0x18000910b  mov     rcx, rsi; this
0x18000910e  call    ??_GCGatherResourceProperty@@QEAAPEAXI@Z; CGatherResourceProperty::`scalar deleting destructor'(uint)
0x180009113  test    edi, edi
0x180009115  jns     loc_180008F07
0x18000911b  mov     rdx, rbx
0x18000911e  mov     rcx, r13
0x180009121  call    ?Remove@?$CTPtrKPtrHashMap@VCFullPropSpecWrapper@@VCGatherResourceProperty@@UtagFULLPROPSPEC@@@@QEAAPEAVCGatherResourceProperty@@PEBVCFullPropSpecWrapper@@@Z; CTPtrKPtrHashMap<CFullPropSpecWrapper,CGatherResourceProperty,tagFULLPROPSPEC>::Remove(CFullPropSpecWrapper const *)
0x180009126  jmp     loc_180008F09
0x18000912b  mov     eax, 80040DB0h
0x180009130  jmp     loc_180008F14
0x180009135  lea     rcx, [rbx+58h]
0x180009139  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18000913e  mov     rax, [rbx+60h]
0x180009142  mov     [rbx+40h], rax
0x180009146  jmp     loc_180008F68
0x18000914b  lea     rcx, [rbx+58h]
0x18000914f  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180009154  mov     rax, [rbx+60h]
0x180009158  mov     [rbx+40h], rax
0x18000915c  jmp     loc_180008EA8
0x180009161  mov     rcx, [rsp+78h]; this
0x180009166  mov     r9d, eax; char *
0x180009169  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\appmodel\\Search\\mss"...
0x180009170  mov     edx, 20h ; ' '; void *
0x180009175  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000917b  mov     edi, 8007000Eh
0x180009180  jmp     loc_180008F09
0x180009185  mov     r8, rbx
0x180009188  mov     rdx, r14
0x18000918b  lea     rcx, [r15+50h]
0x18000918f  call    ?Insert@?$CTPtrKPtrHashMap@V?$TLMString@$0GA@$0GA@$0EAA@@@VCGatherResourceProperty@@VCLMSubStr@@@@QEAAHPEBV?$TLMString@$0GA@$0GA@$0EAA@@@PEAVCGatherResourceProperty@@@Z; CTPtrKPtrHashMap<TLMString<96,96,1024>,CGatherResourceProperty,CLMSubStr>::Insert(TLMString<96,96,1024> const *,CGatherResourceProperty *)
0x180009194  test    eax, eax
0x180009196  jnz     loc_180008F07
0x18000919c  jmp     loc_180009065
0x1800091a1  mov     rcx, rbx; this
0x1800091a4  call    ??_GCGatherResourceProperty@@QEAAPEAXI@Z; CGatherResourceProperty::`scalar deleting destructor'(uint)
0x1800091a9  jmp     loc_180008F12
```
