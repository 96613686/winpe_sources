# SAXReader::putProperty(ushort const *,tagVARIANT)

- ea: `0x1800d0210`
- end: `0x1800d05f4`
- name: `?putProperty@SAXReader@@UEAAJPEBGUtagVARIANT@@@Z`
- size: `996`
- prototype: `int(SAXReader *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180012000`
- `0x18002ac90`
- `0x18002b204`
- `0x18002d7e0`
- `0x1800368b4`
- `0x18005f9b8`
- `0x180064034`
- `0x1800d0210`
- `0x1800e9198`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800d04e4`
- `msvcrt!_resetstkoflw` at `0x1800d04e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d0537`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d0537`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d04d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d0563`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d04d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d0563`
- `OLEAUT32!__imp_VariantCopy` at `0x1800d04bb`
- `OLEAUT32!__imp_VariantCopy` at `0x1800d04bb`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800d0419`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800d0419`

## pseudocode

```c
__int64 __fastcall SAXReader::putProperty(struct IUnknown **this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  int v6; // ebx
  struct IUnknown *v8; // r13
  struct IUnknown *v9; // r12
  unsigned int v10; // edi
  int i; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  void **v16; // rbx
  struct IUnknown **v17; // rcx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  unsigned __int16 BaseType; // ax
  VARIANTARG *v23; // rcx
  HRESULT v24; // eax
  struct IUnknown *v25; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  VARIANTARG pvargDest; // [rsp+48h] [rbp-60h] BYREF
  __int128 v28; // [rsp+60h] [rbp-48h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp-38h]
  char v31; // [rsp+C8h] [rbp+20h] BYREF

  v6 = ModelInit::init(&v31, 0, a3);
  if ( v6 < 0 )
  {
    ModelInit::~ModelInit((ModelInit *)&v31);
    return (unsigned int)v6;
  }
  v8 = 0;
  v9 = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( a2 )
  {
    v10 = 0;
    for ( i = 9; ; ++i )
    {
      if ( i > 20 )
      {
        ModelInit::~ModelInit((ModelInit *)&v31);
        return 2147942487LL;
      }
      if ( String::equals((String *)(&SAXNames::_cstrings)[i], a2) )
        break;
    }
    if ( i <= 15 )
    {
      if ( i != 15 )
      {
        v12 = i - 9;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              v15 = v14 - 1;
              if ( v15 )
              {
                if ( (unsigned int)(v15 - 1) > 1 )
                  goto LABEL_42;
              }
            }
            goto LABEL_16;
          }
          v9 = Variant::QIForIID(a3, &IID_ISAXDeclHandler);
          v16 = (void **)(this + 25);
          assign(this + 25, v9);
          v17 = (struct IUnknown **)&this[19][11];
        }
        else
        {
          v8 = Variant::QIForIID(a3, &IID_ISAXLexicalHandler);
          v16 = (void **)(this + 24);
          assign(this + 24, v8);
          assign((struct IUnknown **)&this[18][12], this[24]);
          v17 = (struct IUnknown **)&this[19][10];
        }
        assign(v17, *v16);
        goto LABEL_42;
      }
LABEL_16:
      v10 = -2147467259;
      goto LABEL_42;
    }
    v18 = i - 16;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( !v19 )
      {
        if ( a3->vt == 11 )
          *((_BYTE *)this + 225) = a3->iVal != 0;
        else
          v10 = -2147467259;
        goto LABEL_42;
      }
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 != 1 )
            goto LABEL_42;
          BaseType = Variant::getBaseType(a3);
          if ( BaseType && BaseType != 1 && BaseType != 8 && BaseType != 10 )
          {
            v10 = -2147024809;
            goto LABEL_42;
          }
          v23 = (VARIANTARG *)(this + 32);
          goto LABEL_40;
        }
        pvargDest.vt = 0;
        if ( VariantChangeTypeEx(&pvargDest, a3, 0x409u, 0, 3u) < 0 || pvargDest.lVal > 0x3FFFFFu )
        {
          v10 = -2147024809;
          goto LABEL_42;
        }
        v24 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))this[15]->lpVtbl[10].AddRef)(
                this[15],
                (unsigned int)(pvargDest.lVal << 10));
      }
      else
      {
        v25 = this[15];
        lpVtbl = v25->lpVtbl;
        v28 = *(_OWORD *)&a3->vt;
        pRecInfo = a3->pRecInfo;
        v24 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, __int128 *))lpVtbl[11].QueryInterface)(
                v25,
                L"MaxElementDepth",
                &v28);
      }
LABEL_41:
      v10 = v24;
      goto LABEL_42;
    }
    v23 = (VARIANTARG *)(this + 29);
LABEL_40:
    v24 = VariantCopy(v23, a3);
    goto LABEL_41;
  }
  v10 = -2147024809;
LABEL_42:
  if ( v8 )
    ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->Release)(v8);
  if ( v9 )
    ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
  ModelInit::~ModelInit((ModelInit *)&v31);
  return v10;
}

```

## disassembly

```asm
0x1800d0210  mov     rax, rsp
0x1800d0213  mov     [rax+8], rbx
0x1800d0217  mov     [rax+18h], rsi
0x1800d021b  mov     [rax+10h], rdx
0x1800d021f  push    rdi
0x1800d0220  push    r12
0x1800d0222  push    r13
0x1800d0224  push    r14
0x1800d0226  push    r15
0x1800d0228  sub     rsp, 80h
0x1800d022f  mov     r14, r8
0x1800d0232  mov     rdi, rdx
0x1800d0235  mov     r15, rcx
0x1800d0238  xor     edx, edx
0x1800d023a  lea     rcx, [rax+20h]
0x1800d023e  call    ?init@ModelInit@@QEAAJW4RentalEnum@@@Z; ModelInit::init(RentalEnum)
0x1800d0243  mov     ebx, eax
0x1800d0245  xor     esi, esi
0x1800d0247  test    eax, eax
0x1800d0249  jns     short loc_1800D025F
0x1800d024b  lea     rcx, [rsp+0A8h+arg_18]; this
0x1800d0253  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800d0258  mov     eax, ebx
0x1800d025a  jmp     loc_1800D05D0
0x1800d025f  mov     r13, rsi
0x1800d0262  mov     [rsp+0A8h+var_70], rsi
0x1800d0267  mov     r12, rsi
0x1800d026a  mov     [rsp+0A8h+var_68], rsi
0x1800d026f  xorps   xmm0, xmm0
0x1800d0272  xor     eax, eax
0x1800d0274  movups  xmmword ptr [rsp+0A8h+pvargDest], xmm0
0x1800d0279  mov     qword ptr [rsp+0A8h+pvargDest+10h], rax
0x1800d027e  test    rdi, rdi
0x1800d0281  jnz     short loc_1800D028D
0x1800d0283  mov     edi, 80070057h
0x1800d0288  jmp     loc_1800D0597
0x1800d028d  mov     edi, esi
0x1800d028f  mov     ebx, 9
0x1800d0294  cmp     ebx, 14h
0x1800d0297  jle     short loc_1800D02B0
0x1800d0299  lea     rcx, [rsp+0A8h+arg_18]; this
0x1800d02a1  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800d02a6  mov     eax, 80070057h
0x1800d02ab  jmp     loc_1800D05D0
0x1800d02b0  movsxd  rcx, ebx
0x1800d02b3  lea     rax, ?_cstrings@SAXNames@@2QBQEBVString@@B; String const * const near * const SAXNames::_cstrings
0x1800d02ba  mov     rdx, [rsp+0A8h+arg_8]; unsigned __int16 *
0x1800d02c2  mov     rcx, [rax+rcx*8]; this
0x1800d02c6  call    ?equals@String@@QEAA_NPEBG@Z; String::equals(ushort const *)
0x1800d02cb  test    al, al
0x1800d02cd  jz      loc_1800D05ED
0x1800d02d3  cmp     ebx, 0Fh
0x1800d02d6  jg      loc_1800D0398
0x1800d02dc  jz      short loc_1800D0300
0x1800d02de  sub     ebx, 9
0x1800d02e1  jz      short loc_1800D0344
0x1800d02e3  sub     ebx, 1
0x1800d02e6  jz      short loc_1800D030E
0x1800d02e8  sub     ebx, 1
0x1800d02eb  jz      short loc_1800D0300
0x1800d02ed  sub     ebx, 1
0x1800d02f0  jz      short loc_1800D0300
0x1800d02f2  sub     ebx, 1
0x1800d02f5  jz      short loc_1800D0300
0x1800d02f7  cmp     ebx, 1
0x1800d02fa  jnz     loc_1800D04C7
0x1800d0300  mov     edi, 80004005h
0x1800d0305  mov     [rsp+0A8h+var_78], edi
0x1800d0309  jmp     loc_1800D04C7
0x1800d030e  lea     rdx, IID_ISAXDeclHandler; struct _GUID *
0x1800d0315  mov     rcx, r14; struct tagVARIANT *
0x1800d0318  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x1800d031d  mov     r12, rax
0x1800d0320  mov     [rsp+0A8h+var_68], rax
0x1800d0325  lea     rbx, [r15+0C8h]
0x1800d032c  mov     rdx, rax; void *
0x1800d032f  mov     rcx, rbx; struct IUnknown **
0x1800d0332  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d0337  mov     rcx, [r15+98h]
0x1800d033e  add     rcx, 58h ; 'X'
0x1800d0342  jmp     short loc_1800D038B
0x1800d0344  lea     rdx, IID_ISAXLexicalHandler; struct _GUID *
0x1800d034b  mov     rcx, r14; struct tagVARIANT *
0x1800d034e  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x1800d0353  mov     r13, rax
0x1800d0356  mov     [rsp+0A8h+var_70], rax
0x1800d035b  lea     rbx, [r15+0C0h]
0x1800d0362  mov     rdx, rax; void *
0x1800d0365  mov     rcx, rbx; struct IUnknown **
0x1800d0368  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d036d  mov     rcx, [r15+90h]
0x1800d0374  add     rcx, 60h ; '`'; struct IUnknown **
0x1800d0378  mov     rdx, [rbx]; void *
0x1800d037b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d0380  mov     rcx, [r15+98h]
0x1800d0387  add     rcx, 50h ; 'P'; struct IUnknown **
0x1800d038b  mov     rdx, [rbx]; void *
0x1800d038e  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d0393  jmp     loc_1800D04C7
0x1800d0398  sub     ebx, 10h
0x1800d039b  jz      loc_1800D04B1
0x1800d03a1  sub     ebx, 1
0x1800d03a4  jz      loc_1800D048B
0x1800d03aa  sub     ebx, 1
0x1800d03ad  jz      loc_1800D0455
0x1800d03b3  sub     ebx, 1
0x1800d03b6  jz      short loc_1800D03F9
0x1800d03b8  cmp     ebx, 1
0x1800d03bb  jnz     loc_1800D04C7
0x1800d03c1  mov     rcx, r14; struct tagVARIANT *
0x1800d03c4  call    ?getBaseType@Variant@@SAGPEAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1800d03c9  movzx   r8d, ax
0x1800d03cd  test    r8d, r8d
0x1800d03d0  jz      short loc_1800D03ED
0x1800d03d2  sub     r8d, ebx
0x1800d03d5  jz      short loc_1800D03ED
0x1800d03d7  sub     r8d, 7
0x1800d03db  jz      short loc_1800D03ED
0x1800d03dd  cmp     r8d, 2
0x1800d03e1  jz      short loc_1800D03ED
0x1800d03e3  mov     edi, 80070057h
0x1800d03e8  jmp     loc_1800D0305
0x1800d03ed  lea     rcx, [r15+100h]
0x1800d03f4  jmp     loc_1800D04B8
0x1800d03f9  mov     word ptr [rsp+0A8h+pvargDest], si
0x1800d03fe  mov     eax, 3
0x1800d0403  xor     r9d, r9d; wFlags
0x1800d0406  mov     [rsp+0A8h+vt], ax; vt
0x1800d040b  mov     r8d, 409h; lcid
0x1800d0411  mov     rdx, r14; pvarSrc
0x1800d0414  lea     rcx, [rsp+0A8h+pvargDest]; pvargDest
0x1800d0419  call    cs:__imp_VariantChangeTypeEx
0x1800d041f  test    eax, eax
0x1800d0421  js      short loc_1800D0447
0x1800d0423  mov     edx, dword ptr [rsp+0A8h+pvargDest+8]
0x1800d0427  cmp     edx, 3FFFFFh
0x1800d042d  ja      short loc_1800D0447
0x1800d042f  mov     rcx, [r15+78h]
0x1800d0433  mov     rax, [rcx]
0x1800d0436  shl     edx, 0Ah
0x1800d0439  mov     rax, [rax+0F8h]
0x1800d0440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0445  jmp     short loc_1800D04C1
0x1800d0447  mov     edi, 80070057h
0x1800d044c  mov     [rsp+0A8h+var_78], edi
0x1800d0450  jmp     loc_1800D0597
0x1800d0455  mov     rcx, [r15+78h]
0x1800d0459  mov     rax, [rcx]
0x1800d045c  movups  xmm0, xmmword ptr [r14]
0x1800d0460  movaps  [rsp+0A8h+var_48], xmm0
0x1800d0465  movsd   xmm1, qword ptr [r14+10h]
0x1800d046b  movsd   [rsp+0A8h+var_38], xmm1
0x1800d0471  lea     r8, [rsp+0A8h+var_48]
0x1800d0476  lea     rdx, ?s_MaxElementDepth_pwz@XMLParser@@2QBGB; "MaxElementDepth"
0x1800d047d  mov     rax, [rax+108h]
0x1800d0484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0489  jmp     short loc_1800D04C1
0x1800d048b  cmp     word ptr [r14], 0Bh
0x1800d0490  jz      short loc_1800D04A0
0x1800d0492  mov     edi, 80004005h
0x1800d0497  mov     [rsp+0A8h+var_78], edi
0x1800d049b  jmp     loc_1800D0597
0x1800d04a0  cmp     [r14+8], si
0x1800d04a5  setnz   al
0x1800d04a8  mov     [r15+0E1h], al
0x1800d04af  jmp     short loc_1800D04C7
0x1800d04b1  lea     rcx, [r15+0E8h]; pvargDest
0x1800d04b8  mov     rdx, r14; pvargSrc
0x1800d04bb  call    cs:__imp_VariantCopy
0x1800d04c1  mov     [rsp+0A8h+var_78], eax
0x1800d04c5  mov     edi, eax
0x1800d04c7  jmp     loc_1800D0597
0x1800d04cc  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800d04d2  call    cs:__imp_TlsGetValue
0x1800d04d8  mov     rbx, rax
0x1800d04db  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800d04e2  jnz     short loc_1800D055D
0x1800d04e4  call    cs:__imp__resetstkoflw
0x1800d04ea  test    eax, eax
0x1800d04ec  jnz     short loc_1800D053F
0x1800d04ee  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800d04f5  test    rcx, rcx
0x1800d04f8  jz      short loc_1800D050C
0x1800d04fa  cmp     [rcx+50h], rbx
0x1800d04fe  jnz     short loc_1800D050C
0x1800d0500  mov     rax, [rcx]
0x1800d0503  mov     rax, [rax+20h]
0x1800d0507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d050c  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800d0513  test    rcx, rcx
0x1800d0516  jz      short loc_1800D052A
0x1800d0518  cmp     [rcx+50h], rbx
0x1800d051c  jnz     short loc_1800D052A
0x1800d051e  mov     rax, [rcx]
0x1800d0521  mov     rax, [rax+20h]
0x1800d0525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d052a  xor     r9d, r9d; lpArguments
0x1800d052d  xor     r8d, r8d; nNumberOfArguments
0x1800d0530  xor     edx, edx; dwExceptionFlags
0x1800d0532  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800d0537  call    cs:__imp_RaiseException
0x1800d053d  jmp     short loc_1800D055D
0x1800d053f  mov     rax, [rbx+60h]
0x1800d0543  mov     [rbx+68h], rax
0x1800d0547  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800d054e  mov     [rbx+60h], rax
0x1800d0552  mov     dword ptr [rbx+54h], 800703E9h
0x1800d0559  mov     byte ptr [rbx+78h], 0
0x1800d055d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800d0563  call    cs:__imp_TlsGetValue
0x1800d0569  mov     rcx, [rax+60h]; struct Exception *
0x1800d056d  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800d0572  mov     rdx, rax
0x1800d0575  mov     rcx, [rax]
0x1800d0578  mov     rax, [rcx+80h]
0x1800d057f  mov     rcx, rdx
0x1800d0582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0587  mov     edi, eax
0x1800d0589  mov     [rsp+0A8h+var_78], eax
0x1800d058d  mov     r13, [rsp+0A8h+var_70]
0x1800d0592  mov     r12, [rsp+0A8h+var_68]
0x1800d0597  test    r13, r13
0x1800d059a  jz      short loc_1800D05AC
0x1800d059c  mov     rax, [r13+0]
0x1800d05a0  mov     rcx, r13
0x1800d05a3  mov     rax, [rax+10h]
0x1800d05a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d05ac  test    r12, r12
0x1800d05af  jz      short loc_1800D05C1
0x1800d05b1  mov     rax, [r12]
0x1800d05b5  mov     rcx, r12
0x1800d05b8  mov     rax, [rax+10h]
0x1800d05bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d05c1  lea     rcx, [rsp+0A8h+arg_18]; this
0x1800d05c9  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800d05ce  mov     eax, edi
0x1800d05d0  lea     r11, [rsp+0A8h+var_28]
0x1800d05d8  mov     rbx, [r11+30h]
0x1800d05dc  mov     rsi, [r11+40h]
0x1800d05e0  mov     rsp, r11
0x1800d05e3  pop     r15
0x1800d05e5  pop     r14
0x1800d05e7  pop     r13
0x1800d05e9  pop     r12
0x1800d05eb  pop     rdi
0x1800d05ec  retn
0x1800d05ed  inc     ebx
0x1800d05ef  jmp     loc_1800D0294
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
