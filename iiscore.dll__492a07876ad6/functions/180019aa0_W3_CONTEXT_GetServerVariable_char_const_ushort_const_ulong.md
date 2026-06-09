# W3_CONTEXT::GetServerVariable(char const *,ushort const * *,ulong *)

- ea: `0x180019aa0`
- end: `0x180019f07`
- name: `?GetServerVariable@W3_CONTEXT@@UEAAJPEBDPEAPEBGPEAK@Z`
- size: `1127`
- prototype: `int(W3_CONTEXT *__hidden this, const char *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180010f80`
- `0x180019aa0`
- `0x180037752`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180019c82`
- `msvcrt!_stricmp` at `0x180019c82`
- `msvcrt!strchr` at `0x180019d6d`
- `msvcrt!strchr` at `0x180019d8c`
- `msvcrt!strchr` at `0x180019d6d`
- `msvcrt!strchr` at `0x180019d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ea4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019e53`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019e94`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019e53`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019e94`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180019d04`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180019d04`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180019d50`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180019def`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180019ee7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180019d50`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180019def`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180019ee7`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180019d39`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180019d39`

## pseudocode

```c
int __fastcall W3_CONTEXT::GetServerVariable(
        W3_CONTEXT *this,
        const char *a2,
        const unsigned __int16 **a3,
        unsigned int *a4)
{
  unsigned int v8; // r11d
  __int64 v9; // r9
  __int64 v10; // rbx
  const char *v11; // rax
  const char *v12; // r8
  int v13; // ecx
  int v14; // edx
  unsigned __int8 v15; // cl
  unsigned int v16; // edx
  const char *v17; // rdi
  _DWORD *v18; // r14
  int v19; // eax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdx
  int result; // eax
  __int64 v23; // rdi
  __int64 i; // rbx
  __int64 v25; // rax
  bool v26; // zf
  __int64 (__fastcall *v27)(W3_CONTEXT *, const unsigned __int16 **, unsigned int *); // rax
  __int64 (__fastcall *v28)(W3_CONTEXT *, LPCCH *, int *); // rax
  int v29; // ebx
  char *j; // rax
  char *v31; // rdx
  WCHAR *lpWideCharStr; // rax
  unsigned __int16 *v33; // rbx
  int v34; // eax
  unsigned __int16 v35[2]; // [rsp+30h] [rbp-A8h] BYREF
  int v36; // [rsp+34h] [rbp-A4h] BYREF
  LPCCH lpMultiByteStr; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v38[32]; // [rsp+40h] [rbp-98h] BYREF
  char *Str; // [rsp+60h] [rbp-78h]
  char v40[32]; // [rsp+78h] [rbp-60h] BYREF

  lpMultiByteStr = 0;
  v36 = 0;
  if ( !a2 || !a3 || !a4 )
    return -2147024809;
  v8 = *((_DWORD *)this + 2268);
  if ( v8 )
  {
    v9 = 0;
    v10 = *(_QWORD *)(*((_QWORD *)this + 1132) + 32LL);
    while ( 1 )
    {
      v11 = *(const char **)(v10 + 8 * v9);
      v12 = (const char *)(a2 - v11);
      do
      {
        v13 = (unsigned __int8)v12[(_QWORD)v11];
        v14 = *(unsigned __int8 *)v11 - v13;
        if ( v14 )
          break;
        ++v11;
      }
      while ( v13 );
      if ( !v14 )
        break;
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v8 )
        goto LABEL_11;
    }
    v20 = -1;
    v21 = *(const unsigned __int16 **)(8 * v9 + *(_QWORD *)(*((_QWORD *)this + 1133) + 32LL));
    *a3 = v21;
    do
      ++v20;
    while ( v21[v20] );
    goto LABEL_17;
  }
LABEL_11:
  v15 = *a2;
  v16 = 0;
  v17 = a2;
  v18 = SERVERVAR_HASH::sm_pServerVarHash;
  if ( *((_DWORD *)SERVERVAR_HASH::sm_pServerVarHash + 214) )
  {
    if ( v15 )
    {
      do
      {
        ++v17;
        v19 = v15;
        v15 = *v17;
        v16 = v19 + 101 * v16;
      }
      while ( *v17 );
    }
  }
  else if ( v15 )
  {
    do
    {
      ++v17;
      v16 = (v15 & 0xDF) + 101 * v16;
      v15 = *v17;
    }
    while ( *v17 );
  }
  v23 = v17 - a2;
  for ( i = *((_QWORD *)SERVERVAR_HASH::sm_pServerVarHash + v16 % 0x6B); i; i = *(_QWORD *)(i + 8) )
  {
    v25 = *(unsigned __int16 *)(i + 16);
    if ( v18[214] )
    {
      if ( v23 == v25 )
      {
        v26 = strcmp(a2, *(const char **)i) == 0;
        goto LABEL_27;
      }
    }
    else if ( v23 == v25 )
    {
      v26 = _stricmp(a2, *(const char **)i) == 0;
LABEL_27:
      if ( v26 )
        break;
    }
  }
  if ( !i )
    goto LABEL_35;
  v27 = *(__int64 (__fastcall **)(W3_CONTEXT *, const unsigned __int16 **, unsigned int *))(i + 24);
  if ( v27 )
    return v27(this, a3, a4);
  v28 = *(__int64 (__fastcall **)(W3_CONTEXT *, LPCCH *, int *))(i + 32);
  if ( !v28 )
  {
LABEL_35:
    STRA::STRA((STRA *)v38, v40, 0x20u);
    v35[0] = 0;
    if ( !strncmp_0(a2, "HTTP_", 5u) )
    {
      v29 = STRA::Copy((STRA *)v38, a2 + 5);
      if ( v29 < 0 )
      {
        STRA::~STRA((STRA *)v38);
        return v29;
      }
      for ( j = strchr(Str, 95); j; j = strchr(j + 1, 95) )
        *j = 45;
      v31 = Str;
    }
    else
    {
      if ( strncmp_0(a2, "HEADER_", 7u) )
        goto LABEL_55;
      v31 = (char *)(a2 + 7);
    }
    lpMultiByteStr = W3_REQUEST::GetHeader(*((W3_REQUEST **)this + 6), v31, v35);
    if ( lpMultiByteStr )
    {
      v36 = v35[0];
      STRA::~STRA((STRA *)v38);
      goto LABEL_45;
    }
LABEL_55:
    STRA::~STRA((STRA *)v38);
    return -2147023483;
  }
  result = v28(this, &lpMultiByteStr, &v36);
  if ( result < 0 )
    return result;
LABEL_45:
  if ( !v36 )
  {
    LODWORD(v20) = 0;
    *a3 = &dword_18003C134;
    goto LABEL_17;
  }
  lpWideCharStr = (WCHAR *)(*(__int64 (__fastcall **)(W3_CONTEXT *, _QWORD))(*(_QWORD *)this + 144LL))(
                             this,
                             (unsigned int)(2 * v36 + 2));
  v33 = lpWideCharStr;
  if ( !lpWideCharStr )
    return -2147024888;
  v34 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, v36 + 1, lpWideCharStr, v36 + 1);
  if ( v34 || GetLastError() == 1113 && (v34 = MultiByteToWideChar(0, 9u, lpMultiByteStr, v36 + 1, v33, v36 + 1)) != 0 )
  {
    LODWORD(v20) = v34 - 1;
    *a3 = v33;
LABEL_17:
    *a4 = v20;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180019aa0  push    rbp
0x180019aa2  push    rsi
0x180019aa3  push    r12
0x180019aa5  push    r15
0x180019aa7  sub     rsp, 0B8h
0x180019aae  mov     rax, cs:__security_cookie
0x180019ab5  xor     rax, rsp
0x180019ab8  mov     [rsp+0D8h+var_40], rax
0x180019ac0  mov     [rsp+0D8h+lpMultiByteStr], 0
0x180019ac9  mov     rbp, r9
0x180019acc  mov     [rsp+0D8h+var_A4], 0
0x180019ad4  mov     r12, r8
0x180019ad7  mov     rsi, rdx
0x180019ada  mov     r15, rcx
0x180019add  test    rdx, rdx
0x180019ae0  jz      loc_180019EFD
0x180019ae6  test    r8, r8
0x180019ae9  jz      loc_180019EFD
0x180019aef  test    r9, r9
0x180019af2  jz      loc_180019EFD
0x180019af8  mov     r11d, [rcx+2370h]
0x180019aff  mov     [rsp+0D8h+var_28], rbx
0x180019b07  test    r11d, r11d
0x180019b0a  jz      short loc_180019B51
0x180019b0c  mov     rax, [rcx+2360h]
0x180019b13  xor     r9d, r9d
0x180019b16  mov     rbx, [rax+20h]
0x180019b1a  nop     word ptr [rax+rax+00h]
0x180019b20  mov     rax, [rbx+r9*8]
0x180019b24  lea     r10, ds:0[r9*8]
0x180019b2c  mov     r8, rsi
0x180019b2f  sub     r8, rax
0x180019b32  movzx   edx, byte ptr [rax]
0x180019b35  movzx   ecx, byte ptr [rax+r8]
0x180019b3a  sub     edx, ecx
0x180019b3c  jnz     short loc_180019B45
0x180019b3e  inc     rax
0x180019b41  test    ecx, ecx
0x180019b43  jnz     short loc_180019B32
0x180019b45  test    edx, edx
0x180019b47  jz      short loc_180019B95
0x180019b49  inc     r9d
0x180019b4c  cmp     r9d, r11d
0x180019b4f  jb      short loc_180019B20
0x180019b51  movzx   ecx, byte ptr [rsi]
0x180019b54  xor     edx, edx
0x180019b56  mov     [rsp+0D8h+var_30], rdi
0x180019b5e  mov     rdi, rsi
0x180019b61  mov     [rsp+0D8h+var_38], r14
0x180019b69  mov     r14, cs:?sm_pServerVarHash@SERVERVAR_HASH@@0PEAV1@EA; SERVERVAR_HASH * SERVERVAR_HASH::sm_pServerVarHash
0x180019b70  cmp     [r14+358h], edx
0x180019b77  jz      short loc_180019BE6
0x180019b79  test    cl, cl
0x180019b7b  jz      loc_180019C05
0x180019b81  imul    edx, 65h ; 'e'
0x180019b84  inc     rdi
0x180019b87  movzx   eax, cl
0x180019b8a  movzx   ecx, byte ptr [rdi]
0x180019b8d  add     edx, eax
0x180019b8f  test    cl, cl
0x180019b91  jnz     short loc_180019B81
0x180019b93  jmp     short loc_180019C05
0x180019b95  mov     rax, [r15+2368h]
0x180019b9c  mov     rcx, [rax+20h]
0x180019ba0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019ba7  mov     rdx, [r10+rcx]
0x180019bab  mov     [r12], rdx
0x180019baf  nop
0x180019bb0  inc     rax
0x180019bb3  cmp     word ptr [rdx+rax*2], 0
0x180019bb8  jnz     short loc_180019BB0
0x180019bba  mov     [rbp+0], eax
0x180019bbd  xor     eax, eax
0x180019bbf  mov     rbx, [rsp+0D8h+var_28]
0x180019bc7  mov     rcx, [rsp+0D8h+var_40]
0x180019bcf  xor     rcx, rsp; StackCookie
0x180019bd2  call    __security_check_cookie
0x180019bd7  add     rsp, 0B8h
0x180019bde  pop     r15
0x180019be0  pop     r12
0x180019be2  pop     rsi
0x180019be3  pop     rbp
0x180019be4  retn
0x180019be6  test    cl, cl
0x180019be8  jz      short loc_180019C05
0x180019bea  nop     word ptr [rax+rax+00h]
0x180019bf0  and     ecx, 0DFh
0x180019bf6  imul    edx, 65h ; 'e'
0x180019bf9  inc     rdi
0x180019bfc  add     edx, ecx
0x180019bfe  movzx   ecx, byte ptr [rdi]
0x180019c01  test    cl, cl
0x180019c03  jnz     short loc_180019BF0
0x180019c05  mov     ecx, edx
0x180019c07  mov     rax, 323E34A2B10BF66Fh
0x180019c11  mul     rcx
0x180019c14  mov     eax, ecx
0x180019c16  sub     rdi, rsi
0x180019c19  sub     rax, rdx
0x180019c1c  shr     rax, 1
0x180019c1f  add     rax, rdx
0x180019c22  shr     rax, 6
0x180019c26  imul    rax, 6Bh ; 'k'
0x180019c2a  sub     rcx, rax
0x180019c2d  mov     eax, ecx
0x180019c2f  mov     rbx, [r14+rax*8]
0x180019c33  test    rbx, rbx
0x180019c36  jz      short loc_180019C9B
0x180019c38  nop     dword ptr [rax+rax+00000000h]
0x180019c40  cmp     dword ptr [r14+358h], 0
0x180019c48  movzx   eax, word ptr [rbx+10h]
0x180019c4c  jz      short loc_180019C77
0x180019c4e  cmp     rdi, rax
0x180019c51  jnz     short loc_180019C92
0x180019c53  mov     r8, [rbx]
0x180019c56  mov     rax, rsi
0x180019c59  sub     r8, rsi
0x180019c5c  nop     dword ptr [rax+00h]
0x180019c60  movzx   edx, byte ptr [rax]
0x180019c63  movzx   ecx, byte ptr [rax+r8]
0x180019c68  sub     edx, ecx
0x180019c6a  jnz     short loc_180019C73
0x180019c6c  inc     rax
0x180019c6f  test    ecx, ecx
0x180019c71  jnz     short loc_180019C60
0x180019c73  test    edx, edx
0x180019c75  jmp     short loc_180019C90
0x180019c77  cmp     rdi, rax
0x180019c7a  jnz     short loc_180019C92
0x180019c7c  mov     rdx, [rbx]; String2
0x180019c7f  mov     rcx, rsi; String1
0x180019c82  call    cs:__imp__stricmp
0x180019c89  nop     dword ptr [rax+rax+00h]
0x180019c8e  test    eax, eax
0x180019c90  jz      short loc_180019C9B
0x180019c92  mov     rbx, [rbx+8]
0x180019c96  test    rbx, rbx
0x180019c99  jnz     short loc_180019C40
0x180019c9b  mov     r14, [rsp+0D8h+var_38]
0x180019ca3  mov     rdi, [rsp+0D8h+var_30]
0x180019cab  test    rbx, rbx
0x180019cae  jz      short loc_180019CF4
0x180019cb0  mov     rax, [rbx+18h]
0x180019cb4  test    rax, rax
0x180019cb7  jz      short loc_180019CCC
0x180019cb9  mov     r8, rbp
0x180019cbc  mov     rdx, r12
0x180019cbf  mov     rcx, r15
0x180019cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc7  jmp     loc_180019BBF
0x180019ccc  mov     rax, [rbx+20h]
0x180019cd0  test    rax, rax
0x180019cd3  jz      short loc_180019CF4
0x180019cd5  lea     r8, [rsp+0D8h+var_A4]
0x180019cda  mov     rcx, r15
0x180019cdd  lea     rdx, [rsp+0D8h+lpMultiByteStr]
0x180019ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ce7  test    eax, eax
0x180019ce9  jns     loc_180019DFB
0x180019cef  jmp     loc_180019BBF
0x180019cf4  mov     r8d, 20h ; ' '
0x180019cfa  lea     rdx, [rsp+0D8h+var_60]
0x180019cff  lea     rcx, [rsp+0D8h+var_98]
0x180019d04  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180019d0b  nop     dword ptr [rax+rax+00h]
0x180019d10  xor     eax, eax
0x180019d12  lea     rdx, aHttp; "HTTP_"
0x180019d19  mov     r8d, 5; MaxCount
0x180019d1f  mov     [rsp+0D8h+var_A8], ax
0x180019d24  mov     rcx, rsi; Str1
0x180019d27  call    strncmp_0
0x180019d2c  test    eax, eax
0x180019d2e  jnz     short loc_180019DA4
0x180019d30  lea     rdx, [rsi+5]
0x180019d34  lea     rcx, [rsp+0D8h+var_98]
0x180019d39  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180019d40  nop     dword ptr [rax+rax+00h]
0x180019d45  mov     ebx, eax
0x180019d47  test    eax, eax
0x180019d49  jns     short loc_180019D63
0x180019d4b  lea     rcx, [rsp+0D8h+var_98]
0x180019d50  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180019d57  nop     dword ptr [rax+rax+00h]
0x180019d5c  mov     eax, ebx
0x180019d5e  jmp     loc_180019BBF
0x180019d63  mov     rcx, [rsp+0D8h+Str]; Str
0x180019d68  mov     edx, 5Fh ; '_'; Val
0x180019d6d  call    cs:__imp_strchr
0x180019d74  nop     dword ptr [rax+rax+00h]
0x180019d79  test    rax, rax
0x180019d7c  jz      short loc_180019D9D
0x180019d7e  xchg    ax, ax
0x180019d80  lea     rcx, [rax+1]; Str
0x180019d84  mov     byte ptr [rax], 2Dh ; '-'
0x180019d87  mov     edx, 5Fh ; '_'; Val
0x180019d8c  call    cs:__imp_strchr
0x180019d93  nop     dword ptr [rax+rax+00h]
0x180019d98  test    rax, rax
0x180019d9b  jnz     short loc_180019D80
0x180019d9d  mov     rdx, [rsp+0D8h+Str]
0x180019da2  jmp     short loc_180019DC5
0x180019da4  mov     r8d, 7; MaxCount
0x180019daa  lea     rdx, aHeader; "HEADER_"
0x180019db1  mov     rcx, rsi; Str1
0x180019db4  call    strncmp_0
0x180019db9  test    eax, eax
0x180019dbb  jnz     loc_180019EE2
0x180019dc1  lea     rdx, [rsi+7]; char *
0x180019dc5  mov     rcx, [r15+30h]; this
0x180019dc9  lea     r8, [rsp+0D8h+var_A8]; unsigned __int16 *
0x180019dce  call    ?GetHeader@W3_REQUEST@@QEBAPEBDPEBDPEAG@Z; W3_REQUEST::GetHeader(char const *,ushort *)
0x180019dd3  mov     [rsp+0D8h+lpMultiByteStr], rax
0x180019dd8  test    rax, rax
0x180019ddb  jz      loc_180019EE2
0x180019de1  movzx   eax, [rsp+0D8h+var_A8]
0x180019de6  lea     rcx, [rsp+0D8h+var_98]
0x180019deb  mov     [rsp+0D8h+var_A4], eax
0x180019def  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180019df6  nop     dword ptr [rax+rax+00h]
0x180019dfb  mov     edx, [rsp+0D8h+var_A4]
0x180019dff  test    edx, edx
0x180019e01  jz      loc_180019ED0
0x180019e07  mov     rax, [r15]
0x180019e0a  lea     edx, ds:2[rdx*2]
0x180019e11  mov     rcx, r15
0x180019e14  mov     rax, [rax+90h]
0x180019e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e20  mov     rbx, rax
0x180019e23  test    rax, rax
0x180019e26  jnz     short loc_180019E32
0x180019e28  mov     eax, 80070008h
0x180019e2d  jmp     loc_180019BBF
0x180019e32  mov     r9d, [rsp+0D8h+var_A4]
0x180019e37  mov     edx, 8; dwFlags
0x180019e3c  mov     r8, [rsp+0D8h+lpMultiByteStr]; lpMultiByteStr
0x180019e41  inc     r9d; cbMultiByte
0x180019e44  mov     [rsp+0D8h+cchWideChar], r9d; cchWideChar
0x180019e49  mov     ecx, 0FDE9h; CodePage
0x180019e4e  mov     [rsp+0D8h+lpWideCharStr], rbx; lpWideCharStr
0x180019e53  call    cs:__imp_MultiByteToWideChar
0x180019e5a  nop     dword ptr [rax+rax+00h]
0x180019e5f  test    eax, eax
0x180019e61  jnz     short loc_180019EC5
0x180019e63  call    cs:__imp_GetLastError
0x180019e6a  nop     dword ptr [rax+rax+00h]
0x180019e6f  cmp     eax, 459h
0x180019e74  jnz     short loc_180019EA4
0x180019e76  mov     r9d, [rsp+0D8h+var_A4]
0x180019e7b  mov     edx, 9; dwFlags
0x180019e80  mov     r8, [rsp+0D8h+lpMultiByteStr]; lpMultiByteStr
0x180019e85  inc     r9d; cbMultiByte
0x180019e88  mov     [rsp+0D8h+cchWideChar], r9d; cchWideChar
0x180019e8d  xor     ecx, ecx; CodePage
0x180019e8f  mov     [rsp+0D8h+lpWideCharStr], rbx; lpWideCharStr
0x180019e94  call    cs:__imp_MultiByteToWideChar
0x180019e9b  nop     dword ptr [rax+rax+00h]
0x180019ea0  test    eax, eax
0x180019ea2  jnz     short loc_180019EC5
0x180019ea4  call    cs:__imp_GetLastError
0x180019eab  nop     dword ptr [rax+rax+00h]
0x180019eb0  test    eax, eax
0x180019eb2  jle     loc_180019BBF
0x180019eb8  movzx   eax, ax
0x180019ebb  or      eax, 80070000h
0x180019ec0  jmp     loc_180019BBF
0x180019ec5  dec     eax
0x180019ec7  mov     [r12], rbx
0x180019ecb  jmp     loc_180019BBA
0x180019ed0  lea     rbx, dword_18003C134
0x180019ed7  xor     eax, eax
0x180019ed9  mov     [r12], rbx
0x180019edd  jmp     loc_180019BBA
0x180019ee2  lea     rcx, [rsp+0D8h+var_98]
0x180019ee7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180019eee  nop     dword ptr [rax+rax+00h]
0x180019ef3  mov     eax, 80070585h
0x180019ef8  jmp     loc_180019BBF
0x180019efd  mov     eax, 80070057h
0x180019f02  jmp     loc_180019BC7
```
