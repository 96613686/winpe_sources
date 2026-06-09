# CPDFPackage::ImportComponentsAndRolesToProvider(CArray<CompInfo *,CompInfo * const &> *,int)

- ea: `0x18004557c`
- end: `0x18004594b`
- name: `?ImportComponentsAndRolesToProvider@CPDFPackage@@QEAAJPEAV?$CArray@PEAUCompInfo@@AEBQEAU1@@@H@Z`
- size: `975`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800474b0`

## callees

- `0x18004557c`
- `0x1800465e0`
- `0x180047104`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180045626`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180045799`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180045626`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180045799`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800455dd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045746`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045889`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800455dd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045746`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045889`

## pseudocode

```c
__int64 __fastcall CPDFPackage::ImportComponentsAndRolesToProvider(__int64 a1, __int64 a2)
{
  HRESULT SimpleTableDispenser; // ebx
  int v3; // r15d
  __int64 **v6; // rdi
  const OLECHAR *v7; // rcx
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // r14
  HRESULT v11; // eax
  bool v12; // zf
  const OLECHAR *v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  LPCOLESTR *v16; // rbx
  unsigned int v17; // esi
  unsigned int i; // edi
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 result; // rax
  struct ISimpleTableWrite *v23; // [rsp+50h] [rbp-29h] BYREF
  signed __int64 v24; // [rsp+58h] [rbp-21h] BYREF
  GUID *v25; // [rsp+60h] [rbp-19h] BYREF
  int v26; // [rsp+68h] [rbp-11h]
  int v27; // [rsp+6Ch] [rbp-Dh]
  int v28; // [rsp+70h] [rbp-9h]
  int v29; // [rsp+74h] [rbp-5h]
  GUID pclsid; // [rsp+78h] [rbp-1h] BYREF
  GUID v31; // [rsp+88h] [rbp+Fh] BYREF
  int v32; // [rsp+98h] [rbp+1Fh]
  int v33; // [rsp+9Ch] [rbp+23h]

  SimpleTableDispenser = 0;
  v3 = 0;
  if ( !*(_DWORD *)(a1 + 144) )
    goto LABEL_23;
  v6 = *(__int64 ***)(a1 + 128);
  v7 = *(const OLECHAR **)a1;
  pclsid = GUID_NULL;
  v23 = 0;
  SimpleTableDispenser = CLSIDFromString(v7, &pclsid);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_19;
  v8 = qword_180075518;
  *(_QWORD *)&v31.Data1 = &pclsid;
  *(_QWORD *)v31.Data4 = 0;
  v32 = 72;
  v33 = 16;
  v23 = 0;
  if ( qword_180075518 )
  {
LABEL_10:
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, GUID *, __int64, int, int, struct ISimpleTableWrite **))(*(_QWORD *)v8 + 24LL))(
                             v8,
                             didCOMSERVICES,
                             tidCOMSERVICES_LT_ROLEDEFINITION,
                             &v31,
                             1,
                             1,
                             12,
                             &v23);
    goto LABEL_11;
  }
  v24 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v24);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( !v24 )
    {
      SimpleTableDispenser = -2147024882;
      goto LABEL_19;
    }
    if ( _InterlockedCompareExchange64(&qword_180075518, v24, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v24 + 16LL))(v24);
    v8 = qword_180075518;
    goto LABEL_10;
  }
LABEL_11:
  if ( SimpleTableDispenser >= 0 )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v23 + 24LL))(v23);
    if ( SimpleTableDispenser >= 0 )
    {
      if ( v6 )
      {
        do
        {
          if ( SimpleTableDispenser )
            break;
          v10 = *v6;
          v11 = CPDFRole::ImportToProvider((CPDFRole *)v6[2], v23, v9);
          SimpleTableDispenser = v11;
          if ( v11 )
          {
            if ( v11 != 1115152 )
              break;
            SimpleTableDispenser = 0;
            v3 = 1;
          }
          v6 = (__int64 **)v10;
        }
        while ( v10 );
      }
    }
  }
LABEL_19:
  if ( v23 )
    (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v23 + 16LL))(v23);
  v12 = SimpleTableDispenser == 0;
  if ( SimpleTableDispenser >= 0 )
  {
    if ( SimpleTableDispenser )
      return (unsigned int)SimpleTableDispenser;
LABEL_23:
    if ( !*(_DWORD *)(a1 + 88) )
      goto LABEL_52;
    v13 = *(const OLECHAR **)a1;
    v23 = 0;
    v31 = GUID_NULL;
    pclsid = GUID_NULL;
    SimpleTableDispenser = CLSIDFromString(v13, &v31);
    if ( SimpleTableDispenser )
      goto LABEL_48;
    v14 = qword_180075518;
    v25 = &v31;
    v26 = 0;
    v27 = 9;
    v28 = 72;
    v29 = 16;
    v23 = 0;
    if ( !qword_180075518 )
    {
      v24 = 0;
      SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v24);
      if ( SimpleTableDispenser < 0 )
        goto LABEL_33;
      if ( !v24 )
      {
        SimpleTableDispenser = -2147024882;
LABEL_48:
        if ( v23 )
          (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v23 + 16LL))(v23);
        v12 = SimpleTableDispenser == 0;
        goto LABEL_51;
      }
      if ( _InterlockedCompareExchange64(&qword_180075518, v24, 0) )
        (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v24 + 16LL))(v24);
      v14 = qword_180075518;
    }
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, GUID **, __int64, int, int, struct ISimpleTableWrite **))(*(_QWORD *)v14 + 24LL))(
                             v14,
                             didCOMSERVICES,
                             tidCOMSERVICES_CLASSES,
                             &v25,
                             1,
                             1,
                             2097156,
                             &v23);
LABEL_33:
    if ( !SimpleTableDispenser )
    {
      if ( !v23 )
        return (unsigned int)-2147024882;
      SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v23 + 24LL))(v23);
      if ( !SimpleTableDispenser )
      {
        SimpleTableDispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v23 + 32LL))(v23);
        if ( !SimpleTableDispenser )
        {
          v15 = *(_QWORD **)(a1 + 72);
          while ( v15 )
          {
            v16 = (LPCOLESTR *)v15[2];
            v15 = (_QWORD *)*v15;
            CLSIDFromString(v16[1], &pclsid);
            SimpleTableDispenser = CPDFComponent::ImportToProvider((CPDFComponent *)v16, v23);
            if ( SimpleTableDispenser )
            {
              v17 = *(_DWORD *)(a2 + 16);
              for ( i = 0; i < v17; ++i )
              {
                v19 = memcmp_0(&GUID_NULL, &pclsid, 0x10u);
                v20 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL * (int)i);
                if ( v19 )
                {
                  v21 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)v20;
                  if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)v20 )
                    v21 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)(v20 + 8);
                  if ( v21 )
                    continue;
                }
                *(_DWORD *)(v20 + 104) = SimpleTableDispenser;
                SimpleTableDispenser = -2146368511;
              }
              goto LABEL_48;
            }
          }
        }
      }
    }
    goto LABEL_48;
  }
LABEL_51:
  if ( v12 )
  {
LABEL_52:
    result = 1115152;
    if ( v3 )
      return result;
  }
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18004557c  mov     [rsp-8+arg_10], rbx
0x180045581  mov     [rsp-8+arg_18], rsi
0x180045586  push    rbp
0x180045587  push    rdi
0x180045588  push    r13
0x18004558a  push    r14
0x18004558c  push    r15
0x18004558e  lea     rbp, [rsp-37h]
0x180045593  sub     rsp, 0B0h
0x18004559a  mov     rax, cs:__security_cookie
0x1800455a1  xor     rax, rsp
0x1800455a4  mov     [rbp+57h+var_30], rax
0x1800455a8  xor     ebx, ebx
0x1800455aa  xor     r15d, r15d
0x1800455ad  mov     r13, rdx
0x1800455b0  mov     rsi, rcx
0x1800455b3  cmp     [rcx+90h], ebx
0x1800455b9  jz      loc_18004571C
0x1800455bf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800455c6  mov     rdi, [rcx+80h]
0x1800455cd  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800455d1  mov     rcx, [rcx]; lpsz
0x1800455d4  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1800455d9  mov     [rbp+57h+var_80], rbx
0x1800455dd  call    cs:__imp_CLSIDFromString
0x1800455e3  mov     ebx, eax
0x1800455e5  test    eax, eax
0x1800455e7  js      loc_1800456F9
0x1800455ed  mov     rcx, cs:qword_180075518
0x1800455f4  lea     rax, [rbp+57h+pclsid]
0x1800455f8  mov     qword ptr [rbp+57h+var_48.Data1], rax
0x1800455fc  mov     qword ptr [rbp+57h+var_48.Data4], r15
0x180045600  mov     [rbp+57h+var_38], 48h ; 'H'
0x180045607  mov     [rbp+57h+var_34], 10h
0x18004560e  mov     [rbp+57h+var_80], r15
0x180045612  test    rcx, rcx
0x180045615  jnz     short loc_180045669
0x180045617  lea     rdx, [rbp+57h+var_78]
0x18004561b  mov     [rbp+57h+var_78], r15
0x18004561f  lea     rcx, IID_ISimpleTableDispenser
0x180045626  call    cs:__imp_GetSimpleTableDispenser
0x18004562c  mov     ebx, eax
0x18004562e  test    eax, eax
0x180045630  js      short loc_1800456AB
0x180045632  mov     rcx, [rbp+57h+var_78]
0x180045636  test    rcx, rcx
0x180045639  jnz     short loc_180045645
0x18004563b  mov     ebx, 8007000Eh
0x180045640  jmp     loc_1800456F9
0x180045645  xor     eax, eax
0x180045647  lock cmpxchg cs:qword_180075518, rcx
0x180045650  jz      short loc_180045662
0x180045652  mov     rcx, [rbp+57h+var_78]
0x180045656  mov     rax, [rcx]
0x180045659  mov     rax, [rax+10h]
0x18004565d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045662  mov     rcx, cs:qword_180075518
0x180045669  mov     rax, [rcx]
0x18004566c  lea     rdx, [rbp+57h+var_80]
0x180045670  mov     [rsp+0D0h+var_98], rdx
0x180045675  lea     r9, [rbp+57h+var_48]
0x180045679  mov     [rsp+0D0h+var_A0], 0Ch
0x180045681  lea     r8, tidCOMSERVICES_LT_ROLEDEFINITION
0x180045688  mov     [rsp+0D0h+var_A8], 1
0x180045690  lea     rdx, didCOMSERVICES
0x180045697  mov     rax, [rax+18h]
0x18004569b  mov     [rsp+0D0h+var_B0], 1
0x1800456a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800456a9  mov     ebx, eax
0x1800456ab  test    ebx, ebx
0x1800456ad  js      short loc_1800456F9
0x1800456af  mov     rcx, [rbp+57h+var_80]
0x1800456b3  mov     rax, [rcx]
0x1800456b6  mov     rax, [rax+18h]
0x1800456ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800456bf  mov     ebx, eax
0x1800456c1  test    eax, eax
0x1800456c3  js      short loc_1800456F9
0x1800456c5  test    rdi, rdi
0x1800456c8  jz      short loc_1800456F9
0x1800456ca  test    ebx, ebx
0x1800456cc  jnz     short loc_1800456F9
0x1800456ce  mov     rdx, [rbp+57h+var_80]; struct ISimpleTableWrite *
0x1800456d2  mov     rcx, [rdi+10h]; this
0x1800456d6  mov     r14, [rdi]
0x1800456d9  call    ?ImportToProvider@CPDFRole@@QEAAJPEAUISimpleTableWrite@@H@Z; CPDFRole::ImportToProvider(ISimpleTableWrite *,int)
0x1800456de  mov     ebx, eax
0x1800456e0  test    eax, eax
0x1800456e2  jz      short loc_1800456F1
0x1800456e4  cmp     eax, 110410h
0x1800456e9  jnz     short loc_1800456F9
0x1800456eb  xor     ebx, ebx
0x1800456ed  lea     r15d, [rbx+1]
0x1800456f1  mov     rdi, r14
0x1800456f4  test    r14, r14
0x1800456f7  jnz     short loc_1800456CA
0x1800456f9  mov     rcx, [rbp+57h+var_80]
0x1800456fd  test    rcx, rcx
0x180045700  jz      short loc_18004570E
0x180045702  mov     rax, [rcx]
0x180045705  mov     rax, [rax+10h]
0x180045709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004570e  test    ebx, ebx
0x180045710  js      loc_180045915
0x180045716  jnz     loc_180045921
0x18004571c  cmp     dword ptr [rsi+58h], 0
0x180045720  jz      loc_180045917
0x180045726  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004572d  mov     rcx, [rsi]; lpsz
0x180045730  lea     rdx, [rbp+57h+var_48]; pclsid
0x180045734  mov     [rbp+57h+var_80], 0
0x18004573c  movdqu  xmmword ptr [rbp+57h+var_48.Data1], xmm0
0x180045741  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180045746  call    cs:__imp_CLSIDFromString
0x18004574c  mov     ebx, eax
0x18004574e  test    eax, eax
0x180045750  jnz     loc_1800458FE
0x180045756  mov     rcx, cs:qword_180075518
0x18004575d  lea     rax, [rbp+57h+var_48]
0x180045761  mov     [rbp+57h+var_70], rax
0x180045765  mov     [rbp+57h+var_68], ebx
0x180045768  mov     [rbp+57h+var_64], 9
0x18004576f  mov     [rbp+57h+var_60], 48h ; 'H'
0x180045776  mov     [rbp+57h+var_5C], 10h
0x18004577d  mov     [rbp+57h+var_80], 0
0x180045785  test    rcx, rcx
0x180045788  jnz     short loc_1800457DC
0x18004578a  mov     [rbp+57h+var_78], rcx
0x18004578e  lea     rdx, [rbp+57h+var_78]
0x180045792  lea     rcx, IID_ISimpleTableDispenser
0x180045799  call    cs:__imp_GetSimpleTableDispenser
0x18004579f  mov     ebx, eax
0x1800457a1  test    eax, eax
0x1800457a3  js      short loc_18004581E
0x1800457a5  mov     rcx, [rbp+57h+var_78]
0x1800457a9  test    rcx, rcx
0x1800457ac  jnz     short loc_1800457B8
0x1800457ae  mov     ebx, 8007000Eh
0x1800457b3  jmp     loc_1800458FE
0x1800457b8  xor     eax, eax
0x1800457ba  lock cmpxchg cs:qword_180075518, rcx
0x1800457c3  jz      short loc_1800457D5
0x1800457c5  mov     rcx, [rbp+57h+var_78]
0x1800457c9  mov     rax, [rcx]
0x1800457cc  mov     rax, [rax+10h]
0x1800457d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457d5  mov     rcx, cs:qword_180075518
0x1800457dc  mov     rax, [rcx]
0x1800457df  lea     r8, [rbp+57h+var_80]
0x1800457e3  mov     [rsp+0D0h+var_98], r8
0x1800457e8  lea     r9, [rbp+57h+var_70]
0x1800457ec  mov     [rsp+0D0h+var_A0], 200004h
0x1800457f4  lea     r8, tidCOMSERVICES_CLASSES
0x1800457fb  mov     [rsp+0D0h+var_A8], 1
0x180045803  lea     rdx, didCOMSERVICES
0x18004580a  mov     rax, [rax+18h]
0x18004580e  mov     [rsp+0D0h+var_B0], 1
0x180045817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004581c  mov     ebx, eax
0x18004581e  test    ebx, ebx
0x180045820  jnz     loc_1800458FE
0x180045826  mov     rcx, [rbp+57h+var_80]
0x18004582a  test    rcx, rcx
0x18004582d  jnz     short loc_180045839
0x18004582f  mov     ebx, 8007000Eh
0x180045834  jmp     loc_180045921
0x180045839  mov     rax, [rcx]
0x18004583c  mov     rax, [rax+18h]
0x180045840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045845  mov     ebx, eax
0x180045847  test    eax, eax
0x180045849  jnz     loc_1800458FE
0x18004584f  mov     rcx, [rbp+57h+var_80]
0x180045853  mov     rax, [rcx]
0x180045856  mov     rax, [rax+20h]
0x18004585a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004585f  mov     ebx, eax
0x180045861  test    eax, eax
0x180045863  jnz     loc_1800458FE
0x180045869  mov     rdi, [rsi+48h]
0x18004586d  test    rdi, rdi
0x180045870  jz      loc_1800458FE
0x180045876  test    ebx, ebx
0x180045878  jnz     short loc_1800458A1
0x18004587a  mov     rbx, [rdi+10h]
0x18004587e  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180045882  mov     rdi, [rdi]
0x180045885  mov     rcx, [rbx+8]; lpsz
0x180045889  call    cs:__imp_CLSIDFromString
0x18004588f  mov     rdx, [rbp+57h+var_80]; struct ISimpleTableWrite *
0x180045893  mov     rcx, rbx; this
0x180045896  call    ?ImportToProvider@CPDFComponent@@QEAAJPEAUISimpleTableWrite@@@Z; CPDFComponent::ImportToProvider(ISimpleTableWrite *)
0x18004589b  mov     ebx, eax
0x18004589d  test    eax, eax
0x18004589f  jz      short loc_18004586D
0x1800458a1  mov     esi, [r13+10h]
0x1800458a5  xor     edi, edi
0x1800458a7  test    esi, esi
0x1800458a9  jz      short loc_1800458FE
0x1800458ab  mov     r14d, 80110401h
0x1800458b1  mov     r8d, 10h; Size
0x1800458b7  lea     rdx, [rbp+57h+pclsid]; Buf2
0x1800458bb  lea     rcx, GUID_NULL; Buf1
0x1800458c2  call    memcmp_0
0x1800458c7  test    eax, eax
0x1800458c9  movsxd  rcx, edi
0x1800458cc  mov     rax, [r13+8]
0x1800458d0  setz    dl
0x1800458d3  mov     r8, [rax+rcx*8]
0x1800458d7  test    dl, dl
0x1800458d9  jnz     short loc_1800458F1
0x1800458db  mov     rax, qword ptr [rbp+57h+pclsid.Data1]
0x1800458df  sub     rax, [r8]
0x1800458e2  jnz     short loc_1800458EC
0x1800458e4  mov     rax, qword ptr [rbp+57h+pclsid.Data4]
0x1800458e8  sub     rax, [r8+8]
0x1800458ec  test    rax, rax
0x1800458ef  jnz     short loc_1800458F8
0x1800458f1  mov     [r8+68h], ebx
0x1800458f5  mov     ebx, r14d
0x1800458f8  inc     edi
0x1800458fa  cmp     edi, esi
0x1800458fc  jb      short loc_1800458B1
0x1800458fe  mov     rcx, [rbp+57h+var_80]
0x180045902  test    rcx, rcx
0x180045905  jz      short loc_180045913
0x180045907  mov     rdx, [rcx]
0x18004590a  mov     rax, [rdx+10h]
0x18004590e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045913  test    ebx, ebx
0x180045915  jnz     short loc_180045921
0x180045917  mov     eax, 110410h
0x18004591c  test    r15d, r15d
0x18004591f  jnz     short loc_180045923
0x180045921  mov     eax, ebx
0x180045923  mov     rcx, [rbp+57h+var_30]
0x180045927  xor     rcx, rsp; StackCookie
0x18004592a  call    __security_check_cookie
0x18004592f  lea     r11, [rsp+0D0h+var_20]
0x180045937  mov     rbx, [r11+40h]
0x18004593b  mov     rsi, [r11+48h]
0x18004593f  mov     rsp, r11
0x180045942  pop     r15
0x180045944  pop     r14
0x180045946  pop     r13
0x180045948  pop     rdi
0x180045949  pop     rbp
0x18004594a  retn
```
