# EnumerateRegistryValues

- ea: `0x1800666b4`
- end: `0x180066913`
- name: `EnumerateRegistryValues`
- size: `607`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180034ba0`

## callees

- `0x18000c058`
- `0x18000c630`
- `0x180019bd0`
- `0x18001a000`
- `0x1800666b4`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1800668de`
- `ntoskrnl!ZwSetValueKey` at `0x1800668de`
- `ntoskrnl!ZwQueryKey` at `0x180066713`
- `ntoskrnl!ZwQueryKey` at `0x180066713`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180066872`
- `ntoskrnl!ZwEnumerateValueKey` at `0x180066872`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066900`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066900`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066812`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066812`

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
0x1800666b4  mov     [rsp-38h+arg_8], rbx
0x1800666b9  push    rbp
0x1800666ba  push    rsi
0x1800666bb  push    rdi
0x1800666bc  push    r12
0x1800666be  push    r13
0x1800666c0  push    r14
0x1800666c2  push    r15
0x1800666c4  mov     rbp, rsp
0x1800666c7  sub     rsp, 80h
0x1800666ce  mov     rax, cs:__security_cookie
0x1800666d5  xor     rax, rsp
0x1800666d8  mov     [rbp+var_8], rax
0x1800666dc  xorps   xmm0, xmm0
0x1800666df  lea     rax, [rbp+var_50]
0x1800666e3  xor     r12d, r12d
0x1800666e6  mov     [rsp+80h+ResultLength], rax; ResultLength
0x1800666eb  mov     r13, r8
0x1800666ee  mov     [rbp+var_50], r12d
0x1800666f2  lea     r8, [rbp+KeyInformation]; KeyInformation
0x1800666f6  mov     r15, rcx
0x1800666f9  movups  [rbp+KeyInformation], xmm0
0x1800666fd  lea     r9d, [r12+30h]; Length
0x180066702  lea     edx, [r12+2]; KeyInformationClass
0x180066707  movups  [rbp+var_28], xmm0
0x18006670b  movups  [rbp+var_18], xmm0
0x18006670f  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x180066713  call    cs:__imp_ZwQueryKey
0x18006671a  nop     dword ptr [rax+rax+00h]
0x18006671f  mov     esi, eax
0x180066721  test    eax, eax
0x180066723  jns     short loc_180066795
0x180066725  lea     rcx, WPP_RECORDER_INITIALIZED
0x18006672c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180066733  jz      short loc_180066768
0x180066735  mov     rcx, cs:WPP_GLOBAL_Control
0x18006673c  cmp     [rcx+48h], r12w
0x180066741  jz      short loc_180066768
0x180066743  mov     rcx, [rcx+40h]
0x180066747  lea     r9d, [r12+44h]
0x18006674c  mov     dword ptr [rsp+80h+var_58], eax
0x180066750  lea     r8d, [r12+1]
0x180066755  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18006675c  mov     dl, 5
0x18006675e  mov     [rsp+80h+ResultLength], rax
0x180066763  call    WPP_RECORDER_SF_D
0x180066768  mov     eax, 0C000009Ah
0x18006676d  mov     rcx, [rbp+var_8]
0x180066771  xor     rcx, rsp; StackCookie
0x180066774  call    __security_check_cookie
0x180066779  mov     rbx, [rsp+80h+arg_8]
0x180066781  add     rsp, 80h
0x180066788  pop     r15
0x18006678a  pop     r14
0x18006678c  pop     r13
0x18006678e  pop     r12
0x180066790  pop     rdi
0x180066791  pop     rsi
0x180066792  pop     rbp
0x180066793  retn
0x180066795  lea     rcx, WPP_RECORDER_INITIALIZED
0x18006679c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800667a3  jz      short loc_1800667D7
0x1800667a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667ac  cmp     [rcx+48h], r12w
0x1800667b1  jz      short loc_1800667D7
0x1800667b3  mov     eax, dword ptr [rbp+var_18]
0x1800667b6  mov     r9d, 45h ; 'E'
0x1800667bc  mov     rcx, [rcx+40h]
0x1800667c0  mov     dl, 5
0x1800667c2  mov     dword ptr [rsp+80h+var_58], eax
0x1800667c6  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800667cd  mov     [rsp+80h+ResultLength], rax
0x1800667d2  call    WPP_RECORDER_SF_d
0x1800667d7  mov     ecx, dword ptr [rbp+var_18+4]
0x1800667da  mov     eax, 0FFFFFFFFh
0x1800667df  add     rcx, rcx
0x1800667e2  cmp     rcx, rax
0x1800667e5  ja      short loc_180066768
0x1800667e7  mov     edx, dword ptr [rbp+var_18+8]
0x1800667ea  add     edx, ecx
0x1800667ec  cmp     edx, ecx
0x1800667ee  jb      loc_180066768
0x1800667f4  lea     r14d, [rdx+18h]
0x1800667f8  cmp     r14d, edx
0x1800667fb  jb      loc_180066768
0x180066801  mov     r8d, 696B5753h; Tag
0x180066807  mov     edx, r14d; NumberOfBytes
0x18006680a  mov     ecx, 401h; PoolType
0x18006680f  mov     edi, r14d
0x180066812  call    cs:__imp_ExAllocatePoolWithTag
0x180066819  nop     dword ptr [rax+rax+00h]
0x18006681e  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x180066825  mov     rbx, rax
0x180066828  jnz     short loc_180066840
0x18006682a  test    rax, rax
0x18006682d  jz      loc_180066768
0x180066833  mov     r8d, edi; Size
0x180066836  xor     edx, edx; Val
0x180066838  mov     rcx, rax; void *
0x18006683b  call    memset
0x180066840  test    rbx, rbx
0x180066843  jz      loc_180066768
0x180066849  mov     edi, r12d
0x18006684c  cmp     dword ptr [rbp+var_18], r12d
0x180066850  jbe     loc_1800668FB
0x180066856  lea     rax, [rbp+var_50]
0x18006685a  mov     r9, rbx; KeyValueInformation
0x18006685d  mov     [rsp+80h+var_58], rax; ResultLength
0x180066862  mov     r8d, 1; KeyValueInformationClass
0x180066868  mov     edx, edi; Index
0x18006686a  mov     dword ptr [rsp+80h+ResultLength], r14d; Length
0x18006686f  mov     rcx, r15; KeyHandle
0x180066872  call    cs:__imp_ZwEnumerateValueKey
0x180066879  nop     dword ptr [rax+rax+00h]
0x18006687e  mov     esi, eax
0x180066880  test    eax, eax
0x180066882  js      short loc_1800668F0
0x180066884  lea     rdx, [rbx+14h]
0x180066888  mov     r8d, 2
0x18006688e  mov     [rbp+ValueName.Buffer], rdx
0x180066892  movzx   ecx, word ptr [rbx+10h]
0x180066896  mov     [rbp+ValueName.Length], cx
0x18006689a  movzx   eax, word ptr [rbx+10h]
0x18006689e  mov     [rbp+ValueName.MaximumLength], ax
0x1800668a2  cmp     cx, r8w
0x1800668a6  jb      short loc_1800668BD
0x1800668a8  mov     eax, ecx
0x1800668aa  shr     rax, 1
0x1800668ad  cmp     [rdx+rax*2-2], r12w
0x1800668b3  jnz     short loc_1800668BD
0x1800668b5  sub     cx, r8w
0x1800668b9  mov     [rbp+ValueName.Length], cx
0x1800668bd  mov     ecx, [rbx+8]
0x1800668c0  lea     rdx, [rbp+ValueName]; ValueName
0x1800668c4  mov     eax, [rbx+0Ch]
0x1800668c7  add     rcx, rbx
0x1800668ca  mov     r9d, [rbx+4]; Type
0x1800668ce  xor     r8d, r8d; TitleIndex
0x1800668d1  mov     dword ptr [rsp+80h+var_58], eax; DataSize
0x1800668d5  mov     [rsp+80h+ResultLength], rcx; Data
0x1800668da  mov     rcx, [r13+8]; KeyHandle
0x1800668de  call    cs:__imp_ZwSetValueKey
0x1800668e5  nop     dword ptr [rax+rax+00h]
0x1800668ea  mov     esi, eax
0x1800668ec  test    eax, eax
0x1800668ee  js      short loc_1800668FB
0x1800668f0  inc     edi
0x1800668f2  cmp     edi, dword ptr [rbp+var_18]
0x1800668f5  jb      loc_180066856
0x1800668fb  xor     edx, edx; Tag
0x1800668fd  mov     rcx, rbx; P
0x180066900  call    cs:__imp_ExFreePoolWithTag
0x180066907  nop     dword ptr [rax+rax+00h]
0x18006690c  mov     eax, esi
0x18006690e  jmp     loc_18006676D
```
