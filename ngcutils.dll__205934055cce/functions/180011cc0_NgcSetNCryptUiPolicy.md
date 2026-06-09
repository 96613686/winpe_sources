# NgcSetNCryptUiPolicy

- ea: `0x180011cc0`
- end: `0x180011d50`
- name: `NgcSetNCryptUiPolicy`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180011cc0`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180011cff`
- `ncrypt!NCryptSetProperty` at `0x180011cff`

## string_xrefs

- `0x180011d2c`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180011d13`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcSetNCryptUiPolicy(NCRYPT_HANDLE a1, __int64 a2)
{
  SECURITY_STATUS v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-38h]
  int v6; // [rsp+20h] [rbp-38h]
  int v7; // [rsp+30h] [rbp-28h] BYREF
  __int128 v8; // [rsp+34h] [rbp-24h]
  int v9; // [rsp+44h] [rbp-14h]
  __int64 v10; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    return 0;
  v8 = 0;
  v9 = 0;
  v7 = 1;
  v10 = a2;
  v2 = NCryptSetProperty(a1, L"UI Policy", (PBYTE)&v7, 0x20u, 0);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19E,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
    (const char *)(unsigned int)v2,
    v5);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
    (const char *)v3,
    v6);
  return v3;
}

```

## disassembly

```asm
0x180011cc0  mov     rax, rsp
0x180011cc3  push    rbx
0x180011cc4  sub     rsp, 50h
0x180011cc8  test    rdx, rdx
0x180011ccb  jz      short loc_180011D41
0x180011ccd  xorps   xmm0, xmm0
0x180011cd0  movdqu  xmmword ptr [rax-24h], xmm0
0x180011cd5  mov     dword ptr [rax-14h], 0
0x180011cdc  mov     dword ptr [rax-28h], 1
0x180011ce3  mov     [rax-10h], rdx
0x180011ce7  mov     dword ptr [rax-38h], 0
0x180011cee  mov     r9d, 20h ; ' '; cbInput
0x180011cf4  lea     r8, [rax-28h]; pbInput
0x180011cf8  lea     rdx, pszProperty; "UI Policy"
0x180011cff  call    cs:__imp_NCryptSetProperty
0x180011d05  mov     ebx, eax
0x180011d07  test    eax, eax
0x180011d09  jns     short loc_180011D41
0x180011d0b  mov     rcx, [rsp+58h]; this
0x180011d10  mov     r9d, eax; char *
0x180011d13  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011d1a  mov     edx, 19Eh; void *
0x180011d1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d24  mov     rcx, [rsp+58h]; this
0x180011d29  mov     r9d, ebx; char *
0x180011d2c  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011d33  mov     edx, 0D5h; void *
0x180011d38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d3d  mov     eax, ebx
0x180011d3f  jmp     short loc_180011D49
0x180011d41  xor     eax, eax
0x180011d43  jmp     short loc_180011D49
0x180011d45  mov     eax, [rsp+58h+arg_8]
0x180011d49  add     rsp, 50h
0x180011d4d  pop     rbx
0x180011d4e  retn
```
