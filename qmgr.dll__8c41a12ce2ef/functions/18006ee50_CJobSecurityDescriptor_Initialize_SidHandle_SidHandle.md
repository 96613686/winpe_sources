# CJobSecurityDescriptor::Initialize(SidHandle,SidHandle)

- ea: `0x18006ee50`
- end: `0x18006f4c7`
- name: `?Initialize@CJobSecurityDescriptor@@AEAAXVSidHandle@@0@Z`
- size: `1655`
- prototype: `void __fastcall(__int64, PSID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006ecfc`

## callees

- `0x180006640`
- `0x18006ee50`
- `0x18006f4d0`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a3de8`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f25c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f25c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f32e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18006f320`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18006f320`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18006f24e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18006f24e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18006eff6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18006eff6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18006ef51`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18006ef51`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006eeb5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006eeb5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006f1ac`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006f1ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CJobSecurityDescriptor::Initialize(__int64 a1, PSID *a2, void **a3)
{
  void *v6; // r15
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  unsigned int v10; // ebx
  signed int v11; // eax
  unsigned int v12; // ebx
  signed int v13; // eax
  unsigned int v14; // esi
  signed int v15; // eax
  unsigned int v16; // ebx
  struct _ACL *v17; // r12
  signed int v18; // eax
  unsigned int v19; // ebx
  volatile signed __int32 *v20; // rax
  volatile signed __int32 *v21; // rax
  LPVOID v22; // rbx
  DWORD v23; // eax
  PACL NewAcl; // [rsp+30h] [rbp-418h] BYREF
  struct _ACL *v25; // [rsp+38h] [rbp-410h]
  LPVOID v26; // [rsp+40h] [rbp-408h]
  PSID v27; // [rsp+48h] [rbp-400h] BYREF
  volatile signed __int32 *v28; // [rsp+50h] [rbp-3F8h]
  PSID *v29; // [rsp+58h] [rbp-3F0h]
  void **v30; // [rsp+60h] [rbp-3E8h]
  void **pExceptionObject; // [rsp+70h] [rbp-3D8h] BYREF
  __int128 v32; // [rsp+78h] [rbp-3D0h]
  unsigned int v33; // [rsp+88h] [rbp-3C0h]
  int v34; // [rsp+8Ch] [rbp-3BCh]
  int v35; // [rsp+90h] [rbp-3B8h]
  void **v36; // [rsp+D0h] [rbp-378h] BYREF
  __int128 v37; // [rsp+D8h] [rbp-370h]
  unsigned int v38; // [rsp+E8h] [rbp-360h]
  int v39; // [rsp+ECh] [rbp-35Ch]
  int v40; // [rsp+F0h] [rbp-358h]
  void **v41; // [rsp+130h] [rbp-318h] BYREF
  __int128 v42; // [rsp+138h] [rbp-310h]
  unsigned int v43; // [rsp+148h] [rbp-300h]
  int v44; // [rsp+14Ch] [rbp-2FCh]
  int v45; // [rsp+150h] [rbp-2F8h]
  void **v46; // [rsp+190h] [rbp-2B8h] BYREF
  __int128 v47; // [rsp+198h] [rbp-2B0h]
  unsigned int v48; // [rsp+1A8h] [rbp-2A0h]
  int v49; // [rsp+1ACh] [rbp-29Ch]
  int v50; // [rsp+1B0h] [rbp-298h]
  void **v51; // [rsp+1F0h] [rbp-258h] BYREF
  __int128 v52; // [rsp+1F8h] [rbp-250h]
  unsigned int v53; // [rsp+208h] [rbp-240h]
  int v54; // [rsp+20Ch] [rbp-23Ch]
  int v55; // [rsp+210h] [rbp-238h]
  void **v56; // [rsp+250h] [rbp-1F8h] BYREF
  __int128 v57; // [rsp+258h] [rbp-1F0h]
  unsigned int v58; // [rsp+268h] [rbp-1E0h]
  int v59; // [rsp+26Ch] [rbp-1DCh]
  int v60; // [rsp+270h] [rbp-1D8h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+2B0h] [rbp-198h] BYREF
  int v62; // [rsp+2E0h] [rbp-168h]
  __int64 v63; // [rsp+2E4h] [rbp-164h]
  int v64; // [rsp+2FCh] [rbp-14Ch]
  int v65; // [rsp+300h] [rbp-148h]
  PSID v66; // [rsp+308h] [rbp-140h]
  int v67; // [rsp+310h] [rbp-138h]
  __int64 v68; // [rsp+314h] [rbp-134h]
  int v69; // [rsp+32Ch] [rbp-11Ch]
  int v70; // [rsp+330h] [rbp-118h]
  __int64 v71; // [rsp+338h] [rbp-110h]
  int v72; // [rsp+340h] [rbp-108h]
  __int64 v73; // [rsp+344h] [rbp-104h]
  int v74; // [rsp+35Ch] [rbp-ECh]
  int v75; // [rsp+360h] [rbp-E8h]
  __int64 v76; // [rsp+368h] [rbp-E0h]
  int v77; // [rsp+370h] [rbp-D8h]
  __int64 v78; // [rsp+374h] [rbp-D4h]
  int v79; // [rsp+38Ch] [rbp-BCh]
  int v80; // [rsp+390h] [rbp-B8h]
  __int64 v81; // [rsp+398h] [rbp-B0h]
  __int64 v82; // [rsp+3A0h] [rbp-A8h] BYREF

  v29 = a2;
  v30 = a3;
  NewAcl = 0;
  v25 = 0;
  v26 = 0;
  try
  {
    v6 = operator new(0x28u);
    v26 = v6;
    if ( !InitializeSecurityDescriptor(v6, 1u) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v8);
      v32 = 0;
      pExceptionObject = &ComError::`vftable';
      v33 = v8;
      v34 = 651;
      v35 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( !SetSecurityDescriptorOwner(v6, *a2, 1) )
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v10);
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v10;
      v39 = 658;
      v40 = 1;
      throw (ComError *)&v36;
    }
    if ( !SetSecurityDescriptorGroup(v6, *a2, 1) )
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v12);
      v42 = 0;
      v41 = &ComError::`vftable';
      v43 = v12;
      v44 = 665;
      v45 = 1;
      throw (ComError *)&v41;
    }
    memset_0(&pListOfExplicitEntries, 0, 0xF0u);
    pListOfExplicitEntries.grfAccessPermissions = 983103;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 3;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)*((_QWORD *)g_GlobalInfo + 15);
    v62 = 983103;
    v63 = 2;
    v64 = 0;
    v65 = 1;
    v66 = *a2;
    v67 = 983103;
    v68 = 2;
    v69 = 0;
    v70 = 2;
    v71 = *((_QWORD *)g_GlobalInfo + 7);
    v72 = 983103;
    v73 = 2;
    v74 = 0;
    v75 = 2;
    v76 = *((_QWORD *)g_GlobalInfo + 9);
    v77 = 983103;
    v78 = 2;
    v79 = 0;
    v80 = 2;
    v81 = *((_QWORD *)g_GlobalInfo + 21);
    v13 = SetEntriesInAclW(5u, &pListOfExplicitEntries, 0, &NewAcl);
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v14);
      v47 = 0;
      v46 = &ComError::`vftable';
      v48 = v14;
      v49 = 724;
      v50 = 1;
      throw (ComError *)&v46;
    }
    if ( !SetSecurityDescriptorDacl(v6, 1, NewAcl, 1) )
    {
      v15 = GetLastError();
      v16 = v15;
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v16);
      v52 = 0;
      v51 = &ComError::`vftable';
      v53 = v16;
      v54 = 736;
      v55 = 1;
      throw (ComError *)&v51;
    }
    v27 = *a3;
    v28 = (volatile signed __int32 *)a3[1];
    _InterlockedAdd(v28, 1u);
    v17 = CreateIntegrityLevelAcl(&v27);
    v25 = v17;
    if ( !SetSecurityDescriptorSacl(v6, 1, v17, 0) )
    {
      v18 = GetLastError();
      v19 = v18;
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v19);
      v57 = 0;
      v56 = &ComError::`vftable';
      v58 = v19;
      v59 = 750;
      v60 = 1;
      throw (ComError *)&v56;
    }
    *(_QWORD *)a1 = v6;
    if ( *(PSID *)(a1 + 8) != *a2 )
    {
      if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(a1 + 16), 0xFFFFFFFF) == 1 )
      {
        operator delete(*(void **)(a1 + 16), 4u);
        operator delete(*(void **)(a1 + 8), 0);
      }
      *(_QWORD *)(a1 + 8) = *a2;
      v20 = (volatile signed __int32 *)a2[1];
      *(_QWORD *)(a1 + 16) = v20;
      _InterlockedIncrement(v20);
    }
    if ( *(PSID *)(a1 + 24) != *a2 )
    {
      if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(a1 + 32), 0xFFFFFFFF) == 1 )
      {
        operator delete(*(void **)(a1 + 32), 4u);
        operator delete(*(void **)(a1 + 24), 0);
      }
      *(_QWORD *)(a1 + 24) = *a2;
      v21 = (volatile signed __int32 *)a2[1];
      *(_QWORD *)(a1 + 32) = v21;
      _InterlockedIncrement(v21);
    }
    *(_QWORD *)(a1 + 40) = NewAcl;
    *(_QWORD *)(a1 + 48) = v17;
  }
  catch ( ComError v82 )
  {
    operator delete(v25, 8u);
    if ( NewAcl )
      LocalFree(NewAcl);
    v22 = v26;
    if ( v26
      && !HeapFree(hBitsHeap, 0, v26)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v23 = GetLastError();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v22, v23);
    }
    throw;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2[1], 0xFFFFFFFF) == 1 )
  {
    operator delete(a2[1], 4u);
    operator delete(*a2, 0);
    a2[1] = 0;
    *a2 = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3[1], 0xFFFFFFFF) == 1 )
  {
    operator delete(a3[1], 4u);
    operator delete(*a3, 0);
    a3[1] = 0;
    *a3 = 0;
  }
}

```

## disassembly

```asm
0x18006ee50  push    rbx
0x18006ee52  push    rsi
0x18006ee53  push    rdi
0x18006ee54  push    r12
0x18006ee56  push    r13
0x18006ee58  push    r14
0x18006ee5a  push    r15
0x18006ee5c  sub     rsp, 410h
0x18006ee63  mov     rax, cs:__security_cookie
0x18006ee6a  xor     rax, rsp
0x18006ee6d  mov     [rsp+448h+var_48], rax
0x18006ee75  mov     r14, r8
0x18006ee78  mov     rbx, rdx
0x18006ee7b  mov     rdi, rcx
0x18006ee7e  mov     [rsp+448h+var_3F0], rdx
0x18006ee83  mov     [rsp+448h+var_3E8], r8
0x18006ee88  xor     r13d, r13d
0x18006ee8b  mov     [rsp+448h+NewAcl], r13
0x18006ee90  mov     [rsp+448h+var_410], r13
0x18006ee95  mov     [rsp+448h+var_408], r13
0x18006ee9a  lea     ecx, [r13+28h]; dwBytes
0x18006ee9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006eea3  mov     r15, rax
0x18006eea6  mov     [rsp+448h+var_408], rax
0x18006eeab  lea     r12d, [r13+1]
0x18006eeaf  mov     edx, r12d; dwRevision
0x18006eeb2  mov     rcx, rax; pSecurityDescriptor
0x18006eeb5  call    cs:__imp_InitializeSecurityDescriptor
0x18006eebb  test    eax, eax
0x18006eebd  jnz     loc_18006EF48
0x18006eec3  call    cs:__imp_GetLastError
0x18006eec9  mov     ebx, eax
0x18006eecb  test    eax, eax
0x18006eecd  jle     short loc_18006EED8
0x18006eecf  movzx   ebx, ax
0x18006eed2  or      ebx, 80070000h
0x18006eed8  lea     rax, WPP_GLOBAL_Control
0x18006eedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eee6  cmp     rcx, rax
0x18006eee9  jz      short loc_18006EF09
0x18006eeeb  test    byte ptr [rcx+1Ch], 4
0x18006eeef  jz      short loc_18006EF09
0x18006eef1  mov     edx, 1Ch
0x18006eef6  mov     r9d, ebx
0x18006eef9  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18006ef00  mov     rcx, [rcx+10h]
0x18006ef04  call    WPP_SF_d
0x18006ef09  xorps   xmm0, xmm0
0x18006ef0c  movups  [rsp+448h+var_3D0], xmm0
0x18006ef11  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006ef18  mov     [rsp+448h+pExceptionObject], rax
0x18006ef1d  mov     [rsp+448h+var_3C0], ebx
0x18006ef24  mov     [rsp+448h+var_3BC], 28Bh
0x18006ef2f  mov     [rsp+448h+var_3B8], r12d
0x18006ef37  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006ef3e  lea     rcx, [rsp+448h+pExceptionObject]; pExceptionObject
0x18006ef43  call    _CxxThrowException_0
0x18006ef48  mov     r8d, r12d; bOwnerDefaulted
0x18006ef4b  mov     rdx, [rbx]; pOwner
0x18006ef4e  mov     rcx, r15; pSecurityDescriptor
0x18006ef51  call    cs:__imp_SetSecurityDescriptorOwner
0x18006ef57  test    eax, eax
0x18006ef59  jnz     loc_18006EFED
0x18006ef5f  call    cs:__imp_GetLastError
0x18006ef65  mov     ebx, eax
0x18006ef67  test    eax, eax
0x18006ef69  jle     short loc_18006EF74
0x18006ef6b  movzx   ebx, ax
0x18006ef6e  or      ebx, 80070000h
0x18006ef74  lea     rax, WPP_GLOBAL_Control
0x18006ef7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ef82  cmp     rcx, rax
0x18006ef85  jz      short loc_18006EFA5
0x18006ef87  test    byte ptr [rcx+1Ch], 4
0x18006ef8b  jz      short loc_18006EFA5
0x18006ef8d  mov     edx, 1Dh
0x18006ef92  mov     r9d, ebx
0x18006ef95  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18006ef9c  mov     rcx, [rcx+10h]
0x18006efa0  call    WPP_SF_d
0x18006efa5  xorps   xmm0, xmm0
0x18006efa8  movups  [rsp+448h+var_370], xmm0
0x18006efb0  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006efb7  mov     [rsp+448h+var_378], rax
0x18006efbf  mov     [rsp+448h+var_360], ebx
0x18006efc6  mov     [rsp+448h+var_35C], 292h
0x18006efd1  mov     [rsp+448h+var_358], r12d
0x18006efd9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006efe0  lea     rcx, [rsp+448h+var_378]; pExceptionObject
0x18006efe8  call    _CxxThrowException_0
0x18006efed  mov     r8d, r12d; bGroupDefaulted
0x18006eff0  mov     rdx, [rbx]; pGroup
0x18006eff3  mov     rcx, r15; pSecurityDescriptor
0x18006eff6  call    cs:__imp_SetSecurityDescriptorGroup
0x18006effc  test    eax, eax
0x18006effe  jnz     loc_18006F092
0x18006f004  call    cs:__imp_GetLastError
0x18006f00a  mov     ebx, eax
0x18006f00c  test    eax, eax
0x18006f00e  jle     short loc_18006F019
0x18006f010  movzx   ebx, ax
0x18006f013  or      ebx, 80070000h
0x18006f019  lea     rax, WPP_GLOBAL_Control
0x18006f020  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f027  cmp     rcx, rax
0x18006f02a  jz      short loc_18006F04A
0x18006f02c  test    byte ptr [rcx+1Ch], 4
0x18006f030  jz      short loc_18006F04A
0x18006f032  mov     edx, 1Eh
0x18006f037  mov     r9d, ebx
0x18006f03a  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18006f041  mov     rcx, [rcx+10h]
0x18006f045  call    WPP_SF_d
0x18006f04a  xorps   xmm0, xmm0
0x18006f04d  movups  [rsp+448h+var_310], xmm0
0x18006f055  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006f05c  mov     [rsp+448h+var_318], rax
0x18006f064  mov     [rsp+448h+var_300], ebx
0x18006f06b  mov     [rsp+448h+var_2FC], 299h
0x18006f076  mov     [rsp+448h+var_2F8], r12d
0x18006f07e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006f085  lea     rcx, [rsp+448h+var_318]; pExceptionObject
0x18006f08d  call    _CxxThrowException_0
0x18006f092  xor     edx, edx; Val
0x18006f094  mov     r8d, 0F0h; Size
0x18006f09a  lea     rcx, [rsp+448h+pListOfExplicitEntries]; void *
0x18006f0a2  call    memset_0
0x18006f0a7  mov     r8d, 0F003Fh
0x18006f0ad  mov     [rsp+448h+pListOfExplicitEntries.grfAccessPermissions], r8d
0x18006f0b5  mov     qword ptr [rsp+448h+pListOfExplicitEntries.grfAccessMode], 3
0x18006f0c1  mov     [rsp+448h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x18006f0c9  mov     [rsp+448h+pListOfExplicitEntries.Trustee.TrusteeType], r12d
0x18006f0d1  mov     rcx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18006f0d8  mov     rax, [rcx+78h]
0x18006f0dc  mov     [rsp+448h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18006f0e4  mov     [rsp+448h+var_168], r8d
0x18006f0ec  mov     edx, 2
0x18006f0f1  mov     [rsp+448h+var_164], rdx
0x18006f0f9  mov     [rsp+448h+var_14C], r13d
0x18006f101  mov     [rsp+448h+var_148], r12d
0x18006f109  mov     rax, [rbx]
0x18006f10c  mov     [rsp+448h+var_140], rax
0x18006f114  mov     [rsp+448h+var_138], r8d
0x18006f11c  mov     [rsp+448h+var_134], rdx
0x18006f124  mov     [rsp+448h+var_11C], r13d
0x18006f12c  mov     [rsp+448h+var_118], edx
0x18006f133  mov     rax, [rcx+38h]
0x18006f137  mov     [rsp+448h+var_110], rax
0x18006f13f  mov     [rsp+448h+var_108], r8d
0x18006f147  mov     [rsp+448h+var_104], rdx
0x18006f14f  mov     [rsp+448h+var_EC], r13d
0x18006f157  mov     [rsp+448h+var_E8], edx
0x18006f15e  mov     rax, [rcx+48h]
0x18006f162  mov     [rsp+448h+var_E0], rax
0x18006f16a  mov     [rsp+448h+var_D8], r8d
0x18006f172  mov     [rsp+448h+var_D4], rdx
0x18006f17a  mov     [rsp+448h+var_BC], r13d
0x18006f182  mov     [rsp+448h+var_B8], edx
0x18006f189  mov     rax, [rcx+0A8h]
0x18006f190  mov     [rsp+448h+var_B0], rax
0x18006f198  lea     r9, [rsp+448h+NewAcl]; NewAcl
0x18006f19d  xor     r8d, r8d; OldAcl
0x18006f1a0  lea     rdx, [rsp+448h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18006f1a8  lea     ecx, [r8+5]; cCountOfExplicitEntries
0x18006f1ac  call    cs:__imp_SetEntriesInAclW
0x18006f1b2  mov     esi, eax
0x18006f1b4  test    eax, eax
0x18006f1b6  jz      loc_18006F240
0x18006f1bc  jle     short loc_18006F1C7
0x18006f1be  movzx   esi, ax
0x18006f1c1  or      esi, 80070000h
0x18006f1c7  lea     rax, WPP_GLOBAL_Control
0x18006f1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f1d5  cmp     rcx, rax
0x18006f1d8  jz      short loc_18006F1F8
0x18006f1da  test    byte ptr [rcx+1Ch], 4
0x18006f1de  jz      short loc_18006F1F8
0x18006f1e0  mov     edx, 1Fh
0x18006f1e5  mov     r9d, esi
0x18006f1e8  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18006f1ef  mov     rcx, [rcx+10h]
0x18006f1f3  call    WPP_SF_d
0x18006f1f8  xorps   xmm0, xmm0
0x18006f1fb  movups  [rsp+448h+var_2B0], xmm0
0x18006f203  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006f20a  mov     [rsp+448h+var_2B8], rax
0x18006f212  mov     [rsp+448h+var_2A0], esi
0x18006f219  mov     [rsp+448h+var_29C], 2D4h
0x18006f224  mov     [rsp+448h+var_298], r12d
0x18006f22c  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006f233  lea     rcx, [rsp+448h+var_2B8]; pExceptionObject
0x18006f23b  call    _CxxThrowException_0
0x18006f240  mov     r9d, r12d; bDaclDefaulted
0x18006f243  mov     r8, [rsp+448h+NewAcl]; pDacl
0x18006f248  mov     edx, r12d; bDaclPresent
0x18006f24b  mov     rcx, r15; pSecurityDescriptor
0x18006f24e  call    cs:__imp_SetSecurityDescriptorDacl
0x18006f254  test    eax, eax
0x18006f256  jnz     loc_18006F2EA
0x18006f25c  call    cs:__imp_GetLastError
0x18006f262  mov     ebx, eax
0x18006f264  test    eax, eax
0x18006f266  jle     short loc_18006F271
0x18006f268  movzx   ebx, ax
0x18006f26b  or      ebx, 80070000h
0x18006f271  lea     rax, WPP_GLOBAL_Control
0x18006f278  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f27f  cmp     rcx, rax
0x18006f282  jz      short loc_18006F2A2
0x18006f284  test    byte ptr [rcx+1Ch], 4
0x18006f288  jz      short loc_18006F2A2
0x18006f28a  mov     edx, 20h ; ' '
0x18006f28f  mov     r9d, ebx
0x18006f292  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18006f299  mov     rcx, [rcx+10h]
0x18006f29d  call    WPP_SF_d
0x18006f2a2  xorps   xmm0, xmm0
0x18006f2a5  movups  [rsp+448h+var_250], xmm0
0x18006f2ad  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006f2b4  mov     [rsp+448h+var_258], rax
0x18006f2bc  mov     [rsp+448h+var_240], ebx
0x18006f2c3  mov     [rsp+448h+var_23C], 2E0h
0x18006f2ce  mov     [rsp+448h+var_238], r12d
0x18006f2d6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006f2dd  lea     rcx, [rsp+448h+var_258]; pExceptionObject
0x18006f2e5  call    _CxxThrowException_0
0x18006f2ea  mov     rax, [r14]
0x18006f2ed  mov     [rsp+448h+var_400], rax
0x18006f2f2  mov     rax, [r14+8]
0x18006f2f6  mov     [rsp+448h+var_3F8], rax
0x18006f2fb  lock add [rax], r12d
0x18006f2ff  lea     rcx, [rsp+448h+var_400]
0x18006f304  call    ?CreateIntegrityLevelAcl@@YAPEAU_ACL@@VSidHandle@@@Z; CreateIntegrityLevelAcl(SidHandle)
0x18006f309  mov     r12, rax
0x18006f30c  mov     [rsp+448h+var_410], rax
0x18006f311  xor     r9d, r9d; bSaclDefaulted
0x18006f314  mov     r8, rax; pSacl
0x18006f317  lea     esi, [r9+1]
0x18006f31b  mov     edx, esi; bSaclPresent
0x18006f31d  mov     rcx, r15; pSecurityDescriptor
0x18006f320  call    cs:__imp_SetSecurityDescriptorSacl
0x18006f326  test    eax, eax
0x18006f328  jnz     loc_18006F3BB
0x18006f32e  call    cs:__imp_GetLastError
0x18006f334  mov     ebx, eax
0x18006f336  test    eax, eax
0x18006f338  jle     short loc_18006F343
0x18006f33a  movzx   ebx, ax
0x18006f33d  or      ebx, 80070000h
0x18006f343  lea     rax, WPP_GLOBAL_Control
0x18006f34a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f351  cmp     rcx, rax
0x18006f354  jz      short loc_18006F374
0x18006f356  test    byte ptr [rcx+1Ch], 4
0x18006f35a  jz      short loc_18006F374
0x18006f35c  mov     edx, 21h ; '!'
0x18006f361  mov     r9d, ebx
0x18006f364  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18006f36b  mov     rcx, [rcx+10h]
0x18006f36f  call    WPP_SF_d
0x18006f374  xorps   xmm0, xmm0
0x18006f377  movups  [rsp+448h+var_1F0], xmm0
0x18006f37f  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006f386  mov     [rsp+448h+var_1F8], rax
0x18006f38e  mov     [rsp+448h+var_1E0], ebx
0x18006f395  mov     [rsp+448h+var_1DC], 2EEh
0x18006f3a0  mov     [rsp+448h+var_1D8], esi
0x18006f3a7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006f3ae  lea     rcx, [rsp+448h+var_1F8]; pExceptionObject
0x18006f3b6  call    _CxxThrowException_0
0x18006f3bb  mov     [rdi], r15
0x18006f3be  mov     rax, [rbx]
0x18006f3c1  or      esi, 0FFFFFFFFh
0x18006f3c4  cmp     [rdi+8], rax
0x18006f3c8  jz      short loc_18006F401
0x18006f3ca  mov     rcx, [rdi+10h]
0x18006f3ce  mov     eax, esi
0x18006f3d0  lock xadd [rcx], eax
0x18006f3d4  add     eax, esi
0x18006f3d6  jnz     short loc_18006F3EF
0x18006f3d8  lea     edx, [rsi+5]; unsigned __int64
0x18006f3db  mov     rcx, [rdi+10h]; void *
0x18006f3df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f3e4  xor     edx, edx; unsigned __int64
0x18006f3e6  mov     rcx, [rdi+8]; void *
0x18006f3ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f3ef  mov     rax, [rbx]
0x18006f3f2  mov     [rdi+8], rax
0x18006f3f6  mov     rax, [rbx+8]
0x18006f3fa  mov     [rdi+10h], rax
0x18006f3fe  lock inc dword ptr [rax]
0x18006f401  mov     rax, [rbx]
0x18006f404  cmp     [rdi+18h], rax
0x18006f408  jz      short loc_18006F441
0x18006f40a  mov     rax, [rdi+20h]
0x18006f40e  mov     ecx, esi
0x18006f410  lock xadd [rax], ecx
0x18006f414  add     ecx, esi
0x18006f416  jnz     short loc_18006F42F
0x18006f418  lea     edx, [rcx+4]; unsigned __int64
  ... truncated ...
```
