# CASCLOG::WriteFileLogRecord(_iobuf *,ILogScripting *,bool)

- ea: `0x18000cb70`
- end: `0x18000d090`
- name: `?WriteFileLogRecord@CASCLOG@@MEAAJPEAU_iobuf@@PEAUILogScripting@@_N@Z`
- size: `1312`
- prototype: `__int64 __fastcall(CASCLOG *__hidden this, struct _iobuf *, struct ILogScripting *, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1800022a8`
- `0x18000cb70`
- `0x18000eca0`
- `0x18000ed30`
- `0x180010010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000ceab`
- `msvcrt!sprintf_s` at `0x18000d04e`
- `msvcrt!sprintf_s` at `0x18000ceab`
- `msvcrt!sprintf_s` at `0x18000d04e`
- `msvcrt!fprintf` at `0x18000d065`
- `msvcrt!fprintf` at `0x18000d065`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x18000ce0d`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x18000ce0d`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18000cdea`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18000cdea`

## pseudocode

```c
__int64 __fastcall CASCLOG::WriteFileLogRecord(CASCLOG *this, struct _iobuf *a2, struct ILogScripting *a3)
{
  unsigned int v6; // esi
  __int64 v7; // rax
  int (__fastcall *v8)(struct ILogScripting *, __int128 *); // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r9
  unsigned int v14; // eax
  unsigned int v16; // r14d
  char *v17; // rcx
  unsigned int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // rcx
  int v21; // r14d
  char *v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v25; // r14d
  char *v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // rcx
  int v29; // r14d
  char *v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // rcx
  int v33; // r14d
  char *v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r9
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h]
  __int128 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int128 v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h]
  __int128 v44; // [rsp+98h] [rbp-68h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  __int128 v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h]
  unsigned int Value[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h]
  unsigned int v50[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-10h]
  unsigned int v52[4]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+108h] [rbp+8h]
  unsigned int v54[4]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v55; // [rsp+120h] [rbp+20h]
  unsigned int v56[4]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v57; // [rsp+138h] [rbp+38h]
  __int128 v58; // [rsp+140h] [rbp+40h] BYREF
  __int64 v59; // [rsp+150h] [rbp+50h]
  __int128 v60; // [rsp+158h] [rbp+58h] BYREF
  __int64 v61; // [rsp+168h] [rbp+68h]
  __int128 v62; // [rsp+170h] [rbp+70h] BYREF
  __int64 v63; // [rsp+180h] [rbp+80h]
  DOUBLE vtime[2]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v65; // [rsp+198h] [rbp+98h]
  struct _SYSTEMTIME SystemTime; // [rsp+1A0h] [rbp+A0h] BYREF
  char v67[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  char Buffer[4096]; // [rsp+1D0h] [rbp+D0h] BYREF

  v47 = 0;
  v45 = 0;
  v43 = 0;
  v41 = 0;
  v39 = 0;
  v63 = 0;
  v61 = 0;
  v6 = -2147467259;
  v59 = 0;
  v65 = 0;
  v49 = 0;
  v53 = 0;
  v51 = 0;
  v55 = 0;
  v57 = 0;
  v7 = *(_QWORD *)a3;
  v46 = 0;
  v44 = 0;
  v8 = *(int (__fastcall **)(struct ILogScripting *, __int128 *))(v7 + 128);
  v42 = 0;
  v40 = 0;
  v38 = 0;
  v62 = 0;
  v60 = 0;
  v58 = 0;
  *(_OWORD *)vtime = 0;
  *(_OWORD *)Value = 0;
  *(_OWORD *)v52 = 0;
  *(_OWORD *)v50 = 0;
  *(_OWORD *)v54 = 0;
  *(_OWORD *)v56 = 0;
  SystemTime = 0;
  if ( v8(a3, &v46) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 136LL))(a3, &v44) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, DOUBLE *))(*(_QWORD *)a3 + 104LL))(a3, vtime) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 112LL))(a3, &v42) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 120LL))(a3, &v40) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 144LL))(a3, &v38) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, unsigned int *))(*(_QWORD *)a3 + 176LL))(a3, Value) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, unsigned int *))(*(_QWORD *)a3 + 192LL))(a3, v50) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, unsigned int *))(*(_QWORD *)a3 + 184LL))(a3, v52) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, unsigned int *))(*(_QWORD *)a3 + 208LL))(a3, v54) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, unsigned int *))(*(_QWORD *)a3 + 200LL))(a3, v56) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 152LL))(a3, &v62) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 160LL))(a3, &v60) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 168LL))(a3, &v58) >= 0
    && VariantTimeToSystemTime(vtime[1], &SystemTime) )
  {
    CACHED_DATETIME_FORMATS::GetFormattedDateTime((CASCLOG *)((char *)this + 1168), &SystemTime, v67);
    v9 = *((_QWORD *)&v38 + 1);
    if ( (unsigned __int16)v38 < 2u )
      v9 = *((_QWORD *)this + 145);
    v10 = *((_QWORD *)&v40 + 1);
    if ( (unsigned __int16)v40 < 2u )
      v10 = *((_QWORD *)this + 145);
    v11 = *((_QWORD *)&v42 + 1);
    if ( (unsigned __int16)v42 < 2u )
      v11 = *((_QWORD *)this + 145);
    v12 = *((_QWORD *)&v44 + 1);
    if ( (unsigned __int16)v44 < 2u )
      v12 = *((_QWORD *)this + 145);
    v13 = *((_QWORD *)&v46 + 1);
    if ( (unsigned __int16)v46 < 2u )
      v13 = *((_QWORD *)this + 145);
    v14 = sprintf_s(Buffer, 0x1000u, "%ws, %ws, %s%ws, %ws, %ws,", v13, v12, v67, v11, v10, v9);
    if ( v14 >= 0x1000 )
      return 2147942511LL;
    v16 = v14 + 1;
    Buffer[v14] = 32;
    v17 = &Buffer[v14 + 1];
    v18 = 1;
    if ( LOWORD(Value[0]) < 2u )
    {
      *(_WORD *)v17 = 45;
      v19 = 1;
    }
    else
    {
      v19 = FastDwToA(v17, Value[2]);
    }
    Buffer[v16 + v19] = 44;
    v20 = v16 + v19 + 1;
    v21 = v16 + v19 + 2;
    Buffer[v20] = 32;
    v22 = &Buffer[v21];
    if ( LOWORD(v50[0]) < 2u )
    {
      *(_WORD *)v22 = 45;
      v23 = 1;
    }
    else
    {
      v23 = FastDwToA(v22, v50[2]);
    }
    Buffer[v21 + v23] = 44;
    v24 = v21 + v23 + 1;
    v25 = v21 + v23 + 2;
    Buffer[v24] = 32;
    v26 = &Buffer[v25];
    if ( LOWORD(v52[0]) < 2u )
    {
      *(_WORD *)v26 = 45;
      v27 = 1;
    }
    else
    {
      v27 = FastDwToA(v26, v52[2]);
    }
    Buffer[v25 + v27] = 44;
    v28 = v25 + v27 + 1;
    v29 = v25 + v27 + 2;
    Buffer[v28] = 32;
    v30 = &Buffer[v29];
    if ( LOWORD(v54[0]) < 2u )
    {
      *(_WORD *)v30 = 45;
      v31 = 1;
    }
    else
    {
      v31 = FastDwToA(v30, v54[2]);
    }
    Buffer[v29 + v31] = 44;
    v32 = v29 + v31 + 1;
    v33 = v29 + v31 + 2;
    Buffer[v32] = 32;
    v34 = &Buffer[v33];
    if ( LOWORD(v56[0]) < 2u )
      *(_WORD *)v34 = 45;
    else
      v18 = FastDwToA(v34, v56[2]);
    v35 = *((_QWORD *)&v58 + 1);
    if ( (unsigned __int16)v58 < 2u )
      v35 = *((_QWORD *)this + 145);
    v36 = *((_QWORD *)&v60 + 1);
    if ( (unsigned __int16)v60 < 2u )
      v36 = *((_QWORD *)this + 145);
    v37 = *((_QWORD *)&v62 + 1);
    if ( (unsigned __int16)v62 < 2u )
      v37 = *((_QWORD *)this + 145);
    sprintf_s(&Buffer[v33 + v18], 4096LL - (v33 + v18), ", %ws, %ws, %ws", v37, v36, v35);
    fprintf(a2, "%s,\n", Buffer);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000cb70  push    rbp
0x18000cb72  push    rbx
0x18000cb73  push    rsi
0x18000cb74  push    rdi
0x18000cb75  push    r13
0x18000cb77  push    r14
0x18000cb79  push    r15
0x18000cb7b  lea     rbp, [rsp-10E0h]
0x18000cb83  mov     eax, 11E0h
0x18000cb88  call    _alloca_probe
0x18000cb8d  sub     rsp, rax
0x18000cb90  mov     rax, cs:__security_cookie
0x18000cb97  xor     rax, rsp
0x18000cb9a  mov     [rbp+1110h+var_40], rax
0x18000cba1  xor     eax, eax
0x18000cba3  xorps   xmm0, xmm0
0x18000cba6  xorps   xmm1, xmm1
0x18000cba9  mov     [rbp+1110h+var_1150], rax
0x18000cbad  mov     [rbp+1110h+var_1168], rax
0x18000cbb1  mov     r15, rdx
0x18000cbb4  mov     [rbp+1110h+var_1180], rax
0x18000cbb8  lea     rdx, [rbp+1110h+var_1160]
0x18000cbbc  mov     [rsp+1210h+var_1198], rax
0x18000cbc1  mov     rdi, rcx
0x18000cbc4  mov     [rsp+1210h+var_11B0], rax
0x18000cbc9  mov     rcx, r8
0x18000cbcc  mov     [rbp+1110h+var_1090], rax
0x18000cbd3  mov     rbx, r8
0x18000cbd6  mov     [rbp+1110h+var_10A8], rax
0x18000cbda  mov     esi, 80004005h
0x18000cbdf  mov     [rbp+1110h+var_10C0], rax
0x18000cbe3  mov     [rbp+1110h+var_1078], rax
0x18000cbea  mov     [rbp+1110h+var_1138], rax
0x18000cbee  mov     [rbp+1110h+var_1108], rax
0x18000cbf2  mov     [rbp+1110h+var_1120], rax
0x18000cbf6  mov     [rbp+1110h+var_10F0], rax
0x18000cbfa  mov     [rbp+1110h+var_10D8], rax
0x18000cbfe  mov     rax, [r8]
0x18000cc01  movups  [rbp+1110h+var_1160], xmm0
0x18000cc05  movups  [rbp+1110h+var_1178], xmm1
0x18000cc09  mov     rax, [rax+80h]
0x18000cc10  movups  [rbp+1110h+var_1190], xmm0
0x18000cc14  movups  [rsp+1210h+var_11A8], xmm1
0x18000cc19  movups  [rsp+1210h+var_11C0], xmm0
0x18000cc1e  movups  [rbp+1110h+var_10A0], xmm1
0x18000cc22  movups  [rbp+1110h+var_10B8], xmm0
0x18000cc26  movups  [rbp+1110h+var_10D0], xmm1
0x18000cc2a  movups  xmmword ptr [rbp+1110h+vtime], xmm0
0x18000cc31  movups  xmmword ptr [rbp+1110h+Value], xmm1
0x18000cc35  movups  xmmword ptr [rbp+1110h+var_1118], xmm0
0x18000cc39  movups  xmmword ptr [rbp+1110h+var_1130], xmm1
0x18000cc3d  movups  xmmword ptr [rbp+1110h+var_1100], xmm0
0x18000cc41  movups  xmmword ptr [rbp+1110h+var_10E8], xmm1
0x18000cc45  movups  xmmword ptr [rbp+1110h+SystemTime.wYear], xmm0
0x18000cc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc51  test    eax, eax
0x18000cc53  js      loc_18000D06D
0x18000cc59  mov     rax, [rbx]
0x18000cc5c  lea     rdx, [rbp+1110h+var_1178]
0x18000cc60  mov     rcx, rbx
0x18000cc63  mov     rax, [rax+88h]
0x18000cc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc6f  test    eax, eax
0x18000cc71  js      loc_18000D06D
0x18000cc77  mov     rax, [rbx]
0x18000cc7a  lea     rdx, [rbp+1110h+vtime]
0x18000cc81  mov     rcx, rbx
0x18000cc84  mov     rax, [rax+68h]
0x18000cc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc8d  test    eax, eax
0x18000cc8f  js      loc_18000D06D
0x18000cc95  mov     rax, [rbx]
0x18000cc98  lea     rdx, [rbp+1110h+var_1190]
0x18000cc9c  mov     rcx, rbx
0x18000cc9f  mov     rax, [rax+70h]
0x18000cca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca8  test    eax, eax
0x18000ccaa  js      loc_18000D06D
0x18000ccb0  mov     rax, [rbx]
0x18000ccb3  lea     rdx, [rsp+1210h+var_11A8]
0x18000ccb8  mov     rcx, rbx
0x18000ccbb  mov     rax, [rax+78h]
0x18000ccbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc4  test    eax, eax
0x18000ccc6  js      loc_18000D06D
0x18000cccc  mov     rax, [rbx]
0x18000cccf  lea     rdx, [rsp+1210h+var_11C0]
0x18000ccd4  mov     rcx, rbx
0x18000ccd7  mov     rax, [rax+90h]
0x18000ccde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cce3  test    eax, eax
0x18000cce5  js      loc_18000D06D
0x18000cceb  mov     rax, [rbx]
0x18000ccee  lea     rdx, [rbp+1110h+Value]
0x18000ccf2  mov     rcx, rbx
0x18000ccf5  mov     rax, [rax+0B0h]
0x18000ccfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd01  test    eax, eax
0x18000cd03  js      loc_18000D06D
0x18000cd09  mov     rax, [rbx]
0x18000cd0c  lea     rdx, [rbp+1110h+var_1130]
0x18000cd10  mov     rcx, rbx
0x18000cd13  mov     rax, [rax+0C0h]
0x18000cd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd1f  test    eax, eax
0x18000cd21  js      loc_18000D06D
0x18000cd27  mov     rax, [rbx]
0x18000cd2a  lea     rdx, [rbp+1110h+var_1118]
0x18000cd2e  mov     rcx, rbx
0x18000cd31  mov     rax, [rax+0B8h]
0x18000cd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd3d  test    eax, eax
0x18000cd3f  js      loc_18000D06D
0x18000cd45  mov     rax, [rbx]
0x18000cd48  lea     rdx, [rbp+1110h+var_1100]
0x18000cd4c  mov     rcx, rbx
0x18000cd4f  mov     rax, [rax+0D0h]
0x18000cd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd5b  test    eax, eax
0x18000cd5d  js      loc_18000D06D
0x18000cd63  mov     rax, [rbx]
0x18000cd66  lea     rdx, [rbp+1110h+var_10E8]
0x18000cd6a  mov     rcx, rbx
0x18000cd6d  mov     rax, [rax+0C8h]
0x18000cd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd79  test    eax, eax
0x18000cd7b  js      loc_18000D06D
0x18000cd81  mov     rax, [rbx]
0x18000cd84  lea     rdx, [rbp+1110h+var_10A0]
0x18000cd88  mov     rcx, rbx
0x18000cd8b  mov     rax, [rax+98h]
0x18000cd92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd97  test    eax, eax
0x18000cd99  js      loc_18000D06D
0x18000cd9f  mov     rax, [rbx]
0x18000cda2  lea     rdx, [rbp+1110h+var_10B8]
0x18000cda6  mov     rcx, rbx
0x18000cda9  mov     rax, [rax+0A0h]
0x18000cdb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdb5  test    eax, eax
0x18000cdb7  js      loc_18000D06D
0x18000cdbd  mov     rax, [rbx]
0x18000cdc0  lea     rdx, [rbp+1110h+var_10D0]
0x18000cdc4  mov     rcx, rbx
0x18000cdc7  mov     rax, [rax+0A8h]
0x18000cdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd3  test    eax, eax
0x18000cdd5  js      loc_18000D06D
0x18000cddb  movsd   xmm0, [rbp+1110h+vtime+8]; vtime
0x18000cde3  lea     rdx, [rbp+1110h+SystemTime]; lpSystemTime
0x18000cdea  call    cs:__imp_VariantTimeToSystemTime
0x18000cdf0  test    eax, eax
0x18000cdf2  jz      loc_18000D06D
0x18000cdf8  lea     rcx, [rdi+490h]
0x18000cdff  lea     r8, [rbp+1110h+var_1060]
0x18000ce06  lea     rdx, [rbp+1110h+SystemTime]
0x18000ce0d  call    cs:__imp_?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z; CACHED_DATETIME_FORMATS::GetFormattedDateTime(_SYSTEMTIME const *,char *)
0x18000ce13  mov     r8, qword ptr [rsp+1210h+var_11C0+8]
0x18000ce18  mov     r13w, 2
0x18000ce1d  cmp     word ptr [rsp+1210h+var_11C0], r13w
0x18000ce23  jnb     short loc_18000CE2C
0x18000ce25  mov     r8, [rdi+488h]
0x18000ce2c  mov     rdx, qword ptr [rsp+1210h+var_11A8+8]
0x18000ce31  cmp     word ptr [rsp+1210h+var_11A8], r13w
0x18000ce37  jnb     short loc_18000CE40
0x18000ce39  mov     rdx, [rdi+488h]
0x18000ce40  mov     rcx, qword ptr [rbp+1110h+var_1190+8]
0x18000ce44  cmp     word ptr [rbp+1110h+var_1190], r13w
0x18000ce49  jnb     short loc_18000CE52
0x18000ce4b  mov     rcx, [rdi+488h]
0x18000ce52  mov     rax, qword ptr [rbp+1110h+var_1178+8]
0x18000ce56  cmp     word ptr [rbp+1110h+var_1178], r13w
0x18000ce5b  jnb     short loc_18000CE64
0x18000ce5d  mov     rax, [rdi+488h]
0x18000ce64  mov     r9, qword ptr [rbp+1110h+var_1160+8]
0x18000ce68  cmp     word ptr [rbp+1110h+var_1160], r13w
0x18000ce6d  jnb     short loc_18000CE76
0x18000ce6f  mov     r9, [rdi+488h]
0x18000ce76  mov     [rsp+1210h+var_11D0], r8
0x18000ce7b  mov     esi, 1000h
0x18000ce80  mov     [rsp+1210h+var_11D8], rdx
0x18000ce85  lea     r8, aWsWsSWsWsWs; "%ws, %ws, %s%ws, %ws, %ws,"
0x18000ce8c  mov     [rsp+1210h+var_11E0], rcx
0x18000ce91  mov     edx, esi; BufferCount
0x18000ce93  lea     rcx, [rbp+1110h+var_1060]
0x18000ce9a  mov     [rsp+1210h+var_11E8], rcx
0x18000ce9f  lea     rcx, [rbp+1110h+Buffer]; Buffer
0x18000cea6  mov     [rsp+1210h+var_11F0], rax
0x18000ceab  call    cs:__imp_sprintf_s
0x18000ceb1  mov     ecx, eax
0x18000ceb3  cmp     eax, esi
0x18000ceb5  jb      short loc_18000CEC1
0x18000ceb7  mov     eax, 8007006Fh
0x18000cebc  jmp     loc_18000D06F
0x18000cec1  lea     r14d, [rcx+1]
0x18000cec5  mov     [rbp+rcx+1110h+Buffer], 20h ; ' '
0x18000cecd  mov     eax, r14d
0x18000ced0  lea     rcx, [rbp+1110h+Buffer]
0x18000ced7  add     rcx, rax; Buffer
0x18000ceda  mov     ebx, 1
0x18000cedf  cmp     word ptr [rbp+1110h+Value], r13w
0x18000cee4  jb      short loc_18000CEF0
0x18000cee6  mov     edx, [rbp+1110h+Value+8]; Value
0x18000cee9  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000ceee  jmp     short loc_18000CEF7
0x18000cef0  mov     word ptr [rcx], 2Dh ; '-'
0x18000cef5  mov     eax, ebx
0x18000cef7  lea     ecx, [r14+rax]
0x18000cefb  mov     [rbp+rcx+1110h+Buffer], 2Ch ; ','
0x18000cf03  inc     ecx
0x18000cf05  lea     r14d, [rcx+1]
0x18000cf09  mov     [rbp+rcx+1110h+Buffer], 20h ; ' '
0x18000cf11  mov     eax, r14d
0x18000cf14  lea     rcx, [rbp+1110h+Buffer]
0x18000cf1b  add     rcx, rax; Buffer
0x18000cf1e  cmp     word ptr [rbp+1110h+var_1130], r13w
0x18000cf23  jb      short loc_18000CF2F
0x18000cf25  mov     edx, [rbp+1110h+var_1130+8]; Value
0x18000cf28  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000cf2d  jmp     short loc_18000CF36
0x18000cf2f  mov     word ptr [rcx], 2Dh ; '-'
0x18000cf34  mov     eax, ebx
0x18000cf36  lea     ecx, [r14+rax]
0x18000cf3a  mov     [rbp+rcx+1110h+Buffer], 2Ch ; ','
0x18000cf42  inc     ecx
0x18000cf44  lea     r14d, [rcx+1]
0x18000cf48  mov     [rbp+rcx+1110h+Buffer], 20h ; ' '
0x18000cf50  mov     eax, r14d
0x18000cf53  lea     rcx, [rbp+1110h+Buffer]
0x18000cf5a  add     rcx, rax; Buffer
0x18000cf5d  cmp     word ptr [rbp+1110h+var_1118], r13w
0x18000cf62  jb      short loc_18000CF6E
0x18000cf64  mov     edx, [rbp+1110h+var_1118+8]; Value
0x18000cf67  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000cf6c  jmp     short loc_18000CF75
0x18000cf6e  mov     word ptr [rcx], 2Dh ; '-'
0x18000cf73  mov     eax, ebx
0x18000cf75  lea     ecx, [r14+rax]
0x18000cf79  mov     [rbp+rcx+1110h+Buffer], 2Ch ; ','
0x18000cf81  inc     ecx
0x18000cf83  lea     r14d, [rcx+1]
0x18000cf87  mov     [rbp+rcx+1110h+Buffer], 20h ; ' '
0x18000cf8f  mov     eax, r14d
0x18000cf92  lea     rcx, [rbp+1110h+Buffer]
0x18000cf99  add     rcx, rax; Buffer
0x18000cf9c  cmp     word ptr [rbp+1110h+var_1100], r13w
0x18000cfa1  jb      short loc_18000CFAD
0x18000cfa3  mov     edx, [rbp+1110h+var_1100+8]; Value
0x18000cfa6  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000cfab  jmp     short loc_18000CFB4
0x18000cfad  mov     word ptr [rcx], 2Dh ; '-'
0x18000cfb2  mov     eax, ebx
0x18000cfb4  lea     ecx, [r14+rax]
0x18000cfb8  mov     [rbp+rcx+1110h+Buffer], 2Ch ; ','
0x18000cfc0  inc     ecx
0x18000cfc2  lea     r14d, [rcx+1]
0x18000cfc6  mov     [rbp+rcx+1110h+Buffer], 20h ; ' '
0x18000cfce  mov     eax, r14d
0x18000cfd1  lea     rcx, [rbp+1110h+Buffer]
0x18000cfd8  add     rcx, rax; Buffer
0x18000cfdb  cmp     word ptr [rbp+1110h+var_10E8], r13w
0x18000cfe0  jb      short loc_18000CFEE
0x18000cfe2  mov     edx, [rbp+1110h+var_10E8+8]; Value
0x18000cfe5  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000cfea  mov     ebx, eax
0x18000cfec  jmp     short loc_18000CFF3
0x18000cfee  mov     word ptr [rcx], 2Dh ; '-'
0x18000cff3  lea     eax, [r14+rbx]
0x18000cff7  mov     r8, qword ptr [rbp+1110h+var_10D0+8]
0x18000cffb  cmp     word ptr [rbp+1110h+var_10D0], r13w
0x18000d000  jnb     short loc_18000D009
0x18000d002  mov     r8, [rdi+488h]
0x18000d009  mov     rdx, qword ptr [rbp+1110h+var_10B8+8]
0x18000d00d  cmp     word ptr [rbp+1110h+var_10B8], r13w
0x18000d012  jnb     short loc_18000D01B
0x18000d014  mov     rdx, [rdi+488h]
0x18000d01b  mov     r9, qword ptr [rbp+1110h+var_10A0+8]
0x18000d01f  cmp     word ptr [rbp+1110h+var_10A0], r13w
0x18000d024  jnb     short loc_18000D02D
0x18000d026  mov     r9, [rdi+488h]
0x18000d02d  mov     [rsp+1210h+var_11E8], r8
0x18000d032  lea     rcx, [rbp+1110h+Buffer]
0x18000d039  sub     rsi, rax
0x18000d03c  mov     [rsp+1210h+var_11F0], rdx
0x18000d041  add     rcx, rax; Buffer
0x18000d044  lea     r8, aWsWsWs; ", %ws, %ws, %ws"
0x18000d04b  mov     rdx, rsi; BufferCount
0x18000d04e  call    cs:__imp_sprintf_s
0x18000d054  lea     r8, [rbp+1110h+Buffer]
0x18000d05b  mov     rcx, r15; Stream
0x18000d05e  lea     rdx, aS; "%s,\n"
0x18000d065  call    cs:__imp_fprintf
0x18000d06b  xor     esi, esi
0x18000d06d  mov     eax, esi
0x18000d06f  mov     rcx, [rbp+1110h+var_40]
0x18000d076  xor     rcx, rsp; StackCookie
0x18000d079  call    __security_check_cookie
0x18000d07e  add     rsp, 11E0h
0x18000d085  pop     r15
0x18000d087  pop     r14
  ... truncated ...
```
