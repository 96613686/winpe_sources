# TLSGeneratePid

- ea: `0x180020284`
- end: `0x1800204b6`
- name: `TLSGeneratePid`
- size: `562`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180020614`
- `0x180020790`

## callees

- `0x18000cff0`
- `0x18000d060`
- `0x18001fdac`
- `0x180020284`
- `0x180078610`

## import_xrefs

- `msvcrt!iswalpha` at `0x180020427`
- `msvcrt!iswalpha` at `0x180020427`
- `KERNEL32!GetTickCount` at `0x180020361`
- `KERNEL32!GetTickCount` at `0x1800203ce`
- `KERNEL32!GetTickCount` at `0x180020361`
- `KERNEL32!GetTickCount` at `0x1800203ce`
- `KERNEL32!GetCurrentThreadId` at `0x18002036f`
- `KERNEL32!GetCurrentThreadId` at `0x1800203dc`
- `KERNEL32!GetCurrentThreadId` at `0x18002036f`
- `KERNEL32!GetCurrentThreadId` at `0x1800203dc`
- `KERNEL32!GetLastError` at `0x180020334`
- `KERNEL32!GetLastError` at `0x180020334`
- `KERNEL32!LocalAlloc` at `0x180020320`
- `KERNEL32!LocalAlloc` at `0x180020320`
- `KERNEL32!LocalFree` at `0x18002048f`
- `KERNEL32!LocalFree` at `0x18002048f`

## pseudocode

```c
__int64 __fastcall TLSGeneratePid(unsigned __int16 *a1, _DWORD *a2, unsigned __int16 **a3, _DWORD *a4)
{
  wint_t *v6; // rdi
  int v7; // r14d
  unsigned int v8; // eax
  DWORD LastError; // esi
  __int64 v10; // rbp
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // r15
  __int64 v13; // rax
  DWORD TickCount; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v16; // rax
  int v17; // r14d
  DWORD v18; // ebx
  DWORD v19; // eax
  __int64 v20; // rax
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+8h] BYREF
  _DWORD *v24; // [rsp+88h] [rbp+10h]
  unsigned __int16 **v25; // [rsp+90h] [rbp+18h]

  v25 = a3;
  v24 = a2;
  hMem = 0;
  v6 = 0;
  v7 = 1;
  if ( !a1 || !a2 || !a3 || !a4 )
    goto LABEL_23;
  v8 = TLSReadRegistryValue(a1, L"ProductId", (unsigned __int16 **)&hMem, &v23);
  v6 = (wint_t *)hMem;
  LastError = v8;
  if ( v8 )
    goto LABEL_24;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)hMem + v11) );
  if ( v11 < 0x17 )
  {
LABEL_23:
    LastError = 87;
LABEL_24:
    if ( v6 )
      LocalFree(v6);
    return LastError;
  }
  v12 = (unsigned __int16 *)LocalAlloc(0x40u, 0xCu);
  if ( !v12 )
  {
    LastError = GetLastError();
    if ( !LastError )
      return LastError;
    goto LABEL_24;
  }
  v13 = 5;
  do
  {
    v7 *= 10;
    --v13;
  }
  while ( v13 );
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  GenerateRandomNumber(CurrentThreadId + TickCount);
  StringCchPrintfW(v12, 6u, L"%0*u");
  *((_QWORD *)v6 + 3) = *(_QWORD *)v12;
  v6[16] = v12[4];
  v16 = 3;
  v17 = 1;
  do
  {
    v17 *= 10;
    --v16;
  }
  while ( v16 );
  v18 = GetTickCount();
  v19 = GetCurrentThreadId();
  GenerateRandomNumber(v19 + v18);
  StringCchPrintfW(v12, 6u, L"%0*u");
  StringCchCopyW(v6 + 20, 4u, v12);
  if ( iswalpha(v6[18]) )
    v6[19] = 84;
  *(_QWORD *)a1 = v6;
  v20 = -1;
  do
    ++v20;
  while ( v6[v20] );
  *v24 = 2 * v20 + 2;
  *v25 = v12;
  do
    ++v10;
  while ( v12[v10] );
  *a4 = 2 * v10 + 2;
  return LastError;
}

```

## disassembly

```asm
0x180020284  mov     r11, rsp
0x180020287  mov     [r11+20h], rbx
0x18002028b  mov     [r11+18h], r8
0x18002028f  mov     [r11+10h], rdx
0x180020293  push    rbp
0x180020294  push    rsi
0x180020295  push    rdi
0x180020296  push    r12
0x180020298  push    r13
0x18002029a  push    r14
0x18002029c  push    r15
0x18002029e  sub     rsp, 40h
0x1800202a2  xor     ebx, ebx
0x1800202a4  mov     r12, r9
0x1800202a7  mov     [r11-48h], rbx
0x1800202ab  mov     rax, r8
0x1800202ae  mov     r13, rcx
0x1800202b1  mov     edi, ebx
0x1800202b3  lea     r14d, [rbx+1]
0x1800202b7  test    rcx, rcx
0x1800202ba  jz      loc_180020482
0x1800202c0  test    rdx, rdx
0x1800202c3  jz      loc_180020482
0x1800202c9  test    rax, rax
0x1800202cc  jz      loc_180020482
0x1800202d2  test    r9, r9
0x1800202d5  jz      loc_180020482
0x1800202db  lea     r9, [r11+8]; unsigned int *
0x1800202df  lea     r8, [r11-48h]; unsigned __int16 **
0x1800202e3  lea     rdx, aProductid; "ProductId"
0x1800202ea  call    ?TLSReadRegistryValue@@YAKPEAG0PEAPEAGPEAK@Z; TLSReadRegistryValue(ushort *,ushort *,ushort * *,ulong *)
0x1800202ef  mov     rdi, [rsp+78h+hMem]
0x1800202f4  mov     esi, eax
0x1800202f6  test    eax, eax
0x1800202f8  jnz     loc_180020487
0x1800202fe  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180020302  mov     rax, rbp
0x180020305  inc     rax
0x180020308  cmp     [rdi+rax*2], bx
0x18002030c  jnz     short loc_180020305
0x18002030e  cmp     rax, 17h
0x180020312  jb      loc_180020482
0x180020318  mov     edx, 0Ch; uBytes
0x18002031d  lea     ecx, [rdx+34h]; uFlags
0x180020320  call    cs:__imp_LocalAlloc
0x180020327  nop     dword ptr [rax+rax+00h]
0x18002032c  mov     r15, rax
0x18002032f  test    rax, rax
0x180020332  jnz     short loc_18002034F
0x180020334  call    cs:__imp_GetLastError
0x18002033b  nop     dword ptr [rax+rax+00h]
0x180020340  mov     esi, eax
0x180020342  test    eax, eax
0x180020344  jz      loc_18002049B
0x18002034a  jmp     loc_180020487
0x18002034f  mov     eax, 5
0x180020354  lea     r14d, [r14+r14*4]
0x180020358  add     r14d, r14d
0x18002035b  sub     rax, 1
0x18002035f  jnz     short loc_180020354
0x180020361  call    cs:__imp_GetTickCount
0x180020368  nop     dword ptr [rax+rax+00h]
0x18002036d  mov     ebx, eax
0x18002036f  call    cs:__imp_GetCurrentThreadId
0x180020376  nop     dword ptr [rax+rax+00h]
0x18002037b  lea     ecx, [rax+rbx]; unsigned int
0x18002037e  call    ?GenerateRandomNumber@@YAKK@Z; GenerateRandomNumber(ulong)
0x180020383  xor     edx, edx
0x180020385  lea     r8, a0U; "%0*u"
0x18002038c  div     r14d
0x18002038f  mov     r9d, 5
0x180020395  mov     rcx, r15; unsigned __int16 *
0x180020398  mov     [rsp+78h+var_58], edx
0x18002039c  lea     edx, [r9+1]; unsigned __int64
0x1800203a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800203a5  movsd   xmm0, qword ptr [r15]
0x1800203aa  movsd   qword ptr [rdi+18h], xmm0
0x1800203af  movzx   eax, word ptr [r15+8]
0x1800203b4  mov     [rdi+20h], ax
0x1800203b8  mov     eax, 3
0x1800203bd  lea     r14d, [rax-2]
0x1800203c1  lea     r14d, [r14+r14*4]
0x1800203c5  add     r14d, r14d
0x1800203c8  sub     rax, 1
0x1800203cc  jnz     short loc_1800203C1
0x1800203ce  call    cs:__imp_GetTickCount
0x1800203d5  nop     dword ptr [rax+rax+00h]
0x1800203da  mov     ebx, eax
0x1800203dc  call    cs:__imp_GetCurrentThreadId
0x1800203e3  nop     dword ptr [rax+rax+00h]
0x1800203e8  lea     ecx, [rax+rbx]; unsigned int
0x1800203eb  call    ?GenerateRandomNumber@@YAKK@Z; GenerateRandomNumber(ulong)
0x1800203f0  xor     edx, edx
0x1800203f2  lea     r8, a0U; "%0*u"
0x1800203f9  div     r14d
0x1800203fc  mov     r9d, 3
0x180020402  mov     rcx, r15; unsigned __int16 *
0x180020405  mov     [rsp+78h+var_58], edx
0x180020409  lea     edx, [r9+3]; unsigned __int64
0x18002040d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020412  lea     rcx, [rdi+28h]; unsigned __int16 *
0x180020416  mov     r8, r15; unsigned __int16 *
0x180020419  mov     edx, 4; unsigned __int64
0x18002041e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020423  movzx   ecx, word ptr [rdi+24h]; C
0x180020427  call    cs:__imp_iswalpha
0x18002042e  nop     dword ptr [rax+rax+00h]
0x180020433  xor     edx, edx
0x180020435  test    eax, eax
0x180020437  jz      short loc_18002043F
0x180020439  mov     word ptr [rdi+26h], 54h ; 'T'
0x18002043f  mov     [r13+0], rdi
0x180020443  mov     rax, rbp
0x180020446  inc     rax
0x180020449  cmp     [rdi+rax*2], dx
0x18002044d  jnz     short loc_180020446
0x18002044f  mov     rcx, [rsp+78h+arg_8]
0x180020457  lea     eax, ds:2[rax*2]
0x18002045e  mov     [rcx], eax
0x180020460  mov     rax, [rsp+78h+arg_10]
0x180020468  mov     [rax], r15
0x18002046b  inc     rbp
0x18002046e  cmp     [r15+rbp*2], dx
0x180020473  jnz     short loc_18002046B
0x180020475  lea     eax, ds:2[rbp*2]
0x18002047c  mov     [r12], eax
0x180020480  jmp     short loc_18002049B
0x180020482  mov     esi, 57h ; 'W'
0x180020487  test    rdi, rdi
0x18002048a  jz      short loc_18002049B
0x18002048c  mov     rcx, rdi; hMem
0x18002048f  call    cs:__imp_LocalFree
0x180020496  nop     dword ptr [rax+rax+00h]
0x18002049b  mov     rbx, [rsp+78h+arg_18]
0x1800204a3  mov     eax, esi
0x1800204a5  add     rsp, 40h
0x1800204a9  pop     r15
0x1800204ab  pop     r14
0x1800204ad  pop     r13
0x1800204af  pop     r12
0x1800204b1  pop     rdi
0x1800204b2  pop     rsi
0x1800204b3  pop     rbp
0x1800204b4  retn
```
