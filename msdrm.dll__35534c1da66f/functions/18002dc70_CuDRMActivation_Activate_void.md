# CuDRMActivation::Activate(void)

- ea: `0x18002dc70`
- end: `0x18002e039`
- name: `?Activate@CuDRMActivation@@UEAAJXZ`
- size: `969`
- prototype: `__int64 __fastcall(CuDRMActivation *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x180015438`
- `0x18002dc70`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18002dfad`
- `msvcrt!_beginthreadex` at `0x18002dfad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dfef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dfef`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=3
__int64 __fastcall CuDRMActivation::Activate(const unsigned __int16 **this)
{
  void **v2; // rax
  void **v3; // rsi
  const unsigned __int16 *v4; // rax
  __int64 v5; // rdx
  signed int v6; // ebx
  unsigned __int64 v7; // r8
  signed __int64 v8; // r12
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  unsigned __int64 v15; // r8
  signed __int64 v16; // r12
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int16 *v20; // rax
  const unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  signed __int64 v24; // r15
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int16 *v28; // rax
  void *v29; // rax
  unsigned int ThrdAddr; // [rsp+90h] [rbp+18h] BYREF
  void **v32; // [rsp+98h] [rbp+20h]

  ThrdAddr = 0;
  v2 = (void **)operator new(0x38u);
  v3 = v2;
  v32 = v2;
  if ( !v2 )
  {
LABEL_43:
    v6 = -2147024882;
    goto LABEL_44;
  }
  *(_OWORD *)v2 = 0;
  *((_OWORD *)v2 + 1) = 0;
  *((_OWORD *)v2 + 2) = 0;
  v2[5] = CuDRMActivation::EventCallback;
  v2[6] = this;
  v2[4] = (void *)this[12];
  *(_DWORD *)v2 = *((_DWORD *)this + 26) != 0 ? 6 : 2;
  v4 = this[4];
  if ( v4 )
  {
    v5 = 0x7FFFFFFF;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = v5 == 0 ? 0x80070057 : 0;
    v7 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
    if ( !v5 )
      goto LABEL_44;
    v8 = v7 + 1;
    if ( v7 + 1 < v7 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v5);
    v9 = HIDWORD(v8);
    if ( v8 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v9);
    v10 = 2LL * (unsigned int)v8;
    v11 = v9 << 33;
    if ( v11 + v10 < v10 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v11);
    if ( v11 + v10 )
    {
      v12 = (unsigned __int16 *)operator new[](saturated_mul(v8, 2u));
      v3[3] = v12;
      if ( !v12 )
      {
        v6 = -2147024882;
        goto LABEL_44;
      }
      v6 = StringCchCopyW(v12, v8, this[4]);
      if ( v6 < 0 )
        goto LABEL_44;
    }
  }
  else
  {
    v6 = 0;
    v3[3] = 0;
  }
  v13 = this[2];
  if ( v13 )
  {
    v14 = 0x7FFFFFFF;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v14;
    }
    while ( v14 );
    v6 = v14 == 0 ? 0x80070057 : 0;
    v15 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
    if ( !v14 )
      goto LABEL_44;
    v16 = v15 + 1;
    if ( v15 + 1 < v15 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v14);
    v17 = HIDWORD(v16);
    if ( v16 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
    v18 = 2LL * (unsigned int)v16;
    v19 = v17 << 33;
    if ( v19 + v18 < v18 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v19);
    if ( v19 + v18 )
    {
      v20 = (unsigned __int16 *)operator new[](saturated_mul(v16, 2u));
      v3[1] = v20;
      if ( !v20 )
      {
        v6 = -2147024882;
        goto LABEL_44;
      }
      v6 = StringCchCopyW(v20, v16, this[2]);
      if ( v6 < 0 )
        goto LABEL_44;
    }
  }
  else
  {
    v3[1] = 0;
  }
  v21 = this[3];
  if ( !v21 )
  {
    v3[2] = 0;
LABEL_42:
    *((_BYTE *)this + 108) = 0;
    v29 = (void *)_beginthreadex(0, 0, InternalActivationProc, v3, 0, &ThrdAddr);
    if ( v29 )
    {
      CloseHandle(v29);
      return (unsigned int)v6;
    }
    goto LABEL_43;
  }
  v22 = 0x7FFFFFFF;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v22;
  }
  while ( v22 );
  v6 = v22 == 0 ? 0x80070057 : 0;
  v23 = (0x7FFFFFFF - v22) & ((unsigned __int128)-(__int128)(unsigned __int64)v22 >> 64);
  if ( v22 )
  {
    v24 = v23 + 1;
    if ( v23 + 1 < v23 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v22);
    v25 = HIDWORD(v24);
    if ( v24 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v25);
    v26 = 2LL * (unsigned int)v24;
    v27 = v25 << 33;
    if ( v27 + v26 < v26 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v27);
    if ( v27 + v26 )
    {
      v28 = (unsigned __int16 *)operator new[](saturated_mul(v24, 2u));
      v3[2] = v28;
      if ( !v28 )
      {
        v6 = -2147024882;
        goto LABEL_44;
      }
      v6 = StringCchCopyW(v28, v24, this[3]);
      if ( v6 < 0 )
        goto LABEL_44;
    }
    goto LABEL_42;
  }
LABEL_44:
  *((_BYTE *)this + 108) = 1;
  if ( v3 )
  {
    operator delete(v3[1]);
    operator delete(v3[2]);
    operator delete(v3[3]);
  }
  operator delete(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002dc70  mov     rax, rsp
0x18002dc73  mov     [rax+8], rcx
0x18002dc77  push    rbx
0x18002dc78  push    rsi
0x18002dc79  push    rdi
0x18002dc7a  push    r12
0x18002dc7c  push    r13
0x18002dc7e  push    r14
0x18002dc80  push    r15
0x18002dc82  sub     rsp, 40h
0x18002dc86  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18002dc8e  mov     r14, rcx
0x18002dc91  xor     edi, edi
0x18002dc93  mov     [rax+18h], edi
0x18002dc96  lea     ecx, [rdi+38h]; Size
0x18002dc99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dc9e  mov     rsi, rax
0x18002dca1  mov     [rsp+78h+arg_18], rax
0x18002dca9  test    rax, rax
0x18002dcac  jz      loc_18002DFB8
0x18002dcb2  xorps   xmm0, xmm0
0x18002dcb5  movups  xmmword ptr [rax], xmm0
0x18002dcb8  movups  xmmword ptr [rax+10h], xmm0
0x18002dcbc  movups  xmmword ptr [rax+20h], xmm0
0x18002dcc0  lea     rax, ?EventCallback@CuDRMActivation@@SAJW4_DRM_STATUS_MSG@@JPEAX1@Z; CuDRMActivation::EventCallback(_DRM_STATUS_MSG,long,void *,void *)
0x18002dcc7  mov     [rsi+28h], rax
0x18002dccb  mov     [rsi+30h], r14
0x18002dccf  mov     rax, [r14+60h]
0x18002dcd3  mov     [rsi+20h], rax
0x18002dcd7  mov     eax, [r14+68h]
0x18002dcdb  neg     eax
0x18002dcdd  sbb     ecx, ecx
0x18002dcdf  and     ecx, 4
0x18002dce2  add     ecx, 2
0x18002dce5  mov     [rsi], ecx
0x18002dce7  mov     rax, [r14+20h]
0x18002dceb  test    rax, rax
0x18002dcee  jz      loc_18002DDE1
0x18002dcf4  mov     r15d, 7FFFFFFFh
0x18002dcfa  mov     edx, r15d
0x18002dcfd  cmp     [rax], di
0x18002dd00  jz      short loc_18002DD0C
0x18002dd02  add     rax, 2
0x18002dd06  sub     rdx, 1
0x18002dd0a  jnz     short loc_18002DCFD
0x18002dd0c  mov     rax, rdx
0x18002dd0f  neg     rax
0x18002dd12  sbb     ebx, ebx
0x18002dd14  not     ebx
0x18002dd16  and     ebx, 80070057h
0x18002dd1c  mov     rax, rdx
0x18002dd1f  mov     rcx, r15
0x18002dd22  sub     rcx, rdx
0x18002dd25  neg     rax
0x18002dd28  sbb     r8, r8
0x18002dd2b  and     r8, rcx
0x18002dd2e  test    rdx, rdx
0x18002dd31  jnz     short loc_18002DD38
0x18002dd33  jmp     loc_18002DFBD
0x18002dd38  lea     r12, [r8+1]
0x18002dd3c  cmp     r12, r8
0x18002dd3f  jb      loc_18002E007
0x18002dd45  mov     rcx, r12
0x18002dd48  shr     rcx, 20h
0x18002dd4c  mov     rax, rcx
0x18002dd4f  shr     rax, 1Fh
0x18002dd53  test    eax, eax
0x18002dd55  jnz     loc_18002E00D
0x18002dd5b  mov     eax, r12d
0x18002dd5e  add     rax, rax
0x18002dd61  shl     rcx, 21h
0x18002dd65  lea     rdx, [rcx+rax]
0x18002dd69  cmp     rdx, rax
0x18002dd6c  jb      loc_18002E012
0x18002dd72  test    rdx, rdx
0x18002dd75  jz      short loc_18002DDBF
0x18002dd77  mov     eax, 2
0x18002dd7c  mul     r12
0x18002dd7f  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18002dd86  cmovb   rax, r13
0x18002dd8a  mov     rcx, rax; unsigned __int64
0x18002dd8d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002dd92  mov     [rsi+18h], rax
0x18002dd96  test    rax, rax
0x18002dd99  jnz     short loc_18002DDA5
0x18002dd9b  mov     ebx, 8007000Eh
0x18002dda0  jmp     loc_18002DFBD
0x18002dda5  mov     r8, [r14+20h]; unsigned __int16 *
0x18002dda9  mov     rdx, r12; unsigned __int64
0x18002ddac  mov     rcx, rax; unsigned __int16 *
0x18002ddaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ddb4  mov     ebx, eax
0x18002ddb6  test    eax, eax
0x18002ddb8  jns     short loc_18002DDC3
0x18002ddba  jmp     loc_18002DFBD
0x18002ddbf  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002ddc3  jmp     short loc_18002DDF1
0x18002ddc5  mov     r14, [rsp+78h+arg_0]
0x18002ddcd  mov     ebx, [rsp+78h+arg_8]
0x18002ddd4  mov     rsi, [rsp+78h+arg_18]
0x18002dddc  jmp     loc_18002DFBD
0x18002dde1  mov     ebx, edi
0x18002dde3  mov     [rsi+18h], rdi
0x18002dde7  mov     r15d, 7FFFFFFFh
0x18002dded  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002ddf1  mov     rax, [r14+10h]
0x18002ddf5  test    rax, rax
0x18002ddf8  jz      loc_18002DEBE
0x18002ddfe  mov     rdx, r15
0x18002de01  cmp     [rax], di
0x18002de04  jz      short loc_18002DE10
0x18002de06  add     rax, 2
0x18002de0a  sub     rdx, 1
0x18002de0e  jnz     short loc_18002DE01
0x18002de10  mov     rax, rdx
0x18002de13  neg     rax
0x18002de16  sbb     ebx, ebx
0x18002de18  not     ebx
0x18002de1a  and     ebx, 80070057h
0x18002de20  mov     rax, rdx
0x18002de23  mov     rcx, r15
0x18002de26  sub     rcx, rdx
0x18002de29  neg     rax
0x18002de2c  sbb     r8, r8
0x18002de2f  and     r8, rcx
0x18002de32  test    rdx, rdx
0x18002de35  jnz     short loc_18002DE3C
0x18002de37  jmp     loc_18002DFBD
0x18002de3c  lea     r12, [r8+1]
0x18002de40  cmp     r12, r8
0x18002de43  jb      loc_18002E018
0x18002de49  mov     rcx, r12
0x18002de4c  shr     rcx, 20h
0x18002de50  mov     rax, rcx
0x18002de53  shr     rax, 1Fh
0x18002de57  test    eax, eax
0x18002de59  jnz     loc_18002E01D
0x18002de5f  mov     eax, r12d
0x18002de62  add     rax, rax
0x18002de65  shl     rcx, 21h
0x18002de69  lea     rdx, [rcx+rax]
0x18002de6d  cmp     rdx, rax
0x18002de70  jb      loc_18002E022
0x18002de76  test    rdx, rdx
0x18002de79  jz      short loc_18002DEBC
0x18002de7b  mov     eax, 2
0x18002de80  mul     r12
0x18002de83  cmovb   rax, r13
0x18002de87  mov     rcx, rax; unsigned __int64
0x18002de8a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002de8f  mov     [rsi+8], rax
0x18002de93  test    rax, rax
0x18002de96  jnz     short loc_18002DEA2
0x18002de98  mov     ebx, 8007000Eh
0x18002de9d  jmp     loc_18002DFBD
0x18002dea2  mov     r8, [r14+10h]; unsigned __int16 *
0x18002dea6  mov     rdx, r12; unsigned __int64
0x18002dea9  mov     rcx, rax; unsigned __int16 *
0x18002deac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002deb1  mov     ebx, eax
0x18002deb3  test    eax, eax
0x18002deb5  jns     short loc_18002DEBC
0x18002deb7  jmp     loc_18002DFBD
0x18002debc  jmp     short loc_18002DEC2
0x18002debe  mov     [rsi+8], rdi
0x18002dec2  mov     rax, [r14+18h]
0x18002dec6  test    rax, rax
0x18002dec9  jz      loc_18002DF86
0x18002decf  mov     rcx, r15
0x18002ded2  cmp     [rax], di
0x18002ded5  jz      short loc_18002DEE1
0x18002ded7  add     rax, 2
0x18002dedb  sub     rcx, 1
0x18002dedf  jnz     short loc_18002DED2
0x18002dee1  mov     rax, rcx
0x18002dee4  neg     rax
0x18002dee7  sbb     ebx, ebx
0x18002dee9  not     ebx
0x18002deeb  and     ebx, 80070057h
0x18002def1  mov     rax, rcx
0x18002def4  sub     r15, rcx
0x18002def7  neg     rax
0x18002defa  sbb     rdx, rdx
0x18002defd  and     rdx, r15
0x18002df00  test    rcx, rcx
0x18002df03  jnz     short loc_18002DF0A
0x18002df05  jmp     loc_18002DFBD
0x18002df0a  lea     r15, [rdx+1]
0x18002df0e  cmp     r15, rdx
0x18002df11  jb      loc_18002E028
0x18002df17  mov     rcx, r15
0x18002df1a  shr     rcx, 20h
0x18002df1e  mov     rax, rcx
0x18002df21  shr     rax, 1Fh
0x18002df25  test    eax, eax
0x18002df27  jnz     loc_18002E02D
0x18002df2d  mov     eax, r15d
0x18002df30  add     rax, rax
0x18002df33  shl     rcx, 21h
0x18002df37  lea     rdx, [rcx+rax]
0x18002df3b  cmp     rdx, rax
0x18002df3e  jb      loc_18002E032
0x18002df44  test    rdx, rdx
0x18002df47  jz      short loc_18002DF84
0x18002df49  mov     eax, 2
0x18002df4e  mul     r15
0x18002df51  cmovb   rax, r13
0x18002df55  mov     rcx, rax; unsigned __int64
0x18002df58  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002df5d  mov     [rsi+10h], rax
0x18002df61  test    rax, rax
0x18002df64  jnz     short loc_18002DF6D
0x18002df66  mov     ebx, 8007000Eh
0x18002df6b  jmp     short loc_18002DFBD
0x18002df6d  mov     r8, [r14+18h]; unsigned __int16 *
0x18002df71  mov     rdx, r15; unsigned __int64
0x18002df74  mov     rcx, rax; unsigned __int16 *
0x18002df77  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002df7c  mov     ebx, eax
0x18002df7e  test    eax, eax
0x18002df80  jns     short loc_18002DF84
0x18002df82  jmp     short loc_18002DFBD
0x18002df84  jmp     short loc_18002DF8A
0x18002df86  mov     [rsi+10h], rdi
0x18002df8a  mov     [r14+6Ch], dil
0x18002df8e  lea     rax, [rsp+78h+arg_10]
0x18002df96  mov     [rsp+78h+ThrdAddr], rax; ThrdAddr
0x18002df9b  mov     [rsp+78h+InitFlag], edi; InitFlag
0x18002df9f  mov     r9, rsi; ArgList
0x18002dfa2  lea     r8, ?InternalActivationProc@@YAIPEAX@Z; StartAddress
0x18002dfa9  xor     edx, edx; StackSize
0x18002dfab  xor     ecx, ecx; Security
0x18002dfad  call    cs:__imp__beginthreadex
0x18002dfb3  test    rax, rax
0x18002dfb6  jnz     short loc_18002DFEC
0x18002dfb8  mov     ebx, 8007000Eh
0x18002dfbd  mov     byte ptr [r14+6Ch], 1
0x18002dfc2  test    rsi, rsi
0x18002dfc5  jz      short loc_18002DFE2
0x18002dfc7  mov     rcx, [rsi+8]; Block
0x18002dfcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002dfd0  mov     rcx, [rsi+10h]; Block
0x18002dfd4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002dfd9  mov     rcx, [rsi+18h]; Block
0x18002dfdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002dfe2  mov     rcx, rsi; Block
0x18002dfe5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002dfea  jmp     short loc_18002DFF5
0x18002dfec  mov     rcx, rax; hObject
0x18002dfef  call    cs:__imp_CloseHandle
0x18002dff5  mov     eax, ebx
0x18002dff7  add     rsp, 40h
0x18002dffb  pop     r15
0x18002dffd  pop     r14
0x18002dfff  pop     r13
0x18002e001  pop     r12
0x18002e003  pop     rdi
0x18002e004  pop     rsi
0x18002e005  pop     rbx
0x18002e006  retn
0x18002e007  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e00d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e012  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e018  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e01d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e022  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e028  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e02d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002e032  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
