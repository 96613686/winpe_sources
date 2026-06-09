# CUiccHandler2::GetValue(ushort const *,ulong *,uchar *,ulong const *)

- ea: `0x18002ff10`
- end: `0x180030119`
- name: `?GetValue@CUiccHandler2@@UEAAJPEBGPEAKPEAEPEBK@Z`
- size: `521`
- prototype: `__int64 __fastcall(CUiccHandler2 *this, char *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076a4`
- `0x180012e18`
- `0x18002ff10`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800300b0`
- `msvcrt!memcpy_s` at `0x1800300b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800300ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800300ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUiccHandler2::GetValue(
        CUiccHandler2 *this,
        char *a2,
        unsigned int *a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  signed __int64 v8; // r9
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // ecx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int16 **v14; // rax
  __int64 v15; // rdx
  __int16 *v16; // r9
  __int64 v17; // r8
  _WORD *v18; // rcx
  __int16 v19; // ax
  unsigned int v20; // ebx
  _WORD *v21; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  __int64 v24; // rax
  bool v25; // di
  void *v26; // rcx
  unsigned int v27; // eax
  void *v28; // rcx
  int v30; // [rsp+20h] [rbp-51h]
  rsize_t SourceSize; // [rsp+30h] [rbp-41h] BYREF
  void *Source; // [rsp+38h] [rbp-39h] BYREF
  void **p_Source; // [rsp+40h] [rbp-31h]
  void *v34; // [rsp+48h] [rbp-29h] BYREF
  char v35; // [rsp+50h] [rbp-21h]
  _OWORD v36[3]; // [rsp+58h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v8 = (char *)L"ProfileSelection" - a2;
  do
  {
    v9 = *(unsigned __int16 *)&a2[v8];
    v10 = *(unsigned __int16 *)a2 - v9;
    if ( v10 )
      break;
    a2 += 2;
  }
  while ( v9 );
  if ( v10 )
  {
    v20 = -2147024809;
    v22 = 521;
    goto LABEL_34;
  }
  memset(v36, 0, sizeof(v36));
  if ( a5 )
    v11 = *a5;
  else
    v11 = 0;
  v12 = (_QWORD *)*((_QWORD *)this + 6);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v12[1] - *v12) >> 4) <= v11 )
    std::vector<UiccKeySet>::_Xran();
  v13 = *v12 + 48LL * v11;
  v14 = *(__int16 ***)v13;
  v15 = 2147483646;
  if ( *(_QWORD *)(*(_QWORD *)v13 + 24LL) < 8u )
    v14 = (__int16 **)v13;
  v16 = *v14;
  v17 = 21;
  v18 = v36;
  do
  {
    if ( !v15 )
      break;
    v19 = *v16;
    if ( !*v16 )
      break;
    ++v16;
    *v18++ = v19;
    --v15;
    --v17;
  }
  while ( v17 );
  v20 = v17 == 0 ? 0x8007007A : 0;
  v21 = v18 - 1;
  if ( v17 )
    v21 = v18;
  *v21 = 0;
  if ( !v17 )
  {
    v22 = 526;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)v20,
      v30);
    return v20;
  }
  LODWORD(SourceSize) = 0;
  Source = 0;
  v20 = 0;
  v23 = (__int64 *)*((_QWORD *)this + 4);
  v24 = *v23;
  p_Source = &Source;
  v34 = 0;
  v35 = 1;
  v25 = (*(int (__fastcall **)(__int64 *, _OWORD *, rsize_t *, void **))(v24 + 56))(v23, v36, &SourceSize, &v34) >= 0;
  if ( v35 )
  {
    v26 = *p_Source;
    *p_Source = v34;
    if ( v26 )
      CoTaskMemFree(v26);
  }
  if ( v25 )
  {
    v27 = SourceSize;
    if ( (_DWORD)SourceSize )
    {
      if ( *a3 && *a3 < (unsigned int)SourceSize )
      {
        v20 = -2147024774;
      }
      else
      {
        if ( memcpy_s(a4, (unsigned int)SourceSize, Source, (unsigned int)SourceSize) )
          v20 = -2147024774;
        v27 = SourceSize;
      }
      *a3 = v27;
    }
  }
  v28 = Source;
  Source = 0;
  if ( v28 )
    CoTaskMemFree(v28);
  return v20;
}

```

## disassembly

```asm
0x18002ff10  push    rbp
0x18002ff12  push    rbx
0x18002ff13  push    rsi
0x18002ff14  push    rdi
0x18002ff15  push    r12
0x18002ff17  push    r14
0x18002ff19  push    r15
0x18002ff1b  lea     rbp, [rsp-1Fh]
0x18002ff20  sub     rsp, 90h
0x18002ff27  mov     rax, cs:__security_cookie
0x18002ff2e  xor     rax, rsp
0x18002ff31  mov     [rbp+4Fh+var_38], rax
0x18002ff35  mov     r14, r9
0x18002ff38  mov     rsi, r8
0x18002ff3b  mov     r10, rcx
0x18002ff3e  lea     r9, ?gc_wszProfileSelection@@3QBGB; "ProfileSelection"
0x18002ff45  sub     r9, rdx
0x18002ff48  movzx   ecx, word ptr [rdx]
0x18002ff4b  movzx   eax, word ptr [rdx+r9]
0x18002ff50  sub     ecx, eax
0x18002ff52  jnz     short loc_18002FF5C
0x18002ff54  add     rdx, 2
0x18002ff58  test    eax, eax
0x18002ff5a  jnz     short loc_18002FF48
0x18002ff5c  xor     r15d, r15d
0x18002ff5f  test    ecx, ecx
0x18002ff61  jnz     loc_1800300D6
0x18002ff67  xorps   xmm0, xmm0
0x18002ff6a  movups  [rbp+4Fh+var_68], xmm0
0x18002ff6e  movups  [rbp+4Fh+var_58], xmm0
0x18002ff72  movups  [rbp+4Fh+var_48], xmm0
0x18002ff76  mov     rax, [rbp+4Fh+arg_20]
0x18002ff7a  test    rax, rax
0x18002ff7d  jz      short loc_18002FF83
0x18002ff7f  mov     ecx, [rax]
0x18002ff81  jmp     short loc_18002FF86
0x18002ff83  mov     ecx, r15d
0x18002ff86  mov     rax, [r10+30h]
0x18002ff8a  mov     r8, [rax]
0x18002ff8d  mov     edx, ecx
0x18002ff8f  mov     rcx, [rax+8]
0x18002ff93  sub     rcx, r8
0x18002ff96  sar     rcx, 4
0x18002ff9a  mov     rax, 0AAAAAAAAAAAAAAABh
0x18002ffa4  imul    rcx, rax
0x18002ffa8  cmp     rcx, rdx
0x18002ffab  jbe     loc_180030113
0x18002ffb1  lea     rcx, [rdx+rdx*2]
0x18002ffb5  shl     rcx, 4
0x18002ffb9  add     rcx, r8
0x18002ffbc  mov     rax, [rcx]
0x18002ffbf  mov     edx, 7FFFFFFEh
0x18002ffc4  cmp     qword ptr [rax+18h], 8
0x18002ffc9  cmovb   rax, rcx
0x18002ffcd  mov     r9, [rax]
0x18002ffd0  mov     r8d, 15h
0x18002ffd6  lea     rcx, [rbp+4Fh+var_68]
0x18002ffda  test    rdx, rdx
0x18002ffdd  jz      short loc_18002FFFC
0x18002ffdf  movzx   eax, word ptr [r9]
0x18002ffe3  test    ax, ax
0x18002ffe6  jz      short loc_18002FFFC
0x18002ffe8  add     r9, 2
0x18002ffec  mov     [rcx], ax
0x18002ffef  add     rcx, 2
0x18002fff3  dec     rdx
0x18002fff6  sub     r8, 1
0x18002fffa  jnz     short loc_18002FFDA
0x18002fffc  mov     rax, r8
0x18002ffff  neg     rax
0x180030002  sbb     ebx, ebx
0x180030004  not     ebx
0x180030006  mov     r12d, 8007007Ah
0x18003000c  and     ebx, r12d
0x18003000f  lea     rdx, [rcx-2]
0x180030013  test    r8, r8
0x180030016  cmovnz  rdx, rcx
0x18003001a  mov     [rdx], r15w
0x18003001e  jnz     short loc_18003002A
0x180030020  mov     edx, 20Eh
0x180030025  jmp     loc_1800300E0
0x18003002a  mov     dword ptr [rbp+4Fh+SourceSize], r15d
0x18003002e  mov     [rbp+4Fh+Source], r15
0x180030032  mov     ebx, r15d
0x180030035  mov     rcx, [r10+20h]
0x180030039  mov     rax, [rcx]
0x18003003c  lea     rdx, [rbp+4Fh+Source]
0x180030040  mov     [rbp+4Fh+var_80], rdx
0x180030044  mov     [rbp+4Fh+var_78], r15
0x180030048  mov     [rbp+4Fh+var_70], 1
0x18003004c  lea     r9, [rbp+4Fh+var_78]
0x180030050  lea     r8, [rbp+4Fh+SourceSize]
0x180030054  lea     rdx, [rbp+4Fh+var_68]
0x180030058  mov     rax, [rax+38h]
0x18003005c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030061  mov     edi, eax
0x180030063  shr     edi, 1Fh
0x180030066  xor     dil, 1
0x18003006a  cmp     [rbp+4Fh+var_70], r15b
0x18003006e  jz      short loc_180030089
0x180030070  mov     r8, [rbp+4Fh+var_80]
0x180030074  mov     rcx, [r8]; pv
0x180030077  mov     rdx, [rbp+4Fh+var_78]
0x18003007b  mov     [r8], rdx
0x18003007e  test    rcx, rcx
0x180030081  jz      short loc_180030089
0x180030083  call    cs:__imp_CoTaskMemFree
0x180030089  test    dil, dil
0x18003008c  jz      short loc_1800300C1
0x18003008e  mov     eax, dword ptr [rbp+4Fh+SourceSize]
0x180030091  test    eax, eax
0x180030093  jz      short loc_1800300C1
0x180030095  cmp     [rsi], r15d
0x180030098  jbe     short loc_1800300A3
0x18003009a  cmp     [rsi], eax
0x18003009c  jnb     short loc_1800300A3
0x18003009e  mov     ebx, r12d
0x1800300a1  jmp     short loc_1800300BF
0x1800300a3  mov     rdx, rax; DestinationSize
0x1800300a6  mov     r9, rax; SourceSize
0x1800300a9  mov     r8, [rbp+4Fh+Source]; Source
0x1800300ad  mov     rcx, r14; Destination
0x1800300b0  call    cs:__imp_memcpy_s
0x1800300b6  test    eax, eax
0x1800300b8  cmovnz  ebx, r12d
0x1800300bc  mov     eax, dword ptr [rbp+4Fh+SourceSize]
0x1800300bf  mov     [rsi], eax
0x1800300c1  mov     rcx, [rbp+4Fh+Source]; pv
0x1800300c5  mov     [rbp+4Fh+Source], r15
0x1800300c9  test    rcx, rcx
0x1800300cc  jz      short loc_1800300F3
0x1800300ce  call    cs:__imp_CoTaskMemFree
0x1800300d4  jmp     short loc_1800300F3
0x1800300d6  mov     ebx, 80070057h
0x1800300db  mov     edx, 209h; void *
0x1800300e0  mov     r9d, ebx; char *
0x1800300e3  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800300ea  mov     rcx, [rbp+57h]; this
0x1800300ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800300f3  mov     eax, ebx
0x1800300f5  mov     rcx, [rbp+4Fh+var_38]
0x1800300f9  xor     rcx, rsp; StackCookie
0x1800300fc  call    __security_check_cookie
0x180030101  add     rsp, 90h
0x180030108  pop     r15
0x18003010a  pop     r14
0x18003010c  pop     r12
0x18003010e  pop     rdi
0x18003010f  pop     rsi
0x180030110  pop     rbx
0x180030111  pop     rbp
0x180030112  retn
0x180030113  call    ?_Xran@?$vector@UUiccKeySet@@V?$allocator@UUiccKeySet@@@std@@@std@@IEBAXXZ; std::vector<UiccKeySet>::_Xran(void)
```
