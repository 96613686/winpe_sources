# DavGetCompletePathName

- ea: `0x18000c500`
- end: `0x18000c7d7`
- name: `DavGetCompletePathName`
- size: `727`
- prototype: `__int64 __fastcall(_WORD *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c980`

## callees

- `0x1800051a0`
- `0x18000c500`
- `0x180010a14`
- `0x180010be8`
- `0x180010c28`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000c5e3`
- `msvcrt!_wcsnicmp` at `0x18000c5e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c674`
- `KERNEL32!LocalAlloc` at `0x18000c663`
- `KERNEL32!LocalAlloc` at `0x18000c663`

## pseudocode

```c
__int64 __fastcall DavGetCompletePathName(_WORD *a1, wchar_t **a2)
{
  _BYTE *v4; // rcx
  const wchar_t *v5; // rdi
  const wchar_t *v6; // rdx
  wchar_t v7; // ax
  DWORD LastError; // esi
  int v9; // eax
  size_t v10; // rdx
  const wchar_t *v11; // rcx
  const wchar_t *v12; // r14
  __int64 v13; // rdx
  size_t v14; // rdi
  wchar_t *v15; // rax
  wchar_t *v16; // rcx
  DWORD v17; // eax
  wchar_t v19; // ax
  __int64 v20; // rdx
  size_t pcchLength; // [rsp+70h] [rbp+8h] BYREF

  pcchLength = 0;
  if ( !a1 || !a2 )
  {
    LastError = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_51;
    v20 = 286;
    goto LABEL_49;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *a1 != 92 || a1[1] != 92 )
  {
    LastError = 87;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (v4[28] & 1) == 0 )
      goto LABEL_51;
    v20 = 288;
LABEL_49:
    WPP_SF_d(*((_QWORD *)v4 + 2), v20, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, 87);
    goto LABEL_50;
  }
  v5 = a1 + 2;
  v6 = v5;
  v7 = *v5;
  if ( *v5 != 92 )
  {
    do
    {
      if ( !v7 )
        break;
      v7 = *++v5;
    }
    while ( *v5 != 92 );
    if ( v5 < v6 )
      goto LABEL_40;
  }
  if ( (unsigned __int64)(v5 - v6) > 0x104 )
  {
LABEL_40:
    LastError = 87;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (v4[28] & 1) == 0 )
      goto LABEL_51;
    v13 = 289;
    goto LABEL_22;
  }
  LastError = 0;
  if ( *v5 != 92 )
  {
LABEL_51:
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 0x20) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 294, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
    return LastError;
  }
  v9 = _wcsnicmp(v5 + 1, L"DavWWWRoot", 0xAu);
  v11 = v5 + 11;
  if ( v9 )
    v11 = v5;
  v12 = v11 + 1;
  if ( *v11 != 92 )
    v12 = v11;
  if ( StringCchLengthW(v12, v10, &pcchLength) < 0 )
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_51;
    v13 = 290;
LABEL_22:
    WPP_SF_(*((_QWORD *)v4 + 2), v13, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
LABEL_50:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_51;
  }
  v14 = pcchLength;
  if ( !pcchLength )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_51;
    v13 = 293;
    goto LABEL_22;
  }
  v15 = (wchar_t *)LocalAlloc(0x40u, 2 * pcchLength + 2);
  *a2 = v15;
  v16 = v15;
  if ( !v15 )
  {
    v17 = GetLastError();
    LastError = v17;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_51;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 291, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v17);
    goto LABEL_50;
  }
  while ( *v12 )
  {
    if ( !v14-- )
      break;
    if ( *v12 == 92 )
      v19 = 47;
    else
      v19 = *v12;
    *v16++ = v19;
    ++v12;
  }
  *v16 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 292, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, *a2);
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000c500  push    rbx
0x18000c502  push    rbp
0x18000c503  push    rsi
0x18000c504  push    rdi
0x18000c505  push    r12
0x18000c507  push    r13
0x18000c509  push    r14
0x18000c50b  push    r15
0x18000c50d  sub     rsp, 28h
0x18000c511  xor     ebp, ebp
0x18000c513  lea     r12, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c51a  mov     [rsp+68h+pcchLength], rbp
0x18000c51f  mov     r15, rdx
0x18000c522  mov     rdi, rcx
0x18000c525  test    rcx, rcx
0x18000c528  jz      loc_18000C76B
0x18000c52e  test    rdx, rdx
0x18000c531  jz      loc_18000C76B
0x18000c537  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c53e  lea     rbx, WPP_GLOBAL_Control
0x18000c545  cmp     rcx, rbx
0x18000c548  jz      short loc_18000C56B
0x18000c54a  test    byte ptr [rcx+1Ch], 20h
0x18000c54e  jz      short loc_18000C56B
0x18000c550  mov     rcx, [rcx+10h]
0x18000c554  mov     edx, 11Fh
0x18000c559  mov     r9, rdi
0x18000c55c  mov     r8, r12
0x18000c55f  call    WPP_SF_S
0x18000c564  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c56b  mov     r13d, 5Ch ; '\'
0x18000c571  cmp     [rdi], r13w
0x18000c575  jnz     loc_18000C750
0x18000c57b  cmp     [rdi+2], r13w
0x18000c580  jnz     loc_18000C750
0x18000c586  add     rdi, 4
0x18000c58a  mov     rdx, rdi
0x18000c58d  movzx   eax, word ptr [rdi]
0x18000c590  cmp     ax, r13w
0x18000c594  jz      short loc_18000C5B1
0x18000c596  test    ax, ax
0x18000c599  jz      short loc_18000C5A8
0x18000c59b  add     rdi, 2
0x18000c59f  movzx   eax, word ptr [rdi]
0x18000c5a2  cmp     ax, r13w
0x18000c5a6  jnz     short loc_18000C596
0x18000c5a8  cmp     rdi, rdx
0x18000c5ab  jb      loc_18000C732
0x18000c5b1  mov     rax, rdi
0x18000c5b4  sub     rax, rdx
0x18000c5b7  sar     rax, 1
0x18000c5ba  cmp     rax, 104h
0x18000c5c0  ja      loc_18000C732
0x18000c5c6  mov     esi, ebp
0x18000c5c8  cmp     [rdi], r13w
0x18000c5cc  jnz     loc_18000C7A5
0x18000c5d2  lea     rcx, [rdi+2]; String1
0x18000c5d6  mov     r8d, 0Ah; MaxCount
0x18000c5dc  lea     rdx, aDavwwwroot; "DavWWWRoot"
0x18000c5e3  call    cs:__imp__wcsnicmp
0x18000c5e9  test    eax, eax
0x18000c5eb  lea     rcx, [rdi+16h]
0x18000c5ef  lea     r8, [rsp+68h+pcchLength]; pcchLength
0x18000c5f4  cmovnz  rcx, rdi
0x18000c5f8  cmp     r13w, [rcx]
0x18000c5fc  lea     r14, [rcx+2]
0x18000c600  cmovnz  r14, rcx
0x18000c604  mov     rcx, r14; psz
0x18000c607  call    StringCchLengthW
0x18000c60c  test    eax, eax
0x18000c60e  jns     short loc_18000C648
0x18000c610  call    cs:__imp_GetLastError
0x18000c616  mov     esi, eax
0x18000c618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c61f  cmp     rcx, rbx
0x18000c622  jz      loc_18000C7C4
0x18000c628  test    byte ptr [rcx+1Ch], 1
0x18000c62c  jz      loc_18000C7A5
0x18000c632  mov     edx, 122h
0x18000c637  mov     rcx, [rcx+10h]
0x18000c63b  mov     r8, r12
0x18000c63e  call    WPP_SF_
0x18000c643  jmp     loc_18000C79E
0x18000c648  mov     rdi, [rsp+68h+pcchLength]
0x18000c64d  test    rdi, rdi
0x18000c650  jz      loc_18000C712
0x18000c656  lea     rdx, ds:2[rdi*2]; uBytes
0x18000c65e  mov     ecx, 40h ; '@'; uFlags
0x18000c663  call    cs:__imp_LocalAlloc
0x18000c669  mov     [r15], rax
0x18000c66c  mov     rcx, rax
0x18000c66f  test    rax, rax
0x18000c672  jnz     short loc_18000C6D6
0x18000c674  call    cs:__imp_GetLastError
0x18000c67a  mov     esi, eax
0x18000c67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c683  cmp     rcx, rbx
0x18000c686  jz      loc_18000C7C4
0x18000c68c  test    byte ptr [rcx+1Ch], 1
0x18000c690  jz      loc_18000C7A5
0x18000c696  mov     rcx, [rcx+10h]
0x18000c69a  mov     edx, 123h
0x18000c69f  mov     r9d, eax
0x18000c6a2  mov     r8, r12
0x18000c6a5  call    WPP_SF_d
0x18000c6aa  jmp     loc_18000C79E
0x18000c6af  mov     rax, rdi
0x18000c6b2  dec     rdi
0x18000c6b5  test    rax, rax
0x18000c6b8  jz      short loc_18000C6DC
0x18000c6ba  cmp     [r14], r13w
0x18000c6be  jnz     short loc_18000C6C7
0x18000c6c0  mov     eax, 2Fh ; '/'
0x18000c6c5  jmp     short loc_18000C6CB
0x18000c6c7  movzx   eax, word ptr [r14]
0x18000c6cb  mov     [rcx], ax
0x18000c6ce  add     rcx, 2
0x18000c6d2  add     r14, 2
0x18000c6d6  cmp     [r14], bp
0x18000c6da  jnz     short loc_18000C6AF
0x18000c6dc  mov     [rcx], bp
0x18000c6df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6e6  cmp     rcx, rbx
0x18000c6e9  jz      loc_18000C7C4
0x18000c6ef  test    byte ptr [rcx+1Ch], 20h
0x18000c6f3  jz      loc_18000C7A5
0x18000c6f9  mov     r9, [r15]
0x18000c6fc  mov     edx, 124h
0x18000c701  mov     rcx, [rcx+10h]
0x18000c705  mov     r8, r12
0x18000c708  call    WPP_SF_S
0x18000c70d  jmp     loc_18000C79E
0x18000c712  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c719  cmp     rcx, rbx
0x18000c71c  jz      loc_18000C7C4
0x18000c722  test    byte ptr [rcx+1Ch], 20h
0x18000c726  jz      short loc_18000C7A5
0x18000c728  mov     edx, 125h
0x18000c72d  jmp     loc_18000C637
0x18000c732  mov     esi, 57h ; 'W'
0x18000c737  cmp     rcx, rbx
0x18000c73a  jz      loc_18000C7C4
0x18000c740  test    byte ptr [rcx+1Ch], 1
0x18000c744  jz      short loc_18000C7A5
0x18000c746  mov     edx, 121h
0x18000c74b  jmp     loc_18000C637
0x18000c750  mov     r9d, 57h ; 'W'
0x18000c756  mov     esi, r9d
0x18000c759  cmp     rcx, rbx
0x18000c75c  jz      short loc_18000C7C4
0x18000c75e  test    byte ptr [rcx+1Ch], 1
0x18000c762  jz      short loc_18000C7A5
0x18000c764  mov     edx, 120h
0x18000c769  jmp     short loc_18000C792
0x18000c76b  mov     r9d, 57h ; 'W'
0x18000c771  mov     esi, r9d
0x18000c774  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c77b  lea     rbx, WPP_GLOBAL_Control
0x18000c782  cmp     rcx, rbx
0x18000c785  jz      short loc_18000C7C4
0x18000c787  test    byte ptr [rcx+1Ch], 1
0x18000c78b  jz      short loc_18000C7A5
0x18000c78d  mov     edx, 11Eh
0x18000c792  mov     rcx, [rcx+10h]
0x18000c796  mov     r8, r12
0x18000c799  call    WPP_SF_d
0x18000c79e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7a5  cmp     rcx, rbx
0x18000c7a8  jz      short loc_18000C7C4
0x18000c7aa  test    byte ptr [rcx+1Ch], 20h
0x18000c7ae  jz      short loc_18000C7C4
0x18000c7b0  mov     rcx, [rcx+10h]
0x18000c7b4  mov     edx, 126h
0x18000c7b9  mov     r9d, esi
0x18000c7bc  mov     r8, r12
0x18000c7bf  call    WPP_SF_d
0x18000c7c4  mov     eax, esi
0x18000c7c6  add     rsp, 28h
0x18000c7ca  pop     r15
0x18000c7cc  pop     r14
0x18000c7ce  pop     r13
0x18000c7d0  pop     r12
0x18000c7d2  pop     rdi
0x18000c7d3  pop     rsi
0x18000c7d4  pop     rbp
0x18000c7d5  pop     rbx
0x18000c7d6  retn
```
