# System::DeleteFileByName(ushort const *,Err &)

- ea: `0x1004f7b0`
- end: `0x1004f859`
- name: `?DeleteFileByName@System@@QAEXPBGAAVErr@@@Z`
- size: `169`
- prototype: `void __thiscall(const unsigned __int16 *, LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1001fe30`
- `0x1002e4e0`
- `0x10044340`

## callees

- `0x1004eda0`
- `0x1004f7b0`
- `0x1005d6b4`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1004f834`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1004f834`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1004f7d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1004f7d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1004f809`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1004f809`

## pseudocode

```c
void __thiscall System::DeleteFileByName(const unsigned __int16 *this, LPCWSTR lpFileName, int a3)
{
  struct Err *v3; // ecx
  BOOL v4; // esi
  BOOL v5; // eax
  int v6; // [esp+8h] [ebp-218h] BYREF
  LPCSTR v7; // [esp+Ch] [ebp-214h]
  char v8; // [esp+10h] [ebp-210h] BYREF

  if ( wrap )
  {
    v4 = DeleteFileW(lpFileName);
  }
  else
  {
    v6 = 0;
    v7 = 0;
    CStrIn::Init((CStrIn *)&v6, lpFileName, -1);
    v5 = DeleteFileA(v7);
    v3 = (struct Err *)v7;
    v4 = v5;
    if ( v7 != &v8 && (unsigned int)v7 >> 16 && v6 != -1 )
      _free((void *)v7);
  }
  if ( !v4 )
    System::ErrGetLastError(v3);
}

```

## disassembly

```asm
0x1004f7b0  mov     edi, edi
0x1004f7b2  push    ebp
0x1004f7b3  mov     ebp, esp
0x1004f7b5  sub     esp, 218h
0x1004f7bb  mov     eax, ___security_cookie
0x1004f7c0  xor     eax, ebp
0x1004f7c2  mov     [ebp+var_4], eax
0x1004f7c5  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1004f7cc  mov     eax, [ebp+lpFileName]
0x1004f7cf  push    esi
0x1004f7d0  push    edi
0x1004f7d1  mov     edi, [ebp+arg_4]
0x1004f7d4  jz      short loc_1004F7E1
0x1004f7d6  push    eax; lpFileName
0x1004f7d7  call    ds:__imp__DeleteFileW@4; DeleteFileW(x)
0x1004f7dd  mov     esi, eax
0x1004f7df  jmp     short loc_1004F83D
0x1004f7e1  push    0FFFFFFFFh; int
0x1004f7e3  push    eax; lpWideCharStr
0x1004f7e4  lea     ecx, [ebp+var_218]; this
0x1004f7ea  mov     [ebp+var_218], 0
0x1004f7f4  mov     [ebp+var_214], 0
0x1004f7fe  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x1004f803  push    [ebp+var_214]; lpFileName
0x1004f809  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x1004f80f  mov     ecx, [ebp+var_214]
0x1004f815  mov     esi, eax
0x1004f817  lea     eax, [ebp+var_210]
0x1004f81d  cmp     ecx, eax
0x1004f81f  jz      short loc_1004F83D
0x1004f821  mov     eax, ecx
0x1004f823  shr     eax, 10h
0x1004f826  test    eax, eax
0x1004f828  jz      short loc_1004F83D
0x1004f82a  cmp     [ebp+var_218], 0FFFFFFFFh
0x1004f831  jz      short loc_1004F83D
0x1004f833  push    ecx; Block
0x1004f834  call    ds:__imp__free
0x1004f83a  add     esp, 4
0x1004f83d  test    esi, esi
0x1004f83f  jnz     short loc_1004F847
0x1004f841  push    edi
0x1004f842  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1004f847  mov     ecx, [ebp+var_4]
0x1004f84a  pop     edi
0x1004f84b  xor     ecx, ebp; StackCookie
0x1004f84d  pop     esi
0x1004f84e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004f853  mov     esp, ebp
0x1004f855  pop     ebp
0x1004f856  retn    8
```
