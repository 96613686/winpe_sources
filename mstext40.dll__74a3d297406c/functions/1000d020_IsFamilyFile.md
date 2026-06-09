# IsFamilyFile

- ea: `0x1000d020`
- end: `0x1000d12e`
- name: `IsFamilyFile`
- size: `270`
- prototype: `int __stdcall(wchar_t *FullPath, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1000c370`

## callees

- `0x1000bf70`
- `0x1000c2f0`
- `0x1000d020`
- `0x1002b81a`

## pseudocode

```c
int __stdcall IsFamilyFile(wchar_t *FullPath, const unsigned __int16 **a2)
{
  const unsigned __int16 *v2; // ebp
  char *v3; // eax
  char *v4; // ebx
  signed int v5; // edx
  __int16 v6; // cx
  int v7; // eax
  int v8; // edx
  const unsigned __int16 *v9; // ecx
  int v10; // ebx
  int v11; // esi
  int v12; // edi
  char *v14; // [esp+10h] [ebp-208h]
  wchar_t Ext[256]; // [esp+14h] [ebp-204h] BYREF

  SplitPath(FullPath, 0, 0, 0, 0, 0, 0, Ext, 0x100u);
  v2 = *a2;
  if ( !*a2 )
    return 0;
  while ( 1 )
  {
    v3 = (char *)DBToUpper(Ext);
    v4 = v3;
    v14 = v3;
    v5 = wcslen(v2);
    do
    {
      v6 = *(_WORD *)v3;
      v3 += 2;
    }
    while ( v6 );
    v7 = (v3 - (v4 + 2)) >> 1;
    if ( v5 < v7 )
      v7 = v5;
    v8 = 0;
    if ( v7 <= 0 )
      break;
    v9 = v2;
    v10 = v4 - (char *)v2;
    while ( 1 )
    {
      v11 = *v9;
      if ( v11 != 63 )
      {
        v12 = *(const unsigned __int16 *)((char *)v9 + v10);
        if ( v12 != 63 && (_WORD)v11 != (_WORD)v12 )
          break;
      }
      ++v8;
      ++v9;
      if ( v8 >= v7 )
        return 1;
    }
    if ( v2[v8] == *(unsigned __int16 *)&v14[2 * v8] )
      break;
    v2 = *++a2;
    if ( !*a2 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1000d020  sub     esp, 208h
0x1000d026  mov     eax, ___security_cookie
0x1000d02b  xor     eax, esp
0x1000d02d  mov     [esp+208h+var_4], eax
0x1000d034  push    ebx
0x1000d035  mov     eax, [esp+20Ch+FullPath]
0x1000d03c  lea     ecx, [esp+20Ch+Ext]
0x1000d040  push    ebp
0x1000d041  push    esi
0x1000d042  push    edi
0x1000d043  push    100h; ExtCount
0x1000d048  push    ecx; Ext
0x1000d049  push    0; FilenameCount
0x1000d04b  push    0; Filename
0x1000d04d  push    0; DirCount
0x1000d04f  push    0; Dir
0x1000d051  push    0; DriveCount
0x1000d053  push    0; Drive
0x1000d055  push    eax; FullPath
0x1000d056  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1000d05b  mov     ebp, [esp+218h+arg_4]
0x1000d062  mov     ebp, [ebp+0]
0x1000d065  test    ebp, ebp
0x1000d067  jz      loc_1000D111
0x1000d06d  lea     ecx, [ecx+0]
0x1000d070  lea     eax, [esp+218h+Ext]
0x1000d074  push    eax
0x1000d075  call    _DBToUpper@4; DBToUpper(x)
0x1000d07a  mov     edx, ebp
0x1000d07c  mov     ebx, eax
0x1000d07e  mov     [esp+218h+var_208], ebx
0x1000d082  lea     esi, [edx+2]
0x1000d085  mov     cx, [edx]
0x1000d088  add     edx, 2
0x1000d08b  test    cx, cx
0x1000d08e  jnz     short loc_1000D085
0x1000d090  mov     eax, ebx
0x1000d092  sub     edx, esi
0x1000d094  sar     edx, 1
0x1000d096  lea     esi, [eax+2]
0x1000d099  lea     esp, [esp+0]
0x1000d0a0  mov     cx, [eax]
0x1000d0a3  add     eax, 2
0x1000d0a6  test    cx, cx
0x1000d0a9  jnz     short loc_1000D0A0
0x1000d0ab  sub     eax, esi
0x1000d0ad  sar     eax, 1
0x1000d0af  cmp     edx, eax
0x1000d0b1  cmovl   eax, edx
0x1000d0b4  xor     edx, edx
0x1000d0b6  test    eax, eax
0x1000d0b8  jle     short loc_1000D0DE
0x1000d0ba  mov     ecx, ebp
0x1000d0bc  sub     ebx, ebp
0x1000d0be  mov     edi, edi
0x1000d0c0  movzx   esi, word ptr [ecx]
0x1000d0c3  cmp     esi, 3Fh ; '?'
0x1000d0c6  jz      short loc_1000D0D6
0x1000d0c8  movzx   edi, word ptr [ebx+ecx]
0x1000d0cc  cmp     edi, 3Fh ; '?'
0x1000d0cf  jz      short loc_1000D0D6
0x1000d0d1  cmp     si, di
0x1000d0d4  jnz     short loc_1000D0E5
0x1000d0d6  inc     edx
0x1000d0d7  add     ecx, 2
0x1000d0da  cmp     edx, eax
0x1000d0dc  jl      short loc_1000D0C0
0x1000d0de  mov     eax, 1
0x1000d0e3  jmp     short loc_1000D113
0x1000d0e5  mov     eax, [esp+218h+var_208]
0x1000d0e9  movzx   ecx, word ptr [ebp+edx*2+0]
0x1000d0ee  movzx   eax, word ptr [eax+edx*2]
0x1000d0f2  sub     ecx, eax
0x1000d0f4  jz      short loc_1000D0DE
0x1000d0f6  mov     eax, [esp+218h+arg_4]
0x1000d0fd  add     eax, 4
0x1000d100  mov     [esp+218h+arg_4], eax
0x1000d107  mov     ebp, [eax]
0x1000d109  test    ebp, ebp
0x1000d10b  jnz     loc_1000D070
0x1000d111  xor     eax, eax
0x1000d113  mov     ecx, [esp+218h+var_4]
0x1000d11a  pop     edi
0x1000d11b  pop     esi
0x1000d11c  pop     ebp
0x1000d11d  pop     ebx
0x1000d11e  xor     ecx, esp; StackCookie
0x1000d120  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000d125  add     esp, 208h
0x1000d12b  retn    8
```
