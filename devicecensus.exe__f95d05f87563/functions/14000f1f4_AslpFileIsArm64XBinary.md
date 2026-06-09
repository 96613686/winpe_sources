# AslpFileIsArm64XBinary

- ea: `0x14000f1f4`
- end: `0x14000f3a0`
- name: `AslpFileIsArm64XBinary`
- size: `428`
- prototype: `__int64 __fastcall(bool *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x14000c630`

## callees

- `0x140007074`
- `0x14000bf5c`
- `0x14000dc74`
- `0x14000f1f4`
- `0x1400101cc`
- `0x1400115c2`

## string_xrefs

- `0x14000f2c5`: `AslpFileGetImageNtHeader failed [%x]`
- `0x14000f339`: `AslpImageRvaToVa failed to find LoadConfigTableDirectory RVA`

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
    FileKindDetail = AslFileMappingGetFileKindDetail((int *)&v14, a2);
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
0x14000f1f4  mov     rax, rsp
0x14000f1f7  mov     [rax+10h], rbx
0x14000f1fb  mov     [rax+20h], rbp
0x14000f1ff  push    rsi
0x14000f200  push    rdi
0x14000f201  push    r12
0x14000f203  push    r14
0x14000f205  push    r15
0x14000f207  sub     rsp, 30h
0x14000f20b  mov     dword ptr [rax+8], 0
0x14000f212  mov     rbp, rdx
0x14000f215  mov     qword ptr [rax+18h], 0
0x14000f21d  mov     rdi, rcx
0x14000f220  mov     ebx, 0C00000F0h
0x14000f225  test    rcx, rcx
0x14000f228  jz      loc_14000F387
0x14000f22e  mov     byte ptr [rcx], 0
0x14000f231  lea     rcx, [rax+8]
0x14000f235  call    AslFileMappingGetFileKindDetail
0x14000f23a  mov     ebx, eax
0x14000f23c  test    eax, eax
0x14000f23e  jns     short loc_14000F267
0x14000f240  lea     r9, aAslfilemapping; "AslFileMappingGetFileKindDetails failed"...
0x14000f247  mov     r8d, 16E2h
0x14000f24d  lea     rdx, aAslpfileisarm6; "AslpFileIsArm64XBinary"
0x14000f254  mov     [rsp+58h+var_38], eax
0x14000f258  mov     ecx, 1
0x14000f25d  call    AslLogCallPrintf
0x14000f262  jmp     loc_14000F387
0x14000f267  mov     ecx, [rsp+58h+arg_0]
0x14000f26b  test    ecx, ecx
0x14000f26d  jz      loc_14000F382
0x14000f273  sub     ecx, 1
0x14000f276  jz      loc_14000F382
0x14000f27c  sub     ecx, 1
0x14000f27f  jz      loc_14000F382
0x14000f285  sub     ecx, 1
0x14000f288  jz      loc_14000F382
0x14000f28e  sub     ecx, 1
0x14000f291  jz      loc_14000F382
0x14000f297  sub     ecx, 4
0x14000f29a  jz      short loc_14000F2B2
0x14000f29c  sub     ecx, 1
0x14000f29f  jz      short loc_14000F2B2
0x14000f2a1  sub     ecx, 1
0x14000f2a4  jz      short loc_14000F2B2
0x14000f2a6  cmp     ecx, 5
0x14000f2a9  jz      short loc_14000F2B2
0x14000f2ab  xor     ebx, ebx
0x14000f2ad  jmp     loc_14000F387
0x14000f2b2  mov     rdx, rbp
0x14000f2b5  lea     rcx, [rsp+58h+arg_10]
0x14000f2ba  call    AslpFileGetImageNtHeader
0x14000f2bf  mov     ebx, eax
0x14000f2c1  test    eax, eax
0x14000f2c3  jns     short loc_14000F2D7
0x14000f2c5  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14000f2cc  mov     r8d, 1702h
0x14000f2d2  jmp     loc_14000F24D
0x14000f2d7  mov     rbx, [rsp+58h+arg_10]
0x14000f2dc  mov     r14d, [rbx+0D8h]
0x14000f2e3  test    r14d, r14d
0x14000f2e6  jz      short loc_14000F2AB
0x14000f2e8  movzx   r12d, word ptr [rbx+14h]
0x14000f2ed  xor     esi, esi
0x14000f2ef  movzx   r15d, word ptr [rbx+6]
0x14000f2f4  add     r12, 18h
0x14000f2f8  add     r12, rbx
0x14000f2fb  test    r15, r15
0x14000f2fe  jz      short loc_14000F326
0x14000f300  lea     rax, [rsi+rsi*4]
0x14000f304  mov     r8d, 8; MaxCount
0x14000f30a  lea     rdx, [r12+rax*8]; Str2
0x14000f30e  lea     rcx, Str1; ".a64xrm"
0x14000f315  call    strncmp_0
0x14000f31a  test    eax, eax
0x14000f31c  jz      short loc_14000F35C
0x14000f31e  inc     rsi
0x14000f321  cmp     rsi, r15
0x14000f324  jb      short loc_14000F300
0x14000f326  mov     r8d, r14d
0x14000f329  mov     rdx, rbp
0x14000f32c  mov     rcx, rbx
0x14000f32f  call    AslpImageRvaToVa
0x14000f334  test    rax, rax
0x14000f337  jnz     short loc_14000F364
0x14000f339  lea     r9, aAslpimagervato_1; "AslpImageRvaToVa failed to find LoadCon"...
0x14000f340  mov     r8d, 1721h
0x14000f346  lea     rdx, aAslpfileisarm6; "AslpFileIsArm64XBinary"
0x14000f34d  mov     ebx, 0C0000225h
0x14000f352  lea     ecx, [rax+1]
0x14000f355  call    AslLogCallPrintf
0x14000f35a  jmp     short loc_14000F387
0x14000f35c  mov     byte ptr [rdi], 1
0x14000f35f  jmp     loc_14000F2AB
0x14000f364  cmp     dword ptr [rax], 0D0h
0x14000f36a  jb      loc_14000F2AB
0x14000f370  cmp     qword ptr [rax+0C8h], 0
0x14000f378  setnz   al
0x14000f37b  mov     [rdi], al
0x14000f37d  jmp     loc_14000F2AB
0x14000f382  mov     ebx, 80000022h
0x14000f387  mov     rbp, [rsp+58h+arg_18]
0x14000f38c  mov     eax, ebx
0x14000f38e  mov     rbx, [rsp+58h+arg_8]
0x14000f393  add     rsp, 30h
0x14000f397  pop     r15
0x14000f399  pop     r14
0x14000f39b  pop     r12
0x14000f39d  pop     rdi
0x14000f39e  pop     rsi
0x14000f39f  retn
```
