# CImmersiveColorImpl::EnsureInitialized(void)

- ea: `0x1400493e8`
- end: `0x1400495c1`
- name: `?EnsureInitialized@CImmersiveColorImpl@@SAJXZ`
- size: `473`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140048a74`
- `0x140048bf0`
- `0x140048e38`
- `0x140049308`
- `0x1401398d4`

## callees

- `0x1400203a4`
- `0x140048960`
- `0x140048ae4`
- `0x1400493e8`
- `0x140049624`
- `0x140049654`
- `0x140049844`
- `0x14008d8f8`
- `0x140090930`
- `0x1401397b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140049577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140049588`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140049577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140049588`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140049448`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140049501`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140049448`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140049501`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400494db`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400494db`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140049493`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140049493`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140049558`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140049558`

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
0x1400493e8  mov     [rsp+arg_10], rbx
0x1400493ed  mov     [rsp+arg_18], rbp
0x1400493f2  push    rdi
0x1400493f3  sub     rsp, 30h
0x1400493f7  mov     al, cs:?g_fColorDataInitialized@@3_NC; bool volatile g_fColorDataInitialized
0x1400493fd  xor     ebx, ebx
0x1400493ff  test    al, al
0x140049401  jz      short loc_140049416
0x140049403  mov     rbp, [rsp+38h+arg_18]
0x140049408  mov     eax, ebx
0x14004940a  mov     rbx, [rsp+38h+arg_10]
0x14004940f  add     rsp, 30h
0x140049413  pop     rdi
0x140049414  retn
0x140049416  call    ?AcquireColorMutex@CImmersiveColorImpl@@SAJXZ; CImmersiveColorImpl::AcquireColorMutex(void)
0x14004941b  mov     ebx, eax
0x14004941d  test    eax, eax
0x14004941f  js      short loc_140049403
0x140049421  mov     cl, cs:?g_fColorDataInitialized@@3_NC; bool volatile g_fColorDataInitialized
0x140049427  test    cl, cl
0x140049429  jnz     loc_1400494B7
0x14004942f  lea     rbp, aLocalSessionim; "Local\\SessionImmersiveColorPreference"
0x140049436  mov     edx, 1; bInheritHandle
0x14004943b  mov     r8, rbp; lpName
0x14004943e  mov     ecx, 0F001Fh; dwDesiredAccess
0x140049443  mov     bl, 1
0x140049445  xor     dil, dil
0x140049448  call    cs:__imp_OpenFileMappingW
0x14004944f  nop     dword ptr [rax+rax+00h]
0x140049454  test    rax, rax
0x140049457  jz      loc_1400494F6
0x14004945d  mov     cs:?g_hColorPreferenceMapping@@3REAXEA, rax; void * g_hColorPreferenceMapping
0x140049464  mov     cs:?g_fColorPreferenceMappingWritable@@3_NC, bl; bool volatile g_fColorPreferenceMappingWritable
0x14004946a  mov     al, cs:?g_fColorPreferenceMappingWritable@@3_NC; bool volatile g_fColorPreferenceMappingWritable
0x140049470  mov     rcx, cs:?g_hColorPreferenceMapping@@3REAXEA; hFileMappingObject
0x140049477  neg     al
0x140049479  mov     [rsp+38h+dwNumberOfBytesToMap], 8; dwNumberOfBytesToMap
0x140049482  sbb     edx, edx
0x140049484  xor     r9d, r9d; dwFileOffsetLow
0x140049487  and     edx, 0F001Bh
0x14004948d  xor     r8d, r8d; dwFileOffsetHigh
0x140049490  add     edx, 4; dwDesiredAccess
0x140049493  call    cs:__imp_MapViewOfFile
0x14004949a  nop     dword ptr [rax+rax+00h]
0x14004949f  mov     cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA, rax; IMMERSIVE_COLOR_PREFERENCE * g_pcpColorPreference
0x1400494a6  mov     rax, cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA; IMMERSIVE_COLOR_PREFERENCE * g_pcpColorPreference
0x1400494ad  test    rax, rax
0x1400494b0  jnz     short loc_14004951A
0x1400494b2  mov     ebx, 80004005h
0x1400494b7  call    ?ReleaseColorMutex@CImmersiveColorImpl@@SAXXZ; CImmersiveColorImpl::ReleaseColorMutex(void)
0x1400494bc  jmp     loc_140049403
0x1400494c1  xor     r9d, r9d; dwMaximumSizeHigh
0x1400494c4  mov     [rsp+38h+lpName], rbp; lpName
0x1400494c9  xor     edx, edx; lpFileMappingAttributes
0x1400494cb  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], 8; dwMaximumSizeLow
0x1400494d3  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1400494d7  lea     r8d, [r9+4]; flProtect
0x1400494db  call    cs:__imp_CreateFileMappingW
0x1400494e2  nop     dword ptr [rax+rax+00h]
0x1400494e7  test    rax, rax
0x1400494ea  jz      short loc_1400494B2
0x1400494ec  mov     bl, 1
0x1400494ee  mov     dil, bl
0x1400494f1  jmp     loc_14004945D
0x1400494f6  mov     edx, 1; bInheritHandle
0x1400494fb  mov     r8, rbp; lpName
0x1400494fe  lea     ecx, [rdx+3]; dwDesiredAccess
0x140049501  call    cs:__imp_OpenFileMappingW
0x140049508  nop     dword ptr [rax+rax+00h]
0x14004950d  xor     bl, bl
0x14004950f  test    rax, rax
0x140049512  jnz     loc_14004945D
0x140049518  jmp     short loc_1400494C1
0x14004951a  xor     ebx, ebx
0x14004951c  test    dil, dil
0x14004951f  jz      short loc_140049594
0x140049521  mov     rcx, cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA; lpData
0x140049528  call    ?GetColorPreferenceFromRegistry@CImmersiveColorImpl@@CAJPEAUIMMERSIVE_COLOR_PREFERENCE@@@Z; CImmersiveColorImpl::GetColorPreferenceFromRegistry(IMMERSIVE_COLOR_PREFERENCE *)
0x14004952d  call    ?IsCurrentUserLocalSystem@@YA_NXZ; IsCurrentUserLocalSystem(void)
0x140049532  test    al, al
0x140049534  jnz     short loc_140049594
0x140049536  lea     rcx, [rsp+38h+Sid]; void **
0x14004953b  mov     [rsp+38h+Sid], rbx
0x140049540  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x140049545  test    eax, eax
0x140049547  js      short loc_140049594
0x140049549  mov     rcx, [rsp+38h+Sid]; Sid
0x14004954e  lea     rdx, [rsp+38h+StringSid]; StringSid
0x140049553  mov     [rsp+38h+StringSid], rbx
0x140049558  call    cs:__imp_ConvertSidToStringSidW
0x14004955f  nop     dword ptr [rax+rax+00h]
0x140049564  test    eax, eax
0x140049566  jz      short loc_140049583
0x140049568  mov     rcx, [rsp+38h+StringSid]; unsigned __int16 *
0x14004956d  call    ?SetACLOnSharedObjectsforUser@CImmersiveColorImpl@@SAJPEBG@Z; CImmersiveColorImpl::SetACLOnSharedObjectsforUser(ushort const *)
0x140049572  mov     rcx, [rsp+38h+StringSid]; hMem
0x140049577  call    cs:__imp_LocalFree
0x14004957e  nop     dword ptr [rax+rax+00h]
0x140049583  mov     rcx, [rsp+38h+Sid]; hMem
0x140049588  call    cs:__imp_LocalFree
0x14004958f  nop     dword ptr [rax+rax+00h]
0x140049594  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x140049599  test    eax, eax
0x14004959b  jz      short loc_1400495AB
0x14004959d  mov     rax, cs:?g_cpDefaultServerColorPreference@@3UIMMERSIVE_COLOR_PREFERENCE@@A; IMMERSIVE_COLOR_PREFERENCE g_cpDefaultServerColorPreference
0x1400495a4  mov     cs:?g_cpDefaultColorPreference@@3UIMMERSIVE_COLOR_PREFERENCE@@A, rax; IMMERSIVE_COLOR_PREFERENCE g_cpDefaultColorPreference
0x1400495ab  call    ?GetDefaultColorPreferenceFromRegistry@CImmersiveColorImpl@@CAJPEAUIMMERSIVE_COLOR_PREFERENCE@@@Z; CImmersiveColorImpl::GetDefaultColorPreferenceFromRegistry(IMMERSIVE_COLOR_PREFERENCE *)
0x1400495b0  call    RefreshImmersiveColorPolicyState
0x1400495b5  mov     cs:?g_fColorDataInitialized@@3_NC, 1; bool volatile g_fColorDataInitialized
0x1400495bc  jmp     loc_1400494B7
```
