# EfsFilePostCreate

- ea: `0x140051de0`
- end: `0x140052026`
- name: `EfsFilePostCreate`
- size: `582`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14000b5d0`
- `0x140051de0`
- `0x14005202c`
- `0x14005252c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140051fd8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140051fd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051fee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051fee`
- `ntoskrnl!SeExports` at `0x140051ee7`
- `ntoskrnl!RtlEqualSid` at `0x140051efe`
- `ntoskrnl!RtlEqualSid` at `0x140051efe`

## pseudocode

```c
__int64 __fastcall EfsFilePostCreate(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        void **a9)
{
  PSID *v9; // rsi
  int UserInformation; // edi
  int v11; // r13d
  _QWORD *v12; // rbx
  __int64 v13; // r12
  __int64 v14; // rax
  char v15; // r14
  void *v16; // rcx
  void *v17; // rcx
  int v19; // [rsp+88h] [rbp-29h] BYREF
  PSID *v20; // [rsp+90h] [rbp-21h] BYREF
  __int64 v21; // [rsp+98h] [rbp-19h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-9h] BYREF

  v9 = 0;
  UserInformation = a5;
  v11 = a3;
  v23 = 0;
  v19 = 2;
  v21 = 0;
  v22 = 0;
  v20 = 0;
  if ( !a9 )
    return (unsigned int)UserInformation;
  v12 = *a9;
  if ( *a9 )
  {
    if ( (unsigned int)a5 > 0x102 && a5 < 261 || !*(_DWORD *)v12 )
      goto LABEL_20;
    v13 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL);
    UserInformation = EfspPostCreateGetUserInformation(
                        (unsigned int)*(_QWORD *)(v13 + 8) + 32,
                        (unsigned int)&v23,
                        (unsigned int)&v20,
                        (unsigned int)&v21,
                        (__int64)&v22,
                        (__int64)&v19);
    if ( UserInformation >= 0 )
    {
      v14 = v12[1];
      if ( v14 && *(_DWORD *)(v14 + 4) == 1 )
      {
        v9 = v20;
        if ( (*(_DWORD *)v12 & 0xFFFFFFF) == 4 && (*(_BYTE *)(v14 + 14) & 3) != 0 )
        {
          v15 = 1;
        }
        else if ( !v20 || (v15 = 0, !RtlEqualSid(SeExports->SeLocalSystemSid, *v20)) )
        {
          UserInformation = -1073741790;
LABEL_20:
          *a9 = 0;
          v16 = (void *)v12[1];
          if ( v16 )
          {
            ExFreePoolWithTag(v16, 0);
            v12[1] = 0;
          }
          v17 = (void *)v12[2];
          if ( v17 )
          {
            ExFreePoolWithTag(v17, 0);
            v12[2] = 0;
          }
          ExFreeToNPagedLookasideList(&Lookaside, v12);
          goto LABEL_25;
        }
        if ( v15 != 1 )
          goto LABEL_20;
      }
      else
      {
        v15 = 0;
      }
      UserInformation = EfspPostCreate(
                          a1,
                          a2,
                          v11,
                          v13,
                          v23,
                          a6,
                          a4,
                          (__int64)&v20,
                          (__int64)&v21,
                          v22,
                          v19,
                          a7,
                          v15,
                          a8,
                          (__int64)v12);
    }
    v9 = v20;
    goto LABEL_20;
  }
LABEL_25:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v21 )
    SrpDeleteEnterpriseId();
  return (unsigned int)UserInformation;
}

```

## disassembly

```asm
0x140051de0  mov     rax, rsp
0x140051de3  mov     [rax+18h], rbx
0x140051de7  mov     [rax+20h], r9
0x140051deb  mov     [rax+10h], rdx
0x140051def  mov     [rax+8], rcx
0x140051df3  push    rbp
0x140051df4  push    rsi
0x140051df5  push    rdi
0x140051df6  push    r12
0x140051df8  push    r13
0x140051dfa  push    r14
0x140051dfc  push    r15
0x140051dfe  lea     rbp, [rax-3Fh]
0x140051e02  sub     rsp, 0B0h
0x140051e09  mov     r15, [rbp+37h+arg_40]
0x140051e10  xor     esi, esi
0x140051e12  mov     edi, [rbp+37h+arg_20]
0x140051e15  mov     r13, r8
0x140051e18  mov     [rbp+37h+var_40], 0
0x140051e20  mov     [rbp+37h+var_60], 2
0x140051e27  mov     [rbp+37h+var_50], 0
0x140051e2f  mov     [rbp+37h+var_48], 0
0x140051e37  mov     [rbp+37h+var_58], rsi
0x140051e3b  test    r15, r15
0x140051e3e  jz      loc_140052008
0x140051e44  mov     rbx, [r15]
0x140051e47  test    rbx, rbx
0x140051e4a  jz      loc_140051FE4
0x140051e50  cmp     edi, 102h
0x140051e56  jbe     short loc_140051E64
0x140051e58  cmp     edi, 105h
0x140051e5e  jl      loc_140051F89
0x140051e64  cmp     [rbx], esi
0x140051e66  jz      loc_140051F89
0x140051e6c  mov     rax, [r8+0B8h]
0x140051e73  lea     r9, [rbp+37h+var_50]
0x140051e77  lea     r8, [rbp+37h+var_58]
0x140051e7b  lea     rdx, [rbp+37h+var_40]
0x140051e7f  mov     r12, [rax+8]
0x140051e83  lea     rax, [rbp+37h+var_60]
0x140051e87  mov     [rsp+0E0h+var_B8], rax
0x140051e8c  lea     rax, [rbp+37h+var_48]
0x140051e90  mov     [rsp+0E0h+var_C0], rax
0x140051e95  mov     rcx, [r12+8]
0x140051e9a  add     rcx, 20h ; ' '
0x140051e9e  call    EfspPostCreateGetUserInformation
0x140051ea3  mov     edi, eax
0x140051ea5  test    eax, eax
0x140051ea7  js      loc_140051F85
0x140051ead  mov     rax, [rbx+8]
0x140051eb1  test    rax, rax
0x140051eb4  jz      short loc_140051F16
0x140051eb6  cmp     dword ptr [rax+4], 1
0x140051eba  jnz     short loc_140051F16
0x140051ebc  mov     ecx, [rbx]
0x140051ebe  mov     rsi, [rbp+37h+var_58]
0x140051ec2  and     ecx, 0FFFFFFFh
0x140051ec8  cmp     ecx, 4
0x140051ecb  jnz     short loc_140051ED8
0x140051ecd  test    byte ptr [rax+0Eh], 3
0x140051ed1  jz      short loc_140051ED8
0x140051ed3  mov     r14b, 1
0x140051ed6  jmp     short loc_140051F0E
0x140051ed8  test    rsi, rsi
0x140051edb  jnz     short loc_140051EE7
0x140051edd  mov     edi, 0C0000022h
0x140051ee2  jmp     loc_140051F89
0x140051ee7  mov     rax, cs:__imp_SeExports
0x140051eee  xor     r14b, r14b
0x140051ef1  mov     rdx, [rsi]; Sid2
0x140051ef4  mov     rcx, [rax]
0x140051ef7  mov     rcx, [rcx+108h]; Sid1
0x140051efe  call    cs:__imp_RtlEqualSid
0x140051f05  nop     dword ptr [rax+rax+00h]
0x140051f0a  test    al, al
0x140051f0c  jz      short loc_140051EDD
0x140051f0e  cmp     r14b, 1
0x140051f12  jz      short loc_140051F19
0x140051f14  jmp     short loc_140051F89
0x140051f16  xor     r14b, r14b
0x140051f19  mov     rax, [rbp+37h+arg_38]
0x140051f1d  mov     r9, r12
0x140051f20  mov     rdx, [rbp+37h+arg_8]
0x140051f24  mov     r8, r13
0x140051f27  mov     rcx, [rbp+37h+arg_0]
0x140051f2b  mov     [rsp+70h], rbx
0x140051f30  mov     [rsp+0E0h+var_78], rax
0x140051f35  mov     rax, [rbp+37h+arg_30]
0x140051f39  mov     byte ptr [rsp+0E0h+var_80], r14b
0x140051f3e  mov     qword ptr [rsp+0E0h+var_88], rax
0x140051f43  mov     eax, [rbp+37h+var_60]
0x140051f46  mov     dword ptr [rsp+0E0h+var_90], eax
0x140051f4a  mov     rax, [rbp+37h+var_48]
0x140051f4e  mov     qword ptr [rsp+0E0h+var_98], rax
0x140051f53  lea     rax, [rbp+37h+var_50]
0x140051f57  mov     [rsp+0E0h+var_A0], rax
0x140051f5c  lea     rax, [rbp+37h+var_58]
0x140051f60  mov     [rsp+0E0h+var_A8], rax
0x140051f65  mov     rax, [rbp+37h+arg_18]
0x140051f69  mov     [rsp+0E0h+var_B0], rax
0x140051f6e  mov     eax, [rbp+37h+arg_28]
0x140051f71  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140051f75  mov     rax, [rbp+37h+var_40]
0x140051f79  mov     [rsp+0E0h+var_C0], rax
0x140051f7e  call    EfspPostCreate
0x140051f83  mov     edi, eax
0x140051f85  mov     rsi, [rbp+37h+var_58]
0x140051f89  mov     qword ptr [r15], 0
0x140051f90  mov     rcx, [rbx+8]; P
0x140051f94  test    rcx, rcx
0x140051f97  jz      short loc_140051FAF
0x140051f99  xor     edx, edx; Tag
0x140051f9b  call    cs:__imp_ExFreePoolWithTag
0x140051fa2  nop     dword ptr [rax+rax+00h]
0x140051fa7  mov     qword ptr [rbx+8], 0
0x140051faf  mov     rcx, [rbx+10h]; P
0x140051fb3  test    rcx, rcx
0x140051fb6  jz      short loc_140051FCE
0x140051fb8  xor     edx, edx; Tag
0x140051fba  call    cs:__imp_ExFreePoolWithTag
0x140051fc1  nop     dword ptr [rax+rax+00h]
0x140051fc6  mov     qword ptr [rbx+10h], 0
0x140051fce  mov     rdx, rbx; Entry
0x140051fd1  lea     rcx, Lookaside; Lookaside
0x140051fd8  call    cs:__imp_ExFreeToNPagedLookasideList
0x140051fdf  nop     dword ptr [rax+rax+00h]
0x140051fe4  test    rsi, rsi
0x140051fe7  jz      short loc_140051FFA
0x140051fe9  xor     edx, edx; Tag
0x140051feb  mov     rcx, rsi; P
0x140051fee  call    cs:__imp_ExFreePoolWithTag
0x140051ff5  nop     dword ptr [rax+rax+00h]
0x140051ffa  mov     rcx, [rbp+37h+var_50]
0x140051ffe  test    rcx, rcx
0x140052001  jz      short loc_140052008
0x140052003  call    SrpDeleteEnterpriseId
0x140052008  mov     rbx, [rsp+0E0h+arg_10]
0x140052010  mov     eax, edi
0x140052012  add     rsp, 0B0h
0x140052019  pop     r15
0x14005201b  pop     r14
0x14005201d  pop     r13
0x14005201f  pop     r12
0x140052021  pop     rdi
0x140052022  pop     rsi
0x140052023  pop     rbp
0x140052024  retn
```
