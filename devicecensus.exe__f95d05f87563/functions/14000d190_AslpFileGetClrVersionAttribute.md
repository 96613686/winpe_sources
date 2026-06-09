# AslpFileGetClrVersionAttribute

- ea: `0x14000d190`
- end: `0x14000d314`
- name: `AslpFileGetClrVersionAttribute`
- size: `388`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000c630`

## callees

- `0x14000233f`
- `0x140007074`
- `0x1400096a0`
- `0x140009c14`
- `0x14000bde8`
- `0x14000cfe8`
- `0x14000d190`
- `0x14000d7d0`
- `0x1400115f0`

## string_xrefs

- `0x14000d2ac`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetClrVersionAttribute(__int64 a1, __int64 a2)
{
  int FileKindDetailAttribute; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-148h]
  __int64 v12; // [rsp+30h] [rbp-138h] BYREF
  _BYTE v13[256]; // [rsp+40h] [rbp-128h] BYREF

  memset_0(v13, 0, sizeof(v13));
  v12 = 0;
  FileKindDetailAttribute = AslFileMappingEnsure(a2);
  v5 = FileKindDetailAttribute;
  if ( FileKindDetailAttribute >= 0 )
  {
    if ( *(_DWORD *)(a2 + 56) != 6 )
      goto LABEL_5;
    if ( (*(_BYTE *)(a1 + 920) & 1) == 0 )
    {
      FileKindDetailAttribute = AslpFileGetFileKindDetailAttribute(a1, a2);
      v5 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v6 = "AslpFileGetFileKindDetailAttribute failed [%x]";
        v7 = 5603;
        goto LABEL_3;
      }
    }
    if ( (unsigned int)(*(_DWORD *)(a1 + 912) - 12) <= 3 )
    {
      FileKindDetailAttribute = AslpFileGetClrVersion(v13, a2);
      v5 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v6 = "AslpFileGetClrVersion failed [%x]";
        v7 = 5622;
        goto LABEL_3;
      }
      FileKindDetailAttribute = AslStringAnsiToUnicode(&v12, v13);
      v5 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v6 = "AslStringAnsiToUnicode failed [%x]";
        v7 = 5628;
        goto LABEL_3;
      }
      FileKindDetailAttribute = AslStringXmlSanitize(v12);
      v5 = FileKindDetailAttribute;
      if ( FileKindDetailAttribute < 0 )
      {
        v6 = "AslStringXmlSanitize failed [%x]";
        v7 = 5634;
        goto LABEL_3;
      }
      *(_DWORD *)(a1 + 864) = 4;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      *(_DWORD *)(a1 + 888) |= 5u;
      *(_QWORD *)(a1 + 872) = v9;
      *(_QWORD *)(a1 + 880) = v8;
    }
    else
    {
LABEL_5:
      *(_DWORD *)(a1 + 888) |= 2u;
    }
    return 0;
  }
  v6 = "AslFileMappingEnsure failed [%x]";
  v7 = 5586;
LABEL_3:
  v11 = FileKindDetailAttribute;
  AslLogCallPrintf(1, "AslpFileGetClrVersionAttribute", v7, v6, v11);
  return v5;
}

```

## disassembly

```asm
0x14000d190  mov     [rsp+arg_10], rbx
0x14000d195  push    rbp
0x14000d196  push    rdi
0x14000d197  push    r14
0x14000d199  sub     rsp, 150h
0x14000d1a0  mov     rax, cs:__security_cookie
0x14000d1a7  xor     rax, rsp
0x14000d1aa  mov     [rsp+168h+var_28], rax
0x14000d1b2  mov     rbp, rdx
0x14000d1b5  mov     rdi, rcx
0x14000d1b8  xor     edx, edx; Val
0x14000d1ba  lea     rcx, [rsp+168h+var_128]; void *
0x14000d1bf  mov     r8d, 100h; Size
0x14000d1c5  call    memset_0
0x14000d1ca  xor     r14d, r14d
0x14000d1cd  mov     rcx, rbp
0x14000d1d0  mov     [rsp+168h+var_138], r14
0x14000d1d5  call    AslFileMappingEnsure
0x14000d1da  mov     ebx, eax
0x14000d1dc  test    eax, eax
0x14000d1de  jns     short loc_14000D207
0x14000d1e0  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14000d1e7  mov     r8d, 15D2h
0x14000d1ed  lea     rdx, aAslpfilegetclr_1; "AslpFileGetClrVersionAttribute"
0x14000d1f4  mov     [rsp+168h+var_148], eax
0x14000d1f8  mov     ecx, 1
0x14000d1fd  call    AslLogCallPrintf
0x14000d202  jmp     loc_14000D2EE
0x14000d207  cmp     dword ptr [rbp+38h], 6
0x14000d20b  jz      short loc_14000D219
0x14000d20d  or      dword ptr [rdi+378h], 2
0x14000d214  jmp     loc_14000D2EB
0x14000d219  test    byte ptr [rdi+398h], 1
0x14000d220  jnz     short loc_14000D242
0x14000d222  mov     rdx, rbp
0x14000d225  mov     rcx, rdi
0x14000d228  call    AslpFileGetFileKindDetailAttribute
0x14000d22d  mov     ebx, eax
0x14000d22f  test    eax, eax
0x14000d231  jns     short loc_14000D242
0x14000d233  lea     r9, aAslpfilegetfil_0; "AslpFileGetFileKindDetailAttribute fail"...
0x14000d23a  mov     r8d, 15E3h
0x14000d240  jmp     short loc_14000D1ED
0x14000d242  mov     eax, [rdi+390h]
0x14000d248  sub     eax, 0Ch
0x14000d24b  cmp     eax, 3
0x14000d24e  ja      short loc_14000D20D
0x14000d250  mov     rdx, rbp
0x14000d253  lea     rcx, [rsp+168h+var_128]; void *
0x14000d258  call    AslpFileGetClrVersion
0x14000d25d  mov     ebx, eax
0x14000d25f  test    eax, eax
0x14000d261  jns     short loc_14000D275
0x14000d263  lea     r9, aAslpfilegetclr_2; "AslpFileGetClrVersion failed [%x]"
0x14000d26a  mov     r8d, 15F6h
0x14000d270  jmp     loc_14000D1ED
0x14000d275  lea     rdx, [rsp+168h+var_128]
0x14000d27a  lea     rcx, [rsp+168h+var_138]
0x14000d27f  call    AslStringAnsiToUnicode
0x14000d284  mov     ebx, eax
0x14000d286  test    eax, eax
0x14000d288  jns     short loc_14000D29C
0x14000d28a  lea     r9, aAslstringansit_0; "AslStringAnsiToUnicode failed [%x]"
0x14000d291  mov     r8d, 15FCh
0x14000d297  jmp     loc_14000D1ED
0x14000d29c  mov     rcx, [rsp+168h+var_138]
0x14000d2a1  call    AslStringXmlSanitize
0x14000d2a6  mov     ebx, eax
0x14000d2a8  test    eax, eax
0x14000d2aa  jns     short loc_14000D2BE
0x14000d2ac  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x14000d2b3  mov     r8d, 1602h
0x14000d2b9  jmp     loc_14000D1ED
0x14000d2be  mov     dword ptr [rdi+360h], 4
0x14000d2c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d2cc  inc     rax
0x14000d2cf  cmp     [rcx+rax*2], r14w
0x14000d2d4  jnz     short loc_14000D2CC
0x14000d2d6  or      dword ptr [rdi+378h], 5
0x14000d2dd  mov     [rdi+368h], rax
0x14000d2e4  mov     [rdi+370h], rcx
0x14000d2eb  mov     ebx, r14d
0x14000d2ee  mov     eax, ebx
0x14000d2f0  mov     rcx, [rsp+168h+var_28]
0x14000d2f8  xor     rcx, rsp; StackCookie
0x14000d2fb  call    __security_check_cookie
0x14000d300  mov     rbx, [rsp+168h+arg_10]
0x14000d308  add     rsp, 150h
0x14000d30f  pop     r14
0x14000d311  pop     rdi
0x14000d312  pop     rbp
0x14000d313  retn
```
