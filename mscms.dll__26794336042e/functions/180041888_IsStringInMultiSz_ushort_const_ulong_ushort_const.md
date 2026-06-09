# IsStringInMultiSz(ushort const *,ulong,ushort const *)

- ea: `0x180041888`
- end: `0x18004196d`
- name: `?IsStringInMultiSz@@YAHPEBGK0@Z`
- size: `229`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003e944`
- `0x180042334`
- `0x18004364c`

## callees

- `0x180040ea4`
- `0x180041888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041954`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004192f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004192f`

## pseudocode

```c
__int64 __fastcall IsStringInMultiSz(PCNZWCH lpString1, unsigned int a2, const unsigned __int16 *a3)
{
  const WCHAR *v4; // rbx
  __int64 cchCount2; // rdi
  unsigned int v6; // ebp
  unsigned int v7; // r14d
  const WCHAR *v8; // r12
  __int64 v9; // rsi
  __int64 v10; // rax
  unsigned int v12; // [rsp+88h] [rbp+10h] BYREF

  v12 = a2;
  v4 = lpString1;
  if ( !a3 || !lpString1 )
    goto LABEL_17;
  if ( !(unsigned int)GetMultiSzStringSize(lpString1, a2, &v12) )
    return 0;
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( a3[cchCount2] );
  if ( !(_DWORD)cchCount2 )
  {
LABEL_17:
    SetLastError(0x57u);
    return 0;
  }
  v6 = 0;
  v7 = 0;
  v8 = v4;
  while ( v7 < v12 && v4 - v8 < v12 && *v4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v4[v9] );
    if ( CompareStringW(0x7Fu, 1u, v4, v9, a3, cchCount2) == 2 )
      return 1;
    v10 = (unsigned int)(v9 + 1);
    v7 += v10;
    v4 += v10;
  }
  return v6;
}

```

## disassembly

```asm
0x180041888  mov     rax, rsp
0x18004188b  mov     [rax+10h], edx
0x18004188e  push    rbx
0x18004188f  push    rbp
0x180041890  push    rsi
0x180041891  push    rdi
0x180041892  push    r12
0x180041894  push    r13
0x180041896  push    r14
0x180041898  push    r15
0x18004189a  sub     rsp, 38h
0x18004189e  xor     r13d, r13d
0x1800418a1  mov     r15, r8
0x1800418a4  mov     rbx, rcx
0x1800418a7  test    r8, r8
0x1800418aa  jz      loc_18004194F
0x1800418b0  test    rcx, rcx
0x1800418b3  jz      loc_18004194F
0x1800418b9  lea     r8, [rax+10h]; unsigned int *
0x1800418bd  call    ?GetMultiSzStringSize@@YAHPEBGKPEAK@Z; GetMultiSzStringSize(ushort const *,ulong,ulong *)
0x1800418c2  test    eax, eax
0x1800418c4  jz      loc_18004195A
0x1800418ca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800418ce  inc     rdi
0x1800418d1  cmp     [r15+rdi*2], r13w
0x1800418d6  jnz     short loc_1800418CE
0x1800418d8  test    edi, edi
0x1800418da  jz      short loc_18004194F
0x1800418dc  mov     ebp, r13d
0x1800418df  mov     r14d, r13d
0x1800418e2  mov     r12, rbx
0x1800418e5  cmp     r14d, [rsp+78h+arg_8]
0x1800418ed  jnb     short loc_18004194B
0x1800418ef  mov     eax, [rsp+78h+arg_8]
0x1800418f6  mov     rcx, rbx
0x1800418f9  sub     rcx, r12
0x1800418fc  sar     rcx, 1
0x1800418ff  cmp     rcx, rax
0x180041902  jge     short loc_18004194B
0x180041904  cmp     [rbx], r13w
0x180041908  jz      short loc_18004194B
0x18004190a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004190e  inc     rsi
0x180041911  cmp     [rbx+rsi*2], r13w
0x180041916  jnz     short loc_18004190E
0x180041918  mov     edx, 1; dwCmpFlags
0x18004191d  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180041921  mov     r9d, esi; cchCount1
0x180041924  mov     [rsp+78h+lpString2], r15; lpString2
0x180041929  mov     r8, rbx; lpString1
0x18004192c  lea     ecx, [rdx+7Eh]; Locale
0x18004192f  call    cs:__imp_CompareStringW
0x180041935  cmp     eax, 2
0x180041938  jz      short loc_180041946
0x18004193a  lea     eax, [rsi+1]
0x18004193d  add     r14d, eax
0x180041940  lea     rbx, [rbx+rax*2]
0x180041944  jmp     short loc_1800418E5
0x180041946  mov     ebp, 1
0x18004194b  mov     eax, ebp
0x18004194d  jmp     short loc_18004195C
0x18004194f  mov     ecx, 57h ; 'W'; dwErrCode
0x180041954  call    cs:__imp_SetLastError
0x18004195a  xor     eax, eax
0x18004195c  add     rsp, 38h
0x180041960  pop     r15
0x180041962  pop     r14
0x180041964  pop     r13
0x180041966  pop     r12
0x180041968  pop     rdi
0x180041969  pop     rsi
0x18004196a  pop     rbp
0x18004196b  pop     rbx
0x18004196c  retn
```
