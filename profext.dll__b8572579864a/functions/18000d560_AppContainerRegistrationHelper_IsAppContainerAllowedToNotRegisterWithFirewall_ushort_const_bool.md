# AppContainerRegistrationHelper::IsAppContainerAllowedToNotRegisterWithFirewall(ushort const *,bool *)

- ea: `0x18000d560`
- end: `0x18000d5f0`
- name: `?IsAppContainerAllowedToNotRegisterWithFirewall@AppContainerRegistrationHelper@@CAJPEBGPEA_N@Z`
- size: `144`
- prototype: `__int64 __fastcall(LPCWCH lpString2, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d980`
- `0x18000ea1c`

## callees

- `0x180004594`
- `0x18000d560`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d5c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000d5c5`

## string_xrefs

- `0x18000d581`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::IsAppContainerAllowedToNotRegisterWithFirewall(
        LPCWCH lpString2,
        bool *a2)
{
  unsigned int v2; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = 0;
  if ( a2 )
  {
    *a2 = 0;
    while ( v2 < 5 )
    {
      if ( CompareStringOrdinal(off_180025BB8[v2], -1, lpString2, -1, 1) == 2 )
      {
        *a2 = 1;
        return 0;
      }
      ++v2;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC6,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000d560  mov     [rsp+arg_0], rbx
0x18000d565  mov     [rsp+arg_8], rsi
0x18000d56a  push    rdi
0x18000d56b  sub     rsp, 30h
0x18000d56f  xor     ebx, ebx
0x18000d571  mov     rdi, rdx
0x18000d574  mov     rsi, rcx
0x18000d577  test    rdx, rdx
0x18000d57a  jnz     short loc_18000D59E
0x18000d57c  mov     rcx, [rsp+38h]; this
0x18000d581  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d588  mov     ebx, 80070057h
0x18000d58d  mov     edx, 0CC6h; void *
0x18000d592  mov     r9d, ebx; char *
0x18000d595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d59a  mov     eax, ebx
0x18000d59c  jmp     short loc_18000D5DF
0x18000d59e  mov     [rdx], bl
0x18000d5a0  cmp     ebx, 5
0x18000d5a3  jnb     short loc_18000D5DD
0x18000d5a5  lea     rax, off_180025BB8; "Microsoft.Windows.Cortana_cw5n1h2txyewy"
0x18000d5ac  movsxd  rcx, ebx
0x18000d5af  or      r9d, 0FFFFFFFFh; cchCount2
0x18000d5b3  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000d5bb  mov     r8, rsi; lpString2
0x18000d5be  or      edx, r9d; cchCount1
0x18000d5c1  mov     rcx, [rax+rcx*8]; lpString1
0x18000d5c5  call    cs:__imp_CompareStringOrdinal
0x18000d5cc  nop     dword ptr [rax+rax+00h]
0x18000d5d1  cmp     eax, 2
0x18000d5d4  jz      short loc_18000D5DA
0x18000d5d6  inc     ebx
0x18000d5d8  jmp     short loc_18000D5A0
0x18000d5da  mov     byte ptr [rdi], 1
0x18000d5dd  xor     eax, eax
0x18000d5df  mov     rbx, [rsp+38h+arg_0]
0x18000d5e4  mov     rsi, [rsp+38h+arg_8]
0x18000d5e9  add     rsp, 30h
0x18000d5ed  pop     rdi
0x18000d5ee  retn
```
