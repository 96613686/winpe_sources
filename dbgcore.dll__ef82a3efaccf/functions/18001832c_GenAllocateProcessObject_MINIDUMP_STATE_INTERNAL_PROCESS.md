# GenAllocateProcessObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS * *)

- ea: `0x18001832c`
- end: `0x180018b6f`
- name: `?GenAllocateProcessObject@@YAJPEAU_MINIDUMP_STATE@@PEAPEAU_INTERNAL_PROCESS@@@Z`
- size: `2115`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001ad48`

## callees

- `0x1800021f4`
- `0x180016b74`
- `0x18001832c`
- `0x18002c010`

## string_xrefs

- `0x1800186b2`: `ProcessToken(%d,%I64x,%d,%d)`
- `0x180018752`: `ProcessToken_SessionId(0x%08X,%d,%d,%d)`
- `0x180018801`: `ProcessToken_User(0x%08X,%d,%d,%d)`
- `0x18001889b`: `ProcessToken_Groups(0x%08X,%d,%d,%d)`
- `0x180018935`: `ProcessToken_PrimaryGroup(0x%08X,%d,%d,%d)`
- `0x1800189cf`: `ProcessToken_Privileges(0x%08X,%d,%d,%d)`
- `0x180018a69`: `ProcessToken_Statistics(0x%08X,%d,%d,%d)`
- `0x180018b02`: `ProcessToken_RestrictedSids(0x%08X,%d,%d,%d)`

## pseudocode

```c
__int64 __fastcall GenAllocateProcessObject(struct _MINIDUMP_STATE *a1, struct _INTERNAL_PROCESS **a2)
{
  struct _INTERNAL_PROCESS **v2; // r13
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 result; // rax
  int v7; // r9d
  unsigned int v8; // edi
  unsigned int v9; // r14d
  int v10; // r8d
  int v11; // edx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // edi
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r9
  unsigned int *v22; // rax
  unsigned int *v23; // r14
  int v24; // r13d
  int v25; // rdx^4
  unsigned int v26; // eax
  unsigned int v27; // r15d
  __int64 v28; // rdx
  unsigned int v29; // edi
  _DWORD *v30; // r13
  __int64 v31; // rdx
  unsigned int v32; // r8d
  _DWORD *v33; // r13
  __int64 v34; // rdx
  unsigned int v35; // r8d
  _DWORD *v36; // r13
  __int64 v37; // rdx
  unsigned int v38; // r8d
  _DWORD *v39; // r13
  __int64 v40; // rdx
  unsigned int v41; // r8d
  _DWORD *v42; // r13
  __int64 v43; // rdx
  unsigned int v44; // r8d
  _DWORD *v45; // r13
  __int64 v46; // rdx
  unsigned int v47; // r8d
  __int64 v48; // [rsp+20h] [rbp-30h]
  __int64 v49; // [rsp+20h] [rbp-30h]
  __int64 v50; // [rsp+20h] [rbp-30h]
  __int64 v51; // [rsp+20h] [rbp-30h]
  __int64 v52; // [rsp+20h] [rbp-30h]
  __int64 v53; // [rsp+20h] [rbp-30h]
  __int64 v54; // [rsp+20h] [rbp-30h]
  __int64 v55; // [rsp+20h] [rbp-30h]
  __int64 v56; // [rsp+28h] [rbp-28h]
  __int64 v57; // [rsp+28h] [rbp-28h]
  __int64 v58; // [rsp+28h] [rbp-28h]
  __int64 v59; // [rsp+28h] [rbp-28h]
  __int64 v60; // [rsp+28h] [rbp-28h]
  __int64 v61; // [rsp+28h] [rbp-28h]
  __int64 v62; // [rsp+28h] [rbp-28h]
  __int64 v63; // [rsp+30h] [rbp-20h]
  __int64 v64; // [rsp+30h] [rbp-20h]
  __int64 v65; // [rsp+30h] [rbp-20h]
  __int64 v66; // [rsp+30h] [rbp-20h]
  __int64 v67; // [rsp+30h] [rbp-20h]
  __int64 v68; // [rsp+30h] [rbp-20h]
  unsigned __int64 v69; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v70; // [rsp+48h] [rbp-8h] BYREF
  __int64 v72; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int64 v73; // [rsp+A8h] [rbp+58h] BYREF

  v2 = a2;
  v73 = 0;
  v69 = 0;
  v70 = 0;
  v4 = AllocMemory(a1, 0x11DF8u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  *(_DWORD *)v4 = *((_DWORD *)a1 + 2);
  v4[8] = *(_QWORD *)a1;
  v4[14] = v4 + 13;
  v4[13] = v4 + 13;
  v4[16] = v4 + 15;
  v4[15] = v4 + 15;
  v4[18] = v4 + 17;
  v4[17] = v4 + 17;
  v4[20] = v4 + 19;
  v4[19] = v4 + 19;
  v4[950] = v4 + 949;
  v4[949] = v4 + 949;
  *((_DWORD *)v4 + 18) = 0;
  *((_DWORD *)v4 + 21) = 0;
  *((_DWORD *)v4 + 25) = 0;
  v4[9148] = 0;
  v7 = *((_DWORD *)a1 + 14);
  if ( (v7 & 0x10200) != 0 )
  {
    v8 = 200;
    v9 = 500;
  }
  else
  {
    v10 = (*((_DWORD *)a1 + 14) & 1) != 0 ? 120 : 100;
    v11 = (*((_DWORD *)a1 + 14) & 1) != 0 ? 60 : 50;
    if ( (v7 & 0x40) != 0 )
    {
      v11 = (*((_DWORD *)a1 + 14) & 1) != 0 ? 110 : 100;
      v10 = (*((_DWORD *)a1 + 14) & 1) != 0 ? 170 : 150;
    }
    v9 = v10 + 20;
    v8 = v11 + 10;
    if ( (v7 & 0x100) == 0 )
    {
      v9 = v10;
      v8 = v11;
    }
    if ( (v7 & 0x2000) != 0 )
    {
      v8 += 10;
      v9 += 20;
    }
  }
  memset_0(v4 + 22, 0, 0x1CB8u);
  v5[941] = a1;
  *((_DWORD *)v5 + 1884) = 32;
  v12 = 0x7FFFFFF;
  if ( v8 <= 0x7FFFFFF )
    v12 = v8;
  *((_DWORD *)v5 + 1885) = v12;
  v13 = 268435454;
  v5[943] = 0;
  v5[944] = 0;
  v5[945] = a1;
  if ( v9 <= 0xFFFFFFE )
    v13 = v9;
  *((_DWORD *)v5 + 1892) = 16;
  *((_DWORD *)v5 + 1893) = v13;
  v5[947] = 0;
  v5[948] = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, _QWORD *))(**((_QWORD **)a1 + 2) + 216LL))(
          *((_QWORD *)a1 + 2),
          *(_QWORD *)a1,
          v5 + 1,
          v5 + 2);
  if ( v14 )
  {
    if ( (*((_DWORD *)a1 + 14) & 0x100) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v5);
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "GenAllocateProcessObject.GetPeb(0x%x) failed, 0x%08x",
        *((unsigned int *)a1 + 2),
        v14);
      return v14;
    }
    v5[1] = 0;
    *((_DWORD *)v5 + 4) = 0;
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *))(**((_QWORD **)a1 + 2) + 224LL))(
          *((_QWORD *)a1 + 2),
          *(_QWORD *)a1,
          &v73,
          &v69,
          &v70) )
  {
    *((_DWORD *)v5 + 5) = 1;
    *((_DWORD *)v5 + 6) = v73 / 0x989680 + 1240428288;
    *((_DWORD *)v5 + 7) = v69 / 0x989680;
    *((_DWORD *)v5 + 8) = v70 / 0x989680;
  }
  if ( (*((_BYTE *)a1 + 88) & 1) == 0 )
  {
    LODWORD(v72) = 0;
    v15 = AllocMemory(a1, 0x600u);
    v16 = v15;
    if ( v15 )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64 *))(**((_QWORD **)a1 + 2) + 32LL))(
              *((_QWORD *)a1 + 2),
              64,
              v15,
              &v72);
      v19 = (unsigned int)v17;
      if ( v17 )
      {
        if ( v17 < 0 )
          (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
            *((_QWORD *)a1 + 5),
            4,
            "GenAllocateProcessObject.GetCpuPowerInfo() failed, 0x%08x");
      }
      else
      {
        *((_DWORD *)v5 + 9) = 1;
        *(_OWORD *)(v5 + 5) = *(_OWORD *)v16;
        v5[7] = v16[2];
      }
      (*(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64))(**((_QWORD **)a1 + 4) + 24LL))(
        *((_QWORD *)a1 + 4),
        v16,
        v18,
        v19);
    }
  }
  if ( (*((_DWORD *)a1 + 14) & 0x40000) != 0
    && (v20 = *((_QWORD *)a1 + 2),
        v21 = *(_QWORD *)a1,
        v72 = 0,
        !(*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)v20 + 456LL))(
           v20,
           *((unsigned int *)a1 + 2),
           0,
           v21,
           &v72))
    && v72 )
  {
    v22 = (unsigned int *)AllocMemory(a1, 0x10000u);
    v5[9143] = v22;
    v23 = v22;
    if ( v22 )
    {
      memset_0(v22, 0, 0x10000u);
      v23[1] = *((_DWORD *)a1 + 2);
      v24 = 72;
      v25 = HIDWORD(v72);
      *((_QWORD *)v23 + 1) = v72;
      HIDWORD(v48) = v25;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken(%d,%I64x,%d,%d)");
      LODWORD(v48) = 65464;
      v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64, unsigned int *))(**((_QWORD **)a1 + 2)
                                                                                                  + 464LL))(
              *((_QWORD *)a1 + 2),
              v72,
              12,
              v5[9143] + 72LL,
              v48,
              v23 + 5);
      v27 = v26;
      if ( v26 )
      {
        LODWORD(v28) = 0;
        v23[5] = 0;
        v29 = 72;
        v24 = 0;
      }
      else
      {
        v28 = v23[5];
        v29 = 8 * ((unsigned __int64)(v28 + 7) >> 3) + 72;
      }
      v23[4] = v24;
      LODWORD(v56) = v28;
      LODWORD(v49) = v24;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken_SessionId(0x%08X,%d,%d,%d)",
        v26,
        v49,
        v56,
        v29);
      v30 = v23 + 7;
      if ( v29 >= 0x10000
        || (v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
                    *((_QWORD *)a1 + 2),
                    v72,
                    1,
                    v5[9143] + v29,
                    0x10000 - v29,
                    v23 + 7)) != 0 )
      {
        LODWORD(v31) = 0;
        *v30 = 0;
        v32 = 0;
      }
      else
      {
        v31 = (unsigned int)*v30;
        v32 = v29;
        v29 += 8 * ((unsigned __int64)(v31 + 7) >> 3);
      }
      LODWORD(v63) = v29;
      LODWORD(v57) = v31;
      LODWORD(v50) = v32;
      v23[6] = v32;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken_User(0x%08X,%d,%d,%d)",
        v27,
        v50,
        v57,
        v63);
      v33 = v23 + 9;
      if ( v29 >= 0x10000
        || (v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
                    *((_QWORD *)a1 + 2),
                    v72,
                    2,
                    v5[9143] + v29,
                    0x10000 - v29,
                    v23 + 9)) != 0 )
      {
        LODWORD(v34) = 0;
        *v33 = 0;
        v35 = 0;
      }
      else
      {
        v34 = (unsigned int)*v33;
        v35 = v29;
        v29 += 8 * ((unsigned __int64)(v34 + 7) >> 3);
      }
      LODWORD(v64) = v29;
      LODWORD(v58) = v34;
      LODWORD(v51) = v35;
      v23[8] = v35;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken_Groups(0x%08X,%d,%d,%d)",
        v27,
        v51,
        v58,
        v64);
      v36 = v23 + 11;
      if ( v29 >= 0x10000
        || (v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
                    *((_QWORD *)a1 + 2),
                    v72,
                    5,
                    v5[9143] + v29,
                    0x10000 - v29,
                    v23 + 11)) != 0 )
      {
        LODWORD(v37) = 0;
        *v36 = 0;
        v38 = 0;
      }
      else
      {
        v37 = (unsigned int)*v36;
        v38 = v29;
        v29 += 8 * ((unsigned __int64)(v37 + 7) >> 3);
      }
      LODWORD(v65) = v29;
      LODWORD(v59) = v37;
      LODWORD(v52) = v38;
      v23[10] = v38;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken_PrimaryGroup(0x%08X,%d,%d,%d)",
        v27,
        v52,
        v59,
        v65);
      v39 = v23 + 13;
      if ( v29 >= 0x10000
        || (v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
                    *((_QWORD *)a1 + 2),
                    v72,
                    3,
                    v5[9143] + v29,
                    0x10000 - v29,
                    v23 + 13)) != 0 )
      {
        LODWORD(v40) = 0;
        *v39 = 0;
        v41 = 0;
      }
      else
      {
        v40 = (unsigned int)*v39;
        v41 = v29;
        v29 += 8 * ((unsigned __int64)(v40 + 7) >> 3);
      }
      LODWORD(v66) = v29;
      LODWORD(v60) = v40;
      LODWORD(v53) = v41;
      v23[12] = v41;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken_Privileges(0x%08X,%d,%d,%d)",
        v27,
        v53,
        v60,
        v66);
      v42 = v23 + 15;
      if ( v29 >= 0x10000
        || (v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
                    *((_QWORD *)a1 + 2),
                    v72,
                    10,
                    v5[9143] + v29,
                    0x10000 - v29,
                    v23 + 15)) != 0 )
      {
        LODWORD(v43) = 0;
        *v42 = 0;
        v44 = 0;
      }
      else
      {
        v43 = (unsigned int)*v42;
        v44 = v29;
        v29 += 8 * ((unsigned __int64)(v43 + 7) >> 3);
      }
      LODWORD(v67) = v29;
      LODWORD(v61) = v43;
      LODWORD(v54) = v44;
      v23[14] = v44;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken_Statistics(0x%08X,%d,%d,%d)",
        v27,
        v54,
        v61,
        v67);
      v45 = v23 + 17;
      if ( v29 >= 0x10000
        || (v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)a1 + 2) + 464LL))(
                    *((_QWORD *)a1 + 2),
                    v72,
                    11,
                    v5[9143] + v29,
                    0x10000 - v29,
                    v23 + 17)) != 0 )
      {
        LODWORD(v46) = 0;
        *v45 = 0;
        v47 = 0;
      }
      else
      {
        v46 = (unsigned int)*v45;
        v47 = v29;
        v29 += 8 * ((unsigned __int64)(v46 + 7) >> 3);
      }
      LODWORD(v68) = v29;
      LODWORD(v62) = v46;
      LODWORD(v55) = v47;
      v23[16] = v47;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "ProcessToken_RestrictedSids(0x%08X,%d,%d,%d)",
        v27,
        v55,
        v62,
        v68);
      v2 = a2;
      *v23 = v29;
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 2) + 472LL))(*((_QWORD *)a1 + 2), v72);
  }
  else
  {
    v5[9143] = 0;
  }
  v5[9149] = 0;
  result = 0;
  *((_DWORD *)v5 + 18300) = 0;
  *v2 = (struct _INTERNAL_PROCESS *)v5;
  return result;
}

```

## disassembly

```asm
0x18001832c  mov     [rsp-38h+arg_0], rbx
0x180018331  mov     [rsp-38h+arg_8], rdx
0x180018336  push    rbp
0x180018337  push    rsi
0x180018338  push    rdi
0x180018339  push    r12
0x18001833b  push    r13
0x18001833d  push    r14
0x18001833f  push    r15
0x180018341  mov     rbp, rsp
0x180018344  sub     rsp, 50h
0x180018348  xor     r15d, r15d
0x18001834b  mov     r13, rdx
0x18001834e  mov     edx, 11DF8h; unsigned int
0x180018353  mov     [rbp+arg_18], r15
0x180018357  mov     [rbp+var_10], r15
0x18001835b  mov     rsi, rcx
0x18001835e  mov     [rbp+var_8], r15
0x180018362  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x180018367  mov     rbx, rax
0x18001836a  test    rax, rax
0x18001836d  jnz     short loc_180018379
0x18001836f  mov     eax, 8007000Eh
0x180018374  jmp     loc_180018B57
0x180018379  mov     eax, [rsi+8]
0x18001837c  mov     r12d, 40h ; '@'
0x180018382  mov     [rbx], eax
0x180018384  mov     rax, [rsi]
0x180018387  mov     [rbx+40h], rax
0x18001838b  lea     rax, [rbx+68h]
0x18001838f  mov     [rbx+70h], rax
0x180018393  mov     [rax], rax
0x180018396  lea     rax, [rbx+78h]
0x18001839a  mov     [rbx+80h], rax
0x1800183a1  mov     [rax], rax
0x1800183a4  lea     rax, [rbx+88h]
0x1800183ab  mov     [rbx+90h], rax
0x1800183b2  mov     [rax], rax
0x1800183b5  lea     rax, [rbx+98h]
0x1800183bc  mov     [rbx+0A0h], rax
0x1800183c3  mov     [rax], rax
0x1800183c6  lea     rax, [rbx+1DA8h]
0x1800183cd  mov     [rbx+1DB0h], rax
0x1800183d4  mov     [rax], rax
0x1800183d7  mov     [rbx+48h], r15d
0x1800183db  mov     [rbx+54h], r15d
0x1800183df  mov     [rbx+64h], r15d
0x1800183e3  mov     [rbx+11DE0h], r15
0x1800183ea  mov     r9d, [rsi+38h]
0x1800183ee  test    r9d, 10200h
0x1800183f5  jz      short loc_180018404
0x1800183f7  mov     edi, 0C8h
0x1800183fc  mov     r14d, 1F4h
0x180018402  jmp     short loc_180018450
0x180018404  mov     ecx, r9d
0x180018407  and     ecx, 1
0x18001840a  mov     eax, ecx
0x18001840c  neg     eax
0x18001840e  sbb     r8d, r8d
0x180018411  and     r8d, 14h
0x180018415  add     r8d, 64h ; 'd'
0x180018419  neg     ecx
0x18001841b  sbb     edx, edx
0x18001841d  and     edx, 0Ah
0x180018420  add     edx, 32h ; '2'
0x180018423  test    r12b, r9b
0x180018426  jz      short loc_18001842F
0x180018428  add     edx, 32h ; '2'
0x18001842b  add     r8d, 32h ; '2'
0x18001842f  bt      r9d, 8
0x180018434  lea     r14d, [r8+14h]
0x180018438  lea     edi, [rdx+0Ah]
0x18001843b  cmovnb  r14d, r8d
0x18001843f  cmovnb  edi, edx
0x180018442  bt      r9d, 0Dh
0x180018447  jnb     short loc_180018450
0x180018449  add     edi, 0Ah
0x18001844c  add     r14d, 14h
0x180018450  lea     rcx, [rbx+0B0h]; void *
0x180018457  xor     edx, edx; Val
0x180018459  mov     r8d, 1CB8h; Size
0x18001845f  call    memset_0
0x180018464  mov     [rbx+1D68h], rsi
0x18001846b  lea     r9, [rbx+10h]
0x18001846f  mov     dword ptr [rbx+1D70h], 20h ; ' '
0x180018479  lea     r8, [rbx+8]
0x18001847d  mov     eax, 7FFFFFFh
0x180018482  cmp     edi, eax
0x180018484  cmovbe  eax, edi
0x180018487  mov     [rbx+1D74h], eax
0x18001848d  mov     eax, 0FFFFFFEh
0x180018492  mov     [rbx+1D78h], r15
0x180018499  cmp     r14d, eax
0x18001849c  mov     [rbx+1D80h], r15
0x1800184a3  mov     [rbx+1D88h], rsi
0x1800184aa  cmovbe  eax, r14d
0x1800184ae  mov     dword ptr [rbx+1D90h], 10h
0x1800184b8  mov     [rbx+1D94h], eax
0x1800184be  mov     [rbx+1D98h], r15
0x1800184c5  mov     [rbx+1DA0h], r15
0x1800184cc  mov     rcx, [rsi+10h]
0x1800184d0  mov     rdx, [rsi]
0x1800184d3  mov     rax, [rcx]
0x1800184d6  mov     rax, [rax+0D8h]
0x1800184dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184e2  mov     edi, eax
0x1800184e4  test    eax, eax
0x1800184e6  jz      short loc_180018537
0x1800184e8  test    dword ptr [rsi+38h], 100h
0x1800184ef  jz      short loc_18001852F
0x1800184f1  mov     rcx, [rsi+20h]
0x1800184f5  mov     rdx, [rcx]
0x1800184f8  mov     rax, [rdx+18h]
0x1800184fc  mov     rdx, rbx
0x1800184ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018504  mov     rcx, [rsi+28h]
0x180018508  lea     r8, aGenallocatepro_0; "GenAllocateProcessObject.GetPeb(0x%x) f"...
0x18001850f  mov     r9d, [rsi+8]
0x180018513  mov     edx, 4
0x180018518  mov     dword ptr [rsp+50h+var_30], edi
0x18001851c  mov     rax, [rcx]
0x18001851f  mov     rax, [rax+8]
0x180018523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018528  mov     eax, edi
0x18001852a  jmp     loc_180018B57
0x18001852f  mov     [rbx+8], r15
0x180018533  mov     [rbx+10h], r15d
0x180018537  mov     rcx, [rsi+10h]
0x18001853b  lea     rdx, [rbp+var_8]
0x18001853f  mov     [rsp+50h+var_30], rdx
0x180018544  lea     r9, [rbp+var_10]
0x180018548  mov     rdx, [rsi]
0x18001854b  lea     r8, [rbp+arg_18]
0x18001854f  mov     rax, [rcx]
0x180018552  mov     rax, [rax+0E0h]
0x180018559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001855e  test    eax, eax
0x180018560  jnz     short loc_1800185A3
0x180018562  mov     rcx, 0D6BF94D5E57A42BDh
0x18001856c  mov     dword ptr [rbx+14h], 1
0x180018573  mov     rax, rcx
0x180018576  mul     [rbp+arg_18]
0x18001857a  mov     rax, rcx
0x18001857d  shr     rdx, 17h
0x180018581  add     edx, 49EF6F00h
0x180018587  mov     [rbx+18h], edx
0x18001858a  mul     [rbp+var_10]
0x18001858e  mov     rax, rcx
0x180018591  shr     rdx, 17h
0x180018595  mov     [rbx+1Ch], edx
0x180018598  mul     [rbp+var_8]
0x18001859c  shr     rdx, 17h
0x1800185a0  mov     [rbx+20h], edx
0x1800185a3  test    byte ptr [rsi+58h], 1
0x1800185a7  jnz     loc_180018635
0x1800185ad  mov     edx, 600h; unsigned int
0x1800185b2  mov     dword ptr [rbp+arg_10], r15d
0x1800185b6  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x1800185b9  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x1800185be  mov     rdi, rax
0x1800185c1  test    rax, rax
0x1800185c4  jz      short loc_180018635
0x1800185c6  mov     rcx, [rsi+10h]
0x1800185ca  lea     r9, [rbp+arg_10]
0x1800185ce  mov     r8, rdi
0x1800185d1  mov     rdx, [rcx]
0x1800185d4  mov     rax, [rdx+20h]
0x1800185d8  mov     edx, r12d
0x1800185db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185e0  mov     r9d, eax
0x1800185e3  test    eax, eax
0x1800185e5  jnz     short loc_180018601
0x1800185e7  mov     dword ptr [rbx+24h], 1
0x1800185ee  movups  xmm0, xmmword ptr [rdi]
0x1800185f1  movups  xmmword ptr [rbx+28h], xmm0
0x1800185f5  movsd   xmm1, qword ptr [rdi+10h]
0x1800185fa  movsd   qword ptr [rbx+38h], xmm1
0x1800185ff  jmp     short loc_180018622
0x180018601  test    r9d, r9d
0x180018604  jns     short loc_180018622
0x180018606  mov     rcx, [rsi+28h]
0x18001860a  lea     r8, aGenallocatepro; "GenAllocateProcessObject.GetCpuPowerInf"...
0x180018611  mov     edx, 4
0x180018616  mov     rax, [rcx]
0x180018619  mov     rax, [rax+8]
0x18001861d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018622  mov     rcx, [rsi+20h]
0x180018626  mov     rdx, rdi
0x180018629  mov     rax, [rcx]
0x18001862c  mov     rax, [rax+18h]
0x180018630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018635  test    dword ptr [rsi+38h], 40000h
0x18001863c  jz      loc_180018B3C
0x180018642  mov     rcx, [rsi+10h]
0x180018646  lea     rdx, [rbp+arg_10]
0x18001864a  mov     r9, [rsi]
0x18001864d  xor     r8d, r8d
0x180018650  mov     [rbp+arg_10], r15
0x180018654  mov     [rsp+50h+var_30], rdx
0x180018659  mov     rax, [rcx]
0x18001865c  mov     edx, [rsi+8]
0x18001865f  mov     rax, [rax+1C8h]
0x180018666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001866b  test    eax, eax
0x18001866d  jnz     loc_180018B3C
0x180018673  cmp     [rbp+arg_10], r15
0x180018677  jz      loc_180018B3C
0x18001867d  mov     r12d, 10000h
0x180018683  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x180018686  mov     edx, r12d; unsigned int
0x180018689  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x18001868e  mov     [rbx+11DB8h], rax
0x180018695  mov     r14, rax
0x180018698  test    rax, rax
0x18001869b  jz      loc_180018B23
0x1800186a1  mov     r8d, r12d; Size
0x1800186a4  xor     edx, edx; Val
0x1800186a6  mov     rcx, rax; void *
0x1800186a9  call    memset_0
0x1800186ae  mov     r9d, [rsi+8]
0x1800186b2  lea     r8, aProcesstokenDI; "ProcessToken(%d,%I64x,%d,%d)"
0x1800186b9  mov     [r14+4], r9d
0x1800186bd  mov     r13d, 48h ; 'H'
0x1800186c3  mov     rdx, [rbp+arg_10]
0x1800186c7  mov     [r14+8], rdx
0x1800186cb  mov     rcx, [rsi+28h]
0x1800186cf  mov     [rsp+50h+var_20], r12d
0x1800186d4  mov     dword ptr [rsp+50h+var_28], r13d
0x1800186d9  mov     [rsp+50h+var_30], rdx
0x1800186de  lea     edx, [r13-47h]
0x1800186e2  mov     rax, [rcx]
0x1800186e5  mov     rax, [rax+8]
0x1800186e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186ee  mov     rcx, [rsi+10h]
0x1800186f2  lea     rdi, [r14+14h]
0x1800186f6  mov     r9, [rbx+11DB8h]
0x1800186fd  lea     r8d, [r13-3Ch]
0x180018701  mov     rdx, [rbp+arg_10]
0x180018705  add     r9, r13
0x180018708  mov     [rsp+50h+var_28], rdi
0x18001870d  mov     rax, [rcx]
0x180018710  mov     dword ptr [rsp+50h+var_30], 0FFB8h
0x180018718  mov     rax, [rax+1D0h]
0x18001871f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018724  mov     r15d, eax
0x180018727  test    eax, eax
0x180018729  jnz     short loc_18001873E
0x18001872b  mov     edx, [rdi]
0x18001872d  lea     rcx, [rdx+7]
0x180018731  shr     rcx, 3
0x180018735  lea     edi, ds:48h[rcx*8]
0x18001873c  jmp     short loc_18001874E
0x18001873e  xor     edx, edx
0x180018740  mov     dword ptr [r14+14h], 0
0x180018748  mov     edi, r13d
0x18001874b  xor     r13d, r13d
0x18001874e  mov     [r14+10h], r13d
0x180018752  lea     r8, aProcesstokenSe; "ProcessToken_SessionId(0x%08X,%d,%d,%d)"
0x180018759  mov     rcx, [rsi+28h]
0x18001875d  mov     r9d, r15d
0x180018760  mov     [rsp+50h+var_20], edi
0x180018764  mov     dword ptr [rsp+50h+var_28], edx
0x180018768  mov     edx, 1
0x18001876d  mov     dword ptr [rsp+50h+var_30], r13d
0x180018772  mov     rax, [rcx]
0x180018775  mov     rax, [rax+8]
0x180018779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001877e  lea     r13, [r14+1Ch]
0x180018782  cmp     edi, r12d
0x180018785  jnb     short loc_1800187D7
0x180018787  mov     rcx, [rsi+10h]
0x18001878b  mov     edx, r12d
0x18001878e  sub     edx, edi
0x180018790  mov     r9d, edi
0x180018793  add     r9, [rbx+11DB8h]
0x18001879a  mov     r8d, 1
0x1800187a0  mov     [rsp+50h+var_28], r13
0x1800187a5  mov     rax, [rcx]
0x1800187a8  mov     dword ptr [rsp+50h+var_30], edx
0x1800187ac  mov     rdx, [rbp+arg_10]
0x1800187b0  mov     rax, [rax+1D0h]
0x1800187b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187bc  mov     r15d, eax
0x1800187bf  test    eax, eax
0x1800187c1  jnz     short loc_1800187D7
0x1800187c3  mov     edx, [r13+0]
0x1800187c7  mov     r8d, edi
0x1800187ca  lea     rax, [rdx+7]
0x1800187ce  shr     rax, 3
0x1800187d2  lea     edi, [rdi+rax*8]
0x1800187d5  jmp     short loc_1800187E0
0x1800187d7  xor     edx, edx
0x1800187d9  mov     [r13+0], edx
0x1800187dd  xor     r8d, r8d
0x1800187e0  mov     eax, 18h
0x1800187e5  mov     [rsp+50h+var_20], edi
0x1800187e9  mov     dword ptr [rsp+50h+var_28], edx
0x1800187ed  mov     rcx, r14
0x1800187f0  mov     dword ptr [rsp+50h+var_30], r8d
0x1800187f5  mov     r9d, r15d
  ... truncated ...
```
