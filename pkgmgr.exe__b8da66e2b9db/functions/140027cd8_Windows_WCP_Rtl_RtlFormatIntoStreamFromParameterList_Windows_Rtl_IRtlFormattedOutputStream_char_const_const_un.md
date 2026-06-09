# Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)

- ea: `0x140027cd8`
- end: `0x140027e95`
- name: `?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z`
- size: `445`
- prototype: `void __fastcall(Windows::WCP::Rtl *this, struct Windows::Rtl::IRtlFormattedOutputStream *, const char *const, __int64)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1400067bc`
- `0x140006de8`
- `0x140006e20`
- `0x140006e70`
- `0x14000979c`
- `0x14000aa44`
- `0x14000aa7c`
- `0x1400125b4`
- `0x140012604`
- `0x140016a8c`

## callees

- `0x140002360`
- `0x140002e4c`
- `0x140027cd8`
- `0x140029bd0`
- `0x14002a010`

## pseudocode

```c
void __fastcall Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
        Windows::WCP::Rtl *this,
        struct Windows::Rtl::IRtlFormattedOutputStream *a2,
        const char *const a3,
        __int64 a4)
{
  char v4; // al
  const char *v5; // rbx
  const char *v8; // rdi
  unsigned __int64 v10; // r12
  __int64 v11; // rdx
  unsigned __int64 v12; // rsi
  char *v13; // rdx
  void (__fastcall *v14)(Windows::WCP::Rtl *, _QWORD); // rax
  char Buffer[16]; // [rsp+20h] [rbp-68h] BYREF
  __int128 v16; // [rsp+30h] [rbp-58h]

  v4 = *(_BYTE *)a2;
  v5 = (char *)a2 + 1;
  v8 = (const char *)a2;
  v10 = 0;
  while ( v4 )
  {
    switch ( v4 )
    {
      case '%':
        if ( ((*v5 - 123) & 0xFD) != 0 )
          goto LABEL_23;
        if ( v5 - 1 != v8 )
          (*(void (__fastcall **)(Windows::WCP::Rtl *, signed __int64, const char *))(*(_QWORD *)this + 280LL))(
            this,
            v5 - v8 - 1,
            v8);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64, const char *))(*(_QWORD *)this + 280LL))(this, 1, v5++);
        break;
      case '{':
        if ( v5 - 1 != v8 )
        {
          v11 = v5 - v8 - 1;
LABEL_21:
          (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64, const char *))(*(_QWORD *)this + 280LL))(this, v11, v8);
        }
        break;
      case '}':
        v12 = v10++;
        if ( v5 - v8 == 1 )
        {
LABEL_17:
          if ( v12 >= (unsigned __int64)a3 )
            goto LABEL_20;
        }
        else
        {
          v12 = 0;
          if ( !a3 )
            goto LABEL_20;
          while ( 1 )
          {
            v13 = *(char **)(a4 + 24 * v12);
            *(_OWORD *)Buffer = 0;
            v16 = 0;
            if ( !v13 )
            {
              sprintf_s(Buffer, 0x20u, "%zu", v12);
              v13 = Buffer;
            }
            if ( !strncmp_0(v8, v13, (unsigned int)((_DWORD)v5 - (_DWORD)v8 - 1)) )
              break;
            if ( ++v12 >= (unsigned __int64)a3 )
              goto LABEL_17;
          }
        }
        v14 = *(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(a4 + 24 * v12 + 8);
        if ( !v14 )
        {
LABEL_20:
          v11 = v5 - v8 - 1;
          goto LABEL_21;
        }
        v14(this, *(_QWORD *)(a4 + 24 * v12 + 16));
        break;
      default:
        goto LABEL_23;
    }
    v8 = v5;
LABEL_23:
    v4 = *v5++;
  }
  if ( v5 - 1 != v8 )
    (*(void (__fastcall **)(Windows::WCP::Rtl *, signed __int64, const char *))(*(_QWORD *)this + 280LL))(
      this,
      v5 - v8 - 1,
      v8);
}

```

## disassembly

```asm
0x140027cd8  mov     [rsp+arg_10], rbx
0x140027cdd  push    rbp
0x140027cde  push    rsi
0x140027cdf  push    rdi
0x140027ce0  push    r12
0x140027ce2  push    r13
0x140027ce4  push    r14
0x140027ce6  push    r15
0x140027ce8  sub     rsp, 50h
0x140027cec  mov     rax, cs:__security_cookie
0x140027cf3  xor     rax, rsp
0x140027cf6  mov     [rsp+88h+var_48], rax
0x140027cfb  mov     al, [rdx]
0x140027cfd  lea     rbx, [rdx+1]
0x140027d01  mov     r13, r9
0x140027d04  mov     r15, r8
0x140027d07  mov     rdi, rdx
0x140027d0a  mov     r14, rcx
0x140027d0d  xor     r12d, r12d
0x140027d10  jmp     loc_140027E43
0x140027d15  cmp     al, 25h ; '%'
0x140027d17  jnz     short loc_140027D6E
0x140027d19  mov     al, [rbx]
0x140027d1b  sub     al, 7Bh ; '{'
0x140027d1d  test    al, 0FDh
0x140027d1f  jnz     loc_140027E3B
0x140027d25  lea     rax, [rbx-1]
0x140027d29  cmp     rax, rdi
0x140027d2c  jz      short loc_140027D4C
0x140027d2e  mov     rax, [r14]
0x140027d31  mov     rdx, rbx
0x140027d34  sub     rdx, rdi
0x140027d37  mov     r8, rdi
0x140027d3a  dec     rdx
0x140027d3d  mov     rcx, r14
0x140027d40  mov     rax, [rax+118h]
0x140027d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027d4c  mov     rax, [r14]
0x140027d4f  mov     r8, rbx
0x140027d52  mov     edx, 1
0x140027d57  mov     rcx, r14
0x140027d5a  mov     rax, [rax+118h]
0x140027d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027d66  inc     rbx
0x140027d69  jmp     loc_140027E38
0x140027d6e  cmp     al, 7Bh ; '{'
0x140027d70  jnz     short loc_140027D8D
0x140027d72  lea     rax, [rbx-1]
0x140027d76  cmp     rax, rdi
0x140027d79  jz      loc_140027E38
0x140027d7f  mov     rdx, rbx
0x140027d82  sub     rdx, rdi
0x140027d85  dec     rdx
0x140027d88  jmp     loc_140027E23
0x140027d8d  cmp     al, 7Dh ; '}'
0x140027d8f  jnz     loc_140027E3B
0x140027d95  mov     rbp, rbx
0x140027d98  mov     rsi, r12
0x140027d9b  sub     rbp, rdi
0x140027d9e  inc     r12
0x140027da1  sub     rbp, 1
0x140027da5  jz      short loc_140027DFE
0x140027da7  xor     esi, esi
0x140027da9  test    r15, r15
0x140027dac  jz      short loc_140027E20
0x140027dae  xorps   xmm0, xmm0
0x140027db1  lea     rax, [rsi+rsi*2]
0x140027db5  mov     rdx, [r13+rax*8+0]
0x140027dba  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x140027dbf  movups  [rsp+88h+var_58], xmm0
0x140027dc4  test    rdx, rdx
0x140027dc7  jnz     short loc_140027DE7
0x140027dc9  mov     r9, rsi
0x140027dcc  lea     r8, aZu; "%zu"
0x140027dd3  mov     edx, 20h ; ' '; BufferCount
0x140027dd8  lea     rcx, [rsp+88h+Buffer]; Buffer
0x140027ddd  call    sprintf_s
0x140027de2  lea     rdx, [rsp+88h+Buffer]; Str2
0x140027de7  mov     r8d, ebp; MaxCount
0x140027dea  mov     rcx, rdi; Str1
0x140027ded  call    strncmp_0
0x140027df2  test    eax, eax
0x140027df4  jz      short loc_140027E03
0x140027df6  inc     rsi
0x140027df9  cmp     rsi, r15
0x140027dfc  jb      short loc_140027DAE
0x140027dfe  cmp     rsi, r15
0x140027e01  jnb     short loc_140027E20
0x140027e03  lea     rdx, [rsi+rsi*2]
0x140027e07  mov     rax, [r13+rdx*8+8]
0x140027e0c  test    rax, rax
0x140027e0f  jz      short loc_140027E20
0x140027e11  mov     rdx, [r13+rdx*8+10h]
0x140027e16  mov     rcx, r14
0x140027e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027e1e  jmp     short loc_140027E38
0x140027e20  mov     rdx, rbp
0x140027e23  mov     rax, [r14]
0x140027e26  mov     r8, rdi
0x140027e29  mov     rcx, r14
0x140027e2c  mov     rax, [rax+118h]
0x140027e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027e38  mov     rdi, rbx
0x140027e3b  mov     rax, rbx
0x140027e3e  mov     al, [rbx]
0x140027e40  inc     rbx
0x140027e43  test    al, al
0x140027e45  jnz     loc_140027D15
0x140027e4b  lea     rax, [rbx-1]
0x140027e4f  cmp     rax, rdi
0x140027e52  jz      short loc_140027E70
0x140027e54  mov     rax, [r14]
0x140027e57  sub     rbx, rdi
0x140027e5a  mov     r8, rdi
0x140027e5d  mov     rcx, r14
0x140027e60  mov     rax, [rax+118h]
0x140027e67  lea     rdx, [rbx-1]
0x140027e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027e70  mov     rcx, [rsp+88h+var_48]
0x140027e75  xor     rcx, rsp; StackCookie
0x140027e78  call    __security_check_cookie
0x140027e7d  mov     rbx, [rsp+88h+arg_10]
0x140027e85  add     rsp, 50h
0x140027e89  pop     r15
0x140027e8b  pop     r14
0x140027e8d  pop     r13
0x140027e8f  pop     r12
0x140027e91  pop     rdi
0x140027e92  pop     rsi
0x140027e93  pop     rbp
0x140027e94  retn
```
