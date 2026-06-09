# CLocalMachine::Initialise(void)

- ea: `0x14004ab3c`
- end: `0x14004ac2f`
- name: `?Initialise@CLocalMachine@@AEAAKXZ`
- size: `243`
- prototype: `unsigned int __fastcall(CLocalMachine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14004ac38`

## callees

- `0x14004a814`
- `0x14004a9f4`
- `0x14004ab3c`
- `0x14005ce46`
- `0x14005ce70`

## import_xrefs

- `msvcrt!wcschr` at `0x14004ab83`
- `msvcrt!wcschr` at `0x14004ab83`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14004abe8`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x14004abe8`

## string_xrefs

- `0x14004abf8`: `DSREPAIR`

## pseudocode

```c
__int64 __fastcall CLocalMachine::Initialise(CLocalMachine *this, __int64 a2, WCHAR *a3, DWORD a4)
{
  unsigned int NameInfoW_0; // ebx
  const wchar_t *v6; // rcx
  wchar_t *v7; // rax
  WCHAR *v8; // r8
  DWORD v9; // r9d
  socklen_t SockaddrLength[2]; // [rsp+20h] [rbp-48h] BYREF
  WCHAR Buffer[8]; // [rsp+28h] [rbp-40h] BYREF
  __int128 v13; // [rsp+38h] [rbp-30h]
  int v14; // [rsp+48h] [rbp-20h]

  NameInfoW_0 = GetNameInfoW_0(
                  (const SOCKADDR *)3,
                  (socklen_t)SockaddrLength,
                  a3,
                  a4,
                  0,
                  *(DWORD *)Buffer,
                  *(INT *)&Buffer[4]);
  if ( !NameInfoW_0 )
  {
    v6 = *(const wchar_t **)SockaddrLength;
    *((_QWORD *)this + 1) = *(_QWORD *)SockaddrLength;
    v7 = wcschr(v6, 0x2Eu);
    if ( v7 )
      *((_QWORD *)this + 3) = v7 + 1;
    NameInfoW_0 = GetNameInfoW_0(
                    0,
                    (socklen_t)SockaddrLength,
                    v8,
                    v9,
                    *(PWCHAR *)SockaddrLength,
                    *(DWORD *)Buffer,
                    *(INT *)&Buffer[4]);
    if ( !NameInfoW_0 )
    {
      *((_QWORD *)this + 2) = *(_QWORD *)SockaddrLength;
      NameInfoW_0 = CLocalMachine::InitAdDomainInfo(this);
      if ( !NameInfoW_0 )
      {
        v14 = 0;
        *(_OWORD *)Buffer = 0;
        v13 = 0;
        if ( GetEnvironmentVariableW(L"SAFEBOOT_OPTION", Buffer, 0x12u) )
        {
          if ( !wcscmp_0(Buffer, L"DSREPAIR") )
            *((_DWORD *)this + 10) = 1;
        }
      }
    }
  }
  return NameInfoW_0;
}

```

## disassembly

```asm
0x14004ab3c  mov     [rsp+arg_8], rbx
0x14004ab41  push    rdi
0x14004ab42  sub     rsp, 60h
0x14004ab46  mov     rax, cs:__security_cookie
0x14004ab4d  xor     rax, rsp
0x14004ab50  mov     [rsp+68h+var_18], rax
0x14004ab55  and     qword ptr [rsp+68h+SockaddrLength], 0
0x14004ab5b  lea     rdx, [rsp+68h+SockaddrLength]; SockaddrLength
0x14004ab60  mov     rdi, rcx
0x14004ab63  mov     ecx, 3; pSockaddr
0x14004ab68  call    GetNameInfoW_0
0x14004ab6d  mov     ebx, eax
0x14004ab6f  test    eax, eax
0x14004ab71  jnz     loc_14004AC14
0x14004ab77  mov     rcx, qword ptr [rsp+68h+SockaddrLength]; Str
0x14004ab7c  lea     edx, [rax+2Eh]; Ch
0x14004ab7f  mov     [rdi+8], rcx
0x14004ab83  call    cs:__imp_wcschr
0x14004ab8a  nop     dword ptr [rax+rax+00h]
0x14004ab8f  test    rax, rax
0x14004ab92  jz      short loc_14004AB9C
0x14004ab94  add     rax, 2
0x14004ab98  mov     [rdi+18h], rax
0x14004ab9c  lea     rdx, [rsp+68h+SockaddrLength]; SockaddrLength
0x14004aba1  xor     ecx, ecx; pSockaddr
0x14004aba3  call    GetNameInfoW_0
0x14004aba8  mov     ebx, eax
0x14004abaa  test    eax, eax
0x14004abac  jnz     short loc_14004AC14
0x14004abae  mov     rax, qword ptr [rsp+68h+SockaddrLength]
0x14004abb3  mov     rcx, rdi; this
0x14004abb6  mov     [rdi+10h], rax
0x14004abba  call    ?InitAdDomainInfo@CLocalMachine@@AEAAKXZ; CLocalMachine::InitAdDomainInfo(void)
0x14004abbf  mov     ebx, eax
0x14004abc1  test    eax, eax
0x14004abc3  jnz     short loc_14004AC14
0x14004abc5  xorps   xmm0, xmm0
0x14004abc8  lea     r8d, [rbx+12h]; nSize
0x14004abcc  xor     eax, eax
0x14004abce  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x14004abd3  lea     rcx, Name; "SAFEBOOT_OPTION"
0x14004abda  mov     [rsp+68h+var_20], eax
0x14004abde  movups  xmmword ptr [rsp+68h+Buffer], xmm0
0x14004abe3  movups  [rsp+68h+var_30], xmm0
0x14004abe8  call    cs:__imp_GetEnvironmentVariableW
0x14004abef  nop     dword ptr [rax+rax+00h]
0x14004abf4  test    eax, eax
0x14004abf6  jz      short loc_14004AC14
0x14004abf8  lea     rdx, aDsrepair; "DSREPAIR"
0x14004abff  lea     rcx, [rsp+68h+Buffer]; String1
0x14004ac04  call    wcscmp_0
0x14004ac09  test    eax, eax
0x14004ac0b  jnz     short loc_14004AC14
0x14004ac0d  mov     dword ptr [rdi+28h], 1
0x14004ac14  mov     eax, ebx
0x14004ac16  mov     rcx, [rsp+68h+var_18]
0x14004ac1b  xor     rcx, rsp; StackCookie
0x14004ac1e  call    __security_check_cookie
0x14004ac23  mov     rbx, [rsp+68h+arg_8]
0x14004ac28  add     rsp, 60h
0x14004ac2c  pop     rdi
0x14004ac2d  retn
```
