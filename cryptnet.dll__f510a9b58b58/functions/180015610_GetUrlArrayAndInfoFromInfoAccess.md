# GetUrlArrayAndInfoFromInfoAccess

- ea: `0x180015610`
- end: `0x180015bb2`
- name: `GetUrlArrayAndInfoFromInfoAccess`
- size: `1442`
- prototype: `__int64(unsigned int, __int64, const char *, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013bc0`
- `0x180015bb8`

## callees

- `0x180013ab0`
- `0x180015610`
- `0x18001acb4`
- `0x180026552`
- `0x180026576`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001575c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001585b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001575c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001585b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015848`
- `CRYPT32!CryptMemAlloc` at `0x18001591e`
- `CRYPT32!CryptMemAlloc` at `0x180015a1d`
- `CRYPT32!CryptMemAlloc` at `0x18001591e`
- `CRYPT32!CryptMemAlloc` at `0x180015a1d`
- `CRYPT32!CryptMemFree` at `0x180015831`
- `CRYPT32!CryptMemFree` at `0x180015b70`
- `CRYPT32!CryptMemFree` at `0x180015831`
- `CRYPT32!CryptMemFree` at `0x180015b70`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800158e2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015b0d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800158e2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015b0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015656`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015656`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015853`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015853`

## pseudocode

```c
__int64 GetUrlArrayAndInfoFromInfoAccess(unsigned int a1, __int64 a2, const char *a3, ...)
{
  unsigned int v3; // r12d
  __int64 v4; // r13
  unsigned int v5; // r14d
  _QWORD *v6; // rax
  unsigned int v7; // esi
  int v8; // ebp
  unsigned int v9; // edi
  __int64 v10; // r14
  unsigned int v11; // r15d
  __int64 v12; // r12
  _QWORD *v13; // rdi
  __int64 v14; // rbx
  const WCHAR *lpString2; // rbx
  va_list v16; // r9
  _QWORD *v17; // rbx
  __int64 v18; // rbp
  int v19; // r8d
  __int64 i; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  ULONG v23; // r15d
  __int64 j; // rbx
  DWORD LastError; // ebx
  unsigned __int64 v27; // r9
  const WCHAR *v28; // rcx
  unsigned __int64 cchCount2; // rdx
  const WCHAR *v30; // rcx
  __int64 v31; // rax
  unsigned int v33; // esi
  void *v34; // rax
  void *v35; // rbp
  _QWORD *v36; // r12
  ULONG *v37; // r13
  _QWORD *v38; // r14
  unsigned int v39; // ecx
  int v40; // esi
  __int64 v41; // rdi
  char *v42; // rbp
  unsigned int v43; // r13d
  _WORD *v44; // rdx
  __int64 v45; // rbx
  unsigned int v46; // ebx
  unsigned int v47; // ecx
  unsigned __int64 v48; // r9
  const WCHAR *v49; // rcx
  unsigned __int64 v50; // rcx
  const WCHAR *v51; // rdx
  int v52; // [rsp+30h] [rbp-78h]
  _QWORD *hMem; // [rsp+38h] [rbp-70h]
  unsigned int v54; // [rsp+48h] [rbp-60h] BYREF
  _QWORD *v55; // [rsp+50h] [rbp-58h]
  int v56; // [rsp+58h] [rbp-50h]
  int v57; // [rsp+5Ch] [rbp-4Ch]
  __int64 v61; // [rsp+C8h] [rbp+20h] BYREF
  va_list va; // [rsp+C8h] [rbp+20h]
  ULONG *v63; // [rsp+D0h] [rbp+28h]
  __int64 v64; // [rsp+D8h] [rbp+30h]
  __int64 v65; // [rsp+E0h] [rbp+38h]
  va_list va1; // [rsp+E8h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v61 = va_arg(va1, _QWORD);
  v63 = va_arg(va1, ULONG *);
  v64 = va_arg(va1, _QWORD);
  v65 = va_arg(va1, _QWORD);
  v3 = a1;
  v4 = a2;
  v5 = 0;
  v57 = 5;
  v54 = 0;
  v6 = LocalAlloc(0x40u, 8u);
  hMem = v6;
  if ( !v6 )
  {
    SetLastError(0x8007000E);
    SetLastError(8u);
    hMem = 0;
    SetLastError(0x8007000E);
    v7 = 0;
    goto LABEL_29;
  }
  v7 = 1;
  v55 = v6;
  v8 = 0;
  v9 = 0;
  *v6 = 0;
  v52 = 0;
  v56 = 1;
  while ( v9 < v3 )
  {
    v10 = *(_QWORD *)(v4 + 16LL * v9 + 8);
    if ( v10 )
    {
      v11 = 0;
      if ( *(_DWORD *)v10 )
      {
        v12 = *(_QWORD *)(v10 + 8);
        v13 = hMem;
        while ( 1 )
        {
          if ( v7 != 1 )
          {
LABEL_14:
            v3 = a1;
            v4 = a2;
            hMem = v13;
            v9 = v52;
            break;
          }
          v14 = 32LL * v11;
          if ( !strcmp(a3, *(const char **)(v14 + v12)) && *(_DWORD *)(v14 + v12 + 8) == 7 )
          {
            lpString2 = *(const WCHAR **)(v14 + v12 + 16);
            if ( lpString2 )
            {
              for ( ; *lpString2 == 32; ++lpString2 )
                ;
              if ( strcmp_0("1.3.6.1.5.5.7.48.1", a3) )
                goto LABEL_44;
              v27 = 0;
              v28 = L"http";
              do
              {
                if ( !*v28 )
                  break;
                ++v27;
                ++v28;
              }
              while ( v27 < 4 );
              cchCount2 = 0;
              v30 = lpString2;
              do
              {
                if ( !*v30 )
                  break;
                ++cchCount2;
                ++v30;
              }
              while ( cchCount2 < 4 );
              if ( CompareStringW(0x409u, 1u, L"http", v27, lpString2, cchCount2) == 2 )
                goto LABEL_44;
              v48 = 0;
              v49 = L"post";
              do
              {
                if ( !*v49 )
                  break;
                ++v48;
                ++v49;
              }
              while ( v48 < 4 );
              v50 = 0;
              v51 = lpString2;
              do
              {
                if ( !*v51 )
                  break;
                ++v50;
                ++v51;
              }
              while ( v50 < 4 );
              if ( CompareStringW(0x409u, 1u, L"post", v48, lpString2, v50) == 2 )
              {
LABEL_44:
                v31 = -1;
                while ( lpString2[++v31] != 0 )
                  ;
                v33 = v31 + 1;
                if ( (unsigned int)(v31 + 1) > 0xFFFF )
                {
                  SetLastError(0x216u);
LABEL_48:
                  SetLastError(0x8007000E);
                  v7 = 0;
LABEL_49:
                  v8 = 1;
                  goto LABEL_13;
                }
                v34 = CryptMemAlloc(2 * v33);
                v35 = v34;
                if ( !v34 )
                  goto LABEL_48;
                memcpy_0(v34, lpString2, 2LL * v33);
                v47 = v54;
                v7 = 1;
                if ( v56 == v54 )
                {
                  v7 = CCryptUrlArray::GrowArray((CCryptUrlArray *)&v54);
                  if ( v7 != 1 )
                  {
                    CryptMemFree(v35);
                    v13 = v55;
                    goto LABEL_49;
                  }
                  v13 = v55;
                  v47 = v54;
                }
                v54 = v47 + 1;
                v13[v47] = v35;
                v8 = 1;
              }
            }
          }
LABEL_13:
          if ( ++v11 >= *(_DWORD *)v10 )
            goto LABEL_14;
        }
      }
    }
    v52 = ++v9;
    if ( v7 != 1 )
    {
      v5 = v54;
      goto LABEL_29;
    }
  }
  if ( !v8 )
  {
    SetLastError(0x80092004);
    v5 = v54;
    v7 = 0;
    goto LABEL_29;
  }
  v5 = v54;
  va_copy(v16, va);
  v17 = hMem;
  if ( !v61 )
    v16 = 0;
  v18 = v54;
  v19 = 0;
  for ( i = 0; (unsigned int)i < v54; v19 += 2 * v22 + 2 )
  {
    v21 = hMem[i];
    if ( v21 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
    }
    else
    {
      LODWORD(v22) = 0;
    }
    i = (unsigned int)(i + 1);
  }
  v23 = v19 + v18 * 8 + 16;
  if ( v16 )
  {
    v36 = *(_QWORD **)v16;
    v37 = v63;
    if ( *(_QWORD *)v16 )
    {
      if ( !v63 || *v63 < v23 )
        goto LABEL_83;
      v38 = *(_QWORD **)v16;
    }
    else
    {
      v38 = CryptMemAlloc(v23);
      if ( !v38 )
      {
        SetLastError(0x8007000E);
        v5 = v54;
        v7 = 0;
        goto LABEL_29;
      }
    }
    v39 = v54;
    v40 = 0;
    *(_DWORD *)v38 = v54;
    v41 = 0;
    v38[1] = v38 + 2;
    if ( v39 )
    {
      v42 = (char *)&v38[v18 + 2];
      v43 = v39;
      do
      {
        *(_QWORD *)(8 * v41 + v38[1]) = &v42[v40];
        v44 = (_WORD *)v17[v41];
        if ( v44 )
        {
          v45 = -1;
          do
            ++v45;
          while ( v44[v45] );
        }
        else
        {
          LODWORD(v45) = 0;
        }
        v46 = 2 * v45 + 2;
        memcpy_0(*(void **)(8 * v41 + v38[1]), v44, v46);
        v40 += v46;
        v41 = (unsigned int)(v41 + 1);
        v17 = hMem;
      }
      while ( (unsigned int)v41 < v43 );
      v37 = v63;
    }
    if ( v36 != v38 && v37 )
      *v37 = v23;
    v5 = v54;
    goto LABEL_27;
  }
  if ( !v63 )
  {
LABEL_83:
    SetLastError(0x80070057);
    v7 = 0;
    goto LABEL_29;
  }
  *v63 = v23;
LABEL_27:
  v7 = 1;
  if ( v65 )
    InitializeDefaultUrlInfo(v64);
LABEL_29:
  for ( j = 0; (unsigned int)j < v5; j = (unsigned int)(j + 1) )
    CryptMemFree((LPVOID)hMem[j]);
  if ( hMem )
  {
    LastError = GetLastError();
    LocalFree(hMem);
    SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x180015610  mov     rax, rsp
0x180015613  mov     [rax+20h], r9
0x180015617  mov     [rax+18h], r8
0x18001561b  mov     [rax+10h], rdx
0x18001561f  mov     [rax+8], ecx
0x180015622  push    rbx
0x180015623  push    rsi
0x180015624  push    rdi
0x180015625  sub     rsp, 90h
0x18001562c  mov     [rax-28h], r12
0x180015630  mov     r12d, ecx
0x180015633  mov     [rax-30h], r13
0x180015637  mov     ecx, 40h ; '@'; uFlags
0x18001563c  mov     [rax-38h], r14
0x180015640  mov     r13, rdx
0x180015643  xor     r14d, r14d
0x180015646  mov     dword ptr [rax-4Ch], 5
0x18001564d  mov     edx, 8; uBytes
0x180015652  mov     [rax-60h], r14d
0x180015656  call    cs:__imp_LocalAlloc
0x18001565c  mov     [rsp+0A8h+hMem], rax
0x180015661  mov     rbx, rax
0x180015664  test    rax, rax
0x180015667  jz      loc_180015B21
0x18001566d  mov     [rsp+0A8h+var_20], rbp
0x180015675  mov     esi, 1
0x18001567a  mov     [rsp+0A8h+var_58], rax
0x18001567f  xor     ebp, ebp
0x180015681  xor     eax, eax
0x180015683  mov     [rsp+0A8h+var_40], r15
0x180015688  xor     edi, edi
0x18001568a  mov     [rbx], rax
0x18001568d  mov     [rsp+0A8h+var_78], edi
0x180015691  mov     r9d, 20h ; ' '
0x180015697  mov     [rsp+0A8h+var_50], esi
0x18001569b  nop     dword ptr [rax+rax+00h]
0x1800156a0  cmp     edi, r12d
0x1800156a3  jnb     loc_180015753
0x1800156a9  mov     eax, edi
0x1800156ab  add     rax, rax
0x1800156ae  mov     r14, [r13+rax*8+8]
0x1800156b3  test    r14, r14
0x1800156b6  jnz     short loc_1800156CD
0x1800156b8  inc     edi
0x1800156ba  mov     [rsp+0A8h+var_78], edi
0x1800156be  cmp     esi, 1
0x1800156c1  jz      short loc_1800156A0
0x1800156c3  mov     r14d, [rsp+0A8h+var_60]
0x1800156c8  jmp     loc_180015807
0x1800156cd  mov     rax, [r14+8]
0x1800156d1  xor     r15d, r15d
0x1800156d4  cmp     [r14], r15d
0x1800156d7  jbe     short loc_1800156B8
0x1800156d9  mov     r13, [rsp+0A8h+Str2]
0x1800156e1  mov     r12, rax
0x1800156e4  mov     rdi, [rsp+0A8h+hMem]
0x1800156e9  cmp     esi, 1
0x1800156ec  jnz     short loc_180015735
0x1800156ee  mov     ebx, r15d
0x1800156f1  mov     rax, r13
0x1800156f4  shl     rbx, 5
0x1800156f8  mov     r8, [rbx+r12]
0x1800156fc  sub     r8, r13
0x1800156ff  nop
0x180015700  movzx   edx, byte ptr [rax]
0x180015703  movzx   ecx, byte ptr [rax+r8]
0x180015708  sub     edx, ecx
0x18001570a  jnz     short loc_180015713
0x18001570c  inc     rax
0x18001570f  test    ecx, ecx
0x180015711  jnz     short loc_180015700
0x180015713  test    edx, edx
0x180015715  jnz     short loc_18001572D
0x180015717  cmp     dword ptr [rbx+r12+8], 7
0x18001571d  jnz     short loc_18001572D
0x18001571f  mov     rbx, [rbx+r12+10h]
0x180015724  test    rbx, rbx
0x180015727  jnz     loc_18001586E
0x18001572d  inc     r15d
0x180015730  cmp     r15d, [r14]
0x180015733  jb      short loc_1800156E9
0x180015735  mov     r12d, [rsp+0A8h+arg_0]
0x18001573d  mov     r13, [rsp+0A8h+arg_8]
0x180015745  mov     [rsp+0A8h+hMem], rdi
0x18001574a  mov     edi, [rsp+0A8h+var_78]
0x18001574e  jmp     loc_1800156B8
0x180015753  test    ebp, ebp
0x180015755  jnz     short loc_18001576E
0x180015757  mov     ecx, 80092004h; dwErrCode
0x18001575c  call    cs:__imp_SetLastError
0x180015762  mov     r14d, [rsp+0A8h+var_60]
0x180015767  xor     esi, esi
0x180015769  jmp     loc_180015807
0x18001576e  mov     r14d, [rsp+0A8h+var_60]
0x180015773  lea     r9, [rsp+0A8h+arg_18]
0x18001577b  mov     rbx, [rsp+0A8h+hMem]
0x180015780  xor     eax, eax
0x180015782  cmp     [rsp+0A8h+arg_18], rax
0x18001578a  cmovz   r9, rax
0x18001578e  lea     ebp, ds:0[r14*8]
0x180015796  xor     r8d, r8d
0x180015799  xor     edx, edx
0x18001579b  test    r14d, r14d
0x18001579e  jz      short loc_1800157CD
0x1800157a0  mov     rcx, [rbx+rdx*8]
0x1800157a4  test    rcx, rcx
0x1800157a7  jz      loc_180015B80
0x1800157ad  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800157b4  inc     rax
0x1800157b7  cmp     word ptr [rcx+rax*2], 0
0x1800157bc  jnz     short loc_1800157B4
0x1800157be  lea     r8d, [r8+rax*2]
0x1800157c2  inc     edx
0x1800157c4  add     r8d, 2
0x1800157c8  cmp     edx, r14d
0x1800157cb  jb      short loc_1800157A0
0x1800157cd  lea     r15d, [rbp+10h]
0x1800157d1  add     r15d, r8d
0x1800157d4  test    r9, r9
0x1800157d7  jnz     loc_18001594D
0x1800157dd  mov     rax, [rsp+0A8h+arg_20]
0x1800157e5  test    rax, rax
0x1800157e8  jz      loc_180015A46
0x1800157ee  mov     [rax], r15d
0x1800157f1  mov     rdx, [rsp+0A8h+arg_30]
0x1800157f9  mov     esi, 1
0x1800157fe  test    rdx, rdx
0x180015801  jnz     loc_180015AB4
0x180015807  mov     rbp, [rsp+0A8h+var_20]
0x18001580f  mov     r15, [rsp+0A8h+var_40]
0x180015814  mov     r13, [rsp+0A8h+var_30]
0x180015819  xor     ebx, ebx
0x18001581b  mov     r12, [rsp+0A8h+var_28]
0x180015823  mov     rdi, [rsp+0A8h+hMem]
0x180015828  test    r14d, r14d
0x18001582b  jz      short loc_18001583E
0x18001582d  mov     rcx, [rdi+rbx*8]; pv
0x180015831  call    cs:__imp_CryptMemFree
0x180015837  inc     ebx
0x180015839  cmp     ebx, r14d
0x18001583c  jb      short loc_18001582D
0x18001583e  mov     r14, [rsp+0A8h+var_38]
0x180015843  test    rdi, rdi
0x180015846  jz      short loc_180015861
0x180015848  call    cs:__imp_GetLastError
0x18001584e  mov     rcx, rdi; hMem
0x180015851  mov     ebx, eax
0x180015853  call    cs:__imp_LocalFree
0x180015859  mov     ecx, ebx; dwErrCode
0x18001585b  call    cs:__imp_SetLastError
0x180015861  mov     eax, esi
0x180015863  add     rsp, 90h
0x18001586a  pop     rdi
0x18001586b  pop     rsi
0x18001586c  pop     rbx
0x18001586d  retn
0x18001586e  cmp     r9w, [rbx]
0x180015872  jnz     short loc_18001587E
0x180015874  add     rbx, 2
0x180015878  cmp     r9w, [rbx]
0x18001587c  jz      short loc_180015874
0x18001587e  mov     rdx, r13; Str2
0x180015881  lea     rcx, Str1; "1.3.6.1.5.5.7.48.1"
0x180015888  call    strcmp_0
0x18001588d  test    eax, eax
0x18001588f  jnz     short loc_1800158F1
0x180015891  xor     r9d, r9d
0x180015894  lea     rcx, aHttp_0; "http"
0x18001589b  xor     eax, eax
0x18001589d  cmp     ax, [rcx]
0x1800158a0  jz      short loc_1800158AF
0x1800158a2  inc     r9; cchCount1
0x1800158a5  add     rcx, 2
0x1800158a9  cmp     r9, 4
0x1800158ad  jb      short loc_18001589B
0x1800158af  xor     edx, edx
0x1800158b1  mov     rcx, rbx
0x1800158b4  xor     eax, eax
0x1800158b6  cmp     ax, [rcx]
0x1800158b9  jz      short loc_1800158C8
0x1800158bb  inc     rdx
0x1800158be  add     rcx, 2
0x1800158c2  cmp     rdx, 4
0x1800158c6  jb      short loc_1800158B4
0x1800158c8  mov     [rsp+0A8h+cchCount2], edx; cchCount2
0x1800158cc  lea     r8, aHttp_0; "http"
0x1800158d3  mov     edx, 1; dwCmpFlags
0x1800158d8  mov     [rsp+0A8h+lpString2], rbx; lpString2
0x1800158dd  mov     ecx, 409h; Locale
0x1800158e2  call    cs:__imp_CompareStringW
0x1800158e8  cmp     eax, 2
0x1800158eb  jnz     loc_180015B4E
0x1800158f1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800158f8  nop     dword ptr [rax+rax+00000000h]
0x180015900  cmp     word ptr [rbx+rax*2+2], 0
0x180015906  lea     rax, [rax+1]
0x18001590a  jnz     short loc_180015900
0x18001590c  lea     esi, [rax+1]
0x18001590f  cmp     esi, 0FFFFh
0x180015915  ja      loc_180015B5D
0x18001591b  lea     ecx, [rsi+rsi]; cbSize
0x18001591e  call    cs:__imp_CryptMemAlloc
0x180015924  mov     rbp, rax
0x180015927  test    rax, rax
0x18001592a  jnz     loc_180015A58
0x180015930  mov     ecx, 8007000Eh; dwErrCode
0x180015935  call    cs:__imp_SetLastError
0x18001593b  xor     esi, esi
0x18001593d  mov     ebp, 1
0x180015942  mov     r9d, 20h ; ' '
0x180015948  jmp     loc_18001572D
0x18001594d  mov     r12, [r9]
0x180015950  mov     r13, [rsp+0A8h+arg_20]
0x180015958  test    r12, r12
0x18001595b  jz      loc_180015A1A
0x180015961  test    r13, r13
0x180015964  jz      loc_180015B87
0x18001596a  cmp     [r13+0], r15d
0x18001596e  jb      loc_180015A46
0x180015974  mov     r14, r12
0x180015977  mov     ecx, [rsp+0A8h+var_60]
0x18001597b  lea     rax, [r14+10h]
0x18001597f  xor     esi, esi
0x180015981  mov     [r14], ecx
0x180015984  xor     edi, edi
0x180015986  mov     [r14+8], rax
0x18001598a  test    ecx, ecx
0x18001598c  jz      short loc_180015A07
0x18001598e  add     rbp, rax
0x180015991  mov     r13d, ecx
0x180015994  nop     dword ptr [rax+00h]
0x180015998  nop     dword ptr [rax+rax+00000000h]
0x1800159a0  mov     rax, [r14+8]
0x1800159a4  lea     r9, ds:0[rdi*8]
0x1800159ac  mov     ecx, esi
0x1800159ae  add     rcx, rbp
0x1800159b1  mov     [r9+rax], rcx
0x1800159b5  mov     rdx, [r9+rbx]; Src
0x1800159b9  test    rdx, rdx
0x1800159bc  jz      loc_180015B99
0x1800159c2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800159c9  nop     dword ptr [rax+00000000h]
0x1800159d0  inc     rbx
0x1800159d3  cmp     word ptr [rdx+rbx*2], 0
0x1800159d8  jnz     short loc_1800159D0
0x1800159da  mov     rcx, [r14+8]
0x1800159de  lea     ebx, ds:2[rbx*2]
0x1800159e5  mov     r8d, ebx; Size
0x1800159e8  mov     rcx, [r9+rcx]; void *
0x1800159ec  call    memcpy_0
0x1800159f1  add     esi, ebx
0x1800159f3  inc     edi
0x1800159f5  mov     rbx, [rsp+0A8h+hMem]
0x1800159fa  cmp     edi, r13d
0x1800159fd  jb      short loc_1800159A0
0x1800159ff  mov     r13, [rsp+0A8h+arg_20]
0x180015a07  cmp     r12, r14
0x180015a0a  jnz     loc_180015BA0
0x180015a10  mov     r14d, [rsp+0A8h+var_60]
0x180015a15  jmp     loc_1800157F1
0x180015a1a  mov     ecx, r15d; cbSize
0x180015a1d  call    cs:__imp_CryptMemAlloc
0x180015a23  mov     r14, rax
0x180015a26  test    rax, rax
0x180015a29  jnz     loc_180015977
0x180015a2f  mov     ecx, 8007000Eh; dwErrCode
0x180015a34  call    cs:__imp_SetLastError
0x180015a3a  mov     r14d, [rsp+0A8h+var_60]
0x180015a3f  xor     esi, esi
0x180015a41  jmp     loc_180015807
0x180015a46  mov     ecx, 80070057h; dwErrCode
0x180015a4b  call    cs:__imp_SetLastError
0x180015a51  xor     esi, esi
0x180015a53  jmp     loc_180015807
0x180015a58  mov     r8d, esi
0x180015a5b  mov     rdx, rbx; Src
0x180015a5e  add     r8, r8; Size
0x180015a61  mov     rcx, rbp; void *
0x180015a64  call    memcpy_0
0x180015a69  mov     ecx, [rsp+0A8h+var_60]
0x180015a6d  mov     esi, 1
0x180015a72  cmp     [rsp+0A8h+var_50], ecx
0x180015a76  jz      short loc_180015A94
0x180015a78  mov     eax, ecx
0x180015a7a  mov     r9d, 20h ; ' '
0x180015a80  inc     ecx
0x180015a82  mov     [rsp+0A8h+var_60], ecx
0x180015a86  mov     [rdi+rax*8], rbp
0x180015a8a  mov     ebp, 1
0x180015a8f  jmp     loc_18001572D
0x180015a94  lea     rcx, [rsp+0A8h+var_60]; this
0x180015a99  call    ?GrowArray@CCryptUrlArray@@AEAAHXZ; CCryptUrlArray::GrowArray(void)
0x180015a9e  mov     esi, eax
0x180015aa0  cmp     eax, 1
0x180015aa3  jnz     loc_180015B6D
0x180015aa9  mov     rdi, [rsp+0A8h+var_58]
0x180015aae  mov     ecx, [rsp+0A8h+var_60]
0x180015ab2  jmp     short loc_180015A78
0x180015ab4  mov     rcx, [rsp+0A8h+arg_28]
0x180015abc  call    InitializeDefaultUrlInfo
  ... truncated ...
```
