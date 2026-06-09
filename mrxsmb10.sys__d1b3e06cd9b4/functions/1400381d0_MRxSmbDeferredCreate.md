# MRxSmbDeferredCreate

- ea: `0x1400381d0`
- end: `0x140038682`
- name: `MRxSmbDeferredCreate`
- size: `1202`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140028a70`
- `0x140029170`
- `0x140029440`
- `0x140029910`
- `0x14002b980`
- `0x14002e3c0`
- `0x14002f120`
- `0x140030bb0`
- `0x140039390`
- `0x140042fd4`

## callees

- `0x140010768`
- `0x140010a74`
- `0x140036d40`
- `0x1400381d0`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140038590`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140038590`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14003857d`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14003857d`
- `ntoskrnl!KeSetEvent` at `0x140038539`
- `ntoskrnl!KeSetEvent` at `0x140038539`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003829d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003855d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400385e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003829d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003855d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400385e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038291`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038551`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400385dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038291`
- `ntoskrnl!ExReleaseResourceLite` at `0x140038551`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400385dc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140038260`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400384df`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140038260`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400384df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140038248`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400384ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140038248`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400384ca`
- `ntoskrnl!KeInitializeEvent` at `0x14003862e`
- `ntoskrnl!KeInitializeEvent` at `0x14003862e`
- `ntoskrnl!ExAllocatePool2` at `0x1400382b9`
- `ntoskrnl!ExAllocatePool2` at `0x1400382b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038459`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038475`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038459`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038475`
- `rdbss!RxAcquireSharedFcbResourceInMRx` at `0x14003865b`
- `rdbss!RxAcquireSharedFcbResourceInMRx` at `0x14003865b`
- `rdbss!RxWaitSync` at `0x140038611`
- `rdbss!RxWaitSync` at `0x140038611`
- `rdbss!RxInitializeContext` at `0x1400382e3`
- `rdbss!RxInitializeContext` at `0x1400382e3`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140038644`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140038644`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x140038602`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x140038602`

## pseudocode

```c
__int64 __fastcall MRxSmbDeferredCreate(__int64 a1)
{
  struct _MRX_FOBX_ *v1; // rdi
  struct _MRX_SRV_OPEN_ *Context2; // r15
  __int64 v4; // rbx
  int v5; // edi
  struct _MRX_FCB_ *v6; // r13
  __int64 **v7; // r14
  struct _RX_CONTEXT *Pool2; // rax
  struct _RX_CONTEXT *v9; // r12
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  struct _IO_STACK_LOCATION *v14; // rcx
  PMRXSHADOW_SRV_OPEN ShadowContext; // rax
  PFAST_IO_WRITE FastIoWrite; // rax
  __int64 v17; // r8
  __int64 *v18; // rbx
  __int64 *v19; // rdx
  __int64 v20; // r8
  __int64 *v21; // rax
  struct _KEVENT *v22; // rcx
  struct _ERESOURCE *Resource; // rcx
  BOOLEAN IsResourceAcquiredExclusiveLite; // r15
  ULONG IsResourceAcquiredSharedLite; // eax
  __int64 ***v26; // rcx
  ULONG v27; // ebx
  __int128 v29; // [rsp+40h] [rbp-20h] BYREF
  __int128 v30; // [rsp+50h] [rbp-10h]
  struct _MRX_FOBX_ *v31; // [rsp+A0h] [rbp+40h]
  __int64 v32; // [rsp+A8h] [rbp+48h]

  v1 = *(struct _MRX_FOBX_ **)(a1 + 64);
  v31 = v1;
  Context2 = (struct _MRX_SRV_OPEN_ *)v1->Context2;
  if ( Context2 )
    v4 = *(_QWORD *)&Context2->Flags;
  else
    v4 = 0;
  if ( *(_DWORD *)(v4 + 128) || ((__int64)Context2->Key & 0x100000) != 0 )
  {
    v32 = *(_QWORD *)(v4 + 16);
    if ( !v32 && (((__int64)Context2->Key & 4) != 0 || (*(_DWORD *)v4 & 0x400) != 0) )
    {
      return (unsigned int)-1073741528;
    }
    else
    {
      v6 = *(struct _MRX_FCB_ **)(a1 + 56);
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
      v7 = (__int64 **)(v4 + 136);
      if ( *(_BYTE *)(v4 + 133) )
      {
        Resource = v6->Header.Resource;
        v29 = 0;
        v30 = 0;
        IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(Resource);
        IsResourceAcquiredSharedLite = ExIsResourceAcquiredSharedLite(v6->Header.Resource);
        v26 = *(__int64 ****)(v4 + 144);
        v27 = IsResourceAcquiredSharedLite;
        *(_QWORD *)&v30 = a1;
        *((_QWORD *)&v29 + 1) = &v29;
        *(_QWORD *)&v29 = &v29;
        if ( *v26 != v7 )
LABEL_38:
          __fastfail(3u);
        *((_QWORD *)&v29 + 1) = v26;
        *(_QWORD *)&v29 = v7;
        *v26 = (__int64 **)&v29;
        v7[1] = (__int64 *)&v29;
        ExReleaseResourceLite(&s_SmbCeDbResource);
        KeLeaveCriticalRegion();
        if ( IsResourceAcquiredExclusiveLite || v27 )
          RxReleaseFcbResourceInMRx(0);
        RxWaitSync(a1);
        v5 = DWORD2(v30);
        KeInitializeEvent((PRKEVENT)(a1 + 384), SynchronizationEvent, 0);
        if ( IsResourceAcquiredExclusiveLite )
        {
          RxAcquireExclusiveFcbResourceInMRx(0);
        }
        else if ( v27 )
        {
          RxAcquireSharedFcbResourceInMRx(0);
        }
      }
      else
      {
        *(_BYTE *)(v4 + 133) = 1;
        *(_QWORD *)(v4 + 144) = v4 + 136;
        *v7 = (__int64 *)v7;
        ExReleaseResourceLite(&s_SmbCeDbResource);
        KeLeaveCriticalRegion();
        Pool2 = (struct _RX_CONTEXT *)ExAllocatePool2(64, 896, 2018667859);
        v9 = Pool2;
        if ( Pool2 )
        {
          RxInitializeContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 0, Pool2);
          v9->pFcb = v6;
          v9->pFobx = v1;
          v9->CurrentIrp = *(PIRP *)(a1 + 40);
          v13 = *(_QWORD *)(a1 + 40);
          if ( v13 )
            v14 = *(struct _IO_STACK_LOCATION **)(v13 + 184);
          else
            v14 = 0;
          v9->CurrentIrpSp = v14;
          LOBYTE(v9->RealDevice) = 0;
          v9->pRelevantSrvOpen = Context2;
          ShadowContext = Context2->ShadowContext;
          *(_QWORD *)&v9->TrackerHistory[0].Flags = ShadowContext;
          FastIoWrite = ShadowContext->FastIoWrite;
          v9->TrackerHistory[0].FileName = (PSZ)FastIoWrite;
          *(_QWORD *)&v9->TrackerHistory[0].AcquireRelease = *((_QWORD *)FastIoWrite + 4);
          LODWORD(v9->RdbssDbgExtension) = *(_DWORD *)(v32 + 88) | 0x80400002;
          WORD1(v9->TrackerHistory[4].FileName) = *(_WORD *)(v32 + 100);
          *((_OWORD *)&v9->9 + 7) = *(_OWORD *)v32;
          *((_OWORD *)&v9->9 + 8) = *(_OWORD *)(v32 + 16);
          *((_OWORD *)&v9->9 + 9) = *(_OWORD *)(v32 + 32);
          *((_OWORD *)&v9->9 + 10) = *(_OWORD *)(v32 + 48);
          *((_OWORD *)&v9->9 + 11) = *(_OWORD *)(v32 + 64);
          v9->Create.Password.Buffer = *(PWSTR *)(v32 + 80);
          v5 = MRxSmbCreate(v9, v10, v11, v12);
          if ( *(_DWORD *)(v4 + 128) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_qqqL(WPP_GLOBAL_Control->AttachedDevice, 24, v17, v6, v31, a1, v5);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_qqqL(WPP_GLOBAL_Control->AttachedDevice, 23, v17, v6, v31, a1, v5);
            }
            if ( v5 >= 0 )
              LODWORD(Context2->Key) &= ~0x100000u;
          }
          ExFreePoolWithTag(v9, 0);
        }
        else
        {
          v5 = -1073741670;
        }
        if ( ((__int64)Context2->Key & 0x404) != 0 )
        {
          ExFreePoolWithTag(*(PVOID *)(v4 + 16), 0);
          *(_QWORD *)(v4 + 16) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_Zq(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              (unsigned int)WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
              *(_QWORD *)(a1 + 56) + 360,
              v4);
          }
        }
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
        *(_BYTE *)(v4 + 133) = 0;
        v18 = *v7;
        while ( v18 != (__int64 *)v7 )
        {
          v19 = (__int64 *)*v18;
          if ( *(__int64 **)(*v18 + 8) != v18 )
            goto LABEL_38;
          v20 = *v19;
          if ( *(__int64 **)(*v19 + 8) != v19 )
            goto LABEL_38;
          v21 = v18;
          v18 = (__int64 *)*v18;
          *v21 = v20;
          *(_QWORD *)(v20 + 8) = v21;
          v22 = (struct _KEVENT *)v21[2];
          *((_DWORD *)v21 + 6) = v5;
          v22[5].Header.LockNV &= ~0x100000u;
          KeSetEvent(v22 + 16, 0, 0);
        }
        ExReleaseResourceLite(&s_SmbCeDbResource);
        KeLeaveCriticalRegion();
      }
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400381d0  mov     [rsp-38h+arg_10], rbx
0x1400381d5  push    rbp
0x1400381d6  push    rsi
0x1400381d7  push    rdi
0x1400381d8  push    r12
0x1400381da  push    r13
0x1400381dc  push    r14
0x1400381de  push    r15
0x1400381e0  mov     rbp, rsp
0x1400381e3  sub     rsp, 60h
0x1400381e7  mov     rdi, [rcx+40h]
0x1400381eb  mov     rsi, rcx
0x1400381ee  mov     [rbp+arg_0], rdi
0x1400381f2  mov     r15, [rdi+20h]
0x1400381f6  test    r15, r15
0x1400381f9  jnz     short loc_1400381FF
0x1400381fb  xor     ebx, ebx
0x1400381fd  jmp     short loc_140038203
0x1400381ff  mov     rbx, [r15+30h]
0x140038203  cmp     dword ptr [rbx+80h], 0
0x14003820a  jnz     short loc_14003821D
0x14003820c  test    dword ptr [r15+48h], 100000h
0x140038214  jnz     short loc_14003821D
0x140038216  xor     edi, edi
0x140038218  jmp     loc_140038667
0x14003821d  mov     rax, [rbx+10h]
0x140038221  mov     [rbp+arg_8], rax
0x140038225  test    rax, rax
0x140038228  jnz     short loc_140038244
0x14003822a  mov     eax, [r15+48h]
0x14003822e  test    al, 4
0x140038230  jnz     short loc_14003823A
0x140038232  test    dword ptr [rbx], 400h
0x140038238  jz      short loc_140038244
0x14003823a  mov     edi, 0C0000128h
0x14003823f  jmp     loc_140038667
0x140038244  mov     r13, [rcx+38h]
0x140038248  call    cs:__imp_KeEnterCriticalRegion
0x14003824f  nop     dword ptr [rax+rax+00h]
0x140038254  lea     r12, s_SmbCeDbResource
0x14003825b  mov     dl, 1; Wait
0x14003825d  mov     rcx, r12; Resource
0x140038260  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140038267  nop     dword ptr [rax+rax+00h]
0x14003826c  cmp     byte ptr [rbx+85h], 0
0x140038273  lea     r14, [rbx+88h]
0x14003827a  jnz     loc_14003856E
0x140038280  mov     byte ptr [rbx+85h], 1
0x140038287  mov     rcx, r12; Resource
0x14003828a  mov     [r14+8], r14
0x14003828e  mov     [r14], r14
0x140038291  call    cs:__imp_ExReleaseResourceLite
0x140038298  nop     dword ptr [rax+rax+00h]
0x14003829d  call    cs:__imp_KeLeaveCriticalRegion
0x1400382a4  nop     dword ptr [rax+rax+00h]
0x1400382a9  mov     edx, 380h
0x1400382ae  mov     ecx, 40h ; '@'
0x1400382b3  mov     r8d, 78526D53h
0x1400382b9  call    cs:__imp_ExAllocatePool2
0x1400382c0  nop     dword ptr [rax+rax+00h]
0x1400382c5  mov     r12, rax
0x1400382c8  test    rax, rax
0x1400382cb  jnz     short loc_1400382D7
0x1400382cd  mov     edi, 0C000009Ah
0x1400382d2  jmp     loc_140038465
0x1400382d7  mov     rdx, [rsi+50h]; RxDeviceObject
0x1400382db  mov     r9, r12; RxContext
0x1400382de  xor     r8d, r8d; InitialContextFlags
0x1400382e1  xor     ecx, ecx; Irp
0x1400382e3  call    cs:__imp_RxInitializeContext
0x1400382ea  nop     dword ptr [rax+rax+00h]
0x1400382ef  mov     [r12+38h], r13
0x1400382f4  mov     [r12+40h], rdi
0x1400382f9  mov     rax, [rsi+28h]
0x1400382fd  mov     [r12+28h], rax
0x140038302  mov     rax, [rsi+28h]
0x140038306  test    rax, rax
0x140038309  jz      short loc_140038314
0x14003830b  mov     rcx, [rax+0B8h]
0x140038312  jmp     short loc_140038316
0x140038314  xor     ecx, ecx
0x140038316  mov     [r12+30h], rcx
0x14003831b  mov     rcx, [rbp+arg_8]
0x14003831f  mov     byte ptr [r12+20h], 0
0x140038325  mov     [r12+48h], r15
0x14003832a  mov     rax, [r15+28h]
0x14003832e  mov     [r12+290h], rax
0x140038336  mov     rax, [rax+20h]
0x14003833a  mov     [r12+288h], rax
0x140038342  mov     rax, [rax+20h]
0x140038346  mov     [r12+280h], rax
0x14003834e  mov     eax, [rcx+58h]
0x140038351  or      eax, 80400002h
0x140038356  mov     [r12+78h], eax
0x14003835b  movzx   eax, word ptr [rcx+64h]
0x14003835f  mov     [r12+2EAh], ax
0x140038368  movups  xmm0, xmmword ptr [rcx]
0x14003836b  movups  xmmword ptr [r12+200h], xmm0
0x140038374  movups  xmm1, xmmword ptr [rcx+10h]
0x140038378  movups  xmmword ptr [r12+210h], xmm1
0x140038381  movups  xmm0, xmmword ptr [rcx+20h]
0x140038385  movups  xmmword ptr [r12+220h], xmm0
0x14003838e  movups  xmm1, xmmword ptr [rcx+30h]
0x140038392  movups  xmmword ptr [r12+230h], xmm1
0x14003839b  movups  xmm0, xmmword ptr [rcx+40h]
0x14003839f  movups  xmmword ptr [r12+240h], xmm0
0x1400383a8  movsd   xmm1, qword ptr [rcx+50h]
0x1400383ad  mov     rcx, r12; RxContext
0x1400383b0  movsd   qword ptr [r12+250h], xmm1
0x1400383ba  call    MRxSmbCreate
0x1400383bf  cmp     dword ptr [rbx+80h], 0
0x1400383c6  mov     edi, eax
0x1400383c8  jnz     short loc_140038415
0x1400383ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400383d1  lea     rax, WPP_GLOBAL_Control
0x1400383d8  cmp     rcx, rax
0x1400383db  jz      short loc_140038409
0x1400383dd  test    dword ptr [rcx+2Ch], 200h
0x1400383e4  jz      short loc_140038409
0x1400383e6  mov     rax, [rbp+arg_0]
0x1400383ea  mov     edx, 17h
0x1400383ef  mov     rcx, [rcx+18h]
0x1400383f3  mov     r9, r13
0x1400383f6  mov     [rsp+60h+var_30], edi
0x1400383fa  mov     [rsp+60h+var_38], rsi
0x1400383ff  mov     [rsp+60h+var_40], rax
0x140038404  call    WPP_SF_qqqL
0x140038409  test    edi, edi
0x14003840b  js      short loc_140038454
0x14003840d  btr     dword ptr [r15+48h], 14h
0x140038413  jmp     short loc_140038454
0x140038415  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003841c  lea     rax, WPP_GLOBAL_Control
0x140038423  cmp     rcx, rax
0x140038426  jz      short loc_140038454
0x140038428  test    dword ptr [rcx+2Ch], 200h
0x14003842f  jz      short loc_140038454
0x140038431  mov     rax, [rbp+arg_0]
0x140038435  mov     edx, 18h
0x14003843a  mov     rcx, [rcx+18h]
0x14003843e  mov     r9, r13
0x140038441  mov     [rsp+60h+var_30], edi
0x140038445  mov     [rsp+60h+var_38], rsi
0x14003844a  mov     [rsp+60h+var_40], rax
0x14003844f  call    WPP_SF_qqqL
0x140038454  xor     edx, edx; Tag
0x140038456  mov     rcx, r12; P
0x140038459  call    cs:__imp_ExFreePoolWithTag
0x140038460  nop     dword ptr [rax+rax+00h]
0x140038465  test    dword ptr [r15+48h], 404h
0x14003846d  jz      short loc_1400384CA
0x14003846f  mov     rcx, [rbx+10h]; P
0x140038473  xor     edx, edx; Tag
0x140038475  call    cs:__imp_ExFreePoolWithTag
0x14003847c  nop     dword ptr [rax+rax+00h]
0x140038481  mov     qword ptr [rbx+10h], 0
0x140038489  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140038490  lea     rax, WPP_GLOBAL_Control
0x140038497  cmp     rcx, rax
0x14003849a  jz      short loc_1400384CA
0x14003849c  test    dword ptr [rcx+2Ch], 400h
0x1400384a3  jz      short loc_1400384CA
0x1400384a5  mov     r9, [rsi+38h]
0x1400384a9  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400384b0  mov     rcx, [rcx+18h]
0x1400384b4  add     r9, 168h
0x1400384bb  mov     edx, 19h
0x1400384c0  mov     [rsp+60h+var_40], rbx
0x1400384c5  call    WPP_SF_Zq
0x1400384ca  call    cs:__imp_KeEnterCriticalRegion
0x1400384d1  nop     dword ptr [rax+rax+00h]
0x1400384d6  mov     dl, 1; Wait
0x1400384d8  lea     rcx, s_SmbCeDbResource; Resource
0x1400384df  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400384e6  nop     dword ptr [rax+rax+00h]
0x1400384eb  mov     byte ptr [rbx+85h], 0
0x1400384f2  mov     rbx, [r14]
0x1400384f5  jmp     short loc_140038545
0x1400384f7  mov     rdx, [rbx]
0x1400384fa  cmp     [rdx+8], rbx
0x1400384fe  jnz     loc_1400385BB
0x140038504  mov     r8, [rdx]
0x140038507  cmp     [r8+8], rdx
0x14003850b  jnz     loc_1400385BB
0x140038511  mov     rax, rbx
0x140038514  mov     rcx, rbx
0x140038517  mov     rbx, rdx
0x14003851a  xor     edx, edx; Increment
0x14003851c  mov     [rax], r8
0x14003851f  mov     [r8+8], rax
0x140038523  xor     r8d, r8d; Wait
0x140038526  mov     rcx, [rax+10h]
0x14003852a  mov     [rax+18h], edi
0x14003852d  btr     dword ptr [rcx+78h], 14h
0x140038532  add     rcx, 180h; Event
0x140038539  call    cs:__imp_KeSetEvent
0x140038540  nop     dword ptr [rax+rax+00h]
0x140038545  cmp     rbx, r14
0x140038548  jnz     short loc_1400384F7
0x14003854a  lea     rcx, s_SmbCeDbResource; Resource
0x140038551  call    cs:__imp_ExReleaseResourceLite
0x140038558  nop     dword ptr [rax+rax+00h]
0x14003855d  call    cs:__imp_KeLeaveCriticalRegion
0x140038564  nop     dword ptr [rax+rax+00h]
0x140038569  jmp     loc_140038667
0x14003856e  mov     rcx, [r13+8]; Resource
0x140038572  xorps   xmm0, xmm0
0x140038575  movups  [rbp+var_20], xmm0
0x140038579  movups  [rbp+var_10], xmm0
0x14003857d  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140038584  nop     dword ptr [rax+rax+00h]
0x140038589  mov     rcx, [r13+8]; Resource
0x14003858d  mov     r15b, al
0x140038590  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140038597  nop     dword ptr [rax+rax+00h]
0x14003859c  mov     rcx, [r14+8]
0x1400385a0  mov     ebx, eax
0x1400385a2  lea     rax, [rbp+var_20]
0x1400385a6  mov     qword ptr [rbp+var_10], rsi
0x1400385aa  mov     qword ptr [rbp+var_20+8], rax
0x1400385ae  lea     rax, [rbp+var_20]
0x1400385b2  mov     qword ptr [rbp+var_20], rax
0x1400385b6  cmp     [rcx], r14
0x1400385b9  jz      short loc_1400385C2
0x1400385bb  mov     ecx, 3
0x1400385c0  int     29h; Win8: RtlFailFast(ecx)
0x1400385c2  mov     qword ptr [rbp+var_20+8], rcx
0x1400385c6  lea     rax, [rbp+var_20]
0x1400385ca  mov     qword ptr [rbp+var_20], r14
0x1400385ce  mov     [rcx], rax
0x1400385d1  lea     rax, [rbp+var_20]
0x1400385d5  mov     rcx, r12; Resource
0x1400385d8  mov     [r14+8], rax
0x1400385dc  call    cs:__imp_ExReleaseResourceLite
0x1400385e3  nop     dword ptr [rax+rax+00h]
0x1400385e8  call    cs:__imp_KeLeaveCriticalRegion
0x1400385ef  nop     dword ptr [rax+rax+00h]
0x1400385f4  test    r15b, r15b
0x1400385f7  jnz     short loc_1400385FD
0x1400385f9  test    ebx, ebx
0x1400385fb  jz      short loc_14003860E
0x1400385fd  mov     rdx, r13
0x140038600  xor     ecx, ecx; Fcb
0x140038602  call    cs:__imp_RxReleaseFcbResourceInMRx
0x140038609  nop     dword ptr [rax+rax+00h]
0x14003860e  mov     rcx, rsi
0x140038611  call    cs:__imp_RxWaitSync
0x140038618  nop     dword ptr [rax+rax+00h]
0x14003861d  mov     edi, dword ptr [rbp+var_10+8]
0x140038620  lea     rcx, [rsi+180h]; Event
0x140038627  xor     r8d, r8d; State
0x14003862a  lea     edx, [r8+1]; Type
0x14003862e  call    cs:__imp_KeInitializeEvent
0x140038635  nop     dword ptr [rax+rax+00h]
0x14003863a  test    r15b, r15b
0x14003863d  jz      short loc_140038652
0x14003863f  mov     rdx, r13
0x140038642  xor     ecx, ecx; Fcb
0x140038644  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x14003864b  nop     dword ptr [rax+rax+00h]
0x140038650  jmp     short loc_140038667
0x140038652  test    ebx, ebx
0x140038654  jz      short loc_140038667
0x140038656  mov     rdx, r13
0x140038659  xor     ecx, ecx; Fcb
0x14003865b  call    cs:__imp_RxAcquireSharedFcbResourceInMRx
0x140038662  nop     dword ptr [rax+rax+00h]
0x140038667  mov     rbx, [rsp+60h+arg_10]
0x14003866f  mov     eax, edi
0x140038671  add     rsp, 60h
0x140038675  pop     r15
0x140038677  pop     r14
0x140038679  pop     r13
0x14003867b  pop     r12
0x14003867d  pop     rdi
0x14003867e  pop     rsi
0x14003867f  pop     rbp
0x140038680  retn
```
