# basessp::_CreateSmartcardEx2PackedCreds(void * (*)(unsigned __int64),void (*)(void *),_UNICODE_STRING *,_KERB_CERTIFICATE_LOGON *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS * *)

- ea: `0x18000ec9c`
- end: `0x18000ef4d`
- name: `?_CreateSmartcardEx2PackedCreds@basessp@@YAJP6APEAX_K@ZP6AXPEAX@ZPEAU_UNICODE_STRING@@PEAU_KERB_CERTIFICATE_LOGON@@PEAPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(basessp *__hidden this, void *(*)(unsigned __int64), void (*)(void *), struct _UNICODE_STRING *, struct _KERB_CERTIFICATE_LOGON *, struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e2b4`

## callees

- `0x18000ec9c`
- `0x18000ef54`
- `0x18000f09c`
- `0x18001ece2`
- `0x18001ecee`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall basessp::_CreateSmartcardEx2PackedCreds(
        basessp *this,
        void *(*a2)(unsigned __int64),
        const void **a3,
        struct _UNICODE_STRING *a4,
        struct _KERB_CERTIFICATE_LOGON *a5)
{
  void *(*v7)(unsigned __int64); // r15
  unsigned __int16 v9; // ax
  unsigned int v10; // edi
  char *v11; // rax
  unsigned int v12; // r10d
  __int64 v13; // r9
  unsigned int v14; // r10d
  unsigned __int16 v15; // si
  __int64 v16; // rbp
  _DWORD *v17; // rax
  const char *v18; // rcx
  _DWORD *v19; // rbx
  char *v20; // r8
  unsigned int v21; // eax
  const char *v22; // rcx
  unsigned int v23; // edx
  const char *v24; // rcx
  char *v25; // r8
  unsigned int v26; // r10d
  const char *v27; // rcx
  _WORD *v28; // r14
  char *v29; // r8
  char *v30; // rax
  unsigned int v31; // r10d
  _BYTE *v32; // rax

  v7 = a2;
  *(_QWORD *)&a5->MessageType = 0;
  v9 = WORD2(a4[3].Buffer) + 44;
  if ( v9 < 0x2Cu )
  {
    v10 = -1073741675;
    v11 = _DBG_BASENAME((const char *)this);
    v13 = 314;
LABEL_3:
    WPPTraceLogA("0x%08x %s:%u : %s:%ws", v12, v11, v13, "RtlUShortAdd", &dword_180021D0C);
    return v10;
  }
  v15 = *(_WORD *)a3 + v9;
  if ( v15 < v9 )
  {
    v10 = -1073741675;
    v11 = _DBG_BASENAME((const char *)this);
    v13 = 317;
    goto LABEL_3;
  }
  v16 = v15;
  v17 = (_DWORD *)((__int64 (__fastcall *)(_QWORD))this)(v15);
  v19 = v17;
  if ( v17 )
  {
    memset_0(v17, 0, v15);
    v19[2] = LODWORD(a4[3].Buffer) | 4;
    v21 = WORD2(a4[3].Buffer);
    *((_WORD *)v19 + 8) = v21;
    v19[3] = 44;
    memcpy_0(v19 + 11, *(const void **)&a4[4].Length, v21);
    v23 = v19[3] + *((unsigned __int16 *)v19 + 8);
    *((_WORD *)v19 + 12) = *(_WORD *)a3;
    if ( v23 < v19[3] )
    {
      v19[5] = -1;
      v10 = -1073741675;
      v30 = _DBG_BASENAME(v22);
      WPPTraceLogA("0x%08x %s:%u : %s:%ws", v31, v30, 336, "RtlULongAdd", &dword_180021D0C);
    }
    else
    {
      v19[5] = v23;
      memcpy_0((char *)v19 + v23, a3[1], *((unsigned __int16 *)v19 + 12));
      if ( v15 < 0xFFE4u )
      {
        v28 = (_WORD *)((__int64 (__fastcall *)(_QWORD))this)((unsigned __int16)(v15 + 28));
        *(_QWORD *)&a5->MessageType = v28;
        if ( v28 )
        {
          v10 = 0;
          memset_0(v28, 0, (unsigned __int16)(v15 + 28));
          *v28 = 28;
          v28[1] = v15 + 28;
          *(_OWORD *)(v28 + 2) = SEC_WINNT_AUTH_DATA_TYPE_NGC;
          v28[12] = v15;
          *((_DWORD *)v28 + 5) = 28;
          memcpy_0(v28 + 14, v19, v15);
        }
        else
        {
          v10 = -1073741801;
          v29 = _DBG_BASENAME(v27);
          WPPTraceLogA("0x%08x %s:%u : %s:%ws", v26, v29, 349, "AllocFn", &dword_180021D0C);
        }
      }
      else
      {
        v10 = -1073741675;
        v25 = _DBG_BASENAME(v24);
        WPPTraceLogA("0x%08x %s:%u : %s:%ws", v26, v25, 342, "RtlUShortAdd", &dword_180021D0C);
      }
      v7 = a2;
    }
    v32 = v19;
    if ( v15 )
    {
      do
      {
        *v32++ = 0;
        --v16;
      }
      while ( v16 );
    }
    ((void (__fastcall *)(_DWORD *))v7)(v19);
  }
  else
  {
    v10 = -1073741801;
    v20 = _DBG_BASENAME(v18);
    WPPTraceLogA("0x%08x %s:%u : %s:%ws", v14, v20, 323, "AllocFn", &dword_180021D0C);
  }
  return v10;
}

```

## disassembly

```asm
0x18000ec9c  mov     [rsp+arg_8], rdx
0x18000eca1  push    rbx
0x18000eca2  push    rbp
0x18000eca3  push    rsi
0x18000eca4  push    rdi
0x18000eca5  push    r12
0x18000eca7  push    r13
0x18000eca9  push    r14
0x18000ecab  push    r15
0x18000ecad  sub     rsp, 38h
0x18000ecb1  mov     rax, [rsp+78h+arg_20]
0x18000ecb9  mov     r12d, 2Ch ; ','
0x18000ecbf  mov     r14, r9
0x18000ecc2  mov     rdi, r8
0x18000ecc5  mov     r15, rdx
0x18000ecc8  mov     r13, rcx
0x18000eccb  mov     qword ptr [rax], 0
0x18000ecd2  movzx   eax, word ptr [r9+3Ch]
0x18000ecd7  add     ax, r12w
0x18000ecdb  cmp     ax, r12w
0x18000ecdf  jnb     short loc_18000ED24
0x18000ece1  mov     r10d, 0C0000095h
0x18000ece7  mov     edi, r10d
0x18000ecea  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ecef  mov     r9d, 13Ah
0x18000ecf5  mov     r8, rax
0x18000ecf8  lea     rax, dword_180021D0C
0x18000ecff  mov     [rsp+78h+var_50], rax
0x18000ed04  lea     rax, aRtlushortadd; "RtlUShortAdd"
0x18000ed0b  mov     edx, r10d
0x18000ed0e  mov     [rsp+78h+var_58], rax
0x18000ed13  lea     rcx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ed1a  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ed1f  jmp     loc_18000EF3A
0x18000ed24  movzx   esi, ax
0x18000ed27  add     si, [r8]
0x18000ed2b  cmp     si, ax
0x18000ed2e  jnb     short loc_18000ED46
0x18000ed30  mov     r10d, 0C0000095h
0x18000ed36  mov     edi, r10d
0x18000ed39  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ed3e  mov     r9d, 13Dh
0x18000ed44  jmp     short loc_18000ECF5
0x18000ed46  movzx   ebp, si
0x18000ed49  mov     rax, r13
0x18000ed4c  mov     ecx, ebp
0x18000ed4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed53  mov     rbx, rax
0x18000ed56  test    rax, rax
0x18000ed59  jnz     short loc_18000ED87
0x18000ed5b  mov     r10d, 0C0000017h
0x18000ed61  mov     edi, r10d
0x18000ed64  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ed69  mov     r8, rax
0x18000ed6c  mov     r9d, 143h
0x18000ed72  lea     rax, dword_180021D0C
0x18000ed79  mov     [rsp+78h+var_50], rax
0x18000ed7e  lea     rax, aAllocfn; "AllocFn"
0x18000ed85  jmp     short loc_18000ED0B
0x18000ed87  mov     r8, rbp; Size
0x18000ed8a  xor     edx, edx; Val
0x18000ed8c  mov     rcx, rbx; void *
0x18000ed8f  call    memset_0
0x18000ed94  mov     eax, [r14+38h]
0x18000ed98  lea     rcx, [rbx+2Ch]; void *
0x18000ed9c  or      eax, 4
0x18000ed9f  mov     [rbx+8], eax
0x18000eda2  movzx   eax, word ptr [r14+3Ch]
0x18000eda7  mov     [rbx+10h], ax
0x18000edab  mov     r8d, eax; Size
0x18000edae  mov     [rbx+0Ch], r12d
0x18000edb2  mov     rdx, [r14+40h]; Src
0x18000edb6  call    memcpy_0
0x18000edbb  movzx   edx, word ptr [rbx+10h]
0x18000edbf  add     edx, [rbx+0Ch]
0x18000edc2  movzx   eax, word ptr [rdi]
0x18000edc5  mov     [rbx+18h], ax
0x18000edc9  cmp     edx, [rbx+0Ch]
0x18000edcc  jb      loc_18000EED6
0x18000edd2  mov     ecx, edx
0x18000edd4  mov     [rbx+14h], edx
0x18000edd7  add     rcx, rbx; void *
0x18000edda  movzx   r8d, word ptr [rbx+18h]; Size
0x18000eddf  mov     rdx, [rdi+8]; Src
0x18000ede3  call    memcpy_0
0x18000ede8  mov     eax, 1Ch
0x18000eded  lea     r15d, [rax+rsi]
0x18000edf1  cmp     r15w, ax
0x18000edf5  jnb     short loc_18000EE42
0x18000edf7  mov     r10d, 0C0000095h
0x18000edfd  mov     edi, r10d
0x18000ee00  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ee05  mov     r8, rax
0x18000ee08  mov     r9d, 156h
0x18000ee0e  lea     rax, dword_180021D0C
0x18000ee15  mov     [rsp+78h+var_50], rax
0x18000ee1a  lea     rax, aRtlushortadd; "RtlUShortAdd"
0x18000ee21  mov     edx, r10d
0x18000ee24  mov     [rsp+78h+var_58], rax
0x18000ee29  lea     rcx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ee30  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ee35  mov     r15, [rsp+78h+arg_8]
0x18000ee3d  jmp     loc_18000EF1B
0x18000ee42  movzx   r12d, r15w
0x18000ee46  mov     rax, r13
0x18000ee49  mov     ecx, r12d
0x18000ee4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee51  mov     r14, rax
0x18000ee54  mov     rax, [rsp+78h+arg_20]
0x18000ee5c  mov     [rax], r14
0x18000ee5f  test    r14, r14
0x18000ee62  jnz     short loc_18000EE90
0x18000ee64  mov     r10d, 0C0000017h
0x18000ee6a  mov     edi, r10d
0x18000ee6d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ee72  mov     r8, rax
0x18000ee75  mov     r9d, 15Dh
0x18000ee7b  lea     rax, dword_180021D0C
0x18000ee82  mov     [rsp+78h+var_50], rax
0x18000ee87  lea     rax, aAllocfn; "AllocFn"
0x18000ee8e  jmp     short loc_18000EE21
0x18000ee90  mov     r8, r12; Size
0x18000ee93  xor     edx, edx; Val
0x18000ee95  mov     rcx, r14; void *
0x18000ee98  xor     edi, edi
0x18000ee9a  call    memset_0
0x18000ee9f  movups  xmm0, cs:SEC_WINNT_AUTH_DATA_TYPE_NGC
0x18000eea6  lea     eax, [rdi+1Ch]
0x18000eea9  movzx   r8d, si; Size
0x18000eead  mov     [r14], ax
0x18000eeb1  lea     rcx, [r14+1Ch]; void *
0x18000eeb5  mov     [r14+2], r15w
0x18000eeba  mov     rdx, rbx; Src
0x18000eebd  movdqu  xmmword ptr [r14+4], xmm0
0x18000eec3  mov     [r14+18h], si
0x18000eec8  mov     [r14+14h], eax
0x18000eecc  call    memcpy_0
0x18000eed1  jmp     loc_18000EE35
0x18000eed6  mov     r10d, 0C0000095h
0x18000eedc  mov     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000eee3  mov     edi, r10d
0x18000eee6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000eeeb  mov     r8, rax
0x18000eeee  lea     rcx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000eef5  lea     rax, dword_180021D0C
0x18000eefc  mov     r9d, 150h
0x18000ef02  mov     [rsp+78h+var_50], rax
0x18000ef07  mov     edx, r10d
0x18000ef0a  lea     rax, aRtlulongadd; "RtlULongAdd"
0x18000ef11  mov     [rsp+78h+var_58], rax
0x18000ef16  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ef1b  mov     rax, rbx
0x18000ef1e  test    rbp, rbp
0x18000ef21  jz      short loc_18000EF2F
0x18000ef23  mov     byte ptr [rax], 0
0x18000ef26  inc     rax
0x18000ef29  sub     rbp, 1
0x18000ef2d  jnz     short loc_18000EF23
0x18000ef2f  mov     rcx, rbx
0x18000ef32  mov     rax, r15
0x18000ef35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef3a  mov     eax, edi
0x18000ef3c  add     rsp, 38h
0x18000ef40  pop     r15
0x18000ef42  pop     r14
0x18000ef44  pop     r13
0x18000ef46  pop     r12
0x18000ef48  pop     rdi
0x18000ef49  pop     rsi
0x18000ef4a  pop     rbp
0x18000ef4b  pop     rbx
0x18000ef4c  retn
```
