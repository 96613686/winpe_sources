# W3_CONTEXT::SetServerVariable(char const *,ushort const *)

- ea: `0x180022a40`
- end: `0x180022e0d`
- name: `?SetServerVariable@W3_CONTEXT@@UEAAJPEBDPEBG@Z`
- size: `973`
- prototype: `__int64 __fastcall(W3_REQUEST **this, const char *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180010444`
- `0x180019558`
- `0x180022a40`
- `0x180028230`
- `0x180034382`
- `0x18003438e`
- `0x1800343b2`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!strchr` at `0x180022aec`
- `msvcrt!strchr` at `0x180022aec`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180022d9b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180022dbd`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180022d9b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180022dbd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022a84`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022b42`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022a84`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180022b42`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022b61`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022ca0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022cb6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022e00`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022b61`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022ca0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022cb6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022e00`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180022ac7`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180022ac7`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180022b50`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180022b50`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::SetServerVariable(W3_REQUEST **this, const char *a2, const unsigned __int16 *a3)
{
  int v6; // esi
  char *i; // rcx
  char *v8; // rax
  char *v9; // rdi
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // r15
  __int64 v13; // rax
  size_t v14; // r12
  unsigned __int16 *v15; // rax
  const unsigned __int16 *v16; // rsi
  unsigned int v17; // r8d
  unsigned int v18; // esi
  __int64 v19; // r12
  unsigned __int8 **v20; // r10
  unsigned __int8 *v21; // rax
  int v22; // ecx
  int v23; // edx
  int v25; // esi
  __int64 v26; // rcx
  void *v27; // rax
  void *v28; // rsi
  _BYTE v29[32]; // [rsp+30h] [rbp-D0h] BYREF
  char *v30; // [rsp+50h] [rbp-B0h]
  _BYTE v31[32]; // [rsp+68h] [rbp-98h] BYREF
  char *v32; // [rsp+88h] [rbp-78h]
  unsigned __int16 v33; // [rsp+98h] [rbp-68h]
  char v34[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v35[64]; // [rsp+C0h] [rbp-40h] BYREF

  STRA::STRA((STRA *)v29, v34, 0x20u);
  if ( !a2 )
  {
    v6 = -2147024809;
LABEL_37:
    STRA::~STRA((STRA *)v29);
    return (unsigned int)v6;
  }
  if ( *a2 == 72 )
  {
    if ( !strncmp_0(a2, "HTTP_", 5u) )
    {
      v6 = STRA::Copy((STRA *)v29, a2 + 5);
      if ( v6 < 0 )
        goto LABEL_37;
      for ( i = v30; ; i = v8 + 1 )
      {
        v8 = strchr(i, 95);
        if ( !v8 )
          break;
        *v8 = 45;
      }
      v9 = v30;
LABEL_12:
      if ( a3 )
      {
        STRA::STRA((STRA *)v31, v35, 0x40u);
        v6 = STRA::CopyWToUTF8Unescaped((STRA *)v31, a3);
        if ( v6 >= 0 )
          v6 = W3_REQUEST::SetHeader(this[6], v9, v32, v33, 1);
        STRA::~STRA((STRA *)v31);
      }
      else
      {
        v6 = W3_REQUEST::DeleteHeader(this[6], v9);
      }
      goto LABEL_37;
    }
    if ( !strncmp_0(a2, "HEADER_", 7u) )
    {
      v9 = (char *)(a2 + 7);
      goto LABEL_12;
    }
  }
  ++*((_DWORD *)this + 2269);
  if ( !this[1132] )
  {
    v10 = operator new(0x30u);
    if ( !v10 )
    {
      this[1132] = 0;
      goto LABEL_39;
    }
    *v10 = 0;
    v10[4] = v10;
    *((_DWORD *)v10 + 10) = 32;
    *((_WORD *)v10 + 22) = 256;
    this[1132] = (W3_REQUEST *)v10;
  }
  if ( !this[1133] )
  {
    v11 = operator new(0x30u);
    if ( !v11 )
    {
      this[1133] = 0;
      goto LABEL_39;
    }
    *v11 = 0;
    v11[4] = v11;
    *((_DWORD *)v11 + 10) = 32;
    *((_WORD *)v11 + 22) = 256;
    this[1133] = (W3_REQUEST *)v11;
  }
  v12 = -1;
  if ( !a3 )
    goto LABEL_28;
  v13 = -1;
  do
    ++v13;
  while ( a3[v13] );
  v14 = 2 * v13 + 2;
  v15 = (unsigned __int16 *)(*((__int64 (__fastcall **)(W3_REQUEST **, _QWORD))*this + 18))(this, (unsigned int)v14);
  v16 = v15;
  if ( !v15 )
  {
LABEL_39:
    STRA::~STRA((STRA *)v29);
    return 2147942408LL;
  }
  memcpy_0(v15, a3, v14);
  a3 = v16;
LABEL_28:
  v17 = *((_DWORD *)this + 2268);
  if ( v17 )
  {
    v18 = 0;
    while ( 1 )
    {
      v19 = v18;
      v20 = (unsigned __int8 **)(*((_QWORD *)this[1132] + 4) + 8LL * v18);
      v21 = *v20;
      do
      {
        v22 = v21[a2 - (const char *)*v20];
        v23 = *v21 - v22;
        if ( v23 )
          break;
        ++v21;
      }
      while ( v22 );
      if ( !v23 )
        break;
      if ( ++v18 >= v17 )
        goto LABEL_35;
    }
    if ( a3 )
    {
      *(_QWORD *)(*((_QWORD *)this[1133] + 4) + 8LL * v18) = a3;
    }
    else
    {
      v25 = ~v18;
      memmove_0(v20, v20 + 1, 8LL * (v25 + v17));
      v26 = *((_QWORD *)this[1133] + 4) + 8 * v19;
      memmove_0((void *)v26, (const void *)(v26 + 8), 8LL * (unsigned int)(v25 + *((_DWORD *)this + 2268)));
      --*((_DWORD *)this + 2268);
    }
    goto LABEL_36;
  }
LABEL_35:
  if ( !a3 )
  {
LABEL_36:
    v6 = 0;
    goto LABEL_37;
  }
  do
    ++v12;
  while ( a2[v12] );
  v27 = (void *)(*((__int64 (__fastcall **)(W3_REQUEST **, _QWORD))*this + 18))(this, (unsigned int)(v12 + 1));
  v28 = v27;
  if ( !v27 )
    goto LABEL_39;
  memcpy_0(v27, a2, v12 + 1);
  if ( !BUFFER::Resize(this[1132], 8 * *((_DWORD *)this + 2268) + 8)
    || !BUFFER::Resize(this[1133], 8 * *((_DWORD *)this + 2268) + 8) )
  {
    goto LABEL_39;
  }
  *(_QWORD *)(*((_QWORD *)this[1132] + 4) + 8LL * *((unsigned int *)this + 2268)) = v28;
  *(_QWORD *)(*((_QWORD *)this[1133] + 4) + 8LL * (unsigned int)(*((_DWORD *)this + 2268))++) = a3;
  STRA::~STRA((STRA *)v29);
  return 0;
}

```

## disassembly

```asm
0x180022a40  mov     [rsp-8+arg_18], rbx
0x180022a45  push    rbp
0x180022a46  push    rsi
0x180022a47  push    rdi
0x180022a48  push    r12
0x180022a4a  push    r13
0x180022a4c  push    r14
0x180022a4e  push    r15
0x180022a50  lea     rbp, [rsp-10h]
0x180022a55  sub     rsp, 110h
0x180022a5c  mov     rax, cs:__security_cookie
0x180022a63  xor     rax, rsp
0x180022a66  mov     [rbp+40h+var_40], rax
0x180022a6a  mov     r14, r8
0x180022a6d  mov     rdi, rdx
0x180022a70  mov     rbx, rcx
0x180022a73  lea     rdx, [rbp+40h+var_A0]
0x180022a77  mov     esi, 20h ; ' '
0x180022a7c  lea     rcx, [rsp+140h+var_110]
0x180022a81  mov     r8d, esi
0x180022a84  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180022a8a  xor     r13d, r13d
0x180022a8d  test    rdi, rdi
0x180022a90  jnz     short loc_180022A9C
0x180022a92  mov     esi, 80070057h
0x180022a97  jmp     loc_180022C9B
0x180022a9c  cmp     byte ptr [rdi], 48h ; 'H'
0x180022a9f  jnz     loc_180022B8D
0x180022aa5  mov     r8d, 5; MaxCount
0x180022aab  lea     rdx, aHttp; "HTTP_"
0x180022ab2  mov     rcx, rdi; Str1
0x180022ab5  call    strncmp_0
0x180022aba  test    eax, eax
0x180022abc  jnz     short loc_180022AFE
0x180022abe  lea     rdx, [rdi+5]
0x180022ac2  lea     rcx, [rsp+140h+var_110]
0x180022ac7  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180022acd  mov     esi, eax
0x180022acf  test    eax, eax
0x180022ad1  js      loc_180022C9B
0x180022ad7  mov     rcx, [rsp+140h+var_F0]
0x180022adc  mov     edi, 5Fh ; '_'
0x180022ae1  jmp     short loc_180022AEA
0x180022ae3  mov     byte ptr [rax], 2Dh ; '-'
0x180022ae6  lea     rcx, [rax+1]; Str
0x180022aea  mov     edx, edi; Val
0x180022aec  call    cs:__imp_strchr
0x180022af2  test    rax, rax
0x180022af5  jnz     short loc_180022AE3
0x180022af7  mov     rdi, [rsp+140h+var_F0]
0x180022afc  jmp     short loc_180022B1B
0x180022afe  mov     r8d, 7; MaxCount
0x180022b04  lea     rdx, aHeader; "HEADER_"
0x180022b0b  mov     rcx, rdi; Str1
0x180022b0e  call    strncmp_0
0x180022b13  test    eax, eax
0x180022b15  jnz     short loc_180022B8D
0x180022b17  add     rdi, 7
0x180022b1b  test    r14, r14
0x180022b1e  jnz     short loc_180022B33
0x180022b20  mov     rcx, [rbx+30h]; this
0x180022b24  mov     rdx, rdi; char *
0x180022b27  call    ?DeleteHeader@W3_REQUEST@@QEAAJPEBD@Z; W3_REQUEST::DeleteHeader(char const *)
0x180022b2c  mov     esi, eax
0x180022b2e  jmp     loc_180022C9B
0x180022b33  mov     r8d, 40h ; '@'
0x180022b39  lea     rdx, [rbp+40h+var_80]
0x180022b3d  lea     rcx, [rsp+140h+var_D8]
0x180022b42  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180022b48  mov     rdx, r14
0x180022b4b  lea     rcx, [rsp+140h+var_D8]
0x180022b50  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180022b56  mov     esi, eax
0x180022b58  test    eax, eax
0x180022b5a  jns     short loc_180022B6C
0x180022b5c  lea     rcx, [rsp+140h+var_D8]
0x180022b61  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180022b67  jmp     loc_180022C9B
0x180022b6c  movzx   r9d, [rbp+40h+var_A8]; unsigned __int16
0x180022b71  mov     rdx, rdi; char *
0x180022b74  mov     r8, [rbp+40h+var_B8]; char *
0x180022b78  mov     rcx, [rbx+30h]; this
0x180022b7c  mov     [rsp+140h+var_120], 1; int
0x180022b84  call    ?SetHeader@W3_REQUEST@@QEAAJPEBD0GH@Z; W3_REQUEST::SetHeader(char const *,char const *,ushort,int)
0x180022b89  mov     esi, eax
0x180022b8b  jmp     short loc_180022B5C
0x180022b8d  inc     dword ptr [rbx+2374h]
0x180022b93  mov     r15d, 30h ; '0'
0x180022b99  cmp     [rbx+2360h], r13
0x180022ba0  jnz     short loc_180022BCA
0x180022ba2  mov     ecx, r15d; Size
0x180022ba5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022baa  test    rax, rax
0x180022bad  jz      loc_180022CAA
0x180022bb3  mov     [rax], r13
0x180022bb6  mov     [rax+20h], rax
0x180022bba  mov     [rax+28h], esi
0x180022bbd  mov     word ptr [rax+2Ch], 100h
0x180022bc3  mov     [rbx+2360h], rax
0x180022bca  cmp     [rbx+2368h], r13
0x180022bd1  jnz     short loc_180022BFB
0x180022bd3  mov     rcx, r15; Size
0x180022bd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022bdb  test    rax, rax
0x180022bde  jz      loc_180022CE8
0x180022be4  mov     [rax], r13
0x180022be7  mov     [rax+20h], rax
0x180022beb  mov     [rax+28h], esi
0x180022bee  mov     word ptr [rax+2Ch], 100h
0x180022bf4  mov     [rbx+2368h], rax
0x180022bfb  or      r15, 0FFFFFFFFFFFFFFFFh
0x180022bff  test    r14, r14
0x180022c02  jz      short loc_180022C47
0x180022c04  mov     rax, r15
0x180022c07  inc     rax
0x180022c0a  cmp     [r14+rax*2], r13w
0x180022c0f  jnz     short loc_180022C07
0x180022c11  lea     r12, ds:2[rax*2]
0x180022c19  mov     rcx, rbx
0x180022c1c  mov     rax, [rbx]
0x180022c1f  mov     edx, r12d
0x180022c22  mov     rax, [rax+90h]
0x180022c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c2e  mov     rsi, rax
0x180022c31  test    rax, rax
0x180022c34  jz      short loc_180022CB1
0x180022c36  mov     r8, r12; Size
0x180022c39  mov     rdx, r14; Src
0x180022c3c  mov     rcx, rax; void *
0x180022c3f  call    memcpy_0
0x180022c44  mov     r14, rsi
0x180022c47  mov     r8d, [rbx+2370h]
0x180022c4e  test    r8d, r8d
0x180022c51  jz      short loc_180022C8F
0x180022c53  mov     rax, [rbx+2360h]
0x180022c5a  mov     esi, r13d
0x180022c5d  mov     r11, [rax+20h]
0x180022c61  mov     r12d, esi
0x180022c64  mov     r9, rdi
0x180022c67  lea     r10, [r11+r12*8]
0x180022c6b  mov     rax, [r10]
0x180022c6e  sub     r9, rax
0x180022c71  movzx   edx, byte ptr [rax]
0x180022c74  movzx   ecx, byte ptr [rax+r9]
0x180022c79  sub     edx, ecx
0x180022c7b  jnz     short loc_180022C84
0x180022c7d  inc     rax
0x180022c80  test    ecx, ecx
0x180022c82  jnz     short loc_180022C71
0x180022c84  test    edx, edx
0x180022c86  jz      short loc_180022CF1
0x180022c88  inc     esi
0x180022c8a  cmp     esi, r8d
0x180022c8d  jb      short loc_180022C61
0x180022c8f  test    r14, r14
0x180022c92  jnz     loc_180022D4D
0x180022c98  mov     esi, r13d
0x180022c9b  lea     rcx, [rsp+140h+var_110]
0x180022ca0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180022ca6  mov     eax, esi
0x180022ca8  jmp     short loc_180022CC1
0x180022caa  mov     [rbx+2360h], r13
0x180022cb1  lea     rcx, [rsp+140h+var_110]
0x180022cb6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180022cbc  mov     eax, 80070008h
0x180022cc1  mov     rcx, [rbp+40h+var_40]
0x180022cc5  xor     rcx, rsp; StackCookie
0x180022cc8  call    __security_check_cookie
0x180022ccd  mov     rbx, [rsp+140h+arg_18]
0x180022cd5  add     rsp, 110h
0x180022cdc  pop     r15
0x180022cde  pop     r14
0x180022ce0  pop     r13
0x180022ce2  pop     r12
0x180022ce4  pop     rdi
0x180022ce5  pop     rsi
0x180022ce6  pop     rbp
0x180022ce7  retn
0x180022ce8  mov     [rbx+2368h], r13
0x180022cef  jmp     short loc_180022CB1
0x180022cf1  test    r14, r14
0x180022cf4  jz      short loc_180022D07
0x180022cf6  mov     rax, [rbx+2368h]
0x180022cfd  mov     rcx, [rax+20h]
0x180022d01  mov     [rcx+r12*8], r14
0x180022d05  jmp     short loc_180022C98
0x180022d07  not     esi
0x180022d09  lea     rdx, [r10+8]; Src
0x180022d0d  add     r8d, esi
0x180022d10  mov     rcx, r10; void *
0x180022d13  shl     r8, 3; Size
0x180022d17  call    memmove_0
0x180022d1c  mov     r8d, [rbx+2370h]
0x180022d23  mov     rax, [rbx+2368h]
0x180022d2a  add     r8d, esi
0x180022d2d  shl     r8, 3; Size
0x180022d31  mov     rcx, [rax+20h]
0x180022d35  lea     rcx, [rcx+r12*8]; void *
0x180022d39  lea     rdx, [rcx+8]; Src
0x180022d3d  call    memmove_0
0x180022d42  dec     dword ptr [rbx+2370h]
0x180022d48  jmp     loc_180022C98
0x180022d4d  inc     r15
0x180022d50  cmp     [rdi+r15], r13b
0x180022d54  jnz     short loc_180022D4D
0x180022d56  mov     rax, [rbx]
0x180022d59  lea     edx, [r15+1]
0x180022d5d  mov     rcx, rbx
0x180022d60  mov     rax, [rax+90h]
0x180022d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d6c  mov     rsi, rax
0x180022d6f  test    rax, rax
0x180022d72  jz      loc_180022CB1
0x180022d78  lea     r8, [r15+1]; Size
0x180022d7c  mov     rdx, rdi; Src
0x180022d7f  mov     rcx, rax; void *
0x180022d82  call    memcpy_0
0x180022d87  mov     edx, [rbx+2370h]
0x180022d8d  mov     rcx, [rbx+2360h]
0x180022d94  lea     edx, ds:8[rdx*8]
0x180022d9b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180022da1  test    al, al
0x180022da3  jz      loc_180022CB1
0x180022da9  mov     edx, [rbx+2370h]
0x180022daf  mov     rcx, [rbx+2368h]
0x180022db6  lea     edx, ds:8[rdx*8]
0x180022dbd  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180022dc3  test    al, al
0x180022dc5  jz      loc_180022CB1
0x180022dcb  mov     rax, [rbx+2360h]
0x180022dd2  mov     edx, [rbx+2370h]
0x180022dd8  mov     rcx, [rax+20h]
0x180022ddc  mov     [rcx+rdx*8], rsi
0x180022de0  mov     rax, [rbx+2368h]
0x180022de7  mov     edx, [rbx+2370h]
0x180022ded  mov     rcx, [rax+20h]
0x180022df1  mov     [rcx+rdx*8], r14
0x180022df5  lea     rcx, [rsp+140h+var_110]
0x180022dfa  inc     dword ptr [rbx+2370h]
0x180022e00  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180022e06  xor     eax, eax
0x180022e08  jmp     loc_180022CC1
```
