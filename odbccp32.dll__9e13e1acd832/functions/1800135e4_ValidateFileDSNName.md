# ValidateFileDSNName

- ea: `0x1800135e4`
- end: `0x1800136aa`
- name: `ValidateFileDSNName`
- size: `198`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012e90`

## callees

- `0x180002e14`
- `0x180004bac`
- `0x180012b14`
- `0x1800135e4`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_waccess` at `0x18001364c`
- `msvcrt!_waccess` at `0x18001364c`
- `msvcrt!_errno` at `0x180013656`
- `msvcrt!_errno` at `0x180013661`
- `msvcrt!_errno` at `0x180013656`
- `msvcrt!_errno` at `0x180013661`

## pseudocode

```c
__int64 __fastcall ValidateFileDSNName(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // rax
  unsigned int v3; // r11d
  __int64 v4; // rcx
  int *v5; // rax
  int v6; // ecx
  wchar_t pszDest[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  if ( (unsigned int)v2 >= 0x104 )
  {
    v6 = 9;
LABEL_11:
    PostInstError(v6);
    return 0xFFFF;
  }
  StringCchCopyW(pszDest, 0x104u, a2);
  if ( (unsigned __int16)EnforceDSNExtension(v4, pszDest, v3) != 0xFFFF )
  {
    if ( _waccess(pszDest, 4) != -1 )
      return 0;
    if ( *_errno() == 2 || (v5 = _errno(), v6 = 1, *v5 == 22) )
      v6 = 12;
    goto LABEL_11;
  }
  return 0xFFFF;
}

```

## disassembly

```asm
0x1800135e4  mov     [rsp+arg_0], rbx
0x1800135e9  push    rdi
0x1800135ea  sub     rsp, 240h
0x1800135f1  mov     rax, cs:__security_cookie
0x1800135f8  xor     rax, rsp
0x1800135fb  mov     [rsp+248h+var_18], rax
0x180013603  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013607  mov     rax, rbx
0x18001360a  xor     edi, edi
0x18001360c  inc     rax
0x18001360f  cmp     [rdx+rax*2], di
0x180013613  jnz     short loc_18001360C
0x180013615  mov     r11d, 104h
0x18001361b  cmp     eax, r11d
0x18001361e  jnb     short loc_18001367C
0x180013620  mov     r8, rdx; pszSrc
0x180013623  lea     rcx, [rsp+248h+pszDest]; pszDest
0x180013628  mov     edx, r11d; cchDest
0x18001362b  call    StringCchCopyW
0x180013630  mov     r8d, r11d
0x180013633  lea     rdx, [rsp+248h+pszDest]
0x180013638  call    EnforceDSNExtension
0x18001363d  cmp     ax, bx
0x180013640  jz      short loc_180013686
0x180013642  mov     edx, 4; AccessMode
0x180013647  lea     rcx, [rsp+248h+pszDest]; FileName
0x18001364c  call    cs:__imp__waccess
0x180013652  cmp     eax, ebx
0x180013654  jnz     short loc_180013678
0x180013656  call    cs:__imp__errno
0x18001365c  cmp     dword ptr [rax], 2
0x18001365f  jz      short loc_180013671
0x180013661  call    cs:__imp__errno
0x180013667  mov     ecx, 1
0x18001366c  cmp     dword ptr [rax], 16h
0x18001366f  jnz     short loc_180013681
0x180013671  mov     ecx, 0Ch
0x180013676  jmp     short loc_180013681
0x180013678  mov     eax, edi
0x18001367a  jmp     short loc_180013689
0x18001367c  mov     ecx, 9
0x180013681  call    PostInstError
0x180013686  movzx   eax, bx
0x180013689  mov     rcx, [rsp+248h+var_18]
0x180013691  xor     rcx, rsp; StackCookie
0x180013694  call    __security_check_cookie
0x180013699  mov     rbx, [rsp+248h+arg_0]
0x1800136a1  add     rsp, 240h
0x1800136a8  pop     rdi
0x1800136a9  retn
```
