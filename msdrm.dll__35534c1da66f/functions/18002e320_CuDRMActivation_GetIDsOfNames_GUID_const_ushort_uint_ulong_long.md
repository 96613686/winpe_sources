# CuDRMActivation::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18002e320`
- end: `0x18002e569`
- name: `?GetIDsOfNames@CuDRMActivation@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `585`
- prototype: `__int64 __fastcall(CuDRMActivation *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID Locale, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002e320`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e386`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e3bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e3ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e424`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e45a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e490`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e4c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e4f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e52c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e386`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e3bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e3ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e424`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e45a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e490`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e4c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e4f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e52c`

## string_xrefs

- `0x18002e4de`: `Temporary`

## pseudocode

```c
__int64 __fastcall CuDRMActivation::GetIDsOfNames(
        CuDRMActivation *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID Locale,
        int *a6)
{
  unsigned int v9; // r15d
  __int64 i; // rbp

  if ( !a6 )
    return 2147942487LL;
  v9 = 0;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    if ( CompareStringW(Locale, 0x20000u, L"Init", -1, a3[i], -1) == 2 )
    {
      a6[i] = 1;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"CloseWizard", -1, a3[i], -1) == 2 )
    {
      a6[i] = 2;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"bstrUserID", -1, a3[i], -1) == 2 )
    {
      a6[i] = 3;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"Activate", -1, a3[i], -1) == 2 )
    {
      a6[i] = 4;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"GetReturnCode", -1, a3[i], -1) == 2 )
    {
      a6[i] = 5;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"GetConsumption", -1, a3[i], -1) == 2 )
    {
      a6[i] = 6;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"GetQuota", -1, a3[i], -1) == 2 )
    {
      a6[i] = 7;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"Temporary", -1, a3[i], -1) == 2 )
    {
      a6[i] = 8;
    }
    else if ( CompareStringW(Locale, 0x20000u, L"TerminateActivation", -1, a3[i], -1) == 2 )
    {
      a6[i] = 9;
    }
    else
    {
      v9 = -2147352570;
      a6[i] = -1;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18002e320  push    rbx
0x18002e322  push    rbp
0x18002e323  push    rsi
0x18002e324  push    rdi
0x18002e325  push    r12
0x18002e327  push    r13
0x18002e329  push    r14
0x18002e32b  push    r15
0x18002e32d  sub     rsp, 38h
0x18002e331  mov     rdi, [rsp+78h+arg_28]
0x18002e339  mov     r12d, r9d
0x18002e33c  mov     r14, r8
0x18002e33f  test    rdi, rdi
0x18002e342  jnz     short loc_18002E34E
0x18002e344  mov     eax, 80070057h
0x18002e349  jmp     loc_18002E558
0x18002e34e  xor     r15d, r15d
0x18002e351  xor     ebp, ebp
0x18002e353  test    r12d, r12d
0x18002e356  jz      loc_18002E555
0x18002e35c  mov     esi, [rsp+78h+Locale]
0x18002e363  or      r13d, 0FFFFFFFFh
0x18002e367  mov     rax, [r14+rbp*8]
0x18002e36b  lea     r8, String1; "Init"
0x18002e372  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e377  mov     r9d, r13d; cchCount1
0x18002e37a  mov     edx, 20000h; dwCmpFlags
0x18002e37f  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e384  mov     ecx, esi; Locale
0x18002e386  call    cs:__imp_CompareStringW
0x18002e38c  cmp     eax, 2
0x18002e38f  jnz     short loc_18002E39D
0x18002e391  mov     dword ptr [rdi+rbp*4], 1
0x18002e398  jmp     loc_18002E54A
0x18002e39d  mov     rax, [r14+rbp*8]
0x18002e3a1  lea     r8, aClosewizard; "CloseWizard"
0x18002e3a8  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e3ad  mov     r9d, r13d; cchCount1
0x18002e3b0  mov     edx, 20000h; dwCmpFlags
0x18002e3b5  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e3ba  mov     ecx, esi; Locale
0x18002e3bc  call    cs:__imp_CompareStringW
0x18002e3c2  cmp     eax, 2
0x18002e3c5  jnz     short loc_18002E3CF
0x18002e3c7  mov     [rdi+rbp*4], eax
0x18002e3ca  jmp     loc_18002E54A
0x18002e3cf  mov     rax, [r14+rbp*8]
0x18002e3d3  lea     r8, aBstruserid; "bstrUserID"
0x18002e3da  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e3df  mov     r9d, r13d; cchCount1
0x18002e3e2  mov     edx, 20000h; dwCmpFlags
0x18002e3e7  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e3ec  mov     ecx, esi; Locale
0x18002e3ee  call    cs:__imp_CompareStringW
0x18002e3f4  cmp     eax, 2
0x18002e3f7  jnz     short loc_18002E405
0x18002e3f9  mov     dword ptr [rdi+rbp*4], 3
0x18002e400  jmp     loc_18002E54A
0x18002e405  mov     rax, [r14+rbp*8]
0x18002e409  lea     r8, aActivate; "Activate"
0x18002e410  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e415  mov     r9d, r13d; cchCount1
0x18002e418  mov     edx, 20000h; dwCmpFlags
0x18002e41d  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e422  mov     ecx, esi; Locale
0x18002e424  call    cs:__imp_CompareStringW
0x18002e42a  cmp     eax, 2
0x18002e42d  jnz     short loc_18002E43B
0x18002e42f  mov     dword ptr [rdi+rbp*4], 4
0x18002e436  jmp     loc_18002E54A
0x18002e43b  mov     rax, [r14+rbp*8]
0x18002e43f  lea     r8, aGetreturncode; "GetReturnCode"
0x18002e446  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e44b  mov     r9d, r13d; cchCount1
0x18002e44e  mov     edx, 20000h; dwCmpFlags
0x18002e453  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e458  mov     ecx, esi; Locale
0x18002e45a  call    cs:__imp_CompareStringW
0x18002e460  cmp     eax, 2
0x18002e463  jnz     short loc_18002E471
0x18002e465  mov     dword ptr [rdi+rbp*4], 5
0x18002e46c  jmp     loc_18002E54A
0x18002e471  mov     rax, [r14+rbp*8]
0x18002e475  lea     r8, aGetconsumption; "GetConsumption"
0x18002e47c  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e481  mov     r9d, r13d; cchCount1
0x18002e484  mov     edx, 20000h; dwCmpFlags
0x18002e489  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e48e  mov     ecx, esi; Locale
0x18002e490  call    cs:__imp_CompareStringW
0x18002e496  cmp     eax, 2
0x18002e499  jnz     short loc_18002E4A7
0x18002e49b  mov     dword ptr [rdi+rbp*4], 6
0x18002e4a2  jmp     loc_18002E54A
0x18002e4a7  mov     rax, [r14+rbp*8]
0x18002e4ab  lea     r8, aGetquota; "GetQuota"
0x18002e4b2  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e4b7  mov     r9d, r13d; cchCount1
0x18002e4ba  mov     edx, 20000h; dwCmpFlags
0x18002e4bf  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e4c4  mov     ecx, esi; Locale
0x18002e4c6  call    cs:__imp_CompareStringW
0x18002e4cc  cmp     eax, 2
0x18002e4cf  jnz     short loc_18002E4DA
0x18002e4d1  mov     dword ptr [rdi+rbp*4], 7
0x18002e4d8  jmp     short loc_18002E54A
0x18002e4da  mov     rax, [r14+rbp*8]
0x18002e4de  lea     r8, aTemporary; "Temporary"
0x18002e4e5  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e4ea  mov     r9d, r13d; cchCount1
0x18002e4ed  mov     edx, 20000h; dwCmpFlags
0x18002e4f2  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e4f7  mov     ecx, esi; Locale
0x18002e4f9  call    cs:__imp_CompareStringW
0x18002e4ff  cmp     eax, 2
0x18002e502  jnz     short loc_18002E50D
0x18002e504  mov     dword ptr [rdi+rbp*4], 8
0x18002e50b  jmp     short loc_18002E54A
0x18002e50d  mov     rax, [r14+rbp*8]
0x18002e511  lea     r8, aTerminateactiv; "TerminateActivation"
0x18002e518  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x18002e51d  mov     r9d, r13d; cchCount1
0x18002e520  mov     edx, 20000h; dwCmpFlags
0x18002e525  mov     [rsp+78h+lpString2], rax; lpString2
0x18002e52a  mov     ecx, esi; Locale
0x18002e52c  call    cs:__imp_CompareStringW
0x18002e532  cmp     eax, 2
0x18002e535  jnz     short loc_18002E540
0x18002e537  mov     dword ptr [rdi+rbp*4], 9
0x18002e53e  jmp     short loc_18002E54A
0x18002e540  mov     r15d, 80020006h
0x18002e546  mov     [rdi+rbp*4], r13d
0x18002e54a  inc     ebp
0x18002e54c  cmp     ebp, r12d
0x18002e54f  jb      loc_18002E367
0x18002e555  mov     eax, r15d
0x18002e558  add     rsp, 38h
0x18002e55c  pop     r15
0x18002e55e  pop     r14
0x18002e560  pop     r13
0x18002e562  pop     r12
0x18002e564  pop     rdi
0x18002e565  pop     rsi
0x18002e566  pop     rbp
0x18002e567  pop     rbx
0x18002e568  retn
```
