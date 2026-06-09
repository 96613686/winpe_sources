# ceVerifyAltNameString(long,ushort *)

- ea: `0x18000662c`
- end: `0x180006758`
- name: `?ceVerifyAltNameString@@YAJJPEAG@Z`
- size: `300`
- prototype: `int(int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800032e0`
- `0x1800081f0`

## callees

- `0x180005ab8`
- `0x1800064e0`
- `0x18000662c`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x1800066c5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800066f0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800066c5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800066f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000673b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000673b`
- `CRYPT32!CryptEncodeObjectEx` at `0x180006722`
- `CRYPT32!CryptEncodeObjectEx` at `0x180006722`

## pseudocode

```c
__int64 __fastcall ceVerifyAltNameString(int a1, unsigned __int16 *a2, int a3)
{
  HLOCAL v3; // rdi
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  unsigned int v11; // ebx
  int v12; // eax
  _QWORD pvStructInfo[2]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v16; // [rsp+60h] [rbp-20h]
  __int128 v17; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v18; // [rsp+78h] [rbp-8h]
  DWORD pcbEncoded; // [rsp+90h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp+20h] BYREF

  pvStructInfo[0] = 1;
  v18 = 0;
  pcbEncoded = 0;
  v3 = 0;
  hMem = 0;
  pvStructInfo[1] = &v15;
  v15 = 0;
  LODWORD(v15) = a1;
  v16 = 0;
  v17 = 0;
  v5 = a1 - 1;
  if ( !v5 )
  {
    *((_QWORD *)&v15 + 1) = &v17;
    *(_QWORD *)&v17 = "1.3.6.1.4.1.311.20.2.3";
    DWORD2(v17) = SysStringByteLen(a2);
    v18 = a2;
LABEL_15:
    v11 = 0;
    if ( !CryptEncodeObjectEx(1u, (LPCSTR)0xC, pvStructInfo, 0x60000u, 0, 0, &pcbEncoded) )
      v11 = ceHLastError();
    goto LABEL_17;
  }
  v6 = v5 - 1;
  if ( !v6 )
    goto LABEL_13;
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_13;
  v8 = v7 - 2;
  if ( !v8 )
  {
LABEL_12:
    DWORD2(v15) = SysStringByteLen(a2);
    v16 = a2;
    goto LABEL_15;
  }
  v9 = v8 - 2;
  if ( !v9 )
  {
LABEL_13:
    *((_QWORD *)&v15 + 1) = a2;
    goto LABEL_15;
  }
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_12;
  if ( v10 != 1 )
    return (unsigned int)-2147024809;
  v12 = ceConvertWszToSz((char **)&hMem, a2, a3);
  v3 = hMem;
  if ( v12 )
  {
    *((_QWORD *)&v15 + 1) = hMem;
    goto LABEL_15;
  }
  v11 = -2147024882;
LABEL_17:
  if ( v3 )
    LocalFree(v3);
  return v11;
}

```

## disassembly

```asm
0x18000662c  mov     [rsp-8+arg_8], rbx
0x180006631  mov     [rsp-8+arg_18], rdi
0x180006636  push    rbp
0x180006637  mov     rbp, rsp
0x18000663a  sub     rsp, 80h
0x180006641  xor     eax, eax
0x180006643  mov     [rbp+pvStructInfo], 1
0x18000664b  mov     [rbp+var_8], rax
0x18000664f  xorps   xmm0, xmm0
0x180006652  mov     [rbp+arg_0], eax
0x180006655  xor     edi, edi
0x180006657  lea     rax, [rbp+var_30]
0x18000665b  mov     [rbp+hMem], rdi
0x18000665f  mov     [rbp+var_38], rax
0x180006663  mov     rbx, rdx
0x180006666  xor     eax, eax
0x180006668  movups  [rbp+var_30], xmm0
0x18000666c  mov     dword ptr [rbp+var_30], ecx
0x18000666f  mov     [rbp+var_20], rax
0x180006673  movups  [rbp+var_18], xmm0
0x180006677  sub     ecx, 1
0x18000667a  jz      short loc_1800066DA
0x18000667c  sub     ecx, 1
0x18000667f  jz      short loc_1800066D4
0x180006681  sub     ecx, 1
0x180006684  jz      short loc_1800066D4
0x180006686  sub     ecx, 2
0x180006689  jz      short loc_1800066C2
0x18000668b  sub     ecx, 2
0x18000668e  jz      short loc_1800066D4
0x180006690  sub     ecx, 1
0x180006693  jz      short loc_1800066C2
0x180006695  cmp     ecx, 1
0x180006698  jz      short loc_1800066A4
0x18000669a  mov     ebx, 80070057h
0x18000669f  jmp     loc_180006741
0x1800066a4  lea     rcx, [rbp+hMem]; char **
0x1800066a8  call    ?ceConvertWszToSz@@YAHPEAPEADPEBGJ@Z; ceConvertWszToSz(char * *,ushort const *,long)
0x1800066ad  mov     rdi, [rbp+hMem]
0x1800066b1  test    eax, eax
0x1800066b3  jnz     short loc_1800066BC
0x1800066b5  mov     ebx, 8007000Eh
0x1800066ba  jmp     short loc_180006733
0x1800066bc  mov     qword ptr [rbp+var_30+8], rdi
0x1800066c0  jmp     short loc_1800066FD
0x1800066c2  mov     rcx, rbx; bstr
0x1800066c5  call    cs:__imp_SysStringByteLen
0x1800066cb  mov     dword ptr [rbp+var_30+8], eax
0x1800066ce  mov     [rbp+var_20], rbx
0x1800066d2  jmp     short loc_1800066FD
0x1800066d4  mov     qword ptr [rbp+var_30+8], rbx
0x1800066d8  jmp     short loc_1800066FD
0x1800066da  lea     rax, [rbp+var_18]
0x1800066de  mov     rcx, rbx; bstr
0x1800066e1  mov     qword ptr [rbp+var_30+8], rax
0x1800066e5  lea     rax, a1361413112023; "1.3.6.1.4.1.311.20.2.3"
0x1800066ec  mov     qword ptr [rbp+var_18], rax
0x1800066f0  call    cs:__imp_SysStringByteLen
0x1800066f6  mov     dword ptr [rbp+var_18+8], eax
0x1800066f9  mov     [rbp+var_8], rbx
0x1800066fd  xor     ebx, ebx
0x1800066ff  lea     rax, [rbp+arg_0]
0x180006703  mov     [rsp+80h+pcbEncoded], rax; pcbEncoded
0x180006708  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x18000670c  mov     [rsp+80h+pvEncoded], rbx; pvEncoded
0x180006711  mov     r9d, 60000h; dwFlags
0x180006717  mov     [rsp+80h+pEncodePara], rbx; pEncodePara
0x18000671c  lea     edx, [rbx+0Ch]; lpszStructType
0x18000671f  lea     ecx, [rbx+1]; dwCertEncodingType
0x180006722  call    cs:__imp_CryptEncodeObjectEx
0x180006728  test    eax, eax
0x18000672a  jnz     short loc_180006733
0x18000672c  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x180006731  mov     ebx, eax
0x180006733  test    rdi, rdi
0x180006736  jz      short loc_180006741
0x180006738  mov     rcx, rdi; hMem
0x18000673b  call    cs:__imp_LocalFree
0x180006741  lea     r11, [rsp+80h+var_s0]
0x180006749  mov     eax, ebx
0x18000674b  mov     rbx, [r11+18h]
0x18000674f  mov     rdi, [r11+28h]
0x180006753  mov     rsp, r11
0x180006756  pop     rbp
0x180006757  retn
```
