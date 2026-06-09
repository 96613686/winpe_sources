# W3_CONTEXT::GetServerVariable(char const *,char const * *,ulong *)

- ea: `0x180020860`
- end: `0x180020b43`
- name: `?GetServerVariable@W3_CONTEXT@@UEAAJPEBDPEAPEBDPEAK@Z`
- size: `739`
- prototype: `int(W3_CONTEXT *__hidden this, const char *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18000ff90`
- `0x180010240`
- `0x180020860`
- `0x1800343b2`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!strchr` at `0x180020abc`
- `msvcrt!strchr` at `0x180020abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209d9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800209cd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020a3d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800209cd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020a3d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180020a75`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180020a75`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180020b14`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180020b14`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180020a9c`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180020a9c`

## pseudocode

```c
int __fastcall W3_CONTEXT::GetServerVariable(W3_CONTEXT *this, const char *a2, const char **a3, __int64 a4)
{
  _DWORD *v4; // r14
  const WCHAR *v8; // r8
  unsigned int v9; // r11d
  __int64 v10; // r12
  unsigned int i; // edx
  const char *v12; // rcx
  const char *v13; // rsi
  int v14; // eax
  int v15; // r10d
  int result; // eax
  unsigned int v17; // eax
  int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax
  const char *v20; // rbx
  int v21; // eax
  int v22; // eax
  int v23; // ebx
  const char *j; // rcx
  char *v25; // rax
  const char *v26; // rdx
  const char *Header; // rax
  unsigned __int16 v28[2]; // [rsp+40h] [rbp-69h] BYREF
  int v29; // [rsp+44h] [rbp-65h] BYREF
  LPCWCH lpWideCharStr; // [rsp+48h] [rbp-61h] BYREF
  int (*v31)(struct W3_CONTEXT *, const char **, unsigned int *); // [rsp+50h] [rbp-59h] BYREF
  int (*v32)(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *); // [rsp+58h] [rbp-51h] BYREF
  _BYTE v33[32]; // [rsp+60h] [rbp-49h] BYREF
  const char *v34; // [rsp+80h] [rbp-29h]
  char v35[32]; // [rsp+98h] [rbp-11h] BYREF

  v4 = (_DWORD *)a4;
  lpWideCharStr = 0;
  v29 = 0;
  v8 = 0;
  LODWORD(a4) = 0;
  if ( !a2 || !a3 || !v4 )
    return -2147024809;
  v9 = *((_DWORD *)this + 2268);
  if ( !v9 )
    goto LABEL_15;
  v10 = *((_QWORD *)this + 1132);
  for ( i = 0; i < v9; ++i )
  {
    v12 = *(const char **)(*(_QWORD *)(v10 + 32) + 8LL * i);
    v13 = (const char *)(a2 - v12);
    do
    {
      v14 = (unsigned __int8)v13[(_QWORD)v12];
      v15 = *(unsigned __int8 *)v12 - v14;
      if ( v15 )
        break;
      ++v12;
    }
    while ( v14 );
    if ( !v15 )
    {
      a4 = -1;
      v8 = *(const WCHAR **)(*(_QWORD *)(*((_QWORD *)this + 1133) + 32LL) + 8LL * i);
      lpWideCharStr = v8;
      do
        ++a4;
      while ( v8[a4] );
      v29 = a4;
    }
  }
  if ( !v8 )
  {
LABEL_15:
    v32 = 0;
    v31 = 0;
    result = SERVERVAR_HASH::GetFunction(a2, &v32, &v31);
    if ( result < 0 )
      return result;
    if ( v31 )
      return ((__int64 (__fastcall *)(W3_CONTEXT *, const char **, _DWORD *))v31)(this, a3, v4);
    if ( v32 )
    {
      result = ((__int64 (__fastcall *)(W3_CONTEXT *, LPCWCH *, int *))v32)(this, &lpWideCharStr, &v29);
      if ( result < 0 )
        return result;
      v8 = lpWideCharStr;
      LODWORD(a4) = v29;
      goto LABEL_21;
    }
    v28[0] = 0;
    STRA::STRA((STRA *)v33, v35, 0x20u);
    if ( !strncmp_0(a2, "HTTP_", 5u) )
    {
      v23 = STRA::Copy((STRA *)v33, a2 + 5);
      if ( v23 < 0 )
      {
LABEL_42:
        STRA::~STRA((STRA *)v33);
        return v23;
      }
      for ( j = v34; ; j = v25 + 1 )
      {
        v25 = strchr(j, 95);
        if ( !v25 )
          break;
        *v25 = 45;
      }
      v26 = v34;
    }
    else
    {
      if ( strncmp_0(a2, "HEADER_", 7u) )
        goto LABEL_41;
      v26 = a2 + 7;
    }
    Header = W3_REQUEST::GetHeader(*((W3_REQUEST **)this + 6), v26, v28);
    *a3 = Header;
    if ( Header )
    {
      v23 = 0;
      *v4 = v28[0];
      goto LABEL_42;
    }
LABEL_41:
    v23 = -2147023483;
    goto LABEL_42;
  }
LABEL_21:
  if ( !(_DWORD)a4 )
  {
    v22 = 0;
    v20 = dword_1800395E4;
    goto LABEL_30;
  }
  v17 = WideCharToMultiByte(0, 0x400u, v8, a4 + 1, 0, 0, 0, 0);
  cbMultiByte = v17;
  if ( v17 )
  {
    lpMultiByteStr = (CHAR *)(*(__int64 (__fastcall **)(W3_CONTEXT *, _QWORD))(*(_QWORD *)this + 144LL))(this, v17);
    v20 = lpMultiByteStr;
    if ( !lpMultiByteStr )
      return -2147024888;
    v21 = WideCharToMultiByte(0, 0x400u, lpWideCharStr, v29 + 1, lpMultiByteStr, cbMultiByte, 0, 0);
    if ( v21 )
    {
      v22 = v21 - 1;
LABEL_30:
      *a3 = v20;
      *v4 = v22;
      return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180020860  push    rbp
0x180020862  push    rbx
0x180020863  push    rsi
0x180020864  push    rdi
0x180020865  push    r12
0x180020867  push    r13
0x180020869  push    r14
0x18002086b  push    r15
0x18002086d  lea     rbp, [rsp-1Fh]
0x180020872  sub     rsp, 0C8h
0x180020879  mov     rax, cs:__security_cookie
0x180020880  xor     rax, rsp
0x180020883  mov     [rbp+57h+var_48], rax
0x180020887  xor     r13d, r13d
0x18002088a  mov     r14, r9
0x18002088d  mov     [rbp+57h+lpWideCharStr], r13
0x180020891  mov     r15, r8
0x180020894  mov     [rbp+57h+var_BC], r13d
0x180020898  mov     rbx, rdx
0x18002089b  mov     rdi, rcx
0x18002089e  mov     r8d, r13d
0x1800208a1  mov     r9d, r13d
0x1800208a4  test    rdx, rdx
0x1800208a7  jz      loc_180020B1E
0x1800208ad  test    r15, r15
0x1800208b0  jz      loc_180020B1E
0x1800208b6  test    r14, r14
0x1800208b9  jz      loc_180020B1E
0x1800208bf  mov     r11d, [rcx+2370h]
0x1800208c6  test    r11d, r11d
0x1800208c9  jz      short loc_180020939
0x1800208cb  mov     r12, [rcx+2360h]
0x1800208d2  mov     edx, r13d
0x1800208d5  mov     rax, [r12+20h]
0x1800208da  mov     rsi, rbx
0x1800208dd  mov     r13d, edx
0x1800208e0  mov     rcx, [rax+r13*8]
0x1800208e4  sub     rsi, rcx
0x1800208e7  movzx   r10d, byte ptr [rcx]
0x1800208eb  movzx   eax, byte ptr [rcx+rsi]
0x1800208ef  sub     r10d, eax
0x1800208f2  jnz     short loc_1800208FB
0x1800208f4  inc     rcx
0x1800208f7  test    eax, eax
0x1800208f9  jnz     short loc_1800208E7
0x1800208fb  test    r10d, r10d
0x1800208fe  jnz     short loc_18002092A
0x180020900  mov     rax, [rdi+2368h]
0x180020907  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002090b  mov     rcx, [rax+20h]
0x18002090f  mov     r8, [rcx+r13*8]
0x180020913  xor     r13d, r13d
0x180020916  mov     [rbp+57h+lpWideCharStr], r8
0x18002091a  inc     r9
0x18002091d  cmp     [r8+r9*2], r13w
0x180020922  jnz     short loc_18002091A
0x180020924  mov     [rbp+57h+var_BC], r9d
0x180020928  jmp     short loc_18002092D
0x18002092a  xor     r13d, r13d
0x18002092d  inc     edx
0x18002092f  cmp     edx, r11d
0x180020932  jb      short loc_1800208D5
0x180020934  test    r8, r8
0x180020937  jnz     short loc_1800209A2
0x180020939  lea     r8, [rbp+57h+var_B0]; int (**)(struct W3_CONTEXT *, const char **, unsigned int *)
0x18002093d  mov     [rbp+57h+var_A8], r13
0x180020941  lea     rdx, [rbp+57h+var_A8]; int (**)(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)
0x180020945  mov     [rbp+57h+var_B0], r13
0x180020949  mov     rcx, rbx; char *
0x18002094c  call    ?GetFunction@SERVERVAR_HASH@@SAJPEBDPEAP6AJPEAVW3_CONTEXT@@PEAPEBGPEAK@ZPEAP6AJ1PEAPEBD3@Z@Z; SERVERVAR_HASH::GetFunction(char const *,long (**)(W3_CONTEXT *,ushort const * *,ulong *),long (**)(W3_CONTEXT *,char const * *,ulong *))
0x180020951  test    eax, eax
0x180020953  js      loc_180020B23
0x180020959  mov     rax, [rbp+57h+var_B0]
0x18002095d  test    rax, rax
0x180020960  jz      short loc_180020975
0x180020962  mov     r8, r14
0x180020965  mov     rdx, r15
0x180020968  mov     rcx, rdi
0x18002096b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020970  jmp     loc_180020B23
0x180020975  mov     rax, [rbp+57h+var_A8]
0x180020979  test    rax, rax
0x18002097c  jz      loc_180020A62
0x180020982  lea     r8, [rbp+57h+var_BC]
0x180020986  mov     rcx, rdi
0x180020989  lea     rdx, [rbp+57h+lpWideCharStr]
0x18002098d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020992  test    eax, eax
0x180020994  js      loc_180020B23
0x18002099a  mov     r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x18002099e  mov     r9d, [rbp+57h+var_BC]
0x1800209a2  test    r9d, r9d
0x1800209a5  jz      loc_180020A4B
0x1800209ab  mov     [rsp+100h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800209b0  mov     r12d, 400h
0x1800209b6  mov     [rsp+100h+lpDefaultChar], r13; lpDefaultChar
0x1800209bb  mov     edx, r12d; dwFlags
0x1800209be  mov     [rsp+100h+cbMultiByte], r13d; cbMultiByte
0x1800209c3  inc     r9d; cchWideChar
0x1800209c6  xor     ecx, ecx; CodePage
0x1800209c8  mov     [rsp+100h+lpMultiByteStr], r13; lpMultiByteStr
0x1800209cd  call    cs:__imp_WideCharToMultiByte
0x1800209d3  mov     esi, eax
0x1800209d5  test    eax, eax
0x1800209d7  jnz     short loc_1800209F4
0x1800209d9  call    cs:__imp_GetLastError
0x1800209df  test    eax, eax
0x1800209e1  jle     loc_180020B23
0x1800209e7  movzx   eax, ax
0x1800209ea  or      eax, 80070000h
0x1800209ef  jmp     loc_180020B23
0x1800209f4  mov     rax, [rdi]
0x1800209f7  mov     edx, esi
0x1800209f9  mov     rcx, rdi
0x1800209fc  mov     rax, [rax+90h]
0x180020a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a08  mov     rbx, rax
0x180020a0b  test    rax, rax
0x180020a0e  jnz     short loc_180020A1A
0x180020a10  mov     eax, 80070008h
0x180020a15  jmp     loc_180020B23
0x180020a1a  mov     r9d, [rbp+57h+var_BC]
0x180020a1e  mov     edx, r12d; dwFlags
0x180020a21  mov     r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x180020a25  inc     r9d; cchWideChar
0x180020a28  mov     [rsp+100h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180020a2d  xor     ecx, ecx; CodePage
0x180020a2f  mov     [rsp+100h+lpDefaultChar], r13; lpDefaultChar
0x180020a34  mov     [rsp+100h+cbMultiByte], esi; cbMultiByte
0x180020a38  mov     [rsp+100h+lpMultiByteStr], rax; lpMultiByteStr
0x180020a3d  call    cs:__imp_WideCharToMultiByte
0x180020a43  test    eax, eax
0x180020a45  jz      short loc_1800209D9
0x180020a47  dec     eax
0x180020a49  jmp     short loc_180020A55
0x180020a4b  mov     eax, r13d
0x180020a4e  lea     rbx, dword_1800395E4
0x180020a55  mov     [r15], rbx
0x180020a58  mov     [r14], eax
0x180020a5b  xor     eax, eax
0x180020a5d  jmp     loc_180020B23
0x180020a62  mov     r8d, 20h ; ' '
0x180020a68  mov     [rbp+57h+var_C0], r13w
0x180020a6d  lea     rdx, [rbp+57h+var_68]
0x180020a71  lea     rcx, [rbp+57h+var_A0]
0x180020a75  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180020a7b  mov     r8d, 5; MaxCount
0x180020a81  lea     rdx, aHttp; "HTTP_"
0x180020a88  mov     rcx, rbx; Str1
0x180020a8b  call    strncmp_0
0x180020a90  test    eax, eax
0x180020a92  jnz     short loc_180020ACD
0x180020a94  lea     rdx, [rbx+5]
0x180020a98  lea     rcx, [rbp+57h+var_A0]
0x180020a9c  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180020aa2  mov     ebx, eax
0x180020aa4  test    eax, eax
0x180020aa6  js      short loc_180020B10
0x180020aa8  mov     rcx, [rbp+57h+var_80]
0x180020aac  mov     ebx, 5Fh ; '_'
0x180020ab1  jmp     short loc_180020ABA
0x180020ab3  mov     byte ptr [rax], 2Dh ; '-'
0x180020ab6  lea     rcx, [rax+1]; Str
0x180020aba  mov     edx, ebx; Val
0x180020abc  call    cs:__imp_strchr
0x180020ac2  test    rax, rax
0x180020ac5  jnz     short loc_180020AB3
0x180020ac7  mov     rdx, [rbp+57h+var_80]
0x180020acb  jmp     short loc_180020AEA
0x180020acd  mov     r8d, 7; MaxCount
0x180020ad3  lea     rdx, aHeader; "HEADER_"
0x180020ada  mov     rcx, rbx; Str1
0x180020add  call    strncmp_0
0x180020ae2  test    eax, eax
0x180020ae4  jnz     short loc_180020B0B
0x180020ae6  lea     rdx, [rbx+7]; char *
0x180020aea  mov     rcx, [rdi+30h]; this
0x180020aee  lea     r8, [rbp+57h+var_C0]; unsigned __int16 *
0x180020af2  call    ?GetHeader@W3_REQUEST@@QEBAPEBDPEBDPEAG@Z; W3_REQUEST::GetHeader(char const *,ushort *)
0x180020af7  mov     [r15], rax
0x180020afa  test    rax, rax
0x180020afd  jz      short loc_180020B0B
0x180020aff  movzx   eax, [rbp+57h+var_C0]
0x180020b03  mov     ebx, r13d
0x180020b06  mov     [r14], eax
0x180020b09  jmp     short loc_180020B10
0x180020b0b  mov     ebx, 80070585h
0x180020b10  lea     rcx, [rbp+57h+var_A0]
0x180020b14  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180020b1a  mov     eax, ebx
0x180020b1c  jmp     short loc_180020B23
0x180020b1e  mov     eax, 80070057h
0x180020b23  mov     rcx, [rbp+57h+var_48]
0x180020b27  xor     rcx, rsp; StackCookie
0x180020b2a  call    __security_check_cookie
0x180020b2f  add     rsp, 0C8h
0x180020b36  pop     r15
0x180020b38  pop     r14
0x180020b3a  pop     r13
0x180020b3c  pop     r12
0x180020b3e  pop     rdi
0x180020b3f  pop     rsi
0x180020b40  pop     rbx
0x180020b41  pop     rbp
0x180020b42  retn
```
