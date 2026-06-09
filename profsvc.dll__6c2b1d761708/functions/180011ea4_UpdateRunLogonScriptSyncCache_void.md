# UpdateRunLogonScriptSyncCache(void *)

- ea: `0x180011ea4`
- end: `0x180012145`
- name: `?UpdateRunLogonScriptSyncCache@@YAXPEAX@Z`
- size: `673`
- prototype: `void __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c980`

## callees

- `0x180005370`
- `0x18000b060`
- `0x18000d2c0`
- `0x180011c00`
- `0x180011ea4`
- `0x18001214c`
- `0x180012180`
- `0x180037140`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011edb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011f56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011edb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001200e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001200e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ffa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011f77`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011f77`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011f2e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011f2e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011f11`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800120e4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011f11`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800120e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012068`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012068`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011fd2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011fd2`

## pseudocode

```c
void __fastcall UpdateRunLogonScriptSyncCache(HANDLE TokenHandle)
{
  HANDLE ProcessHeap; // rax
  LPWSTR v3; // rdi
  void *v4; // r14
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v7; // rax
  void *v8; // rax
  void *v9; // rsi
  HANDLE v10; // rax
  WCHAR *v11; // rdi
  int v12; // ebx
  HANDLE v13; // rax
  int IsRunLogonScriptSync; // esi
  int ProfileListKeyNameFromSid; // eax
  HKEY v16; // rcx
  unsigned __int16 *v17; // rbx
  int v18; // eax
  BOOL TokenInformation; // eax
  unsigned __int16 *v20; // [rsp+30h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+30h] BYREF

  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v3 = StringSid;
  if ( !StringSid )
  {
    v12 = -2147024882;
    v11 = 0;
LABEL_20:
    if ( v12 >= 0 )
    {
      v20 = 0;
      IsRunLogonScriptSync = _IsRunLogonScriptSync(v11);
      ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(v11, &v20, 0);
      v17 = v20;
      if ( ProfileListKeyNameFromSid >= 0 )
        SHRegSetBOOL(v16, v20, L"RunLogonScriptSync", IsRunLogonScriptSync);
      if ( v17 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v17);
    }
    goto LABEL_25;
  }
  v4 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v18 = ResultFromHeapReAlloc(v3, TokenInformationLength, (void **)&StringSid);
      v3 = StringSid;
      Error = v18;
      if ( v18 < 0 )
        goto LABEL_9;
      TokenInformation = GetTokenInformation(
                           TokenHandle,
                           TokenUser,
                           StringSid,
                           TokenInformationLength,
                           &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v3);
    TokenInformationLength = LengthSid;
    v7 = GetProcessHeap();
    v8 = HeapAlloc(v7, 8u, LengthSid);
    v9 = v8;
    if ( v8 )
    {
      if ( CopySid(TokenInformationLength, v8, *(PSID *)v3) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          ResultFromHeapFree(v9);
          goto LABEL_9;
        }
      }
      v4 = v9;
    }
    else
    {
      Error = -2147024882;
    }
  }
LABEL_9:
  if ( v3 )
  {
    v10 = GetProcessHeap();
    if ( !HeapFree(v10, 0, v3) )
      ResultFromKnownLastError();
  }
  v11 = 0;
  if ( Error >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(v4, &StringSid) )
    {
      v12 = 0;
    }
    else
    {
      v12 = ResultFromKnownLastError();
      if ( v12 < 0 )
      {
LABEL_17:
        if ( v4 )
        {
          v13 = GetProcessHeap();
          if ( !HeapFree(v13, 0, v4) )
            ResultFromKnownLastError();
        }
        goto LABEL_20;
      }
    }
    v11 = StringSid;
    goto LABEL_17;
  }
LABEL_25:
  if ( v11 )
    LocalFree(v11);
}

```

## disassembly

```asm
0x180011ea4  mov     [rsp-18h+arg_0], rbx
0x180011ea9  mov     [rsp-18h+arg_18], rsi
0x180011eae  push    rbp
0x180011eaf  push    rdi
0x180011eb0  push    r14
0x180011eb2  mov     rbp, rsp
0x180011eb5  sub     rsp, 50h
0x180011eb9  mov     ebx, 0C8h
0x180011ebe  mov     rsi, rcx
0x180011ec1  mov     [rbp+TokenInformationLength], ebx
0x180011ec4  call    cs:__imp_GetProcessHeap
0x180011ecb  nop     dword ptr [rax+rax+00h]
0x180011ed0  mov     r8d, ebx; dwBytes
0x180011ed3  mov     edx, 8; dwFlags
0x180011ed8  mov     rcx, rax; hHeap
0x180011edb  call    cs:__imp_HeapAlloc
0x180011ee2  nop     dword ptr [rax+rax+00h]
0x180011ee7  mov     [rbp+StringSid], rax
0x180011eeb  mov     rdi, rax
0x180011eee  test    rax, rax
0x180011ef1  jz      loc_18001208A
0x180011ef7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180011efb  lea     rax, [rbp+TokenInformationLength]
0x180011eff  xor     r14d, r14d
0x180011f02  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180011f07  mov     r8, rdi; TokenInformation
0x180011f0a  mov     rcx, rsi; TokenHandle
0x180011f0d  lea     edx, [r14+1]; TokenInformationClass
0x180011f11  call    cs:__imp_GetTokenInformation
0x180011f18  nop     dword ptr [rax+rax+00h]
0x180011f1d  test    eax, eax
0x180011f1f  jz      loc_18001209D
0x180011f25  xor     ebx, ebx
0x180011f27  test    ebx, ebx
0x180011f29  js      short loc_180011F90
0x180011f2b  mov     rcx, [rdi]; pSid
0x180011f2e  call    cs:__imp_GetLengthSid
0x180011f35  nop     dword ptr [rax+rax+00h]
0x180011f3a  mov     ebx, eax
0x180011f3c  mov     [rbp+TokenInformationLength], ebx
0x180011f3f  call    cs:__imp_GetProcessHeap
0x180011f46  nop     dword ptr [rax+rax+00h]
0x180011f4b  mov     r8d, ebx; dwBytes
0x180011f4e  mov     edx, 8; dwFlags
0x180011f53  mov     rcx, rax; hHeap
0x180011f56  call    cs:__imp_HeapAlloc
0x180011f5d  nop     dword ptr [rax+rax+00h]
0x180011f62  mov     rsi, rax
0x180011f65  test    rax, rax
0x180011f68  jz      loc_180012093
0x180011f6e  mov     r8, [rdi]; pSourceSid
0x180011f71  mov     rdx, rax; pDestinationSid
0x180011f74  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180011f77  call    cs:__imp_CopySid
0x180011f7e  nop     dword ptr [rax+rax+00h]
0x180011f83  test    eax, eax
0x180011f85  jz      loc_1800120FE
0x180011f8b  xor     ebx, ebx
0x180011f8d  mov     r14, rsi
0x180011f90  test    rdi, rdi
0x180011f93  jz      short loc_180011FBD
0x180011f95  call    cs:__imp_GetProcessHeap
0x180011f9c  nop     dword ptr [rax+rax+00h]
0x180011fa1  mov     r8, rdi; lpMem
0x180011fa4  xor     edx, edx; dwFlags
0x180011fa6  mov     rcx, rax; hHeap
0x180011fa9  call    cs:__imp_HeapFree
0x180011fb0  nop     dword ptr [rax+rax+00h]
0x180011fb5  test    eax, eax
0x180011fb7  jz      loc_18001211A
0x180011fbd  xor     edi, edi
0x180011fbf  test    ebx, ebx
0x180011fc1  js      loc_180012060
0x180011fc7  lea     rdx, [rbp+StringSid]; StringSid
0x180011fcb  mov     [rbp+StringSid], rdi
0x180011fcf  mov     rcx, r14; Sid
0x180011fd2  call    cs:__imp_ConvertSidToStringSidW
0x180011fd9  nop     dword ptr [rax+rax+00h]
0x180011fde  test    eax, eax
0x180011fe0  jz      short loc_180011FE6
0x180011fe2  xor     ebx, ebx
0x180011fe4  jmp     short loc_180011FF1
0x180011fe6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011feb  mov     ebx, eax
0x180011fed  test    eax, eax
0x180011fef  js      short loc_180011FF5
0x180011ff1  mov     rdi, [rbp+StringSid]
0x180011ff5  test    r14, r14
0x180011ff8  jz      short loc_180012022
0x180011ffa  call    cs:__imp_GetProcessHeap
0x180012001  nop     dword ptr [rax+rax+00h]
0x180012006  mov     r8, r14; lpMem
0x180012009  xor     edx, edx; dwFlags
0x18001200b  mov     rcx, rax; hHeap
0x18001200e  call    cs:__imp_HeapFree
0x180012015  nop     dword ptr [rax+rax+00h]
0x18001201a  test    eax, eax
0x18001201c  jz      loc_180012124
0x180012022  test    ebx, ebx
0x180012024  js      short loc_180012060
0x180012026  mov     rcx, rdi; lpSubKey
0x180012029  call    ?_IsRunLogonScriptSync@@YAHPEBG@Z; _IsRunLogonScriptSync(ushort const *)
0x18001202e  xor     r8d, r8d; int *
0x180012031  mov     [rbp+var_20], 0
0x180012039  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x18001203d  mov     rcx, rdi; lpString1
0x180012040  mov     esi, eax
0x180012042  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180012047  mov     rbx, [rbp+var_20]
0x18001204b  test    eax, eax
0x18001204d  jns     loc_18001212E
0x180012053  test    rbx, rbx
0x180012056  jz      short loc_180012060
0x180012058  mov     rcx, rbx
0x18001205b  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180012060  test    rdi, rdi
0x180012063  jz      short loc_180012074
0x180012065  mov     rcx, rdi; hMem
0x180012068  call    cs:__imp_LocalFree
0x18001206f  nop     dword ptr [rax+rax+00h]
0x180012074  lea     r11, [rsp+50h+var_s0]
0x180012079  mov     rbx, [r11+20h]
0x18001207d  mov     rsi, [r11+38h]
0x180012081  mov     rsp, r11
0x180012084  pop     r14
0x180012086  pop     rdi
0x180012087  pop     rbp
0x180012088  retn
0x18001208a  mov     ebx, 8007000Eh
0x18001208f  xor     edi, edi
0x180012091  jmp     short loc_180012022
0x180012093  mov     ebx, 8007000Eh
0x180012098  jmp     loc_180011F90
0x18001209d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800120a2  mov     ebx, eax
0x1800120a4  cmp     eax, 8007007Ah
0x1800120a9  jnz     loc_180011F27
0x1800120af  mov     edx, [rbp+TokenInformationLength]; dwBytes
0x1800120b2  lea     r8, [rbp+StringSid]; void **
0x1800120b6  mov     rcx, rdi; lpMem
0x1800120b9  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800120be  mov     rdi, [rbp+StringSid]
0x1800120c2  mov     ebx, eax
0x1800120c4  test    eax, eax
0x1800120c6  js      loc_180011F90
0x1800120cc  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800120d0  lea     rax, [rbp+TokenInformationLength]
0x1800120d4  mov     r8, rdi; TokenInformation
0x1800120d7  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800120dc  mov     edx, 1; TokenInformationClass
0x1800120e1  mov     rcx, rsi; TokenHandle
0x1800120e4  call    cs:__imp_GetTokenInformation
0x1800120eb  nop     dword ptr [rax+rax+00h]
0x1800120f0  mov     ecx, eax; int
0x1800120f2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800120f7  mov     ebx, eax
0x1800120f9  jmp     loc_180011F27
0x1800120fe  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180012103  mov     ebx, eax
0x180012105  test    eax, eax
0x180012107  jns     loc_180011F8D
0x18001210d  mov     rcx, rsi; lpMem
0x180012110  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180012115  jmp     loc_180011F90
0x18001211a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001211f  jmp     loc_180011FBD
0x180012124  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180012129  jmp     loc_180012022
0x18001212e  mov     r9d, esi; int
0x180012131  lea     r8, aRunlogonscript; "RunLogonScriptSync"
0x180012138  mov     rdx, rbx; unsigned __int16 *
0x18001213b  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x180012140  jmp     loc_180012053
```
