# KerbPackData(void *,ulong,ulong *,uchar * *)

- ea: `0x180013b20`
- end: `0x180013d26`
- name: `?KerbPackData@@YAJPEAXKPEAKPEAPEAE@Z`
- size: `518`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1800071a0`
- `0x180007b18`
- `0x18000fc70`
- `0x18002e8b8`
- `0x180030efc`
- `0x180031534`
- `0x180031678`
- `0x180031b70`
- `0x180035dc0`
- `0x1800372f0`

## callees

- `0x180013b20`
- `0x180021a54`
- `0x180023ce0`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `MSASN1!ASN1_CreateEncoder` at `0x180013bc8`
- `MSASN1!ASN1_CreateEncoder` at `0x180013bc8`
- `MSASN1!ASN1_CloseEncoder` at `0x180013d13`
- `MSASN1!ASN1_CloseEncoder` at `0x180013d13`
- `MSASN1!ASN1_Encode` at `0x180013c28`
- `MSASN1!ASN1_Encode` at `0x180013c28`
- `MSASN1!ASN1_FreeEncoded` at `0x180013d03`
- `MSASN1!ASN1_FreeEncoded` at `0x180013d03`
- `MSASN1!ASN1_CreateModule` at `0x180013b9f`
- `MSASN1!ASN1_CreateModule` at `0x180013b9f`

## pseudocode

```c
__int64 __fastcall KerbPackData(void *a1, unsigned int a2, unsigned int *a3, unsigned __int8 **a4)
{
  __int64 Module; // rax
  unsigned int Encoder; // eax
  unsigned int v10; // edi
  int v11; // eax
  size_t v12; // rbp
  unsigned __int8 *v13; // rbx
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned __int8 *v16; // rax
  _QWORD v18[7]; // [rsp+50h] [rbp-38h] BYREF

  v18[0] = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  Encoder = ASN1_CreateEncoder(Module, v18, 0, 0, 0);
  if ( Encoder )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, Encoder);
      v10 = 60;
      goto LABEL_21;
    }
    goto LABEL_12;
  }
  v11 = ASN1_Encode(v18[0], a1, a2, 16, 0, 0);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v11);
LABEL_12:
    v10 = 60;
    goto LABEL_21;
  }
  v12 = *(unsigned int *)(v18[0] + 28LL);
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v13 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v12);
  }
  else
  {
    v16 = (unsigned __int8 *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v12);
    v13 = v16;
    if ( v16 )
    {
      memset_0(v16, 0, v12);
      *a4 = v13;
      goto LABEL_19;
    }
  }
  *a4 = v13;
  if ( v13 )
  {
LABEL_19:
    v10 = 0;
    memcpy_0(v13, *(const void **)(v18[0] + 16LL), *(unsigned int *)(v18[0] + 28LL));
    v14 = v18[0];
    v15 = *(_DWORD *)(v18[0] + 28LL);
    goto LABEL_20;
  }
  v14 = v18[0];
  v10 = 60;
  v15 = 0;
LABEL_20:
  *a3 = v15;
  ASN1_FreeEncoded(v14, *(_QWORD *)(v14 + 16));
LABEL_21:
  if ( v18[0] )
    ASN1_CloseEncoder();
  return v10;
}

```

## disassembly

```asm
0x180013b20  push    rbx
0x180013b22  push    rbp
0x180013b23  push    rsi
0x180013b24  push    rdi
0x180013b25  push    r14
0x180013b27  sub     rsp, 60h
0x180013b2b  xor     r14d, r14d
0x180013b2e  mov     rdi, r9
0x180013b31  cmp     cs:?fKRB5ModuleStarted@@3HA, r14d; int fKRB5ModuleStarted
0x180013b38  mov     rsi, r8
0x180013b3b  mov     ebx, edx
0x180013b3d  mov     [rsp+88h+var_38], r14
0x180013b42  mov     rbp, rcx
0x180013b45  jnz     short loc_180013BAE
0x180013b47  mov     [rsp+88h+var_48], 32756B70h
0x180013b4f  lea     rax, qword_180049F80
0x180013b56  mov     [rsp+88h+var_50], rax
0x180013b5b  mov     edx, 400h
0x180013b60  lea     rax, off_180047030
0x180013b67  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180013b71  mov     [rsp+88h+var_58], rax
0x180013b76  mov     ecx, 10000h
0x180013b7b  lea     rax, off_1800471C0
0x180013b82  mov     r9d, 31h ; '1'
0x180013b88  mov     [rsp+88h+var_60], rax
0x180013b8d  mov     r8d, 1000h
0x180013b93  lea     rax, off_180047350
0x180013b9a  mov     [rsp+88h+var_68], rax
0x180013b9f  call    cs:__imp_ASN1_CreateModule
0x180013ba5  mov     cs:PKU2UMSG_Module, rax
0x180013bac  jmp     short loc_180013BB5
0x180013bae  mov     rax, cs:PKU2UMSG_Module
0x180013bb5  xor     r9d, r9d
0x180013bb8  mov     [rsp+88h+var_68], r14
0x180013bbd  xor     r8d, r8d
0x180013bc0  lea     rdx, [rsp+88h+var_38]
0x180013bc5  mov     rcx, rax
0x180013bc8  call    cs:__imp_ASN1_CreateEncoder
0x180013bce  test    eax, eax
0x180013bd0  jz      short loc_180013C0D
0x180013bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bd9  lea     rdx, WPP_GLOBAL_Control
0x180013be0  cmp     rcx, rdx
0x180013be3  jz      short loc_180013C63
0x180013be5  test    byte ptr [rcx+1Ch], 1
0x180013be9  jz      short loc_180013C63
0x180013beb  mov     rcx, [rcx+10h]
0x180013bef  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180013bf6  mov     edx, 4Dh ; 'M'
0x180013bfb  mov     r9d, eax
0x180013bfe  call    WPP_SF_d
0x180013c03  mov     edi, 3Ch ; '<'
0x180013c08  jmp     loc_180013D09
0x180013c0d  mov     rcx, [rsp+88h+var_38]
0x180013c12  mov     r9d, 10h
0x180013c18  mov     dword ptr [rsp+88h+var_60], r14d
0x180013c1d  mov     r8d, ebx
0x180013c20  mov     rdx, rbp
0x180013c23  mov     [rsp+88h+var_68], r14
0x180013c28  call    cs:__imp_ASN1_Encode
0x180013c2e  test    eax, eax
0x180013c30  jns     short loc_180013C6D
0x180013c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c39  lea     rdx, WPP_GLOBAL_Control
0x180013c40  cmp     rcx, rdx
0x180013c43  jz      short loc_180013C63
0x180013c45  test    byte ptr [rcx+1Ch], 1
0x180013c49  jz      short loc_180013C63
0x180013c4b  mov     rcx, [rcx+10h]
0x180013c4f  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180013c56  mov     edx, 4Eh ; 'N'
0x180013c5b  mov     r9d, eax
0x180013c5e  call    WPP_SF_d
0x180013c63  mov     edi, 3Ch ; '<'
0x180013c68  jmp     loc_180013D09
0x180013c6d  mov     rax, [rsp+88h+var_38]
0x180013c72  mov     ebp, [rax+1Ch]
0x180013c75  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180013c7c  cmp     dword ptr [rax+0D0h], 1
0x180013c83  jnz     short loc_180013CB4
0x180013c85  mov     rax, [rax+0F0h]
0x180013c8c  mov     ecx, ebp
0x180013c8e  mov     rax, [rax+180h]
0x180013c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c9a  mov     rbx, rax
0x180013c9d  mov     [rdi], rbx
0x180013ca0  test    rbx, rbx
0x180013ca3  jnz     short loc_180013CDD
0x180013ca5  mov     rcx, [rsp+88h+var_38]
0x180013caa  mov     edi, 3Ch ; '<'
0x180013caf  mov     eax, r14d
0x180013cb2  jmp     short loc_180013CFD
0x180013cb4  mov     rax, [rax+0F8h]
0x180013cbb  mov     ecx, ebp
0x180013cbd  mov     rax, [rax]
0x180013cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cc5  mov     rbx, rax
0x180013cc8  test    rax, rax
0x180013ccb  jz      short loc_180013C9D
0x180013ccd  mov     r8, rbp; Size
0x180013cd0  xor     edx, edx; Val
0x180013cd2  mov     rcx, rax; void *
0x180013cd5  call    memset_0
0x180013cda  mov     [rdi], rbx
0x180013cdd  mov     rdx, [rsp+88h+var_38]
0x180013ce2  mov     rcx, rbx; void *
0x180013ce5  mov     edi, r14d
0x180013ce8  mov     r8d, [rdx+1Ch]; Size
0x180013cec  mov     rdx, [rdx+10h]; Src
0x180013cf0  call    memcpy_0
0x180013cf5  mov     rcx, [rsp+88h+var_38]
0x180013cfa  mov     eax, [rcx+1Ch]
0x180013cfd  mov     [rsi], eax
0x180013cff  mov     rdx, [rcx+10h]
0x180013d03  call    cs:__imp_ASN1_FreeEncoded
0x180013d09  mov     rcx, [rsp+88h+var_38]
0x180013d0e  test    rcx, rcx
0x180013d11  jz      short loc_180013D19
0x180013d13  call    cs:__imp_ASN1_CloseEncoder
0x180013d19  mov     eax, edi
0x180013d1b  add     rsp, 60h
0x180013d1f  pop     r14
0x180013d21  pop     rdi
0x180013d22  pop     rsi
0x180013d23  pop     rbp
0x180013d24  pop     rbx
0x180013d25  retn
```
