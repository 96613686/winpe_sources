# CipValidateDataMappedFile

- ea: `0x180097958`
- end: `0x180097ae2`
- name: `CipValidateDataMappedFile`
- size: `394`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800638d4`
- `0x180097690`

## callees

- `0x180097958`
- `0x180097ae8`
- `0x180097b24`
- `0x180097d10`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800979ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800979ec`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180097995`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180097995`

## pseudocode

```c
__int64 __fastcall CipValidateDataMappedFile(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned int a4,
        char a5,
        char a6,
        int a7,
        _DWORD *a8,
        _OWORD *a9,
        int a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        _DWORD *a14)
{
  unsigned int v15; // esi
  struct _UNICODE_STRING *v17; // rax
  struct _UNICODE_STRING *v18; // rdi
  int v19; // ebx
  _OWORD *v21; // rdx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  char v25; // [rsp+28h] [rbp-30h]
  char v26; // [rsp+30h] [rbp-28h]
  __int64 v27; // [rsp+70h] [rbp+18h] BYREF

  v27 = 0;
  v15 = a2;
  if ( a2 > 0xFFFFFFFF )
  {
    return (unsigned int)-1073741701;
  }
  else
  {
    v17 = (struct _UNICODE_STRING *)ExAllocateFromPagedLookasideList(&g_CiValidationLookasideList);
    v18 = v17;
    if ( v17 )
    {
      v19 = CiInitializeValidationContext(a4, 0, v17);
      *(_QWORD *)&v18[190].Length = 0;
      *(_QWORD *)&v18[207].Length = 0;
      v18[189].Buffer = (PWSTR)&off_18002EE80;
      if ( v19 >= 0 )
      {
        RtlInitUnicodeString(v18 + 53, 0);
        LODWORD(v18[190].Buffer) |= 0x80u;
        v26 = a6;
        v25 = a5;
        v18[42].Buffer = 0;
        *(_QWORD *)&v18[206].Length = 0;
        v19 = CipValidateDataMappedFileWithContext(v18, a1, v15, 0, a4, v25, v26, &v27);
        if ( v19 >= 0 )
        {
          v21 = (_OWORD *)v27;
          if ( a8 )
            *a8 = *(_DWORD *)(v27 + 48);
          v22 = a9;
          if ( a9 )
          {
            v23 = v21[1];
            *a9 = *v21;
            v24 = v21[2];
            v22[1] = v23;
            *v21 = 0;
            v21[1] = 0;
            v21[2] = 0;
            v22[2] = v24;
          }
          if ( a14 )
            *a14 = *(_DWORD *)&v18[188].Length;
        }
      }
      CiFreeValidationContext((void (***)(void))v18);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180097958  mov     rax, rsp
0x18009795b  mov     [rax+8], rbx
0x18009795f  mov     [rax+10h], rbp
0x180097963  mov     [rax+18h], r8
0x180097967  push    rsi
0x180097968  push    rdi
0x180097969  push    r14
0x18009796b  sub     rsp, 40h
0x18009796f  mov     qword ptr [rax+18h], 0
0x180097977  mov     ebp, r9d
0x18009797a  mov     eax, 0FFFFFFFFh
0x18009797f  mov     rsi, rdx
0x180097982  mov     r14, rcx
0x180097985  cmp     rdx, rax
0x180097988  ja      loc_180097A6F
0x18009798e  lea     rcx, g_CiValidationLookasideList; Lookaside
0x180097995  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009799c  nop     dword ptr [rax+rax+00h]
0x1800979a1  mov     rdi, rax
0x1800979a4  test    rax, rax
0x1800979a7  jz      loc_180097AD8
0x1800979ad  mov     r8, rax
0x1800979b0  xor     edx, edx
0x1800979b2  mov     ecx, ebp
0x1800979b4  call    CiInitializeValidationContext
0x1800979b9  mov     ebx, eax
0x1800979bb  mov     qword ptr [rdi+0BE0h], 0
0x1800979c6  mov     qword ptr [rdi+0CF0h], 0
0x1800979d1  lea     rax, off_18002EE80
0x1800979d8  mov     [rdi+0BD8h], rax
0x1800979df  test    ebx, ebx
0x1800979e1  js      short loc_180097A51
0x1800979e3  lea     rcx, [rdi+350h]; DestinationString
0x1800979ea  xor     edx, edx; SourceString
0x1800979ec  call    cs:__imp_RtlInitUnicodeString
0x1800979f3  nop     dword ptr [rax+rax+00h]
0x1800979f8  bts     dword ptr [rdi+0BE8h], 7
0x180097a00  lea     rax, [rsp+58h+arg_10]
0x180097a05  mov     [rsp+58h+var_20], rax
0x180097a0a  xor     r9d, r9d
0x180097a0d  mov     al, [rsp+58h+arg_28]
0x180097a14  mov     rdx, r14
0x180097a17  mov     [rsp+58h+var_28], al
0x180097a1b  mov     rcx, rdi
0x180097a1e  mov     al, [rsp+58h+arg_20]
0x180097a25  mov     [rsp+58h+var_30], al
0x180097a29  mov     r8d, esi
0x180097a2c  mov     [rsp+58h+var_38], ebp
0x180097a30  mov     qword ptr [rdi+2A8h], 0
0x180097a3b  mov     qword ptr [rdi+0CE0h], 0
0x180097a46  call    CipValidateDataMappedFileWithContext
0x180097a4b  mov     ebx, eax
0x180097a4d  test    eax, eax
0x180097a4f  jns     short loc_180097A76
0x180097a51  mov     rcx, rdi; Entry
0x180097a54  call    CiFreeValidationContext
0x180097a59  mov     rbp, [rsp+58h+arg_8]
0x180097a5e  mov     eax, ebx
0x180097a60  mov     rbx, [rsp+58h+arg_0]
0x180097a65  add     rsp, 40h
0x180097a69  pop     r14
0x180097a6b  pop     rdi
0x180097a6c  pop     rsi
0x180097a6d  retn
0x180097a6f  mov     ebx, 0C000007Bh
0x180097a74  jmp     short loc_180097A59
0x180097a76  mov     rax, [rsp+58h+arg_38]
0x180097a7e  mov     rdx, [rsp+58h+arg_10]
0x180097a83  test    rax, rax
0x180097a86  jz      short loc_180097A8D
0x180097a88  mov     ecx, [rdx+30h]
0x180097a8b  mov     [rax], ecx
0x180097a8d  mov     rax, [rsp+58h+arg_40]
0x180097a95  test    rax, rax
0x180097a98  jz      short loc_180097ABE
0x180097a9a  movups  xmm0, xmmword ptr [rdx]
0x180097a9d  movups  xmm1, xmmword ptr [rdx+10h]
0x180097aa1  movups  xmmword ptr [rax], xmm0
0x180097aa4  movups  xmm0, xmmword ptr [rdx+20h]
0x180097aa8  movups  xmmword ptr [rax+10h], xmm1
0x180097aac  xorps   xmm1, xmm1
0x180097aaf  movups  xmmword ptr [rdx], xmm1
0x180097ab2  movups  xmmword ptr [rdx+10h], xmm1
0x180097ab6  movups  xmmword ptr [rdx+20h], xmm1
0x180097aba  movups  xmmword ptr [rax+20h], xmm0
0x180097abe  mov     rcx, [rsp+58h+arg_68]
0x180097ac6  test    rcx, rcx
0x180097ac9  jz      short loc_180097A51
0x180097acb  mov     eax, [rdi+0BC0h]
0x180097ad1  mov     [rcx], eax
0x180097ad3  jmp     loc_180097A51
0x180097ad8  mov     ebx, 0C0000017h
0x180097add  jmp     loc_180097A59
```
