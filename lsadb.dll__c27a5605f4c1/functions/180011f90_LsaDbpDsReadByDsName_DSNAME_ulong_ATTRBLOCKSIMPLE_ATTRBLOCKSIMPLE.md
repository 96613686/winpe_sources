# LsaDbpDsReadByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)

- ea: `0x180011f90`
- end: `0x180012117`
- name: `?LsaDbpDsReadByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@1@Z`
- size: `391`
- prototype: `int(struct _DSNAME *, unsigned int, struct _ATTRBLOCKSIMPLE *, struct _ATTRBLOCKSIMPLE *)`
- caller_count: `17`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c4f0`
- `0x1800101b0`
- `0x180011f28`
- `0x180012120`
- `0x180014358`
- `0x180014a40`
- `0x1800194a8`
- `0x180020018`
- `0x18002051c`
- `0x1800206c0`
- `0x18002cff0`
- `0x18002d240`
- `0x18002db90`
- `0x18002de10`
- `0x18002e200`
- `0x18002f020`
- `0x180036630`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180010d48`
- `0x18001182c`
- `0x180011d6c`
- `0x180011f90`
- `0x18001f3b4`

## import_xrefs

- `NTDSA!THQuery` at `0x180011fe4`
- `NTDSA!THQuery` at `0x180011fe4`
- `NTDSA!THClearErrors` at `0x1800120c6`
- `NTDSA!THClearErrors` at `0x1800120c6`
- `NTDSA!DirRead` at `0x1800120b6`
- `NTDSA!DirRead` at `0x1800120b6`

## pseudocode

```c
__int64 __fastcall LsaDbpDsReadByDsName(
        struct _DSNAME *a1,
        unsigned int a2,
        struct _ATTRBLOCKSIMPLE *a3,
        struct _ATTRBLOCKSIMPLE *a4)
{
  __int64 v9; // r8
  int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v16; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v17; // [rsp+38h] [rbp-C8h]
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[200]; // [rsp+68h] [rbp-98h] BYREF

  v16 = 0;
  v17 = 0;
  memset_0(v18, 0, 0xE0u);
  v15 = 0;
  if ( !(unsigned int)THQuery() )
    return 3221225756LL;
  LOBYTE(v16) = 76;
  BYTE8(v17) = 86;
  memset_0(v19, 0, 0xD0u);
  v18[0] = a1;
  v18[1] = &v16;
  LsaDbpDsInitializeStdCommArg((struct _COMMARG *)v20, a2);
  *(_QWORD *)&v17 = LsaDbpDsAlloc(24 * *(_DWORD *)a3);
  v9 = v17;
  if ( (_QWORD)v17 )
  {
    v11 = 0;
    DWORD2(v16) = *(_DWORD *)a3;
    if ( DWORD2(v16) )
    {
      while ( 1 )
      {
        v12 = 3 * v11;
        v11 = (unsigned int)(v11 + 1);
        *(_DWORD *)(v9 + 8 * v12) = *(_DWORD *)(*((_QWORD *)a3 + 1) + 8 * v12);
        *(_DWORD *)(v17 + 8 * v12 + 8) = *(_DWORD *)(*((_QWORD *)a3 + 1) + 8 * v12 + 8);
        *(_QWORD *)(v17 + 8 * v12 + 16) = *(_QWORD *)(*((_QWORD *)a3 + 1) + 8 * v12 + 16);
        LOBYTE(v16) = 76;
        BYTE8(v17) = 86;
        if ( (unsigned int)v11 >= *(_DWORD *)a3 )
          break;
        v9 = v17;
      }
    }
    v13 = DirRead(v18, &v15, v9, v11);
    if ( v15 )
    {
      v10 = LsaDbpDsMapDsReturnToStatusEx(v13, (struct _COMMRES *)(v15 + 48));
    }
    else
    {
      THClearErrors();
      v10 = -1073741801;
    }
    LsaDbpDsContinueTransaction();
    if ( v10 >= 0 )
    {
      v14 = v15;
      *(_DWORD *)a4 = *(_DWORD *)(v15 + 16);
      *((_QWORD *)a4 + 1) = *(_QWORD *)(v14 + 24);
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011f90  push    rbp
0x180011f92  push    rbx
0x180011f93  push    rsi
0x180011f94  push    rdi
0x180011f95  push    r14
0x180011f97  lea     rbp, [rsp-40h]
0x180011f9c  sub     rsp, 140h
0x180011fa3  mov     rax, cs:__security_cookie
0x180011faa  xor     rax, rsp
0x180011fad  mov     [rbp+60h+var_30], rax
0x180011fb1  xorps   xmm0, xmm0
0x180011fb4  mov     rbx, r8
0x180011fb7  mov     esi, edx
0x180011fb9  mov     r14, rcx
0x180011fbc  xor     edx, edx; Val
0x180011fbe  lea     rcx, [rsp+160h+var_110]; void *
0x180011fc3  mov     r8d, 0E0h; Size
0x180011fc9  mov     rdi, r9
0x180011fcc  movups  [rsp+160h+var_138], xmm0
0x180011fd1  movups  [rsp+160h+var_128], xmm0
0x180011fd6  call    memset_0
0x180011fdb  mov     [rsp+160h+var_140], 0
0x180011fe4  call    cs:__imp_THQuery
0x180011fea  test    eax, eax
0x180011fec  jnz     short loc_180011FF8
0x180011fee  mov     eax, 0C000011Ch
0x180011ff3  jmp     loc_1800120FD
0x180011ff8  xor     edx, edx; Val
0x180011ffa  mov     byte ptr [rsp+160h+var_138], 4Ch ; 'L'
0x180011fff  mov     r8d, 0D0h; Size
0x180012005  mov     byte ptr [rsp+160h+var_128+8], 56h ; 'V'
0x18001200a  lea     rcx, [rsp+160h+var_100]; void *
0x18001200f  call    memset_0
0x180012014  lea     rax, [rsp+160h+var_138]
0x180012019  mov     [rsp+160h+var_110], r14
0x18001201e  mov     edx, esi; unsigned int
0x180012020  mov     [rsp+160h+var_108], rax
0x180012025  lea     rcx, [rsp+160h+var_F8]; struct _COMMARG *
0x18001202a  call    ?LsaDbpDsInitializeStdCommArg@@YAXPEAU_COMMARG@@K@Z; LsaDbpDsInitializeStdCommArg(_COMMARG *,ulong)
0x18001202f  mov     eax, [rbx]
0x180012031  lea     ecx, [rax+rax*2]
0x180012034  shl     ecx, 3; unsigned int
0x180012037  call    ?LsaDbpDsAlloc@@YAPEAXK@Z; LsaDbpDsAlloc(ulong)
0x18001203c  mov     qword ptr [rsp+160h+var_128], rax
0x180012041  mov     r8, rax
0x180012044  test    rax, rax
0x180012047  jnz     short loc_180012053
0x180012049  mov     ebx, 0C0000017h
0x18001204e  jmp     loc_1800120FB
0x180012053  mov     eax, [rbx]
0x180012055  xor     r9d, r9d
0x180012058  mov     dword ptr [rsp+160h+var_138+8], eax
0x18001205c  test    eax, eax
0x18001205e  jz      short loc_1800120AC
0x180012060  mov     rax, [rbx+8]
0x180012064  lea     rdx, [r9+r9*2]
0x180012068  inc     r9d
0x18001206b  mov     ecx, [rax+rdx*8]
0x18001206e  mov     [r8+rdx*8], ecx
0x180012072  mov     rax, [rbx+8]
0x180012076  mov     ecx, [rax+rdx*8+8]
0x18001207a  mov     rax, qword ptr [rsp+160h+var_128]
0x18001207f  mov     [rax+rdx*8+8], ecx
0x180012083  mov     rax, [rbx+8]
0x180012087  mov     rcx, [rax+rdx*8+10h]
0x18001208c  mov     rax, qword ptr [rsp+160h+var_128]
0x180012091  mov     [rax+rdx*8+10h], rcx
0x180012096  mov     byte ptr [rsp+160h+var_138], 4Ch ; 'L'
0x18001209b  mov     byte ptr [rsp+160h+var_128+8], 56h ; 'V'
0x1800120a0  cmp     r9d, [rbx]
0x1800120a3  jnb     short loc_1800120AC
0x1800120a5  mov     r8, qword ptr [rsp+160h+var_128]
0x1800120aa  jmp     short loc_180012060
0x1800120ac  lea     rdx, [rsp+160h+var_140]
0x1800120b1  lea     rcx, [rsp+160h+var_110]
0x1800120b6  call    cs:__imp_DirRead
0x1800120bc  mov     rdx, [rsp+160h+var_140]
0x1800120c1  test    rdx, rdx
0x1800120c4  jnz     short loc_1800120D3
0x1800120c6  call    cs:__imp_THClearErrors
0x1800120cc  mov     ebx, 0C0000017h
0x1800120d1  jmp     short loc_1800120E0
0x1800120d3  add     rdx, 30h ; '0'; struct _COMMRES *
0x1800120d7  mov     ecx, eax; unsigned int
0x1800120d9  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x1800120de  mov     ebx, eax
0x1800120e0  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x1800120e5  test    ebx, ebx
0x1800120e7  js      short loc_1800120FB
0x1800120e9  mov     rdx, [rsp+160h+var_140]
0x1800120ee  mov     ecx, [rdx+10h]
0x1800120f1  mov     [rdi], ecx
0x1800120f3  mov     rcx, [rdx+18h]
0x1800120f7  mov     [rdi+8], rcx
0x1800120fb  mov     eax, ebx
0x1800120fd  mov     rcx, [rbp+60h+var_30]
0x180012101  xor     rcx, rsp; StackCookie
0x180012104  call    __security_check_cookie
0x180012109  add     rsp, 140h
0x180012110  pop     r14
0x180012112  pop     rdi
0x180012113  pop     rsi
0x180012114  pop     rbx
0x180012115  pop     rbp
0x180012116  retn
```
