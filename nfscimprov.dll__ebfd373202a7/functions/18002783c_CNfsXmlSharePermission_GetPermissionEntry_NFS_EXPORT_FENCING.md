# CNfsXmlSharePermission::GetPermissionEntry(_NFS_EXPORT_FENCING * *)

- ea: `0x18002783c`
- end: `0x180027956`
- name: `?GetPermissionEntry@CNfsXmlSharePermission@@QEAAKPEAPEAU_NFS_EXPORT_FENCING@@@Z`
- size: `282`
- prototype: `unsigned int __fastcall(CNfsXmlSharePermission *__hidden this, struct _NFS_EXPORT_FENCING **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180027a2c`

## callees

- `0x180009670`
- `0x18001d4c8`
- `0x18002783c`
- `0x180028cac`
- `0x180028d80`
- `0x180028efc`
- `0x180035b40`

## import_xrefs

- `msvcrt!free` at `0x180027927`
- `msvcrt!free` at `0x180027927`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNfsXmlSharePermission::GetPermissionEntry(
        CNfsXmlSharePermission *this,
        struct _NFS_EXPORT_FENCING **a2)
{
  unsigned int v4; // edi
  CNfsXmlSharePermission *v5; // rdx
  const char **v6; // rax
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-65h] BYREF
  unsigned int v11; // [rsp+48h] [rbp-61h] BYREF
  void *Block; // [rsp+50h] [rbp-59h] BYREF
  char v13; // [rsp+58h] [rbp-51h] BYREF

  v4 = 1;
  v9 = 1;
  v11 = 0;
  v10 = 0;
  if ( !*((_BYTE *)this + 136)
    || !*((_BYTE *)this + 137)
    || !CNfsXmlSharePermission::ValidatePermission(this, &v11)
    || !CNfsXmlSharePermission::ValidateLanguageEncoding(this, &v10) )
  {
    return 87;
  }
  if ( *((_BYTE *)this + 137) )
  {
    if ( CNfsXmlSharePermission::ValidateClientType(this, &v9) )
    {
      v4 = v9;
      goto LABEL_8;
    }
    return 87;
  }
LABEL_8:
  if ( *((_QWORD *)this + 3) < 8u )
    v5 = this;
  else
    v5 = *(CNfsXmlSharePermission **)this;
  v6 = (const char **)ATL::CW2AEX<128>::CW2AEX<128>(&Block, v5);
  v7 = CreatePermissionEntry(*v6, v4, &v11, &v10, (unsigned __int8 *)this + 96, 0, 1u, a2);
  if ( Block != &v13 )
    free(Block);
  return v7;
}

```

## disassembly

```asm
0x18002783c  mov     [rsp-8+arg_10], rbx
0x180027841  push    rbp
0x180027842  push    rsi
0x180027843  push    rdi
0x180027844  lea     rbp, [rsp-47h]
0x180027849  sub     rsp, 0F0h
0x180027850  mov     rax, cs:__security_cookie
0x180027857  xor     rax, rsp
0x18002785a  mov     [rbp+57h+var_20], rax
0x18002785e  mov     rsi, rdx
0x180027861  mov     rbx, rcx
0x180027864  mov     edi, 1
0x180027869  mov     [rbp+57h+var_C0], edi
0x18002786c  mov     [rbp+57h+var_B8], 0
0x180027873  mov     [rbp+57h+var_BC], 0
0x18002787a  cmp     byte ptr [rcx+88h], 0
0x180027881  jz      loc_180027930
0x180027887  cmp     byte ptr [rcx+89h], 0
0x18002788e  jz      loc_180027930
0x180027894  lea     rdx, [rbp+57h+var_B8]; unsigned int *
0x180027898  call    ?ValidatePermission@CNfsXmlSharePermission@@AEAAEPEAK@Z; CNfsXmlSharePermission::ValidatePermission(ulong *)
0x18002789d  test    al, al
0x18002789f  jz      loc_180027930
0x1800278a5  lea     rdx, [rbp+57h+var_BC]; unsigned int *
0x1800278a9  mov     rcx, rbx; this
0x1800278ac  call    ?ValidateLanguageEncoding@CNfsXmlSharePermission@@AEAAEPEAK@Z; CNfsXmlSharePermission::ValidateLanguageEncoding(ulong *)
0x1800278b1  test    al, al
0x1800278b3  jz      short loc_180027930
0x1800278b5  cmp     byte ptr [rbx+89h], 0
0x1800278bc  jz      short loc_1800278D1
0x1800278be  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x1800278c2  mov     rcx, rbx; this
0x1800278c5  call    ?ValidateClientType@CNfsXmlSharePermission@@AEAAEPEAK@Z; CNfsXmlSharePermission::ValidateClientType(ulong *)
0x1800278ca  test    al, al
0x1800278cc  jz      short loc_180027930
0x1800278ce  mov     edi, [rbp+57h+var_C0]
0x1800278d1  cmp     qword ptr [rbx+18h], 8
0x1800278d6  jb      short loc_1800278DD
0x1800278d8  mov     rdx, [rbx]
0x1800278db  jmp     short loc_1800278E0
0x1800278dd  mov     rdx, rbx
0x1800278e0  lea     rcx, [rbp+57h+Block]
0x1800278e4  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x1800278e9  nop
0x1800278ea  lea     rcx, [rbx+60h]
0x1800278ee  mov     [rsp+100h+var_C8], rsi; struct _NFS_EXPORT_FENCING **
0x1800278f3  mov     [rsp+100h+var_D0], 1; unsigned __int8
0x1800278f8  mov     [rsp+100h+var_D8], 0; char *
0x180027901  mov     [rsp+100h+var_E0], rcx; unsigned __int8 *
0x180027906  lea     r9, [rbp+57h+var_BC]; unsigned int *
0x18002790a  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x18002790e  mov     edx, edi; unsigned int
0x180027910  mov     rcx, [rax]; char *
0x180027913  call    ?CreatePermissionEntry@@YAKPEBDKPEAK1PEAE0EPEAPEAU_NFS_EXPORT_FENCING@@@Z; CreatePermissionEntry(char const *,ulong,ulong *,ulong *,uchar *,char const *,uchar,_NFS_EXPORT_FENCING * *)
0x180027918  mov     ebx, eax
0x18002791a  mov     rcx, [rbp+57h+Block]; Block
0x18002791e  lea     rax, [rbp+57h+var_A8]
0x180027922  cmp     rcx, rax
0x180027925  jz      short loc_18002792E
0x180027927  call    cs:__imp_free
0x18002792d  nop
0x18002792e  jmp     short loc_180027935
0x180027930  mov     ebx, 57h ; 'W'
0x180027935  mov     eax, ebx
0x180027937  mov     rcx, [rbp+57h+var_20]
0x18002793b  xor     rcx, rsp; StackCookie
0x18002793e  call    __security_check_cookie
0x180027943  mov     rbx, [rsp+100h+arg_10]
0x18002794b  add     rsp, 0F0h
0x180027952  pop     rdi
0x180027953  pop     rsi
0x180027954  pop     rbp
0x180027955  retn
```
