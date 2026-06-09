# PdbManager::GenerateNewDBGuid(Guid *)

- ea: `0x140072414`
- end: `0x1400727df`
- name: `?GenerateNewDBGuid@PdbManager@@AEAAPEAVFrsStatus@@PEAVGuid@@@Z`
- size: `971`
- prototype: `struct FrsStatus *__fastcall(PdbManager *__hidden this, struct Guid *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140072eac`

## callees

- `0x1400036a0`
- `0x14000cb00`
- `0x14002a2c4`
- `0x14002ad08`
- `0x140072414`
- `0x1401b9494`
- `0x1401c09d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400725b0`
- `KERNEL32!GetLastError` at `0x140072610`
- `KERNEL32!GetLastError` at `0x14007265f`
- `KERNEL32!GetLastError` at `0x1400726ad`
- `KERNEL32!GetLastError` at `0x140072703`
- `KERNEL32!GetLastError` at `0x1400725b0`
- `KERNEL32!GetLastError` at `0x140072610`
- `KERNEL32!GetLastError` at `0x14007265f`
- `KERNEL32!GetLastError` at `0x1400726ad`
- `KERNEL32!GetLastError` at `0x140072703`
- `KERNEL32!GetCurrentThreadId` at `0x14007247e`
- `KERNEL32!GetCurrentThreadId` at `0x1400725a2`
- `KERNEL32!GetCurrentThreadId` at `0x140072602`
- `KERNEL32!GetCurrentThreadId` at `0x140072651`
- `KERNEL32!GetCurrentThreadId` at `0x14007269f`
- `KERNEL32!GetCurrentThreadId` at `0x1400726f5`
- `KERNEL32!GetCurrentThreadId` at `0x14007247e`
- `KERNEL32!GetCurrentThreadId` at `0x1400725a2`
- `KERNEL32!GetCurrentThreadId` at `0x140072602`
- `KERNEL32!GetCurrentThreadId` at `0x140072651`
- `KERNEL32!GetCurrentThreadId` at `0x14007269f`
- `KERNEL32!GetCurrentThreadId` at `0x1400726f5`
- `ADVAPI32!CryptReleaseContext` at `0x1400727a7`
- `ADVAPI32!CryptReleaseContext` at `0x1400727a7`
- `ADVAPI32!CryptDestroyHash` at `0x140072790`
- `ADVAPI32!CryptDestroyHash` at `0x140072790`
- `ADVAPI32!CryptGetHashParam` at `0x1400726e5`
- `ADVAPI32!CryptGetHashParam` at `0x1400726e5`
- `ADVAPI32!CryptHashData` at `0x140072641`
- `ADVAPI32!CryptHashData` at `0x14007268f`
- `ADVAPI32!CryptHashData` at `0x140072641`
- `ADVAPI32!CryptHashData` at `0x14007268f`
- `ADVAPI32!CryptCreateHash` at `0x1400725f2`
- `ADVAPI32!CryptCreateHash` at `0x1400725f2`
- `ADVAPI32!CryptAcquireContextW` at `0x140072592`
- `ADVAPI32!CryptAcquireContextW` at `0x140072592`
- `ole32!CoCreateGuid` at `0x14007246b`
- `ole32!CoCreateGuid` at `0x14007246b`

## pseudocode

```c
struct FrsStatus *__fastcall PdbManager::GenerateNewDBGuid(PdbManager *this, struct Guid *a2)
{
  __int64 v2; // rsi
  unsigned int v4; // r14d
  DWORD CurrentThreadId; // eax
  __int64 v6; // r9
  __int64 v7; // rdx
  DWORD v8; // ebx
  DWORD LastError; // eax
  DWORD v10; // ebx
  DWORD v11; // ebx
  DWORD v12; // ebx
  DWORD v13; // ebx
  int v15; // [rsp+30h] [rbp-69h]
  DWORD v16; // [rsp+38h] [rbp-61h]
  unsigned int CurrentVMGuid; // [rsp+50h] [rbp-49h] BYREF
  HCRYPTHASH phHash; // [rsp+58h] [rbp-41h] BYREF
  const wchar_t *v19; // [rsp+60h] [rbp-39h] BYREF
  int v20; // [rsp+68h] [rbp-31h]
  int v21; // [rsp+6Ch] [rbp-2Dh]
  const wchar_t *v22; // [rsp+70h] [rbp-29h]
  DWORD pdwDataLen; // [rsp+78h] [rbp-21h] BYREF
  HCRYPTPROV phProv; // [rsp+80h] [rbp-19h] BYREF
  GUID pguid; // [rsp+88h] [rbp-11h] BYREF
  BYTE pbData[16]; // [rsp+98h] [rbp-1h] BYREF
  BYTE v27[32]; // [rsp+A8h] [rbp+Fh] BYREF

  pdwDataLen = 32;
  phProv = 0;
  phHash = 0;
  pguid = 0;
  v2 = 0;
  CurrentVMGuid = 0;
  *(_OWORD *)pbData = 0;
  v4 = CoCreateGuid(&pguid);
  if ( v4 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 4;
    v16 = CurrentThreadId;
    v7 = v4;
    v15 = 5790;
LABEL_3:
    v2 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
           v7,
           0,
           v6,
           "base\\fs\\remotefs\\frs\\src\\db\\pdb.cpp",
           "PdbManager::GenerateNewDBGuid",
           v15,
           v16,
           0);
    goto LABEL_29;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v19 = L"PdbManager::GenerateNewDBGuid";
    v20 = 5794;
    v21 = 4;
    v22 = L"PDBX";
    dbgobj::DbgPrint<unsigned short,Guid>(&v19, L"Initial DB Guid: %?", &pguid);
  }
  *(GUID *)a2 = pguid;
  CurrentVMGuid = System::GetCurrentVMGuid((struct _VM_GENCOUNTER *)pbData);
  if ( CurrentVMGuid )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v19 = L"PdbManager::GenerateNewDBGuid";
      v20 = 5883;
      v21 = 4;
      v22 = L"PDBX";
      dbgobj::DbgPrint<unsigned short,unsigned int>(
        &v19,
        L"VM Generation ID query failed with error %d. This is probably because the system is either not running in a VM, "
         "or is running under a hypervisor version not supporting the VM generation ID query.  Continuing.",
        &CurrentVMGuid);
    }
  }
  else
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v19 = L"PdbManager::GenerateNewDBGuid";
      v20 = 5814;
      v21 = 4;
      v22 = L"PDBX";
      dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned __int64>(
        &v19,
        L"VMGenID: %I64x.%I64x",
        pbData,
        &pbData[8]);
    }
    if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000040) )
    {
      v8 = GetCurrentThreadId();
      LastError = GetLastError();
      v16 = v8;
      v15 = 5822;
LABEL_15:
      v6 = 1;
      v7 = LastError;
      goto LABEL_3;
    }
    if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
    {
      v10 = GetCurrentThreadId();
      LastError = GetLastError();
      v16 = v10;
      v15 = 5832;
      goto LABEL_15;
    }
    if ( !CryptHashData(phHash, (const BYTE *)&pguid, 0x10u, 0) )
    {
      v11 = GetCurrentThreadId();
      LastError = GetLastError();
      v16 = v11;
      v15 = 5840;
      goto LABEL_15;
    }
    if ( !CryptHashData(phHash, pbData, 0x10u, 0) )
    {
      v12 = GetCurrentThreadId();
      LastError = GetLastError();
      v16 = v12;
      v15 = 5848;
      goto LABEL_15;
    }
    if ( !CryptGetHashParam(phHash, 2u, v27, &pdwDataLen, 0) )
    {
      v13 = GetCurrentThreadId();
      LastError = GetLastError();
      v16 = v13;
      v15 = 5857;
      goto LABEL_15;
    }
    *(_OWORD *)a2 = *(_OWORD *)v27;
    *((_WORD *)a2 + 3) = *((_WORD *)a2 + 3) & 0xFFF | 0x4000;
    *((_BYTE *)a2 + 8) = *((_BYTE *)a2 + 8) & 0x3F | 0x80;
  }
LABEL_29:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x140072414  mov     [rsp-8+arg_0], rbx
0x140072419  mov     [rsp-8+arg_10], rsi
0x14007241e  push    rbp
0x14007241f  push    rdi
0x140072420  push    r12
0x140072422  push    r14
0x140072424  push    r15
0x140072426  lea     rbp, [rsp-37h]
0x14007242b  sub     rsp, 0D0h
0x140072432  mov     rax, cs:__security_cookie
0x140072439  xor     rax, rsp
0x14007243c  mov     [rbp+57h+var_28], rax
0x140072440  xor     r15d, r15d
0x140072443  mov     [rbp+57h+pdwDataLen], 20h ; ' '
0x14007244a  xorps   xmm0, xmm0
0x14007244d  mov     [rbp+57h+phProv], r15
0x140072451  lea     rcx, [rbp+57h+pguid]; pguid
0x140072455  mov     [rbp+57h+phHash], r15
0x140072459  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x14007245d  mov     esi, r15d
0x140072460  mov     [rbp+57h+var_A0], r15d
0x140072464  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x140072468  mov     rdi, rdx
0x14007246b  call    cs:__imp_CoCreateGuid
0x140072472  nop     dword ptr [rax+rax+00h]
0x140072477  mov     r14d, eax
0x14007247a  test    eax, eax
0x14007247c  jz      short loc_1400724CA
0x14007247e  call    cs:__imp_GetCurrentThreadId
0x140072485  nop     dword ptr [rax+rax+00h]
0x14007248a  mov     [rsp+0F0h+var_B0], r15
0x14007248f  lea     r9d, [r15+4]
0x140072493  mov     [rsp+0F0h+var_B8], eax
0x140072497  mov     edx, r14d
0x14007249a  mov     [rsp+0F0h+var_C0], 169Eh
0x1400724a2  lea     rcx, aPdbmanagerGene_0; "PdbManager::GenerateNewDBGuid"
0x1400724a9  xor     r8d, r8d
0x1400724ac  mov     [rsp+0F0h+var_C8], rcx
0x1400724b1  lea     rcx, aBaseFsRemotefs_80; "base\\fs\\remotefs\\frs\\src\\db\\pdb.c"...
0x1400724b8  mov     qword ptr [rsp+0F0h+dwFlags], rcx
0x1400724bd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400724c2  mov     rsi, rax
0x1400724c5  jmp     loc_140072787
0x1400724ca  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400724d1  lea     r14, aPdbmanagerGene; "PdbManager::GenerateNewDBGuid"
0x1400724d8  lea     r12, aPdbx; "PDBX"
0x1400724df  mov     ebx, 4
0x1400724e4  test    rax, rax
0x1400724e7  jz      short loc_14007251A
0x1400724e9  cmp     [rax+40h], r15d
0x1400724ed  jz      short loc_14007251A
0x1400724ef  cmp     [rax+38h], ebx
0x1400724f2  jl      short loc_14007251A
0x1400724f4  lea     r8, [rbp+57h+pguid]
0x1400724f8  mov     [rbp+57h+var_90], r14
0x1400724fc  lea     rdx, aInitialDbGuid; "Initial DB Guid: %?"
0x140072503  mov     [rbp+57h+var_88], 16A2h
0x14007250a  lea     rcx, [rbp+57h+var_90]
0x14007250e  mov     [rbp+57h+var_84], ebx
0x140072511  mov     [rbp+57h+var_80], r12
0x140072515  call    ??$DbgPrint@GVGuid@@@dbgobj@@QEAA_KPEBGAEBVGuid@@@Z; dbgobj::DbgPrint<ushort,Guid>(ushort const *,Guid const &)
0x14007251a  movups  xmm0, xmmword ptr [rbp+57h+pguid.Data1]
0x14007251e  lea     rcx, [rbp+57h+pbData]; lpOutBuffer
0x140072522  movdqu  xmmword ptr [rdi], xmm0
0x140072526  call    ?GetCurrentVMGuid@System@@SAKPEAU_VM_GENCOUNTER@@@Z; System::GetCurrentVMGuid(_VM_GENCOUNTER *)
0x14007252b  mov     [rbp+57h+var_A0], eax
0x14007252e  test    eax, eax
0x140072530  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140072537  jnz     loc_140072751
0x14007253d  test    rax, rax
0x140072540  jz      short loc_140072577
0x140072542  cmp     [rax+40h], r15d
0x140072546  jz      short loc_140072577
0x140072548  cmp     [rax+38h], ebx
0x14007254b  jl      short loc_140072577
0x14007254d  lea     r9, [rbp+57h+pbData+8]
0x140072551  mov     [rbp+57h+var_90], r14
0x140072555  lea     r8, [rbp+57h+pbData]
0x140072559  mov     [rbp+57h+var_88], 16B6h
0x140072560  lea     rdx, aVmgenidI64xI64; "VMGenID: %I64x.%I64x"
0x140072567  mov     [rbp+57h+var_84], ebx
0x14007256a  lea     rcx, [rbp+57h+var_90]
0x14007256e  mov     [rbp+57h+var_80], r12
0x140072572  call    ??$DbgPrint@G_K_K@dbgobj@@QEAA_KPEBGAEB_K1@Z; dbgobj::DbgPrint<ushort,unsigned __int64,unsigned __int64>(ushort const *,unsigned __int64 const &,unsigned __int64 const &)
0x140072577  mov     r9d, 18h; dwProvType
0x14007257d  mov     [rsp+0F0h+dwFlags], 0F0000040h; dwFlags
0x140072585  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x14007258c  xor     edx, edx; szContainer
0x14007258e  lea     rcx, [rbp+57h+phProv]; phProv
0x140072592  call    cs:__imp_CryptAcquireContextW
0x140072599  nop     dword ptr [rax+rax+00h]
0x14007259e  test    eax, eax
0x1400725a0  jnz     short loc_1400725DA
0x1400725a2  call    cs:__imp_GetCurrentThreadId
0x1400725a9  nop     dword ptr [rax+rax+00h]
0x1400725ae  mov     ebx, eax
0x1400725b0  call    cs:__imp_GetLastError
0x1400725b7  nop     dword ptr [rax+rax+00h]
0x1400725bc  mov     [rsp+0F0h+var_B0], r15
0x1400725c1  mov     [rsp+0F0h+var_B8], ebx
0x1400725c5  mov     [rsp+0F0h+var_C0], 16BEh
0x1400725cd  mov     r9d, 1
0x1400725d3  mov     edx, eax
0x1400725d5  jmp     loc_1400724A2
0x1400725da  mov     rcx, [rbp+57h+phProv]; hProv
0x1400725de  lea     rax, [rbp+57h+phHash]
0x1400725e2  xor     r9d, r9d; dwFlags
0x1400725e5  mov     qword ptr [rsp+0F0h+dwFlags], rax; phHash
0x1400725ea  xor     r8d, r8d; hKey
0x1400725ed  mov     edx, 800Ch; Algid
0x1400725f2  call    cs:__imp_CryptCreateHash
0x1400725f9  nop     dword ptr [rax+rax+00h]
0x1400725fe  test    eax, eax
0x140072600  jnz     short loc_14007262F
0x140072602  call    cs:__imp_GetCurrentThreadId
0x140072609  nop     dword ptr [rax+rax+00h]
0x14007260e  mov     ebx, eax
0x140072610  call    cs:__imp_GetLastError
0x140072617  nop     dword ptr [rax+rax+00h]
0x14007261c  mov     [rsp+0F0h+var_B0], r15
0x140072621  mov     [rsp+0F0h+var_B8], ebx
0x140072625  mov     [rsp+0F0h+var_C0], 16C8h
0x14007262d  jmp     short loc_1400725CD
0x14007262f  mov     rcx, [rbp+57h+phHash]; hHash
0x140072633  lea     rdx, [rbp+57h+pguid]; pbData
0x140072637  xor     r9d, r9d; dwFlags
0x14007263a  lea     ebx, [r9+10h]
0x14007263e  mov     r8d, ebx; dwDataLen
0x140072641  call    cs:__imp_CryptHashData
0x140072648  nop     dword ptr [rax+rax+00h]
0x14007264d  test    eax, eax
0x14007264f  jnz     short loc_140072681
0x140072651  call    cs:__imp_GetCurrentThreadId
0x140072658  nop     dword ptr [rax+rax+00h]
0x14007265d  mov     ebx, eax
0x14007265f  call    cs:__imp_GetLastError
0x140072666  nop     dword ptr [rax+rax+00h]
0x14007266b  mov     [rsp+0F0h+var_B0], r15
0x140072670  mov     [rsp+0F0h+var_B8], ebx
0x140072674  mov     [rsp+0F0h+var_C0], 16D0h
0x14007267c  jmp     loc_1400725CD
0x140072681  mov     rcx, [rbp+57h+phHash]; hHash
0x140072685  lea     rdx, [rbp+57h+pbData]; pbData
0x140072689  xor     r9d, r9d; dwFlags
0x14007268c  mov     r8d, ebx; dwDataLen
0x14007268f  call    cs:__imp_CryptHashData
0x140072696  nop     dword ptr [rax+rax+00h]
0x14007269b  test    eax, eax
0x14007269d  jnz     short loc_1400726CF
0x14007269f  call    cs:__imp_GetCurrentThreadId
0x1400726a6  nop     dword ptr [rax+rax+00h]
0x1400726ab  mov     ebx, eax
0x1400726ad  call    cs:__imp_GetLastError
0x1400726b4  nop     dword ptr [rax+rax+00h]
0x1400726b9  mov     [rsp+0F0h+var_B0], r15
0x1400726be  mov     [rsp+0F0h+var_B8], ebx
0x1400726c2  mov     [rsp+0F0h+var_C0], 16D8h
0x1400726ca  jmp     loc_1400725CD
0x1400726cf  mov     rcx, [rbp+57h+phHash]; hHash
0x1400726d3  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1400726d7  lea     r8, [rbp+57h+var_48]; pbData
0x1400726db  mov     [rsp+0F0h+dwFlags], r15d; dwFlags
0x1400726e0  mov     edx, 2; dwParam
0x1400726e5  call    cs:__imp_CryptGetHashParam
0x1400726ec  nop     dword ptr [rax+rax+00h]
0x1400726f1  test    eax, eax
0x1400726f3  jnz     short loc_140072725
0x1400726f5  call    cs:__imp_GetCurrentThreadId
0x1400726fc  nop     dword ptr [rax+rax+00h]
0x140072701  mov     ebx, eax
0x140072703  call    cs:__imp_GetLastError
0x14007270a  nop     dword ptr [rax+rax+00h]
0x14007270f  mov     [rsp+0F0h+var_B0], r15
0x140072714  mov     [rsp+0F0h+var_B8], ebx
0x140072718  mov     [rsp+0F0h+var_C0], 16E1h
0x140072720  jmp     loc_1400725CD
0x140072725  movups  xmm0, xmmword ptr [rbp+57h+var_48]
0x140072729  mov     ecx, 0FFFh
0x14007272e  movdqu  xmmword ptr [rdi], xmm0
0x140072732  movzx   eax, word ptr [rdi+6]
0x140072736  and     ax, cx
0x140072739  mov     ecx, 4000h
0x14007273e  or      ax, cx
0x140072741  mov     [rdi+6], ax
0x140072745  mov     al, [rdi+8]
0x140072748  and     al, 3Fh
0x14007274a  or      al, 80h
0x14007274c  mov     [rdi+8], al
0x14007274f  jmp     short loc_140072787
0x140072751  test    rax, rax
0x140072754  jz      short loc_140072787
0x140072756  cmp     [rax+40h], r15d
0x14007275a  jz      short loc_140072787
0x14007275c  cmp     [rax+38h], ebx
0x14007275f  jl      short loc_140072787
0x140072761  lea     r8, [rbp+57h+var_A0]
0x140072765  mov     [rbp+57h+var_90], r14
0x140072769  lea     rdx, aVmGenerationId; "VM Generation ID query failed with erro"...
0x140072770  mov     [rbp+57h+var_88], 16FBh
0x140072777  lea     rcx, [rbp+57h+var_90]
0x14007277b  mov     [rbp+57h+var_84], ebx
0x14007277e  mov     [rbp+57h+var_80], r12
0x140072782  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140072787  mov     rcx, [rbp+57h+phHash]; hHash
0x14007278b  test    rcx, rcx
0x14007278e  jz      short loc_14007279C
0x140072790  call    cs:__imp_CryptDestroyHash
0x140072797  nop     dword ptr [rax+rax+00h]
0x14007279c  mov     rcx, [rbp+57h+phProv]; hProv
0x1400727a0  test    rcx, rcx
0x1400727a3  jz      short loc_1400727B3
0x1400727a5  xor     edx, edx; dwFlags
0x1400727a7  call    cs:__imp_CryptReleaseContext
0x1400727ae  nop     dword ptr [rax+rax+00h]
0x1400727b3  mov     rax, rsi
0x1400727b6  mov     rcx, [rbp+57h+var_28]
0x1400727ba  xor     rcx, rsp; StackCookie
0x1400727bd  call    __security_check_cookie
0x1400727c2  lea     r11, [rsp+0F0h+var_20]
0x1400727ca  mov     rbx, [r11+30h]
0x1400727ce  mov     rsi, [r11+40h]
0x1400727d2  mov     rsp, r11
0x1400727d5  pop     r15
0x1400727d7  pop     r14
0x1400727d9  pop     r12
0x1400727db  pop     rdi
0x1400727dc  pop     rbp
0x1400727dd  retn
```
