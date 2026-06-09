# CExposedStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180015b70`
- end: `0x180015f26`
- name: `?Stat@CExposedStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `950`
- prototype: `__int64 __fastcall(CExposedStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015b70`
- `0x180015f30`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015d8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015d8a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f1b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015e75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015e75`

## pseudocode

```c
__int64 __fastcall CExposedStream::Stat(CExposedStream *this, struct tagSTATSTG *a2, int a3)
{
  _QWORD *v3; // rsi
  __int128 v4; // xmm6
  char v5; // bp
  int v9; // r14d
  _QWORD *v10; // rcx
  __int64 v11; // rdi
  int v12; // r8d
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int64 v26; // rdx
  __int64 v27; // r8
  _QWORD *v28; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v30; // rcx
  bool v31; // zf
  __int64 v32; // rax
  __int64 v33; // rax
  void *v34; // rax
  __int64 v35; // rax
  __int64 v36; // r9
  int v37; // r10d
  int v38; // ecx
  int v39; // [rsp+20h] [rbp-A8h] BYREF
  _QWORD *v40; // [rsp+28h] [rbp-A0h]
  __int128 v41; // [rsp+30h] [rbp-98h]
  __int128 v42; // [rsp+40h] [rbp-88h]
  __int128 v43; // [rsp+50h] [rbp-78h]
  _OWORD v44[2]; // [rsp+70h] [rbp-58h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 15);
  v4 = 0;
  v5 = a3;
  v39 = -2147286784;
  v40 = v3;
  v42 = 0;
  v43 = 0;
  memset(v44, 0, sizeof(v44));
  v41 = 0;
  if ( !a2 )
    return 2147680265LL;
  if ( (a3 & 0xFFFFFFFE) == 0 )
  {
    v33 = *((_QWORD *)this + 8) - *(_QWORD *)&GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data1;
    if ( !v33 )
      v33 = *((_QWORD *)this + 9) - *(_QWORD *)GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data4;
    if ( v33 )
      return (unsigned int)-2147287034;
    v9 = CSafeSem::Take((CSafeSem *)&v39);
    if ( v9 < 0 )
    {
LABEL_26:
      v26 = *((_QWORD *)&v41 + 1);
      if ( *((_QWORD *)&v41 + 1) )
      {
        v27 = v41;
        if ( (_QWORD)v41 )
        {
          v35 = *(_QWORD *)(v41 + 88);
          v36 = *(_QWORD *)(v41 + 96);
          v37 = *(_DWORD *)(v41 + 104);
          *(_QWORD *)(*((_QWORD *)&v41 + 1) + 8LL) = v35;
          *(_QWORD *)(v26 + 16) = v36;
          if ( v35 )
            v38 = *(_DWORD *)(v35 + 16) - 24;
          else
            v38 = 0;
          *(_DWORD *)(v26 + 32) = v38;
          *(_DWORD *)(v26 + 36) = v37;
          *(_QWORD *)NtCurrentTeb()->ReservedForOle = v36;
          *(_QWORD *)(v26 + 24) = v27;
        }
        else
        {
          *(_QWORD *)(*((_QWORD *)&v41 + 1) + 8LL) = 0;
          *(_QWORD *)(v26 + 16) = 0;
          *(_QWORD *)(v26 + 32) = 0;
          *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
          *(_QWORD *)(v26 + 24) = 0;
        }
      }
      if ( v39 >= 0 )
      {
        v28 = v40;
        CurrentThreadId = GetCurrentThreadId();
        v30 = v28[14];
        if ( *(_DWORD *)(v30 + 8) == CurrentThreadId )
        {
          v31 = (*(_DWORD *)(v30 + 4))-- == 1;
          v32 = v28[14];
          if ( v31 )
          {
            *(_DWORD *)(v32 + 8) = 0;
            if ( _InterlockedDecrement((volatile signed __int32 *)v28[14]) >= 0 )
              SetEvent((HANDLE)v28[15]);
          }
          else
          {
            _InterlockedDecrement((volatile signed __int32 *)v32);
          }
        }
      }
      return (unsigned int)v9;
    }
    v10 = (_QWORD *)*((_QWORD *)this + 14);
    v10[4] = v3[2];
    v10[5] = v3[3];
    v10[6] = v3[4];
    v11 = *((_QWORD *)this + 13);
    v12 = *(_DWORD *)(v11 + 20);
    if ( (v12 & 0x20) != 0 )
    {
      v9 = -2147286782;
    }
    else
    {
      v13 = *(_DWORD *)(v11 + 20) & 0x80;
      if ( (v12 & 0x40) != 0 )
        v14 = v13 != 0 ? 2 : 0;
      else
        v14 = v13 != 0;
      if ( (v12 & 0x100) != 0 )
      {
        v15 = 16;
        if ( (v12 & 0x200) == 0 )
          v15 = 48;
      }
      else
      {
        v15 = 64;
        if ( (v12 & 0x200) != 0 )
          v15 = 32;
      }
      v16 = v15 | v14;
      *(_QWORD *)&v42 = 0;
      v17 = v16 | 0x10000;
      memset((char *)v44 + 8, 0, 20);
      if ( (v12 & 2) == 0 )
        v17 = v16;
      v18 = v17 | 0x40000;
      if ( (v12 & 0x400) == 0 )
        v18 = v17;
      v19 = v18 | 0x100000;
      if ( (v12 & 0x4000) == 0 )
        v19 = v18;
      v20 = v19 | 0x200000;
      if ( (v12 & 0x40000) == 0 )
        v20 = v19;
      LODWORD(v44[0]) = v20;
      if ( (v5 & 1) != 0 )
        goto LABEL_19;
      v34 = CoTaskMemAlloc(*(unsigned __int16 *)(v11 + 88));
      *(_QWORD *)&v42 = v34;
      if ( v34 )
      {
        memcpy_0(v34, (const void *)(v11 + 24), *(unsigned __int16 *)(v11 + 88));
LABEL_19:
        v21 = *(_QWORD *)(v11 + 104);
        v9 = 0;
        if ( v21 )
          v22 = v21 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
        else
          v22 = 0;
        if ( *(_DWORD *)v22 == 1381258052 )
        {
          v23 = *(_QWORD *)(v22 + 176);
        }
        else
        {
          v23 = 0;
          if ( *(_DWORD *)v22 == 1381258068 )
            v23 = *(_QWORD *)(v22 + 112);
        }
        *(_QWORD *)&v43 = v23;
        v4 = v43;
        goto LABEL_24;
      }
      v9 = -2147287032;
    }
LABEL_24:
    if ( v9 >= 0 )
    {
      v24 = v44[1];
      *(_OWORD *)a2 = v42;
      v25 = v44[0];
      *((_OWORD *)a2 + 1) = v4;
      *((_OWORD *)a2 + 2) = 0;
      *((_OWORD *)a2 + 3) = v25;
      *((_OWORD *)a2 + 4) = v24;
      *((_DWORD *)a2 + 2) = 2;
      *((_DWORD *)a2 + 13) = 0;
      *((_DWORD *)a2 + 19) = 0;
      *((_QWORD *)a2 + 4) = 0;
      *((_QWORD *)a2 + 3) = 0;
      *((_QWORD *)a2 + 5) = 0;
    }
    goto LABEL_26;
  }
  return 2147680511LL;
}

```

## disassembly

```asm
0x180015b70  mov     rax, rsp
0x180015b73  mov     [rax+20h], rbx
0x180015b77  push    rbp
0x180015b78  push    rsi
0x180015b79  push    rdi
0x180015b7a  sub     rsp, 0B0h
0x180015b81  mov     rsi, [rcx+78h]
0x180015b85  xorps   xmm0, xmm0
0x180015b88  movaps  xmmword ptr [rax-28h], xmm6
0x180015b8c  xorps   xmm6, xmm6
0x180015b8f  movaps  xmmword ptr [rax-38h], xmm7
0x180015b93  mov     ebp, r8d
0x180015b96  mov     [rsp+0C8h+var_A8], 80030100h
0x180015b9e  mov     rbx, rdx
0x180015ba1  mov     [rsp+0C8h+var_A0], rsi
0x180015ba6  mov     rdi, rcx
0x180015ba9  xorps   xmm7, xmm7
0x180015bac  movups  [rsp+0C8h+var_88], xmm6
0x180015bb1  movaps  xmmword ptr [rax-78h], xmm6
0x180015bb5  movups  xmmword ptr [rax-58h], xmm6
0x180015bb9  movups  xmmword ptr [rax-48h], xmm6
0x180015bbd  movdqu  [rsp+0C8h+var_98], xmm0
0x180015bc3  test    rdx, rdx
0x180015bc6  jnz     loc_180015DF1
0x180015bcc  mov     eax, 80030009h
0x180015bd1  jmp     loc_180015DD4
0x180015bd6  lea     rcx, [rsp+0C8h+var_A8]; this
0x180015bdb  call    ?Take@CSafeSem@@QEAAJXZ; CSafeSem::Take(void)
0x180015be0  xor     r15d, r15d
0x180015be3  mov     r14d, eax
0x180015be6  test    eax, eax
0x180015be8  js      loc_180015D43
0x180015bee  mov     rcx, [rdi+70h]
0x180015bf2  mov     rax, [rsi+10h]
0x180015bf6  mov     [rcx+20h], rax
0x180015bfa  mov     rax, [rsi+18h]
0x180015bfe  mov     [rcx+28h], rax
0x180015c02  mov     rax, [rsi+20h]
0x180015c06  mov     [rcx+30h], rax
0x180015c0a  mov     rdi, [rdi+68h]
0x180015c0e  mov     r8d, [rdi+14h]
0x180015c12  test    r8b, 20h
0x180015c16  jnz     loc_180015E48
0x180015c1c  mov     eax, r8d
0x180015c1f  and     eax, 80h
0x180015c24  test    r8b, 40h
0x180015c28  jz      loc_180015E36
0x180015c2e  neg     eax
0x180015c30  sbb     edx, edx
0x180015c32  and     edx, 2
0x180015c35  mov     eax, r8d
0x180015c38  and     eax, 200h
0x180015c3d  bt      r8d, 8
0x180015c42  jnb     loc_180015E53
0x180015c48  test    eax, eax
0x180015c4a  mov     ecx, 10h
0x180015c4f  mov     r9d, 30h ; '0'
0x180015c55  cmovz   ecx, r9d
0x180015c59  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180015c60  or      edx, ecx
0x180015c62  mov     [rsp+0C8h+var_40], r15d
0x180015c6a  mov     ecx, edx
0x180015c6c  mov     qword ptr [rsp+0C8h+var_88], r15
0x180015c71  bts     ecx, 10h
0x180015c75  test    r8b, 2
0x180015c79  movups  [rsp+0C8h+var_58+8], xmm0
0x180015c7e  cmovz   ecx, edx
0x180015c81  mov     edx, ecx
0x180015c83  bts     edx, 12h
0x180015c87  bt      r8d, 0Ah
0x180015c8c  cmovnb  edx, ecx
0x180015c8f  mov     ecx, edx
0x180015c91  bts     ecx, 14h
0x180015c95  bt      r8d, 0Eh
0x180015c9a  cmovnb  ecx, edx
0x180015c9d  mov     eax, ecx
0x180015c9f  bts     eax, 15h
0x180015ca3  bt      r8d, 12h
0x180015ca8  cmovnb  eax, ecx
0x180015cab  mov     dword ptr [rsp+0C8h+var_58], eax
0x180015caf  test    bpl, 1
0x180015cb3  jz      loc_180015E71
0x180015cb9  mov     rdx, [rdi+68h]
0x180015cbd  mov     r14d, r15d
0x180015cc0  test    rdx, rdx
0x180015cc3  jz      loc_180015F00
0x180015cc9  mov     rax, gs:30h
0x180015cd2  mov     rcx, [rax+1758h]
0x180015cd9  mov     rcx, [rcx]
0x180015cdc  add     rcx, rdx
0x180015cdf  mov     edx, [rcx]
0x180015ce1  cmp     edx, 52545344h
0x180015ce7  jnz     loc_180015E9B
0x180015ced  mov     rax, [rcx+0B0h]
0x180015cf4  mov     qword ptr [rsp+0C8h+var_78], rax
0x180015cf9  movaps  xmm6, [rsp+0C8h+var_78]
0x180015cfe  test    r14d, r14d
0x180015d01  js      short loc_180015D43
0x180015d03  movaps  xmm0, [rsp+0C8h+var_88]
0x180015d08  movaps  xmm1, xmmword ptr [rsp+80h]
0x180015d10  movups  xmmword ptr [rbx], xmm0
0x180015d13  movaps  xmm0, [rsp+0C8h+var_58]
0x180015d18  movups  xmmword ptr [rbx+10h], xmm6
0x180015d1c  movups  xmmword ptr [rbx+20h], xmm7
0x180015d20  movups  xmmword ptr [rbx+30h], xmm0
0x180015d24  movups  xmmword ptr [rbx+40h], xmm1
0x180015d28  mov     dword ptr [rbx+8], 2
0x180015d2f  mov     [rbx+34h], r15d
0x180015d33  mov     [rbx+4Ch], r15d
0x180015d37  mov     [rbx+20h], r15
0x180015d3b  mov     [rbx+18h], r15
0x180015d3f  mov     [rbx+28h], r15
0x180015d43  mov     rdx, qword ptr [rsp+0C8h+var_98+8]
0x180015d48  test    rdx, rdx
0x180015d4b  jz      short loc_180015D7E
0x180015d4d  mov     r8, qword ptr [rsp+0C8h+var_98]
0x180015d52  test    r8, r8
0x180015d55  jnz     loc_180015EB3
0x180015d5b  mov     [rdx+8], r15
0x180015d5f  mov     [rdx+10h], r15
0x180015d63  mov     [rdx+20h], r15
0x180015d67  mov     rax, gs:30h
0x180015d70  mov     rcx, [rax+1758h]
0x180015d77  mov     [rcx], r15
0x180015d7a  mov     [rdx+18h], r15
0x180015d7e  cmp     [rsp+0C8h+var_A8], r15d
0x180015d83  jl      short loc_180015DC1
0x180015d85  mov     rbx, [rsp+0C8h+var_A0]
0x180015d8a  call    cs:__imp_GetCurrentThreadId
0x180015d90  mov     rcx, [rbx+70h]
0x180015d94  cmp     [rcx+8], eax
0x180015d97  jnz     short loc_180015DC1
0x180015d99  sub     dword ptr [rcx+4], 1
0x180015d9d  mov     rax, [rbx+70h]
0x180015da1  jnz     loc_180015E69
0x180015da7  mov     [rax+8], r15d
0x180015dab  mov     ecx, 0FFFFFFFFh
0x180015db0  mov     rax, [rbx+70h]
0x180015db4  lock xadd [rax], ecx
0x180015db8  cmp     ecx, 1
0x180015dbb  jns     loc_180015F17
0x180015dc1  mov     r15, [rsp+0C8h+arg_10]
0x180015dc9  mov     eax, r14d
0x180015dcc  mov     r14, [rsp+0C8h+arg_8]
0x180015dd4  lea     r11, [rsp+0C8h+var_18]
0x180015ddc  mov     rbx, [r11+38h]
0x180015de0  movaps  xmm6, xmmword ptr [r11-10h]
0x180015de5  movaps  xmm7, xmmword ptr [r11-20h]
0x180015dea  mov     rsp, r11
0x180015ded  pop     rdi
0x180015dee  pop     rsi
0x180015def  pop     rbp
0x180015df0  retn
0x180015df1  test    ebp, 0FFFFFFFEh
0x180015df7  jnz     loc_180015F0D
0x180015dfd  mov     rax, [rcx+40h]
0x180015e01  sub     rax, qword ptr cs:_GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data1
0x180015e08  mov     [rsp+0C8h+arg_8], r14
0x180015e10  jnz     short loc_180015E1D
0x180015e12  mov     rax, [rcx+48h]
0x180015e16  sub     rax, qword ptr cs:_GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data4
0x180015e1d  mov     [rsp+0C8h+arg_10], r15
0x180015e25  test    rax, rax
0x180015e28  jz      loc_180015BD6
0x180015e2e  mov     r14d, 80030006h
0x180015e34  jmp     short loc_180015DC1
0x180015e36  test    eax, eax
0x180015e38  mov     edx, r15d
0x180015e3b  mov     ecx, 1
0x180015e40  cmovnz  edx, ecx
0x180015e43  jmp     loc_180015C35
0x180015e48  mov     r14d, 80030102h
0x180015e4e  jmp     loc_180015CFE
0x180015e53  test    eax, eax
0x180015e55  mov     ecx, 40h ; '@'
0x180015e5a  mov     r9d, 20h ; ' '
0x180015e60  cmovnz  ecx, r9d
0x180015e64  jmp     loc_180015C59
0x180015e69  lock dec dword ptr [rax]
0x180015e6c  jmp     loc_180015DC1
0x180015e71  movzx   ecx, word ptr [rdi+58h]; cb
0x180015e75  call    cs:__imp_CoTaskMemAlloc
0x180015e7b  mov     qword ptr [rsp+0C8h+var_88], rax
0x180015e80  test    rax, rax
0x180015e83  jz      short loc_180015EF5
0x180015e85  movzx   r8d, word ptr [rdi+58h]; Size
0x180015e8a  lea     rdx, [rdi+18h]; Src
0x180015e8e  mov     rcx, rax; void *
0x180015e91  call    memcpy_0
0x180015e96  jmp     loc_180015CB9
0x180015e9b  mov     rax, r15
0x180015e9e  cmp     edx, 52545354h
0x180015ea4  jnz     loc_180015CF4
0x180015eaa  mov     rax, [rcx+70h]
0x180015eae  jmp     loc_180015CF4
0x180015eb3  mov     rax, [r8+58h]
0x180015eb7  mov     r9, [r8+60h]
0x180015ebb  mov     r10d, [r8+68h]
0x180015ebf  mov     [rdx+8], rax
0x180015ec3  mov     [rdx+10h], r9
0x180015ec7  test    rax, rax
0x180015eca  jz      short loc_180015F08
0x180015ecc  mov     ecx, [rax+10h]
0x180015ecf  sub     ecx, 18h
0x180015ed2  mov     [rdx+20h], ecx
0x180015ed5  mov     [rdx+24h], r10d
0x180015ed9  mov     rax, gs:30h
0x180015ee2  mov     rcx, [rax+1758h]
0x180015ee9  mov     [rcx], r9
0x180015eec  mov     [rdx+18h], r8
0x180015ef0  jmp     loc_180015D7E
0x180015ef5  mov     r14d, 80030008h
0x180015efb  jmp     loc_180015CFE
0x180015f00  mov     rcx, r15
0x180015f03  jmp     loc_180015CDF
0x180015f08  mov     ecx, r15d
0x180015f0b  jmp     short loc_180015ED2
0x180015f0d  mov     eax, 800300FFh
0x180015f12  jmp     loc_180015DD4
0x180015f17  mov     rcx, [rbx+78h]; hEvent
0x180015f1b  call    cs:__imp_SetEvent
0x180015f21  jmp     loc_180015DC1
```
