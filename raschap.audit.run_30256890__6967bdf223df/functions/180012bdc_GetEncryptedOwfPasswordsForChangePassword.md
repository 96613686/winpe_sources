# GetEncryptedOwfPasswordsForChangePassword

- ea: `0x180012bdc`
- end: `0x18001307b`
- name: `GetEncryptedOwfPasswordsForChangePassword`
- size: `1183`
- prototype: `__int64 __usercall@<rax>(PCSZ Source@<rcx>, PCSZ@<rdx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012974`

## callees

- `0x18000b460`
- `0x18000b810`
- `0x180012bdc`
- `0x180013b20`
- `0x180014610`

## import_xrefs

- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180012eda`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180012f95`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180012eda`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180012f95`
- `ntdll!RtlFreeUnicodeString` at `0x180012f1d`
- `ntdll!RtlFreeUnicodeString` at `0x180012f62`
- `ntdll!RtlFreeUnicodeString` at `0x180012f1d`
- `ntdll!RtlFreeUnicodeString` at `0x180012f62`
- `CRYPTSP!SystemFunction007` at `0x180012ef2`
- `CRYPTSP!SystemFunction007` at `0x180012fad`
- `CRYPTSP!SystemFunction007` at `0x180012ef2`
- `CRYPTSP!SystemFunction007` at `0x180012fad`
- `CRYPTSP!SystemFunction006` at `0x180012d1c`
- `CRYPTSP!SystemFunction006` at `0x180012e31`
- `CRYPTSP!SystemFunction006` at `0x180012d1c`
- `CRYPTSP!SystemFunction006` at `0x180012e31`
- `CRYPTSP!SystemFunction016` at `0x180012d5d`
- `CRYPTSP!SystemFunction016` at `0x180012e76`
- `CRYPTSP!SystemFunction016` at `0x180012d5d`
- `CRYPTSP!SystemFunction016` at `0x180012e76`
- `CRYPTSP!SystemFunction018` at `0x180012f37`
- `CRYPTSP!SystemFunction018` at `0x180012fe9`
- `CRYPTSP!SystemFunction018` at `0x180012f37`
- `CRYPTSP!SystemFunction018` at `0x180012fe9`

## pseudocode

```c
__int64 __fastcall GetEncryptedOwfPasswordsForChangePassword(
        PCSZ Source,
        PCSZ a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // rbx
  unsigned __int64 v11; // rax
  __int64 v13; // rsi
  unsigned __int64 v14; // rax
  char *i; // rax
  char *j; // rax
  int v17; // ecx
  char *k; // rax
  char *m; // rax
  __int128 *v21; // rax
  __int64 v22; // rcx
  __int128 *v23; // rax
  char *n; // rax
  char *ii; // rax
  char *jj; // rax
  char *kk; // rax
  __int128 *v28; // rax
  __int64 v29; // rcx
  __int128 *v30; // rax
  int v31; // ebx
  __int64 Length; // rcx
  PWSTR Buffer; // rdx
  __int64 v34; // rcx
  PWSTR v35; // rdx
  __int128 *v36; // rax
  __int64 v37; // rcx
  __int128 *v38; // rax
  __int64 v39; // rcx
  PWSTR v40; // rdx
  __int64 v41; // rcx
  PWSTR v42; // rdx
  __int128 *v43; // rax
  __int64 v44; // rax
  PWSTR v45; // rcx
  __int128 *v46; // rax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v48; // [rsp+30h] [rbp-D0h]
  __int64 v49; // [rsp+38h] [rbp-C8h]
  __int64 v50; // [rsp+40h] [rbp-C0h]
  __int128 v51; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v52; // [rsp+58h] [rbp-A8h] BYREF
  char pszDest[144]; // [rsp+70h] [rbp-90h] BYREF

  v48 = a5;
  v7 = -1;
  v49 = a6;
  v50 = a7;
  v11 = -1;
  Destination = 0;
  v52 = 0;
  do
    ++v11;
  while ( Source[v11] );
  v13 = 16;
  if ( v11 <= 0x80 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    if ( v14 <= 0x80 )
    {
      memset_0(pszDest, 0, 0x81u);
      v51 = 0;
      if ( StringCchCopyA(pszDest, 0x81u, Source) )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( i = pszDest; v7; --v7 )
          *i++ = 0;
        return 1;
      }
      if ( !(unsigned int)Uppercase(pszDest) )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( j = pszDest; v7; --v7 )
          *j++ = 0;
        return 1;
      }
      v17 = SystemFunction006(pszDest, &v51);
      if ( v17 < 0 )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( k = pszDest; v7; --v7 )
          *k++ = 0;
        return (unsigned int)v17;
      }
      v17 = SystemFunction016(&v51, a3, a4);
      if ( v17 < 0 )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( m = pszDest; v7; --v7 )
          *m++ = 0;
        v21 = &v51;
        do
        {
          *(_BYTE *)v21 = 0;
          v21 = (__int128 *)((char *)v21 + 1);
          --v13;
        }
        while ( v13 );
        return (unsigned int)v17;
      }
      v22 = 16;
      v23 = &v51;
      do
      {
        *(_BYTE *)v23 = 0;
        v23 = (__int128 *)((char *)v23 + 1);
        --v22;
      }
      while ( v22 );
      if ( StringCchCopyA(pszDest, 0x81u, a2) )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( n = pszDest; v7; --v7 )
          *n++ = 0;
        return 1;
      }
      if ( !(unsigned int)Uppercase(pszDest) )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( ii = pszDest; v7; --v7 )
          *ii++ = 0;
        return 1;
      }
      v17 = SystemFunction006(pszDest, &v51);
      if ( v17 < 0 )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( jj = pszDest; v7; --v7 )
          *jj++ = 0;
        return (unsigned int)v17;
      }
      v17 = SystemFunction016(&v51, a3, v48);
      if ( v17 < 0 )
      {
        do
          ++v7;
        while ( pszDest[v7] );
        for ( kk = pszDest; v7; --v7 )
          *kk++ = 0;
        v28 = &v51;
        do
        {
          *(_BYTE *)v28 = 0;
          v28 = (__int128 *)((char *)v28 + 1);
          --v13;
        }
        while ( v13 );
        return (unsigned int)v17;
      }
      v29 = 16;
      v30 = &v51;
      do
      {
        *(_BYTE *)v30 = 0;
        v30 = (__int128 *)((char *)v30 + 1);
        --v29;
      }
      while ( v29 );
    }
  }
  if ( RtlCreateUnicodeStringFromAsciiz(&Destination, Source) )
  {
    v31 = SystemFunction007(&Destination, &v52);
    if ( v31 < 0 )
    {
      Length = Destination.Length;
      Buffer = Destination.Buffer;
      if ( Destination.Length )
      {
        do
        {
          *(_BYTE *)Buffer = 0;
          Buffer = (PWSTR)((char *)Buffer + 1);
          --Length;
        }
        while ( Length );
      }
LABEL_59:
      RtlFreeUnicodeString(&Destination);
      return (unsigned int)v31;
    }
    v31 = SystemFunction018(&v52, a3, v49);
    if ( v31 < 0 )
    {
      v34 = Destination.Length;
      v35 = Destination.Buffer;
      if ( Destination.Length )
      {
        do
        {
          *(_BYTE *)v35 = 0;
          v35 = (PWSTR)((char *)v35 + 1);
          --v34;
        }
        while ( v34 );
      }
      RtlFreeUnicodeString(&Destination);
      v36 = &v52;
      do
      {
        *(_BYTE *)v36 = 0;
        v36 = (__int128 *)((char *)v36 + 1);
        --v13;
      }
      while ( v13 );
      return (unsigned int)v31;
    }
    v37 = 16;
    v38 = &v52;
    do
    {
      *(_BYTE *)v38 = 0;
      v38 = (__int128 *)((char *)v38 + 1);
      --v37;
    }
    while ( v37 );
    if ( RtlCreateUnicodeStringFromAsciiz(&Destination, a2) )
    {
      v31 = SystemFunction007(&Destination, &v52);
      if ( v31 >= 0 )
      {
        v31 = SystemFunction018(&v52, a3, v50);
        if ( v31 >= 0 )
        {
          v44 = Destination.Length;
          v45 = Destination.Buffer;
          if ( Destination.Length )
          {
            do
            {
              *(_BYTE *)v45 = 0;
              v45 = (PWSTR)((char *)v45 + 1);
              --v44;
            }
            while ( v44 );
          }
          v46 = &v52;
          do
          {
            *(_BYTE *)v46 = 0;
            v46 = (__int128 *)((char *)v46 + 1);
            --v13;
          }
          while ( v13 );
          v31 = 0;
        }
        else
        {
          v41 = Destination.Length;
          v42 = Destination.Buffer;
          if ( Destination.Length )
          {
            do
            {
              *(_BYTE *)v42 = 0;
              v42 = (PWSTR)((char *)v42 + 1);
              --v41;
            }
            while ( v41 );
          }
          v43 = &v52;
          do
          {
            *(_BYTE *)v43 = 0;
            v43 = (__int128 *)((char *)v43 + 1);
            --v13;
          }
          while ( v13 );
        }
      }
      else
      {
        v39 = Destination.Length;
        v40 = Destination.Buffer;
        if ( Destination.Length )
        {
          do
          {
            *(_BYTE *)v40 = 0;
            v40 = (PWSTR)((char *)v40 + 1);
            --v39;
          }
          while ( v39 );
        }
      }
      goto LABEL_59;
    }
  }
  return 8;
}

```

## disassembly

```asm
0x180012bdc  push    rbp
0x180012bde  push    rbx
0x180012bdf  push    rsi
0x180012be0  push    rdi
0x180012be1  push    r12
0x180012be3  push    r13
0x180012be5  push    r14
0x180012be7  push    r15
0x180012be9  lea     rbp, [rsp-18h]
0x180012bee  sub     rsp, 118h
0x180012bf5  mov     rax, cs:__security_cookie
0x180012bfc  xor     rax, rsp
0x180012bff  mov     [rbp+50h+var_50], rax
0x180012c03  mov     rax, [rbp+50h+arg_20]
0x180012c0a  xorps   xmm0, xmm0
0x180012c0d  mov     [rsp+150h+var_120], rax
0x180012c12  xorps   xmm1, xmm1
0x180012c15  mov     rax, [rbp+50h+arg_28]
0x180012c1c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012c20  mov     [rsp+150h+var_118], rax
0x180012c25  mov     r13, r9
0x180012c28  mov     rax, [rbp+50h+arg_30]
0x180012c2f  mov     r14, r8
0x180012c32  mov     [rsp+150h+var_110], rax
0x180012c37  mov     r12, rdx
0x180012c3a  mov     rax, rbx
0x180012c3d  mov     r15, rcx
0x180012c40  movups  xmmword ptr [rsp+150h+Destination.Length], xmm0
0x180012c45  movups  [rsp+150h+var_F8], xmm1
0x180012c4a  inc     rax
0x180012c4d  cmp     byte ptr [rcx+rax], 0
0x180012c51  jnz     short loc_180012C4A
0x180012c53  mov     edi, 1
0x180012c58  lea     ecx, [rdi+7Fh]
0x180012c5b  lea     esi, [rdi+0Fh]
0x180012c5e  cmp     rax, rcx
0x180012c61  ja      loc_180012ECF
0x180012c67  mov     rax, rbx
0x180012c6a  inc     rax
0x180012c6d  cmp     byte ptr [rdx+rax], 0
0x180012c71  jnz     short loc_180012C6A
0x180012c73  cmp     rax, rcx
0x180012c76  ja      loc_180012ECF
0x180012c7c  xor     edx, edx; Val
0x180012c7e  lea     rcx, [rsp+150h+pszDest]; void *
0x180012c83  mov     r8d, 81h; Size
0x180012c89  call    memset_0
0x180012c8e  xorps   xmm0, xmm0
0x180012c91  lea     rcx, [rsp+150h+pszDest]; pszDest
0x180012c96  mov     r8, r15; pszSrc
0x180012c99  mov     edx, 81h; cchDest
0x180012c9e  movups  [rsp+150h+var_108], xmm0
0x180012ca3  call    StringCchCopyA
0x180012ca8  test    eax, eax
0x180012caa  jz      short loc_180012CD8
0x180012cac  lea     rax, [rsp+150h+pszDest]
0x180012cb1  inc     rbx
0x180012cb4  cmp     byte ptr [rax+rbx], 0
0x180012cb8  jnz     short loc_180012CB1
0x180012cba  lea     rax, [rsp+150h+pszDest]
0x180012cbf  test    rbx, rbx
0x180012cc2  jz      loc_180012E20
0x180012cc8  mov     byte ptr [rax], 0
0x180012ccb  add     rax, rdi
0x180012cce  sub     rbx, rdi
0x180012cd1  jnz     short loc_180012CC8
0x180012cd3  jmp     loc_180012E20
0x180012cd8  lea     rcx, [rsp+150h+pszDest]; pszDest
0x180012cdd  call    Uppercase
0x180012ce2  test    eax, eax
0x180012ce4  jnz     short loc_180012D12
0x180012ce6  lea     rax, [rsp+150h+pszDest]
0x180012ceb  inc     rbx
0x180012cee  cmp     byte ptr [rax+rbx], 0
0x180012cf2  jnz     short loc_180012CEB
0x180012cf4  lea     rax, [rsp+150h+pszDest]
0x180012cf9  test    rbx, rbx
0x180012cfc  jz      loc_180012E20
0x180012d02  mov     byte ptr [rax], 0
0x180012d05  add     rax, rdi
0x180012d08  sub     rbx, rdi
0x180012d0b  jnz     short loc_180012D02
0x180012d0d  jmp     loc_180012E20
0x180012d12  lea     rdx, [rsp+150h+var_108]
0x180012d17  lea     rcx, [rsp+150h+pszDest]
0x180012d1c  call    cs:__imp_SystemFunction006
0x180012d22  mov     ecx, eax
0x180012d24  test    eax, eax
0x180012d26  jns     short loc_180012D52
0x180012d28  lea     rax, [rsp+150h+pszDest]
0x180012d2d  inc     rbx
0x180012d30  cmp     byte ptr [rax+rbx], 0
0x180012d34  jnz     short loc_180012D2D
0x180012d36  lea     rax, [rsp+150h+pszDest]
0x180012d3b  test    rbx, rbx
0x180012d3e  jz      short loc_180012D4B
0x180012d40  mov     byte ptr [rax], 0
0x180012d43  add     rax, rdi
0x180012d46  sub     rbx, rdi
0x180012d49  jnz     short loc_180012D40
0x180012d4b  mov     eax, ecx
0x180012d4d  jmp     loc_18001305B
0x180012d52  mov     r8, r13
0x180012d55  lea     rcx, [rsp+150h+var_108]
0x180012d5a  mov     rdx, r14
0x180012d5d  call    cs:__imp_SystemFunction016
0x180012d63  xor     r13d, r13d
0x180012d66  mov     ecx, eax
0x180012d68  test    eax, eax
0x180012d6a  jns     short loc_180012DA1
0x180012d6c  lea     rax, [rsp+150h+pszDest]
0x180012d71  inc     rbx
0x180012d74  cmp     [rax+rbx], r13b
0x180012d78  jnz     short loc_180012D71
0x180012d7a  lea     rax, [rsp+150h+pszDest]
0x180012d7f  test    rbx, rbx
0x180012d82  jz      short loc_180012D8F
0x180012d84  mov     [rax], r13b
0x180012d87  add     rax, rdi
0x180012d8a  sub     rbx, rdi
0x180012d8d  jnz     short loc_180012D84
0x180012d8f  lea     rax, [rsp+150h+var_108]
0x180012d94  mov     [rax], r13b
0x180012d97  add     rax, rdi
0x180012d9a  sub     rsi, rdi
0x180012d9d  jnz     short loc_180012D94
0x180012d9f  jmp     short loc_180012D4B
0x180012da1  mov     rcx, rsi
0x180012da4  lea     rax, [rsp+150h+var_108]
0x180012da9  mov     [rax], r13b
0x180012dac  add     rax, rdi
0x180012daf  sub     rcx, rdi
0x180012db2  jnz     short loc_180012DA9
0x180012db4  mov     r8, r12; pszSrc
0x180012db7  lea     rcx, [rsp+150h+pszDest]; pszDest
0x180012dbc  mov     edx, 81h; cchDest
0x180012dc1  call    StringCchCopyA
0x180012dc6  test    eax, eax
0x180012dc8  jz      short loc_180012DEF
0x180012dca  lea     rax, [rsp+150h+pszDest]
0x180012dcf  inc     rbx
0x180012dd2  cmp     [rax+rbx], r13b
0x180012dd6  jnz     short loc_180012DCF
0x180012dd8  lea     rax, [rsp+150h+pszDest]
0x180012ddd  test    rbx, rbx
0x180012de0  jz      short loc_180012E20
0x180012de2  mov     [rax], r13b
0x180012de5  add     rax, rdi
0x180012de8  sub     rbx, rdi
0x180012deb  jnz     short loc_180012DE2
0x180012ded  jmp     short loc_180012E20
0x180012def  lea     rcx, [rsp+150h+pszDest]; pszDest
0x180012df4  call    Uppercase
0x180012df9  test    eax, eax
0x180012dfb  jnz     short loc_180012E27
0x180012dfd  lea     rax, [rsp+150h+pszDest]
0x180012e02  inc     rbx
0x180012e05  cmp     [rax+rbx], r13b
0x180012e09  jnz     short loc_180012E02
0x180012e0b  lea     rax, [rsp+150h+pszDest]
0x180012e10  test    rbx, rbx
0x180012e13  jz      short loc_180012E20
0x180012e15  mov     [rax], r13b
0x180012e18  add     rax, rdi
0x180012e1b  sub     rbx, rdi
0x180012e1e  jnz     short loc_180012E15
0x180012e20  mov     eax, edi
0x180012e22  jmp     loc_18001305B
0x180012e27  lea     rdx, [rsp+150h+var_108]
0x180012e2c  lea     rcx, [rsp+150h+pszDest]
0x180012e31  call    cs:__imp_SystemFunction006
0x180012e37  mov     ecx, eax
0x180012e39  test    eax, eax
0x180012e3b  jns     short loc_180012E69
0x180012e3d  lea     rax, [rsp+150h+pszDest]
0x180012e42  inc     rbx
0x180012e45  cmp     [rax+rbx], r13b
0x180012e49  jnz     short loc_180012E42
0x180012e4b  lea     rax, [rsp+150h+pszDest]
0x180012e50  test    rbx, rbx
0x180012e53  jz      loc_180012D4B
0x180012e59  mov     [rax], r13b
0x180012e5c  add     rax, rdi
0x180012e5f  sub     rbx, rdi
0x180012e62  jnz     short loc_180012E59
0x180012e64  jmp     loc_180012D4B
0x180012e69  mov     r8, [rsp+150h+var_120]
0x180012e6e  lea     rcx, [rsp+150h+var_108]
0x180012e73  mov     rdx, r14
0x180012e76  call    cs:__imp_SystemFunction016
0x180012e7c  mov     ecx, eax
0x180012e7e  test    eax, eax
0x180012e80  jns     short loc_180012EBA
0x180012e82  lea     rax, [rsp+150h+pszDest]
0x180012e87  inc     rbx
0x180012e8a  cmp     [rax+rbx], r13b
0x180012e8e  jnz     short loc_180012E87
0x180012e90  lea     rax, [rsp+150h+pszDest]
0x180012e95  test    rbx, rbx
0x180012e98  jz      short loc_180012EA5
0x180012e9a  mov     [rax], r13b
0x180012e9d  add     rax, rdi
0x180012ea0  sub     rbx, rdi
0x180012ea3  jnz     short loc_180012E9A
0x180012ea5  lea     rax, [rsp+150h+var_108]
0x180012eaa  mov     [rax], r13b
0x180012ead  add     rax, rdi
0x180012eb0  sub     rsi, rdi
0x180012eb3  jnz     short loc_180012EAA
0x180012eb5  jmp     loc_180012D4B
0x180012eba  mov     rcx, rsi
0x180012ebd  lea     rax, [rsp+150h+var_108]
0x180012ec2  mov     [rax], r13b
0x180012ec5  add     rax, rdi
0x180012ec8  sub     rcx, rdi
0x180012ecb  jnz     short loc_180012EC2
0x180012ecd  jmp     short loc_180012ED2
0x180012ecf  xor     r13d, r13d
0x180012ed2  mov     rdx, r15; Source
0x180012ed5  lea     rcx, [rsp+150h+Destination]; Destination
0x180012eda  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180012ee0  test    al, al
0x180012ee2  jz      loc_180013056
0x180012ee8  lea     rdx, [rsp+150h+var_F8]
0x180012eed  lea     rcx, [rsp+150h+Destination]
0x180012ef2  call    cs:__imp_SystemFunction007
0x180012ef8  mov     ebx, eax
0x180012efa  test    eax, eax
0x180012efc  jns     short loc_180012F2A
0x180012efe  movzx   ecx, [rsp+150h+Destination.Length]
0x180012f03  mov     rdx, [rsp+150h+Destination.Buffer]
0x180012f08  test    rcx, rcx
0x180012f0b  jz      short loc_180012F18
0x180012f0d  mov     [rdx], r13b
0x180012f10  add     rdx, rdi
0x180012f13  sub     rcx, rdi
0x180012f16  jnz     short loc_180012F0D
0x180012f18  lea     rcx, [rsp+150h+Destination]; UnicodeString
0x180012f1d  call    cs:__imp_RtlFreeUnicodeString
0x180012f23  mov     eax, ebx
0x180012f25  jmp     loc_18001305B
0x180012f2a  mov     r8, [rsp+150h+var_118]
0x180012f2f  lea     rcx, [rsp+150h+var_F8]
0x180012f34  mov     rdx, r14
0x180012f37  call    cs:__imp_SystemFunction018
0x180012f3d  mov     ebx, eax
0x180012f3f  test    eax, eax
0x180012f41  jns     short loc_180012F7A
0x180012f43  movzx   ecx, [rsp+150h+Destination.Length]
0x180012f48  mov     rdx, [rsp+150h+Destination.Buffer]
0x180012f4d  test    rcx, rcx
0x180012f50  jz      short loc_180012F5D
0x180012f52  mov     [rdx], r13b
0x180012f55  add     rdx, rdi
0x180012f58  sub     rcx, rdi
0x180012f5b  jnz     short loc_180012F52
0x180012f5d  lea     rcx, [rsp+150h+Destination]; UnicodeString
0x180012f62  call    cs:__imp_RtlFreeUnicodeString
0x180012f68  lea     rax, [rsp+150h+var_F8]
0x180012f6d  mov     [rax], r13b
0x180012f70  add     rax, rdi
0x180012f73  sub     rsi, rdi
0x180012f76  jnz     short loc_180012F6D
0x180012f78  jmp     short loc_180012F23
0x180012f7a  mov     rcx, rsi
0x180012f7d  lea     rax, [rsp+150h+var_F8]
0x180012f82  mov     [rax], r13b
0x180012f85  add     rax, rdi
0x180012f88  sub     rcx, rdi
0x180012f8b  jnz     short loc_180012F82
0x180012f8d  mov     rdx, r12; Source
0x180012f90  lea     rcx, [rsp+150h+Destination]; Destination
0x180012f95  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180012f9b  test    al, al
0x180012f9d  jz      loc_180013056
0x180012fa3  lea     rdx, [rsp+150h+var_F8]
0x180012fa8  lea     rcx, [rsp+150h+Destination]
0x180012fad  call    cs:__imp_SystemFunction007
0x180012fb3  mov     ebx, eax
0x180012fb5  test    eax, eax
0x180012fb7  jns     short loc_180012FDC
0x180012fb9  movzx   ecx, [rsp+150h+Destination.Length]
0x180012fbe  mov     rdx, [rsp+150h+Destination.Buffer]
0x180012fc3  test    rcx, rcx
0x180012fc6  jz      loc_180012F18
0x180012fcc  mov     [rdx], r13b
0x180012fcf  add     rdx, rdi
0x180012fd2  sub     rcx, rdi
0x180012fd5  jnz     short loc_180012FCC
0x180012fd7  jmp     loc_180012F18
0x180012fdc  mov     r8, [rsp+150h+var_110]
0x180012fe1  lea     rcx, [rsp+150h+var_F8]
0x180012fe6  mov     rdx, r14
0x180012fe9  call    cs:__imp_SystemFunction018
0x180012fef  mov     ebx, eax
0x180012ff1  test    eax, eax
0x180012ff3  jns     short loc_180013024
0x180012ff5  movzx   ecx, [rsp+150h+Destination.Length]
0x180012ffa  mov     rdx, [rsp+150h+Destination.Buffer]
0x180012fff  test    rcx, rcx
  ... truncated ...
```
