# CClfsRequest::AuthenticateLogFile(_IRP *)

- ea: `0x140040444`
- end: `0x140040821`
- name: `?AuthenticateLogFile@CClfsRequest@@CAJPEAU_IRP@@@Z`
- size: `989`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140040ba8`

## callees

- `0x14000bd70`
- `0x140017f20`
- `0x140040444`
- `0x14005ed70`
- `0x14005fd18`
- `0x14005fdcc`
- `0x140061c00`
- `0x140061d00`
- `0x140062980`
- `0x140062a30`
- `0x1400632d4`
- `0x140075cd4`
- `0x1400787ec`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400407ff`
- `ntoskrnl!KeSetEvent` at `0x14007e8f6`
- `ntoskrnl!KeSetEvent` at `0x1400407ff`
- `ntoskrnl!KeSetEvent` at `0x14007e8f6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040601`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040601`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400407dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400407dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e8ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400405d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400405d4`

## pseudocode

```c
__int64 __fastcall CClfsRequest::AuthenticateLogFile(struct _IRP *a1)
{
  volatile signed __int32 *v2; // rsi
  struct _CLFS_CLIENT_CONTEXT *v3; // r12
  unsigned int *PoolWithTag; // r14
  struct _IRP *MasterIrp; // r10
  NTSTATUS v6; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned __int64 Options; // rcx
  struct _DEVICE_OBJECT *DeviceObject; // rbx
  wchar_t *v10; // r10
  __int64 v11; // r11
  __int64 v12; // rax
  wchar_t *v13; // rdx
  int v14; // ecx
  CClfsBaseFilePersisted *v15; // rax
  unsigned __int8 v16; // di
  union _CLS_LSN v17; // rbx
  unsigned int i; // edi
  struct _CLFS_CONTAINER_CONTEXT *v19; // r13
  CClfsAuthContainer *v20; // rcx
  struct _KEVENT *UserEvent; // rcx
  struct _CLFS_CONTAINER_CONTEXT *v23; // [rsp+58h] [rbp-C0h] BYREF
  struct _CLFS_CLIENT_CONTEXT *v24; // [rsp+60h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v25; // [rsp+68h] [rbp-B0h] BYREF
  int v26; // [rsp+78h] [rbp-A0h]
  unsigned int v27; // [rsp+7Ch] [rbp-9Ch]
  volatile signed __int32 *v28; // [rsp+80h] [rbp-98h]
  unsigned int *v29; // [rsp+88h] [rbp-90h]
  __int64 v30; // [rsp+90h] [rbp-88h]
  wchar_t *v31; // [rsp+98h] [rbp-80h]
  __int64 v32; // [rsp+A0h] [rbp-78h]
  __int64 v33; // [rsp+A8h] [rbp-70h]
  unsigned __int64 v34; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v35; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-50h]
  union _CLS_LSN v37; // [rsp+D0h] [rbp-48h]
  char v38; // [rsp+128h] [rbp+10h] BYREF
  unsigned int v39; // [rsp+130h] [rbp+18h] BYREF
  unsigned int v40; // [rsp+138h] [rbp+20h] BYREF

  *(_QWORD *)&v25.Length = 0;
  v25.Buffer = 0;
  v2 = 0;
  v28 = 0;
  v3 = 0;
  v24 = 0;
  v23 = 0;
  v39 = 0;
  v40 = 0;
  v34 = 0;
  PoolWithTag = 0;
  v29 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
  {
LABEL_2:
    v6 = -1073741592;
    goto LABEL_34;
  }
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( (unsigned int)Options >= 2 )
  {
    DeviceObject = CurrentStackLocation->FileObject->DeviceObject;
    if ( (int)RtlStringCbLengthW((const unsigned __int16 *)MasterIrp, Options, 0) < 0 )
      goto LABEL_2;
    v26 = 0;
    v25 = 0;
    v30 = 0;
    v12 = 0x7FFF;
    v32 = 0x7FFF;
    v13 = v10;
    v31 = v10;
    v14 = 0;
    while ( v12 && *v13 )
    {
      v13 = (wchar_t *)((char *)v13 + v11);
      v31 = v13;
      v32 = --v12;
    }
    if ( !v12 )
      v14 = -1073741811;
    v30 = v14 < 0 ? 0LL : 0x7FFF - v12;
    v26 = v14;
    if ( v14 < 0 )
      goto LABEL_2;
    v33 = 2 * v30;
    v25.Length = 2 * v30;
    v25.MaximumLength = v11 + 2 * v30;
    v25.Buffer = v10;
    if ( !(2 * (_WORD)v30) )
      goto LABEL_2;
    PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PagedPool, 0x1000u, 0x73666C43u);
    v29 = PoolWithTag;
    if ( PoolWithTag
      && ((v15 = (CClfsBaseFilePersisted *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceExtension)) == 0
        ? (v2 = 0)
        : (v2 = (volatile signed __int32 *)CClfsBaseFilePersisted::CClfsBaseFilePersisted(v15, DeviceObject)),
          (v28 = v2) != 0) )
    {
      _InterlockedIncrement(v2 + 2);
      v6 = CClfsBaseFilePersisted::OpenImage(
             (CClfsBaseFilePersisted *)v2,
             &v25,
             (const struct _CLFS_FILTER_CONTEXT *)&v35,
             0x2000000u,
             (unsigned __int8 *)&v38);
      if ( v6 >= 0 )
      {
        CClfsBaseFile::AcquireClientContext((CClfsBaseFile *)v2, 0, &v24);
        v3 = v24;
        if ( v24 )
        {
          v16 = (*((_BYTE *)v24 + 10) & 2) != 0;
          v37 = *(union _CLS_LSN *)((char *)v24 + 88);
          v17 = v37;
          CClfsBaseFile::ReleaseClientContext((CClfsBaseFile *)v2, &v24);
          v3 = 0;
          v24 = 0;
          v6 = CClfsBaseFilePersisted::LoadContainerQ(
                 (CClfsBaseFilePersisted *)v2,
                 PoolWithTag,
                 1024,
                 v16,
                 v38,
                 v17,
                 &v39,
                 &v40,
                 &v34);
          if ( v6 >= 0 )
          {
            for ( i = v39; ; ++i )
            {
              v27 = i;
              if ( i >= v40 )
                break;
              v6 = CClfsBaseFile::AcquireContainerContext((PERESOURCE *)v2, PoolWithTag[i & 0x3FF], &v23);
              if ( v6 < 0 )
                break;
              if ( !v23 )
                goto LABEL_25;
              v19 = v23;
              v20 = (CClfsAuthContainer *)*((_QWORD *)v23 + 3);
              if ( v20 )
              {
                CClfsAuthContainer::Close(v20);
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 + 3) + 8LL))(*((_QWORD *)v19 + 3));
                *((_QWORD *)v19 + 3) = 0;
              }
              CClfsBaseFile::ReleaseContainerContext((CClfsBaseFile *)v2, &v23);
              v23 = 0;
            }
          }
        }
        else
        {
LABEL_25:
          v6 = -1072037875;
        }
      }
    }
    else
    {
      v6 = -1073741670;
    }
  }
  else
  {
    v6 = -1073741306;
  }
LABEL_34:
  if ( v2 )
  {
    if ( v23 )
      CClfsBaseFile::ReleaseContainerContext((CClfsBaseFile *)v2, &v23);
    if ( v3 )
      CClfsBaseFile::ReleaseClientContext((CClfsBaseFile *)v2, &v24);
    CClfsBaseFilePersisted::CloseImage((CClfsBaseFilePersisted *)v2);
    CClfsBaseFile::Release((CClfsBaseFile *)v2);
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  a1->IoStatus.Status = v6;
  a1->IoStatus.Information = 0;
  UserEvent = a1->UserEvent;
  if ( UserEvent )
    KeSetEvent(UserEvent, 0, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140040444  mov     rax, rsp
0x140040447  mov     [rax+8], rcx
0x14004044b  push    rbx
0x14004044c  push    rsi
0x14004044d  push    rdi
0x14004044e  push    r12
0x140040450  push    r13
0x140040452  push    r14
0x140040454  push    r15
0x140040456  sub     rsp, 0E0h
0x14004045d  mov     r15, rcx
0x140040460  xor     r13d, r13d
0x140040463  mov     [rsp+118h+var_C8], r13d
0x140040468  mov     qword ptr [rsp+118h+var_B0.Length], r13
0x14004046d  mov     [rsp+118h+var_B0.Buffer], r13
0x140040472  mov     esi, r13d
0x140040475  mov     [rax-98h], r13
0x14004047c  mov     r12d, r13d
0x14004047f  mov     [rsp+118h+var_B8], r13
0x140040484  mov     [rsp+118h+var_C0], r13
0x140040489  mov     [rax+18h], r13d
0x14004048d  mov     [rax+20h], r13d
0x140040491  mov     [rax-68h], r13
0x140040495  mov     r14d, r13d
0x140040498  mov     [rax-90h], r13
0x14004049f  mov     [rax+10h], r13b
0x1400404a3  xorps   xmm0, xmm0
0x1400404a6  movdqu  xmmword ptr [rax-60h], xmm0
0x1400404ab  mov     [rax-50h], r13
0x1400404af  mov     r10, [rcx+18h]
0x1400404b3  test    r10, r10
0x1400404b6  jnz     short loc_1400404C6
0x1400404b8  mov     ebx, 0C00000E8h
0x1400404bd  mov     [rsp+118h+var_C8], ebx
0x1400404c1  jmp     loc_140040798
0x1400404c6  mov     rax, [rcx+0B8h]
0x1400404cd  mov     ecx, [rax+10h]
0x1400404d0  mov     r11d, 2
0x1400404d6  cmp     ecx, r11d
0x1400404d9  jnb     short loc_1400404E2
0x1400404db  mov     ebx, 0C0000206h
0x1400404e0  jmp     short loc_1400404BD
0x1400404e2  mov     rax, [rax+30h]
0x1400404e6  mov     rbx, [rax+8]
0x1400404ea  mov     rdx, rcx; unsigned __int64
0x1400404ed  xor     r8d, r8d; unsigned __int64 *
0x1400404f0  mov     rcx, r10; unsigned __int16 *
0x1400404f3  call    ?RtlStringCbLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400404f8  mov     [rsp+118h+var_C8], eax
0x1400404fc  test    eax, eax
0x1400404fe  js      short loc_1400404B8
0x140040500  mov     [rsp+118h+var_A0], r13d
0x140040505  movups  xmmword ptr [rsp+118h+var_B0.Length], xmm0
0x14004050a  mov     [rsp+118h+var_88], r13
0x140040512  lea     r9, [rsp+118h+var_88]
0x14004051a  mov     r8d, 7FFFh
0x140040520  mov     eax, r8d
0x140040523  mov     [rsp+118h+var_78], rax
0x14004052b  mov     rdx, r10
0x14004052e  mov     [rsp+118h+var_80], rdx
0x140040536  mov     ecx, r13d
0x140040539  test    rax, rax
0x14004053c  jz      short loc_14004055C
0x14004053e  cmp     [rdx], r13w
0x140040542  jz      short loc_14004055C
0x140040544  add     rdx, r11
0x140040547  mov     [rsp+118h+var_80], rdx
0x14004054f  dec     rax
0x140040552  mov     [rsp+118h+var_78], rax
0x14004055a  jmp     short loc_140040539
0x14004055c  mov     edx, 0C000000Dh
0x140040561  test    rax, rax
0x140040564  cmovz   ecx, edx
0x140040567  test    ecx, ecx
0x140040569  js      short loc_140040573
0x14004056b  sub     r8, rax
0x14004056e  mov     [r9], r8
0x140040571  jmp     short loc_140040576
0x140040573  mov     [r9], r13
0x140040576  mov     [rsp+118h+var_A0], ecx
0x14004057a  test    ecx, ecx
0x14004057c  js      short loc_1400405AC
0x14004057e  mov     [rsp+118h+var_70], r13
0x140040586  mov     rax, [rsp+118h+var_88]
0x14004058e  add     rax, rax
0x140040591  mov     [rsp+118h+var_70], rax
0x140040599  mov     [rsp+118h+var_B0.Length], ax
0x14004059e  add     ax, r11w
0x1400405a2  mov     [rsp+118h+var_B0.MaximumLength], ax
0x1400405a7  mov     [rsp+118h+var_B0.Buffer], r10
0x1400405ac  mov     [rsp+118h+var_C8], ecx
0x1400405b0  test    ecx, ecx
0x1400405b2  js      loc_1400404B8
0x1400405b8  cmp     [rsp+118h+var_B0.Length], r13w
0x1400405be  jz      loc_1400404B8
0x1400405c4  mov     edx, 1000h; NumberOfBytes
0x1400405c9  mov     ecx, 1; PoolType
0x1400405ce  mov     r8d, 73666C43h; Tag
0x1400405d4  call    cs:__imp_ExAllocatePoolWithTag
0x1400405db  nop     dword ptr [rax+rax+00h]
0x1400405e0  mov     r14, rax
0x1400405e3  mov     [rsp+118h+var_90], rax
0x1400405eb  test    rax, rax
0x1400405ee  jnz     short loc_1400405FA
0x1400405f0  mov     ebx, 0C000009Ah
0x1400405f5  jmp     loc_1400404BD
0x1400405fa  lea     rcx, WPP_MAIN_CB.DeviceExtension; Lookaside
0x140040601  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140040608  nop     dword ptr [rax+rax+00h]
0x14004060d  test    rax, rax
0x140040610  jz      short loc_140040622
0x140040612  mov     rdx, rbx; struct _DEVICE_OBJECT *
0x140040615  mov     rcx, rax; this
0x140040618  call    ??0CClfsBaseFilePersisted@@QEAA@PEAU_DEVICE_OBJECT@@@Z; CClfsBaseFilePersisted::CClfsBaseFilePersisted(_DEVICE_OBJECT *)
0x14004061d  mov     rsi, rax
0x140040620  jmp     short loc_140040625
0x140040622  mov     rsi, r13
0x140040625  mov     [rsp+118h+var_98], rsi
0x14004062d  test    rsi, rsi
0x140040630  jz      short loc_1400405F0
0x140040632  lock inc dword ptr [rsi+8]
0x140040636  lea     rax, [rsp+118h+arg_8]
0x14004063e  mov     [rsp+118h+var_F8], rax; unsigned __int8 *
0x140040643  mov     r9d, 2000000h; unsigned int
0x140040649  lea     r8, [rsp+118h+var_60]; struct _CLFS_FILTER_CONTEXT *
0x140040651  lea     rdx, [rsp+118h+var_B0]; struct _UNICODE_STRING *
0x140040656  mov     rcx, rsi; this
0x140040659  call    ?OpenImage@CClfsBaseFilePersisted@@QEAAJPEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@KAEAE@Z; CClfsBaseFilePersisted::OpenImage(_UNICODE_STRING *,_CLFS_FILTER_CONTEXT const &,ulong,uchar &)
0x14004065e  mov     ebx, eax
0x140040660  mov     [rsp+118h+var_C8], eax
0x140040664  test    eax, eax
0x140040666  js      loc_140040798
0x14004066c  lea     r8, [rsp+118h+var_B8]; struct _CLFS_CLIENT_CONTEXT **
0x140040671  xor     edx, edx; unsigned __int8
0x140040673  mov     rcx, rsi; this
0x140040676  call    ?AcquireClientContext@CClfsBaseFile@@QEAAJEPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::AcquireClientContext(uchar,_CLFS_CLIENT_CONTEXT * *)
0x14004067b  mov     r12, [rsp+118h+var_B8]
0x140040680  test    r12, r12
0x140040683  jnz     short loc_14004068F
0x140040685  mov     ebx, 0C01A000Dh
0x14004068a  jmp     loc_1400404BD
0x14004068f  mov     dil, [r12+0Ah]
0x140040694  shr     dil, 1
0x140040697  and     dil, 1
0x14004069b  mov     rbx, [r12+58h]
0x1400406a0  mov     [rsp+118h+var_48], rbx
0x1400406a8  lea     rdx, [rsp+118h+var_B8]; struct _CLFS_CLIENT_CONTEXT **
0x1400406ad  mov     rcx, rsi; this
0x1400406b0  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x1400406b5  mov     r12, r13
0x1400406b8  mov     [rsp+118h+var_B8], r13
0x1400406bd  lea     rax, [rsp+118h+var_68]
0x1400406c5  mov     [rsp+118h+var_D8], rax; unsigned __int64 *
0x1400406ca  lea     rax, [rsp+118h+arg_18]
0x1400406d2  mov     [rsp+118h+var_E0], rax; unsigned int *
0x1400406d7  lea     rax, [rsp+118h+arg_10]
0x1400406df  mov     [rsp+118h+var_E8], rax; unsigned int *
0x1400406e4  mov     qword ptr [rsp+118h+var_F0], rbx; union _CLS_LSN
0x1400406e9  mov     al, [rsp+118h+arg_8]
0x1400406f0  mov     byte ptr [rsp+118h+var_F8], al; char
0x1400406f4  mov     r9b, dil; unsigned __int8
0x1400406f7  mov     r8d, 400h; unsigned int
0x1400406fd  mov     rdx, r14; unsigned int *
0x140040700  mov     rcx, rsi; this
0x140040703  call    ?LoadContainerQ@CClfsBaseFilePersisted@@QEAAJQEAKKEET_CLS_LSN@@AEAK2AEA_K@Z; CClfsBaseFilePersisted::LoadContainerQ(ulong * const,ulong,uchar,uchar,_CLS_LSN,ulong &,ulong &,unsigned __int64 &)
0x140040708  mov     ebx, eax
0x14004070a  mov     [rsp+118h+var_C8], eax
0x14004070e  test    eax, eax
0x140040710  js      loc_140040798
0x140040716  mov     edi, [rsp+118h+arg_10]
0x14004071d  mov     [rsp+118h+var_9C], edi
0x140040721  cmp     edi, [rsp+118h+arg_18]
0x140040728  jnb     short loc_140040798
0x14004072a  mov     edx, edi
0x14004072c  and     edx, 3FFh
0x140040732  lea     r8, [rsp+118h+var_C0]; struct _CLFS_CONTAINER_CONTEXT **
0x140040737  mov     edx, [r14+rdx*4]; unsigned int
0x14004073b  mov     rcx, rsi; this
0x14004073e  call    ?AcquireContainerContext@CClfsBaseFile@@QEAAJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::AcquireContainerContext(ulong,_CLFS_CONTAINER_CONTEXT * *)
0x140040743  mov     ebx, eax
0x140040745  mov     [rsp+118h+var_C8], eax
0x140040749  test    eax, eax
0x14004074b  js      short loc_140040798
0x14004074d  cmp     [rsp+118h+var_C0], r13
0x140040752  jz      loc_140040685
0x140040758  mov     r13, [rsp+118h+var_C0]
0x14004075d  mov     rcx, [r13+18h]; this
0x140040761  test    rcx, rcx
0x140040764  jz      short loc_14004077F
0x140040766  call    ?Close@CClfsAuthContainer@@QEAAJXZ; CClfsAuthContainer::Close(void)
0x14004076b  mov     rcx, [r13+18h]
0x14004076f  mov     rax, [rcx]
0x140040772  mov     rax, [rax+8]
0x140040776  call    _guard_dispatch_icall
0x14004077b  mov     [r13+18h], r12
0x14004077f  lea     rdx, [rsp+118h+var_C0]; struct _CLFS_CONTAINER_CONTEXT **
0x140040784  mov     rcx, rsi; this
0x140040787  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x14004078c  xor     r13d, r13d
0x14004078f  mov     [rsp+118h+var_C0], r13
0x140040794  inc     edi
0x140040796  jmp     short loc_14004071D
0x140040798  test    rsi, rsi
0x14004079b  jz      short loc_1400407D3
0x14004079d  cmp     [rsp+118h+var_C0], r13
0x1400407a2  jz      short loc_1400407B1
0x1400407a4  lea     rdx, [rsp+118h+var_C0]; struct _CLFS_CONTAINER_CONTEXT **
0x1400407a9  mov     rcx, rsi; this
0x1400407ac  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x1400407b1  test    r12, r12
0x1400407b4  jz      short loc_1400407C3
0x1400407b6  lea     rdx, [rsp+118h+var_B8]; struct _CLFS_CLIENT_CONTEXT **
0x1400407bb  mov     rcx, rsi; this
0x1400407be  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x1400407c3  mov     rcx, rsi; this
0x1400407c6  call    ?CloseImage@CClfsBaseFilePersisted@@QEAAJXZ; CClfsBaseFilePersisted::CloseImage(void)
0x1400407cb  mov     rcx, rsi; this
0x1400407ce  call    ?Release@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::Release(void)
0x1400407d3  test    r14, r14
0x1400407d6  jz      short loc_1400407E9
0x1400407d8  xor     edx, edx; Tag
0x1400407da  mov     rcx, r14; P
0x1400407dd  call    cs:__imp_ExFreePoolWithTag
0x1400407e4  nop     dword ptr [rax+rax+00h]
0x1400407e9  mov     [r15+30h], ebx
0x1400407ed  mov     [r15+38h], r13
0x1400407f1  mov     rcx, [r15+50h]; Event
0x1400407f5  test    rcx, rcx
0x1400407f8  jz      short loc_14004080B
0x1400407fa  xor     r8d, r8d; Wait
0x1400407fd  xor     edx, edx; Increment
0x1400407ff  call    cs:__imp_KeSetEvent
0x140040806  nop     dword ptr [rax+rax+00h]
0x14004080b  mov     eax, ebx
0x14004080d  add     rsp, 0E0h
0x140040814  pop     r15
0x140040816  pop     r14
0x140040818  pop     r13
0x14004081a  pop     r12
0x14004081c  pop     rdi
0x14004081d  pop     rsi
0x14004081e  pop     rbx
0x14004081f  retn
0x14007e853  push    rbx
0x14007e855  push    rbp
0x14007e856  sub     rsp, 58h
0x14007e85a  mov     rbp, rdx
0x14007e85d  mov     rbx, [rbp+80h]
0x14007e864  test    rbx, rbx
0x14007e867  jz      short loc_14007E8AC
0x14007e869  cmp     qword ptr [rbp+58h], 0
0x14007e86e  jz      short loc_14007E87D
0x14007e870  lea     rdx, [rbp+58h]; struct _CLFS_CONTAINER_CONTEXT **
0x14007e874  mov     rcx, rbx; this
0x14007e877  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x14007e87c  nop
0x14007e87d  cmp     qword ptr [rbp+60h], 0
0x14007e882  jz      short loc_14007E891
0x14007e884  lea     rdx, [rbp+60h]; struct _CLFS_CLIENT_CONTEXT **
0x14007e888  mov     rcx, rbx; this
0x14007e88b  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x14007e890  nop
0x14007e891  mov     rcx, rbx; this
0x14007e894  call    ?CloseImage@CClfsBaseFilePersisted@@QEAAJXZ; CClfsBaseFilePersisted::CloseImage(void)
0x14007e899  mov     rcx, rbx; this
0x14007e89c  call    ?Release@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::Release(void)
0x14007e8a1  mov     qword ptr [rbp+80h], 0
0x14007e8ac  mov     rcx, [rbp+88h]; P
0x14007e8b3  test    rcx, rcx
0x14007e8b6  jz      short loc_14007E8D1
0x14007e8b8  xor     edx, edx; Tag
0x14007e8ba  call    cs:__imp_ExFreePoolWithTag
0x14007e8c1  nop     dword ptr [rax+rax+00h]
0x14007e8c6  mov     qword ptr [rbp+88h], 0
0x14007e8d1  mov     eax, [rbp+50h]
0x14007e8d4  mov     rcx, [rbp+120h]
0x14007e8db  mov     [rcx+30h], eax
0x14007e8de  mov     qword ptr [rcx+38h], 0
0x14007e8e6  cmp     qword ptr [rcx+50h], 0
0x14007e8eb  jz      short loc_14007E903
0x14007e8ed  xor     r8d, r8d; Wait
0x14007e8f0  xor     edx, edx; Increment
0x14007e8f2  mov     rcx, [rcx+50h]; Event
0x14007e8f6  call    cs:__imp_KeSetEvent
0x14007e8fd  nop     dword ptr [rax+rax+00h]
0x14007e902  nop
0x14007e903  add     rsp, 58h
0x14007e907  pop     rbp
0x14007e908  pop     rbx
0x14007e909  retn
```
