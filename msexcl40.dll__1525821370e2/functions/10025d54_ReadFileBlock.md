# ReadFileBlock

- ea: `0x10025d54`
- end: `0x10025def`
- name: `ReadFileBlock`
- size: `155`
- prototype: `int __thiscall(void *this)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000dcc0`
- `0x1000dd90`
- `0x1000df70`
- `0x10025ed1`
- `0x10025f86`
- `0x10026233`
- `0x100264c2`

## callees

- `0x10025d54`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x10025d80`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x10025d80`

## pseudocode

```c
int __thiscall ReadFileBlock(void *this)
{
  bool v2; // zf
  BOOL v3; // eax
  DWORD v4; // esi
  int v5; // edx
  int v6; // eax
  DWORD v7; // ecx
  int v8; // eax
  DWORD v10; // [esp+Ch] [ebp-8h] BYREF
  DWORD NumberOfBytesRead; // [esp+10h] [ebp-4h] BYREF

  v2 = *((_DWORD *)this + 3) == 0;
  *((_DWORD *)this + 21) = *((_DWORD *)this + 20);
  if ( v2 )
  {
    v3 = ReadFile(*((HANDLE *)this + 5), *((LPVOID *)this + 1), *((_DWORD *)this + 16), &NumberOfBytesRead, 0);
    v4 = NumberOfBytesRead;
    if ( !v3 )
      v4 = 0xFFFF;
  }
  else
  {
    if ( (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD, DWORD *))(**((_DWORD **)this + 8) + 12))(
           *(_DWORD *)(**((_DWORD **)this + 8) + 12),
           *((_DWORD *)this + 8),
           *((_DWORD *)this + 1),
           *((_DWORD *)this + 16),
           &v10) )
    {
      return -5;
    }
    v4 = v10;
  }
  if ( v4 == 0xFFFF )
    return -5;
  v5 = *((_DWORD *)this + 20);
  v6 = v5 + *((_DWORD *)this + 16);
  v7 = *((_DWORD *)this + 22) - v5;
  *((_DWORD *)this + 19) = 1;
  if ( v6 <= *((_DWORD *)this + 22) )
    v7 = v4;
  *(_DWORD *)this = v7;
  *((_DWORD *)this + 20) = v7 + v5;
  v8 = *((_DWORD *)this + 1);
  *((_DWORD *)this + 2) = v8;
  *((_DWORD *)this + 17) = v8;
  return 0;
}

```

## disassembly

```asm
0x10025d54  mov     edi, edi
0x10025d56  push    ebp
0x10025d57  mov     ebp, esp
0x10025d59  push    ecx
0x10025d5a  push    ecx
0x10025d5b  push    ebx
0x10025d5c  push    esi
0x10025d5d  push    edi
0x10025d5e  mov     edi, ecx
0x10025d60  mov     ebx, 0FFFFh
0x10025d65  cmp     dword ptr [edi+0Ch], 0
0x10025d69  mov     eax, [edi+50h]
0x10025d6c  mov     [edi+54h], eax
0x10025d6f  jnz     short loc_10025D90
0x10025d71  push    0; lpOverlapped
0x10025d73  lea     eax, [ebp+NumberOfBytesRead]
0x10025d76  push    eax; lpNumberOfBytesRead
0x10025d77  push    dword ptr [edi+40h]; nNumberOfBytesToRead
0x10025d7a  push    dword ptr [edi+4]; lpBuffer
0x10025d7d  push    dword ptr [edi+14h]; hFile
0x10025d80  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x10025d86  mov     esi, [ebp+NumberOfBytesRead]
0x10025d89  test    eax, eax
0x10025d8b  cmovz   esi, ebx
0x10025d8e  jmp     short loc_10025DB4
0x10025d90  mov     eax, [edi+20h]
0x10025d93  lea     ecx, [ebp+var_8]
0x10025d96  push    ecx
0x10025d97  push    dword ptr [edi+40h]
0x10025d9a  mov     esi, [eax]
0x10025d9c  push    dword ptr [edi+4]
0x10025d9f  push    eax
0x10025da0  mov     esi, [esi+0Ch]
0x10025da3  mov     ecx, esi
0x10025da5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025dab  call    esi
0x10025dad  test    eax, eax
0x10025daf  jnz     short loc_10025DE7
0x10025db1  mov     esi, [ebp+var_8]
0x10025db4  cmp     esi, ebx
0x10025db6  jz      short loc_10025DE7
0x10025db8  mov     edx, [edi+50h]
0x10025dbb  mov     eax, [edi+40h]
0x10025dbe  mov     ecx, [edi+58h]
0x10025dc1  add     eax, edx
0x10025dc3  sub     ecx, edx
0x10025dc5  mov     dword ptr [edi+4Ch], 1
0x10025dcc  cmp     eax, [edi+58h]
0x10025dcf  cmovle  ecx, esi
0x10025dd2  mov     [edi], ecx
0x10025dd4  lea     eax, [ecx+edx]
0x10025dd7  mov     [edi+50h], eax
0x10025dda  mov     eax, [edi+4]
0x10025ddd  mov     [edi+8], eax
0x10025de0  mov     [edi+44h], eax
0x10025de3  xor     eax, eax
0x10025de5  jmp     short loc_10025DEA
0x10025de7  push    0FFFFFFFBh
0x10025de9  pop     eax
0x10025dea  pop     edi
0x10025deb  pop     esi
0x10025dec  pop     ebx
0x10025ded  leave
0x10025dee  retn
```
