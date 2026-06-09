# CCatalogServer::InternalReadTable(_GUID const &,_GUID const &,ulong,char *,ulong,char *,ulong,ulong,char * *,ulong *,char * *,ulong *,char * *,ulong *,char * *,ulong *,char * *,ulong *)

- ea: `0x180005150`
- end: `0x18000567f`
- name: `?InternalReadTable@CCatalogServer@@AEAAJAEBU_GUID@@0KPEADK1KKPEAPEADPEAK23232323@Z`
- size: `1327`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int, char *Src, size_t Size, char *, unsigned int, unsigned int, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004c10`

## callees

- `0x180005150`
- `0x18005488c`
- `0x18005550e`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005665`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005665`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000560e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000560e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000531a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000531a`

## pseudocode

```c
__int64 __fastcall CCatalogServer::InternalReadTable(
        CCatalogServer *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        int a4,
        char *Src,
        size_t Size,
        char *a7,
        unsigned int a8,
        unsigned int a9,
        char **a10,
        unsigned int *a11,
        char **a12,
        unsigned int *a13,
        char **a14,
        unsigned int *a15,
        char **a16,
        unsigned int *a17,
        char **a18,
        unsigned int *a19)
{
  char *v19; // rdi
  char **v20; // r14
  char **v22; // r15
  char *v23; // rsi
  unsigned int v24; // ebx
  char *v25; // r15
  unsigned int v26; // edx
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned int v29; // esi
  HRESULT v30; // ebx
  int v31; // esi
  HRESULT v33; // eax
  unsigned int v34; // ebx
  char *v35; // r14
  unsigned int v36; // r10d
  __int64 v37; // r9
  __int64 v38; // rdx
  char *v39; // rcx
  char *v40; // r11
  int v41; // eax
  char *v42; // rax
  int v43; // [rsp+74h] [rbp-8Ch]
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  int v47; // [rsp+90h] [rbp-70h]
  LPVOID ppv; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v49; // [rsp+A0h] [rbp-60h]
  char **v50; // [rsp+A8h] [rbp-58h]
  const struct _GUID *v51; // [rsp+B0h] [rbp-50h]
  const struct _GUID *v52; // [rsp+B8h] [rbp-48h]
  unsigned int *v53; // [rsp+C0h] [rbp-40h]
  char **v54; // [rsp+C8h] [rbp-38h]
  unsigned int *v55; // [rsp+D0h] [rbp-30h]
  unsigned int *v56; // [rsp+D8h] [rbp-28h]
  unsigned int *v57; // [rsp+E0h] [rbp-20h]
  unsigned int *v58; // [rsp+E8h] [rbp-18h]
  __int128 v59; // [rsp+F0h] [rbp-10h] BYREF

  v19 = Src;
  v20 = a14;
  v22 = a16;
  v47 = a4;
  v51 = a3;
  v52 = a2;
  v58 = a11;
  v57 = a13;
  v56 = a15;
  v55 = a17;
  v50 = a14;
  v49 = (unsigned __int64)a16;
  v54 = a18;
  v53 = a19;
  ppv = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v59 = 0;
  if ( !Src && (_DWORD)Size )
    return (unsigned int)-2147024809;
  v23 = a7;
  if ( !a7 && a8 || a9 != 1 || !a10 && !a11 || !a12 && !a13 || !a14 && !a15 || !a16 && !a17 || !a18 && !a19 )
    return (unsigned int)-2147024809;
  if ( *((_DWORD *)this + 58) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !(_DWORD)Size )
  {
    v29 = 0;
    v43 = 0;
    goto LABEL_22;
  }
  if ( *((_DWORD *)this + 59) )
  {
    v24 = (unsigned int)Size / 0x18;
    if ( ((unsigned __int8)Src & 7) == 0 )
    {
      v43 = 0;
      v25 = Src;
LABEL_15:
      v26 = 0;
      if ( v24 )
      {
        v27 = 0;
        do
        {
          v28 = 3 * v27;
          if ( *(_QWORD *)&v25[24 * v27] )
            *(_QWORD *)&v25[24 * v27] = v23;
          ++v26;
          ++v27;
          v23 += (*(_DWORD *)&v25[8 * v28 + 20] + 3) & 0xFFFFFFFC;
        }
        while ( v26 < v24 );
      }
      v19 = v25;
      v29 = (unsigned int)Size / 0x18;
      v22 = (char **)v49;
LABEL_21:
      v20 = v50;
LABEL_22:
      v30 = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
      if ( v30 >= 0 )
      {
        v30 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const struct _GUID *, char *, _QWORD, int, unsigned int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                ppv,
                v52,
                v51,
                v19,
                v29,
                1,
                v47 | 1u,
                &v44);
        if ( v30 >= 0 )
        {
          v30 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v44)(v44, &IID_ISimpleTableControl, &v46);
          if ( v30 >= 0 )
          {
            v30 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v46 + 112LL))(v46, &v59, &v45);
            if ( v30 >= 0 )
            {
              v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44);
              v30 = v33;
              if ( !v33 )
              {
                v31 = 0;
LABEL_42:
                v30 = (*(__int64 (__fastcall **)(__int64, __int64, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *, char **, unsigned int *))(*(_QWORD *)v45 + 24LL))(
                        v45,
                        327680,
                        a10,
                        v58,
                        a12,
                        v57,
                        v20,
                        v56,
                        v22,
                        v55,
                        v54,
                        v53);
                goto LABEL_25;
              }
              if ( v33 == -2146367486 )
              {
                v31 = 1;
                goto LABEL_42;
              }
            }
          }
        }
      }
      v31 = 0;
      goto LABEL_25;
    }
    v43 = 1;
    v42 = (char *)CoTaskMemAlloc(24LL * v24);
    v25 = v42;
    if ( v42 )
    {
      memcpy_0(v42, Src, (unsigned int)Size);
      goto LABEL_15;
    }
  }
  else
  {
    v43 = 0;
    v34 = (unsigned int)Size / 0x14;
    v49 = (unsigned int)Size / 0x14uLL;
    v35 = (char *)CoTaskMemAlloc(24LL * ((unsigned int)Size / 0x14));
    if ( v35 )
    {
      v36 = 0;
      v43 = 1;
      if ( v34 )
      {
        v37 = 0;
        do
        {
          v38 = *(unsigned int *)&Src[20 * v37];
          v39 = &Src[20 * v37];
          *(_QWORD *)&v35[24 * v37] = v38;
          v40 = &v35[24 * v37];
          *((_DWORD *)v40 + 2) = *((_DWORD *)v39 + 1);
          *((_DWORD *)v40 + 3) = *((_DWORD *)v39 + 2);
          *((_DWORD *)v40 + 4) = *((_DWORD *)v39 + 3);
          v41 = *((_DWORD *)v39 + 4);
          *((_DWORD *)v40 + 5) = v41;
          if ( v38 )
            *(_QWORD *)v40 = v23;
          ++v36;
          ++v37;
          v23 += (v41 + 3) & 0xFFFFFFFC;
        }
        while ( v36 < v34 );
      }
      v29 = v49;
      v19 = v35;
      goto LABEL_21;
    }
  }
  v30 = -2147024882;
  v19 = 0;
  v31 = 0;
LABEL_25:
  if ( v43 && v19 )
    CoTaskMemFree(v19);
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( !v30 && v31 )
    return (unsigned int)-2146367486;
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x180005150  push    rbp
0x180005152  push    rbx
0x180005153  push    rdi
0x180005154  push    r12
0x180005156  push    r13
0x180005158  push    r14
0x18000515a  push    r15
0x18000515c  lea     rbp, [rsp-10h]
0x180005161  sub     rsp, 110h
0x180005168  mov     rax, cs:__security_cookie
0x18000516f  xor     rax, rsp
0x180005172  mov     [rbp+40h+var_40], rax
0x180005176  mov     rdi, [rbp+40h+Src]
0x18000517a  xor     r11d, r11d
0x18000517d  mov     r14, [rbp+40h+arg_68]
0x180005184  mov     rbx, rcx
0x180005187  mov     rcx, [rbp+40h+arg_50]
0x18000518e  xorps   xmm0, xmm0
0x180005191  mov     r15, [rbp+40h+arg_78]
0x180005198  mov     rax, [rbp+40h+arg_88]
0x18000519f  mov     r10, [rbp+40h+arg_90]
0x1800051a6  mov     r12, [rbp+40h+arg_48]
0x1800051ad  mov     r13, [rbp+40h+arg_58]
0x1800051b4  mov     [rbp+40h+var_B0], r9d
0x1800051b8  mov     r9, [rbp+40h+arg_80]
0x1800051bf  mov     [rbp+40h+var_90], r8
0x1800051c3  mov     r8, [rbp+40h+arg_70]
0x1800051ca  mov     [rbp+40h+var_88], rdx
0x1800051ce  mov     rdx, [rbp+40h+arg_60]
0x1800051d5  mov     [rbp+40h+var_58], rcx
0x1800051d9  mov     [rbp+40h+var_60], rdx
0x1800051dd  mov     [rbp+40h+var_68], r8
0x1800051e1  mov     [rbp+40h+var_70], r9
0x1800051e5  mov     [rbp+40h+var_98], r14
0x1800051e9  mov     [rbp+40h+var_A0], r15
0x1800051ed  mov     [rbp+40h+var_78], rax
0x1800051f1  mov     [rbp+40h+var_80], r10
0x1800051f5  mov     [rbp+40h+var_A8], r11
0x1800051f9  mov     [rsp+140h+var_C8], r11
0x1800051fe  mov     [rbp+40h+var_C0], r11
0x180005202  mov     [rbp+40h+var_B8], r11
0x180005206  movups  [rbp+40h+var_50], xmm0
0x18000520a  test    rdi, rdi
0x18000520d  jz      loc_180005417
0x180005213  mov     [rsp+140h+arg_0], rsi
0x18000521b  mov     rsi, [rbp+40h+arg_30]
0x180005222  test    rsi, rsi
0x180005225  jz      loc_1800054ED
0x18000522b  cmp     [rbp+40h+arg_40], 1
0x180005232  jnz     loc_18000552C
0x180005238  test    r12, r12
0x18000523b  jz      loc_1800054FB
0x180005241  test    r13, r13
0x180005244  jz      loc_180005505
0x18000524a  test    r14, r14
0x18000524d  jz      loc_18000550F
0x180005253  test    r15, r15
0x180005256  jz      loc_180005519
0x18000525c  test    rax, rax
0x18000525f  jz      loc_180005523
0x180005265  cmp     dword ptr [rbx+0E8h], 1
0x18000526c  mov     [rsp+140h+var_D0], r11d
0x180005271  jnz     loc_180005536
0x180005277  cmp     dword ptr [rbp+40h+Size], 0
0x18000527b  jz      loc_180005543
0x180005281  cmp     dword ptr [rbx+0ECh], 0
0x180005288  mov     r14d, dword ptr [rbp+40h+Size]
0x18000528c  jz      loc_180005550
0x180005292  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000529c  mul     r14
0x18000529f  mov     rbx, rdx
0x1800052a2  shr     rbx, 4
0x1800052a6  test    dil, 7
0x1800052aa  jnz     loc_1800055FC
0x1800052b0  mov     [rsp+140h+var_CC], r11d
0x1800052b5  mov     r15, rdi
0x1800052b8  mov     edx, r11d
0x1800052bb  test    ebx, ebx
0x1800052bd  jz      short loc_1800052EE
0x1800052bf  mov     rcx, r11
0x1800052c2  mov     r8d, 0FFFFFFFCh
0x1800052c8  lea     rax, [rcx+rcx*2]
0x1800052cc  cmp     qword ptr [r15+rax*8], 0
0x1800052d1  jz      short loc_1800052D7
0x1800052d3  mov     [r15+rax*8], rsi
0x1800052d7  mov     eax, [r15+rax*8+14h]
0x1800052dc  inc     edx
0x1800052de  add     eax, 3
0x1800052e1  inc     rcx
0x1800052e4  and     rax, r8
0x1800052e7  add     rsi, rax
0x1800052ea  cmp     edx, ebx
0x1800052ec  jb      short loc_1800052C8
0x1800052ee  mov     rdi, r15
0x1800052f1  mov     esi, ebx
0x1800052f3  mov     r15, [rbp+40h+var_A0]
0x1800052f7  mov     r14, [rbp+40h+var_98]
0x1800052fb  lea     rax, [rbp+40h+var_A8]
0x1800052ff  xor     edx, edx; pUnkOuter
0x180005301  lea     r9, IID_ISimpleTableDispenser; riid
0x180005308  mov     [rsp+140h+ppv], rax; ppv
0x18000530d  mov     r8d, 1; dwClsContext
0x180005313  lea     rcx, CLSID_STDispenser; rclsid
0x18000531a  call    cs:__imp_CoCreateInstance
0x180005320  mov     ebx, eax
0x180005322  test    eax, eax
0x180005324  js      short loc_180005372
0x180005326  mov     rcx, [rbp+40h+var_A8]
0x18000532a  lea     rdx, [rsp+140h+var_C8]
0x18000532f  mov     r10d, [rbp+40h+var_B0]
0x180005333  mov     r8, [rbp+40h+var_90]
0x180005337  or      r10d, 1
0x18000533b  mov     [rsp+140h+var_108], rdx
0x180005340  mov     rax, [rcx]
0x180005343  mov     rdx, [rbp+40h+var_88]
0x180005347  mov     dword ptr [rsp+140h+var_110], r10d
0x18000534c  mov     r9d, esi
0x18000534f  mov     rax, [rax+18h]
0x180005353  mov     dword ptr [rsp+140h+var_118], 1
0x18000535b  mov     [rsp+140h+ppv], r9
0x180005360  mov     r9, rdi
0x180005363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005368  mov     ebx, eax
0x18000536a  test    eax, eax
0x18000536c  jns     loc_180005428
0x180005372  mov     esi, [rsp+140h+var_D0]
0x180005376  xor     r14d, r14d
0x180005379  cmp     [rsp+140h+var_CC], 0
0x18000537e  jnz     loc_180005659
0x180005384  mov     rcx, [rsp+140h+var_C8]
0x180005389  test    rcx, rcx
0x18000538c  jz      short loc_18000539F
0x18000538e  mov     rax, [rcx]
0x180005391  mov     rax, [rax+10h]
0x180005395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539a  mov     [rsp+140h+var_C8], r14
0x18000539f  mov     rcx, [rbp+40h+var_C0]
0x1800053a3  test    rcx, rcx
0x1800053a6  jz      short loc_1800053B8
0x1800053a8  mov     rax, [rcx]
0x1800053ab  mov     rax, [rax+10h]
0x1800053af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b4  mov     [rbp+40h+var_C0], r14
0x1800053b8  mov     rcx, [rbp+40h+var_B8]
0x1800053bc  test    rcx, rcx
0x1800053bf  jz      short loc_1800053D1
0x1800053c1  mov     rax, [rcx]
0x1800053c4  mov     rax, [rax+10h]
0x1800053c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cd  mov     [rbp+40h+var_B8], r14
0x1800053d1  mov     rcx, [rbp+40h+var_A8]
0x1800053d5  test    rcx, rcx
0x1800053d8  jz      short loc_1800053E6
0x1800053da  mov     rax, [rcx]
0x1800053dd  mov     rax, [rax+10h]
0x1800053e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e6  test    ebx, ebx
0x1800053e8  jz      loc_180005670
0x1800053ee  mov     rsi, [rsp+140h+arg_0]
0x1800053f6  mov     eax, ebx
0x1800053f8  mov     rcx, [rbp+40h+var_40]
0x1800053fc  xor     rcx, rsp; StackCookie
0x1800053ff  call    __security_check_cookie
0x180005404  add     rsp, 110h
0x18000540b  pop     r15
0x18000540d  pop     r14
0x18000540f  pop     r13
0x180005411  pop     r12
0x180005413  pop     rdi
0x180005414  pop     rbx
0x180005415  pop     rbp
0x180005416  retn
0x180005417  cmp     dword ptr [rbp+40h+Size], r11d
0x18000541b  jz      loc_180005213
0x180005421  mov     ebx, 80070057h
0x180005426  jmp     short loc_1800053F6
0x180005428  mov     rcx, [rsp+140h+var_C8]
0x18000542d  lea     r8, [rbp+40h+var_B8]
0x180005431  lea     rdx, IID_ISimpleTableControl
0x180005438  mov     rax, [rcx]
0x18000543b  mov     rax, [rax]
0x18000543e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005443  mov     ebx, eax
0x180005445  test    eax, eax
0x180005447  js      loc_180005372
0x18000544d  mov     rcx, [rbp+40h+var_B8]
0x180005451  lea     r8, [rbp+40h+var_C0]
0x180005455  lea     rdx, [rbp+40h+var_50]
0x180005459  mov     rax, [rcx]
0x18000545c  mov     rax, [rax+70h]
0x180005460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005465  mov     ebx, eax
0x180005467  test    eax, eax
0x180005469  js      loc_180005372
0x18000546f  mov     rcx, [rsp+140h+var_C8]
0x180005474  mov     rax, [rcx]
0x180005477  mov     rax, [rax+18h]
0x18000547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005480  mov     ebx, eax
0x180005482  test    eax, eax
0x180005484  jnz     loc_180005644
0x18000548a  mov     esi, [rsp+140h+var_D0]
0x18000548e  mov     rdx, [rbp+40h+var_80]
0x180005492  mov     r8, r12
0x180005495  mov     rcx, [rbp+40h+var_C0]
0x180005499  mov     r9, [rbp+40h+var_58]
0x18000549d  mov     [rsp+140h+var_E8], rdx
0x1800054a2  mov     rdx, [rbp+40h+var_78]
0x1800054a6  mov     rax, [rcx]
0x1800054a9  mov     [rsp+140h+var_F0], rdx
0x1800054ae  mov     rdx, [rbp+40h+var_70]
0x1800054b2  mov     [rsp+140h+var_F8], rdx
0x1800054b7  mov     rdx, [rbp+40h+var_68]
0x1800054bb  mov     rax, [rax+18h]
0x1800054bf  mov     [rsp+140h+var_100], r15
0x1800054c4  mov     [rsp+140h+var_108], rdx
0x1800054c9  mov     rdx, [rbp+40h+var_60]
0x1800054cd  mov     [rsp+140h+var_110], r14
0x1800054d2  mov     [rsp+140h+var_118], rdx
0x1800054d7  mov     edx, 50000h
0x1800054dc  mov     [rsp+140h+ppv], r13
0x1800054e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e6  mov     ebx, eax
0x1800054e8  jmp     loc_180005376
0x1800054ed  cmp     [rbp+40h+arg_38], r11d
0x1800054f4  jnz     short loc_18000552C
0x1800054f6  jmp     loc_18000522B
0x1800054fb  test    rcx, rcx
0x1800054fe  jz      short loc_18000552C
0x180005500  jmp     loc_180005241
0x180005505  test    rdx, rdx
0x180005508  jz      short loc_18000552C
0x18000550a  jmp     loc_18000524A
0x18000550f  test    r8, r8
0x180005512  jz      short loc_18000552C
0x180005514  jmp     loc_180005253
0x180005519  test    r9, r9
0x18000551c  jz      short loc_18000552C
0x18000551e  jmp     loc_18000525C
0x180005523  test    r10, r10
0x180005526  jnz     loc_180005265
0x18000552c  mov     ebx, 80070057h
0x180005531  jmp     loc_1800053EE
0x180005536  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000553b  xor     r11d, r11d
0x18000553e  jmp     loc_180005277
0x180005543  mov     esi, r11d
0x180005546  mov     [rsp+140h+var_CC], r11d
0x18000554b  jmp     loc_1800052FB
0x180005550  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000555a  mov     [rsp+140h+var_CC], r11d
0x18000555f  mul     r14
0x180005562  mov     rbx, rdx
0x180005565  shr     rbx, 4
0x180005569  mov     eax, ebx
0x18000556b  mov     [rbp+40h+var_A0], rbx
0x18000556f  lea     rcx, [rax+rax*2]
0x180005573  shl     rcx, 3; cb
0x180005577  call    cs:__imp_CoTaskMemAlloc
0x18000557d  mov     r14, rax
0x180005580  test    rax, rax
0x180005583  jz      loc_180005632
0x180005589  xor     r10d, r10d
0x18000558c  mov     [rsp+140h+var_CC], 1
0x180005594  test    ebx, ebx
0x180005596  jz      short loc_1800055F0
0x180005598  xor     r9d, r9d
0x18000559b  mov     r8d, 0FFFFFFFCh
0x1800055a1  lea     rax, [r9+r9*4]
0x1800055a5  mov     edx, [rdi+rax*4]
0x1800055a8  lea     rcx, [rdi+rax*4]
0x1800055ac  lea     rax, [r9+r9*2]
0x1800055b0  mov     [r14+rax*8], rdx
0x1800055b4  lea     r11, [r14+rax*8]
0x1800055b8  mov     eax, [rcx+4]
0x1800055bb  mov     [r11+8], eax
0x1800055bf  mov     eax, [rcx+8]
0x1800055c2  mov     [r11+0Ch], eax
0x1800055c6  mov     eax, [rcx+0Ch]
0x1800055c9  mov     [r11+10h], eax
0x1800055cd  mov     eax, [rcx+10h]
0x1800055d0  mov     [r11+14h], eax
0x1800055d4  test    rdx, rdx
0x1800055d7  jz      short loc_1800055DC
0x1800055d9  mov     [r11], rsi
0x1800055dc  add     eax, 3
0x1800055df  inc     r10d
0x1800055e2  and     rax, r8
0x1800055e5  inc     r9
0x1800055e8  add     rsi, rax
0x1800055eb  cmp     r10d, ebx
0x1800055ee  jb      short loc_1800055A1
0x1800055f0  mov     rsi, [rbp+40h+var_A0]
0x1800055f4  mov     rdi, r14
0x1800055f7  jmp     loc_1800052F7
0x1800055fc  mov     eax, ebx
0x1800055fe  mov     [rsp+140h+var_CC], 1
0x180005606  lea     rcx, [rax+rax*2]
0x18000560a  shl     rcx, 3; cb
0x18000560e  call    cs:__imp_CoTaskMemAlloc
  ... truncated ...
```
