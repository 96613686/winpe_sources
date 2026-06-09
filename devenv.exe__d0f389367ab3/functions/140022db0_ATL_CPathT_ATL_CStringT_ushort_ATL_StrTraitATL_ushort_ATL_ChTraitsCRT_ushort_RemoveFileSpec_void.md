# ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)

- ea: `0x140022db0`
- end: `0x140022e3d`
- name: `?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ`
- size: `141`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400033f0`
- `0x14001a938`
- `0x14001d8a0`
- `0x1400222b0`
- `0x140022d80`
- `0x140024c30`
- `0x14002a1b0`
- `0x14002a810`
- `0x14003eff0`
- `0x140041648`
- `0x140047690`
- `0x140048444`
- `0x14004b1b0`
- `0x140051c20`
- `0x140060fa0`
- `0x1400618d0`
- `0x140061a60`
- `0x140064b20`

## callees

- `0x140002dd0`
- `0x140022db0`
- `0x140033ab0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140022e03`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140022e03`
- `SHLWAPI!PathRemoveFileSpecW` at `0x140022deb`
- `SHLWAPI!PathRemoveFileSpecW` at `0x140022deb`

## pseudocode

```c
__int64 __fastcall ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(
        LPWSTR *a1)
{
  __int64 v2; // rdx
  unsigned int v3; // edi
  int v4; // eax

  v2 = *((unsigned int *)*a1 - 4);
  if ( (int)v2 < 0 )
    goto LABEL_9;
  if ( (int)((*((_DWORD *)*a1 - 3) - v2) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v2);
  }
  v3 = PathRemoveFileSpecW(*a1);
  if ( *a1 )
  {
    v4 = wcsnlen(*a1, *((int *)*a1 - 3));
    if ( v4 < 0 )
      goto LABEL_9;
  }
  else
  {
    v4 = 0;
  }
  if ( v4 > *((_DWORD *)*a1 - 3) )
LABEL_9:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v4;
  (*a1)[v4] = 0;
  return v3;
}

```

## disassembly

```asm
0x140022db0  mov     [rsp+arg_0], rbx
0x140022db5  mov     [rsp+arg_8], rsi
0x140022dba  push    rdi
0x140022dbb  sub     rsp, 20h
0x140022dbf  mov     rax, [rcx]
0x140022dc2  xor     esi, esi
0x140022dc4  mov     rbx, rcx
0x140022dc7  mov     edx, [rax-10h]
0x140022dca  test    edx, edx
0x140022dcc  js      short loc_140022E33
0x140022dce  lea     r8d, [rsi+1]
0x140022dd2  sub     r8d, [rax-8]
0x140022dd6  mov     eax, [rax-0Ch]
0x140022dd9  sub     eax, edx
0x140022ddb  or      r8d, eax
0x140022dde  jge     short loc_140022DE8
0x140022de0  lfence
0x140022de3  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140022de8  mov     rcx, [rbx]; pszPath
0x140022deb  call    cs:__imp_PathRemoveFileSpecW
0x140022df1  mov     rcx, [rbx]; Source
0x140022df4  mov     edi, eax
0x140022df6  test    rcx, rcx
0x140022df9  jnz     short loc_140022DFF
0x140022dfb  mov     eax, esi
0x140022dfd  jmp     short loc_140022E0D
0x140022dff  movsxd  rdx, dword ptr [rcx-0Ch]; MaxCount
0x140022e03  call    cs:__imp_wcsnlen
0x140022e09  test    eax, eax
0x140022e0b  js      short loc_140022E33
0x140022e0d  mov     rcx, [rbx]
0x140022e10  cmp     eax, [rcx-0Ch]
0x140022e13  jg      short loc_140022E33
0x140022e15  mov     [rcx-10h], eax
0x140022e18  mov     ecx, eax
0x140022e1a  mov     rax, [rbx]
0x140022e1d  mov     rbx, [rsp+28h+arg_0]
0x140022e22  mov     [rax+rcx*2], si
0x140022e26  mov     eax, edi
0x140022e28  mov     rsi, [rsp+28h+arg_8]
0x140022e2d  add     rsp, 20h
0x140022e31  pop     rdi
0x140022e32  retn
0x140022e33  mov     ecx, 80070057h; int
0x140022e38  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
