# TransformOldFile_PE_ResourcesOldCompatible

- ea: `0x180006858`
- end: `0x18000691f`
- name: `TransformOldFile_PE_ResourcesOldCompatible`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000541c`

## callees

- `0x180001cae`
- `0x180004cc4`
- `0x180004db8`
- `0x180004e98`
- `0x180006858`
- `0x180006a60`

## pseudocode

```c
__int64 __fastcall TransformOldFile_PE_ResourcesOldCompatible(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v6; // rdi
  __int64 result; // rax
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rax
  __int64 v12; // r11
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+38h] [rbp-38h]
  unsigned __int64 v15; // [rsp+40h] [rbp-30h]
  unsigned int v16[4]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h]
  unsigned int v18; // [rsp+60h] [rbp-10h]
  int NewRvaFromRiftTable; // [rsp+64h] [rbp-Ch]
  int v20; // [rsp+68h] [rbp-8h]

  v6 = a3;
  memset_0(&v13, 0, 0x40u);
  result = ImageDirectoryMappedAddress(a1, 2, v16, a2, v6);
  v14 = result;
  if ( result && v16[0] >= 0x10 )
  {
    v10 = a2 + v6;
    v11 = v16[0] + result;
    v16[1] = 0;
    if ( v11 < a2 + v6 )
      v10 = v11;
    v15 = v10;
    v18 = ImageDirectoryRvaAndSize(a1, 2, 0, a2, v6);
    NewRvaFromRiftTable = GetNewRvaFromRiftTable(a5, v18);
    v16[3] = *(_DWORD *)(a1 + 80);
    v16[2] = a4;
    v17 = a2;
    v13 = v12;
    v20 = 0;
    return TransformResourceRecursiveOldCompatible(&v13, v14);
  }
  return result;
}

```

## disassembly

```asm
0x180006858  push    rbp
0x18000685a  push    rbx
0x18000685b  push    rsi
0x18000685c  push    rdi
0x18000685d  push    r14
0x18000685f  mov     rbp, rsp
0x180006862  sub     rsp, 70h
0x180006866  mov     rbx, rdx
0x180006869  mov     edi, r8d
0x18000686c  xor     edx, edx; Val
0x18000686e  mov     rsi, rcx
0x180006871  lea     rcx, [rbp+var_40]; void *
0x180006875  mov     r14d, r9d
0x180006878  lea     r8d, [rdx+40h]; Size
0x18000687c  call    memset_0
0x180006881  mov     r9, rbx
0x180006884  mov     [rsp+70h+var_50], edi
0x180006888  lea     r8, [rbp+var_28]
0x18000688c  mov     edx, 2
0x180006891  mov     rcx, rsi
0x180006894  call    ImageDirectoryMappedAddress
0x180006899  mov     [rbp+var_38], rax
0x18000689d  test    rax, rax
0x1800068a0  jz      short loc_180006914
0x1800068a2  cmp     [rbp+var_28], 10h
0x1800068a6  jb      short loc_180006914
0x1800068a8  mov     ecx, [rbp+var_28]
0x1800068ab  lea     r8, [rbx+rdi]
0x1800068af  add     rax, rcx
0x1800068b2  mov     [rbp+var_24], 0
0x1800068b9  cmp     rax, r8
0x1800068bc  mov     [rsp+70h+var_50], edi
0x1800068c0  mov     r9, rbx
0x1800068c3  mov     rcx, rsi
0x1800068c6  cmovb   r8, rax
0x1800068ca  mov     [rbp+var_30], r8
0x1800068ce  xor     r8d, r8d
0x1800068d1  lea     edx, [r8+2]
0x1800068d5  call    ImageDirectoryRvaAndSize
0x1800068da  mov     r11, [rbp+arg_20]
0x1800068de  mov     edx, eax
0x1800068e0  mov     rcx, r11
0x1800068e3  mov     [rbp+var_10], eax
0x1800068e6  call    GetNewRvaFromRiftTable
0x1800068eb  mov     rdx, [rbp+var_38]
0x1800068ef  lea     rcx, [rbp+var_40]
0x1800068f3  mov     [rbp+var_C], eax
0x1800068f6  mov     eax, [rsi+50h]
0x1800068f9  mov     [rbp+var_1C], eax
0x1800068fc  mov     [rbp+var_20], r14d
0x180006900  mov     [rbp+var_18], rbx
0x180006904  mov     [rbp+var_40], r11
0x180006908  mov     [rbp+var_8], 0
0x18000690f  call    TransformResourceRecursiveOldCompatible
0x180006914  add     rsp, 70h
0x180006918  pop     r14
0x18000691a  pop     rdi
0x18000691b  pop     rsi
0x18000691c  pop     rbx
0x18000691d  pop     rbp
0x18000691e  retn
```
