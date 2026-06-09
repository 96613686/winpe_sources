# ISAPI_REQUEST::ExecuteUrl(unsigned __int64,EXEC_URL_INFO *)

- ea: `0x18000cc50`
- end: `0x18000d1a5`
- name: `?ExecuteUrl@ISAPI_REQUEST@@UEAAJ_KPEAUEXEC_URL_INFO@@@Z`
- size: `1365`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *this, __int64, struct EXEC_URL_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001020`
- `0x18000c728`
- `0x18000cc50`
- `0x18000f91c`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000cefe`
- `msvcrt!_wcsnicmp` at `0x18000cefe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000d169`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000d173`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000d169`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000d173`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000cc97`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000ccad`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000cc97`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000ccad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d155`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d15f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d155`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d15f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cfad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d0c8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cfad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d0c8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d072`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d07f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d072`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d07f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cf77`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cf81`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cf77`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cf81`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ccd4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ccf5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ccd4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ccf5`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000cfb5`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000cfdb`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000cfb5`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000cfdb`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::ExecuteUrl(ISAPI_REQUEST *this, __int64 a2, struct EXEC_URL_INFO *a3)
{
  _DWORD *v6; // rdi
  unsigned int v7; // r8d
  _QWORD *v8; // r15
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // r14d
  unsigned int v13; // ebx
  int v14; // ebx
  char *v15; // rbx
  struct IHttpRequest *v16; // rax
  __int64 (*v17)(void); // rax
  __int64 v18; // rax
  unsigned int *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r12
  __int64 (*v24)(void); // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 (__fastcall *v28)(__int64, __int64, __int64, __int64); // r10
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  const unsigned __int16 *v35; // rdx
  int v36; // eax
  const char *v37; // rdx
  __int64 v38; // rax
  __int64 v39; // r8
  int v40; // eax
  void *v41; // rsi
  __int64 v42; // rax
  const unsigned __int16 *Str; // rbx
  const unsigned __int16 *v44; // rax
  __int64 v45; // rax
  const unsigned __int16 *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rcx
  int v51; // [rsp+40h] [rbp-C0h]
  _BYTE v52[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v53[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v54[56]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v55[56]; // [rsp+F0h] [rbp-10h] BYREF
  char v56[16]; // [rsp+128h] [rbp+28h] BYREF
  _OWORD v57[3]; // [rsp+138h] [rbp+38h] BYREF
  char v58[24]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int16 v59[64]; // [rsp+180h] [rbp+80h] BYREF

  STRA::STRA((STRA *)v55, v56, 0xAu);
  STRA::STRA((STRA *)v54, v58, 0x18u);
  memset_0(v59, 0, sizeof(v59));
  STRU::STRU((STRU *)v53, v59, 0x40u);
  memset(v57, 0, sizeof(v57));
  STRU::STRU((STRU *)v52, (unsigned __int16 *)v57, 0x18u);
  v6 = 0;
  v51 = *((_DWORD *)this + 12);
  if ( !*((_QWORD *)this + 2) )
    *((_QWORD *)this + 2) = a2;
  v7 = *((_DWORD *)a3 + 14);
  v8 = (_QWORD *)((char *)this + 56);
  v9 = (v7 >> 1) & 1 | 8;
  if ( (v7 & 0x20) == 0 )
    v9 = (*((_DWORD *)a3 + 14) >> 1) & 1;
  v10 = v9 | 2;
  if ( (v7 & 4) == 0 )
    v10 = v9;
  v11 = v10 | 0x40;
  if ( (v7 & 0x80u) == 0 )
    v11 = v10;
  v12 = v11 | 0x10;
  if ( *((_QWORD *)a3 + 1) )
    v12 = v11;
  v13 = (*((_QWORD *)a3 + 4) != 0 ? 5 : 7) | 8;
  if ( (v7 & 0x10) == 0 )
    v13 = *((_QWORD *)a3 + 4) != 0 ? 5 : 7;
  if ( *v8 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 256LL))(*v8);
    *v8 = 0;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 3) + 248LL))(
          *((_QWORD *)this + 3),
          v13,
          (char *)this + 56);
  if ( v14 < 0 )
    goto LABEL_56;
  v15 = (char *)*((_QWORD *)a3 + 4);
  if ( v15 )
  {
    v16 = (struct IHttpRequest *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 24LL))(*v8);
    v14 = SetHeadersByStream(v16, v15);
    if ( v14 < 0 )
      goto LABEL_56;
  }
  v17 = *(__int64 (**)(void))(*(_QWORD *)*v8 + 24LL);
  if ( *((_QWORD *)a3 + 6) )
  {
    v18 = v17();
    v19 = (unsigned int *)*((_QWORD *)a3 + 6);
    v20 = *v19;
    v21 = *((_QWORD *)v19 + 1);
  }
  else
  {
    v18 = v17();
    v22 = *((_QWORD *)this + 4);
    v20 = *(unsigned int *)(v22 + 48);
    v21 = *(_QWORD *)(v22 + 56);
  }
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 136LL))(v18, v21, v20);
  if ( v14 < 0 )
    goto LABEL_56;
  v23 = -1;
  if ( *((_QWORD *)a3 + 1) )
  {
    v24 = *(__int64 (**)(void))(*(_QWORD *)*v8 + 24LL);
    if ( *(_DWORD *)a3 )
    {
      v25 = v24();
      v26 = *((_QWORD *)a3 + 1);
      v27 = -1;
      v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v25 + 88LL);
      do
        ++v27;
      while ( *(_WORD *)(v26 + 2 * v27) );
    }
    else
    {
      v25 = v24();
      v26 = *((_QWORD *)a3 + 1);
      v27 = -1;
      v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v25 + 80LL);
      do
        ++v27;
      while ( *(_BYTE *)(v26 + v27) );
    }
    v14 = v28(v25, v26, v27, 1);
    if ( v14 < 0 )
      goto LABEL_56;
    v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 24LL))(*v8);
    v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
    v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
    v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
    if ( *(_WORD *)(v30 + 68) == *(_WORD *)(v32 + 68)
      && !_wcsnicmp(
            *(const wchar_t **)(v30 + 88),
            *(const wchar_t **)(v32 + 88),
            (unsigned __int64)*(unsigned __int16 *)(v30 + 68) >> 1) )
    {
      v12 |= 0x10u;
    }
  }
  if ( !*((_QWORD *)a3 + 3)
    || (v33 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 24LL))(*v8),
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v33 + 72LL))(v33, *((_QWORD *)a3 + 3)),
        v14 >= 0) )
  {
    if ( !*((_QWORD *)a3 + 5) )
    {
LABEL_54:
      v47 = *((_QWORD *)this + 3);
      v48 = *v8;
      *((_DWORD *)this + 12) = 1;
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD *, _QWORD))(*(_QWORD *)v47 + 104LL))(
              v47,
              1,
              v48,
              v12,
              v6,
              0);
      if ( v14 >= 0 )
      {
        v14 = 0;
        goto LABEL_60;
      }
      goto LABEL_53;
    }
    v6 = operator new(0x90u);
    if ( !v6 )
    {
      v14 = -2147024888;
LABEL_53:
      v6 = 0;
      goto LABEL_56;
    }
    *(_QWORD *)v6 = &CUSTOM_USER_CONTEXT::`vftable';
    STRU::STRU((STRU *)(v6 + 4));
    STRU::STRU((STRU *)(v6 + 18));
    v6[2] = 1;
    *((_QWORD *)v6 + 16) = 0;
    *((_QWORD *)v6 + 17) = 0;
    v34 = *((_QWORD *)a3 + 5);
    v35 = *(const unsigned __int16 **)(v34 + 16);
    if ( *(_DWORD *)(v34 + 8) )
      v36 = STRU::Copy((STRU *)v53, v35);
    else
      v36 = STRU::CopyA((STRU *)v53, (const char *)v35);
    v14 = v36;
    if ( v36 < 0 )
      goto LABEL_56;
    v37 = *(const char **)(*((_QWORD *)a3 + 5) + 32LL);
    if ( !v37 )
    {
      v45 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
      v46 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      v40 = STRU::Copy((STRU *)v52, v46);
LABEL_46:
      v14 = v40;
      if ( v40 < 0 )
        goto LABEL_56;
      v41 = (void *)**((_QWORD **)a3 + 5);
      if ( !v41 )
      {
        v42 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
        v41 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 32LL))(v42);
      }
      Str = STRU::QueryStr((STRU *)v52);
      v44 = STRU::QueryStr((STRU *)v53);
      v14 = CUSTOM_USER_CONTEXT::Create((CUSTOM_USER_CONTEXT *)v6, v41, v44, Str);
      if ( v14 < 0 )
        goto LABEL_56;
      goto LABEL_54;
    }
    v14 = STRU::CopyA((STRU *)v52, v37);
    if ( v14 >= 0 )
    {
      v38 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 24LL))(*v8);
      v39 = *(_QWORD *)(*((_QWORD *)a3 + 5) + 32LL);
      do
        ++v23;
      while ( *(_BYTE *)(v39 + v23) );
      v40 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int))(*(_QWORD *)v38 + 32LL))(
              v38,
              24,
              v39,
              (unsigned __int16)v23,
              1);
      goto LABEL_46;
    }
  }
LABEL_56:
  v49 = *v8;
  *((_DWORD *)this + 12) = v51;
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 256LL))(v49);
    *v8 = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 56LL))(v6);
LABEL_60:
  STRU::~STRU((STRU *)v52);
  STRU::~STRU((STRU *)v53);
  STRA::~STRA((STRA *)v54);
  STRA::~STRA((STRA *)v55);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000cc50  mov     [rsp-8+arg_8], rbx
0x18000cc55  push    rbp
0x18000cc56  push    rsi
0x18000cc57  push    rdi
0x18000cc58  push    r12
0x18000cc5a  push    r13
0x18000cc5c  push    r14
0x18000cc5e  push    r15
0x18000cc60  lea     rbp, [rsp-110h]
0x18000cc68  sub     rsp, 210h
0x18000cc6f  mov     rax, cs:__security_cookie
0x18000cc76  xor     rax, rsp
0x18000cc79  mov     [rbp+140h+var_40], rax
0x18000cc80  mov     rsi, r8
0x18000cc83  mov     rbx, rdx
0x18000cc86  mov     r13, rcx
0x18000cc89  lea     rdx, [rbp+140h+var_118]
0x18000cc8d  mov     r8d, 0Ah
0x18000cc93  lea     rcx, [rbp+140h+var_150]
0x18000cc97  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000cc9d  mov     edi, 18h
0x18000cca2  lea     rdx, [rbp+140h+var_D8]
0x18000cca6  mov     r8d, edi
0x18000cca9  lea     rcx, [rbp+140h+var_188]
0x18000ccad  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000ccb3  xor     edx, edx; Val
0x18000ccb5  lea     r8d, [rdi+68h]; Size
0x18000ccb9  lea     rcx, [rbp+140h+var_C0]; void *
0x18000ccc0  call    memset_0
0x18000ccc5  lea     r8d, [rdi+28h]
0x18000ccc9  lea     rdx, [rbp+140h+var_C0]
0x18000ccd0  lea     rcx, [rbp+140h+var_1C0]
0x18000ccd4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000ccda  xorps   xmm0, xmm0
0x18000ccdd  lea     rdx, [rbp+140h+var_108]
0x18000cce1  mov     r8d, edi
0x18000cce4  lea     rcx, [rsp+240h+var_1F8]
0x18000cce9  movups  [rbp+140h+var_108], xmm0
0x18000cced  movups  [rbp+140h+var_F8], xmm0
0x18000ccf1  movups  [rbp+140h+var_E8], xmm0
0x18000ccf5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000ccfb  mov     eax, [r13+30h]
0x18000ccff  xor     r12d, r12d
0x18000cd02  mov     edi, r12d
0x18000cd05  mov     [rsp+240h+var_200], eax
0x18000cd09  cmp     [r13+10h], r12
0x18000cd0d  jnz     short loc_18000CD13
0x18000cd0f  mov     [r13+10h], rbx
0x18000cd13  mov     r8d, [rsi+38h]
0x18000cd17  lea     r15, [r13+38h]
0x18000cd1b  mov     rax, [rsi+20h]
0x18000cd1f  mov     ecx, r8d
0x18000cd22  shr     ecx, 1
0x18000cd24  and     ecx, 1
0x18000cd27  mov     edx, ecx
0x18000cd29  or      edx, 8
0x18000cd2c  test    r8b, 20h
0x18000cd30  cmovz   edx, ecx
0x18000cd33  mov     ecx, edx
0x18000cd35  or      ecx, 2
0x18000cd38  test    r8b, 4
0x18000cd3c  cmovz   ecx, edx
0x18000cd3f  mov     edx, ecx
0x18000cd41  or      edx, 40h
0x18000cd44  test    r8b, 80h
0x18000cd48  cmovz   edx, ecx
0x18000cd4b  mov     r14d, edx
0x18000cd4e  or      r14d, 10h
0x18000cd52  cmp     [rsi+8], r12
0x18000cd56  cmovnz  r14d, edx
0x18000cd5a  neg     rax
0x18000cd5d  sbb     ecx, ecx
0x18000cd5f  and     ecx, 0FFFFFFFEh
0x18000cd62  add     ecx, 7
0x18000cd65  mov     ebx, ecx
0x18000cd67  or      ebx, 8
0x18000cd6a  test    r8b, 10h
0x18000cd6e  cmovz   ebx, ecx
0x18000cd71  mov     rcx, [r15]
0x18000cd74  test    rcx, rcx
0x18000cd77  jz      short loc_18000CD8B
0x18000cd79  mov     rax, [rcx]
0x18000cd7c  mov     rax, [rax+100h]
0x18000cd83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd88  mov     [r15], r12
0x18000cd8b  mov     rcx, [r13+18h]
0x18000cd8f  mov     r8, r15
0x18000cd92  mov     edx, ebx
0x18000cd94  mov     rax, [rcx]
0x18000cd97  mov     rax, [rax+0F8h]
0x18000cd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cda3  mov     ebx, eax
0x18000cda5  test    eax, eax
0x18000cda7  js      loc_18000D11A
0x18000cdad  mov     rbx, [rsi+20h]
0x18000cdb1  test    rbx, rbx
0x18000cdb4  jz      short loc_18000CDDA
0x18000cdb6  mov     rcx, [r15]
0x18000cdb9  mov     rax, [rcx]
0x18000cdbc  mov     rax, [rax+18h]
0x18000cdc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc5  mov     rdx, rbx; char *
0x18000cdc8  mov     rcx, rax; struct IHttpRequest *
0x18000cdcb  call    ?SetHeadersByStream@@YAJPEAVIHttpRequest@@PEAD@Z; SetHeadersByStream(IHttpRequest *,char *)
0x18000cdd0  mov     ebx, eax
0x18000cdd2  test    eax, eax
0x18000cdd4  js      loc_18000D11A
0x18000cdda  mov     rcx, [r15]
0x18000cddd  mov     rax, [rcx]
0x18000cde0  mov     rax, [rax+18h]
0x18000cde4  cmp     [rsi+30h], r12
0x18000cde8  jz      short loc_18000CDFC
0x18000cdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdef  mov     rdx, [rsi+30h]
0x18000cdf3  mov     r8d, [rdx]
0x18000cdf6  mov     rdx, [rdx+8]
0x18000cdfa  jmp     short loc_18000CE0D
0x18000cdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce01  mov     rdx, [r13+20h]
0x18000ce05  mov     r8d, [rdx+30h]
0x18000ce09  mov     rdx, [rdx+38h]
0x18000ce0d  mov     rcx, [rax]
0x18000ce10  mov     r9, rax
0x18000ce13  mov     rax, [rcx+88h]
0x18000ce1a  mov     rcx, r9
0x18000ce1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce22  mov     ebx, eax
0x18000ce24  test    eax, eax
0x18000ce26  js      loc_18000D11A
0x18000ce2c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ce30  xor     ebx, ebx
0x18000ce32  cmp     [rsi+8], rbx
0x18000ce36  jz      loc_18000CF12
0x18000ce3c  mov     rcx, [r15]
0x18000ce3f  mov     rax, [rcx]
0x18000ce42  mov     rax, [rax+18h]
0x18000ce46  cmp     [rsi], ebx
0x18000ce48  jz      short loc_18000CE69
0x18000ce4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce4f  mov     rdx, [rsi+8]
0x18000ce53  mov     r8, r12
0x18000ce56  mov     rcx, [rax]
0x18000ce59  mov     r10, [rcx+58h]
0x18000ce5d  inc     r8
0x18000ce60  cmp     [rdx+r8*2], bx
0x18000ce65  jnz     short loc_18000CE5D
0x18000ce67  jmp     short loc_18000CE85
0x18000ce69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce6e  mov     rdx, [rsi+8]
0x18000ce72  mov     r8, r12
0x18000ce75  mov     rcx, [rax]
0x18000ce78  mov     r10, [rcx+50h]
0x18000ce7c  inc     r8
0x18000ce7f  cmp     [rdx+r8], bl
0x18000ce83  jnz     short loc_18000CE7C
0x18000ce85  mov     rcx, rax
0x18000ce88  mov     r9d, 1
0x18000ce8e  mov     rax, r10
0x18000ce91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce96  mov     ebx, eax
0x18000ce98  test    eax, eax
0x18000ce9a  js      loc_18000D117
0x18000cea0  mov     rcx, [r15]
0x18000cea3  mov     rax, [rcx]
0x18000cea6  mov     rax, [rax+18h]
0x18000ceaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceaf  mov     rdx, rax
0x18000ceb2  mov     rcx, [rax]
0x18000ceb5  mov     rax, [rcx+8]
0x18000ceb9  mov     rcx, rdx
0x18000cebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec1  mov     rcx, [r13+18h]
0x18000cec5  mov     rbx, rax
0x18000cec8  mov     rdx, [rcx]
0x18000cecb  mov     rax, [rdx+18h]
0x18000cecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ced4  mov     rdx, rax
0x18000ced7  mov     rcx, [rax]
0x18000ceda  mov     rax, [rcx+8]
0x18000cede  mov     rcx, rdx
0x18000cee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee6  movzx   ecx, word ptr [rbx+44h]
0x18000ceea  cmp     cx, [rax+44h]
0x18000ceee  jnz     short loc_18000CF10
0x18000cef0  mov     rdx, [rax+58h]; String2
0x18000cef4  mov     r8d, ecx
0x18000cef7  mov     rcx, [rbx+58h]; String1
0x18000cefb  shr     r8, 1; MaxCount
0x18000cefe  call    cs:__imp__wcsnicmp
0x18000cf04  xor     ebx, ebx
0x18000cf06  test    eax, eax
0x18000cf08  jnz     short loc_18000CF12
0x18000cf0a  or      r14d, 10h
0x18000cf0e  jmp     short loc_18000CF12
0x18000cf10  xor     ebx, ebx
0x18000cf12  cmp     [rsi+18h], rbx
0x18000cf16  jz      short loc_18000CF49
0x18000cf18  mov     rcx, [r15]
0x18000cf1b  mov     rax, [rcx]
0x18000cf1e  mov     rax, [rax+18h]
0x18000cf22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf27  mov     rdx, [rsi+18h]
0x18000cf2b  mov     r8, rax
0x18000cf2e  mov     rcx, [rax]
0x18000cf31  mov     rax, [rcx+48h]
0x18000cf35  mov     rcx, r8
0x18000cf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf3d  mov     ebx, eax
0x18000cf3f  test    eax, eax
0x18000cf41  js      loc_18000D117
0x18000cf47  xor     ebx, ebx
0x18000cf49  cmp     [rsi+28h], rbx
0x18000cf4d  jz      loc_18000D0E0
0x18000cf53  mov     ecx, 90h; Size
0x18000cf58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cf5d  mov     rdi, rax
0x18000cf60  test    rax, rax
0x18000cf63  jz      loc_18000D0D3
0x18000cf69  lea     rax, ??_7CUSTOM_USER_CONTEXT@@6B@; const CUSTOM_USER_CONTEXT::`vftable'
0x18000cf70  lea     rcx, [rdi+10h]
0x18000cf74  mov     [rdi], rax
0x18000cf77  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cf7d  lea     rcx, [rdi+48h]
0x18000cf81  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cf87  mov     dword ptr [rdi+8], 1
0x18000cf8e  lea     rcx, [rbp+140h+var_1C0]
0x18000cf92  mov     [rdi+80h], rbx
0x18000cf99  mov     [rdi+88h], rbx
0x18000cfa0  mov     rax, [rsi+28h]
0x18000cfa4  mov     rdx, [rax+10h]
0x18000cfa8  cmp     [rax+8], ebx
0x18000cfab  jz      short loc_18000CFB5
0x18000cfad  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000cfb3  jmp     short loc_18000CFBB
0x18000cfb5  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000cfbb  mov     ebx, eax
0x18000cfbd  test    eax, eax
0x18000cfbf  js      loc_18000D117
0x18000cfc5  mov     rax, [rsi+28h]
0x18000cfc9  mov     rdx, [rax+20h]
0x18000cfcd  test    rdx, rdx
0x18000cfd0  jz      loc_18000D09E
0x18000cfd6  lea     rcx, [rsp+240h+var_1F8]
0x18000cfdb  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000cfe1  mov     ebx, eax
0x18000cfe3  test    eax, eax
0x18000cfe5  js      loc_18000D117
0x18000cfeb  mov     rcx, [r15]
0x18000cfee  mov     rax, [rcx]
0x18000cff1  mov     rax, [rax+18h]
0x18000cff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cffa  mov     rcx, [rax]
0x18000cffd  mov     r10, [rcx+20h]
0x18000d001  mov     rcx, [rsi+28h]
0x18000d005  mov     r8, [rcx+20h]
0x18000d009  inc     r12
0x18000d00c  cmp     byte ptr [r8+r12], 0
0x18000d011  jnz     short loc_18000D009
0x18000d013  mov     rcx, rax
0x18000d016  mov     dword ptr [rsp+240h+var_220], 1
0x18000d01e  mov     rax, r10
0x18000d021  movzx   r9d, r12w
0x18000d025  mov     edx, 18h
0x18000d02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d02f  xor     r12d, r12d
0x18000d032  mov     ebx, eax
0x18000d034  test    eax, eax
0x18000d036  js      loc_18000D11A
0x18000d03c  mov     rax, [rsi+28h]
0x18000d040  mov     rsi, [rax]
0x18000d043  test    rsi, rsi
0x18000d046  jnz     short loc_18000D06D
0x18000d048  mov     rcx, [r13+18h]
0x18000d04c  mov     rax, [rcx]
0x18000d04f  mov     rax, [rax+30h]
0x18000d053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d058  mov     rdx, rax
0x18000d05b  mov     rcx, [rax]
0x18000d05e  mov     rax, [rcx+20h]
0x18000d062  mov     rcx, rdx
0x18000d065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d06a  mov     rsi, rax
0x18000d06d  lea     rcx, [rsp+240h+var_1F8]
0x18000d072  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d078  lea     rcx, [rbp+140h+var_1C0]
0x18000d07c  mov     rbx, rax
0x18000d07f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d085  mov     r9, rbx; unsigned __int16 *
0x18000d088  mov     rdx, rsi; void *
0x18000d08b  mov     r8, rax; unsigned __int16 *
0x18000d08e  mov     rcx, rdi; this
0x18000d091  call    ?Create@CUSTOM_USER_CONTEXT@@QEAAJPEAXPEBG1@Z; CUSTOM_USER_CONTEXT::Create(void *,ushort const *,ushort const *)
0x18000d096  mov     ebx, eax
0x18000d098  test    eax, eax
0x18000d09a  js      short loc_18000D11A
0x18000d09c  jmp     short loc_18000D0E3
0x18000d09e  mov     rcx, [r13+18h]
0x18000d0a2  mov     rax, [rcx]
0x18000d0a5  mov     rax, [rax+30h]
0x18000d0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
