# CPropertyBagEx::WriteMultiple(ulong,ushort const * const * const,tagPROPVARIANT const * const)

- ea: `0x1800564a0`
- end: `0x1800566e4`
- name: `?WriteMultiple@CPropertyBagEx@@UEAAJKQEBQEBGQEBUtagPROPVARIANT@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(CPropertyBagEx *__hidden this, unsigned int, const unsigned __int16 *const *const, const struct tagPROPVARIANT *const)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023e70`
- `0x18003a6b0`
- `0x18003e690`
- `0x18003f5e8`
- `0x180042800`
- `0x180055bfc`
- `0x1800564a0`
- `0x1800566ec`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056692`

## pseudocode

```c
__int64 __fastcall CPropertyBagEx::WriteMultiple(
        CPropertyBagEx *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        const struct tagPROPVARIANT *const a4)
{
  __int64 v5; // rsi
  int v8; // ebx
  struct tagPROPSPEC *v9; // rbp
  int v10; // edi
  __int64 i; // r8
  __int64 v12; // rcx
  __int64 v13; // rcx
  _BYTE *v14; // rax
  BYTE *pData; // xmm1_8
  _BYTE *v16; // rdx
  __int64 j; // rdi
  const struct tagPROPVARIANT *v18; // r8
  _BYTE *v20; // [rsp+30h] [rbp-668h] BYREF
  int v21; // [rsp+38h] [rbp-660h]
  _BYTE *v22; // [rsp+40h] [rbp-658h]
  int v23; // [rsp+48h] [rbp-650h]
  _BYTE v24[1536]; // [rsp+50h] [rbp-648h] BYREF

  v5 = a2;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), 0xFFFFFFFFLL);
  v21 = 64;
  v20 = v24;
  v23 = 24;
  v22 = v24;
  v8 = CStackBuffer::Init((CStackBuffer *)&v20, v5);
  if ( v8 >= 0 )
  {
    if ( (_DWORD)v5 )
    {
      if ( (unsigned int)v5 <= 0x200000 )
      {
        v8 = ValidateInRGLPOLESTR(v5, a3);
        if ( !v8 )
        {
          if ( (unsigned int)IsValidReadPtrIn(a4, 24 * v5) )
          {
            v8 = CPropertyBagEx::OpenPropStg(this, v8 + 1);
            if ( v8 >= 0 )
            {
              if ( (unsigned __int64)(16 * v5) > 0xFFFFFFFF )
              {
                v8 = -2147024362;
              }
              else
              {
                v9 = (struct tagPROPSPEC *)CoTaskMemAlloc((unsigned int)(16 * v5));
                if ( v9 )
                {
                  v10 = 0;
                  for ( i = 0; (unsigned int)i < (unsigned int)v5; i = (unsigned int)(i + 1) )
                  {
                    v12 = (unsigned int)i;
                    v9[v12].ulKind = 0;
                    v9[v12].lpwstr = (LPOLESTR)a3[i];
                    v13 = 3 * i;
                    v14 = v20;
                    pData = a4[i].bstrblobVal.pData;
                    *(_OWORD *)&v20[8 * v13] = *(_OWORD *)&a4[i].vt;
                    *(_QWORD *)&v14[8 * v13 + 16] = pData;
                    v16 = v20;
                    if ( (((*(_WORD *)&v20[24 * i] & 0xBFFF) - 9) & 0xFFFFFFFB) == 0 )
                    {
                      if ( !*(_QWORD *)&v20[24 * i + 8] )
                      {
                        v8 = -2147024809;
                        goto LABEL_27;
                      }
                      *(_OWORD *)&v20[24 * i] = 0;
                      *(_QWORD *)&v16[24 * i + 16] = 0;
                      v10 = 1;
                    }
                  }
                  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPSPEC *, _BYTE *, int))(**((_QWORD **)this + 4) + 32LL))(
                         *((_QWORD *)this + 4),
                         (unsigned int)v5,
                         v9,
                         v20,
                         2);
                  if ( v8 >= 0 )
                  {
                    if ( v10 )
                    {
                      for ( j = 0; (unsigned int)j < (unsigned int)v5; j = (unsigned int)(j + 1) )
                      {
                        v18 = &a4[j];
                        if ( (((v18->vt & 0xBFFF) - 9) & 0xFFFFFFFB) == 0 )
                        {
                          v8 = CPropertyBagEx::WriteOneObject(this, &v9[(unsigned int)j], v18);
                          if ( v8 < 0 )
                            goto LABEL_27;
                        }
                      }
                    }
                    v8 = 0;
                  }
LABEL_27:
                  CoTaskMemFree(v9);
                }
                else
                {
                  v8 = -2147024882;
                }
              }
            }
          }
          else
          {
            v8 = -2147024809;
          }
        }
      }
      else
      {
        v8 = -2147286953;
      }
    }
    else
    {
      v8 = 0;
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5));
  CStackBuffer::~CStackBuffer((CStackBuffer *)&v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800564a0  push    rbx
0x1800564a2  push    rbp
0x1800564a3  push    rsi
0x1800564a4  push    rdi
0x1800564a5  push    r12
0x1800564a7  push    r14
0x1800564a9  push    r15
0x1800564ab  sub     rsp, 660h
0x1800564b2  mov     rax, cs:__security_cookie
0x1800564b9  xor     rax, rsp
0x1800564bc  mov     [rsp+698h+var_48], rax
0x1800564c4  mov     r14, rcx
0x1800564c7  mov     esi, edx
0x1800564c9  mov     rcx, [rcx+28h]
0x1800564cd  mov     ebp, 0FFFFFFFFh
0x1800564d2  mov     edx, ebp
0x1800564d4  mov     r15, r9
0x1800564d7  mov     r12, r8
0x1800564da  mov     rax, [rcx]
0x1800564dd  mov     rax, [rax+18h]
0x1800564e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564e6  lea     rax, [rsp+698h+var_648]
0x1800564eb  mov     [rsp+698h+var_660], 40h ; '@'
0x1800564f3  mov     [rsp+698h+var_668], rax
0x1800564f8  lea     rcx, [rsp+698h+var_668]; this
0x1800564fd  lea     rax, [rsp+698h+var_648]
0x180056502  mov     [rsp+698h+var_650], 18h
0x18005650a  mov     edx, esi; unsigned int
0x18005650c  mov     [rsp+698h+var_658], rax
0x180056511  call    ?Init@CStackBuffer@@QEAAJK@Z; CStackBuffer::Init(ulong)
0x180056516  mov     ebx, eax
0x180056518  test    eax, eax
0x18005651a  js      loc_1800566A6
0x180056520  test    esi, esi
0x180056522  jnz     short loc_18005652B
0x180056524  xor     ebx, ebx
0x180056526  jmp     loc_1800566A6
0x18005652b  cmp     esi, 200000h
0x180056531  jbe     short loc_18005653D
0x180056533  mov     ebx, 80030057h
0x180056538  jmp     loc_1800566A6
0x18005653d  mov     rdx, r12; unsigned __int16 **
0x180056540  mov     ecx, esi; unsigned int
0x180056542  call    ?ValidateInRGLPOLESTR@@YAJKQEBQEBG@Z; ValidateInRGLPOLESTR(ulong,ushort const * const * const)
0x180056547  mov     ebx, eax
0x180056549  test    eax, eax
0x18005654b  jnz     loc_1800566A6
0x180056551  lea     rdx, [rsi+rsi*2]
0x180056555  mov     rcx, r15; void *
0x180056558  shl     rdx, 3; unsigned __int64
0x18005655c  mov     rdi, rsi
0x18005655f  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x180056564  test    eax, eax
0x180056566  jz      loc_1800566A1
0x18005656c  lea     edx, [rbx+1]; unsigned int
0x18005656f  mov     rcx, r14; this
0x180056572  call    ?OpenPropStg@CPropertyBagEx@@AEAAJK@Z; CPropertyBagEx::OpenPropStg(ulong)
0x180056577  mov     ebx, eax
0x180056579  test    eax, eax
0x18005657b  js      loc_1800566A6
0x180056581  shl     rdi, 4
0x180056585  cmp     rdi, rbp
0x180056588  ja      loc_18005669A
0x18005658e  mov     ecx, edi; cb
0x180056590  call    cs:__imp_CoTaskMemAlloc
0x180056596  mov     rbp, rax
0x180056599  test    rax, rax
0x18005659c  jnz     short loc_1800565A8
0x18005659e  mov     ebx, 8007000Eh
0x1800565a3  jmp     loc_1800566A6
0x1800565a8  xor     edi, edi
0x1800565aa  xor     r8d, r8d
0x1800565ad  cmp     r8d, esi
0x1800565b0  jnb     short loc_180056626
0x1800565b2  mov     ecx, r8d
0x1800565b5  add     rcx, rcx
0x1800565b8  mov     dword ptr [rbp+rcx*8+0], 0
0x1800565c0  mov     rax, [r12+r8*8]
0x1800565c4  mov     [rbp+rcx*8+8], rax
0x1800565c9  lea     rcx, [r8+r8*2]
0x1800565cd  mov     rax, [rsp+698h+var_668]
0x1800565d2  movups  xmm0, xmmword ptr [r15+rcx*8]
0x1800565d7  movsd   xmm1, qword ptr [r15+rcx*8+10h]
0x1800565de  movups  xmmword ptr [rax+rcx*8], xmm0
0x1800565e2  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x1800565e8  mov     rdx, [rsp+698h+var_668]
0x1800565ed  movzx   eax, word ptr [rdx+rcx*8]
0x1800565f1  btr     eax, 0Eh
0x1800565f5  sub     eax, 9
0x1800565f8  test    eax, 0FFFFFFFBh
0x1800565fd  jnz     short loc_18005661A
0x1800565ff  cmp     qword ptr [rdx+rcx*8+8], 0
0x180056605  jz      short loc_18005661F
0x180056607  xorps   xmm0, xmm0
0x18005660a  xor     eax, eax
0x18005660c  movups  xmmword ptr [rdx+rcx*8], xmm0
0x180056610  mov     [rdx+rcx*8+10h], rax
0x180056615  mov     edi, 1
0x18005661a  inc     r8d
0x18005661d  jmp     short loc_1800565AD
0x18005661f  mov     ebx, 80070057h
0x180056624  jmp     short loc_18005668F
0x180056626  mov     rcx, [r14+20h]
0x18005662a  mov     r8, rbp
0x18005662d  mov     r9, [rsp+698h+var_668]
0x180056632  mov     edx, esi
0x180056634  mov     [rsp+698h+var_678], 2
0x18005663c  mov     rax, [rcx]
0x18005663f  mov     rax, [rax+20h]
0x180056643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056648  mov     ebx, eax
0x18005664a  test    eax, eax
0x18005664c  js      short loc_18005668F
0x18005664e  test    edi, edi
0x180056650  jz      short loc_18005668D
0x180056652  xor     edi, edi
0x180056654  cmp     edi, esi
0x180056656  jnb     short loc_18005668D
0x180056658  lea     rax, [rdi+rdi*2]
0x18005665c  mov     edx, edi
0x18005665e  lea     r8, [r15+rax*8]; struct tagPROPVARIANT *
0x180056662  movzx   eax, word ptr [r8]
0x180056666  btr     eax, 0Eh
0x18005666a  sub     eax, 9
0x18005666d  test    eax, 0FFFFFFFBh
0x180056672  jnz     short loc_180056689
0x180056674  shl     rdx, 4
0x180056678  mov     rcx, r14; this
0x18005667b  add     rdx, rbp; struct tagPROPSPEC *
0x18005667e  call    ?WriteOneObject@CPropertyBagEx@@AEAAJPEBUtagPROPSPEC@@PEBUtagPROPVARIANT@@@Z; CPropertyBagEx::WriteOneObject(tagPROPSPEC const *,tagPROPVARIANT const *)
0x180056683  mov     ebx, eax
0x180056685  test    eax, eax
0x180056687  js      short loc_18005668F
0x180056689  inc     edi
0x18005668b  jmp     short loc_180056654
0x18005668d  xor     ebx, ebx
0x18005668f  mov     rcx, rbp; pv
0x180056692  call    cs:__imp_CoTaskMemFree
0x180056698  jmp     short loc_1800566A6
0x18005669a  mov     ebx, 80070216h
0x18005669f  jmp     short loc_1800566A6
0x1800566a1  mov     ebx, 80070057h
0x1800566a6  mov     rcx, [r14+28h]
0x1800566aa  mov     rax, [rcx]
0x1800566ad  mov     rax, [rax+20h]
0x1800566b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566b6  lea     rcx, [rsp+698h+var_668]; this
0x1800566bb  call    ??1CStackBuffer@@QEAA@XZ; CStackBuffer::~CStackBuffer(void)
0x1800566c0  mov     eax, ebx
0x1800566c2  mov     rcx, [rsp+698h+var_48]
0x1800566ca  xor     rcx, rsp; StackCookie
0x1800566cd  call    __security_check_cookie
0x1800566d2  add     rsp, 660h
0x1800566d9  pop     r15
0x1800566db  pop     r14
0x1800566dd  pop     r12
0x1800566df  pop     rdi
0x1800566e0  pop     rsi
0x1800566e1  pop     rbp
0x1800566e2  pop     rbx
0x1800566e3  retn
```
