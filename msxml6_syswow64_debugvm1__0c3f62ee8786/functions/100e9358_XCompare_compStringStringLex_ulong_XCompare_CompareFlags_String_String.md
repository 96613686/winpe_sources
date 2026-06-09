# XCompare::compStringStringLex(ulong,XCompare::CompareFlags,String *,String *)

- ea: `0x100e9358`
- end: `0x100e93c5`
- name: `?compStringStringLex@XCompare@@SGHKW4CompareFlags@1@PAVString@@1@Z`
- size: `109`
- prototype: `int __userpurge@<eax>(unsigned int lcid@<ecx>, XCompare::CompareFlags flags@<edx>, String *str1, String *str2)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100d95f0`
- `0x100e92e0`

## callees

- `0x100e9358`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e938f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e93b1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e938f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e93b1`

## pseudocode

```c
int __fastcall XCompare::compStringStringLex(LCID lcid, XCompare::CompareFlags flags, String *str1, String *str2)
{
  char v4; // bl
  DWORD v5; // eax
  int v6; // eax
  int v7; // ecx

  v4 = flags;
  v5 = 0;
  if ( (flags & 0x18) != 0 )
  {
    v5 = 1;
    if ( (flags & 8) != 0 )
      v5 = 196609;
  }
  v6 = CompareStringW(lcid, v5, str1->_pwsz, str1->_length, str2->_pwsz, str2->_length);
  v7 = v6 - 2;
  if ( (v4 & 0x10) != 0 && v6 == 2 )
    return 2 - CompareStringW(lcid, 0, str1->_pwsz, str1->_length, str2->_pwsz, str2->_length);
  return v7;
}

```

## disassembly

```asm
0x100e9358  mov     edi, edi
0x100e935a  push    ebp
0x100e935b  mov     ebp, esp
0x100e935d  push    lcid
0x100e935e  push    ebx
0x100e935f  mov     ebx, flags
0x100e9361  mov     [ebp+Locale], lcid
0x100e9364  push    esi
0x100e9365  xor     eax, eax
0x100e9367  push    edi
0x100e9368  test    bl, 18h
0x100e936b  jz      short loc_100E937B
0x100e936d  push    1
0x100e936f  test    bl, 8
0x100e9372  mov     flags, 30001h
0x100e9377  pop     eax
0x100e9378  cmovnz  eax, flags
0x100e937b  mov     esi, [ebp+str2]
0x100e937e  mov     edi, [ebp+str1]
0x100e9381  push    dword ptr [esi+8]; cchCount2
0x100e9384  push    dword ptr [esi+0Ch]; lpString2
0x100e9387  push    dword ptr [edi+8]; cchCount1
0x100e938a  push    dword ptr [edi+0Ch]; lpString1
0x100e938d  push    eax; dwCmpFlags
0x100e938e  push    lcid; Locale
0x100e938f  call    ds:__imp__CompareStringW@24; CompareStringW(x,x,x,x,x,x)
0x100e9395  lea     lcid, [eax-2]
0x100e9398  test    bl, 10h
0x100e939b  jz      short loc_100E93BC
0x100e939d  test    lcid, lcid
0x100e939f  jnz     short loc_100E93BC
0x100e93a1  push    dword ptr [esi+8]; cchCount2
0x100e93a4  push    dword ptr [esi+0Ch]; lpString2
0x100e93a7  push    dword ptr [edi+8]; cchCount1
0x100e93aa  push    dword ptr [edi+0Ch]; lpString1
0x100e93ad  push    lcid; dwCmpFlags
0x100e93ae  push    [ebp+Locale]; Locale
0x100e93b1  call    ds:__imp__CompareStringW@24; CompareStringW(x,x,x,x,x,x)
0x100e93b7  push    2
0x100e93b9  pop     lcid
0x100e93ba  sub     lcid, eax
0x100e93bc  pop     edi
0x100e93bd  pop     esi
0x100e93be  mov     eax, lcid
0x100e93c0  pop     ebx
0x100e93c1  leave
0x100e93c2  retn    8
```
