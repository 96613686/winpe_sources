# DfsADBlobStore::RemoveDomainRootTarget(DfsRootFolder *,ushort const *,ushort const *,ushort const *,ushort const *,uchar,uchar)

- ea: `0x14000dd80`
- end: `0x14000e21f`
- name: `?RemoveDomainRootTarget@DfsADBlobStore@@UEAAKPEAVDfsRootFolder@@PEBG111EE@Z`
- size: `1183`
- prototype: `unsigned int(DfsADBlobStore *__hidden this, struct DfsRootFolder *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, unsigned __int8)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x140005b28`
- `0x140005c10`
- `0x140005f20`
- `0x14000a354`
- `0x14000c214`
- `0x14000dd80`
- `0x14000e228`
- `0x14000e278`
- `0x14002e1b8`
- `0x14003ea74`
- `0x140056dd8`
- `0x140057cdc`
- `0x140057f64`
- `0x1400586a8`
- `0x140059044`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000deca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000deca`

## pseudocode

```c
__int64 __fastcall DfsADBlobStore::RemoveDomainRootTarget(
        DfsADBlobStore *this,
        RTL_SRWLOCK *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *SourceString,
        unsigned __int8 a7,
        unsigned __int8 a8)
{
  unsigned __int16 *v8; // r15
  unsigned int inited; // ebx
  __int64 v13; // rdx
  unsigned int v14; // r14d
  bool v15; // zf
  unsigned __int8 v16; // r8
  DfsStore *v17; // r13
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  unsigned __int8 v22; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+31h] [rbp-3Fh]
  unsigned __int8 v24[6]; // [rsp+32h] [rbp-3Eh] BYREF
  void *Block; // [rsp+38h] [rbp-38h] BYREF
  HKEY v26; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-28h]
  struct _UNICODE_STRING v28; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING v29; // [rsp+60h] [rbp-10h] BYREF

  v22 = 0;
  v29 = 0;
  v23 = 0;
  v8 = 0;
  v28 = 0;
  Block = 0;
  v24[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x40) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_SS(
      *((_QWORD *)pWppControl + 2),
      22,
      (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
      (_DWORD)a5,
      (__int64)SourceString);
  }
  inited = DfsRtlInitUnicodeStringEx(&v29, a3);
  if ( !inited )
  {
    inited = DfsRtlInitUnicodeStringEx(&v26, SourceString);
    if ( !inited )
    {
      inited = DfsRtlInitUnicodeStringEx(&v28, a5);
      if ( !inited )
      {
        LOBYTE(v13) = 1;
        inited = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD, const unsigned __int16 *))a2->Ptr + 15))(
                   a2,
                   v13,
                   0,
                   a4);
        if ( !inited )
        {
          v23 = 1;
          inited = DfsADBlobStore::CheckDeleteAccess(this, (struct DfsRootFolder *)a2, a4, &v29, &v28);
          if ( !inited )
          {
            inited = DfsRootFolder::AcquireRootLock((DfsRootFolder *)a2, 1u);
            if ( !inited )
            {
              LODWORD(a2[34].Ptr) |= 0x4000u;
              ++LODWORD(a2[15].Ptr);
              ReleaseSRWLockExclusive(a2 + 14);
              if ( a8 )
                goto LABEL_19;
              inited = DfsGetNamespaceRegistrySubkeyName(a3, SourceString, a7, (const unsigned __int16 **)&Block);
              if ( !inited )
              {
                v26 = 0;
                v27 = 0;
                if ( (unsigned int)CRegistry::OpenKey(
                                     (CRegistry *)&v26,
                                     HKEY_LOCAL_MACHINE,
                                     L"SOFTWARE\\Microsoft\\Dfs\\Roots\\Domain",
                                     0x20006u) )
                {
                  inited = 0;
                  if ( !CRegistry::DeleteKey(&v26, (const unsigned __int16 *)Block) )
                    inited = v27;
                }
                else
                {
                  inited = v27;
                }
                CRegistry::~CRegistry((CRegistry *)&v26);
                if ( !inited )
                {
LABEL_19:
                  v8 = (unsigned __int16 *)DfsInvertHostNameToNetbiosOrFqdn(a3, v24);
                  inited = DfsUpdateRootRemoteServerName(SourceString, a4, a3, a5, 0);
                  if ( inited == 2 && v8 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && pWppControl
                      && (pWppControl[7] & 0x20) != 0
                      && *((_BYTE *)pWppControl + 25) >= 3u )
                    {
                      WPP_SF_S(
                        *((_QWORD *)pWppControl + 2),
                        inited + 21,
                        WPP_85082c1995493ee34407538da2d11b51_Traceguids,
                        v8);
                    }
                    inited = DfsUpdateRootRemoteServerName(SourceString, a4, v8, a5, 0);
                  }
                  v14 = inited;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && pWppControl
                    && (pWppControl[7] & 0x20) != 0
                    && *((_BYTE *)pWppControl + 25) >= 3u )
                  {
                    WPP_SF_D(*((_QWORD *)pWppControl + 2), 24, WPP_85082c1995493ee34407538da2d11b51_Traceguids, inited);
                  }
                  if ( a8 )
                    v15 = inited == 2;
                  else
                    v15 = inited == 0;
                  if ( v15 )
                  {
                    inited = DfsADBlobStore::RemoveRootTargetFromMetadata(
                               this,
                               (struct DfsRootFolder *)a2,
                               a3,
                               a5,
                               &v22);
                    if ( inited == 2 && v8 )
                    {
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && pWppControl
                        && (pWppControl[7] & 0x20) != 0
                        && *((_BYTE *)pWppControl + 25) >= 3u )
                      {
                        WPP_SF_S(
                          *((_QWORD *)pWppControl + 2),
                          inited + 23,
                          WPP_85082c1995493ee34407538da2d11b51_Traceguids,
                          v8);
                      }
                      v17 = this;
                      inited = DfsADBlobStore::RemoveRootTargetFromMetadata(
                                 this,
                                 (struct DfsRootFolder *)a2,
                                 v8,
                                 a5,
                                 &v22);
                    }
                    else
                    {
                      v17 = this;
                    }
                    if ( a8 )
                    {
                      if ( !v14 || !inited )
                        inited = 0;
                    }
                    else
                    {
                      v18 = DfsStore::RemoveRootFolder(v17, (struct DfsRootFolder *)a2, v16);
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && pWppControl
                        && (((1 << (v18 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
                        && *((_BYTE *)pWppControl + 25) )
                      {
                        WPP_SF_D(*((_QWORD *)pWppControl + 2), 26, WPP_85082c1995493ee34407538da2d11b51_Traceguids, v18);
                      }
                      v19 = DfsRootFolder::ReleaseRootShareDirectory((DfsRootFolder *)a2);
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && pWppControl
                        && (((1 << (v19 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
                        && *((_BYTE *)pWppControl + 25) >= 3u )
                      {
                        WPP_SF_D(*((_QWORD *)pWppControl + 2), 27, WPP_85082c1995493ee34407538da2d11b51_Traceguids, v19);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  operator delete(Block);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( pWppControl )
    {
      v20 = inited != 0 ? 11 : 31;
      if ( (((1 << (inited != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
        WPP_SF_D(*((_QWORD *)pWppControl + 2), 28, WPP_85082c1995493ee34407538da2d11b51_Traceguids, inited);
    }
  }
  if ( v23 )
  {
    LOBYTE(v20) = 1;
    (*((void (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD))a2->Ptr + 16))(a2, v20, inited);
  }
  if ( v24[0] )
    operator delete(v8);
  return inited;
}

```

## disassembly

```asm
0x14000dd80  mov     [rsp-38h+arg_8], rbx
0x14000dd85  mov     [rsp-38h+arg_10], r8
0x14000dd8a  mov     [rsp-38h+arg_0], rcx
0x14000dd8f  push    rbp
0x14000dd90  push    rsi
0x14000dd91  push    rdi
0x14000dd92  push    r12
0x14000dd94  push    r13
0x14000dd96  push    r14
0x14000dd98  push    r15
0x14000dd9a  mov     rbp, rsp
0x14000dd9d  sub     rsp, 70h
0x14000dda1  xor     eax, eax
0x14000dda3  xorps   xmm0, xmm0
0x14000dda6  xorps   xmm1, xmm1
0x14000dda9  mov     [rbp+var_40], al
0x14000ddac  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x14000ddb0  mov     [rbp+var_3F], al
0x14000ddb3  mov     r15d, eax
0x14000ddb6  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x14000ddba  mov     [rbp+Block], rax
0x14000ddbe  mov     r12, r9
0x14000ddc1  mov     [rbp+var_3E], al
0x14000ddc4  mov     rbx, r8
0x14000ddc7  mov     rdi, rdx
0x14000ddca  mov     r14, [rbp+SourceString]
0x14000ddce  lea     rcx, WPP_GLOBAL_Control
0x14000ddd5  cmp     cs:WPP_GLOBAL_Control, rcx
0x14000dddc  mov     r13, [rbp+arg_20]
0x14000dde0  jz      short loc_14000DE15
0x14000dde2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000dde9  test    rcx, rcx
0x14000ddec  jz      short loc_14000DE15
0x14000ddee  test    byte ptr [rcx+1Ch], 40h
0x14000ddf2  jz      short loc_14000DE15
0x14000ddf4  cmp     byte ptr [rcx+19h], 2
0x14000ddf8  jb      short loc_14000DE15
0x14000ddfa  mov     rcx, [rcx+10h]
0x14000ddfe  lea     edx, [rax+16h]
0x14000de01  mov     r9, r13
0x14000de04  mov     [rsp+70h+var_50], r14
0x14000de09  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000de10  call    WPP_SF_SS
0x14000de15  mov     rdx, rbx
0x14000de18  lea     rcx, [rbp+var_10]
0x14000de1c  call    DfsRtlInitUnicodeStringEx
0x14000de21  mov     ebx, eax
0x14000de23  mov     esi, 20h ; ' '
0x14000de28  test    eax, eax
0x14000de2a  jnz     loc_14000E182
0x14000de30  mov     rdx, r14
0x14000de33  lea     rcx, [rbp+var_30]
0x14000de37  call    DfsRtlInitUnicodeStringEx
0x14000de3c  mov     ebx, eax
0x14000de3e  test    eax, eax
0x14000de40  jnz     loc_14000E182
0x14000de46  mov     rdx, r13
0x14000de49  lea     rcx, [rbp+var_20]
0x14000de4d  call    DfsRtlInitUnicodeStringEx
0x14000de52  mov     ebx, eax
0x14000de54  test    eax, eax
0x14000de56  jnz     loc_14000E182
0x14000de5c  mov     rax, [rdi]
0x14000de5f  mov     r9, r12
0x14000de62  xor     r8d, r8d
0x14000de65  mov     dl, 1
0x14000de67  mov     rcx, rdi
0x14000de6a  mov     rax, [rax+78h]
0x14000de6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de73  mov     ebx, eax
0x14000de75  test    eax, eax
0x14000de77  jnz     loc_14000E182
0x14000de7d  mov     rcx, [rbp+arg_0]; this
0x14000de81  lea     rax, [rbp+var_20]
0x14000de85  lea     r9, [rbp+var_10]; struct _UNICODE_STRING *
0x14000de89  mov     [rsp+70h+var_50], rax; struct _UNICODE_STRING *
0x14000de8e  mov     r8, r12; unsigned __int16 *
0x14000de91  mov     [rbp+var_3F], 1
0x14000de95  mov     rdx, rdi; struct DfsRootFolder *
0x14000de98  call    ?CheckDeleteAccess@DfsADBlobStore@@QEAAKPEAVDfsRootFolder@@PEBGPEAU_UNICODE_STRING@@2@Z; DfsADBlobStore::CheckDeleteAccess(DfsRootFolder *,ushort const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000de9d  mov     ebx, eax
0x14000de9f  test    eax, eax
0x14000dea1  jnz     loc_14000E182
0x14000dea7  mov     dl, 1; unsigned __int8
0x14000dea9  mov     rcx, rdi; this
0x14000deac  call    ?AcquireRootLock@DfsRootFolder@@QEAAKE@Z; DfsRootFolder::AcquireRootLock(uchar)
0x14000deb1  mov     ebx, eax
0x14000deb3  test    eax, eax
0x14000deb5  jnz     loc_14000E182
0x14000debb  bts     dword ptr [rdi+110h], 0Eh
0x14000dec3  lea     rcx, [rdi+70h]; SRWLock
0x14000dec7  inc     dword ptr [rdi+78h]
0x14000deca  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ded1  nop     dword ptr [rax+rax+00h]
0x14000ded6  cmp     [rbp+arg_38], r15b
0x14000deda  jnz     short loc_14000DF4E
0x14000dedc  mov     r8b, [rbp+arg_30]; unsigned __int8
0x14000dee0  lea     r9, [rbp+Block]; unsigned __int16 **
0x14000dee4  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x14000dee8  mov     rdx, r14; unsigned __int16 *
0x14000deeb  call    ?DfsGetNamespaceRegistrySubkeyName@@YAKPEBG0EPEAPEBG@Z; DfsGetNamespaceRegistrySubkeyName(ushort const *,ushort const *,uchar,ushort const * *)
0x14000def0  mov     ebx, eax
0x14000def2  test    eax, eax
0x14000def4  jnz     loc_14000E182
0x14000defa  and     [rbp+var_30], r15
0x14000defe  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Dfs\\Roots\\Domain"
0x14000df05  and     [rbp+var_28], r15d
0x14000df09  lea     rcx, [rbp+var_30]; this
0x14000df0d  mov     r9d, 20006h; unsigned int
0x14000df13  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14000df1a  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x14000df1f  test    eax, eax
0x14000df21  jnz     short loc_14000DF28
0x14000df23  mov     ebx, [rbp+var_28]
0x14000df26  jmp     short loc_14000DF3D
0x14000df28  mov     rdx, [rbp+Block]; unsigned __int16 *
0x14000df2c  lea     rcx, [rbp+var_30]; this
0x14000df30  call    ?DeleteKey@CRegistry@@QEAAHPEBG@Z; CRegistry::DeleteKey(ushort const *)
0x14000df35  xor     ebx, ebx
0x14000df37  test    eax, eax
0x14000df39  cmovz   ebx, [rbp+var_28]
0x14000df3d  lea     rcx, [rbp+var_30]; this
0x14000df41  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x14000df46  test    ebx, ebx
0x14000df48  jnz     loc_14000E182
0x14000df4e  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x14000df52  lea     rdx, [rbp+var_3E]; unsigned __int8 *
0x14000df56  call    ?DfsInvertHostNameToNetbiosOrFqdn@@YAPEBGPEBGPEAE@Z; DfsInvertHostNameToNetbiosOrFqdn(ushort const *,uchar *)
0x14000df5b  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x14000df5f  mov     r9, r13; unsigned __int16 *
0x14000df62  mov     rdx, r12; unsigned __int16 *
0x14000df65  mov     byte ptr [rsp+70h+var_50], 0; unsigned __int8
0x14000df6a  mov     rcx, r14; SourceString
0x14000df6d  mov     r15, rax
0x14000df70  call    ?DfsUpdateRootRemoteServerName@@YAKPEBG000E@Z; DfsUpdateRootRemoteServerName(ushort const *,ushort const *,ushort const *,ushort const *,uchar)
0x14000df75  mov     ebx, eax
0x14000df77  cmp     eax, 2
0x14000df7a  jnz     short loc_14000DFD7
0x14000df7c  test    r15, r15
0x14000df7f  jz      short loc_14000DFD7
0x14000df81  lea     rax, WPP_GLOBAL_Control
0x14000df88  cmp     cs:WPP_GLOBAL_Control, rax
0x14000df8f  jz      short loc_14000DFBF
0x14000df91  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000df98  test    rcx, rcx
0x14000df9b  jz      short loc_14000DFBF
0x14000df9d  test    [rcx+1Ch], sil
0x14000dfa1  jz      short loc_14000DFBF
0x14000dfa3  cmp     byte ptr [rcx+19h], 3
0x14000dfa7  jb      short loc_14000DFBF
0x14000dfa9  mov     rcx, [rcx+10h]
0x14000dfad  lea     edx, [rbx+15h]
0x14000dfb0  mov     r9, r15
0x14000dfb3  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000dfba  call    WPP_SF_S
0x14000dfbf  mov     r9, r13; unsigned __int16 *
0x14000dfc2  mov     byte ptr [rsp+70h+var_50], 0; unsigned __int8
0x14000dfc7  mov     r8, r15; unsigned __int16 *
0x14000dfca  mov     rdx, r12; unsigned __int16 *
0x14000dfcd  mov     rcx, r14; SourceString
0x14000dfd0  call    ?DfsUpdateRootRemoteServerName@@YAKPEBG000E@Z; DfsUpdateRootRemoteServerName(ushort const *,ushort const *,ushort const *,ushort const *,uchar)
0x14000dfd5  mov     ebx, eax
0x14000dfd7  lea     rax, WPP_GLOBAL_Control
0x14000dfde  mov     r14d, ebx
0x14000dfe1  cmp     cs:WPP_GLOBAL_Control, rax
0x14000dfe8  jz      short loc_14000E01A
0x14000dfea  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000dff1  test    rcx, rcx
0x14000dff4  jz      short loc_14000E01A
0x14000dff6  test    [rcx+1Ch], sil
0x14000dffa  jz      short loc_14000E01A
0x14000dffc  cmp     byte ptr [rcx+19h], 3
0x14000e000  jb      short loc_14000E01A
0x14000e002  mov     rcx, [rcx+10h]
0x14000e006  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e00d  mov     edx, 18h
0x14000e012  mov     r9d, ebx
0x14000e015  call    WPP_SF_D
0x14000e01a  mov     r12b, [rbp+arg_38]
0x14000e01e  test    r12b, r12b
0x14000e021  jnz     short loc_14000E027
0x14000e023  test    ebx, ebx
0x14000e025  jmp     short loc_14000E02A
0x14000e027  cmp     ebx, 2
0x14000e02a  jnz     loc_14000E182
0x14000e030  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x14000e034  lea     rax, [rbp+var_40]
0x14000e038  mov     rcx, [rbp+arg_0]; this
0x14000e03c  mov     r9, r13; unsigned __int16 *
0x14000e03f  mov     rdx, rdi; struct DfsRootFolder *
0x14000e042  mov     [rsp+70h+var_50], rax; unsigned __int8 *
0x14000e047  call    ?RemoveRootTargetFromMetadata@DfsADBlobStore@@QEAAKPEAVDfsRootFolder@@PEBG1PEAE@Z; DfsADBlobStore::RemoveRootTargetFromMetadata(DfsRootFolder *,ushort const *,ushort const *,uchar *)
0x14000e04c  mov     ebx, eax
0x14000e04e  cmp     eax, 2
0x14000e051  jnz     short loc_14000E0B8
0x14000e053  test    r15, r15
0x14000e056  jz      short loc_14000E0B8
0x14000e058  lea     rax, WPP_GLOBAL_Control
0x14000e05f  cmp     cs:WPP_GLOBAL_Control, rax
0x14000e066  jz      short loc_14000E096
0x14000e068  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e06f  test    rcx, rcx
0x14000e072  jz      short loc_14000E096
0x14000e074  test    [rcx+1Ch], sil
0x14000e078  jz      short loc_14000E096
0x14000e07a  cmp     byte ptr [rcx+19h], 3
0x14000e07e  jb      short loc_14000E096
0x14000e080  mov     rcx, [rcx+10h]
0x14000e084  lea     edx, [rbx+17h]
0x14000e087  mov     r9, r15
0x14000e08a  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e091  call    WPP_SF_S
0x14000e096  mov     r9, r13; unsigned __int16 *
0x14000e099  lea     rax, [rbp+var_40]
0x14000e09d  mov     r13, [rbp+arg_0]
0x14000e0a1  mov     r8, r15; unsigned __int16 *
0x14000e0a4  mov     rcx, r13; this
0x14000e0a7  mov     [rsp+70h+var_50], rax; unsigned __int8 *
0x14000e0ac  mov     rdx, rdi; struct DfsRootFolder *
0x14000e0af  call    ?RemoveRootTargetFromMetadata@DfsADBlobStore@@QEAAKPEAVDfsRootFolder@@PEBG1PEAE@Z; DfsADBlobStore::RemoveRootTargetFromMetadata(DfsRootFolder *,ushort const *,ushort const *,uchar *)
0x14000e0b4  mov     ebx, eax
0x14000e0b6  jmp     short loc_14000E0BC
0x14000e0b8  mov     r13, [rbp+arg_0]
0x14000e0bc  test    r12b, r12b
0x14000e0bf  jnz     loc_14000E177
0x14000e0c5  mov     rdx, rdi; struct DfsRootFolder *
0x14000e0c8  mov     rcx, r13; this
0x14000e0cb  call    ?RemoveRootFolder@DfsStore@@QEAAKPEAVDfsRootFolder@@E@Z; DfsStore::RemoveRootFolder(DfsRootFolder *,uchar)
0x14000e0d0  mov     r9d, eax
0x14000e0d3  lea     r14, WPP_GLOBAL_Control
0x14000e0da  cmp     cs:WPP_GLOBAL_Control, r14
0x14000e0e1  jz      short loc_14000E122
0x14000e0e3  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e0ea  test    r10, r10
0x14000e0ed  jz      short loc_14000E122
0x14000e0ef  mov     ecx, eax
0x14000e0f1  mov     eax, esi
0x14000e0f3  neg     ecx
0x14000e0f5  sbb     edx, edx
0x14000e0f7  and     edx, 0FFFFFFECh
0x14000e0fa  add     edx, 1Fh
0x14000e0fd  bts     eax, edx
0x14000e100  test    [r10+1Ch], eax
0x14000e104  jz      short loc_14000E122
0x14000e106  cmp     byte ptr [r10+19h], 1
0x14000e10b  jb      short loc_14000E122
0x14000e10d  mov     rcx, [r10+10h]
0x14000e111  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e118  mov     edx, 1Ah
0x14000e11d  call    WPP_SF_D
0x14000e122  mov     rcx, rdi; this
0x14000e125  call    ?ReleaseRootShareDirectory@DfsRootFolder@@QEAAKXZ; DfsRootFolder::ReleaseRootShareDirectory(void)
0x14000e12a  mov     r9d, eax
0x14000e12d  cmp     cs:WPP_GLOBAL_Control, r14
0x14000e134  jz      short loc_14000E182
0x14000e136  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e13d  test    r10, r10
0x14000e140  jz      short loc_14000E182
0x14000e142  mov     ecx, eax
0x14000e144  mov     eax, esi
0x14000e146  neg     ecx
0x14000e148  sbb     edx, edx
0x14000e14a  and     edx, 0FFFFFFECh
0x14000e14d  add     edx, 1Fh
0x14000e150  bts     eax, edx
0x14000e153  test    [r10+1Ch], eax
0x14000e157  jz      short loc_14000E182
0x14000e159  cmp     byte ptr [r10+19h], 3
0x14000e15e  jb      short loc_14000E182
0x14000e160  mov     rcx, [r10+10h]
0x14000e164  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e16b  mov     edx, 1Bh
0x14000e170  call    WPP_SF_D
0x14000e175  jmp     short loc_14000E182
0x14000e177  test    r14d, r14d
0x14000e17a  jz      short loc_14000E180
0x14000e17c  test    ebx, ebx
0x14000e17e  jnz     short loc_14000E182
0x14000e180  xor     ebx, ebx
0x14000e182  mov     rcx, [rbp+Block]; Block
0x14000e186  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000e18b  lea     rax, WPP_GLOBAL_Control
0x14000e192  cmp     cs:WPP_GLOBAL_Control, rax
0x14000e199  jz      short loc_14000E1D9
0x14000e19b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000e1a2  test    rcx, rcx
0x14000e1a5  jz      short loc_14000E1D9
0x14000e1a7  mov     eax, ebx
0x14000e1a9  neg     eax
0x14000e1ab  sbb     edx, edx
0x14000e1ad  and     edx, 0FFFFFFECh
0x14000e1b0  add     edx, 1Fh
0x14000e1b3  bts     esi, edx
0x14000e1b6  test    [rcx+1Ch], esi
0x14000e1b9  jz      short loc_14000E1D9
0x14000e1bb  cmp     byte ptr [rcx+19h], 3
0x14000e1bf  jb      short loc_14000E1D9
0x14000e1c1  mov     rcx, [rcx+10h]
0x14000e1c5  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000e1cc  mov     edx, 1Ch
  ... truncated ...
```
