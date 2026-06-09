# SetHeadersByStream(IHttpRequest *,char *)

- ea: `0x18000f91c`
- end: `0x18000fb0e`
- name: `?SetHeadersByStream@@YAJPEAVIHttpRequest@@PEAD@Z`
- size: `498`
- prototype: `__int64 __fastcall(struct IHttpRequest *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000cc50`

## callees

- `0x18000f91c`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `msvcrt!strchr` at `0x18000fa11`
- `msvcrt!strchr` at `0x18000fa11`
- `msvcrt!strstr` at `0x18000f9ca`
- `msvcrt!strstr` at `0x18000f9ca`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa03`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa28`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa37`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa8c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa99`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa03`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa28`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa37`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa8c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fa99`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000facb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fad5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fae0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000facb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fad5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fae0`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f95d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f971`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f986`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f95d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f971`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f986`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000fa7f`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000fa7f`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000f9ea`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000fa47`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000f9ea`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000fa47`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000fa67`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000fa67`

## pseudocode

```c
__int64 __fastcall SetHeadersByStream(struct IHttpRequest *a1, char *a2)
{
  int v4; // ebx
  char *v5; // rax
  char *v6; // rdi
  const char *Str; // rax
  char *v8; // rdi
  unsigned int v9; // ebx
  const char *v10; // rax
  __int64 (__fastcall *v11)(struct IHttpRequest *, char *, char *, _QWORD, int); // rsi
  unsigned __int16 CCH; // di
  char *v13; // rbx
  char *v14; // rax
  _BYTE v16[56]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[56]; // [rsp+A8h] [rbp-58h] BYREF
  char v19[32]; // [rsp+E0h] [rbp-20h] BYREF
  char v20[64]; // [rsp+100h] [rbp+0h] BYREF
  char v21[128]; // [rsp+140h] [rbp+40h] BYREF

  STRA::STRA((STRA *)v16, v21, 0x80u);
  STRA::STRA((STRA *)v18, v19, 0x20u);
  STRA::STRA((STRA *)v17, v20, 0x40u);
  if ( a2 )
  {
    v4 = 0;
    while ( a2 && *a2 && (*a2 != 13 || a2[1] != 10) )
    {
      v5 = strstr(a2, "\r\n");
      v6 = v5;
      if ( !v5 )
        break;
      v4 = STRA::Copy((STRA *)v16, a2, (_DWORD)v5 - (_DWORD)a2);
      if ( v4 < 0 )
        break;
      a2 = v6 + 2;
      Str = STRA::QueryStr((STRA *)v16);
      v8 = strchr(Str, 58);
      if ( v8 )
      {
        v9 = (_DWORD)v8 - (unsigned int)STRA::QueryStr((STRA *)v16);
        v10 = STRA::QueryStr((STRA *)v16);
        v4 = STRA::Copy((STRA *)v18, v10, v9);
        if ( v4 < 0 )
          break;
        if ( v8[1] == 32 )
          ++v8;
        v4 = STRA::Copy((STRA *)v17, v8 + 1);
        if ( v4 < 0 )
          break;
        v11 = *(__int64 (__fastcall **)(struct IHttpRequest *, char *, char *, _QWORD, int))(*(_QWORD *)a1 + 40LL);
        CCH = STRA::QueryCCH((STRA *)v17);
        v13 = STRA::QueryStr((STRA *)v17);
        v14 = STRA::QueryStr((STRA *)v18);
        v4 = v11(a1, v14, v13, CCH, 1);
        if ( v4 < 0 )
          break;
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  STRA::~STRA((STRA *)v17);
  STRA::~STRA((STRA *)v18);
  STRA::~STRA((STRA *)v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f91c  mov     [rsp-8+arg_10], rbx
0x18000f921  push    rbp
0x18000f922  push    rsi
0x18000f923  push    rdi
0x18000f924  push    r14
0x18000f926  push    r15
0x18000f928  lea     rbp, [rsp-0D0h]
0x18000f930  sub     rsp, 1D0h
0x18000f937  mov     rax, cs:__security_cookie
0x18000f93e  xor     rax, rsp
0x18000f941  mov     [rbp+0F0h+var_30], rax
0x18000f948  mov     r14, rdx
0x18000f94b  mov     r15, rcx
0x18000f94e  lea     rdx, [rbp+0F0h+var_B0]
0x18000f952  mov     r8d, 80h
0x18000f958  lea     rcx, [rsp+1F0h+var_1B8]
0x18000f95d  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000f963  mov     r8d, 20h ; ' '
0x18000f969  lea     rdx, [rbp+0F0h+var_110]
0x18000f96d  lea     rcx, [rbp+0F0h+var_148]
0x18000f971  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000f977  mov     r8d, 40h ; '@'
0x18000f97d  lea     rdx, [rbp+0F0h+var_F0]
0x18000f981  lea     rcx, [rsp+1F0h+var_180]
0x18000f986  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000f98c  test    r14, r14
0x18000f98f  jnz     short loc_18000F99B
0x18000f991  mov     ebx, 80070057h
0x18000f996  jmp     loc_18000FAC6
0x18000f99b  xor     ebx, ebx
0x18000f99d  test    r14, r14
0x18000f9a0  jz      loc_18000FAC6
0x18000f9a6  mov     al, [r14]
0x18000f9a9  test    al, al
0x18000f9ab  jz      loc_18000FAC6
0x18000f9b1  cmp     al, 0Dh
0x18000f9b3  jnz     short loc_18000F9C0
0x18000f9b5  cmp     byte ptr [r14+1], 0Ah
0x18000f9ba  jz      loc_18000FAC6
0x18000f9c0  lea     rdx, Control; "\r\n"
0x18000f9c7  mov     rcx, r14; Str
0x18000f9ca  call    cs:__imp_strstr
0x18000f9d0  mov     rdi, rax
0x18000f9d3  test    rax, rax
0x18000f9d6  jz      loc_18000FAC6
0x18000f9dc  mov     r8d, edi
0x18000f9df  lea     rcx, [rsp+1F0h+var_1B8]
0x18000f9e4  sub     r8d, r14d
0x18000f9e7  mov     rdx, r14
0x18000f9ea  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000f9f0  mov     ebx, eax
0x18000f9f2  test    eax, eax
0x18000f9f4  js      loc_18000FAC6
0x18000f9fa  lea     rcx, [rsp+1F0h+var_1B8]
0x18000f9ff  lea     r14, [rdi+2]
0x18000fa03  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000fa09  mov     rcx, rax; Str
0x18000fa0c  mov     edx, 3Ah ; ':'; Val
0x18000fa11  call    cs:__imp_strchr
0x18000fa17  mov     rdi, rax
0x18000fa1a  test    rax, rax
0x18000fa1d  jz      loc_18000F99D
0x18000fa23  lea     rcx, [rsp+1F0h+var_1B8]
0x18000fa28  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000fa2e  mov     ebx, edi
0x18000fa30  lea     rcx, [rsp+1F0h+var_1B8]
0x18000fa35  sub     ebx, eax
0x18000fa37  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000fa3d  mov     r8d, ebx
0x18000fa40  lea     rcx, [rbp+0F0h+var_148]
0x18000fa44  mov     rdx, rax
0x18000fa47  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000fa4d  mov     ebx, eax
0x18000fa4f  test    eax, eax
0x18000fa51  js      short loc_18000FAC6
0x18000fa53  lea     rax, [rdi+1]
0x18000fa57  cmp     byte ptr [rax], 20h ; ' '
0x18000fa5a  lea     rcx, [rsp+1F0h+var_180]
0x18000fa5f  cmovz   rdi, rax
0x18000fa63  lea     rdx, [rdi+1]
0x18000fa67  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000fa6d  mov     ebx, eax
0x18000fa6f  test    eax, eax
0x18000fa71  js      short loc_18000FAC6
0x18000fa73  mov     rax, [r15]
0x18000fa76  lea     rcx, [rsp+1F0h+var_180]
0x18000fa7b  mov     rsi, [rax+28h]
0x18000fa7f  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000fa85  lea     rcx, [rsp+1F0h+var_180]
0x18000fa8a  mov     edi, eax
0x18000fa8c  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000fa92  lea     rcx, [rbp+0F0h+var_148]
0x18000fa96  mov     rbx, rax
0x18000fa99  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000fa9f  movzx   r9d, di
0x18000faa3  mov     [rsp+1F0h+var_1D0], 1
0x18000faab  mov     rdx, rax
0x18000faae  mov     r8, rbx
0x18000fab1  mov     rax, rsi
0x18000fab4  mov     rcx, r15
0x18000fab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fabc  mov     ebx, eax
0x18000fabe  test    eax, eax
0x18000fac0  jns     loc_18000F99D
0x18000fac6  lea     rcx, [rsp+1F0h+var_180]
0x18000facb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000fad1  lea     rcx, [rbp+0F0h+var_148]
0x18000fad5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000fadb  lea     rcx, [rsp+1F0h+var_1B8]
0x18000fae0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000fae6  mov     eax, ebx
0x18000fae8  mov     rcx, [rbp+0F0h+var_30]
0x18000faef  xor     rcx, rsp; StackCookie
0x18000faf2  call    __security_check_cookie
0x18000faf7  mov     rbx, [rsp+1F0h+arg_10]
0x18000faff  add     rsp, 1D0h
0x18000fb06  pop     r15
0x18000fb08  pop     r14
0x18000fb0a  pop     rdi
0x18000fb0b  pop     rsi
0x18000fb0c  pop     rbp
0x18000fb0d  retn
```
