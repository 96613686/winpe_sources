# LogEEInfoRecordToEtw(tagRPC_ERROR_ENUM_HANDLE *)

- ea: `0x180015868`
- end: `0x180015c7a`
- name: `?LogEEInfoRecordToEtw@@YAJPEAUtagRPC_ERROR_ENUM_HANDLE@@@Z`
- size: `1042`
- prototype: `__int64 __fastcall(struct tagRPC_ERROR_ENUM_HANDLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800164f8`

## callees

- `0x180015760`
- `0x180015868`
- `0x180021e70`
- `0x180022870`
- `0x1800ca049`
- `0x1800ca140`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180015c40`
- `ntdll!EtwEventWrite` at `0x180015c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001594a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001594a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180015940`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180015940`

## pseudocode

```c
__int64 __fastcall LogEEInfoRecordToEtw(struct tagRPC_ERROR_ENUM_HANDLE *a1)
{
  bool v2; // zf
  DWORD LastError; // edi
  void **CurrentPos; // rbx
  __int16 v5; // ax
  int v6; // r14d
  int v7; // esi
  unsigned int v8; // esi
  _DWORD *v9; // rbx
  PWSTR Buffer; // rax
  __int64 v11; // rax
  int v12; // eax
  void **v13; // rcx
  int v14; // r10d
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  char *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r11
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v30; // [rsp+20h] [rbp-B9h] BYREF
  __int64 v31; // [rsp+28h] [rbp-B1h] BYREF
  int v32; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v33; // [rsp+38h] [rbp-A1h] BYREF
  int v34; // [rsp+40h] [rbp-99h] BYREF
  _WORD *v35; // [rsp+48h] [rbp-91h] BYREF
  int v36; // [rsp+50h] [rbp-89h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+54h] [rbp-85h] BYREF
  int v38; // [rsp+64h] [rbp-75h] BYREF
  int v39; // [rsp+68h] [rbp-71h] BYREF
  __int16 v40; // [rsp+6Ch] [rbp-6Dh] BYREF
  __int16 v41; // [rsp+6Eh] [rbp-6Bh] BYREF
  int v42; // [rsp+70h] [rbp-69h]
  _DWORD v43[26]; // [rsp+78h] [rbp-61h] BYREF

  memset_0(&v34, 0, 0x98u);
  v34 = 1;
  v2 = a1->Signature == -50529028;
  HIDWORD(v31) = 0;
  WORD2(v30) = 0;
  LOWORD(v31) = 0;
  v42 = 4;
  LOBYTE(v30) = 0;
  v33 = 0;
  v32 = 0;
  v41 = 0;
  if ( !v2 )
    return 87;
  CurrentPos = (void **)a1->CurrentPos;
  if ( !CurrentPos )
    return 1761;
  if ( *((__int16 *)CurrentPos + 30) > 4 )
    return 122;
  if ( *((_DWORD *)CurrentPos + 2) == 2 )
    v35 = 0;
  else
    v35 = CurrentPos[3];
  v36 = *((_DWORD *)CurrentPos + 8);
  if ( FileTimeToSystemTime((const FILETIME *)CurrentPos + 5, &SystemTime) )
  {
    v38 = *((_DWORD *)CurrentPos + 12);
    v39 = *((_DWORD *)CurrentPos + 13);
    v40 = *((_WORD *)CurrentPos + 28);
    v5 = *((_WORD *)CurrentPos + 29);
    v41 = v5;
    if ( *CurrentPos && (*((_BYTE *)*CurrentPos + 58) & 1) != 0 )
      v41 = v5 | 2;
    v6 = *((__int16 *)CurrentPos + 30);
    v7 = 0;
    v42 = v6;
    while ( v7 < v6 )
    {
      LastError = ConvertPrivateParamToPublicParam(
                    (struct tagParam *)&CurrentPos[3 * v7 + 8],
                    0,
                    (struct tagRPC_EE_INFO_PARAM *)&v43[6 * v7]);
      if ( LastError )
        return LastError;
      ++v7;
    }
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      return LastError;
  }
  a1->CurrentPos = *CurrentPos;
  v8 = v42 + 4 * v42 + 9;
  v9 = AllocWrapper(saturated_mul(v8, 0x10u));
  if ( !v9 )
    return LastError;
  Buffer = pBaseNameUnicodeString->Buffer;
  v9[2] = pBaseNameUnicodeString->Length + 2;
  *(_QWORD *)v9 = Buffer;
  v9[3] = 0;
  if ( v35 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v35[v11] );
    v12 = 2 * v11 + 2;
    v13 = (void **)&v35;
  }
  else
  {
    v12 = 2;
    v13 = (void **)&v31;
  }
  *((_QWORD *)v9 + 2) = v13;
  v14 = 0;
  v9[6] = v12;
  v9[7] = 0;
  *((_QWORD *)v9 + 4) = &v36;
  *((_QWORD *)v9 + 5) = 4;
  *((_QWORD *)v9 + 6) = &SystemTime;
  *((_QWORD *)v9 + 7) = 16;
  *((_QWORD *)v9 + 8) = &v38;
  *((_QWORD *)v9 + 9) = 4;
  *((_QWORD *)v9 + 10) = &v39;
  *((_QWORD *)v9 + 11) = 4;
  *((_QWORD *)v9 + 12) = &v40;
  *((_QWORD *)v9 + 13) = 2;
  *((_QWORD *)v9 + 14) = &v41;
  *((_QWORD *)v9 + 15) = 2;
  WORD2(v30) = v42;
  *((_QWORD *)v9 + 16) = (char *)&v30 + 4;
  *((_QWORD *)v9 + 17) = 2;
  if ( v42 > 0 )
  {
    while ( 1 )
    {
      v15 = (unsigned int)(v14 + 4 * v14 + 9);
      v16 = 2 * v15;
      *(_QWORD *)&v9[2 * v16] = &v43[6 * v14];
      *(_QWORD *)&v9[2 * v16 + 2] = 4;
      *(_QWORD *)&v9[2 * v16 + 4] = &v30;
      *(_QWORD *)&v9[2 * v16 + 6] = 1;
      v17 = 2 * (v15 + 2);
      *(_QWORD *)&v9[2 * v17] = &v31;
      *(_QWORD *)&v9[2 * v17 + 2] = 2;
      v18 = 2 * (v15 + 3);
      *(_QWORD *)&v9[2 * v18] = &v32;
      *(_QWORD *)&v9[2 * v18 + 2] = 4;
      v19 = 2 * (v15 + 4);
      *(_QWORD *)&v9[2 * v19] = &v33;
      *(_QWORD *)&v9[2 * v19 + 2] = 8;
      if ( v43[6 * v14] == 1 )
        break;
      if ( v43[6 * v14] == 2 )
      {
        v23 = *(_QWORD *)&v43[6 * v14 + 2];
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(v23 + 2 * v24) );
        v25 = (unsigned int)(v15 + 2);
        v26 = 2 * v24 + 2;
LABEL_43:
        v28 = 2 * v25;
        v9[2 * v28 + 3] = 0;
        v9[2 * v28 + 2] = v26;
        *(_QWORD *)&v9[2 * v28] = v23;
        goto LABEL_44;
      }
      if ( v43[6 * v14] == 3 )
      {
        v21 = (char *)&v43[6 * v14 + 2];
      }
      else
      {
        if ( v43[6 * v14] != 4 )
        {
          if ( v43[6 * v14] == 5 )
          {
            v20 = 2LL * (unsigned int)(v15 + 4);
            *(_QWORD *)&v9[2 * v20] = &v43[6 * v14 + 2];
            *(_QWORD *)&v9[2 * v20 + 2] = 8;
          }
          goto LABEL_44;
        }
        HIDWORD(v31) = SLOWORD(v43[6 * v14 + 2]);
        v21 = (char *)&v31 + 4;
      }
      v22 = 2LL * (unsigned int)(v15 + 3);
      *(_QWORD *)&v9[2 * v22] = v21;
      *(_QWORD *)&v9[2 * v22 + 2] = 4;
LABEL_44:
      if ( ++v14 >= v42 )
        goto LABEL_45;
    }
    v23 = *(_QWORD *)&v43[6 * v14 + 2];
    v27 = -1;
    do
      ++v27;
    while ( *(_BYTE *)(v23 + v27) );
    v25 = (unsigned int)(v15 + 1);
    v26 = v27 + 1;
    goto LABEL_43;
  }
LABEL_45:
  if ( (unsigned int)EtwEventWrite(RpcEtwGuid_Context, RpcEEInfoEvent, v8, v9, v30, v31, v32, v33, v34) )
    LastError = 14;
  FreeWrapper(v9);
  return LastError;
}

```

## disassembly

```asm
0x180015868  push    rbp
0x18001586a  push    rbx
0x18001586b  push    rsi
0x18001586c  push    rdi
0x18001586d  push    r12
0x18001586f  push    r13
0x180015871  push    r14
0x180015873  push    r15
0x180015875  lea     rbp, [rsp-1Fh]
0x18001587a  sub     rsp, 0F8h
0x180015881  mov     rax, cs:__security_cookie
0x180015888  xor     rax, rsp
0x18001588b  mov     [rbp+57h+var_50], rax
0x18001588f  mov     r15, rcx
0x180015892  xor     edx, edx; Val
0x180015894  lea     rcx, [rsp+130h+var_F0]; void *
0x180015899  mov     r8d, 98h; Size
0x18001589f  call    memset_0
0x1800158a4  xor     r12d, r12d
0x1800158a7  mov     [rsp+130h+var_F0], 1
0x1800158af  cmp     dword ptr [r15], 0FCFCFCFCh
0x1800158b6  mov     [rsp+130h+var_104], r12d
0x1800158bb  mov     [rsp+130h+var_10C], r12w
0x1800158c1  lea     r13d, [r12+4]
0x1800158c6  mov     [rsp+130h+var_108], r12w
0x1800158cc  mov     [rbp+57h+var_C0], r13d
0x1800158d0  mov     [rsp+130h+var_110], r12b
0x1800158d5  mov     [rsp+130h+var_F8], r12
0x1800158da  mov     [rsp+130h+var_100], r12d
0x1800158df  mov     [rbp+57h+var_C2], r12w
0x1800158e4  jz      short loc_1800158F0
0x1800158e6  lea     edi, [r12+57h]
0x1800158eb  jmp     loc_180015C58
0x1800158f0  mov     rbx, [r15+8]
0x1800158f4  test    rbx, rbx
0x1800158f7  jnz     short loc_180015903
0x1800158f9  mov     edi, 6E1h
0x1800158fe  jmp     loc_180015C58
0x180015903  cmp     r13w, [rbx+3Ch]
0x180015908  jge     short loc_180015914
0x18001590a  mov     edi, 7Ah ; 'z'
0x18001590f  jmp     loc_180015C58
0x180015914  mov     r14d, 2
0x18001591a  cmp     [rbx+8], r14d
0x18001591e  jnz     short loc_180015927
0x180015920  mov     [rsp+130h+var_E8], r12
0x180015925  jmp     short loc_180015930
0x180015927  mov     rax, [rbx+18h]
0x18001592b  mov     [rsp+130h+var_E8], rax
0x180015930  mov     eax, [rbx+20h]
0x180015933  lea     rcx, [rbx+28h]; lpFileTime
0x180015937  lea     rdx, [rsp+130h+SystemTime]; lpSystemTime
0x18001593c  mov     [rsp+130h+var_E0], eax
0x180015940  call    cs:__imp_FileTimeToSystemTime
0x180015946  test    eax, eax
0x180015948  jnz     short loc_18001595C
0x18001594a  call    cs:__imp_GetLastError
0x180015950  mov     edi, eax
0x180015952  test    eax, eax
0x180015954  jnz     loc_180015C58
0x18001595a  jmp     short loc_1800159D4
0x18001595c  mov     eax, [rbx+30h]
0x18001595f  mov     [rbp+57h+var_CC], eax
0x180015962  mov     eax, [rbx+34h]
0x180015965  mov     [rbp+57h+var_C8], eax
0x180015968  movzx   eax, word ptr [rbx+38h]
0x18001596c  mov     [rbp+57h+var_C4], ax
0x180015970  movzx   eax, word ptr [rbx+3Ah]
0x180015974  mov     [rbp+57h+var_C2], ax
0x180015978  mov     rcx, [rbx]
0x18001597b  test    rcx, rcx
0x18001597e  jz      short loc_18001598E
0x180015980  test    byte ptr [rcx+3Ah], 1
0x180015984  jz      short loc_18001598E
0x180015986  or      ax, r14w
0x18001598a  mov     [rbp+57h+var_C2], ax
0x18001598e  movsx   r14d, word ptr [rbx+3Ch]
0x180015993  mov     esi, r12d
0x180015996  mov     [rbp+57h+var_C0], r14d
0x18001599a  cmp     esi, r14d
0x18001599d  jge     short loc_1800159CB
0x18001599f  movsxd  rax, esi
0x1800159a2  lea     r8, [rbp+57h+var_B8]
0x1800159a6  xor     edx, edx; int
0x1800159a8  lea     rcx, [rax+rax*2]
0x1800159ac  lea     r8, [r8+rcx*8]; struct tagRPC_EE_INFO_PARAM *
0x1800159b0  lea     rcx, [rcx+8]
0x1800159b4  lea     rcx, [rbx+rcx*8]; struct tagParam *
0x1800159b8  call    ?ConvertPrivateParamToPublicParam@@YAJPEAUtagParam@@HPEAUtagRPC_EE_INFO_PARAM@@@Z; ConvertPrivateParamToPublicParam(tagParam *,int,tagRPC_EE_INFO_PARAM *)
0x1800159bd  mov     edi, eax
0x1800159bf  test    eax, eax
0x1800159c1  jnz     loc_180015C58
0x1800159c7  inc     esi
0x1800159c9  jmp     short loc_18001599A
0x1800159cb  mov     edi, r12d
0x1800159ce  mov     r14d, 2
0x1800159d4  mov     rax, [rbx]
0x1800159d7  mov     [r15+8], rax
0x1800159db  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800159e2  mov     eax, [rbp+57h+var_C0]
0x1800159e5  lea     esi, ds:9[rax*4]
0x1800159ec  add     esi, eax
0x1800159ee  mov     eax, 10h
0x1800159f3  mov     ecx, esi
0x1800159f5  mul     rcx
0x1800159f8  cmovb   rax, r15
0x1800159fc  mov     rcx, rax; dwBytes
0x1800159ff  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180015a04  mov     rbx, rax
0x180015a07  test    rax, rax
0x180015a0a  jz      loc_180015C58
0x180015a10  mov     rcx, cs:?pBaseNameUnicodeString@@3PEAU_UNICODE_STRING@@EA; _UNICODE_STRING * pBaseNameUnicodeString
0x180015a17  movzx   edx, word ptr [rcx]
0x180015a1a  mov     rax, [rcx+8]
0x180015a1e  add     edx, 2
0x180015a21  mov     [rbx+8], edx
0x180015a24  mov     [rbx], rax
0x180015a27  mov     [rbx+0Ch], r12d
0x180015a2b  mov     rcx, [rsp+130h+var_E8]
0x180015a30  test    rcx, rcx
0x180015a33  jz      short loc_180015A50
0x180015a35  mov     rax, r15
0x180015a38  inc     rax
0x180015a3b  cmp     [rcx+rax*2], r12w
0x180015a40  jnz     short loc_180015A38
0x180015a42  lea     eax, ds:2[rax*2]
0x180015a49  lea     rcx, [rsp+130h+var_E8]
0x180015a4e  jmp     short loc_180015A58
0x180015a50  mov     eax, r14d
0x180015a53  lea     rcx, [rsp+130h+var_108]
0x180015a58  mov     [rbx+10h], rcx
0x180015a5c  mov     r10d, r12d
0x180015a5f  mov     [rbx+18h], eax
0x180015a62  lea     rax, [rsp+130h+var_E0]
0x180015a67  mov     [rbx+1Ch], r12d
0x180015a6b  mov     [rbx+20h], rax
0x180015a6f  lea     rax, [rsp+130h+SystemTime]
0x180015a74  mov     [rbx+28h], r13
0x180015a78  mov     [rbx+30h], rax
0x180015a7c  lea     rax, [rbp+57h+var_CC]
0x180015a80  mov     qword ptr [rbx+38h], 10h
0x180015a88  mov     [rbx+40h], rax
0x180015a8c  lea     rax, [rbp+57h+var_C8]
0x180015a90  mov     [rbx+48h], r13
0x180015a94  mov     [rbx+50h], rax
0x180015a98  lea     rax, [rbp+57h+var_C4]
0x180015a9c  mov     [rbx+58h], r13
0x180015aa0  mov     [rbx+60h], rax
0x180015aa4  lea     rax, [rbp+57h+var_C2]
0x180015aa8  mov     qword ptr [rbx+68h], 2
0x180015ab0  mov     [rbx+70h], rax
0x180015ab4  mov     qword ptr [rbx+78h], 2
0x180015abc  movzx   eax, word ptr [rbp+57h+var_C0]
0x180015ac0  mov     [rsp+130h+var_10C], ax
0x180015ac5  lea     rax, [rsp+130h+var_10C]
0x180015aca  mov     [rbx+80h], rax
0x180015ad1  mov     qword ptr [rbx+88h], 2
0x180015adc  cmp     [rbp+57h+var_C0], r12d
0x180015ae0  jle     loc_180015C2C
0x180015ae6  lea     r9d, ds:9[r10*4]
0x180015aee  movsxd  rax, r10d
0x180015af1  add     r9d, r10d
0x180015af4  mov     ecx, r9d
0x180015af7  add     rcx, rcx
0x180015afa  lea     r8, [rax+rax*2]
0x180015afe  lea     rax, [rbp+57h+var_B8]
0x180015b02  lea     rax, [rax+r8*8]
0x180015b06  mov     [rbx+rcx*8], rax
0x180015b0a  lea     rax, [rsp+130h+var_110]
0x180015b0f  mov     [rbx+rcx*8+8], r13
0x180015b14  mov     [rbx+rcx*8+10h], rax
0x180015b19  lea     rax, [r9+2]
0x180015b1d  mov     qword ptr [rbx+rcx*8+18h], 1
0x180015b26  add     rax, rax
0x180015b29  lea     rcx, [rsp+130h+var_108]
0x180015b2e  mov     [rbx+rax*8], rcx
0x180015b32  lea     rcx, [rsp+130h+var_100]
0x180015b37  mov     qword ptr [rbx+rax*8+8], 2
0x180015b40  lea     rax, [r9+3]
0x180015b44  add     rax, rax
0x180015b47  mov     [rbx+rax*8], rcx
0x180015b4b  lea     rcx, [rsp+130h+var_F8]
0x180015b50  mov     [rbx+rax*8+8], r13
0x180015b55  lea     rax, [r9+4]
0x180015b59  add     rax, rax
0x180015b5c  mov     [rbx+rax*8], rcx
0x180015b60  mov     qword ptr [rbx+rax*8+8], 8
0x180015b69  mov     ecx, [rbp+r8*8+57h+var_B8]
0x180015b6e  sub     ecx, 1
0x180015b71  jz      loc_180015BF7
0x180015b77  sub     ecx, 1
0x180015b7a  jz      short loc_180015BD8
0x180015b7c  sub     ecx, 1
0x180015b7f  jz      short loc_180015BBE
0x180015b81  sub     ecx, 1
0x180015b84  jz      short loc_180015BAD
0x180015b86  cmp     ecx, 1
0x180015b89  jnz     loc_180015C1F
0x180015b8f  lea     ecx, [r9+4]
0x180015b93  add     rcx, rcx
0x180015b96  lea     rax, [rbp+57h+var_B0]
0x180015b9a  lea     rax, [rax+r8*8]
0x180015b9e  mov     [rbx+rcx*8], rax
0x180015ba2  mov     qword ptr [rbx+rcx*8+8], 8
0x180015bab  jmp     short loc_180015C1F
0x180015bad  movsx   eax, word ptr [rbp+r8*8+57h+var_B0]
0x180015bb3  mov     [rsp+130h+var_104], eax
0x180015bb7  lea     rax, [rsp+130h+var_104]
0x180015bbc  jmp     short loc_180015BC6
0x180015bbe  lea     rax, [rbp+57h+var_B0]
0x180015bc2  lea     rax, [rax+r8*8]
0x180015bc6  lea     ecx, [r9+3]
0x180015bca  add     rcx, rcx
0x180015bcd  mov     [rbx+rcx*8], rax
0x180015bd1  mov     [rbx+rcx*8+8], r13
0x180015bd6  jmp     short loc_180015C1F
0x180015bd8  mov     r11, [rbp+r8*8+57h+var_B0]
0x180015bdd  mov     rdx, r15
0x180015be0  inc     rdx
0x180015be3  cmp     [r11+rdx*2], r12w
0x180015be8  jnz     short loc_180015BE0
0x180015bea  lea     ecx, [r9+2]
0x180015bee  lea     eax, ds:2[rdx*2]
0x180015bf5  jmp     short loc_180015C0F
0x180015bf7  mov     r11, [rbp+r8*8+57h+var_B0]
0x180015bfc  mov     rdx, r15
0x180015bff  inc     rdx
0x180015c02  cmp     [r11+rdx], r12b
0x180015c06  jnz     short loc_180015BFF
0x180015c08  lea     ecx, [r9+1]
0x180015c0c  lea     eax, [rdx+1]
0x180015c0f  add     rcx, rcx
0x180015c12  mov     [rbx+rcx*8+0Ch], r12d
0x180015c17  mov     [rbx+rcx*8+8], eax
0x180015c1b  mov     [rbx+rcx*8], r11
0x180015c1f  inc     r10d
0x180015c22  cmp     r10d, [rbp+57h+var_C0]
0x180015c26  jl      loc_180015AE6
0x180015c2c  mov     rcx, cs:RpcEtwGuid_Context
0x180015c33  lea     rdx, RpcEEInfoEvent
0x180015c3a  mov     r9, rbx
0x180015c3d  mov     r8d, esi
0x180015c40  call    cs:__imp_EtwEventWrite
0x180015c46  test    eax, eax
0x180015c48  mov     ecx, 0Eh
0x180015c4d  cmovnz  edi, ecx
0x180015c50  mov     rcx, rbx; lpMem
0x180015c53  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180015c58  mov     eax, edi
0x180015c5a  mov     rcx, [rbp+57h+var_50]
0x180015c5e  xor     rcx, rsp; StackCookie
0x180015c61  call    __security_check_cookie
0x180015c66  add     rsp, 0F8h
0x180015c6d  pop     r15
0x180015c6f  pop     r14
0x180015c71  pop     r13
0x180015c73  pop     r12
0x180015c75  pop     rdi
0x180015c76  pop     rsi
0x180015c77  pop     rbx
0x180015c78  pop     rbp
0x180015c79  retn
```
