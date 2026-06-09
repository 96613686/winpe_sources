# CreateDeviceReference

- ea: `0x180064b00`
- end: `0x180064f6f`
- name: `CreateDeviceReference`
- size: `1135`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ae68`
- `0x18000b7bc`
- `0x180011684`
- `0x180019d00`
- `0x18001a000`
- `0x180036030`
- `0x1800635a0`
- `0x180064b00`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x180064dad`
- `ntoskrnl!RtlGUIDFromString` at `0x180064dad`
- `ntoskrnl!_wcsicmp` at `0x180064c56`
- `ntoskrnl!_wcsicmp` at `0x180064c56`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064cf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d06`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d79`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064ead`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064ec8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064edd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064f2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064f47`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064f5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064cf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d06`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064d79`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064ead`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064ec8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064edd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064f2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064f47`
- `ntoskrnl!ExFreePoolWithTag` at `0x180064f5c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064ba3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064c86`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064cd7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064ba3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064c86`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180064cd7`
- `HAL!KeQueryPerformanceCounter` at `0x180064dd6`
- `HAL!KeQueryPerformanceCounter` at `0x180064dd6`

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
      RemoveDeviceAssociations((UNICODE_STRING *)i);
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
0x180064b00  push    rbx
0x180064b02  push    rbp
0x180064b03  push    rsi
0x180064b04  push    rdi
0x180064b05  push    r12
0x180064b07  push    r13
0x180064b09  push    r14
0x180064b0b  push    r15
0x180064b0d  sub     rsp, 38h
0x180064b11  mov     r14, r8
0x180064b14  mov     rbp, rdx
0x180064b17  mov     r12, rcx
0x180064b1a  xor     r13d, r13d
0x180064b1d  lea     rax, WPP_RECORDER_INITIALIZED
0x180064b24  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064b2b  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064b32  lea     r15d, [r13+1]
0x180064b36  jz      short loc_180064B5D
0x180064b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180064b3f  cmp     [rcx+48h], r13w
0x180064b44  jz      short loc_180064B5D
0x180064b46  mov     rcx, [rcx+40h]
0x180064b4a  lea     r9d, [r13+4Ah]
0x180064b4e  mov     [rsp+78h+var_58], rdx
0x180064b53  mov     r8d, r15d
0x180064b56  mov     dl, 5
0x180064b58  call    WPP_RECORDER_SF_
0x180064b5d  mov     rsi, [r14+8]
0x180064b61  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180064b65  mov     rax, [rbp+8]
0x180064b69  mov     rdx, rcx
0x180064b6c  inc     rdx
0x180064b6f  cmp     [rax+rdx*2], r13w
0x180064b74  jnz     short loc_180064B6C
0x180064b76  mov     rax, [r14+10h]
0x180064b7a  mov     r8, [rax+8]
0x180064b7e  inc     rcx
0x180064b81  cmp     [r8+rcx*2], r13w
0x180064b86  jnz     short loc_180064B7E
0x180064b88  lea     rax, [rcx+rdx]
0x180064b8c  mov     r8d, 72625753h; Tag
0x180064b92  lea     rax, ds:4[rax*2]
0x180064b9a  mov     ecx, 401h; PoolType
0x180064b9f  mov     edx, eax; NumberOfBytes
0x180064ba1  mov     ebx, eax
0x180064ba3  call    cs:__imp_ExAllocatePoolWithTag
0x180064baa  nop     dword ptr [rax+rax+00h]
0x180064baf  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x180064bb6  mov     rdi, rax
0x180064bb9  jnz     short loc_180064BD3
0x180064bbb  test    rax, rax
0x180064bbe  jz      loc_180064D12
0x180064bc4  mov     r8d, ebx; Size
0x180064bc7  xor     edx, edx; Val
0x180064bc9  mov     rcx, rax; void *
0x180064bcc  call    memset
0x180064bd1  jmp     short loc_180064BDC
0x180064bd3  test    rdi, rdi
0x180064bd6  jz      loc_180064D12
0x180064bdc  mov     r9, [r14+10h]
0x180064be0  lea     r8, aSS_1; "%s&%s"
0x180064be7  mov     rax, [rbp+8]
0x180064beb  mov     rdx, rbx; cbDest
0x180064bee  mov     rcx, rdi; pszDest
0x180064bf1  mov     [rsp+78h+var_58], rax
0x180064bf6  mov     r9, [r9+8]
0x180064bfa  call    StringCbPrintfW
0x180064bff  test    eax, eax
0x180064c01  js      loc_180064D01
0x180064c07  lea     rax, WPP_RECORDER_INITIALIZED
0x180064c0e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064c15  jz      short loc_180064C45
0x180064c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180064c1e  cmp     [rcx+48h], r13w
0x180064c23  jz      short loc_180064C45
0x180064c25  mov     rcx, [rcx+40h]
0x180064c29  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064c30  mov     r9d, 4Bh ; 'K'
0x180064c36  mov     [rsp+78h+var_50], rdi
0x180064c3b  mov     [rsp+78h+var_58], rax
0x180064c40  call    WPP_RECORDER_SF_S
0x180064c45  mov     rbx, [rsi]
0x180064c48  jmp     short loc_180064C6D
0x180064c4a  mov     rdx, [rbx+60h]; Str2
0x180064c4e  test    rdx, rdx
0x180064c51  jz      short loc_180064C6A
0x180064c53  mov     rcx, rdi; Str1
0x180064c56  call    cs:__imp__wcsicmp
0x180064c5d  nop     dword ptr [rax+rax+00h]
0x180064c62  test    eax, eax
0x180064c64  jz      loc_180064D29
0x180064c6a  mov     rbx, [rbx]
0x180064c6d  cmp     rbx, rsi
0x180064c70  jnz     short loc_180064C4A
0x180064c72  movzx   edx, word ptr [rbp+0]
0x180064c76  mov     r8d, 72645753h; Tag
0x180064c7c  add     rdx, 8Ah; NumberOfBytes
0x180064c83  mov     ecx, r15d; PoolType
0x180064c86  call    cs:__imp_ExAllocatePoolWithTag
0x180064c8d  nop     dword ptr [rax+rax+00h]
0x180064c92  mov     rbx, rax
0x180064c95  test    rax, rax
0x180064c98  jz      short loc_180064D01
0x180064c9a  xor     edx, edx; Val
0x180064c9c  mov     r8d, 88h; Size
0x180064ca2  mov     rcx, rax; void *
0x180064ca5  call    memset
0x180064caa  movzx   r8d, word ptr [rbp+0]
0x180064caf  lea     rcx, [rbx+88h]; void *
0x180064cb6  mov     rdx, [rbp+8]; Src
0x180064cba  add     r8, 2; Size
0x180064cbe  call    memmove
0x180064cc3  mov     rax, [r14+10h]
0x180064cc7  mov     r8d, 64695753h; Tag
0x180064ccd  mov     ecx, r15d; PoolType
0x180064cd0  movzx   edx, word ptr [rax]
0x180064cd3  add     rdx, 2; NumberOfBytes
0x180064cd7  call    cs:__imp_ExAllocatePoolWithTag
0x180064cde  nop     dword ptr [rax+rax+00h]
0x180064ce3  mov     [rbx+68h], rax
0x180064ce7  test    rax, rax
0x180064cea  jnz     loc_180064D8D
0x180064cf0  xor     edx, edx; Tag
0x180064cf2  mov     rcx, rbx; P
0x180064cf5  call    cs:__imp_ExFreePoolWithTag
0x180064cfc  nop     dword ptr [rax+rax+00h]
0x180064d01  xor     edx, edx; Tag
0x180064d03  mov     rcx, rdi; P
0x180064d06  call    cs:__imp_ExFreePoolWithTag
0x180064d0d  nop     dword ptr [rax+rax+00h]
0x180064d12  mov     eax, 0C000009Ah
0x180064d17  add     rsp, 38h
0x180064d1b  pop     r15
0x180064d1d  pop     r14
0x180064d1f  pop     r13
0x180064d21  pop     r12
0x180064d23  pop     rdi
0x180064d24  pop     rsi
0x180064d25  pop     rbp
0x180064d26  pop     rbx
0x180064d27  retn
0x180064d29  lea     rax, WPP_RECORDER_INITIALIZED
0x180064d30  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064d37  jz      short loc_180064D67
0x180064d39  mov     rcx, cs:WPP_GLOBAL_Control
0x180064d40  cmp     [rcx+48h], r13w
0x180064d45  jz      short loc_180064D67
0x180064d47  mov     rcx, [rcx+40h]
0x180064d4b  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064d52  mov     r9d, 4Ch ; 'L'
0x180064d58  mov     [rsp+78h+var_58], rax
0x180064d5d  mov     r8d, r15d
0x180064d60  mov     dl, 5
0x180064d62  call    WPP_RECORDER_SF_
0x180064d67  mov     [rbx+3Ch], r15b
0x180064d6b  cmp     rbx, rsi
0x180064d6e  jz      loc_180064C72
0x180064d74  xor     edx, edx; Tag
0x180064d76  mov     rcx, rdi; P
0x180064d79  call    cs:__imp_ExFreePoolWithTag
0x180064d80  nop     dword ptr [rax+rax+00h]
0x180064d85  mov     r15b, r13b
0x180064d88  jmp     loc_180064E37
0x180064d8d  mov     rdx, [r14+10h]
0x180064d91  mov     rcx, rax; void *
0x180064d94  movzx   r8d, word ptr [rdx]
0x180064d98  mov     rdx, [rdx+8]; Src
0x180064d9c  add     r8, 2; Size
0x180064da0  call    memmove
0x180064da5  mov     rcx, [r14+10h]; GuidString
0x180064da9  lea     rdx, [rbx+40h]; Guid
0x180064dad  call    cs:__imp_RtlGUIDFromString
0x180064db4  nop     dword ptr [rax+rax+00h]
0x180064db9  lea     rax, [rbx+20h]
0x180064dbd  mov     [rbx+3Ch], r15b
0x180064dc1  mov     [rax+8], rax
0x180064dc5  xor     ecx, ecx; PerformanceFrequency
0x180064dc7  mov     [rax], rax
0x180064dca  imul    rax, [rsi+2E8h], 0Fh
0x180064dd2  mov     [rbx+78h], rax
0x180064dd6  call    cs:__imp_KeQueryPerformanceCounter
0x180064ddd  nop     dword ptr [rax+rax+00h]
0x180064de2  mov     [rbx+70h], rax
0x180064de6  lea     rax, [rbx+10h]
0x180064dea  mov     [rbx+60h], rdi
0x180064dee  mov     [rax+8], rax
0x180064df2  mov     [rax], rax
0x180064df5  lea     rax, WPP_RECORDER_INITIALIZED
0x180064dfc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064e03  jz      short loc_180064E37
0x180064e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180064e0c  cmp     [rcx+48h], r13w
0x180064e11  jz      short loc_180064E37
0x180064e13  mov     rax, [rbx+60h]
0x180064e17  mov     r9d, 4Dh ; 'M'
0x180064e1d  mov     rcx, [rcx+40h]
0x180064e21  mov     [rsp+78h+var_50], rax
0x180064e26  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064e2d  mov     [rsp+78h+var_58], rax
0x180064e32  call    WPP_RECORDER_SF_S
0x180064e37  mov     [r14], rbx
0x180064e3a  lea     r8, CreateDeviceAssociation
0x180064e41  mov     [r14+18h], rbp
0x180064e45  mov     r9, r14
0x180064e48  mov     rdx, [rbp+8]
0x180064e4c  mov     rcx, r12
0x180064e4f  call    EnumerateRegistrySubKeys
0x180064e54  mov     edi, eax
0x180064e56  lea     rax, [rbx+10h]
0x180064e5a  cmp     [rax], rax
0x180064e5d  jnz     loc_180064EF0
0x180064e63  lea     rax, WPP_RECORDER_INITIALIZED
0x180064e6a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064e71  jz      short loc_180064EA2
0x180064e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180064e7a  cmp     [rcx+48h], r13w
0x180064e7f  jz      short loc_180064EA2
0x180064e81  mov     rcx, [rcx+40h]
0x180064e85  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180064e8c  mov     r9d, 4Eh ; 'N'
0x180064e92  mov     [rsp+78h+var_58], rax
0x180064e97  mov     dl, 5
0x180064e99  lea     r8d, [r9-4Dh]
0x180064e9d  call    WPP_RECORDER_SF_
0x180064ea2  mov     rcx, [rbx+68h]; P
0x180064ea6  test    rcx, rcx
0x180064ea9  jz      short loc_180064EBD
0x180064eab  xor     edx, edx; Tag
0x180064ead  call    cs:__imp_ExFreePoolWithTag
0x180064eb4  nop     dword ptr [rax+rax+00h]
0x180064eb9  mov     [rbx+68h], r13
0x180064ebd  mov     rcx, [rbx+60h]; P
0x180064ec1  test    rcx, rcx
0x180064ec4  jz      short loc_180064ED8
0x180064ec6  xor     edx, edx; Tag
0x180064ec8  call    cs:__imp_ExFreePoolWithTag
0x180064ecf  nop     dword ptr [rax+rax+00h]
0x180064ed4  mov     [rbx+60h], r13
0x180064ed8  xor     edx, edx; Tag
0x180064eda  mov     rcx, rbx; P
0x180064edd  call    cs:__imp_ExFreePoolWithTag
0x180064ee4  nop     dword ptr [rax+rax+00h]
0x180064ee9  mov     edi, 0C0000184h
0x180064eee  jmp     short loc_180064F68
0x180064ef0  test    r15b, r15b
0x180064ef3  jz      short loc_180064F68
0x180064ef5  test    edi, edi
0x180064ef7  js      short loc_180064F19
0x180064ef9  mov     rax, [rsi+8]
0x180064efd  cmp     [rax], rsi
0x180064f00  jz      short loc_180064F09
0x180064f02  mov     ecx, 3
0x180064f07  int     29h; Win8: RtlFailFast(ecx)
0x180064f09  mov     [rbx], rsi
0x180064f0c  mov     [rbx+8], rax
0x180064f10  mov     [rax], rbx
0x180064f13  mov     [rsi+8], rbx
0x180064f17  jmp     short loc_180064F68
0x180064f19  mov     rcx, rbx
0x180064f1c  call    RemoveDeviceAssociations
0x180064f21  mov     rcx, [rbx+60h]; P
0x180064f25  test    rcx, rcx
0x180064f28  jz      short loc_180064F3C
0x180064f2a  xor     edx, edx; Tag
0x180064f2c  call    cs:__imp_ExFreePoolWithTag
0x180064f33  nop     dword ptr [rax+rax+00h]
0x180064f38  mov     [rbx+60h], r13
0x180064f3c  mov     rcx, [rbx+68h]; P
0x180064f40  test    rcx, rcx
0x180064f43  jz      short loc_180064F57
0x180064f45  xor     edx, edx; Tag
0x180064f47  call    cs:__imp_ExFreePoolWithTag
0x180064f4e  nop     dword ptr [rax+rax+00h]
0x180064f53  mov     [rbx+68h], r13
0x180064f57  xor     edx, edx; Tag
0x180064f59  mov     rcx, rbx; P
0x180064f5c  call    cs:__imp_ExFreePoolWithTag
0x180064f63  nop     dword ptr [rax+rax+00h]
0x180064f68  mov     eax, edi
0x180064f6a  jmp     loc_180064D17
```
