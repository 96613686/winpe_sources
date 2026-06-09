# RegisterServiceExtensionCLSIDs(void)

- ea: `0x180003118`
- end: `0x180003488`
- name: `?RegisterServiceExtensionCLSIDs@@YAXXZ`
- size: `880`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001e60`

## callees

- `0x180003118`
- `0x180003fd0`
- `0x180005010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800032ba`
- `ole32!CoCreateInstance` at `0x1800032ba`
- `ole32!StringFromCLSID` at `0x180003202`
- `ole32!StringFromCLSID` at `0x180003202`
- `ole32!CoGetMalloc` at `0x180003187`
- `ole32!CoGetMalloc` at `0x180003187`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003466`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003466`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800031ec`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003283`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800031ec`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003283`

## string_xrefs

- `0x1800032d7`: `LM/IISADMIN/EXTENSIONS/DCOMCLSIDS`

## pseudocode

```c
void RegisterServiceExtensionCLSIDs(void)
{
  _QWORD *v0; // rbx
  unsigned int v1; // edi
  unsigned int i; // esi
  int v3; // eax
  LPMALLOC v4; // r14
  LPOLESTR v5; // rax
  _QWORD *v6; // rdx
  __int64 v7; // r8
  LPVOID v8; // rcx
  unsigned int v9; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-85h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-81h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-79h] BYREF
  LPMALLOC ppMalloc; // [rsp+58h] [rbp-71h] BYREF
  __int128 v14; // [rsp+60h] [rbp-69h] BYREF
  __int128 v15; // [rsp+70h] [rbp-59h]
  __int64 v16; // [rsp+80h] [rbp-49h]
  IID rclsid; // [rsp+90h] [rbp-39h] BYREF
  _QWORD v18[4]; // [rsp+A0h] [rbp-29h] BYREF
  _QWORD *v19; // [rsp+C0h] [rbp-9h]
  int v20; // [rsp+C8h] [rbp-1h]
  __int16 v21; // [rsp+CCh] [rbp+3h]
  IID v22; // [rsp+D0h] [rbp+7h] BYREF

  v20 = 32;
  ppv = 0;
  v9 = 0;
  v16 = 0;
  v10 = 0;
  v18[0] = 0;
  v22 = 0;
  v19 = v18;
  v14 = 0;
  v21 = 256;
  v15 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v0 = g_piaecHead;
    v1 = 0;
    while ( v0 )
    {
      for ( i = 0; ; ++i )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD, IID *, _QWORD))(*(_QWORD *)*v0 + 32LL))(*v0, &v22, i);
        if ( v3 == -2147024637 )
          break;
        if ( v3 < 0 )
          goto LABEL_21;
        v4 = ppMalloc;
        rclsid = v22;
        lpsz = 0;
        if ( !BUFFER::Resize((BUFFER *)v18, 2 * v1 + 78) )
          goto LABEL_21;
        if ( StringFromCLSID(&rclsid, &lpsz) >= 0 )
        {
          v5 = lpsz;
          v6 = v19;
          v7 = v1;
          v1 += 39;
          *(_OWORD *)((char *)v19 + 2 * v7) = *(_OWORD *)lpsz;
          *(_OWORD *)((char *)v6 + 2 * v7 + 16) = *((_OWORD *)v5 + 1);
          *(_OWORD *)((char *)v6 + 2 * v7 + 32) = *((_OWORD *)v5 + 2);
          *(_OWORD *)((char *)v6 + 2 * v7 + 48) = *((_OWORD *)v5 + 3);
          *(_OWORD *)((char *)v6 + 2 * v7 + 62) = *(_OWORD *)(v5 + 31);
          if ( v4 )
            ((void (__fastcall *)(LPMALLOC, LPOLESTR))v4->lpVtbl->Free)(v4, lpsz);
        }
      }
      v0 = (_QWORD *)v0[1];
    }
    if ( BUFFER::Resize((BUFFER *)v18, 2 * v1 + 2) )
    {
      *((_WORD *)v19 + v1) = 0;
      if ( CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x15u, &IID_IMSAdminBase_W, &ppv) >= 0 )
      {
        if ( (*(unsigned int (__fastcall **)(LPVOID, _QWORD, const wchar_t *, __int64, int, unsigned int *))(*(_QWORD *)ppv + 136LL))(
               ppv,
               0,
               L"LM/IISADMIN/EXTENSIONS/DCOMCLSIDS",
               3,
               2000,
               &v10) != -2147024893
          || (*(int (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64, int, unsigned int *))(*(_QWORD *)ppv + 136LL))(
               ppv,
               0,
               0,
               3,
               2000,
               &v9) >= 0
          && (*(int (__fastcall **)(LPVOID, _QWORD, const wchar_t *))(*(_QWORD *)ppv + 24LL))(
               ppv,
               v9,
               L"LM/IISADMIN/EXTENSIONS/DCOMCLSIDS") >= 0
          && (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 144LL))(ppv, v9) >= 0
          && (v9 = 0,
              (*(int (__fastcall **)(LPVOID, _QWORD, const wchar_t *, __int64, int, unsigned int *))(*(_QWORD *)ppv + 136LL))(
                ppv,
                0,
                L"LM/IISADMIN/EXTENSIONS/DCOMCLSIDS",
                3,
                2000,
                &v10) >= 0) )
        {
          *((_QWORD *)&v15 + 1) = v19;
          *((_QWORD *)&v14 + 1) = 0x500000001LL;
          LODWORD(v15) = 2 * v1 + 2;
          *(_QWORD *)&v14 = 1028;
          (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *))(*(_QWORD *)ppv + 72LL))(ppv, v10, 0, &v14);
        }
      }
    }
  }
LABEL_21:
  v8 = ppv;
  if ( ppv )
  {
    if ( v10 )
    {
      (*(void (**)(void))(*(_QWORD *)ppv + 144LL))();
      v8 = ppv;
      v10 = 0;
    }
    if ( v9 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 144LL))(v8);
      v8 = ppv;
      v9 = 0;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    ppv = 0;
  }
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  BUFFER::~BUFFER((BUFFER *)v18);
}

```

## disassembly

```asm
0x180003118  push    rbp
0x18000311a  push    rbx
0x18000311b  push    rsi
0x18000311c  push    rdi
0x18000311d  push    r14
0x18000311f  push    r15
0x180003121  lea     rbp, [rsp-2Fh]
0x180003126  sub     rsp, 0F8h
0x18000312d  mov     rax, cs:__security_cookie
0x180003134  xor     rax, rsp
0x180003137  mov     [rbp+57h+var_40], rax
0x18000313b  xor     r15d, r15d
0x18000313e  mov     [rbp+57h+var_58], 20h ; ' '
0x180003145  xorps   xmm0, xmm0
0x180003148  mov     [rsp+120h+var_D8], r15
0x18000314d  xor     eax, eax
0x18000314f  mov     [rsp+120h+var_E0], r15d
0x180003154  mov     [rbp+57h+var_A0], rax
0x180003158  lea     rdx, [rbp+57h+ppMalloc]; ppMalloc
0x18000315c  lea     rax, [rbp+57h+var_80]
0x180003160  mov     [rsp+120h+var_DC], r15d
0x180003165  lea     ecx, [r15+1]; dwMemContext
0x180003169  mov     [rbp+57h+var_80], r15
0x18000316d  movups  [rbp+57h+var_50], xmm0
0x180003171  mov     [rbp+57h+var_60], rax
0x180003175  movups  [rbp+57h+var_C0], xmm0
0x180003179  mov     [rbp+57h+var_54], 100h
0x18000317f  movups  [rbp+57h+var_B0], xmm0
0x180003183  mov     [rbp+57h+ppMalloc], r15
0x180003187  call    cs:__imp_CoGetMalloc
0x18000318d  test    eax, eax
0x18000318f  js      loc_1800033F0
0x180003195  mov     rbx, cs:?g_piaecHead@@3PEAU_IADMEXT_CONTAINER@@EA; _IADMEXT_CONTAINER * g_piaecHead
0x18000319c  mov     edi, r15d
0x18000319f  jmp     loc_18000326D
0x1800031a4  mov     esi, r15d
0x1800031a7  mov     rcx, [rbx]
0x1800031aa  lea     rdx, [rbp+57h+var_50]
0x1800031ae  mov     r8d, esi
0x1800031b1  mov     rax, [rcx]
0x1800031b4  mov     rax, [rax+20h]
0x1800031b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bd  cmp     eax, 80070103h
0x1800031c2  jz      loc_180003269
0x1800031c8  test    eax, eax
0x1800031ca  js      loc_1800033F0
0x1800031d0  movaps  xmm0, [rbp+57h+var_50]
0x1800031d4  lea     edx, ds:4Eh[rdi*2]
0x1800031db  mov     r14, [rbp+57h+ppMalloc]
0x1800031df  lea     rcx, [rbp+57h+var_80]
0x1800031e3  movdqa  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x1800031e8  mov     [rbp+57h+lpsz], r15
0x1800031ec  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800031f2  test    al, al
0x1800031f4  jz      loc_1800033F0
0x1800031fa  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800031fe  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180003202  call    cs:__imp_StringFromCLSID
0x180003208  test    eax, eax
0x18000320a  js      short loc_180003262
0x18000320c  mov     rax, [rbp+57h+lpsz]
0x180003210  mov     rdx, [rbp+57h+var_60]
0x180003214  mov     r8d, edi
0x180003217  add     edi, 27h ; '''
0x18000321a  movups  xmm0, xmmword ptr [rax]
0x18000321d  movups  xmmword ptr [rdx+r8*2], xmm0
0x180003222  movups  xmm1, xmmword ptr [rax+10h]
0x180003226  movups  xmmword ptr [rdx+r8*2+10h], xmm1
0x18000322c  movups  xmm0, xmmword ptr [rax+20h]
0x180003230  movups  xmmword ptr [rdx+r8*2+20h], xmm0
0x180003236  movups  xmm1, xmmword ptr [rax+30h]
0x18000323a  movups  xmmword ptr [rdx+r8*2+30h], xmm1
0x180003240  movups  xmm0, xmmword ptr [rax+3Eh]
0x180003244  movups  xmmword ptr [rdx+r8*2+3Eh], xmm0
0x18000324a  test    r14, r14
0x18000324d  jz      short loc_180003262
0x18000324f  mov     rax, [r14]
0x180003252  mov     rcx, r14
0x180003255  mov     rdx, [rbp+57h+lpsz]
0x180003259  mov     rax, [rax+28h]
0x18000325d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003262  inc     esi
0x180003264  jmp     loc_1800031A7
0x180003269  mov     rbx, [rbx+8]
0x18000326d  test    rbx, rbx
0x180003270  jnz     loc_1800031A4
0x180003276  lea     ebx, ds:2[rdi*2]
0x18000327d  mov     edx, ebx
0x18000327f  lea     rcx, [rbp+57h+var_80]
0x180003283  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003289  test    al, al
0x18000328b  jz      loc_1800033F0
0x180003291  mov     rax, [rbp+57h+var_60]
0x180003295  lea     r9, IID_IMSAdminBase_W; riid
0x18000329c  mov     edx, edi
0x18000329e  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x1800032a5  mov     [rax+rdx*2], r15w
0x1800032aa  xor     edx, edx; pUnkOuter
0x1800032ac  lea     rax, [rsp+120h+var_D8]
0x1800032b1  mov     [rsp+120h+ppv], rax; ppv
0x1800032b6  lea     r8d, [rdx+15h]; dwClsContext
0x1800032ba  call    cs:__imp_CoCreateInstance
0x1800032c0  test    eax, eax
0x1800032c2  js      loc_1800033F0
0x1800032c8  mov     rcx, [rsp+120h+var_D8]
0x1800032cd  lea     rdx, [rsp+120h+var_DC]
0x1800032d2  mov     [rsp+120h+var_F8], rdx
0x1800032d7  lea     rdi, aLmIisadminExte; "LM/IISADMIN/EXTENSIONS/DCOMCLSIDS"
0x1800032de  mov     r14d, 3
0x1800032e4  mov     esi, 7D0h
0x1800032e9  mov     r9d, r14d
0x1800032ec  mov     dword ptr [rsp+120h+ppv], esi
0x1800032f0  mov     rax, [rcx]
0x1800032f3  mov     r8, rdi
0x1800032f6  xor     edx, edx
0x1800032f8  mov     rax, [rax+88h]
0x1800032ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003304  cmp     eax, 80070003h
0x180003309  jnz     loc_1800033B0
0x18000330f  mov     rcx, [rsp+120h+var_D8]
0x180003314  lea     rdx, [rsp+120h+var_E0]
0x180003319  mov     [rsp+120h+var_F8], rdx
0x18000331e  mov     r9d, r14d
0x180003321  xor     r8d, r8d
0x180003324  mov     dword ptr [rsp+120h+ppv], esi
0x180003328  xor     edx, edx
0x18000332a  mov     rax, [rcx]
0x18000332d  mov     rax, [rax+88h]
0x180003334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003339  test    eax, eax
0x18000333b  js      loc_1800033F0
0x180003341  mov     rcx, [rsp+120h+var_D8]
0x180003346  mov     r8, rdi
0x180003349  mov     edx, [rsp+120h+var_E0]
0x18000334d  mov     rax, [rcx]
0x180003350  mov     rax, [rax+18h]
0x180003354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003359  test    eax, eax
0x18000335b  js      loc_1800033F0
0x180003361  mov     rcx, [rsp+120h+var_D8]
0x180003366  mov     edx, [rsp+120h+var_E0]
0x18000336a  mov     rax, [rcx]
0x18000336d  mov     rax, [rax+90h]
0x180003374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003379  test    eax, eax
0x18000337b  js      short loc_1800033F0
0x18000337d  mov     rcx, [rsp+120h+var_D8]
0x180003382  lea     rdx, [rsp+120h+var_DC]
0x180003387  mov     [rsp+120h+var_F8], rdx
0x18000338c  mov     r9d, r14d
0x18000338f  mov     [rsp+120h+var_E0], r15d
0x180003394  mov     r8, rdi
0x180003397  xor     edx, edx
0x180003399  mov     dword ptr [rsp+120h+ppv], esi
0x18000339d  mov     rax, [rcx]
0x1800033a0  mov     rax, [rax+88h]
0x1800033a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ac  test    eax, eax
0x1800033ae  js      short loc_1800033F0
0x1800033b0  mov     rax, [rbp+57h+var_60]
0x1800033b4  lea     r9, [rbp+57h+var_C0]
0x1800033b8  mov     rcx, [rsp+120h+var_D8]
0x1800033bd  xor     r8d, r8d
0x1800033c0  mov     edx, [rsp+120h+var_DC]
0x1800033c4  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1800033c8  mov     dword ptr [rbp+57h+var_C0+4], r15d
0x1800033cc  mov     dword ptr [rbp+57h+var_C0+8], 1
0x1800033d3  mov     dword ptr [rbp+57h+var_C0+0Ch], 5
0x1800033da  mov     dword ptr [rbp+57h+var_B0], ebx
0x1800033dd  mov     dword ptr [rbp+57h+var_C0], 404h
0x1800033e4  mov     rax, [rcx]
0x1800033e7  mov     rax, [rax+48h]
0x1800033eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f0  mov     rcx, [rsp+120h+var_D8]
0x1800033f5  test    rcx, rcx
0x1800033f8  jz      short loc_18000344D
0x1800033fa  mov     edx, [rsp+120h+var_DC]
0x1800033fe  test    edx, edx
0x180003400  jz      short loc_18000341B
0x180003402  mov     rax, [rcx]
0x180003405  mov     rax, [rax+90h]
0x18000340c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003411  mov     rcx, [rsp+120h+var_D8]
0x180003416  mov     [rsp+120h+var_DC], r15d
0x18000341b  mov     edx, [rsp+120h+var_E0]
0x18000341f  test    edx, edx
0x180003421  jz      short loc_18000343C
0x180003423  mov     rax, [rcx]
0x180003426  mov     rax, [rax+90h]
0x18000342d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003432  mov     rcx, [rsp+120h+var_D8]
0x180003437  mov     [rsp+120h+var_E0], r15d
0x18000343c  mov     rax, [rcx]
0x18000343f  mov     rax, [rax+10h]
0x180003443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003448  mov     [rsp+120h+var_D8], r15
0x18000344d  mov     rcx, [rbp+57h+ppMalloc]
0x180003451  test    rcx, rcx
0x180003454  jz      short loc_180003462
0x180003456  mov     rax, [rcx]
0x180003459  mov     rax, [rax+10h]
0x18000345d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003462  lea     rcx, [rbp+57h+var_80]
0x180003466  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000346c  mov     rcx, [rbp+57h+var_40]
0x180003470  xor     rcx, rsp; StackCookie
0x180003473  call    __security_check_cookie
0x180003478  add     rsp, 0F8h
0x18000347f  pop     r15
0x180003481  pop     r14
0x180003483  pop     rdi
0x180003484  pop     rsi
0x180003485  pop     rbx
0x180003486  pop     rbp
0x180003487  retn
```
