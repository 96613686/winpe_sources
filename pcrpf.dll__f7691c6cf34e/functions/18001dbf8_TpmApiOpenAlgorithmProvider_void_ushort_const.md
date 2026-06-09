# TpmApiOpenAlgorithmProvider(void * *,ushort const *)

- ea: `0x18001dbf8`
- end: `0x18001dde9`
- name: `?TpmApiOpenAlgorithmProvider@@YAJPEAPEAXPEBG@Z`
- size: `497`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dfd8`

## callees

- `0x18001ced4`
- `0x18001dbf8`
- `0x18001ddf0`
- `0x180059010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001dc40`
- `ntdll!RtlInitUnicodeString` at `0x18001dc57`
- `ntdll!RtlInitUnicodeString` at `0x18001dd57`
- `ntdll!RtlInitUnicodeString` at `0x18001dd6e`
- `ntdll!RtlInitUnicodeString` at `0x18001dc40`
- `ntdll!RtlInitUnicodeString` at `0x18001dc57`
- `ntdll!RtlInitUnicodeString` at `0x18001dd57`
- `ntdll!RtlInitUnicodeString` at `0x18001dd6e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001dd18`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001ddb4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001dd18`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001ddb4`

## string_xrefs

- `0x18001dc28`: `\Registry\Machine\System\CurrentControlSet\Control\BitLocker`
- `0x18001dd44`: `\Registry\Machine\System\CurrentControlSet\Control\BitLocker`

## pseudocode

```c
__int64 __fastcall TpmApiOpenAlgorithmProvider(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId)
{
  const WCHAR *v4; // rbx
  int Value; // eax
  unsigned int v6; // edi
  NTSTATUS v7; // edi
  void *v9; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING v10; // [rsp+38h] [rbp-48h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING v12; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING v13; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v14; // [rsp+B0h] [rbp+30h] BYREF
  unsigned int v15; // [rsp+B8h] [rbp+38h] BYREF

  v14 = 0;
  v9 = 0;
  DestinationString = 0;
  v4 = 0;
  v10 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\BitLocker");
  RtlInitUnicodeString(&v10, L"AlgorithmProvider");
  Value = TpmApiRegistryGetValue(&DestinationString, &v10, 1u, 0, &v14);
  v6 = v14;
  if ( Value == -1073741789 )
  {
    if ( qword_180072B30 )
      qword_180072B30(0, v14, &v9);
    if ( v9 )
    {
      v14 = v6;
      if ( TpmApiRegistryGetValue(&DestinationString, &v10, 1u, v9, &v14) >= 0
        && v14 == v6
        && v14 >= 2
        && (v14 & 1) == 0 )
      {
        *((_WORD *)v9 + ((unsigned __int64)v14 >> 1) - 1) = 0;
        v4 = (const WCHAR *)v9;
        v9 = 0;
      }
    }
  }
  TpmApiCallbackFree(0, v6);
  v7 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, v4, 0);
  if ( v7 < 0 )
  {
    if ( v4 )
    {
      v14 = 0;
      v13 = 0;
      v12 = 0;
      RtlInitUnicodeString(&v13, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\BitLocker");
      RtlInitUnicodeString(&v12, L"DefaultToExistingProviders");
      v15 = 4;
      if ( TpmApiRegistryGetValue(&v13, &v12, 4u, &v14, &v15) < 0 || v14 )
        v7 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, 0, 0);
    }
  }
  TpmApiCallbackFree(0, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001dbf8  mov     [rsp-18h+arg_0], rbx
0x18001dbfd  mov     [rsp-18h+arg_8], rsi
0x18001dc02  push    rbp
0x18001dc03  push    rdi
0x18001dc04  push    r14
0x18001dc06  mov     rbp, rsp
0x18001dc09  sub     rsp, 80h
0x18001dc10  mov     rsi, rdx
0x18001dc13  mov     [rbp+arg_10], 0
0x18001dc1a  mov     r14, rcx
0x18001dc1d  mov     [rbp+var_50], 0
0x18001dc25  xorps   xmm0, xmm0
0x18001dc28  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001dc2f  xorps   xmm1, xmm1
0x18001dc32  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001dc36  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001dc3a  xor     ebx, ebx
0x18001dc3c  movups  xmmword ptr [rbp+var_48.Length], xmm1
0x18001dc40  call    cs:__imp_RtlInitUnicodeString
0x18001dc47  nop     dword ptr [rax+rax+00h]
0x18001dc4c  lea     rdx, aAlgorithmprovi; "AlgorithmProvider"
0x18001dc53  lea     rcx, [rbp+var_48]; DestinationString
0x18001dc57  call    cs:__imp_RtlInitUnicodeString
0x18001dc5e  nop     dword ptr [rax+rax+00h]
0x18001dc63  lea     rax, [rbp+arg_10]
0x18001dc67  xor     r9d, r9d; void *
0x18001dc6a  lea     r8d, [rbx+1]; unsigned int
0x18001dc6e  mov     [rsp+80h+var_60], rax; unsigned int *
0x18001dc73  lea     rdx, [rbp+var_48]; struct _UNICODE_STRING *
0x18001dc77  lea     rcx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x18001dc7b  call    ?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z; TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)
0x18001dc80  mov     edi, [rbp+arg_10]
0x18001dc83  cmp     eax, 0C0000023h
0x18001dc88  jnz     short loc_18001DCFF
0x18001dc8a  mov     rax, cs:qword_180072B30
0x18001dc91  test    rax, rax
0x18001dc94  jz      short loc_18001DCA3
0x18001dc96  lea     r8, [rbp+var_50]
0x18001dc9a  mov     edx, edi
0x18001dc9c  xor     ecx, ecx
0x18001dc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca3  mov     r8, [rbp+var_50]
0x18001dca7  test    r8, r8
0x18001dcaa  jz      short loc_18001DD03
0x18001dcac  lea     rax, [rbp+arg_10]
0x18001dcb0  mov     [rbp+arg_10], edi
0x18001dcb3  mov     r9, r8; void *
0x18001dcb6  mov     [rsp+80h+var_60], rax; unsigned int *
0x18001dcbb  mov     r8d, 1; unsigned int
0x18001dcc1  lea     rdx, [rbp+var_48]; struct _UNICODE_STRING *
0x18001dcc5  lea     rcx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x18001dcc9  call    ?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z; TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)
0x18001dcce  test    eax, eax
0x18001dcd0  js      short loc_18001DCFF
0x18001dcd2  mov     eax, [rbp+arg_10]
0x18001dcd5  cmp     eax, edi
0x18001dcd7  jnz     short loc_18001DCFF
0x18001dcd9  cmp     eax, 2
0x18001dcdc  jb      short loc_18001DCFF
0x18001dcde  test    al, 1
0x18001dce0  jnz     short loc_18001DCFF
0x18001dce2  mov     edx, eax
0x18001dce4  xor     ecx, ecx
0x18001dce6  mov     rax, [rbp+var_50]
0x18001dcea  shr     rdx, 1
0x18001dced  xor     r8d, r8d
0x18001dcf0  mov     [rax+rdx*2-2], cx
0x18001dcf5  mov     rbx, [rbp+var_50]
0x18001dcf9  mov     [rbp+var_50], r8
0x18001dcfd  jmp     short loc_18001DD03
0x18001dcff  mov     r8, [rbp+var_50]
0x18001dd03  mov     edx, edi
0x18001dd05  xor     ecx, ecx
0x18001dd07  call    TpmApiCallbackFree
0x18001dd0c  xor     r9d, r9d; dwFlags
0x18001dd0f  mov     r8, rbx; pszImplementation
0x18001dd12  mov     rdx, rsi; pszAlgId
0x18001dd15  mov     rcx, r14; phAlgorithm
0x18001dd18  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001dd1f  nop     dword ptr [rax+rax+00h]
0x18001dd24  mov     edi, eax
0x18001dd26  test    eax, eax
0x18001dd28  jns     loc_18001DDC2
0x18001dd2e  test    rbx, rbx
0x18001dd31  jz      loc_18001DDC2
0x18001dd37  xorps   xmm0, xmm0
0x18001dd3a  mov     [rbp+arg_10], 0
0x18001dd41  xorps   xmm1, xmm1
0x18001dd44  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001dd4b  lea     rcx, [rbp+var_18]; DestinationString
0x18001dd4f  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x18001dd53  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x18001dd57  call    cs:__imp_RtlInitUnicodeString
0x18001dd5e  nop     dword ptr [rax+rax+00h]
0x18001dd63  lea     rdx, aDefaulttoexist; "DefaultToExistingProviders"
0x18001dd6a  lea     rcx, [rbp+var_28]; DestinationString
0x18001dd6e  call    cs:__imp_RtlInitUnicodeString
0x18001dd75  nop     dword ptr [rax+rax+00h]
0x18001dd7a  mov     r8d, 4; unsigned int
0x18001dd80  lea     rax, [rbp+arg_18]
0x18001dd84  lea     r9, [rbp+arg_10]; void *
0x18001dd88  mov     [rbp+arg_18], r8d
0x18001dd8c  lea     rdx, [rbp+var_28]; struct _UNICODE_STRING *
0x18001dd90  mov     [rsp+80h+var_60], rax; unsigned int *
0x18001dd95  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING *
0x18001dd99  call    ?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z; TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)
0x18001dd9e  test    eax, eax
0x18001dda0  js      short loc_18001DDA8
0x18001dda2  cmp     [rbp+arg_10], 0
0x18001dda6  jz      short loc_18001DDC2
0x18001dda8  xor     r9d, r9d; dwFlags
0x18001ddab  xor     r8d, r8d; pszImplementation
0x18001ddae  mov     rdx, rsi; pszAlgId
0x18001ddb1  mov     rcx, r14; phAlgorithm
0x18001ddb4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001ddbb  nop     dword ptr [rax+rax+00h]
0x18001ddc0  mov     edi, eax
0x18001ddc2  mov     r8, rbx
0x18001ddc5  xor     edx, edx
0x18001ddc7  xor     ecx, ecx
0x18001ddc9  call    TpmApiCallbackFree
0x18001ddce  lea     r11, [rsp+80h+var_s0]
0x18001ddd6  mov     eax, edi
0x18001ddd8  mov     rbx, [r11+20h]
0x18001dddc  mov     rsi, [r11+28h]
0x18001dde0  mov     rsp, r11
0x18001dde3  pop     r14
0x18001dde5  pop     rdi
0x18001dde6  pop     rbp
0x18001dde7  retn
```
