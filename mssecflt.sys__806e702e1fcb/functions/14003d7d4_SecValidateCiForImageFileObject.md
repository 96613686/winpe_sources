# SecValidateCiForImageFileObject

- ea: `0x14003d7d4`
- end: `0x14003d895`
- name: `SecValidateCiForImageFileObject`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003d440`

## callees

- `0x140010128`
- `0x140011650`
- `0x14003d7d4`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14003d82f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14003d82f`
- `ntoskrnl!ZwClose` at `0x14003d86e`
- `ntoskrnl!ZwClose` at `0x14003d86e`

## pseudocode

```c
__int64 __fastcall SecValidateCiForImageFileObject(_DWORD *a1, char a2)
{
  bool v2; // zf
  NTSTATUS v4; // ebx
  __int64 v5; // rdx
  HANDLE Handle; // [rsp+40h] [rbp-18h] BYREF

  v2 = (a1[20] & 0x40000) == 0;
  Handle = 0;
  if ( v2 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v4 = ObOpenObjectByPointer(a1, 0x200u, 0, 1u, 0, 0, &Handle);
    if ( v4 >= 0 )
    {
      LOBYTE(v5) = a2;
      v4 = ZwSetCachedSigningLevel_0(5, v5, &Handle);
    }
    if ( Handle )
      ZwClose(Handle);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14003d7d4  mov     [rsp+arg_10], rbx
0x14003d7d9  push    rdi
0x14003d7da  sub     rsp, 50h
0x14003d7de  mov     rax, cs:__security_cookie
0x14003d7e5  xor     rax, rsp
0x14003d7e8  mov     [rsp+58h+var_10], rax
0x14003d7ed  test    dword ptr [rcx+50h], 40000h
0x14003d7f4  mov     dil, dl
0x14003d7f7  mov     [rsp+58h+var_18], 0
0x14003d800  jnz     short loc_14003D809
0x14003d802  mov     ebx, 0C000000Dh
0x14003d807  jmp     short loc_14003D87A
0x14003d809  lea     rax, [rsp+58h+var_18]
0x14003d80e  mov     r9d, 1; DesiredAccess
0x14003d814  mov     [rsp+58h+Handle], rax; Handle
0x14003d819  xor     r8d, r8d; PassedAccessState
0x14003d81c  mov     [rsp+58h+AccessMode], 0; AccessMode
0x14003d821  mov     edx, 200h; HandleAttributes
0x14003d826  mov     [rsp+58h+ObjectType], 0; ObjectType
0x14003d82f  call    cs:__imp_ObOpenObjectByPointer
0x14003d836  nop     dword ptr [rax+rax+00h]
0x14003d83b  mov     ebx, eax
0x14003d83d  test    eax, eax
0x14003d83f  js      short loc_14003D864
0x14003d841  mov     rax, [rsp+58h+var_18]
0x14003d846  lea     r8, [rsp+58h+var_18]
0x14003d84b  mov     r9d, 1
0x14003d851  mov     [rsp+58h+ObjectType], rax
0x14003d856  mov     dl, dil
0x14003d859  lea     ecx, [r9+4]
0x14003d85d  call    ZwSetCachedSigningLevel_0
0x14003d862  mov     ebx, eax
0x14003d864  mov     rcx, [rsp+58h+var_18]; Handle
0x14003d869  test    rcx, rcx
0x14003d86c  jz      short loc_14003D87A
0x14003d86e  call    cs:__imp_ZwClose
0x14003d875  nop     dword ptr [rax+rax+00h]
0x14003d87a  mov     eax, ebx
0x14003d87c  mov     rcx, [rsp+58h+var_10]
0x14003d881  xor     rcx, rsp; StackCookie
0x14003d884  call    __security_check_cookie
0x14003d889  mov     rbx, [rsp+58h+arg_10]
0x14003d88e  add     rsp, 50h
0x14003d892  pop     rdi
0x14003d893  retn
```
