# LsaDbpGetDelegatedTDOCount(ulong,void *,ulong *)

- ea: `0x180036330`
- end: `0x180036628`
- name: `?LsaDbpGetDelegatedTDOCount@@YAJKPEAXPEAK@Z`
- size: `760`
- prototype: `int(unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035fdc`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18001182c`
- `0x180011d6c`
- `0x18001f3b4`
- `0x18001f5c0`
- `0x18001fbcc`
- `0x180036330`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180036433`
- `ntdll!RtlLengthSid` at `0x180036433`
- `NTDSA!THClearErrors` at `0x1800365da`
- `NTDSA!THClearErrors` at `0x1800365da`
- `NTDSA!SampSetDsa` at `0x18003656c`
- `NTDSA!SampSetDsa` at `0x18003656c`
- `NTDSA!DirSearch` at `0x180036586`
- `NTDSA!DirSearch` at `0x180036586`

## pseudocode

```c
__int64 __fastcall LsaDbpGetDelegatedTDOCount(char a1, void *a2, unsigned int *a3)
{
  int inited; // ebx
  __int64 v7; // r8
  unsigned int v8; // edi
  int v9; // r14d
  __int16 v10; // cx
  __int64 v11; // rcx
  unsigned int v12; // edx
  unsigned int v13; // ebx
  _BYTE v15[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  int v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+48h] [rbp-B8h]
  _DWORD v21[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[80]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v24; // [rsp+C0h] [rbp-40h]
  _BYTE ***v25; // [rsp+C8h] [rbp-38h]
  struct _DSNAME *v26; // [rsp+F0h] [rbp-10h] BYREF
  char v27; // [rsp+F8h] [rbp-8h]
  int v28; // [rsp+FCh] [rbp-4h]
  _BYTE *v29; // [rsp+100h] [rbp+0h]
  int v30; // [rsp+108h] [rbp+8h]
  __int128 *v31; // [rsp+110h] [rbp+10h]
  _BYTE v32[8]; // [rsp+128h] [rbp+28h] BYREF
  int v33; // [rsp+130h] [rbp+30h]
  int v34; // [rsp+158h] [rbp+58h]
  __int64 v35; // [rsp+180h] [rbp+80h]
  unsigned int v36; // [rsp+188h] [rbp+88h]
  _BYTE **v37; // [rsp+200h] [rbp+100h] BYREF
  char v38; // [rsp+208h] [rbp+108h]
  char v39; // [rsp+210h] [rbp+110h]
  int v40; // [rsp+218h] [rbp+118h]
  ULONG v41; // [rsp+220h] [rbp+120h]
  void *v42; // [rsp+228h] [rbp+128h]
  int v43; // [rsp+238h] [rbp+138h]
  _BYTE *v44; // [rsp+278h] [rbp+178h] BYREF
  char v45; // [rsp+280h] [rbp+180h]
  char v46; // [rsp+288h] [rbp+188h]
  int v47; // [rsp+290h] [rbp+190h]
  int v48; // [rsp+298h] [rbp+198h]
  int *v49; // [rsp+2A0h] [rbp+1A0h]
  _BYTE v50[24]; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v51; // [rsp+308h] [rbp+208h]
  int v52; // [rsp+310h] [rbp+210h]
  int *v53; // [rsp+318h] [rbp+218h]

  memset_0(v23, 0, 0x78u);
  v16 = 0;
  v18 = 0;
  v15[0] = 0;
  v21[0] = 589826;
  v19 = 0;
  v21[2] = 0;
  v20 = 0;
  v22 = 0;
  v17 = 1;
  memset_0(&v26, 0, 0x108u);
  inited = LsaDbpDsInitAllocAsNeededEx(50331648, 0, v15);
  if ( inited >= 0 )
  {
    v16 = 655394;
    v8 = 0;
    memset_0(&v37, 0, 0x168u);
    memset_0(v23, 0, 0x78u);
    v38 = 73;
    if ( a2 )
    {
      v39 = 0;
      v40 = 591234;
      v41 = RtlLengthSid(a2);
      v42 = a2;
    }
    else
    {
      v39 = 7;
      v43 = 591234;
    }
    v45 = 73;
    v37 = &v44;
    v49 = &v16;
    v46 = 0;
    v47 = 0;
    v48 = 4;
    v9 = a1 & 1;
    if ( v9 )
    {
      v52 = 4;
      v44 = v50;
      v10 = 3;
      v50[8] = 73;
      v53 = &v17;
      v26 = LsaDbDsStateInfo;
      v27 = 2;
      v50[16] = 0;
      v51 = 131120;
    }
    else
    {
      v10 = 2;
      v26 = qword_180047010;
      v27 = 1;
    }
    v24 = v10;
    v25 = &v37;
    v23[8] = 65;
    v29 = v23;
    v28 = 1;
    v31 = &v19;
    *(_QWORD *)&v20 = v21;
    v30 = 0;
    LOBYTE(v19) = 76;
    DWORD2(v19) = 1;
    BYTE8(v20) = 86;
    LsaDbpDsInitializeStdCommArg((struct _COMMARG *)v32, 0);
    if ( v9 )
      v33 |= 0x20u;
    v36 |= 1u;
    LOBYTE(v11) = 1;
    v34 = 100;
    SampSetDsa(v11);
    LOBYTE(v12) = v36;
    while ( (v12 & 1) != 0 )
    {
      v13 = DirSearch(&v26, &v18);
      LsaDbpDsContinueTransaction();
      if ( !v18 )
      {
        THClearErrors();
        inited = -1073741801;
        goto LABEL_17;
      }
      inited = LsaDbpDsMapDsReturnToStatusEx(v13, (struct _COMMRES *)(v18 + 96));
      if ( inited < 0 )
        goto LABEL_17;
      v8 += *(_DWORD *)(v18 + 16);
      v12 = v36 & 0xFFFFFFFE | *(_DWORD *)(v18 + 120) & 1;
      v36 = v12;
      v35 = *(_QWORD *)(v18 + 112);
    }
    *a3 = v8;
  }
LABEL_17:
  LOBYTE(v7) = v15[0];
  if ( v15[0] )
    LsaDbpDsDeleteAllocAsNeededEx(50331648, 0, v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180036330  mov     [rsp-8+arg_0], rbx
0x180036335  push    rbp
0x180036336  push    rsi
0x180036337  push    rdi
0x180036338  push    r14
0x18003633a  push    r15
0x18003633c  lea     rbp, [rsp-280h]
0x180036344  sub     rsp, 380h
0x18003634b  mov     rax, cs:__security_cookie
0x180036352  xor     rax, rsp
0x180036355  mov     [rbp+2A0h+var_30], rax
0x18003635c  mov     rsi, rdx
0x18003635f  mov     r15, r8
0x180036362  xor     edx, edx; Val
0x180036364  mov     r14d, ecx
0x180036367  lea     rcx, [rsp+3A0h+var_330]; void *
0x18003636c  lea     r8d, [rdx+78h]; Size
0x180036370  call    memset_0
0x180036375  xorps   xmm0, xmm0
0x180036378  mov     [rsp+3A0h+var_37C], 0
0x180036380  xor     edx, edx; Val
0x180036382  mov     [rsp+3A0h+var_370], 0
0x18003638b  mov     r8d, 108h; Size
0x180036391  mov     [rsp+3A0h+var_380], 0
0x180036396  lea     rcx, [rbp+2A0h+var_2B0]; void *
0x18003639a  mov     [rsp+3A0h+var_348], 90002h
0x1800363a2  movups  [rsp+3A0h+var_368], xmm0
0x1800363a7  mov     [rsp+3A0h+var_340], 0
0x1800363af  movups  [rsp+3A0h+var_358], xmm0
0x1800363b4  mov     [rsp+3A0h+var_338], 0
0x1800363bd  mov     [rsp+3A0h+var_378], 1
0x1800363c5  call    memset_0
0x1800363ca  lea     r8, [rsp+3A0h+var_380]
0x1800363cf  xor     edx, edx
0x1800363d1  mov     ecx, 3000000h
0x1800363d6  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x1800363db  mov     ebx, eax
0x1800363dd  test    eax, eax
0x1800363df  js      loc_1800365EA
0x1800363e5  xor     edx, edx; Val
0x1800363e7  mov     [rsp+3A0h+var_37C], 0A0022h
0x1800363ef  mov     r8d, 168h; Size
0x1800363f5  lea     rcx, [rbp+2A0h+var_1A0]; void *
0x1800363fc  xor     edi, edi
0x1800363fe  call    memset_0
0x180036403  xor     edx, edx; Val
0x180036405  lea     r8d, [rdi+78h]; Size
0x180036409  lea     rcx, [rsp+3A0h+var_330]; void *
0x18003640e  call    memset_0
0x180036413  mov     [rbp+2A0h+var_198], 49h ; 'I'
0x18003641a  test    rsi, rsi
0x18003641d  jz      short loc_180036448
0x18003641f  mov     rcx, rsi; Sid
0x180036422  mov     [rbp+2A0h+var_190], dil
0x180036429  mov     [rbp+2A0h+var_188], 90582h
0x180036433  call    cs:__imp_RtlLengthSid
0x180036439  mov     [rbp+2A0h+var_180], eax
0x18003643f  mov     [rbp+2A0h+var_178], rsi
0x180036446  jmp     short loc_180036459
0x180036448  mov     [rbp+2A0h+var_190], 7
0x18003644f  mov     [rbp+2A0h+var_168], 90582h
0x180036459  mov     [rbp+2A0h+var_120], 49h ; 'I'
0x180036460  lea     rax, [rbp+2A0h+var_128]
0x180036467  mov     [rbp+2A0h+var_1A0], rax
0x18003646e  lea     rax, [rsp+3A0h+var_37C]
0x180036473  mov     [rbp+2A0h+var_100], rax
0x18003647a  mov     ecx, 4
0x18003647f  mov     [rbp+2A0h+var_118], dil
0x180036486  mov     [rbp+2A0h+var_110], edi
0x18003648c  mov     [rbp+2A0h+var_108], ecx
0x180036492  and     r14d, 1
0x180036496  jz      short loc_1800364E8
0x180036498  lea     rax, [rbp+2A0h+var_B0]
0x18003649f  mov     [rbp+2A0h+var_90], ecx
0x1800364a5  mov     [rbp+2A0h+var_128], rax
0x1800364ac  mov     ecx, 3
0x1800364b1  lea     rax, [rsp+3A0h+var_378]
0x1800364b6  mov     [rbp+2A0h+var_A8], 49h ; 'I'
0x1800364bd  mov     [rbp+2A0h+var_88], rax
0x1800364c4  mov     rax, cs:?LsaDbDsStateInfo@@3U_LSADS_DS_STATE_INFO@@A; _LSADS_DS_STATE_INFO LsaDbDsStateInfo
0x1800364cb  mov     [rbp+2A0h+var_2B0], rax
0x1800364cf  lea     eax, [rcx-1]
0x1800364d2  mov     [rbp+2A0h+var_2A8], al
0x1800364d5  mov     [rbp+2A0h+var_A0], dil
0x1800364dc  mov     [rbp+2A0h+var_98], 20030h
0x1800364e6  jmp     short loc_1800364FC
0x1800364e8  mov     rax, cs:qword_180047010
0x1800364ef  mov     ecx, 2
0x1800364f4  mov     [rbp+2A0h+var_2B0], rax
0x1800364f8  mov     [rbp+2A0h+var_2A8], 1
0x1800364fc  lea     rax, [rbp+2A0h+var_1A0]
0x180036503  mov     [rbp+2A0h+var_2E0], cx
0x180036507  mov     [rbp+2A0h+var_2D8], rax
0x18003650b  lea     rcx, [rbp+2A0h+var_278]; struct _COMMARG *
0x18003650f  lea     rax, [rsp+3A0h+var_330]
0x180036514  mov     [rsp+3A0h+var_328], 41h ; 'A'
0x180036519  mov     [rbp+2A0h+var_2A0], rax
0x18003651d  xor     edx, edx; unsigned int
0x18003651f  lea     rax, [rsp+3A0h+var_368]
0x180036524  mov     [rbp+2A0h+var_2A4], 1
0x18003652b  mov     [rbp+2A0h+var_290], rax
0x18003652f  lea     rax, [rsp+3A0h+var_348]
0x180036534  mov     qword ptr [rsp+3A0h+var_358], rax
0x180036539  mov     [rbp+2A0h+var_298], edi
0x18003653c  mov     byte ptr [rsp+3A0h+var_368], 4Ch ; 'L'
0x180036541  mov     dword ptr [rsp+3A0h+var_368+8], 1
0x180036549  mov     byte ptr [rsp+3A0h+var_358+8], 56h ; 'V'
0x18003654e  call    ?LsaDbpDsInitializeStdCommArg@@YAXPEAU_COMMARG@@K@Z; LsaDbpDsInitializeStdCommArg(_COMMARG *,ulong)
0x180036553  test    r14d, r14d
0x180036556  jz      short loc_18003655C
0x180036558  or      [rbp+2A0h+var_270], 20h
0x18003655c  or      [rbp+2A0h+var_218], 1
0x180036563  mov     cl, 1
0x180036565  mov     [rbp+2A0h+var_248], 64h ; 'd'
0x18003656c  call    cs:__imp_SampSetDsa
0x180036572  mov     edx, [rbp+2A0h+var_218]
0x180036578  test    dl, 1
0x18003657b  jz      short loc_1800365E7
0x18003657d  lea     rdx, [rsp+3A0h+var_370]
0x180036582  lea     rcx, [rbp+2A0h+var_2B0]
0x180036586  call    cs:__imp_DirSearch
0x18003658c  mov     ebx, eax
0x18003658e  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x180036593  mov     rdx, [rsp+3A0h+var_370]
0x180036598  test    rdx, rdx
0x18003659b  jz      short loc_1800365DA
0x18003659d  add     rdx, 60h ; '`'; struct _COMMRES *
0x1800365a1  mov     ecx, ebx; unsigned int
0x1800365a3  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x1800365a8  mov     ebx, eax
0x1800365aa  test    eax, eax
0x1800365ac  js      short loc_1800365EA
0x1800365ae  mov     rcx, [rsp+3A0h+var_370]
0x1800365b3  mov     eax, [rbp+2A0h+var_218]
0x1800365b9  and     eax, 0FFFFFFFEh
0x1800365bc  mov     edx, [rcx+78h]
0x1800365bf  add     edi, [rcx+10h]
0x1800365c2  and     edx, 1
0x1800365c5  or      edx, eax
0x1800365c7  mov     [rbp+2A0h+var_218], edx
0x1800365cd  mov     rax, [rcx+70h]
0x1800365d1  mov     [rbp+2A0h+var_220], rax
0x1800365d8  jmp     short loc_180036578
0x1800365da  call    cs:__imp_THClearErrors
0x1800365e0  mov     ebx, 0C0000017h
0x1800365e5  jmp     short loc_1800365EA
0x1800365e7  mov     [r15], edi
0x1800365ea  mov     r8b, [rsp+3A0h+var_380]
0x1800365ef  test    r8b, r8b
0x1800365f2  jz      short loc_180036600
0x1800365f4  xor     edx, edx
0x1800365f6  mov     ecx, 3000000h
0x1800365fb  call    ?LsaDbpDsDeleteAllocAsNeededEx@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsaDbpDsDeleteAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x180036600  mov     eax, ebx
0x180036602  mov     rcx, [rbp+2A0h+var_30]
0x180036609  xor     rcx, rsp; StackCookie
0x18003660c  call    __security_check_cookie
0x180036611  mov     rbx, [rsp+3A0h+arg_0]
0x180036619  add     rsp, 380h
0x180036620  pop     r15
0x180036622  pop     r14
0x180036624  pop     rdi
0x180036625  pop     rsi
0x180036626  pop     rbp
0x180036627  retn
```
