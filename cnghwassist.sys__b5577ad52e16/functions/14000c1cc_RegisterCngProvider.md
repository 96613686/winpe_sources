# RegisterCngProvider

- ea: `0x14000c1cc`
- end: `0x14000c318`
- name: `RegisterCngProvider`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c078`

## callees

- `0x14000c1cc`

## import_xrefs

- `cng!BCryptAddContextFunctionProvider` at `0x14000c2e3`
- `cng!BCryptAddContextFunctionProvider` at `0x14000c2e3`
- `cng!BCryptUnregisterProvider` at `0x14000c228`
- `cng!BCryptUnregisterProvider` at `0x14000c228`
- `cng!BCryptRegisterProvider` at `0x14000c2ba`
- `cng!BCryptRegisterProvider` at `0x14000c2ba`
- `cng!BCryptFreeBuffer` at `0x14000c2fa`
- `cng!BCryptFreeBuffer` at `0x14000c2fa`
- `cng!BCryptResolveProviders` at `0x14000c29c`
- `cng!BCryptResolveProviders` at `0x14000c29c`

## pseudocode

```c
__int64 RegisterCngProvider()
{
  NTSTATUS v0; // ebx
  __int128 v2; // [rsp+40h] [rbp-19h] BYREF
  const wchar_t **v3; // [rsp+50h] [rbp-9h]
  __int128 v4; // [rsp+58h] [rbp-1h] BYREF
  __int128 **v5; // [rsp+68h] [rbp+Fh]
  __int128 v6; // [rsp+70h] [rbp+17h] BYREF
  __int128 v7; // [rsp+80h] [rbp+27h]
  ULONG pcbBuffer; // [rsp+C0h] [rbp+67h] BYREF
  __int128 *v9; // [rsp+C8h] [rbp+6Fh] BYREF
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+D0h] [rbp+77h] BYREF
  const wchar_t *v11; // [rsp+D8h] [rbp+7Fh] BYREF

  ppBuffer = 0;
  pcbBuffer = 0;
  v5 = 0;
  v9 = 0;
  v11 = L"AES";
  v2 = 0;
  v4 = 0;
  v6 = 0;
  v7 = 0;
  BCryptUnregisterProvider(L"CngHwAssist");
  v9 = &v2;
  *(_QWORD *)&v2 = 0x100000001LL;
  v3 = &v11;
  *(_QWORD *)&v4 = L"CngHwAssist.sys";
  DWORD2(v2) = 1;
  v5 = &v9;
  DWORD2(v4) = 1;
  *((_QWORD *)&v7 + 1) = &v4;
  v0 = BCryptResolveProviders(0, 0, L"AES", L"CngHwAssist", 2u, 0, &pcbBuffer, &ppBuffer);
  if ( v0 == -1073741275 )
  {
    v0 = BCryptRegisterProvider(L"CngHwAssist", 0, &v6);
    if ( v0 >= 0 )
      v0 = BCryptAddContextFunctionProvider(1, 0, 1, L"AES", L"CngHwAssist", -1);
  }
  if ( ppBuffer )
    BCryptFreeBuffer(ppBuffer);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000c1cc  push    rbp
0x14000c1ce  push    rbx
0x14000c1cf  push    rsi
0x14000c1d0  push    r14
0x14000c1d2  push    r15
0x14000c1d4  lea     rbp, [rsp-37h]
0x14000c1d9  sub     rsp, 90h
0x14000c1e0  xorps   xmm0, xmm0
0x14000c1e3  mov     [rbp+57h+arg_10], 0
0x14000c1eb  xor     eax, eax
0x14000c1ed  mov     [rbp+57h+arg_0], 0
0x14000c1f4  xorps   xmm1, xmm1
0x14000c1f7  mov     [rbp+57h+var_60], rax
0x14000c1fb  lea     r14, pszProvider; "CngHwAssist"
0x14000c202  mov     [rbp+57h+var_48], rax
0x14000c206  lea     r15, aAes; "AES"
0x14000c20d  mov     [rbp+57h+arg_8], rax
0x14000c211  mov     rcx, r14
0x14000c214  mov     [rbp+57h+arg_18], r15
0x14000c218  movups  [rbp+57h+var_70], xmm0
0x14000c21c  movups  [rbp+57h+var_58], xmm1
0x14000c220  movups  [rbp+57h+var_40], xmm0
0x14000c224  movups  [rbp+57h+var_30], xmm0
0x14000c228  call    cs:__imp_BCryptUnregisterProvider
0x14000c22f  nop     dword ptr [rax+rax+00h]
0x14000c234  mov     esi, 1
0x14000c239  lea     rax, [rbp+57h+var_70]
0x14000c23d  mov     [rbp+57h+arg_8], rax
0x14000c241  mov     r9, r14; pszProvider
0x14000c244  lea     rax, [rbp+57h+arg_18]
0x14000c248  mov     dword ptr [rbp+57h+var_70], esi
0x14000c24b  mov     [rbp+57h+var_60], rax
0x14000c24f  mov     r8, r15; pszFunction
0x14000c252  lea     rax, aCnghwassistSys; "CngHwAssist.sys"
0x14000c259  mov     dword ptr [rbp+57h+var_70+4], esi
0x14000c25c  mov     qword ptr [rbp+57h+var_58], rax
0x14000c260  xor     edx, edx; dwInterface
0x14000c262  lea     rax, [rbp+57h+arg_8]
0x14000c266  mov     dword ptr [rbp+57h+var_70+8], esi
0x14000c269  mov     [rbp+57h+var_48], rax
0x14000c26d  xor     ecx, ecx; pszContext
0x14000c26f  lea     rax, [rbp+57h+var_58]
0x14000c273  mov     dword ptr [rbp+57h+var_58+8], esi
0x14000c276  mov     qword ptr [rbp+57h+var_30+8], rax
0x14000c27a  lea     rax, [rbp+57h+arg_10]
0x14000c27e  mov     [rsp+0B0h+ppBuffer], rax; ppBuffer
0x14000c283  lea     rax, [rbp+57h+arg_0]
0x14000c287  mov     [rsp+0B0h+pcbBuffer], rax; pcbBuffer
0x14000c28c  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x14000c294  mov     [rsp+0B0h+dwMode], 2; dwMode
0x14000c29c  call    cs:__imp_BCryptResolveProviders
0x14000c2a3  nop     dword ptr [rax+rax+00h]
0x14000c2a8  mov     ebx, eax
0x14000c2aa  cmp     eax, 0C0000225h
0x14000c2af  jnz     short loc_14000C2F1
0x14000c2b1  lea     r8, [rbp+57h+var_40]
0x14000c2b5  xor     edx, edx
0x14000c2b7  mov     rcx, r14
0x14000c2ba  call    cs:__imp_BCryptRegisterProvider
0x14000c2c1  nop     dword ptr [rax+rax+00h]
0x14000c2c6  mov     ebx, eax
0x14000c2c8  test    eax, eax
0x14000c2ca  js      short loc_14000C2F1
0x14000c2cc  mov     [rsp+0B0h+dwFlags], 0FFFFFFFFh
0x14000c2d4  mov     r9, r15
0x14000c2d7  mov     r8d, esi
0x14000c2da  mov     qword ptr [rsp+0B0h+dwMode], r14
0x14000c2df  xor     edx, edx
0x14000c2e1  mov     ecx, esi
0x14000c2e3  call    cs:__imp_BCryptAddContextFunctionProvider
0x14000c2ea  nop     dword ptr [rax+rax+00h]
0x14000c2ef  mov     ebx, eax
0x14000c2f1  mov     rcx, [rbp+57h+arg_10]; pvBuffer
0x14000c2f5  test    rcx, rcx
0x14000c2f8  jz      short loc_14000C306
0x14000c2fa  call    cs:__imp_BCryptFreeBuffer
0x14000c301  nop     dword ptr [rax+rax+00h]
0x14000c306  mov     eax, ebx
0x14000c308  add     rsp, 90h
0x14000c30f  pop     r15
0x14000c311  pop     r14
0x14000c313  pop     rsi
0x14000c314  pop     rbx
0x14000c315  pop     rbp
0x14000c316  retn
```
