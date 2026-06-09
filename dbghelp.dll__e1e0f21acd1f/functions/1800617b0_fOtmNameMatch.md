# fOtmNameMatch

- ea: `0x1800617b0`
- end: `0x1800618c3`
- name: `fOtmNameMatch`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005e640`

## callees

- `0x1800617b0`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180061834`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006188a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180061834`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006188a`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x180061859`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x180061872`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x180061859`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x180061872`

## pseudocode

```c
char __fastcall fOtmNameMatch(char a1, char a2, char a3, const wchar_t *a4, wchar_t *Path)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  wchar_t *v13; // rcx
  wchar_t *v14; // rdx
  wchar_t v16[264]; // [rsp+20h] [rbp-438h] BYREF
  wchar_t Buffer[264]; // [rsp+230h] [rbp-228h] BYREF

  if ( !Path )
    return 0;
  if ( a1 )
  {
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = v9 + 1;
    do
      ++v8;
    while ( Path[v8] );
    v11 = v8 + 1;
    if ( v11 < v10 )
      return 0;
    v12 = v11 - v10;
    v13 = (wchar_t *)a4;
    v14 = &Path[v12];
    goto LABEL_15;
  }
  if ( !(unsigned int)_o__wcsicmp(Path, a4) )
    return 1;
  if ( !a2 && a3 && _wfullpath(Buffer, a4, 0x104u) && _wfullpath(v16, Path, 0x104u) )
  {
    v14 = v16;
    v13 = Buffer;
LABEL_15:
    if ( !(unsigned int)_o__wcsicmp(v13, v14) )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800617b0  mov     [rsp+arg_0], rbx
0x1800617b5  mov     [rsp+arg_8], rbp
0x1800617ba  mov     [rsp+arg_10], rsi
0x1800617bf  push    rdi
0x1800617c0  sub     rsp, 450h
0x1800617c7  mov     rax, cs:__security_cookie
0x1800617ce  xor     rax, rsp
0x1800617d1  mov     [rsp+458h+var_18], rax
0x1800617d9  mov     rbx, [rsp+458h+Path]
0x1800617e1  mov     rdi, r9
0x1800617e4  movzx   esi, r8b
0x1800617e8  movzx   ebp, dl
0x1800617eb  test    rbx, rbx
0x1800617ee  jz      loc_180061898
0x1800617f4  test    cl, cl
0x1800617f6  jz      short loc_18006182E
0x1800617f8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800617ff  mov     rcx, rax
0x180061802  inc     rcx
0x180061805  cmp     word ptr [r9+rcx*2], 0
0x18006180b  jnz     short loc_180061802
0x18006180d  inc     rcx
0x180061810  inc     rax
0x180061813  cmp     word ptr [rbx+rax*2], 0
0x180061818  jnz     short loc_180061810
0x18006181a  inc     rax
0x18006181d  cmp     rax, rcx
0x180061820  jb      short loc_180061898
0x180061822  sub     rax, rcx
0x180061825  mov     rcx, rdi
0x180061828  lea     rdx, [rbx+rax*2]
0x18006182c  jmp     short loc_18006188A
0x18006182e  mov     rdx, rdi
0x180061831  mov     rcx, rbx
0x180061834  call    cs:__imp__o__wcsicmp
0x18006183a  test    eax, eax
0x18006183c  jz      short loc_180061894
0x18006183e  test    bpl, bpl
0x180061841  jnz     short loc_180061898
0x180061843  test    sil, sil
0x180061846  jz      short loc_180061898
0x180061848  mov     r8d, 104h; BufferCount
0x18006184e  lea     rcx, [rsp+458h+Buffer]; Buffer
0x180061856  mov     rdx, rdi; Path
0x180061859  call    cs:__imp__wfullpath
0x18006185f  test    rax, rax
0x180061862  jz      short loc_180061898
0x180061864  mov     r8d, 104h; BufferCount
0x18006186a  lea     rcx, [rsp+458h+var_438]; Buffer
0x18006186f  mov     rdx, rbx; Path
0x180061872  call    cs:__imp__wfullpath
0x180061878  test    rax, rax
0x18006187b  jz      short loc_180061898
0x18006187d  lea     rdx, [rsp+458h+var_438]
0x180061882  lea     rcx, [rsp+458h+Buffer]
0x18006188a  call    cs:__imp__o__wcsicmp
0x180061890  test    eax, eax
0x180061892  jnz     short loc_180061898
0x180061894  mov     al, 1
0x180061896  jmp     short loc_18006189A
0x180061898  xor     al, al
0x18006189a  mov     rcx, [rsp+458h+var_18]
0x1800618a2  xor     rcx, rsp; StackCookie
0x1800618a5  call    __security_check_cookie
0x1800618aa  lea     r11, [rsp+458h+var_8]
0x1800618b2  mov     rbx, [r11+10h]
0x1800618b6  mov     rbp, [r11+18h]
0x1800618ba  mov     rsi, [r11+20h]
0x1800618be  mov     rsp, r11
0x1800618c1  pop     rdi
0x1800618c2  retn
```
