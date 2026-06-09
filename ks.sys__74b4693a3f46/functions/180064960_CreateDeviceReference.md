# CreateDeviceReference

- ea: `0x180064960`
- end: `0x180064dcf`
- name: `CreateDeviceReference`
- size: `1135`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ae68`
- `0x18000b7bc`
- `0x180010de4`
- `0x180019cc0`
- `0x180019fc0`
- `0x180035f20`
- `0x180063400`
- `0x180064960`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x180064c0d`
- `ntoskrnl!RtlGUIDFromString` at `0x180064c0d`
- `ntoskrnl!_wcsicmp` at `0x180064ab6`
- `ntoskrnl!_wcsicmp` at `0x180064ab6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064b55`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064b66`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064bd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d28`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064da7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064dbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064b55`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064b66`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064bd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d28`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064da7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064dbc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064a03`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064ae6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064b37`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064a03`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064ae6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064b37`
- `HAL!KeQueryPerformanceCounter` at `0x180064c36`
- `HAL!KeQueryPerformanceCounter` at `0x180064c36`

## pseudocode

```c
__int64 __fastcall CreateDeviceReference(void *a1, unsigned __int16 *a2, __int64 a3)
{
  __int64 *v6; // rdx
  char v7; // r15
  PVOID *v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rdx
  SIZE_T v11; // rbx
  PVOID PoolWithTag; // rax
  void *v13; // rdi
  int v14; // edx
  int v15; // r8d
  PVOID *i; // rbx
  const wchar_t *v17; // rdx
  int v18; // edx
  PVOID *v19; // rax
  PVOID v20; // rax
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  int v25; // edi
  PVOID v26; // rcx
  PVOID v27; // rcx
  PVOID **v28; // rax
  PVOID v29; // rcx
  PVOID v30; // rcx

  v6 = WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids;
  v7 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      74,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
  }
  v8 = *(PVOID **)(a3 + 8);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v10) );
  do
    ++v9;
  while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 8LL) + 2 * v9) );
  v11 = (unsigned int)(2 * (v9 + v10) + 4);
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v11, 0x72625753u);
  v13 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, (unsigned int)v11);
      goto LABEL_11;
    }
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
LABEL_11:
  if ( StringCbPrintfW((STRSAFE_LPWSTR)v13, v11, L"%s&%s", *(_QWORD *)(*(_QWORD *)(a3 + 16) + 8LL), *((_QWORD *)a2 + 1)) < 0 )
  {
LABEL_23:
    ExFreePoolWithTag(v13, 0);
    return 3221225626LL;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_S(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      v15,
      75,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
      (__int64)v13);
  for ( i = (PVOID *)*v8; i != v8; i = (PVOID *)*i )
  {
    v17 = (const wchar_t *)i[12];
    if ( v17 && !_wcsicmp((const wchar_t *)v13, v17) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v18) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          1,
          76,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
      }
      *((_BYTE *)i + 60) = 1;
      if ( i != v8 )
      {
        ExFreePoolWithTag(v13, 0);
        v7 = 0;
        goto LABEL_33;
      }
      break;
    }
  }
  v19 = (PVOID *)ExAllocatePoolWithTag(PagedPool, *a2 + 138LL, 0x72645753u);
  i = v19;
  if ( !v19 )
    goto LABEL_23;
  memset(v19, 0, 0x88u);
  memmove(i + 17, *((const void **)a2 + 1), *a2 + 2LL);
  v20 = ExAllocatePoolWithTag(PagedPool, **(unsigned __int16 **)(a3 + 16) + 2LL, 0x64695753u);
  i[13] = v20;
  if ( !v20 )
  {
    ExFreePoolWithTag(i, 0);
    goto LABEL_23;
  }
  memmove(v20, *(const void **)(*(_QWORD *)(a3 + 16) + 8LL), **(unsigned __int16 **)(a3 + 16) + 2LL);
  RtlGUIDFromString(*(PCUNICODE_STRING *)(a3 + 16), (GUID *)i + 4);
  *((_BYTE *)i + 60) = 1;
  i[5] = i + 4;
  i[4] = i + 4;
  i[15] = (PVOID)(15LL * (_QWORD)v8[93]);
  *((LARGE_INTEGER *)i + 14) = KeQueryPerformanceCounter(0);
  i[12] = v13;
  i[3] = i + 2;
  i[2] = i + 2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_S(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      v23,
      77,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
      (__int64)i[12]);
LABEL_33:
  *(_QWORD *)a3 = i;
  *(_QWORD *)(a3 + 24) = a2;
  v25 = EnumerateRegistrySubKeys(
          a1,
          *((const WCHAR **)a2 + 1),
          (__int64 (__fastcall *)(void *, UNICODE_STRING *, __int64))&CreateDeviceAssociation,
          a3);
  if ( i[2] == i + 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v24) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v24,
        1,
        78,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
    }
    v26 = i[13];
    if ( v26 )
    {
      ExFreePoolWithTag(v26, 0);
      i[13] = 0;
    }
    v27 = i[12];
    if ( v27 )
    {
      ExFreePoolWithTag(v27, 0);
      i[12] = 0;
    }
    ExFreePoolWithTag(i, 0);
    return (unsigned int)-1073741436;
  }
  else if ( v7 )
  {
    if ( v25 < 0 )
    {
      RemoveDeviceAssociations(i);
      v29 = i[12];
      if ( v29 )
      {
        ExFreePoolWithTag(v29, 0);
        i[12] = 0;
      }
      v30 = i[13];
      if ( v30 )
      {
        ExFreePoolWithTag(v30, 0);
        i[13] = 0;
      }
      ExFreePoolWithTag(i, 0);
    }
    else
    {
      v28 = (PVOID **)v8[1];
      if ( *v28 != v8 )
        __fastfail(3u);
      *i = v8;
      i[1] = v28;
      *v28 = i;
      v8[1] = i;
    }
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180064960  push    rbx
0x180064962  push    rbp
0x180064963  push    rsi
0x180064964  push    rdi
0x180064965  push    r12
0x180064967  push    r13
0x180064969  push    r14
0x18006496b  push    r15
0x18006496d  sub     rsp, 38h
0x180064971  mov     r14, r8
0x180064974  mov     rbp, rdx
0x180064977  mov     r12, rcx
0x18006497a  xor     r13d, r13d
0x18006497d  lea     rax, WPP_RECORDER_INITIALIZED
0x180064984  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18006498b  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064992  lea     r15d, [r13+1]
0x180064996  jz      short loc_1800649BD
0x180064998  mov     rcx, cs:WPP_GLOBAL_Control
0x18006499f  cmp     [rcx+48h], r13w
0x1800649a4  jz      short loc_1800649BD
0x1800649a6  mov     rcx, [rcx+40h]
0x1800649aa  lea     r9d, [r13+4Ah]
0x1800649ae  mov     [rsp+78h+var_58], rdx
0x1800649b3  mov     r8d, r15d
0x1800649b6  mov     dl, 5
0x1800649b8  call    WPP_RECORDER_SF_
0x1800649bd  mov     rsi, [r14+8]
0x1800649c1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800649c5  mov     rax, [rbp+8]
0x1800649c9  mov     rdx, rcx
0x1800649cc  inc     rdx
0x1800649cf  cmp     [rax+rdx*2], r13w
0x1800649d4  jnz     short loc_1800649CC
0x1800649d6  mov     rax, [r14+10h]
0x1800649da  mov     r8, [rax+8]
0x1800649de  inc     rcx
0x1800649e1  cmp     [r8+rcx*2], r13w
0x1800649e6  jnz     short loc_1800649DE
0x1800649e8  lea     rax, [rcx+rdx]
0x1800649ec  mov     r8d, 72625753h; Tag
0x1800649f2  lea     rax, ds:4[rax*2]
0x1800649fa  mov     ecx, 401h; PoolType
0x1800649ff  mov     edx, eax; NumberOfBytes
0x180064a01  mov     ebx, eax
0x180064a03  call    cs:__imp_ExAllocatePoolWithTag
0x180064a0a  nop     dword ptr [rax+rax+00h]
0x180064a0f  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x180064a16  mov     rdi, rax
0x180064a19  jnz     short loc_180064A33
0x180064a1b  test    rax, rax
0x180064a1e  jz      loc_180064B72
0x180064a24  mov     r8d, ebx; Size
0x180064a27  xor     edx, edx; Val
0x180064a29  mov     rcx, rax; void *
0x180064a2c  call    memset
0x180064a31  jmp     short loc_180064A3C
0x180064a33  test    rdi, rdi
0x180064a36  jz      loc_180064B72
0x180064a3c  mov     r9, [r14+10h]
0x180064a40  lea     r8, aSS_1; "%s&%s"
0x180064a47  mov     rax, [rbp+8]
0x180064a4b  mov     rdx, rbx; cbDest
0x180064a4e  mov     rcx, rdi; pszDest
0x180064a51  mov     [rsp+78h+var_58], rax
0x180064a56  mov     r9, [r9+8]
0x180064a5a  call    StringCbPrintfW
0x180064a5f  test    eax, eax
0x180064a61  js      loc_180064B61
0x180064a67  lea     rax, WPP_RECORDER_INITIALIZED
0x180064a6e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064a75  jz      short loc_180064AA5
0x180064a77  mov     rcx, cs:WPP_GLOBAL_Control
0x180064a7e  cmp     [rcx+48h], r13w
0x180064a83  jz      short loc_180064AA5
0x180064a85  mov     rcx, [rcx+40h]
0x180064a89  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064a90  mov     r9d, 4Bh ; 'K'
0x180064a96  mov     [rsp+78h+var_50], rdi
0x180064a9b  mov     [rsp+78h+var_58], rax
0x180064aa0  call    WPP_RECORDER_SF_S
0x180064aa5  mov     rbx, [rsi]
0x180064aa8  jmp     short loc_180064ACD
0x180064aaa  mov     rdx, [rbx+60h]; Str2
0x180064aae  test    rdx, rdx
0x180064ab1  jz      short loc_180064ACA
0x180064ab3  mov     rcx, rdi; Str1
0x180064ab6  call    cs:__imp__wcsicmp
0x180064abd  nop     dword ptr [rax+rax+00h]
0x180064ac2  test    eax, eax
0x180064ac4  jz      loc_180064B89
0x180064aca  mov     rbx, [rbx]
0x180064acd  cmp     rbx, rsi
0x180064ad0  jnz     short loc_180064AAA
0x180064ad2  movzx   edx, word ptr [rbp+0]
0x180064ad6  mov     r8d, 72645753h; Tag
0x180064adc  add     rdx, 8Ah; NumberOfBytes
0x180064ae3  mov     ecx, r15d; PoolType
0x180064ae6  call    cs:__imp_ExAllocatePoolWithTag
0x180064aed  nop     dword ptr [rax+rax+00h]
0x180064af2  mov     rbx, rax
0x180064af5  test    rax, rax
0x180064af8  jz      short loc_180064B61
0x180064afa  xor     edx, edx; Val
0x180064afc  mov     r8d, 88h; Size
0x180064b02  mov     rcx, rax; void *
0x180064b05  call    memset
0x180064b0a  movzx   r8d, word ptr [rbp+0]
0x180064b0f  lea     rcx, [rbx+88h]; void *
0x180064b16  mov     rdx, [rbp+8]; Src
0x180064b1a  add     r8, 2; Size
0x180064b1e  call    memmove
0x180064b23  mov     rax, [r14+10h]
0x180064b27  mov     r8d, 64695753h; Tag
0x180064b2d  mov     ecx, r15d; PoolType
0x180064b30  movzx   edx, word ptr [rax]
0x180064b33  add     rdx, 2; NumberOfBytes
0x180064b37  call    cs:__imp_ExAllocatePoolWithTag
0x180064b3e  nop     dword ptr [rax+rax+00h]
0x180064b43  mov     [rbx+68h], rax
0x180064b47  test    rax, rax
0x180064b4a  jnz     loc_180064BED
0x180064b50  xor     edx, edx; Tag
0x180064b52  mov     rcx, rbx; P
0x180064b55  call    cs:__imp_ExFreePoolWithTag
0x180064b5c  nop     dword ptr [rax+rax+00h]
0x180064b61  xor     edx, edx; Tag
0x180064b63  mov     rcx, rdi; P
0x180064b66  call    cs:__imp_ExFreePoolWithTag
0x180064b6d  nop     dword ptr [rax+rax+00h]
0x180064b72  mov     eax, 0C000009Ah
0x180064b77  add     rsp, 38h
0x180064b7b  pop     r15
0x180064b7d  pop     r14
0x180064b7f  pop     r13
0x180064b81  pop     r12
0x180064b83  pop     rdi
0x180064b84  pop     rsi
0x180064b85  pop     rbp
0x180064b86  pop     rbx
0x180064b87  retn
0x180064b89  lea     rax, WPP_RECORDER_INITIALIZED
0x180064b90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064b97  jz      short loc_180064BC7
0x180064b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180064ba0  cmp     [rcx+48h], r13w
0x180064ba5  jz      short loc_180064BC7
0x180064ba7  mov     rcx, [rcx+40h]
0x180064bab  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064bb2  mov     r9d, 4Ch ; 'L'
0x180064bb8  mov     [rsp+78h+var_58], rax
0x180064bbd  mov     r8d, r15d
0x180064bc0  mov     dl, 5
0x180064bc2  call    WPP_RECORDER_SF_
0x180064bc7  mov     [rbx+3Ch], r15b
0x180064bcb  cmp     rbx, rsi
0x180064bce  jz      loc_180064AD2
0x180064bd4  xor     edx, edx; Tag
0x180064bd6  mov     rcx, rdi; P
0x180064bd9  call    cs:__imp_ExFreePoolWithTag
0x180064be0  nop     dword ptr [rax+rax+00h]
0x180064be5  mov     r15b, r13b
0x180064be8  jmp     loc_180064C97
0x180064bed  mov     rdx, [r14+10h]
0x180064bf1  mov     rcx, rax; void *
0x180064bf4  movzx   r8d, word ptr [rdx]
0x180064bf8  mov     rdx, [rdx+8]; Src
0x180064bfc  add     r8, 2; Size
0x180064c00  call    memmove
0x180064c05  mov     rcx, [r14+10h]; GuidString
0x180064c09  lea     rdx, [rbx+40h]; Guid
0x180064c0d  call    cs:__imp_RtlGUIDFromString
0x180064c14  nop     dword ptr [rax+rax+00h]
0x180064c19  lea     rax, [rbx+20h]
0x180064c1d  mov     [rbx+3Ch], r15b
0x180064c21  mov     [rax+8], rax
0x180064c25  xor     ecx, ecx; PerformanceFrequency
0x180064c27  mov     [rax], rax
0x180064c2a  imul    rax, [rsi+2E8h], 0Fh
0x180064c32  mov     [rbx+78h], rax
0x180064c36  call    cs:__imp_KeQueryPerformanceCounter
0x180064c3d  nop     dword ptr [rax+rax+00h]
0x180064c42  mov     [rbx+70h], rax
0x180064c46  lea     rax, [rbx+10h]
0x180064c4a  mov     [rbx+60h], rdi
0x180064c4e  mov     [rax+8], rax
0x180064c52  mov     [rax], rax
0x180064c55  lea     rax, WPP_RECORDER_INITIALIZED
0x180064c5c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064c63  jz      short loc_180064C97
0x180064c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180064c6c  cmp     [rcx+48h], r13w
0x180064c71  jz      short loc_180064C97
0x180064c73  mov     rax, [rbx+60h]
0x180064c77  mov     r9d, 4Dh ; 'M'
0x180064c7d  mov     rcx, [rcx+40h]
0x180064c81  mov     [rsp+78h+var_50], rax
0x180064c86  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064c8d  mov     [rsp+78h+var_58], rax
0x180064c92  call    WPP_RECORDER_SF_S
0x180064c97  mov     [r14], rbx
0x180064c9a  lea     r8, CreateDeviceAssociation
0x180064ca1  mov     [r14+18h], rbp
0x180064ca5  mov     r9, r14
0x180064ca8  mov     rdx, [rbp+8]
0x180064cac  mov     rcx, r12
0x180064caf  call    EnumerateRegistrySubKeys
0x180064cb4  mov     edi, eax
0x180064cb6  lea     rax, [rbx+10h]
0x180064cba  cmp     [rax], rax
0x180064cbd  jnz     loc_180064D50
0x180064cc3  lea     rax, WPP_RECORDER_INITIALIZED
0x180064cca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064cd1  jz      short loc_180064D02
0x180064cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180064cda  cmp     [rcx+48h], r13w
0x180064cdf  jz      short loc_180064D02
0x180064ce1  mov     rcx, [rcx+40h]
0x180064ce5  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064cec  mov     r9d, 4Eh ; 'N'
0x180064cf2  mov     [rsp+78h+var_58], rax
0x180064cf7  mov     dl, 5
0x180064cf9  lea     r8d, [r9-4Dh]
0x180064cfd  call    WPP_RECORDER_SF_
0x180064d02  mov     rcx, [rbx+68h]; P
0x180064d06  test    rcx, rcx
0x180064d09  jz      short loc_180064D1D
0x180064d0b  xor     edx, edx; Tag
0x180064d0d  call    cs:__imp_ExFreePoolWithTag
0x180064d14  nop     dword ptr [rax+rax+00h]
0x180064d19  mov     [rbx+68h], r13
0x180064d1d  mov     rcx, [rbx+60h]; P
0x180064d21  test    rcx, rcx
0x180064d24  jz      short loc_180064D38
0x180064d26  xor     edx, edx; Tag
0x180064d28  call    cs:__imp_ExFreePoolWithTag
0x180064d2f  nop     dword ptr [rax+rax+00h]
0x180064d34  mov     [rbx+60h], r13
0x180064d38  xor     edx, edx; Tag
0x180064d3a  mov     rcx, rbx; P
0x180064d3d  call    cs:__imp_ExFreePoolWithTag
0x180064d44  nop     dword ptr [rax+rax+00h]
0x180064d49  mov     edi, 0C0000184h
0x180064d4e  jmp     short loc_180064DC8
0x180064d50  test    r15b, r15b
0x180064d53  jz      short loc_180064DC8
0x180064d55  test    edi, edi
0x180064d57  js      short loc_180064D79
0x180064d59  mov     rax, [rsi+8]
0x180064d5d  cmp     [rax], rsi
0x180064d60  jz      short loc_180064D69
0x180064d62  mov     ecx, 3
0x180064d67  int     29h; Win8: RtlFailFast(ecx)
0x180064d69  mov     [rbx], rsi
0x180064d6c  mov     [rbx+8], rax
0x180064d70  mov     [rax], rbx
0x180064d73  mov     [rsi+8], rbx
0x180064d77  jmp     short loc_180064DC8
0x180064d79  mov     rcx, rbx
0x180064d7c  call    RemoveDeviceAssociations
0x180064d81  mov     rcx, [rbx+60h]; P
0x180064d85  test    rcx, rcx
0x180064d88  jz      short loc_180064D9C
0x180064d8a  xor     edx, edx; Tag
0x180064d8c  call    cs:__imp_ExFreePoolWithTag
0x180064d93  nop     dword ptr [rax+rax+00h]
0x180064d98  mov     [rbx+60h], r13
0x180064d9c  mov     rcx, [rbx+68h]; P
0x180064da0  test    rcx, rcx
0x180064da3  jz      short loc_180064DB7
0x180064da5  xor     edx, edx; Tag
0x180064da7  call    cs:__imp_ExFreePoolWithTag
0x180064dae  nop     dword ptr [rax+rax+00h]
0x180064db3  mov     [rbx+68h], r13
0x180064db7  xor     edx, edx; Tag
0x180064db9  mov     rcx, rbx; P
0x180064dbc  call    cs:__imp_ExFreePoolWithTag
0x180064dc3  nop     dword ptr [rax+rax+00h]
0x180064dc8  mov     eax, edi
0x180064dca  jmp     loc_180064B77
```
