# LTraceSession::SetExtendedFlags(IValueMap *,ushort const *,tagSAFEARRAY * *,tagSAFEARRAY * *)

- ea: `0x180096e20`
- end: `0x18009758c`
- name: `?SetExtendedFlags@LTraceSession@@EEAAJPEAUIValueMap@@PEBGPEAPEAUtagSAFEARRAY@@2@Z`
- size: `1900`
- prototype: `__int64 __fastcall(LTraceSession *__hidden this, struct IValueMap *, const unsigned __int16 *, struct tagSAFEARRAY **, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180018420`
- `0x180024ea0`
- `0x180026850`
- `0x18008da24`
- `0x180096e20`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800974fc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009750a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800974fc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009750a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800971f1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180097278`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800971f1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180097278`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974a3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974d7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974ea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974a3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974d7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800974ea`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800970cd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180097161`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800970cd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180097161`

## pseudocode

```c
__int64 __fastcall LTraceSession::SetExtendedFlags(
        LTraceSession *this,
        struct IValueMap *a2,
        unsigned __int16 *a3,
        struct tagSAFEARRAY **a4,
        struct tagSAFEARRAY **a5)
{
  ULONG v5; // r15d
  SAFEARRAY *Vector; // r14
  SAFEARRAY *v7; // rsi
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  unsigned __int16 **v13; // r9
  unsigned __int16 **v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  HRESULT v21; // eax
  __int64 v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rax
  int Ul; // eax
  const char *v26; // rdx
  int v27; // r8d
  unsigned __int16 *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  int v32; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v33; // [rsp+78h] [rbp-88h] BYREF
  ULONG cElements; // [rsp+80h] [rbp-80h] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  void *v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v40; // [rsp+B0h] [rbp-50h] BYREF
  struct tagVARIANT v41; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v42[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v43[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v44[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v45[64]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v46[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v47[64]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v48[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v49[64]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v50[64]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v5 = 0;
  v33 = a3;
  cElements = 0;
  v39 = 0;
  memset(&v41, 0, sizeof(v41));
  Vector = 0;
  v32 = 0;
  v7 = 0;
  ppvData = 0;
  v36 = 0;
  v40 = 0;
  v38 = 0;
  v37 = 0;
  PlaiVariantInit(&v41);
  v10 = ((__int64 (__fastcall *)(struct IValueMap *, __int64 *))a2->lpVtbl->get__NewEnum)(a2, &v38);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v38)(v38, &IID_IEnumVARIANT, &v40);
    v11 = v15;
    if ( v15 >= 0 )
    {
      v17 = ((__int64 (__fastcall *)(struct IValueMap *, ULONG *))a2->lpVtbl->get_Count)(a2, &cElements);
      v11 = v17;
      if ( v17 >= 0 )
      {
        Vector = SafeArrayCreateVector(8u, 0, cElements);
        if ( Vector )
        {
          v7 = SafeArrayCreateVector(3u, 0, cElements);
          if ( v7 )
          {
            v21 = SafeArrayAccessData(Vector, &ppvData);
            v11 = v21;
            if ( v21 >= 0 )
            {
              v23 = SafeArrayAccessData(v7, &v36);
              v11 = v23;
              if ( v23 >= 0 )
              {
                while ( 1 )
                {
                  if ( v5 >= cElements )
                  {
                    if ( ppvData )
                    {
                      SafeArrayUnaccessData(Vector);
                      ppvData = 0;
                    }
                    if ( v36 )
                    {
                      SafeArrayUnaccessData(v7);
                      v36 = 0;
                    }
                    *a4 = Vector;
                    Vector = 0;
                    *a5 = v7;
                    v7 = 0;
                    goto LABEL_74;
                  }
                  if ( v37 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                    v37 = 0;
                  }
                  PlaiVariantClear(&v41);
                  (*(void (__fastcall **)(__int64, __int64, struct tagVARIANT *, int *))(*(_QWORD *)v40 + 24LL))(
                    v40,
                    1,
                    &v41,
                    &v39);
                  (**(void (__fastcall ***)(LONGLONG, GUID *, __int64 *))v41.llVal)(v41.llVal, &IID_IValueMapItem, &v37);
                  Ul = PlaiGetUlValue<IValueMapItem>(v37, &v32);
                  v11 = Ul;
                  if ( Ul < 0 )
                    break;
                  *((_DWORD *)v36 + v5) = v32;
                  v28 = PlaiAllocStringEx(v33, v26, v27);
                  *((_QWORD *)ppvData + v5) = v28;
                  if ( !*((_QWORD *)ppvData + v5) )
                  {
                    v11 = -2147024882;
                    LODWORD(v33) = 0;
                    v32 = -2147024882;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v49, 0x4000000000000800uLL);
                      v29 = -1;
                      do
                        ++v29;
                      while ( v49[v29] );
                      goto LABEL_15;
                    }
                    goto LABEL_74;
                  }
                  ++v5;
                }
                v32 = Ul;
                LODWORD(v33) = 0;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v50, 0x4000000000000800uLL);
                  v30 = -1;
                  do
                    ++v30;
                  while ( v50[v30] );
                  goto LABEL_15;
                }
                goto LABEL_74;
              }
              LODWORD(v33) = 0;
              v32 = v23;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_74;
              }
              PlaiWhoAmI(v48, 0x4000000000000800uLL);
              v24 = -1;
              do
                ++v24;
              while ( v48[v24] );
            }
            else
            {
              LODWORD(v33) = 0;
              v32 = v21;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_74;
              }
              PlaiWhoAmI(v47, 0x4000000000000800uLL);
              v22 = -1;
              do
                ++v22;
              while ( v47[v22] );
            }
          }
          else
          {
            v11 = -2147024882;
            v32 = -2147024882;
            LODWORD(v33) = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_74;
            }
            PlaiWhoAmI(v46, 0x4000000000000800uLL);
            v20 = -1;
            do
              ++v20;
            while ( v46[v20] );
          }
        }
        else
        {
          v11 = -2147024882;
          v32 = -2147024882;
          LODWORD(v33) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_74;
          }
          PlaiWhoAmI(v45, 0x4000000000000800uLL);
          v19 = -1;
          do
            ++v19;
          while ( v45[v19] );
        }
      }
      else
      {
        LODWORD(v33) = 0;
        v32 = v17;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_74;
        }
        PlaiWhoAmI(v44, 0x4000000000000800uLL);
        v18 = -1;
        do
          ++v18;
        while ( v44[v18] );
      }
    }
    else
    {
      LODWORD(v33) = 0;
      v32 = v15;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_74;
      }
      PlaiWhoAmI(v43, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v43[v16] );
    }
LABEL_15:
    v13 = (unsigned __int16 **)&v32;
    v14 = &v33;
LABEL_8:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      v13,
      4,
      qword_180147320,
      1,
      v14,
      4,
      "LTraceSession::SetExtendedFlags",
      32);
    goto LABEL_74;
  }
  v32 = 0;
  LODWORD(v33) = v10;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v42, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v42[v12] );
    v13 = &v33;
    v14 = (unsigned __int16 **)&v32;
    goto LABEL_8;
  }
LABEL_74:
  if ( ppvData )
  {
    SafeArrayUnaccessData(Vector);
    ppvData = 0;
  }
  if ( v36 )
  {
    SafeArrayUnaccessData(v7);
    v36 = 0;
  }
  if ( Vector )
    SafeArrayDestroy(Vector);
  if ( v7 )
    SafeArrayDestroy(v7);
  PlaiVariantClear(&v41);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  return v11;
}

```

## disassembly

```asm
0x180096e20  mov     [rsp-8+arg_0], rbx
0x180096e25  push    rbp
0x180096e26  push    rsi
0x180096e27  push    rdi
0x180096e28  push    r12
0x180096e2a  push    r13
0x180096e2c  push    r14
0x180096e2e  push    r15
0x180096e30  lea     rbp, [rsp-460h]
0x180096e38  sub     rsp, 560h
0x180096e3f  mov     rax, cs:__security_cookie
0x180096e46  xor     rax, rsp
0x180096e49  mov     [rbp+490h+var_40], rax
0x180096e50  mov     r13, [rbp+490h+arg_20]
0x180096e57  lea     rcx, [rbp+490h+var_4D8]; struct tagVARIANT *
0x180096e5b  xor     r15d, r15d
0x180096e5e  mov     [rsp+590h+var_518], r8
0x180096e63  xorps   xmm0, xmm0
0x180096e66  mov     [rbp+490h+cElements], r15d
0x180096e6a  xor     eax, eax
0x180096e6c  mov     [rbp+490h+var_4E8], r15d
0x180096e70  movups  xmmword ptr [rbp+490h+var_4D8], xmm0
0x180096e74  mov     qword ptr [rbp+490h+var_4D8+10h], rax
0x180096e78  mov     r14d, r15d
0x180096e7b  mov     [rsp+590h+var_520], r15d
0x180096e80  mov     esi, r15d
0x180096e83  mov     [rbp+490h+ppvData], r15
0x180096e87  mov     r12, r9
0x180096e8a  mov     [rbp+490h+var_500], r15
0x180096e8e  mov     rbx, rdx
0x180096e91  mov     [rbp+490h+var_4E0], r15
0x180096e95  mov     [rbp+490h+var_4F0], r15
0x180096e99  mov     [rbp+490h+var_4F8], r15
0x180096e9d  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x180096ea2  mov     rax, [rbx]
0x180096ea5  lea     rdx, [rbp+490h+var_4F0]
0x180096ea9  mov     rcx, rbx
0x180096eac  mov     rax, [rax+48h]
0x180096eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096eb5  mov     edi, eax
0x180096eb7  test    eax, eax
0x180096eb9  jns     loc_180096F97
0x180096ebf  cmp     dword ptr cs:xmmword_180169738, r15d
0x180096ec6  mov     [rsp+590h+var_520], r15d
0x180096ecb  mov     dword ptr [rsp+590h+var_518], eax
0x180096ecf  jz      loc_1800974CE
0x180096ed5  mov     rdx, 4000000000000800h; unsigned __int64
0x180096edf  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096ee6  jz      loc_1800974CE
0x180096eec  mov     rax, cs:qword_180169748
0x180096ef3  and     rax, rdx
0x180096ef6  cmp     cs:qword_180169748, rax
0x180096efd  jnz     loc_1800974CE
0x180096f03  lea     rcx, [rbp+490h+var_4C0]; unsigned __int16 *
0x180096f07  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180096f0c  lea     rcx, [rbp+490h+var_4C0]
0x180096f10  or      rax, 0FFFFFFFFFFFFFFFFh
0x180096f14  inc     rax
0x180096f17  cmp     [rcx+rax*2], r15w
0x180096f1c  jnz     short loc_180096F14
0x180096f1e  lea     ecx, [rax+rax]
0x180096f21  add     rcx, 2
0x180096f25  lea     rax, [rbp+490h+var_4C0]
0x180096f29  mov     [rsp+590h+var_530], rcx
0x180096f2e  lea     r9, [rsp+590h+var_518]
0x180096f33  lea     rcx, [rsp+590h+var_520]
0x180096f38  mov     [rsp+590h+var_538], rax
0x180096f3d  lea     rdx, PLA_EVENT_ERROR
0x180096f44  mov     [rsp+590h+var_540], 20h ; ' '
0x180096f4d  lea     rax, aLtracesessionS_0; "LTraceSession::SetExtendedFlags"
0x180096f54  mov     [rsp+590h+var_548], rax
0x180096f59  mov     eax, 4
0x180096f5e  mov     [rsp+590h+var_550], rax
0x180096f63  mov     [rsp+590h+var_558], rcx
0x180096f68  lea     rcx, qword_180147320
0x180096f6f  mov     [rsp+590h+var_560], 1
0x180096f78  mov     [rsp+590h+var_568], rcx
0x180096f7d  lea     r8d, [rax+1]
0x180096f81  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180096f88  mov     [rsp+590h+var_570], rax
0x180096f8d  call    EventingWriteEvent
0x180096f92  jmp     loc_1800974CE
0x180096f97  mov     rcx, [rbp+490h+var_4F0]
0x180096f9b  lea     r8, [rbp+490h+var_4E0]
0x180096f9f  lea     rdx, IID_IEnumVARIANT
0x180096fa6  mov     rax, [rcx]
0x180096fa9  mov     rax, [rax]
0x180096fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096fb1  mov     edi, eax
0x180096fb3  test    eax, eax
0x180096fb5  jns     short loc_180097035
0x180096fb7  cmp     dword ptr cs:xmmword_180169738, r15d
0x180096fbe  mov     dword ptr [rsp+590h+var_518], r15d
0x180096fc3  mov     [rsp+590h+var_520], eax
0x180096fc7  jz      loc_1800974CE
0x180096fcd  mov     rdx, 4000000000000800h; unsigned __int64
0x180096fd7  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096fde  jz      loc_1800974CE
0x180096fe4  mov     rax, cs:qword_180169748
0x180096feb  and     rax, rdx
0x180096fee  cmp     cs:qword_180169748, rax
0x180096ff5  jnz     loc_1800974CE
0x180096ffb  lea     rcx, [rbp+490h+var_440]; unsigned __int16 *
0x180096fff  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180097004  lea     rcx, [rbp+490h+var_440]
0x180097008  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009700c  inc     rax
0x18009700f  cmp     [rcx+rax*2], r15w
0x180097014  jnz     short loc_18009700C
0x180097016  lea     ecx, [rax+rax]
0x180097019  lea     rax, [rbp+490h+var_440]
0x18009701d  add     rcx, 2
0x180097021  lea     r9, [rsp+590h+var_520]
0x180097026  mov     [rsp+590h+var_530], rcx
0x18009702b  lea     rcx, [rsp+590h+var_518]
0x180097030  jmp     loc_180096F38
0x180097035  mov     rax, [rbx]
0x180097038  lea     rdx, [rbp+490h+cElements]
0x18009703c  mov     rcx, rbx
0x18009703f  mov     rax, [rax+38h]
0x180097043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097048  mov     edi, eax
0x18009704a  test    eax, eax
0x18009704c  jns     short loc_1800970C2
0x18009704e  cmp     dword ptr cs:xmmword_180169738, r15d
0x180097055  mov     dword ptr [rsp+590h+var_518], r15d
0x18009705a  mov     [rsp+590h+var_520], eax
0x18009705e  jz      loc_1800974CE
0x180097064  mov     rdx, 4000000000000800h; unsigned __int64
0x18009706e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180097075  jz      loc_1800974CE
0x18009707b  mov     rax, cs:qword_180169748
0x180097082  and     rax, rdx
0x180097085  cmp     cs:qword_180169748, rax
0x18009708c  jnz     loc_1800974CE
0x180097092  lea     rcx, [rbp+490h+var_3C0]; unsigned __int16 *
0x180097099  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009709e  lea     rcx, [rbp+490h+var_3C0]
0x1800970a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800970a9  inc     rax
0x1800970ac  cmp     [rcx+rax*2], r15w
0x1800970b1  jnz     short loc_1800970A9
0x1800970b3  lea     ecx, [rax+rax]
0x1800970b6  lea     rax, [rbp+490h+var_3C0]
0x1800970bd  jmp     loc_18009701D
0x1800970c2  mov     r8d, [rbp+490h+cElements]; cElements
0x1800970c6  mov     ecx, 8; vt
0x1800970cb  xor     edx, edx; lLbound
0x1800970cd  call    cs:__imp_SafeArrayCreateVector
0x1800970d3  mov     r14, rax
0x1800970d6  test    rax, rax
0x1800970d9  jnz     short loc_180097156
0x1800970db  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800970e2  mov     ecx, 8007000Eh
0x1800970e7  mov     edi, ecx
0x1800970e9  mov     [rsp+590h+var_520], ecx
0x1800970ed  mov     dword ptr [rsp+590h+var_518], r15d
0x1800970f2  jz      loc_1800974CE
0x1800970f8  mov     rdx, 4000000000000800h; unsigned __int64
0x180097102  test    qword ptr cs:xmmword_180169738+8, rdx
0x180097109  jz      loc_1800974CE
0x18009710f  mov     rax, cs:qword_180169748
0x180097116  and     rax, rdx
0x180097119  cmp     cs:qword_180169748, rax
0x180097120  jnz     loc_1800974CE
0x180097126  lea     rcx, [rbp+490h+var_340]; unsigned __int16 *
0x18009712d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180097132  lea     rcx, [rbp+490h+var_340]
0x180097139  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009713d  inc     rax
0x180097140  cmp     [rcx+rax*2], r15w
0x180097145  jnz     short loc_18009713D
0x180097147  lea     ecx, [rax+rax]
0x18009714a  lea     rax, [rbp+490h+var_340]
0x180097151  jmp     loc_18009701D
0x180097156  mov     r8d, [rbp+490h+cElements]; cElements
0x18009715a  mov     ecx, 3; vt
0x18009715f  xor     edx, edx; lLbound
0x180097161  call    cs:__imp_SafeArrayCreateVector
0x180097167  mov     rsi, rax
0x18009716a  test    rax, rax
0x18009716d  jnz     short loc_1800971EA
0x18009716f  cmp     dword ptr cs:xmmword_180169738, r15d
0x180097176  mov     ecx, 8007000Eh
0x18009717b  mov     edi, ecx
0x18009717d  mov     [rsp+590h+var_520], ecx
0x180097181  mov     dword ptr [rsp+590h+var_518], r15d
0x180097186  jz      loc_1800974CE
0x18009718c  mov     rdx, 4000000000000800h; unsigned __int64
0x180097196  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009719d  jz      loc_1800974CE
0x1800971a3  mov     rax, cs:qword_180169748
0x1800971aa  and     rax, rdx
0x1800971ad  cmp     cs:qword_180169748, rax
0x1800971b4  jnz     loc_1800974CE
0x1800971ba  lea     rcx, [rbp+490h+var_2C0]; unsigned __int16 *
0x1800971c1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800971c6  lea     rcx, [rbp+490h+var_2C0]
0x1800971cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800971d1  inc     rax
0x1800971d4  cmp     [rcx+rax*2], r15w
0x1800971d9  jnz     short loc_1800971D1
0x1800971db  lea     ecx, [rax+rax]
0x1800971de  lea     rax, [rbp+490h+var_2C0]
0x1800971e5  jmp     loc_18009701D
0x1800971ea  lea     rdx, [rbp+490h+ppvData]; ppvData
0x1800971ee  mov     rcx, r14; psa
0x1800971f1  call    cs:__imp_SafeArrayAccessData
0x1800971f7  mov     edi, eax
0x1800971f9  test    eax, eax
0x1800971fb  jns     short loc_180097271
0x1800971fd  cmp     dword ptr cs:xmmword_180169738, r15d
0x180097204  mov     dword ptr [rsp+590h+var_518], r15d
0x180097209  mov     [rsp+590h+var_520], eax
0x18009720d  jz      loc_1800974CE
0x180097213  mov     rdx, 4000000000000800h; unsigned __int64
0x18009721d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180097224  jz      loc_1800974CE
0x18009722a  mov     rax, cs:qword_180169748
0x180097231  and     rax, rdx
0x180097234  cmp     cs:qword_180169748, rax
0x18009723b  jnz     loc_1800974CE
0x180097241  lea     rcx, [rbp+490h+var_240]; unsigned __int16 *
0x180097248  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009724d  lea     rcx, [rbp+490h+var_240]
0x180097254  or      rax, 0FFFFFFFFFFFFFFFFh
0x180097258  inc     rax
0x18009725b  cmp     [rcx+rax*2], r15w
0x180097260  jnz     short loc_180097258
0x180097262  lea     ecx, [rax+rax]
0x180097265  lea     rax, [rbp+490h+var_240]
0x18009726c  jmp     loc_18009701D
0x180097271  lea     rdx, [rbp+490h+var_500]; ppvData
0x180097275  mov     rcx, rsi; psa
0x180097278  call    cs:__imp_SafeArrayAccessData
0x18009727e  mov     edi, eax
0x180097280  test    eax, eax
0x180097282  jns     short loc_1800972F8
0x180097284  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009728b  mov     dword ptr [rsp+590h+var_518], r15d
0x180097290  mov     [rsp+590h+var_520], eax
0x180097294  jz      loc_1800974CE
0x18009729a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800972a4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800972ab  jz      loc_1800974CE
0x1800972b1  mov     rax, cs:qword_180169748
0x1800972b8  and     rax, rdx
0x1800972bb  cmp     cs:qword_180169748, rax
0x1800972c2  jnz     loc_1800974CE
0x1800972c8  lea     rcx, [rbp+490h+var_1C0]; unsigned __int16 *
0x1800972cf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800972d4  lea     rcx, [rbp+490h+var_1C0]
0x1800972db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800972df  inc     rax
0x1800972e2  cmp     [rcx+rax*2], r15w
0x1800972e7  jnz     short loc_1800972DF
0x1800972e9  lea     ecx, [rax+rax]
0x1800972ec  lea     rax, [rbp+490h+var_1C0]
0x1800972f3  jmp     loc_18009701D
0x1800972f8  cmp     r15d, [rbp+490h+cElements]
0x1800972fc  jnb     loc_180097497
0x180097302  mov     rcx, [rbp+490h+var_4F8]
0x180097306  test    rcx, rcx
0x180097309  jz      short loc_18009731F
0x18009730b  mov     rax, [rcx]
0x18009730e  mov     rax, [rax+10h]
0x180097312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097317  mov     [rbp+490h+var_4F8], 0
0x18009731f  lea     rcx, [rbp+490h+var_4D8]; struct tagVARIANT *
0x180097323  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x180097328  mov     rcx, [rbp+490h+var_4E0]
0x18009732c  lea     r9, [rbp+490h+var_4E8]
0x180097330  lea     r8, [rbp+490h+var_4D8]
0x180097334  mov     edx, 1
0x180097339  mov     rax, [rcx]
0x18009733c  mov     rax, [rax+18h]
0x180097340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097345  mov     rcx, qword ptr [rbp+490h+var_4D8+8]
0x180097349  lea     r8, [rbp+490h+var_4F8]
0x18009734d  lea     rdx, IID_IValueMapItem
0x180097354  mov     rax, [rcx]
0x180097357  mov     rax, [rax]
0x18009735a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009735f  mov     rcx, [rbp+490h+var_4F8]
0x180097363  lea     rdx, [rsp+590h+var_520]
0x180097368  call    ??$PlaiGetUlValue@UIValueMapItem@@@@YAJPEAUIValueMapItem@@PEAK@Z; PlaiGetUlValue<IValueMapItem>(IValueMapItem *,ulong *)
0x18009736d  mov     edi, eax
0x18009736f  test    eax, eax
0x180097371  js      loc_180097428
0x180097377  mov     rax, [rbp+490h+var_500]
0x18009737b  mov     ecx, [rsp+590h+var_520]
0x18009737f  mov     ebx, r15d
0x180097382  mov     [rax+rbx*4], ecx
0x180097385  mov     rcx, [rsp+590h+var_518]; unsigned __int16 *
0x18009738a  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18009738f  mov     rcx, [rbp+490h+ppvData]
0x180097393  mov     [rcx+rbx*8], rax
0x180097397  mov     rax, [rbp+490h+ppvData]
0x18009739b  cmp     qword ptr [rax+rbx*8], 0
0x1800973a0  jz      short loc_1800973AA
  ... truncated ...
```
