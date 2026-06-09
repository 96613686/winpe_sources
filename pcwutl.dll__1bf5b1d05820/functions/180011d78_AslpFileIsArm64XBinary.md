# AslpFileIsArm64XBinary

- ea: `0x180011d78`
- end: `0x180011f24`
- name: `AslpFileIsArm64XBinary`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000d258`

## callees

- `0x18000de68`
- `0x18000e240`
- `0x1800107f8`
- `0x180011d78`
- `0x180013658`
- `0x1800191ae`

## string_xrefs

- `0x180011e49`: `AslpFileGetImageNtHeader failed [%x]`
- `0x180011ebd`: `AslpImageRvaToVa failed to find LoadConfigTableDirectory RVA`

## pseudocode

```c
__int64 __fastcall AslpFileIsArm64XBinary(bool *a1, __int64 a2)
{
  unsigned int v4; // ebx
  int FileKindDetail; // eax
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rsi
  unsigned __int64 v10; // r15
  __int64 v11; // r12
  __int64 v12; // rax
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  v15 = 0;
  v4 = -1073741584;
  if ( a1 )
  {
    *a1 = 0;
    FileKindDetail = AslFileMappingGetFileKindDetail(&v14);
    v4 = FileKindDetail;
    if ( FileKindDetail < 0 )
    {
      v6 = "AslFileMappingGetFileKindDetails failed [%x]";
      v7 = 5858;
LABEL_4:
      AslLogCallPrintf(1, "AslpFileIsArm64XBinary", v7, v6, FileKindDetail);
      return v4;
    }
    if ( v14 <= 4 )
      return (unsigned int)-2147483614;
    if ( v14 == 8 || v14 == 9 || v14 == 10 || v14 == 15 )
    {
      FileKindDetail = AslpFileGetImageNtHeader(&v15, a2);
      v4 = FileKindDetail;
      if ( FileKindDetail < 0 )
      {
        v6 = "AslpFileGetImageNtHeader failed [%x]";
        v7 = 5890;
        goto LABEL_4;
      }
      v8 = v15;
      if ( *(_DWORD *)(v15 + 216) )
      {
        v9 = 0;
        v10 = *(unsigned __int16 *)(v15 + 6);
        v11 = v15 + *(unsigned __int16 *)(v15 + 20) + 24LL;
        if ( *(_WORD *)(v15 + 6) )
        {
          while ( strncmp_0(".a64xrm", (const char *)(v11 + 40 * v9), 8u) )
          {
            if ( ++v9 >= v10 )
              goto LABEL_17;
          }
          *a1 = 1;
        }
        else
        {
LABEL_17:
          v12 = AslpImageRvaToVa(v8, a2);
          if ( !v12 )
          {
            v4 = -1073741275;
            AslLogCallPrintf(
              1,
              "AslpFileIsArm64XBinary",
              5921,
              "AslpImageRvaToVa failed to find LoadConfigTableDirectory RVA");
            return v4;
          }
          if ( *(_DWORD *)v12 >= 0xD0u )
            *a1 = *(_QWORD *)(v12 + 200) != 0;
        }
      }
    }
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180011d78  mov     rax, rsp
0x180011d7b  mov     [rax+10h], rbx
0x180011d7f  mov     [rax+20h], rbp
0x180011d83  push    rsi
0x180011d84  push    rdi
0x180011d85  push    r12
0x180011d87  push    r14
0x180011d89  push    r15
0x180011d8b  sub     rsp, 30h
0x180011d8f  mov     dword ptr [rax+8], 0
0x180011d96  mov     rbp, rdx
0x180011d99  mov     qword ptr [rax+18h], 0
0x180011da1  mov     rdi, rcx
0x180011da4  mov     ebx, 0C00000F0h
0x180011da9  test    rcx, rcx
0x180011dac  jz      loc_180011F0B
0x180011db2  mov     byte ptr [rcx], 0
0x180011db5  lea     rcx, [rax+8]
0x180011db9  call    AslFileMappingGetFileKindDetail
0x180011dbe  mov     ebx, eax
0x180011dc0  test    eax, eax
0x180011dc2  jns     short loc_180011DEB
0x180011dc4  lea     r9, aAslfilemapping; "AslFileMappingGetFileKindDetails failed"...
0x180011dcb  mov     r8d, 16E2h
0x180011dd1  lea     rdx, aAslpfileisarm6; "AslpFileIsArm64XBinary"
0x180011dd8  mov     [rsp+58h+var_38], eax
0x180011ddc  mov     ecx, 1
0x180011de1  call    AslLogCallPrintf
0x180011de6  jmp     loc_180011F0B
0x180011deb  mov     ecx, [rsp+58h+arg_0]
0x180011def  test    ecx, ecx
0x180011df1  jz      loc_180011F06
0x180011df7  sub     ecx, 1
0x180011dfa  jz      loc_180011F06
0x180011e00  sub     ecx, 1
0x180011e03  jz      loc_180011F06
0x180011e09  sub     ecx, 1
0x180011e0c  jz      loc_180011F06
0x180011e12  sub     ecx, 1
0x180011e15  jz      loc_180011F06
0x180011e1b  sub     ecx, 4
0x180011e1e  jz      short loc_180011E36
0x180011e20  sub     ecx, 1
0x180011e23  jz      short loc_180011E36
0x180011e25  sub     ecx, 1
0x180011e28  jz      short loc_180011E36
0x180011e2a  cmp     ecx, 5
0x180011e2d  jz      short loc_180011E36
0x180011e2f  xor     ebx, ebx
0x180011e31  jmp     loc_180011F0B
0x180011e36  mov     rdx, rbp
0x180011e39  lea     rcx, [rsp+58h+arg_10]
0x180011e3e  call    AslpFileGetImageNtHeader
0x180011e43  mov     ebx, eax
0x180011e45  test    eax, eax
0x180011e47  jns     short loc_180011E5B
0x180011e49  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x180011e50  mov     r8d, 1702h
0x180011e56  jmp     loc_180011DD1
0x180011e5b  mov     rbx, [rsp+58h+arg_10]
0x180011e60  mov     r14d, [rbx+0D8h]
0x180011e67  test    r14d, r14d
0x180011e6a  jz      short loc_180011E2F
0x180011e6c  movzx   r12d, word ptr [rbx+14h]
0x180011e71  xor     esi, esi
0x180011e73  movzx   r15d, word ptr [rbx+6]
0x180011e78  add     r12, 18h
0x180011e7c  add     r12, rbx
0x180011e7f  test    r15, r15
0x180011e82  jz      short loc_180011EAA
0x180011e84  lea     rax, [rsi+rsi*4]
0x180011e88  mov     r8d, 8; MaxCount
0x180011e8e  lea     rdx, [r12+rax*8]; Str2
0x180011e92  lea     rcx, Str1; ".a64xrm"
0x180011e99  call    strncmp_0
0x180011e9e  test    eax, eax
0x180011ea0  jz      short loc_180011EE0
0x180011ea2  inc     rsi
0x180011ea5  cmp     rsi, r15
0x180011ea8  jb      short loc_180011E84
0x180011eaa  mov     r8d, r14d
0x180011ead  mov     rdx, rbp
0x180011eb0  mov     rcx, rbx
0x180011eb3  call    AslpImageRvaToVa
0x180011eb8  test    rax, rax
0x180011ebb  jnz     short loc_180011EE8
0x180011ebd  lea     r9, aAslpimagervato_1; "AslpImageRvaToVa failed to find LoadCon"...
0x180011ec4  mov     r8d, 1721h
0x180011eca  lea     rdx, aAslpfileisarm6; "AslpFileIsArm64XBinary"
0x180011ed1  mov     ebx, 0C0000225h
0x180011ed6  lea     ecx, [rax+1]
0x180011ed9  call    AslLogCallPrintf
0x180011ede  jmp     short loc_180011F0B
0x180011ee0  mov     byte ptr [rdi], 1
0x180011ee3  jmp     loc_180011E2F
0x180011ee8  cmp     dword ptr [rax], 0D0h
0x180011eee  jb      loc_180011E2F
0x180011ef4  cmp     qword ptr [rax+0C8h], 0
0x180011efc  setnz   al
0x180011eff  mov     [rdi], al
0x180011f01  jmp     loc_180011E2F
0x180011f06  mov     ebx, 80000022h
0x180011f0b  mov     rbp, [rsp+58h+arg_18]
0x180011f10  mov     eax, ebx
0x180011f12  mov     rbx, [rsp+58h+arg_8]
0x180011f17  add     rsp, 30h
0x180011f1b  pop     r15
0x180011f1d  pop     r14
0x180011f1f  pop     r12
0x180011f21  pop     rdi
0x180011f22  pop     rsi
0x180011f23  retn
```
