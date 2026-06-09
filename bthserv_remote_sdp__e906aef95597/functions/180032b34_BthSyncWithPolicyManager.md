# BthSyncWithPolicyManager

- ea: `0x180032b34`
- end: `0x180032dda`
- name: `BthSyncWithPolicyManager`
- size: `678`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180010f60`
- `0x18001dd58`

## callees

- `0x1800026d0`
- `0x1800026dc`
- `0x1800026e8`
- `0x18000270c`
- `0x18003278c`
- `0x1800328b4`
- `0x1800329a0`
- `0x180032b34`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180032c66`
- `ntdll!RtlInitUnicodeString` at `0x180032c66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032d39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032d39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032db6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032db6`
- `policymanager!PolicyManager_GetPolicyString` at `0x180032c0d`
- `policymanager!PolicyManager_GetPolicyString` at `0x180032c98`
- `policymanager!PolicyManager_GetPolicyString` at `0x180032cee`
- `policymanager!PolicyManager_GetPolicyString` at `0x180032c0d`
- `policymanager!PolicyManager_GetPolicyString` at `0x180032c98`
- `policymanager!PolicyManager_GetPolicyString` at `0x180032cee`
- `policymanager!PolicyManager_FreeStringValue` at `0x180032c7a`
- `policymanager!PolicyManager_FreeStringValue` at `0x180032cd0`
- `policymanager!PolicyManager_FreeStringValue` at `0x180032d26`
- `policymanager!PolicyManager_FreeStringValue` at `0x180032c7a`
- `policymanager!PolicyManager_FreeStringValue` at `0x180032cd0`
- `policymanager!PolicyManager_FreeStringValue` at `0x180032d26`

## string_xrefs

- `0x180032ce0`: `ServicesAllowedList`

## pseudocode

```c
__int64 BthSyncWithPolicyManager()
{
  wchar_t *v0; // rdi
  __int64 v1; // rbx
  __int64 v2; // rcx
  wchar_t *v3; // rax
  const WCHAR *v4; // rsi
  unsigned __int16 v5; // dx
  unsigned __int16 v6; // dx
  __int128 v8; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+40h] [rbp-30h] BYREF
  struct _GUID *v11[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v12; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+90h] [rbp+20h] BYREF
  wchar_t *Source; // [rsp+98h] [rbp+28h] BYREF

  Source = 0;
  memset_0(&v8, 0, 0x50u);
  BthReadPolicyManagerPolicyValue(&v8, 1, &v8);
  BthReadPolicyManagerPolicyValue(&v8, 2, (char *)&v8 + 4);
  BthReadPolicyManagerPolicyValue(&v8, 4, (char *)&v8 + 8);
  BthReadPolicyManagerPolicyValue(&v8, 8, (char *)&v8 + 12);
  BthReadPolicyManagerPolicyValue(&v8, 16, &DestinationString);
  BthReadPolicyManagerPolicyValue(&v8, 32, &DestinationString.MaximumLength + 1);
  BthReadPolicyManagerPolicyValue(&v8, 512, &v11[1]);
  BthReadPolicyManagerPolicyValue(&v8, 1024, (char *)&v11[1] + 4);
  BthReadPolicyManagerPolicyValue(&v8, 2048, &v12);
  if ( (int)PolicyManager_GetPolicyString(L"Bluetooth", L"LocalDeviceName", &Source) >= 0 )
  {
    v0 = Source;
    v1 = -1;
    v2 = -1;
    do
      ++v2;
    while ( Source[v2] );
    v3 = (wchar_t *)o_malloc_0(2 * v2 + 2);
    v4 = v3;
    do
      ++v1;
    while ( v0[v1] );
    if ( !wcscpy_s(v3, v1 + 1, v0) )
    {
      RtlInitUnicodeString((PUNICODE_STRING)&DestinationString.Buffer, v4);
      DWORD1(v12) |= 0x40u;
    }
    PolicyManager_FreeStringValue(Source);
  }
  if ( (int)PolicyManager_GetPolicyString(L"Bluetooth", L"DevicesAllowedList", &Source) >= 0 )
  {
    v13 = 0;
    if ( (int)TokenListToBthAddrArray(Source, v5, (unsigned __int64 **)&v10 + 1, &v13) >= 0 )
    {
      DWORD1(v12) |= 0x80u;
      DWORD2(v12) = v13;
    }
    PolicyManager_FreeStringValue(Source);
  }
  if ( (int)PolicyManager_GetPolicyString(L"Bluetooth", L"ServicesAllowedList", &Source) >= 0 )
  {
    v13 = 0;
    if ( (int)TokenListToGuidArray(Source, v6, v11, &v13) >= 0 )
    {
      DWORD1(v12) |= 0x100u;
      HIDWORD(v12) = v13;
    }
    PolicyManager_FreeStringValue(Source);
  }
  EnterCriticalSection(&g_PolicyLock);
  if ( *(_QWORD *)&ymmword_180046F70.m256_f32[4] )
    free(*(void **)&ymmword_180046F70.m256_f32[4]);
  if ( *(_QWORD *)&ymmword_180046F70.m256_f32[6] )
    free(*(void **)&ymmword_180046F70.m256_f32[6]);
  if ( Src )
    free(Src);
  g_Policies = v8;
  *(_OWORD *)&ymmword_180046F70.m256_f32[4] = v10;
  *(struct _UNICODE_STRING *)ymmword_180046F70.m256_f32 = DestinationString;
  *(_OWORD *)byte_180046FA0 = v12;
  *(_OWORD *)&Src = *(_OWORD *)v11;
  LeaveCriticalSection(&g_PolicyLock);
  return 0;
}

```

## disassembly

```asm
0x180032b34  mov     [rsp-18h+arg_10], rbx
0x180032b39  mov     [rsp-18h+arg_18], rsi
0x180032b3e  push    rbp
0x180032b3f  push    rdi
0x180032b40  push    r14
0x180032b42  mov     rbp, rsp
0x180032b45  sub     rsp, 70h
0x180032b49  xor     r14d, r14d
0x180032b4c  lea     rcx, [rbp+var_50]; void *
0x180032b50  xor     edx, edx; Val
0x180032b52  mov     [rbp+Source], r14
0x180032b56  lea     r8d, [r14+50h]; Size
0x180032b5a  call    memset_0
0x180032b5f  lea     r8, [rbp+var_50]
0x180032b63  lea     edx, [r14+1]
0x180032b67  lea     rcx, [rbp+var_50]
0x180032b6b  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032b70  lea     r8, [rbp+var_50+4]
0x180032b74  lea     edx, [r14+2]
0x180032b78  lea     rcx, [rbp+var_50]
0x180032b7c  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032b81  lea     r8, [rbp+var_50+8]
0x180032b85  lea     edx, [r14+4]
0x180032b89  lea     rcx, [rbp+var_50]
0x180032b8d  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032b92  lea     r8, [rbp+var_50+0Ch]
0x180032b96  lea     edx, [r14+8]
0x180032b9a  lea     rcx, [rbp+var_50]
0x180032b9e  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032ba3  lea     r8, [rbp+DestinationString]
0x180032ba7  lea     edx, [r14+10h]
0x180032bab  lea     rcx, [rbp+var_50]
0x180032baf  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032bb4  lea     r8, [rbp+DestinationString+4]
0x180032bb8  lea     edx, [r14+20h]
0x180032bbc  lea     rcx, [rbp+var_50]
0x180032bc0  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032bc5  lea     r8, [rbp+var_20+8]
0x180032bc9  mov     edx, 200h
0x180032bce  lea     rcx, [rbp+var_50]
0x180032bd2  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032bd7  lea     r8, [rbp+var_20+0Ch]
0x180032bdb  mov     edx, 400h
0x180032be0  lea     rcx, [rbp+var_50]
0x180032be4  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032be9  lea     r8, [rbp+var_10]
0x180032bed  mov     edx, 800h
0x180032bf2  lea     rcx, [rbp+var_50]
0x180032bf6  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180032bfb  lea     r8, [rbp+Source]
0x180032bff  lea     rdx, aLocaldevicenam; "LocalDeviceName"
0x180032c06  lea     rcx, aBluetooth; "Bluetooth"
0x180032c0d  call    cs:__imp_PolicyManager_GetPolicyString
0x180032c14  nop     dword ptr [rax+rax+00h]
0x180032c19  test    eax, eax
0x180032c1b  js      short loc_180032C86
0x180032c1d  mov     rdi, [rbp+Source]
0x180032c21  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180032c25  mov     rcx, rbx
0x180032c28  inc     rcx
0x180032c2b  cmp     [rdi+rcx*2], r14w
0x180032c30  jnz     short loc_180032C28
0x180032c32  lea     rcx, ds:2[rcx*2]; Size
0x180032c3a  call    _o_malloc_0
0x180032c3f  mov     rsi, rax
0x180032c42  inc     rbx
0x180032c45  cmp     [rdi+rbx*2], r14w
0x180032c4a  jnz     short loc_180032C42
0x180032c4c  lea     rdx, [rbx+1]; SizeInWords
0x180032c50  mov     r8, rdi; Source
0x180032c53  mov     rcx, rsi; Destination
0x180032c56  call    wcscpy_s
0x180032c5b  test    eax, eax
0x180032c5d  jnz     short loc_180032C76
0x180032c5f  mov     rdx, rsi; SourceString
0x180032c62  lea     rcx, [rbp+DestinationString.Buffer]; DestinationString
0x180032c66  call    cs:__imp_RtlInitUnicodeString
0x180032c6d  nop     dword ptr [rax+rax+00h]
0x180032c72  or      dword ptr [rbp+var_10+4], 40h
0x180032c76  mov     rcx, [rbp+Source]
0x180032c7a  call    cs:__imp_PolicyManager_FreeStringValue
0x180032c81  nop     dword ptr [rax+rax+00h]
0x180032c86  lea     r8, [rbp+Source]
0x180032c8a  lea     rdx, aDevicesallowed; "DevicesAllowedList"
0x180032c91  lea     rcx, aBluetooth; "Bluetooth"
0x180032c98  call    cs:__imp_PolicyManager_GetPolicyString
0x180032c9f  nop     dword ptr [rax+rax+00h]
0x180032ca4  test    eax, eax
0x180032ca6  js      short loc_180032CDC
0x180032ca8  mov     rcx, [rbp+Source]; unsigned __int16 *
0x180032cac  lea     r9, [rbp+arg_0]; unsigned int *
0x180032cb0  lea     r8, [rbp+var_28]; unsigned __int64 **
0x180032cb4  mov     [rbp+arg_0], r14d
0x180032cb8  call    ?TokenListToBthAddrArray@@YAJPEAGGPEAPEA_KPEAI@Z; TokenListToBthAddrArray(ushort *,ushort,unsigned __int64 * *,uint *)
0x180032cbd  test    eax, eax
0x180032cbf  js      short loc_180032CCC
0x180032cc1  mov     eax, [rbp+arg_0]
0x180032cc4  bts     dword ptr [rbp+var_10+4], 7
0x180032cc9  mov     dword ptr [rbp+var_10+8], eax
0x180032ccc  mov     rcx, [rbp+Source]
0x180032cd0  call    cs:__imp_PolicyManager_FreeStringValue
0x180032cd7  nop     dword ptr [rax+rax+00h]
0x180032cdc  lea     r8, [rbp+Source]
0x180032ce0  lea     rdx, aServicesallowe; "ServicesAllowedList"
0x180032ce7  lea     rcx, aBluetooth; "Bluetooth"
0x180032cee  call    cs:__imp_PolicyManager_GetPolicyString
0x180032cf5  nop     dword ptr [rax+rax+00h]
0x180032cfa  test    eax, eax
0x180032cfc  js      short loc_180032D32
0x180032cfe  mov     rcx, [rbp+Source]; unsigned __int16 *
0x180032d02  lea     r9, [rbp+arg_0]; unsigned int *
0x180032d06  lea     r8, [rbp+var_20]; struct _GUID **
0x180032d0a  mov     [rbp+arg_0], r14d
0x180032d0e  call    ?TokenListToGuidArray@@YAJPEAGGPEAPEAU_GUID@@PEAI@Z; TokenListToGuidArray(ushort *,ushort,_GUID * *,uint *)
0x180032d13  test    eax, eax
0x180032d15  js      short loc_180032D22
0x180032d17  mov     eax, [rbp+arg_0]
0x180032d1a  bts     dword ptr [rbp+var_10+4], 8
0x180032d1f  mov     dword ptr [rbp+var_10+0Ch], eax
0x180032d22  mov     rcx, [rbp+Source]
0x180032d26  call    cs:__imp_PolicyManager_FreeStringValue
0x180032d2d  nop     dword ptr [rax+rax+00h]
0x180032d32  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180032d39  call    cs:__imp_EnterCriticalSection
0x180032d40  nop     dword ptr [rax+rax+00h]
0x180032d45  mov     rcx, qword ptr cs:ymmword_180046F70+10h; Block
0x180032d4c  test    rcx, rcx
0x180032d4f  jz      short loc_180032D56
0x180032d51  call    free
0x180032d56  mov     rcx, qword ptr cs:ymmword_180046F70+18h; Block
0x180032d5d  test    rcx, rcx
0x180032d60  jz      short loc_180032D67
0x180032d62  call    free
0x180032d67  mov     rcx, qword ptr cs:Src; Block
0x180032d6e  test    rcx, rcx
0x180032d71  jz      short loc_180032D78
0x180032d73  call    free
0x180032d78  movaps  xmm0, [rbp+var_50]
0x180032d7c  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180032d83  movaps  xmm1, xmmword ptr [rbp+DestinationString.Length]
0x180032d87  movaps  cs:?g_Policies@@3UPolicies@@A, xmm0; Policies g_Policies
0x180032d8e  movaps  xmm0, xmmword ptr [rbp-30h]
0x180032d92  movaps  xmmword ptr cs:ymmword_180046F70+10h, xmm0
0x180032d99  movaps  xmm0, [rbp+var_10]
0x180032d9d  movaps  xmmword ptr cs:ymmword_180046F70, xmm1
0x180032da4  movaps  xmm1, xmmword ptr [rbp+var_20]
0x180032da8  movaps  xmmword ptr cs:byte_180046FA0, xmm0
0x180032daf  movaps  cs:Src, xmm1
0x180032db6  call    cs:__imp_LeaveCriticalSection
0x180032dbd  nop     dword ptr [rax+rax+00h]
0x180032dc2  lea     r11, [rsp+70h+var_s0]
0x180032dc7  xor     eax, eax
0x180032dc9  mov     rbx, [r11+30h]
0x180032dcd  mov     rsi, [r11+38h]
0x180032dd1  mov     rsp, r11
0x180032dd4  pop     r14
0x180032dd6  pop     rdi
0x180032dd7  pop     rbp
0x180032dd8  retn
```
