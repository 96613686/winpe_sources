# AslpImageRvaToVa

- ea: `0x180013658`
- end: `0x180013783`
- name: `AslpImageRvaToVa`
- size: `299`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e01c`
- `0x18000fb6c`
- `0x1800108c4`
- `0x180011638`
- `0x180011d78`
- `0x180012c38`

## callees

- `0x18000e240`
- `0x1800107f8`
- `0x180013658`

## string_xrefs

- `0x1800136fe`: `AslpFileGetImageNtHeader failed [%x]`

## pseudocode

```c
unsigned __int64 __fastcall AslpImageRvaToVa(unsigned __int64 a1, __int64 a2, unsigned int a3)
{
  unsigned __int64 v5; // r9
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rdx
  int ImageNtHeader; // eax
  _DWORD *v12; // rdx
  int v13; // r8d
  unsigned int v14; // ecx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a1;
  if ( !a3 )
    return 0;
  if ( *(_BYTE *)(a2 + 51) )
  {
    if ( (unsigned __int64)a3 < *(_QWORD *)(a2 + 40) )
      return a3 + *(_QWORD *)(a2 + 32);
    return 0;
  }
  v7 = *(_QWORD *)(a2 + 32);
  v16 = a1;
  if ( a1 < v7
    || (v8 = a1 + 264, v5 > v8)
    || (v9 = *(_QWORD *)(a2 + 40), v10 = v7 + v9, v5 > v7 + v9)
    || v8 < v7
    || v8 > v10
    || v7 > v10
    || v9 < 0x108 )
  {
    AslLogCallPrintf(
      2,
      "AslpImageRvaToVa",
      5477,
      "AslpImageRvaToVa called with headers not contained in the file view.");
    ImageNtHeader = AslpFileGetImageNtHeader(&v16, a2);
    if ( ImageNtHeader < 0 )
    {
      AslLogCallPrintf(1, "AslpImageRvaToVa", 5481, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
      return 0;
    }
    v5 = v16;
  }
  v12 = (_DWORD *)(*(unsigned __int16 *)(v5 + 20) + v5 + 24);
  v13 = 0;
  if ( !*(_WORD *)(v5 + 6) )
    return 0;
  while ( 1 )
  {
    v14 = v12[3];
    if ( a3 >= v14 && a3 < v12[4] + v14 )
      break;
    v12 += 10;
    if ( ++v13 >= (unsigned int)*(unsigned __int16 *)(v5 + 6) )
      return 0;
  }
  if ( !v12 )
    return 0;
  v15 = a3 + v12[5] - v12[3];
  if ( v15 >= *(_QWORD *)(a2 + 24) )
    return 0;
  return v15 + *(_QWORD *)(a2 + 32);
}

```

## disassembly

```asm
0x180013658  mov     [rsp+arg_0], rbx
0x18001365d  push    rdi
0x18001365e  sub     rsp, 30h
0x180013662  mov     edi, r8d
0x180013665  mov     rbx, rdx
0x180013668  mov     r9, rcx
0x18001366b  test    r8d, r8d
0x18001366e  jz      loc_180013720
0x180013674  cmp     byte ptr [rdx+33h], 0
0x180013678  jz      short loc_180013690
0x18001367a  cmp     rdi, [rdx+28h]
0x18001367e  jnb     loc_180013720
0x180013684  mov     rax, [rdx+20h]
0x180013688  add     rax, rdi
0x18001368b  jmp     loc_180013722
0x180013690  mov     rax, [rdx+20h]
0x180013694  mov     [rsp+38h+arg_18], r9
0x180013699  cmp     r9, rax
0x18001369c  jb      short loc_1800136CF
0x18001369e  add     rcx, 108h
0x1800136a5  cmp     r9, rcx
0x1800136a8  ja      short loc_1800136CF
0x1800136aa  mov     r8, [rdx+28h]
0x1800136ae  lea     rdx, [rax+r8]
0x1800136b2  cmp     r9, rdx
0x1800136b5  ja      short loc_1800136CF
0x1800136b7  cmp     rcx, rax
0x1800136ba  jb      short loc_1800136CF
0x1800136bc  cmp     rcx, rdx
0x1800136bf  ja      short loc_1800136CF
0x1800136c1  cmp     rax, rdx
0x1800136c4  ja      short loc_1800136CF
0x1800136c6  cmp     r8, 108h
0x1800136cd  jnb     short loc_180013732
0x1800136cf  lea     r9, aAslpimagervato_0; "AslpImageRvaToVa called with headers no"...
0x1800136d6  mov     r8d, 1565h
0x1800136dc  lea     rdx, aAslpimagervato; "AslpImageRvaToVa"
0x1800136e3  mov     ecx, 2
0x1800136e8  call    AslLogCallPrintf
0x1800136ed  mov     rdx, rbx
0x1800136f0  lea     rcx, [rsp+38h+arg_18]
0x1800136f5  call    AslpFileGetImageNtHeader
0x1800136fa  test    eax, eax
0x1800136fc  jns     short loc_18001372D
0x1800136fe  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x180013705  mov     [rsp+38h+var_18], eax
0x180013709  mov     r8d, 1569h
0x18001370f  lea     rdx, aAslpimagervato; "AslpImageRvaToVa"
0x180013716  mov     ecx, 1
0x18001371b  call    AslLogCallPrintf
0x180013720  xor     eax, eax
0x180013722  mov     rbx, [rsp+38h+arg_0]
0x180013727  add     rsp, 30h
0x18001372b  pop     rdi
0x18001372c  retn
0x18001372d  mov     r9, [rsp+38h+arg_18]
0x180013732  movzx   eax, word ptr [r9+14h]
0x180013737  lea     rdx, [r9+18h]
0x18001373b  movzx   r10d, word ptr [r9+6]
0x180013740  add     rdx, rax
0x180013743  xor     r8d, r8d
0x180013746  test    r10d, r10d
0x180013749  jz      short loc_180013720
0x18001374b  mov     ecx, [rdx+0Ch]
0x18001374e  cmp     edi, ecx
0x180013750  jb      short loc_180013759
0x180013752  add     ecx, [rdx+10h]
0x180013755  cmp     edi, ecx
0x180013757  jb      short loc_180013767
0x180013759  add     rdx, 28h ; '('
0x18001375d  inc     r8d
0x180013760  cmp     r8d, r10d
0x180013763  jb      short loc_18001374B
0x180013765  jmp     short loc_180013720
0x180013767  test    rdx, rdx
0x18001376a  jz      short loc_180013720
0x18001376c  mov     ecx, [rdx+14h]
0x18001376f  sub     ecx, [rdx+0Ch]
0x180013772  add     ecx, edi
0x180013774  cmp     rcx, [rbx+18h]
0x180013778  jnb     short loc_180013720
0x18001377a  mov     rax, [rbx+20h]
0x18001377e  add     rax, rcx
0x180013781  jmp     short loc_180013722
```
