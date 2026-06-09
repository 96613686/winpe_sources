# LpacCapabilityStore::AppendCapabilityArray(_APPCONTAINER_CAPABILITY const *,ulong)

- ea: `0x18001e520`
- end: `0x18001e5a8`
- name: `?AppendCapabilityArray@LpacCapabilityStore@@QEAAJPEBU_APPCONTAINER_CAPABILITY@@K@Z`
- size: `136`
- prototype: `__int64 __fastcall(LpacCapabilityStore *__hidden this, const struct _APPCONTAINER_CAPABILITY *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001dcb0`

## callees

- `0x180004594`
- `0x18001e430`
- `0x18001e520`

## string_xrefs

- `0x18001e543`: `onecore\ds\security\gina\profile\profext\lpaccapabilitystore.cpp`
- `0x18001e590`: `onecore\ds\security\gina\profile\profext\lpaccapabilitystore.cpp`

## pseudocode

```c
__int64 __fastcall LpacCapabilityStore::AppendCapabilityArray(
        LpacCapabilityStore *this,
        const unsigned __int16 **a2,
        unsigned int a3)
{
  __int64 v7; // rbx
  int v8; // eax
  unsigned int v9; // esi
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 || !a3 )
  {
    v7 = 0;
    if ( a3 )
    {
      while ( 1 )
      {
        v8 = LpacCapabilityStore::AddCapability(this, a2[v7]);
        v9 = v8;
        if ( v8 < 0 )
          break;
        v7 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v7 >= a3 )
          return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpaccapabilitystore.cpp",
        (const char *)(unsigned int)v8,
        v10);
      return v9;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpaccapabilitystore.cpp",
      (const char *)0x80070057LL,
      v10);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001e520  push    rbx
0x18001e522  push    rbp
0x18001e523  push    rsi
0x18001e524  push    rdi
0x18001e525  push    r14; int
0x18001e527  sub     rsp, 20h
0x18001e52b  mov     edi, r8d
0x18001e52e  mov     r14, rdx
0x18001e531  mov     rbp, rcx
0x18001e534  test    rdx, rdx
0x18001e537  jnz     short loc_18001E55F
0x18001e539  test    r8d, r8d
0x18001e53c  jz      short loc_18001E55F
0x18001e53e  mov     rcx, [rsp+48h]; this
0x18001e543  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e54a  mov     ebx, 80070057h
0x18001e54f  lea     edx, [r14+35h]; void *
0x18001e553  mov     r9d, ebx; char *
0x18001e556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e55b  mov     eax, ebx
0x18001e55d  jmp     short loc_18001E57F
0x18001e55f  xor     ebx, ebx
0x18001e561  test    edi, edi
0x18001e563  jz      short loc_18001E57D
0x18001e565  mov     rdx, [r14+rbx*8]; unsigned __int16 *
0x18001e569  mov     rcx, rbp; this
0x18001e56c  call    ?AddCapability@LpacCapabilityStore@@QEAAJPEBG@Z; LpacCapabilityStore::AddCapability(ushort const *)
0x18001e571  mov     esi, eax
0x18001e573  test    eax, eax
0x18001e575  js      short loc_18001E58B
0x18001e577  inc     ebx
0x18001e579  cmp     ebx, edi
0x18001e57b  jb      short loc_18001E565
0x18001e57d  xor     eax, eax
0x18001e57f  add     rsp, 20h
0x18001e583  pop     r14
0x18001e585  pop     rdi
0x18001e586  pop     rsi
0x18001e587  pop     rbp
0x18001e588  pop     rbx
0x18001e589  retn
0x18001e58b  mov     rcx, [rsp+48h]; this
0x18001e590  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e597  mov     r9d, esi; char *
0x18001e59a  mov     edx, 38h ; '8'; void *
0x18001e59f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5a4  mov     eax, esi
0x18001e5a6  jmp     short loc_18001E57F
```
