# CClfsAuthContainer::InitializeGlobals(void)

- ea: `0x14003d11c`
- end: `0x14003d26e`
- name: `?InitializeGlobals@CClfsAuthContainer@@SAJXZ`
- size: `338`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14004c5a0`

## callees

- `0x140033e5c`
- `0x14003d11c`
- `0x14004e7c0`
- `0x1400751d0`
- `0x140075300`
- `0x1400753f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14003d1d4`
- `ntoskrnl!ZwClose` at `0x14003d1d4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003d179`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003d179`
- `cng!BCryptHashData` at `0x14003d20c`
- `cng!BCryptHashData` at `0x14003d22f`
- `cng!BCryptHashData` at `0x14003d20c`
- `cng!BCryptHashData` at `0x14003d22f`

## pseudocode

```c
__int64 CClfsAuthContainer::InitializeGlobals(void)
{
  int AuthKeyValue; // ebx
  NTSTATUS v1; // eax
  rsize_t Size; // [rsp+20h] [rbp-48h]
  int v4; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+48h] [rbp-20h]
  int pbInput; // [rsp+80h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+20h] BYREF
  __int64 pbSecret; // [rsp+90h] [rbp+28h] BYREF
  __int64 v9; // [rsp+98h] [rbp+30h] BYREF

  v4 = 0;
  v9 = 0x436C667070666C43LL;
  pbSecret = 0;
  pbInput = -1162803723;
  *(_OWORD *)hHash = 0;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue.32, 0, 0, 0, 0xD0u, 0x41666C43u, 0);
  CClfsAuthContainer::m_fGlobalInitialize = 1;
  Handle = 0;
  AuthKeyValue = CreateAuthRegistryKey(&Handle, 0);
  if ( AuthKeyValue >= 0 )
  {
    LODWORD(Size) = 32;
    AuthKeyValue = QueryAuthKeyValue(Handle, Size);
    ZwClose(Handle);
    if ( AuthKeyValue >= 0 )
    {
      AuthKeyValue = CClfsHashObject::Start((CClfsHashObject *)&v4, (PUCHAR)&pbSecret, 8u);
      if ( AuthKeyValue >= 0 )
      {
        v1 = BCryptHashData(hHash[1], (PUCHAR)&pbInput, 4u, 0);
        if ( v1 < 0
          || (v1 = BCryptHashData(hHash[1], (PUCHAR)&v9, 8u, 0), v1 < 0)
          || (v1 = CClfsHashObject::Finalize((CClfsHashObject *)&v4, &CClfsAuthContainer::m_bPatchFileMagic, 0x20u),
              v1 < 0) )
        {
          AuthKeyValue = v1;
        }
        else
        {
          AuthKeyValue = 0;
        }
      }
    }
  }
  CClfsHashObject::~CClfsHashObject((CClfsHashObject *)&v4);
  return (unsigned int)AuthKeyValue;
}

```

## disassembly

```asm
0x14003d11c  push    rbp
0x14003d11e  push    rbx
0x14003d11f  mov     rbp, rsp
0x14003d122  sub     rsp, 68h
0x14003d126  mov     rax, 436C667070666C43h
0x14003d130  mov     [rbp+var_28], 0
0x14003d137  mov     [rbp+arg_18], rax
0x14003d13b  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h; Lookaside
0x14003d142  xor     eax, eax
0x14003d144  mov     [rbp+pbSecret], 0
0x14003d14c  mov     [rsp+68h+Depth], ax; Depth
0x14003d151  xorps   xmm0, xmm0
0x14003d154  mov     [rsp+68h+Tag], 41666C43h; Tag
0x14003d15c  xor     r9d, r9d; Flags
0x14003d15f  xor     r8d, r8d; Free
0x14003d162  mov     [rsp+68h+Size], 0D0h; Size
0x14003d16b  xor     edx, edx; Allocate
0x14003d16d  mov     [rbp+pbInput], 0BAB105F5h
0x14003d174  movdqu  xmmword ptr [rbp+hHash], xmm0
0x14003d179  call    cs:__imp_ExInitializePagedLookasideList
0x14003d180  nop     dword ptr [rax+rax+00h]
0x14003d185  xor     edx, edx
0x14003d187  mov     cs:?m_fGlobalInitialize@CClfsAuthContainer@@0_NA, 1; bool CClfsAuthContainer::m_fGlobalInitialize
0x14003d18e  lea     rcx, [rbp+Handle]; KeyHandle
0x14003d192  mov     [rbp+Handle], 0
0x14003d19a  call    CreateAuthRegistryKey
0x14003d19f  mov     ebx, eax
0x14003d1a1  test    eax, eax
0x14003d1a3  js      loc_14003D25B
0x14003d1a9  mov     rcx, [rbp+Handle]; KeyHandle
0x14003d1ad  lea     r9, ?m_bContainerAuthSecret@CClfsAuthContainer@@0PAEA; uchar near * CClfsAuthContainer::m_bContainerAuthSecret
0x14003d1b4  mov     r8d, 3
0x14003d1ba  mov     dword ptr [rsp+68h+Size], 20h ; ' '; DstSize
0x14003d1c2  lea     rdx, aKey; "Key"
0x14003d1c9  call    QueryAuthKeyValue
0x14003d1ce  mov     rcx, [rbp+Handle]; Handle
0x14003d1d2  mov     ebx, eax
0x14003d1d4  call    cs:__imp_ZwClose
0x14003d1db  nop     dword ptr [rax+rax+00h]
0x14003d1e0  test    ebx, ebx
0x14003d1e2  js      short loc_14003D25B
0x14003d1e4  mov     r8d, 8; cbSecret
0x14003d1ea  lea     rdx, [rbp+pbSecret]; pbSecret
0x14003d1ee  lea     rcx, [rbp+var_28]; this
0x14003d1f2  call    ?Start@CClfsHashObject@@QEAAJPEAEK@Z; CClfsHashObject::Start(uchar *,ulong)
0x14003d1f7  mov     ebx, eax
0x14003d1f9  test    eax, eax
0x14003d1fb  js      short loc_14003D25B
0x14003d1fd  mov     rcx, [rbp+hHash+8]; hHash
0x14003d201  lea     rdx, [rbp+pbInput]; pbInput
0x14003d205  xor     r9d, r9d; dwFlags
0x14003d208  lea     r8d, [r9+4]; cbInput
0x14003d20c  call    cs:__imp_BCryptHashData
0x14003d213  nop     dword ptr [rax+rax+00h]
0x14003d218  test    eax, eax
0x14003d21a  jns     short loc_14003D220
0x14003d21c  mov     ebx, eax
0x14003d21e  jmp     short loc_14003D25B
0x14003d220  mov     rcx, [rbp+hHash+8]; hHash
0x14003d224  lea     rdx, [rbp+arg_18]; pbInput
0x14003d228  xor     r9d, r9d; dwFlags
0x14003d22b  lea     r8d, [r9+8]; cbInput
0x14003d22f  call    cs:__imp_BCryptHashData
0x14003d236  nop     dword ptr [rax+rax+00h]
0x14003d23b  test    eax, eax
0x14003d23d  js      short loc_14003D21C
0x14003d23f  mov     r8d, 20h ; ' '; unsigned int
0x14003d245  lea     rdx, ?m_bPatchFileMagic@CClfsAuthContainer@@0PAEA; void *
0x14003d24c  lea     rcx, [rbp+var_28]; this
0x14003d250  call    ?Finalize@CClfsHashObject@@QEAAJPEAXK@Z; CClfsHashObject::Finalize(void *,ulong)
0x14003d255  test    eax, eax
0x14003d257  js      short loc_14003D21C
0x14003d259  xor     ebx, ebx
0x14003d25b  lea     rcx, [rbp+var_28]; this
0x14003d25f  call    ??1CClfsHashObject@@QEAA@XZ; CClfsHashObject::~CClfsHashObject(void)
0x14003d264  mov     eax, ebx
0x14003d266  add     rsp, 68h
0x14003d26a  pop     rbx
0x14003d26b  pop     rbp
0x14003d26c  retn
```
