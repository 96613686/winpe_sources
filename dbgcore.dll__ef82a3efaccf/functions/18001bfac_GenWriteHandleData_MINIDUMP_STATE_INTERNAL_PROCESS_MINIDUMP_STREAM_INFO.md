# GenWriteHandleData(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_MINIDUMP_STREAM_INFO *)

- ea: `0x18001bfac`
- end: `0x18001c49a`
- name: `?GenWriteHandleData@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_MINIDUMP_STREAM_INFO@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _MINIDUMP_STREAM_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180003424`
- `0x18001951c`
- `0x18001bfac`
- `0x18002c010`

## string_xrefs

- `0x18001c01c`: `GenWriteHandleData stream RVA overflow`
- `0x18001c067`: `GenWriteHandleData.Seek(0x%x) failed, 0x%08x`
- `0x18001c3bd`: `GenWriteHandleData.TypeNameLen.Write(0x%x) failed, 0x%08x`
- `0x18001c396`: `GenWriteHandleData.TypeName.Write(0x%x) failed, 0x%08x`
- `0x18001c3dd`: `GenWriteHandleData.ObjectNameLen.Write(0x%x) failed, 0x%08x`
- `0x18001c3d4`: `GenWriteHandleData.ObjectName.Write(0x%x) failed, 0x%08x`
- `0x18001c3f7`: `GenWriteHandleData.InfoHdr.Write(0x%I64x) failed, 0x%08x`
- `0x18001c3ea`: `GenWriteHandleData.Info.Write(0x%I64x) failed, 0x%08x`
- `0x18001c38d`: `GenWriteHandleData.Header.Write(0x%x) failed, 0x%08x`
- `0x18001c436`: `GenWriteHandleData.Desc.Write(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall GenWriteHandleData(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _MINIDUMP_STREAM_INFO *a3)
{
  __int64 result; // rax
  unsigned int v7; // r14d
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // r12
  __int64 v12; // r15
  __int64 v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // ebx
  char *v22; // rcx
  unsigned int v23; // ebx
  __int64 v24; // rcx
  unsigned int v25; // eax
  struct _MINIDUMP_STREAM_INFO *v26; // r15
  __int64 v27; // r9
  const char *v28; // r8
  const char *v29; // r8
  unsigned int v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-ACh]
  int v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  char *v34; // [rsp+68h] [rbp-98h]
  struct _MINIDUMP_STREAM_INFO *v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  unsigned int i; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v39[736]; // [rsp+A0h] [rbp-60h] BYREF

  v35 = a3;
  memset_0(v39, 0, 0x2D8u);
  v30 = 0;
  v38 = 0;
  if ( *((_QWORD *)a3 + 20) > 0xFFFFFFFF )
  {
    (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "GenWriteHandleData stream RVA overflow");
    return 2147942487LL;
  }
  v7 = *((_DWORD *)a3 + 40);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 24LL))(
         *((_QWORD *)a1 + 3),
         0,
         v7,
         0);
  v9 = v8;
  if ( !v8 )
  {
    result = *((unsigned int *)a2 + 18288);
    if ( !(_DWORD)result )
      return result;
    if ( (unsigned int)result > 0x6666666 )
      return 2147942934LL;
    v10 = 0;
    v32 = 0;
    while ( 2 )
    {
      if ( (unsigned int)GenCheckCancel(a1) )
      {
LABEL_39:
        v9 = -2147023673;
        goto LABEL_42;
      }
      v11 = *((_QWORD *)a2 + 9145);
      v33 = 0;
      v12 = 5 * v10;
      memset_0(v39, 0, 0x2D8u);
      v13 = *(unsigned int *)(v11 + 40 * v10 + 8);
      if ( (_DWORD)v13 )
      {
        v33 = *((_QWORD *)a2 + 9146);
        v30 = *(_DWORD *)(v13 + v33 - 40);
        v14 = *(_DWORD *)(v11 + 40 * v10 + 8);
        *(_DWORD *)(v11 + 40 * v10 + 8) = v7;
        v15 = *((_QWORD *)a1 + 3);
        v31 = v14;
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v15 + 32LL))(v15, &v30, 4);
        if ( v9 )
        {
          v28 = "GenWriteHandleData.TypeNameLen.Write(0x%x) failed, 0x%08x";
          goto LABEL_33;
        }
        v16 = (__int64 *)*((_QWORD *)a1 + 3);
        v30 += 2;
        v17 = *v16;
        v33 += v31 - 36LL;
        v9 = (*(__int64 (__fastcall **)(__int64 *))(v17 + 32))(v16);
        if ( v9 )
        {
          v29 = "GenWriteHandleData.TypeName.Write(0x%x) failed, 0x%08x";
LABEL_31:
          (*(void (__fastcall **)(_QWORD, __int64, const char *, _QWORD, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
            *((_QWORD *)a1 + 5),
            4,
            v29,
            v30,
            v9);
LABEL_42:
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 2) + 360LL))(*((_QWORD *)a1 + 2));
          return v9;
        }
        v7 += v30 + 4;
      }
      v18 = *(unsigned int *)(v11 + 8 * v12 + 12);
      if ( !(_DWORD)v18 )
        goto LABEL_20;
      v34 = (char *)*((_QWORD *)a2 + 9146);
      v30 = *(_DWORD *)&v34[v18 - 40];
      v19 = *(_DWORD *)(v11 + 8 * v12 + 12);
      *(_DWORD *)(v11 + 8 * v12 + 12) = v7;
      v20 = *((_QWORD *)a1 + 3);
      v31 = v19;
      v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v20 + 32LL))(v20, &v30, 4);
      if ( !v9 )
      {
        v21 = v30 + 2;
        v30 = v21;
        v22 = &v34[v31 - 36];
        v34 = v22;
        if ( v21 <= 0x2D0 )
          memcpy_0(v39, v22, v21);
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
               *((_QWORD *)a1 + 3),
               v34,
               v21);
        if ( !v9 )
        {
          v7 += v30 + 4;
LABEL_20:
          v36 = 0;
          v23 = 0;
          for ( i = 0;
                !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, char *, _BYTE *, int, unsigned int *))(**((_QWORD **)a1 + 2) + 352LL))(
                   *((_QWORD *)a1 + 2),
                   *(_QWORD *)(v11 + 8 * v12),
                   v33,
                   HIDWORD(v36),
                   (char *)&v36 + 4,
                   v39,
                   728,
                   &i);
                v7 += i + 12 )
          {
            if ( (unsigned int)GenCheckCancel(a1) )
              goto LABEL_39;
            v24 = *((_QWORD *)a1 + 3);
            LODWORD(v36) = v23;
            v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v24 + 32LL))(v24, &v36, 12);
            if ( v9 )
            {
              v27 = *(_QWORD *)(v11 + 8 * v12);
              v28 = "GenWriteHandleData.InfoHdr.Write(0x%I64x) failed, 0x%08x";
              goto LABEL_34;
            }
            v9 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
                   *((_QWORD *)a1 + 3),
                   v39,
                   i);
            if ( v9 )
            {
              v27 = *(_QWORD *)(v11 + 8 * v12);
              v28 = "GenWriteHandleData.Info.Write(0x%I64x) failed, 0x%08x";
              goto LABEL_34;
            }
            v23 = v7;
          }
          *(_DWORD *)(v11 + 8 * v12 + 32) = v23;
          v10 = (unsigned int)(v32 + 1);
          *(_DWORD *)(v11 + 8 * v12 + 36) = 0;
          v25 = *((_DWORD *)a2 + 18288);
          v32 = v10;
          if ( (unsigned int)v10 < v25 )
            continue;
          v26 = v35;
          DWORD2(v38) = v25;
          *((_DWORD *)v35 + 44) = v7;
          DWORD1(v38) = 40;
          HIDWORD(v38) = 0;
          *((_DWORD *)v26 + 45) = 40 * v25 + 16;
          LODWORD(v38) = 16;
          *((_QWORD *)v26 + 20) = v7 + 40 * v25 + 16;
          v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64))(**((_QWORD **)a1 + 3) + 32LL))(
                 *((_QWORD *)a1 + 3),
                 &v38,
                 16);
          if ( v9 )
          {
            v27 = 16;
            v28 = "GenWriteHandleData.Header.Write(0x%x) failed, 0x%08x";
            goto LABEL_34;
          }
          v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
                 *((_QWORD *)a1 + 3),
                 *((_QWORD *)a2 + 9145),
                 (unsigned int)(40 * *((_DWORD *)a2 + 18288)));
          if ( v9 )
            (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
              *((_QWORD *)a1 + 5),
              4,
              "GenWriteHandleData.Desc.Write(0x%x) failed, 0x%08x",
              40LL * DWORD2(v38),
              v9);
          goto LABEL_42;
        }
        v29 = "GenWriteHandleData.ObjectName.Write(0x%x) failed, 0x%08x";
        goto LABEL_31;
      }
      break;
    }
    v28 = "GenWriteHandleData.ObjectNameLen.Write(0x%x) failed, 0x%08x";
LABEL_33:
    v27 = 4;
LABEL_34:
    (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      v28,
      v27,
      v9);
    goto LABEL_42;
  }
  (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
    *((_QWORD *)a1 + 5),
    4,
    "GenWriteHandleData.Seek(0x%x) failed, 0x%08x",
    v7,
    v8);
  return v9;
}

```

## disassembly

```asm
0x18001bfac  mov     [rsp-8+arg_18], rbx
0x18001bfb1  push    rbp
0x18001bfb2  push    rsi
0x18001bfb3  push    rdi
0x18001bfb4  push    r12
0x18001bfb6  push    r13
0x18001bfb8  push    r14
0x18001bfba  push    r15
0x18001bfbc  lea     rbp, [rsp-290h]
0x18001bfc4  sub     rsp, 390h
0x18001bfcb  mov     rax, cs:__security_cookie
0x18001bfd2  xor     rax, rsp
0x18001bfd5  mov     [rbp+2C0h+var_40], rax
0x18001bfdc  mov     r15, r8
0x18001bfdf  mov     [rsp+3C0h+var_350], r8
0x18001bfe4  mov     r13, rdx
0x18001bfe7  mov     rdi, rcx
0x18001bfea  xor     edx, edx; Val
0x18001bfec  lea     rcx, [rbp+2C0h+var_320]; void *
0x18001bff0  mov     r8d, 2D8h; Size
0x18001bff6  call    memset_0
0x18001bffb  mov     eax, 0FFFFFFFFh
0x18001c000  mov     [rsp+3C0h+var_370], 0
0x18001c008  xorps   xmm0, xmm0
0x18001c00b  movups  [rbp+2C0h+var_338], xmm0
0x18001c00f  cmp     [r15+0A0h], rax
0x18001c016  jbe     short loc_18001C03E
0x18001c018  mov     rcx, [rdi+28h]
0x18001c01c  lea     r8, aGenwritehandle_4; "GenWriteHandleData stream RVA overflow"
0x18001c023  mov     edx, 4
0x18001c028  mov     rax, [rcx]
0x18001c02b  mov     rax, [rax+8]
0x18001c02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c034  mov     eax, 80070057h
0x18001c039  jmp     loc_18001C470
0x18001c03e  mov     rcx, [rdi+18h]
0x18001c042  xor     r9d, r9d
0x18001c045  mov     r14d, [r15+0A0h]
0x18001c04c  xor     edx, edx
0x18001c04e  mov     r8d, r14d
0x18001c051  mov     rax, [rcx]
0x18001c054  mov     rax, [rax+18h]
0x18001c058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c05d  mov     ebx, eax
0x18001c05f  test    eax, eax
0x18001c061  jz      short loc_18001C08B
0x18001c063  mov     rcx, [rdi+28h]
0x18001c067  lea     r8, aGenwritehandle_0; "GenWriteHandleData.Seek(0x%x) failed, 0"...
0x18001c06e  mov     r9d, r14d
0x18001c071  mov     dword ptr [rsp+3C0h+var_3A0], ebx
0x18001c075  mov     rdx, [rcx]
0x18001c078  mov     rax, [rdx+8]
0x18001c07c  mov     edx, 4
0x18001c081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c086  jmp     loc_18001C46E
0x18001c08b  mov     eax, [r13+11DC0h]
0x18001c092  test    eax, eax
0x18001c094  jz      loc_18001C470
0x18001c09a  cmp     eax, 6666666h
0x18001c09f  jbe     short loc_18001C0AB
0x18001c0a1  mov     eax, 80070216h
0x18001c0a6  jmp     loc_18001C470
0x18001c0ab  xor     ebx, ebx
0x18001c0ad  mov     [rsp+3C0h+var_368], ebx
0x18001c0b1  lea     esi, [rbx+4]
0x18001c0b4  test    eax, eax
0x18001c0b6  jz      loc_18001C32A
0x18001c0bc  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18001c0bf  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18001c0c4  test    eax, eax
0x18001c0c6  jnz     loc_18001C400
0x18001c0cc  mov     r12, [r13+11DC8h]
0x18001c0d3  lea     rcx, [rbp+2C0h+var_320]; void *
0x18001c0d7  xor     edx, edx; Val
0x18001c0d9  mov     [rsp+3C0h+var_360], 0
0x18001c0e2  mov     r8d, 2D8h; Size
0x18001c0e8  lea     r15, [rbx+rbx*4]
0x18001c0ec  call    memset_0
0x18001c0f1  mov     eax, [r12+r15*8+8]
0x18001c0f6  test    eax, eax
0x18001c0f8  jz      loc_18001C188
0x18001c0fe  mov     rcx, [r13+11DD0h]
0x18001c105  lea     rdx, [rsp+3C0h+var_370]
0x18001c10a  mov     [rsp+3C0h+var_360], rcx
0x18001c10f  mov     r8d, esi
0x18001c112  mov     ecx, [rax+rcx-28h]
0x18001c116  mov     [rsp+3C0h+var_370], ecx
0x18001c11a  mov     eax, [r12+r15*8+8]
0x18001c11f  mov     [r12+r15*8+8], r14d
0x18001c124  mov     rcx, [rdi+18h]
0x18001c128  mov     [rsp+3C0h+var_36C], eax
0x18001c12c  mov     rax, [rcx]
0x18001c12f  mov     rax, [rax+20h]
0x18001c133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c138  mov     ebx, eax
0x18001c13a  test    eax, eax
0x18001c13c  jnz     loc_18001C3BD
0x18001c142  mov     r8d, [rsp+3C0h+var_370]
0x18001c147  mov     rcx, [rdi+18h]
0x18001c14b  add     r8d, 2
0x18001c14f  mov     rdx, [rsp+3C0h+var_360]
0x18001c154  mov     eax, [rsp+3C0h+var_36C]
0x18001c158  add     rax, 0FFFFFFFFFFFFFFDCh
0x18001c15c  mov     [rsp+3C0h+var_370], r8d
0x18001c161  add     rdx, rax
0x18001c164  mov     rax, [rcx]
0x18001c167  mov     [rsp+3C0h+var_360], rdx
0x18001c16c  mov     rax, [rax+20h]
0x18001c170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c175  mov     ebx, eax
0x18001c177  test    eax, eax
0x18001c179  jnz     loc_18001C396
0x18001c17f  mov     eax, [rsp+3C0h+var_370]
0x18001c183  add     eax, esi
0x18001c185  add     r14d, eax
0x18001c188  mov     eax, [r12+r15*8+0Ch]
0x18001c18d  test    eax, eax
0x18001c18f  jz      loc_18001C23D
0x18001c195  mov     rcx, [r13+11DD0h]
0x18001c19c  lea     rdx, [rsp+3C0h+var_370]
0x18001c1a1  mov     [rsp+3C0h+var_358], rcx
0x18001c1a6  mov     r8d, esi
0x18001c1a9  mov     ecx, [rax+rcx-28h]
0x18001c1ad  mov     [rsp+3C0h+var_370], ecx
0x18001c1b1  mov     eax, [r12+r15*8+0Ch]
0x18001c1b6  mov     [r12+r15*8+0Ch], r14d
0x18001c1bb  mov     rcx, [rdi+18h]
0x18001c1bf  mov     [rsp+3C0h+var_36C], eax
0x18001c1c3  mov     rax, [rcx]
0x18001c1c6  mov     rax, [rax+20h]
0x18001c1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1cf  mov     ebx, eax
0x18001c1d1  test    eax, eax
0x18001c1d3  jnz     loc_18001C3DD
0x18001c1d9  mov     rcx, [rsp+3C0h+var_358]
0x18001c1de  mov     ebx, [rsp+3C0h+var_370]
0x18001c1e2  mov     eax, [rsp+3C0h+var_36C]
0x18001c1e6  add     ebx, 2
0x18001c1e9  add     rax, 0FFFFFFFFFFFFFFDCh
0x18001c1ed  mov     [rsp+3C0h+var_370], ebx
0x18001c1f1  add     rcx, rax
0x18001c1f4  mov     eax, ebx
0x18001c1f6  mov     [rsp+3C0h+var_358], rcx
0x18001c1fb  cmp     ebx, 2D0h
0x18001c201  ja      short loc_18001C212
0x18001c203  mov     rdx, rcx; Src
0x18001c206  mov     r8d, eax; Size
0x18001c209  lea     rcx, [rbp+2C0h+var_320]; void *
0x18001c20d  call    memcpy_0
0x18001c212  mov     rcx, [rdi+18h]
0x18001c216  mov     r8d, ebx
0x18001c219  mov     rdx, [rsp+3C0h+var_358]
0x18001c21e  mov     rax, [rcx]
0x18001c221  mov     rax, [rax+20h]
0x18001c225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c22a  mov     ebx, eax
0x18001c22c  test    eax, eax
0x18001c22e  jnz     loc_18001C3D4
0x18001c234  mov     eax, [rsp+3C0h+var_370]
0x18001c238  add     eax, esi
0x18001c23a  add     r14d, eax
0x18001c23d  xor     eax, eax
0x18001c23f  mov     [rsp+3C0h+var_348], rax
0x18001c244  xor     ebx, ebx
0x18001c246  mov     [rbp+2C0h+var_340], eax
0x18001c249  mov     rcx, [rdi+10h]
0x18001c24d  lea     rdx, [rbp+2C0h+var_340]
0x18001c251  mov     r9d, dword ptr [rsp+3C0h+var_348+4]
0x18001c256  mov     r8, [rsp+3C0h+var_360]
0x18001c25b  mov     [rsp+3C0h+var_388], rdx
0x18001c260  lea     rdx, [rbp+2C0h+var_320]
0x18001c264  mov     rax, [rcx]
0x18001c267  mov     [rsp+3C0h+var_390], 2D8h
0x18001c26f  mov     [rsp+3C0h+var_398], rdx
0x18001c274  lea     rdx, [rsp+3C0h+var_348+4]
0x18001c279  mov     [rsp+3C0h+var_3A0], rdx
0x18001c27e  mov     rax, [rax+160h]
0x18001c285  mov     rdx, [r12+r15*8]
0x18001c289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c28e  test    eax, eax
0x18001c290  jnz     short loc_18001C2FE
0x18001c292  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18001c295  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18001c29a  test    eax, eax
0x18001c29c  jnz     loc_18001C400
0x18001c2a2  mov     rcx, [rdi+18h]
0x18001c2a6  lea     rdx, [rsp+3C0h+var_348]
0x18001c2ab  mov     dword ptr [rsp+3C0h+var_348], ebx
0x18001c2af  mov     r8d, 0Ch
0x18001c2b5  mov     rax, [rcx]
0x18001c2b8  mov     rax, [rax+20h]
0x18001c2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2c1  mov     ebx, eax
0x18001c2c3  test    eax, eax
0x18001c2c5  jnz     loc_18001C3F3
0x18001c2cb  mov     rcx, [rdi+18h]
0x18001c2cf  lea     rdx, [rbp+2C0h+var_320]
0x18001c2d3  mov     r8d, [rbp+2C0h+var_340]
0x18001c2d7  mov     rax, [rcx]
0x18001c2da  mov     rax, [rax+20h]
0x18001c2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2e3  mov     ebx, eax
0x18001c2e5  test    eax, eax
0x18001c2e7  jnz     loc_18001C3E6
0x18001c2ed  mov     eax, [rbp+2C0h+var_340]
0x18001c2f0  mov     ebx, r14d
0x18001c2f3  add     eax, 0Ch
0x18001c2f6  add     r14d, eax
0x18001c2f9  jmp     loc_18001C249
0x18001c2fe  mov     [r12+r15*8+20h], ebx
0x18001c303  mov     ebx, [rsp+3C0h+var_368]
0x18001c307  inc     ebx
0x18001c309  mov     dword ptr [r12+r15*8+24h], 0
0x18001c312  mov     eax, [r13+11DC0h]
0x18001c319  mov     [rsp+3C0h+var_368], ebx
0x18001c31d  cmp     ebx, eax
0x18001c31f  jb      loc_18001C0BC
0x18001c325  mov     r15, [rsp+3C0h+var_350]
0x18001c32a  mov     dword ptr [rbp+2C0h+var_338+8], eax
0x18001c32d  lea     rdx, [rbp+2C0h+var_338]
0x18001c331  lea     eax, [rax+rax*4]
0x18001c334  mov     [r15+0B0h], r14d
0x18001c33b  lea     ecx, ds:0[rax*8]
0x18001c342  mov     dword ptr [rbp+2C0h+var_338+4], 28h ; '('
0x18001c349  lea     eax, [rcx+10h]
0x18001c34c  mov     dword ptr [rbp+2C0h+var_338+0Ch], 0
0x18001c353  mov     [r15+0B4h], eax
0x18001c35a  mov     r12d, 10h
0x18001c360  add     ecx, r12d
0x18001c363  mov     dword ptr [rbp+2C0h+var_338], r12d
0x18001c367  add     ecx, r14d
0x18001c36a  mov     r8d, r12d
0x18001c36d  mov     [r15+0A0h], rcx
0x18001c374  mov     rcx, [rdi+18h]
0x18001c378  mov     rax, [rcx]
0x18001c37b  mov     rax, [rax+20h]
0x18001c37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c384  mov     ebx, eax
0x18001c386  test    eax, eax
0x18001c388  jz      short loc_18001C407
0x18001c38a  mov     r9d, r12d
0x18001c38d  lea     r8, aGenwritehandle_6; "GenWriteHandleData.Header.Write(0x%x) f"...
0x18001c394  jmp     short loc_18001C3C7
0x18001c396  lea     r8, aGenwritehandle_2; "GenWriteHandleData.TypeName.Write(0x%x)"...
0x18001c39d  mov     rcx, [rdi+28h]
0x18001c3a1  mov     edx, esi
0x18001c3a3  mov     r9d, [rsp+3C0h+var_370]
0x18001c3a8  mov     dword ptr [rsp+3C0h+var_3A0], ebx
0x18001c3ac  mov     rax, [rcx]
0x18001c3af  mov     rax, [rax+8]
0x18001c3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3b8  jmp     loc_18001C45B
0x18001c3bd  lea     r8, aGenwritehandle_7; "GenWriteHandleData.TypeNameLen.Write(0x"...
0x18001c3c4  mov     r9, rsi
0x18001c3c7  mov     rcx, [rdi+28h]
0x18001c3cb  mov     rax, [rcx]
0x18001c3ce  mov     rax, [rax+8]
0x18001c3d2  jmp     short loc_18001C450
0x18001c3d4  lea     r8, aGenwritehandle_10; "GenWriteHandleData.ObjectName.Write(0x%"...
0x18001c3db  jmp     short loc_18001C39D
0x18001c3dd  lea     r8, aGenwritehandle_11; "GenWriteHandleData.ObjectNameLen.Write("...
0x18001c3e4  jmp     short loc_18001C3C4
0x18001c3e6  mov     r9, [r12+r15*8]
0x18001c3ea  lea     r8, aGenwritehandle_8; "GenWriteHandleData.Info.Write(0x%I64x) "...
0x18001c3f1  jmp     short loc_18001C3C7
0x18001c3f3  mov     r9, [r12+r15*8]
0x18001c3f7  lea     r8, aGenwritehandle_9; "GenWriteHandleData.InfoHdr.Write(0x%I64"...
0x18001c3fe  jmp     short loc_18001C3C7
0x18001c400  mov     ebx, 800704C7h
0x18001c405  jmp     short loc_18001C45B
0x18001c407  mov     eax, [r13+11DC0h]
0x18001c40e  mov     rcx, [rdi+18h]
0x18001c412  lea     r8d, [rax+rax*4]
0x18001c416  mov     rdx, [rcx]
0x18001c419  shl     r8d, 3
0x18001c41d  mov     rax, [rdx+20h]
0x18001c421  mov     rdx, [r13+11DC8h]
0x18001c428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c42d  mov     ebx, eax
0x18001c42f  test    eax, eax
0x18001c431  jz      short loc_18001C45B
0x18001c433  mov     eax, dword ptr [rbp+2C0h+var_338+8]
0x18001c436  lea     r8, aGenwritehandle_3; "GenWriteHandleData.Desc.Write(0x%x) fai"...
0x18001c43d  mov     rcx, [rdi+28h]
0x18001c441  lea     r9, [rax+rax*4]
0x18001c445  mov     rdx, [rcx]
0x18001c448  shl     r9, 3
0x18001c44c  mov     rax, [rdx+8]
0x18001c450  mov     edx, esi
0x18001c452  mov     dword ptr [rsp+3C0h+var_3A0], ebx
0x18001c456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c45b  mov     rcx, [rdi+10h]
0x18001c45f  mov     rax, [rcx]
0x18001c462  mov     rax, [rax+168h]
0x18001c469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c46e  mov     eax, ebx
0x18001c470  mov     rcx, [rbp+2C0h+var_40]
0x18001c477  xor     rcx, rsp; StackCookie
0x18001c47a  call    __security_check_cookie
0x18001c47f  mov     rbx, [rsp+3C0h+arg_18]
  ... truncated ...
```
