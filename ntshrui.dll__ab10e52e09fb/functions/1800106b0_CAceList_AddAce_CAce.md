# CAceList::AddAce(CAce *)

- ea: `0x1800106b0`
- end: `0x180010a7e`
- name: `?AddAce@CAceList@@QEAAJPEAVCAce@@@Z`
- size: `974`
- prototype: `__int64 __fastcall(CAceList *__hidden this, struct CAce *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005b360`
- `0x18005b52c`

## callees

- `0x18000f7a0`
- `0x18000f7f0`
- `0x1800106b0`
- `0x180026370`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001090d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001090d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001078c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001081b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001078c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001081b`

## pseudocode

```c
__int64 __fastcall CAceList::AddAce(int **this, struct CAce *a2)
{
  int v2; // eax
  int v5; // eax
  __int64 (__fastcall *v6)(int *, __int64, struct CAce *); // rax
  int *v7; // rbx
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // r15d
  int i; // ebp
  int *v13; // r14
  __int64 v14; // r14
  bool v15; // cl
  BOOL v16; // edx
  int *v17; // rax
  int v18; // r14d
  int j; // ebp
  int *v20; // r15
  __int64 v21; // r15
  bool v22; // cl
  BOOL v23; // edx
  __int64 (__fastcall *v24)(int *, __int64, struct CAce *); // rax
  int *v25; // rsi

  v2 = *((_DWORD *)a2 + 7);
  if ( (v2 & 0x20) == 0 )
  {
    v5 = v2 & 1;
    if ( v5 )
      goto LABEL_3;
    v9 = 0;
    if ( *this )
      v11 = **this;
    else
      v11 = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= v11 )
      {
LABEL_51:
        v24 = (__int64 (__fastcall *)(int *, __int64, struct CAce *))qword_1800959F8;
        v25 = *this;
        if ( qword_1800959F8 == -1 )
        {
LABEL_52:
          GetProcFromComCtl32(&qword_1800959F8, 334);
          v24 = (__int64 (__fastcall *)(int *, __int64, struct CAce *))qword_1800959F8;
        }
LABEL_48:
        if ( v24 )
          v8 = v24(v25, 0x7FFFFFFF, a2);
        else
          v8 = -1;
        goto LABEL_10;
      }
      v13 = *this;
      if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
      {
        if ( !g_hinstCC )
        {
          DelayLoadCC();
          if ( !g_hinstCC )
          {
            qword_180095A20 = 0;
LABEL_62:
            v14 = 0;
            goto LABEL_21;
          }
        }
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      }
      if ( !qword_180095A20 )
        goto LABEL_62;
      v14 = qword_180095A20(v13, i);
LABEL_21:
      if ( *((int *)a2 + 7) < 0 && *(int *)(v14 + 28) < 0 )
      {
        v15 = EqualSid(*((PSID *)a2 + 1), *(PSID *)(v14 + 8))
           && *((_DWORD *)a2 + 7) == *(_DWORD *)(v14 + 28)
           && *((_DWORD *)a2 + 1) == *(_DWORD *)(v14 + 4)
           && *((_BYTE *)a2 + 1) == *(_BYTE *)(v14 + 1)
           && *(_BYTE *)a2 == *(_BYTE *)v14
           && *((_DWORD *)a2 + 6) == *(_DWORD *)(v14 + 24);
        v16 = 0;
        if ( *(_QWORD *)(v14 + 16) )
          v16 = v15;
        if ( v16 )
        {
          if ( !memcmp_0(*(const void **)(v14 + 16), *((const void **)a2 + 2), *(unsigned int *)(v14 + 24)) )
          {
LABEL_50:
            if ( v14 )
            {
              *(_DWORD *)(v14 + 4) |= *((_DWORD *)a2 + 1);
              return 1;
            }
            goto LABEL_51;
          }
        }
        else if ( v15 )
        {
          goto LABEL_50;
        }
      }
    }
  }
  v5 = v2 & 1;
LABEL_3:
  if ( (*((_DWORD *)a2 + 7) & 0x20) == 0 && v5 )
  {
    v17 = this[1];
    v9 = 0;
    if ( v17 )
      v18 = *v17;
    else
      v18 = 0;
    for ( j = 0; ; ++j )
    {
      if ( j >= v18 )
      {
LABEL_47:
        v24 = (__int64 (__fastcall *)(int *, __int64, struct CAce *))qword_1800959F8;
        v25 = this[1];
        if ( qword_1800959F8 == -1 )
          goto LABEL_52;
        goto LABEL_48;
      }
      v20 = this[1];
      if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
      {
        if ( !g_hinstCC )
        {
          DelayLoadCC();
          if ( !g_hinstCC )
          {
            qword_180095A20 = 0;
LABEL_60:
            v21 = 0;
            goto LABEL_37;
          }
        }
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      }
      if ( !qword_180095A20 )
        goto LABEL_60;
      v21 = qword_180095A20(v20, j);
LABEL_37:
      if ( *((int *)a2 + 7) < 0 && *(int *)(v21 + 28) < 0 )
      {
        v22 = EqualSid(*((PSID *)a2 + 1), *(PSID *)(v21 + 8))
           && *((_DWORD *)a2 + 7) == *(_DWORD *)(v21 + 28)
           && *((_DWORD *)a2 + 1) == *(_DWORD *)(v21 + 4)
           && *((_BYTE *)a2 + 1) == *(_BYTE *)(v21 + 1)
           && *(_BYTE *)a2 == *(_BYTE *)v21
           && *((_DWORD *)a2 + 6) == *(_DWORD *)(v21 + 24);
        v23 = 0;
        if ( *(_QWORD *)(v21 + 16) )
          v23 = v22;
        if ( v23 )
        {
          if ( !memcmp_0(*(const void **)(v21 + 16), *((const void **)a2 + 2), *(unsigned int *)(v21 + 24)) )
          {
LABEL_46:
            if ( v21 )
            {
              *(_DWORD *)(v21 + 4) |= *((_DWORD *)a2 + 1);
              return 1;
            }
            goto LABEL_47;
          }
        }
        else if ( v22 )
        {
          goto LABEL_46;
        }
      }
    }
  }
  v6 = (__int64 (__fastcall *)(int *, __int64, struct CAce *))qword_1800959F8;
  v7 = this[2];
  if ( qword_1800959F8 == -1 )
  {
    GetProcFromComCtl32(&qword_1800959F8, 334);
    v6 = (__int64 (__fastcall *)(int *, __int64, struct CAce *))qword_1800959F8;
  }
  if ( v6 )
    v8 = v6(v7, 0x7FFFFFFF, a2);
  else
    v8 = -1;
  v9 = 0;
LABEL_10:
  if ( v8 == -1 )
    return (unsigned int)-2147024882;
  return v9;
}

```

## disassembly

```asm
0x1800106b0  push    rbx
0x1800106b2  push    rbp
0x1800106b3  push    rsi
0x1800106b4  push    rdi
0x1800106b5  push    r14
0x1800106b7  push    r15
0x1800106b9  sub     rsp, 28h
0x1800106bd  mov     eax, [rdx+1Ch]
0x1800106c0  mov     rdi, rdx
0x1800106c3  mov     r8d, eax
0x1800106c6  mov     rsi, rcx
0x1800106c9  and     r8d, 20h
0x1800106cd  jz      short loc_180010729
0x1800106cf  and     eax, 1
0x1800106d2  test    r8d, r8d
0x1800106d5  jnz     short loc_1800106DF
0x1800106d7  test    eax, eax
0x1800106d9  jnz     loc_1800107BF
0x1800106df  mov     rax, cs:qword_1800959F8
0x1800106e6  mov     rbx, [rcx+10h]
0x1800106ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800106ee  jz      loc_180010A57
0x1800106f4  test    rax, rax
0x1800106f7  jz      loc_180010A74
0x1800106fd  mov     r8, rdi
0x180010700  mov     edx, 7FFFFFFFh
0x180010705  mov     rcx, rbx
0x180010708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001070d  xor     ebx, ebx
0x18001070f  cmp     eax, 0FFFFFFFFh
0x180010712  mov     ecx, 8007000Eh
0x180010717  cmovz   ebx, ecx
0x18001071a  mov     eax, ebx
0x18001071c  add     rsp, 28h
0x180010720  pop     r15
0x180010722  pop     r14
0x180010724  pop     rdi
0x180010725  pop     rsi
0x180010726  pop     rbp
0x180010727  pop     rbx
0x180010728  retn
0x180010729  and     eax, 1
0x18001072c  jnz     short loc_1800106D2
0x18001072e  mov     rax, [rcx]
0x180010731  xor     ebx, ebx
0x180010733  test    rax, rax
0x180010736  jz      loc_180010973
0x18001073c  mov     r15d, [rax]
0x18001073f  mov     ebp, ebx
0x180010741  cmp     ebp, r15d
0x180010744  jge     loc_18001088B
0x18001074a  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x180010752  mov     r14, [rsi]
0x180010755  jz      loc_1800108EA
0x18001075b  mov     rax, cs:qword_180095A20
0x180010762  test    rax, rax
0x180010765  jz      loc_180010935
0x18001076b  movsxd  rdx, ebp
0x18001076e  mov     rcx, r14
0x180010771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010776  mov     r14, rax
0x180010779  cmp     [rdi+1Ch], ebx
0x18001077c  jge     short loc_1800107BB
0x18001077e  cmp     [r14+1Ch], ebx
0x180010782  jge     short loc_1800107BB
0x180010784  mov     rdx, [r14+8]; pSid2
0x180010788  mov     rcx, [rdi+8]; pSid1
0x18001078c  call    cs:__imp_EqualSid
0x180010792  test    eax, eax
0x180010794  jnz     loc_18001097B
0x18001079a  xor     cl, cl
0x18001079c  mov     r9, [r14+10h]
0x1800107a0  mov     edx, ebx
0x1800107a2  test    r9, r9
0x1800107a5  movzx   eax, cl
0x1800107a8  cmovnz  edx, eax
0x1800107ab  test    edx, edx
0x1800107ad  jnz     loc_1800109C3
0x1800107b3  test    cl, cl
0x1800107b5  jnz     loc_180010882
0x1800107bb  inc     ebp
0x1800107bd  jmp     short loc_180010741
0x1800107bf  mov     rax, [rcx+8]
0x1800107c3  xor     ebx, ebx
0x1800107c5  test    rax, rax
0x1800107c8  jz      loc_1800109EA
0x1800107ce  mov     r14d, [rax]
0x1800107d1  mov     ebp, ebx
0x1800107d3  cmp     ebp, r14d
0x1800107d6  jge     short loc_180010853
0x1800107d8  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x1800107e0  mov     r15, [rsi+8]
0x1800107e4  jz      loc_1800108B5
0x1800107ea  mov     rax, cs:qword_180095A20
0x1800107f1  test    rax, rax
0x1800107f4  jz      loc_180010926
0x1800107fa  movsxd  rdx, ebp
0x1800107fd  mov     rcx, r15
0x180010800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010805  mov     r15, rax
0x180010808  cmp     [rdi+1Ch], ebx
0x18001080b  jge     short loc_180010846
0x18001080d  cmp     [r15+1Ch], ebx
0x180010811  jge     short loc_180010846
0x180010813  mov     rdx, [r15+8]; pSid2
0x180010817  mov     rcx, [rdi+8]; pSid1
0x18001081b  call    cs:__imp_EqualSid
0x180010821  test    eax, eax
0x180010823  jnz     loc_1800109F2
0x180010829  xor     cl, cl
0x18001082b  mov     r9, [r15+10h]
0x18001082f  mov     edx, ebx
0x180010831  test    r9, r9
0x180010834  movzx   eax, cl
0x180010837  cmovnz  edx, eax
0x18001083a  test    edx, edx
0x18001083c  jnz     loc_180010A3A
0x180010842  test    cl, cl
0x180010844  jnz     short loc_18001084A
0x180010846  inc     ebp
0x180010848  jmp     short loc_1800107D3
0x18001084a  test    r15, r15
0x18001084d  jnz     loc_18001093D
0x180010853  mov     rax, cs:qword_1800959F8
0x18001085a  mov     rsi, [rsi+8]
0x18001085e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010862  jz      short loc_18001089B
0x180010864  test    rax, rax
0x180010867  jz      loc_1800109E0
0x18001086d  mov     r8, rdi
0x180010870  mov     edx, 7FFFFFFFh
0x180010875  mov     rcx, rsi
0x180010878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001087d  jmp     loc_18001070F
0x180010882  test    r14, r14
0x180010885  jnz     loc_180010958
0x18001088b  mov     rax, cs:qword_1800959F8
0x180010892  mov     rsi, [rsi]
0x180010895  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010899  jnz     short loc_180010864
0x18001089b  mov     edx, 14Eh
0x1800108a0  lea     rcx, qword_1800959F8
0x1800108a7  call    _GetProcFromComCtl32
0x1800108ac  mov     rax, cs:qword_1800959F8
0x1800108b3  jmp     short loc_180010864
0x1800108b5  cmp     cs:g_hinstCC, rbx
0x1800108bc  jnz     short loc_1800108CC
0x1800108be  call    DelayLoadCC
0x1800108c3  cmp     cs:g_hinstCC, rbx
0x1800108ca  jz      short loc_18001091F
0x1800108cc  mov     rcx, cs:g_hinstCC; hModule
0x1800108d3  mov     edx, 14Ch; lpProcName
0x1800108d8  call    cs:__imp_GetProcAddress
0x1800108de  mov     cs:qword_180095A20, rax
0x1800108e5  jmp     loc_1800107EA
0x1800108ea  cmp     cs:g_hinstCC, rbx
0x1800108f1  jnz     short loc_180010901
0x1800108f3  call    DelayLoadCC
0x1800108f8  cmp     cs:g_hinstCC, rbx
0x1800108ff  jz      short loc_18001092E
0x180010901  mov     rcx, cs:g_hinstCC; hModule
0x180010908  mov     edx, 14Ch; lpProcName
0x18001090d  call    cs:__imp_GetProcAddress
0x180010913  mov     cs:qword_180095A20, rax
0x18001091a  jmp     loc_18001075B
0x18001091f  mov     cs:qword_180095A20, rbx
0x180010926  mov     r15, rbx
0x180010929  jmp     loc_180010808
0x18001092e  mov     cs:qword_180095A20, rbx
0x180010935  mov     r14, rbx
0x180010938  jmp     loc_180010779
0x18001093d  mov     eax, [rdi+4]
0x180010940  mov     ebx, 1
0x180010945  or      [r15+4], eax
0x180010949  mov     eax, ebx
0x18001094b  add     rsp, 28h
0x18001094f  pop     r15
0x180010951  pop     r14
0x180010953  pop     rdi
0x180010954  pop     rsi
0x180010955  pop     rbp
0x180010956  pop     rbx
0x180010957  retn
0x180010958  mov     eax, [rdi+4]
0x18001095b  mov     ebx, 1
0x180010960  or      [r14+4], eax
0x180010964  mov     eax, ebx
0x180010966  add     rsp, 28h
0x18001096a  pop     r15
0x18001096c  pop     r14
0x18001096e  pop     rdi
0x18001096f  pop     rsi
0x180010970  pop     rbp
0x180010971  pop     rbx
0x180010972  retn
0x180010973  mov     r15d, ebx
0x180010976  jmp     loc_18001073F
0x18001097b  mov     eax, [r14+1Ch]
0x18001097f  cmp     [rdi+1Ch], eax
0x180010982  jnz     loc_18001079A
0x180010988  mov     eax, [r14+4]
0x18001098c  cmp     [rdi+4], eax
0x18001098f  jnz     loc_18001079A
0x180010995  movzx   eax, byte ptr [r14+1]
0x18001099a  cmp     [rdi+1], al
0x18001099d  jnz     loc_18001079A
0x1800109a3  movzx   eax, byte ptr [r14]
0x1800109a7  cmp     [rdi], al
0x1800109a9  jnz     loc_18001079A
0x1800109af  mov     eax, [r14+18h]
0x1800109b3  cmp     [rdi+18h], eax
0x1800109b6  jnz     loc_18001079A
0x1800109bc  mov     cl, 1
0x1800109be  jmp     loc_18001079C
0x1800109c3  mov     r8d, [r14+18h]; Size
0x1800109c7  mov     rcx, r9; Buf1
0x1800109ca  mov     rdx, [rdi+10h]; Buf2
0x1800109ce  call    memcmp_0
0x1800109d3  test    eax, eax
0x1800109d5  jz      loc_180010882
0x1800109db  jmp     loc_1800107BB
0x1800109e0  mov     eax, 0FFFFFFFFh
0x1800109e5  jmp     loc_18001070F
0x1800109ea  mov     r14d, ebx
0x1800109ed  jmp     loc_1800107D1
0x1800109f2  mov     eax, [r15+1Ch]
0x1800109f6  cmp     [rdi+1Ch], eax
0x1800109f9  jnz     loc_180010829
0x1800109ff  mov     eax, [r15+4]
0x180010a03  cmp     [rdi+4], eax
0x180010a06  jnz     loc_180010829
0x180010a0c  movzx   eax, byte ptr [r15+1]
0x180010a11  cmp     [rdi+1], al
0x180010a14  jnz     loc_180010829
0x180010a1a  movzx   eax, byte ptr [r15]
0x180010a1e  cmp     [rdi], al
0x180010a20  jnz     loc_180010829
0x180010a26  mov     eax, [r15+18h]
0x180010a2a  cmp     [rdi+18h], eax
0x180010a2d  jnz     loc_180010829
0x180010a33  mov     cl, 1
0x180010a35  jmp     loc_18001082B
0x180010a3a  mov     r8d, [r15+18h]; Size
0x180010a3e  mov     rcx, r9; Buf1
0x180010a41  mov     rdx, [rdi+10h]; Buf2
0x180010a45  call    memcmp_0
0x180010a4a  test    eax, eax
0x180010a4c  jz      loc_18001084A
0x180010a52  jmp     loc_180010846
0x180010a57  mov     edx, 14Eh
0x180010a5c  lea     rcx, qword_1800959F8
0x180010a63  call    _GetProcFromComCtl32
0x180010a68  mov     rax, cs:qword_1800959F8
0x180010a6f  jmp     loc_1800106F4
0x180010a74  mov     eax, 0FFFFFFFFh
0x180010a79  jmp     loc_18001070D
```
