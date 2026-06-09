# SeEncodeSamClaimsBlob

- ea: `0x1400598a4`
- end: `0x140059ac7`
- name: `SeEncodeSamClaimsBlob`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140059730`

## callees

- `0x14004aae0`
- `0x1400598a4`
- `0x140059ad0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400599bd`
- `ntoskrnl!ExAllocatePool2` at `0x1400599bd`
- `msrpc!MesHandleFree` at `0x140059a9a`
- `msrpc!MesHandleFree` at `0x140059a9a`
- `msrpc!NdrMesTypeEncode3` at `0x140059a4a`
- `msrpc!NdrMesTypeEncode3` at `0x140059a4a`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x140059933`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x140059933`
- `msrpc!NdrMesTypeAlignSize3` at `0x14005997b`
- `msrpc!NdrMesTypeAlignSize3` at `0x14005997b`
- `msrpc!MesBufferHandleReset` at `0x140059a08`
- `msrpc!MesBufferHandleReset` at `0x140059a08`

## pseudocode

```c
__int64 __fastcall SeEncodeSamClaimsBlob(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  void *v5; // rdi
  int v6; // ebx
  __int64 v7; // r15
  __int64 Pool2; // rax
  __int64 v10; // [rsp+30h] [rbp-78h] BYREF
  __int64 v11; // [rsp+38h] [rbp-70h] BYREF
  __int64 v12; // [rsp+40h] [rbp-68h]
  __int64 v13; // [rsp+48h] [rbp-60h]
  void **v14; // [rsp+50h] [rbp-58h] BYREF
  void *v15[2]; // [rsp+58h] [rbp-50h] BYREF
  __int128 v16; // [rsp+68h] [rbp-40h] BYREF
  __int64 v17; // [rsp+78h] [rbp-30h]
  int v18; // [rsp+C8h] [rbp+20h] BYREF

  v11 = 0;
  v18 = 0;
  v5 = 0;
  v12 = 0;
  v13 = 0;
  v10 = 0;
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v17 = 0;
  v14 = v15;
  *a2 = 0;
  *a3 = 0;
  v6 = SeEncodeSamClaimsSet(a1, (char *)&v16 + 4, &v15[1]);
  if ( v6 )
    goto LABEL_8;
  LODWORD(v15[0]) = DWORD1(v16);
  if ( (unsigned int)MesEncodeDynBufferHandleCreate(&v11, &v18, &v10) )
  {
LABEL_3:
    v6 = -1073741823;
    goto LABEL_9;
  }
  v7 = NdrMesTypeAlignSize3(v10, "TP 3\a", &off_1400624E0, &off_1400701A8, 1, &v14);
  v13 = v7;
  Pool2 = ExAllocatePool2(66, v7, 1834185815);
  v5 = (void *)Pool2;
  v12 = Pool2;
  if ( Pool2 )
  {
    v11 = Pool2;
    v6 = MesBufferHandleReset(v10, 1, 0, &v11, v7, &v18);
    if ( v6 )
      goto LABEL_3;
    NdrMesTypeEncode3(v10, "TP 3\a", &off_1400624E0, &off_1400701A8, 1, &v14);
    *a3 = v5;
    *a2 = v18;
LABEL_8:
    if ( v6 >= 0 )
      goto LABEL_11;
    goto LABEL_9;
  }
  v6 = -1073741801;
LABEL_9:
  if ( v5 )
    MIDL_user_free(v5);
LABEL_11:
  MesHandleFree(v10);
  if ( v15[1] )
    MIDL_user_free(v15[1]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400598a4  mov     r11, rsp
0x1400598a7  mov     [r11+18h], r8
0x1400598ab  mov     [r11+10h], rdx
0x1400598af  push    rbx
0x1400598b0  push    rsi
0x1400598b1  push    rdi
0x1400598b2  push    r14
0x1400598b4  push    r15
0x1400598b6  sub     rsp, 80h
0x1400598bd  mov     rsi, r8
0x1400598c0  mov     r14, rdx
0x1400598c3  mov     qword ptr [r11-70h], 0
0x1400598cb  mov     dword ptr [r11+20h], 0
0x1400598d3  xor     edi, edi
0x1400598d5  mov     [rsp+0A8h+var_68], rdi
0x1400598da  mov     [r11-60h], rdi
0x1400598de  mov     [r11-78h], rdi
0x1400598e2  xorps   xmm0, xmm0
0x1400598e5  xor     eax, eax
0x1400598e7  movups  xmmword ptr [rsp+0A8h+var_50], xmm0
0x1400598ec  movups  [rsp+0A8h+var_40], xmm0
0x1400598f1  mov     [r11-30h], rax
0x1400598f5  lea     rax, [r11-50h]
0x1400598f9  mov     [r11-58h], rax
0x1400598fd  mov     [rdx], edi
0x1400598ff  mov     [r8], rdi
0x140059902  lea     r8, [r11-48h]
0x140059906  lea     rdx, [r11-3Ch]
0x14005990a  call    SeEncodeSamClaimsSet
0x14005990f  mov     ebx, eax
0x140059911  test    eax, eax
0x140059913  jnz     loc_140059A84
0x140059919  mov     eax, dword ptr [rsp+0A8h+var_40+4]
0x14005991d  mov     dword ptr [rsp+0A8h+var_50], eax
0x140059921  lea     r8, [rsp+0A8h+var_78]
0x140059926  lea     rdx, [rsp+0A8h+arg_18]
0x14005992e  lea     rcx, [rsp+0A8h+var_70]
0x140059933  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x14005993a  nop     dword ptr [rax+rax+00h]
0x14005993f  mov     ebx, eax
0x140059941  test    eax, eax
0x140059943  jz      short loc_14005994F
0x140059945  mov     ebx, 0C0000001h
0x14005994a  jmp     loc_140059A88
0x14005994f  lea     rax, [rsp+0A8h+var_58]
0x140059954  mov     [rsp+0A8h+var_80], rax
0x140059959  mov     [rsp+0A8h+var_88], 1
0x140059961  lea     r9, off_1400701A8
0x140059968  lea     r8, off_1400624E0
0x14005996f  lea     rdx, aTp3; "TP 3\a"
0x140059976  mov     rcx, [rsp+0A8h+var_78]
0x14005997b  call    cs:__imp_NdrMesTypeAlignSize3
0x140059982  nop     dword ptr [rax+rax+00h]
0x140059987  mov     r15, rax
0x14005998a  mov     [rsp+0A8h+var_60], rax
0x14005998f  jmp     short loc_1400599AD
0x140059991  mov     ebx, eax
0x140059993  mov     rsi, [rsp+0A8h+arg_10]
0x14005999b  mov     r14, [rsp+0A8h+arg_8]
0x1400599a3  mov     rdi, [rsp+0A8h+var_68]
0x1400599a8  mov     r15, [rsp+0A8h+var_60]
0x1400599ad  test    ebx, ebx
0x1400599af  jnz     short loc_140059945
0x1400599b1  mov     r8d, 6D537457h
0x1400599b7  mov     rdx, r15
0x1400599ba  lea     ecx, [rbx+42h]
0x1400599bd  call    cs:__imp_ExAllocatePool2
0x1400599c4  nop     dword ptr [rax+rax+00h]
0x1400599c9  mov     rdi, rax
0x1400599cc  mov     [rsp+0A8h+var_68], rax
0x1400599d1  test    rax, rax
0x1400599d4  jnz     short loc_1400599E0
0x1400599d6  mov     ebx, 0C0000017h
0x1400599db  jmp     loc_140059A88
0x1400599e0  mov     [rsp+0A8h+var_70], rax
0x1400599e5  lea     rax, [rsp+0A8h+arg_18]
0x1400599ed  mov     [rsp+0A8h+var_80], rax
0x1400599f2  mov     [rsp+0A8h+var_88], r15d
0x1400599f7  lea     r9, [rsp+0A8h+var_70]
0x1400599fc  xor     r8d, r8d
0x1400599ff  lea     edx, [r8+1]
0x140059a03  mov     rcx, [rsp+0A8h+var_78]
0x140059a08  call    cs:__imp_MesBufferHandleReset
0x140059a0f  nop     dword ptr [rax+rax+00h]
0x140059a14  mov     ebx, eax
0x140059a16  test    eax, eax
0x140059a18  jnz     loc_140059945
0x140059a1e  lea     rax, [rsp+0A8h+var_58]
0x140059a23  mov     [rsp+0A8h+var_80], rax
0x140059a28  mov     [rsp+0A8h+var_88], 1
0x140059a30  lea     r9, off_1400701A8
0x140059a37  lea     r8, off_1400624E0
0x140059a3e  lea     rdx, aTp3; "TP 3\a"
0x140059a45  mov     rcx, [rsp+0A8h+var_78]
0x140059a4a  call    cs:__imp_NdrMesTypeEncode3
0x140059a51  nop     dword ptr [rax+rax+00h]
0x140059a56  jmp     short loc_140059A6F
0x140059a58  mov     ebx, eax
0x140059a5a  mov     rsi, [rsp+0A8h+arg_10]
0x140059a62  mov     r14, [rsp+0A8h+arg_8]
0x140059a6a  mov     rdi, [rsp+0A8h+var_68]
0x140059a6f  test    ebx, ebx
0x140059a71  jnz     loc_140059945
0x140059a77  mov     [rsi], rdi
0x140059a7a  mov     eax, [rsp+0A8h+arg_18]
0x140059a81  mov     [r14], eax
0x140059a84  test    ebx, ebx
0x140059a86  jns     short loc_140059A95
0x140059a88  test    rdi, rdi
0x140059a8b  jz      short loc_140059A95
0x140059a8d  mov     rcx, rdi; void *
0x140059a90  call    MIDL_user_free
0x140059a95  mov     rcx, [rsp+0A8h+var_78]
0x140059a9a  call    cs:__imp_MesHandleFree
0x140059aa1  nop     dword ptr [rax+rax+00h]
0x140059aa6  mov     rcx, [rsp+0A8h+var_50+8]; void *
0x140059aab  test    rcx, rcx
0x140059aae  jz      short loc_140059AB5
0x140059ab0  call    MIDL_user_free
0x140059ab5  mov     eax, ebx
0x140059ab7  add     rsp, 80h
0x140059abe  pop     r15
0x140059ac0  pop     r14
0x140059ac2  pop     rdi
0x140059ac3  pop     rsi
0x140059ac4  pop     rbx
0x140059ac5  retn
0x14005a9a2  push    rbp
0x14005a9a4  sub     rsp, 30h
0x14005a9a8  mov     rbp, rdx
0x14005a9ab  mov     rcx, [rcx]
0x14005a9ae  mov     ecx, [rcx]; ExceptionCode
0x14005a9b0  call    cs:__imp_I_RpcExceptionFilter
0x14005a9b7  nop     dword ptr [rax+rax+00h]
0x14005a9bc  nop
0x14005a9bd  add     rsp, 30h
0x14005a9c1  pop     rbp
0x14005a9c2  retn
0x14005a9c4  push    rbp
0x14005a9c6  sub     rsp, 30h
0x14005a9ca  mov     rbp, rdx
0x14005a9cd  mov     rcx, [rcx]
0x14005a9d0  mov     ecx, [rcx]; ExceptionCode
0x14005a9d2  call    cs:__imp_I_RpcExceptionFilter
0x14005a9d9  nop     dword ptr [rax+rax+00h]
0x14005a9de  nop
0x14005a9df  add     rsp, 30h
0x14005a9e3  pop     rbp
0x14005a9e4  retn
```
