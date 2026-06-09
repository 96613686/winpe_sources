# basessp::WSTConvertLegacySCardBufferToEx2PackedCreds(void * (*)(unsigned __int64),void (*)(void *),void *,void *,ulong,_SEC_WINNT_AUTH_PACKED_CREDENTIALS * *)

- ea: `0x18001e2b4`
- end: `0x18001e5e8`
- name: `?WSTConvertLegacySCardBufferToEx2PackedCreds@basessp@@YAJP6APEAX_K@ZP6AXPEAX@Z22KPEAPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@@Z`
- size: `820`
- prototype: `int(basessp *__hidden this, void *(*)(unsigned __int64), void (*)(void *), void *, void *, unsigned int, struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005bc0`

## callees

- `0x18000ec9c`
- `0x18000ef54`
- `0x18000f09c`
- `0x18001e2b4`
- `0x18001e5f0`
- `0x18001ece2`
- `0x180020010`

## string_xrefs

- `0x18001e3a6`: `No Client Token`
- `0x18001e52c`: `_CreateSmartcardEx2PackedCreds`

## pseudocode

```c
__int64 __fastcall basessp::WSTConvertLegacySCardBufferToEx2PackedCreds(
        basessp *this,
        void (__fastcall *a2)(void (*)(void *)),
        void (*a3)(void *),
        unsigned __int16 *a4,
        void *a5,
        _QWORD *a6)
{
  _QWORD *v6; // r14
  __int64 v7; // rbp
  unsigned int v11; // edx
  unsigned int SmartcardEx2PackedCreds; // ebx
  const char *v13; // r8
  __int64 v14; // r9
  const char *v15; // rax
  const char *v16; // r8
  int v17; // r9d
  __int64 v18; // r15
  void (*v19)(void *); // rsi
  unsigned __int64 v20; // rcx
  __int64 v21; // r8
  unsigned __int64 v22; // rcx
  unsigned int v23; // eax
  void (*v24)(void *); // rax
  const char *v25; // rcx
  const char *v26; // rcx
  const char *v27; // rax
  const char *v28; // rcx
  const char *v29; // rax
  __int64 v30; // rcx
  void (*v31)(void *); // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  _BYTE *v34; // rdx
  __int64 v35; // rax
  _BYTE *v36; // rcx
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **v38; // [rsp+28h] [rbp-50h]
  _OWORD v39[4]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v41; // [rsp+98h] [rbp+20h] BYREF

  v6 = a6;
  v7 = 0;
  v41 = 0;
  v39[0] = 0;
  if ( a6 )
    *a6 = 0;
  v11 = (unsigned int)a5;
  if ( (unsigned int)a5 < 4 )
  {
    SmartcardEx2PackedCreds = -1073741811;
    v13 = _DBG_BASENAME((const char *)this);
    v14 = 401;
    v15 = "Invalid Buffer length";
LABEL_5:
    WPPTraceLogA("0x%08x %s:%u : %s:%ws", SmartcardEx2PackedCreds, v13, v14, v15, &dword_180021D0C);
    goto LABEL_38;
  }
  if ( ((*(_DWORD *)a4 - 13) & 0xFFFFFFFD) != 0 )
  {
    SmartcardEx2PackedCreds = -1073741637;
    v16 = _DBG_BASENAME((const char *)this);
    WPPTraceLogA("0x%08x %s:%u : %s:%u", 3221225659LL, v16, 409, "Invalid Message Type for Cloud AP logon", v17);
    goto LABEL_38;
  }
  LODWORD(v18) = 0;
  v19 = 0;
  if ( !v6 )
    goto LABEL_34;
  if ( !a3 )
  {
    SmartcardEx2PackedCreds = -1073741811;
    v13 = _DBG_BASENAME((const char *)this);
    v14 = 420;
    v15 = "No Client Token";
    goto LABEL_5;
  }
  v20 = *((_QWORD *)a4 + 6);
  if ( !v20
    || v20 > (unsigned int)a5
    || (v21 = a4[20], v20 + v21 > (unsigned int)a5)
    || v20 < 0x48
    || (v20 & 1) != 0
    || (a4[21] = v21, *((_QWORD *)a4 + 6) = (char *)a4 + v20, (v21 & 1) != 0) )
  {
LABEL_18:
    SmartcardEx2PackedCreds = -1073741811;
    goto LABEL_38;
  }
  v22 = *((_QWORD *)a4 + 8);
  v23 = *((_DWORD *)a4 + 15);
  if ( v22 )
  {
    if ( v23 )
    {
      if ( v23 > v11 || v22 > v11 - v23 )
        goto LABEL_18;
      *((_QWORD *)a4 + 8) = (char *)a4 + v22;
    }
    else
    {
      *((_QWORD *)a4 + 8) = 0;
    }
  }
  else if ( v23 )
  {
    goto LABEL_18;
  }
  v18 = (unsigned int)(v21 + 2);
  v24 = (void (*)(void *))((__int64 (__fastcall *)(__int64))this)(v18);
  v19 = v24;
  if ( !v24 )
  {
    SmartcardEx2PackedCreds = -1073741801;
    v13 = _DBG_BASENAME(v25);
    v14 = 442;
    v15 = "AllocFn";
    goto LABEL_5;
  }
  memcpy_0(v24, *((const void **)a4 + 6), a4[20]);
  *((_WORD *)v19 + ((unsigned __int64)(v18 - 2) >> 1)) = 0;
  SmartcardEx2PackedCreds = basessp::_DecodePin(this, a2, v19, (unsigned __int16 *)a3, (USHORT *)v39);
  if ( !SmartcardEx2PackedCreds )
  {
    SmartcardEx2PackedCreds = basessp::_CreateSmartcardEx2PackedCreds(
                                this,
                                (void *(*)(unsigned __int64))a2,
                                (void (*)(void *))v39,
                                (struct _UNICODE_STRING *)a4,
                                (struct _KERB_CERTIFICATE_LOGON *)&v41,
                                v38);
    if ( SmartcardEx2PackedCreds )
    {
      v29 = _DBG_BASENAME(v28);
      WPPTraceLogA(
        "0x%08x %s:%u : %s:%ws",
        SmartcardEx2PackedCreds,
        v29,
        462,
        "_CreateSmartcardEx2PackedCreds",
        &dword_180021D0C);
      v7 = v41;
      goto LABEL_35;
    }
    *v6 = v41;
LABEL_34:
    SmartcardEx2PackedCreds = 0;
    if ( !v19 )
      goto LABEL_38;
    goto LABEL_35;
  }
  v27 = _DBG_BASENAME(v26);
  WPPTraceLogA("0x%08x %s:%u : %s:%ws", SmartcardEx2PackedCreds, v27, 454, "_DecodePin", &dword_180021D0C);
LABEL_35:
  v30 = (unsigned int)v18;
  v31 = v19;
  if ( (_DWORD)v18 )
  {
    do
    {
      *(_BYTE *)v31 = 0;
      v31 = (void (*)(void *))((char *)v31 + 1);
      --v30;
    }
    while ( v30 );
  }
  a2(v19);
LABEL_38:
  v32 = *((_QWORD *)&v39[0] + 1);
  if ( *((_QWORD *)&v39[0] + 1) )
  {
    v33 = LOWORD(v39[0]);
    v34 = (_BYTE *)*((_QWORD *)&v39[0] + 1);
    if ( LOWORD(v39[0]) )
    {
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
    }
    ((void (__fastcall *)(__int64, _BYTE *))a2)(v32, v34);
  }
  if ( v7 )
  {
    v35 = *(unsigned __int16 *)(v7 + 2);
    v36 = (_BYTE *)v7;
    if ( *(_WORD *)(v7 + 2) )
    {
      do
      {
        *v36++ = 0;
        --v35;
      }
      while ( v35 );
    }
    a2((void (*)(void *))v7);
  }
  return SmartcardEx2PackedCreds;
}

```

## disassembly

```asm
0x18001e2b4  mov     rax, rsp
0x18001e2b7  mov     [rax+8], rbx
0x18001e2bb  mov     [rax+18h], r8
0x18001e2bf  push    rbp
0x18001e2c0  push    rsi
0x18001e2c1  push    rdi
0x18001e2c2  push    r12
0x18001e2c4  push    r13
0x18001e2c6  push    r14
0x18001e2c8  push    r15
0x18001e2ca  sub     rsp, 40h
0x18001e2ce  mov     r14, [rsp+78h+arg_28]
0x18001e2d6  xor     ebp, ebp
0x18001e2d8  mov     [rax+20h], rbp
0x18001e2dc  xorps   xmm0, xmm0
0x18001e2df  mov     rdi, r9
0x18001e2e2  mov     r12, rdx
0x18001e2e5  mov     r13, rcx
0x18001e2e8  movups  xmmword ptr [rax-48h], xmm0
0x18001e2ec  test    r14, r14
0x18001e2ef  jz      short loc_18001E2F4
0x18001e2f1  mov     [r14], rbp
0x18001e2f4  mov     edx, [rsp+0A0h]
0x18001e2fb  cmp     edx, 4
0x18001e2fe  jnb     short loc_18001E33E
0x18001e300  mov     ebx, 0C000000Dh
0x18001e305  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e30a  mov     r8, rax
0x18001e30d  mov     r9d, 191h
0x18001e313  lea     rax, dword_180021D0C
0x18001e31a  mov     [rsp+78h+var_50], rax
0x18001e31f  lea     rax, aInvalidBufferL; "Invalid Buffer length"
0x18001e326  lea     rcx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001e32d  mov     edx, ebx
0x18001e32f  mov     [rsp+78h+var_58], rax
0x18001e334  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001e339  jmp     loc_18001E57B
0x18001e33e  mov     r9d, [r9]
0x18001e341  lea     eax, [r9-0Dh]
0x18001e345  test    eax, 0FFFFFFFDh
0x18001e34a  jz      short loc_18001E374
0x18001e34c  mov     ebx, 0C00000BBh
0x18001e351  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e356  mov     r8, rax
0x18001e359  mov     dword ptr [rsp+78h+var_50], r9d
0x18001e35e  lea     rax, aInvalidMessage; "Invalid Message Type for Cloud AP logon"
0x18001e365  mov     r9d, 199h
0x18001e36b  lea     rcx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x18001e372  jmp     short loc_18001E32D
0x18001e374  xor     r15d, r15d
0x18001e377  xor     esi, esi
0x18001e379  test    r14, r14
0x18001e37c  jz      loc_18001E552
0x18001e382  test    r8, r8
0x18001e385  jnz     short loc_18001E3B2
0x18001e387  mov     ebx, 0C000000Dh
0x18001e38c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e391  mov     r8, rax
0x18001e394  mov     r9d, 1A4h
0x18001e39a  lea     rax, dword_180021D0C
0x18001e3a1  mov     [rsp+78h+var_50], rax
0x18001e3a6  lea     rax, aNoClientToken; "No Client Token"
0x18001e3ad  jmp     loc_18001E326
0x18001e3b2  mov     rcx, [rdi+30h]
0x18001e3b6  test    rcx, rcx
0x18001e3b9  jz      short loc_18001E3EC
0x18001e3bb  cmp     rcx, rdx
0x18001e3be  ja      short loc_18001E3EC
0x18001e3c0  movzx   r8d, word ptr [rdi+28h]
0x18001e3c5  lea     rax, [rcx+r8]
0x18001e3c9  cmp     rax, rdx
0x18001e3cc  ja      short loc_18001E3EC
0x18001e3ce  cmp     rcx, 48h ; 'H'
0x18001e3d2  jb      short loc_18001E3EC
0x18001e3d4  test    cl, 1
0x18001e3d7  jnz     short loc_18001E3EC
0x18001e3d9  mov     [rdi+2Ah], r8w
0x18001e3de  lea     rax, [rcx+rdi]
0x18001e3e2  mov     [rdi+30h], rax
0x18001e3e6  test    r8b, 1
0x18001e3ea  jz      short loc_18001E3F6
0x18001e3ec  mov     ebx, 0C000000Dh
0x18001e3f1  jmp     loc_18001E57B
0x18001e3f6  mov     rcx, [rdi+40h]
0x18001e3fa  mov     eax, [rdi+3Ch]
0x18001e3fd  test    rcx, rcx
0x18001e400  jnz     short loc_18001E408
0x18001e402  test    eax, eax
0x18001e404  jz      short loc_18001E427
0x18001e406  jmp     short loc_18001E3EC
0x18001e408  test    eax, eax
0x18001e40a  jnz     short loc_18001E412
0x18001e40c  mov     [rdi+40h], rsi
0x18001e410  jmp     short loc_18001E427
0x18001e412  cmp     eax, edx
0x18001e414  ja      short loc_18001E3EC
0x18001e416  sub     edx, eax
0x18001e418  mov     eax, edx
0x18001e41a  cmp     rcx, rax
0x18001e41d  ja      short loc_18001E3EC
0x18001e41f  lea     rax, [rcx+rdi]
0x18001e423  mov     [rdi+40h], rax
0x18001e427  lea     r15d, [r8+2]
0x18001e42b  mov     rax, r13
0x18001e42e  mov     ecx, r15d
0x18001e431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e436  mov     rsi, rax
0x18001e439  test    rax, rax
0x18001e43c  jnz     short loc_18001E469
0x18001e43e  mov     ebx, 0C0000017h
0x18001e443  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e448  mov     r8, rax
0x18001e44b  mov     r9d, 1BAh
0x18001e451  lea     rax, dword_180021D0C
0x18001e458  mov     [rsp+78h+var_50], rax
0x18001e45d  lea     rax, aAllocfn; "AllocFn"
0x18001e464  jmp     loc_18001E326
0x18001e469  movzx   r8d, word ptr [rdi+28h]; Size
0x18001e46e  mov     rcx, rsi; void *
0x18001e471  mov     rdx, [rdi+30h]; Src
0x18001e475  call    memcpy_0
0x18001e47a  mov     r9, [rsp+78h+arg_10]; unsigned __int16 *
0x18001e482  lea     rcx, [r15-2]
0x18001e486  shr     rcx, 1
0x18001e489  xor     eax, eax
0x18001e48b  mov     r8, rsi; void (*)(void *)
0x18001e48e  mov     rdx, r12; void *(*)(unsigned __int64)
0x18001e491  mov     [rsi+rcx*2], ax
0x18001e495  lea     rax, [rsp+78h+var_48]
0x18001e49a  mov     rcx, r13; this
0x18001e49d  mov     [rsp+78h+var_58], rax; void *
0x18001e4a2  call    ?_DecodePin@basessp@@YAJP6APEAX_K@ZP6AXPEAX@ZPEAG2PEAU_UNICODE_STRING@@@Z; basessp::_DecodePin(void * (*)(unsigned __int64),void (*)(void *),ushort *,void *,_UNICODE_STRING *)
0x18001e4a7  mov     ebx, eax
0x18001e4a9  test    eax, eax
0x18001e4ab  jz      short loc_18001E4E3
0x18001e4ad  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e4b2  mov     r8, rax
0x18001e4b5  lea     rcx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001e4bc  lea     rax, dword_180021D0C
0x18001e4c3  mov     r9d, 1C6h
0x18001e4c9  mov     [rsp+78h+var_50], rax
0x18001e4ce  mov     edx, ebx
0x18001e4d0  lea     rax, aDecodepin; "_DecodePin"
0x18001e4d7  mov     [rsp+78h+var_58], rax
0x18001e4dc  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001e4e1  jmp     short loc_18001E559
0x18001e4e3  lea     rax, [rsp+78h+arg_18]
0x18001e4eb  mov     r9, rdi; struct _UNICODE_STRING *
0x18001e4ee  lea     r8, [rsp+78h+var_48]; void (*)(void *)
0x18001e4f3  mov     [rsp+78h+var_58], rax; struct _KERB_CERTIFICATE_LOGON *
0x18001e4f8  mov     rdx, r12; void *(*)(unsigned __int64)
0x18001e4fb  mov     rcx, r13; this
0x18001e4fe  call    ?_CreateSmartcardEx2PackedCreds@basessp@@YAJP6APEAX_K@ZP6AXPEAX@ZPEAU_UNICODE_STRING@@PEAU_KERB_CERTIFICATE_LOGON@@PEAPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@@Z; basessp::_CreateSmartcardEx2PackedCreds(void * (*)(unsigned __int64),void (*)(void *),_UNICODE_STRING *,_KERB_CERTIFICATE_LOGON *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS * *)
0x18001e503  mov     ebx, eax
0x18001e505  test    eax, eax
0x18001e507  jz      short loc_18001E547
0x18001e509  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e50e  mov     r8, rax
0x18001e511  lea     rcx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001e518  lea     rax, dword_180021D0C
0x18001e51f  mov     r9d, 1CEh
0x18001e525  mov     [rsp+78h+var_50], rax
0x18001e52a  mov     edx, ebx
0x18001e52c  lea     rax, aCreatesmartcar; "_CreateSmartcardEx2PackedCreds"
0x18001e533  mov     [rsp+78h+var_58], rax
0x18001e538  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001e53d  mov     rbp, [rsp+78h+arg_18]
0x18001e545  jmp     short loc_18001E559
0x18001e547  mov     rax, [rsp+78h+arg_18]
0x18001e54f  mov     [r14], rax
0x18001e552  xor     ebx, ebx
0x18001e554  test    rsi, rsi
0x18001e557  jz      short loc_18001E57B
0x18001e559  mov     ecx, r15d
0x18001e55c  mov     rax, rsi
0x18001e55f  test    r15d, r15d
0x18001e562  jz      short loc_18001E570
0x18001e564  mov     byte ptr [rax], 0
0x18001e567  inc     rax
0x18001e56a  sub     rcx, 1
0x18001e56e  jnz     short loc_18001E564
0x18001e570  mov     rcx, rsi
0x18001e573  mov     rax, r12
0x18001e576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e57b  mov     rcx, [rsp+78h+var_40]
0x18001e580  test    rcx, rcx
0x18001e583  jz      short loc_18001E5A6
0x18001e585  movzx   eax, [rsp+78h+var_48]
0x18001e58a  mov     rdx, rcx
0x18001e58d  test    rax, rax
0x18001e590  jz      short loc_18001E59E
0x18001e592  mov     byte ptr [rdx], 0
0x18001e595  inc     rdx
0x18001e598  sub     rax, 1
0x18001e59c  jnz     short loc_18001E592
0x18001e59e  mov     rax, r12
0x18001e5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5a6  test    rbp, rbp
0x18001e5a9  jz      short loc_18001E5CE
0x18001e5ab  movzx   eax, word ptr [rbp+2]
0x18001e5af  mov     rcx, rbp
0x18001e5b2  test    rax, rax
0x18001e5b5  jz      short loc_18001E5C3
0x18001e5b7  mov     byte ptr [rcx], 0
0x18001e5ba  inc     rcx
0x18001e5bd  sub     rax, 1
0x18001e5c1  jnz     short loc_18001E5B7
0x18001e5c3  mov     rcx, rbp
0x18001e5c6  mov     rax, r12
0x18001e5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ce  mov     eax, ebx
0x18001e5d0  mov     rbx, [rsp+78h+arg_0]
0x18001e5d8  add     rsp, 40h
0x18001e5dc  pop     r15
0x18001e5de  pop     r14
0x18001e5e0  pop     r13
0x18001e5e2  pop     r12
0x18001e5e4  pop     rdi
0x18001e5e5  pop     rsi
0x18001e5e6  pop     rbp
0x18001e5e7  retn
```
