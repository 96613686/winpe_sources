# BcdOpenObject

- ea: `0x14098ce10`
- end: `0x14098cf85`
- name: `BcdOpenObject`
- size: `373`
- prototype: ``
- caller_count: `18`
- callee_count: `11`
- tags: ``

## callers

- `0x14060b43c`
- `0x14068a49c`
- `0x14079c02c`
- `0x14079c15c`
- `0x14079ff44`
- `0x14082dc18`
- `0x14082ffcc`
- `0x1408305b4`
- `0x140987134`
- `0x140987da0`
- `0x140988764`
- `0x14098a38c`
- `0x14098a660`
- `0x14098c7e8`
- `0x140acc1c8`
- `0x140ae3b40`
- `0x140af0340`
- `0x140afc1a0`

## callees

- `0x1406d9d70`
- `0x14082dbb4`
- `0x14082dc18`
- `0x14098b264`
- `0x14098b544`
- `0x14098b748`
- `0x14098be90`
- `0x14098ce10`
- `0x14098d68c`
- `0x14098dc20`
- `0x140abadc0`

## string_xrefs

- `0x14098ce75`: `Opening object %s`
- `0x14098ce99`: `BcdOpenObject: Failed to acquire BCD sync mutant. Status: %x`
- `0x14098cef2`: `Failed to open key for all objects. Status: %x`
- `0x14098cf53`: `Failed to open object's key. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdOpenObject(__int64 a1, __int64 a2, _QWORD *a3)
{
  char *v5; // r14
  unsigned int v6; // edi
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // r8d
  int v11; // eax
  unsigned int v12; // ebx
  const wchar_t *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int CurrentBootEntryIdentifier; // eax
  int v17; // [rsp+20h] [rbp-79h] BYREF
  HANDLE Handle; // [rsp+28h] [rbp-71h] BYREF
  __int64 v19; // [rsp+30h] [rbp-69h] BYREF
  char *v20; // [rsp+38h] [rbp-61h]
  __int64 v21; // [rsp+40h] [rbp-59h]
  __int128 v22; // [rsp+48h] [rbp-51h] BYREF
  char v23; // [rsp+60h] [rbp-39h] BYREF

  v21 = a2;
  v19 = 5111808;
  v20 = &v23;
  v17 = 0;
  v22 = 0;
  BiStringFromGUID(a2, &v19);
  v5 = v20;
  v6 = 2;
  BiLogMessage(2, L"Opening object %s", v20);
  LOBYTE(v7) = a1 & 1;
  v8 = BiAcquireBcdSyncMutant(v7);
  if ( v8 < 0 )
  {
    BiLogMessage(4, L"BcdOpenObject: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v8);
    return v9;
  }
  *a3 = 0;
  Handle = 0;
  v11 = BiOpenKey(a1, L"Objects", 131097, &Handle);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = L"Failed to open key for all objects. Status: %x";
    v14 = 4;
    goto LABEL_5;
  }
  if ( (unsigned __int8)BiIsObjectAliased(v21, &v17) )
  {
    if ( v17 == 1 )
    {
      CurrentBootEntryIdentifier = BiGetCurrentBootEntryIdentifier(&v22);
    }
    else
    {
      if ( v17 != 2 )
      {
        v12 = -1073741811;
        goto LABEL_21;
      }
      CurrentBootEntryIdentifier = BiGetDefaultBootEntryIdentifier(a1, &v22);
    }
    v12 = CurrentBootEntryIdentifier;
    if ( CurrentBootEntryIdentifier >= 0 )
    {
      BiStringFromGUID(&v22, &v19);
      v5 = v20;
      BiLogMessage(2, L"Object alias resolves to %s", v20);
      goto LABEL_10;
    }
LABEL_21:
    BiLogMessage(4, L"Failed to get aliased identifier. Status: %x", v12);
    goto LABEL_6;
  }
LABEL_10:
  v11 = BiOpenKey(Handle, v5, 983103, a3);
  v12 = v11;
  if ( v11 >= 0 )
    goto LABEL_6;
  v13 = L"Failed to open object's key. Status: %x";
  if ( v11 != -1073741772 )
    v6 = 4;
  v14 = v6;
LABEL_5:
  BiLogMessage(v14, v13, (unsigned int)v11);
LABEL_6:
  if ( Handle )
    BiCloseKey(Handle);
  LOBYTE(v15) = a1 & 1;
  BiReleaseBcdSyncMutant(v15);
  return v12;
}

```

## disassembly

```asm
0x14098ce10  push    rbp
0x14098ce12  push    rbx
0x14098ce13  push    rdi
0x14098ce14  push    r12
0x14098ce16  push    r13
0x14098ce18  push    r14
0x14098ce1a  push    r15
0x14098ce1c  lea     rbp, [rsp-27h]
0x14098ce21  sub     rsp, 0C0h
0x14098ce28  mov     rax, cs:__security_cookie
0x14098ce2f  xor     rax, rsp
0x14098ce32  mov     [rbp+57h+var_40], rax
0x14098ce36  mov     r12, r8
0x14098ce39  mov     [rbp+57h+var_B0], rdx
0x14098ce3d  mov     r8, rdx
0x14098ce40  mov     [rbp+57h+var_C0], 4E0000h
0x14098ce48  mov     r15, rcx
0x14098ce4b  lea     rax, [rbp+57h+var_90]
0x14098ce4f  xorps   xmm0, xmm0
0x14098ce52  mov     [rbp+57h+var_B8], rax
0x14098ce56  xor     ebx, ebx
0x14098ce58  lea     rdx, [rbp+57h+var_C0]
0x14098ce5c  mov     rcx, r8
0x14098ce5f  mov     [rbp+57h+var_D0], ebx
0x14098ce62  movups  [rbp+57h+var_A8], xmm0
0x14098ce66  call    BiStringFromGUID
0x14098ce6b  mov     r14, [rbp+57h+var_B8]
0x14098ce6f  lea     edi, [rbx+2]
0x14098ce72  mov     r8, r14
0x14098ce75  lea     rdx, aOpeningObjectS; "Opening object %s"
0x14098ce7c  mov     ecx, edi
0x14098ce7e  call    BiLogMessage
0x14098ce83  mov     r13b, r15b
0x14098ce86  and     r13b, 1
0x14098ce8a  mov     cl, r13b
0x14098ce8d  call    BiAcquireBcdSyncMutant
0x14098ce92  mov     r8d, eax
0x14098ce95  test    eax, eax
0x14098ce97  jns     short loc_14098CECB
0x14098ce99  lea     rdx, aBcdopenobjectF; "BcdOpenObject: Failed to acquire BCD sy"...
0x14098cea0  lea     ecx, [rbx+4]
0x14098cea3  call    BiLogMessage
0x14098cea8  mov     eax, r8d
0x14098ceab  mov     rcx, [rbp+57h+var_40]
0x14098ceaf  xor     rcx, rsp; StackCookie
0x14098ceb2  call    __security_check_cookie
0x14098ceb7  add     rsp, 0C0h
0x14098cebe  pop     r15
0x14098cec0  pop     r14
0x14098cec2  pop     r13
0x14098cec4  pop     r12
0x14098cec6  pop     rdi
0x14098cec7  pop     rbx
0x14098cec8  pop     rbp
0x14098cec9  retn
0x14098cecb  lea     r9, [rbp+57h+Handle]
0x14098cecf  mov     [r12], rbx
0x14098ced3  mov     r8d, 20019h
0x14098ced9  mov     [rbp+57h+Handle], rbx
0x14098cedd  lea     rdx, aObjects; "Objects"
0x14098cee4  mov     rcx, r15
0x14098cee7  call    BiOpenKey
0x14098ceec  mov     ebx, eax
0x14098ceee  test    eax, eax
0x14098cef0  jns     short loc_14098CF22
0x14098cef2  lea     rdx, aFailedToOpenKe_1; "Failed to open key for all objects. Sta"...
0x14098cef9  mov     ecx, 4
0x14098cefe  mov     r8d, eax
0x14098cf01  call    BiLogMessage
0x14098cf06  cmp     [rbp+57h+Handle], 0
0x14098cf0b  jz      short loc_14098CF16
0x14098cf0d  mov     rcx, [rbp+57h+Handle]; Handle
0x14098cf11  call    BiCloseKey
0x14098cf16  mov     cl, r13b
0x14098cf19  call    BiReleaseBcdSyncMutant
0x14098cf1e  mov     eax, ebx
0x14098cf20  jmp     short loc_14098CEAB
0x14098cf22  mov     rcx, [rbp+57h+var_B0]
0x14098cf26  lea     rdx, [rbp+57h+var_D0]
0x14098cf2a  call    BiIsObjectAliased
0x14098cf2f  test    al, al
0x14098cf31  jnz     short loc_14098CF66
0x14098cf33  mov     rcx, [rbp+57h+Handle]
0x14098cf37  mov     r9, r12
0x14098cf3a  mov     r8d, 0F003Fh
0x14098cf40  mov     rdx, r14
0x14098cf43  call    BiOpenKey
0x14098cf48  mov     ebx, eax
0x14098cf4a  test    eax, eax
0x14098cf4c  jns     short loc_14098CF06
0x14098cf4e  mov     ecx, 4
0x14098cf53  lea     rdx, aFailedToOpenOb; "Failed to open object's key. Status: %x"
0x14098cf5a  cmp     eax, 0C0000034h
0x14098cf5f  cmovnz  edi, ecx
0x14098cf62  mov     ecx, edi
0x14098cf64  jmp     short loc_14098CEFE
0x14098cf66  mov     ecx, [rbp+57h+var_D0]
0x14098cf69  sub     ecx, 1
0x14098cf6c  jz      loc_140B61C20
0x14098cf72  cmp     ecx, 1
0x14098cf75  jz      loc_140B61C12
0x14098cf7b  mov     ebx, 0C000000Dh
0x14098cf80  jmp     loc_140B61C57
0x140b61c12  lea     rdx, [rbp+57h+var_A8]
0x140b61c16  mov     rcx, r15
0x140b61c19  call    BiGetDefaultBootEntryIdentifier
0x140b61c1e  jmp     short loc_140B61C29
0x140b61c20  lea     rcx, [rbp+57h+var_A8]
0x140b61c24  call    BiGetCurrentBootEntryIdentifier
0x140b61c29  mov     ebx, eax
0x140b61c2b  test    eax, eax
0x140b61c2d  js      short loc_140B61C57
0x140b61c2f  lea     rdx, [rbp+57h+var_C0]
0x140b61c33  lea     rcx, [rbp+57h+var_A8]
0x140b61c37  call    BiStringFromGUID
0x140b61c3c  mov     r14, [rbp+57h+var_B8]
0x140b61c40  lea     rdx, aObjectAliasRes; "Object alias resolves to %s"
0x140b61c47  mov     r8, r14
0x140b61c4a  mov     ecx, edi
0x140b61c4c  call    BiLogMessage
0x140b61c51  nop
0x140b61c52  jmp     loc_14098CF33
0x140b61c57  mov     r8d, ebx
0x140b61c5a  lea     rdx, aFailedToGetAli; "Failed to get aliased identifier. Statu"...
0x140b61c61  mov     ecx, 4
0x140b61c66  jmp     loc_14098CF01
```
