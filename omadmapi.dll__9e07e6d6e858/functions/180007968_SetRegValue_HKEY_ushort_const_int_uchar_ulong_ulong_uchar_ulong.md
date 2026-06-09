# SetRegValue(HKEY__ *,ushort const *,int,uchar *,ulong,ulong,uchar *,ulong)

- ea: `0x180007968`
- end: `0x180007b32`
- name: `?SetRegValue@@YAJPEAUHKEY__@@PEBGHPEAEKK2K@Z`
- size: `458`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, int@<r8d>, unsigned __int8 *@<r9>, unsigned int, DWORD dwType, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008600`

## callees

- `0x180007968`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007abf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007abf`
- `CRYPT32!CryptProtectData` at `0x180007a6e`
- `CRYPT32!CryptProtectData` at `0x180007a6e`

## pseudocode

```c
__int64 __fastcall SetRegValue(
        HKEY hKey,
        LPCWSTR lpValueName,
        int a3,
        unsigned __int8 *a4,
        DWORD a5,
        DWORD dwType,
        unsigned __int8 *lpData,
        unsigned int a8)
{
  DWORD v8; // r10d
  BYTE *pbData; // rdx
  signed int v13; // ebx
  unsigned int cbData; // ecx
  unsigned __int8 *v15; // rax
  __int64 v16; // r8
  signed int LastError; // eax
  LSTATUS v18; // eax
  BYTE *v19; // rcx
  __int64 v20; // rax
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-38h] BYREF
  DATA_BLOB pOptionalEntropy; // [rsp+50h] [rbp-28h] BYREF
  DATA_BLOB pDataIn; // [rsp+60h] [rbp-18h] BYREF

  v8 = dwType;
  pDataIn = 0;
  pDataOut = 0;
  pOptionalEntropy = 0;
  if ( dwType != 1 && dwType - 3 > 1 )
    goto LABEL_25;
  pbData = lpData;
  v13 = 0;
  if ( !lpData )
  {
    cbData = 0;
    pbData = 0;
    if ( a8 - 1 > 0xFFFFFFFD )
    {
LABEL_21:
      v18 = RegSetValueExW(hKey, lpValueName, 0, v8, pbData, cbData);
      if ( v18 )
      {
        if ( v18 > 0 )
          v13 = (unsigned __int16)v18 | 0x80070000;
        else
          v13 = v18;
      }
      goto LABEL_27;
    }
LABEL_25:
    v13 = -2147024809;
    goto LABEL_27;
  }
  if ( a8 == -1 )
  {
    if ( dwType == 1 )
    {
      v15 = lpData;
      v16 = 2147483646;
      do
      {
        if ( !*(_WORD *)v15 )
          break;
        v15 += 2;
        --v16;
      }
      while ( v16 );
      v13 = v16 == 0 ? 0x80070057 : 0;
      if ( !v16 )
        goto LABEL_27;
      cbData = v16 != 0 ? 2 * (2147483646 - v16) + 2 : 2;
    }
    else
    {
      if ( dwType != 4 )
      {
        v13 = -2147418113;
        goto LABEL_27;
      }
      cbData = 4;
    }
  }
  else
  {
    cbData = a8;
  }
  if ( !a3 )
    goto LABEL_21;
  pOptionalEntropy.cbData = a5;
  pDataIn.pbData = lpData;
  pDataIn.cbData = cbData;
  pOptionalEntropy.pbData = a4;
  if ( CryptProtectData(&pDataIn, 0, &pOptionalEntropy, 0, 0, 1u, &pDataOut) )
    goto LABEL_20;
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( v13 >= 0 )
  {
LABEL_20:
    pbData = pDataOut.pbData;
    v8 = 3;
    cbData = pDataOut.cbData;
    goto LABEL_21;
  }
LABEL_27:
  v19 = pDataOut.pbData;
  if ( pDataOut.pbData )
  {
    v20 = pDataOut.cbData;
    if ( pDataOut.cbData )
    {
      do
      {
        *v19++ = 0;
        --v20;
      }
      while ( v20 );
      v19 = pDataOut.pbData;
    }
    LocalFree(v19);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180007968  push    rbp
0x18000796a  push    rbx
0x18000796b  push    rsi
0x18000796c  push    rdi
0x18000796d  push    r14
0x18000796f  push    r15
0x180007971  mov     rbp, rsp
0x180007974  sub     rsp, 78h
0x180007978  mov     r10d, [rbp+dwType]
0x18000797c  xorps   xmm0, xmm0
0x18000797f  mov     eax, r10d
0x180007982  xor     r15d, r15d
0x180007985  xorps   xmm1, xmm1
0x180007988  mov     rdi, r9
0x18000798b  mov     r11d, r8d
0x18000798e  mov     rsi, rdx
0x180007991  mov     r14, rcx
0x180007994  movups  xmmword ptr [rbp+pDataIn.cbData], xmm0
0x180007998  movups  xmmword ptr [rbp+var_38.cbData], xmm1
0x18000799c  movups  xmmword ptr [rbp+pOptionalEntropy.cbData], xmm0
0x1800079a0  sub     eax, 1
0x1800079a3  jz      short loc_1800079B3
0x1800079a5  sub     eax, 2
0x1800079a8  jz      short loc_1800079B3
0x1800079aa  cmp     eax, 1
0x1800079ad  jnz     loc_180007AE5
0x1800079b3  mov     rdx, [rbp+lpData]
0x1800079b7  mov     ebx, r15d
0x1800079ba  test    rdx, rdx
0x1800079bd  jz      loc_180007AD5
0x1800079c3  cmp     [rbp+arg_38], 0FFFFFFFFh
0x1800079c7  jnz     short loc_180007A32
0x1800079c9  mov     eax, r10d
0x1800079cc  sub     eax, 1
0x1800079cf  jz      short loc_1800079E7
0x1800079d1  cmp     eax, 3
0x1800079d4  jz      short loc_1800079E0
0x1800079d6  mov     ebx, 8000FFFFh
0x1800079db  jmp     loc_180007AF5
0x1800079e0  mov     ecx, 4
0x1800079e5  jmp     short loc_180007A35
0x1800079e7  mov     r9d, 7FFFFFFEh
0x1800079ed  mov     rax, rdx
0x1800079f0  mov     r8d, r9d
0x1800079f3  cmp     [rax], r15w
0x1800079f7  jz      short loc_180007A03
0x1800079f9  add     rax, 2
0x1800079fd  sub     r8, 1
0x180007a01  jnz     short loc_1800079F3
0x180007a03  mov     rax, r8
0x180007a06  mov     ebx, 80070057h
0x180007a0b  neg     rax
0x180007a0e  sbb     ecx, ecx
0x180007a10  not     ecx
0x180007a12  and     ebx, ecx
0x180007a14  test    r8, r8
0x180007a17  jz      loc_180007AF5
0x180007a1d  sub     r9, r8
0x180007a20  add     r9, r9
0x180007a23  neg     r8
0x180007a26  sbb     rcx, rcx
0x180007a29  and     rcx, r9
0x180007a2c  add     rcx, 2
0x180007a30  jmp     short loc_180007A35
0x180007a32  mov     ecx, [rbp+arg_38]
0x180007a35  test    r11d, r11d
0x180007a38  jz      short loc_180007AAA
0x180007a3a  mov     eax, [rbp+arg_20]
0x180007a3d  lea     r8, [rbp+pOptionalEntropy]; pOptionalEntropy
0x180007a41  mov     [rbp+pOptionalEntropy.cbData], eax
0x180007a44  xor     r9d, r9d; pvReserved
0x180007a47  lea     rax, [rbp+var_38]
0x180007a4b  mov     [rbp+pDataIn.pbData], rdx
0x180007a4f  mov     [rsp+78h+pDataOut], rax; pDataOut
0x180007a54  xor     edx, edx; szDataDescr
0x180007a56  mov     [rbp+pDataIn.cbData], ecx
0x180007a59  lea     rcx, [rbp+pDataIn]; pDataIn
0x180007a5d  mov     [rsp+78h+dwFlags], 1; dwFlags
0x180007a65  mov     [rsp+78h+pPromptStruct], r15; pPromptStruct
0x180007a6a  mov     [rbp+pOptionalEntropy.pbData], rdi
0x180007a6e  call    cs:__imp_CryptProtectData
0x180007a75  nop     dword ptr [rax+rax+00h]
0x180007a7a  test    eax, eax
0x180007a7c  jnz     short loc_180007A9D
0x180007a7e  call    cs:__imp_GetLastError
0x180007a85  nop     dword ptr [rax+rax+00h]
0x180007a8a  mov     ebx, eax
0x180007a8c  test    eax, eax
0x180007a8e  jle     short loc_180007A99
0x180007a90  movzx   ebx, ax
0x180007a93  or      ebx, 80070000h
0x180007a99  test    ebx, ebx
0x180007a9b  js      short loc_180007AF5
0x180007a9d  mov     rdx, [rbp+var_38.pbData]
0x180007aa1  mov     r10d, 3
0x180007aa7  mov     ecx, [rbp+var_38.cbData]
0x180007aaa  mov     [rsp+78h+dwFlags], ecx; cbData
0x180007aae  mov     r9d, r10d; dwType
0x180007ab1  mov     [rsp+78h+pPromptStruct], rdx; lpData
0x180007ab6  xor     r8d, r8d; Reserved
0x180007ab9  mov     rdx, rsi; lpValueName
0x180007abc  mov     rcx, r14; hKey
0x180007abf  call    cs:__imp_RegSetValueExW
0x180007ac6  nop     dword ptr [rax+rax+00h]
0x180007acb  test    eax, eax
0x180007acd  jz      short loc_180007AF5
0x180007acf  jg      short loc_180007AEC
0x180007ad1  mov     ebx, eax
0x180007ad3  jmp     short loc_180007AF5
0x180007ad5  mov     eax, [rbp+arg_38]
0x180007ad8  mov     rcx, r15
0x180007adb  dec     eax
0x180007add  mov     rdx, r15
0x180007ae0  cmp     eax, 0FFFFFFFDh
0x180007ae3  ja      short loc_180007AAA
0x180007ae5  mov     ebx, 80070057h
0x180007aea  jmp     short loc_180007AF5
0x180007aec  movzx   ebx, ax
0x180007aef  or      ebx, 80070000h
0x180007af5  mov     rcx, [rbp+var_38.pbData]
0x180007af9  test    rcx, rcx
0x180007afc  jz      short loc_180007B22
0x180007afe  mov     eax, [rbp+var_38.cbData]
0x180007b01  test    rax, rax
0x180007b04  jz      short loc_180007B16
0x180007b06  mov     [rcx], r15b
0x180007b09  inc     rcx
0x180007b0c  sub     rax, 1
0x180007b10  jnz     short loc_180007B06
0x180007b12  mov     rcx, [rbp+var_38.pbData]; hMem
0x180007b16  call    cs:__imp_LocalFree
0x180007b1d  nop     dword ptr [rax+rax+00h]
0x180007b22  mov     eax, ebx
0x180007b24  add     rsp, 78h
0x180007b28  pop     r15
0x180007b2a  pop     r14
0x180007b2c  pop     rdi
0x180007b2d  pop     rsi
0x180007b2e  pop     rbx
0x180007b2f  pop     rbp
0x180007b30  retn
```
