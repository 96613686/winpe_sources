# W3_FILTER_CONTEXT::GetFilterHeader(_HTTP_FILTER_CONTEXT *,char *,void *,ulong *)

- ea: `0x1800057f0`
- end: `0x180005b0d`
- name: `?GetFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEADPEAXPEAK@Z`
- size: `797`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, char *, char *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800057f0`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180005a34`
- `msvcrt!_itoa_s` at `0x180005a4e`
- `msvcrt!_itoa_s` at `0x180005a34`
- `msvcrt!_itoa_s` at `0x180005a4e`
- `msvcrt!_stricmp` at `0x18000589b`
- `msvcrt!_stricmp` at `0x180005938`
- `msvcrt!_stricmp` at `0x180005950`
- `msvcrt!_stricmp` at `0x18000589b`
- `msvcrt!_stricmp` at `0x180005938`
- `msvcrt!_stricmp` at `0x180005950`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005919`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005af5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005919`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005af5`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005a75`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005a8d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005aa2`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005a75`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005a8d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180005aa2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800059c5`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800059c5`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800058b7`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800059a9`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180005ad3`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800058b7`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800059a9`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180005ad3`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800058d2`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800058d2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800058e7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005924`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800059f1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005aaf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005aea`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005b00`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800058e7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005924`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800059f1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005aaf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005aea`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005b00`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000582f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000596d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000582f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000596d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005a13`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005a60`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005a13`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005a60`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::GetFilterHeader(
        struct _HTTP_FILTER_CONTEXT *a1,
        char *a2,
        char *a3,
        unsigned int *a4)
{
  _QWORD **ServerContext; // rax
  __int64 v9; // r14
  __int64 v10; // rdi
  signed int v11; // ebx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 (__fastcall *v15)(__int64, char *, unsigned __int16 *); // rbx
  char *Str; // rax
  const char *v17; // rax
  const char *v18; // rax
  unsigned __int16 v19; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v20[56]; // [rsp+28h] [rbp-D8h] BYREF
  char v21[56]; // [rsp+60h] [rbp-A0h] BYREF
  char Buffer[8]; // [rsp+98h] [rbp-68h] BYREF
  char v23[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v24[64]; // [rsp+B0h] [rbp-50h] BYREF
  char v25[128]; // [rsp+F0h] [rbp-10h] BYREF

  STRA::STRA((STRA *)v20, v25, 0x80u);
  v19 = 0;
  if ( !a1 || (ServerContext = (_QWORD **)a1->ServerContext) == 0 || !a2 || !a4 )
  {
    SetLastError(0x57u);
    STRA::~STRA((STRA *)v20);
    return 0;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(*ServerContext[3] + 24LL))(ServerContext[3]);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  if ( !_stricmp(a2, "url") )
  {
    v11 = STRA::Copy((STRA *)v20, *(const char **)(v10 + 56), *(unsigned __int16 *)(v10 + 42));
  }
  else if ( !_stricmp(a2, "method") )
  {
    v18 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 64LL))(v9);
    v11 = STRA::Copy((STRA *)v20, v18);
  }
  else if ( !_stricmp(a2, "version") )
  {
    _itoa_s(*(unsigned __int16 *)(v10 + 32), Buffer, 6u, 10);
    _itoa_s(*(unsigned __int16 *)(v10 + 34), v23, 6u, 10);
    v11 = STRA::Copy((STRA *)v20, "HTTP/");
    if ( v11 < 0
      || (v11 = STRA::Append((STRA *)v20, Buffer), v11 < 0)
      || (v11 = STRA::Append((STRA *)v20, "."), v11 < 0) )
    {
LABEL_28:
      if ( (v11 & 0x1FFF0000) != 0x70000 )
      {
LABEL_33:
        SetLastError(v11);
        STRA::~STRA((STRA *)v20);
        return 0;
      }
LABEL_32:
      v11 = (unsigned __int16)v11;
      goto LABEL_33;
    }
    v11 = STRA::Append((STRA *)v20, v23);
  }
  else
  {
    STRA::STRA((STRA *)v21, v24, 0x40u);
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    if ( (unsigned int)v13 <= 1 || (v14 = (unsigned int)(v13 - 1), a2[v14] != 58) )
    {
      LOWORD(v11) = 87;
      STRA::~STRA((STRA *)v21);
      goto LABEL_32;
    }
    v11 = STRA::Copy((STRA *)v21, a2, v14);
    if ( v11 < 0 )
    {
      STRA::~STRA((STRA *)v21);
      goto LABEL_28;
    }
    v15 = *(__int64 (__fastcall **)(__int64, char *, unsigned __int16 *))(*(_QWORD *)v9 + 24LL);
    Str = STRA::QueryStr((STRA *)v21);
    v17 = (const char *)v15(v9, Str, &v19);
    if ( v17 )
      v11 = STRA::Copy((STRA *)v20, v17, v19);
    else
      v11 = -2147023483;
    STRA::~STRA((STRA *)v21);
  }
  if ( v11 < 0 )
    goto LABEL_28;
  v11 = STRA::CopyToBuffer((STRA *)v20, a3, a4);
  if ( v11 < 0 )
    goto LABEL_28;
  STRA::~STRA((STRA *)v20);
  return 1;
}

```

## disassembly

```asm
0x1800057f0  push    rbp
0x1800057f2  push    rbx
0x1800057f3  push    rsi
0x1800057f4  push    rdi
0x1800057f5  push    r15
0x1800057f7  lea     rbp, [rsp-90h]
0x1800057ff  sub     rsp, 190h
0x180005806  mov     rax, cs:__security_cookie
0x18000580d  xor     rax, rsp
0x180005810  mov     [rbp+0B0h+var_40], rax
0x180005814  mov     r15, r8
0x180005817  mov     rbx, rdx
0x18000581a  mov     rdi, rcx
0x18000581d  lea     rdx, [rbp+0B0h+var_C0]
0x180005821  mov     r8d, 80h
0x180005827  lea     rcx, [rsp+1B0h+var_188]
0x18000582c  mov     rsi, r9
0x18000582f  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180005835  xor     eax, eax
0x180005837  mov     [rsp+1B0h+var_190], ax
0x18000583c  test    rdi, rdi
0x18000583f  jz      loc_180005914
0x180005845  mov     rax, [rdi+8]
0x180005849  test    rax, rax
0x18000584c  jz      loc_180005914
0x180005852  test    rbx, rbx
0x180005855  jz      loc_180005914
0x18000585b  test    rsi, rsi
0x18000585e  jz      loc_180005914
0x180005864  mov     rcx, [rax+18h]
0x180005868  mov     [rsp+1B0h+var_28], r14
0x180005870  mov     rax, [rcx]
0x180005873  mov     rax, [rax+18h]
0x180005877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587c  mov     r14, rax
0x18000587f  mov     rcx, [rax]
0x180005882  mov     rax, [rcx+8]
0x180005886  mov     rcx, r14
0x180005889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000588e  lea     rdx, aUrl; "url"
0x180005895  mov     rcx, rbx; String1
0x180005898  mov     rdi, rax
0x18000589b  call    cs:__imp__stricmp
0x1800058a1  test    eax, eax
0x1800058a3  jnz     loc_18000592E
0x1800058a9  movzx   r8d, word ptr [rdi+2Ah]
0x1800058ae  lea     rcx, [rsp+1B0h+var_188]
0x1800058b3  mov     rdx, [rdi+38h]
0x1800058b7  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800058bd  mov     ebx, eax
0x1800058bf  test    ebx, ebx
0x1800058c1  js      loc_180005AB5
0x1800058c7  mov     r8, rsi
0x1800058ca  lea     rcx, [rsp+1B0h+var_188]
0x1800058cf  mov     rdx, r15
0x1800058d2  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x1800058d8  mov     ebx, eax
0x1800058da  test    eax, eax
0x1800058dc  js      loc_180005AB5
0x1800058e2  lea     rcx, [rsp+1B0h+var_188]
0x1800058e7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800058ed  mov     eax, 1
0x1800058f2  mov     r14, [rsp+1B0h+var_28]
0x1800058fa  mov     rcx, [rbp+0B0h+var_40]
0x1800058fe  xor     rcx, rsp; StackCookie
0x180005901  call    __security_check_cookie
0x180005906  add     rsp, 190h
0x18000590d  pop     r15
0x18000590f  pop     rdi
0x180005910  pop     rsi
0x180005911  pop     rbx
0x180005912  pop     rbp
0x180005913  retn
0x180005914  mov     ecx, 57h ; 'W'; dwErrCode
0x180005919  call    cs:__imp_SetLastError
0x18000591f  lea     rcx, [rsp+1B0h+var_188]
0x180005924  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000592a  xor     eax, eax
0x18000592c  jmp     short loc_1800058FA
0x18000592e  lea     rdx, aMethod; "method"
0x180005935  mov     rcx, rbx; String1
0x180005938  call    cs:__imp__stricmp
0x18000593e  test    eax, eax
0x180005940  jz      loc_1800059FC
0x180005946  lea     rdx, aVersion; "version"
0x18000594d  mov     rcx, rbx; String1
0x180005950  call    cs:__imp__stricmp
0x180005956  test    eax, eax
0x180005958  jz      loc_180005A20
0x18000595e  mov     r8d, 40h ; '@'
0x180005964  lea     rdx, [rbp+0B0h+var_100]
0x180005968  lea     rcx, [rsp+1B0h+var_150]
0x18000596d  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180005973  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000597a  nop     word ptr [rax+rax+00h]
0x180005980  inc     rax
0x180005983  cmp     byte ptr [rbx+rax], 0
0x180005987  jnz     short loc_180005980
0x180005989  cmp     eax, 1
0x18000598c  jbe     loc_180005AE0
0x180005992  lea     r8d, [rax-1]
0x180005996  cmp     byte ptr [r8+rbx], 3Ah ; ':'
0x18000599b  jnz     loc_180005AE0
0x1800059a1  mov     rdx, rbx
0x1800059a4  lea     rcx, [rsp+1B0h+var_150]
0x1800059a9  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800059af  lea     rcx, [rsp+1B0h+var_150]
0x1800059b4  mov     ebx, eax
0x1800059b6  test    eax, eax
0x1800059b8  js      loc_180005AAF
0x1800059be  mov     rax, [r14]
0x1800059c1  mov     rbx, [rax+18h]
0x1800059c5  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800059cb  lea     r8, [rsp+1B0h+var_190]
0x1800059d0  mov     rcx, r14
0x1800059d3  mov     rdx, rax
0x1800059d6  mov     rax, rbx
0x1800059d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059de  test    rax, rax
0x1800059e1  jnz     loc_180005AC5
0x1800059e7  mov     ebx, 80070585h
0x1800059ec  lea     rcx, [rsp+1B0h+var_150]
0x1800059f1  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800059f7  jmp     loc_1800058BF
0x1800059fc  mov     rax, [r14]
0x1800059ff  mov     rcx, r14
0x180005a02  mov     rax, [rax+40h]
0x180005a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0b  mov     rdx, rax
0x180005a0e  lea     rcx, [rsp+1B0h+var_188]
0x180005a13  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180005a19  mov     ebx, eax
0x180005a1b  jmp     loc_1800058BF
0x180005a20  movzx   ecx, word ptr [rdi+20h]; Value
0x180005a24  lea     rdx, [rbp+0B0h+Buffer]; Buffer
0x180005a28  mov     r9d, 0Ah; Radix
0x180005a2e  mov     r8d, 6; BufferCount
0x180005a34  call    cs:__imp__itoa_s
0x180005a3a  movzx   ecx, word ptr [rdi+22h]; Value
0x180005a3e  lea     rdx, [rbp+0B0h+var_110]; Buffer
0x180005a42  mov     r9d, 0Ah; Radix
0x180005a48  mov     r8d, 6; BufferCount
0x180005a4e  call    cs:__imp__itoa_s
0x180005a54  lea     rdx, aHttp; "HTTP/"
0x180005a5b  lea     rcx, [rsp+1B0h+var_188]
0x180005a60  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180005a66  mov     ebx, eax
0x180005a68  test    eax, eax
0x180005a6a  js      short loc_180005AB5
0x180005a6c  lea     rdx, [rbp+0B0h+Buffer]
0x180005a70  lea     rcx, [rsp+1B0h+var_188]
0x180005a75  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180005a7b  mov     ebx, eax
0x180005a7d  test    eax, eax
0x180005a7f  js      short loc_180005AB5
0x180005a81  lea     rdx, asc_18000FB6C; "."
0x180005a88  lea     rcx, [rsp+1B0h+var_188]
0x180005a8d  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180005a93  mov     ebx, eax
0x180005a95  test    eax, eax
0x180005a97  js      short loc_180005AB5
0x180005a99  lea     rdx, [rbp+0B0h+var_110]
0x180005a9d  lea     rcx, [rsp+1B0h+var_188]
0x180005aa2  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180005aa8  mov     ebx, eax
0x180005aaa  jmp     loc_1800058BF
0x180005aaf  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005ab5  mov     eax, ebx
0x180005ab7  and     eax, 1FFF0000h
0x180005abc  cmp     eax, 70000h
0x180005ac1  jnz     short loc_180005AF3
0x180005ac3  jmp     short loc_180005AF0
0x180005ac5  movzx   r8d, [rsp+1B0h+var_190]
0x180005acb  lea     rcx, [rsp+1B0h+var_188]
0x180005ad0  mov     rdx, rax
0x180005ad3  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180005ad9  mov     ebx, eax
0x180005adb  jmp     loc_1800059EC
0x180005ae0  lea     rcx, [rsp+1B0h+var_150]
0x180005ae5  mov     ebx, 80070057h
0x180005aea  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005af0  movzx   ebx, bx
0x180005af3  mov     ecx, ebx; dwErrCode
0x180005af5  call    cs:__imp_SetLastError
0x180005afb  lea     rcx, [rsp+1B0h+var_188]
0x180005b00  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005b06  xor     eax, eax
0x180005b08  jmp     loc_1800058F2
```
