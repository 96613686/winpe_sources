# CCertRequest::GetCAProperty(ushort * const,long,long,long,long,tagVARIANT *)

- ea: `0x18000e140`
- end: `0x18000e66c`
- name: `?GetCAProperty@CCertRequest@@UEAAJQEAGJJJJPEAUtagVARIANT@@@Z`
- size: `1324`
- prototype: `__int64 __fastcall(CCertRequest *__hidden this, unsigned __int16 *const, int, int, unsigned int, unsigned int, VARIANTARG *pvarg)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002306`
- `0x18000e140`
- `0x18001027c`
- `0x18001053c`
- `0x1800119dc`
- `0x18001e170`
- `0x18001f728`
- `0x18003f010`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e404`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e45b`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e5b8`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e5fa`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e404`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e45b`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e5b8`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000e5fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e64b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e64b`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1c5`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1c5`
- `OLEAUT32!__imp_VariantClear` at `0x18000e620`
- `OLEAUT32!__imp_VariantClear` at `0x18000e620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e630`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e630`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000e1b7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000e612`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000e1b7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000e612`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000e49b`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000e49b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCertRequest::GetCAProperty(
        CCertRequest *this,
        unsigned __int16 *const a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6,
        VARIANTARG *pvarg)
{
  CCertRequest *v10; // r15
  struct tagVARIANT *v11; // r12
  int v12; // edi
  int SCEPProperty; // eax
  int v14; // edx
  unsigned int v15; // ecx
  int v16; // eax
  const unsigned __int8 *v17; // rdi
  unsigned int v18; // r14d
  int v19; // eax
  unsigned int v20; // r14d
  const unsigned __int8 **v21; // r12
  unsigned __int8 *v22; // r13
  void (*v23)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  __int64 v24; // rdx
  __int64 v25; // rdx
  void (*v26)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  CCertRequest *v27; // rcx
  unsigned int v28; // ebx
  unsigned int v30; // [rsp+40h] [rbp-88h] BYREF
  int v31; // [rsp+44h] [rbp-84h]
  unsigned __int8 *v32; // [rsp+48h] [rbp-80h] BYREF
  int v33; // [rsp+50h] [rbp-78h] BYREF
  const unsigned __int8 **v34; // [rsp+58h] [rbp-70h]
  size_t Size; // [rsp+60h] [rbp-68h]
  __int64 v36; // [rsp+68h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-58h]
  BSTR bstrString; // [rsp+78h] [rbp-50h] BYREF
  unsigned __int16 *v39; // [rsp+80h] [rbp-48h] BYREF
  void (*v40)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+88h] [rbp-40h]
  const struct _EXCEPTION_POINTERS *v41; // [rsp+90h] [rbp-38h] BYREF
  const struct _EXCEPTION_POINTERS *v42; // [rsp+98h] [rbp-30h] BYREF

  v10 = this;
  v36 = 0;
  pv = 0;
  bstrString = 0;
  v32 = 0;
  v30 = 0;
  v33 = 0;
  v11 = pvarg;
  if ( !pvarg )
  {
    v12 = -2147467261;
    CSPrintErrorLineFile(0x8A0709u, -2147467261);
    goto LABEL_73;
  }
  VariantInit(pvarg);
  if ( (unsigned int)(a3 - 1000) > 2 )
  {
    v39 = 0;
    v19 = CCertRequest::_OpenConnection(v10, 0, a2, 2u, &v39);
    v12 = v19;
    if ( v19 )
    {
      v14 = v19;
      v15 = 11077385;
      goto LABEL_71;
    }
    v20 = -1;
    v30 = -1;
    v21 = 0;
    v34 = 0;
    LODWORD(Size) = 1;
    v22 = 0;
    v32 = 0;
    if ( a3 > 23 )
    {
      switch ( a3 )
      {
        case 24:
          v20 = 28;
          break;
        case 25:
          v20 = 32;
          break;
        case 27:
          v21 = (const unsigned __int8 **)((char *)v10 + 328);
          v22 = (unsigned __int8 *)v10 + 336;
          goto LABEL_40;
        case 28:
          v20 = 36;
          break;
        default:
          switch ( a3 )
          {
            case '%':
              v21 = (const unsigned __int8 **)((char *)v10 + 344);
              v22 = (unsigned __int8 *)v10 + 352;
              break;
            case '&':
              v21 = (const unsigned __int8 **)((char *)v10 + 360);
              v22 = (unsigned __int8 *)v10 + 368;
              break;
            case '\'':
              v21 = (const unsigned __int8 **)((char *)v10 + 248);
              v22 = (unsigned __int8 *)v10 + 256;
              LODWORD(Size) = 4;
              break;
            default:
              goto LABEL_78;
          }
          goto LABEL_40;
      }
    }
    else
    {
      switch ( a3 )
      {
        case 23:
          v20 = 24;
          break;
        case 3:
          v20 = 16;
          break;
        case 10:
          v20 = 4;
          break;
        case 11:
          v20 = 8;
          break;
        case 14:
          v20 = 12;
          break;
        default:
          switch ( a3 )
          {
            case 19:
              v21 = (const unsigned __int8 **)((char *)v10 + 232);
              v22 = (unsigned __int8 *)v10 + 240;
              break;
            case 20:
              v21 = (const unsigned __int8 **)((char *)v10 + 264);
              v22 = (unsigned __int8 *)v10 + 272;
              break;
            case 21:
              v20 = 20;
              goto LABEL_45;
            default:
LABEL_78:
              try
              {
                v23 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
                v40 = v23;
                v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, _QWORD, int, __int64 *))(**((_QWORD **)v10 + 10) + 56LL))(
                        *((_QWORD *)v10 + 10),
                        v39,
                        (unsigned int)a3,
                        (unsigned int)a4,
                        a5,
                        &v36);
                v31 = v12;
                _set_se_translator(v23);
              }
              catch ( const StructuredException *v41 )
              {
                v31 = myHExceptionCodePrint(v41 + 77, 0, 0x709u, 0x10Cu);
                v10 = this;
                v12 = v31;
                v20 = v30;
                v21 = v34;
                v22 = v32;
              }
              if ( v12 )
              {
                if ( v12 != -2147024809 )
                  CSPrintErrorLineFile2(0x11D0709u, v12, -2147024894);
                goto LABEL_72;
              }
              v17 = (const unsigned __int8 *)pv;
              v30 = v36;
              if ( v20 != -1 )
              {
                if ( !pv || *(_DWORD *)pv < 4u || (_DWORD)v36 != *(_DWORD *)pv )
                {
                  v12 = -2147024883;
                  v15 = 20055817;
                  goto LABEL_70;
                }
                *((_DWORD *)v10 + 76) = v36;
                *((_QWORD *)v10 + 37) = v17;
                pv = 0;
                goto LABEL_55;
              }
              if ( !v21 )
              {
                v18 = v30;
                goto LABEL_67;
              }
              *(_DWORD *)v22 = v36;
              *v21 = v17;
              pv = 0;
LABEL_60:
              if ( a4 > 0x10000 || (unsigned int)Size > 4 )
              {
                v12 = -2147024362;
                v15 = 22677257;
                goto LABEL_70;
              }
              v25 = (unsigned int)(a4 * Size);
              if ( (unsigned int)(v25 + Size) > *(_DWORD *)v22 )
              {
                v14 = -2147024809;
                v12 = -2147024809;
                v15 = 23004937;
                goto LABEL_71;
              }
              v33 = 0;
              memcpy_0(&v33, &(*v21)[v25], (unsigned int)Size);
              v17 = (const unsigned __int8 *)&v33;
              v18 = 4;
              goto LABEL_67;
          }
LABEL_40:
          v32 = v22;
          v34 = v21;
          if ( v21 && *v21 )
            goto LABEL_60;
          goto LABEL_78;
      }
    }
LABEL_45:
    v30 = v20;
    if ( *((_QWORD *)v10 + 37) )
    {
LABEL_55:
      v24 = v20;
      v17 = (const unsigned __int8 *)(v20 + *((_QWORD *)v10 + 37));
      v18 = 4;
      if ( v24 + 4 > (unsigned __int64)*((unsigned int *)v10 + 76) )
      {
        v12 = -2147467263;
        v15 = 21825289;
LABEL_70:
        v14 = v12;
        goto LABEL_71;
      }
LABEL_67:
      v11 = pvarg;
      goto LABEL_83;
    }
    goto LABEL_78;
  }
  SCEPProperty = CCertRequest::_GetSCEPProperty(v10, a2, a3, a4, a5, &bstrString);
  v12 = SCEPProperty;
  if ( SCEPProperty )
  {
    v14 = SCEPProperty;
    v15 = 9897737;
LABEL_71:
    CSPrintErrorLineFile(v15, v14);
LABEL_72:
    VariantClear(pvarg);
    goto LABEL_73;
  }
  myGetBStrBuffer(bstrString, &v30, &v32);
  v16 = 1048580;
  if ( a5 != 4 )
    v16 = a5;
  a5 = v16;
  v17 = v32;
  v18 = v30;
LABEL_83:
  try
  {
    v26 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
    v40 = v26;
    v12 = myUnmarshalFormattedVariant(a6, a3, a5, v18, v17, v11);
    v31 = v12;
    _set_se_translator(v26);
  }
  catch ( const StructuredException *v42 )
  {
    v31 = myHExceptionCodePrint(v42 + 77, 0, 0x709u, 0x177u);
    v12 = v31;
  }
  if ( v12 )
  {
    v15 = 24708873;
    goto LABEL_70;
  }
LABEL_73:
  v27 = (CCertRequest *)pv;
  if ( pv )
    CoTaskMemFree(pv);
  v28 = CCertRequest::_SetErrorInfo(v27, v12, L"CCertRequest::GetCAProperty");
  SysFreeString(bstrString);
  return v28;
}

```

## disassembly

```asm
0x18000e140  mov     rax, rsp
0x18000e143  mov     [rax+10h], rbx
0x18000e147  mov     [rax+20h], r9d
0x18000e14b  mov     [rax+18h], r8d
0x18000e14f  mov     [rax+8], rcx
0x18000e153  push    rdi
0x18000e154  push    r12
0x18000e156  push    r13
0x18000e158  push    r14
0x18000e15a  push    r15
0x18000e15c  sub     rsp, 0A0h
0x18000e163  mov     edi, r9d
0x18000e166  mov     ebx, r8d
0x18000e169  mov     r13, rdx
0x18000e16c  mov     r15, rcx
0x18000e16f  mov     qword ptr [rax-60h], 0
0x18000e177  mov     qword ptr [rax-58h], 0
0x18000e17f  mov     qword ptr [rax-50h], 0
0x18000e187  mov     qword ptr [rax-80h], 0
0x18000e18f  mov     [rsp+0C8h+var_88], 0
0x18000e197  mov     dword ptr [rax-78h], 0
0x18000e19e  mov     r12, [rsp+0C8h+pvarg]
0x18000e1a6  test    r12, r12
0x18000e1a9  jnz     short loc_18000E1C2
0x18000e1ab  mov     edi, 80004003h
0x18000e1b0  mov     edx, edi
0x18000e1b2  mov     ecx, 8A0709h
0x18000e1b7  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000e1bd  jmp     loc_18000E626
0x18000e1c2  mov     rcx, r12; pvarg
0x18000e1c5  call    cs:__imp_VariantInit
0x18000e1cb  lea     eax, [rbx-3E8h]
0x18000e1d1  mov     rcx, r15; this
0x18000e1d4  cmp     eax, 2
0x18000e1d7  ja      short loc_18000E247
0x18000e1d9  lea     rax, [rsp+0C8h+bstrString]
0x18000e1de  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 **
0x18000e1e3  mov     r14d, [rsp+0C8h+arg_20]
0x18000e1eb  mov     dword ptr [rsp+0C8h+var_A8], r14d; int
0x18000e1f0  mov     r9d, edi; int
0x18000e1f3  mov     r8d, ebx; int
0x18000e1f6  mov     rdx, r13; unsigned __int16 *
0x18000e1f9  call    ?_GetSCEPProperty@CCertRequest@@AEAAJQEAGJJJPEAPEAG@Z; CCertRequest::_GetSCEPProperty(ushort * const,long,long,long,ushort * *)
0x18000e1fe  mov     edi, eax
0x18000e200  test    eax, eax
0x18000e202  jz      short loc_18000E210
0x18000e204  mov     edx, eax
0x18000e206  mov     ecx, 970709h
0x18000e20b  jmp     loc_18000E612
0x18000e210  lea     r8, [rsp+0C8h+var_80]; unsigned __int8 **
0x18000e215  lea     rdx, [rsp+0C8h+var_88]; unsigned int *
0x18000e21a  mov     rcx, [rsp+0C8h+bstrString]; bstr
0x18000e21f  call    ?myGetBStrBuffer@@YAXPEAGPEAKPEAPEAE@Z; myGetBStrBuffer(ushort *,ulong *,uchar * *)
0x18000e224  mov     eax, 100004h
0x18000e229  cmp     r14d, 4
0x18000e22d  cmovnz  eax, r14d
0x18000e231  mov     [rsp+0C8h+arg_20], eax
0x18000e238  mov     rdi, [rsp+0C8h+var_80]
0x18000e23d  mov     r14d, [rsp+0C8h+var_88]
0x18000e242  jmp     loc_18000E5B1
0x18000e247  mov     [rsp+0C8h+var_48], 0
0x18000e253  lea     rax, [rsp+0C8h+var_48]
0x18000e25b  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 **
0x18000e260  mov     r9d, 2; unsigned int
0x18000e266  mov     r8, r13; unsigned __int16 *
0x18000e269  xor     edx, edx; int
0x18000e26b  call    ?_OpenConnection@CCertRequest@@AEAAJHPEBGKPEAPEBG@Z; CCertRequest::_OpenConnection(int,ushort const *,ulong,ushort const * *)
0x18000e270  mov     edi, eax
0x18000e272  test    eax, eax
0x18000e274  jz      short loc_18000E282
0x18000e276  mov     edx, eax
0x18000e278  mov     ecx, 0A90709h
0x18000e27d  jmp     loc_18000E612
0x18000e282  or      edx, 0FFFFFFFFh
0x18000e285  mov     r14d, edx
0x18000e288  mov     [rsp+0C8h+var_88], edx
0x18000e28c  xor     r12d, r12d
0x18000e28f  mov     [rsp+0C8h+var_70], r12
0x18000e294  mov     dword ptr [rsp+0C8h+Size], 1
0x18000e29c  xor     r13d, r13d
0x18000e29f  mov     [rsp+0C8h+var_80], r13
0x18000e2a4  cmp     ebx, 17h
0x18000e2a7  jg      loc_18000E343
0x18000e2ad  jz      loc_18000E338
0x18000e2b3  mov     ecx, ebx
0x18000e2b5  sub     ecx, 3
0x18000e2b8  jz      short loc_18000E32D
0x18000e2ba  sub     ecx, 7
0x18000e2bd  jz      short loc_18000E322
0x18000e2bf  sub     ecx, 1
0x18000e2c2  jz      short loc_18000E317
0x18000e2c4  sub     ecx, 3
0x18000e2c7  jz      short loc_18000E30C
0x18000e2c9  sub     ecx, 5
0x18000e2cc  jz      short loc_18000E2F9
0x18000e2ce  sub     ecx, 1
0x18000e2d1  jz      short loc_18000E2E6
0x18000e2d3  cmp     ecx, 1
0x18000e2d6  jnz     loc_18000E3FD
0x18000e2dc  lea     r14d, [r12+14h]
0x18000e2e1  jmp     loc_18000E3EB
0x18000e2e6  lea     r12, [r15+108h]
0x18000e2ed  lea     r13, [r15+110h]
0x18000e2f4  jmp     loc_18000E3C2
0x18000e2f9  lea     r12, [r15+0E8h]
0x18000e300  lea     r13, [r15+0F0h]
0x18000e307  jmp     loc_18000E3C2
0x18000e30c  mov     r14d, 0Ch
0x18000e312  jmp     loc_18000E3EB
0x18000e317  mov     r14d, 8
0x18000e31d  jmp     loc_18000E3EB
0x18000e322  mov     r14d, 4
0x18000e328  jmp     loc_18000E3EB
0x18000e32d  mov     r14d, 10h
0x18000e333  jmp     loc_18000E3EB
0x18000e338  mov     r14d, 18h
0x18000e33e  jmp     loc_18000E3EB
0x18000e343  mov     ecx, ebx
0x18000e345  sub     ecx, 18h
0x18000e348  jz      loc_18000E3E5
0x18000e34e  sub     ecx, 1
0x18000e351  jz      loc_18000E3DD
0x18000e357  sub     ecx, 2
0x18000e35a  jz      short loc_18000E3B4
0x18000e35c  sub     ecx, 1
0x18000e35f  jz      short loc_18000E3AC
0x18000e361  sub     ecx, 9
0x18000e364  jz      short loc_18000E39C
0x18000e366  sub     ecx, 1
0x18000e369  jz      short loc_18000E38C
0x18000e36b  cmp     ecx, 1
0x18000e36e  jnz     loc_18000E3FD
0x18000e374  lea     r12, [r15+0F8h]
0x18000e37b  lea     r13, [r15+100h]
0x18000e382  mov     dword ptr [rsp+0C8h+Size], 4
0x18000e38a  jmp     short loc_18000E3C2
0x18000e38c  lea     r12, [r15+168h]
0x18000e393  lea     r13, [r15+170h]
0x18000e39a  jmp     short loc_18000E3C2
0x18000e39c  lea     r12, [r15+158h]
0x18000e3a3  lea     r13, [r15+160h]
0x18000e3aa  jmp     short loc_18000E3C2
0x18000e3ac  mov     r14d, 24h ; '$'
0x18000e3b2  jmp     short loc_18000E3EB
0x18000e3b4  lea     r12, [r15+148h]
0x18000e3bb  lea     r13, [r15+150h]
0x18000e3c2  mov     [rsp+0C8h+var_80], r13
0x18000e3c7  mov     [rsp+0C8h+var_70], r12
0x18000e3cc  test    r12, r12
0x18000e3cf  jz      short loc_18000E3FD
0x18000e3d1  cmp     qword ptr [r12], 0
0x18000e3d6  jz      short loc_18000E3FD
0x18000e3d8  jmp     loc_18000E53C
0x18000e3dd  mov     r14d, 20h ; ' '
0x18000e3e3  jmp     short loc_18000E3EB
0x18000e3e5  mov     r14d, 1Ch
0x18000e3eb  mov     [rsp+0C8h+var_88], r14d
0x18000e3f0  cmp     [r15+128h], r12
0x18000e3f7  jnz     loc_18000E4E1
0x18000e3fd  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18000e404  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000e40a  mov     rbx, rax
0x18000e40d  mov     [rsp+0C8h+var_40], rax
0x18000e415  mov     rcx, [r15+50h]
0x18000e419  mov     rax, [rcx]
0x18000e41c  lea     rdx, [rsp+0C8h+var_60]
0x18000e421  mov     [rsp+0C8h+var_A0], rdx
0x18000e426  mov     edx, [rsp+0C8h+arg_20]
0x18000e42d  mov     dword ptr [rsp+0C8h+var_A8], edx
0x18000e431  mov     r9d, [rsp+0C8h+arg_18]
0x18000e439  mov     r8d, [rsp+0C8h+arg_10]
0x18000e441  mov     rdx, [rsp+0C8h+var_48]
0x18000e449  mov     rax, [rax+38h]
0x18000e44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e452  mov     edi, eax
0x18000e454  mov     [rsp+0C8h+var_84], eax
0x18000e458  mov     rcx, rbx
0x18000e45b  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000e461  nop
0x18000e462  jmp     short loc_18000E47F
0x18000e464  mov     r15, [rsp+0C8h+arg_0]
0x18000e46c  mov     edi, [rsp+0C8h+var_84]
0x18000e470  mov     r14d, [rsp+0C8h+var_88]
0x18000e475  mov     r12, [rsp+0C8h+var_70]
0x18000e47a  mov     r13, [rsp+0C8h+var_80]
0x18000e47f  test    edi, edi
0x18000e481  jz      short loc_18000E4A6
0x18000e483  mov     edx, 80070057h
0x18000e488  cmp     edi, edx
0x18000e48a  jz      loc_18000E618
0x18000e490  lea     r8d, [rdx-55h]
0x18000e494  mov     edx, edi
0x18000e496  mov     ecx, 11D0709h
0x18000e49b  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x18000e4a1  jmp     loc_18000E618
0x18000e4a6  mov     rdi, [rsp+0C8h+pv]
0x18000e4ab  mov     r8d, dword ptr [rsp+0C8h+var_60]
0x18000e4b0  mov     [rsp+0C8h+var_88], r8d
0x18000e4b5  cmp     r14d, 0FFFFFFFFh
0x18000e4b9  jz      short loc_18000E526
0x18000e4bb  test    rdi, rdi
0x18000e4be  jz      short loc_18000E517
0x18000e4c0  cmp     dword ptr [rdi], 4
0x18000e4c3  jb      short loc_18000E517
0x18000e4c5  cmp     r8d, [rdi]
0x18000e4c8  jnz     short loc_18000E517
0x18000e4ca  mov     [r15+130h], r8d
0x18000e4d1  mov     [r15+128h], rdi
0x18000e4d8  mov     [rsp+0C8h+pv], 0
0x18000e4e1  mov     edx, r14d
0x18000e4e4  mov     rdi, [r15+128h]
0x18000e4eb  add     rdi, rdx
0x18000e4ee  mov     r14d, 4
0x18000e4f4  mov     ecx, [r15+130h]
0x18000e4fb  lea     rax, [rdx+4]
0x18000e4ff  cmp     rax, rcx
0x18000e502  jbe     loc_18000E5A9
0x18000e508  mov     edi, 80004001h
0x18000e50d  mov     ecx, 14D0709h
0x18000e512  jmp     loc_18000E610
0x18000e517  mov     edi, 8007000Dh
0x18000e51c  mov     ecx, 1320709h
0x18000e521  jmp     loc_18000E610
0x18000e526  test    r12, r12
0x18000e529  jz      short loc_18000E5A4
0x18000e52b  mov     [r13+0], r8d
0x18000e52f  mov     [r12], rdi
0x18000e533  mov     [rsp+0C8h+pv], 0
0x18000e53c  mov     eax, [rsp+0C8h+arg_18]
0x18000e543  cmp     eax, 10000h
0x18000e548  jg      short loc_18000E598
0x18000e54a  mov     ecx, dword ptr [rsp+0C8h+Size]
0x18000e54e  cmp     ecx, 4
0x18000e551  ja      short loc_18000E598
0x18000e553  mov     edx, ecx
0x18000e555  imul    edx, eax
0x18000e558  lea     eax, [rdx+rcx]
0x18000e55b  cmp     eax, [r13+0]
0x18000e55f  jbe     short loc_18000E572
0x18000e561  mov     edx, 80070057h
0x18000e566  mov     edi, edx
0x18000e568  mov     ecx, 15F0709h
0x18000e56d  jmp     loc_18000E612
0x18000e572  mov     [rsp+0C8h+var_78], 0
0x18000e57a  mov     r8, rcx; Size
0x18000e57d  add     rdx, [r12]; Src
0x18000e581  lea     rcx, [rsp+0C8h+var_78]; void *
0x18000e586  call    memcpy_0
0x18000e58b  lea     rdi, [rsp+0C8h+var_78]
0x18000e590  mov     r14d, 4
0x18000e596  jmp     short loc_18000E5A9
0x18000e598  mov     edi, 80070216h
0x18000e59d  mov     ecx, 15A0709h
0x18000e5a2  jmp     short loc_18000E610
0x18000e5a4  mov     r14d, [rsp+0C8h+var_88]
0x18000e5a9  mov     r12, [rsp+0C8h+pvarg]
0x18000e5b1  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18000e5b8  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000e5be  mov     rbx, rax
0x18000e5c1  mov     [rsp+0C8h+var_40], rax
0x18000e5c9  mov     [rsp+0C8h+var_A0], r12; struct tagVARIANT *
0x18000e5ce  mov     [rsp+0C8h+var_A8], rdi; unsigned __int8 *
0x18000e5d3  mov     r9d, r14d; unsigned int
0x18000e5d6  mov     r8d, [rsp+0C8h+arg_20]; unsigned int
0x18000e5de  mov     edx, [rsp+0C8h+arg_10]; unsigned int
0x18000e5e5  mov     ecx, [rsp+0C8h+arg_28]; unsigned int
0x18000e5ec  call    ?myUnmarshalFormattedVariant@@YAJKKKKPEBEPEAUtagVARIANT@@@Z; myUnmarshalFormattedVariant(ulong,ulong,ulong,ulong,uchar const *,tagVARIANT *)
0x18000e5f1  mov     edi, eax
0x18000e5f3  mov     [rsp+0C8h+var_84], eax
0x18000e5f7  mov     rcx, rbx
0x18000e5fa  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000e600  nop
0x18000e601  jmp     short loc_18000E607
0x18000e603  mov     edi, [rsp+0C8h+var_84]
0x18000e607  test    edi, edi
0x18000e609  jz      short loc_18000E626
0x18000e60b  mov     ecx, 1790709h
0x18000e610  mov     edx, edi
0x18000e612  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000e618  mov     rcx, [rsp+0C8h+pvarg]; pvarg
0x18000e620  call    cs:__imp_VariantClear
0x18000e626  mov     rcx, [rsp+0C8h+pv]; pv
0x18000e62b  test    rcx, rcx
0x18000e62e  jz      short loc_18000E636
0x18000e630  call    cs:__imp_CoTaskMemFree
0x18000e636  lea     r8, aCcertrequestGe_4; "CCertRequest::GetCAProperty"
0x18000e63d  mov     edx, edi; int
0x18000e63f  call    ?_SetErrorInfo@CCertRequest@@AEAAJJPEBG@Z; CCertRequest::_SetErrorInfo(long,ushort const *)
0x18000e644  mov     ebx, eax
0x18000e646  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x18000e64b  call    cs:__imp_SysFreeString
0x18000e651  mov     eax, ebx
0x18000e653  mov     rbx, [rsp+0C8h+arg_8]
0x18000e65b  add     rsp, 0A0h
0x18000e662  pop     r15
0x18000e664  pop     r14
0x18000e666  pop     r13
0x18000e668  pop     r12
0x18000e66a  pop     rdi
0x18000e66b  retn
  ... truncated ...
```
