# RxFindCreateDestinationVNetRoot

- ea: `0x14004d498`
- end: `0x14004dbb8`
- name: `RxFindCreateDestinationVNetRoot`
- size: `1824`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004f55c`
- `0x140060560`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x14000f4d0`
- `0x140014d10`
- `0x140014e40`
- `0x1400169b0`
- `0x140016e20`
- `0x140016e70`
- `0x140021c64`
- `0x140025d00`
- `0x140025d80`
- `0x14004d498`
- `0x14004dc60`
- `0x140050414`
- `0x140058f00`
- `0x14005f110`
- `0x140060f10`
- `0x1400621c0`
- `0x140069800`
- `0x14006b1d0`
- `0x140078460`
- `0x140078a90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004d619`
- `ntoskrnl!ExAllocatePool2` at `0x14004d619`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d6ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d878`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d993`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004daa1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d6ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d878`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d993`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004daa1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d817`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da43`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004db03`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004db2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d817`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da43`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004db03`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004db2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004db4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004db4c`

## pseudocode

```c
__int64 __fastcall RxFindCreateDestinationVNetRoot(__int64 a1, __int64 a2, __int64 a3, __int64 *a4, __int64 a5)
{
  __int64 v5; // rax
  __int64 v8; // r12
  __int64 v9; // rdi
  struct _RDBSS_DEVICE_OBJECT *v10; // rbx
  LARGE_INTEGER CacheWriteBytesRequested; // r13
  PRX_CONTEXT RxContext; // rax
  PRX_CONTEXT v13; // r14
  int v14; // esi
  __int64 v15; // rax
  wchar_t *Pool2; // rax
  __int64 v17; // rbx
  LOCK_HOLDING_STATE v18; // r15d
  __int64 v19; // r8
  _QWORD *v20; // r13
  _QWORD *v21; // r12
  __int64 v22; // rbx
  int IsCompatibleSecurityContext; // eax
  _QWORD *v24; // rdx
  struct _ERESOURCE *v25; // r13
  struct _ERESOURCE *v26; // r15
  __int64 v27; // rdx
  bool v28; // zf
  int v29; // ebx
  PV_NET_ROOT v30; // rax
  NTSTATUS v31; // eax
  int v32; // eax
  struct _ERESOURCE *v33; // r13
  bool v34; // sf
  __int64 (__fastcall *v35)(__int64, __int64); // rax
  int FilePath; // [rsp+28h] [rbp-51h]
  enum _LOCK_HOLDING_STATE *FilePatha; // [rsp+28h] [rbp-51h]
  int v39; // [rsp+30h] [rbp-49h]
  char v40; // [rsp+38h] [rbp-41h]
  int v41; // [rsp+3Ch] [rbp-3Dh] BYREF
  PERESOURCE Resource; // [rsp+40h] [rbp-39h]
  __int64 v43; // [rsp+48h] [rbp-31h] BYREF
  LARGE_INTEGER v44; // [rsp+50h] [rbp-29h]
  UNICODE_STRING CanonicalName; // [rsp+58h] [rbp-21h] BYREF
  UNICODE_STRING LocalNetRootName; // [rsp+68h] [rbp-11h] BYREF
  char v47[80]; // [rsp+78h] [rbp-1h] BYREF

  v5 = *(_QWORD *)(a3 + 32);
  v8 = a2;
  v43 = 0;
  v9 = 0;
  v10 = *(struct _RDBSS_DEVICE_OBJECT **)(v5 + 48);
  CacheWriteBytesRequested = v10->CacheWriteBytesRequested;
  v44 = CacheWriteBytesRequested;
  *(_QWORD *)&CanonicalName.Length = 0;
  CanonicalName.Buffer = 0;
  *(_QWORD *)&LocalNetRootName.Length = 0;
  LocalNetRootName.Buffer = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qZD(
        WPP_GLOBAL_Control->AttachedDevice,
        117,
        (unsigned int)&WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
        a2,
        a2 + 224,
        *(_DWORD *)(a2 + 56));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        118,
        (unsigned int)&WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
        a3,
        a3 + 216);
    }
  }
  RxContext = RxCreateRxContext(0, v10, 2u);
  v13 = RxContext;
  if ( !RxContext )
  {
    v14 = -1073741670;
    goto LABEL_93;
  }
  LOWORD(RxContext->RealDevice) = 0;
  *(_QWORD *)&RxContext->TrackerHistory[0].Flags = 0;
  RxContext->TrackerHistory[0].FileName = 0;
  *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = 0;
  v15 = *(_QWORD *)(a1 + 568);
  LODWORD(v13->RdbssDbgExtension) |= 0x100u;
  *((_QWORD *)&v13->9 + 21) = v15;
  if ( (*(_DWORD *)(v8 + 56) & 0x40) != 0 )
  {
    LODWORD(v13->RdbssDbgExtension) |= 0x800u;
    *(_QWORD *)&v13->TrackerHistory[8].AcquireRelease = a5 + 112;
  }
  CanonicalName.Length = *(_WORD *)(a3 + 216) + 2 * *(_WORD *)(v8 + 304);
  CanonicalName.MaximumLength = CanonicalName.Length;
  Pool2 = (wchar_t *)ExAllocatePool2(258, CanonicalName.Length, 1061124178);
  CanonicalName.Buffer = Pool2;
  if ( !Pool2 )
  {
    v14 = -1073741670;
    goto LABEL_92;
  }
  v17 = v8 + 288;
  v40 = 0;
  v14 = 0;
  memmove(Pool2, *(const void **)(v8 + 232), 2LL * *(unsigned __int16 *)(v8 + 304));
  memmove(
    &CanonicalName.Buffer[*(unsigned __int16 *)(v8 + 304)],
    *(const void **)(a3 + 224),
    *(unsigned __int16 *)(a3 + 216));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 119, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, &CanonicalName);
  }
  Resource = (PERESOURCE)(CacheWriteBytesRequested.QuadPart + 24);
  ExAcquireResourceExclusiveLite((PERESOURCE)(CacheWriteBytesRequested.QuadPart + 24), 1u);
  v18 = LHS_ExclusiveLockHeld;
  v41 = 2;
LABEL_20:
  LOBYTE(FilePath) = 0;
  v9 = 0;
  v20 = (_QWORD *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))RxPrefixTableLookupNameEx)(
                    (LARGE_INTEGER)CacheWriteBytesRequested.QuadPart,
                    &CanonicalName,
                    v47,
                    v17,
                    FilePath);
  if ( v20 )
  {
    if ( *(_WORD *)v20 == 0xEB12 )
    {
      v21 = (_QWORD *)(v20[4] + 176LL);
      if ( (_QWORD *)*v21 == v21 )
        v22 = 0;
      else
        v22 = *v21 - 336LL;
      while ( 1 )
      {
        v9 = 0;
        if ( !v22 )
          break;
        if ( (((unsigned __int8)(*(_DWORD *)(a2 + 56) >> 6) ^ (unsigned __int8)(*(_DWORD *)(v22 + 56) >> 6)) & 1) == 0 )
        {
          IsCompatibleSecurityContext = RxIsCompatibleSecurityContext((PLUID)(v22 + 72), (int *)(a2 + 72), v19);
          v14 = IsCompatibleSecurityContext;
          if ( IsCompatibleSecurityContext >= 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 120, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, v22);
            }
            RxReference((PVOID)v22);
            v9 = v22;
            break;
          }
          if ( IsCompatibleSecurityContext != -1073741802 )
            break;
        }
        v24 = *(_QWORD **)(v22 + 336);
        v22 = (__int64)(v24 - 42);
        if ( v24 == v21 )
          v22 = 0;
      }
      RxDereference(v20, LHS_ExclusiveLockHeld);
      v8 = a2;
    }
    else
    {
      RxDereference(v20, LHS_ExclusiveLockHeld);
    }
  }
  v25 = Resource;
  while ( 1 )
  {
    if ( !v9 )
      goto LABEL_58;
    if ( *(int *)(v9 + 204) >= 3 )
    {
      LOBYTE(v19) = v40;
    }
    else
    {
      v26 = Resource;
      ExReleaseResourceLite(Resource);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 121, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, v9);
      }
      RxWaitForStableCondition((PRX_BLOCK_CONDITION)a1, (PLIST_ENTRY)(v9 + 204), (PRX_CONTEXT)(v9 + 360), 0);
      ExAcquireResourceExclusiveLite(v26, 1u);
      LOBYTE(v19) = v40;
      v41 = 2;
      v18 = LHS_ExclusiveLockHeld;
      if ( !v40 )
      {
        RxDereference((PVOID)v9, LHS_ExclusiveLockHeld);
        CacheWriteBytesRequested = v44;
        v17 = v8 + 288;
        goto LABEL_20;
      }
      v25 = Resource;
    }
    v27 = *(unsigned int *)(v9 + 204);
    if ( (_DWORD)v27 == 3 )
      break;
    if ( (_BYTE)v19 )
    {
      v14 = *(_DWORD *)(v9 + 208);
      if ( v14 >= 0 )
        v14 = -1073741634;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LOBYTE(v19) = -(char)v19;
      LOBYTE(v39) = (_BYTE)v19 != 0 ? 78 : 89;
      WPP_SF_qDc(WPP_GLOBAL_Control->AttachedDevice, v27, v19, v9, v27, v39);
    }
    RxDereference((PVOID)v9, v18);
    v9 = 0;
LABEL_58:
    v28 = v14 == 0;
    if ( v14 < 0 )
      goto LABEL_73;
    RxStripSessionPrefix(&CanonicalName, &LocalNetRootName, 0);
    v29 = a3;
    v30 = RxCreateVNetRoot(
            v13,
            (PNET_ROOT)a3,
            &CanonicalName,
            &LocalNetRootName,
            (PUNICODE_STRING)(v8 + 288),
            (PRX_CONNECTION_ID)v8);
    v9 = (__int64)v30;
    if ( !v30 )
    {
      v14 = -1073741670;
      goto LABEL_76;
    }
    RxReference(v30);
    v31 = RxConstructNetRoot(v13, 0, (PNET_ROOT)v9, (PV_NET_ROOT)&v41, FilePatha);
    v18 = v41;
    v14 = v31;
    if ( v31 != 259 )
      goto LABEL_66;
    v40 = 1;
    if ( !v41 )
    {
      ExAcquireResourceExclusiveLite(v25, 1u);
      v18 = LHS_ExclusiveLockHeld;
      v41 = 2;
    }
    v14 = 0;
  }
  v29 = a3;
LABEL_66:
  v28 = v14 == 0;
  if ( v14 >= 0 )
  {
    if ( (*(_DWORD *)(v9 + 56) & 0x50) == 0
      && (unsigned __int8)RxGetShareRights(v9, &v43)
      && !(_WORD)v43
      && !(unsigned __int8)RxIsUserCredentialPresent(*(_QWORD *)(v9 + 104)) )
    {
      v32 = RxRecreateVNetRootOnLogicalRdr(a1, v29, v9, a5, (__int64)&v41);
      v18 = v41;
      v14 = v32;
    }
    v28 = v14 == 0;
  }
LABEL_73:
  if ( !v28 && v9 )
  {
    RxDereference((PVOID)v9, v18);
    v9 = 0;
  }
LABEL_76:
  v33 = Resource;
  if ( v18 )
  {
    ExReleaseResourceLite(Resource);
    v18 = LHS_LockNotHeld;
  }
  v34 = v14 < 0;
  if ( v14 )
  {
LABEL_89:
    if ( v34 && v9 )
    {
      RxDereference((PVOID)v9, v18);
      v9 = 0;
    }
  }
  else
  {
    RxWaitForStableCondition((PRX_BLOCK_CONDITION)v13, (PLIST_ENTRY)(v9 + 204), (PRX_CONTEXT)(v9 + 360), 0);
    if ( *(_DWORD *)(v9 + 204) == 3 && !*(_QWORD *)(v9 + 392) && *(_QWORD *)(v8 + 392) )
    {
      ExAcquireResourceExclusiveLite(v33, 1u);
      if ( !*(_QWORD *)(v9 + 392) )
      {
        v35 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)(v8 + 392) + 352LL) + 424LL);
        if ( v35 )
          v14 = v35(v9, a5);
        else
          v14 = -1073741822;
        *(_QWORD *)(v9 + 392) = *(_QWORD *)(v8 + 392);
      }
      ExReleaseResourceLite(v33);
      v34 = v14 < 0;
      goto LABEL_89;
    }
  }
LABEL_92:
  RxDereferenceAndDeleteRxContext_Real(v13);
LABEL_93:
  if ( CanonicalName.Buffer )
  {
    ExFreePoolWithTag(CanonicalName.Buffer, 0);
    CanonicalName.Buffer = 0;
  }
  *a4 = v9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      123,
      &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14004d498  mov     rax, rsp
0x14004d49b  mov     [rax+20h], r9
0x14004d49f  mov     [rax+18h], r8
0x14004d4a3  mov     [rax+10h], rdx
0x14004d4a7  mov     [rax+8], rcx
0x14004d4ab  push    rbp
0x14004d4ac  push    rbx
0x14004d4ad  push    rsi
0x14004d4ae  push    rdi
0x14004d4af  push    r12
0x14004d4b1  push    r13
0x14004d4b3  push    r14
0x14004d4b5  push    r15
0x14004d4b7  lea     rbp, [rax-57h]
0x14004d4bb  sub     rsp, 88h
0x14004d4c2  mov     rax, [r8+20h]
0x14004d4c6  mov     rsi, rcx
0x14004d4c9  xor     ecx, ecx
0x14004d4cb  mov     r15, r8
0x14004d4ce  mov     r12, rdx
0x14004d4d1  mov     [rbp+4Fh+var_80], rcx
0x14004d4d5  mov     edi, ecx
0x14004d4d7  mov     rbx, [rax+30h]
0x14004d4db  mov     r13, [rbx+1F8h]
0x14004d4e2  mov     [rbp+4Fh+var_78], r13
0x14004d4e6  mov     qword ptr [rbp+4Fh+CanonicalName.Length], rcx
0x14004d4ea  mov     [rbp+4Fh+CanonicalName.Buffer], rcx
0x14004d4ee  mov     qword ptr [rbp+4Fh+LocalNetRootName.Length], rcx
0x14004d4f2  mov     [rbp+4Fh+LocalNetRootName.Buffer], rcx
0x14004d4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d4fd  lea     r14, WPP_GLOBAL_Control
0x14004d504  cmp     rcx, r14
0x14004d507  jz      short loc_14004D582
0x14004d509  test    dword ptr [rcx+2Ch], 400h
0x14004d510  jz      short loc_14004D543
0x14004d512  cmp     byte ptr [rcx+29h], 2
0x14004d516  jb      short loc_14004D543
0x14004d518  mov     eax, [r12+38h]
0x14004d51d  lea     r8, [rdx+0E0h]
0x14004d524  mov     rcx, [rcx+18h]
0x14004d528  lea     edx, [rdi+75h]
0x14004d52b  mov     [rsp+28h], eax
0x14004d52f  mov     r9, r12
0x14004d532  mov     [rsp+0C0h+FilePath], r8
0x14004d537  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004d53e  call    WPP_SF_qZD
0x14004d543  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d54a  cmp     rcx, r14
0x14004d54d  jz      short loc_14004D582
0x14004d54f  test    dword ptr [rcx+2Ch], 400h
0x14004d556  jz      short loc_14004D582
0x14004d558  cmp     byte ptr [rcx+29h], 2
0x14004d55c  jb      short loc_14004D582
0x14004d55e  mov     rcx, [rcx+18h]
0x14004d562  lea     rax, [r15+0D8h]
0x14004d569  mov     edx, 76h ; 'v'
0x14004d56e  mov     [rsp+0C0h+FilePath], rax
0x14004d573  mov     r9, r15
0x14004d576  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004d57d  call    WPP_SF_qZ
0x14004d582  mov     r8d, 2; InitialContextFlags
0x14004d588  mov     rdx, rbx; RxDeviceObject
0x14004d58b  xor     ecx, ecx; Irp
0x14004d58d  call    RxCreateRxContext
0x14004d592  mov     r14, rax
0x14004d595  test    rax, rax
0x14004d598  jnz     short loc_14004D5A4
0x14004d59a  mov     esi, 0C000009Ah
0x14004d59f  jmp     loc_14004DB41
0x14004d5a4  mov     [rax+20h], di
0x14004d5a8  mov     [rax+290h], rdi
0x14004d5af  mov     [rax+288h], rdi
0x14004d5b6  mov     [rax+280h], rdi
0x14004d5bd  mov     rax, [rsi+238h]
0x14004d5c4  bts     dword ptr [r14+78h], 8
0x14004d5ca  mov     [r14+238h], rax
0x14004d5d1  mov     eax, [r12+38h]
0x14004d5d6  test    al, 40h
0x14004d5d8  jz      short loc_14004D5EF
0x14004d5da  bts     dword ptr [r14+78h], 0Bh
0x14004d5e0  mov     rax, [rbp+4Fh+arg_20]
0x14004d5e4  add     rax, 70h ; 'p'
0x14004d5e8  mov     [r14+340h], rax
0x14004d5ef  movzx   eax, word ptr [r12+130h]
0x14004d5f8  mov     ecx, 102h
0x14004d5fd  add     ax, ax
0x14004d600  mov     r8d, 3F3F7852h
0x14004d606  add     ax, [r15+0D8h]
0x14004d60e  movzx   edx, ax
0x14004d611  mov     [rbp+4Fh+CanonicalName.Length], dx
0x14004d615  mov     [rbp+4Fh+CanonicalName.MaximumLength], dx
0x14004d619  call    cs:__imp_ExAllocatePool2
0x14004d620  nop     dword ptr [rax+rax+00h]
0x14004d625  mov     [rbp+4Fh+CanonicalName.Buffer], rax
0x14004d629  test    rax, rax
0x14004d62c  jnz     short loc_14004D638
0x14004d62e  mov     esi, 0C000009Ah
0x14004d633  jmp     loc_14004DB39
0x14004d638  movzx   r8d, word ptr [r12+130h]
0x14004d641  lea     rbx, [r12+120h]
0x14004d649  mov     rdx, [r12+0E8h]; Src
0x14004d651  xor     cl, cl
0x14004d653  mov     [rbp+4Fh+var_90], cl
0x14004d656  add     r8, r8; Size
0x14004d659  mov     rcx, rax; void *
0x14004d65c  xor     esi, esi
0x14004d65e  call    memmove
0x14004d663  movzx   ecx, word ptr [r12+130h]
0x14004d66c  mov     rax, [rbp+4Fh+CanonicalName.Buffer]
0x14004d670  movzx   r8d, word ptr [r15+0D8h]; Size
0x14004d678  mov     rdx, [r15+0E0h]; Src
0x14004d67f  lea     rcx, [rax+rcx*2]; void *
0x14004d683  call    memmove
0x14004d688  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d68f  lea     rax, WPP_GLOBAL_Control
0x14004d696  cmp     rcx, rax
0x14004d699  jz      short loc_14004D6C1
0x14004d69b  test    dword ptr [rcx+2Ch], 400h
0x14004d6a2  jz      short loc_14004D6C1
0x14004d6a4  cmp     byte ptr [rcx+29h], 2
0x14004d6a8  jb      short loc_14004D6C1
0x14004d6aa  mov     rcx, [rcx+18h]
0x14004d6ae  lea     edx, [rsi+77h]
0x14004d6b1  lea     r9, [rbp+4Fh+CanonicalName]
0x14004d6b5  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004d6bc  call    WPP_SF_Z
0x14004d6c1  lea     rax, [r13+18h]
0x14004d6c5  mov     dl, 1; Wait
0x14004d6c7  mov     rcx, rax; Resource
0x14004d6ca  mov     [rbp+4Fh+Resource], rax
0x14004d6ce  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004d6d5  nop     dword ptr [rax+rax+00h]
0x14004d6da  mov     r15d, 2
0x14004d6e0  mov     [rbp+4Fh+var_8C], r15d
0x14004d6e4  mov     r9, rbx
0x14004d6e7  mov     byte ptr [rsp+0C0h+FilePath], 0
0x14004d6ec  lea     r8, [rbp+4Fh+var_50]
0x14004d6f0  mov     rcx, r13
0x14004d6f3  lea     rdx, [rbp+4Fh+CanonicalName]
0x14004d6f7  call    RxPrefixTableLookupNameEx
0x14004d6fc  xor     edi, edi
0x14004d6fe  mov     r13, rax
0x14004d701  test    rax, rax
0x14004d704  jz      loc_14004D7F3
0x14004d70a  mov     eax, 0EB12h
0x14004d70f  cmp     [r13+0], ax
0x14004d714  jnz     loc_14004D7E6
0x14004d71a  mov     r12, [r13+20h]
0x14004d71e  add     r12, 0B0h
0x14004d725  mov     rbx, [r12]
0x14004d729  cmp     rbx, r12
0x14004d72c  jnz     short loc_14004D732
0x14004d72e  xor     ebx, ebx
0x14004d730  jmp     short loc_14004D739
0x14004d732  add     rbx, 0FFFFFFFFFFFFFEB0h
0x14004d739  xor     edi, edi
0x14004d73b  test    rbx, rbx
0x14004d73e  jz      loc_14004D7D3
0x14004d744  mov     rdx, [rbp+4Fh+arg_8]
0x14004d748  mov     ecx, [rbx+38h]
0x14004d74b  shr     ecx, 6
0x14004d74e  mov     eax, [rdx+38h]
0x14004d751  shr     eax, 6
0x14004d754  xor     cl, al
0x14004d756  test    cl, 1
0x14004d759  jnz     short loc_14004D775
0x14004d75b  add     rdx, 48h ; 'H'
0x14004d75f  lea     rcx, [rbx+48h]; LogonId
0x14004d763  call    RxIsCompatibleSecurityContext
0x14004d768  mov     esi, eax
0x14004d76a  test    eax, eax
0x14004d76c  jns     short loc_14004D78E
0x14004d76e  cmp     eax, 0C0000016h
0x14004d773  jnz     short loc_14004D7D3
0x14004d775  mov     rdx, [rbx+150h]
0x14004d77c  xor     ecx, ecx
0x14004d77e  cmp     rdx, r12
0x14004d781  lea     rbx, [rdx-150h]
0x14004d788  cmovz   rbx, rcx
0x14004d78c  jmp     short loc_14004D739
0x14004d78e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d795  lea     rax, WPP_GLOBAL_Control
0x14004d79c  cmp     rcx, rax
0x14004d79f  jz      short loc_14004D7C8
0x14004d7a1  test    dword ptr [rcx+2Ch], 400h
0x14004d7a8  jz      short loc_14004D7C8
0x14004d7aa  cmp     byte ptr [rcx+29h], 2
0x14004d7ae  jb      short loc_14004D7C8
0x14004d7b0  mov     rcx, [rcx+18h]
0x14004d7b4  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004d7bb  mov     edx, 78h ; 'x'
0x14004d7c0  mov     r9, rbx
0x14004d7c3  call    WPP_SF_q
0x14004d7c8  mov     rcx, rbx; Instance
0x14004d7cb  call    RxReference
0x14004d7d0  mov     rdi, rbx
0x14004d7d3  mov     edx, 2; LockHoldingState
0x14004d7d8  mov     rcx, r13; Instance
0x14004d7db  call    RxDereference
0x14004d7e0  mov     r12, [rbp+4Fh+arg_8]
0x14004d7e4  jmp     short loc_14004D7F3
0x14004d7e6  mov     edx, 2; LockHoldingState
0x14004d7eb  mov     rcx, r13; Instance
0x14004d7ee  call    RxDereference
0x14004d7f3  mov     r13, [rbp+4Fh+Resource]
0x14004d7f7  test    rdi, rdi
0x14004d7fa  jz      loc_14004D912
0x14004d800  lea     rbx, [rdi+0CCh]
0x14004d807  cmp     dword ptr [rbx], 3
0x14004d80a  jge     loc_14004D8A2
0x14004d810  mov     r15, [rbp+4Fh+Resource]
0x14004d814  mov     rcx, r15; Resource
0x14004d817  call    cs:__imp_ExReleaseResourceLite
0x14004d81e  nop     dword ptr [rax+rax+00h]
0x14004d823  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d82a  lea     rax, WPP_GLOBAL_Control
0x14004d831  cmp     rcx, rax
0x14004d834  jz      short loc_14004D85D
0x14004d836  test    dword ptr [rcx+2Ch], 400h
0x14004d83d  jz      short loc_14004D85D
0x14004d83f  cmp     byte ptr [rcx+29h], 4
0x14004d843  jb      short loc_14004D85D
0x14004d845  mov     rcx, [rcx+18h]
0x14004d849  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004d850  mov     edx, 79h ; 'y'
0x14004d855  mov     r9, rdi
0x14004d858  call    WPP_SF_q
0x14004d85d  mov     rcx, [rbp+4Fh+Condition]; Condition
0x14004d861  lea     r8, [rdi+168h]; RxContext
0x14004d868  xor     r9d, r9d; AsyncStatus
0x14004d86b  mov     rdx, rbx; TransitionWaitList
0x14004d86e  call    RxWaitForStableCondition
0x14004d873  mov     dl, 1; Wait
0x14004d875  mov     rcx, r15; Resource
0x14004d878  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004d87f  nop     dword ptr [rax+rax+00h]
0x14004d884  mov     r8b, [rbp+4Fh+var_90]
0x14004d888  mov     eax, 2
0x14004d88d  mov     [rbp+4Fh+var_8C], eax
0x14004d890  mov     r15d, eax
0x14004d893  test    r8b, r8b
0x14004d896  jz      loc_14004D9B0
0x14004d89c  mov     r13, [rbp+4Fh+Resource]
0x14004d8a0  jmp     short loc_14004D8A6
0x14004d8a2  mov     r8b, [rbp+4Fh+var_90]
0x14004d8a6  mov     edx, [rbx]
0x14004d8a8  cmp     edx, 3
0x14004d8ab  jz      loc_14004D9CB
0x14004d8b1  test    r8b, r8b
0x14004d8b4  jz      short loc_14004D8C6
0x14004d8b6  mov     esi, [rdi+0D0h]
0x14004d8bc  mov     eax, 0C00000BEh
0x14004d8c1  test    esi, esi
0x14004d8c3  cmovns  esi, eax
0x14004d8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d8cd  lea     rax, WPP_GLOBAL_Control
0x14004d8d4  cmp     rcx, rax
0x14004d8d7  jz      short loc_14004D905
0x14004d8d9  test    dword ptr [rcx+2Ch], 400h
0x14004d8e0  jz      short loc_14004D905
0x14004d8e2  cmp     byte ptr [rcx+29h], 4
0x14004d8e6  jb      short loc_14004D905
0x14004d8e8  mov     rcx, [rcx+18h]
0x14004d8ec  neg     r8b
0x14004d8ef  mov     r9, rdi
0x14004d8f2  sbb     al, al
0x14004d8f4  and     al, 0F5h
0x14004d8f6  add     al, 59h ; 'Y'
0x14004d8f8  mov     [rsp+28h], al
0x14004d8fc  mov     dword ptr [rsp+0C0h+FilePath], edx
0x14004d900  call    WPP_SF_qDc
0x14004d905  mov     edx, r15d; LockHoldingState
0x14004d908  mov     rcx, rdi; Instance
0x14004d90b  call    RxDereference
0x14004d910  xor     edi, edi
0x14004d912  test    esi, esi
0x14004d914  js      loc_14004DA23
0x14004d91a  xor     r8d, r8d
0x14004d91d  lea     rdx, [rbp+4Fh+LocalNetRootName]
0x14004d921  lea     rcx, [rbp+4Fh+CanonicalName]
0x14004d925  call    RxStripSessionPrefix
0x14004d92a  mov     rbx, [rbp+4Fh+NetRoot]
0x14004d92e  lea     rax, [r12+120h]
0x14004d936  mov     rdx, rbx; NetRoot
0x14004d939  mov     [rsp+28h], r12; RxConnectionId
0x14004d93e  lea     r9, [rbp+4Fh+LocalNetRootName]; LocalNetRootName
0x14004d942  mov     [rsp+0C0h+FilePath], rax; LockHoldingState
0x14004d947  lea     r8, [rbp+4Fh+CanonicalName]; CanonicalName
0x14004d94b  mov     rcx, r14; RxContext
0x14004d94e  call    RxCreateVNetRoot
0x14004d953  mov     rdi, rax
0x14004d956  test    rax, rax
0x14004d959  jz      loc_14004DAD9
0x14004d95f  mov     rcx, rax; Instance
0x14004d962  call    RxReference
0x14004d967  lea     r9, [rbp+4Fh+var_8C]; VirtualNetRoot
0x14004d96b  mov     r8, rdi; NetRoot
0x14004d96e  xor     edx, edx; SrvCall
0x14004d970  mov     rcx, r14; RxContext
0x14004d973  call    RxConstructNetRoot
  ... truncated ...
```
