# REGUTIL::EnvGetString(ushort const *,int)

- ea: `0x180036ca0`
- end: `0x180036df9`
- name: `?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z`
- size: `345`
- prototype: `unsigned __int16 *__fastcall(wchar_t *Source, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180036dfc`
- `0x180036fd0`

## callees

- `0x180030530`
- `0x180036ca0`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x180036d8f`
- `KERNEL32!GetEnvironmentVariableW` at `0x180036dc3`
- `KERNEL32!GetEnvironmentVariableW` at `0x180036d8f`
- `KERNEL32!GetEnvironmentVariableW` at `0x180036dc3`
- `ucrtbase_clr0400!wcscat_s` at `0x180036d7f`
- `ucrtbase_clr0400!wcscat_s` at `0x180036d7f`
- `ucrtbase_clr0400!wcscpy_s` at `0x180036d67`
- `ucrtbase_clr0400!wcscpy_s` at `0x180036d67`

## string_xrefs

- `0x180036d58`: `COMPlus_`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
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
      v8 = *((_DWORD *)qword_18006FE48 + ((unsigned __int64)v6 >> 5));
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
0x180036ca0  mov     [rsp+arg_8], rbx
0x180036ca5  mov     [rsp+arg_10], rbp
0x180036caa  mov     [rsp+arg_18], rsi
0x180036caf  push    rdi
0x180036cb0  sub     rsp, 0B0h
0x180036cb7  mov     rax, cs:__security_cookie
0x180036cbe  xor     rax, rsp
0x180036cc1  mov     [rsp+0B8h+var_18], rax
0x180036cc9  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180036ccd  mov     rbx, rcx
0x180036cd0  mov     r8, rbp
0x180036cd3  xor     esi, esi
0x180036cd5  inc     r8
0x180036cd8  cmp     [rcx+r8*2], si
0x180036cdd  jnz     short loc_180036CD5
0x180036cdf  mov     eax, edx
0x180036ce1  neg     eax
0x180036ce3  sbb     rcx, rcx
0x180036ce6  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180036cea  add     rcx, 3Fh ; '?'
0x180036cee  cmp     r8, rcx
0x180036cf1  ja      loc_180036DCE
0x180036cf7  mov     edi, 40h ; '@'
0x180036cfc  test    edx, edx
0x180036cfe  jz      short loc_180036D6F
0x180036d00  cmp     cs:?s_fUseEnvCache@REGUTIL@@0HA, esi; int REGUTIL::s_fUseEnvCache
0x180036d06  jz      short loc_180036D58
0x180036d08  movzx   edx, word ptr [rbx]
0x180036d0b  mov     r9, rbx
0x180036d0e  mov     r8d, 1505h
0x180036d14  jmp     short loc_180036D36
0x180036d16  lea     eax, [rdx-61h]
0x180036d19  mov     ecx, edx
0x180036d1b  and     ecx, 0FFFFFFDFh
0x180036d1e  lea     r9, [r9+2]
0x180036d22  cmp     eax, 19h
0x180036d25  cmova   ecx, edx
0x180036d28  movzx   edx, word ptr [r9]
0x180036d2c  imul    eax, r8d, 21h ; '!'
0x180036d30  mov     r8d, ecx
0x180036d33  xor     r8d, eax
0x180036d36  test    edx, edx
0x180036d38  jnz     short loc_180036D16
0x180036d3a  movzx   ecx, r8b
0x180036d3e  mov     eax, ecx
0x180036d40  mov     edx, ecx
0x180036d42  shr     rax, 5
0x180036d46  lea     rcx, qword_18006FE48
0x180036d4d  and     edx, 1Fh
0x180036d50  mov     eax, [rcx+rax*4]
0x180036d53  bt      eax, edx
0x180036d56  jnb     short loc_180036DCE
0x180036d58  lea     r8, aComplus; "COMPlus_"
0x180036d5f  mov     rdx, rdi; SizeInWords
0x180036d62  lea     rcx, [rsp+0B8h+Destination]; Destination
0x180036d67  call    cs:__imp_wcscpy_s
0x180036d6d  jmp     short loc_180036D74
0x180036d6f  mov     [rsp+0B8h+Destination], si
0x180036d74  mov     r8, rbx; Source
0x180036d77  lea     rcx, [rsp+0B8h+Destination]; Destination
0x180036d7c  mov     rdx, rdi; SizeInWords
0x180036d7f  call    cs:__imp_wcscat_s
0x180036d85  xor     r8d, r8d; nSize
0x180036d88  lea     rcx, [rsp+0B8h+Destination]; lpName
0x180036d8d  xor     edx, edx; lpBuffer
0x180036d8f  call    cs:__imp_GetEnvironmentVariableW
0x180036d95  movsxd  rdi, eax
0x180036d98  test    eax, eax
0x180036d9a  jz      short loc_180036DCE
0x180036d9c  mov     eax, 2
0x180036da1  mul     rdi
0x180036da4  cmovo   rax, rbp
0x180036da8  mov     rcx, rax; dwBytes
0x180036dab  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180036db0  mov     rbx, rax
0x180036db3  test    rax, rax
0x180036db6  jz      short loc_180036DC9
0x180036db8  mov     r8d, edi; nSize
0x180036dbb  lea     rcx, [rsp+0B8h+Destination]; lpName
0x180036dc0  mov     rdx, rax; lpBuffer
0x180036dc3  call    cs:__imp_GetEnvironmentVariableW
0x180036dc9  mov     rax, rbx
0x180036dcc  jmp     short loc_180036DD0
0x180036dce  xor     eax, eax
0x180036dd0  mov     rcx, [rsp+0B8h+var_18]
0x180036dd8  xor     rcx, rsp; StackCookie
0x180036ddb  call    __security_check_cookie
0x180036de0  lea     r11, [rsp+0B8h+var_8]
0x180036de8  mov     rbx, [r11+18h]
0x180036dec  mov     rbp, [r11+20h]
0x180036df0  mov     rsi, [r11+28h]
0x180036df4  mov     rsp, r11
0x180036df7  pop     rdi
0x180036df8  retn
```
