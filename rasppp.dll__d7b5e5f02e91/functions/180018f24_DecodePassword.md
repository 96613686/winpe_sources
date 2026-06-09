# DecodePassword

- ea: `0x180018f24`
- end: `0x180018fc6`
- name: `DecodePassword`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e0c`
- `0x180015430`
- `0x180017510`
- `0x180017fa0`
- `0x18002a9b0`

## callees

- `0x180018f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f8e`
- `CRYPT32!CryptUnprotectData` at `0x180018f7e`
- `CRYPT32!CryptUnprotectData` at `0x180018f7e`

## pseudocode

```c
__int64 __fastcall DecodePassword(DATA_BLOB *a1, DWORD *a2, BYTE **a3)
{
  unsigned int v5; // ebx
  DATA_BLOB v7; // [rsp+40h] [rbp-18h] BYREF

  if ( a1 && a2 && a3 )
  {
    v5 = 0;
    *a2 = 0;
    *a3 = 0;
    if ( a1->pbData && a1->cbData )
    {
      v7 = 0;
      if ( CryptUnprotectData(a1, 0, 0, 0, 0, 5u, &v7) )
      {
        *a2 = v7.cbData;
        *a3 = v7.pbData;
      }
      else
      {
        return GetLastError();
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180018f24  mov     r11, rsp
0x180018f27  mov     [r11+8], rbx
0x180018f2b  mov     [r11+10h], rsi
0x180018f2f  push    rdi
0x180018f30  sub     rsp, 50h
0x180018f34  mov     rdi, r8
0x180018f37  mov     rsi, rdx
0x180018f3a  test    rcx, rcx
0x180018f3d  jz      short loc_180018FAE
0x180018f3f  test    rdx, rdx
0x180018f42  jz      short loc_180018FAE
0x180018f44  test    r8, r8
0x180018f47  jz      short loc_180018FAE
0x180018f49  xor     ebx, ebx
0x180018f4b  mov     [rdx], ebx
0x180018f4d  mov     [r8], rbx
0x180018f50  cmp     [rcx+8], rbx
0x180018f54  jz      short loc_180018FB3
0x180018f56  cmp     [rcx], ebx
0x180018f58  jz      short loc_180018FB3
0x180018f5a  lea     rax, [r11-18h]
0x180018f5e  xorps   xmm0, xmm0
0x180018f61  mov     [r11-28h], rax
0x180018f65  xor     r9d, r9d; pvReserved
0x180018f68  mov     [rsp+58h+dwFlags], 5; dwFlags
0x180018f70  xor     r8d, r8d; pOptionalEntropy
0x180018f73  xor     edx, edx; ppszDataDescr
0x180018f75  mov     [r11-38h], rbx
0x180018f79  movups  xmmword ptr [rsp+58h+var_18.cbData], xmm0
0x180018f7e  call    cs:__imp_CryptUnprotectData
0x180018f85  nop     dword ptr [rax+rax+00h]
0x180018f8a  test    eax, eax
0x180018f8c  jnz     short loc_180018F9E
0x180018f8e  call    cs:__imp_GetLastError
0x180018f95  nop     dword ptr [rax+rax+00h]
0x180018f9a  mov     ebx, eax
0x180018f9c  jmp     short loc_180018FB3
0x180018f9e  mov     eax, [rsp+58h+var_18.cbData]
0x180018fa2  mov     [rsi], eax
0x180018fa4  mov     rax, [rsp+58h+var_18.pbData]
0x180018fa9  mov     [rdi], rax
0x180018fac  jmp     short loc_180018FB3
0x180018fae  mov     ebx, 80070057h
0x180018fb3  mov     rsi, [rsp+58h+arg_8]
0x180018fb8  mov     eax, ebx
0x180018fba  mov     rbx, [rsp+58h+arg_0]
0x180018fbf  add     rsp, 50h
0x180018fc3  pop     rdi
0x180018fc4  retn
```
