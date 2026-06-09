# Microsoft::Resources::Runtime::CContext::_SetSystemQualifierOverrideState(ushort const *,bool)

- ea: `0x180046a40`
- end: `0x180046b7c`
- name: `?_SetSystemQualifierOverrideState@CContext@Runtime@Resources@Microsoft@@AEAAJPEBG_N@Z`
- size: `316`
- prototype: `int(Microsoft::Resources::Runtime::CContext *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022ba0`
- `0x180045ad4`
- `0x18004619c`
- `0x180047d94`
- `0x1800a79c4`

## callees

- `0x180028ad0`
- `0x180046a40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a71`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ac5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046aef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046b15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a71`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046ac5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046aef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046b15`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CContext::_SetSystemQualifierOverrideState(
        Microsoft::Resources::Runtime::CContext *this,
        const unsigned __int16 *a2,
        char a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ecx

  v6 = CompareStringOrdinal(a2, -1, L"Scale", -1, 1);
  if ( (unsigned int)IntToComparison((unsigned int)(v6 - 2)) )
  {
    v7 = CompareStringOrdinal(a2, -1, L"Language", -1, 1);
    if ( (unsigned int)IntToComparison((unsigned int)(v7 - 2)) )
    {
      v8 = CompareStringOrdinal(a2, -1, L"Contrast", -1, 1);
      if ( (unsigned int)IntToComparison((unsigned int)(v8 - 2)) )
      {
        v9 = CompareStringOrdinal(a2, -1, L"LayoutDirection", -1, 1);
        if ( (unsigned int)IntToComparison((unsigned int)(v9 - 2)) )
        {
          v10 = CompareStringOrdinal(a2, -1, L"HomeRegion", -1, 1);
          if ( (unsigned int)IntToComparison((unsigned int)(v10 - 2)) )
            return 0;
          v11 = *((_DWORD *)this + 10) | 0x10;
          v12 = *((_DWORD *)this + 10) & 0xFFFFFFEF;
        }
        else
        {
          v11 = *((_DWORD *)this + 10) | 8;
          v12 = *((_DWORD *)this + 10) & 0xFFFFFFF7;
        }
      }
      else
      {
        v11 = *((_DWORD *)this + 10) | 4;
        v12 = *((_DWORD *)this + 10) & 0xFFFFFFFB;
      }
    }
    else
    {
      v11 = *((_DWORD *)this + 10) | 2;
      v12 = *((_DWORD *)this + 10) & 0xFFFFFFFD;
    }
  }
  else
  {
    v11 = *((_DWORD *)this + 10) | 1;
    v12 = *((_DWORD *)this + 10) & 0xFFFFFFFE;
  }
  if ( !a3 )
    v12 = v11;
  *((_DWORD *)this + 10) = v12;
  return 0;
}

```

## disassembly

```asm
0x180046a40  push    rbx
0x180046a42  push    rbp
0x180046a43  push    rsi
0x180046a44  push    rdi
0x180046a45  push    r14
0x180046a47  sub     rsp, 30h
0x180046a4b  mov     rsi, rdx
0x180046a4e  or      ebp, 0FFFFFFFFh
0x180046a51  mov     dil, r8b
0x180046a54  mov     rbx, rcx
0x180046a57  mov     r14d, 1
0x180046a5d  lea     r8, String2; "Scale"
0x180046a64  mov     r9d, ebp; cchCount2
0x180046a67  mov     [rsp+58h+bIgnoreCase], r14d; bIgnoreCase
0x180046a6c  mov     edx, ebp; cchCount1
0x180046a6e  mov     rcx, rsi; lpString1
0x180046a71  call    cs:__imp_CompareStringOrdinal
0x180046a77  lea     ecx, [rax-2]
0x180046a7a  call    _IntToComparison
0x180046a7f  test    eax, eax
0x180046a81  jz      loc_180046B34
0x180046a87  mov     r9d, ebp; cchCount2
0x180046a8a  mov     [rsp+58h+bIgnoreCase], r14d; bIgnoreCase
0x180046a8f  lea     r8, aLanguage; "Language"
0x180046a96  mov     edx, ebp; cchCount1
0x180046a98  mov     rcx, rsi; lpString1
0x180046a9b  call    cs:__imp_CompareStringOrdinal
0x180046aa1  lea     ecx, [rax-2]
0x180046aa4  call    _IntToComparison
0x180046aa9  test    eax, eax
0x180046aab  jz      loc_180046B55
0x180046ab1  mov     r9d, ebp; cchCount2
0x180046ab4  mov     [rsp+58h+bIgnoreCase], r14d; bIgnoreCase
0x180046ab9  lea     r8, aContrast_0; "Contrast"
0x180046ac0  mov     edx, ebp; cchCount1
0x180046ac2  mov     rcx, rsi; lpString1
0x180046ac5  call    cs:__imp_CompareStringOrdinal
0x180046acb  lea     ecx, [rax-2]
0x180046ace  call    _IntToComparison
0x180046ad3  test    eax, eax
0x180046ad5  jz      loc_180046B62
0x180046adb  mov     r9d, ebp; cchCount2
0x180046ade  mov     [rsp+58h+bIgnoreCase], r14d; bIgnoreCase
0x180046ae3  lea     r8, aLayoutdirectio; "LayoutDirection"
0x180046aea  mov     edx, ebp; cchCount1
0x180046aec  mov     rcx, rsi; lpString1
0x180046aef  call    cs:__imp_CompareStringOrdinal
0x180046af5  lea     ecx, [rax-2]
0x180046af8  call    _IntToComparison
0x180046afd  test    eax, eax
0x180046aff  jz      short loc_180046B6F
0x180046b01  mov     r9d, ebp; cchCount2
0x180046b04  mov     [rsp+58h+bIgnoreCase], r14d; bIgnoreCase
0x180046b09  lea     r8, aHomeregion; "HomeRegion"
0x180046b10  mov     edx, ebp; cchCount1
0x180046b12  mov     rcx, rsi; lpString1
0x180046b15  call    cs:__imp_CompareStringOrdinal
0x180046b1b  lea     ecx, [rax-2]
0x180046b1e  call    _IntToComparison
0x180046b23  test    eax, eax
0x180046b25  jnz     short loc_180046B48
0x180046b27  mov     ecx, [rbx+28h]
0x180046b2a  mov     eax, ecx
0x180046b2c  or      eax, 10h
0x180046b2f  and     ecx, 0FFFFFFEFh
0x180046b32  jmp     short loc_180046B3F
0x180046b34  mov     ecx, [rbx+28h]
0x180046b37  mov     eax, ecx
0x180046b39  or      eax, r14d
0x180046b3c  and     ecx, 0FFFFFFFEh
0x180046b3f  test    dil, dil
0x180046b42  cmovz   ecx, eax
0x180046b45  mov     [rbx+28h], ecx
0x180046b48  xor     eax, eax
0x180046b4a  add     rsp, 30h
0x180046b4e  pop     r14
0x180046b50  pop     rdi
0x180046b51  pop     rsi
0x180046b52  pop     rbp
0x180046b53  pop     rbx
0x180046b54  retn
0x180046b55  mov     ecx, [rbx+28h]
0x180046b58  mov     eax, ecx
0x180046b5a  or      eax, 2
0x180046b5d  and     ecx, 0FFFFFFFDh
0x180046b60  jmp     short loc_180046B3F
0x180046b62  mov     ecx, [rbx+28h]
0x180046b65  mov     eax, ecx
0x180046b67  or      eax, 4
0x180046b6a  and     ecx, 0FFFFFFFBh
0x180046b6d  jmp     short loc_180046B3F
0x180046b6f  mov     ecx, [rbx+28h]
0x180046b72  mov     eax, ecx
0x180046b74  or      eax, 8
0x180046b77  and     ecx, 0FFFFFFF7h
0x180046b7a  jmp     short loc_180046B3F
```
