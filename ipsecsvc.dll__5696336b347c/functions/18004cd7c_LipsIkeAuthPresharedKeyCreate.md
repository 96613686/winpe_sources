# LipsIkeAuthPresharedKeyCreate

- ea: `0x18004cd7c`
- end: `0x18004ce3a`
- name: `LipsIkeAuthPresharedKeyCreate`
- size: `190`
- prototype: `__int64 __fastcall(__int64, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004cb0c`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004cd7c`
- `0x18004ce40`

## string_xrefs

- `0x18004ce22`: `LipsIkeAuthPresharedKeyCreate`

## pseudocode

```c
__int64 __fastcall LipsIkeAuthPresharedKeyCreate(__int64 a1, unsigned int *a2, __int64 a3)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r10
  __int64 v9; // rax

  v4 = *a2;
  if ( (unsigned int)v4 >= *(_DWORD *)(a3 + 8) )
  {
    v5 = 13;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)LipsReportError(v5, "LipsIkeAuthPresharedKeyCreate");
    v7 = 21;
LABEL_9:
    WPP_SF_d(v6[2], v7, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids, v5);
    return (unsigned int)LipsReportError(v5, "LipsIkeAuthPresharedKeyCreate");
  }
  v8 = 3LL * a2[1];
  v9 = *(_QWORD *)(a1 + 32);
  *(_DWORD *)((v4 << 6) + *(_QWORD *)a3) = 0;
  v5 = LipsStringCopyWtoAAlloc(*(LPCWCH *)(v9 + 8 * v8 + 8), *(_DWORD *)(v9 + 8 * v8 + 4) >> 1);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)LipsReportError(v5, "LipsIkeAuthPresharedKeyCreate");
    v7 = 22;
    goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x18004cd7c  push    rbx
0x18004cd7e  sub     rsp, 20h
0x18004cd82  mov     rax, rdx
0x18004cd85  mov     r9, rcx
0x18004cd88  mov     edx, [rdx]
0x18004cd8a  cmp     edx, [r8+8]
0x18004cd8e  jb      short loc_18004CDB3
0x18004cd90  mov     ebx, 0Dh
0x18004cd95  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cd9c  lea     rax, WPP_GLOBAL_Control
0x18004cda3  cmp     rcx, rax
0x18004cda6  jz      short loc_18004CE22
0x18004cda8  test    byte ptr [rcx+1Ch], 10h
0x18004cdac  jz      short loc_18004CE22
0x18004cdae  lea     edx, [rbx+8]
0x18004cdb1  jmp     short loc_18004CE0F
0x18004cdb3  mov     rcx, [r8]
0x18004cdb6  mov     eax, [rax+4]
0x18004cdb9  shl     rdx, 6
0x18004cdbd  lea     r8, [rcx+10h]
0x18004cdc1  lea     r10, [rax+rax*2]
0x18004cdc5  add     r8, rdx
0x18004cdc8  mov     rax, [r9+20h]
0x18004cdcc  lea     r9, [rcx+8]
0x18004cdd0  mov     dword ptr [rdx+rcx], 0
0x18004cdd7  add     r9, rdx
0x18004cdda  mov     edx, [rax+r10*8+4]
0x18004cddf  mov     rcx, [rax+r10*8+8]; lpWideCharStr
0x18004cde4  shr     edx, 1; cchWideChar
0x18004cde6  call    LipsStringCopyWtoAAlloc
0x18004cdeb  mov     ebx, eax
0x18004cded  test    eax, eax
0x18004cdef  jz      short loc_18004CE32
0x18004cdf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cdf8  lea     rax, WPP_GLOBAL_Control
0x18004cdff  cmp     rcx, rax
0x18004ce02  jz      short loc_18004CE22
0x18004ce04  test    byte ptr [rcx+1Ch], 10h
0x18004ce08  jz      short loc_18004CE22
0x18004ce0a  mov     edx, 16h
0x18004ce0f  mov     rcx, [rcx+10h]
0x18004ce13  lea     r8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids
0x18004ce1a  mov     r9d, ebx
0x18004ce1d  call    WPP_SF_d
0x18004ce22  lea     rdx, aLipsikeauthpre; "LipsIkeAuthPresharedKeyCreate"
0x18004ce29  mov     ecx, ebx
0x18004ce2b  call    LipsReportError
0x18004ce30  mov     ebx, eax
0x18004ce32  mov     eax, ebx
0x18004ce34  add     rsp, 20h
0x18004ce38  pop     rbx
0x18004ce39  retn
```
