# CSecConLib::AddExtensionFile(ushort const *,bool,ushort const *,bool,ushort const *,ushort const *)

- ea: `0x18000e83c`
- end: `0x18000ec62`
- name: `?AddExtensionFile@CSecConLib@@QEAAJPEBG_N0100@Z`
- size: `1062`
- prototype: `__int64 __fastcall(CSecConLib *this, wchar_t *Source, char, const unsigned __int16 *, bool, wchar_t *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180008770`

## callees

- `0x180001048`
- `0x180001054`
- `0x18000e83c`
- `0x18000f02c`
- `0x18000f1c0`
- `0x18001011c`
- `0x1800111a2`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000eae0`
- `msvcrt!_wcsnicmp` at `0x18000eae0`
- `msvcrt!wcscpy_s` at `0x18000e94b`
- `msvcrt!wcscpy_s` at `0x18000eacd`
- `msvcrt!wcscpy_s` at `0x18000eb5b`
- `msvcrt!wcscpy_s` at `0x18000e94b`
- `msvcrt!wcscpy_s` at `0x18000eacd`
- `msvcrt!wcscpy_s` at `0x18000eb5b`
- `msvcrt!wcscat_s` at `0x18000e961`
- `msvcrt!wcscat_s` at `0x18000e970`
- `msvcrt!wcscat_s` at `0x18000e97f`
- `msvcrt!wcscat_s` at `0x18000e9a3`
- `msvcrt!wcscat_s` at `0x18000e9b2`
- `msvcrt!wcscat_s` at `0x18000e9c6`
- `msvcrt!wcscat_s` at `0x18000e9d5`
- `msvcrt!wcscat_s` at `0x18000e9e9`
- `msvcrt!wcscat_s` at `0x18000eb7d`
- `msvcrt!wcscat_s` at `0x18000eb8c`
- `msvcrt!wcscat_s` at `0x18000eb9b`
- `msvcrt!wcscat_s` at `0x18000ebbf`
- `msvcrt!wcscat_s` at `0x18000ebce`
- `msvcrt!wcscat_s` at `0x18000ebe2`
- `msvcrt!wcscat_s` at `0x18000ebf1`
- `msvcrt!wcscat_s` at `0x18000ec05`
- `msvcrt!wcscat_s` at `0x18000e961`
- `msvcrt!wcscat_s` at `0x18000e970`
- `msvcrt!wcscat_s` at `0x18000e97f`
- `msvcrt!wcscat_s` at `0x18000e9a3`
- `msvcrt!wcscat_s` at `0x18000e9b2`
- `msvcrt!wcscat_s` at `0x18000e9c6`
- `msvcrt!wcscat_s` at `0x18000e9d5`
- `msvcrt!wcscat_s` at `0x18000e9e9`
- `msvcrt!wcscat_s` at `0x18000eb7d`
- `msvcrt!wcscat_s` at `0x18000eb8c`
- `msvcrt!wcscat_s` at `0x18000eb9b`
- `msvcrt!wcscat_s` at `0x18000ebbf`
- `msvcrt!wcscat_s` at `0x18000ebce`
- `msvcrt!wcscat_s` at `0x18000ebe2`
- `msvcrt!wcscat_s` at `0x18000ebf1`
- `msvcrt!wcscat_s` at `0x18000ec05`

## pseudocode

```c
__int64 __fastcall CSecConLib::AddExtensionFile(
        CSecConLib *this,
        wchar_t *Source,
        char a3,
        const unsigned __int16 *a4,
        bool a5,
        wchar_t *a6,
        unsigned __int16 *a7)
{
  __int64 v10; // rsi
  __int64 v11; // r15
  __int64 v12; // rdi
  __int64 v13; // rbp
  int inited; // ebx
  int MultiSZPropVal; // eax
  unsigned int v16; // ebx
  unsigned int v17; // ebp
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  const wchar_t *v20; // r8
  wchar_t *v21; // r13
  const wchar_t *v22; // r8
  wchar_t *v23; // rax
  const wchar_t *v24; // r14
  void *v26; // r12
  unsigned int v27; // ecx
  __int64 v28; // rbp
  wchar_t *v29; // rbx
  const wchar_t *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  const wchar_t *v33; // r8
  rsize_t v34; // rbp
  const wchar_t *v35; // r8
  unsigned int v36; // [rsp+30h] [rbp-58h] BYREF
  void *Src; // [rsp+38h] [rbp-50h] BYREF

  v10 = -1;
  Src = 0;
  v11 = -1;
  v36 = 0;
  do
    ++v11;
  while ( Source[v11] );
  v12 = -1;
  do
    ++v12;
  while ( a4[v12] );
  v13 = -1;
  do
    ++v13;
  while ( a6[v13] );
  inited = CSecConLib::InternalInitIfNecessary(this);
  if ( inited < 0 )
    return (unsigned int)inited;
  MultiSZPropVal = CSecConLib::GetMultiSZPropVal(this, a7, 0x878u, (unsigned __int16 **)&Src, &v36);
  inited = MultiSZPropVal;
  if ( MultiSZPropVal == -2146646015 )
  {
    v16 = 0;
  }
  else
  {
    if ( MultiSZPropVal < 0 )
    {
LABEL_22:
      v19 = (wchar_t *)Src;
      goto LABEL_23;
    }
    v16 = v36;
  }
  if ( !v16 )
  {
    v17 = v11 + 8 + v12 + v13;
    v18 = (wchar_t *)operator new[](saturated_mul(v17, 2u));
    v19 = v18;
    if ( !v18 )
    {
      inited = -2147024882;
      goto LABEL_23;
    }
    v20 = L"1";
    v21 = 0;
    if ( !a3 )
      v20 = L"0";
    wcscpy_s(v18, v17, v20);
    wcscat_s(v19, v17, L",");
    wcscat_s(v19, v17, Source);
    wcscat_s(v19, v17, L",");
    v22 = L"1";
    if ( !a5 )
      v22 = L"0";
    wcscat_s(v19, v17, v22);
    wcscat_s(v19, v17, L",");
    wcscat_s(v19, v17, a4);
    wcscat_s(v19, v17, L",");
    wcscat_s(v19, v17, a6);
    v19[v17 - 1] = 0;
    v19[v17 - 2] = 0;
LABEL_46:
    inited = CSecConLib::SetMultiSZPropVal(this, a7, 0x878u, v19, v17);
    if ( !v21 )
      goto LABEL_23;
    goto LABEL_47;
  }
  v23 = (wchar_t *)operator new[](saturated_mul(v16, 2u));
  v24 = v23;
  if ( !v23 )
  {
    inited = -2147024882;
    goto LABEL_22;
  }
  v26 = Src;
  v21 = v23;
  memcpy_0(v23, Src, 2LL * v16);
  if ( v26 )
    operator delete(v26);
  v27 = v16 + v11 + v13 + v12 + 7;
  v28 = v27;
  v36 = v27;
  v19 = (wchar_t *)operator new[](saturated_mul(v27, 2u));
  if ( v19 )
  {
    v29 = v19;
    if ( !*v24 )
    {
LABEL_39:
      v33 = L"1";
      if ( !a3 )
        v33 = L"0";
      wcscpy_s(v29, v28 - (v29 - v19), v33);
      v34 = v28 - (v29 - v19);
      wcscat_s(v29, v34, L",");
      wcscat_s(v29, v34, Source);
      wcscat_s(v29, v34, L",");
      v35 = L"1";
      if ( !a5 )
        v35 = L"0";
      wcscat_s(v29, v34, v35);
      wcscat_s(v29, v34, L",");
      wcscat_s(v29, v34, a4);
      wcscat_s(v29, v34, L",");
      wcscat_s(v29, v34, a6);
      do
        ++v10;
      while ( v29[v10] );
      v17 = v36;
      v29[(unsigned int)(v10 + 1)] = 0;
      goto LABEL_46;
    }
    while ( 1 )
    {
      wcscpy_s(v29, v28 - (v29 - v19), v24);
      v30 = v29 + 2;
      if ( !_wcsnicmp(Source, v30, (unsigned int)v11) && (v30[(unsigned int)v11] == 44 || !v30[(unsigned int)v11]) )
        break;
      v31 = -1;
      do
        ++v31;
      while ( v24[v31] );
      v24 += (unsigned int)(v31 + 1);
      v32 = -1;
      do
        ++v32;
      while ( v30[v32] );
      v29 = (wchar_t *)&v30[(unsigned int)(v32 + 1)];
      if ( !*v24 )
        goto LABEL_39;
    }
    inited = -2147024844;
  }
  else
  {
    inited = -2147024882;
  }
LABEL_47:
  operator delete(v21);
LABEL_23:
  if ( v19 )
    operator delete(v19);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000e83c  mov     rax, rsp
0x18000e83f  mov     [rax+20h], r9
0x18000e843  mov     [rax+18h], r8b
0x18000e847  mov     [rax+10h], rdx
0x18000e84b  mov     [rax+8], rcx
0x18000e84f  push    rbx
0x18000e850  push    rbp
0x18000e851  push    rsi
0x18000e852  push    rdi
0x18000e853  push    r12
0x18000e855  push    r13
0x18000e857  push    r14
0x18000e859  push    r15
0x18000e85b  sub     rsp, 48h
0x18000e85f  mov     r13, rcx
0x18000e862  mov     r14b, r8b
0x18000e865  xor     ecx, ecx
0x18000e867  mov     r12, rdx
0x18000e86a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e86e  mov     [rax-50h], rcx
0x18000e872  mov     r15, rsi
0x18000e875  mov     [rax-58h], ecx
0x18000e878  inc     r15
0x18000e87b  cmp     [rdx+r15*2], cx
0x18000e880  jnz     short loc_18000E878
0x18000e882  mov     rdi, rsi
0x18000e885  inc     rdi
0x18000e888  cmp     [r9+rdi*2], cx
0x18000e88d  jnz     short loc_18000E885
0x18000e88f  mov     rax, [rsp+88h+arg_28]
0x18000e897  mov     rbp, rsi
0x18000e89a  inc     rbp
0x18000e89d  cmp     [rax+rbp*2], cx
0x18000e8a1  jnz     short loc_18000E89A
0x18000e8a3  mov     rcx, r13; this
0x18000e8a6  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000e8ab  mov     ebx, eax
0x18000e8ad  test    eax, eax
0x18000e8af  js      loc_18000EA35
0x18000e8b5  mov     rdx, [rsp+88h+arg_30]; unsigned __int16 *
0x18000e8bd  lea     rax, [rsp+88h+var_58]
0x18000e8c2  lea     r9, [rsp+88h+Src]; unsigned __int16 **
0x18000e8c7  mov     [rsp+88h+var_68], rax; unsigned int *
0x18000e8cc  mov     r8d, 878h; unsigned int
0x18000e8d2  mov     rcx, r13; this
0x18000e8d5  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x18000e8da  mov     ebx, eax
0x18000e8dc  cmp     eax, 800CC801h
0x18000e8e1  jnz     short loc_18000E8E7
0x18000e8e3  xor     ebx, ebx
0x18000e8e5  jmp     short loc_18000E8F3
0x18000e8e7  test    eax, eax
0x18000e8e9  js      loc_18000EA23
0x18000e8ef  mov     ebx, [rsp+88h+var_58]
0x18000e8f3  mov     eax, 2
0x18000e8f8  test    ebx, ebx
0x18000e8fa  jnz     loc_18000EA04
0x18000e900  add     ebp, edi
0x18000e902  add     r15d, 8
0x18000e906  add     ebp, r15d
0x18000e909  mov     ebx, ebp
0x18000e90b  mul     rbx
0x18000e90e  cmovb   rax, rsi
0x18000e912  mov     rcx, rax; unsigned __int64
0x18000e915  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e91a  xor     r15d, r15d
0x18000e91d  mov     rdi, rax
0x18000e920  test    rax, rax
0x18000e923  jnz     short loc_18000E92F
0x18000e925  mov     ebx, 8007000Eh
0x18000e92a  jmp     loc_18000EA28
0x18000e92f  lea     r8, a1; "1"
0x18000e936  mov     r13, r15
0x18000e939  mov     rdx, rbx; SizeInWords
0x18000e93c  mov     rcx, rdi; Destination
0x18000e93f  test    r14b, r14b
0x18000e942  jnz     short loc_18000E94B
0x18000e944  lea     r8, a0; "0"
0x18000e94b  call    cs:__imp_wcscpy_s
0x18000e951  lea     r14, Delimiter; ","
0x18000e958  mov     rdx, rbx; SizeInWords
0x18000e95b  mov     r8, r14; Source
0x18000e95e  mov     rcx, rdi; Destination
0x18000e961  call    cs:__imp_wcscat_s
0x18000e967  mov     r8, r12; Source
0x18000e96a  mov     rdx, rbx; SizeInWords
0x18000e96d  mov     rcx, rdi; Destination
0x18000e970  call    cs:__imp_wcscat_s
0x18000e976  mov     r8, r14; Source
0x18000e979  mov     rdx, rbx; SizeInWords
0x18000e97c  mov     rcx, rdi; Destination
0x18000e97f  call    cs:__imp_wcscat_s
0x18000e985  lea     r8, a1; "1"
0x18000e98c  mov     rdx, rbx; SizeInWords
0x18000e98f  mov     rcx, rdi; Destination
0x18000e992  cmp     [rsp+88h+arg_20], r15b
0x18000e99a  jnz     short loc_18000E9A3
0x18000e99c  lea     r8, a0; "0"
0x18000e9a3  call    cs:__imp_wcscat_s
0x18000e9a9  mov     r8, r14; Source
0x18000e9ac  mov     rdx, rbx; SizeInWords
0x18000e9af  mov     rcx, rdi; Destination
0x18000e9b2  call    cs:__imp_wcscat_s
0x18000e9b8  mov     r8, [rsp+88h+Source]; Source
0x18000e9c0  mov     rdx, rbx; SizeInWords
0x18000e9c3  mov     rcx, rdi; Destination
0x18000e9c6  call    cs:__imp_wcscat_s
0x18000e9cc  mov     r8, r14; Source
0x18000e9cf  mov     rdx, rbx; SizeInWords
0x18000e9d2  mov     rcx, rdi; Destination
0x18000e9d5  call    cs:__imp_wcscat_s
0x18000e9db  mov     r8, [rsp+88h+arg_28]; Source
0x18000e9e3  mov     rdx, rbx; SizeInWords
0x18000e9e6  mov     rcx, rdi; Destination
0x18000e9e9  call    cs:__imp_wcscat_s
0x18000e9ef  lea     eax, [rbp-1]
0x18000e9f2  mov     [rdi+rax*2], r15w
0x18000e9f7  lea     eax, [rbp-2]
0x18000e9fa  mov     [rdi+rax*2], r15w
0x18000e9ff  jmp     loc_18000EC21
0x18000ea04  mov     r12d, ebx
0x18000ea07  mul     r12
0x18000ea0a  cmovb   rax, rsi
0x18000ea0e  mov     rcx, rax; unsigned __int64
0x18000ea11  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ea16  mov     r14, rax
0x18000ea19  test    rax, rax
0x18000ea1c  jnz     short loc_18000EA48
0x18000ea1e  mov     ebx, 8007000Eh
0x18000ea23  mov     rdi, [rsp+88h+Src]
0x18000ea28  test    rdi, rdi
0x18000ea2b  jz      short loc_18000EA35
0x18000ea2d  mov     rcx, rdi; Block
0x18000ea30  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ea35  mov     eax, ebx
0x18000ea37  add     rsp, 48h
0x18000ea3b  pop     r15
0x18000ea3d  pop     r14
0x18000ea3f  pop     r13
0x18000ea41  pop     r12
0x18000ea43  pop     rdi
0x18000ea44  pop     rsi
0x18000ea45  pop     rbp
0x18000ea46  pop     rbx
0x18000ea47  retn
0x18000ea48  lea     r8, [r12+r12]; Size
0x18000ea4c  mov     rcx, r14; void *
0x18000ea4f  mov     r12, [rsp+88h+Src]
0x18000ea54  mov     r13, r14
0x18000ea57  mov     rdx, r12; Src
0x18000ea5a  call    memcpy_0
0x18000ea5f  test    r12, r12
0x18000ea62  jz      short loc_18000EA6C
0x18000ea64  mov     rcx, r12; Block
0x18000ea67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ea6c  lea     ecx, [rdi+7]
0x18000ea6f  mov     eax, 2
0x18000ea74  add     ecx, ebp
0x18000ea76  add     ecx, r15d
0x18000ea79  add     ecx, ebx
0x18000ea7b  mov     ebp, ecx
0x18000ea7d  mul     rbp
0x18000ea80  mov     [rsp+88h+var_58], ecx
0x18000ea84  cmovb   rax, rsi
0x18000ea88  mov     rcx, rax; unsigned __int64
0x18000ea8b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ea90  mov     rdi, rax
0x18000ea93  xor     eax, eax
0x18000ea95  test    rdi, rdi
0x18000ea98  jnz     short loc_18000EAA4
0x18000ea9a  mov     ebx, 8007000Eh
0x18000ea9f  jmp     loc_18000EC4E
0x18000eaa4  mov     rbx, rdi
0x18000eaa7  mov     r12, [rsp+88h+String1]
0x18000eaaf  cmp     [r14], ax
0x18000eab3  jz      short loc_18000EB2E
0x18000eab5  mov     r15d, r15d
0x18000eab8  mov     rax, rbx
0x18000eabb  mov     rdx, rbp
0x18000eabe  sub     rax, rdi
0x18000eac1  mov     r8, r14; Source
0x18000eac4  sar     rax, 1
0x18000eac7  mov     rcx, rbx; Destination
0x18000eaca  sub     rdx, rax; SizeInWords
0x18000eacd  call    cs:__imp_wcscpy_s
0x18000ead3  add     rbx, 4
0x18000ead7  mov     r8, r15; MaxCount
0x18000eada  mov     rdx, rbx; String2
0x18000eadd  mov     rcx, r12; String1
0x18000eae0  call    cs:__imp__wcsnicmp
0x18000eae6  xor     edx, edx
0x18000eae8  test    eax, eax
0x18000eaea  jnz     short loc_18000EB03
0x18000eaec  cmp     word ptr [rbx+r15*2], 2Ch ; ','
0x18000eaf2  jz      loc_18000EC5B
0x18000eaf8  cmp     [rbx+r15*2], dx
0x18000eafd  jz      loc_18000EC5B
0x18000eb03  mov     rax, rsi
0x18000eb06  inc     rax
0x18000eb09  cmp     [r14+rax*2], dx
0x18000eb0e  jnz     short loc_18000EB06
0x18000eb10  inc     eax
0x18000eb12  lea     r14, [r14+rax*2]
0x18000eb16  mov     rax, rsi
0x18000eb19  inc     rax
0x18000eb1c  cmp     [rbx+rax*2], dx
0x18000eb20  jnz     short loc_18000EB19
0x18000eb22  inc     eax
0x18000eb24  lea     rbx, [rbx+rax*2]
0x18000eb28  cmp     [r14], dx
0x18000eb2c  jnz     short loc_18000EAB8
0x18000eb2e  mov     rax, rbx
0x18000eb31  lea     r8, a1; "1"
0x18000eb38  sub     rax, rdi
0x18000eb3b  mov     rdx, rbp
0x18000eb3e  sar     rax, 1
0x18000eb41  xor     r15d, r15d
0x18000eb44  sub     rdx, rax; SizeInWords
0x18000eb47  mov     rcx, rbx; Destination
0x18000eb4a  cmp     [rsp+88h+arg_10], r15b
0x18000eb52  jnz     short loc_18000EB5B
0x18000eb54  lea     r8, a0; "0"
0x18000eb5b  call    cs:__imp_wcscpy_s
0x18000eb61  mov     rax, rbx
0x18000eb64  lea     r14, Delimiter; ","
0x18000eb6b  sub     rax, rdi
0x18000eb6e  mov     r8, r14; Source
0x18000eb71  sar     rax, 1
0x18000eb74  mov     rcx, rbx; Destination
0x18000eb77  sub     rbp, rax
0x18000eb7a  mov     rdx, rbp; SizeInWords
0x18000eb7d  call    cs:__imp_wcscat_s
0x18000eb83  mov     r8, r12; Source
0x18000eb86  mov     rdx, rbp; SizeInWords
0x18000eb89  mov     rcx, rbx; Destination
0x18000eb8c  call    cs:__imp_wcscat_s
0x18000eb92  mov     r8, r14; Source
0x18000eb95  mov     rdx, rbp; SizeInWords
0x18000eb98  mov     rcx, rbx; Destination
0x18000eb9b  call    cs:__imp_wcscat_s
0x18000eba1  lea     r8, a1; "1"
0x18000eba8  mov     rdx, rbp; SizeInWords
0x18000ebab  mov     rcx, rbx; Destination
0x18000ebae  cmp     [rsp+88h+arg_20], r15b
0x18000ebb6  jnz     short loc_18000EBBF
0x18000ebb8  lea     r8, a0; "0"
0x18000ebbf  call    cs:__imp_wcscat_s
0x18000ebc5  mov     r8, r14; Source
0x18000ebc8  mov     rdx, rbp; SizeInWords
0x18000ebcb  mov     rcx, rbx; Destination
0x18000ebce  call    cs:__imp_wcscat_s
0x18000ebd4  mov     r8, [rsp+88h+Source]; Source
0x18000ebdc  mov     rdx, rbp; SizeInWords
0x18000ebdf  mov     rcx, rbx; Destination
0x18000ebe2  call    cs:__imp_wcscat_s
0x18000ebe8  mov     r8, r14; Source
0x18000ebeb  mov     rdx, rbp; SizeInWords
0x18000ebee  mov     rcx, rbx; Destination
0x18000ebf1  call    cs:__imp_wcscat_s
0x18000ebf7  mov     r8, [rsp+88h+arg_28]; Source
0x18000ebff  mov     rdx, rbp; SizeInWords
0x18000ec02  mov     rcx, rbx; Destination
0x18000ec05  call    cs:__imp_wcscat_s
0x18000ec0b  inc     rsi
0x18000ec0e  cmp     [rbx+rsi*2], r15w
0x18000ec13  jnz     short loc_18000EC0B
0x18000ec15  mov     ebp, [rsp+88h+var_58]
0x18000ec19  lea     eax, [rsi+1]
0x18000ec1c  mov     [rbx+rax*2], r15w
0x18000ec21  mov     rdx, [rsp+88h+arg_30]; unsigned __int16 *
0x18000ec29  mov     r9, rdi; unsigned __int16 *
0x18000ec2c  mov     rcx, [rsp+88h+arg_0]; this
0x18000ec34  mov     r8d, 878h; unsigned int
0x18000ec3a  mov     dword ptr [rsp+88h+var_68], ebp; unsigned int
0x18000ec3e  call    ?SetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAGK@Z; CSecConLib::SetMultiSZPropVal(ushort const *,ulong,ushort *,ulong)
0x18000ec43  mov     ebx, eax
0x18000ec45  test    r13, r13
0x18000ec48  jz      loc_18000EA28
0x18000ec4e  mov     rcx, r13; Block
0x18000ec51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ec56  jmp     loc_18000EA28
0x18000ec5b  mov     ebx, 80070034h
0x18000ec60  jmp     short loc_18000EC4E
```
