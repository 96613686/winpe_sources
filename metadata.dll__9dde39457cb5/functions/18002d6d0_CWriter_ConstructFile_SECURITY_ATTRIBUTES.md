# CWriter::ConstructFile(_SECURITY_ATTRIBUTES *)

- ea: `0x18002d6d0`
- end: `0x18002d781`
- name: `?ConstructFile@CWriter@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `177`
- prototype: `int(CWriter *__hidden this, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002d4fc`

## callees

- `0x18002d6d0`
- `0x18002df14`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002d746`
- `KERNEL32!CreateFileW` at `0x18002d746`
- `KERNEL32!GetLastError` at `0x18002d759`
- `KERNEL32!GetLastError` at `0x18002d759`

## pseudocode

```c
int __fastcall CWriter::ConstructFile(CWriter *this, struct _SECURITY_ATTRIBUTES *a2)
{
  struct _SECURITY_ATTRIBUTES *v2; // rdi
  int result; // eax
  __int64 v5; // rax
  HANDLE FileW; // rax
  __int128 v7; // [rsp+40h] [rbp-28h] BYREF
  __int64 v8; // [rsp+50h] [rbp-18h]

  v8 = 0;
  v2 = a2;
  v7 = 0;
  if ( !a2 )
  {
    result = CWriter::SetSecurityDescriptor(this);
    if ( result < 0 )
      return result;
    v5 = *((_QWORD *)this + 8198);
    if ( v5 )
    {
      LODWORD(v8) = 0;
      v2 = (struct _SECURITY_ATTRIBUTES *)&v7;
      LODWORD(v7) = 24;
      *((_QWORD *)&v7 + 1) = v5;
    }
  }
  FileW = CreateFileW(*(LPCWSTR *)this, 0x40000000u, 0, v2, 2u, 0x80u, 0);
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
  return result;
}

```

## disassembly

```asm
0x18002d6d0  mov     [rsp+arg_0], rbx
0x18002d6d5  push    rdi
0x18002d6d6  sub     rsp, 60h
0x18002d6da  xor     eax, eax
0x18002d6dc  xorps   xmm0, xmm0
0x18002d6df  mov     [rsp+68h+var_18], rax
0x18002d6e4  mov     rdi, rdx
0x18002d6e7  mov     rbx, rcx
0x18002d6ea  movups  [rsp+68h+var_28], xmm0
0x18002d6ef  test    rdx, rdx
0x18002d6f2  jnz     short loc_18002D71F
0x18002d6f4  call    ?SetSecurityDescriptor@CWriter@@AEAAJXZ; CWriter::SetSecurityDescriptor(void)
0x18002d6f9  test    eax, eax
0x18002d6fb  js      short loc_18002D776
0x18002d6fd  mov     rax, [rbx+10030h]
0x18002d704  test    rax, rax
0x18002d707  jz      short loc_18002D71F
0x18002d709  mov     dword ptr [rsp+68h+var_18], edi
0x18002d70d  lea     rdi, [rsp+68h+var_28]
0x18002d712  mov     dword ptr [rsp+68h+var_28], 18h
0x18002d71a  mov     qword ptr [rsp+68h+var_28+8], rax
0x18002d71f  mov     rcx, [rbx]; lpFileName
0x18002d722  mov     r9, rdi; lpSecurityAttributes
0x18002d725  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18002d72e  xor     r8d, r8d; dwShareMode
0x18002d731  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002d739  mov     edx, 40000000h; dwDesiredAccess
0x18002d73e  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18002d746  call    cs:__imp_CreateFileW
0x18002d74c  mov     [rbx+10038h], rax
0x18002d753  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d757  jnz     short loc_18002D76D
0x18002d759  call    cs:__imp_GetLastError
0x18002d75f  test    eax, eax
0x18002d761  jle     short loc_18002D776
0x18002d763  movzx   eax, ax
0x18002d766  or      eax, 80070000h
0x18002d76b  jmp     short loc_18002D776
0x18002d76d  mov     dword ptr [rbx+8], 1
0x18002d774  xor     eax, eax
0x18002d776  mov     rbx, [rsp+68h+arg_0]
0x18002d77b  add     rsp, 60h
0x18002d77f  pop     rdi
0x18002d780  retn
```
