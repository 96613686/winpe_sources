# REGUTIL::EnvGetString(ushort const *,int)

- ea: `0x18007aa1c`
- end: `0x18007ab73`
- name: `?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z`
- size: `343`
- prototype: `unsigned __int16 *__fastcall(wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007abac`

## callees

- `0x18007262c`
- `0x18007aa1c`
- `0x1800f0d20`
- `0x1800f9348`
- `0x1800f9ac8`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x18007ab09`
- `KERNEL32!GetEnvironmentVariableW` at `0x18007ab3d`
- `KERNEL32!GetEnvironmentVariableW` at `0x18007ab09`
- `KERNEL32!GetEnvironmentVariableW` at `0x18007ab3d`

## string_xrefs

- `0x18007aad4`: `COMPlus_`

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
      v8 = *((_DWORD *)qword_180163DD8 + ((unsigned __int64)v6 >> 5));
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
  v12 = (WCHAR *)operator new(v11, *((const struct NoThrow **)&v11 + 1));
  v13 = v12;
  if ( v12 )
    GetEnvironmentVariableW(Destination, v12, v10);
  return v13;
}

```

## disassembly

```asm
0x18007aa1c  mov     [rsp+arg_8], rbx
0x18007aa21  mov     [rsp+arg_10], rbp
0x18007aa26  mov     [rsp+arg_18], rsi
0x18007aa2b  push    rdi
0x18007aa2c  sub     rsp, 0B0h
0x18007aa33  mov     rax, cs:__security_cookie
0x18007aa3a  xor     rax, rsp
0x18007aa3d  mov     [rsp+0B8h+var_18], rax
0x18007aa45  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18007aa49  mov     rbx, rcx
0x18007aa4c  mov     r8, rbp
0x18007aa4f  xor     esi, esi
0x18007aa51  inc     r8
0x18007aa54  cmp     [rcx+r8*2], si
0x18007aa59  jnz     short loc_18007AA51
0x18007aa5b  mov     eax, edx
0x18007aa5d  neg     eax
0x18007aa5f  sbb     rcx, rcx
0x18007aa62  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18007aa66  add     rcx, 3Fh ; '?'
0x18007aa6a  cmp     r8, rcx
0x18007aa6d  ja      loc_18007AB48
0x18007aa73  mov     edi, 40h ; '@'
0x18007aa78  test    edx, edx
0x18007aa7a  jz      short loc_18007AAEA
0x18007aa7c  cmp     cs:?s_fUseEnvCache@REGUTIL@@0HA, esi; int REGUTIL::s_fUseEnvCache
0x18007aa82  jz      short loc_18007AAD4
0x18007aa84  movzx   edx, word ptr [rbx]
0x18007aa87  mov     r9, rbx
0x18007aa8a  mov     r8d, 1505h
0x18007aa90  jmp     short loc_18007AAB2
0x18007aa92  lea     eax, [rdx-61h]
0x18007aa95  mov     ecx, edx
0x18007aa97  and     ecx, 0FFFFFFDFh
0x18007aa9a  lea     r9, [r9+2]
0x18007aa9e  cmp     eax, 19h
0x18007aaa1  cmova   ecx, edx
0x18007aaa4  movzx   edx, word ptr [r9]
0x18007aaa8  imul    eax, r8d, 21h ; '!'
0x18007aaac  mov     r8d, ecx
0x18007aaaf  xor     r8d, eax
0x18007aab2  test    edx, edx
0x18007aab4  jnz     short loc_18007AA92
0x18007aab6  movzx   ecx, r8b
0x18007aaba  mov     eax, ecx
0x18007aabc  mov     edx, ecx
0x18007aabe  shr     rax, 5
0x18007aac2  lea     rcx, qword_180163DD8
0x18007aac9  and     edx, 1Fh
0x18007aacc  mov     eax, [rcx+rax*4]
0x18007aacf  bt      eax, edx
0x18007aad2  jnb     short loc_18007AB48
0x18007aad4  lea     r8, aComplus; "COMPlus_"
0x18007aadb  mov     rdx, rdi; SizeInWords
0x18007aade  lea     rcx, [rsp+0B8h+Destination]; Destination
0x18007aae3  call    wcscpy_s
0x18007aae8  jmp     short loc_18007AAEF
0x18007aaea  mov     [rsp+0B8h+Destination], si
0x18007aaef  mov     r8, rbx; Source
0x18007aaf2  lea     rcx, [rsp+0B8h+Destination]; Destination
0x18007aaf7  mov     rdx, rdi; SizeInWords
0x18007aafa  call    wcscat_s
0x18007aaff  xor     r8d, r8d; nSize
0x18007ab02  lea     rcx, [rsp+0B8h+Destination]; lpName
0x18007ab07  xor     edx, edx; lpBuffer
0x18007ab09  call    cs:__imp_GetEnvironmentVariableW
0x18007ab0f  movsxd  rdi, eax
0x18007ab12  test    eax, eax
0x18007ab14  jz      short loc_18007AB48
0x18007ab16  mov     eax, 2
0x18007ab1b  mul     rdi
0x18007ab1e  cmovo   rax, rbp
0x18007ab22  mov     rcx, rax; dwBytes
0x18007ab25  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18007ab2a  mov     rbx, rax
0x18007ab2d  test    rax, rax
0x18007ab30  jz      short loc_18007AB43
0x18007ab32  mov     r8d, edi; nSize
0x18007ab35  lea     rcx, [rsp+0B8h+Destination]; lpName
0x18007ab3a  mov     rdx, rax; lpBuffer
0x18007ab3d  call    cs:__imp_GetEnvironmentVariableW
0x18007ab43  mov     rax, rbx
0x18007ab46  jmp     short loc_18007AB4A
0x18007ab48  xor     eax, eax
0x18007ab4a  mov     rcx, [rsp+0B8h+var_18]
0x18007ab52  xor     rcx, rsp; StackCookie
0x18007ab55  call    __security_check_cookie
0x18007ab5a  lea     r11, [rsp+0B8h+var_8]
0x18007ab62  mov     rbx, [r11+18h]
0x18007ab66  mov     rbp, [r11+20h]
0x18007ab6a  mov     rsi, [r11+28h]
0x18007ab6e  mov     rsp, r11
0x18007ab71  pop     rdi
0x18007ab72  retn
```
