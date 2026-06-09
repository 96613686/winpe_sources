# TextSetHTMLFilePosition

- ea: `0x10028a60`
- end: `0x10028bab`
- name: `TextSetHTMLFilePosition`
- size: `331`
- prototype: `int __stdcall(int, int, int, LONG lDistanceToMove, int)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10025cc0`
- `0x10027030`
- `0x100279a0`
- `0x10027de0`
- `0x10028640`
- `0x100287b0`

## callees

- `0x1001d6a0`
- `0x1001d770`
- `0x10028a60`
- `0x100295f0`
- `0x1002ba60`

## pseudocode

```c
unsigned int __stdcall TextSetHTMLFilePosition(int *a1, int a2, int a3, LONG lDistanceToMove, unsigned int a5)
{
  unsigned int v5; // eax
  int v6; // ebx
  unsigned int v7; // ebp
  LONG v8; // ecx
  int v9; // eax
  int v10; // esi
  unsigned int result; // eax
  size_t v12; // esi
  int v13; // ecx

  v5 = dword_10041B74;
  v6 = a3;
  v7 = 0;
  if ( a3 != 1 || dword_10041B74 )
  {
    v8 = lDistanceToMove;
  }
  else
  {
    v8 = lDistanceToMove;
    if ( a5 == -1 )
    {
      v6 = 0;
      a5 = 0;
      if ( lDistanceToMove )
        v8 = --lDistanceToMove;
    }
  }
  if ( a1[1] != v8 )
  {
    BFSetFilePosition(*a1, 0, v8);
    a1[1] = lDistanceToMove;
    v9 = BFReadFile(*a1, a1 + 17, 0x1000u, (int)&a3);
    v10 = a3;
    v7 = v9;
    if ( v9 == -14 )
    {
      dword_10041B7C = 1;
      if ( !a3 )
      {
LABEL_18:
        v5 = dword_10041B74;
        goto LABEL_19;
      }
    }
    else
    {
      if ( a3 != 4096 )
        return -5;
      dword_10041B7C = 0;
    }
    dword_10041B78 = 4096;
    a1[11] = 0;
    v7 = TextConvertToUnicode(a2, a1 + 11, (char *)a1 + 68, (size_t *)&a3, &word_10041B80, (int)&dword_10041B78, 0);
    if ( v7 )
    {
      dword_10041B7C = 1;
      v7 = -14;
    }
    v12 = v10 - a3;
    a1[12] = v12;
    if ( v12 )
      memcpy((char *)a1 - v12 + 68, (char *)a1 - v12 + 4164, v12);
    goto LABEL_18;
  }
LABEL_19:
  if ( v6 )
  {
    if ( v6 != 1 )
      goto LABEL_24;
    v5 += a5;
  }
  else
  {
    v5 = a5;
  }
  dword_10041B74 = v5;
LABEL_24:
  if ( dword_10041B78 < v5 )
    return -5;
  v13 = dword_10041B78 - v5;
  result = v7;
  dword_10041B70 = v13;
  return result;
}

```

## disassembly

```asm
0x10028a60  mov     eax, dword_10041B74
0x10028a65  push    ebx
0x10028a66  mov     ebx, [esp+4+arg_8]
0x10028a6a  push    ebp
0x10028a6b  push    esi
0x10028a6c  xor     ebp, ebp
0x10028a6e  push    edi
0x10028a6f  cmp     ebx, 1
0x10028a72  jnz     short loc_10028A94
0x10028a74  test    eax, eax
0x10028a76  jnz     short loc_10028A94
0x10028a78  cmp     [esp+10h+arg_10], 0FFFFFFFFh
0x10028a7d  mov     ecx, [esp+10h+lDistanceToMove]
0x10028a81  jnz     short loc_10028A98
0x10028a83  xor     ebx, ebx
0x10028a85  mov     [esp+10h+arg_10], ebx
0x10028a89  test    ecx, ecx
0x10028a8b  jz      short loc_10028A98
0x10028a8d  dec     ecx
0x10028a8e  mov     [esp+10h+lDistanceToMove], ecx
0x10028a92  jmp     short loc_10028A98
0x10028a94  mov     ecx, [esp+10h+lDistanceToMove]
0x10028a98  mov     edi, [esp+10h+arg_0]
0x10028a9c  cmp     [edi+4], ecx
0x10028a9f  jz      loc_10028B74
0x10028aa5  push    ecx; lDistanceToMove
0x10028aa6  push    0; int
0x10028aa8  push    dword ptr [edi]; int
0x10028aaa  call    _BFSetFilePosition@12; BFSetFilePosition(x,x,x)
0x10028aaf  mov     eax, [esp+10h+lDistanceToMove]
0x10028ab3  lea     ecx, [esp+10h+arg_8]
0x10028ab7  push    ecx; int
0x10028ab8  mov     [edi+4], eax
0x10028abb  lea     eax, [edi+44h]
0x10028abe  push    1000h; Size
0x10028ac3  push    eax; void *
0x10028ac4  push    dword ptr [edi]; int
0x10028ac6  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x10028acb  mov     esi, [esp+10h+arg_8]
0x10028acf  mov     ebp, eax
0x10028ad1  cmp     ebp, 0FFFFFFF2h
0x10028ad4  jnz     short loc_10028AEA
0x10028ad6  mov     dword_10041B7C, 1
0x10028ae0  test    esi, esi
0x10028ae2  jz      loc_10028B6F
0x10028ae8  jmp     short loc_10028B08
0x10028aea  cmp     esi, 1000h
0x10028af0  jz      short loc_10028AFE
0x10028af2  pop     edi
0x10028af3  pop     esi
0x10028af4  pop     ebp
0x10028af5  mov     eax, 0FFFFFFFBh
0x10028afa  pop     ebx
0x10028afb  retn    14h
0x10028afe  mov     dword_10041B7C, 0
0x10028b08  push    0; int
0x10028b0a  push    offset dword_10041B78; int
0x10028b0f  push    offset word_10041B80; lpWideCharStr
0x10028b14  lea     ecx, [esp+1Ch+arg_8]
0x10028b18  mov     dword_10041B78, 1000h
0x10028b22  push    ecx; int
0x10028b23  lea     ecx, [edi+44h]
0x10028b26  mov     dword ptr [edi+2Ch], 0
0x10028b2d  lea     eax, [edi+2Ch]
0x10028b30  push    ecx; Src
0x10028b31  push    eax; int
0x10028b32  push    [esp+28h+arg_4]; int
0x10028b36  call    _TextConvertToUnicode@28; TextConvertToUnicode(x,x,x,x,x,x,x)
0x10028b3b  mov     ebp, eax
0x10028b3d  test    ebp, ebp
0x10028b3f  jz      short loc_10028B50
0x10028b41  mov     dword_10041B7C, 1
0x10028b4b  mov     ebp, 0FFFFFFF2h
0x10028b50  sub     esi, [esp+10h+arg_8]
0x10028b54  mov     [edi+30h], esi
0x10028b57  jz      short loc_10028B6F
0x10028b59  sub     edi, esi
0x10028b5b  push    esi; Size
0x10028b5c  lea     eax, [edi+1044h]
0x10028b62  push    eax; Src
0x10028b63  lea     eax, [edi+44h]
0x10028b66  push    eax; void *
0x10028b67  call    _memcpy
0x10028b6c  add     esp, 0Ch
0x10028b6f  mov     eax, dword_10041B74
0x10028b74  test    ebx, ebx
0x10028b76  jnz     short loc_10028B7E
0x10028b78  mov     eax, [esp+10h+arg_10]
0x10028b7c  jmp     short loc_10028B87
0x10028b7e  cmp     ebx, 1
0x10028b81  jnz     short loc_10028B8C
0x10028b83  add     eax, [esp+10h+arg_10]
0x10028b87  mov     dword_10041B74, eax
0x10028b8c  mov     ecx, dword_10041B78
0x10028b92  cmp     ecx, eax
0x10028b94  jb      loc_10028AF2
0x10028b9a  pop     edi
0x10028b9b  sub     ecx, eax
0x10028b9d  mov     eax, ebp
0x10028b9f  pop     esi
0x10028ba0  pop     ebp
0x10028ba1  mov     dword_10041B70, ecx
0x10028ba7  pop     ebx
0x10028ba8  retn    14h
```
