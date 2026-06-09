# NgcAreStringsEqual

- ea: `0x18000fd00`
- end: `0x18000fdb0`
- name: `NgcAreStringsEqual`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x18000fd00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fd91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fd91`

## string_xrefs

- `0x18000fd1b`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18000fd42`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x18000fd69`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`

## pseudocode

```c
__int64 __fastcall NgcAreStringsEqual(const WCHAR *a1, const WCHAR *a2, _DWORD *a3)
{
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        *a3 = CompareStringOrdinal(a1, -1, a2, -1, 1) == 2;
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FE,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
          (const char *)0x80004003LL,
          bIgnoreCase);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
        (const char *)0x80004003LL,
        bIgnoreCase);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      bIgnoreCase);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000fd00  push    rbx
0x18000fd02  sub     rsp, 30h
0x18000fd06  mov     rbx, r8
0x18000fd09  test    rcx, rcx
0x18000fd0c  jnz     short loc_18000FD30
0x18000fd0e  mov     rcx, [rsp+38h]; this
0x18000fd13  mov     ebx, 80004003h
0x18000fd18  mov     r9d, ebx; char *
0x18000fd1b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000fd22  mov     edx, 1FCh; void *
0x18000fd27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd2c  mov     eax, ebx
0x18000fd2e  jmp     short loc_18000FDA9
0x18000fd30  test    rdx, rdx
0x18000fd33  jnz     short loc_18000FD57
0x18000fd35  mov     rcx, [rsp+38h]; this
0x18000fd3a  mov     ebx, 80004003h
0x18000fd3f  mov     r9d, ebx; char *
0x18000fd42  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000fd49  mov     edx, 1FDh; void *
0x18000fd4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd53  mov     eax, ebx
0x18000fd55  jmp     short loc_18000FDA9
0x18000fd57  test    rbx, rbx
0x18000fd5a  jnz     short loc_18000FD7E
0x18000fd5c  mov     rcx, [rsp+38h]; this
0x18000fd61  mov     ebx, 80004003h
0x18000fd66  mov     r9d, ebx; char *
0x18000fd69  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000fd70  mov     edx, 1FEh; void *
0x18000fd75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd7a  mov     eax, ebx
0x18000fd7c  jmp     short loc_18000FDA9
0x18000fd7e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000fd86  or      eax, 0FFFFFFFFh
0x18000fd89  mov     r9d, eax; cchCount2
0x18000fd8c  mov     r8, rdx; lpString2
0x18000fd8f  mov     edx, eax; cchCount1
0x18000fd91  call    cs:__imp_CompareStringOrdinal
0x18000fd97  xor     ecx, ecx
0x18000fd99  cmp     eax, 2
0x18000fd9c  setz    cl
0x18000fd9f  mov     [rbx], ecx
0x18000fda1  xor     eax, eax
0x18000fda3  jmp     short loc_18000FDA9
0x18000fda5  mov     eax, [rsp+38h+arg_0]
0x18000fda9  add     rsp, 30h
0x18000fdad  pop     rbx
0x18000fdae  retn
```
