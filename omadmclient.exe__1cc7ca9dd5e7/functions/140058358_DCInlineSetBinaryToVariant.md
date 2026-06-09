# DCInlineSetBinaryToVariant

- ea: `0x140058358`
- end: `0x14005845a`
- name: `DCInlineSetBinaryToVariant`
- size: `258`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14005c570`

## callees

- `0x14000597e`
- `0x140058358`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400583a1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400583a1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140058438`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140058438`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400583c7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400583c7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400583f8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140058429`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400583f8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140058429`

## pseudocode

```c
__int64 __fastcall DCInlineSetBinaryToVariant(void *Src, size_t Size, __int64 a3)
{
  size_t v3; // rbp
  SAFEARRAY *v7; // rax
  SAFEARRAY *v8; // rbx
  HRESULT v9; // edi
  void *ppvData; // [rsp+50h] [rbp+18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp+20h] BYREF

  v3 = (unsigned int)Size;
  rgsabound.lLbound = 0;
  ppvData = 0;
  if ( !a3 )
    return 2147942487LL;
  rgsabound.lLbound = 0;
  rgsabound.cElements = Size;
  v7 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v8 = v7;
  if ( v7 )
  {
    v9 = SafeArrayAccessData(v7, &ppvData);
    if ( v9 < 0 )
      goto LABEL_10;
    if ( !ppvData )
      return 2147549183LL;
    memcpy_0(ppvData, Src, v3);
    v9 = SafeArrayUnaccessData(v8);
    if ( v9 < 0 )
    {
LABEL_10:
      if ( ppvData )
        SafeArrayUnaccessData(v8);
      SafeArrayDestroy(v8);
    }
    else
    {
      ppvData = 0;
      *(_QWORD *)(a3 + 8) = v8;
      *(_WORD *)a3 = 8209;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140058358  mov     [rsp+arg_0], rbx
0x14005835d  mov     [rsp+arg_8], rbp
0x140058362  push    rsi
0x140058363  push    rdi
0x140058364  push    r14
0x140058366  sub     rsp, 20h
0x14005836a  xor     eax, eax
0x14005836c  mov     ebp, edx
0x14005836e  mov     [rsp+38h+rgsabound.lLbound], eax
0x140058372  mov     rsi, r8
0x140058375  mov     [rsp+38h+ppvData], rax
0x14005837a  mov     r14, rcx
0x14005837d  test    r8, r8
0x140058380  jnz     short loc_14005838C
0x140058382  mov     eax, 80070057h
0x140058387  jmp     loc_140058446
0x14005838c  mov     ecx, 11h; vt
0x140058391  mov     [rsp+38h+rgsabound.lLbound], eax
0x140058395  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x14005839a  mov     [rsp+38h+rgsabound.cElements], ebp
0x14005839e  lea     edx, [rcx-10h]; cDims
0x1400583a1  call    cs:__imp_SafeArrayCreate
0x1400583a8  nop     dword ptr [rax+rax+00h]
0x1400583ad  mov     rbx, rax
0x1400583b0  test    rax, rax
0x1400583b3  jnz     short loc_1400583BF
0x1400583b5  mov     edi, 8007000Eh
0x1400583ba  jmp     loc_140058444
0x1400583bf  lea     rdx, [rsp+38h+ppvData]; ppvData
0x1400583c4  mov     rcx, rbx; psa
0x1400583c7  call    cs:__imp_SafeArrayAccessData
0x1400583ce  nop     dword ptr [rax+rax+00h]
0x1400583d3  mov     edi, eax
0x1400583d5  test    eax, eax
0x1400583d7  js      short loc_14005841E
0x1400583d9  mov     rcx, [rsp+38h+ppvData]; void *
0x1400583de  test    rcx, rcx
0x1400583e1  jnz     short loc_1400583EA
0x1400583e3  mov     eax, 8000FFFFh
0x1400583e8  jmp     short loc_140058446
0x1400583ea  mov     r8, rbp; Size
0x1400583ed  mov     rdx, r14; Src
0x1400583f0  call    memcpy_0
0x1400583f5  mov     rcx, rbx; psa
0x1400583f8  call    cs:__imp_SafeArrayUnaccessData
0x1400583ff  nop     dword ptr [rax+rax+00h]
0x140058404  mov     edi, eax
0x140058406  test    eax, eax
0x140058408  js      short loc_14005841E
0x14005840a  mov     [rsp+38h+ppvData], 0
0x140058413  mov     [rsi+8], rbx
0x140058417  mov     word ptr [rsi], 2011h
0x14005841c  jmp     short loc_140058444
0x14005841e  cmp     [rsp+38h+ppvData], 0
0x140058424  jz      short loc_140058435
0x140058426  mov     rcx, rbx; psa
0x140058429  call    cs:__imp_SafeArrayUnaccessData
0x140058430  nop     dword ptr [rax+rax+00h]
0x140058435  mov     rcx, rbx; psa
0x140058438  call    cs:__imp_SafeArrayDestroy
0x14005843f  nop     dword ptr [rax+rax+00h]
0x140058444  mov     eax, edi
0x140058446  mov     rbx, [rsp+38h+arg_0]
0x14005844b  mov     rbp, [rsp+38h+arg_8]
0x140058450  add     rsp, 20h
0x140058454  pop     r14
0x140058456  pop     rdi
0x140058457  pop     rsi
0x140058458  retn
```
