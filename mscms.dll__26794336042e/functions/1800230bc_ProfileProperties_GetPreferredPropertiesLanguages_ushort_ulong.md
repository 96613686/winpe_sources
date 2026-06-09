# ProfileProperties::GetPreferredPropertiesLanguages(ushort * *,ulong *)

- ea: `0x1800230bc`
- end: `0x18002318b`
- name: `?GetPreferredPropertiesLanguages@ProfileProperties@@YAJPEAPEAGPEAK@Z`
- size: `207`
- prototype: `int(ProfileProperties *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e34`
- `0x18004ee44`

## callees

- `0x1800230bc`
- `0x18002eab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230f2`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1800230e8`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180023137`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1800230e8`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180023137`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x18002315b`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x18002315b`

## pseudocode

```c
__int64 __fastcall ProfileProperties::GetPreferredPropertiesLanguages(WCHAR **this, ULONG *a2, unsigned int *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  __int64 v9; // rax
  ULONG pulNumLanguages; // [rsp+70h] [rbp+18h] BYREF

  pulNumLanguages = 0;
  if ( GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, 0, a2)
    && (v7 = (WCHAR *)operator new[](saturated_mul(*a2, 2u)),
        *this = v7,
        GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, v7, a2)) )
  {
    v8 = *this;
    v6 = 0;
    while ( *v8 && v8 < &(*this)[*a2] )
    {
      CharUpperW(v8);
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v8 += v9 + 1;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x1800230bc  push    rbx
0x1800230be  push    rbp
0x1800230bf  push    rsi
0x1800230c0  push    rdi
0x1800230c1  push    r14
0x1800230c3  push    r15
0x1800230c5  sub     rsp, 28h
0x1800230c9  xor     r14d, r14d
0x1800230cc  mov     rbp, rdx
0x1800230cf  mov     rsi, rcx
0x1800230d2  mov     [rsp+58h+pulNumLanguages], r14d
0x1800230d7  mov     r9, rdx; pcchLanguagesBuffer
0x1800230da  xor     r8d, r8d; pwszLanguagesBuffer
0x1800230dd  lea     rdx, [rsp+58h+pulNumLanguages]; pulNumLanguages
0x1800230e2  lea     ebx, [r14+28h]
0x1800230e6  mov     ecx, ebx; dwFlags
0x1800230e8  call    cs:__imp_GetThreadPreferredUILanguages
0x1800230ee  test    eax, eax
0x1800230f0  jnz     short loc_180023109
0x1800230f2  call    cs:__imp_GetLastError
0x1800230f8  mov     ebx, eax
0x1800230fa  test    eax, eax
0x1800230fc  jle     short loc_18002317C
0x1800230fe  movzx   ebx, ax
0x180023101  or      ebx, 80070000h
0x180023107  jmp     short loc_18002317C
0x180023109  mov     edx, [rbp+0]
0x18002310c  mov     eax, 2
0x180023111  mul     rdx
0x180023114  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002311b  cmovb   rax, r15
0x18002311f  mov     rcx, rax; unsigned __int64
0x180023122  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180023127  mov     r9, rbp; pcchLanguagesBuffer
0x18002312a  mov     [rsi], rax
0x18002312d  mov     r8, rax; pwszLanguagesBuffer
0x180023130  lea     rdx, [rsp+58h+pulNumLanguages]; pulNumLanguages
0x180023135  mov     ecx, ebx; dwFlags
0x180023137  call    cs:__imp_GetThreadPreferredUILanguages
0x18002313d  test    eax, eax
0x18002313f  jz      short loc_1800230F2
0x180023141  mov     rdi, [rsi]
0x180023144  mov     ebx, r14d
0x180023147  jmp     short loc_180023176
0x180023149  mov     ecx, [rbp+0]
0x18002314c  mov     rax, [rsi]
0x18002314f  lea     rcx, [rax+rcx*2]
0x180023153  cmp     rdi, rcx
0x180023156  jnb     short loc_18002317C
0x180023158  mov     rcx, rdi; lpsz
0x18002315b  call    cs:__imp_CharUpperW
0x180023161  mov     rax, r15
0x180023164  inc     rax
0x180023167  cmp     [rdi+rax*2], r14w
0x18002316c  jnz     short loc_180023164
0x18002316e  lea     rdi, [rdi+rax*2]
0x180023172  add     rdi, 2
0x180023176  cmp     [rdi], r14w
0x18002317a  jnz     short loc_180023149
0x18002317c  mov     eax, ebx
0x18002317e  add     rsp, 28h
0x180023182  pop     r15
0x180023184  pop     r14
0x180023186  pop     rdi
0x180023187  pop     rsi
0x180023188  pop     rbp
0x180023189  pop     rbx
0x18002318a  retn
```
