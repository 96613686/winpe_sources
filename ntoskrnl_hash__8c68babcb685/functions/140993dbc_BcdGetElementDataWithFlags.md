# BcdGetElementDataWithFlags

- ea: `0x140993dbc`
- end: `0x14099407e`
- name: `BcdGetElementDataWithFlags`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x140993d9c`

## callees

- `0x140549550`
- `0x1406dc8c0`
- `0x140991068`
- `0x140992b54`
- `0x140992e34`
- `0x140992e5c`
- `0x140993038`
- `0x140993780`
- `0x140993dbc`
- `0x140994d3c`
- `0x140994f7c`
- `0x140995510`
- `0x140afd2b4`
- `0x140bb19f0`

## string_xrefs

- `0x140994061`: `BcdGetElementDataWithFlags: Failed to get registry value.Object: %ws Reg type: %lu Status: %x`
- `0x14099403e`: `BcdGetElementDataWithFlags: Failed to open key.Object: %ws Type: %ws Status: %x`
- `0x140994006`: `BcdGetElementDataWithFlags: Failed to open elements key.Object: %ws Status: %x`

## pseudocode

```c
__int64 __fastcall BcdGetElementDataWithFlags(__int64 a1, unsigned int a2, __int64 a3, GUID *a4, unsigned int *a5)
{
  unsigned int *v6; // rcx
  int v8; // eax
  const wchar_t *v9; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int RegistryValue; // eax
  PVOID v15; // r15
  unsigned int v17; // r8d
  __int64 v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  ULONG v20; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-A8h]
  unsigned int v24; // [rsp+5Ch] [rbp-A4h]
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v27; // [rsp+70h] [rbp-90h]
  unsigned int *v28; // [rsp+78h] [rbp-88h]
  GUID *v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+88h] [rbp-78h] BYREF
  wchar_t DstBuf[28]; // [rsp+98h] [rbp-68h] BYREF
  char v32; // [rsp+D0h] [rbp-30h] BYREF

  v29 = a4;
  v6 = a5;
  v24 = a2;
  v28 = a5;
  v26 = 5111808;
  v27 = (const wchar_t *)&v32;
  v20 = 0;
  v30 = 0;
  if ( !a5 || !a4 && *a5 )
    return 3221225485LL;
  LOBYTE(v6) = a1 & 1;
  v8 = BiAcquireBcdSyncMutant(v6);
  if ( v8 < 0 )
  {
    BiLogMessage(4, L"BcdGetElementDataWithFlags: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v8);
    return v17;
  }
  else
  {
    v22 = 0;
    Handle = 0;
    P = 0;
    if ( (int)BiGetObjectIdentifier(a1, &v30) >= 0 )
    {
      BiStringFromGUID(&v30, &v26);
      v9 = v27;
    }
    else
    {
      v9 = L"N/A";
    }
    v10 = BiOpenKey(a1, L"Elements", 131097, &v22);
    v11 = v10;
    if ( v10 < 0 )
    {
      BiLogMessage(
        4,
        L"BcdGetElementDataWithFlags: Failed to open elements key.Object: %ws Status: %x",
        v9,
        (unsigned int)v10);
    }
    else if ( ultow_s(a2, DstBuf, 0x16u, 16) )
    {
      v11 = -1073741823;
    }
    else
    {
      v13 = BiOpenKey(v22, DstBuf, 131097, &Handle);
      if ( v13 < 0 )
      {
        v18 = 2;
        if ( v13 != -1073741772 )
          v18 = 4;
        BiLogMessage(
          v18,
          L"BcdGetElementDataWithFlags: Failed to open key.Object: %ws Type: %ws Status: %x",
          v9,
          DstBuf,
          v13);
        v11 = -1073741275;
      }
      else
      {
        v23 = BiConvertElementFormatToValueType(HIBYTE(a2) & 0xF);
        RegistryValue = BiGetRegistryValue((unsigned __int64)Handle, L"Element", 0, v23, &P, &v20);
        v15 = P;
        v11 = RegistryValue;
        if ( RegistryValue < 0 )
        {
          LODWORD(v19) = RegistryValue;
          BiLogMessage(
            4,
            L"BcdGetElementDataWithFlags: Failed to get registry value.Object: %ws Reg type: %lu Status: %x",
            v9,
            v23,
            v19);
        }
        else
        {
          v11 = BiConvertRegistryDataToElement(a1, (unsigned int *)P, v20, v24, 0, v29, v28);
        }
        if ( v15 )
          ExFreePoolWithTag(v15, 0x4B444342u);
      }
      if ( Handle )
        BiCloseKey(Handle);
    }
    if ( v22 )
      BiCloseKey(v22);
    LOBYTE(v12) = a1 & 1;
    BiReleaseBcdSyncMutant(v12);
    return v11;
  }
}

```

## disassembly

```asm
0x140993dbc  mov     [rsp-8+arg_10], rbx
0x140993dc1  push    rbp
0x140993dc2  push    rsi
0x140993dc3  push    rdi
0x140993dc4  push    r14
0x140993dc6  push    r15
0x140993dc8  lea     rbp, [rsp-30h]
0x140993dcd  sub     rsp, 130h
0x140993dd4  mov     rax, cs:__security_cookie
0x140993ddb  xor     rax, rsp
0x140993dde  mov     [rbp+50h+var_30], rax
0x140993de2  mov     r14, rcx
0x140993de5  mov     [rbp+50h+var_D0], r9
0x140993de9  mov     rcx, [rbp+50h+arg_20]
0x140993df0  lea     rax, [rbp+50h+var_80]
0x140993df4  mov     [rsp+150h+var_F4], edx
0x140993df8  xorps   xmm0, xmm0
0x140993dfb  mov     [rsp+150h+var_D8], rcx
0x140993e00  mov     r15d, edx
0x140993e03  mov     [rsp+150h+var_E8], 4E0000h
0x140993e0c  mov     [rsp+150h+var_E0], rax
0x140993e11  mov     [rsp+150h+var_110], 0
0x140993e19  movups  [rbp+50h+var_C8], xmm0
0x140993e1d  test    rcx, rcx
0x140993e20  jz      loc_140993FC4
0x140993e26  test    r9, r9
0x140993e29  jz      loc_140993FE3
0x140993e2f  mov     sil, r14b
0x140993e32  and     sil, 1
0x140993e36  mov     cl, sil
0x140993e39  call    BiAcquireBcdSyncMutant
0x140993e3e  mov     r8d, eax
0x140993e41  test    eax, eax
0x140993e43  js      loc_140993FED
0x140993e49  lea     rdx, [rbp+50h+var_C8]
0x140993e4d  mov     [rsp+150h+var_100], 0
0x140993e56  mov     rcx, r14
0x140993e59  mov     [rsp+150h+Handle], 0
0x140993e62  mov     [rsp+150h+P], 0
0x140993e6b  call    BiGetObjectIdentifier
0x140993e70  test    eax, eax
0x140993e72  jns     loc_140993FCB
0x140993e78  lea     rdi, aNA_0; "N/A"
0x140993e7f  lea     r9, [rsp+150h+var_100]
0x140993e84  mov     r8d, 20019h
0x140993e8a  lea     rdx, aElements; "Elements"
0x140993e91  mov     rcx, r14
0x140993e94  call    BiOpenKey
0x140993e99  mov     ebx, eax
0x140993e9b  test    eax, eax
0x140993e9d  js      loc_140994003
0x140993ea3  mov     r9d, 10h; Radix
0x140993ea9  lea     rdx, [rbp+50h+DstBuf]; DstBuf
0x140993ead  mov     ecx, r15d; Val
0x140993eb0  lea     r8d, [r9+6]; SizeInWords
0x140993eb4  call    _ultow_s
0x140993eb9  test    eax, eax
0x140993ebb  jnz     loc_14099401F
0x140993ec1  mov     rcx, [rsp+150h+var_100]
0x140993ec6  lea     r9, [rsp+150h+Handle]
0x140993ecb  mov     r8d, 20019h
0x140993ed1  lea     rdx, [rbp+50h+DstBuf]
0x140993ed5  call    BiOpenKey
0x140993eda  test    eax, eax
0x140993edc  js      loc_140994029
0x140993ee2  mov     ecx, r15d
0x140993ee5  shr     ecx, 18h
0x140993ee8  and     ecx, 0Fh
0x140993eeb  call    BiConvertElementFormatToValueType
0x140993ef0  lea     rcx, [rsp+150h+var_110]
0x140993ef5  mov     [rsp+150h+var_F8], eax
0x140993ef9  mov     [rsp+150h+var_128], rcx
0x140993efe  lea     rdx, aElement; "Element"
0x140993f05  lea     rcx, [rsp+150h+P]
0x140993f0a  mov     r9d, eax
0x140993f0d  mov     [rsp+150h+var_130], rcx
0x140993f12  xor     r8d, r8d
0x140993f15  mov     rcx, [rsp+150h+Handle]
0x140993f1a  call    BiGetRegistryValue
0x140993f1f  mov     r15, [rsp+150h+P]
0x140993f24  mov     ebx, eax
0x140993f26  test    eax, eax
0x140993f28  js      loc_14099405C
0x140993f2e  mov     rax, [rsp+150h+var_D8]
0x140993f33  mov     rdx, r15
0x140993f36  mov     r9d, [rsp+150h+var_F4]
0x140993f3b  mov     rcx, r14
0x140993f3e  mov     r8d, [rsp+150h+var_110]
0x140993f43  mov     [rsp+150h+var_120], rax
0x140993f48  mov     rax, [rbp+50h+var_D0]
0x140993f4c  mov     [rsp+150h+var_128], rax
0x140993f51  mov     dword ptr [rsp+150h+var_130], 0
0x140993f59  call    BiConvertRegistryDataToElement
0x140993f5e  mov     ebx, eax
0x140993f60  test    r15, r15
0x140993f63  jz      short loc_140993F72
0x140993f65  mov     edx, 4B444342h; Tag
0x140993f6a  mov     rcx, r15; P
0x140993f6d  call    ExFreePoolWithTag
0x140993f72  cmp     [rsp+150h+Handle], 0
0x140993f78  jz      short loc_140993F84
0x140993f7a  mov     rcx, [rsp+150h+Handle]; Handle
0x140993f7f  call    BiCloseKey
0x140993f84  cmp     [rsp+150h+var_100], 0
0x140993f8a  jz      short loc_140993F96
0x140993f8c  mov     rcx, [rsp+150h+var_100]; Handle
0x140993f91  call    BiCloseKey
0x140993f96  mov     cl, sil
0x140993f99  call    BiReleaseBcdSyncMutant
0x140993f9e  mov     eax, ebx
0x140993fa0  mov     rcx, [rbp+50h+var_30]
0x140993fa4  xor     rcx, rsp; StackCookie
0x140993fa7  call    __security_check_cookie
0x140993fac  mov     rbx, [rsp+150h+arg_10]
0x140993fb4  add     rsp, 130h
0x140993fbb  pop     r15
0x140993fbd  pop     r14
0x140993fbf  pop     rdi
0x140993fc0  pop     rsi
0x140993fc1  pop     rbp
0x140993fc2  retn
0x140993fc4  mov     eax, 0C000000Dh
0x140993fc9  jmp     short loc_140993FA0
0x140993fcb  lea     rdx, [rsp+150h+var_E8]
0x140993fd0  lea     rcx, [rbp+50h+var_C8]
0x140993fd4  call    BiStringFromGUID
0x140993fd9  mov     rdi, [rsp+150h+var_E0]
0x140993fde  jmp     loc_140993E7F
0x140993fe3  cmp     dword ptr [rcx], 0
0x140993fe6  jnz     short loc_140993FC4
0x140993fe8  jmp     loc_140993E2F
0x140993fed  lea     rdx, aBcdgetelementd_0; "BcdGetElementDataWithFlags: Failed to a"...
0x140993ff4  mov     ecx, 4
0x140993ff9  call    BiLogMessage
0x140993ffe  mov     eax, r8d
0x140994001  jmp     short loc_140993FA0
0x140994003  mov     r9d, eax
0x140994006  lea     rdx, aBcdgetelementd_1; "BcdGetElementDataWithFlags: Failed to o"...
0x14099400d  mov     r8, rdi
0x140994010  mov     ecx, 4
0x140994015  call    BiLogMessage
0x14099401a  jmp     loc_140993F84
0x14099401f  mov     ebx, 0C0000001h
0x140994024  jmp     loc_140993F84
0x140994029  mov     ecx, 2
0x14099402e  mov     dword ptr [rsp+150h+var_130], eax
0x140994032  cmp     eax, 0C0000034h
0x140994037  lea     r9, [rbp+50h+DstBuf]
0x14099403b  mov     r8, rdi
0x14099403e  lea     rdx, aBcdgetelementd; "BcdGetElementDataWithFlags: Failed to o"...
0x140994045  lea     r10d, [rcx+2]
0x140994049  cmovnz  ecx, r10d
0x14099404d  call    BiLogMessage
0x140994052  mov     ebx, 0C0000225h
0x140994057  jmp     loc_140993F72
0x14099405c  mov     r9d, [rsp+150h+var_F8]
0x140994061  lea     rdx, aBcdgetelementd_2; "BcdGetElementDataWithFlags: Failed to g"...
0x140994068  mov     r8, rdi
0x14099406b  mov     dword ptr [rsp+150h+var_130], eax
0x14099406f  mov     ecx, 4
0x140994074  call    BiLogMessage
0x140994079  jmp     loc_140993F60
```
