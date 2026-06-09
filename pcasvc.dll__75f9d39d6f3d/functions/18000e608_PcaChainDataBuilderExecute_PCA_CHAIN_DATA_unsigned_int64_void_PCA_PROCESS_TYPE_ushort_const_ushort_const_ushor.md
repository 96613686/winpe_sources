# PcaChainDataBuilderExecute(_PCA_CHAIN_DATA *,unsigned __int64,void *,PCA_PROCESS_TYPE,ushort const *,ushort const *,ushort const *,uint)

- ea: `0x18000e608`
- end: `0x18000eb9c`
- name: `?PcaChainDataBuilderExecute@@YAKPEAU_PCA_CHAIN_DATA@@_KPEAXW4PCA_PROCESS_TYPE@@PEBG44I@Z`
- size: `1428`
- prototype: `__int64 __fastcall(_DWORD *, unsigned __int64 *, void *, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001d23c`

## callees

- `0x1800085b8`
- `0x18000a8dc`
- `0x18000dd7c`
- `0x18000deec`
- `0x18000e0b8`
- `0x18000e298`
- `0x18000e4d8`
- `0x18000e608`
- `0x18000eba4`
- `0x18000f234`
- `0x180012920`
- `0x1800280c8`
- `0x18007a9cf`
- `0x18007aa17`
- `0x18008db68`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea71`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e6ea`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000e6ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e6a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e6a2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000e6d3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000e6d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e989`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e989`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e8e6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000e8e6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000e75d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000e75d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000e92e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000e92e`

## string_xrefs

- `0x18000e8b6`: `Failed to open process token [%d]`
- `0x18000ea7d`: `Failed to impersonate user [%d]`
- `0x18000ea4d`: `Failed to read image name [%d]`
- `0x18000ead7`: `Failed to read layers for MSI [%d]`
- `0x18000eae9`: `Failed to create store [%d]`
- `0x18000ea89`: `Failed to retrieve application paths [%d]`
- `0x18000eab3`: `Failed to read layers for CPL [%d]`
- `0x18000eb8a`: `Failed to update cache [%d]`
- `0x18000eb23`: `PcaStoreDeleteValue`
- `0x18000eb12`: `Failed to delete value [%d]`

## pseudocode

```c
__int64 __fastcall PcaChainDataBuilderExecute(
        _DWORD *a1,
        unsigned __int64 *a2,
        void *a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        char a8)
{
  HKEY *v11; // r14
  DWORD ProcessId; // eax
  unsigned int UserData; // ebx
  __int128 v14; // xmm0
  int v15; // eax
  __int128 v16; // xmm1
  const char *v17; // r9
  int v18; // r8d
  DWORD LastError; // eax
  int v20; // r8d
  const char *v21; // r9
  unsigned int CachedData; // eax
  int v24; // [rsp+30h] [rbp-A1h]
  void *TokenHandle; // [rsp+38h] [rbp-99h] BYREF
  int v26; // [rsp+40h] [rbp-91h]
  PVOID P; // [rsp+48h] [rbp-89h] BYREF
  unsigned __int16 *v28; // [rsp+50h] [rbp-81h]
  unsigned __int16 *v29; // [rsp+58h] [rbp-79h]
  __int128 Buf1; // [rsp+60h] [rbp-71h] BYREF
  __int128 v31; // [rsp+70h] [rbp-61h]
  __int64 v32; // [rsp+80h] [rbp-51h]
  unsigned __int16 *v33; // [rsp+88h] [rbp-49h]
  unsigned __int64 *v34; // [rsp+90h] [rbp-41h]
  __int128 Buf2; // [rsp+98h] [rbp-39h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-29h]
  __int64 v37; // [rsp+B8h] [rbp-19h]

  v29 = a5;
  v28 = a6;
  v34 = a2;
  v33 = a7;
  v26 = a4;
  memset_0(a1, 0, 0x14C0u);
  v37 = 0;
  v32 = 0;
  v11 = 0;
  TokenHandle = 0;
  v24 = 0;
  P = 0;
  Buf2 = 0;
  v36 = 0;
  Buf1 = 0;
  v31 = 0;
  if ( !OpenProcessToken(a3, 0xEu, &TokenHandle) )
  {
    LastError = GetLastError();
    v20 = 1055;
    v21 = "Failed to open process token [%d]";
    goto LABEL_25;
  }
  *a1 = a4;
  if ( (a8 & 1) != 0 )
    a1[1324] = 1;
  if ( (a8 & 2) != 0 )
    a1[1184] = 1;
  ProcessId = GetProcessId(a3);
  a1[1] = ProcessId;
  if ( !ProcessId )
  {
    UserData = 87;
    v17 = "Bad process handle [%d]";
    v18 = 1084;
    goto LABEL_22;
  }
  if ( !ProcessIdToSessionId(ProcessId, a1 + 2) )
  {
    LastError = GetLastError();
    v20 = 1095;
    v21 = "Failed to get session id [%d]";
    goto LABEL_25;
  }
  UserData = PcapChainDataBuilderGetUserData((STRSAFE_LPWSTR)a1 + 6, a1 + 134, a1 + 133, TokenHandle);
  if ( UserData )
  {
    v17 = "Failed to retrieve user data [%d]";
    v18 = 1108;
    goto LABEL_22;
  }
  UserData = PcaUtilityGetProcessImageName((unsigned __int16 *)a1 + 1556, a3, v29, v28);
  if ( UserData )
  {
    v17 = "Failed to read image name [%d]";
    v18 = 1121;
    goto LABEL_22;
  }
  UserData = PcapChainDataBuilderGetShimData((struct _PCA_CHAIN_DATA *)a1, a3);
  if ( UserData )
  {
    v17 = "Failed to retrieve attributes [%d]";
    v18 = 1131;
    goto LABEL_22;
  }
  if ( !ImpersonateLoggedOnUser(TokenHandle) )
  {
    LastError = GetLastError();
    v20 = 1145;
    v21 = "Failed to impersonate user [%d]";
LABEL_25:
    UserData = LastError;
    AslLogCallPrintf(1, (unsigned int)"PcaChainDataBuilderExecute", v20, (_DWORD)v21);
    if ( UserData )
      goto LABEL_23;
    goto LABEL_26;
  }
  v24 = 1;
  UserData = PcapChainDataBuilderGetPaths((struct _PCA_CHAIN_DATA *)a1, v29, v28, v33);
  if ( UserData )
  {
    v17 = "Failed to retrieve application paths [%d]";
    v18 = 1160;
    goto LABEL_22;
  }
  if ( a1[135] == 3 )
  {
    *a1 = 2;
    UserData = PcapChainDataBuilderReadPermLayers((struct _PCA_CHAIN_DATA *)a1);
    if ( UserData )
    {
      v17 = "Failed to read layers for CPL [%d]";
      v18 = 1172;
      goto LABEL_22;
    }
  }
  if ( a1[135] == 2 )
  {
    UserData = PcapChainDataBuilderReadPermLayers((struct _PCA_CHAIN_DATA *)a1);
    if ( UserData )
    {
      v17 = "Failed to read layers for MSI [%d]";
      v18 = 1180;
      goto LABEL_22;
    }
  }
  a1[1169] = 1;
  UserData = PcaStoreCreate((unsigned __int64 *)&P, (const unsigned __int16 *)a1 + 6);
  if ( UserData )
  {
    AslLogCallPrintf(1, (unsigned int)"PcaChainDataBuilderExecute", 1193, (unsigned int)"Failed to create store [%d]");
    v11 = (HKEY *)P;
    goto LABEL_23;
  }
  v11 = (HKEY *)P;
  if ( !(unsigned int)PcaStoreGetValue(&Buf2, 40, P, a1 + 1038, 7) )
  {
    if ( a1[135] || *(_QWORD *)(a1 + 1171) == (_QWORD)Buf2 )
    {
      v14 = Buf2;
      v15 = DWORD2(Buf2);
      v16 = v36;
      a1[1169] = 0;
      Buf1 = v14;
      *a1 = v15;
      v32 = v37;
      v31 = v16;
    }
    else
    {
      if ( RegDeleteKeyValueW(*v11, 0, (LPCWSTR)a1 + 2076) )
        AslLogCallPrintf(1, (unsigned int)"PcaStoreDeleteValue", 1144, (unsigned int)"Failed to delete value [%d]");
      Buf2 = 0;
      v37 = 0;
      v36 = 0;
    }
  }
  UserData = PcapChainDataBuilderGetOverrideDbFlags(
               (struct _PCA_CHAIN_DATA *)a1,
               (struct _PCA_CHAIN_DATA_CACHE *)&Buf1,
               *v34,
               (const unsigned __int16 *)a1 + 1556,
               *((_WORD *)a1 + 2340),
               a1[1169]);
  if ( UserData )
  {
    v17 = "Failed to retrieve override flags [%d]";
    v18 = 1240;
LABEL_22:
    AslLogCallPrintf(1, (unsigned int)"PcaChainDataBuilderExecute", v18, (_DWORD)v17);
LABEL_23:
    memset_0(a1, 0, 0x14C0u);
    goto LABEL_26;
  }
  CachedData = PcapChainDataBuilderGetCachedData(
                 (struct _PCA_CHAIN_DATA *)a1,
                 (struct _PCA_CHAIN_DATA_CACHE *)&Buf1,
                 (const unsigned __int16 *)a1 + 1556,
                 a1[1169]);
  UserData = CachedData;
  if ( CachedData )
  {
    if ( CachedData == 8 )
      goto LABEL_23;
    v17 = "Failed to get Genome [%d]";
    v18 = 1254;
    goto LABEL_22;
  }
  if ( a1[135] == 3 )
    a1[1176] = a1[1174] == 167772178 && (*((_QWORD *)a1 + 587) & 0x10000000000LL) != 0;
  if ( a1[1169] || memcmp_0(&Buf1, &Buf2, 0x28u) )
  {
    DWORD2(Buf1) = v26;
    *(_QWORD *)&Buf1 = *(_QWORD *)(a1 + 1171);
    UserData = PcaStoreSetValue(v11, a1 + 1038, 7, &Buf1, 40);
    if ( UserData )
    {
      v17 = "Failed to update cache [%d]";
      v18 = 1290;
      goto LABEL_22;
    }
  }
  UserData = 0;
LABEL_26:
  if ( v11 )
    PcaStoreDelete(v11);
  if ( v24 )
    RevertToSelf();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return UserData;
}

```

## disassembly

```asm
0x18000e608  push    rbp
0x18000e60a  push    rbx
0x18000e60b  push    rsi
0x18000e60c  push    rdi
0x18000e60d  push    r12
0x18000e60f  push    r13
0x18000e611  push    r14
0x18000e613  push    r15
0x18000e615  lea     rbp, [rsp-7]
0x18000e61a  sub     rsp, 0D8h
0x18000e621  mov     rax, cs:__security_cookie
0x18000e628  xor     rax, rsp
0x18000e62b  mov     [rbp+3Fh+var_50], rax
0x18000e62f  mov     rax, [rbp+3Fh+arg_20]
0x18000e633  mov     ebx, r9d
0x18000e636  mov     [rbp+3Fh+var_B8], rax
0x18000e63a  mov     r15, r8
0x18000e63d  mov     rax, [rbp+3Fh+arg_28]
0x18000e641  mov     r8d, 14C0h; Size
0x18000e647  mov     [rsp+110h+var_C0], rax
0x18000e64c  mov     rdi, rcx
0x18000e64f  mov     rax, [rbp+3Fh+arg_30]
0x18000e653  mov     [rbp+3Fh+var_80], rdx
0x18000e657  xor     edx, edx; Val
0x18000e659  mov     [rbp+3Fh+var_88], rax
0x18000e65d  mov     [rsp+110h+var_D0], ebx
0x18000e661  call    memset_0
0x18000e666  xor     eax, eax
0x18000e668  lea     r8, [rsp+110h+TokenHandle]; TokenHandle
0x18000e66d  xorps   xmm0, xmm0
0x18000e670  mov     [rbp+3Fh+var_58], rax
0x18000e674  xorps   xmm1, xmm1
0x18000e677  mov     [rbp+3Fh+var_90], rax
0x18000e67b  xor     r14d, r14d
0x18000e67e  mov     [rsp+110h+TokenHandle], rax
0x18000e683  lea     edx, [rax+0Eh]; DesiredAccess
0x18000e686  mov     [rsp+110h+var_E0], eax
0x18000e68a  mov     rcx, r15; ProcessHandle
0x18000e68d  mov     [rsp+110h+P], r14
0x18000e692  movups  [rbp+3Fh+Buf2], xmm0
0x18000e696  movups  [rbp+3Fh+var_68], xmm0
0x18000e69a  movups  [rbp+3Fh+Buf1], xmm1
0x18000e69e  movups  [rbp+3Fh+var_A0], xmm1
0x18000e6a2  call    cs:__imp_OpenProcessToken
0x18000e6a8  test    eax, eax
0x18000e6aa  jz      loc_18000E8AA
0x18000e6b0  lea     esi, [r14+1]
0x18000e6b4  mov     [rdi], ebx
0x18000e6b6  test    [rbp+3Fh+arg_38], sil
0x18000e6bd  jnz     loc_18000E9F2
0x18000e6c3  test    [rbp+3Fh+arg_38], 2
0x18000e6ca  jnz     loc_18000E9FD
0x18000e6d0  mov     rcx, r15; Process
0x18000e6d3  call    cs:__imp_GetProcessId
0x18000e6d9  mov     [rdi+4], eax
0x18000e6dc  test    eax, eax
0x18000e6de  jz      loc_18000EA08
0x18000e6e4  lea     rdx, [rdi+8]; pSessionId
0x18000e6e8  mov     ecx, eax; dwProcessId
0x18000e6ea  call    cs:__imp_ProcessIdToSessionId
0x18000e6f0  test    eax, eax
0x18000e6f2  jz      loc_18000EA23
0x18000e6f8  mov     r9, [rsp+110h+TokenHandle]; void *
0x18000e6fd  lea     r8, [rdi+214h]; int *
0x18000e704  lea     rdx, [rdi+218h]; int *
0x18000e70b  lea     rcx, [rdi+0Ch]; pszDest
0x18000e70f  call    ?PcapChainDataBuilderGetUserData@@YAKPEAGPEAH1PEAX@Z; PcapChainDataBuilderGetUserData(ushort *,int *,int *,void *)
0x18000e714  mov     ebx, eax
0x18000e716  test    eax, eax
0x18000e718  jnz     loc_18000EA3B
0x18000e71e  mov     r9, [rsp+110h+var_C0]; unsigned __int16 *
0x18000e723  lea     r13, [rdi+0C28h]
0x18000e72a  mov     r8, [rbp+3Fh+var_B8]; unsigned __int16 *
0x18000e72e  mov     rcx, r13; unsigned __int16 *
0x18000e731  mov     rdx, r15; hProcess
0x18000e734  call    ?PcaUtilityGetProcessImageName@@YAKPEAGPEAXPEBG2@Z; PcaUtilityGetProcessImageName(ushort *,void *,ushort const *,ushort const *)
0x18000e739  mov     ebx, eax
0x18000e73b  test    eax, eax
0x18000e73d  jnz     loc_18000EA4D
0x18000e743  mov     rdx, r15; void *
0x18000e746  mov     rcx, rdi; struct _PCA_CHAIN_DATA *
0x18000e749  call    ?PcapChainDataBuilderGetShimData@@YAKPEAU_PCA_CHAIN_DATA@@PEAX@Z; PcapChainDataBuilderGetShimData(_PCA_CHAIN_DATA *,void *)
0x18000e74e  mov     ebx, eax
0x18000e750  test    eax, eax
0x18000e752  jnz     loc_18000EA5F
0x18000e758  mov     rcx, [rsp+110h+TokenHandle]; hToken
0x18000e75d  call    cs:__imp_ImpersonateLoggedOnUser
0x18000e763  test    eax, eax
0x18000e765  jz      loc_18000EA71
0x18000e76b  mov     r9, [rbp+3Fh+var_88]; unsigned __int16 *
0x18000e76f  mov     rcx, rdi; struct _PCA_CHAIN_DATA *
0x18000e772  mov     r8, [rsp+110h+var_C0]; unsigned __int16 *
0x18000e777  mov     rdx, [rbp+3Fh+var_B8]; unsigned __int16 *
0x18000e77b  mov     [rsp+110h+var_E0], esi
0x18000e77f  call    ?PcapChainDataBuilderGetPaths@@YAKPEAU_PCA_CHAIN_DATA@@PEBG11@Z; PcapChainDataBuilderGetPaths(_PCA_CHAIN_DATA *,ushort const *,ushort const *,ushort const *)
0x18000e784  mov     ebx, eax
0x18000e786  test    eax, eax
0x18000e788  jnz     loc_18000EA89
0x18000e78e  cmp     dword ptr [rdi+21Ch], 3
0x18000e795  jz      loc_18000EA9B
0x18000e79b  cmp     dword ptr [rdi+21Ch], 2
0x18000e7a2  jz      loc_18000EAC5
0x18000e7a8  lea     rdx, [rdi+0Ch]; unsigned __int16 *
0x18000e7ac  mov     [rdi+1244h], esi
0x18000e7b2  lea     rcx, [rsp+110h+P]; unsigned __int64 *
0x18000e7b7  call    ?PcaStoreCreate@@YAKPEA_KPEBG@Z; PcaStoreCreate(unsigned __int64 *,ushort const *)
0x18000e7bc  mov     ebx, eax
0x18000e7be  test    eax, eax
0x18000e7c0  jnz     loc_18000EAE9
0x18000e7c6  mov     r14, [rsp+110h+P]
0x18000e7cb  lea     r12d, [rax+28h]
0x18000e7cf  lea     r15, [rdi+1038h]
0x18000e7d6  mov     dword ptr [rsp+110h+var_F0], 7
0x18000e7de  mov     r9, r15
0x18000e7e1  lea     rcx, [rbp+3Fh+Buf2]
0x18000e7e5  mov     r8, r14
0x18000e7e8  mov     edx, r12d
0x18000e7eb  call    ?PcaStoreGetValue@@YAKPEAX_K1PEBGW4_PCA_SLOT_ID@@@Z; PcaStoreGetValue(void *,unsigned __int64,unsigned __int64,ushort const *,_PCA_SLOT_ID)
0x18000e7f0  test    eax, eax
0x18000e7f2  jnz     short loc_18000E843
0x18000e7f4  cmp     [rdi+21Ch], eax
0x18000e7fa  jnz     short loc_18000E81A
0x18000e7fc  mov     eax, dword ptr [rbp+3Fh+Buf2]
0x18000e7ff  cmp     [rdi+124Ch], eax
0x18000e805  jnz     loc_18000E926
0x18000e80b  mov     eax, dword ptr [rbp+3Fh+Buf2+4]
0x18000e80e  cmp     [rdi+1250h], eax
0x18000e814  jnz     loc_18000E926
0x18000e81a  movups  xmm0, [rbp+3Fh+Buf2]
0x18000e81e  mov     eax, dword ptr [rbp+3Fh+Buf2+8]
0x18000e821  movups  xmm1, [rbp+3Fh+var_68]
0x18000e825  mov     dword ptr [rdi+1244h], 0
0x18000e82f  movups  [rbp+3Fh+Buf1], xmm0
0x18000e833  mov     [rdi], eax
0x18000e835  movsd   xmm0, [rbp+3Fh+var_58]
0x18000e83a  movsd   [rbp+3Fh+var_90], xmm0
0x18000e83f  movups  [rbp+3Fh+var_A0], xmm1
0x18000e843  mov     eax, [rdi+1244h]
0x18000e849  lea     rdx, [rbp+3Fh+Buf1]; struct _PCA_CHAIN_DATA_CACHE *
0x18000e84d  mov     r8, [rbp+3Fh+var_80]
0x18000e851  mov     r9, r13; unsigned __int16 *
0x18000e854  mov     [rsp+110h+var_E8], eax; int
0x18000e858  mov     rcx, rdi; struct _PCA_CHAIN_DATA *
0x18000e85b  movzx   eax, word ptr [rdi+1248h]
0x18000e862  mov     [rsp+110h+var_F0], ax; unsigned __int16
0x18000e867  mov     r8, [r8]; unsigned __int64
0x18000e86a  call    ?PcapChainDataBuilderGetOverrideDbFlags@@YAKPEAU_PCA_CHAIN_DATA@@PEAU_PCA_CHAIN_DATA_CACHE@@_KPEBGGH@Z; PcapChainDataBuilderGetOverrideDbFlags(_PCA_CHAIN_DATA *,_PCA_CHAIN_DATA_CACHE *,unsigned __int64,ushort const *,ushort,int)
0x18000e86f  mov     ebx, eax
0x18000e871  test    eax, eax
0x18000e873  jz      loc_18000E952
0x18000e879  lea     r9, aFailedToRetrie_15; "Failed to retrieve override flags [%d]"
0x18000e880  mov     r8d, 4D8h
0x18000e886  mov     dword ptr [rsp+110h+var_F0], eax
0x18000e88a  lea     rdx, aPcachaindatabu; "PcaChainDataBuilderExecute"
0x18000e891  mov     ecx, esi
0x18000e893  call    AslLogCallPrintf
0x18000e898  xor     edx, edx; Val
0x18000e89a  mov     r8d, 14C0h; Size
0x18000e8a0  mov     rcx, rdi; void *
0x18000e8a3  call    memset_0
0x18000e8a8  jmp     short loc_18000E8DA
0x18000e8aa  call    cs:__imp_GetLastError
0x18000e8b0  mov     r8d, 41Fh
0x18000e8b6  lea     r9, aFailedToOpenPr; "Failed to open process token [%d]"
0x18000e8bd  mov     esi, 1
0x18000e8c2  mov     ebx, eax
0x18000e8c4  lea     rdx, aPcachaindatabu; "PcaChainDataBuilderExecute"
0x18000e8cb  mov     ecx, esi
0x18000e8cd  mov     dword ptr [rsp+110h+var_F0], eax
0x18000e8d1  call    AslLogCallPrintf
0x18000e8d6  test    ebx, ebx
0x18000e8d8  jnz     short loc_18000E898
0x18000e8da  test    r14, r14
0x18000e8dd  jnz     short loc_18000E91C
0x18000e8df  cmp     [rsp+110h+var_E0], 0
0x18000e8e4  jz      short loc_18000E8EC
0x18000e8e6  call    cs:__imp_RevertToSelf
0x18000e8ec  mov     rcx, [rsp+110h+TokenHandle]; hObject
0x18000e8f1  test    rcx, rcx
0x18000e8f4  jnz     loc_18000E989
0x18000e8fa  mov     eax, ebx
0x18000e8fc  mov     rcx, [rbp+3Fh+var_50]
0x18000e900  xor     rcx, rsp; StackCookie
0x18000e903  call    __security_check_cookie
0x18000e908  add     rsp, 0D8h
0x18000e90f  pop     r15
0x18000e911  pop     r14
0x18000e913  pop     r13
0x18000e915  pop     r12
0x18000e917  pop     rdi
0x18000e918  pop     rsi
0x18000e919  pop     rbx
0x18000e91a  pop     rbp
0x18000e91b  retn
0x18000e91c  mov     rcx, r14; P
0x18000e91f  call    ?PcaStoreDelete@@YAX_K@Z; PcaStoreDelete(unsigned __int64)
0x18000e924  jmp     short loc_18000E8DF
0x18000e926  mov     rcx, [r14]; hKey
0x18000e929  mov     r8, r15; lpValueName
0x18000e92c  xor     edx, edx; lpSubKey
0x18000e92e  call    cs:__imp_RegDeleteKeyValueW
0x18000e934  test    eax, eax
0x18000e936  jnz     loc_18000EB12
0x18000e93c  xorps   xmm0, xmm0
0x18000e93f  xor     eax, eax
0x18000e941  movups  [rbp+3Fh+Buf2], xmm0
0x18000e945  mov     [rbp+3Fh+var_58], rax
0x18000e949  movups  [rbp+3Fh+var_68], xmm0
0x18000e94d  jmp     loc_18000E843
0x18000e952  mov     r9d, [rdi+1244h]; int
0x18000e959  lea     rdx, [rbp+3Fh+Buf1]; struct _PCA_CHAIN_DATA_CACHE *
0x18000e95d  mov     r8, r13; unsigned __int16 *
0x18000e960  mov     rcx, rdi; struct _PCA_CHAIN_DATA *
0x18000e963  call    ?PcapChainDataBuilderGetCachedData@@YAKPEAU_PCA_CHAIN_DATA@@PEAU_PCA_CHAIN_DATA_CACHE@@PEBGH@Z; PcapChainDataBuilderGetCachedData(_PCA_CHAIN_DATA *,_PCA_CHAIN_DATA_CACHE *,ushort const *,int)
0x18000e968  mov     ebx, eax
0x18000e96a  test    eax, eax
0x18000e96c  jz      short loc_18000E994
0x18000e96e  cmp     eax, 8
0x18000e971  jz      loc_18000E898
0x18000e977  lea     r9, aFailedToGetGen; "Failed to get Genome [%d]"
0x18000e97e  mov     r8d, 4E6h
0x18000e984  jmp     loc_18000E886
0x18000e989  call    cs:__imp_CloseHandle
0x18000e98f  jmp     loc_18000E8FA
0x18000e994  cmp     dword ptr [rdi+21Ch], 3
0x18000e99b  jz      loc_18000EB36
0x18000e9a1  cmp     dword ptr [rdi+1244h], 0
0x18000e9a8  jz      loc_18000EB6D
0x18000e9ae  mov     eax, [rsp+110h+var_D0]
0x18000e9b2  lea     r9, [rbp+3Fh+Buf1]
0x18000e9b6  mov     dword ptr [rbp+3Fh+Buf1+8], eax
0x18000e9b9  mov     r8d, 7
0x18000e9bf  mov     eax, [rdi+124Ch]
0x18000e9c5  mov     rdx, r15
0x18000e9c8  mov     dword ptr [rbp+3Fh+Buf1], eax
0x18000e9cb  mov     rcx, r14
0x18000e9ce  mov     eax, [rdi+1250h]
0x18000e9d4  mov     dword ptr [rbp+3Fh+Buf1+4], eax
0x18000e9d7  mov     qword ptr [rsp+110h+var_F0], r12
0x18000e9dc  call    ?PcaStoreSetValue@@YAK_KPEBGW4_PCA_SLOT_ID@@PEAX0@Z; PcaStoreSetValue(unsigned __int64,ushort const *,_PCA_SLOT_ID,void *,unsigned __int64)
0x18000e9e1  mov     ebx, eax
0x18000e9e3  test    eax, eax
0x18000e9e5  jnz     loc_18000EB8A
0x18000e9eb  xor     ebx, ebx
0x18000e9ed  jmp     loc_18000E8DA
0x18000e9f2  mov     [rdi+14B0h], esi
0x18000e9f8  jmp     loc_18000E6C3
0x18000e9fd  mov     [rdi+1280h], esi
0x18000ea03  jmp     loc_18000E6D0
0x18000ea08  mov     ebx, 57h ; 'W'
0x18000ea0d  lea     r9, aBadProcessHand; "Bad process handle [%d]"
0x18000ea14  mov     dword ptr [rsp+110h+var_F0], ebx
0x18000ea18  mov     r8d, 43Ch
0x18000ea1e  jmp     loc_18000E88A
0x18000ea23  call    cs:__imp_GetLastError
0x18000ea29  mov     r8d, 447h
0x18000ea2f  lea     r9, aFailedToGetSes; "Failed to get session id [%d]"
0x18000ea36  jmp     loc_18000E8C2
0x18000ea3b  lea     r9, aFailedToRetrie_2; "Failed to retrieve user data [%d]"
0x18000ea42  mov     r8d, 454h
0x18000ea48  jmp     loc_18000E886
0x18000ea4d  lea     r9, aFailedToReadIm; "Failed to read image name [%d]"
0x18000ea54  mov     r8d, 461h
0x18000ea5a  jmp     loc_18000E886
0x18000ea5f  lea     r9, aFailedToRetrie_3; "Failed to retrieve attributes [%d]"
0x18000ea66  mov     r8d, 46Bh
0x18000ea6c  jmp     loc_18000E886
0x18000ea71  call    cs:__imp_GetLastError
0x18000ea77  mov     r8d, 479h
0x18000ea7d  lea     r9, aFailedToImpers_0; "Failed to impersonate user [%d]"
0x18000ea84  jmp     loc_18000E8C2
0x18000ea89  lea     r9, aFailedToRetrie_13; "Failed to retrieve application paths [%"...
0x18000ea90  mov     r8d, 488h
0x18000ea96  jmp     loc_18000E886
0x18000ea9b  mov     rcx, rdi; struct _PCA_CHAIN_DATA *
0x18000ea9e  mov     dword ptr [rdi], 2
0x18000eaa4  call    ?PcapChainDataBuilderReadPermLayers@@YAKPEAU_PCA_CHAIN_DATA@@@Z; PcapChainDataBuilderReadPermLayers(_PCA_CHAIN_DATA *)
0x18000eaa9  mov     ebx, eax
0x18000eaab  test    eax, eax
0x18000eaad  jz      loc_18000E79B
0x18000eab3  lea     r9, aFailedToReadLa_1; "Failed to read layers for CPL [%d]"
0x18000eaba  mov     r8d, 494h
0x18000eac0  jmp     loc_18000E886
0x18000eac5  mov     rcx, rdi; struct _PCA_CHAIN_DATA *
0x18000eac8  call    ?PcapChainDataBuilderReadPermLayers@@YAKPEAU_PCA_CHAIN_DATA@@@Z; PcapChainDataBuilderReadPermLayers(_PCA_CHAIN_DATA *)
0x18000eacd  mov     ebx, eax
0x18000eacf  test    eax, eax
0x18000ead1  jz      loc_18000E7A8
0x18000ead7  lea     r9, aFailedToReadLa_0; "Failed to read layers for MSI [%d]"
0x18000eade  mov     r8d, 49Ch
0x18000eae4  jmp     loc_18000E886
0x18000eae9  lea     r9, aFailedToCreate_67; "Failed to create store [%d]"
0x18000eaf0  mov     dword ptr [rsp+110h+var_F0], eax
0x18000eaf4  mov     r8d, 4A9h
0x18000eafa  lea     rdx, aPcachaindatabu; "PcaChainDataBuilderExecute"
0x18000eb01  mov     ecx, esi
0x18000eb03  call    AslLogCallPrintf
0x18000eb08  mov     r14, [rsp+110h+P]
0x18000eb0d  jmp     loc_18000E898
0x18000eb12  lea     r9, aFailedToDelete_12; "Failed to delete value [%d]"
  ... truncated ...
```
