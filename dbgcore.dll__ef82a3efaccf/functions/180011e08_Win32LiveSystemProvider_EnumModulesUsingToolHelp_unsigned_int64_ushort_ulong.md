# Win32LiveSystemProvider::EnumModulesUsingToolHelp(unsigned __int64 *,ushort *,ulong)

- ea: `0x180011e08`
- end: `0x18001213a`
- name: `?EnumModulesUsingToolHelp@Win32LiveSystemProvider@@AEAAJPEA_KPEAGK@Z`
- size: `818`
- prototype: `int __fastcall(__int64 (__fastcall **this)(__int64, wchar_t *), unsigned __int64 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800119d0`

## callees

- `0x180001710`
- `0x1800021d0`
- `0x1800021f4`
- `0x180011e08`
- `0x180014950`
- `0x18001bec8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180012051`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180012068`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001207f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800120dc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180012051`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180012068`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001207f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800120dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f0b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011ef3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011ef3`

## string_xrefs

- `0x1800120d0`: `system32`

## pseudocode

```c
int __fastcall Win32LiveSystemProvider::EnumModulesUsingToolHelp(
        __int64 (__fastcall **this)(__int64, wchar_t *),
        unsigned __int64 *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 (__fastcall *v8)(__int64, wchar_t *); // rdi
  __int64 (__fastcall *v9)(__int64, wchar_t *); // rsi
  __int64 (__fastcall *v10)(__int64, wchar_t *); // rax
  int v11; // eax
  unsigned __int64 v12; // rax
  int result; // eax
  __int64 (__fastcall *v14)(__int64, wchar_t *); // rcx
  int v15; // eax
  unsigned __int64 v16; // rax
  __int64 (__fastcall *v17)(__int64, wchar_t *); // rax
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rsi
  unsigned int i; // r14d
  __int64 v21; // rbx
  wchar_t v22; // ax
  unsigned int j; // esi
  __int64 v24; // rbx
  wchar_t v25; // ax
  wchar_t Str[2]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v27[5]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v28; // [rsp+48h] [rbp-B8h]
  CHAR MultiByteStr[272]; // [rsp+160h] [rbp+60h] BYREF
  int v30; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v31[20]; // [rsp+274h] [rbp+174h] BYREF
  unsigned __int64 v32; // [rsp+288h] [rbp+188h]
  __int64 v33; // [rsp+298h] [rbp+198h]
  unsigned __int16 v34[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  if ( !*((_DWORD *)this + 170) )
  {
    if ( this[37] && this[38] )
    {
      result = Win32LiveSystemProvider::LoadPsApi((Win32LiveSystemProvider *)this);
      if ( result )
        return result;
      memset_0(v31, 0, 0x434u);
      v14 = this[84];
      v30 = 1080;
      if ( *((_DWORD *)this + 172) )
        v15 = this[38]((__int64)v14, (wchar_t *)&v30);
      else
        v15 = this[37]((__int64)v14, (wchar_t *)&v30);
      if ( v15 )
      {
        v16 = v32;
        ++*((_DWORD *)this + 172);
        *a2 = v16;
        v17 = this[64];
        if ( !v17
          || !((unsigned int (__fastcall *)(__int64 (__fastcall *)(__int64, wchar_t *), __int64, unsigned __int16 *, _QWORD))v17)(
                this[82],
                v33,
                a3,
                a4) )
        {
          return GenStrCopyNW(a3, v34, a4) == 0 ? 0x80070057 : 0;
        }
        v18 = -1;
        v19 = -1;
        do
          ++v19;
        while ( v34[v19] );
        memset_0(Str, 0, 0x20Au);
        for ( i = 0; i < v19; Str[v21] = v22 )
        {
          if ( i >= 0x104 )
            break;
          v21 = i;
          v22 = o_towlower_0(v34[i++]);
        }
        if ( wcsstr(Str, L"syswow64") || wcsstr(Str, L"sysarm32") || wcsstr(Str, L"sychpe32") )
        {
          do
            ++v18;
          while ( a3[v18] );
          memset_0(Str, 0, 0x20Au);
          for ( j = 0; j < v18; Str[v24] = v25 )
          {
            if ( j >= 0x104 )
              break;
            v24 = j;
            v25 = o_towlower_0(a3[j++]);
          }
          if ( wcsstr(Str, L"system32") )
            return GenStrCopyNW(a3, v34, a4) == 0 ? 0x80070057 : 0;
        }
        return 0;
      }
      return 1;
    }
    return -2147467263;
  }
  v8 = this[35];
  if ( !v8 )
    return -2147467263;
  v9 = this[36];
  if ( !v9 )
    return -2147467263;
  memset_0(v27, 0, 0x234u);
  v10 = this[84];
  wcscpy(Str, L"ȸ");
  if ( *((_DWORD *)this + 172) )
  {
    v27[0] = *((_DWORD *)this + 173);
    v11 = v9((__int64)v10, Str);
  }
  else
  {
    v11 = v8((__int64)v10, Str);
  }
  if ( !v11 )
    return 1;
  v12 = v28;
  ++*((_DWORD *)this + 172);
  *a2 = v12;
  *((_DWORD *)this + 173) = v27[0];
  if ( MultiByteToWideChar(0, 0, MultiByteStr, -1, a3, a4) )
    return 0;
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180011e08  push    rbp
0x180011e0a  push    rbx
0x180011e0b  push    rsi
0x180011e0c  push    rdi
0x180011e0d  push    r12
0x180011e0f  push    r13
0x180011e11  push    r14
0x180011e13  push    r15
0x180011e15  lea     rbp, [rsp-5C8h]
0x180011e1d  sub     rsp, 6C8h
0x180011e24  mov     rax, cs:__security_cookie
0x180011e2b  xor     rax, rsp
0x180011e2e  mov     [rbp+600h+var_50], rax
0x180011e35  xor     r13d, r13d
0x180011e38  mov     r12d, r9d
0x180011e3b  mov     r15, r8
0x180011e3e  mov     r14, rdx
0x180011e41  mov     rbx, rcx
0x180011e44  cmp     [rcx+2A8h], r13d
0x180011e4b  jz      loc_180011F30
0x180011e51  mov     rdi, [rcx+118h]
0x180011e58  test    rdi, rdi
0x180011e5b  jz      loc_180012112
0x180011e61  mov     rsi, [rcx+120h]
0x180011e68  test    rsi, rsi
0x180011e6b  jz      loc_180012112
0x180011e71  xor     edx, edx; Val
0x180011e73  lea     rcx, [rsp+700h+var_6CC]; void *
0x180011e78  mov     r8d, 234h; Size
0x180011e7e  call    memset_0
0x180011e83  lea     rdx, [rsp+700h+Str]
0x180011e88  mov     rax, [rbx+2A0h]
0x180011e8f  mov     dword ptr [rsp+700h+Str], 238h
0x180011e97  cmp     [rbx+2B0h], r13d
0x180011e9e  jnz     short loc_180011EA8
0x180011ea0  mov     rcx, rax
0x180011ea3  mov     rax, rdi
0x180011ea6  jmp     short loc_180011EB8
0x180011ea8  mov     ecx, [rbx+2B4h]
0x180011eae  mov     [rsp+700h+var_6CC], ecx
0x180011eb2  mov     rcx, rax
0x180011eb5  mov     rax, rsi
0x180011eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ebd  test    eax, eax
0x180011ebf  jz      loc_18001210B
0x180011ec5  mov     rax, [rsp+700h+var_6B8]
0x180011eca  lea     r8, [rbp+600h+MultiByteStr]; lpMultiByteStr
0x180011ece  inc     dword ptr [rbx+2B0h]
0x180011ed4  or      r9, 0FFFFFFFFFFFFFFFFh; cbMultiByte
0x180011ed8  mov     [r14], rax
0x180011edb  xor     edx, edx; dwFlags
0x180011edd  mov     eax, [rsp+700h+var_6CC]
0x180011ee1  xor     ecx, ecx; CodePage
0x180011ee3  mov     [rsp+700h+cchWideChar], r12d; cchWideChar
0x180011ee8  mov     [rbx+2B4h], eax
0x180011eee  mov     [rsp+700h+lpWideCharStr], r15; lpWideCharStr
0x180011ef3  call    cs:__imp_MultiByteToWideChar
0x180011ef9  test    eax, eax
0x180011efb  jnz     loc_1800120E7
0x180011f01  call    cs:__imp_GetLastError
0x180011f07  test    eax, eax
0x180011f09  jz      short loc_180011F26
0x180011f0b  call    cs:__imp_GetLastError
0x180011f11  test    eax, eax
0x180011f13  jle     loc_180012117
0x180011f19  movzx   eax, ax
0x180011f1c  or      eax, 80070000h
0x180011f21  jmp     loc_180012117
0x180011f26  mov     eax, 80004005h
0x180011f2b  jmp     loc_180012117
0x180011f30  cmp     [rcx+128h], r13
0x180011f37  jz      loc_180012112
0x180011f3d  cmp     [rcx+130h], r13
0x180011f44  jz      loc_180012112
0x180011f4a  call    ?LoadPsApi@Win32LiveSystemProvider@@IEAAJXZ; Win32LiveSystemProvider::LoadPsApi(void)
0x180011f4f  test    eax, eax
0x180011f51  jnz     loc_180012117
0x180011f57  xor     edx, edx; Val
0x180011f59  lea     rcx, [rbp+600h+var_48C]; void *
0x180011f60  mov     r8d, 434h; Size
0x180011f66  call    memset_0
0x180011f6b  lea     rdx, [rbp+600h+var_490]
0x180011f72  mov     rcx, [rbx+2A0h]
0x180011f79  mov     [rbp+600h+var_490], 438h
0x180011f83  cmp     [rbx+2B0h], r13d
0x180011f8a  jnz     short loc_180011F95
0x180011f8c  mov     rax, [rbx+128h]
0x180011f93  jmp     short loc_180011F9C
0x180011f95  mov     rax, [rbx+130h]
0x180011f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fa1  test    eax, eax
0x180011fa3  jz      loc_18001210B
0x180011fa9  mov     rax, [rbp+600h+var_478]
0x180011fb0  inc     dword ptr [rbx+2B0h]
0x180011fb6  mov     [r14], rax
0x180011fb9  mov     rax, [rbx+200h]
0x180011fc0  test    rax, rax
0x180011fc3  jz      loc_1800120EB
0x180011fc9  mov     rdx, [rbp+600h+var_468]
0x180011fd0  mov     r9d, r12d
0x180011fd3  mov     rcx, [rbx+290h]
0x180011fda  mov     r8, r15
0x180011fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fe2  test    eax, eax
0x180011fe4  jz      loc_1800120EB
0x180011fea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011fee  lea     rax, [rbp+600h+var_260]
0x180011ff5  mov     rsi, rdi
0x180011ff8  inc     rsi
0x180011ffb  cmp     [rax+rsi*2], r13w
0x180012000  jnz     short loc_180011FF8
0x180012002  xor     edx, edx; Val
0x180012004  lea     rcx, [rsp+700h+Str]; void *
0x180012009  mov     r8d, 20Ah; Size
0x18001200f  call    memset_0
0x180012014  mov     r14d, r13d
0x180012017  test    rsi, rsi
0x18001201a  jz      short loc_180012045
0x18001201c  cmp     r14d, 104h
0x180012023  jnb     short loc_180012045
0x180012025  mov     ebx, r14d
0x180012028  movzx   ecx, [rbp+rbx*2+600h+var_260]
0x180012030  call    _o_towlower_0
0x180012035  inc     r14d
0x180012038  mov     [rsp+rbx*2+700h+Str], ax
0x18001203d  mov     eax, r14d
0x180012040  cmp     rax, rsi
0x180012043  jb      short loc_18001201C
0x180012045  lea     rdx, aSyswow64; "syswow64"
0x18001204c  lea     rcx, [rsp+700h+Str]; Str
0x180012051  call    cs:__imp_wcsstr
0x180012057  test    rax, rax
0x18001205a  jnz     short loc_18001208A
0x18001205c  lea     rdx, aSysarm32; "sysarm32"
0x180012063  lea     rcx, [rsp+700h+Str]; Str
0x180012068  call    cs:__imp_wcsstr
0x18001206e  test    rax, rax
0x180012071  jnz     short loc_18001208A
0x180012073  lea     rdx, aSychpe32; "sychpe32"
0x18001207a  lea     rcx, [rsp+700h+Str]; Str
0x18001207f  call    cs:__imp_wcsstr
0x180012085  test    rax, rax
0x180012088  jz      short loc_1800120E7
0x18001208a  inc     rdi
0x18001208d  cmp     [r15+rdi*2], r13w
0x180012092  jnz     short loc_18001208A
0x180012094  xor     edx, edx; Val
0x180012096  lea     rcx, [rsp+700h+Str]; void *
0x18001209b  mov     r8d, 20Ah; Size
0x1800120a1  call    memset_0
0x1800120a6  mov     esi, r13d
0x1800120a9  test    rdi, rdi
0x1800120ac  jz      short loc_1800120D0
0x1800120ae  cmp     esi, 104h
0x1800120b4  jnb     short loc_1800120D0
0x1800120b6  mov     ebx, esi
0x1800120b8  movzx   ecx, word ptr [r15+rbx*2]
0x1800120bd  call    _o_towlower_0
0x1800120c2  inc     esi
0x1800120c4  mov     [rsp+rbx*2+700h+Str], ax
0x1800120c9  mov     eax, esi
0x1800120cb  cmp     rax, rdi
0x1800120ce  jb      short loc_1800120AE
0x1800120d0  lea     rdx, aSystem32; "system32"
0x1800120d7  lea     rcx, [rsp+700h+Str]; Str
0x1800120dc  call    cs:__imp_wcsstr
0x1800120e2  test    rax, rax
0x1800120e5  jnz     short loc_1800120EB
0x1800120e7  xor     eax, eax
0x1800120e9  jmp     short loc_180012117
0x1800120eb  mov     r8d, r12d; int
0x1800120ee  lea     rdx, [rbp+600h+var_260]; unsigned __int16 *
0x1800120f5  mov     rcx, r15; unsigned __int16 *
0x1800120f8  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x1800120fd  neg     rax
0x180012100  sbb     eax, eax
0x180012102  not     eax
0x180012104  and     eax, 80070057h
0x180012109  jmp     short loc_180012117
0x18001210b  mov     eax, 1
0x180012110  jmp     short loc_180012117
0x180012112  mov     eax, 80004001h
0x180012117  mov     rcx, [rbp+600h+var_50]
0x18001211e  xor     rcx, rsp; StackCookie
0x180012121  call    __security_check_cookie
0x180012126  add     rsp, 6C8h
0x18001212d  pop     r15
0x18001212f  pop     r14
0x180012131  pop     r13
0x180012133  pop     r12
0x180012135  pop     rdi
0x180012136  pop     rsi
0x180012137  pop     rbx
0x180012138  pop     rbp
0x180012139  retn
```
