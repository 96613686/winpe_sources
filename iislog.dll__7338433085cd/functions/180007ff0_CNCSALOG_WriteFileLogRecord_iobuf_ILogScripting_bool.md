# CNCSALOG::WriteFileLogRecord(_iobuf *,ILogScripting *,bool)

- ea: `0x180007ff0`
- end: `0x1800083bd`
- name: `?WriteFileLogRecord@CNCSALOG@@MEAAJPEAU_iobuf@@PEAUILogScripting@@_N@Z`
- size: `973`
- prototype: `__int64 __fastcall(CNCSALOG *__hidden this, struct _iobuf *, struct ILogScripting *, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001748`
- `0x1800022a8`
- `0x180007ff0`
- `0x18000eca0`
- `0x18000ed30`
- `0x180010010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180008274`
- `msvcrt!sprintf_s` at `0x1800082b5`
- `msvcrt!sprintf_s` at `0x1800082f1`
- `msvcrt!sprintf_s` at `0x180008274`
- `msvcrt!sprintf_s` at `0x1800082b5`
- `msvcrt!sprintf_s` at `0x1800082f1`
- `msvcrt!fprintf` at `0x180008382`
- `msvcrt!fprintf` at `0x180008382`
- `IisRTL!Month3CharNames` at `0x1800081e5`
- `IisRTL!Month3CharNames` at `0x1800081e5`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800081a6`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800081a6`

## pseudocode

```c
__int64 __fastcall CNCSALOG::WriteFileLogRecord(CNCSALOG *this, struct _iobuf *a2, struct ILogScripting *a3)
{
  unsigned int v6; // esi
  __int64 v7; // rax
  int (__fastcall *v8)(struct ILogScripting *, __int128 *); // rax
  __int64 v9; // r14
  __int64 v10; // rbx
  unsigned int v11; // esi
  const char *v12; // r12
  __int64 v13; // r15
  __int64 v14; // r9
  unsigned __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r9
  unsigned int v20; // eax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rdx
  int wDay; // [rsp+28h] [rbp-D8h]
  int wYear; // [rsp+38h] [rbp-C8h]
  int wHour; // [rsp+40h] [rbp-C0h]
  int wMinute; // [rsp+48h] [rbp-B8h]
  int wSecond; // [rsp+50h] [rbp-B0h]
  __int128 v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-50h]
  __int128 v34; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-38h]
  __int128 v36; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v37; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v39; // [rsp+F8h] [rbp-8h]
  unsigned int Value[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v41; // [rsp+110h] [rbp+10h]
  unsigned int v42[4]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v43; // [rsp+128h] [rbp+28h]
  __int128 v44; // [rsp+130h] [rbp+30h] BYREF
  __int64 v45; // [rsp+140h] [rbp+40h]
  struct _SYSTEMTIME SystemTime; // [rsp+148h] [rbp+48h] BYREF
  char Buffer[4096]; // [rsp+160h] [rbp+60h] BYREF

  v35 = 0;
  v33 = 0;
  v31 = 0;
  v29 = 0;
  v37 = 0;
  v39 = 0;
  v45 = 0;
  v6 = -2147467259;
  v43 = 0;
  v41 = 0;
  v7 = *(_QWORD *)a3;
  v34 = 0;
  v32 = 0;
  v8 = *(int (__fastcall **)(struct ILogScripting *, __int128 *))(v7 + 128);
  v30 = 0;
  v28 = 0;
  v36 = 0;
  v38 = 0;
  v44 = 0;
  *(_OWORD *)v42 = 0;
  *(_OWORD *)Value = 0;
  SystemTime = 0;
  if ( v8(a3, &v34) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 136LL))(a3, &v32) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 104LL))(a3, &v44) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 152LL))(a3, &v30) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 160LL))(a3, &v28) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 168LL))(a3, &v36) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, unsigned int *))(*(_QWORD *)a3 + 184LL))(a3, v42) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, unsigned int *))(*(_QWORD *)a3 + 208LL))(a3, Value) >= 0
    && (*(int (__fastcall **)(struct ILogScripting *, __int128 *))(*(_QWORD *)a3 + 224LL))(a3, &v38) >= 0
    && VariantTimeToSystemTime(*((double *)&v44 + 1) + *((double *)this + 148), &SystemTime) )
  {
    v9 = *((_QWORD *)&v28 + 1);
    if ( (unsigned __int16)v28 < 2u )
      v9 = *((_QWORD *)this + 145);
    v10 = *((_QWORD *)&v30 + 1);
    if ( (unsigned __int16)v30 < 2u )
      v10 = *((_QWORD *)this + 145);
    v11 = 1;
    v12 = Month3CharNames((unsigned int)SystemTime.wMonth - 1);
    v13 = *((_QWORD *)&v32 + 1);
    if ( (unsigned __int16)v32 < 2u )
      v13 = *((_QWORD *)this + 145);
    v14 = *((_QWORD *)&v34 + 1);
    if ( (unsigned __int16)v34 < 2u )
      v14 = *((_QWORD *)this + 145);
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wYear = SystemTime.wYear;
    wDay = SystemTime.wDay;
    sprintf_s(
      Buffer,
      0x1000u,
      "%ws - %ws [%02d/%s/%d:%02d:%02d:%02d %s] \"%ws %ws",
      v14,
      v13,
      wDay,
      v12,
      wYear,
      wHour,
      wMinute,
      wSecond,
      (char *)this + 1168,
      v10,
      v9);
    v15 = -1;
    if ( (unsigned __int16)v36 >= 2u )
    {
      v16 = -1;
      do
        ++v16;
      while ( Buffer[v16] );
      sprintf_s(&Buffer[v16], 4096 - v16, "?%ws", *((_QWORD *)&v36 + 1));
    }
    v17 = -1;
    do
      ++v17;
    while ( Buffer[v17] );
    v18 = *((_QWORD *)&v38 + 1);
    if ( (unsigned __int16)v38 < 2u )
      v18 = *((_QWORD *)this + 145);
    sprintf_s(&Buffer[v17], 4096 - v17, " %ws\"", v18);
    do
      ++v15;
    while ( Buffer[v15] );
    if ( v15 >= 0x1000 )
      return 2147942511LL;
    Buffer[v15] = 32;
    if ( LOWORD(Value[0]) < 2u )
    {
      *(_WORD *)&Buffer[v15 + 1] = 45;
      v20 = 1;
    }
    else
    {
      v20 = FastDwToA(&Buffer[v15 + 1], Value[2]);
    }
    v21 = v20 + 1LL + v15;
    Buffer[v21] = 32;
    if ( LOWORD(v42[0]) < 2u )
      *(_WORD *)&Buffer[v21 + 1] = 45;
    else
      v11 = FastDwToA(&Buffer[v21 + 1], v42[2]);
    v22 = v21 + v11 + 1LL;
    if ( v22 >= 0x1000 )
      _report_rangecheckfailure();
    Buffer[v22] = 0;
    fprintf(a2, "%s\n", Buffer);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180007ff0  mov     [rsp-8+arg_18], rbx
0x180007ff5  push    rbp
0x180007ff6  push    rsi
0x180007ff7  push    rdi
0x180007ff8  push    r12
0x180007ffa  push    r13
0x180007ffc  push    r14
0x180007ffe  push    r15
0x180008000  lea     rbp, [rsp-1070h]
0x180008008  mov     eax, 1170h
0x18000800d  call    _alloca_probe
0x180008012  sub     rsp, rax
0x180008015  mov     rax, cs:__security_cookie
0x18000801c  xor     rax, rsp
0x18000801f  mov     [rbp+10A0h+var_40], rax
0x180008026  xor     eax, eax
0x180008028  xorps   xmm0, xmm0
0x18000802b  xorps   xmm1, xmm1
0x18000802e  mov     [rbp+10A0h+var_10D8], rax
0x180008032  mov     [rbp+10A0h+var_10F0], rax
0x180008036  mov     r13, rdx
0x180008039  mov     [rbp+10A0h+var_1108], rax
0x18000803d  lea     rdx, [rbp+10A0h+var_10E8]
0x180008041  mov     [rbp+10A0h+var_1120], rax
0x180008045  mov     rdi, rcx
0x180008048  mov     [rbp+10A0h+var_10C0], rax
0x18000804c  mov     rcx, r8
0x18000804f  mov     [rbp+10A0h+var_10A8], rax
0x180008053  mov     rbx, r8
0x180008056  mov     [rbp+10A0h+var_1060], rax
0x18000805a  mov     esi, 80004005h
0x18000805f  mov     [rbp+10A0h+var_1078], rax
0x180008063  mov     [rbp+10A0h+var_1090], rax
0x180008067  mov     rax, [r8]
0x18000806a  movups  [rbp+10A0h+var_10E8], xmm0
0x18000806e  movups  [rbp+10A0h+var_1100], xmm1
0x180008072  mov     rax, [rax+80h]
0x180008079  movups  [rbp+10A0h+var_1118], xmm0
0x18000807d  movups  [rsp+11A0h+var_1130], xmm1
0x180008082  movups  [rbp+10A0h+var_10D0], xmm0
0x180008086  movups  [rbp+10A0h+var_10B8], xmm1
0x18000808a  movups  [rbp+10A0h+var_1070], xmm0
0x18000808e  movups  xmmword ptr [rbp+10A0h+var_1088], xmm1
0x180008092  movups  xmmword ptr [rbp+10A0h+Value], xmm0
0x180008096  movups  xmmword ptr [rbp+10A0h+SystemTime.wYear], xmm0
0x18000809a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000809f  test    eax, eax
0x1800080a1  js      loc_18000838B
0x1800080a7  mov     rax, [rbx]
0x1800080aa  lea     rdx, [rbp+10A0h+var_1100]
0x1800080ae  mov     rcx, rbx
0x1800080b1  mov     rax, [rax+88h]
0x1800080b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080bd  test    eax, eax
0x1800080bf  js      loc_18000838B
0x1800080c5  mov     rax, [rbx]
0x1800080c8  lea     rdx, [rbp+10A0h+var_1070]
0x1800080cc  mov     rcx, rbx
0x1800080cf  mov     rax, [rax+68h]
0x1800080d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d8  test    eax, eax
0x1800080da  js      loc_18000838B
0x1800080e0  mov     rax, [rbx]
0x1800080e3  lea     rdx, [rbp+10A0h+var_1118]
0x1800080e7  mov     rcx, rbx
0x1800080ea  mov     rax, [rax+98h]
0x1800080f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080f6  test    eax, eax
0x1800080f8  js      loc_18000838B
0x1800080fe  mov     rax, [rbx]
0x180008101  lea     rdx, [rsp+11A0h+var_1130]
0x180008106  mov     rcx, rbx
0x180008109  mov     rax, [rax+0A0h]
0x180008110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008115  test    eax, eax
0x180008117  js      loc_18000838B
0x18000811d  mov     rax, [rbx]
0x180008120  lea     rdx, [rbp+10A0h+var_10D0]
0x180008124  mov     rcx, rbx
0x180008127  mov     rax, [rax+0A8h]
0x18000812e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008133  test    eax, eax
0x180008135  js      loc_18000838B
0x18000813b  mov     rax, [rbx]
0x18000813e  lea     rdx, [rbp+10A0h+var_1088]
0x180008142  mov     rcx, rbx
0x180008145  mov     rax, [rax+0B8h]
0x18000814c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008151  test    eax, eax
0x180008153  js      loc_18000838B
0x180008159  mov     rax, [rbx]
0x18000815c  lea     rdx, [rbp+10A0h+Value]
0x180008160  mov     rcx, rbx
0x180008163  mov     rax, [rax+0D0h]
0x18000816a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000816f  test    eax, eax
0x180008171  js      loc_18000838B
0x180008177  mov     rax, [rbx]
0x18000817a  lea     rdx, [rbp+10A0h+var_10B8]
0x18000817e  mov     rcx, rbx
0x180008181  mov     rax, [rax+0E0h]
0x180008188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000818d  test    eax, eax
0x18000818f  js      loc_18000838B
0x180008195  movsd   xmm0, qword ptr [rbp+10A0h+var_1070+8]
0x18000819a  lea     rdx, [rbp+10A0h+SystemTime]; lpSystemTime
0x18000819e  addsd   xmm0, qword ptr [rdi+4A0h]; vtime
0x1800081a6  call    cs:__imp_VariantTimeToSystemTime
0x1800081ac  test    eax, eax
0x1800081ae  jz      loc_18000838B
0x1800081b4  cmp     word ptr [rsp+11A0h+var_1130], 2
0x1800081ba  mov     r14, qword ptr [rsp+11A0h+var_1130+8]
0x1800081bf  jnb     short loc_1800081C8
0x1800081c1  mov     r14, [rdi+488h]
0x1800081c8  cmp     word ptr [rbp+10A0h+var_1118], 2
0x1800081cd  mov     rbx, qword ptr [rbp+10A0h+var_1118+8]
0x1800081d1  jnb     short loc_1800081DA
0x1800081d3  mov     rbx, [rdi+488h]
0x1800081da  movzx   ecx, [rbp+10A0h+SystemTime.wMonth]
0x1800081de  mov     esi, 1
0x1800081e3  sub     ecx, esi
0x1800081e5  call    cs:__imp_?Month3CharNames@@YAPEBDK@Z; Month3CharNames(ulong)
0x1800081eb  cmp     word ptr [rbp+10A0h+var_1100], 2
0x1800081f0  mov     r12, rax
0x1800081f3  mov     r15, qword ptr [rbp+10A0h+var_1100+8]
0x1800081f7  jnb     short loc_180008200
0x1800081f9  mov     r15, [rdi+488h]
0x180008200  cmp     word ptr [rbp+10A0h+var_10E8], 2
0x180008205  mov     r9, qword ptr [rbp+10A0h+var_10E8+8]
0x180008209  jnb     short loc_180008212
0x18000820b  mov     r9, [rdi+488h]
0x180008212  movzx   ecx, [rbp+10A0h+SystemTime.wSecond]
0x180008216  lea     rax, [rdi+490h]
0x18000821d  movzx   edx, [rbp+10A0h+SystemTime.wMinute]
0x180008221  movzx   r8d, [rbp+10A0h+SystemTime.wHour]
0x180008226  movzx   r10d, [rbp+10A0h+SystemTime.wYear]
0x18000822b  movzx   r11d, [rbp+10A0h+SystemTime.wDay]
0x180008230  mov     [rsp+11A0h+var_1138], r14
0x180008235  mov     [rsp+11A0h+var_1140], rbx
0x18000823a  mov     [rsp+11A0h+var_1148], rax
0x18000823f  mov     [rsp+11A0h+var_1150], ecx
0x180008243  lea     rcx, [rbp+10A0h+Buffer]; Buffer
0x180008247  mov     [rsp+11A0h+var_1158], edx
0x18000824b  mov     [rsp+11A0h+var_1160], r8d
0x180008250  lea     r8, aWsWs02dSD02d02; "%ws - %ws [%02d/%s/%d:%02d:%02d:%02d %s"...
0x180008257  mov     [rsp+11A0h+var_1168], r10d
0x18000825c  mov     [rsp+11A0h+var_1170], r12
0x180008261  mov     r12d, 1000h
0x180008267  mov     [rsp+11A0h+var_1178], r11d
0x18000826c  mov     edx, r12d; BufferCount
0x18000826f  mov     [rsp+11A0h+var_1180], r15
0x180008274  call    cs:__imp_sprintf_s
0x18000827a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000827e  mov     r15w, 2
0x180008283  xor     r14d, r14d
0x180008286  cmp     word ptr [rbp+10A0h+var_10D0], r15w
0x18000828b  jb      short loc_1800082BB
0x18000828d  lea     rcx, [rbp+10A0h+Buffer]
0x180008291  mov     rax, rbx
0x180008294  inc     rax
0x180008297  cmp     [rcx+rax], r14b
0x18000829b  jnz     short loc_180008294
0x18000829d  mov     r9, qword ptr [rbp+10A0h+var_10D0+8]
0x1800082a1  lea     rcx, [rbp+10A0h+Buffer]
0x1800082a5  mov     rdx, r12
0x1800082a8  lea     r8, aWs; "?%ws"
0x1800082af  sub     rdx, rax; BufferCount
0x1800082b2  add     rcx, rax; Buffer
0x1800082b5  call    cs:__imp_sprintf_s
0x1800082bb  lea     rcx, [rbp+10A0h+Buffer]
0x1800082bf  mov     rax, rbx
0x1800082c2  inc     rax
0x1800082c5  cmp     [rcx+rax], r14b
0x1800082c9  jnz     short loc_1800082C2
0x1800082cb  mov     r9, qword ptr [rbp+10A0h+var_10B8+8]
0x1800082cf  cmp     word ptr [rbp+10A0h+var_10B8], r15w
0x1800082d4  jnb     short loc_1800082DD
0x1800082d6  mov     r9, [rdi+488h]
0x1800082dd  mov     rdx, r12
0x1800082e0  lea     rcx, [rbp+10A0h+Buffer]
0x1800082e4  sub     rdx, rax; BufferCount
0x1800082e7  lea     r8, aWs_0; " %ws\""
0x1800082ee  add     rcx, rax; Buffer
0x1800082f1  call    cs:__imp_sprintf_s
0x1800082f7  lea     rax, [rbp+10A0h+Buffer]
0x1800082fb  inc     rbx
0x1800082fe  cmp     [rax+rbx], r14b
0x180008302  jnz     short loc_1800082FB
0x180008304  cmp     rbx, r12
0x180008307  jb      short loc_180008310
0x180008309  mov     eax, 8007006Fh
0x18000830e  jmp     short loc_18000838D
0x180008310  lea     rax, [rbp+rbx+10A0h+var_103F]
0x180008315  mov     [rbp+rbx+10A0h+Buffer], 20h ; ' '
0x18000831a  cmp     word ptr [rbp+10A0h+Value], r15w
0x18000831f  jb      short loc_18000832E
0x180008321  mov     edx, [rbp+10A0h+Value+8]; Value
0x180008324  mov     rcx, rax; Buffer
0x180008327  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x18000832c  jmp     short loc_180008335
0x18000832e  mov     word ptr [rax], 2Dh ; '-'
0x180008333  mov     eax, esi
0x180008335  mov     eax, eax
0x180008337  inc     rax
0x18000833a  add     rbx, rax
0x18000833d  lea     rax, [rbp+rbx+10A0h+var_103F]
0x180008342  mov     [rbp+rbx+10A0h+Buffer], 20h ; ' '
0x180008347  cmp     word ptr [rbp+10A0h+var_1088], r15w
0x18000834c  jb      short loc_18000835D
0x18000834e  mov     edx, [rbp+10A0h+var_1088+8]; Value
0x180008351  mov     rcx, rax; Buffer
0x180008354  call    ?FastDwToA@@YAKPEADK@Z; FastDwToA(char *,ulong)
0x180008359  mov     esi, eax
0x18000835b  jmp     short loc_180008362
0x18000835d  mov     word ptr [rax], 2Dh ; '-'
0x180008362  mov     edx, esi
0x180008364  inc     rdx
0x180008367  add     rdx, rbx
0x18000836a  cmp     rdx, r12
0x18000836d  jnb     short loc_1800083B7
0x18000836f  mov     [rbp+rdx+10A0h+Buffer], r14b
0x180008374  lea     r8, [rbp+10A0h+Buffer]
0x180008378  lea     rdx, aS_0; "%s\n"
0x18000837f  mov     rcx, r13; Stream
0x180008382  call    cs:__imp_fprintf
0x180008388  mov     esi, r14d
0x18000838b  mov     eax, esi
0x18000838d  mov     rcx, [rbp+10A0h+var_40]
0x180008394  xor     rcx, rsp; StackCookie
0x180008397  call    __security_check_cookie
0x18000839c  mov     rbx, [rsp+11A0h+arg_18]
0x1800083a4  add     rsp, 1170h
0x1800083ab  pop     r15
0x1800083ad  pop     r14
0x1800083af  pop     r13
0x1800083b1  pop     r12
0x1800083b3  pop     rdi
0x1800083b4  pop     rsi
0x1800083b5  pop     rbp
0x1800083b6  retn
0x1800083b7  call    __report_rangecheckfailure
```
