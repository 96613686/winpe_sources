# CADMCOMW::GetAllData(ulong,ushort const *,ulong,ulong,ulong,ulong *,ulong *,ulong,uchar *,ulong *)

- ea: `0x180005290`
- end: `0x18000550d`
- name: `?GetAllData@CADMCOMW@@UEAAJKPEBGKKKPEAK1KPEAE1@Z`
- size: `637`
- prototype: `__int64 __usercall@<rax>(CADMCOMW *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005290`
- `0x180006e44`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetAllData(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int *a11)
{
  unsigned int *v11; // r12
  __int64 v14; // rsi
  unsigned __int8 *v15; // rbx
  unsigned int v16; // r15d
  char v17; // al
  unsigned int v18; // edi
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // edx
  unsigned int v23; // edi
  __int64 v24; // r14
  int v25; // r12d
  __int64 v26; // rdx
  unsigned __int8 *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned __int8 *i; // rcx
  unsigned int v33; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v34; // [rsp+64h] [rbp-1Ch] BYREF
  int v35; // [rsp+68h] [rbp-18h] BYREF
  int v36; // [rsp+6Ch] [rbp-14h] BYREF
  __int64 v37; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v40; // [rsp+100h] [rbp+80h]

  v11 = a7;
  v34 = 0;
  v35 = 0;
  v33 = 0;
  v36 = 0;
  if ( !a7 )
    return (unsigned int)-2147024809;
  v14 = a9;
  v15 = a10;
  if ( a9 )
  {
    if ( !a10 )
      return (unsigned int)-2147024809;
  }
  if ( (a4 & 8) != 0 || (a4 & 3) == 2 || a6 >= 6 )
    return (unsigned int)-2147024809;
  *a7 = 0;
  v16 = CADMCOMW::LookupAndAccessCheck(this, a2, &v34, (__int64)a3, 1u, 0, 0, (__int64)&v35, &v37, &v36, 0);
  if ( (v16 & 0x80000000) == 0 )
  {
    v17 = a4;
    v18 = a4 | 0x20;
    LODWORD(v37) = v17 & 0x20;
    if ( !v35 )
      v18 |= 0x100u;
    v19 = *((_QWORD *)this + 101);
    if ( v19 && v36 == 1 )
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, unsigned int, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *))(*(_QWORD *)v19 + 56LL))(
              v19,
              v34,
              a3,
              v18,
              a5,
              a6,
              &v33,
              a8,
              a9,
              a10,
              a11);
    else
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, unsigned int, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *))(**((_QWORD **)this + 4) + 216LL))(
              *((_QWORD *)this + 4),
              v34,
              a3,
              v18,
              a5,
              a6,
              &v33,
              a8,
              a9,
              a10,
              a11);
    v40 = v20;
    v16 = v20;
    if ( v20 < 0 )
    {
      if ( a10 )
      {
        v21 = v14;
        if ( (_DWORD)v14 )
        {
          do
          {
            *v15++ = 0;
            --v21;
          }
          while ( v21 );
        }
      }
      return v16;
    }
    v22 = v33;
    v23 = 0;
    v24 = 0;
    if ( !v33 )
      goto LABEL_36;
    v25 = v37;
    while ( 1 )
    {
      if ( (a10[4] & 4) == 0 )
        goto LABEL_27;
      if ( !(unsigned int)CADMCOMW::IsReadAccessGranted(this, a2, a3, (struct _METADATA_RECORD *)&a10[40 * v24]) )
        break;
      v26 = *(unsigned int *)&a10[28 * (unsigned int)v24 + 16];
      v27 = &a10[*(unsigned int *)&a10[28 * (unsigned int)v24 + 20]];
      if ( *(_DWORD *)&a10[28 * (unsigned int)v24 + 16] )
      {
        do
        {
          *v27++ = 0;
          --v26;
        }
        while ( v26 );
      }
      v22 = v33;
LABEL_32:
      v24 = (unsigned int)(v24 + 1);
      if ( (unsigned int)v24 >= v22 )
      {
        v16 = v40;
        v11 = a7;
        if ( v23 < v22 )
        {
          v30 = 28LL * (v22 - v23);
          for ( i = &a10[28 * v23]; v30; --v30 )
            *i++ = 0;
        }
LABEL_36:
        *v11 = v23;
        return v16;
      }
    }
    v22 = v33;
LABEL_27:
    v28 = 28LL * (unsigned int)v24;
    if ( !v25 )
      *(_DWORD *)&a10[v28 + 4] &= ~0x20u;
    if ( (_DWORD)v24 != v23 )
    {
      v29 = 28LL * v23;
      *(_OWORD *)&a10[v29] = *(_OWORD *)&a10[v28];
      *(_OWORD *)&a10[v29 + 12] = *(_OWORD *)&a10[v28 + 12];
    }
    ++v23;
    goto LABEL_32;
  }
  return v16;
}

```

## disassembly

```asm
0x180005290  mov     [rsp-38h+arg_0], rbx
0x180005295  mov     [rsp-38h+arg_10], r8
0x18000529a  mov     [rsp-38h+arg_8], edx
0x18000529e  push    rbp
0x18000529f  push    rsi
0x1800052a0  push    rdi
0x1800052a1  push    r12
0x1800052a3  push    r13
0x1800052a5  push    r14
0x1800052a7  push    r15
0x1800052a9  mov     rbp, rsp
0x1800052ac  sub     rsp, 80h
0x1800052b3  mov     r12, [rbp+arg_30]
0x1800052b7  mov     r13, rcx
0x1800052ba  xor     ecx, ecx
0x1800052bc  mov     edi, r9d
0x1800052bf  mov     [rbp+var_1C], ecx
0x1800052c2  mov     [rbp+var_18], ecx
0x1800052c5  mov     [rbp+var_20], ecx
0x1800052c8  mov     [rbp+var_14], ecx
0x1800052cb  test    r12, r12
0x1800052ce  jz      loc_1800054E9
0x1800052d4  mov     esi, [rbp+arg_40]
0x1800052da  mov     rbx, [rbp+arg_48]
0x1800052e1  test    esi, esi
0x1800052e3  jz      short loc_1800052EE
0x1800052e5  test    rbx, rbx
0x1800052e8  jz      loc_1800054E9
0x1800052ee  test    dil, 8
0x1800052f2  jnz     loc_1800054E9
0x1800052f8  mov     eax, edi
0x1800052fa  and     al, 3
0x1800052fc  cmp     al, 2
0x1800052fe  jz      loc_1800054E9
0x180005304  mov     r14d, [rbp+arg_28]
0x180005308  cmp     r14d, 6
0x18000530c  jnb     loc_1800054E9
0x180005312  mov     [rsp+80h+var_30], rcx
0x180005317  lea     rax, [rbp+var_14]
0x18000531b  mov     [rsp+80h+var_38], rax
0x180005320  mov     r9, r8
0x180005323  lea     rax, [rbp+var_10]
0x180005327  mov     [r12], ecx
0x18000532b  mov     [rsp+80h+var_40], rax
0x180005330  lea     r8, [rbp+var_1C]
0x180005334  lea     rax, [rbp+var_18]
0x180005338  mov     [rsp+80h+var_48], rax
0x18000533d  mov     [rsp+80h+var_50], rcx
0x180005342  mov     [rsp+80h+var_58], ecx
0x180005346  mov     rcx, r13
0x180005349  mov     [rsp+80h+var_60], 1
0x180005351  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180005356  mov     r15d, eax
0x180005359  test    eax, eax
0x18000535b  js      loc_1800054EF
0x180005361  mov     eax, edi
0x180005363  or      edi, 20h
0x180005366  and     eax, 20h
0x180005369  cmp     [rbp+var_18], 0
0x18000536d  mov     dword ptr [rbp+var_10], eax
0x180005370  jnz     short loc_180005376
0x180005372  bts     edi, 8
0x180005376  mov     rcx, [r13+328h]
0x18000537d  test    rcx, rcx
0x180005380  jz      short loc_180005391
0x180005382  cmp     [rbp+var_14], 1
0x180005386  jnz     short loc_180005391
0x180005388  mov     rax, [rcx]
0x18000538b  mov     rax, [rax+38h]
0x18000538f  jmp     short loc_18000539F
0x180005391  mov     rcx, [r13+20h]
0x180005395  mov     rax, [rcx]
0x180005398  mov     rax, [rax+0D8h]
0x18000539f  mov     rdx, [rbp+arg_50]
0x1800053a6  mov     r9d, edi
0x1800053a9  mov     r8, [rbp+arg_10]
0x1800053ad  mov     [rsp+80h+var_30], rdx
0x1800053b2  mov     rdx, [rbp+arg_38]
0x1800053b6  mov     [rsp+80h+var_38], rbx
0x1800053bb  mov     dword ptr [rsp+80h+var_40], esi
0x1800053bf  mov     [rsp+80h+var_48], rdx
0x1800053c4  lea     rdx, [rbp+var_20]
0x1800053c8  mov     [rsp+80h+var_50], rdx
0x1800053cd  mov     edx, [rbp+arg_20]
0x1800053d0  mov     [rsp+80h+var_58], r14d
0x1800053d5  mov     [rsp+80h+var_60], edx
0x1800053d9  mov     edx, [rbp+var_1C]
0x1800053dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e1  mov     [rbp+arg_40], eax
0x1800053e7  mov     r15d, eax
0x1800053ea  test    eax, eax
0x1800053ec  jns     short loc_180005413
0x1800053ee  test    rbx, rbx
0x1800053f1  jz      loc_1800054EF
0x1800053f7  mov     rax, rsi
0x1800053fa  test    esi, esi
0x1800053fc  jz      loc_1800054EF
0x180005402  mov     byte ptr [rbx], 0
0x180005405  inc     rbx
0x180005408  sub     rax, 1
0x18000540c  jnz     short loc_180005402
0x18000540e  jmp     loc_1800054EF
0x180005413  mov     edx, [rbp+var_20]
0x180005416  xor     edi, edi
0x180005418  xor     r14d, r14d
0x18000541b  test    edx, edx
0x18000541d  jz      loc_1800054E3
0x180005423  mov     r12d, dword ptr [rbp+var_10]
0x180005427  mov     r15, [rbp+arg_10]
0x18000542b  test    byte ptr [rbx+4], 4
0x18000542f  mov     esi, r14d
0x180005432  jz      short loc_180005476
0x180005434  mov     edx, [rbp+arg_8]; unsigned int
0x180005437  lea     rax, [r14+r14*4]
0x18000543b  lea     r9, [rbx+rax*8]; struct _METADATA_RECORD *
0x18000543f  mov     r8, r15; unsigned __int16 *
0x180005442  mov     rcx, r13; this
0x180005445  call    ?IsReadAccessGranted@CADMCOMW@@QEAAJKPEBGPEAU_METADATA_RECORD@@@Z; CADMCOMW::IsReadAccessGranted(ulong,ushort const *,_METADATA_RECORD *)
0x18000544a  test    eax, eax
0x18000544c  jz      short loc_180005473
0x18000544e  imul    rax, rsi, 1Ch
0x180005452  mov     ecx, [rax+rbx+14h]
0x180005456  mov     edx, [rax+rbx+10h]
0x18000545a  add     rcx, rbx
0x18000545d  test    rdx, rdx
0x180005460  jz      short loc_18000546E
0x180005462  mov     byte ptr [rcx], 0
0x180005465  inc     rcx
0x180005468  sub     rdx, 1
0x18000546c  jnz     short loc_180005462
0x18000546e  mov     edx, [rbp+var_20]
0x180005471  jmp     short loc_1800054A6
0x180005473  mov     edx, [rbp+var_20]
0x180005476  imul    r8, rsi, 1Ch
0x18000547a  test    r12d, r12d
0x18000547d  jnz     short loc_180005485
0x18000547f  and     dword ptr [r8+rbx+4], 0FFFFFFDFh
0x180005485  cmp     r14d, edi
0x180005488  jz      short loc_1800054A4
0x18000548a  movups  xmm0, xmmword ptr [r8+rbx]
0x18000548f  mov     eax, edi
0x180005491  imul    rcx, rax, 1Ch
0x180005495  movups  xmmword ptr [rcx+rbx], xmm0
0x180005499  movups  xmm1, xmmword ptr [r8+rbx+0Ch]
0x18000549f  movups  xmmword ptr [rcx+rbx+0Ch], xmm1
0x1800054a4  inc     edi
0x1800054a6  inc     r14d
0x1800054a9  cmp     r14d, edx
0x1800054ac  jb      loc_18000542B
0x1800054b2  mov     r15d, [rbp+arg_40]
0x1800054b9  mov     r12, [rbp+arg_30]
0x1800054bd  cmp     edi, edx
0x1800054bf  jnb     short loc_1800054E3
0x1800054c1  sub     edx, edi
0x1800054c3  mov     eax, edx
0x1800054c5  imul    rdx, rax, 1Ch
0x1800054c9  mov     eax, edi
0x1800054cb  imul    rcx, rax, 1Ch
0x1800054cf  add     rcx, rbx
0x1800054d2  test    rdx, rdx
0x1800054d5  jz      short loc_1800054E3
0x1800054d7  mov     byte ptr [rcx], 0
0x1800054da  inc     rcx
0x1800054dd  sub     rdx, 1
0x1800054e1  jnz     short loc_1800054D7
0x1800054e3  mov     [r12], edi
0x1800054e7  jmp     short loc_1800054EF
0x1800054e9  mov     r15d, 80070057h
0x1800054ef  mov     rbx, [rsp+80h+arg_0]
0x1800054f7  mov     eax, r15d
0x1800054fa  add     rsp, 80h
0x180005501  pop     r15
0x180005503  pop     r14
0x180005505  pop     r13
0x180005507  pop     r12
0x180005509  pop     rdi
0x18000550a  pop     rsi
0x18000550b  pop     rbp
0x18000550c  retn
```
