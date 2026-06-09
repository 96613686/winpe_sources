# XCompare::compStringStringLex(ulong,XCompare::CompareFlags,String *,String *)

- ea: `0x100e9478`
- end: `0x100e94e5`
- name: `?compStringStringLex@XCompare@@SGHKW4CompareFlags@1@PAVString@@1@Z`
- size: `109`
- prototype: `int __userpurge@<eax>(unsigned int lcid@<ecx>, XCompare::CompareFlags flags@<edx>, String *str1, String *str2)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100d9710`
- `0x100e9400`

## callees

- `0x100e9478`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e94af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e94d1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e94af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x100e94d1`

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
0x100e9478  mov     edi, edi
0x100e947a  push    ebp
0x100e947b  mov     ebp, esp
0x100e947d  push    lcid
0x100e947e  push    ebx
0x100e947f  mov     ebx, flags
0x100e9481  mov     [ebp+Locale], lcid
0x100e9484  push    esi
0x100e9485  xor     eax, eax
0x100e9487  push    edi
0x100e9488  test    bl, 18h
0x100e948b  jz      short loc_100E949B
0x100e948d  push    1
0x100e948f  test    bl, 8
0x100e9492  mov     flags, 30001h
0x100e9497  pop     eax
0x100e9498  cmovnz  eax, flags
0x100e949b  mov     esi, [ebp+str2]
0x100e949e  mov     edi, [ebp+str1]
0x100e94a1  push    dword ptr [esi+8]; cchCount2
0x100e94a4  push    dword ptr [esi+0Ch]; lpString2
0x100e94a7  push    dword ptr [edi+8]; cchCount1
0x100e94aa  push    dword ptr [edi+0Ch]; lpString1
0x100e94ad  push    eax; dwCmpFlags
0x100e94ae  push    lcid; Locale
0x100e94af  call    ds:__imp__CompareStringW@24; CompareStringW(x,x,x,x,x,x)
0x100e94b5  lea     lcid, [eax-2]
0x100e94b8  test    bl, 10h
0x100e94bb  jz      short loc_100E94DC
0x100e94bd  test    lcid, lcid
0x100e94bf  jnz     short loc_100E94DC
0x100e94c1  push    dword ptr [esi+8]; cchCount2
0x100e94c4  push    dword ptr [esi+0Ch]; lpString2
0x100e94c7  push    dword ptr [edi+8]; cchCount1
0x100e94ca  push    dword ptr [edi+0Ch]; lpString1
0x100e94cd  push    lcid; dwCmpFlags
0x100e94ce  push    [ebp+Locale]; Locale
0x100e94d1  call    ds:__imp__CompareStringW@24; CompareStringW(x,x,x,x,x,x)
0x100e94d7  push    2
0x100e94d9  pop     lcid
0x100e94da  sub     lcid, eax
0x100e94dc  pop     edi
0x100e94dd  pop     esi
0x100e94de  mov     eax, lcid
0x100e94e0  pop     ebx
0x100e94e1  leave
0x100e94e2  retn    8
```
