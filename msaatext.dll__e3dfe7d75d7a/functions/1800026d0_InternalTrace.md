# InternalTrace

- ea: `0x1800026d0`
- end: `0x18000298c`
- name: `InternalTrace`
- size: `700`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int Value@<edx>, int, int, __int64)`
- caller_count: `59`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800050d4`
- `0x1800051a8`
- `0x18000527c`
- `0x180005350`
- `0x1800055b4`
- `0x1800056cc`
- `0x180005944`
- `0x180005d40`
- `0x180005f90`
- `0x1800065e0`
- `0x180006de0`
- `0x180006ee0`
- `0x180006ffc`
- `0x1800071ac`
- `0x1800074c8`
- `0x180007d80`
- `0x180007e70`
- `0x1800087d0`
- `0x180008930`
- `0x180008a40`
- `0x180008b90`
- `0x180008d60`
- `0x180008eb0`
- `0x180009080`
- `0x1800091e0`
- `0x1800094e0`
- `0x1800095f0`
- `0x180009700`
- `0x180009810`
- `0x180009920`
- `0x1800099f0`
- `0x180009ae0`
- `0x180009b50`
- `0x180009c30`
- `0x180009d00`
- `0x180009df0`
- `0x180009ee0`
- `0x18000ae90`
- `0x18000b1a0`
- `0x18000b2a0`
- `0x18000b3a0`
- `0x18000b400`
- `0x18000b550`
- `0x18000b670`
- `0x18000b7c0`
- `0x18000b920`
- `0x18000bb10`
- `0x18000bd20`
- `0x18000be80`
- `0x18000c000`

## callees

- `0x180002474`
- `0x180002610`
- `0x1800026d0`
- `0x180002994`
- `0x180002b44`
- `0x180002dcc`
- `0x180003078`
- `0x180012b40`

## import_xrefs

- `msvcrt!_ultow` at `0x1800027f3`
- `msvcrt!_ultow` at `0x1800027f3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000295f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000295f`
- `KERNEL32!GetCurrentProcessId` at `0x180002714`
- `KERNEL32!GetCurrentProcessId` at `0x180002714`
- `KERNEL32!GetLastError` at `0x1800028c5`
- `KERNEL32!GetLastError` at `0x1800028c5`
- `KERNEL32!GetCurrentThreadId` at `0x18000271d`
- `KERNEL32!GetCurrentThreadId` at `0x18000271d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InternalTrace(
        unsigned __int16 *a1,
        unsigned int Value,
        unsigned int a3,
        char a4,
        int a5,
        int a6,
        wchar_t *a7)
{
  wchar_t *v10; // r14
  __int64 v11; // rbx
  __int64 v12; // r8
  wchar_t **v13; // rcx
  const unsigned __int16 * near *v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // r8
  const unsigned __int16 *v17; // rdx
  wchar_t *v18; // rax
  __int64 v19; // r8
  void *v20; // rbx
  void *v21; // rax
  void *v22; // rax
  void *v23; // rax
  wchar_t *v24; // rcx
  wchar_t *Format[2]; // [rsp+38h] [rbp-79h] BYREF
  __int64 v26; // [rsp+48h] [rbp-69h]
  unsigned __int64 v27; // [rsp+50h] [rbp-61h]
  int v28; // [rsp+58h] [rbp-59h]
  wchar_t Buffer[40]; // [rsp+60h] [rbp-51h] BYREF

  v10 = a7;
  v11 = 11;
  if ( a3 < 0xC )
    v11 = a3;
  GetCurrentProcessId();
  GetCurrentThreadId();
  v27 = 7;
  v26 = 0;
  LOWORD(Format[0]) = 0;
  v28 = -1;
  LOBYTE(v12) = 1;
  if ( (unsigned __int8)std::wstring::_Grow(Format, 513, v12) )
  {
    v13 = Format;
    if ( v27 >= 8 )
      v13 = (wchar_t **)Format[0];
    v26 = 0;
    *(_WORD *)v13 = 0;
  }
  v14 = (&g_pLevelStrs)[v11];
  v15 = -1;
  if ( v14 )
  {
    if ( *(_WORD *)v14 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *((_WORD *)v14 + v16) );
    }
    std::wstring::append(Format, v14);
  }
  std::wstring::append(Format, L" ");
  v17 = L"[missing file]";
  if ( a1 )
    v17 = a1;
  WriteFilename((struct TSTR *)Format, v17);
  std::wstring::append(Format, L":");
  v18 = _ultow(Value, Buffer, 10);
  if ( *v18 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
  }
  std::wstring::append(Format, v18);
  std::wstring::append(Format, L" ");
  v20 = (void *)operator<<(Format);
  std::wstring::append(v20, L":");
  v21 = (void *)operator<<(v20);
  std::wstring::append(v21, L" ");
  if ( (a4 & 1) != 0 )
  {
    v22 = (void *)operator<<(Format);
    std::wstring::append(v22, L" ");
  }
  if ( (a4 & 2) != 0 )
  {
    GetLastError();
    v23 = (void *)operator<<(Format);
    std::wstring::append(v23, L" ");
  }
  if ( a7 )
  {
    if ( *a7 )
    {
      do
        ++v15;
      while ( a7[v15] );
    }
  }
  else
  {
    v10 = L"[missing string]";
  }
  std::wstring::append(Format, v10);
  std::wstring::append(Format, L"\r\n");
  v24 = (wchar_t *)Format;
  if ( v27 >= 8 )
    v24 = Format[0];
  OutputDebugStringDBWIN(v24);
  if ( v27 >= 8 )
    operator delete(Format[0]);
}

```

## disassembly

```asm
0x1800026d0  mov     [rsp-8+arg_18], rbx
0x1800026d5  push    rbp
0x1800026d6  push    rsi
0x1800026d7  push    rdi
0x1800026d8  push    r12
0x1800026da  push    r13
0x1800026dc  push    r14
0x1800026de  push    r15
0x1800026e0  lea     rbp, [rsp-0Fh]
0x1800026e5  sub     rsp, 0C0h
0x1800026ec  mov     rax, cs:__security_cookie
0x1800026f3  xor     rax, rsp
0x1800026f6  mov     [rbp+3Fh+var_40], rax
0x1800026fa  mov     r15d, r9d
0x1800026fd  mov     r12d, edx
0x180002700  mov     rsi, rcx
0x180002703  mov     r14, [rbp+3Fh+arg_30]
0x180002707  mov     ebx, 0Bh
0x18000270c  cmp     r8d, 0Ch
0x180002710  cmovb   ebx, r8d
0x180002714  call    cs:__imp_GetCurrentProcessId
0x18000271a  mov     r13d, eax
0x18000271d  call    cs:__imp_GetCurrentThreadId
0x180002723  mov     [rsp+0F0h+var_C0], eax
0x180002727  mov     [rbp+3Fh+var_A0], 7
0x18000272f  xor     eax, eax
0x180002731  mov     [rbp+3Fh+var_A8], rax
0x180002735  mov     word ptr [rbp+3Fh+Format], ax
0x180002739  mov     [rbp+3Fh+var_98], 0FFFFFFFFh
0x180002740  mov     r8b, 1
0x180002743  mov     edx, 201h
0x180002748  lea     rcx, [rbp+3Fh+Format]
0x18000274c  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180002751  xor     r9d, r9d
0x180002754  test    al, al
0x180002756  jz      short loc_18000276E
0x180002758  lea     rcx, [rbp+3Fh+Format]
0x18000275c  cmp     [rbp+3Fh+var_A0], 8
0x180002761  cmovnb  rcx, [rbp+3Fh+Format]
0x180002766  mov     [rbp+3Fh+var_A8], r9
0x18000276a  mov     [rcx], r9w
0x18000276e  lea     rdx, ?g_pLevelStrs@@3PAPEBGA; ushort const * near * g_pLevelStrs
0x180002775  mov     rdx, [rdx+rbx*8]; void *
0x180002779  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000277d  test    rdx, rdx
0x180002780  jz      short loc_1800027A3
0x180002782  cmp     [rdx], r9w
0x180002786  jnz     short loc_18000278D
0x180002788  mov     r8, r9
0x18000278b  jmp     short loc_18000279A
0x18000278d  mov     r8, rdi
0x180002790  inc     r8
0x180002793  cmp     [rdx+r8*2], r9w
0x180002798  jnz     short loc_180002790
0x18000279a  lea     rcx, [rbp+3Fh+Format]; Src
0x18000279e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800027a3  mov     r8d, 1
0x1800027a9  lea     rdx, asc_18001BF08; " "
0x1800027b0  lea     rcx, [rbp+3Fh+Format]; Src
0x1800027b4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800027b9  lea     rdx, aMissingFile; "[missing file]"
0x1800027c0  test    rsi, rsi
0x1800027c3  cmovnz  rdx, rsi; unsigned __int16 *
0x1800027c7  lea     rcx, [rbp+3Fh+Format]; struct TSTR *
0x1800027cb  call    ?WriteFilename@@YAXAEAVTSTR@@PEBG@Z; WriteFilename(TSTR &,ushort const *)
0x1800027d0  mov     esi, 1
0x1800027d5  mov     r8d, esi
0x1800027d8  lea     rdx, asc_18001BFC0; ":"
0x1800027df  lea     rcx, [rbp+3Fh+Format]; Src
0x1800027e3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800027e8  lea     r8d, [rsi+9]; Radix
0x1800027ec  lea     rdx, [rbp+3Fh+Buffer]; Buffer
0x1800027f0  mov     ecx, r12d; Value
0x1800027f3  call    cs:__imp__ultow
0x1800027f9  xor     r12d, r12d
0x1800027fc  cmp     [rax], r12w
0x180002800  jnz     short loc_180002807
0x180002802  mov     r8d, r12d
0x180002805  jmp     short loc_180002814
0x180002807  mov     r8, rdi
0x18000280a  inc     r8
0x18000280d  cmp     [rax+r8*2], r12w
0x180002812  jnz     short loc_18000280A
0x180002814  mov     rdx, rax; void *
0x180002817  lea     rcx, [rbp+3Fh+Format]; Src
0x18000281b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002820  mov     r8, rsi
0x180002823  lea     rdx, asc_18001BF08; " "
0x18000282a  lea     rcx, [rbp+3Fh+Format]; Src
0x18000282e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002833  mov     [rsp+0F0h+var_D0], r13
0x180002838  mov     dword ptr [rsp+0F0h+var_C8], edi
0x18000283c  lea     rdx, [rsp+0F0h+var_D0]
0x180002841  lea     rcx, [rbp+3Fh+Format]; Src
0x180002845  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteHex@@@Z; operator<<(TSTR &,WriteHex const &)
0x18000284a  mov     rbx, rax
0x18000284d  mov     r8, rsi
0x180002850  lea     rdx, asc_18001BFC0; ":"
0x180002857  mov     rcx, rax; Src
0x18000285a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000285f  mov     ecx, [rsp+0F0h+var_C0]
0x180002863  mov     [rsp+0F0h+var_D0], rcx
0x180002868  mov     dword ptr [rsp+0F0h+var_C8], edi
0x18000286c  lea     rdx, [rsp+0F0h+var_D0]
0x180002871  mov     rcx, rbx; Src
0x180002874  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteHex@@@Z; operator<<(TSTR &,WriteHex const &)
0x180002879  mov     rcx, rax; Src
0x18000287c  mov     r8, rsi
0x18000287f  lea     rbx, asc_18001BF08; " "
0x180002886  mov     rdx, rbx; void *
0x180002889  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000288e  test    sil, r15b
0x180002891  jz      short loc_1800028BB
0x180002893  mov     eax, [rbp+3Fh+arg_28]
0x180002896  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18000289a  mov     [rsp+0F0h+var_C8], r12
0x18000289f  lea     rdx, [rsp+0F0h+var_D0]
0x1800028a4  lea     rcx, [rbp+3Fh+Format]; Src
0x1800028a8  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteError@@@Z; operator<<(TSTR &,WriteError const &)
0x1800028ad  mov     rcx, rax; Src
0x1800028b0  mov     r8, rsi
0x1800028b3  mov     rdx, rbx; void *
0x1800028b6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800028bb  mov     esi, 2
0x1800028c0  test    sil, r15b
0x1800028c3  jz      short loc_1800028F1
0x1800028c5  call    cs:__imp_GetLastError
0x1800028cb  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800028cf  mov     [rsp+0F0h+var_C8], r12
0x1800028d4  lea     rdx, [rsp+0F0h+var_D0]
0x1800028d9  lea     rcx, [rbp+3Fh+Format]; Src
0x1800028dd  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteError@@@Z; operator<<(TSTR &,WriteError const &)
0x1800028e2  mov     rcx, rax; Src
0x1800028e5  lea     r8d, [rsi-1]
0x1800028e9  mov     rdx, rbx; void *
0x1800028ec  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800028f1  test    r14, r14
0x1800028f4  jnz     short loc_180002904
0x1800028f6  lea     r14, aMissingString; "[missing string]"
0x1800028fd  mov     edi, 10h
0x180002902  jmp     short loc_180002919
0x180002904  cmp     [r14], r12w
0x180002908  jnz     short loc_18000290F
0x18000290a  mov     rdi, r12
0x18000290d  jmp     short loc_180002919
0x18000290f  inc     rdi
0x180002912  cmp     [r14+rdi*2], r12w
0x180002917  jnz     short loc_18000290F
0x180002919  lea     rbx, asc_18001BFC4; "\r\n"
0x180002920  lea     r15, [rbp+3Fh+Format]
0x180002924  mov     r8, rdi
0x180002927  mov     rdx, r14; void *
0x18000292a  mov     rcx, r15; Src
0x18000292d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002932  mov     r8, rsi
0x180002935  mov     rdx, rbx; void *
0x180002938  mov     rcx, r15; Src
0x18000293b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002940  lea     rcx, [rbp+3Fh+Format]
0x180002944  cmp     [rbp+3Fh+var_A0], 8
0x180002949  cmovnb  rcx, [rbp+3Fh+Format]; Format
0x18000294e  call    ?OutputDebugStringDBWIN@@YAXPEBGZZ; OutputDebugStringDBWIN(ushort const *,...)
0x180002953  nop
0x180002954  cmp     [rbp+3Fh+var_A0], 8
0x180002959  jb      short loc_180002965
0x18000295b  mov     rcx, [rbp+3Fh+Format]
0x18000295f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002965  mov     rcx, [rbp+3Fh+var_40]
0x180002969  xor     rcx, rsp; StackCookie
0x18000296c  call    __security_check_cookie
0x180002971  mov     rbx, [rsp+0F0h+arg_18]
0x180002979  add     rsp, 0C0h
0x180002980  pop     r15
0x180002982  pop     r14
0x180002984  pop     r13
0x180002986  pop     r12
0x180002988  pop     rdi
0x180002989  pop     rsi
0x18000298a  pop     rbp
0x18000298b  retn
```
