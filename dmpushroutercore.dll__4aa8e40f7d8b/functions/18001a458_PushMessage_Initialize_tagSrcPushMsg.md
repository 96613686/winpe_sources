# PushMessage::Initialize(tagSrcPushMsg *)

- ea: `0x18001a458`
- end: `0x18001abcc`
- name: `?Initialize@PushMessage@@QEAAJPEAUtagSrcPushMsg@@@Z`
- size: `1908`
- prototype: `__int64 __fastcall(PushMessage *__hidden this, struct tagSrcPushMsg *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800174e4`

## callees

- `0x1800127c4`
- `0x180013528`
- `0x180017258`
- `0x180017384`
- `0x18001a458`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a936`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aba2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001abac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a936`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aba2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001abac`
- `DMCmnUtils!BigStrcat` at `0x18001a96c`
- `DMCmnUtils!BigStrcat` at `0x18001a96c`
- `DMCmnUtils!CopyString` at `0x18001a4df`
- `DMCmnUtils!CopyString` at `0x18001a646`
- `DMCmnUtils!CopyString` at `0x18001a7b1`
- `DMCmnUtils!CopyString` at `0x18001a91c`
- `DMCmnUtils!CopyString` at `0x18001ab2c`
- `DMCmnUtils!CopyString` at `0x18001a4df`
- `DMCmnUtils!CopyString` at `0x18001a646`
- `DMCmnUtils!CopyString` at `0x18001a7b1`
- `DMCmnUtils!CopyString` at `0x18001a91c`
- `DMCmnUtils!CopyString` at `0x18001ab2c`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001a5fe`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001a769`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001a8d4`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001aae4`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001a5fe`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001a769`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001a8d4`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001aae4`

## string_xrefs

- `0x18001a4f3`: `X-WAP-Initiator-URI`
- `0x18001a5f4`: `X-WAP-Initiator-URI`
- `0x18001a94b`: `X-WAP-Initiator-URI`
- `0x18001a66a`: `X-WAP-Content-URI`
- `0x18001a75f`: `X-WAP-Content-URI`

## pseudocode

```c
__int64 __fastcall PushMessage::Initialize(PushMessage *this, struct tagSrcPushMsg *a2)
{
  signed int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r8
  unsigned __int16 *v7; // rdi
  const wchar_t *v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rsi
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rcx
  int v15; // r8d
  unsigned __int16 v16; // ax
  int v17; // eax
  unsigned __int16 *v18; // rdi
  const wchar_t *v19; // rax
  __int64 v20; // rdx
  unsigned __int64 v21; // rsi
  __int64 v22; // rdx
  unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // rbx
  unsigned __int16 *v25; // rcx
  int v26; // r8d
  unsigned __int16 v27; // ax
  int v28; // eax
  unsigned __int16 *v29; // rdi
  const wchar_t *v30; // rax
  __int64 v31; // rdx
  unsigned __int64 v32; // rsi
  __int64 v33; // rdx
  unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rbx
  unsigned __int16 *v36; // rcx
  int v37; // r8d
  unsigned __int16 v38; // ax
  int v39; // eax
  unsigned __int16 *v40; // rax
  unsigned __int16 *v41; // rdi
  const unsigned __int16 *v42; // rax
  HLOCAL v43; // rsi
  __int64 v44; // rdx
  unsigned __int64 v45; // r15
  __int64 v46; // rcx
  _WORD *v47; // rax
  const unsigned __int16 *v48; // rbx
  unsigned __int16 *v49; // rcx
  int v50; // r8d
  unsigned __int16 v51; // ax
  int v52; // eax
  __int64 v54; // [rsp+28h] [rbp-38h]
  HLOCAL v55; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL v57; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v58; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v59; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v60; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v61; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v62; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v63; // [rsp+B8h] [rbp+58h] BYREF

  v55 = 0;
  hMem = 0;
  v57 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    goto LABEL_105;
  }
  v5 = *((_QWORD *)a2 + 4);
  if ( !v5 || (v4 = PersistObject::Set(this, 4, v5), v4 >= 0) )
  {
    v6 = *((_QWORD *)a2 + 5);
    if ( !v6 || (v4 = PersistObject::Set(this, 8, v6, *((unsigned int *)a2 + 12)), v4 >= 0) )
    {
      v4 = CopyString(*((const unsigned __int16 **)a2 + 1), 0xFFFFFFFF, (unsigned __int16 **)&hMem);
      if ( v4 >= 0 )
      {
        v7 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
        v8 = L"X-WAP-Initiator-URI";
        v59 = v7;
        v58 = v7;
        v9 = 0x7FFFFFFF;
        v61 = 0;
        v55 = 0;
        do
        {
          if ( !*v8 )
            break;
          ++v8;
          --v9;
        }
        while ( v9 );
        v4 = v9 == 0 ? 0x80070057 : 0;
        v10 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
        if ( v9 )
        {
          if ( v7 )
          {
            v11 = 0x7FFFFFFF;
            v12 = v7;
            do
            {
              if ( !*v12 )
                break;
              ++v12;
              --v11;
            }
            while ( v11 );
            v4 = v11 == 0 ? 0x80070057 : 0;
            if ( !v11 )
              goto LABEL_105;
            v13 = &v7[(0x7FFFFFFF - v11) & -(__int64)(v11 != 0)];
            while ( (unsigned int)FindEndOfHeader((const unsigned __int16 **)&v59, v13, &v61) )
            {
              v14 = v7;
              v15 = 0;
              if ( v61 )
              {
                while ( 1 )
                {
                  v16 = *v14++;
                  if ( v16 == 58 )
                    break;
                  if ( ++v15 >= v61 )
                    goto LABEL_25;
                }
                v60 = v14;
                v62 = v14 - v7 - 1;
                v63 = v61 - v62;
                if ( (unsigned int)Trim((const unsigned __int16 **)&v58, &v62) )
                {
                  if ( v62 == v10 && !InvStrCmpNIW(v58, L"X-WAP-Initiator-URI", v10) )
                  {
                    v17 = Trim((const unsigned __int16 **)&v60, &v63);
                    v4 = CopyString(v60, v17 != 0 ? v63 : 0, (unsigned __int16 **)&v55);
                    if ( v4 < 0 )
                      goto LABEL_105;
                    break;
                  }
                }
              }
LABEL_25:
              v7 = v59;
              v58 = v59;
            }
          }
          if ( v55 )
            goto LABEL_76;
          v18 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
          v19 = L"X-WAP-Content-URI";
          v58 = v18;
          v20 = 0x7FFFFFFF;
          v59 = v18;
          v61 = 0;
          v55 = 0;
          do
          {
            if ( !*v19 )
              break;
            ++v19;
            --v20;
          }
          while ( v20 );
          v4 = v20 == 0 ? 0x80070057 : 0;
          v21 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
          if ( !v20 )
            goto LABEL_105;
          if ( v18 )
          {
            v22 = 0x7FFFFFFF;
            v23 = v18;
            do
            {
              if ( !*v23 )
                break;
              ++v23;
              --v22;
            }
            while ( v22 );
            v4 = v22 == 0 ? 0x80070057 : 0;
            if ( !v22 )
              goto LABEL_105;
            v24 = &v18[(0x7FFFFFFF - v22) & -(__int64)(v22 != 0)];
            while ( (unsigned int)FindEndOfHeader((const unsigned __int16 **)&v58, v24, &v61) )
            {
              v25 = v18;
              v26 = 0;
              if ( v61 )
              {
                while ( 1 )
                {
                  v27 = *v25++;
                  if ( v27 == 58 )
                    break;
                  if ( ++v26 >= v61 )
                    goto LABEL_47;
                }
                v60 = v25;
                v62 = v25 - v18 - 1;
                v63 = v61 - v62;
                if ( (unsigned int)Trim((const unsigned __int16 **)&v59, &v62) )
                {
                  if ( v62 == v21 && !InvStrCmpNIW(v59, L"X-WAP-Content-URI", v21) )
                  {
                    v28 = Trim((const unsigned __int16 **)&v60, &v63);
                    v4 = CopyString(v60, v28 != 0 ? v63 : 0, (unsigned __int16 **)&v55);
                    if ( v4 < 0 )
                      goto LABEL_105;
                    break;
                  }
                }
              }
LABEL_47:
              v18 = v58;
              v59 = v58;
            }
          }
          if ( v55 )
            goto LABEL_74;
          v29 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
          v30 = L"Content-Location";
          v58 = v29;
          v31 = 0x7FFFFFFF;
          v59 = v29;
          v61 = 0;
          v55 = 0;
          do
          {
            if ( !*v30 )
              break;
            ++v30;
            --v31;
          }
          while ( v31 );
          v4 = v31 == 0 ? 0x80070057 : 0;
          v32 = (0x7FFFFFFF - v31) & -(__int64)(v31 != 0);
          if ( !v31 )
            goto LABEL_105;
          if ( v29 )
          {
            v33 = 0x7FFFFFFF;
            v34 = v29;
            do
            {
              if ( !*v34 )
                break;
              ++v34;
              --v33;
            }
            while ( v33 );
            v4 = v33 == 0 ? 0x80070057 : 0;
            if ( !v33 )
              goto LABEL_105;
            v35 = &v29[(0x7FFFFFFF - v33) & -(__int64)(v33 != 0)];
            while ( (unsigned int)FindEndOfHeader((const unsigned __int16 **)&v58, v35, &v61) )
            {
              v36 = v29;
              v37 = 0;
              if ( v61 )
              {
                while ( 1 )
                {
                  v38 = *v36++;
                  if ( v38 == 58 )
                    break;
                  if ( ++v37 >= v61 )
                    goto LABEL_69;
                }
                v60 = v36;
                v62 = v36 - v29 - 1;
                v63 = v61 - v62;
                if ( (unsigned int)Trim((const unsigned __int16 **)&v59, &v62) )
                {
                  if ( v62 == v32 && !InvStrCmpNIW(v59, L"Content-Location", v32) )
                  {
                    v39 = Trim((const unsigned __int16 **)&v60, &v63);
                    v4 = CopyString(v60, v39 != 0 ? v63 : 0, (unsigned __int16 **)&v55);
                    if ( v4 < 0 )
                      goto LABEL_105;
                    break;
                  }
                }
              }
LABEL_69:
              v29 = v58;
              v59 = v58;
            }
          }
          if ( v55 )
          {
LABEL_74:
            LocalFree(hMem);
            v54 = *((_QWORD *)a2 + 1);
            hMem = 0;
            v40 = BigStrcat(5u, L"X-WAP-Initiator-URI", L": ", v55, L"\r\n", v54);
            hMem = v40;
            if ( !v40 )
            {
              v4 = -2147024882;
              goto LABEL_105;
            }
          }
          else
          {
LABEL_76:
            v40 = (unsigned __int16 *)hMem;
          }
          v4 = PersistObject::Set(this, 2, v40);
          if ( v4 >= 0 )
          {
            v4 = PersistObject::Set(this, 0, *((_QWORD *)a2 + 2), *((unsigned int *)a2 + 6));
            if ( v4 >= 0 )
            {
              v41 = (unsigned __int16 *)hMem;
              v42 = L"X-Wap-Application-Id";
              v58 = (unsigned __int16 *)hMem;
              v43 = 0;
              v59 = (unsigned __int16 *)hMem;
              v44 = 0x7FFFFFFF;
              v61 = 0;
              v57 = 0;
              do
              {
                if ( !*v42 )
                  break;
                ++v42;
                --v44;
              }
              while ( v44 );
              v4 = v44 == 0 ? 0x80070057 : 0;
              v45 = (0x7FFFFFFF - v44) & -(__int64)(v44 != 0);
              if ( v44 )
              {
                if ( hMem )
                {
                  v46 = 0x7FFFFFFF;
                  v47 = hMem;
                  do
                  {
                    if ( !*v47 )
                      break;
                    ++v47;
                    --v46;
                  }
                  while ( v46 );
                  v4 = v46 == 0 ? 0x80070057 : 0;
                  if ( !v46 )
                    goto LABEL_105;
                  v48 = (const unsigned __int16 *)((char *)hMem
                                                 + 2
                                                 * ((0x7FFFFFFF - v46)
                                                  & ((unsigned __int128)-(__int128)(unsigned __int64)v46 >> 64)));
                  if ( (unsigned int)FindEndOfHeader((const unsigned __int16 **)&v58, v48, &v61) )
                  {
                    while ( 1 )
                    {
                      v49 = v41;
                      v50 = 0;
                      if ( v61 )
                      {
                        while ( 1 )
                        {
                          v51 = *v49++;
                          if ( v51 == 58 )
                            break;
                          if ( ++v50 >= v61 )
                            goto LABEL_96;
                        }
                        v60 = v49;
                        v62 = v49 - v41 - 1;
                        v63 = v61 - v62;
                        if ( (unsigned int)Trim((const unsigned __int16 **)&v59, &v62) )
                        {
                          if ( v62 == v45 && !InvStrCmpNIW(v59, L"X-Wap-Application-Id", v45) )
                            break;
                        }
                      }
LABEL_96:
                      v41 = v58;
                      v59 = v58;
                      if ( !(unsigned int)FindEndOfHeader((const unsigned __int16 **)&v58, v48, &v61) )
                        goto LABEL_99;
                    }
                    v52 = Trim((const unsigned __int16 **)&v60, &v63);
                    v4 = CopyString(v60, v52 != 0 ? v63 : 0, (unsigned __int16 **)&v57);
                    if ( v4 < 0 )
                      goto LABEL_105;
LABEL_99:
                    v43 = v57;
                  }
                }
                if ( !v43 || (v4 = PersistObject::Set(this, 3, v43), v4 >= 0) )
                {
                  v4 = PersistObject::Set(this, 5, 0);
                  if ( v4 >= 0 )
                  {
                    v4 = PersistObject::Set(this, 6, 0);
                    if ( v4 >= 0 )
                      v4 = PersistObject::Set(this, 7, *((unsigned int *)a2 + 7));
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_105:
  LocalFree(v55);
  LocalFree(hMem);
  LocalFree(v57);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001a458  mov     [rsp-38h+arg_0], rbx
0x18001a45d  push    rbp
0x18001a45e  push    rsi
0x18001a45f  push    rdi
0x18001a460  push    r12
0x18001a462  push    r13
0x18001a464  push    r14
0x18001a466  push    r15
0x18001a468  mov     rbp, rsp
0x18001a46b  sub     rsp, 60h
0x18001a46f  xor     r15d, r15d
0x18001a472  mov     r13, rdx
0x18001a475  mov     [rbp+var_30], r15
0x18001a479  mov     r12, rcx
0x18001a47c  mov     [rbp+hMem], r15
0x18001a480  mov     [rbp+var_20], r15
0x18001a484  test    rdx, rdx
0x18001a487  jnz     short loc_18001A493
0x18001a489  mov     ebx, 80004003h
0x18001a48e  jmp     loc_18001AB94
0x18001a493  mov     r8, [rdx+20h]
0x18001a497  test    r8, r8
0x18001a49a  jz      short loc_18001A4B0
0x18001a49c  mov     edx, 4
0x18001a4a1  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@PEBG@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ushort const *)
0x18001a4a6  mov     ebx, eax
0x18001a4a8  test    eax, eax
0x18001a4aa  js      loc_18001AB94
0x18001a4b0  mov     r8, [r13+28h]
0x18001a4b4  test    r8, r8
0x18001a4b7  jz      short loc_18001A4D4
0x18001a4b9  mov     r9d, [r13+30h]
0x18001a4bd  mov     edx, 8
0x18001a4c2  mov     rcx, r12
0x18001a4c5  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@QEAEK@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,uchar * const,ulong)
0x18001a4ca  mov     ebx, eax
0x18001a4cc  test    eax, eax
0x18001a4ce  js      loc_18001AB94
0x18001a4d4  mov     rcx, [r13+8]
0x18001a4d8  lea     r8, [rbp+hMem]
0x18001a4dc  or      edx, 0FFFFFFFFh
0x18001a4df  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001a4e5  mov     ebx, eax
0x18001a4e7  test    eax, eax
0x18001a4e9  js      loc_18001AB94
0x18001a4ef  mov     rdi, [r13+8]
0x18001a4f3  lea     rax, aXWapInitiatorU; "X-WAP-Initiator-URI"
0x18001a4fa  mov     r14d, 7FFFFFFFh
0x18001a500  mov     [rbp+var_10], rdi
0x18001a504  mov     [rbp+var_18], rdi
0x18001a508  mov     edx, r14d
0x18001a50b  mov     [rbp+arg_8], r15d
0x18001a50f  mov     [rbp+var_30], r15
0x18001a513  cmp     [rax], r15w
0x18001a517  jz      short loc_18001A523
0x18001a519  add     rax, 2
0x18001a51d  sub     rdx, 1
0x18001a521  jnz     short loc_18001A513
0x18001a523  mov     rax, rdx
0x18001a526  mov     r8d, 80070057h
0x18001a52c  neg     rax
0x18001a52f  mov     rcx, r14
0x18001a532  mov     rax, rdx
0x18001a535  sbb     ebx, ebx
0x18001a537  sub     rcx, rdx
0x18001a53a  not     ebx
0x18001a53c  and     ebx, r8d
0x18001a53f  neg     rax
0x18001a542  sbb     rsi, rsi
0x18001a545  and     rsi, rcx
0x18001a548  test    rdx, rdx
0x18001a54b  jz      loc_18001AB94
0x18001a551  test    rdi, rdi
0x18001a554  jz      loc_18001A65C
0x18001a55a  mov     rdx, r14
0x18001a55d  mov     rax, rdi
0x18001a560  cmp     [rax], r15w
0x18001a564  jz      short loc_18001A570
0x18001a566  add     rax, 2
0x18001a56a  sub     rdx, 1
0x18001a56e  jnz     short loc_18001A560
0x18001a570  mov     rax, rdx
0x18001a573  mov     rcx, r14
0x18001a576  neg     rax
0x18001a579  mov     rax, rdx
0x18001a57c  sbb     ebx, ebx
0x18001a57e  sub     rcx, rdx
0x18001a581  not     ebx
0x18001a583  and     ebx, r8d
0x18001a586  neg     rax
0x18001a589  sbb     r8, r8
0x18001a58c  and     r8, rcx
0x18001a58f  test    rdx, rdx
0x18001a592  jz      loc_18001AB94
0x18001a598  lea     rbx, [rdi+r8*2]
0x18001a59c  jmp     short loc_18001A610
0x18001a59e  mov     edx, [rbp+arg_8]
0x18001a5a1  mov     rcx, rdi
0x18001a5a4  mov     r8d, r15d
0x18001a5a7  test    edx, edx
0x18001a5a9  jz      short loc_18001A608
0x18001a5ab  movzx   eax, word ptr [rcx]
0x18001a5ae  add     rcx, 2
0x18001a5b2  cmp     ax, 3Ah ; ':'
0x18001a5b6  jz      short loc_18001A5C2
0x18001a5b8  inc     r8d
0x18001a5bb  cmp     r8d, edx
0x18001a5be  jb      short loc_18001A5AB
0x18001a5c0  jmp     short loc_18001A608
0x18001a5c2  mov     [rbp+var_8], rcx
0x18001a5c6  sub     rcx, rdi
0x18001a5c9  sar     rcx, 1
0x18001a5cc  lea     eax, [rcx-1]
0x18001a5cf  sub     edx, eax
0x18001a5d1  mov     [rbp+arg_10], eax
0x18001a5d4  mov     [rbp+arg_18], edx
0x18001a5d7  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x18001a5db  lea     rdx, [rbp+arg_10]; unsigned int *
0x18001a5df  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001a5e4  test    eax, eax
0x18001a5e6  jz      short loc_18001A608
0x18001a5e8  mov     eax, [rbp+arg_10]
0x18001a5eb  cmp     rax, rsi
0x18001a5ee  jnz     short loc_18001A608
0x18001a5f0  mov     rcx, [rbp+var_18]
0x18001a5f4  lea     rdx, aXWapInitiatorU; "X-WAP-Initiator-URI"
0x18001a5fb  mov     r8, rsi
0x18001a5fe  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18001a604  test    eax, eax
0x18001a606  jz      short loc_18001A62A
0x18001a608  mov     rdi, [rbp+var_10]
0x18001a60c  mov     [rbp+var_18], rdi
0x18001a610  lea     r8, [rbp+arg_8]; unsigned int *
0x18001a614  mov     rdx, rbx; unsigned __int16 *
0x18001a617  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x18001a61b  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x18001a620  test    eax, eax
0x18001a622  jnz     loc_18001A59E
0x18001a628  jmp     short loc_18001A656
0x18001a62a  lea     rdx, [rbp+arg_18]; unsigned int *
0x18001a62e  lea     rcx, [rbp+var_8]; unsigned __int16 **
0x18001a632  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001a637  mov     rcx, [rbp+var_8]
0x18001a63b  lea     r8, [rbp+var_30]
0x18001a63f  neg     eax
0x18001a641  sbb     edx, edx
0x18001a643  and     edx, [rbp+arg_18]
0x18001a646  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001a64c  mov     ebx, eax
0x18001a64e  test    eax, eax
0x18001a650  js      loc_18001AB94
0x18001a656  mov     r8d, 80070057h
0x18001a65c  cmp     [rbp+var_30], r15
0x18001a660  jnz     loc_18001A985
0x18001a666  mov     rdi, [r13+8]
0x18001a66a  lea     rax, aXWapContentUri; "X-WAP-Content-URI"
0x18001a671  mov     [rbp+var_18], rdi
0x18001a675  mov     rdx, r14
0x18001a678  mov     [rbp+var_10], rdi
0x18001a67c  mov     [rbp+arg_8], r15d
0x18001a680  mov     [rbp+var_30], r15
0x18001a684  cmp     [rax], r15w
0x18001a688  jz      short loc_18001A694
0x18001a68a  add     rax, 2
0x18001a68e  sub     rdx, 1
0x18001a692  jnz     short loc_18001A684
0x18001a694  mov     rax, rdx
0x18001a697  mov     rcx, r14
0x18001a69a  neg     rax
0x18001a69d  mov     rax, rdx
0x18001a6a0  sbb     ebx, ebx
0x18001a6a2  sub     rcx, rdx
0x18001a6a5  not     ebx
0x18001a6a7  and     ebx, r8d
0x18001a6aa  neg     rax
0x18001a6ad  sbb     rsi, rsi
0x18001a6b0  and     rsi, rcx
0x18001a6b3  test    rdx, rdx
0x18001a6b6  jz      loc_18001AB94
0x18001a6bc  test    rdi, rdi
0x18001a6bf  jz      loc_18001A7C7
0x18001a6c5  mov     rdx, r14
0x18001a6c8  mov     rax, rdi
0x18001a6cb  cmp     [rax], r15w
0x18001a6cf  jz      short loc_18001A6DB
0x18001a6d1  add     rax, 2
0x18001a6d5  sub     rdx, 1
0x18001a6d9  jnz     short loc_18001A6CB
0x18001a6db  mov     rax, rdx
0x18001a6de  mov     rcx, r14
0x18001a6e1  neg     rax
0x18001a6e4  mov     rax, rdx
0x18001a6e7  sbb     ebx, ebx
0x18001a6e9  sub     rcx, rdx
0x18001a6ec  not     ebx
0x18001a6ee  and     ebx, r8d
0x18001a6f1  neg     rax
0x18001a6f4  sbb     r8, r8
0x18001a6f7  and     r8, rcx
0x18001a6fa  test    rdx, rdx
0x18001a6fd  jz      loc_18001AB94
0x18001a703  lea     rbx, [rdi+r8*2]
0x18001a707  jmp     short loc_18001A77B
0x18001a709  mov     edx, [rbp+arg_8]
0x18001a70c  mov     rcx, rdi
0x18001a70f  mov     r8d, r15d
0x18001a712  test    edx, edx
0x18001a714  jz      short loc_18001A773
0x18001a716  movzx   eax, word ptr [rcx]
0x18001a719  add     rcx, 2
0x18001a71d  cmp     ax, 3Ah ; ':'
0x18001a721  jz      short loc_18001A72D
0x18001a723  inc     r8d
0x18001a726  cmp     r8d, edx
0x18001a729  jb      short loc_18001A716
0x18001a72b  jmp     short loc_18001A773
0x18001a72d  mov     [rbp+var_8], rcx
0x18001a731  sub     rcx, rdi
0x18001a734  sar     rcx, 1
0x18001a737  lea     eax, [rcx-1]
0x18001a73a  sub     edx, eax
0x18001a73c  mov     [rbp+arg_10], eax
0x18001a73f  mov     [rbp+arg_18], edx
0x18001a742  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x18001a746  lea     rdx, [rbp+arg_10]; unsigned int *
0x18001a74a  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001a74f  test    eax, eax
0x18001a751  jz      short loc_18001A773
0x18001a753  mov     eax, [rbp+arg_10]
0x18001a756  cmp     rax, rsi
0x18001a759  jnz     short loc_18001A773
0x18001a75b  mov     rcx, [rbp+var_10]
0x18001a75f  lea     rdx, aXWapContentUri; "X-WAP-Content-URI"
0x18001a766  mov     r8, rsi
0x18001a769  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18001a76f  test    eax, eax
0x18001a771  jz      short loc_18001A795
0x18001a773  mov     rdi, [rbp+var_18]
0x18001a777  mov     [rbp+var_10], rdi
0x18001a77b  lea     r8, [rbp+arg_8]; unsigned int *
0x18001a77f  mov     rdx, rbx; unsigned __int16 *
0x18001a782  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x18001a786  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x18001a78b  test    eax, eax
0x18001a78d  jnz     loc_18001A709
0x18001a793  jmp     short loc_18001A7C1
0x18001a795  lea     rdx, [rbp+arg_18]; unsigned int *
0x18001a799  lea     rcx, [rbp+var_8]; unsigned __int16 **
0x18001a79d  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001a7a2  mov     rcx, [rbp+var_8]
0x18001a7a6  lea     r8, [rbp+var_30]
0x18001a7aa  neg     eax
0x18001a7ac  sbb     edx, edx
0x18001a7ae  and     edx, [rbp+arg_18]
0x18001a7b1  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001a7b7  mov     ebx, eax
0x18001a7b9  test    eax, eax
0x18001a7bb  js      loc_18001AB94
0x18001a7c1  mov     r8d, 80070057h
0x18001a7c7  cmp     [rbp+var_30], r15
0x18001a7cb  jnz     loc_18001A932
0x18001a7d1  mov     rdi, [r13+8]
0x18001a7d5  lea     rax, aContentLocatio; "Content-Location"
0x18001a7dc  mov     [rbp+var_18], rdi
0x18001a7e0  mov     rdx, r14
0x18001a7e3  mov     [rbp+var_10], rdi
0x18001a7e7  mov     [rbp+arg_8], r15d
0x18001a7eb  mov     [rbp+var_30], r15
0x18001a7ef  cmp     [rax], r15w
0x18001a7f3  jz      short loc_18001A7FF
0x18001a7f5  add     rax, 2
0x18001a7f9  sub     rdx, 1
0x18001a7fd  jnz     short loc_18001A7EF
0x18001a7ff  mov     rax, rdx
0x18001a802  mov     rcx, r14
0x18001a805  neg     rax
0x18001a808  mov     rax, rdx
0x18001a80b  sbb     ebx, ebx
0x18001a80d  sub     rcx, rdx
0x18001a810  not     ebx
0x18001a812  and     ebx, r8d
0x18001a815  neg     rax
0x18001a818  sbb     rsi, rsi
0x18001a81b  and     rsi, rcx
0x18001a81e  test    rdx, rdx
0x18001a821  jz      loc_18001AB94
0x18001a827  test    rdi, rdi
0x18001a82a  jz      loc_18001A92C
0x18001a830  mov     rdx, r14
0x18001a833  mov     rax, rdi
0x18001a836  cmp     [rax], r15w
0x18001a83a  jz      short loc_18001A846
0x18001a83c  add     rax, 2
0x18001a840  sub     rdx, 1
0x18001a844  jnz     short loc_18001A836
0x18001a846  mov     rax, rdx
0x18001a849  mov     rcx, r14
0x18001a84c  neg     rax
0x18001a84f  mov     rax, rdx
0x18001a852  sbb     ebx, ebx
  ... truncated ...
```
