# SaBlob_WriteNameOrAlias

- ea: `0x18001671c`
- end: `0x1800167eb`
- name: `SaBlob_WriteNameOrAlias`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015310`
- `0x18001571c`

## callees

- `0x18001671c`
- `0x180029a14`
- `0x18002a98c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167bb`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x1800167a7`
- `DNSAPI!DnsStringCopyAllocateEx` at `0x1800167a7`

## pseudocode

```c
DWORD __fastcall SaBlob_WriteNameOrAlias(__int64 a1, _WORD *a2, int a3)
{
  __int64 v3; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v9; // rax
  __int64 v10; // rcx

  v3 = *(unsigned int *)(a1 + 24);
  if ( a3 )
  {
    if ( (unsigned int)v3 < 8 )
      goto LABEL_3;
    return 234;
  }
  if ( *(_QWORD *)a1 )
    return 234;
LABEL_3:
  if ( (Feature_5977_1413__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( !a2 )
      return 13;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    if ( !v9 )
      return 13;
    v10 = SaBlob_StringCopyAllocW(a2);
    if ( !v10 )
      return 14;
  }
  else
  {
    v10 = DnsStringCopyAllocateEx(a2, 0, 1);
    if ( !v10 )
      return GetLastError();
  }
  if ( a3 )
  {
    *(_QWORD *)(a1 + 8 * v3 + 32) = v10;
    *(_DWORD *)(a1 + 24) = v3 + 1;
  }
  else
  {
    *(_QWORD *)a1 = v10;
  }
  return 0;
}

```

## disassembly

```asm
0x18001671c  push    rbx
0x18001671e  push    rbp
0x18001671f  push    rsi
0x180016720  push    rdi
0x180016721  push    r14
0x180016723  sub     rsp, 20h
0x180016727  mov     esi, [rcx+18h]
0x18001672a  xor     r14d, r14d
0x18001672d  mov     ebp, r8d
0x180016730  mov     rdi, rdx
0x180016733  mov     rbx, rcx
0x180016736  test    r8d, r8d
0x180016739  jz      short loc_18001674F
0x18001673b  cmp     esi, 8
0x18001673e  jnb     short loc_180016754
0x180016740  mov     eax, cs:Feature_5977_1413__private_featureState
0x180016746  test    al, 10h
0x180016748  jz      short loc_18001675E
0x18001674a  and     eax, 1
0x18001674d  jmp     short loc_180016763
0x18001674f  cmp     [rcx], r14
0x180016752  jz      short loc_180016740
0x180016754  mov     eax, 0EAh
0x180016759  jmp     loc_1800167DF
0x18001675e  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x180016763  test    eax, eax
0x180016765  jz      short loc_18001679B
0x180016767  test    rdi, rdi
0x18001676a  jz      short loc_180016794
0x18001676c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016770  inc     rax
0x180016773  cmp     [rdi+rax*2], r14w
0x180016778  jnz     short loc_180016770
0x18001677a  test    rax, rax
0x18001677d  jz      short loc_180016794
0x18001677f  mov     rcx, rdi; Src
0x180016782  call    SaBlob_StringCopyAllocW
0x180016787  mov     rcx, rax
0x18001678a  test    rax, rax
0x18001678d  jnz     short loc_1800167C9
0x18001678f  lea     eax, [rcx+0Eh]
0x180016792  jmp     short loc_1800167DF
0x180016794  mov     eax, 0Dh
0x180016799  jmp     short loc_1800167DF
0x18001679b  xor     edx, edx
0x18001679d  mov     rcx, rdi
0x1800167a0  lea     r9d, [rdx+1]
0x1800167a4  mov     r8d, r9d
0x1800167a7  call    cs:__imp_DnsStringCopyAllocateEx
0x1800167ae  nop     dword ptr [rax+rax+00h]
0x1800167b3  mov     rcx, rax
0x1800167b6  test    rax, rax
0x1800167b9  jnz     short loc_1800167C9
0x1800167bb  call    cs:__imp_GetLastError
0x1800167c2  nop     dword ptr [rax+rax+00h]
0x1800167c7  jmp     short loc_1800167DF
0x1800167c9  test    ebp, ebp
0x1800167cb  jz      short loc_1800167DA
0x1800167cd  lea     eax, [rsi+1]
0x1800167d0  mov     [rbx+rsi*8+20h], rcx
0x1800167d5  mov     [rbx+18h], eax
0x1800167d8  jmp     short loc_1800167DD
0x1800167da  mov     [rbx], rcx
0x1800167dd  xor     eax, eax
0x1800167df  add     rsp, 20h
0x1800167e3  pop     r14
0x1800167e5  pop     rdi
0x1800167e6  pop     rsi
0x1800167e7  pop     rbp
0x1800167e8  pop     rbx
0x1800167e9  retn
```
