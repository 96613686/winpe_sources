# XCompare::compStringStringLex(ulong,XCompare::CompareFlags,String *,String *)

- ea: `0x1800716cc`
- end: `0x180071755`
- name: `?compStringStringLex@XCompare@@SAHKW4CompareFlags@1@PEAVString@@1@Z`
- size: `137`
- prototype: `int __fastcall(unsigned int lcid, XCompare::CompareFlags flags, String *str1, String *str2)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180071670`
- `0x180115600`

## callees

- `0x1800716cc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007170f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007173d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007170f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007173d`

## pseudocode

```c
__int64 __fastcall XCompare::compStringStringLex(LCID lcid, XCompare::CompareFlags flags, String *str1, String *str2)
{
  char v4; // bl
  DWORD v6; // edx
  unsigned int v9; // ecx

  v4 = flags;
  v6 = 0;
  if ( (v4 & 0x18) != 0 )
    v6 = (v4 & 8) != 0 ? 196609 : 1;
  v9 = CompareStringW(lcid, v6, str1->_pwsz, str1->_length, str2->_pwsz, str2->_length) - 2;
  if ( (v4 & 0x10) != 0 && !v9 )
    return (unsigned int)(2 - CompareStringW(lcid, 0, str1->_pwsz, str1->_length, str2->_pwsz, str2->_length));
  return v9;
}

```

## disassembly

```asm
0x1800716cc  push    rbx
0x1800716ce  push    rbp
0x1800716cf  push    rsi
0x1800716d0  push    rdi
0x1800716d1  sub     rsp, 38h
0x1800716d5  mov     ebx, flags
0x1800716d7  mov     rdi, str2
0x1800716da  xor     flags, flags
0x1800716dc  mov     rsi, str1
0x1800716df  mov     ebp, lcid
0x1800716e1  test    bl, 18h
0x1800716e4  jz      short loc_1800716F6
0x1800716e6  mov     al, bl
0x1800716e8  and     al, 8
0x1800716ea  neg     al
0x1800716ec  sbb     flags, flags
0x1800716ee  and     flags, 30000h
0x1800716f4  inc     flags; dwCmpFlags
0x1800716f6  mov     eax, [str2+10h]
0x1800716fa  mov     [rsp+58h+cchCount2], eax; cchCount2
0x1800716fe  mov     rax, [str2+18h]
0x180071702  mov     r9d, [str1+10h]; cchCount1
0x180071706  mov     str1, [str1+18h]; lpString1
0x18007170a  mov     [rsp+58h+lpString2], rax; lpString2
0x18007170f  call    cs:__imp_CompareStringW
0x180071715  lea     lcid, [rax-2]
0x180071718  test    bl, 10h
0x18007171b  jz      short loc_18007174A
0x18007171d  test    lcid, lcid
0x18007171f  jnz     short loc_18007174A
0x180071721  mov     eax, [rdi+10h]
0x180071724  xor     flags, flags; dwCmpFlags
0x180071726  mov     r9d, [rsi+10h]; cchCount1
0x18007172a  mov     lcid, ebp; Locale
0x18007172c  mov     str1, [rsi+18h]; lpString1
0x180071730  mov     [rsp+58h+cchCount2], eax; cchCount2
0x180071734  mov     rax, [rdi+18h]
0x180071738  mov     [rsp+58h+lpString2], rax; lpString2
0x18007173d  call    cs:__imp_CompareStringW
0x180071743  mov     lcid, 2
0x180071748  sub     lcid, eax
0x18007174a  mov     eax, lcid
0x18007174c  add     rsp, 38h
0x180071750  pop     rdi
0x180071751  pop     rsi
0x180071752  pop     rbp
0x180071753  pop     rbx
0x180071754  retn
```
