# IsRuleGroup(_tag_FW_RULE *,ushort *,ulong)

- ea: `0x180022b1c`
- end: `0x180022be0`
- name: `?IsRuleGroup@@YAHPEAU_tag_FW_RULE@@PEAGK@Z`
- size: `196`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022324`
- `0x18002bfe0`

## callees

- `0x18000994c`
- `0x180022b1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022bad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022bad`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180022b51`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180022b51`

## pseudocode

```c
__int64 __fastcall IsRuleGroup(struct _tag_FW_RULE *a1, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  const WCHAR *v4; // rcx
  HRESULT v6; // eax

  *a2 = 0;
  v3 = 0;
  v4 = (const WCHAR *)*((_QWORD *)a1 + 39);
  if ( v4 )
  {
    v6 = SHLoadIndirectString(v4, a2, 0x400u, 0);
    if ( v6 >= 0 )
    {
      return CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a1 + 39), -1, a2, -1) != 2 || (**((_WORD **)a1 + 39) & 0xFFBF) != 0;
    }
    else if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_1aaa36be460e3ec051e4f2cd9cb11fbc_Traceguids,
        (unsigned int)v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180022b1c  mov     [rsp+arg_0], rbx
0x180022b21  mov     [rsp+arg_8], rsi
0x180022b26  push    rdi
0x180022b27  sub     rsp, 30h
0x180022b2b  xor     eax, eax
0x180022b2d  mov     rsi, rcx
0x180022b30  mov     [rdx], ax
0x180022b33  xor     ebx, ebx
0x180022b35  mov     rcx, [rcx+138h]; pszSource
0x180022b3c  mov     rdi, rdx
0x180022b3f  test    rcx, rcx
0x180022b42  jz      loc_180022BCE
0x180022b48  xor     r9d, r9d; ppvReserved
0x180022b4b  mov     r8d, 400h; cchOutBuf
0x180022b51  call    cs:__imp_SHLoadIndirectString
0x180022b57  test    eax, eax
0x180022b59  jns     short loc_180022B8F
0x180022b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b62  lea     rdx, WPP_GLOBAL_Control
0x180022b69  cmp     rcx, rdx
0x180022b6c  jz      short loc_180022BCE
0x180022b6e  lea     edi, [rbx+1]
0x180022b71  test    [rcx+1Ch], dil
0x180022b75  jz      short loc_180022BCE
0x180022b77  mov     rcx, [rcx+10h]
0x180022b7b  lea     edx, [rbx+0Ah]
0x180022b7e  mov     r9d, eax
0x180022b81  lea     r8, WPP_1aaa36be460e3ec051e4f2cd9cb11fbc_Traceguids
0x180022b88  call    WPP_SF_d
0x180022b8d  jmp     short loc_180022BCE
0x180022b8f  mov     r8, [rsi+138h]; lpString1
0x180022b96  or      r9d, 0FFFFFFFFh; cchCount1
0x180022b9a  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180022b9f  mov     [rsp+38h+lpString2], rdi; lpString2
0x180022ba4  lea     edi, [r9+2]
0x180022ba8  mov     edx, edi; dwCmpFlags
0x180022baa  lea     ecx, [rdi+7Eh]; Locale
0x180022bad  call    cs:__imp_CompareStringW
0x180022bb3  cmp     eax, 2
0x180022bb6  jz      short loc_180022BBC
0x180022bb8  mov     ebx, edi
0x180022bba  jmp     short loc_180022BCE
0x180022bbc  mov     rcx, [rsi+138h]
0x180022bc3  mov     eax, 0FFBFh
0x180022bc8  test    [rcx], ax
0x180022bcb  cmovnz  ebx, edi
0x180022bce  mov     rsi, [rsp+38h+arg_8]
0x180022bd3  mov     eax, ebx
0x180022bd5  mov     rbx, [rsp+38h+arg_0]
0x180022bda  add     rsp, 30h
0x180022bde  pop     rdi
0x180022bdf  retn
```
