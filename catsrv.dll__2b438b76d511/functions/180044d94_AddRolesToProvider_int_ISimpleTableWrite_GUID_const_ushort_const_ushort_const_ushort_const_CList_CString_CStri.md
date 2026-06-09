# AddRolesToProvider(int,ISimpleTableWrite *,_GUID const &,ushort const *,ushort const *,ushort const *,CList<CString,CString &> &)

- ea: `0x180044d94`
- end: `0x180045225`
- name: `?AddRolesToProvider@@YAJHPEAUISimpleTableWrite@@AEBU_GUID@@PEBG22AEAV?$CList@VCString@@AEAV1@@@@Z`
- size: `1169`
- prototype: `__int64 __fastcall(int, __int64, __int64, const OLECHAR *, const OLECHAR *lpsz, const OLECHAR *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800465e0`
- `0x180046e60`

## callees

- `0x180044d94`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180044e5c`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180044e5c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180044e11`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180044fed`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800450bc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800450d3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180044e11`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180044fed`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800450bc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800450d3`

## pseudocode

```c
__int64 __fastcall AddRolesToProvider(
        int a1,
        __int64 a2,
        __int64 a3,
        const OLECHAR *a4,
        const OLECHAR *lpsz,
        const OLECHAR *a6,
        __int64 a7)
{
  HRESULT SimpleTableDispenser; // ebx
  __int64 v11; // rcx
  _QWORD *i; // rsi
  _QWORD *v13; // r15
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 v16; // [rsp+50h] [rbp-61h] BYREF
  int v17; // [rsp+58h] [rbp-59h] BYREF
  int v18; // [rsp+5Ch] [rbp-55h]
  signed __int64 v19; // [rsp+60h] [rbp-51h] BYREF
  _QWORD v20[2]; // [rsp+68h] [rbp-49h] BYREF
  int v21; // [rsp+78h] [rbp-39h]
  int v22; // [rsp+7Ch] [rbp-35h]
  GUID v23; // [rsp+80h] [rbp-31h] BYREF
  GUID pclsid; // [rsp+90h] [rbp-21h] BYREF
  GUID v25; // [rsp+A0h] [rbp-11h] BYREF

  v18 = a1;
  v17 = 1;
  pclsid = GUID_NULL;
  v23 = GUID_NULL;
  v25 = GUID_NULL;
  if ( !a2 )
    return 2147942487LL;
  v16 = 0;
  SimpleTableDispenser = CLSIDFromString(a4, &pclsid);
  if ( SimpleTableDispenser >= 0 )
  {
    v11 = qword_180075518;
    v20[0] = &pclsid;
    v20[1] = 0;
    v21 = 72;
    v22 = 16;
    v16 = 0;
    if ( !qword_180075518 )
    {
      v19 = 0;
      SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v19);
      if ( SimpleTableDispenser < 0 )
      {
LABEL_12:
        if ( SimpleTableDispenser >= 0 )
        {
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
          if ( SimpleTableDispenser >= 0 )
          {
            for ( i = *(_QWORD **)(a7 + 8); i; i = v13 )
            {
              if ( SimpleTableDispenser )
                break;
              v13 = (_QWORD *)*i;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 120LL))(v16);
              if ( SimpleTableDispenser < 0 )
                break;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *))(*(_QWORD *)v16 + 160LL))(
                                       v16,
                                       0,
                                       0,
                                       &pclsid);
              if ( SimpleTableDispenser < 0 )
                break;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 160LL))(
                                       v16,
                                       1,
                                       0,
                                       i[2]);
              if ( SimpleTableDispenser < 0 )
                break;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 144LL))(v16);
              if ( SimpleTableDispenser < 0 )
                break;
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 96LL))(v16);
              SimpleTableDispenser = v14;
              if ( v14 )
              {
                if ( v14 != -2146368500 )
                  break;
              }
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
              if ( SimpleTableDispenser < 0 )
                break;
              if ( v18 == 30 )
              {
                if ( !lpsz )
                  goto LABEL_45;
                SimpleTableDispenser = CLSIDFromString(lpsz, &v23);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         0,
                                         0,
                                         &v23);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         1,
                                         0,
                                         a3);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         2,
                                         0,
                                         &GUID_NULL);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         3,
                                         0,
                                         &v17);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                v15 = 4;
              }
              else
              {
                if ( !lpsz || !a6 )
                {
LABEL_45:
                  SimpleTableDispenser = -2147024809;
                  goto LABEL_46;
                }
                SimpleTableDispenser = CLSIDFromString(lpsz, &v23);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = CLSIDFromString(a6, &v25);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         0,
                                         0,
                                         &v23);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         1,
                                         0,
                                         a3);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         2,
                                         0,
                                         &GUID_NULL);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         3,
                                         0,
                                         &v25);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)a2 + 160LL))(
                                         a2,
                                         4,
                                         0,
                                         &v17);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_46;
                v15 = 5;
              }
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 160LL))(
                                       a2,
                                       v15,
                                       0,
                                       i[2]);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_46;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 144LL))(a2);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_46;
            }
          }
        }
        goto LABEL_46;
      }
      if ( !v19 )
      {
        SimpleTableDispenser = -2147024882;
        goto LABEL_46;
      }
      if ( _InterlockedCompareExchange64(&qword_180075518, v19, 0) )
        (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v19 + 16LL))(v19);
      v11 = qword_180075518;
    }
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)v11 + 24LL))(
                             v11,
                             didCOMSERVICES,
                             tidCOMSERVICES_LT_ROLEDEFINITION,
                             v20,
                             1,
                             1,
                             12,
                             &v16);
    goto LABEL_12;
  }
LABEL_46:
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x180044d94  mov     [rsp-8+arg_0], rbx
0x180044d99  push    rbp
0x180044d9a  push    rsi
0x180044d9b  push    rdi
0x180044d9c  push    r12
0x180044d9e  push    r13
0x180044da0  push    r14
0x180044da2  push    r15
0x180044da4  lea     rbp, [rsp-0Fh]
0x180044da9  sub     rsp, 0C0h
0x180044db0  mov     rax, cs:__security_cookie
0x180044db7  xor     rax, rsp
0x180044dba  mov     [rbp+3Fh+var_40], rax
0x180044dbe  mov     r14, [rbp+3Fh+lpsz]
0x180044dc2  mov     r15d, 1
0x180044dc8  mov     r12, [rbp+3Fh+arg_28]
0x180044dcc  mov     r13, r8
0x180044dcf  mov     rsi, [rbp+3Fh+arg_30]
0x180044dd3  mov     rdi, rdx
0x180044dd6  mov     [rbp+3Fh+var_94], ecx
0x180044dd9  mov     [rbp+3Fh+var_98], r15d
0x180044ddd  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044de4  movdqu  xmmword ptr [rbp+3Fh+pclsid.Data1], xmm0
0x180044de9  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x180044dee  movdqu  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x180044df3  test    rdx, rdx
0x180044df6  jnz     short loc_180044E02
0x180044df8  mov     eax, 80070057h
0x180044dfd  jmp     loc_1800451FE
0x180044e02  lea     rdx, [rbp+3Fh+pclsid]; pclsid
0x180044e06  mov     [rbp+3Fh+var_A0], 0
0x180044e0e  mov     rcx, r9; lpsz
0x180044e11  call    cs:__imp_CLSIDFromString
0x180044e17  mov     ebx, eax
0x180044e19  test    eax, eax
0x180044e1b  js      loc_1800451E7
0x180044e21  mov     rcx, cs:qword_180075518
0x180044e28  lea     rax, [rbp+3Fh+pclsid]
0x180044e2c  mov     [rbp+3Fh+var_88], rax
0x180044e30  xor     eax, eax
0x180044e32  mov     [rbp+3Fh+var_80], rax
0x180044e36  mov     [rbp+3Fh+var_78], 48h ; 'H'
0x180044e3d  mov     [rbp+3Fh+var_74], 10h
0x180044e44  mov     [rbp+3Fh+var_A0], rax
0x180044e48  test    rcx, rcx
0x180044e4b  jnz     short loc_180044E9F
0x180044e4d  lea     rdx, [rbp+3Fh+var_90]
0x180044e51  mov     [rbp+3Fh+var_90], rax
0x180044e55  lea     rcx, IID_ISimpleTableDispenser
0x180044e5c  call    cs:__imp_GetSimpleTableDispenser
0x180044e62  mov     ebx, eax
0x180044e64  test    eax, eax
0x180044e66  js      short loc_180044EDA
0x180044e68  mov     rcx, [rbp+3Fh+var_90]
0x180044e6c  test    rcx, rcx
0x180044e6f  jnz     short loc_180044E7B
0x180044e71  mov     ebx, 8007000Eh
0x180044e76  jmp     loc_1800451E7
0x180044e7b  xor     eax, eax
0x180044e7d  lock cmpxchg cs:qword_180075518, rcx
0x180044e86  jz      short loc_180044E98
0x180044e88  mov     rcx, [rbp+3Fh+var_90]
0x180044e8c  mov     rax, [rcx]
0x180044e8f  mov     rax, [rax+10h]
0x180044e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e98  mov     rcx, cs:qword_180075518
0x180044e9f  mov     rax, [rcx]
0x180044ea2  lea     rdx, [rbp+3Fh+var_A0]
0x180044ea6  mov     [rsp+0F0h+var_B8], rdx
0x180044eab  lea     r9, [rbp+3Fh+var_88]
0x180044eaf  mov     [rsp+0F0h+var_C0], 0Ch
0x180044eb7  lea     r8, tidCOMSERVICES_LT_ROLEDEFINITION
0x180044ebe  mov     [rsp+0F0h+var_C8], r15d
0x180044ec3  lea     rdx, didCOMSERVICES
0x180044eca  mov     rax, [rax+18h]
0x180044ece  mov     [rsp+0F0h+var_D0], r15
0x180044ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ed8  mov     ebx, eax
0x180044eda  test    ebx, ebx
0x180044edc  js      loc_1800451E7
0x180044ee2  mov     rcx, [rbp+3Fh+var_A0]
0x180044ee6  mov     rax, [rcx]
0x180044ee9  mov     rax, [rax+18h]
0x180044eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ef2  mov     ebx, eax
0x180044ef4  test    eax, eax
0x180044ef6  js      loc_1800451E7
0x180044efc  mov     rsi, [rsi+8]
0x180044f00  test    rsi, rsi
0x180044f03  jz      loc_1800451E7
0x180044f09  test    ebx, ebx
0x180044f0b  jnz     loc_1800451E7
0x180044f11  mov     rcx, [rbp+3Fh+var_A0]
0x180044f15  mov     r15, [rsi]
0x180044f18  mov     rax, [rcx]
0x180044f1b  mov     rax, [rax+78h]
0x180044f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f24  mov     ebx, eax
0x180044f26  test    eax, eax
0x180044f28  js      loc_1800451E7
0x180044f2e  mov     rcx, [rbp+3Fh+var_A0]
0x180044f32  lea     r9, [rbp+3Fh+pclsid]
0x180044f36  xor     r8d, r8d
0x180044f39  xor     edx, edx
0x180044f3b  mov     rax, [rcx]
0x180044f3e  mov     rax, [rax+0A0h]
0x180044f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f4a  mov     ebx, eax
0x180044f4c  test    eax, eax
0x180044f4e  js      loc_1800451E7
0x180044f54  mov     rcx, [rbp+3Fh+var_A0]
0x180044f58  xor     r8d, r8d
0x180044f5b  mov     r9, [rsi+10h]
0x180044f5f  mov     rax, [rcx]
0x180044f62  lea     edx, [r8+1]
0x180044f66  mov     rax, [rax+0A0h]
0x180044f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f72  mov     ebx, eax
0x180044f74  test    eax, eax
0x180044f76  js      loc_1800451E7
0x180044f7c  mov     rcx, [rbp+3Fh+var_A0]
0x180044f80  mov     rax, [rcx]
0x180044f83  mov     rax, [rax+90h]
0x180044f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f8f  mov     ebx, eax
0x180044f91  test    eax, eax
0x180044f93  js      loc_1800451E7
0x180044f99  mov     rcx, [rbp+3Fh+var_A0]
0x180044f9d  mov     rax, [rcx]
0x180044fa0  mov     rax, [rax+60h]
0x180044fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fa9  mov     ebx, eax
0x180044fab  test    eax, eax
0x180044fad  jz      short loc_180044FBA
0x180044faf  cmp     eax, 8011040Ch
0x180044fb4  jnz     loc_1800451E7
0x180044fba  mov     rax, [rdi]
0x180044fbd  mov     rcx, rdi
0x180044fc0  mov     rax, [rax+78h]
0x180044fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fc9  mov     ebx, eax
0x180044fcb  test    eax, eax
0x180044fcd  js      loc_1800451E7
0x180044fd3  cmp     [rbp+3Fh+var_94], 1Eh
0x180044fd7  jnz     loc_1800450A3
0x180044fdd  test    r14, r14
0x180044fe0  jz      loc_1800451E2
0x180044fe6  lea     rdx, [rbp+3Fh+var_70]; pclsid
0x180044fea  mov     rcx, r14; lpsz
0x180044fed  call    cs:__imp_CLSIDFromString
0x180044ff3  mov     ebx, eax
0x180044ff5  test    eax, eax
0x180044ff7  js      loc_1800451E7
0x180044ffd  mov     rax, [rdi]
0x180045000  lea     r9, [rbp+3Fh+var_70]
0x180045004  xor     r8d, r8d
0x180045007  xor     edx, edx
0x180045009  mov     rcx, rdi
0x18004500c  mov     rax, [rax+0A0h]
0x180045013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045018  mov     ebx, eax
0x18004501a  test    eax, eax
0x18004501c  js      loc_1800451E7
0x180045022  mov     rax, [rdi]
0x180045025  xor     r8d, r8d
0x180045028  mov     r9, r13
0x18004502b  mov     rcx, rdi
0x18004502e  mov     rax, [rax+0A0h]
0x180045035  lea     edx, [r8+1]
0x180045039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004503e  mov     ebx, eax
0x180045040  test    eax, eax
0x180045042  js      loc_1800451E7
0x180045048  mov     rax, [rdi]
0x18004504b  lea     r9, GUID_NULL
0x180045052  xor     r8d, r8d
0x180045055  mov     rcx, rdi
0x180045058  mov     rax, [rax+0A0h]
0x18004505f  lea     edx, [r8+2]
0x180045063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045068  mov     ebx, eax
0x18004506a  test    eax, eax
0x18004506c  js      loc_1800451E7
0x180045072  mov     rax, [rdi]
0x180045075  lea     r9, [rbp+3Fh+var_98]
0x180045079  xor     r8d, r8d
0x18004507c  mov     rcx, rdi
0x18004507f  mov     rax, [rax+0A0h]
0x180045086  lea     edx, [r8+3]
0x18004508a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004508f  mov     ebx, eax
0x180045091  test    eax, eax
0x180045093  js      loc_1800451E7
0x180045099  mov     edx, 4
0x18004509e  jmp     loc_1800451A3
0x1800450a3  test    r14, r14
0x1800450a6  jz      loc_1800451E2
0x1800450ac  test    r12, r12
0x1800450af  jz      loc_1800451E2
0x1800450b5  lea     rdx, [rbp+3Fh+var_70]; pclsid
0x1800450b9  mov     rcx, r14; lpsz
0x1800450bc  call    cs:__imp_CLSIDFromString
0x1800450c2  mov     ebx, eax
0x1800450c4  test    eax, eax
0x1800450c6  js      loc_1800451E7
0x1800450cc  lea     rdx, [rbp+3Fh+var_50]; pclsid
0x1800450d0  mov     rcx, r12; lpsz
0x1800450d3  call    cs:__imp_CLSIDFromString
0x1800450d9  mov     ebx, eax
0x1800450db  test    eax, eax
0x1800450dd  js      loc_1800451E7
0x1800450e3  mov     rax, [rdi]
0x1800450e6  lea     r9, [rbp+3Fh+var_70]
0x1800450ea  xor     r8d, r8d
0x1800450ed  xor     edx, edx
0x1800450ef  mov     rcx, rdi
0x1800450f2  mov     rax, [rax+0A0h]
0x1800450f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450fe  mov     ebx, eax
0x180045100  test    eax, eax
0x180045102  js      loc_1800451E7
0x180045108  mov     rax, [rdi]
0x18004510b  xor     r8d, r8d
0x18004510e  mov     r9, r13
0x180045111  mov     rcx, rdi
0x180045114  mov     rax, [rax+0A0h]
0x18004511b  lea     edx, [r8+1]
0x18004511f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045124  mov     ebx, eax
0x180045126  test    eax, eax
0x180045128  js      loc_1800451E7
0x18004512e  mov     rax, [rdi]
0x180045131  lea     r9, GUID_NULL
0x180045138  xor     r8d, r8d
0x18004513b  mov     rcx, rdi
0x18004513e  mov     rax, [rax+0A0h]
0x180045145  lea     edx, [r8+2]
0x180045149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004514e  mov     ebx, eax
0x180045150  test    eax, eax
0x180045152  js      loc_1800451E7
0x180045158  mov     rax, [rdi]
0x18004515b  lea     r9, [rbp+3Fh+var_50]
0x18004515f  xor     r8d, r8d
0x180045162  mov     rcx, rdi
0x180045165  mov     rax, [rax+0A0h]
0x18004516c  lea     edx, [r8+3]
0x180045170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045175  mov     ebx, eax
0x180045177  test    eax, eax
0x180045179  js      short loc_1800451E7
0x18004517b  mov     rax, [rdi]
0x18004517e  lea     r9, [rbp+3Fh+var_98]
0x180045182  xor     r8d, r8d
0x180045185  mov     rcx, rdi
0x180045188  mov     rax, [rax+0A0h]
0x18004518f  lea     edx, [r8+4]
0x180045193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045198  mov     ebx, eax
0x18004519a  test    eax, eax
0x18004519c  js      short loc_1800451E7
0x18004519e  mov     edx, 5
0x1800451a3  mov     rax, [rdi]
0x1800451a6  xor     r8d, r8d
0x1800451a9  mov     r9, [rsi+10h]
0x1800451ad  mov     rcx, rdi
0x1800451b0  mov     rax, [rax+0A0h]
0x1800451b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451bc  mov     ebx, eax
0x1800451be  test    eax, eax
0x1800451c0  js      short loc_1800451E7
0x1800451c2  mov     rax, [rdi]
0x1800451c5  mov     rcx, rdi
0x1800451c8  mov     rax, [rax+90h]
0x1800451cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451d4  mov     ebx, eax
0x1800451d6  test    eax, eax
0x1800451d8  js      short loc_1800451E7
0x1800451da  mov     rsi, r15
0x1800451dd  jmp     loc_180044F00
0x1800451e2  mov     ebx, 80070057h
0x1800451e7  mov     rcx, [rbp+3Fh+var_A0]
0x1800451eb  test    rcx, rcx
0x1800451ee  jz      short loc_1800451FC
0x1800451f0  mov     rax, [rcx]
0x1800451f3  mov     rax, [rax+10h]
0x1800451f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451fc  mov     eax, ebx
0x1800451fe  mov     rcx, [rbp+3Fh+var_40]
0x180045202  xor     rcx, rsp; StackCookie
0x180045205  call    __security_check_cookie
0x18004520a  mov     rbx, [rsp+0F0h+arg_0]
0x180045212  add     rsp, 0C0h
0x180045219  pop     r15
0x18004521b  pop     r14
0x18004521d  pop     r13
0x18004521f  pop     r12
0x180045221  pop     rdi
0x180045222  pop     rsi
0x180045223  pop     rbp
  ... truncated ...
```
