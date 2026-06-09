# CWriter::ConstructFile(_SECURITY_ATTRIBUTES *)

- ea: `0x18002a458`
- end: `0x18002a4f9`
- name: `?ConstructFile@CWriter@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `161`
- prototype: `signed int __fastcall(CWriter *this, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002a3c4`

## callees

- `0x18002a458`
- `0x18002aad0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002a4c3`
- `KERNEL32!CreateFileW` at `0x18002a4c3`
- `KERNEL32!GetLastError` at `0x18002a4d6`
- `KERNEL32!GetLastError` at `0x18002a4d6`

## pseudocode

```c
signed int __fastcall CWriter::ConstructFile(CWriter *this, struct _SECURITY_ATTRIBUTES *a2)
{
  signed int result; // eax
  void *v4; // rax
  struct _SECURITY_ATTRIBUTES *p_SecurityAttributes; // r9
  HANDLE FileW; // rax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-28h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  result = CWriter::SetSecurityDescriptor(this);
  if ( result >= 0 )
  {
    v4 = (void *)*((_QWORD *)this + 8198);
    p_SecurityAttributes = 0;
    if ( v4 )
    {
      SecurityAttributes.bInheritHandle = 0;
      p_SecurityAttributes = &SecurityAttributes;
      SecurityAttributes.nLength = 24;
      SecurityAttributes.lpSecurityDescriptor = v4;
    }
    FileW = CreateFileW(*(LPCWSTR *)this, 0x40000000u, 0, p_SecurityAttributes, 2u, 0x80u, 0);
    *((_QWORD *)this + 8199) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      *((_DWORD *)this + 2) = 1;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a458  push    rbx
0x18002a45a  sub     rsp, 60h
0x18002a45e  xorps   xmm0, xmm0
0x18002a461  xor     eax, eax
0x18002a463  movups  xmmword ptr [rsp+68h+SecurityAttributes.nLength], xmm0
0x18002a468  mov     qword ptr [rsp+68h+SecurityAttributes.bInheritHandle], rax
0x18002a46d  mov     rbx, rcx
0x18002a470  call    ?SetSecurityDescriptor@CWriter@@AEAAJXZ; CWriter::SetSecurityDescriptor(void)
0x18002a475  test    eax, eax
0x18002a477  js      short loc_18002A4F3
0x18002a479  mov     rax, [rbx+10030h]
0x18002a480  xor     r9d, r9d
0x18002a483  test    rax, rax
0x18002a486  jz      short loc_18002A49F
0x18002a488  mov     [rsp+68h+SecurityAttributes.bInheritHandle], r9d
0x18002a48d  lea     r9, [rsp+68h+SecurityAttributes]; lpSecurityAttributes
0x18002a492  mov     [rsp+68h+SecurityAttributes.nLength], 18h
0x18002a49a  mov     [rsp+68h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002a49f  mov     rcx, [rbx]; lpFileName
0x18002a4a2  xor     r8d, r8d; dwShareMode
0x18002a4a5  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18002a4ae  mov     edx, 40000000h; dwDesiredAccess
0x18002a4b3  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002a4bb  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18002a4c3  call    cs:__imp_CreateFileW
0x18002a4c9  mov     [rbx+10038h], rax
0x18002a4d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a4d4  jnz     short loc_18002A4EA
0x18002a4d6  call    cs:__imp_GetLastError
0x18002a4dc  test    eax, eax
0x18002a4de  jle     short loc_18002A4F3
0x18002a4e0  movzx   eax, ax
0x18002a4e3  or      eax, 80070000h
0x18002a4e8  jmp     short loc_18002A4F3
0x18002a4ea  mov     dword ptr [rbx+8], 1
0x18002a4f1  xor     eax, eax
0x18002a4f3  add     rsp, 60h
0x18002a4f7  pop     rbx
0x18002a4f8  retn
```
