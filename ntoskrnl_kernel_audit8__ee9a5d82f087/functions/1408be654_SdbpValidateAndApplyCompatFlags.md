# SdbpValidateAndApplyCompatFlags

- ea: `0x1408be654`
- end: `0x1408be773`
- name: `SdbpValidateAndApplyCompatFlags`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140821914`
- `0x1408bebe8`

## callees

- `0x14049d9e0`
- `0x1408be654`
- `0x1408be77c`
- `0x1408c132c`
- `0x1408c2c64`
- `0x1408c2f88`

## string_xrefs

- `0x1408be6d7`: `SdbpValidateAndApplyCompatFlags`
- `0x1408be711`: `SdbpValidateAndApplyCompatFlags`
- `0x1408be731`: `SdbpValidateAndApplyCompatFlags`

## pseudocode

```c
__int64 __fastcall SdbpValidateAndApplyCompatFlags(__int64 a1, _DWORD *a2, char a3)
{
  unsigned int v4; // edi

  v4 = 0;
  if ( *a2 == 1 )
  {
    *(_DWORD *)(a1 + 2608) |= 1u;
    goto LABEL_12;
  }
  if ( *a2 == 2 )
  {
LABEL_12:
    *(_DWORD *)(a1 + 2608) |= 2u;
    goto LABEL_4;
  }
  if ( *a2 != 3 && (a3 & 1) == 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpValidateAndApplyCompatFlags",
      979,
      (unsigned int)"MajorVersion mismatch, MajorVersion [0x%lx] Expected 0x%lx");
    return v4;
  }
LABEL_4:
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
    && (int)SdbpValidateRootTagSizes(a1) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpValidateAndApplyCompatFlags",
      990,
      (unsigned int)"SdbpValidateRootTagSizes failed to validate SDB [%x]");
  }
  else
  {
    if ( (unsigned int)SdbGetDatabaseID(a1, a1 + 28) )
      return 1;
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpValidateAndApplyCompatFlags",
      1003,
      (unsigned int)"Failed to get the database ID");
    if ( (a3 & 8) == 0 && ((a3 & 4) == 0 || (unsigned int)SdbFindFirstTag(a1, 0, 28673)) )
      return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x1408be654  mov     [rsp+arg_0], rbx
0x1408be659  mov     [rsp+arg_8], rsi
0x1408be65e  push    rdi
0x1408be65f  sub     rsp, 30h
0x1408be663  mov     esi, r8d
0x1408be666  xor     edi, edi
0x1408be668  mov     r8d, [rdx]
0x1408be66b  mov     rbx, rcx
0x1408be66e  mov     eax, r8d
0x1408be671  sub     eax, 1
0x1408be674  jz      short loc_1408BE6F0
0x1408be676  sub     eax, 1
0x1408be679  jz      short loc_1408BE6F7
0x1408be67b  cmp     eax, 1
0x1408be67e  jnz     short loc_1408BE6BD
0x1408be680  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1408be685  test    eax, eax
0x1408be687  jz      short loc_1408BE695
0x1408be689  mov     rcx, rbx
0x1408be68c  call    SdbpValidateRootTagSizes
0x1408be691  test    eax, eax
0x1408be693  js      short loc_1408BE700
0x1408be695  lea     rdx, [rbx+1Ch]
0x1408be699  mov     rcx, rbx
0x1408be69c  call    SdbGetDatabaseID
0x1408be6a1  test    eax, eax
0x1408be6a3  jz      short loc_1408BE724
0x1408be6a5  mov     edi, 1
0x1408be6aa  mov     rbx, [rsp+38h+arg_0]
0x1408be6af  mov     eax, edi
0x1408be6b1  mov     rsi, [rsp+38h+arg_8]
0x1408be6b6  add     rsp, 30h
0x1408be6ba  pop     rdi
0x1408be6bb  retn
0x1408be6bd  test    sil, 1
0x1408be6c1  jnz     short loc_1408BE680
0x1408be6c3  mov     [rsp+38h+var_10], 3
0x1408be6cb  lea     r9, aMajorversionMi; "MajorVersion mismatch, MajorVersion [0x"...
0x1408be6d2  mov     [rsp+38h+var_18], r8d
0x1408be6d7  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x1408be6de  mov     r8d, 3D3h
0x1408be6e4  mov     ecx, 1
0x1408be6e9  call    AslLogCallPrintf
0x1408be6ee  jmp     short loc_1408BE6AA
0x1408be6f0  or      dword ptr [rcx+0A30h], 1
0x1408be6f7  or      dword ptr [rcx+0A30h], 2
0x1408be6fe  jmp     short loc_1408BE680
0x1408be700  lea     r9, aSdbpvalidatero; "SdbpValidateRootTagSizes failed to vali"...
0x1408be707  mov     [rsp+38h+var_18], eax
0x1408be70b  mov     r8d, 3DEh
0x1408be711  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x1408be718  mov     ecx, 1
0x1408be71d  call    AslLogCallPrintf
0x1408be722  jmp     short loc_1408BE6AA
0x1408be724  lea     r9, aFailedToGetThe; "Failed to get the database ID"
0x1408be72b  mov     r8d, 3EBh
0x1408be731  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x1408be738  mov     ecx, 1
0x1408be73d  call    AslLogCallPrintf
0x1408be742  test    sil, 8
0x1408be746  jnz     loc_1408BE6AA
0x1408be74c  test    sil, 4
0x1408be750  jz      loc_1408BE6A5
0x1408be756  xor     edx, edx
0x1408be758  mov     r8d, 7001h
0x1408be75e  mov     rcx, rbx
0x1408be761  call    SdbFindFirstTag
0x1408be766  test    eax, eax
0x1408be768  jz      loc_1408BE6AA
0x1408be76e  jmp     loc_1408BE6A5
```
