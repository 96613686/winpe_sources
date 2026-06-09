# sub_1400FCAA0

- ea: `0x1400fcaa0`
- end: `0x1400fcb58`
- name: `sub_1400FCAA0`
- size: `184`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140292ff0`

## callees

- `0x14004cf20`
- `0x14004ec70`
- `0x14004f334`
- `0x14005d9e0`
- `0x140060b60`
- `0x1400aabd0`
- `0x1400fcaa0`
- `0x14011fa70`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140171421`
- `KERNEL32!CreateFileW` at `0x140171421`
- `KERNEL32!GetFileAttributesW` at `0x1400fcb15`
- `KERNEL32!GetFileAttributesW` at `0x1400fcb15`

## string_xrefs

- `0x1400fcad8`: `PathHasAccess`

## pseudocode

```c
__int64 __fastcall sub_1400FCAA0(char *lpFileName)
{
  _QWORD *v2; // rdi
  unsigned __int64 v3; // rax
  DWORD v5; // edx
  DWORD dwFlagsAndAttributes; // ecx
  HANDLE FileW; // rax
  _BYTE v8[32]; // [rsp+0h] [rbp-C8h] BYREF
  _QWORD v9[4]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v10[64]; // [rsp+60h] [rbp-68h] BYREF
  __int64 v11; // [rsp+A0h] [rbp-28h]

  memset(v10, 0, sizeof(v10));
  sub_14004CF20(v9, "PathHasAccess", "..\\..\\base\\files\\file_util_win.cc", 743);
  LODWORD(v2) = 0;
  sub_1400AABD0(v10, v9, 0);
  if ( lpFileName[23] < 0 )
    lpFileName = *(char **)lpFileName;
  LODWORD(v3) = GetFileAttributesW((LPCWSTR)lpFileName);
  if ( (_DWORD)v3 != -1 )
    goto LABEL_6;
  while ( 1 )
  {
    sub_14005D9E0(v10);
    v3 = (unsigned __int64)v8 ^ v11;
    if ( _security_cookie == ((unsigned __int64)v8 ^ v11) )
      break;
LABEL_6:
    v5 = 2;
    if ( (v3 & 0x10) == 0 )
      v5 = 0x40000000;
    dwFlagsAndAttributes = 0x2000000;
    if ( (v3 & 0x10) == 0 )
      dwFlagsAndAttributes = 128;
    v2 = v9;
    v9[0] = 0;
    FileW = CreateFileW((LPCWSTR)lpFileName, v5, 7u, 0, 3u, dwFlagsAndAttributes, 0);
    v9[0] = 0;
    sub_14004F334(v9, FileW);
    LOBYTE(v2) = v9[0] != 0 && LODWORD(v9[0]) < 0xFFFFFFF4;
    if ( (_BYTE)v2 == 1 )
    {
      sub_14004EC70();
      sub_140060B60(v9[0]);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400fcaa0  push    r14
0x1400fcaa2  push    rsi
0x1400fcaa3  push    rdi
0x1400fcaa4  push    rbx
0x1400fcaa5  sub     rsp, 0A8h
0x1400fcaac  mov     rsi, rcx
0x1400fcaaf  mov     rax, cs:__security_cookie
0x1400fcab6  xor     rax, rsp
0x1400fcab9  mov     [rsp+0C8h+var_28], rax
0x1400fcac1  xorps   xmm0, xmm0
0x1400fcac4  lea     rbx, [rsp+0C8h+var_68]
0x1400fcac9  movaps  xmmword ptr [rbx+30h], xmm0
0x1400fcacd  movaps  xmmword ptr [rbx+20h], xmm0
0x1400fcad1  movaps  xmmword ptr [rbx+10h], xmm0
0x1400fcad5  movaps  xmmword ptr [rbx], xmm0
0x1400fcad8  lea     rdx, aPathhasaccess; "PathHasAccess"
0x1400fcadf  lea     r8, aBaseFilesFileU; "..\\..\\base\\files\\file_util_win.cc"
0x1400fcae6  lea     r14, [rsp+0C8h+var_88]
0x1400fcaeb  mov     rcx, r14
0x1400fcaee  mov     r9d, 2E7h
0x1400fcaf4  call    sub_14004CF20
0x1400fcaf9  xor     edi, edi
0x1400fcafb  mov     rcx, rbx
0x1400fcafe  mov     rdx, r14
0x1400fcb01  xor     r8d, r8d
0x1400fcb04  call    sub_1400AABD0
0x1400fcb09  cmp     byte ptr [rsi+17h], 0
0x1400fcb0d  jns     short loc_1400FCB12
0x1400fcb0f  mov     rsi, [rsi]
0x1400fcb12  mov     rcx, rsi; lpFileName
0x1400fcb15  call    cs:GetFileAttributesW
0x1400fcb1b  cmp     eax, 0FFFFFFFFh
0x1400fcb1e  jnz     loc_1401713DE
0x1400fcb24  lea     rcx, [rsp+0C8h+var_68]
0x1400fcb29  call    sub_14005D9E0
0x1400fcb2e  mov     rax, [rsp+0C8h+var_28]
0x1400fcb36  xor     rax, rsp
0x1400fcb39  mov     rcx, cs:__security_cookie
0x1400fcb40  cmp     rcx, rax
0x1400fcb43  jnz     loc_1401713CE
0x1400fcb49  mov     eax, edi
0x1400fcb4b  add     rsp, 0A8h
0x1400fcb52  pop     rbx
0x1400fcb53  pop     rdi
0x1400fcb54  pop     rsi
0x1400fcb55  pop     r14
0x1400fcb57  retn
0x1401713ce  mov     rcx, [rsp+0C8h+var_28]
0x1401713d6  xor     rcx, rsp; StackCookie
0x1401713d9  call    __security_check_cookie
0x1401713de  test    al, 10h
0x1401713e0  mov     eax, 40000000h
0x1401713e5  mov     edx, 2
0x1401713ea  cmovz   edx, eax; dwDesiredAccess
0x1401713ed  mov     eax, 80h
0x1401713f2  mov     ecx, 2000000h
0x1401713f7  cmovz   ecx, eax
0x1401713fa  xor     ebx, ebx
0x1401713fc  lea     rdi, [rsp+0C8h+var_88]
0x140171401  mov     [rdi], rbx
0x140171404  mov     [rsp+0C8h+hTemplateFile], rbx; hTemplateFile
0x140171409  mov     [rsp+0C8h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x14017140d  mov     [rsp+0C8h+dwCreationDisposition], 3; dwCreationDisposition
0x140171415  mov     rcx, rsi; lpFileName
0x140171418  mov     r8d, 7; dwShareMode
0x14017141e  xor     r9d, r9d; lpSecurityAttributes
0x140171421  call    cs:CreateFileW
0x140171427  mov     [rdi], rbx
0x14017142a  mov     rcx, rdi
0x14017142d  mov     rdx, rax
0x140171430  call    sub_14004F334
0x140171435  mov     rax, [rdi]
0x140171438  test    rax, rax
0x14017143b  setnz   cl
0x14017143e  cmp     eax, 0FFFFFFF4h
0x140171441  setb    dil
0x140171445  and     dil, cl
0x140171448  cmp     dil, 1
0x14017144c  jnz     loc_1400FCB24
0x140171452  call    sub_14004EC70
0x140171457  mov     rcx, [rsp+0C8h+var_88]
0x14017145c  call    sub_140060B60
0x140171461  jmp     loc_1400FCB24
```
