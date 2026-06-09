# AslFileMappingGetFileKindDetail

- ea: `0x14000bf5c`
- end: `0x14000c10a`
- name: `AslFileMappingGetFileKindDetail`
- size: `430`
- prototype: `__int64 __fastcall(int *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d7d0`
- `0x14000f1f4`

## callees

- `0x140007074`
- `0x14000bde8`
- `0x14000bf5c`
- `0x14000c110`

## pseudocode

```c
__int64 __fastcall AslFileMappingGetFileKindDetail(int *a1, __int64 a2)
{
  bool v3; // zf
  int v5; // ebx
  int ImageType; // eax
  unsigned int v7; // edi
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v11; // [rsp+20h] [rbp-10h]
  __int16 v12; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 v13; // [rsp+68h] [rbp+38h] BYREF
  int v14; // [rsp+70h] [rbp+40h] BYREF
  int v15; // [rsp+78h] [rbp+48h] BYREF

  v3 = *(_DWORD *)(a2 + 56) == 1;
  v13 = 0;
  v12 = 0;
  v15 = 0;
  v14 = 0;
  if ( v3 )
  {
    v5 = 1;
LABEL_37:
    v7 = 0;
    goto LABEL_38;
  }
  v5 = 0;
  ImageType = AslFileMappingEnsure(a2);
  v7 = ImageType;
  if ( ImageType >= 0 )
  {
    switch ( *(_DWORD *)(a2 + 56) )
    {
      case 3:
        v5 = 2;
        goto LABEL_37;
      case 4:
        v5 = 3;
        goto LABEL_37;
      case 5:
        v5 = 4;
        goto LABEL_37;
    }
    if ( *(_DWORD *)(a2 + 56) != 6 )
    {
      v7 = -1073741823;
      AslLogCallPrintf(1, "AslFileMappingGetFileKindDetail", 1510, "Unhandled ASL_FILE_KIND: %d", *(_DWORD *)(a2 + 56));
      goto LABEL_38;
    }
    ImageType = AslFileMappingGetImageTypeEx(
                  (unsigned int)&v13,
                  (unsigned int)&v12,
                  (unsigned int)&v14,
                  (unsigned int)&v15,
                  a2);
    v7 = ImageType;
    if ( ImageType >= 0 )
    {
      if ( v14 )
      {
        if ( v12 == 523 )
        {
          v5 = 15;
        }
        else if ( (v15 & 0x20002) == 0x20002 )
        {
          v5 = 14;
        }
        else
        {
          v5 = 13 - ((v15 & 0x20003) != 1);
        }
      }
      else if ( v12 == 523 )
      {
        if ( v13 == 512 )
        {
          v5 = 11;
        }
        else if ( v13 == 34404 )
        {
          v5 = 9;
        }
        else
        {
          v5 = 10;
          if ( v13 != 43620 )
            v5 = 8;
        }
      }
      else if ( v13 == 332 )
      {
        v5 = 6;
      }
      else if ( v13 == 448 || v13 == 452 )
      {
        v5 = 7;
      }
      else
      {
        v5 = 5;
      }
      goto LABEL_37;
    }
    v8 = "AslFileMappingGetImageTypeEx failed [%x]";
    v9 = 1520;
  }
  else
  {
    v8 = "AslFileMappingEnsure failed [%x]";
    v9 = 1475;
  }
  LODWORD(v11) = ImageType;
  AslLogCallPrintf(1, "AslFileMappingGetFileKindDetail", v9, v8, v11);
LABEL_38:
  if ( a1 )
    *a1 = v5;
  return v7;
}

```

## disassembly

```asm
0x14000bf5c  push    rbp
0x14000bf5e  push    rbx
0x14000bf5f  push    rsi
0x14000bf60  push    rdi
0x14000bf61  push    r14
0x14000bf63  mov     rbp, rsp
0x14000bf66  sub     rsp, 30h
0x14000bf6a  xor     eax, eax
0x14000bf6c  mov     rsi, rdx
0x14000bf6f  cmp     dword ptr [rdx+38h], 1
0x14000bf73  mov     r14, rcx
0x14000bf76  mov     [rbp+arg_8], ax
0x14000bf7a  mov     [rbp+arg_0], ax
0x14000bf7e  mov     [rbp+arg_18], eax
0x14000bf81  mov     [rbp+arg_10], eax
0x14000bf84  jnz     short loc_14000BF8E
0x14000bf86  lea     ebx, [rax+1]
0x14000bf89  jmp     loc_14000C0F3
0x14000bf8e  mov     rcx, rsi
0x14000bf91  xor     ebx, ebx
0x14000bf93  call    AslFileMappingEnsure
0x14000bf98  mov     edi, eax
0x14000bf9a  test    eax, eax
0x14000bf9c  jns     short loc_14000BFC5
0x14000bf9e  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14000bfa5  mov     r8d, 5C3h
0x14000bfab  mov     dword ptr [rsp+30h+var_10], eax
0x14000bfaf  lea     rdx, aAslfilemapping_6; "AslFileMappingGetFileKindDetail"
0x14000bfb6  mov     ecx, 1
0x14000bfbb  call    AslLogCallPrintf
0x14000bfc0  jmp     loc_14000C0F5
0x14000bfc5  mov     edx, [rsi+38h]
0x14000bfc8  mov     ecx, edx
0x14000bfca  sub     ecx, 3
0x14000bfcd  jz      loc_14000C0EE
0x14000bfd3  sub     ecx, 1
0x14000bfd6  jz      loc_14000C0E7
0x14000bfdc  sub     ecx, 1
0x14000bfdf  jz      loc_14000C0E0
0x14000bfe5  cmp     ecx, 1
0x14000bfe8  jz      short loc_14000C002
0x14000bfea  mov     edi, 0C0000001h
0x14000bfef  mov     dword ptr [rsp+30h+var_10], edx
0x14000bff3  lea     r9, aUnhandledAslFi; "Unhandled ASL_FILE_KIND: %d"
0x14000bffa  mov     r8d, 5E6h
0x14000c000  jmp     short loc_14000BFAF
0x14000c002  lea     r9, [rbp+arg_18]
0x14000c006  mov     [rsp+30h+var_10], rsi
0x14000c00b  lea     r8, [rbp+arg_10]
0x14000c00f  lea     rdx, [rbp+arg_0]
0x14000c013  lea     rcx, [rbp+arg_8]
0x14000c017  call    AslFileMappingGetImageTypeEx
0x14000c01c  mov     edi, eax
0x14000c01e  test    eax, eax
0x14000c020  jns     short loc_14000C034
0x14000c022  lea     r9, aAslfilemapping_0; "AslFileMappingGetImageTypeEx failed [%x"...
0x14000c029  mov     r8d, 5F0h
0x14000c02f  jmp     loc_14000BFAB
0x14000c034  mov     eax, 20Bh
0x14000c039  cmp     [rbp+arg_10], ebx
0x14000c03c  jz      short loc_14000C079
0x14000c03e  cmp     [rbp+arg_0], ax
0x14000c042  jnz     short loc_14000C04E
0x14000c044  mov     ebx, 0Fh
0x14000c049  jmp     loc_14000C0F3
0x14000c04e  mov     ecx, [rbp+arg_18]
0x14000c051  mov     edx, 20002h
0x14000c056  mov     eax, ecx
0x14000c058  and     eax, edx
0x14000c05a  cmp     eax, edx
0x14000c05c  jnz     short loc_14000C068
0x14000c05e  mov     ebx, 0Eh
0x14000c063  jmp     loc_14000C0F3
0x14000c068  and     ecx, 20003h
0x14000c06e  dec     ecx
0x14000c070  neg     ecx
0x14000c072  sbb     ebx, ebx
0x14000c074  add     ebx, 0Dh
0x14000c077  jmp     short loc_14000C0F3
0x14000c079  cmp     [rbp+arg_0], ax
0x14000c07d  jnz     short loc_14000C0B1
0x14000c07f  movzx   eax, [rbp+arg_8]
0x14000c083  cmp     eax, 200h
0x14000c088  jz      short loc_14000C0AA
0x14000c08a  cmp     eax, 8664h
0x14000c08f  jz      short loc_14000C0A3
0x14000c091  mov     ebx, 0Ah
0x14000c096  cmp     eax, 0AA64h
0x14000c09b  lea     ecx, [rbx-2]
0x14000c09e  cmovnz  ebx, ecx
0x14000c0a1  jmp     short loc_14000C0F3
0x14000c0a3  mov     ebx, 9
0x14000c0a8  jmp     short loc_14000C0F3
0x14000c0aa  mov     ebx, 0Bh
0x14000c0af  jmp     short loc_14000C0F3
0x14000c0b1  movzx   ecx, [rbp+arg_8]
0x14000c0b5  sub     ecx, 14Ch
0x14000c0bb  jz      short loc_14000C0D9
0x14000c0bd  sub     ecx, 74h ; 't'
0x14000c0c0  jz      short loc_14000C0D2
0x14000c0c2  mov     ebx, 4
0x14000c0c7  cmp     ecx, ebx
0x14000c0c9  jz      short loc_14000C0D2
0x14000c0cb  mov     ebx, 5
0x14000c0d0  jmp     short loc_14000C0F3
0x14000c0d2  mov     ebx, 7
0x14000c0d7  jmp     short loc_14000C0F3
0x14000c0d9  mov     ebx, 6
0x14000c0de  jmp     short loc_14000C0F3
0x14000c0e0  mov     ebx, 4
0x14000c0e5  jmp     short loc_14000C0F3
0x14000c0e7  mov     ebx, 3
0x14000c0ec  jmp     short loc_14000C0F3
0x14000c0ee  mov     ebx, 2
0x14000c0f3  xor     edi, edi
0x14000c0f5  test    r14, r14
0x14000c0f8  jz      short loc_14000C0FD
0x14000c0fa  mov     [r14], ebx
0x14000c0fd  mov     eax, edi
0x14000c0ff  add     rsp, 30h
0x14000c103  pop     r14
0x14000c105  pop     rdi
0x14000c106  pop     rsi
0x14000c107  pop     rbx
0x14000c108  pop     rbp
0x14000c109  retn
```
