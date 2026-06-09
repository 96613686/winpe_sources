# CHECK_ACCESS_HANDLER::PopulateXFFHeader(IHttpContext *)

- ea: `0x1800028b0`
- end: `0x180002a31`
- name: `?PopulateXFFHeader@CHECK_ACCESS_HANDLER@@QEAAJPEAVIHttpContext@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CHECK_ACCESS_HANDLER *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180001b5c`

## callees

- `0x1800028b0`
- `0x180004ad0`
- `0x180005010`

## import_xrefs

- `msvcrt!strchr` at `0x18000296e`
- `msvcrt!strchr` at `0x18000296e`
- `msvcrt!isspace` at `0x180002949`
- `msvcrt!isspace` at `0x18000299e`
- `msvcrt!isspace` at `0x180002949`
- `msvcrt!isspace` at `0x18000299e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002a00`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002a00`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800028f3`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800028f3`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000292e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000292e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800029cd`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800029cd`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800029e2`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800029e2`

## pseudocode

```c
__int64 __fastcall CHECK_ACCESS_HANDLER::PopulateXFFHeader(CHECK_ACCESS_HANDLER *this, struct IHttpContext *a2)
{
  int v4; // esi
  char *v5; // rdi
  int v6; // r15d
  char *v7; // rbx
  __int64 v8; // rax
  char *v9; // r14
  signed int v10; // ebp
  int v12; // [rsp+30h] [rbp-78h] BYREF
  const char *v13; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-68h] BYREF
  char *Str; // [rsp+60h] [rbp-48h]

  v13 = 0;
  v12 = 0;
  STRA::STRA((STRA *)v14);
  if ( (*(int (__fastcall **)(struct IHttpContext *, const char *, const char **, int *))(*(_QWORD *)a2 + 120LL))(
         a2,
         "HTTP_X_FORWARDED_FOR",
         &v13,
         &v12) >= 0 )
  {
    v4 = STRA::Copy((STRA *)v14, v13);
    if ( v4 >= 0 )
    {
      v5 = Str;
      v6 = 0;
      do
      {
        while ( isspace(*v5) || *v5 == 44 )
          ++v5;
        if ( !*v5 )
          break;
        v7 = strchr(v5, 44);
        if ( !v7 )
        {
          v6 = 1;
          v8 = -1;
          do
            ++v8;
          while ( v5[v8] );
          v7 = &v5[(int)v8];
        }
        v9 = v7;
        do
        {
          if ( v7 <= v5 )
            break;
          --v7;
        }
        while ( isspace(*v7) );
        v10 = (_DWORD)v7 - (_DWORD)v5 + 1;
        if ( v10 > 0 )
        {
          if ( *((_DWORD *)this + 74) )
          {
            v4 = STRA::Append((CHECK_ACCESS_HANDLER *)((char *)this + 248), ",");
            if ( v4 < 0 )
              break;
          }
          v4 = STRA::Append((CHECK_ACCESS_HANDLER *)((char *)this + 248), v5, v10);
          if ( v4 < 0 )
            break;
        }
        v5 = v9 + 1;
      }
      while ( !v6 );
    }
  }
  else
  {
    v4 = 0;
  }
  STRA::~STRA((STRA *)v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800028b0  mov     r11, rsp
0x1800028b3  mov     [r11+18h], rbx
0x1800028b7  mov     [r11+20h], rbp
0x1800028bb  push    rsi
0x1800028bc  push    rdi
0x1800028bd  push    r13
0x1800028bf  push    r14
0x1800028c1  push    r15
0x1800028c3  sub     rsp, 80h
0x1800028ca  mov     rax, cs:__security_cookie
0x1800028d1  xor     rax, rsp
0x1800028d4  mov     [rsp+0A8h+var_30], rax
0x1800028d9  mov     r13, rcx
0x1800028dc  mov     qword ptr [r11-70h], 0
0x1800028e4  lea     rcx, [r11-68h]
0x1800028e8  mov     [rsp+0A8h+var_78], 0
0x1800028f0  mov     rbx, rdx
0x1800028f3  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800028f9  mov     rax, [rbx]
0x1800028fc  lea     r9, [rsp+0A8h+var_78]
0x180002901  lea     r8, [rsp+0A8h+var_70]
0x180002906  mov     rcx, rbx
0x180002909  lea     rdx, aHttpXForwarded; "HTTP_X_FORWARDED_FOR"
0x180002910  mov     rax, [rax+78h]
0x180002914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002919  test    eax, eax
0x18000291b  jns     short loc_180002924
0x18000291d  xor     esi, esi
0x18000291f  jmp     loc_1800029FB
0x180002924  mov     rdx, [rsp+0A8h+var_70]
0x180002929  lea     rcx, [rsp+0A8h+var_68]
0x18000292e  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180002934  mov     esi, eax
0x180002936  test    eax, eax
0x180002938  js      loc_1800029FB
0x18000293e  mov     rdi, [rsp+0A8h+Str]
0x180002943  xor     r15d, r15d
0x180002946  movsx   ecx, byte ptr [rdi]; C
0x180002949  call    cs:__imp_isspace
0x18000294f  test    eax, eax
0x180002951  jnz     short loc_180002959
0x180002953  mov     al, [rdi]
0x180002955  cmp     al, 2Ch ; ','
0x180002957  jnz     short loc_18000295E
0x180002959  inc     rdi
0x18000295c  jmp     short loc_180002946
0x18000295e  test    al, al
0x180002960  jz      loc_1800029FB
0x180002966  mov     edx, 2Ch ; ','; Val
0x18000296b  mov     rcx, rdi; Str
0x18000296e  call    cs:__imp_strchr
0x180002974  mov     rbx, rax
0x180002977  test    rax, rax
0x18000297a  jnz     short loc_180002993
0x18000297c  lea     r15d, [rax+1]
0x180002980  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002984  inc     rax
0x180002987  cmp     byte ptr [rdi+rax], 0
0x18000298b  jnz     short loc_180002984
0x18000298d  movsxd  rbx, eax
0x180002990  add     rbx, rdi
0x180002993  mov     r14, rbx
0x180002996  jmp     short loc_1800029A8
0x180002998  dec     rbx
0x18000299b  movsx   ecx, byte ptr [rbx]; C
0x18000299e  call    cs:__imp_isspace
0x1800029a4  test    eax, eax
0x1800029a6  jz      short loc_1800029AD
0x1800029a8  cmp     rbx, rdi
0x1800029ab  ja      short loc_180002998
0x1800029ad  sub     ebx, edi
0x1800029af  lea     ebp, [rbx+1]
0x1800029b2  test    ebp, ebp
0x1800029b4  jle     short loc_1800029EE
0x1800029b6  lea     rbx, [r13+0F8h]
0x1800029bd  cmp     dword ptr [rbx+30h], 0
0x1800029c1  jbe     short loc_1800029D9
0x1800029c3  lea     rdx, asc_180006900; ","
0x1800029ca  mov     rcx, rbx
0x1800029cd  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800029d3  mov     esi, eax
0x1800029d5  test    eax, eax
0x1800029d7  js      short loc_1800029FB
0x1800029d9  mov     r8d, ebp
0x1800029dc  mov     rdx, rdi
0x1800029df  mov     rcx, rbx
0x1800029e2  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x1800029e8  mov     esi, eax
0x1800029ea  test    eax, eax
0x1800029ec  js      short loc_1800029FB
0x1800029ee  lea     rdi, [r14+1]
0x1800029f2  test    r15d, r15d
0x1800029f5  jz      loc_180002946
0x1800029fb  lea     rcx, [rsp+0A8h+var_68]
0x180002a00  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002a06  mov     eax, esi
0x180002a08  mov     rcx, [rsp+0A8h+var_30]
0x180002a0d  xor     rcx, rsp; StackCookie
0x180002a10  call    __security_check_cookie
0x180002a15  lea     r11, [rsp+0A8h+var_28]
0x180002a1d  mov     rbx, [r11+40h]
0x180002a21  mov     rbp, [r11+48h]
0x180002a25  mov     rsp, r11
0x180002a28  pop     r15
0x180002a2a  pop     r14
0x180002a2c  pop     r13
0x180002a2e  pop     rdi
0x180002a2f  pop     rsi
0x180002a30  retn
```
