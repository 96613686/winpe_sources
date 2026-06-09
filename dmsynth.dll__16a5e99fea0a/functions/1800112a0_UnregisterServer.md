# UnregisterServer

- ea: `0x1800112a0`
- end: `0x180011402`
- name: `UnregisterServer`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ee50`

## callees

- `0x1800014f0`
- `0x180010cc0`
- `0x1800112a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800112f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800112f1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800112d3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800112d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112fc`

## string_xrefs

- `0x180011308`: `CLSID\`

## pseudocode

```c
HRESULT __fastcall UnregisterServer(const IID *a1, __int64 a2, __int64 a3, __int64 a4)
{
  HRESULT result; // eax
  __int64 v7; // r9
  const char *v8; // r10
  _BYTE *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r8
  _BYTE *v12; // rax
  __int64 v13; // rdx
  _BYTE *v14; // rax
  _BYTE *v15; // r8
  __int64 v16; // rcx
  _BYTE *v17; // rax
  _BYTE *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r8
  LPOLESTR lpsz; // [rsp+20h] [rbp-148h] BYREF
  _BYTE v22[40]; // [rsp+28h] [rbp-140h] BYREF
  _BYTE v23[256]; // [rsp+50h] [rbp-118h] BYREF

  lpsz = 0;
  result = StringFromCLSID(a1, &lpsz);
  if ( result >= 0 )
  {
    _o_wcstombs(v22, lpsz, 39);
    CoTaskMemFree(lpsz);
    v7 = 2147483646;
    v8 = "CLSID\\";
    v9 = v23;
    v10 = 2147483646;
    v11 = 256;
    do
    {
      if ( !v10 )
        break;
      if ( !*v8 )
        break;
      *v9++ = *v8++;
      --v10;
      --v11;
    }
    while ( v11 );
    v12 = v9 - 1;
    if ( v11 )
      v12 = v9;
    v13 = 256;
    *v12 = 0;
    v14 = v23;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    if ( v13 )
    {
      v16 = v13;
      v17 = v22;
      v15 = &v23[256 - v13];
      do
      {
        if ( !v7 )
          break;
        if ( !*v17 )
          break;
        *v15++ = *v17++;
        --v7;
        --v16;
      }
      while ( v16 );
      v18 = v15 - 1;
      if ( v16 )
        v18 = v15;
      *v18 = 0;
    }
    else
    {
      v15 = 0;
    }
    RegRemoveSubtree(0xFFFFFFFF80000000uLL, v23, v15);
    RegRemoveSubtree(0xFFFFFFFF80000000uLL, a3, v19);
    RegRemoveSubtree(0xFFFFFFFF80000000uLL, a4, v20);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800112a0  mov     [rsp+arg_8], rbx
0x1800112a5  push    rdi
0x1800112a6  sub     rsp, 160h
0x1800112ad  mov     rax, cs:__security_cookie
0x1800112b4  xor     rax, rsp
0x1800112b7  mov     [rsp+168h+var_18], rax
0x1800112bf  lea     rdx, [rsp+168h+lpsz]; lplpsz
0x1800112c4  mov     [rsp+168h+lpsz], 0
0x1800112cd  mov     rdi, r9
0x1800112d0  mov     rbx, r8
0x1800112d3  call    cs:__imp_StringFromCLSID
0x1800112d9  test    eax, eax
0x1800112db  js      loc_1800113E1
0x1800112e1  mov     rdx, [rsp+168h+lpsz]
0x1800112e6  lea     rcx, [rsp+168h+var_140]
0x1800112eb  mov     r8d, 27h ; '''
0x1800112f1  call    cs:__imp__o_wcstombs
0x1800112f7  mov     rcx, [rsp+168h+lpsz]; pv
0x1800112fc  call    cs:__imp_CoTaskMemFree
0x180011302  mov     r9d, 7FFFFFFEh
0x180011308  lea     r10, aClsid; "CLSID\\"
0x18001130f  mov     ecx, 100h
0x180011314  lea     rdx, [rsp+168h+var_118]
0x180011319  mov     eax, r9d
0x18001131c  mov     r8d, ecx
0x18001131f  nop
0x180011320  test    rax, rax
0x180011323  jz      short loc_180011340
0x180011325  movzx   r11d, byte ptr [r10]
0x180011329  test    r11b, r11b
0x18001132c  jz      short loc_180011340
0x18001132e  mov     [rdx], r11b
0x180011331  inc     r10
0x180011334  inc     rdx
0x180011337  dec     rax
0x18001133a  sub     r8, 1
0x18001133e  jnz     short loc_180011320
0x180011340  lea     rax, [rdx-1]
0x180011344  test    r8, r8
0x180011347  cmovnz  rax, rdx
0x18001134b  mov     rdx, rcx
0x18001134e  mov     byte ptr [rax], 0
0x180011351  lea     rax, [rsp+168h+var_118]
0x180011356  cmp     byte ptr [rax], 0
0x180011359  jz      short loc_180011364
0x18001135b  inc     rax
0x18001135e  sub     rdx, 1
0x180011362  jnz     short loc_180011356
0x180011364  xor     eax, eax
0x180011366  mov     r8, rcx
0x180011369  sub     r8, rdx
0x18001136c  test    rdx, rdx
0x18001136f  cmovz   r8, rax
0x180011373  jz      short loc_1800113B0
0x180011375  sub     rcx, r8
0x180011378  lea     rax, [rsp+168h+var_140]
0x18001137d  lea     r8, [rsp+r8+168h+var_118]
0x180011382  jz      short loc_1800113A2
0x180011384  test    r9, r9
0x180011387  jz      short loc_1800113A2
0x180011389  movzx   edx, byte ptr [rax]
0x18001138c  test    dl, dl
0x18001138e  jz      short loc_1800113A2
0x180011390  mov     [r8], dl
0x180011393  inc     rax
0x180011396  inc     r8
0x180011399  dec     r9
0x18001139c  sub     rcx, 1
0x1800113a0  jnz     short loc_180011384
0x1800113a2  test    rcx, rcx
0x1800113a5  lea     rax, [r8-1]
0x1800113a9  cmovnz  rax, r8
0x1800113ad  mov     byte ptr [rax], 0
0x1800113b0  lea     rdx, [rsp+168h+var_118]
0x1800113b5  mov     rcx, 0FFFFFFFF80000000h
0x1800113bc  call    RegRemoveSubtree
0x1800113c1  mov     rdx, rbx
0x1800113c4  mov     rcx, 0FFFFFFFF80000000h
0x1800113cb  call    RegRemoveSubtree
0x1800113d0  mov     rdx, rdi
0x1800113d3  mov     rcx, 0FFFFFFFF80000000h
0x1800113da  call    RegRemoveSubtree
0x1800113df  xor     eax, eax
0x1800113e1  mov     rcx, [rsp+168h+var_18]
0x1800113e9  xor     rcx, rsp; StackCookie
0x1800113ec  call    __security_check_cookie
0x1800113f1  mov     rbx, [rsp+168h+arg_8]
0x1800113f9  add     rsp, 160h
0x180011400  pop     rdi
0x180011401  retn
```
