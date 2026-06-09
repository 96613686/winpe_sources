# SetHeaders(IHttpResponse *,char *,ulong)

- ea: `0x1800074f0`
- end: `0x18000779a`
- name: `?SetHeaders@@YAJPEAVIHttpResponse@@PEADK@Z`
- size: `682`
- prototype: `__int64 __fastcall(struct IHttpResponse *, char *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001d20`
- `0x180005b20`

## callees

- `0x1800074f0`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `msvcrt!strchr` at `0x180007569`
- `msvcrt!strchr` at `0x180007583`
- `msvcrt!strchr` at `0x1800075bd`
- `msvcrt!strchr` at `0x180007569`
- `msvcrt!strchr` at `0x180007583`
- `msvcrt!strchr` at `0x1800075bd`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007676`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007683`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007676`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007683`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800075f2`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007647`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800075f2`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007647`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007669`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007669`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000772b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007736`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007744`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000774f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007760`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000776b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000772b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007736`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007744`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000774f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007760`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000776b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007537`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000754b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007537`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000754b`

## pseudocode

```c
__int64 __fastcall SetHeaders(struct IHttpResponse *a1, char *a2, unsigned int a3)
{
  __int64 v3; // r15
  struct IHttpResponse *v5; // r12
  unsigned int i; // ebx
  const char *v7; // rsi
  char *v8; // rdi
  char *v9; // rax
  char *v10; // r13
  char v11; // al
  const char *j; // r8
  int v13; // ebx
  __int64 k; // rdi
  const char *v15; // r8
  const char *v16; // rdx
  __int64 (__fastcall *v17)(struct IHttpResponse *, char *, char *, _QWORD, _DWORD); // rsi
  unsigned __int16 CCH; // di
  char *Str; // rbx
  char *v20; // rax
  int v21; // eax
  unsigned int v22; // edx
  __int64 v23; // rax
  _QWORD v26[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h]
  int v28; // [rsp+54h] [rbp-ACh]
  _BYTE v29[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v30[56]; // [rsp+90h] [rbp-70h] BYREF
  char v31[32]; // [rsp+C8h] [rbp-38h] BYREF
  char v32[32]; // [rsp+E8h] [rbp-18h] BYREF

  v3 = a3;
  v5 = a1;
  STRA::STRA((STRA *)v29, v31, 0x20u);
  STRA::STRA((STRA *)v30, v32, 0x20u);
  for ( i = 0; i < (unsigned int)v3; i = (_DWORD)v10 - (_DWORD)a2 + 1 )
  {
    v7 = &a2[i];
    v8 = strchr(v7, 58);
    if ( !v8 || (v9 = strchr(&a2[i], 10), (v10 = v9) == 0) || v8 >= v9 )
    {
      if ( *v7 == 10 )
      {
        v21 = 1;
      }
      else
      {
        if ( *v7 != 13 || a2[i + 1] != 10 )
        {
          STRA::~STRA((STRA *)v30);
          STRA::~STRA((STRA *)v29);
          return 2147942487LL;
        }
        v21 = 2;
      }
      v22 = v21 + i;
      if ( v21 + i < (unsigned int)v3 )
      {
        v26[0] = 0;
        v26[1] = &a2[v22];
        v23 = *(_QWORD *)v5;
        v27 = 0;
        v28 = 0;
        v26[2] = (unsigned int)v3 - v22;
        v13 = (*(__int64 (__fastcall **)(struct IHttpResponse *, _QWORD *, _QWORD))(v23 + 160))(v5, v26, 0);
        if ( v13 < 0 )
        {
LABEL_30:
          STRA::~STRA((STRA *)v30);
          STRA::~STRA((STRA *)v29);
          return (unsigned int)v13;
        }
      }
      break;
    }
    if ( v9 < &a2[v3] )
    {
      do
      {
        v11 = v10[1];
        if ( v11 != 32 && v11 != 9 )
          break;
        v10 = strchr(v10 + 1, 10);
      }
      while ( v10 < &a2[v3] );
    }
    for ( j = v8 - 1; j >= v7; --j )
    {
      if ( *j != 32 )
        break;
    }
    v13 = STRA::Copy((STRA *)v30, &a2[i], (_DWORD)j - (_DWORD)a2 - i + 1);
    if ( v13 < 0 )
      goto LABEL_30;
    for ( k = (unsigned int)((_DWORD)v8 - (_DWORD)a2 + 1); a2[k] == 32; k = (unsigned int)(k + 1) )
      ;
    v15 = v10 - 1;
    v16 = &a2[(unsigned int)k];
    if ( v10 - 1 >= v16 )
    {
      do
      {
        if ( *v15 != 32 && *v15 != 13 )
          break;
        --v15;
      }
      while ( v15 >= v16 );
    }
    v13 = STRA::Copy((STRA *)v29, v16, (_DWORD)v15 - (_DWORD)a2 - k + 1);
    if ( v13 < 0 )
      goto LABEL_30;
    v5 = a1;
    v17 = *(__int64 (__fastcall **)(struct IHttpResponse *, char *, char *, _QWORD, _DWORD))(*(_QWORD *)a1 + 40LL);
    CCH = STRA::QueryCCH((STRA *)v29);
    Str = STRA::QueryStr((STRA *)v29);
    v20 = STRA::QueryStr((STRA *)v30);
    v13 = v17(a1, v20, Str, CCH, 0);
    if ( v13 < 0 )
      goto LABEL_30;
  }
  STRA::~STRA((STRA *)v30);
  STRA::~STRA((STRA *)v29);
  return 0;
}

```

## disassembly

```asm
0x1800074f0  mov     [rsp-8+arg_18], rbx
0x1800074f5  push    rbp
0x1800074f6  push    rsi
0x1800074f7  push    rdi
0x1800074f8  push    r12
0x1800074fa  push    r13
0x1800074fc  push    r14
0x1800074fe  push    r15
0x180007500  lea     rbp, [rsp-10h]
0x180007505  sub     rsp, 110h
0x18000750c  mov     rax, cs:__security_cookie
0x180007513  xor     rax, rsp
0x180007516  mov     [rbp+40h+var_38], rax
0x18000751a  mov     r15d, r8d
0x18000751d  mov     r14, rdx
0x180007520  mov     r12, rcx
0x180007523  mov     [rsp+140h+var_110], rcx
0x180007528  mov     r8d, 20h ; ' '
0x18000752e  lea     rdx, [rbp+40h+var_78]
0x180007532  lea     rcx, [rsp+140h+var_E8]
0x180007537  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000753d  mov     r8d, 20h ; ' '
0x180007543  lea     rdx, [rbp+40h+var_58]
0x180007547  lea     rcx, [rbp+40h+var_B0]
0x18000754b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180007551  xor     ebx, ebx
0x180007553  cmp     ebx, r15d
0x180007556  jnb     loc_18000775C
0x18000755c  mov     esi, ebx
0x18000755e  mov     edx, 3Ah ; ':'; Val
0x180007563  add     rsi, r14
0x180007566  mov     rcx, rsi; Str
0x180007569  call    cs:__imp_strchr
0x18000756f  mov     rdi, rax
0x180007572  test    rax, rax
0x180007575  jz      loc_1800076B9
0x18000757b  mov     edx, 0Ah; Val
0x180007580  mov     rcx, rsi; Str
0x180007583  call    cs:__imp_strchr
0x180007589  mov     r13, rax
0x18000758c  test    rax, rax
0x18000758f  jz      loc_1800076B9
0x180007595  cmp     rdi, rax
0x180007598  jnb     loc_1800076B9
0x18000759e  lea     r12, [r14+r15]
0x1800075a2  cmp     rax, r12
0x1800075a5  jnb     short loc_1800075CB
0x1800075a7  movzx   eax, byte ptr [r13+1]
0x1800075ac  lea     rcx, [r13+1]; Str
0x1800075b0  cmp     al, 20h ; ' '
0x1800075b2  jz      short loc_1800075B8
0x1800075b4  cmp     al, 9
0x1800075b6  jnz     short loc_1800075CB
0x1800075b8  mov     edx, 0Ah; Val
0x1800075bd  call    cs:__imp_strchr
0x1800075c3  mov     r13, rax
0x1800075c6  cmp     rax, r12
0x1800075c9  jb      short loc_1800075A7
0x1800075cb  lea     r8, [rdi-1]
0x1800075cf  cmp     r8, rsi
0x1800075d2  jb      short loc_1800075E2
0x1800075d4  cmp     byte ptr [r8], 20h ; ' '
0x1800075d8  jnz     short loc_1800075E2
0x1800075da  dec     r8
0x1800075dd  cmp     r8, rsi
0x1800075e0  jnb     short loc_1800075D4
0x1800075e2  sub     r8d, r14d
0x1800075e5  lea     rcx, [rbp+40h+var_B0]
0x1800075e9  sub     r8d, ebx
0x1800075ec  mov     rdx, rsi
0x1800075ef  inc     r8d
0x1800075f2  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800075f8  mov     ebx, eax
0x1800075fa  test    eax, eax
0x1800075fc  js      loc_180007727
0x180007602  sub     edi, r14d
0x180007605  inc     edi
0x180007607  cmp     byte ptr [rdi+r14], 20h ; ' '
0x18000760c  jnz     short loc_180007617
0x18000760e  inc     edi
0x180007610  cmp     byte ptr [rdi+r14], 20h ; ' '
0x180007615  jz      short loc_18000760E
0x180007617  mov     edx, edi
0x180007619  lea     r8, [r13-1]
0x18000761d  add     rdx, r14
0x180007620  cmp     r8, rdx
0x180007623  jb      short loc_180007639
0x180007625  movzx   eax, byte ptr [r8]
0x180007629  cmp     al, 20h ; ' '
0x18000762b  jz      short loc_180007631
0x18000762d  cmp     al, 0Dh
0x18000762f  jnz     short loc_180007639
0x180007631  dec     r8
0x180007634  cmp     r8, rdx
0x180007637  jnb     short loc_180007625
0x180007639  sub     r8d, r14d
0x18000763c  lea     rcx, [rsp+140h+var_E8]
0x180007641  sub     r8d, edi
0x180007644  inc     r8d
0x180007647  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000764d  mov     ebx, eax
0x18000764f  test    eax, eax
0x180007651  js      loc_180007727
0x180007657  mov     r12, [rsp+140h+var_110]
0x18000765c  lea     rcx, [rsp+140h+var_E8]
0x180007661  mov     rax, [r12]
0x180007665  mov     rsi, [rax+28h]
0x180007669  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000766f  lea     rcx, [rsp+140h+var_E8]
0x180007674  mov     edi, eax
0x180007676  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000767c  lea     rcx, [rbp+40h+var_B0]
0x180007680  mov     rbx, rax
0x180007683  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007689  movzx   r9d, di
0x18000768d  mov     [rsp+140h+var_120], 0
0x180007695  mov     rdx, rax
0x180007698  mov     r8, rbx
0x18000769b  mov     rax, rsi
0x18000769e  mov     rcx, r12
0x1800076a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a6  mov     ebx, eax
0x1800076a8  test    eax, eax
0x1800076aa  js      short loc_180007727
0x1800076ac  mov     ebx, r13d
0x1800076af  sub     ebx, r14d
0x1800076b2  inc     ebx
0x1800076b4  jmp     loc_180007553
0x1800076b9  movzx   eax, byte ptr [rsi]
0x1800076bc  cmp     al, 0Ah
0x1800076be  jnz     short loc_1800076C7
0x1800076c0  mov     eax, 1
0x1800076c5  jmp     short loc_1800076DA
0x1800076c7  cmp     al, 0Dh
0x1800076c9  jnz     short loc_180007740
0x1800076cb  lea     eax, [rbx+1]
0x1800076ce  cmp     byte ptr [rax+r14], 0Ah
0x1800076d3  jnz     short loc_180007740
0x1800076d5  mov     eax, 2
0x1800076da  lea     edx, [rax+rbx]
0x1800076dd  cmp     edx, r15d
0x1800076e0  jnb     short loc_18000775C
0x1800076e2  mov     eax, edx
0x1800076e4  xor     r13d, r13d
0x1800076e7  add     rax, r14
0x1800076ea  mov     [rsp+140h+var_108], r13
0x1800076ef  mov     [rsp+140h+var_100], rax
0x1800076f4  sub     r15d, edx
0x1800076f7  mov     rax, [r12]
0x1800076fb  lea     rdx, [rsp+140h+var_108]
0x180007700  xor     r8d, r8d
0x180007703  mov     [rsp+140h+var_F4], r13
0x180007708  mov     rcx, r12
0x18000770b  mov     [rsp+140h+var_EC], r13d
0x180007710  mov     [rsp+140h+var_F8], r15d
0x180007715  mov     rax, [rax+0A0h]
0x18000771c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007721  mov     ebx, eax
0x180007723  test    eax, eax
0x180007725  jns     short loc_18000775C
0x180007727  lea     rcx, [rbp+40h+var_B0]
0x18000772b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007731  lea     rcx, [rsp+140h+var_E8]
0x180007736  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000773c  mov     eax, ebx
0x18000773e  jmp     short loc_180007773
0x180007740  lea     rcx, [rbp+40h+var_B0]
0x180007744  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000774a  lea     rcx, [rsp+140h+var_E8]
0x18000774f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007755  mov     eax, 80070057h
0x18000775a  jmp     short loc_180007773
0x18000775c  lea     rcx, [rbp+40h+var_B0]
0x180007760  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007766  lea     rcx, [rsp+140h+var_E8]
0x18000776b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007771  xor     eax, eax
0x180007773  mov     rcx, [rbp+40h+var_38]
0x180007777  xor     rcx, rsp; StackCookie
0x18000777a  call    __security_check_cookie
0x18000777f  mov     rbx, [rsp+140h+arg_18]
0x180007787  add     rsp, 110h
0x18000778e  pop     r15
0x180007790  pop     r14
0x180007792  pop     r13
0x180007794  pop     r12
0x180007796  pop     rdi
0x180007797  pop     rsi
0x180007798  pop     rbp
0x180007799  retn
```
