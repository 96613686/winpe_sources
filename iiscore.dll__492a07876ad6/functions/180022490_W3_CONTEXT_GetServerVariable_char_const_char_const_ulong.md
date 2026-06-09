# W3_CONTEXT::GetServerVariable(char const *,char const * *,ulong *)

- ea: `0x180022490`
- end: `0x18002279e`
- name: `?GetServerVariable@W3_CONTEXT@@UEAAJPEBDPEAPEBDPEAK@Z`
- size: `782`
- prototype: `int(W3_CONTEXT *__hidden this, const char *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180010cb0`
- `0x180010f80`
- `0x180022490`
- `0x180037752`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!strchr` at `0x18002270a`
- `msvcrt!strchr` at `0x18002270a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002260f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002260f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800225fd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022679`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800225fd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022679`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800226b7`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800226b7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022768`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180022768`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800226e4`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800226e4`

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
    v20 = dword_18003C5E4;
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
0x180022490  push    rbp
0x180022492  push    rbx
0x180022493  push    rsi
0x180022494  push    rdi
0x180022495  push    r12
0x180022497  push    r13
0x180022499  push    r14
0x18002249b  push    r15
0x18002249d  lea     rbp, [rsp-1Fh]
0x1800224a2  sub     rsp, 0C8h
0x1800224a9  mov     rax, cs:__security_cookie
0x1800224b0  xor     rax, rsp
0x1800224b3  mov     [rbp+57h+var_48], rax
0x1800224b7  xor     r13d, r13d
0x1800224ba  mov     r14, r9
0x1800224bd  mov     [rbp+57h+lpWideCharStr], r13
0x1800224c1  mov     r15, r8
0x1800224c4  mov     [rbp+57h+var_BC], r13d
0x1800224c8  mov     rbx, rdx
0x1800224cb  mov     rdi, rcx
0x1800224ce  mov     r8d, r13d
0x1800224d1  mov     r9d, r13d
0x1800224d4  test    rdx, rdx
0x1800224d7  jz      loc_180022778
0x1800224dd  test    r15, r15
0x1800224e0  jz      loc_180022778
0x1800224e6  test    r14, r14
0x1800224e9  jz      loc_180022778
0x1800224ef  mov     r11d, [rcx+2370h]
0x1800224f6  test    r11d, r11d
0x1800224f9  jz      short loc_180022569
0x1800224fb  mov     r12, [rcx+2360h]
0x180022502  mov     edx, r13d
0x180022505  mov     rax, [r12+20h]
0x18002250a  mov     rsi, rbx
0x18002250d  mov     r13d, edx
0x180022510  mov     rcx, [rax+r13*8]
0x180022514  sub     rsi, rcx
0x180022517  movzx   r10d, byte ptr [rcx]
0x18002251b  movzx   eax, byte ptr [rcx+rsi]
0x18002251f  sub     r10d, eax
0x180022522  jnz     short loc_18002252B
0x180022524  inc     rcx
0x180022527  test    eax, eax
0x180022529  jnz     short loc_180022517
0x18002252b  test    r10d, r10d
0x18002252e  jnz     short loc_18002255A
0x180022530  mov     rax, [rdi+2368h]
0x180022537  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002253b  mov     rcx, [rax+20h]
0x18002253f  mov     r8, [rcx+r13*8]
0x180022543  xor     r13d, r13d
0x180022546  mov     [rbp+57h+lpWideCharStr], r8
0x18002254a  inc     r9
0x18002254d  cmp     [r8+r9*2], r13w
0x180022552  jnz     short loc_18002254A
0x180022554  mov     [rbp+57h+var_BC], r9d
0x180022558  jmp     short loc_18002255D
0x18002255a  xor     r13d, r13d
0x18002255d  inc     edx
0x18002255f  cmp     edx, r11d
0x180022562  jb      short loc_180022505
0x180022564  test    r8, r8
0x180022567  jnz     short loc_1800225D2
0x180022569  lea     r8, [rbp+57h+var_B0]; int (**)(struct W3_CONTEXT *, const char **, unsigned int *)
0x18002256d  mov     [rbp+57h+var_A8], r13
0x180022571  lea     rdx, [rbp+57h+var_A8]; int (**)(struct W3_CONTEXT *, const unsigned __int16 **, unsigned int *)
0x180022575  mov     [rbp+57h+var_B0], r13
0x180022579  mov     rcx, rbx; char *
0x18002257c  call    ?GetFunction@SERVERVAR_HASH@@SAJPEBDPEAP6AJPEAVW3_CONTEXT@@PEAPEBGPEAK@ZPEAP6AJ1PEAPEBD3@Z@Z; SERVERVAR_HASH::GetFunction(char const *,long (**)(W3_CONTEXT *,ushort const * *,ulong *),long (**)(W3_CONTEXT *,char const * *,ulong *))
0x180022581  test    eax, eax
0x180022583  js      loc_18002277D
0x180022589  mov     rax, [rbp+57h+var_B0]
0x18002258d  test    rax, rax
0x180022590  jz      short loc_1800225A5
0x180022592  mov     r8, r14
0x180022595  mov     rdx, r15
0x180022598  mov     rcx, rdi
0x18002259b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225a0  jmp     loc_18002277D
0x1800225a5  mov     rax, [rbp+57h+var_A8]
0x1800225a9  test    rax, rax
0x1800225ac  jz      loc_1800226A4
0x1800225b2  lea     r8, [rbp+57h+var_BC]
0x1800225b6  mov     rcx, rdi
0x1800225b9  lea     rdx, [rbp+57h+lpWideCharStr]
0x1800225bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225c2  test    eax, eax
0x1800225c4  js      loc_18002277D
0x1800225ca  mov     r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x1800225ce  mov     r9d, [rbp+57h+var_BC]
0x1800225d2  test    r9d, r9d
0x1800225d5  jz      loc_18002268D
0x1800225db  mov     [rsp+100h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800225e0  mov     r12d, 400h
0x1800225e6  mov     [rsp+100h+lpDefaultChar], r13; lpDefaultChar
0x1800225eb  mov     edx, r12d; dwFlags
0x1800225ee  mov     [rsp+100h+cbMultiByte], r13d; cbMultiByte
0x1800225f3  inc     r9d; cchWideChar
0x1800225f6  xor     ecx, ecx; CodePage
0x1800225f8  mov     [rsp+100h+lpMultiByteStr], r13; lpMultiByteStr
0x1800225fd  call    cs:__imp_WideCharToMultiByte
0x180022604  nop     dword ptr [rax+rax+00h]
0x180022609  mov     esi, eax
0x18002260b  test    eax, eax
0x18002260d  jnz     short loc_180022630
0x18002260f  call    cs:__imp_GetLastError
0x180022616  nop     dword ptr [rax+rax+00h]
0x18002261b  test    eax, eax
0x18002261d  jle     loc_18002277D
0x180022623  movzx   eax, ax
0x180022626  or      eax, 80070000h
0x18002262b  jmp     loc_18002277D
0x180022630  mov     rax, [rdi]
0x180022633  mov     edx, esi
0x180022635  mov     rcx, rdi
0x180022638  mov     rax, [rax+90h]
0x18002263f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022644  mov     rbx, rax
0x180022647  test    rax, rax
0x18002264a  jnz     short loc_180022656
0x18002264c  mov     eax, 80070008h
0x180022651  jmp     loc_18002277D
0x180022656  mov     r9d, [rbp+57h+var_BC]
0x18002265a  mov     edx, r12d; dwFlags
0x18002265d  mov     r8, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x180022661  inc     r9d; cchWideChar
0x180022664  mov     [rsp+100h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180022669  xor     ecx, ecx; CodePage
0x18002266b  mov     [rsp+100h+lpDefaultChar], r13; lpDefaultChar
0x180022670  mov     [rsp+100h+cbMultiByte], esi; cbMultiByte
0x180022674  mov     [rsp+100h+lpMultiByteStr], rax; lpMultiByteStr
0x180022679  call    cs:__imp_WideCharToMultiByte
0x180022680  nop     dword ptr [rax+rax+00h]
0x180022685  test    eax, eax
0x180022687  jz      short loc_18002260F
0x180022689  dec     eax
0x18002268b  jmp     short loc_180022697
0x18002268d  mov     eax, r13d
0x180022690  lea     rbx, dword_18003C5E4
0x180022697  mov     [r15], rbx
0x18002269a  mov     [r14], eax
0x18002269d  xor     eax, eax
0x18002269f  jmp     loc_18002277D
0x1800226a4  mov     r8d, 20h ; ' '
0x1800226aa  mov     [rbp+57h+var_C0], r13w
0x1800226af  lea     rdx, [rbp+57h+var_68]
0x1800226b3  lea     rcx, [rbp+57h+var_A0]
0x1800226b7  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800226be  nop     dword ptr [rax+rax+00h]
0x1800226c3  mov     r8d, 5; MaxCount
0x1800226c9  lea     rdx, aHttp; "HTTP_"
0x1800226d0  mov     rcx, rbx; Str1
0x1800226d3  call    strncmp_0
0x1800226d8  test    eax, eax
0x1800226da  jnz     short loc_180022721
0x1800226dc  lea     rdx, [rbx+5]
0x1800226e0  lea     rcx, [rbp+57h+var_A0]
0x1800226e4  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800226eb  nop     dword ptr [rax+rax+00h]
0x1800226f0  mov     ebx, eax
0x1800226f2  test    eax, eax
0x1800226f4  js      short loc_180022764
0x1800226f6  mov     rcx, [rbp+57h+var_80]
0x1800226fa  mov     ebx, 5Fh ; '_'
0x1800226ff  jmp     short loc_180022708
0x180022701  mov     byte ptr [rax], 2Dh ; '-'
0x180022704  lea     rcx, [rax+1]; Str
0x180022708  mov     edx, ebx; Val
0x18002270a  call    cs:__imp_strchr
0x180022711  nop     dword ptr [rax+rax+00h]
0x180022716  test    rax, rax
0x180022719  jnz     short loc_180022701
0x18002271b  mov     rdx, [rbp+57h+var_80]
0x18002271f  jmp     short loc_18002273E
0x180022721  mov     r8d, 7; MaxCount
0x180022727  lea     rdx, aHeader; "HEADER_"
0x18002272e  mov     rcx, rbx; Str1
0x180022731  call    strncmp_0
0x180022736  test    eax, eax
0x180022738  jnz     short loc_18002275F
0x18002273a  lea     rdx, [rbx+7]; char *
0x18002273e  mov     rcx, [rdi+30h]; this
0x180022742  lea     r8, [rbp+57h+var_C0]; unsigned __int16 *
0x180022746  call    ?GetHeader@W3_REQUEST@@QEBAPEBDPEBDPEAG@Z; W3_REQUEST::GetHeader(char const *,ushort *)
0x18002274b  mov     [r15], rax
0x18002274e  test    rax, rax
0x180022751  jz      short loc_18002275F
0x180022753  movzx   eax, [rbp+57h+var_C0]
0x180022757  mov     ebx, r13d
0x18002275a  mov     [r14], eax
0x18002275d  jmp     short loc_180022764
0x18002275f  mov     ebx, 80070585h
0x180022764  lea     rcx, [rbp+57h+var_A0]
0x180022768  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002276f  nop     dword ptr [rax+rax+00h]
0x180022774  mov     eax, ebx
0x180022776  jmp     short loc_18002277D
0x180022778  mov     eax, 80070057h
0x18002277d  mov     rcx, [rbp+57h+var_48]
0x180022781  xor     rcx, rsp; StackCookie
0x180022784  call    __security_check_cookie
0x180022789  add     rsp, 0C8h
0x180022790  pop     r15
0x180022792  pop     r14
0x180022794  pop     r13
0x180022796  pop     r12
0x180022798  pop     rdi
0x180022799  pop     rsi
0x18002279a  pop     rbx
0x18002279b  pop     rbp
0x18002279c  retn
```
