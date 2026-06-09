# I_CatDBEventSubsystemAndCatalogTemplate

- ea: `0x18000938c`
- end: `0x18000943a`
- name: `I_CatDBEventSubsystemAndCatalogTemplate`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a490`
- `0x18001b8f4`
- `0x18001c9e0`

## callees

- `0x18000938c`
- `0x18000be40`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000941e`
- `ntdll!EtwEventWrite` at `0x18000941e`
- `ntdll!EtwEventEnabled` at `0x1800093be`
- `ntdll!EtwEventEnabled` at `0x1800093be`

## pseudocode

```c
void __fastcall I_CatDBEventSubsystemAndCatalogTemplate(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // [rsp+20h] [rbp-58h] BYREF
  int v9; // [rsp+28h] [rbp-50h]
  int v10; // [rsp+2Ch] [rbp-4Ch]
  __int64 v11; // [rsp+30h] [rbp-48h]
  int v12; // [rsp+38h] [rbp-40h]
  int v13; // [rsp+3Ch] [rbp-3Ch]

  if ( qword_180032A08 && (unsigned __int8)EtwEventEnabled(qword_180032A08, a3) )
  {
    v6 = -1;
    v8 = a1;
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a1 + 2 * v7) );
    v10 = 0;
    v9 = 2 * v7 + 2;
    v11 = a2;
    do
      ++v6;
    while ( *(_WORD *)(a2 + 2 * v6) );
    v13 = 0;
    v12 = 2 * v6 + 2;
    EtwEventWrite(qword_180032A08, a3, 2, &v8);
  }
}

```

## disassembly

```asm
0x18000938c  push    rbx
0x18000938e  push    rbp
0x18000938f  push    rsi
0x180009390  push    rdi
0x180009391  sub     rsp, 58h
0x180009395  mov     rax, cs:__security_cookie
0x18000939c  xor     rax, rsp
0x18000939f  mov     [rsp+78h+var_38], rax
0x1800093a4  mov     rbx, rcx
0x1800093a7  xor     ebp, ebp
0x1800093a9  mov     rcx, cs:qword_180032A08
0x1800093b0  mov     rsi, r8
0x1800093b3  mov     rdi, rdx
0x1800093b6  test    rcx, rcx
0x1800093b9  jz      short loc_180009424
0x1800093bb  mov     rdx, r8
0x1800093be  call    cs:__imp_EtwEventEnabled
0x1800093c4  test    al, al
0x1800093c6  jz      short loc_180009424
0x1800093c8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800093cc  mov     [rsp+78h+var_58], rbx
0x1800093d1  mov     rax, rcx
0x1800093d4  inc     rax
0x1800093d7  cmp     [rbx+rax*2], bp
0x1800093db  jnz     short loc_1800093D4
0x1800093dd  lea     eax, ds:2[rax*2]
0x1800093e4  mov     [rsp+78h+var_4C], ebp
0x1800093e8  mov     [rsp+78h+var_50], eax
0x1800093ec  mov     [rsp+78h+var_48], rdi
0x1800093f1  inc     rcx
0x1800093f4  cmp     [rdi+rcx*2], bp
0x1800093f8  jnz     short loc_1800093F1
0x1800093fa  lea     eax, ds:2[rcx*2]
0x180009401  mov     [rsp+78h+var_3C], ebp
0x180009405  mov     rcx, cs:qword_180032A08
0x18000940c  lea     r9, [rsp+78h+var_58]
0x180009411  mov     r8d, 2
0x180009417  mov     [rsp+78h+var_40], eax
0x18000941b  mov     rdx, rsi
0x18000941e  call    cs:__imp_EtwEventWrite
0x180009424  mov     rcx, [rsp+78h+var_38]
0x180009429  xor     rcx, rsp; StackCookie
0x18000942c  call    __security_check_cookie
0x180009431  add     rsp, 58h
0x180009435  pop     rdi
0x180009436  pop     rsi
0x180009437  pop     rbp
0x180009438  pop     rbx
0x180009439  retn
```
