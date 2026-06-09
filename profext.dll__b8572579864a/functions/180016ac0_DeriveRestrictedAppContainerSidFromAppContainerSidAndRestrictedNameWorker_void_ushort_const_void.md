# DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker(void *,ushort const *,void * *)

- ea: `0x180016ac0`
- end: `0x180016b3e`
- name: `?DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker@@YAJPEAXPEBGPEAPEAX@Z`
- size: `126`
- prototype: `int(void *, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180004594`
- `0x180016740`
- `0x180016ac0`

## string_xrefs

- `0x180016ad8`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180016b1e`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker(
        void *a1,
        char *a2,
        void **a3)
{
  __int64 v4; // rdx
  unsigned int v6; // eax
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a1 )
  {
    v4 = 3137;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v7);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v4 = 3138;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v4 = 3139;
    goto LABEL_3;
  }
  v6 = AppContainerRegistrationHelper::DeriveChildAppContainerSid(a1, a2, a3);
  return wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0xC49,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
           (const char *)v6,
           (__int64)"RAC %ls",
           a2);
}

```

## disassembly

```asm
0x180016ac0  push    rbx
0x180016ac2  sub     rsp, 30h
0x180016ac6  mov     rbx, rdx
0x180016ac9  test    rcx, rcx
0x180016acc  jnz     short loc_180016AF0
0x180016ace  mov     edx, 0C41h; void *
0x180016ad3  mov     rcx, [rsp+38h]; this
0x180016ad8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016adf  mov     ebx, 80070057h
0x180016ae4  mov     r9d, ebx; char *
0x180016ae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016aec  mov     eax, ebx
0x180016aee  jmp     short loc_180016B37
0x180016af0  test    rbx, rbx
0x180016af3  jnz     short loc_180016AFC
0x180016af5  mov     edx, 0C42h
0x180016afa  jmp     short loc_180016AD3
0x180016afc  test    r8, r8
0x180016aff  jnz     short loc_180016B08
0x180016b01  mov     edx, 0C43h; char *
0x180016b06  jmp     short loc_180016AD3
0x180016b08  call    ?DeriveChildAppContainerSid@AppContainerRegistrationHelper@@SAJPEAXPEBGPEAPEAX@Z; AppContainerRegistrationHelper::DeriveChildAppContainerSid(void *,ushort const *,void * *)
0x180016b0d  mov     rcx, [rsp+38h]; this
0x180016b12  lea     rdx, aRacLs; "RAC %ls"
0x180016b19  mov     [rsp+38h+var_10], rbx; char *
0x180016b1e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016b25  mov     [rsp+38h+var_18], rdx; __int64
0x180016b2a  mov     r9d, eax; char *
0x180016b2d  mov     edx, 0C49h; void *
0x180016b32  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016b37  add     rsp, 30h
0x180016b3b  pop     rbx
0x180016b3c  retn
```
