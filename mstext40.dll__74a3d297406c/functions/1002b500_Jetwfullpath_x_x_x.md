# Jetwfullpath(x,x,x)

- ea: `0x1002b500`
- end: `0x1002b619`
- name: `_Jetwfullpath@12`
- size: `281`
- prototype: `int __stdcall(wchar_t *Buffer, wchar_t *Path, size_t BufferCount)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x10011d90`

## callees

- `0x1002a3b0`
- `0x1002a550`
- `0x1002a5c0`
- `0x1002b500`
- `0x1002b81a`
- `0x1002df32`
- `0x1002dffc`
- `0x1002e0f7`

## pseudocode

```c
wchar_t *__stdcall Jetwfullpath(wchar_t *Buffer, wchar_t *Path, size_t BufferCount)
{
  int v4; // [esp+8h] [ebp-430h] BYREF
  char *v5; // [esp+Ch] [ebp-42Ch]
  char v6; // [esp+10h] [ebp-428h] BYREF
  int v7; // [esp+21Ch] [ebp-21Ch]
  int v8; // [esp+220h] [ebp-218h] BYREF
  char *v9; // [esp+224h] [ebp-214h]
  char v10; // [esp+228h] [ebp-210h] BYREF

  if ( wrap )
    return _wfullpath(Buffer, Path, BufferCount);
  v8 = 0;
  v9 = 0;
  CStrIn::Init((CStrIn *)&v8, Path, -1);
  CStrOut::CStrOut((CStrOut *)&v4, Buffer, BufferCount);
  _fullpath(v5, v9, 2 * v7);
  CStrOut::ConvertIncludingNul((CStrOut *)&v4);
  CStrOut::ConvertIncludingNul((CStrOut *)&v4);
  if ( v5 != &v6 && (unsigned int)v5 >> 16 && v4 != -1 )
    free(v5);
  v5 = 0;
  if ( v9 != &v10 && (unsigned int)v9 >> 16 && v8 != -1 )
    free(v9);
  return Buffer;
}

```

## disassembly

```asm
0x1002b500  sub     esp, 430h
0x1002b506  mov     eax, ___security_cookie
0x1002b50b  xor     eax, esp
0x1002b50d  mov     [esp+430h+var_4], eax
0x1002b514  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002b51b  mov     eax, [esp+430h+Path]
0x1002b522  push    esi
0x1002b523  mov     esi, [esp+434h+Buffer]
0x1002b52a  push    edi
0x1002b52b  mov     edi, [esp+438h+BufferCount]
0x1002b532  jz      short loc_1002B544
0x1002b534  push    edi; BufferCount
0x1002b535  push    eax; Path
0x1002b536  push    esi; Buffer
0x1002b537  call    __wfullpath
0x1002b53c  add     esp, 0Ch
0x1002b53f  jmp     loc_1002B600
0x1002b544  push    0FFFFFFFFh; int
0x1002b546  push    eax; lpWideCharStr
0x1002b547  lea     ecx, [esp+440h+var_218]; this
0x1002b54e  mov     [esp+440h+var_218], 0
0x1002b559  mov     [esp+440h+var_214], 0
0x1002b564  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002b569  push    edi; int
0x1002b56a  push    esi; wchar_t *
0x1002b56b  lea     ecx, [esp+440h+var_430]; this
0x1002b56f  call    ??0CStrOut@@QAE@PA_WH@Z; CStrOut::CStrOut(wchar_t *,int)
0x1002b574  mov     eax, [esp+438h+var_21C]
0x1002b57b  add     eax, eax
0x1002b57d  push    eax; BufferCount
0x1002b57e  push    [esp+43Ch+var_214]; Path
0x1002b585  push    [esp+440h+var_42C]; Buffer
0x1002b589  call    __fullpath
0x1002b58e  add     esp, 0Ch
0x1002b591  lea     ecx, [esp+438h+var_430]; this
0x1002b595  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1002b59a  lea     ecx, [esp+438h+var_430]; this
0x1002b59e  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1002b5a3  mov     ecx, [esp+438h+var_42C]
0x1002b5a7  lea     eax, [esp+438h+var_428]
0x1002b5ab  cmp     ecx, eax
0x1002b5ad  jz      short loc_1002B5C8
0x1002b5af  mov     eax, ecx
0x1002b5b1  shr     eax, 10h
0x1002b5b4  test    eax, eax
0x1002b5b6  jz      short loc_1002B5C8
0x1002b5b8  cmp     [esp+438h+var_430], 0FFFFFFFFh
0x1002b5bd  jz      short loc_1002B5C8
0x1002b5bf  push    ecx; Block
0x1002b5c0  call    _free
0x1002b5c5  add     esp, 4
0x1002b5c8  mov     ecx, [esp+438h+var_214]
0x1002b5cf  lea     eax, [esp+438h+var_210]
0x1002b5d6  mov     [esp+438h+var_42C], 0
0x1002b5de  cmp     ecx, eax
0x1002b5e0  jz      short loc_1002B5FE
0x1002b5e2  mov     eax, ecx
0x1002b5e4  shr     eax, 10h
0x1002b5e7  test    eax, eax
0x1002b5e9  jz      short loc_1002B5FE
0x1002b5eb  cmp     [esp+438h+var_218], 0FFFFFFFFh
0x1002b5f3  jz      short loc_1002B5FE
0x1002b5f5  push    ecx; Block
0x1002b5f6  call    _free
0x1002b5fb  add     esp, 4
0x1002b5fe  mov     eax, esi
0x1002b600  mov     ecx, [esp+438h+var_4]
0x1002b607  pop     edi
0x1002b608  pop     esi
0x1002b609  xor     ecx, esp; StackCookie
0x1002b60b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002b610  add     esp, 430h
0x1002b616  retn    0Ch
```
