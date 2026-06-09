# BcdOpenObject

- ea: `0x140994700`
- end: `0x140994875`
- name: `BcdOpenObject`
- size: `373`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `11`
- tags: ``

## callers

- `0x14061102c`
- `0x14068fe6c`
- `0x1407a00dc`
- `0x1407a020c`
- `0x1407a3f94`
- `0x14082fb88`
- `0x140831f3c`
- `0x140832524`
- `0x14098ea24`
- `0x14098f690`
- `0x140990054`
- `0x140991c7c`
- `0x140991f50`
- `0x1409940d8`
- `0x140ad11d8`
- `0x140ae9810`
- `0x140af69f0`
- `0x140b02560`

## callees

- `0x1406dc8c0`
- `0x14082fb24`
- `0x14082fb88`
- `0x140992b54`
- `0x140992e34`
- `0x140993038`
- `0x140993780`
- `0x140994700`
- `0x140994f7c`
- `0x140995510`
- `0x140ac0070`

## string_xrefs

- `0x140994843`: `Failed to open object's key. Status: %x`
- `0x1409947e2`: `Failed to open key for all objects. Status: %x`
- `0x140994789`: `BcdOpenObject: Failed to acquire BCD sync mutant. Status: %x`
- `0x140994765`: `Opening object %s`

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
0x140994700  push    rbp
0x140994702  push    rbx
0x140994703  push    rdi
0x140994704  push    r12
0x140994706  push    r13
0x140994708  push    r14
0x14099470a  push    r15
0x14099470c  lea     rbp, [rsp-27h]
0x140994711  sub     rsp, 0C0h
0x140994718  mov     rax, cs:__security_cookie
0x14099471f  xor     rax, rsp
0x140994722  mov     [rbp+57h+var_40], rax
0x140994726  mov     r12, r8
0x140994729  mov     [rbp+57h+var_B0], rdx
0x14099472d  mov     r8, rdx
0x140994730  mov     [rbp+57h+var_C0], 4E0000h
0x140994738  mov     r15, rcx
0x14099473b  lea     rax, [rbp+57h+var_90]
0x14099473f  xorps   xmm0, xmm0
0x140994742  mov     [rbp+57h+var_B8], rax
0x140994746  xor     ebx, ebx
0x140994748  lea     rdx, [rbp+57h+var_C0]
0x14099474c  mov     rcx, r8
0x14099474f  mov     [rbp+57h+var_D0], ebx
0x140994752  movups  [rbp+57h+var_A8], xmm0
0x140994756  call    BiStringFromGUID
0x14099475b  mov     r14, [rbp+57h+var_B8]
0x14099475f  lea     edi, [rbx+2]
0x140994762  mov     r8, r14
0x140994765  lea     rdx, aOpeningObjectS; "Opening object %s"
0x14099476c  mov     ecx, edi
0x14099476e  call    BiLogMessage
0x140994773  mov     r13b, r15b
0x140994776  and     r13b, 1
0x14099477a  mov     cl, r13b
0x14099477d  call    BiAcquireBcdSyncMutant
0x140994782  mov     r8d, eax
0x140994785  test    eax, eax
0x140994787  jns     short loc_1409947BB
0x140994789  lea     rdx, aBcdopenobjectF; "BcdOpenObject: Failed to acquire BCD sy"...
0x140994790  lea     ecx, [rbx+4]
0x140994793  call    BiLogMessage
0x140994798  mov     eax, r8d
0x14099479b  mov     rcx, [rbp+57h+var_40]
0x14099479f  xor     rcx, rsp; StackCookie
0x1409947a2  call    __security_check_cookie
0x1409947a7  add     rsp, 0C0h
0x1409947ae  pop     r15
0x1409947b0  pop     r14
0x1409947b2  pop     r13
0x1409947b4  pop     r12
0x1409947b6  pop     rdi
0x1409947b7  pop     rbx
0x1409947b8  pop     rbp
0x1409947b9  retn
0x1409947bb  lea     r9, [rbp+57h+Handle]
0x1409947bf  mov     [r12], rbx
0x1409947c3  mov     r8d, 20019h
0x1409947c9  mov     [rbp+57h+Handle], rbx
0x1409947cd  lea     rdx, aObjects; "Objects"
0x1409947d4  mov     rcx, r15
0x1409947d7  call    BiOpenKey
0x1409947dc  mov     ebx, eax
0x1409947de  test    eax, eax
0x1409947e0  jns     short loc_140994812
0x1409947e2  lea     rdx, aFailedToOpenKe_1; "Failed to open key for all objects. Sta"...
0x1409947e9  mov     ecx, 4
0x1409947ee  mov     r8d, eax
0x1409947f1  call    BiLogMessage
0x1409947f6  cmp     [rbp+57h+Handle], 0
0x1409947fb  jz      short loc_140994806
0x1409947fd  mov     rcx, [rbp+57h+Handle]; Handle
0x140994801  call    BiCloseKey
0x140994806  mov     cl, r13b
0x140994809  call    BiReleaseBcdSyncMutant
0x14099480e  mov     eax, ebx
0x140994810  jmp     short loc_14099479B
0x140994812  mov     rcx, [rbp+57h+var_B0]
0x140994816  lea     rdx, [rbp+57h+var_D0]
0x14099481a  call    BiIsObjectAliased
0x14099481f  test    al, al
0x140994821  jnz     short loc_140994856
0x140994823  mov     rcx, [rbp+57h+Handle]
0x140994827  mov     r9, r12
0x14099482a  mov     r8d, 0F003Fh
0x140994830  mov     rdx, r14
0x140994833  call    BiOpenKey
0x140994838  mov     ebx, eax
0x14099483a  test    eax, eax
0x14099483c  jns     short loc_1409947F6
0x14099483e  mov     ecx, 4
0x140994843  lea     rdx, aFailedToOpenOb; "Failed to open object's key. Status: %x"
0x14099484a  cmp     eax, 0C0000034h
0x14099484f  cmovnz  edi, ecx
0x140994852  mov     ecx, edi
0x140994854  jmp     short loc_1409947EE
0x140994856  mov     ecx, [rbp+57h+var_D0]
0x140994859  sub     ecx, 1
0x14099485c  jz      loc_140B6358A
0x140994862  cmp     ecx, 1
0x140994865  jz      loc_140B6357C
0x14099486b  mov     ebx, 0C000000Dh
0x140994870  jmp     loc_140B635C1
0x140b6357c  lea     rdx, [rbp+57h+var_A8]
0x140b63580  mov     rcx, r15
0x140b63583  call    BiGetDefaultBootEntryIdentifier
0x140b63588  jmp     short loc_140B63593
0x140b6358a  lea     rcx, [rbp+57h+var_A8]
0x140b6358e  call    BiGetCurrentBootEntryIdentifier
0x140b63593  mov     ebx, eax
0x140b63595  test    eax, eax
0x140b63597  js      short loc_140B635C1
0x140b63599  lea     rdx, [rbp+57h+var_C0]
0x140b6359d  lea     rcx, [rbp+57h+var_A8]
0x140b635a1  call    BiStringFromGUID
0x140b635a6  mov     r14, [rbp+57h+var_B8]
0x140b635aa  lea     rdx, aObjectAliasRes; "Object alias resolves to %s"
0x140b635b1  mov     r8, r14
0x140b635b4  mov     ecx, edi
0x140b635b6  call    BiLogMessage
0x140b635bb  nop
0x140b635bc  jmp     loc_140994823
0x140b635c1  mov     r8d, ebx
0x140b635c4  lea     rdx, aFailedToGetAli; "Failed to get aliased identifier. Statu"...
0x140b635cb  mov     ecx, 4
0x140b635d0  jmp     loc_1409947F1
```
