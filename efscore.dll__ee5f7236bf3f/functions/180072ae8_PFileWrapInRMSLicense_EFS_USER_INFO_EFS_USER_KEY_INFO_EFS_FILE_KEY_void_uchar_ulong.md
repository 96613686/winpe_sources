# PFileWrapInRMSLicense(_EFS_USER_INFO *,_EFS_USER_KEY_INFO *,_EFS_FILE_KEY *,void *,uchar * *,ulong *)

- ea: `0x180072ae8`
- end: `0x180073035`
- name: `?PFileWrapInRMSLicense@@YAKPEAU_EFS_USER_INFO@@PEAU_EFS_USER_KEY_INFO@@PEAU_EFS_FILE_KEY@@PEAXPEAPEAEPEAK@Z`
- size: `1357`
- prototype: `unsigned int __fastcall(struct _EFS_USER_INFO *, struct _EFS_USER_KEY_INFO *, struct _EFS_FILE_KEY *, void *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180072238`

## callees

- `0x180004f86`
- `0x180035040`
- `0x180035db8`
- `0x18004a89c`
- `0x1800615d0`
- `0x180062044`
- `0x180063698`
- `0x180066d30`
- `0x180066fd0`
- `0x180069810`
- `0x180069c6c`
- `0x18006a8a8`
- `0x18006cc84`
- `0x180071a70`
- `0x180072ae8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180072e9a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180072e9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072bd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072bd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072c52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072c52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072e6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072e6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072e5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072fe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073002`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072e5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072fe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180073002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072fa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072fa7`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x180072cf7`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x180072cf7`
- `ncrypt!NCryptProtectSecret` at `0x180072d48`
- `ncrypt!NCryptProtectSecret` at `0x180072d48`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180072fc4`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x180072fc4`
- `winmsipc!__imp_IpcCloseHandle` at `0x180072fd6`
- `winmsipc!__imp_IpcCloseHandle` at `0x180072fd6`

## pseudocode

```c
__int64 __fastcall PFileWrapInRMSLicense(
        struct _EFS_USER_INFO *a1,
        struct _EFS_USER_KEY_INFO *a2,
        struct _EFS_FILE_KEY *a3,
        unsigned __int8 *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  __int64 v6; // r8
  __int64 v7; // rcx
  unsigned __int16 *v8; // rsi
  void *v10; // r12
  void *v11; // r15
  unsigned int DescriptorEntryFromCache; // eax
  unsigned int v13; // edi
  __int64 v14; // rbx
  void *v15; // r14
  int v16; // eax
  int v17; // r14d
  __int64 v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // ecx
  unsigned int v21; // r14d
  unsigned __int8 *v22; // rbx
  void *v23; // rbx
  HANDLE ProcessHeap; // rax
  char *v25; // rax
  char *v26; // rdi
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned __int8 *v29; // rax
  HANDLE v30; // rax
  HANDLE v31; // rax
  char v33; // [rsp+28h] [rbp-69h]
  char v34; // [rsp+28h] [rbp-69h]
  size_t Size; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int8 *v36; // [rsp+50h] [rbp-41h] BYREF
  void *Src; // [rsp+58h] [rbp-39h] BYREF
  unsigned int v38; // [rsp+60h] [rbp-31h] BYREF
  void *v39; // [rsp+68h] [rbp-29h] BYREF
  __int64 v40; // [rsp+70h] [rbp-21h] BYREF
  __int64 v41; // [rsp+78h] [rbp-19h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-9h] BYREF
  _QWORD v44[9]; // [rsp+90h] [rbp-1h] BYREF
  void *v46; // [rsp+F0h] [rbp+5Fh] BYREF
  struct _EFS_FILE_KEY *v47; // [rsp+F8h] [rbp+67h]
  unsigned __int8 *v48; // [rsp+100h] [rbp+6Fh]

  v48 = a4;
  v47 = a3;
  v6 = *((_QWORD *)a2 + 7);
  v7 = *((_QWORD *)a1 + 6);
  v8 = 0;
  v40 = 0;
  v10 = 0;
  v44[0] = 0;
  hMem = 0;
  v11 = 0;
  LODWORD(Size) = 0;
  v36 = 0;
  v38 = 0;
  Src = 0;
  LOBYTE(v46) = 0;
  v41 = 0;
  v39 = 0;
  lpMem = 0;
  DescriptorEntryFromCache = EfsGetDescriptorEntryFromCache(v7, 1, v6, &v41);
  v13 = DescriptorEntryFromCache;
  if ( DescriptorEntryFromCache == 1168 )
  {
    v14 = 0;
    v15 = 0;
  }
  else
  {
    if ( DescriptorEntryFromCache )
    {
      v33 = -87;
      goto LABEL_53;
    }
    v14 = *(_QWORD *)(v41 + 8);
    if ( *(_DWORD *)(v14 + 4) != 1 || *(_DWORD *)v14 < 0x40u )
    {
      v13 = 13;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 13, 31, 164);
      goto LABEL_54;
    }
    v15 = *(void **)(v14 + 16);
  }
  DescriptorEntryFromCache = CEfsTokenManager::ModifyCallerContext((CEfsTokenManager *)&v40, 3);
  v13 = DescriptorEntryFromCache;
  if ( DescriptorEntryFromCache )
  {
    v33 = -84;
LABEL_53:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, DescriptorEntryFromCache, 31, v33);
    goto LABEL_54;
  }
  if ( v14 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 24));
  v16 = EfsParseRmsProtectorDescriptor(*((const unsigned __int16 **)a2 + 7), 0, (unsigned __int16 **)&lpMem);
  if ( v16 >= 0 )
  {
    v13 = 0;
    goto LABEL_15;
  }
  if ( (v16 & 0x1FFF0000) != 0x70000 )
  {
    v13 = 1359;
    goto LABEL_50;
  }
  v13 = (unsigned __int16)v16;
  if ( (_WORD)v16 )
  {
LABEL_50:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v13, 31, 188);
    v10 = lpMem;
    goto LABEL_54;
  }
LABEL_15:
  v10 = lpMem;
  if ( g_RmsIntBreakpointEnabled )
    __int2c();
  v17 = CRmsInterface::CreateAndSerializeLicense(
          (CRmsInterface *)(unsigned int)v16,
          v15,
          (const unsigned __int16 *)lpMem,
          *((struct _EFS_KEY **)v47 + 1),
          &v36,
          &v38,
          &v39);
  if ( v14 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 24));
  CEfsTokenManager::RevertToOriginalToken((CEfsTokenManager *)&v40);
  if ( v17 >= 0 )
  {
    if ( !v41 )
    {
      v23 = v39;
      if ( v39 )
      {
        ProcessHeap = GetProcessHeap();
        v25 = (char *)HeapAlloc(ProcessHeap, 8u, 0x40u);
        v26 = v25;
        if ( v25 )
        {
          *(_DWORD *)v25 = 64;
          *((_DWORD *)v25 + 1) = 1;
          *((_QWORD *)v25 + 1) = FreeRmsCacheEntry;
          *((_QWORD *)v25 + 2) = v23;
          InitializeCriticalSection((LPCRITICAL_SECTION)(v25 + 24));
          v27 = *((_QWORD *)a2 + 7);
          v46 = v26;
          v28 = EfsTryAddDescriptorInfoToCache(a1, v27, &v46);
          v13 = v28;
          if ( v28 )
          {
            fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v28, 31, 248);
            v13 = 0;
          }
          v11 = v46;
        }
        else
        {
          v13 = 14;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 14, 31, 0);
        }
        v39 = 0;
      }
    }
    *a6 = v38;
    v29 = v36;
    v36 = 0;
    *a5 = v29;
    goto LABEL_47;
  }
  EfsGet_TEST_BooleanOverrideInternal(L"AllowDpapiOnRmsFailure", v18, &v46);
  if ( !(_BYTE)v46 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v17, 31, 216);
    v13 = 6023;
    goto LABEL_54;
  }
  v19 = EfsxDatumDpapiNgProtectorInfoCreate(
          v48,
          *((const unsigned __int16 **)a2 + 4),
          *((const unsigned __int16 **)a2 + 7),
          (struct _EFSX_DATUM_PROTECTOR_INFO **)&Src);
  v13 = v19;
  if ( v19 )
  {
    v34 = 21;
LABEL_23:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v19, 31, v34);
LABEL_24:
    v8 = (unsigned __int16 *)Src;
    goto LABEL_47;
  }
  v19 = CEfsTokenManager::ModifyCallerContext((CEfsTokenManager *)&v40, 1);
  v13 = v19;
  if ( v19 )
  {
    v34 = 23;
    goto LABEL_23;
  }
  if ( (int)NCryptCreateProtectionDescriptor(L"LOCAL=User", 0, v44) < 0 )
  {
    v13 = 87;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 87, 31, 30);
    goto LABEL_24;
  }
  if ( (int)NCryptProtectSecret(
              v44[0],
              64,
              *((_QWORD *)v47 + 1),
              (unsigned int)(**((_DWORD **)v47 + 1) + 56),
              0,
              0,
              &hMem,
              &Size) < 0 )
  {
    v13 = 87;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 87, 31, 43);
    goto LABEL_24;
  }
  CEfsTokenManager::RevertToOriginalToken((CEfsTokenManager *)&v40);
  v8 = (unsigned __int16 *)Src;
  v20 = *(unsigned __int16 *)Src;
  v21 = v20 + Size;
  if ( v20 + (unsigned int)Size >= v20 )
  {
    v13 = EfsxLibAllocZero(v21, (void **)&v36);
    if ( v13 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, v21, 31, 55);
    }
    else
    {
      v22 = v36;
      memcpy_0(v36, v8, *v8);
      memcpy_0(&v22[*v8], hMem, (unsigned int)Size);
      v36 = 0;
      *a6 = v21;
      *a5 = v22;
    }
  }
  else
  {
    v13 = 13;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 13, 31, 52);
  }
LABEL_47:
  if ( v8 )
    EfsxDatumFree((struct _EFSX_DATUM *)v8);
LABEL_54:
  if ( hMem )
    LocalFree(hMem);
  if ( v36 )
    EdppAuditSiteFree(v36);
  if ( v44[0] )
    NCryptCloseProtectionDescriptor();
  if ( v39 )
    IpcCloseHandle(v39);
  if ( v11 )
  {
    FreeRmsCacheEntry(v11);
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v11);
  }
  if ( v10 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v10);
  }
  CEfsTokenManager::RevertToOriginalToken((CEfsTokenManager *)&v40);
  return v13;
}

```

## disassembly

```asm
0x180072ae8  mov     rax, rsp
0x180072aeb  mov     [rax+20h], r9
0x180072aef  mov     [rax+18h], r8
0x180072af3  mov     [rax+8], rcx
0x180072af7  push    rbp
0x180072af8  push    rbx
0x180072af9  push    rsi
0x180072afa  push    rdi
0x180072afb  push    r12
0x180072afd  push    r13
0x180072aff  push    r14
0x180072b01  push    r15
0x180072b03  lea     rbp, [rax-4Fh]
0x180072b07  sub     rsp, 98h
0x180072b0e  mov     r8, [rdx+38h]
0x180072b12  lea     r9, [rbp+47h+var_60]
0x180072b16  mov     rcx, [rcx+30h]
0x180072b1a  xor     esi, esi
0x180072b1c  mov     r13, rdx
0x180072b1f  mov     [rbp+47h+var_68], 0
0x180072b27  xor     r12d, r12d
0x180072b2a  mov     [rbp+47h+var_48], 0
0x180072b32  mov     [rbp+47h+hMem], 0
0x180072b3a  xor     r15d, r15d
0x180072b3d  lea     edx, [rsi+1]
0x180072b40  mov     dword ptr [rbp+47h+Size], 0
0x180072b47  mov     [rbp+47h+var_88], 0
0x180072b4f  mov     [rbp+47h+var_78], 0
0x180072b56  mov     [rbp+47h+Src], rsi
0x180072b5a  mov     byte ptr [rbp+47h+arg_8], sil
0x180072b5e  mov     [rbp+47h+var_60], rsi
0x180072b62  mov     [rbp+47h+var_70], rsi
0x180072b66  mov     [rbp+47h+lpMem], r12
0x180072b6a  call    EfsGetDescriptorEntryFromCache
0x180072b6f  mov     edi, eax
0x180072b71  cmp     eax, 490h
0x180072b76  jnz     short loc_180072B7F
0x180072b78  xor     ebx, ebx
0x180072b7a  xor     r14d, r14d
0x180072b7d  jmp     short loc_180072BA6
0x180072b7f  test    eax, eax
0x180072b81  jnz     loc_180072F7A
0x180072b87  mov     rbx, [rbp+47h+var_60]
0x180072b8b  mov     rbx, [rbx+8]
0x180072b8f  cmp     dword ptr [rbx+4], 1
0x180072b93  jnz     loc_180072F68
0x180072b99  cmp     dword ptr [rbx], 40h ; '@'
0x180072b9c  jb      loc_180072F68
0x180072ba2  mov     r14, [rbx+10h]
0x180072ba6  mov     edx, 3; unsigned int
0x180072bab  lea     rcx, [rbp+47h+var_68]; this
0x180072baf  call    ?ModifyCallerContext@CEfsTokenManager@@QEAAKK@Z; CEfsTokenManager::ModifyCallerContext(ulong)
0x180072bb4  mov     edi, eax
0x180072bb6  test    eax, eax
0x180072bb8  jz      short loc_180072BC7
0x180072bba  mov     dword ptr [rsp+0D0h+var_B0], 1ACh
0x180072bc2  jmp     loc_180072F82
0x180072bc7  test    rbx, rbx
0x180072bca  jz      short loc_180072BD6
0x180072bcc  lea     rcx, [rbx+18h]; lpCriticalSection
0x180072bd0  call    cs:__imp_EnterCriticalSection
0x180072bd6  mov     rcx, [r13+38h]; unsigned __int16 *
0x180072bda  lea     r8, [rbp+47h+lpMem]; unsigned __int16 **
0x180072bde  xor     edx, edx; unsigned __int16 **
0x180072be0  call    ?EfsParseRmsProtectorDescriptor@@YAJPEBGPEAPEAG1@Z; EfsParseRmsProtectorDescriptor(ushort const *,ushort * *,ushort * *)
0x180072be5  mov     ecx, eax; this
0x180072be7  test    eax, eax
0x180072be9  js      short loc_180072BEF
0x180072beb  xor     edi, edi
0x180072bed  jmp     short loc_180072C0A
0x180072bef  and     eax, 1FFF0000h
0x180072bf4  cmp     eax, 70000h
0x180072bf9  jnz     loc_180072F39
0x180072bff  movzx   edi, cx
0x180072c02  test    edi, edi
0x180072c04  jnz     loc_180072F3E
0x180072c0a  cmp     cs:?g_RmsIntBreakpointEnabled@@3HA, esi; int g_RmsIntBreakpointEnabled
0x180072c10  mov     r12, [rbp+47h+lpMem]
0x180072c14  jz      short loc_180072C18
0x180072c16  int     2Ch; Windows NT - assertion failure
0x180072c18  mov     r9, [rbp+47h+arg_10]
0x180072c1c  lea     rax, [rbp+47h+var_70]
0x180072c20  mov     [rsp+0D0h+var_A0], rax; void **
0x180072c25  mov     r8, r12; unsigned __int16 *
0x180072c28  lea     rax, [rbp+47h+var_78]
0x180072c2c  mov     rdx, r14; void *
0x180072c2f  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x180072c34  lea     rax, [rbp+47h+var_88]
0x180072c38  mov     r9, [r9+8]; struct _EFS_KEY *
0x180072c3c  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 **
0x180072c41  call    ?CreateAndSerializeLicense@CRmsInterface@@QEAAJPEAXPEBGPEAU_EFS_KEY@@PEAPEAEPEAKPEAPEAX@Z; CRmsInterface::CreateAndSerializeLicense(void *,ushort const *,_EFS_KEY *,uchar * *,ulong *,void * *)
0x180072c46  mov     r14d, eax
0x180072c49  test    rbx, rbx
0x180072c4c  jz      short loc_180072C58
0x180072c4e  lea     rcx, [rbx+18h]; lpCriticalSection
0x180072c52  call    cs:__imp_LeaveCriticalSection
0x180072c58  lea     rcx, [rbp+47h+var_68]; this
0x180072c5c  call    ?RevertToOriginalToken@CEfsTokenManager@@QEAAXXZ; CEfsTokenManager::RevertToOriginalToken(void)
0x180072c61  test    r14d, r14d
0x180072c64  jns     loc_180072E43
0x180072c6a  lea     r8, [rbp+47h+arg_8]
0x180072c6e  lea     rcx, aAllowdpapionrm; "AllowDpapiOnRmsFailure"
0x180072c75  call    EfsGet_TEST_BooleanOverrideInternal
0x180072c7a  cmp     byte ptr [rbp+47h+arg_8], sil
0x180072c7e  jz      loc_180072E15
0x180072c84  mov     r8, [r13+38h]; unsigned __int16 *
0x180072c88  lea     r9, [rbp+47h+Src]; struct _EFSX_DATUM_PROTECTOR_INFO **
0x180072c8c  mov     rdx, [r13+20h]; unsigned __int16 *
0x180072c90  mov     rcx, [rbp+47h+arg_18]; unsigned __int8 *
0x180072c94  call    ?EfsxDatumDpapiNgProtectorInfoCreate@@YAKPEAXPEBG1PEAPEAU_EFSX_DATUM_PROTECTOR_INFO@@@Z; EfsxDatumDpapiNgProtectorInfoCreate(void *,ushort const *,ushort const *,_EFSX_DATUM_PROTECTOR_INFO * *)
0x180072c99  mov     edi, eax
0x180072c9b  test    eax, eax
0x180072c9d  jz      short loc_180072CCC
0x180072c9f  mov     dword ptr [rsp+0D0h+var_B0], 215h
0x180072ca7  mov     r8d, eax
0x180072caa  mov     rcx, cs:g_hPublisher
0x180072cb1  lea     rdx, EFS_API_ERROR
0x180072cb8  mov     r9d, 1Fh
0x180072cbe  call    fnEfsLogTrace1
0x180072cc3  mov     rsi, [rbp+47h+Src]
0x180072cc7  jmp     loc_180072F2A
0x180072ccc  mov     edx, 1; unsigned int
0x180072cd1  lea     rcx, [rbp+47h+var_68]; this
0x180072cd5  call    ?ModifyCallerContext@CEfsTokenManager@@QEAAKK@Z; CEfsTokenManager::ModifyCallerContext(ulong)
0x180072cda  mov     edi, eax
0x180072cdc  test    eax, eax
0x180072cde  jz      short loc_180072CEA
0x180072ce0  mov     dword ptr [rsp+0D0h+var_B0], 217h
0x180072ce8  jmp     short loc_180072CA7
0x180072cea  lea     r8, [rbp+47h+var_48]
0x180072cee  xor     edx, edx
0x180072cf0  lea     rcx, aLocalUser_0; "LOCAL=User"
0x180072cf7  call    cs:__imp_NCryptCreateProtectionDescriptor
0x180072cfd  test    eax, eax
0x180072cff  jns     short loc_180072D14
0x180072d01  mov     r8d, 57h ; 'W'
0x180072d07  mov     dword ptr [rsp+0D0h+var_B0], 21Eh
0x180072d0f  mov     edi, r8d
0x180072d12  jmp     short loc_180072CAA
0x180072d14  mov     rax, [rbp+47h+arg_10]
0x180072d18  mov     edx, 40h ; '@'
0x180072d1d  mov     rcx, [rbp+47h+var_48]
0x180072d21  mov     r8, [rax+8]
0x180072d25  lea     rax, [rbp+47h+Size]
0x180072d29  mov     [rsp+38h], rax
0x180072d2e  lea     rax, [rbp+47h+hMem]
0x180072d32  mov     [rsp+0D0h+var_A0], rax
0x180072d37  mov     [rsp+0D0h+var_A8], rsi
0x180072d3c  mov     r9d, [r8]
0x180072d3f  add     r9d, 38h ; '8'
0x180072d43  mov     [rsp+0D0h+var_B0], rsi
0x180072d48  call    cs:__imp_NCryptProtectSecret
0x180072d4e  test    eax, eax
0x180072d50  jns     short loc_180072D68
0x180072d52  mov     r8d, 57h ; 'W'
0x180072d58  mov     dword ptr [rsp+0D0h+var_B0], 22Bh
0x180072d60  mov     edi, r8d
0x180072d63  jmp     loc_180072CAA
0x180072d68  lea     rcx, [rbp+47h+var_68]; this
0x180072d6c  call    ?RevertToOriginalToken@CEfsTokenManager@@QEAAXXZ; CEfsTokenManager::RevertToOriginalToken(void)
0x180072d71  mov     rsi, [rbp+47h+Src]
0x180072d75  mov     r14d, dword ptr [rbp+47h+Size]
0x180072d79  movzx   ecx, word ptr [rsi]
0x180072d7c  add     r14d, ecx
0x180072d7f  cmp     r14d, ecx
0x180072d82  jnb     short loc_180072DB2
0x180072d84  mov     edi, 0Dh
0x180072d89  mov     dword ptr [rsp+0D0h+var_B0], 234h
0x180072d91  mov     r8d, edi
0x180072d94  lea     rdx, EFS_API_ERROR
0x180072d9b  mov     rcx, cs:g_hPublisher
0x180072da2  mov     r9d, 1Fh
0x180072da8  call    fnEfsLogTrace1
0x180072dad  jmp     loc_180072F2A
0x180072db2  mov     ecx, r14d; unsigned __int64
0x180072db5  lea     rdx, [rbp+47h+var_88]; void **
0x180072db9  call    ?EfsxLibAllocZero@@YAK_KPEAPEAX@Z; EfsxLibAllocZero(unsigned __int64,void * *)
0x180072dbe  mov     edi, eax
0x180072dc0  test    eax, eax
0x180072dc2  jz      short loc_180072DD8
0x180072dc4  mov     dword ptr [rsp+0D0h+var_B0], 237h
0x180072dcc  lea     rdx, EFS_ERROR_MEMORY
0x180072dd3  mov     r8d, r14d
0x180072dd6  jmp     short loc_180072D9B
0x180072dd8  mov     rbx, [rbp+47h+var_88]
0x180072ddc  mov     rdx, rsi; Src
0x180072ddf  movzx   r8d, word ptr [rsi]; Size
0x180072de3  mov     rcx, rbx; void *
0x180072de6  call    memcpy_0
0x180072deb  movzx   ecx, word ptr [rsi]
0x180072dee  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x180072df2  add     rcx, rbx; void *
0x180072df5  mov     rdx, [rbp+47h+hMem]; Src
0x180072df9  call    memcpy_0
0x180072dfe  mov     rax, [rbp+47h+arg_28]
0x180072e02  mov     [rbp+47h+var_88], r15
0x180072e06  mov     [rax], r14d
0x180072e09  mov     rax, [rbp+47h+arg_20]
0x180072e0d  mov     [rax], rbx
0x180072e10  jmp     loc_180072F2A
0x180072e15  mov     rcx, cs:g_hPublisher
0x180072e1c  lea     rdx, EFS_API_ERROR
0x180072e23  mov     r9d, 1Fh
0x180072e29  mov     dword ptr [rsp+0D0h+var_B0], 1D8h
0x180072e31  mov     r8d, r14d
0x180072e34  call    fnEfsLogTrace1
0x180072e39  mov     edi, 1787h
0x180072e3e  jmp     loc_180072F9E
0x180072e43  cmp     [rbp+47h+var_60], rsi
0x180072e47  jnz     loc_180072F12
0x180072e4d  mov     rbx, [rbp+47h+var_70]
0x180072e51  test    rbx, rbx
0x180072e54  jz      loc_180072F12
0x180072e5a  call    cs:__imp_GetProcessHeap
0x180072e60  mov     edx, 8; dwFlags
0x180072e65  mov     rcx, rax; hHeap
0x180072e68  lea     r8d, [rdx+38h]; dwBytes
0x180072e6c  call    cs:__imp_HeapAlloc
0x180072e72  mov     rdi, rax
0x180072e75  test    rax, rax
0x180072e78  jz      short loc_180072EE7
0x180072e7a  mov     dword ptr [rax], 40h ; '@'
0x180072e80  lea     rcx, [rdi+18h]; lpCriticalSection
0x180072e84  mov     dword ptr [rax+4], 1
0x180072e8b  lea     rax, ?FreeRmsCacheEntry@@YAHPEAX@Z; FreeRmsCacheEntry(void *)
0x180072e92  mov     [rdi+8], rax
0x180072e96  mov     [rdi+10h], rbx
0x180072e9a  call    cs:__imp_InitializeCriticalSection
0x180072ea0  mov     rdx, [r13+38h]
0x180072ea4  lea     r8, [rbp+47h+arg_8]
0x180072ea8  mov     rcx, [rbp+47h+arg_0]
0x180072eac  mov     [rbp+47h+arg_8], rdi
0x180072eb0  call    EfsTryAddDescriptorInfoToCache
0x180072eb5  mov     edi, eax
0x180072eb7  test    eax, eax
0x180072eb9  jz      short loc_180072EE1
0x180072ebb  mov     rcx, cs:g_hPublisher
0x180072ec2  lea     rdx, EFS_API_ERROR
0x180072ec9  mov     r9d, 1Fh
0x180072ecf  mov     dword ptr [rsp+0D0h+var_B0], 1F8h
0x180072ed7  mov     r8d, eax
0x180072eda  call    fnEfsLogTrace1
0x180072edf  xor     edi, edi
0x180072ee1  mov     r15, [rbp+47h+arg_8]
0x180072ee5  jmp     short loc_180072F0E
0x180072ee7  mov     rcx, cs:g_hPublisher
0x180072eee  lea     rdx, EFS_API_ERROR
0x180072ef5  mov     edi, 0Eh
0x180072efa  mov     dword ptr [rsp+0D0h+var_B0], 200h
0x180072f02  mov     r8d, edi
0x180072f05  lea     r9d, [rdi+11h]
0x180072f09  call    fnEfsLogTrace1
0x180072f0e  mov     [rbp+47h+var_70], rsi
0x180072f12  mov     rdx, [rbp+47h+arg_28]
0x180072f16  mov     eax, [rbp+47h+var_78]
0x180072f19  mov     [rdx], eax
0x180072f1b  mov     rax, [rbp+47h+var_88]
0x180072f1f  mov     rdx, [rbp+47h+arg_20]
0x180072f23  mov     [rbp+47h+var_88], rsi
0x180072f27  mov     [rdx], rax
0x180072f2a  test    rsi, rsi
0x180072f2d  jz      short loc_180072F9E
0x180072f2f  mov     rcx, rsi; struct _EFSX_DATUM *
0x180072f32  call    ?EfsxDatumFree@@YAKPEAU_EFSX_DATUM@@@Z; EfsxDatumFree(_EFSX_DATUM *)
0x180072f37  jmp     short loc_180072F9E
0x180072f39  mov     edi, 54Fh
0x180072f3e  mov     rcx, cs:g_hPublisher
0x180072f45  lea     rdx, EFS_API_ERROR
0x180072f4c  mov     r9d, 1Fh
0x180072f52  mov     dword ptr [rsp+0D0h+var_B0], 1BCh
0x180072f5a  mov     r8d, edi
0x180072f5d  call    fnEfsLogTrace1
0x180072f62  mov     r12, [rbp+47h+lpMem]
0x180072f66  jmp     short loc_180072F9E
0x180072f68  mov     edi, 0Dh
0x180072f6d  mov     dword ptr [rsp+0D0h+var_B0], 1A4h
0x180072f75  mov     r8d, edi
0x180072f78  jmp     short loc_180072F85
0x180072f7a  mov     dword ptr [rsp+0D0h+var_B0], 1A9h
0x180072f82  mov     r8d, eax
0x180072f85  mov     rcx, cs:g_hPublisher
0x180072f8c  lea     rdx, EFS_API_ERROR
0x180072f93  mov     r9d, 1Fh
0x180072f99  call    fnEfsLogTrace1
0x180072f9e  mov     rcx, [rbp+47h+hMem]; hMem
0x180072fa2  test    rcx, rcx
0x180072fa5  jz      short loc_180072FAD
0x180072fa7  call    cs:__imp_LocalFree
0x180072fad  mov     rcx, [rbp+47h+var_88]; void *
0x180072fb1  test    rcx, rcx
0x180072fb4  jz      short loc_180072FBB
0x180072fb6  call    ?EdppAuditSiteFree@@YAXPEAX@Z; EdppAuditSiteFree(void *)
0x180072fbb  mov     rcx, [rbp+47h+var_48]
0x180072fbf  test    rcx, rcx
0x180072fc2  jz      short loc_180072FCA
0x180072fc4  call    cs:__imp_NCryptCloseProtectionDescriptor
0x180072fca  mov     rbx, [rbp+47h+var_70]
0x180072fce  test    rbx, rbx
0x180072fd1  jz      short loc_180072FDC
0x180072fd3  mov     rcx, rbx
  ... truncated ...
```
