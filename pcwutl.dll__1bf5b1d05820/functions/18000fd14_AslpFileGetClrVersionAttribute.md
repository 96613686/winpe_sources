# AslpFileGetClrVersionAttribute

- ea: `0x18000fd14`
- end: `0x18000fe98`
- name: `AslpFileGetClrVersionAttribute`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000d258`

## callees

- `0x18000dcf4`
- `0x18000e240`
- `0x18000edc0`
- `0x18000f334`
- `0x18000fb6c`
- `0x18000fd14`
- `0x180010354`
- `0x1800191a2`
- `0x1800191f0`

## string_xrefs

- `0x18000fe30`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetClrVersionAttribute(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  int FileKindDetailAttribute; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rax
  int v14; // [rsp+20h] [rbp-148h]
  __int64 v15; // [rsp+30h] [rbp-138h] BYREF
  _BYTE v16[256]; // [rsp+40h] [rbp-128h] BYREF

  memset_0(v16, 0, sizeof(v16));
  v15 = 0;
  FileKindDetailAttribute = AslFileMappingEnsure(a2, v4, v5, v6);
  v8 = FileKindDetailAttribute;
  if ( FileKindDetailAttribute >= 0 )
  {
    if ( *(_DWORD *)(a2 + 56) != 6 )
      goto LABEL_5;
    if ( (*(_BYTE *)(a1 + 920) & 1) == 0 )
    {
      FileKindDetailAttribute = AslpFileGetFileKindDetailAttribute(a1, a2);
      v8 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v9 = "AslpFileGetFileKindDetailAttribute failed [%x]";
        v10 = 5603;
        goto LABEL_3;
      }
    }
    if ( (unsigned int)(*(_DWORD *)(a1 + 912) - 12) <= 3 )
    {
      FileKindDetailAttribute = AslpFileGetClrVersion(v16, a2);
      v8 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v9 = "AslpFileGetClrVersion failed [%x]";
        v10 = 5622;
        goto LABEL_3;
      }
      FileKindDetailAttribute = AslStringAnsiToUnicode(&v15, v16);
      v8 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v9 = "AslStringAnsiToUnicode failed [%x]";
        v10 = 5628;
        goto LABEL_3;
      }
      FileKindDetailAttribute = AslStringXmlSanitize(v15);
      v8 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v9 = "AslStringXmlSanitize failed [%x]";
        v10 = 5634;
        goto LABEL_3;
      }
      *(_DWORD *)(a1 + 864) = 4;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v11 + 2 * v12) );
      *(_DWORD *)(a1 + 888) |= 5u;
      *(_QWORD *)(a1 + 872) = v12;
      *(_QWORD *)(a1 + 880) = v11;
    }
    else
    {
LABEL_5:
      *(_DWORD *)(a1 + 888) |= 2u;
    }
    return 0;
  }
  v9 = "AslFileMappingEnsure failed [%x]";
  v10 = 5586;
LABEL_3:
  v14 = FileKindDetailAttribute;
  AslLogCallPrintf(1, "AslpFileGetClrVersionAttribute", v10, v9, v14);
  return v8;
}

```

## disassembly

```asm
0x18000fd14  mov     [rsp+arg_10], rbx
0x18000fd19  push    rbp
0x18000fd1a  push    rdi
0x18000fd1b  push    r14
0x18000fd1d  sub     rsp, 150h
0x18000fd24  mov     rax, cs:__security_cookie
0x18000fd2b  xor     rax, rsp
0x18000fd2e  mov     [rsp+168h+var_28], rax
0x18000fd36  mov     rbp, rdx
0x18000fd39  mov     rdi, rcx
0x18000fd3c  xor     edx, edx; Val
0x18000fd3e  lea     rcx, [rsp+168h+var_128]; void *
0x18000fd43  mov     r8d, 100h; Size
0x18000fd49  call    memset_0
0x18000fd4e  xor     r14d, r14d
0x18000fd51  mov     rcx, rbp
0x18000fd54  mov     [rsp+168h+var_138], r14
0x18000fd59  call    AslFileMappingEnsure
0x18000fd5e  mov     ebx, eax
0x18000fd60  test    eax, eax
0x18000fd62  jns     short loc_18000FD8B
0x18000fd64  lea     r9, aAslfilemapping_2; "AslFileMappingEnsure failed [%x]"
0x18000fd6b  mov     r8d, 15D2h
0x18000fd71  lea     rdx, aAslpfilegetclr_1; "AslpFileGetClrVersionAttribute"
0x18000fd78  mov     [rsp+168h+var_148], eax
0x18000fd7c  mov     ecx, 1
0x18000fd81  call    AslLogCallPrintf
0x18000fd86  jmp     loc_18000FE72
0x18000fd8b  cmp     dword ptr [rbp+38h], 6
0x18000fd8f  jz      short loc_18000FD9D
0x18000fd91  or      dword ptr [rdi+378h], 2
0x18000fd98  jmp     loc_18000FE6F
0x18000fd9d  test    byte ptr [rdi+398h], 1
0x18000fda4  jnz     short loc_18000FDC6
0x18000fda6  mov     rdx, rbp
0x18000fda9  mov     rcx, rdi
0x18000fdac  call    AslpFileGetFileKindDetailAttribute
0x18000fdb1  mov     ebx, eax
0x18000fdb3  test    eax, eax
0x18000fdb5  jns     short loc_18000FDC6
0x18000fdb7  lea     r9, aAslpfilegetfil_0; "AslpFileGetFileKindDetailAttribute fail"...
0x18000fdbe  mov     r8d, 15E3h
0x18000fdc4  jmp     short loc_18000FD71
0x18000fdc6  mov     eax, [rdi+390h]
0x18000fdcc  sub     eax, 0Ch
0x18000fdcf  cmp     eax, 3
0x18000fdd2  ja      short loc_18000FD91
0x18000fdd4  mov     rdx, rbp
0x18000fdd7  lea     rcx, [rsp+168h+var_128]; void *
0x18000fddc  call    AslpFileGetClrVersion
0x18000fde1  mov     ebx, eax
0x18000fde3  test    eax, eax
0x18000fde5  jns     short loc_18000FDF9
0x18000fde7  lea     r9, aAslpfilegetclr_2; "AslpFileGetClrVersion failed [%x]"
0x18000fdee  mov     r8d, 15F6h
0x18000fdf4  jmp     loc_18000FD71
0x18000fdf9  lea     rdx, [rsp+168h+var_128]
0x18000fdfe  lea     rcx, [rsp+168h+var_138]
0x18000fe03  call    AslStringAnsiToUnicode
0x18000fe08  mov     ebx, eax
0x18000fe0a  test    eax, eax
0x18000fe0c  jns     short loc_18000FE20
0x18000fe0e  lea     r9, aAslstringansit_0; "AslStringAnsiToUnicode failed [%x]"
0x18000fe15  mov     r8d, 15FCh
0x18000fe1b  jmp     loc_18000FD71
0x18000fe20  mov     rcx, [rsp+168h+var_138]
0x18000fe25  call    AslStringXmlSanitize
0x18000fe2a  mov     ebx, eax
0x18000fe2c  test    eax, eax
0x18000fe2e  jns     short loc_18000FE42
0x18000fe30  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x18000fe37  mov     r8d, 1602h
0x18000fe3d  jmp     loc_18000FD71
0x18000fe42  mov     dword ptr [rdi+360h], 4
0x18000fe4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fe50  inc     rax
0x18000fe53  cmp     [rcx+rax*2], r14w
0x18000fe58  jnz     short loc_18000FE50
0x18000fe5a  or      dword ptr [rdi+378h], 5
0x18000fe61  mov     [rdi+368h], rax
0x18000fe68  mov     [rdi+370h], rcx
0x18000fe6f  mov     ebx, r14d
0x18000fe72  mov     eax, ebx
0x18000fe74  mov     rcx, [rsp+168h+var_28]
0x18000fe7c  xor     rcx, rsp; StackCookie
0x18000fe7f  call    __security_check_cookie
0x18000fe84  mov     rbx, [rsp+168h+arg_10]
0x18000fe8c  add     rsp, 150h
0x18000fe93  pop     r14
0x18000fe95  pop     rdi
0x18000fe96  pop     rbp
0x18000fe97  retn
```
