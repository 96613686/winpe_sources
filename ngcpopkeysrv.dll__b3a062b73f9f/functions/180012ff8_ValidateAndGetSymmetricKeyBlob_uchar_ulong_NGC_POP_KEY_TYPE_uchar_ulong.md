# ValidateAndGetSymmetricKeyBlob(uchar *,ulong,_NGC_POP_KEY_TYPE *,uchar * *,ulong *)

- ea: `0x180012ff8`
- end: `0x18001304e`
- name: `?ValidateAndGetSymmetricKeyBlob@@YAJPEAEKPEAW4_NGC_POP_KEY_TYPE@@PEAPEAEPEAK@Z`
- size: `86`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, enum _NGC_POP_KEY_TYPE *, unsigned __int8 **, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dc78`
- `0x18000eae0`
- `0x18000f230`
- `0x18000f6b0`
- `0x18000f8b8`
- `0x18000fc20`

## callees

- `0x18000b0fc`
- `0x180012ff8`

## string_xrefs

- `0x18001300b`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ValidateAndGetSymmetricKeyBlob(
        unsigned __int8 *a1,
        unsigned int a2,
        enum _NGC_POP_KEY_TYPE *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 < 8 )
  {
    v5 = 22;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
      (const char *)0x8009000DLL,
      v7);
    return 2148073485LL;
  }
  if ( *(_DWORD *)a1 != 1 )
  {
    v5 = 23;
    goto LABEL_3;
  }
  *(_DWORD *)a3 = *((_DWORD *)a1 + 1);
  *a4 = a1 + 8;
  *a5 = a2 - 8;
  return 0;
}

```

## disassembly

```asm
0x180012ff8  sub     rsp, 28h
0x180012ffc  cmp     edx, 8
0x180012fff  jnb     short loc_180013024
0x180013001  mov     edx, 16h; void *
0x180013006  mov     rcx, [rsp+28h]; this
0x18001300b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180013012  mov     r9d, 8009000Dh; char *
0x180013018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001301d  mov     eax, 8009000Dh
0x180013022  jmp     short loc_180013049
0x180013024  cmp     dword ptr [rcx], 1
0x180013027  jz      short loc_180013030
0x180013029  mov     edx, 17h
0x18001302e  jmp     short loc_180013006
0x180013030  mov     eax, [rcx+4]
0x180013033  mov     [r8], eax
0x180013036  lea     rax, [rcx+8]
0x18001303a  mov     [r9], rax
0x18001303d  lea     ecx, [rdx-8]
0x180013040  mov     rax, [rsp+28h+arg_20]
0x180013045  mov     [rax], ecx
0x180013047  xor     eax, eax
0x180013049  add     rsp, 28h
0x18001304d  retn
```
