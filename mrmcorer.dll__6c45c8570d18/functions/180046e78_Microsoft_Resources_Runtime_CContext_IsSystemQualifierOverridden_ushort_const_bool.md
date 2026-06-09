# Microsoft::Resources::Runtime::CContext::_IsSystemQualifierOverridden(ushort const *,bool *)

- ea: `0x180046e78`
- end: `0x180046f4f`
- name: `?_IsSystemQualifierOverridden@CContext@Runtime@Resources@Microsoft@@AEBAJPEBGPEA_N@Z`
- size: `215`
- prototype: `int(Microsoft::Resources::Runtime::CContext *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018210`
- `0x180045f44`

## callees

- `0x180028ad0`
- `0x180042f70`
- `0x180046e78`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ea9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ee3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046f10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ea9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ee3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046f10`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CContext::_IsSystemQualifierOverridden(
        Microsoft::Resources::Runtime::CContext *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  int v6; // eax
  int v7; // eax
  int v9; // eax
  int v10; // eax

  v6 = CompareStringOrdinal(a2, -1, L"Scale", -1, 1);
  if ( !(unsigned int)IntToComparison((unsigned int)(v6 - 2)) )
  {
    v7 = *((_DWORD *)this + 10);
LABEL_3:
    *a3 = v7 & 1;
    return 0;
  }
  v9 = CompareStringOrdinal(a2, -1, L"Language", -1, 1);
  if ( !(unsigned int)IntToComparison((unsigned int)(v9 - 2)) )
  {
    v7 = *((_DWORD *)this + 10) >> 1;
    goto LABEL_3;
  }
  v10 = CompareStringOrdinal(a2, -1, L"Contrast", -1, 1);
  if ( !(unsigned int)IntToComparison((unsigned int)(v10 - 2)) )
  {
    v7 = *((_DWORD *)this + 10) >> 2;
    goto LABEL_3;
  }
  if ( !(unsigned int)DefString_CompareWithOptions(a2, L"LayoutDirection", 1) )
  {
    v7 = *((_DWORD *)this + 10) >> 3;
    goto LABEL_3;
  }
  if ( !(unsigned int)DefString_CompareWithOptions(a2, L"HomeRegion", 1) )
  {
    v7 = *((_DWORD *)this + 10) >> 4;
    goto LABEL_3;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180046e78  push    rbx
0x180046e7a  push    rbp
0x180046e7b  push    rsi
0x180046e7c  push    rdi
0x180046e7d  push    r14
0x180046e7f  sub     rsp, 30h
0x180046e83  mov     rdi, rdx
0x180046e86  or      r14d, 0FFFFFFFFh
0x180046e8a  mov     rsi, r8
0x180046e8d  mov     rbx, rcx
0x180046e90  mov     ebp, 1
0x180046e95  lea     r8, String2; "Scale"
0x180046e9c  mov     r9d, r14d; cchCount2
0x180046e9f  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180046ea3  mov     edx, r14d; cchCount1
0x180046ea6  mov     rcx, rdi; lpString1
0x180046ea9  call    cs:__imp_CompareStringOrdinal
0x180046eaf  lea     ecx, [rax-2]
0x180046eb2  call    _IntToComparison
0x180046eb7  test    eax, eax
0x180046eb9  jnz     short loc_180046ECF
0x180046ebb  mov     eax, [rbx+28h]
0x180046ebe  and     eax, ebp
0x180046ec0  mov     [rsi], al
0x180046ec2  xor     eax, eax
0x180046ec4  add     rsp, 30h
0x180046ec8  pop     r14
0x180046eca  pop     rdi
0x180046ecb  pop     rsi
0x180046ecc  pop     rbp
0x180046ecd  pop     rbx
0x180046ece  retn
0x180046ecf  mov     r9d, r14d; cchCount2
0x180046ed2  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180046ed6  lea     r8, aLanguage; "Language"
0x180046edd  mov     edx, r14d; cchCount1
0x180046ee0  mov     rcx, rdi; lpString1
0x180046ee3  call    cs:__imp_CompareStringOrdinal
0x180046ee9  lea     ecx, [rax-2]
0x180046eec  call    _IntToComparison
0x180046ef1  test    eax, eax
0x180046ef3  jnz     short loc_180046EFC
0x180046ef5  mov     eax, [rbx+28h]
0x180046ef8  shr     eax, 1
0x180046efa  jmp     short loc_180046EBE
0x180046efc  mov     r9d, r14d; cchCount2
0x180046eff  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180046f03  lea     r8, aContrast_0; "Contrast"
0x180046f0a  mov     edx, r14d; cchCount1
0x180046f0d  mov     rcx, rdi; lpString1
0x180046f10  call    cs:__imp_CompareStringOrdinal
0x180046f16  lea     ecx, [rax-2]
0x180046f19  call    _IntToComparison
0x180046f1e  test    eax, eax
0x180046f20  jnz     short loc_180046F2A
0x180046f22  mov     eax, [rbx+28h]
0x180046f25  shr     eax, 2
0x180046f28  jmp     short loc_180046EBE
0x180046f2a  mov     r8d, ebp
0x180046f2d  lea     rdx, aLayoutdirectio; "LayoutDirection"
0x180046f34  mov     rcx, rdi
0x180046f37  call    DefString_CompareWithOptions
0x180046f3c  test    eax, eax
0x180046f3e  jnz     loc_1800C2D18
0x180046f44  mov     eax, [rbx+28h]
0x180046f47  shr     eax, 3
0x180046f4a  jmp     loc_180046EBE
0x1800c2d18  mov     r8d, ebp
0x1800c2d1b  lea     rdx, aHomeregion; "HomeRegion"
0x1800c2d22  mov     rcx, rdi
0x1800c2d25  call    DefString_CompareWithOptions
0x1800c2d2a  test    eax, eax
0x1800c2d2c  jnz     short loc_1800C2D39
0x1800c2d2e  mov     eax, [rbx+28h]
0x1800c2d31  shr     eax, 4
0x1800c2d34  jmp     loc_180046EBE
0x1800c2d39  mov     eax, 80070057h
0x1800c2d3e  jmp     loc_180046EC4
```
