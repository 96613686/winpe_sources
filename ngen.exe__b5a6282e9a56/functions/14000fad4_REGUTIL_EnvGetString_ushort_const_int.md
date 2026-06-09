# REGUTIL::EnvGetString(ushort const *,int)

- ea: `0x14000fad4`
- end: `0x14000fc2d`
- name: `?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z`
- size: `345`
- prototype: `unsigned __int16 *__fastcall(wchar_t *Source, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000fc30`
- `0x14000fe04`

## callees

- `0x14000a0d4`
- `0x14000fad4`
- `0x140013200`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x14000fbc3`
- `KERNEL32!GetEnvironmentVariableW` at `0x14000fbf7`
- `KERNEL32!GetEnvironmentVariableW` at `0x14000fbc3`
- `KERNEL32!GetEnvironmentVariableW` at `0x14000fbf7`
- `ucrtbase_clr0400!wcscat_s` at `0x14000fbb3`
- `ucrtbase_clr0400!wcscat_s` at `0x14000fbb3`
- `ucrtbase_clr0400!wcscpy_s` at `0x14000fb9b`
- `ucrtbase_clr0400!wcscpy_s` at `0x14000fb9b`

## string_xrefs

- `0x14000fb8c`: `COMPlus_`

## pseudocode

```c
unsigned __int16 *__fastcall REGUTIL::EnvGetString(wchar_t *Source, int a2)
{
  unsigned __int64 v3; // r8
  int v4; // edx
  wchar_t *v5; // r9
  unsigned __int8 v6; // r8
  char v7; // cl
  int v8; // eax
  signed int EnvironmentVariableW; // eax
  unsigned __int64 v10; // rdi
  unsigned __int128 v11; // rax
  WCHAR *v12; // rax
  WCHAR *v13; // rbx
  wchar_t Destination[64]; // [rsp+20h] [rbp-98h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( Source[v3] );
  if ( v3 > (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 63 )
    return 0;
  if ( a2 )
  {
    if ( REGUTIL::s_fUseEnvCache )
    {
      v4 = *Source;
      v5 = Source;
      v6 = 5;
      while ( v4 )
      {
        v7 = v4 & 0xDF;
        ++v5;
        if ( (unsigned int)(v4 - 97) > 0x19 )
          v7 = v4;
        v4 = *v5;
        v6 = (33 * v6) ^ v7;
      }
      v8 = *((_DWORD *)qword_140027980 + ((unsigned __int64)v6 >> 5));
      if ( !_bittest(&v8, v6 & 0x1F) )
        return 0;
    }
    wcscpy_s(Destination, 0x40u, L"COMPlus_");
  }
  else
  {
    Destination[0] = 0;
  }
  wcscat_s(Destination, 0x40u, Source);
  EnvironmentVariableW = GetEnvironmentVariableW(Destination, 0, 0);
  v10 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
    return 0;
  v11 = (unsigned __int64)EnvironmentVariableW * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v10, 2u) )
    *(_QWORD *)&v11 = -1;
  v12 = (WCHAR *)operator new[](v11, *((const struct NoThrow **)&v11 + 1));
  v13 = v12;
  if ( v12 )
    GetEnvironmentVariableW(Destination, v12, v10);
  return v13;
}

```

## disassembly

```asm
0x14000fad4  mov     [rsp+arg_8], rbx
0x14000fad9  mov     [rsp+arg_10], rbp
0x14000fade  mov     [rsp+arg_18], rsi
0x14000fae3  push    rdi
0x14000fae4  sub     rsp, 0B0h
0x14000faeb  mov     rax, cs:__security_cookie
0x14000faf2  xor     rax, rsp
0x14000faf5  mov     [rsp+0B8h+var_18], rax
0x14000fafd  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000fb01  mov     rbx, rcx
0x14000fb04  mov     r8, rbp
0x14000fb07  xor     esi, esi
0x14000fb09  inc     r8
0x14000fb0c  cmp     [rcx+r8*2], si
0x14000fb11  jnz     short loc_14000FB09
0x14000fb13  mov     eax, edx
0x14000fb15  neg     eax
0x14000fb17  sbb     rcx, rcx
0x14000fb1a  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14000fb1e  add     rcx, 3Fh ; '?'
0x14000fb22  cmp     r8, rcx
0x14000fb25  ja      loc_14000FC02
0x14000fb2b  mov     edi, 40h ; '@'
0x14000fb30  test    edx, edx
0x14000fb32  jz      short loc_14000FBA3
0x14000fb34  cmp     cs:?s_fUseEnvCache@REGUTIL@@0HA, esi; int REGUTIL::s_fUseEnvCache
0x14000fb3a  jz      short loc_14000FB8C
0x14000fb3c  movzx   edx, word ptr [rbx]
0x14000fb3f  mov     r9, rbx
0x14000fb42  mov     r8d, 1505h
0x14000fb48  jmp     short loc_14000FB6A
0x14000fb4a  lea     eax, [rdx-61h]
0x14000fb4d  mov     ecx, edx
0x14000fb4f  and     ecx, 0FFFFFFDFh
0x14000fb52  lea     r9, [r9+2]
0x14000fb56  cmp     eax, 19h
0x14000fb59  cmova   ecx, edx
0x14000fb5c  movzx   edx, word ptr [r9]
0x14000fb60  imul    eax, r8d, 21h ; '!'
0x14000fb64  mov     r8d, ecx
0x14000fb67  xor     r8d, eax
0x14000fb6a  test    edx, edx
0x14000fb6c  jnz     short loc_14000FB4A
0x14000fb6e  movzx   ecx, r8b
0x14000fb72  mov     eax, ecx
0x14000fb74  mov     edx, ecx
0x14000fb76  shr     rax, 5
0x14000fb7a  lea     rcx, qword_140027980
0x14000fb81  and     edx, 1Fh
0x14000fb84  mov     eax, [rcx+rax*4]
0x14000fb87  bt      eax, edx
0x14000fb8a  jnb     short loc_14000FC02
0x14000fb8c  lea     r8, aComplus; "COMPlus_"
0x14000fb93  mov     rdx, rdi; SizeInWords
0x14000fb96  lea     rcx, [rsp+0B8h+Destination]; Destination
0x14000fb9b  call    cs:__imp_wcscpy_s
0x14000fba1  jmp     short loc_14000FBA8
0x14000fba3  mov     [rsp+0B8h+Destination], si
0x14000fba8  mov     r8, rbx; Source
0x14000fbab  lea     rcx, [rsp+0B8h+Destination]; Destination
0x14000fbb0  mov     rdx, rdi; SizeInWords
0x14000fbb3  call    cs:__imp_wcscat_s
0x14000fbb9  xor     r8d, r8d; nSize
0x14000fbbc  lea     rcx, [rsp+0B8h+Destination]; lpName
0x14000fbc1  xor     edx, edx; lpBuffer
0x14000fbc3  call    cs:__imp_GetEnvironmentVariableW
0x14000fbc9  movsxd  rdi, eax
0x14000fbcc  test    eax, eax
0x14000fbce  jz      short loc_14000FC02
0x14000fbd0  mov     eax, 2
0x14000fbd5  mul     rdi
0x14000fbd8  cmovo   rax, rbp
0x14000fbdc  mov     rcx, rax; dwBytes
0x14000fbdf  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x14000fbe4  mov     rbx, rax
0x14000fbe7  test    rax, rax
0x14000fbea  jz      short loc_14000FBFD
0x14000fbec  mov     r8d, edi; nSize
0x14000fbef  lea     rcx, [rsp+0B8h+Destination]; lpName
0x14000fbf4  mov     rdx, rax; lpBuffer
0x14000fbf7  call    cs:__imp_GetEnvironmentVariableW
0x14000fbfd  mov     rax, rbx
0x14000fc00  jmp     short loc_14000FC04
0x14000fc02  xor     eax, eax
0x14000fc04  mov     rcx, [rsp+0B8h+var_18]
0x14000fc0c  xor     rcx, rsp; StackCookie
0x14000fc0f  call    __security_check_cookie
0x14000fc14  lea     r11, [rsp+0B8h+var_8]
0x14000fc1c  mov     rbx, [r11+18h]
0x14000fc20  mov     rbp, [r11+20h]
0x14000fc24  mov     rsi, [r11+28h]
0x14000fc28  mov     rsp, r11
0x14000fc2b  pop     rdi
0x14000fc2c  retn
```
