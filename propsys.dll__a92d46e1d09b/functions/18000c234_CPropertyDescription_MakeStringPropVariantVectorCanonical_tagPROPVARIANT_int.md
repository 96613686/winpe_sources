# CPropertyDescription::_MakeStringPropVariantVectorCanonical(tagPROPVARIANT *,int *)

- ea: `0x18000c234`
- end: `0x18000c543`
- name: `?_MakeStringPropVariantVectorCanonical@CPropertyDescription@@AEAAJPEAUtagPROPVARIANT@@PEAH@Z`
- size: `783`
- prototype: `__int64 __fastcall(CPropertyDescription *__hidden this, struct tagPROPVARIANT *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008870`

## callees

- `0x18000c234`
- `0x18000c54c`
- `0x18000c5a4`
- `0x18002cfd0`
- `0x180041f14`
- `0x180042094`
- `0x180069094`
- `0x18006ed20`
- `0x18006fb8c`
- `0x180083bc0`
- `0x180095ee0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c345`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c52d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c52d`

## pseudocode

```c
__int64 __fastcall CPropertyDescription::_MakeStringPropVariantVectorCanonical(
        CPropertyDescription *this,
        struct tagPROPVARIANT *a2,
        int *a3)
{
  int v3; // ebx
  unsigned int ulVal; // eax
  int TreeValueCanonical; // edi
  unsigned int v8; // r14d
  unsigned __int16 *v9; // rbp
  __int64 v10; // r15
  unsigned __int16 *ValueStart; // rax
  __int64 v12; // rax
  _WORD *v13; // rcx
  unsigned int v14; // r8d
  unsigned int v15; // ecx
  unsigned int v16; // edx
  BOOL v17; // eax
  BYTE *pData; // r9
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 v22; // r8
  unsigned int v23; // r15d
  int v24; // r14d
  unsigned int v25; // edi
  const unsigned __int16 *v26; // r12
  __int64 i; // rbp
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rdx
  int v32; // ebx
  int v33; // [rsp+20h] [rbp-68h]
  unsigned int v34; // [rsp+24h] [rbp-64h]
  int v36; // [rsp+38h] [rbp-50h] BYREF

  *a3 = 0;
  v3 = 0;
  ulVal = a2->ulVal;
  v33 = 0;
  v34 = ulVal;
  TreeValueCanonical = 0;
  v8 = 0;
  while ( v8 < ulVal )
  {
    v9 = *(unsigned __int16 **)&a2->bstrblobVal.pData[8 * v8];
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 60LL) & 0x20) != 0 )
      {
        if ( (unsigned int)IsTreeValueCanonical(v9) )
        {
          TreeValueCanonical = 0;
        }
        else
        {
          TreeValueCanonical = MakeTreeValueCanonical(v9);
          if ( TreeValueCanonical >= 0 )
          {
            v31 = -1;
            do
              ++v31;
            while ( v9[v31] );
            v32 = StringCchCopyW(v9, v31 + 1, 0);
            CoTaskMemFree(0);
            TreeValueCanonical = 0;
            if ( v32 != -2147024774 )
              TreeValueCanonical = v32;
            v3 = v33;
          }
        }
      }
      else
      {
        TreeValueCanonical = 0;
        *_FindValueEnd(v9) = 0;
        ValueStart = _FindValueStart(v9);
        if ( ValueStart != v9 )
        {
          v22 = -1;
          do
            ++v22;
          while ( ValueStart[v22] );
          memmove_0(v9, ValueStart, 2 * v22 + 2);
        }
      }
      v12 = -1;
      do
        ++v12;
      while ( v9[v12] );
      if ( TreeValueCanonical >= 0 && (*(_DWORD *)(*((_QWORD *)this + 5) + 60LL) & 0x800) == 0 )
      {
        v13 = *(_WORD **)&a2->bstrblobVal.pData[8 * v8];
        if ( !*v13 )
        {
          CoTaskMemFree(v13);
          *(_QWORD *)&a2->bstrblobVal.pData[8 * v8] = 0;
LABEL_14:
          v3 = 1;
          v33 = 1;
          goto LABEL_15;
        }
      }
      if ( (_DWORD)v10 != (_DWORD)v12 )
        goto LABEL_14;
    }
LABEL_15:
    ulVal = v34;
    ++v8;
    if ( TreeValueCanonical < 0 )
    {
      v36 = 0;
      goto LABEL_17;
    }
  }
  v36 = 0;
  v23 = a2->ulVal;
  if ( v23 >= 0xA )
  {
    TreeValueCanonical = CPropertyDescription::_FindDuplicateStringValuesUsingAlloc(
                           this,
                           a2,
                           (int (*)(unsigned __int16 **, int *))_MarkDuplicateStringCB,
                           &v36);
  }
  else
  {
    v24 = 1;
    v25 = 0;
    do
    {
      if ( v25 >= v23 )
        break;
      v26 = *(const unsigned __int16 **)&a2->bstrblobVal.pData[8 * v25];
      if ( v26 )
      {
        for ( i = v25 + 1; v24 && (unsigned int)i < v23; i = (unsigned int)(i + 1) )
        {
          v28 = *(const unsigned __int16 **)&a2->bstrblobVal.pData[8 * i];
          if ( v28 )
          {
            v29 = CPropertyDescription::_IsStringDuplicate(this, v26, v28);
            if ( v29 )
            {
              v30 = v25;
              if ( v29 != v26 )
                v30 = (unsigned int)i;
              v24 = _MarkDuplicateStringCB((unsigned __int16 **)&a2->bstrblobVal.pData[8 * v30], &v36);
              if ( (_DWORD)v30 == v25 )
                break;
            }
          }
        }
      }
      ++v25;
    }
    while ( v24 );
    v3 = v33;
    TreeValueCanonical = 0;
  }
LABEL_17:
  v14 = a2->ulVal;
  v15 = 0;
  v16 = 0;
  if ( !v14 )
    goto LABEL_18;
  do
  {
    pData = a2->bstrblobVal.pData;
    v19 = *(_QWORD *)&pData[8 * v16];
    if ( v19 )
    {
      v20 = v15++;
      *(_QWORD *)&pData[8 * v20] = v19;
    }
    ++v16;
  }
  while ( v16 < v14 );
  if ( v15 )
  {
    a2->lVal = v15;
    v17 = v15 != v14;
  }
  else
  {
LABEL_18:
    PropVariantClear((PROPVARIANT *)a2);
    v17 = 1;
  }
  if ( v3 || v36 || v17 )
    *a3 = 1;
  return (unsigned int)TreeValueCanonical;
}

```

## disassembly

```asm
0x18000c234  mov     [rsp+arg_18], rbx
0x18000c239  push    rbp
0x18000c23a  push    rsi
0x18000c23b  push    rdi
0x18000c23c  push    r12
0x18000c23e  push    r13
0x18000c240  push    r14
0x18000c242  push    r15
0x18000c244  sub     rsp, 50h
0x18000c248  mov     rax, cs:__security_cookie
0x18000c24f  xor     rax, rsp
0x18000c252  mov     [rsp+88h+var_48], rax
0x18000c257  xor     r11d, r11d
0x18000c25a  mov     [rsp+88h+var_58], r8
0x18000c25f  mov     [r8], r11d
0x18000c262  mov     ebx, r11d
0x18000c265  mov     eax, [rdx+8]
0x18000c268  mov     rsi, rdx
0x18000c26b  mov     [rsp+88h+var_68], ebx
0x18000c26f  mov     r13, rcx
0x18000c272  mov     [rsp+88h+var_64], eax
0x18000c276  mov     edi, r11d
0x18000c279  mov     r14d, r11d
0x18000c27c  cmp     r14d, eax
0x18000c27f  jnb     loc_18000C404
0x18000c285  mov     rax, [rsi+10h]
0x18000c289  mov     r12d, r14d
0x18000c28c  mov     rbp, [rax+r12*8]
0x18000c290  test    rbp, rbp
0x18000c293  jz      loc_18000C31F
0x18000c299  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c29d  inc     r15
0x18000c2a0  cmp     [rbp+r15*2+0], r11w
0x18000c2a6  jnz     short loc_18000C29D
0x18000c2a8  mov     rax, [r13+28h]
0x18000c2ac  mov     rcx, rbp; unsigned __int16 *
0x18000c2af  test    byte ptr [rax+3Ch], 20h
0x18000c2b3  jnz     loc_18000C3EC
0x18000c2b9  call    ?_FindValueEnd@@YAPEAGPEAG@Z; _FindValueEnd(ushort *)
0x18000c2be  xor     edi, edi
0x18000c2c0  mov     rcx, rbp; unsigned __int16 *
0x18000c2c3  mov     [rax], di
0x18000c2c6  call    ?_FindValueStart@@YAPEAGPEAG@Z; _FindValueStart(ushort *)
0x18000c2cb  cmp     rax, rbp
0x18000c2ce  jnz     loc_18000C3C6
0x18000c2d4  xor     r11d, r11d
0x18000c2d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c2db  inc     rax
0x18000c2de  cmp     [rbp+rax*2+0], r11w
0x18000c2e4  jnz     short loc_18000C2DB
0x18000c2e6  cmp     r15d, eax
0x18000c2e9  mov     edx, r11d
0x18000c2ec  setnz   dl
0x18000c2ef  test    edi, edi
0x18000c2f1  js      short loc_18000C312
0x18000c2f3  mov     rax, [r13+28h]
0x18000c2f7  test    dword ptr [rax+3Ch], 800h
0x18000c2fe  jnz     short loc_18000C312
0x18000c300  mov     rax, [rsi+10h]
0x18000c304  mov     rcx, [rax+r12*8]; pv
0x18000c308  cmp     [rcx], r11w
0x18000c30c  jz      loc_18000C52D
0x18000c312  test    edx, edx
0x18000c314  jz      short loc_18000C31F
0x18000c316  mov     ebx, 1
0x18000c31b  mov     [rsp+88h+var_68], ebx
0x18000c31f  mov     eax, [rsp+88h+var_64]
0x18000c323  inc     r14d
0x18000c326  test    edi, edi
0x18000c328  jns     loc_18000C27C
0x18000c32e  mov     [rsp+88h+var_50], r11d
0x18000c333  mov     r8d, [rsi+8]
0x18000c337  mov     ecx, r11d
0x18000c33a  mov     edx, r11d
0x18000c33d  test    r8d, r8d
0x18000c340  jnz     short loc_18000C355
0x18000c342  mov     rcx, rsi; pvar
0x18000c345  call    cs:__imp_PropVariantClear
0x18000c34b  mov     eax, 1
0x18000c350  xor     r11d, r11d
0x18000c353  jmp     short loc_18000C383
0x18000c355  mov     r9, [rsi+10h]
0x18000c359  mov     eax, edx
0x18000c35b  mov     r10, [r9+rax*8]
0x18000c35f  test    r10, r10
0x18000c362  jz      short loc_18000C36C
0x18000c364  mov     eax, ecx
0x18000c366  inc     ecx
0x18000c368  mov     [r9+rax*8], r10
0x18000c36c  inc     edx
0x18000c36e  cmp     edx, r8d
0x18000c371  jb      short loc_18000C355
0x18000c373  test    ecx, ecx
0x18000c375  jz      short loc_18000C342
0x18000c377  cmp     ecx, r8d
0x18000c37a  mov     [rsi+8], ecx
0x18000c37d  mov     eax, r11d
0x18000c380  setnz   al
0x18000c383  test    ebx, ebx
0x18000c385  jnz     short loc_18000C3B9
0x18000c387  cmp     [rsp+88h+var_50], r11d
0x18000c38c  jnz     short loc_18000C3B9
0x18000c38e  test    eax, eax
0x18000c390  jnz     short loc_18000C3B9
0x18000c392  mov     eax, edi
0x18000c394  mov     rcx, [rsp+88h+var_48]
0x18000c399  xor     rcx, rsp; StackCookie
0x18000c39c  call    __security_check_cookie
0x18000c3a1  mov     rbx, [rsp+88h+arg_18]
0x18000c3a9  add     rsp, 50h
0x18000c3ad  pop     r15
0x18000c3af  pop     r14
0x18000c3b1  pop     r13
0x18000c3b3  pop     r12
0x18000c3b5  pop     rdi
0x18000c3b6  pop     rsi
0x18000c3b7  pop     rbp
0x18000c3b8  retn
0x18000c3b9  mov     rax, [rsp+88h+var_58]
0x18000c3be  mov     dword ptr [rax], 1
0x18000c3c4  jmp     short loc_18000C392
0x18000c3c6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c3ca  inc     r8
0x18000c3cd  cmp     [rax+r8*2], di
0x18000c3d2  jnz     short loc_18000C3CA
0x18000c3d4  lea     r8, ds:2[r8*2]; Size
0x18000c3dc  mov     rdx, rax; Src
0x18000c3df  mov     rcx, rbp; void *
0x18000c3e2  call    memmove_0
0x18000c3e7  jmp     loc_18000C2D4
0x18000c3ec  call    ?IsTreeValueCanonical@@YAHPEBG@Z; IsTreeValueCanonical(ushort const *)
0x18000c3f1  xor     r11d, r11d
0x18000c3f4  test    eax, eax
0x18000c3f6  jz      loc_18000C4C7
0x18000c3fc  mov     edi, r11d
0x18000c3ff  jmp     loc_18000C2D7
0x18000c404  mov     [rsp+88h+var_50], r11d
0x18000c409  test    edi, edi
0x18000c40b  js      loc_18000C333
0x18000c411  mov     r15d, [rsi+8]
0x18000c415  cmp     r15d, 0Ah
0x18000c419  jnb     loc_18000C4A6
0x18000c41f  mov     r14d, 1
0x18000c425  mov     edi, r11d
0x18000c428  cmp     edi, r15d
0x18000c42b  jnb     short loc_18000C44B
0x18000c42d  mov     rax, [rsi+10h]
0x18000c431  mov     ecx, edi
0x18000c433  mov     r12, [rax+rcx*8]
0x18000c437  test    r12, r12
0x18000c43a  jz      short loc_18000C444
0x18000c43c  lea     ebp, [rdi+1]
0x18000c43f  test    r14d, r14d
0x18000c442  jnz     short loc_18000C457
0x18000c444  inc     edi
0x18000c446  test    r14d, r14d
0x18000c449  jnz     short loc_18000C428
0x18000c44b  mov     ebx, [rsp+88h+var_68]
0x18000c44f  mov     edi, r11d
0x18000c452  jmp     loc_18000C333
0x18000c457  cmp     ebp, r15d
0x18000c45a  jnb     short loc_18000C444
0x18000c45c  mov     rax, [rsi+10h]
0x18000c460  mov     r8, [rax+rbp*8]; unsigned __int16 *
0x18000c464  test    r8, r8
0x18000c467  jnz     short loc_18000C46D
0x18000c469  inc     ebp
0x18000c46b  jmp     short loc_18000C43F
0x18000c46d  mov     rdx, r12; unsigned __int16 *
0x18000c470  mov     rcx, r13; this
0x18000c473  call    ?_IsStringDuplicate@CPropertyDescription@@AEAAPEBGPEBG0@Z; CPropertyDescription::_IsStringDuplicate(ushort const *,ushort const *)
0x18000c478  xor     r11d, r11d
0x18000c47b  test    rax, rax
0x18000c47e  jz      short loc_18000C469
0x18000c480  cmp     rax, r12
0x18000c483  lea     rdx, [rsp+88h+var_50]; int *
0x18000c488  mov     rax, [rsi+10h]
0x18000c48c  mov     ebx, edi
0x18000c48e  cmovnz  ebx, ebp
0x18000c491  lea     rcx, [rax+rbx*8]; unsigned __int16 **
0x18000c495  call    ?_MarkDuplicateStringCB@@YAHPEAPEAGPEAH@Z; _MarkDuplicateStringCB(ushort * *,int *)
0x18000c49a  xor     r11d, r11d
0x18000c49d  mov     r14d, eax
0x18000c4a0  cmp     ebx, edi
0x18000c4a2  jz      short loc_18000C444
0x18000c4a4  jmp     short loc_18000C469
0x18000c4a6  lea     r9, [rsp+88h+var_50]; int *
0x18000c4ab  mov     rdx, rsi; struct tagPROPVARIANT *
0x18000c4ae  lea     r8, ?_MarkDuplicateStringCB@@YAHPEAPEAGPEAH@Z; int (*)(unsigned __int16 **, int *)
0x18000c4b5  mov     rcx, r13; this
0x18000c4b8  call    ?_FindDuplicateStringValuesUsingAlloc@CPropertyDescription@@AEAAJPEAUtagPROPVARIANT@@P6AHPEAPEAGPEAH@Z2@Z; CPropertyDescription::_FindDuplicateStringValuesUsingAlloc(tagPROPVARIANT *,int (*)(ushort * *,int *),int *)
0x18000c4bd  mov     edi, eax
0x18000c4bf  xor     r11d, r11d
0x18000c4c2  jmp     loc_18000C333
0x18000c4c7  xor     r8d, r8d
0x18000c4ca  mov     [rsp+88h+pv], r11
0x18000c4cf  lea     rdx, [rsp+88h+pv]
0x18000c4d4  mov     rcx, rbp; unsigned __int16 *
0x18000c4d7  call    MakeTreeValueCanonical
0x18000c4dc  xor     r11d, r11d
0x18000c4df  mov     edi, eax
0x18000c4e1  test    eax, eax
0x18000c4e3  js      loc_18000C2D7
0x18000c4e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c4ed  inc     rdx
0x18000c4f0  cmp     [rbp+rdx*2+0], r11w
0x18000c4f6  jnz     short loc_18000C4ED
0x18000c4f8  mov     r8, [rsp+88h+pv]; unsigned __int16 *
0x18000c4fd  inc     rdx; unsigned __int64
0x18000c500  mov     rcx, rbp; unsigned __int16 *
0x18000c503  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c508  mov     rcx, [rsp+88h+pv]; pv
0x18000c50d  mov     ebx, eax
0x18000c50f  call    cs:__imp_CoTaskMemFree
0x18000c515  xor     r11d, r11d
0x18000c518  cmp     ebx, 8007007Ah
0x18000c51e  mov     edi, r11d
0x18000c521  cmovnz  edi, ebx
0x18000c524  mov     ebx, [rsp+88h+var_68]
0x18000c528  jmp     loc_18000C2D7
0x18000c52d  call    cs:__imp_CoTaskMemFree
0x18000c533  mov     rax, [rsi+10h]
0x18000c537  xor     r11d, r11d
0x18000c53a  mov     [rax+r12*8], r11
0x18000c53e  jmp     loc_18000C316
```
