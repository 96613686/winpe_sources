# CImmersiveColorImpl::EnsureInitialized(void)

- ea: `0x14004b1bc`
- end: `0x14004b366`
- name: `?EnsureInitialized@CImmersiveColorImpl@@SAJXZ`
- size: `426`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004a860`
- `0x14004a9d0`
- `0x14004ac04`
- `0x14004b0e0`
- `0x14012dbec`

## callees

- `0x140015710`
- `0x14004a758`
- `0x14004a8d0`
- `0x14004b1bc`
- `0x14004b3c0`
- `0x14004b3e8`
- `0x14004b5b4`
- `0x140087d40`
- `0x14008b2d8`
- `0x14012dae0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b328`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b328`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004b333`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14004b25c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14004b25c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14004b29e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14004b29e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14004b217`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14004b2be`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14004b217`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14004b2be`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004b30f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004b30f`

## pseudocode

```c
__int64 CImmersiveColorImpl::EnsureInitialized(void)
{
  int v0; // ebx
  volatile bool v2; // bl
  char v3; // di
  HANDLE FileMappingW; // rax
  struct IMMERSIVE_COLOR_PREFERENCE *v5; // rcx
  LPWSTR StringSid; // [rsp+40h] [rbp+8h] BYREF
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  if ( !g_fColorDataInitialized )
  {
    v0 = CImmersiveColorImpl::AcquireColorMutex();
    if ( v0 >= 0 )
    {
      if ( g_fColorDataInitialized )
      {
LABEL_8:
        CImmersiveColorImpl::ReleaseColorMutex();
        return (unsigned int)v0;
      }
      v2 = 1;
      v3 = 0;
      FileMappingW = OpenFileMappingW(0xF001Fu, 1, L"Local\\SessionImmersiveColorPreference");
      if ( !FileMappingW )
      {
        FileMappingW = OpenFileMappingW(4u, 1, L"Local\\SessionImmersiveColorPreference");
        v2 = 0;
        if ( !FileMappingW )
        {
          FileMappingW = CreateFileMappingW(
                           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                           0,
                           4u,
                           0,
                           8u,
                           L"Local\\SessionImmersiveColorPreference");
          if ( !FileMappingW )
          {
LABEL_7:
            v0 = -2147467259;
            goto LABEL_8;
          }
          v2 = 1;
          v3 = 1;
        }
      }
      g_hColorPreferenceMapping = FileMappingW;
      g_fColorPreferenceMappingWritable = v2;
      g_pcpColorPreference = (BYTE *)MapViewOfFile(FileMappingW, v2 ? 983071 : 4, 0, 0, 8u);
      if ( g_pcpColorPreference )
      {
        v0 = 0;
        if ( v3 )
        {
          CImmersiveColorImpl::GetColorPreferenceFromRegistry(g_pcpColorPreference);
          if ( !IsCurrentUserLocalSystem() )
          {
            Sid = 0;
            if ( (int)GetCurrentUserSid(&Sid) >= 0 )
            {
              StringSid = 0;
              if ( ConvertSidToStringSidW(Sid, &StringSid) )
              {
                CImmersiveColorImpl::SetACLOnSharedObjectsforUser(StringSid);
                LocalFree(StringSid);
              }
              LocalFree(Sid);
            }
          }
        }
        if ( (unsigned int)IsOS_OS_ANYSERVER() )
          g_cpDefaultColorPreference = g_cpDefaultServerColorPreference;
        CImmersiveColorImpl::GetDefaultColorPreferenceFromRegistry(v5);
        RefreshImmersiveColorPolicyState();
        g_fColorDataInitialized = 1;
        goto LABEL_8;
      }
      goto LABEL_7;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14004b1bc  mov     [rsp+arg_10], rbx
0x14004b1c1  mov     [rsp+arg_18], rbp
0x14004b1c6  push    rdi
0x14004b1c7  sub     rsp, 30h
0x14004b1cb  mov     al, cs:?g_fColorDataInitialized@@3_NC; bool volatile g_fColorDataInitialized
0x14004b1d1  xor     ebx, ebx
0x14004b1d3  test    al, al
0x14004b1d5  jz      short loc_14004B1E9
0x14004b1d7  mov     rbp, [rsp+38h+arg_18]
0x14004b1dc  mov     eax, ebx
0x14004b1de  mov     rbx, [rsp+38h+arg_10]
0x14004b1e3  add     rsp, 30h
0x14004b1e7  pop     rdi
0x14004b1e8  retn
0x14004b1e9  call    ?AcquireColorMutex@CImmersiveColorImpl@@SAJXZ; CImmersiveColorImpl::AcquireColorMutex(void)
0x14004b1ee  mov     ebx, eax
0x14004b1f0  test    eax, eax
0x14004b1f2  js      short loc_14004B1D7
0x14004b1f4  mov     cl, cs:?g_fColorDataInitialized@@3_NC; bool volatile g_fColorDataInitialized
0x14004b1fa  test    cl, cl
0x14004b1fc  jnz     short loc_14004B27A
0x14004b1fe  lea     rbp, aLocalSessionim; "Local\\SessionImmersiveColorPreference"
0x14004b205  mov     edx, 1; bInheritHandle
0x14004b20a  mov     r8, rbp; lpName
0x14004b20d  mov     ecx, 0F001Fh; dwDesiredAccess
0x14004b212  mov     bl, 1
0x14004b214  xor     dil, dil
0x14004b217  call    cs:__imp_OpenFileMappingW
0x14004b21d  test    rax, rax
0x14004b220  jz      loc_14004B2B3
0x14004b226  mov     cs:?g_hColorPreferenceMapping@@3REAXEA, rax; void * g_hColorPreferenceMapping
0x14004b22d  mov     cs:?g_fColorPreferenceMappingWritable@@3_NC, bl; bool volatile g_fColorPreferenceMappingWritable
0x14004b233  mov     al, cs:?g_fColorPreferenceMappingWritable@@3_NC; bool volatile g_fColorPreferenceMappingWritable
0x14004b239  mov     rcx, cs:?g_hColorPreferenceMapping@@3REAXEA; hFileMappingObject
0x14004b240  neg     al
0x14004b242  mov     [rsp+38h+dwNumberOfBytesToMap], 8; dwNumberOfBytesToMap
0x14004b24b  sbb     edx, edx
0x14004b24d  xor     r9d, r9d; dwFileOffsetLow
0x14004b250  and     edx, 0F001Bh
0x14004b256  xor     r8d, r8d; dwFileOffsetHigh
0x14004b259  add     edx, 4; dwDesiredAccess
0x14004b25c  call    cs:__imp_MapViewOfFile
0x14004b262  mov     cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA, rax; IMMERSIVE_COLOR_PREFERENCE * g_pcpColorPreference
0x14004b269  mov     rax, cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA; IMMERSIVE_COLOR_PREFERENCE * g_pcpColorPreference
0x14004b270  test    rax, rax
0x14004b273  jnz     short loc_14004B2D1
0x14004b275  mov     ebx, 80004005h
0x14004b27a  call    ?ReleaseColorMutex@CImmersiveColorImpl@@SAXXZ; CImmersiveColorImpl::ReleaseColorMutex(void)
0x14004b27f  jmp     loc_14004B1D7
0x14004b284  xor     r9d, r9d; dwMaximumSizeHigh
0x14004b287  mov     [rsp+38h+lpName], rbp; lpName
0x14004b28c  xor     edx, edx; lpFileMappingAttributes
0x14004b28e  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], 8; dwMaximumSizeLow
0x14004b296  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14004b29a  lea     r8d, [r9+4]; flProtect
0x14004b29e  call    cs:__imp_CreateFileMappingW
0x14004b2a4  test    rax, rax
0x14004b2a7  jz      short loc_14004B275
0x14004b2a9  mov     bl, 1
0x14004b2ab  mov     dil, bl
0x14004b2ae  jmp     loc_14004B226
0x14004b2b3  mov     edx, 1; bInheritHandle
0x14004b2b8  mov     r8, rbp; lpName
0x14004b2bb  lea     ecx, [rdx+3]; dwDesiredAccess
0x14004b2be  call    cs:__imp_OpenFileMappingW
0x14004b2c4  xor     bl, bl
0x14004b2c6  test    rax, rax
0x14004b2c9  jnz     loc_14004B226
0x14004b2cf  jmp     short loc_14004B284
0x14004b2d1  xor     ebx, ebx
0x14004b2d3  test    dil, dil
0x14004b2d6  jz      short loc_14004B339
0x14004b2d8  mov     rcx, cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA; lpData
0x14004b2df  call    ?GetColorPreferenceFromRegistry@CImmersiveColorImpl@@CAJPEAUIMMERSIVE_COLOR_PREFERENCE@@@Z; CImmersiveColorImpl::GetColorPreferenceFromRegistry(IMMERSIVE_COLOR_PREFERENCE *)
0x14004b2e4  call    ?IsCurrentUserLocalSystem@@YA_NXZ; IsCurrentUserLocalSystem(void)
0x14004b2e9  test    al, al
0x14004b2eb  jnz     short loc_14004B339
0x14004b2ed  lea     rcx, [rsp+38h+Sid]; void **
0x14004b2f2  mov     [rsp+38h+Sid], rbx
0x14004b2f7  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x14004b2fc  test    eax, eax
0x14004b2fe  js      short loc_14004B339
0x14004b300  mov     rcx, [rsp+38h+Sid]; Sid
0x14004b305  lea     rdx, [rsp+38h+StringSid]; StringSid
0x14004b30a  mov     [rsp+38h+StringSid], rbx
0x14004b30f  call    cs:__imp_ConvertSidToStringSidW
0x14004b315  test    eax, eax
0x14004b317  jz      short loc_14004B32E
0x14004b319  mov     rcx, [rsp+38h+StringSid]; unsigned __int16 *
0x14004b31e  call    ?SetACLOnSharedObjectsforUser@CImmersiveColorImpl@@SAJPEBG@Z; CImmersiveColorImpl::SetACLOnSharedObjectsforUser(ushort const *)
0x14004b323  mov     rcx, [rsp+38h+StringSid]; hMem
0x14004b328  call    cs:__imp_LocalFree
0x14004b32e  mov     rcx, [rsp+38h+Sid]; hMem
0x14004b333  call    cs:__imp_LocalFree
0x14004b339  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x14004b33e  test    eax, eax
0x14004b340  jz      short loc_14004B350
0x14004b342  mov     rax, cs:?g_cpDefaultServerColorPreference@@3UIMMERSIVE_COLOR_PREFERENCE@@A; IMMERSIVE_COLOR_PREFERENCE g_cpDefaultServerColorPreference
0x14004b349  mov     cs:?g_cpDefaultColorPreference@@3UIMMERSIVE_COLOR_PREFERENCE@@A, rax; IMMERSIVE_COLOR_PREFERENCE g_cpDefaultColorPreference
0x14004b350  call    ?GetDefaultColorPreferenceFromRegistry@CImmersiveColorImpl@@CAJPEAUIMMERSIVE_COLOR_PREFERENCE@@@Z; CImmersiveColorImpl::GetDefaultColorPreferenceFromRegistry(IMMERSIVE_COLOR_PREFERENCE *)
0x14004b355  call    RefreshImmersiveColorPolicyState
0x14004b35a  mov     cs:?g_fColorDataInitialized@@3_NC, 1; bool volatile g_fColorDataInitialized
0x14004b361  jmp     loc_14004B27A
```
