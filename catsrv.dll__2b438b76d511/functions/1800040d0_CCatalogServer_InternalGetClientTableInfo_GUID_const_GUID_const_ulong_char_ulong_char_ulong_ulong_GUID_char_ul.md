# CCatalogServer::InternalGetClientTableInfo(_GUID const &,_GUID const &,ulong,char *,ulong,char *,ulong,ulong,_GUID *,char * *,ulong *,_GUID * *,ulong *,__MIDL___MIDL_itf_stable_0000_0000_0001 * *,ulong *,_GUID *,void * *,char * *,ulong *)

- ea: `0x1800040d0`
- end: `0x180004aa1`
- name: `?InternalGetClientTableInfo@CCatalogServer@@AEAAJAEBU_GUID@@0KPEADK1KKPEAU2@PEAPEADPEAKPEAPEAU2@4PEAPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@42PEAPEAX34@Z`
- size: `2513`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int, char *Src, size_t Size, char *, unsigned int, unsigned int, struct _GUID *, char **, unsigned int *, struct _GUID **, unsigned int *, struct __MIDL___MIDL_itf_stable_0000_0000_0001 **, unsigned int *, struct _GUID *, void **, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180021760`

## callees

- `0x1800040d0`
- `0x18005488c`
- `0x18005550e`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000474f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800047e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000491d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000474f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800047e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000491d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800042c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800042c1`

## pseudocode

```c
__int64 __fastcall CCatalogServer::InternalGetClientTableInfo(
        CCatalogServer *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        int a4,
        char *Src,
        size_t Size,
        char *a7,
        unsigned int a8,
        unsigned int a9,
        struct _GUID *a10,
        char **a11,
        unsigned int *a12,
        struct _GUID **a13,
        unsigned int *a14,
        struct __MIDL___MIDL_itf_stable_0000_0000_0001 **a15,
        unsigned int *a16,
        struct _GUID *a17,
        void **a18,
        char **a19,
        unsigned int *a20)
{
  LPVOID *v20; // rsi
  LPVOID *v21; // rdi
  char *v22; // r12
  int v23; // r14d
  CCatalogServer *v24; // rax
  char *v26; // rcx
  char *v27; // rsi
  unsigned int v28; // ebx
  char *v29; // rdi
  unsigned int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rax
  unsigned int v33; // edi
  HRESULT v34; // ebx
  _WORD *v35; // rcx
  __int64 v36; // rax
  SIZE_T v38; // rbx
  char *v39; // rax
  char *v40; // rax
  unsigned __int64 v42; // rcx
  __int64 v43; // rsi
  int v44; // eax
  char *v45; // rdi
  unsigned __int64 v46; // rcx
  char *v47; // rbx
  unsigned int v48; // r10d
  __int64 v49; // r9
  __int64 v50; // rdx
  char *v51; // rcx
  char *v52; // r11
  int v53; // eax
  char *v54; // rax
  struct _GUID *v55; // rax
  struct _GUID *v56; // rax
  __int64 i; // rdi
  char *v58; // rcx
  __int64 v59; // [rsp+60h] [rbp-99h] BYREF
  _DWORD *v60; // [rsp+68h] [rbp-91h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-89h] BYREF
  __int64 v62; // [rsp+78h] [rbp-81h] BYREF
  __int64 v63; // [rsp+80h] [rbp-79h] BYREF
  __int128 v64; // [rsp+88h] [rbp-71h] BYREF
  __int64 v65; // [rsp+98h] [rbp-61h]
  __int128 v66; // [rsp+A0h] [rbp-59h] BYREF
  void *v67[2]; // [rsp+B0h] [rbp-49h]
  __int64 v68; // [rsp+C0h] [rbp-39h]
  int v73; // [rsp+160h] [rbp+67h]

  v20 = (LPVOID *)a13;
  v21 = (LPVOID *)a11;
  v22 = 0;
  v23 = a4;
  v24 = this;
  *a11 = 0;
  *a13 = 0;
  ppv = 0;
  v62 = 0;
  v63 = 0;
  v59 = 0;
  v65 = 0;
  v60 = 0;
  v68 = 0;
  v64 = 0;
  v66 = 0;
  *(_OWORD *)v67 = 0;
  if ( !a10 )
  {
    v34 = -2147024809;
LABEL_111:
    if ( *v21 )
    {
      CoTaskMemFree(*v21);
      *v21 = 0;
    }
    if ( *v20 )
    {
      CoTaskMemFree(*v20);
      *v20 = 0;
    }
    if ( v22 )
      CoTaskMemFree(v22);
    *a15 = 0;
    goto LABEL_37;
  }
  if ( !a12 )
  {
    v34 = -2147024809;
    v22 = 0;
    goto LABEL_111;
  }
  if ( !a14 )
  {
    v34 = -2147024809;
    v22 = 0;
    goto LABEL_111;
  }
  if ( !a15 )
  {
    v34 = -2147024809;
    v22 = 0;
    goto LABEL_111;
  }
  if ( !a16 )
  {
    v34 = -2147024809;
    v22 = 0;
    goto LABEL_111;
  }
  if ( !a17 )
  {
    v34 = -2147024809;
    v22 = 0;
    goto LABEL_111;
  }
  if ( !a18 )
  {
    v34 = -2147024809;
    v22 = 0;
    goto LABEL_111;
  }
  v26 = Src;
  if ( !Src && (_DWORD)Size )
  {
    v22 = 0;
    v34 = -2147024809;
    goto LABEL_111;
  }
  v27 = a7;
  if ( !a7 && a8 )
  {
    v22 = 0;
    v34 = -2147024809;
    v20 = (LPVOID *)a13;
    goto LABEL_111;
  }
  if ( a9 != 1 )
  {
    v22 = 0;
    v34 = -2147024809;
    v20 = (LPVOID *)a13;
    goto LABEL_111;
  }
  if ( *((_DWORD *)v24 + 58) != 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v26 = Src;
    v24 = this;
  }
  if ( !(_DWORD)Size )
  {
    v33 = 0;
    v73 = 0;
    goto LABEL_24;
  }
  if ( !*((_DWORD *)v24 + 59) )
  {
    v73 = 0;
    v33 = (unsigned int)Size / 0x14;
    v47 = (char *)CoTaskMemAlloc(24LL * ((unsigned int)Size / 0x14));
    if ( v47 )
    {
      v48 = 0;
      v73 = 1;
      if ( v33 )
      {
        v49 = 0;
        do
        {
          v50 = *(unsigned int *)&Src[20 * v49];
          v51 = &Src[20 * v49];
          *(_QWORD *)&v47[24 * v49] = v50;
          v52 = &v47[24 * v49];
          *((_DWORD *)v52 + 2) = *((_DWORD *)v51 + 1);
          *((_DWORD *)v52 + 3) = *((_DWORD *)v51 + 2);
          *((_DWORD *)v52 + 4) = *((_DWORD *)v51 + 3);
          v53 = *((_DWORD *)v51 + 4);
          *((_DWORD *)v52 + 5) = v53;
          if ( v50 )
            *(_QWORD *)v52 = v27;
          ++v48;
          ++v49;
          v27 += (v53 + 3) & 0xFFFFFFFC;
        }
        while ( v48 < v33 );
      }
      Src = v47;
      goto LABEL_23;
    }
    goto LABEL_87;
  }
  v28 = (unsigned int)Size / 0x18;
  if ( ((unsigned __int8)v26 & 7) != 0 )
  {
    v73 = 1;
    v54 = (char *)CoTaskMemAlloc(24LL * v28);
    v29 = v54;
    if ( v54 )
    {
      memcpy_0(v54, Src, (unsigned int)Size);
      goto LABEL_17;
    }
LABEL_87:
    v40 = 0;
    v34 = -2147024882;
    v22 = 0;
    goto LABEL_34;
  }
  v73 = 0;
  v29 = v26;
LABEL_17:
  v30 = 0;
  if ( v28 )
  {
    v31 = 0;
    do
    {
      v32 = 3 * v31;
      if ( *(_QWORD *)&v29[24 * v31] )
        *(_QWORD *)&v29[24 * v31] = v27;
      ++v30;
      ++v31;
      v27 += (*(_DWORD *)&v29[8 * v32 + 20] + 3) & 0xFFFFFFFC;
    }
    while ( v30 < v28 );
  }
  Src = v29;
  v33 = (unsigned int)Size / 0x18;
LABEL_23:
  v23 = a4;
LABEL_24:
  v20 = (LPVOID *)a13;
  *a11 = 0;
  *a12 = 0;
  *a13 = 0;
  *a14 = 0;
  v34 = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
  if ( v34 < 0
    || (v34 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_ISimpleTableDispenserWiring, &v63),
        v34 < 0) )
  {
    v22 = 0;
    v40 = Src;
    goto LABEL_35;
  }
  v34 = (*(__int64 (__fastcall **)(__int64, __int64, const struct _GUID *, const struct _GUID *, int, __int128 *))(*(_QWORD *)v63 + 32LL))(
          v63,
          1,
          a2,
          a3,
          v23,
          &v66);
  if ( v34 < 0 )
    goto LABEL_32;
  v35 = v67[0];
  *a10 = **((struct _GUID **)&v66 + 1);
  *a17 = IID_ICatalogTableRead1;
  if ( v35 )
  {
    v36 = -1;
    while ( v35[++v36] != 0 )
      ;
    v38 = 2 * v36 + 2;
    v39 = (char *)CoTaskMemAlloc(v38);
    *a11 = v39;
    if ( !v39 )
    {
      v34 = -2147024882;
LABEL_32:
      v22 = 0;
      goto LABEL_33;
    }
    memcpy_0(v39, v67[0], v38);
  }
  else
  {
    LODWORD(v38) = 0;
    *a11 = 0;
  }
  *a12 = v38;
  if ( v67[1] )
  {
    v55 = (struct _GUID *)CoTaskMemAlloc(0x10u);
    *a13 = v55;
    if ( !v55 )
    {
      v22 = 0;
      v34 = -2147024882;
      v40 = Src;
      v20 = (LPVOID *)a13;
      goto LABEL_35;
    }
    v56 = (struct _GUID *)v67[1];
    *a14 = 1;
    **a13 = *v56;
  }
  else
  {
    *a14 = 0;
  }
  *(_QWORD *)&v64 = a3;
  *((_QWORD *)&v64 + 1) = 0xF000000600000000uLL;
  v65 = 0x1000000048LL;
  if ( (*(unsigned int (__fastcall **)(LPVOID, const struct _GUID *, __int64 *, __int128 *, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         a2,
         tidMETA,
         &v64,
         1,
         1,
         3,
         &v59) )
  {
    v34 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const struct _GUID *, char *, _QWORD, int, unsigned int, __int64 *))(*(_QWORD *)ppv + 24LL))(
            ppv,
            a2,
            a3,
            Src,
            v33,
            1,
            v23 | 9u,
            &v62);
    if ( v34 < 0 )
      goto LABEL_32;
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v62 + 72LL))(
            v62,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            a16);
    if ( v34 < 0 )
      goto LABEL_32;
    v46 = 12LL * *a16;
    if ( v46 <= 0xFFFFFFFF )
    {
      v22 = (char *)CoTaskMemAlloc((unsigned int)v46);
      if ( !v22 )
      {
        v34 = -2147024882;
        goto LABEL_33;
      }
      for ( i = 0; (unsigned int)i < *a16; i = (unsigned int)(i + 1) )
      {
        v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, char *, char *))(*(_QWORD *)v62 + 80LL))(
                v62,
                (unsigned int)i,
                &v22[12 * i],
                &v22[12 * i + 4],
                &v22[12 * i + 8]);
        if ( v34 < 0 )
          goto LABEL_33;
      }
      goto LABEL_102;
    }
LABEL_62:
    v34 = -2147024362;
    goto LABEL_32;
  }
  v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v59 + 72LL))(
          v59,
          0,
          0,
          0,
          0,
          0,
          0,
          a16,
          0);
  if ( v34 < 0 )
    goto LABEL_32;
  v42 = 12LL * *a16;
  if ( v42 > 0xFFFFFFFF )
    goto LABEL_62;
  v22 = (char *)CoTaskMemAlloc((unsigned int)v42);
  if ( !v22 )
  {
    v34 = -2147024882;
    goto LABEL_33;
  }
  v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 32LL))(v59);
  if ( v34 < 0 )
  {
LABEL_33:
    v40 = Src;
LABEL_34:
    v20 = (LPVOID *)a13;
    goto LABEL_35;
  }
  v43 = 0;
  while ( 1 )
  {
    v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 40LL))(v59);
    v34 = v44;
    if ( v44 == -2146367487 )
      break;
    if ( v44 < 0 )
      goto LABEL_33;
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v59 + 64LL))(
            v59,
            1,
            0,
            0,
            &v60);
    if ( v34 < 0 )
      goto LABEL_33;
    v45 = &v22[12 * v43];
    *(_DWORD *)v45 = *v60;
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v59 + 64LL))(
            v59,
            3,
            0,
            0,
            &v60);
    if ( v34 < 0 )
      goto LABEL_33;
    *((_DWORD *)v45 + 2) = *v60;
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD **))(*(_QWORD *)v59 + 64LL))(
            v59,
            2,
            0,
            0,
            &v60);
    if ( v34 < 0 )
      goto LABEL_33;
    v43 = (unsigned int)(v43 + 1);
    *((_DWORD *)v45 + 1) = *v60;
  }
  if ( *a16 != (_DWORD)v43 )
  {
    v34 = -2147418113;
    goto LABEL_33;
  }
LABEL_102:
  *a15 = (struct __MIDL___MIDL_itf_stable_0000_0000_0001 *)v22;
  v58 = (char *)this + 40;
  if ( !this )
    v58 = 0;
  v20 = (LPVOID *)a13;
  v34 = (**(__int64 (__fastcall ***)(char *, struct _GUID *, void **))v58)(v58, a17, a18);
  if ( v34 >= 0 )
  {
    *a19 = 0;
    *a20 = 0;
  }
  v40 = Src;
LABEL_35:
  if ( v73 && v40 )
    CoTaskMemFree(v40);
  if ( v34 < 0 )
  {
    v21 = (LPVOID *)a11;
    goto LABEL_111;
  }
LABEL_37:
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v62 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v62 = 0;
  }
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x1800040d0  mov     rax, rsp
0x1800040d3  mov     [rax+20h], r9d
0x1800040d7  mov     [rax+18h], r8
0x1800040db  mov     [rax+10h], rdx
0x1800040df  mov     [rax+8], rcx
0x1800040e3  push    rbp
0x1800040e4  push    rbx
0x1800040e5  lea     rbp, [rax-17h]
0x1800040e9  sub     rsp, 0F8h
0x1800040f0  mov     [rax-18h], rsi
0x1800040f4  xorps   xmm0, xmm0
0x1800040f7  mov     rsi, [rbp+0Fh+arg_60]
0x1800040fb  mov     [rax-20h], rdi
0x1800040ff  mov     rdi, [rbp+0Fh+arg_50]
0x180004103  mov     [rax-28h], r12
0x180004107  xor     r12d, r12d
0x18000410a  mov     [rax-30h], r13
0x18000410e  mov     [rax-38h], r14
0x180004112  mov     r14d, r9d
0x180004115  mov     [rax-40h], r15
0x180004119  mov     rax, rcx
0x18000411c  mov     r15, [rbp+0Fh+arg_48]
0x180004120  xor     ecx, ecx
0x180004122  mov     qword ptr [rdi], 0
0x180004129  mov     qword ptr [rsi], 0
0x180004130  mov     [rsp+100h+var_98], 0
0x180004139  mov     [rsp+100h+var_90], 0
0x180004142  mov     [rbp+0Fh+var_88], 0
0x18000414a  mov     [rsp+100h+var_A8], 0
0x180004153  mov     [rsp+100h+var_B0], r12
0x180004158  mov     [rbp+0Fh+var_70], rcx
0x18000415c  mov     [rsp+100h+var_A0], rcx
0x180004161  mov     [rbp+0Fh+var_48], rcx
0x180004165  movups  [rbp+0Fh+var_80], xmm0
0x180004169  movups  [rbp+0Fh+var_68], xmm0
0x18000416d  movups  xmmword ptr [rbp+0Fh+var_58], xmm0
0x180004171  test    r15, r15
0x180004174  jz      loc_18000466F
0x18000417a  mov     r12, [rbp+0Fh+arg_58]
0x18000417e  test    r12, r12
0x180004181  jz      loc_180004679
0x180004187  mov     r13, [rbp+0Fh+arg_68]
0x18000418e  test    r13, r13
0x180004191  jz      loc_180004686
0x180004197  cmp     [rbp+0Fh+arg_70], rcx
0x18000419e  jz      loc_180004693
0x1800041a4  cmp     [rbp+0Fh+arg_78], rcx
0x1800041ab  jz      loc_1800046A0
0x1800041b1  cmp     [rbp+0Fh+arg_80], rcx
0x1800041b8  jz      loc_1800046AD
0x1800041be  cmp     [rbp+0Fh+arg_88], rcx
0x1800041c5  jz      loc_1800046BA
0x1800041cb  mov     rcx, [rbp+0Fh+Src]
0x1800041cf  mov     ebx, dword ptr [rbp+0Fh+Size]
0x1800041d2  test    rcx, rcx
0x1800041d5  jz      loc_1800046C7
0x1800041db  mov     rsi, [rbp+0Fh+arg_30]
0x1800041df  test    rsi, rsi
0x1800041e2  jz      loc_1800046DE
0x1800041e8  cmp     [rbp+0Fh+arg_40], 1
0x1800041ec  jnz     loc_1800046FB
0x1800041f2  cmp     dword ptr [rax+0E8h], 1
0x1800041f9  jnz     loc_18000470E
0x1800041ff  test    ebx, ebx
0x180004201  jz      loc_180004720
0x180004207  cmp     dword ptr [rax+0ECh], 0
0x18000420e  mov     r14, rbx
0x180004211  jz      loc_18000472A
0x180004217  mov     rax, 0AAAAAAAAAAAAAAABh
0x180004221  mul     r14
0x180004224  mov     rbx, rdx
0x180004227  shr     rbx, 4
0x18000422b  test    cl, 7
0x18000422e  jnz     loc_1800047D5
0x180004234  mov     dword ptr [rbp+0Fh+arg_48], 0
0x18000423b  mov     rdi, rcx
0x18000423e  xor     ecx, ecx
0x180004240  test    ebx, ebx
0x180004242  jz      short loc_180004271
0x180004244  xor     edx, edx
0x180004246  mov     r8d, 0FFFFFFFCh
0x18000424c  lea     rax, [rdx+rdx*2]
0x180004250  cmp     qword ptr [rdi+rax*8], 0
0x180004255  jz      short loc_18000425B
0x180004257  mov     [rdi+rax*8], rsi
0x18000425b  mov     eax, [rdi+rax*8+14h]
0x18000425f  inc     ecx
0x180004261  add     eax, 3
0x180004264  inc     rdx
0x180004267  and     rax, r8
0x18000426a  add     rsi, rax
0x18000426d  cmp     ecx, ebx
0x18000426f  jb      short loc_18000424C
0x180004271  mov     [rbp+0Fh+Src], rdi
0x180004275  mov     edi, ebx
0x180004277  mov     r14d, [rbp+0Fh+arg_18]
0x18000427b  mov     rax, [rbp+0Fh+arg_50]
0x18000427f  lea     r9, IID_ISimpleTableDispenser; riid
0x180004286  mov     rsi, [rbp+0Fh+arg_60]
0x18000428a  lea     rcx, CLSID_STDispenser; rclsid
0x180004291  xor     edx, edx; pUnkOuter
0x180004293  mov     r8d, 1; dwClsContext
0x180004299  mov     qword ptr [rax], 0
0x1800042a0  lea     rax, [rsp+100h+var_98]
0x1800042a5  mov     dword ptr [r12], 0
0x1800042ad  mov     qword ptr [rsi], 0
0x1800042b4  mov     dword ptr [r13+0], 0
0x1800042bc  mov     [rsp+100h+ppv], rax; ppv
0x1800042c1  call    cs:__imp_CoCreateInstance
0x1800042c7  mov     ebx, eax
0x1800042c9  test    eax, eax
0x1800042cb  js      loc_1800049CF
0x1800042d1  mov     rcx, [rsp+100h+var_98]
0x1800042d6  lea     r8, [rbp+0Fh+var_88]
0x1800042da  lea     rdx, IID_ISimpleTableDispenserWiring
0x1800042e1  mov     rax, [rcx]
0x1800042e4  mov     rax, [rax]
0x1800042e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ec  mov     ebx, eax
0x1800042ee  test    eax, eax
0x1800042f0  js      loc_1800049CF
0x1800042f6  mov     rcx, [rbp+0Fh+var_88]
0x1800042fa  lea     rdx, [rbp+0Fh+var_68]
0x1800042fe  mov     rsi, [rbp+0Fh+arg_10]
0x180004302  mov     r8, [rbp+0Fh+arg_8]
0x180004306  mov     r9, rsi
0x180004309  mov     [rsp+100h+var_D8], rdx
0x18000430e  mov     edx, 1
0x180004313  mov     rax, [rcx]
0x180004316  mov     dword ptr [rsp+100h+ppv], r14d
0x18000431b  mov     rax, [rax+20h]
0x18000431f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004324  mov     ebx, eax
0x180004326  test    eax, eax
0x180004328  js      short loc_180004392
0x18000432a  mov     rax, qword ptr [rbp+0Fh+var_68+8]
0x18000432e  movups  xmm1, xmmword ptr cs:IID_ICatalogTableRead1.Data1
0x180004335  mov     rcx, [rbp+0Fh+var_58]
0x180004339  movups  xmm0, xmmword ptr [rax]
0x18000433c  movups  xmmword ptr [r15], xmm0
0x180004340  mov     r15, [rbp+0Fh+arg_80]
0x180004347  movups  xmmword ptr [r15], xmm1
0x18000434b  test    rcx, rcx
0x18000434e  jz      loc_180004424
0x180004354  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000435b  nop     dword ptr [rax+rax+00h]
0x180004360  cmp     word ptr [rcx+rax*2+2], 0
0x180004366  lea     rax, [rax+1]
0x18000436a  jnz     short loc_180004360
0x18000436c  lea     rbx, ds:2[rax*2]
0x180004374  mov     rcx, rbx; cb
0x180004377  call    cs:__imp_CoTaskMemAlloc
0x18000437d  mov     rcx, [rbp+0Fh+arg_50]
0x180004381  mov     [rcx], rax
0x180004384  test    rax, rax
0x180004387  jnz     loc_180004817
0x18000438d  mov     ebx, 8007000Eh
0x180004392  mov     r12, [rsp+100h+var_B0]
0x180004397  mov     rax, [rbp+0Fh+Src]
0x18000439b  mov     rsi, [rbp+0Fh+arg_60]
0x18000439f  cmp     dword ptr [rbp+0Fh+arg_48], 0
0x1800043a3  jnz     loc_1800049DD
0x1800043a9  test    ebx, ebx
0x1800043ab  js      loc_1800049F4
0x1800043b1  mov     rcx, [rbp+0Fh+var_88]
0x1800043b5  mov     r15, [rsp+100h+var_38]
0x1800043bd  mov     r14, [rsp+100h+var_30]
0x1800043c5  mov     r13, [rsp+100h+var_28]
0x1800043cd  mov     r12, [rsp+100h+var_20]
0x1800043d5  mov     rdi, [rsp+100h+var_18]
0x1800043dd  mov     rsi, [rsp+0F0h]
0x1800043e5  test    rcx, rcx
0x1800043e8  jnz     loc_180004A43
0x1800043ee  mov     rcx, [rsp+100h+var_98]
0x1800043f3  test    rcx, rcx
0x1800043f6  jnz     loc_180004A5C
0x1800043fc  mov     rcx, [rsp+100h+var_90]
0x180004401  test    rcx, rcx
0x180004404  jnz     loc_180004A76
0x18000440a  mov     rcx, [rsp+100h+var_A8]
0x18000440f  test    rcx, rcx
0x180004412  jnz     loc_180004A90
0x180004418  mov     eax, ebx
0x18000441a  add     rsp, 0F8h
0x180004421  pop     rbx
0x180004422  pop     rbp
0x180004423  retn
0x180004424  mov     rax, [rbp+0Fh+arg_50]
0x180004428  xor     ebx, ebx
0x18000442a  mov     qword ptr [rax], 0
0x180004431  mov     [r12], ebx
0x180004435  cmp     [rbp+0Fh+var_58+8], 0
0x18000443a  jnz     loc_18000482B
0x180004440  mov     dword ptr [r13+0], 0
0x180004448  mov     rcx, [rsp+100h+var_98]
0x18000444d  lea     rdx, [rsp+100h+var_A8]
0x180004452  mov     rbx, [rbp+0Fh+arg_8]
0x180004456  lea     r9, [rbp+0Fh+var_80]
0x18000445a  mov     [rsp+100h+var_C8], rdx
0x18000445f  lea     r8, tidMETA
0x180004466  mov     qword ptr [rbp+0Fh+var_80], rsi
0x18000446a  mov     rdx, rbx
0x18000446d  mov     dword ptr [rbp+0Fh+var_80+8], 0
0x180004474  mov     dword ptr [rbp+0Fh+var_80+0Ch], 0F0000006h
0x18000447b  mov     dword ptr [rbp+0Fh+var_70], 48h ; 'H'
0x180004482  mov     dword ptr [rbp+0Fh+var_70+4], 10h
0x180004489  mov     rax, [rcx]
0x18000448c  mov     dword ptr [rsp+100h+var_D0], 3
0x180004494  mov     dword ptr [rsp+100h+var_D8], 1
0x18000449c  mov     [rsp+100h+ppv], 1
0x1800044a5  mov     rax, [rax+18h]
0x1800044a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ae  test    eax, eax
0x1800044b0  jnz     loc_18000487C
0x1800044b6  mov     rcx, [rsp+100h+var_A8]
0x1800044bb  xor     r9d, r9d
0x1800044be  mov     rdi, [rbp+0Fh+arg_78]
0x1800044c5  xor     r8d, r8d
0x1800044c8  mov     qword ptr [rsp+40h], 0
0x1800044d1  xor     edx, edx
0x1800044d3  mov     [rsp+100h+var_C8], rdi
0x1800044d8  mov     rax, [rcx]
0x1800044db  mov     [rsp+100h+var_D0], 0
0x1800044e4  mov     [rsp+100h+var_D8], 0
0x1800044ed  mov     [rsp+100h+ppv], 0
0x1800044f6  mov     rax, [rax+48h]
0x1800044fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ff  mov     ebx, eax
0x180004501  test    eax, eax
0x180004503  js      loc_180004392
0x180004509  mov     eax, [rdi]
0x18000450b  lea     rcx, [rax+rax*2]
0x18000450f  mov     eax, 0FFFFFFFFh
0x180004514  shl     rcx, 2
0x180004518  cmp     rcx, rax
0x18000451b  ja      loc_18000464C
0x180004521  mov     ecx, ecx; cb
0x180004523  call    cs:__imp_CoTaskMemAlloc
0x180004529  mov     r12, rax
0x18000452c  test    rax, rax
0x18000452f  jz      loc_180004872
0x180004535  mov     rcx, [rsp+100h+var_A8]
0x18000453a  mov     rax, [rcx]
0x18000453d  mov     rax, [rax+20h]
0x180004541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004546  mov     ebx, eax
0x180004548  test    eax, eax
0x18000454a  js      loc_180004397
0x180004550  xor     esi, esi
0x180004552  mov     rcx, [rsp+100h+var_A8]
0x180004557  mov     rax, [rcx]
0x18000455a  mov     rax, [rax+28h]
0x18000455e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004563  mov     ebx, eax
0x180004565  cmp     eax, 80110801h
0x18000456a  jz      loc_180004656
0x180004570  test    eax, eax
0x180004572  js      loc_180004397
0x180004578  mov     rcx, [rsp+100h+var_A8]
0x18000457d  lea     rdx, [rsp+100h+var_A0]
0x180004582  mov     [rsp+100h+ppv], rdx
0x180004587  xor     r9d, r9d
0x18000458a  xor     r8d, r8d
0x18000458d  mov     edx, 1
0x180004592  mov     rax, [rcx]
0x180004595  mov     rax, [rax+40h]
0x180004599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459e  mov     ebx, eax
0x1800045a0  test    eax, eax
0x1800045a2  js      loc_180004397
0x1800045a8  mov     rax, [rsp+100h+var_A0]
0x1800045ad  lea     rcx, [rsi+rsi*2]
0x1800045b1  lea     rdi, [r12+rcx*4]
0x1800045b5  xor     r9d, r9d
0x1800045b8  lea     rdx, [rsp+100h+var_A0]
0x1800045bd  xor     r8d, r8d
0x1800045c0  mov     [rsp+100h+ppv], rdx
0x1800045c5  mov     edx, 3
0x1800045ca  mov     ecx, [rax]
0x1800045cc  mov     [rdi], ecx
0x1800045ce  mov     rcx, [rsp+100h+var_A8]
0x1800045d3  mov     rax, [rcx]
0x1800045d6  mov     rax, [rax+40h]
0x1800045da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045df  mov     ebx, eax
0x1800045e1  test    eax, eax
0x1800045e3  js      loc_180004397
0x1800045e9  mov     rax, [rsp+100h+var_A0]
0x1800045ee  lea     rdx, [rsp+100h+var_A0]
0x1800045f3  mov     [rsp+100h+ppv], rdx
0x1800045f8  xor     r9d, r9d
0x1800045fb  xor     r8d, r8d
0x1800045fe  mov     edx, 2
0x180004603  mov     ecx, [rax]
0x180004605  mov     [rdi+8], ecx
0x180004608  mov     rcx, [rsp+100h+var_A8]
0x18000460d  mov     rax, [rcx]
0x180004610  mov     rax, [rax+40h]
0x180004614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004619  mov     ebx, eax
  ... truncated ...
```
