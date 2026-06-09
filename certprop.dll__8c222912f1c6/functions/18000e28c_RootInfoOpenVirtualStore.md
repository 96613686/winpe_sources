# RootInfoOpenVirtualStore

- ea: `0x18000e28c`
- end: `0x18000e2f5`
- name: `RootInfoOpenVirtualStore`
- size: `105`
- prototype: `DWORD __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014a30`

## callees

- `0x18000e28c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2e5`
- `CRYPT32!CertOpenStore` at `0x18000e2d7`
- `CRYPT32!CertOpenStore` at `0x18000e2d7`

## pseudocode

```c
DWORD __fastcall RootInfoOpenVirtualStore(int a1, _QWORD *a2)
{
  const wchar_t *pvPara; // rax
  DWORD v4; // r9d
  HCERTSTORE v5; // rax
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  pvPara = L"SmartCardRootCtrl";
  v7 = 0;
  if ( a1 == 1 )
  {
    v4 = 1073876992;
  }
  else
  {
    *((_QWORD *)&v7 + 1) = L"SmartCardRootCtrl";
    v4 = -1073672192;
    pvPara = (const wchar_t *)&v7;
    *(_QWORD *)&v7 = -2147483647;
  }
  v5 = CertOpenStore((LPCSTR)0xD, 0, 0, v4, pvPara);
  *a2 = v5;
  if ( v5 )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18000e28c  push    rbx
0x18000e28e  sub     rsp, 40h
0x18000e292  mov     rbx, rdx
0x18000e295  lea     rax, aSmartcardrootc_0; "SmartCardRootCtrl"
0x18000e29c  xor     edx, edx; dwEncodingType
0x18000e29e  xor     r8d, r8d; hCryptProv
0x18000e2a1  xorps   xmm0, xmm0
0x18000e2a4  cmp     ecx, 1
0x18000e2a7  movups  [rsp+48h+var_18], xmm0
0x18000e2ac  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18000e2af  jnz     short loc_18000E2B9
0x18000e2b1  mov     r9d, 40021000h
0x18000e2b7  jmp     short loc_18000E2D2
0x18000e2b9  mov     qword ptr [rsp+48h+var_18+8], rax
0x18000e2be  mov     r9d, 0C0011000h; dwFlags
0x18000e2c4  lea     rax, [rsp+48h+var_18]
0x18000e2c9  mov     qword ptr [rsp+48h+var_18], 0FFFFFFFF80000001h
0x18000e2d2  mov     [rsp+48h+pvPara], rax; pvPara
0x18000e2d7  call    cs:__imp_CertOpenStore
0x18000e2dd  mov     [rbx], rax
0x18000e2e0  test    rax, rax
0x18000e2e3  jnz     short loc_18000E2ED
0x18000e2e5  call    cs:__imp_GetLastError
0x18000e2eb  jmp     short loc_18000E2EF
0x18000e2ed  xor     eax, eax
0x18000e2ef  add     rsp, 40h
0x18000e2f3  pop     rbx
0x18000e2f4  retn
```
