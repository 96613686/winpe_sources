# _drr_BuildChangeSet

- ea: `0x180004224`
- end: `0x18000457c`
- name: `_drr_BuildChangeSet`
- size: `856`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005c00`
- `0x180006230`

## callees

- `0x180003f4c`
- `0x180004224`
- `0x18000d886`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000431e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000436f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800043ec`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000431e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000436f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800043ec`

## pseudocode

```c
__int64 __fastcall drr_BuildChangeSet(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, _QWORD *a6)
{
  const void **v6; // rdi
  const void **v8; // rbx
  __int64 v9; // rsi
  unsigned int v10; // r14d
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // r13
  char *v13; // rbp
  unsigned __int16 *v14; // rsi
  int v15; // eax
  __int16 v16; // cx
  __int64 v17; // rdx
  __int16 v18; // ax
  __int16 v19; // ax
  __int64 v20; // rdx
  __int16 v21; // ax
  __int64 v22; // rdx

  v6 = *(const void ***)a2;
  v8 = *(const void ***)a3;
  v9 = a1;
  v10 = 0;
  v11 = *(_QWORD *)a2 + 8LL * *(unsigned int *)(a2 + 8);
  v12 = *(_QWORD *)a3 + 8LL * *(unsigned int *)(a3 + 8);
  if ( *(_QWORD *)a2 >= v11 )
  {
    while ( 1 )
    {
LABEL_70:
      if ( (unsigned __int64)v8 >= v12 )
        return v10;
      v21 = *((_WORD *)*v8 + 52);
      if ( (v21 & 1) != 0 )
      {
        if ( !a4 )
          *((_WORD *)*v8 + 52) = v21 & 0xFFFB;
      }
      else
      {
        if ( a4 )
          v22 = a5 != 0 ? 4 : 1;
        else
          v22 = 5;
        v10 = drr_AddChangeToSet(v9, v22);
        if ( v10 )
          return v10;
      }
      ++v8;
    }
  }
  while ( (unsigned __int64)v8 < v12 )
  {
    v13 = (char *)*v8;
    v14 = (unsigned __int16 *)*v6;
    v15 = memcmp_0(*v6, *v8, 0x60u);
    if ( !v15 )
    {
      if ( *((_BYTE *)v14 + 1) == 48 )
      {
        ++v6;
        ++v8;
LABEL_6:
        v9 = a1;
        goto LABEL_53;
      }
      v16 = *((_WORD *)v13 + 52);
      if ( (v16 & 4) != 0 )
      {
        ++v6;
        ++v8;
        if ( a4 )
        {
          v17 = 2 * (v14[52] & 1u) + 2;
        }
        else
        {
          if ( (v16 & 1) == 0 )
            goto LABEL_47;
          v17 = 4;
        }
        goto LABEL_52;
      }
      if ( (v14[52] & 0xA) != 0 )
        goto LABEL_30;
      v18 = v14[52] & 1;
      if ( (v16 & 1) != 0 )
      {
        if ( v18 )
          goto LABEL_23;
        if ( a4 )
        {
          if ( CompareFileTime((const FILETIME *)v13 + 12, (const FILETIME *)v14 + 12) >= 0 )
            v17 = 5;
          else
            v17 = 0;
        }
        else
        {
          v17 = 3;
          *((_QWORD *)v14 + 12) = *a6;
        }
      }
      else
      {
        if ( v18 )
        {
          ++v6;
          ++v8;
          v17 = ((CompareFileTime((const FILETIME *)v13 + 12, (const FILETIME *)v14 + 12) >> 31) & 1u) + 3;
          goto LABEL_52;
        }
LABEL_23:
        if ( ((_BYTE)v14[52] & (unsigned __int8)v16 & 1) != 0 )
          goto LABEL_30;
        if ( (v16 & 8) == 0 || a4 )
        {
          if ( *(_QWORD *)(v14 + 54) == *(_QWORD *)(v13 + 108)
            && *(_QWORD *)(v14 + 58) == *(_QWORD *)(v13 + 116)
            && *((_DWORD *)v14 + 31) == *((_DWORD *)v13 + 31) )
          {
LABEL_30:
            ++v6;
LABEL_46:
            ++v8;
LABEL_47:
            v9 = a1;
            goto LABEL_53;
          }
          if ( a4 && CompareFileTime((const FILETIME *)v13 + 12, (const FILETIME *)v14 + 12) < 0 )
            v17 = 2;
          else
            v17 = 3;
        }
        else
        {
          v17 = 1;
          *((_WORD *)v13 + 52) = v16 & 0xFFF7;
        }
      }
      ++v6;
LABEL_51:
      ++v8;
      goto LABEL_52;
    }
    if ( v15 >= 0 )
    {
      v19 = *((_WORD *)v13 + 52);
      if ( (v19 & 1) != 0 )
      {
        if ( !a4 )
          *((_WORD *)v13 + 52) = v19 & 0xFFFB;
        goto LABEL_46;
      }
      if ( (v19 & 8) != 0 )
        goto LABEL_46;
      if ( a4 )
        v17 = a5 != 0 ? 4 : 1;
      else
        v17 = 5;
      goto LABEL_51;
    }
    if ( (v14[52] & 0xA) != 0 )
    {
      ++v6;
      goto LABEL_6;
    }
    if ( (v14[52] & 1) != 0 )
      v17 = 5 - (unsigned int)(a4 != 0);
    else
      v17 = a4 == 0;
    ++v6;
LABEL_52:
    v9 = a1;
    v10 = drr_AddChangeToSet(a1, v17);
    if ( v10 )
      return v10;
LABEL_53:
    if ( (unsigned __int64)v6 >= v11 )
      goto LABEL_70;
  }
  while ( 1 )
  {
    if ( (*((_BYTE *)*v6 + 104) & 0xA) == 0 )
    {
      v20 = (*((_BYTE *)*v6 + 104) & 1) != 0 ? 5 - (unsigned int)(a4 != 0) : (unsigned __int8)(a4 == 0);
      v10 = drr_AddChangeToSet(v9, v20);
      if ( v10 )
        return v10;
    }
    if ( (unsigned __int64)++v6 >= v11 )
      goto LABEL_70;
  }
}

```

## disassembly

```asm
0x180004224  mov     [rsp+arg_18], rbx
0x180004229  push    rbp
0x18000422a  push    rsi
0x18000422b  push    rdi
0x18000422c  push    r12
0x18000422e  push    r13
0x180004230  push    r14
0x180004232  push    r15
0x180004234  sub     rsp, 30h
0x180004238  mov     rdi, [rdx]
0x18000423b  mov     r15d, r9d
0x18000423e  mov     eax, [rdx+8]
0x180004241  xor     r9d, r9d
0x180004244  mov     rbx, [r8]
0x180004247  mov     rsi, rcx
0x18000424a  mov     [rsp+68h+var_48], rcx
0x18000424f  mov     r14d, r9d
0x180004252  mov     ecx, 0FFFBh
0x180004257  lea     r12, [rdi+rax*8]
0x18000425b  mov     eax, [r8+8]
0x18000425f  lea     r10d, [r9+1]
0x180004263  lea     r13, [rbx+rax*8]
0x180004267  cmp     rdi, r12
0x18000426a  jnb     loc_18000455C
0x180004270  cmp     rbx, r13
0x180004273  jnb     loc_1800044BF
0x180004279  mov     rbp, [rbx]
0x18000427c  mov     r8d, 60h ; '`'; Size
0x180004282  mov     rsi, [rdi]
0x180004285  mov     rdx, rbp; Buf2
0x180004288  mov     rcx, rsi; Buf1
0x18000428b  call    memcmp_0
0x180004290  xor     r9d, r9d
0x180004293  test    eax, eax
0x180004295  jnz     loc_180004407
0x18000429b  cmp     byte ptr [rsi+1], 30h ; '0'
0x18000429f  jnz     short loc_1800042B3
0x1800042a1  add     rdi, 8
0x1800042a5  add     rbx, 8
0x1800042a9  mov     rsi, [rsp+68h+var_48]
0x1800042ae  jmp     loc_1800044AB
0x1800042b3  movzx   ecx, word ptr [rbp+68h]
0x1800042b7  test    cl, 4
0x1800042ba  jz      short loc_1800042F4
0x1800042bc  add     rdi, 8
0x1800042c0  add     rbx, 8
0x1800042c4  test    r15d, r15d
0x1800042c7  jz      short loc_1800042DC
0x1800042c9  movzx   eax, word ptr [rsi+68h]
0x1800042cd  and     eax, 1
0x1800042d0  lea     edx, ds:2[rax*2]
0x1800042d7  jmp     loc_18000448D
0x1800042dc  mov     r10d, 1
0x1800042e2  test    r10b, cl
0x1800042e5  jz      loc_180004463
0x1800042eb  lea     edx, [r10+3]
0x1800042ef  jmp     loc_18000448D
0x1800042f4  test    byte ptr [rsi+68h], 0Ah
0x1800042f8  mov     r10d, 1
0x1800042fe  jnz     loc_1800043D6
0x180004304  movzx   eax, word ptr [rsi+68h]
0x180004308  and     ax, r10w
0x18000430c  test    r10b, cl
0x18000430f  jnz     short loc_180004348
0x180004311  test    ax, ax
0x180004314  jz      short loc_180004395
0x180004316  lea     rdx, [rsi+60h]; lpFileTime2
0x18000431a  lea     rcx, [rbp+60h]; lpFileTime1
0x18000431e  call    cs:__imp_CompareFileTime
0x180004324  mov     edx, eax
0x180004326  mov     rax, rbx
0x180004329  test    edx, edx
0x18000432b  cmovs   rax, rdi
0x18000432f  sar     edx, 1Fh
0x180004332  and     edx, 1
0x180004335  add     rdi, 8
0x180004339  add     rbx, 8
0x18000433d  add     edx, 3
0x180004340  mov     rsi, [rax]
0x180004343  jmp     loc_18000448D
0x180004348  test    ax, ax
0x18000434b  jnz     short loc_180004395
0x18000434d  test    r15d, r15d
0x180004350  jnz     short loc_180004367
0x180004352  mov     rax, [rsp+68h+arg_28]
0x18000435a  lea     edx, [r15+3]
0x18000435e  mov     rax, [rax]
0x180004361  mov     [rsi+60h], rax
0x180004365  jmp     short loc_18000438C
0x180004367  lea     rcx, [rbp+60h]; lpFileTime1
0x18000436b  lea     rdx, [rsi+60h]; lpFileTime2
0x18000436f  call    cs:__imp_CompareFileTime
0x180004375  xor     r9d, r9d
0x180004378  test    eax, eax
0x18000437a  jns     short loc_180004384
0x18000437c  mov     edx, r9d
0x18000437f  mov     rsi, [rdi]
0x180004382  jmp     short loc_18000438C
0x180004384  mov     rsi, [rbx]
0x180004387  mov     edx, 5
0x18000438c  add     rdi, 8
0x180004390  jmp     loc_180004489
0x180004395  mov     al, cl
0x180004397  and     al, [rsi+68h]
0x18000439a  test    r10b, al
0x18000439d  jnz     short loc_1800043D6
0x18000439f  test    cl, 8
0x1800043a2  jz      short loc_1800043BA
0x1800043a4  test    r15d, r15d
0x1800043a7  jnz     short loc_1800043BA
0x1800043a9  mov     eax, 0FFF7h
0x1800043ae  mov     edx, r10d
0x1800043b1  and     cx, ax
0x1800043b4  mov     [rbp+68h], cx
0x1800043b8  jmp     short loc_18000437F
0x1800043ba  mov     rax, [rsi+6Ch]
0x1800043be  cmp     rax, [rbp+6Ch]
0x1800043c2  jnz     short loc_1800043DF
0x1800043c4  mov     rax, [rsi+74h]
0x1800043c8  cmp     rax, [rbp+74h]
0x1800043cc  jnz     short loc_1800043DF
0x1800043ce  mov     eax, [rsi+7Ch]
0x1800043d1  cmp     eax, [rbp+7Ch]
0x1800043d4  jnz     short loc_1800043DF
0x1800043d6  add     rdi, 8
0x1800043da  jmp     loc_18000445F
0x1800043df  test    r15d, r15d
0x1800043e2  jz      short loc_180004400
0x1800043e4  lea     rdx, [rsi+60h]; lpFileTime2
0x1800043e8  lea     rcx, [rbp+60h]; lpFileTime1
0x1800043ec  call    cs:__imp_CompareFileTime
0x1800043f2  test    eax, eax
0x1800043f4  jns     short loc_1800043FD
0x1800043f6  mov     edx, 2
0x1800043fb  jmp     short loc_18000437F
0x1800043fd  mov     rsi, [rbx]
0x180004400  mov     edx, 3
0x180004405  jmp     short loc_18000438C
0x180004407  jns     short loc_180004439
0x180004409  test    byte ptr [rsi+68h], 0Ah
0x18000440d  jz      short loc_180004418
0x18000440f  add     rdi, 8
0x180004413  jmp     loc_1800042A9
0x180004418  test    byte ptr [rsi+68h], 1
0x18000441c  jnz     short loc_180004429
0x18000441e  test    r15d, r15d
0x180004421  mov     edx, r9d
0x180004424  setz    dl
0x180004427  jmp     short loc_180004433
0x180004429  mov     eax, r15d
0x18000442c  neg     eax
0x18000442e  sbb     edx, edx
0x180004430  add     edx, 5
0x180004433  add     rdi, 8
0x180004437  jmp     short loc_18000448D
0x180004439  movzx   eax, word ptr [rbp+68h]
0x18000443d  mov     r10d, 1
0x180004443  test    r10b, al
0x180004446  jz      short loc_18000445B
0x180004448  test    r15d, r15d
0x18000444b  jnz     short loc_18000445F
0x18000444d  mov     ecx, 0FFFBh
0x180004452  and     ax, cx
0x180004455  mov     [rbp+68h], ax
0x180004459  jmp     short loc_18000445F
0x18000445b  test    al, 8
0x18000445d  jz      short loc_18000446A
0x18000445f  add     rbx, 8
0x180004463  mov     rsi, [rsp+68h+var_48]
0x180004468  jmp     short loc_1800044B1
0x18000446a  mov     rsi, rbp
0x18000446d  test    r15d, r15d
0x180004470  jnz     short loc_180004478
0x180004472  lea     edx, [r15+5]
0x180004476  jmp     short loc_180004489
0x180004478  mov     eax, [rsp+68h+arg_20]
0x18000447f  neg     eax
0x180004481  sbb     edx, edx
0x180004483  and     edx, 3
0x180004486  add     edx, r10d
0x180004489  add     rbx, 8
0x18000448d  mov     r8, rsi
0x180004490  mov     rsi, [rsp+68h+var_48]
0x180004495  mov     rcx, rsi
0x180004498  call    _drr_AddChangeToSet
0x18000449d  xor     r9d, r9d
0x1800044a0  mov     r14d, eax
0x1800044a3  test    eax, eax
0x1800044a5  jnz     loc_180004561
0x1800044ab  mov     r10d, 1
0x1800044b1  cmp     rdi, r12
0x1800044b4  jb      loc_180004270
0x1800044ba  jmp     loc_180004557
0x1800044bf  mov     r8, [rdi]
0x1800044c2  test    byte ptr [r8+68h], 0Ah
0x1800044c7  jnz     short loc_1800044FA
0x1800044c9  test    [r8+68h], r10b
0x1800044cd  jnz     short loc_1800044DA
0x1800044cf  test    r15d, r15d
0x1800044d2  mov     edx, r9d
0x1800044d5  setz    dl
0x1800044d8  jmp     short loc_1800044E4
0x1800044da  mov     eax, r15d
0x1800044dd  neg     eax
0x1800044df  sbb     edx, edx
0x1800044e1  add     edx, 5
0x1800044e4  mov     rcx, rsi
0x1800044e7  call    _drr_AddChangeToSet
0x1800044ec  xor     r9d, r9d
0x1800044ef  mov     r14d, eax
0x1800044f2  test    eax, eax
0x1800044f4  jnz     short loc_180004561
0x1800044f6  lea     r10d, [rax+1]
0x1800044fa  add     rdi, 8
0x1800044fe  cmp     rdi, r12
0x180004501  jb      short loc_1800044BF
0x180004503  jmp     short loc_180004557
0x180004505  mov     r8, [rbx]
0x180004508  movzx   eax, word ptr [r8+68h]
0x18000450d  test    r10b, al
0x180004510  jz      short loc_180004521
0x180004512  test    r15d, r15d
0x180004515  jnz     short loc_180004553
0x180004517  and     ax, cx
0x18000451a  mov     [r8+68h], ax
0x18000451f  jmp     short loc_180004553
0x180004521  test    r15d, r15d
0x180004524  jnz     short loc_18000452C
0x180004526  lea     edx, [r15+5]
0x18000452a  jmp     short loc_18000453D
0x18000452c  mov     eax, [rsp+68h+arg_20]
0x180004533  neg     eax
0x180004535  sbb     edx, edx
0x180004537  and     edx, 3
0x18000453a  add     edx, r10d
0x18000453d  mov     rcx, rsi
0x180004540  call    _drr_AddChangeToSet
0x180004545  xor     r9d, r9d
0x180004548  mov     r14d, eax
0x18000454b  test    eax, eax
0x18000454d  jnz     short loc_180004561
0x18000454f  lea     r10d, [rax+1]
0x180004553  add     rbx, 8
0x180004557  mov     ecx, 0FFFBh
0x18000455c  cmp     rbx, r13
0x18000455f  jb      short loc_180004505
0x180004561  mov     rbx, [rsp+68h+arg_18]
0x180004569  mov     eax, r14d
0x18000456c  add     rsp, 30h
0x180004570  pop     r15
0x180004572  pop     r14
0x180004574  pop     r13
0x180004576  pop     r12
0x180004578  pop     rdi
0x180004579  pop     rsi
0x18000457a  pop     rbp
0x18000457b  retn
```
