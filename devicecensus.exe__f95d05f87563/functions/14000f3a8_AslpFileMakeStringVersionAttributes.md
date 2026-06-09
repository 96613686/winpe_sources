# AslpFileMakeStringVersionAttributes

- ea: `0x14000f3a8`
- end: `0x14000f5b0`
- name: `AslpFileMakeStringVersionAttributes`
- size: `520`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000e18c`

## callees

- `0x140007074`
- `0x140009c14`
- `0x14000f3a8`
- `0x14000fb14`
- `0x14000fe54`
- `0x14000fee8`

## string_xrefs

- `0x14000f55a`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileMakeStringVersionAttributes(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // r14
  int v3; // r12d
  __int64 i; // rcx
  __int64 v6; // rax
  unsigned int v7; // edi
  int VersionString; // eax
  unsigned __int16 *v9; // rsi
  unsigned int v10; // r11d
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rdi
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // r15
  __int64 v16; // r13
  __int64 v17; // r13
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v22; // [rsp+20h] [rbp-20h]
  __int64 v23; // [rsp+28h] [rbp-18h]
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  __int64 v25; // [rsp+38h] [rbp-8h] BYREF
  __int64 v26; // [rsp+88h] [rbp+48h] BYREF
  __int64 v27; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int64 v28; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  v3 = a2;
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v28 = 0;
  if ( !a2 )
  {
    for ( i = 0; i != 8; ++i )
    {
      v6 = i;
      *(_DWORD *)(32 * v6 + a1 + 184) |= 2u;
    }
    *(_DWORD *)(a1 + 792) |= 2u;
    return 0;
  }
  VersionString = AslpFileVerQueryBlock(a2, L"\\VarFileInfo\\Translation", &v27, &v26);
  v7 = VersionString;
  if ( VersionString == -1073741275 )
  {
    v9 = 0;
    v10 = 0;
  }
  else
  {
    if ( VersionString < 0 )
    {
      v11 = "AslpFileVerQueryBlock failed [%x]";
      v12 = 2561;
LABEL_28:
      LODWORD(v22) = VersionString;
      AslLogCallPrintf(1, "AslpFileMakeStringVersionAttributes", v12, v11, v22);
      return v7;
    }
    v13 = v27;
    v9 = 0;
    if ( (int)AslpFileVerBlockGetValueOffset(&v28, v27, v26) >= 0 && v28 < v14 )
    {
      v9 = (unsigned __int16 *)(v28 + v13);
      v10 = v14 - v28;
    }
  }
  v15 = (unsigned __int64)v10 >> 2;
  do
  {
    v16 = SLODWORD(qword_140013BC0[2 * v2]);
    v23 = qword_140013BC0[2 * v2 + 1];
    LODWORD(v26) = qword_140013BC0[2 * v2];
    VersionString = AslpFileQueryVersionString((unsigned int)&v24, (unsigned int)&v25, v3, (_DWORD)v9, v15, v23);
    v7 = VersionString;
    if ( VersionString < 0 )
    {
      if ( VersionString != -1073741275 )
      {
        v11 = "AslpFileQueryVersionString failed [%x]";
        v12 = 2616;
        goto LABEL_28;
      }
      *(_DWORD *)(32 * v16 + a1 + 24) |= 2u;
    }
    else
    {
      v17 = v24;
      VersionString = AslStringXmlSanitize(v24);
      v7 = VersionString;
      if ( VersionString < 0 )
      {
        v11 = "AslStringXmlSanitize failed [%x]";
        v12 = 2603;
        goto LABEL_28;
      }
      v18 = 32LL * (int)v26;
      v19 = -1;
      *(_DWORD *)(v18 + a1) = 4;
      do
        ++v19;
      while ( *(_WORD *)(v17 + 2 * v19) );
      *(_DWORD *)(v18 + a1 + 24) |= 1u;
      *(_QWORD *)(v18 + a1 + 8) = v19;
      *(_QWORD *)(v18 + a1 + 16) = v17;
    }
    ++v2;
  }
  while ( v2 < 8 );
  if ( v9 && v15 == 1 )
  {
    v20 = *v9;
    *(_DWORD *)(a1 + 792) |= 1u;
    *(_QWORD *)(a1 + 784) = v20;
    *(_DWORD *)(a1 + 768) = 2;
    *(_QWORD *)(a1 + 776) = 4;
  }
  else
  {
    *(_DWORD *)(a1 + 792) |= 2u;
  }
  return 0;
}

```

## disassembly

```asm
0x14000f3a8  mov     [rsp-38h+arg_0], rbx
0x14000f3ad  push    rbp
0x14000f3ae  push    rsi
0x14000f3af  push    rdi
0x14000f3b0  push    r12
0x14000f3b2  push    r13
0x14000f3b4  push    r14
0x14000f3b6  push    r15
0x14000f3b8  mov     rbp, rsp
0x14000f3bb  sub     rsp, 40h
0x14000f3bf  xor     r14d, r14d
0x14000f3c2  mov     r12, rdx
0x14000f3c5  mov     [rbp+var_10], r14
0x14000f3c9  mov     rbx, rcx
0x14000f3cc  mov     [rbp+var_8], r14
0x14000f3d0  mov     [rbp+arg_10], r14
0x14000f3d4  mov     [rbp+arg_8], r14
0x14000f3d8  mov     [rbp+arg_18], r14
0x14000f3dc  test    rdx, rdx
0x14000f3df  jnz     short loc_14000F40B
0x14000f3e1  mov     ecx, r14d
0x14000f3e4  mov     rax, rcx
0x14000f3e7  inc     rcx
0x14000f3ea  shl     rax, 5
0x14000f3ee  or      dword ptr [rax+rbx+0B8h], 2
0x14000f3f6  cmp     rcx, 8
0x14000f3fa  jnz     short loc_14000F3E4
0x14000f3fc  or      dword ptr [rbx+318h], 2
0x14000f403  mov     edi, r14d
0x14000f406  jmp     loc_14000F596
0x14000f40b  lea     r9, [rbp+arg_8]
0x14000f40f  mov     rcx, r12
0x14000f412  lea     r8, [rbp+arg_10]
0x14000f416  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x14000f41d  call    AslpFileVerQueryBlock
0x14000f422  mov     edi, eax
0x14000f424  cmp     eax, 0C0000225h
0x14000f429  jnz     short loc_14000F433
0x14000f42b  mov     rsi, r14
0x14000f42e  mov     r11d, r14d
0x14000f431  jmp     short loc_14000F47A
0x14000f433  test    eax, eax
0x14000f435  jns     short loc_14000F449
0x14000f437  lea     r9, aAslpfileverque_0; "AslpFileVerQueryBlock failed [%x]"
0x14000f43e  mov     r8d, 0A01h
0x14000f444  jmp     loc_14000F581
0x14000f449  mov     rdi, [rbp+arg_10]
0x14000f44d  lea     rcx, [rbp+arg_18]
0x14000f451  mov     r8, [rbp+arg_8]
0x14000f455  mov     rdx, rdi
0x14000f458  mov     rsi, r14
0x14000f45b  mov     r11d, r14d
0x14000f45e  call    AslpFileVerBlockGetValueOffset
0x14000f463  test    eax, eax
0x14000f465  js      short loc_14000F47A
0x14000f467  mov     rax, [rbp+arg_18]
0x14000f46b  cmp     rax, r8
0x14000f46e  jnb     short loc_14000F47A
0x14000f470  mov     r11d, r8d
0x14000f473  lea     rsi, [rax+rdi]
0x14000f477  sub     r11d, eax
0x14000f47a  mov     r15d, r11d
0x14000f47d  shr     r15, 2
0x14000f481  lea     rcx, qword_140013BC0
0x14000f488  mov     rax, r14
0x14000f48b  add     rax, rax
0x14000f48e  lea     rdx, [rbp+var_8]
0x14000f492  mov     r9, rsi
0x14000f495  mov     r8, r12
0x14000f498  movsxd  r13, dword ptr [rcx+rax*8]
0x14000f49c  mov     rax, [rcx+rax*8+8]
0x14000f4a1  lea     rcx, [rbp+var_10]
0x14000f4a5  mov     [rsp+40h+var_18], rax
0x14000f4aa  mov     [rsp+40h+var_20], r15
0x14000f4af  mov     dword ptr [rbp+arg_8], r13d
0x14000f4b3  call    AslpFileQueryVersionString
0x14000f4b8  xor     edx, edx
0x14000f4ba  mov     edi, eax
0x14000f4bc  test    eax, eax
0x14000f4be  js      short loc_14000F507
0x14000f4c0  mov     r13, [rbp+var_10]
0x14000f4c4  mov     rcx, r13
0x14000f4c7  call    AslStringXmlSanitize
0x14000f4cc  xor     edx, edx
0x14000f4ce  mov     edi, eax
0x14000f4d0  test    eax, eax
0x14000f4d2  js      loc_14000F55A
0x14000f4d8  movsxd  rax, dword ptr [rbp+arg_8]
0x14000f4dc  shl     rax, 5
0x14000f4e0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f4e4  mov     dword ptr [rax+rbx], 4
0x14000f4eb  inc     rcx
0x14000f4ee  cmp     [r13+rcx*2+0], dx
0x14000f4f4  jnz     short loc_14000F4EB
0x14000f4f6  or      dword ptr [rax+rbx+18h], 1
0x14000f4fb  mov     [rax+rbx+8], rcx
0x14000f500  mov     [rax+rbx+10h], r13
0x14000f505  jmp     short loc_14000F51A
0x14000f507  cmp     eax, 0C0000225h
0x14000f50c  jnz     short loc_14000F574
0x14000f50e  mov     rax, r13
0x14000f511  shl     rax, 5
0x14000f515  or      dword ptr [rax+rbx+18h], 2
0x14000f51a  inc     r14
0x14000f51d  cmp     r14, 8
0x14000f521  jb      loc_14000F481
0x14000f527  test    rsi, rsi
0x14000f52a  jz      short loc_14000F569
0x14000f52c  cmp     r15, 1
0x14000f530  jnz     short loc_14000F569
0x14000f532  movzx   eax, word ptr [rsi]
0x14000f535  or      [rbx+318h], r15d
0x14000f53c  mov     [rbx+310h], rax
0x14000f543  mov     dword ptr [rbx+300h], 2
0x14000f54d  mov     qword ptr [rbx+308h], 4
0x14000f558  jmp     short loc_14000F570
0x14000f55a  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x14000f561  mov     r8d, 0A2Bh
0x14000f567  jmp     short loc_14000F581
0x14000f569  or      dword ptr [rbx+318h], 2
0x14000f570  mov     edi, edx
0x14000f572  jmp     short loc_14000F596
0x14000f574  lea     r9, aAslpfilequeryv_0; "AslpFileQueryVersionString failed [%x]"
0x14000f57b  mov     r8d, 0A38h
0x14000f581  lea     rdx, aAslpfilemakest; "AslpFileMakeStringVersionAttributes"
0x14000f588  mov     dword ptr [rsp+40h+var_20], eax
0x14000f58c  mov     ecx, 1
0x14000f591  call    AslLogCallPrintf
0x14000f596  mov     rbx, [rsp+40h+arg_0]
0x14000f59e  mov     eax, edi
0x14000f5a0  add     rsp, 40h
0x14000f5a4  pop     r15
0x14000f5a6  pop     r14
0x14000f5a8  pop     r13
0x14000f5aa  pop     r12
0x14000f5ac  pop     rdi
0x14000f5ad  pop     rsi
0x14000f5ae  pop     rbp
0x14000f5af  retn
```
