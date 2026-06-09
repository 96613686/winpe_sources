# EnumerateRegistryValues

- ea: `0x180065d44`
- end: `0x180065fa3`
- name: `EnumerateRegistryValues`
- size: `607`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180034a90`

## callees

- `0x18000c058`
- `0x18000c630`
- `0x180019b80`
- `0x180019fc0`
- `0x180065d44`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x180065f6e`
- `ntoskrnl!ZwSetValueKey` at `0x180065f6e`
- `ntoskrnl!ZwQueryKey` at `0x180065da3`
- `ntoskrnl!ZwQueryKey` at `0x180065da3`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180065f02`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180065f02`
- `ntoskrnl!ExFreePoolWithTag` at `0x180065f90`
- `ntoskrnl!ExFreePoolWithTag` at `0x180065f90`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180065ea2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180065ea2`

## pseudocode

```c
__int64 __fastcall EnumerateRegistryValues(HANDLE KeyHandle, __int64 a2, __int64 a3)
{
  NTSTATUS v5; // eax
  int v6; // edx
  int v7; // r8d
  NTSTATUS v8; // esi
  unsigned __int64 v10; // rcx
  unsigned int v11; // edx
  ULONG v12; // r14d
  char *PoolWithTag; // rax
  char *v14; // rbx
  ULONG i; // edi
  unsigned int v16; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-50h] BYREF
  UNICODE_STRING ValueName; // [rsp+38h] [rbp-48h] BYREF
  _OWORD KeyInformation[2]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v20; // [rsp+68h] [rbp-18h]

  ResultLength = 0;
  memset(KeyInformation, 0, sizeof(KeyInformation));
  v20 = 0;
  ValueName = 0;
  v5 = ZwQueryKey(KeyHandle, KeyFullInformation, KeyInformation, 0x30u, &ResultLength);
  v8 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v6) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          68,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          v5);
      }
    }
    return 3221225626LL;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v7,
      69,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
      v20);
  }
  v10 = 2LL * DWORD1(v20);
  if ( v10 > 0xFFFFFFFF )
    return 3221225626LL;
  v11 = v10 + DWORD2(v20);
  if ( (int)v10 + DWORD2(v20) < (unsigned int)v10 )
    return 3221225626LL;
  v12 = v11 + 24;
  if ( v11 + 24 < v11 )
    return 3221225626LL;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, v12, 0x696B5753u);
  v14 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
      return 3221225626LL;
    memset(PoolWithTag, 0, v12);
  }
  if ( !v14 )
    return 3221225626LL;
  for ( i = 0; i < (unsigned int)v20; ++i )
  {
    v8 = ZwEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, v14, v12, &ResultLength);
    if ( v8 >= 0 )
    {
      ValueName.Buffer = (wchar_t *)(v14 + 20);
      v16 = *((unsigned __int16 *)v14 + 8);
      ValueName.Length = v16;
      ValueName.MaximumLength = *((_WORD *)v14 + 8);
      if ( (unsigned __int16)v16 >= 2u && !*(_WORD *)&v14[2 * ((unsigned __int64)v16 >> 1) + 18] )
        ValueName.Length = v16 - 2;
      v8 = ZwSetValueKey(
             *(HANDLE *)(a3 + 8),
             &ValueName,
             0,
             *((_DWORD *)v14 + 1),
             &v14[*((unsigned int *)v14 + 2)],
             *((_DWORD *)v14 + 3));
      if ( v8 < 0 )
        break;
    }
  }
  ExFreePoolWithTag(v14, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180065d44  mov     [rsp-38h+arg_8], rbx
0x180065d49  push    rbp
0x180065d4a  push    rsi
0x180065d4b  push    rdi
0x180065d4c  push    r12
0x180065d4e  push    r13
0x180065d50  push    r14
0x180065d52  push    r15
0x180065d54  mov     rbp, rsp
0x180065d57  sub     rsp, 80h
0x180065d5e  mov     rax, cs:__security_cookie
0x180065d65  xor     rax, rsp
0x180065d68  mov     [rbp+var_8], rax
0x180065d6c  xorps   xmm0, xmm0
0x180065d6f  lea     rax, [rbp+var_50]
0x180065d73  xor     r12d, r12d
0x180065d76  mov     [rsp+80h+ResultLength], rax; ResultLength
0x180065d7b  mov     r13, r8
0x180065d7e  mov     [rbp+var_50], r12d
0x180065d82  lea     r8, [rbp+KeyInformation]; KeyInformation
0x180065d86  mov     r15, rcx
0x180065d89  movups  [rbp+KeyInformation], xmm0
0x180065d8d  lea     r9d, [r12+30h]; Length
0x180065d92  lea     edx, [r12+2]; KeyInformationClass
0x180065d97  movups  [rbp+var_28], xmm0
0x180065d9b  movups  [rbp+var_18], xmm0
0x180065d9f  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x180065da3  call    cs:__imp_ZwQueryKey
0x180065daa  nop     dword ptr [rax+rax+00h]
0x180065daf  mov     esi, eax
0x180065db1  test    eax, eax
0x180065db3  jns     short loc_180065E25
0x180065db5  lea     rcx, WPP_RECORDER_INITIALIZED
0x180065dbc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180065dc3  jz      short loc_180065DF8
0x180065dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180065dcc  cmp     [rcx+48h], r12w
0x180065dd1  jz      short loc_180065DF8
0x180065dd3  mov     rcx, [rcx+40h]
0x180065dd7  lea     r9d, [r12+44h]
0x180065ddc  mov     dword ptr [rsp+80h+var_58], eax
0x180065de0  lea     r8d, [r12+1]
0x180065de5  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180065dec  mov     dl, 5
0x180065dee  mov     [rsp+80h+ResultLength], rax
0x180065df3  call    WPP_RECORDER_SF_D
0x180065df8  mov     eax, 0C000009Ah
0x180065dfd  mov     rcx, [rbp+var_8]
0x180065e01  xor     rcx, rsp; StackCookie
0x180065e04  call    __security_check_cookie
0x180065e09  mov     rbx, [rsp+80h+arg_8]
0x180065e11  add     rsp, 80h
0x180065e18  pop     r15
0x180065e1a  pop     r14
0x180065e1c  pop     r13
0x180065e1e  pop     r12
0x180065e20  pop     rdi
0x180065e21  pop     rsi
0x180065e22  pop     rbp
0x180065e23  retn
0x180065e25  lea     rcx, WPP_RECORDER_INITIALIZED
0x180065e2c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180065e33  jz      short loc_180065E67
0x180065e35  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e3c  cmp     [rcx+48h], r12w
0x180065e41  jz      short loc_180065E67
0x180065e43  mov     eax, dword ptr [rbp+var_18]
0x180065e46  mov     r9d, 45h ; 'E'
0x180065e4c  mov     rcx, [rcx+40h]
0x180065e50  mov     dl, 5
0x180065e52  mov     dword ptr [rsp+80h+var_58], eax
0x180065e56  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180065e5d  mov     [rsp+80h+ResultLength], rax
0x180065e62  call    WPP_RECORDER_SF_d
0x180065e67  mov     ecx, dword ptr [rbp+var_18+4]
0x180065e6a  mov     eax, 0FFFFFFFFh
0x180065e6f  add     rcx, rcx
0x180065e72  cmp     rcx, rax
0x180065e75  ja      short loc_180065DF8
0x180065e77  mov     edx, dword ptr [rbp+var_18+8]
0x180065e7a  add     edx, ecx
0x180065e7c  cmp     edx, ecx
0x180065e7e  jb      loc_180065DF8
0x180065e84  lea     r14d, [rdx+18h]
0x180065e88  cmp     r14d, edx
0x180065e8b  jb      loc_180065DF8
0x180065e91  mov     r8d, 696B5753h; Tag
0x180065e97  mov     edx, r14d; NumberOfBytes
0x180065e9a  mov     ecx, 401h; PoolType
0x180065e9f  mov     edi, r14d
0x180065ea2  call    cs:__imp_ExAllocatePoolWithTag
0x180065ea9  nop     dword ptr [rax+rax+00h]
0x180065eae  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x180065eb5  mov     rbx, rax
0x180065eb8  jnz     short loc_180065ED0
0x180065eba  test    rax, rax
0x180065ebd  jz      loc_180065DF8
0x180065ec3  mov     r8d, edi; Size
0x180065ec6  xor     edx, edx; Val
0x180065ec8  mov     rcx, rax; void *
0x180065ecb  call    memset
0x180065ed0  test    rbx, rbx
0x180065ed3  jz      loc_180065DF8
0x180065ed9  mov     edi, r12d
0x180065edc  cmp     dword ptr [rbp+var_18], r12d
0x180065ee0  jbe     loc_180065F8B
0x180065ee6  lea     rax, [rbp+var_50]
0x180065eea  mov     r9, rbx; KeyValueInformation
0x180065eed  mov     [rsp+80h+var_58], rax; ResultLength
0x180065ef2  mov     r8d, 1; KeyValueInformationClass
0x180065ef8  mov     edx, edi; Index
0x180065efa  mov     dword ptr [rsp+80h+ResultLength], r14d; Length
0x180065eff  mov     rcx, r15; KeyHandle
0x180065f02  call    cs:__imp_ZwEnumerateValueKey
0x180065f09  nop     dword ptr [rax+rax+00h]
0x180065f0e  mov     esi, eax
0x180065f10  test    eax, eax
0x180065f12  js      short loc_180065F80
0x180065f14  lea     rdx, [rbx+14h]
0x180065f18  mov     r8d, 2
0x180065f1e  mov     [rbp+ValueName.Buffer], rdx
0x180065f22  movzx   ecx, word ptr [rbx+10h]
0x180065f26  mov     [rbp+ValueName.Length], cx
0x180065f2a  movzx   eax, word ptr [rbx+10h]
0x180065f2e  mov     [rbp+ValueName.MaximumLength], ax
0x180065f32  cmp     cx, r8w
0x180065f36  jb      short loc_180065F4D
0x180065f38  mov     eax, ecx
0x180065f3a  shr     rax, 1
0x180065f3d  cmp     [rdx+rax*2-2], r12w
0x180065f43  jnz     short loc_180065F4D
0x180065f45  sub     cx, r8w
0x180065f49  mov     [rbp+ValueName.Length], cx
0x180065f4d  mov     ecx, [rbx+8]
0x180065f50  lea     rdx, [rbp+ValueName]; ValueName
0x180065f54  mov     eax, [rbx+0Ch]
0x180065f57  add     rcx, rbx
0x180065f5a  mov     r9d, [rbx+4]; Type
0x180065f5e  xor     r8d, r8d; TitleIndex
0x180065f61  mov     dword ptr [rsp+80h+var_58], eax; DataSize
0x180065f65  mov     [rsp+80h+ResultLength], rcx; Data
0x180065f6a  mov     rcx, [r13+8]; KeyHandle
0x180065f6e  call    cs:__imp_ZwSetValueKey
0x180065f75  nop     dword ptr [rax+rax+00h]
0x180065f7a  mov     esi, eax
0x180065f7c  test    eax, eax
0x180065f7e  js      short loc_180065F8B
0x180065f80  inc     edi
0x180065f82  cmp     edi, dword ptr [rbp+var_18]
0x180065f85  jb      loc_180065EE6
0x180065f8b  xor     edx, edx; Tag
0x180065f8d  mov     rcx, rbx; P
0x180065f90  call    cs:__imp_ExFreePoolWithTag
0x180065f97  nop     dword ptr [rax+rax+00h]
0x180065f9c  mov     eax, esi
0x180065f9e  jmp     loc_180065DFD
```
