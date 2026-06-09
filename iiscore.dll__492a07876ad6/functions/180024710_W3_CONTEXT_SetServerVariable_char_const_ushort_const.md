# W3_CONTEXT::SetServerVariable(char const *,ushort const *)

- ea: `0x180024710`
- end: `0x180024b28`
- name: `?SetServerVariable@W3_CONTEXT@@UEAAJPEBDPEBG@Z`
- size: `1048`
- prototype: `int(W3_CONTEXT *__hidden this, const char *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x1800111c8`
- `0x18001ab30`
- `0x180024710`
- `0x18002a430`
- `0x180037722`
- `0x18003772e`
- `0x180037752`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!strchr` at `0x1800247c8`
- `msvcrt!strchr` at `0x1800247c8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024aa4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024acc`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024aa4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024acc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024754`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024828`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024754`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180024828`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024853`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002499c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800249b8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024b15`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024853`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002499c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800249b8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180024b15`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18002479d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18002479d`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x18002483c`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x18002483c`

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
0x180024710  mov     [rsp-8+arg_18], rbx
0x180024715  push    rbp
0x180024716  push    rsi
0x180024717  push    rdi
0x180024718  push    r12
0x18002471a  push    r13
0x18002471c  push    r14
0x18002471e  push    r15
0x180024720  lea     rbp, [rsp-10h]
0x180024725  sub     rsp, 110h
0x18002472c  mov     rax, cs:__security_cookie
0x180024733  xor     rax, rsp
0x180024736  mov     [rbp+40h+var_40], rax
0x18002473a  mov     r14, r8
0x18002473d  mov     rdi, rdx
0x180024740  mov     rbx, rcx
0x180024743  lea     rdx, [rbp+40h+var_A0]
0x180024747  mov     esi, 20h ; ' '
0x18002474c  lea     rcx, [rsp+140h+var_110]
0x180024751  mov     r8d, esi
0x180024754  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002475b  nop     dword ptr [rax+rax+00h]
0x180024760  xor     r13d, r13d
0x180024763  test    rdi, rdi
0x180024766  jnz     short loc_180024772
0x180024768  mov     esi, 80070057h
0x18002476d  jmp     loc_180024997
0x180024772  cmp     byte ptr [rdi], 48h ; 'H'
0x180024775  jnz     loc_180024885
0x18002477b  mov     r8d, 5; MaxCount
0x180024781  lea     rdx, aHttp; "HTTP_"
0x180024788  mov     rcx, rdi; Str1
0x18002478b  call    strncmp_0
0x180024790  test    eax, eax
0x180024792  jnz     short loc_1800247E0
0x180024794  lea     rdx, [rdi+5]
0x180024798  lea     rcx, [rsp+140h+var_110]
0x18002479d  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800247a4  nop     dword ptr [rax+rax+00h]
0x1800247a9  mov     esi, eax
0x1800247ab  test    eax, eax
0x1800247ad  js      loc_180024997
0x1800247b3  mov     rcx, [rsp+140h+var_F0]
0x1800247b8  mov     edi, 5Fh ; '_'
0x1800247bd  jmp     short loc_1800247C6
0x1800247bf  mov     byte ptr [rax], 2Dh ; '-'
0x1800247c2  lea     rcx, [rax+1]; Str
0x1800247c6  mov     edx, edi; Val
0x1800247c8  call    cs:__imp_strchr
0x1800247cf  nop     dword ptr [rax+rax+00h]
0x1800247d4  test    rax, rax
0x1800247d7  jnz     short loc_1800247BF
0x1800247d9  mov     rdi, [rsp+140h+var_F0]
0x1800247de  jmp     short loc_180024801
0x1800247e0  mov     r8d, 7; MaxCount
0x1800247e6  lea     rdx, aHeader; "HEADER_"
0x1800247ed  mov     rcx, rdi; Str1
0x1800247f0  call    strncmp_0
0x1800247f5  test    eax, eax
0x1800247f7  jnz     loc_180024885
0x1800247fd  add     rdi, 7
0x180024801  test    r14, r14
0x180024804  jnz     short loc_180024819
0x180024806  mov     rcx, [rbx+30h]; this
0x18002480a  mov     rdx, rdi; char *
0x18002480d  call    ?DeleteHeader@W3_REQUEST@@QEAAJPEBD@Z; W3_REQUEST::DeleteHeader(char const *)
0x180024812  mov     esi, eax
0x180024814  jmp     loc_180024997
0x180024819  mov     r8d, 40h ; '@'
0x18002481f  lea     rdx, [rbp+40h+var_80]
0x180024823  lea     rcx, [rsp+140h+var_D8]
0x180024828  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002482f  nop     dword ptr [rax+rax+00h]
0x180024834  mov     rdx, r14
0x180024837  lea     rcx, [rsp+140h+var_D8]
0x18002483c  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180024843  nop     dword ptr [rax+rax+00h]
0x180024848  mov     esi, eax
0x18002484a  test    eax, eax
0x18002484c  jns     short loc_180024864
0x18002484e  lea     rcx, [rsp+140h+var_D8]
0x180024853  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002485a  nop     dword ptr [rax+rax+00h]
0x18002485f  jmp     loc_180024997
0x180024864  movzx   r9d, [rbp+40h+var_A8]; unsigned __int16
0x180024869  mov     rdx, rdi; char *
0x18002486c  mov     r8, [rbp+40h+var_B8]; char *
0x180024870  mov     rcx, [rbx+30h]; this
0x180024874  mov     [rsp+140h+var_120], 1; int
0x18002487c  call    ?SetHeader@W3_REQUEST@@QEAAJPEBD0GH@Z; W3_REQUEST::SetHeader(char const *,char const *,ushort,int)
0x180024881  mov     esi, eax
0x180024883  jmp     short loc_18002484E
0x180024885  inc     dword ptr [rbx+2374h]
0x18002488b  mov     r15d, 30h ; '0'
0x180024891  cmp     [rbx+2360h], r13
0x180024898  jnz     short loc_1800248C2
0x18002489a  mov     ecx, r15d; Size
0x18002489d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800248a2  test    rax, rax
0x1800248a5  jz      loc_1800249AC
0x1800248ab  mov     [rax], r13
0x1800248ae  mov     [rax+20h], rax
0x1800248b2  mov     [rax+28h], esi
0x1800248b5  mov     word ptr [rax+2Ch], 100h
0x1800248bb  mov     [rbx+2360h], rax
0x1800248c2  cmp     [rbx+2368h], r13
0x1800248c9  jnz     short loc_1800248F3
0x1800248cb  mov     rcx, r15; Size
0x1800248ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800248d3  test    rax, rax
0x1800248d6  jz      loc_1800249F1
0x1800248dc  mov     [rax], r13
0x1800248df  mov     [rax+20h], rax
0x1800248e3  mov     [rax+28h], esi
0x1800248e6  mov     word ptr [rax+2Ch], 100h
0x1800248ec  mov     [rbx+2368h], rax
0x1800248f3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800248f7  test    r14, r14
0x1800248fa  jz      short loc_180024943
0x1800248fc  mov     rax, r15
0x1800248ff  inc     rax
0x180024902  cmp     [r14+rax*2], r13w
0x180024907  jnz     short loc_1800248FF
0x180024909  lea     r12, ds:2[rax*2]
0x180024911  mov     rcx, rbx
0x180024914  mov     rax, [rbx]
0x180024917  mov     edx, r12d
0x18002491a  mov     rax, [rax+90h]
0x180024921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024926  mov     rsi, rax
0x180024929  test    rax, rax
0x18002492c  jz      loc_1800249B3
0x180024932  mov     r8, r12; Size
0x180024935  mov     rdx, r14; Src
0x180024938  mov     rcx, rax; void *
0x18002493b  call    memcpy_0
0x180024940  mov     r14, rsi
0x180024943  mov     r8d, [rbx+2370h]
0x18002494a  test    r8d, r8d
0x18002494d  jz      short loc_18002498B
0x18002494f  mov     rax, [rbx+2360h]
0x180024956  mov     esi, r13d
0x180024959  mov     r11, [rax+20h]
0x18002495d  mov     r12d, esi
0x180024960  mov     r9, rdi
0x180024963  lea     r10, [r11+r12*8]
0x180024967  mov     rax, [r10]
0x18002496a  sub     r9, rax
0x18002496d  movzx   edx, byte ptr [rax]
0x180024970  movzx   ecx, byte ptr [rax+r9]
0x180024975  sub     edx, ecx
0x180024977  jnz     short loc_180024980
0x180024979  inc     rax
0x18002497c  test    ecx, ecx
0x18002497e  jnz     short loc_18002496D
0x180024980  test    edx, edx
0x180024982  jz      short loc_1800249FA
0x180024984  inc     esi
0x180024986  cmp     esi, r8d
0x180024989  jb      short loc_18002495D
0x18002498b  test    r14, r14
0x18002498e  jnz     loc_180024A56
0x180024994  mov     esi, r13d
0x180024997  lea     rcx, [rsp+140h+var_110]
0x18002499c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800249a3  nop     dword ptr [rax+rax+00h]
0x1800249a8  mov     eax, esi
0x1800249aa  jmp     short loc_1800249C9
0x1800249ac  mov     [rbx+2360h], r13
0x1800249b3  lea     rcx, [rsp+140h+var_110]
0x1800249b8  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800249bf  nop     dword ptr [rax+rax+00h]
0x1800249c4  mov     eax, 80070008h
0x1800249c9  mov     rcx, [rbp+40h+var_40]
0x1800249cd  xor     rcx, rsp; StackCookie
0x1800249d0  call    __security_check_cookie
0x1800249d5  mov     rbx, [rsp+140h+arg_18]
0x1800249dd  add     rsp, 110h
0x1800249e4  pop     r15
0x1800249e6  pop     r14
0x1800249e8  pop     r13
0x1800249ea  pop     r12
0x1800249ec  pop     rdi
0x1800249ed  pop     rsi
0x1800249ee  pop     rbp
0x1800249ef  retn
0x1800249f1  mov     [rbx+2368h], r13
0x1800249f8  jmp     short loc_1800249B3
0x1800249fa  test    r14, r14
0x1800249fd  jz      short loc_180024A10
0x1800249ff  mov     rax, [rbx+2368h]
0x180024a06  mov     rcx, [rax+20h]
0x180024a0a  mov     [rcx+r12*8], r14
0x180024a0e  jmp     short loc_180024994
0x180024a10  not     esi
0x180024a12  lea     rdx, [r10+8]; Src
0x180024a16  add     r8d, esi
0x180024a19  mov     rcx, r10; void *
0x180024a1c  shl     r8, 3; Size
0x180024a20  call    memmove_0
0x180024a25  mov     r8d, [rbx+2370h]
0x180024a2c  mov     rax, [rbx+2368h]
0x180024a33  add     r8d, esi
0x180024a36  shl     r8, 3; Size
0x180024a3a  mov     rcx, [rax+20h]
0x180024a3e  lea     rcx, [rcx+r12*8]; void *
0x180024a42  lea     rdx, [rcx+8]; Src
0x180024a46  call    memmove_0
0x180024a4b  dec     dword ptr [rbx+2370h]
0x180024a51  jmp     loc_180024994
0x180024a56  inc     r15
0x180024a59  cmp     [rdi+r15], r13b
0x180024a5d  jnz     short loc_180024A56
0x180024a5f  mov     rax, [rbx]
0x180024a62  lea     edx, [r15+1]
0x180024a66  mov     rcx, rbx
0x180024a69  mov     rax, [rax+90h]
0x180024a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a75  mov     rsi, rax
0x180024a78  test    rax, rax
0x180024a7b  jz      loc_1800249B3
0x180024a81  lea     r8, [r15+1]; Size
0x180024a85  mov     rdx, rdi; Src
0x180024a88  mov     rcx, rax; void *
0x180024a8b  call    memcpy_0
0x180024a90  mov     edx, [rbx+2370h]
0x180024a96  mov     rcx, [rbx+2360h]
0x180024a9d  lea     edx, ds:8[rdx*8]
0x180024aa4  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180024aab  nop     dword ptr [rax+rax+00h]
0x180024ab0  test    al, al
0x180024ab2  jz      loc_1800249B3
0x180024ab8  mov     edx, [rbx+2370h]
0x180024abe  mov     rcx, [rbx+2368h]
0x180024ac5  lea     edx, ds:8[rdx*8]
0x180024acc  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180024ad3  nop     dword ptr [rax+rax+00h]
0x180024ad8  test    al, al
0x180024ada  jz      loc_1800249B3
0x180024ae0  mov     rax, [rbx+2360h]
0x180024ae7  mov     edx, [rbx+2370h]
0x180024aed  mov     rcx, [rax+20h]
0x180024af1  mov     [rcx+rdx*8], rsi
0x180024af5  mov     rax, [rbx+2368h]
0x180024afc  mov     edx, [rbx+2370h]
0x180024b02  mov     rcx, [rax+20h]
0x180024b06  mov     [rcx+rdx*8], r14
0x180024b0a  lea     rcx, [rsp+140h+var_110]
0x180024b0f  inc     dword ptr [rbx+2370h]
0x180024b15  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180024b1c  nop     dword ptr [rax+rax+00h]
0x180024b21  xor     eax, eax
0x180024b23  jmp     loc_1800249C9
```
