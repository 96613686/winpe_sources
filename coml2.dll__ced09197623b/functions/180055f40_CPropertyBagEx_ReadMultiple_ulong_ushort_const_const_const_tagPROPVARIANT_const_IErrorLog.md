# CPropertyBagEx::ReadMultiple(ulong,ushort const * const * const,tagPROPVARIANT * const,IErrorLog *)

- ea: `0x180055f40`
- end: `0x180056256`
- name: `?ReadMultiple@CPropertyBagEx@@UEAAJKQEBQEBGQEAUtagPROPVARIANT@@PEAUIErrorLog@@@Z`
- size: `790`
- prototype: `int(CPropertyBagEx *__hidden this, unsigned int, const unsigned __int16 *const *const, struct tagPROPVARIANT *const, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023e70`
- `0x18003f5e8`
- `0x180052d50`
- `0x180055524`
- `0x180055bfc`
- `0x180055f40`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005617c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056206`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005617c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056020`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005604e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056020`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005604e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800561c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800561ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800561c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800561ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056217`

## pseudocode

```c
__int64 __fastcall CPropertyBagEx::ReadMultiple(
        CPropertyBagEx *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        struct tagPROPVARIANT *const a4)
{
  __int64 v4; // rdi
  int v7; // ebx
  unsigned __int64 v8; // r14
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _DWORD *v12; // r13
  _QWORD *v13; // rsi
  unsigned int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rax
  __int64 i; // r15
  int vt; // edx
  PROPVARIANT *v21; // r14
  CPropertyBagEx *v22; // rcx
  BYTE *pData; // xmm1_8
  int v24; // eax
  BYTE *v25; // xmm1_8
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  __int64 v28; // r14
  struct tagPROPVARIANT v30; // [rsp+30h] [rbp-58h] BYREF
  int v32; // [rsp+98h] [rbp+10h]

  v4 = a2;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), 0xFFFFFFFFLL);
  if ( (_DWORD)v4 )
  {
    if ( (unsigned int)v4 <= 0x200000 )
    {
      v7 = ValidateInRGLPOLESTR(v4, a3);
      if ( !v7 )
      {
        v8 = 24 * v4;
        if ( (unsigned int)IsValidReadPtrIn(a4, 24 * v4) )
        {
          v9 = CPropertyBagEx::OpenPropStg(this, 3u);
          v7 = v9;
          if ( v9 == -2147287038 )
          {
            v10 = 0;
            do
            {
              v11 = v10;
              v10 = (unsigned int)(v10 + 1);
              a4[v11].vt = 0;
            }
            while ( (unsigned int)v10 < (unsigned int)v4 );
            v7 = 1;
          }
          else if ( v9 >= 0 )
          {
            if ( (unsigned __int64)(16 * v4) > 0xFFFFFFFF )
            {
              v7 = -2147024362;
            }
            else
            {
              v12 = CoTaskMemAlloc((unsigned int)(16 * v4));
              if ( v12 )
              {
                if ( v8 > 0xFFFFFFFF )
                {
                  v13 = 0;
                  v7 = -2147024362;
                }
                else
                {
                  v13 = CoTaskMemAlloc((unsigned int)v8);
                  if ( v13 )
                  {
                    v14 = 0;
                    v15 = 0;
                    do
                    {
                      v16 = 3 * v15;
                      ++v14;
                      *(_OWORD *)&v13[v16] = 0;
                      v13[v16 + 2] = 0;
                      v17 = 2 * v15;
                      v12[2 * v17] = 0;
                      v18 = a3[v15++];
                      *(_QWORD *)&v12[2 * v17 + 2] = v18;
                    }
                    while ( v14 < (unsigned int)v4 );
                    v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, _QWORD *))(**((_QWORD **)this + 4) + 24LL))(
                            *((_QWORD *)this + 4),
                            (unsigned int)v4,
                            v12,
                            v13);
                    v7 = v32;
                    if ( v32 >= 0 )
                    {
                      for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
                      {
                        vt = a4[i].vt;
                        if ( (_WORD)vt )
                        {
                          v21 = (PROPVARIANT *)&v13[3 * i];
                          v22 = (CPropertyBagEx *)*(unsigned __int16 *)v21;
                          if ( (_WORD)v22 != (_WORD)vt )
                          {
                            memset(&v30, 0, sizeof(v30));
                            if ( (((vt & 0xFFFFBFFF) - 9) & 0xFFFFFFFB) != 0
                              || (LOWORD(v22) = (_WORD)v22 - 68, (unsigned __int16)v22 > 1u) )
                            {
                              v24 = StgPropVariantChangeType(&v30, vt);
                            }
                            else
                            {
                              pData = a4[i].bstrblobVal.pData;
                              *(_OWORD *)&v30.vt = *(_OWORD *)&a4[i].vt;
                              v30.bstrblobVal.pData = pData;
                              v24 = CPropertyBagEx::LoadObject(v22, &v30, (struct tagPROPVARIANT *)&v13[3 * i]);
                            }
                            v7 = v24;
                            if ( v24 < 0 )
                              goto LABEL_39;
                            PropVariantClear(v21);
                            v25 = v30.bstrblobVal.pData;
                            *(_OWORD *)v21 = *(_OWORD *)&v30.vt;
                            v21[2] = v25;
                          }
                        }
                      }
                      v26 = 0;
                      do
                      {
                        v27 = v26;
                        v26 = (unsigned int)(v26 + 1);
                        *(_OWORD *)&a4[v27].vt = *(_OWORD *)&v13[v27 * 3];
                        a4[v27].bstrblobVal.pData = (BYTE *)v13[v27 * 3 + 2];
                      }
                      while ( (unsigned int)v26 < (unsigned int)v4 );
                      CoTaskMemFree(v13);
                      v13 = 0;
                      if ( v7 >= 0 )
                        v7 = v32 == 1;
                    }
                  }
                  else
                  {
                    v7 = -2147024882;
                  }
                }
LABEL_39:
                CoTaskMemFree(v12);
                if ( v13 )
                {
                  v28 = 0;
                  do
                  {
                    PropVariantClear((PROPVARIANT *)&v13[3 * v28]);
                    v28 = (unsigned int)(v28 + 1);
                  }
                  while ( (unsigned int)v28 < (unsigned int)v4 );
                  CoTaskMemFree(v13);
                }
              }
              else
              {
                v7 = -2147024882;
              }
            }
          }
        }
        else
        {
          v7 = -2147024809;
        }
      }
    }
    else
    {
      v7 = -2147286953;
    }
  }
  else
  {
    v7 = 0;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180055f40  mov     [rsp+arg_10], rbx
0x180055f45  mov     [rsp+arg_0], rcx
0x180055f4a  push    rbp
0x180055f4b  push    rsi
0x180055f4c  push    rdi
0x180055f4d  push    r12
0x180055f4f  push    r13
0x180055f51  push    r14
0x180055f53  push    r15
0x180055f55  sub     rsp, 50h
0x180055f59  mov     rcx, [rcx+28h]
0x180055f5d  mov     ebp, 0FFFFFFFFh
0x180055f62  mov     edi, edx
0x180055f64  mov     r12, r9
0x180055f67  mov     edx, ebp
0x180055f69  mov     r15, r8
0x180055f6c  mov     rax, [rcx]
0x180055f6f  mov     rax, [rax+18h]
0x180055f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f78  test    edi, edi
0x180055f7a  jnz     short loc_180055F83
0x180055f7c  xor     ebx, ebx
0x180055f7e  jmp     loc_180056224
0x180055f83  cmp     edi, 200000h
0x180055f89  jbe     short loc_180055F95
0x180055f8b  mov     ebx, 80030057h
0x180055f90  jmp     loc_180056224
0x180055f95  mov     rdx, r15; unsigned __int16 **
0x180055f98  mov     ecx, edi; unsigned int
0x180055f9a  call    ?ValidateInRGLPOLESTR@@YAJKQEBQEBG@Z; ValidateInRGLPOLESTR(ulong,ushort const * const * const)
0x180055f9f  mov     ebx, eax
0x180055fa1  test    eax, eax
0x180055fa3  jnz     loc_180056224
0x180055fa9  lea     r14, [rdi+rdi*2]
0x180055fad  mov     rcx, r12; void *
0x180055fb0  shl     r14, 3
0x180055fb4  mov     rsi, rdi
0x180055fb7  mov     rdx, r14; unsigned __int64
0x180055fba  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x180055fbf  test    eax, eax
0x180055fc1  jnz     short loc_180055FCD
0x180055fc3  mov     ebx, 80070057h
0x180055fc8  jmp     loc_180056224
0x180055fcd  mov     rcx, [rsp+88h+arg_0]; this
0x180055fd5  mov     edx, 3; unsigned int
0x180055fda  call    ?OpenPropStg@CPropertyBagEx@@AEAAJK@Z; CPropertyBagEx::OpenPropStg(ulong)
0x180055fdf  mov     ebx, eax
0x180055fe1  cmp     eax, 80030002h
0x180055fe6  jnz     short loc_180056009
0x180055fe8  xor     edx, edx
0x180055fea  lea     ebp, [rdx+1]
0x180055fed  test    edi, edi
0x180055fef  jz      short loc_180056002
0x180055ff1  lea     rcx, [rdx+rdx*2]
0x180055ff5  xor     eax, eax
0x180055ff7  add     edx, ebp
0x180055ff9  mov     [r12+rcx*8], ax
0x180055ffe  cmp     edx, edi
0x180056000  jb      short loc_180055FF1
0x180056002  mov     ebx, ebp
0x180056004  jmp     loc_180056224
0x180056009  test    eax, eax
0x18005600b  js      loc_180056224
0x180056011  shl     rsi, 4
0x180056015  cmp     rsi, rbp
0x180056018  ja      loc_18005621F
0x18005601e  mov     ecx, esi; cb
0x180056020  call    cs:__imp_CoTaskMemAlloc
0x180056026  mov     r13, rax
0x180056029  test    rax, rax
0x18005602c  jnz     short loc_180056038
0x18005602e  mov     ebx, 8007000Eh
0x180056033  jmp     loc_180056224
0x180056038  mov     eax, 0FFFFFFFFh
0x18005603d  mov     ebp, 1
0x180056042  cmp     r14, rax
0x180056045  ja      loc_1800561E2
0x18005604b  mov     ecx, r14d; cb
0x18005604e  call    cs:__imp_CoTaskMemAlloc
0x180056054  mov     rsi, rax
0x180056057  test    rax, rax
0x18005605a  jnz     short loc_180056066
0x18005605c  mov     ebx, 8007000Eh
0x180056061  jmp     loc_1800561E9
0x180056066  xor     r8d, r8d
0x180056069  test    edi, edi
0x18005606b  jz      short loc_1800560A4
0x18005606d  xor     edx, edx
0x18005606f  lea     rax, [rdx+rdx*2]
0x180056073  xor     ecx, ecx
0x180056075  xorps   xmm0, xmm0
0x180056078  add     r8d, ebp
0x18005607b  movups  xmmword ptr [rsi+rax*8], xmm0
0x18005607f  mov     [rsi+rax*8+10h], rcx
0x180056084  mov     rcx, rdx
0x180056087  add     rcx, rcx
0x18005608a  mov     dword ptr [r13+rcx*8+0], 0
0x180056093  mov     rax, [r15+rdx*8]
0x180056097  add     rdx, rbp
0x18005609a  mov     [r13+rcx*8+8], rax
0x18005609f  cmp     r8d, edi
0x1800560a2  jb      short loc_18005606F
0x1800560a4  mov     rax, [rsp+88h+arg_0]
0x1800560ac  mov     r9, rsi
0x1800560af  mov     r8, r13
0x1800560b2  mov     edx, edi
0x1800560b4  mov     rcx, [rax+20h]
0x1800560b8  mov     rax, [rcx]
0x1800560bb  mov     rax, [rax+18h]
0x1800560bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560c4  mov     [rsp+88h+arg_8], eax
0x1800560cb  mov     ebx, eax
0x1800560cd  test    eax, eax
0x1800560cf  js      loc_1800561E9
0x1800560d5  xor     r15d, r15d
0x1800560d8  cmp     r15d, edi
0x1800560db  jnb     loc_18005619F
0x1800560e1  lea     r8, [r15+r15*2]
0x1800560e5  xor     eax, eax
0x1800560e7  movzx   edx, word ptr [r12+r8*8]
0x1800560ec  cmp     ax, dx
0x1800560ef  jz      loc_180056197
0x1800560f5  lea     r14, [rsi+r8*8]
0x1800560f9  movzx   ecx, word ptr [r14]
0x1800560fd  cmp     cx, dx
0x180056100  jz      loc_180056197
0x180056106  mov     qword ptr [rsp+88h+var_58+10h], rax
0x18005610b  xorps   xmm0, xmm0
0x18005610e  mov     eax, edx
0x180056110  btr     eax, 0Eh
0x180056114  sub     eax, 9
0x180056117  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x18005611c  test    eax, 0FFFFFFFBh
0x180056121  jnz     short loc_180056152
0x180056123  sub     cx, 44h ; 'D'; this
0x180056127  cmp     cx, bp
0x18005612a  ja      short loc_180056152
0x18005612c  movups  xmm0, xmmword ptr [r12+r8*8]
0x180056131  lea     rdx, [rsp+88h+var_58]; struct tagPROPVARIANT *
0x180056136  movsd   xmm1, qword ptr [r12+r8*8+10h]
0x18005613d  mov     r8, r14; struct tagPROPVARIANT *
0x180056140  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x180056145  movsd   qword ptr [rsp+88h+var_58+10h], xmm1
0x18005614b  call    ?LoadObject@CPropertyBagEx@@AEBAJPEAUtagPROPVARIANT@@0@Z; CPropertyBagEx::LoadObject(tagPROPVARIANT *,tagPROPVARIANT *)
0x180056150  jmp     short loc_180056173
0x180056152  mov     rax, [rsp+88h+arg_0]
0x18005615a  lea     rcx, [rsp+88h+var_58]; struct tagPROPVARIANT *
0x18005615f  mov     [rsp+88h+var_68], dx; __int16
0x180056164  xor     r9d, r9d
0x180056167  mov     rdx, r14
0x18005616a  mov     r8d, [rax+14h]
0x18005616e  call    StgPropVariantChangeType
0x180056173  mov     ebx, eax
0x180056175  test    eax, eax
0x180056177  js      short loc_1800561E9
0x180056179  mov     rcx, r14; pvar
0x18005617c  call    cs:__imp_PropVariantClear
0x180056182  movups  xmm0, xmmword ptr [rsp+88h+var_58]
0x180056187  movsd   xmm1, qword ptr [rsp+88h+var_58+10h]
0x18005618d  movups  xmmword ptr [r14], xmm0
0x180056191  movsd   qword ptr [r14+10h], xmm1
0x180056197  add     r15d, ebp
0x18005619a  jmp     loc_1800560D8
0x18005619f  xor     edx, edx
0x1800561a1  test    edi, edi
0x1800561a3  jz      short loc_1800561C5
0x1800561a5  lea     rcx, [rdx+rdx*2]
0x1800561a9  add     edx, ebp
0x1800561ab  movups  xmm0, xmmword ptr [rsi+rcx*8]
0x1800561af  movups  xmmword ptr [r12+rcx*8], xmm0
0x1800561b4  movsd   xmm1, qword ptr [rsi+rcx*8+10h]
0x1800561ba  movsd   qword ptr [r12+rcx*8+10h], xmm1
0x1800561c1  cmp     edx, edi
0x1800561c3  jb      short loc_1800561A5
0x1800561c5  mov     rcx, rsi; pv
0x1800561c8  call    cs:__imp_CoTaskMemFree
0x1800561ce  xor     esi, esi
0x1800561d0  test    ebx, ebx
0x1800561d2  js      short loc_1800561E9
0x1800561d4  xor     ebx, ebx
0x1800561d6  cmp     [rsp+88h+arg_8], ebp
0x1800561dd  setz    bl
0x1800561e0  jmp     short loc_1800561E9
0x1800561e2  xor     esi, esi
0x1800561e4  mov     ebx, 80070216h
0x1800561e9  mov     rcx, r13; pv
0x1800561ec  call    cs:__imp_CoTaskMemFree
0x1800561f2  test    rsi, rsi
0x1800561f5  jz      short loc_180056224
0x1800561f7  xor     r14d, r14d
0x1800561fa  test    edi, edi
0x1800561fc  jz      short loc_180056214
0x1800561fe  lea     rcx, [r14+r14*2]
0x180056202  lea     rcx, [rsi+rcx*8]; pvar
0x180056206  call    cs:__imp_PropVariantClear
0x18005620c  add     r14d, ebp
0x18005620f  cmp     r14d, edi
0x180056212  jb      short loc_1800561FE
0x180056214  mov     rcx, rsi; pv
0x180056217  call    cs:__imp_CoTaskMemFree
0x18005621d  jmp     short loc_180056224
0x18005621f  mov     ebx, 80070216h
0x180056224  mov     rax, [rsp+88h+arg_0]
0x18005622c  mov     rcx, [rax+28h]
0x180056230  mov     rax, [rcx]
0x180056233  mov     rax, [rax+20h]
0x180056237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005623c  mov     eax, ebx
0x18005623e  mov     rbx, [rsp+88h+arg_10]
0x180056246  add     rsp, 50h
0x18005624a  pop     r15
0x18005624c  pop     r14
0x18005624e  pop     r13
0x180056250  pop     r12
0x180056252  pop     rdi
0x180056253  pop     rsi
0x180056254  pop     rbp
0x180056255  retn
```
