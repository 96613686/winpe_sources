# SdbpValidateAndApplyCompatFlags

- ea: `0x14097888c`
- end: `0x1409789ab`
- name: `SdbpValidateAndApplyCompatFlags`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14081f9a4`
- `0x140978e20`

## callees

- `0x14048e440`
- `0x14097888c`
- `0x1409789b4`
- `0x14097b4fc`
- `0x14097ce34`
- `0x14097d158`

## string_xrefs

- `0x14097890f`: `SdbpValidateAndApplyCompatFlags`
- `0x140978949`: `SdbpValidateAndApplyCompatFlags`
- `0x140978969`: `SdbpValidateAndApplyCompatFlags`

## pseudocode

```c
__int64 __fastcall SdbpValidateAndApplyCompatFlags(__int64 a1, _DWORD *a2, char a3)
{
  unsigned int v4; // edi
  int v6; // eax

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
      981,
      (unsigned int)"MajorVersion mismatch, MajorVersion [0x%lx] Expected 0x%lx",
      *a2,
      3);
    return v4;
  }
LABEL_4:
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
    && (v6 = SdbpValidateRootTagSizes(a1), v6 < 0) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpValidateAndApplyCompatFlags",
      992,
      (unsigned int)"SdbpValidateRootTagSizes failed to validate SDB [%x]",
      v6);
  }
  else
  {
    if ( (unsigned int)SdbGetDatabaseID(a1, a1 + 28) )
      return 1;
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpValidateAndApplyCompatFlags",
      1005,
      (unsigned int)"Failed to get the database ID");
    if ( (a3 & 8) == 0 && ((a3 & 4) == 0 || (unsigned int)SdbFindFirstTag(a1, 0, 28673)) )
      return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x14097888c  mov     [rsp+arg_0], rbx
0x140978891  mov     [rsp+arg_8], rsi
0x140978896  push    rdi
0x140978897  sub     rsp, 30h
0x14097889b  mov     esi, r8d
0x14097889e  xor     edi, edi
0x1409788a0  mov     r8d, [rdx]
0x1409788a3  mov     rbx, rcx
0x1409788a6  mov     eax, r8d
0x1409788a9  sub     eax, 1
0x1409788ac  jz      short loc_140978928
0x1409788ae  sub     eax, 1
0x1409788b1  jz      short loc_14097892F
0x1409788b3  cmp     eax, 1
0x1409788b6  jnz     short loc_1409788F5
0x1409788b8  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1409788bd  test    eax, eax
0x1409788bf  jz      short loc_1409788CD
0x1409788c1  mov     rcx, rbx
0x1409788c4  call    SdbpValidateRootTagSizes
0x1409788c9  test    eax, eax
0x1409788cb  js      short loc_140978938
0x1409788cd  lea     rdx, [rbx+1Ch]
0x1409788d1  mov     rcx, rbx
0x1409788d4  call    SdbGetDatabaseID
0x1409788d9  test    eax, eax
0x1409788db  jz      short loc_14097895C
0x1409788dd  mov     edi, 1
0x1409788e2  mov     rbx, [rsp+38h+arg_0]
0x1409788e7  mov     eax, edi
0x1409788e9  mov     rsi, [rsp+38h+arg_8]
0x1409788ee  add     rsp, 30h
0x1409788f2  pop     rdi
0x1409788f3  retn
0x1409788f5  test    sil, 1
0x1409788f9  jnz     short loc_1409788B8
0x1409788fb  mov     [rsp+38h+var_10], 3
0x140978903  lea     r9, aMajorversionMi; "MajorVersion mismatch, MajorVersion [0x"...
0x14097890a  mov     [rsp+38h+var_18], r8d
0x14097890f  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x140978916  mov     r8d, 3D5h
0x14097891c  mov     ecx, 1
0x140978921  call    AslLogCallPrintf
0x140978926  jmp     short loc_1409788E2
0x140978928  or      dword ptr [rcx+0A30h], 1
0x14097892f  or      dword ptr [rcx+0A30h], 2
0x140978936  jmp     short loc_1409788B8
0x140978938  lea     r9, aSdbpvalidatero; "SdbpValidateRootTagSizes failed to vali"...
0x14097893f  mov     [rsp+38h+var_18], eax
0x140978943  mov     r8d, 3E0h
0x140978949  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x140978950  mov     ecx, 1
0x140978955  call    AslLogCallPrintf
0x14097895a  jmp     short loc_1409788E2
0x14097895c  lea     r9, aFailedToGetThe; "Failed to get the database ID"
0x140978963  mov     r8d, 3EDh
0x140978969  lea     rdx, aSdbpvalidatean; "SdbpValidateAndApplyCompatFlags"
0x140978970  mov     ecx, 1
0x140978975  call    AslLogCallPrintf
0x14097897a  test    sil, 8
0x14097897e  jnz     loc_1409788E2
0x140978984  test    sil, 4
0x140978988  jz      loc_1409788DD
0x14097898e  xor     edx, edx
0x140978990  mov     r8d, 7001h
0x140978996  mov     rcx, rbx
0x140978999  call    SdbFindFirstTag
0x14097899e  test    eax, eax
0x1409789a0  jz      loc_1409788E2
0x1409789a6  jmp     loc_1409788DD
```
