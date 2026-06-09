# TextOpenDirectory(x,x)

- ea: `0x1001fbb0`
- end: `0x1001fcc3`
- name: `_TextOpenDirectory@8`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10011d90`

## callees

- `0x1000ad60`
- `0x1000b070`
- `0x1000b600`
- `0x1001fbb0`
- `0x1002b81a`
- `0x1002c490`

## pseudocode

```c
int __stdcall TextOpenDirectory(int a1, _DWORD *a2)
{
  _WORD *v2; // eax
  _WORD *v3; // ebx
  int result; // eax
  int v5; // edx
  _WORD *v6; // ecx
  __int16 v7; // ax
  int v8; // edx
  wchar_t *v9; // ecx
  wchar_t v10; // ax
  wchar_t pszDest[262]; // [esp+8h] [ebp-210h] BYREF

  *a2 = 0;
  v2 = (_WORD *)MemAllocate(0x210u);
  v3 = v2;
  if ( !v2 )
    return -1011;
  memset(v2, 0, 0x210u);
  v5 = 261;
  v6 = v3;
  while ( v5 != -2147483385 )
  {
    v7 = *(_WORD *)((char *)v6 + a1 - (_DWORD)v3);
    if ( !v7 )
      break;
    *v6++ = v7;
    if ( !--v5 )
    {
      --v6;
      break;
    }
  }
  v8 = 261;
  *v6 = 0;
  v9 = pszDest;
  while ( v8 != -2147483385 )
  {
    v10 = *(wchar_t *)((char *)v9 + a1 - (_DWORD)pszDest);
    if ( !v10 )
      break;
    *v9++ = v10;
    if ( !--v8 )
    {
      --v9;
      break;
    }
  }
  *v9 = 0;
  StringCchCatW(pszDest, 0x105u, L"SCHEMA.INI");
  *((_DWORD *)v3 + 131) = DOSFileExists(pszDest) == 0;
  result = 0;
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x1001fbb0  sub     esp, 210h
0x1001fbb6  mov     eax, ___security_cookie
0x1001fbbb  xor     eax, esp
0x1001fbbd  mov     [esp+210h+var_4], eax
0x1001fbc4  push    ebx
0x1001fbc5  push    ebp
0x1001fbc6  mov     ebp, [esp+218h+arg_4]
0x1001fbcd  push    210h; Size
0x1001fbd2  mov     dword ptr [ebp+0], 0
0x1001fbd9  call    _MemAllocate@4; MemAllocate(x)
0x1001fbde  mov     ebx, eax
0x1001fbe0  test    ebx, ebx
0x1001fbe2  jnz     short loc_1001FBEE
0x1001fbe4  mov     eax, 0FFFFFC0Dh
0x1001fbe9  jmp     loc_1001FCAA
0x1001fbee  push    esi
0x1001fbef  push    edi
0x1001fbf0  push    210h; Size
0x1001fbf5  push    0; Val
0x1001fbf7  push    ebx; void *
0x1001fbf8  call    _memset
0x1001fbfd  mov     edi, [esp+22Ch+arg_0]
0x1001fc04  add     esp, 0Ch
0x1001fc07  mov     esi, edi
0x1001fc09  mov     edx, 105h
0x1001fc0e  mov     ecx, ebx
0x1001fc10  sub     esi, ebx
0x1001fc12  lea     eax, [edx+7FFFFEF9h]
0x1001fc18  test    eax, eax
0x1001fc1a  jz      short loc_1001FC30
0x1001fc1c  movzx   eax, word ptr [esi+ecx]
0x1001fc20  test    ax, ax
0x1001fc23  jz      short loc_1001FC30
0x1001fc25  mov     [ecx], ax
0x1001fc28  add     ecx, 2
0x1001fc2b  dec     edx
0x1001fc2c  jnz     short loc_1001FC12
0x1001fc2e  jmp     short loc_1001FC34
0x1001fc30  test    edx, edx
0x1001fc32  jnz     short loc_1001FC37
0x1001fc34  sub     ecx, 2
0x1001fc37  xor     eax, eax
0x1001fc39  mov     edx, 105h
0x1001fc3e  mov     [ecx], ax
0x1001fc41  lea     ecx, [esp+220h+pszDest]
0x1001fc45  mov     eax, ecx
0x1001fc47  sub     edi, eax
0x1001fc49  lea     esp, [esp+0]
0x1001fc50  lea     eax, [edx+7FFFFEF9h]
0x1001fc56  test    eax, eax
0x1001fc58  jz      short loc_1001FC6E
0x1001fc5a  movzx   eax, word ptr [edi+ecx]
0x1001fc5e  test    ax, ax
0x1001fc61  jz      short loc_1001FC6E
0x1001fc63  mov     [ecx], ax
0x1001fc66  add     ecx, 2
0x1001fc69  dec     edx
0x1001fc6a  jnz     short loc_1001FC50
0x1001fc6c  jmp     short loc_1001FC72
0x1001fc6e  test    edx, edx
0x1001fc70  jnz     short loc_1001FC75
0x1001fc72  sub     ecx, 2
0x1001fc75  xor     eax, eax
0x1001fc77  push    offset aSchemaIni; "SCHEMA.INI"
0x1001fc7c  mov     [ecx], ax
0x1001fc7f  lea     eax, [esp+224h+pszDest]
0x1001fc83  push    105h; cchDest
0x1001fc88  push    eax; pszDest
0x1001fc89  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1001fc8e  lea     eax, [esp+220h+pszDest]
0x1001fc92  push    eax; lpFileName
0x1001fc93  call    _DOSFileExists@4; DOSFileExists(x)
0x1001fc98  neg     eax
0x1001fc9a  pop     edi
0x1001fc9b  sbb     eax, eax
0x1001fc9d  inc     eax
0x1001fc9e  mov     [ebx+20Ch], eax
0x1001fca4  xor     eax, eax
0x1001fca6  mov     [ebp+0], ebx
0x1001fca9  pop     esi
0x1001fcaa  mov     ecx, [esp+218h+var_4]
0x1001fcb1  pop     ebp
0x1001fcb2  pop     ebx
0x1001fcb3  xor     ecx, esp; StackCookie
0x1001fcb5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001fcba  add     esp, 210h
0x1001fcc0  retn    8
```
