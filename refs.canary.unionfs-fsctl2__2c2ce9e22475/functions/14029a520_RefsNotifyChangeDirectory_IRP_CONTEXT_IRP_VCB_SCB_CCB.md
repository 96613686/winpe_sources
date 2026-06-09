# RefsNotifyChangeDirectory(_IRP_CONTEXT *,_IRP *,_VCB *,_SCB *,_CCB *)

- ea: `0x14029a520`
- end: `0x14029a8ed`
- name: `?RefsNotifyChangeDirectory@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_VCB@@PEAU_SCB@@PEAU_CCB@@@Z`
- size: `973`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _IRP *@<rdx>, struct _VCB *@<r8>, struct _SCB *@<r9>, struct _CCB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140312090`

## callees

- `0x140041b40`
- `0x140081670`
- `0x14008c400`
- `0x14008dbd0`
- `0x14008e360`
- `0x1400ca788`
- `0x14029a520`
- `0x14031ac80`
- `0x14031c8e0`

## import_xrefs

- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x14029a84f`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x14029a84f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14029a6bf`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14029a761`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14029a6bf`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14029a761`
- `ntoskrnl!PsIsThreadImpersonating` at `0x14029a70b`
- `ntoskrnl!PsIsThreadImpersonating` at `0x14029a70b`
- `ntoskrnl!SeTokenIsAdmin` at `0x14029a77e`
- `ntoskrnl!SeTokenIsAdmin` at `0x14029a77e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14029a7b3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14029a7b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029a7c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343e21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029a7c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140343e21`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029a6a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029a745`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029a6a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029a745`

## pseudocode

```c
__int64 __fastcall RefsNotifyChangeDirectory(
        struct _IRP_CONTEXT *a1,
        struct _IRP *a2,
        struct _VCB *a3,
        struct _SCB *a4,
        struct _CCB *FsContext)
{
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rbx
  BOOLEAN (__stdcall *TraverseCallback)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT); // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  BOOLEAN WatchTree; // r15
  unsigned int v13; // r8d
  __int64 v14; // rcx
  unsigned int v15; // r8d
  PACCESS_TOKEN ClientToken; // rcx
  int v17; // ecx
  ULONG CompletionFilter; // [rsp+C8h] [rbp+10h]

  SubjectContext = 0;
  TraverseCallback = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CompletionFilter = CurrentStackLocation->Parameters.Create.Options;
  WatchTree = CurrentStackLocation->Flags & 1;
  *((_QWORD *)a1 + 1) |= 1uLL;
  RefsAcquireSharedVcb(a1, a3, 1u);
  v14 = *((_QWORD *)a4 + 17);
  if ( !*(_DWORD *)(v14 + 176) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids, 3221225558LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741738, a1, "DirCtrl.c", 0x64Du);
    RefsRaiseStatusInternal(a1, -1073741738, v13);
  }
  if ( !RefsIsFileOpen((const struct _FCB *)v14) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids, 3221225768LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528, a1, "DirCtrl.c", 0x657u);
    RefsRaiseStatusInternal(a1, -1073741528, v15);
  }
  if ( WatchTree )
  {
    if ( (*((_DWORD *)FsContext + 1) & 0x80u) != 0 )
    {
      SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                             (POOL_TYPE)(PoolType | 0x10),
                                                             0x20u,
                                                             0x64466552u);
      SeCaptureSubjectContext(SubjectContext);
      TraverseCallback = (BOOLEAN (__stdcall *)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT))RefsNotifyTraverseCheck;
    }
    if ( byte_1402618D8 )
    {
      if ( !_bittest16((const signed __int16 *)FsContext + 44, 9u)
        && ((unsigned __int8)PsIsThreadImpersonating(KeGetCurrentThread())
         || RefsEffectiveMode(a2, a2->Tail.Overlay.CurrentStackLocation) == 1) )
      {
        if ( !SubjectContext )
        {
          SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                                 (POOL_TYPE)(PoolType | 0x10),
                                                                 0x20u,
                                                                 0x64466552u);
          SeCaptureSubjectContext(SubjectContext);
        }
        ClientToken = SubjectContext->ClientToken;
        if ( !SubjectContext->ClientToken )
          ClientToken = SubjectContext->PrimaryToken;
        if ( !SeTokenIsAdmin(ClientToken) )
          TraverseCallback = (BOOLEAN (__stdcall *)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT))RefsNotifyTraverseCheckEx;
      }
      if ( !TraverseCallback && SubjectContext )
      {
        SeReleaseSubjectContext(SubjectContext);
        ExFreePoolWithTag(SubjectContext, 0);
        SubjectContext = 0;
      }
    }
  }
  v17 = *((_DWORD *)FsContext + 1);
  if ( (v17 & 0x800000) == 0 )
  {
    *((_DWORD *)FsContext + 1) = v17 | 0x800000;
    _InterlockedIncrement((volatile signed __int32 *)a3 + 354);
  }
  FsRtlNotifyFilterChangeDirectory(
    *((PNOTIFY_SYNC *)a3 + 108),
    (PLIST_ENTRY)a3 + 53,
    FsContext,
    (PSTRING)((char *)a4 + 392),
    WatchTree,
    0,
    CompletionFilter,
    a2,
    TraverseCallback,
    SubjectContext,
    0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids, 259);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(259, 0, "DirCtrl.c", 0x6BFu);
  RefsReleaseVcb(a1, a3);
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, 0, 0);
  return 259;
}

```

## disassembly

```asm
0x14029a520  mov     rax, rsp
0x14029a523  mov     [rax+18h], r8
0x14029a527  mov     [rax+8], rcx
0x14029a52b  push    rbx
0x14029a52c  push    rsi
0x14029a52d  push    rdi
0x14029a52e  push    r12
0x14029a530  push    r13
0x14029a532  push    r14
0x14029a534  push    r15
0x14029a536  sub     rsp, 80h
0x14029a53d  mov     r12, r9
0x14029a540  mov     r14, r8
0x14029a543  mov     r13, rdx
0x14029a546  mov     rdi, rcx
0x14029a549  xor     ebx, ebx
0x14029a54b  mov     [rax-50h], rbx
0x14029a54f  xor     esi, esi
0x14029a551  mov     [rax-58h], bl
0x14029a554  mov     [rax-57h], bl
0x14029a557  mov     rax, [rdx+0B8h]
0x14029a55e  mov     ecx, [rax+10h]
0x14029a561  mov     [rsp+0B8h+arg_8], ecx
0x14029a568  mov     r15b, [rax+2]
0x14029a56c  and     r15b, 1
0x14029a570  or      qword ptr [rdi+8], 1
0x14029a575  mov     r8b, 1; unsigned __int8
0x14029a578  mov     rdx, r14; struct _VCB *
0x14029a57b  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14029a57e  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x14029a583  nop
0x14029a584  mov     rcx, [r12+88h]
0x14029a58c  cmp     [rcx+0B0h], esi
0x14029a592  jnz     short loc_14029A600
0x14029a594  lea     rax, WPP_GLOBAL_Control
0x14029a59b  mov     rcx, cs:WPP_GLOBAL_Control
0x14029a5a2  cmp     rcx, rax
0x14029a5a5  jz      short loc_14029A5CF
0x14029a5a7  test    dword ptr [rcx+2Ch], 100h
0x14029a5ae  jz      short loc_14029A5CF
0x14029a5b0  cmp     byte ptr [rcx+29h], 4
0x14029a5b4  jb      short loc_14029A5CF
0x14029a5b6  lea     edx, [rbx+1Ah]
0x14029a5b9  mov     r9d, 0C0000056h
0x14029a5bf  lea     r8, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids
0x14029a5c6  mov     rcx, [rcx+18h]
0x14029a5ca  call    WPP_SF_d
0x14029a5cf  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14029a5d5  test    al, al
0x14029a5d7  jz      short loc_14029A5F3
0x14029a5d9  mov     r9d, 64Dh; unsigned int
0x14029a5df  lea     r8, aDirctrlC; "DirCtrl.c"
0x14029a5e6  mov     rdx, rdi; struct _IRP_CONTEXT *
0x14029a5e9  mov     ecx, 0C0000056h; Status
0x14029a5ee  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14029a5f3  mov     edx, 0C0000056h; int
0x14029a5f8  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14029a5fb  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14029a600  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x14029a605  test    al, al
0x14029a607  jnz     short loc_14029A677
0x14029a609  lea     rax, WPP_GLOBAL_Control
0x14029a610  mov     rcx, cs:WPP_GLOBAL_Control
0x14029a617  cmp     rcx, rax
0x14029a61a  jz      short loc_14029A646
0x14029a61c  test    dword ptr [rcx+2Ch], 100h
0x14029a623  jz      short loc_14029A646
0x14029a625  cmp     byte ptr [rcx+29h], 4
0x14029a629  jb      short loc_14029A646
0x14029a62b  mov     edx, 1Bh
0x14029a630  mov     r9d, 0C0000128h
0x14029a636  lea     r8, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids
0x14029a63d  mov     rcx, [rcx+18h]
0x14029a641  call    WPP_SF_d
0x14029a646  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14029a64c  test    al, al
0x14029a64e  jz      short loc_14029A66A
0x14029a650  mov     r9d, 657h; unsigned int
0x14029a656  lea     r8, aDirctrlC; "DirCtrl.c"
0x14029a65d  mov     rdx, rdi; struct _IRP_CONTEXT *
0x14029a660  mov     ecx, 0C0000128h; Status
0x14029a665  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14029a66a  mov     edx, 0C0000128h; int
0x14029a66f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14029a672  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14029a677  test    r15b, r15b
0x14029a67a  jz      loc_14029A7DB
0x14029a680  mov     rax, [rsp+0B8h+FsContext]
0x14029a688  mov     ecx, [rax+4]
0x14029a68b  test    cl, cl
0x14029a68d  jns     short loc_14029A6DC
0x14029a68f  mov     ecx, cs:PoolType
0x14029a695  or      ecx, 10h; PoolType
0x14029a698  mov     edx, 20h ; ' '; NumberOfBytes
0x14029a69d  mov     r8d, 64466552h; Tag
0x14029a6a3  call    cs:__imp_ExAllocatePoolWithTag
0x14029a6aa  nop     dword ptr [rax+rax+00h]
0x14029a6af  mov     rbx, rax
0x14029a6b2  mov     [rsp+0B8h+var_50], rax
0x14029a6b7  mov     [rsp+0B8h+var_58], 1
0x14029a6bc  mov     rcx, rax; SubjectContext
0x14029a6bf  call    cs:__imp_SeCaptureSubjectContext
0x14029a6c6  nop     dword ptr [rax+rax+00h]
0x14029a6cb  mov     [rsp+0B8h+var_58], 0
0x14029a6d0  lea     rsi, ?RefsNotifyTraverseCheck@@YAEPEAX0PEAU_SECURITY_SUBJECT_CONTEXT@@@Z; RefsNotifyTraverseCheck(void *,void *,_SECURITY_SUBJECT_CONTEXT *)
0x14029a6d7  mov     [rsp+0B8h+var_48], rsi
0x14029a6dc  mov     [rsp+0B8h+var_58], 0
0x14029a6e1  cmp     cs:byte_1402618D8, 0
0x14029a6e8  jz      loc_14029A7DB
0x14029a6ee  mov     rax, [rsp+0B8h+FsContext]
0x14029a6f6  bt      word ptr [rax+58h], 9
0x14029a6fc  jb      loc_14029A79C
0x14029a702  mov     rcx, gs:188h
0x14029a70b  call    cs:__imp_PsIsThreadImpersonating
0x14029a712  nop     dword ptr [rax+rax+00h]
0x14029a717  test    al, al
0x14029a719  jnz     short loc_14029A72E
0x14029a71b  mov     rdx, [r13+0B8h]; struct _IO_STACK_LOCATION *
0x14029a722  mov     rcx, r13; struct _IRP *
0x14029a725  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x14029a72a  cmp     al, 1
0x14029a72c  jnz     short loc_14029A79C
0x14029a72e  test    rbx, rbx
0x14029a731  jnz     short loc_14029A772
0x14029a733  mov     ecx, cs:PoolType
0x14029a739  or      ecx, 10h; PoolType
0x14029a73c  lea     edx, [rbx+20h]; NumberOfBytes
0x14029a73f  mov     r8d, 64466552h; Tag
0x14029a745  call    cs:__imp_ExAllocatePoolWithTag
0x14029a74c  nop     dword ptr [rax+rax+00h]
0x14029a751  mov     rbx, rax
0x14029a754  mov     [rsp+0B8h+var_50], rax
0x14029a759  mov     [rsp+0B8h+var_58], 1
0x14029a75e  mov     rcx, rax; SubjectContext
0x14029a761  call    cs:__imp_SeCaptureSubjectContext
0x14029a768  nop     dword ptr [rax+rax+00h]
0x14029a76d  mov     [rsp+0B8h+var_58], 0
0x14029a772  mov     rcx, [rbx]
0x14029a775  test    rcx, rcx
0x14029a778  jnz     short loc_14029A77E
0x14029a77a  mov     rcx, [rbx+10h]; Token
0x14029a77e  call    cs:__imp_SeTokenIsAdmin
0x14029a785  nop     dword ptr [rax+rax+00h]
0x14029a78a  lea     rcx, ?RefsNotifyTraverseCheckEx@@YAEPEAX0PEAU_SECURITY_SUBJECT_CONTEXT@@@Z; RefsNotifyTraverseCheckEx(void *,void *,_SECURITY_SUBJECT_CONTEXT *)
0x14029a791  test    al, al
0x14029a793  cmovz   rsi, rcx
0x14029a797  mov     [rsp+0B8h+var_48], rsi
0x14029a79c  mov     [rsp+0B8h+var_58], 0
0x14029a7a1  test    rsi, rsi
0x14029a7a4  jnz     short loc_14029A7DB
0x14029a7a6  mov     [rsp+0B8h+var_58], sil
0x14029a7ab  test    rbx, rbx
0x14029a7ae  jz      short loc_14029A7DB
0x14029a7b0  mov     rcx, rbx; SubjectContext
0x14029a7b3  call    cs:__imp_SeReleaseSubjectContext
0x14029a7ba  nop     dword ptr [rax+rax+00h]
0x14029a7bf  xor     edx, edx; Tag
0x14029a7c1  mov     rcx, rbx; P
0x14029a7c4  call    cs:__imp_ExFreePoolWithTag
0x14029a7cb  nop     dword ptr [rax+rax+00h]
0x14029a7d0  xor     ebx, ebx
0x14029a7d2  mov     [rsp+0B8h+var_50], rbx
0x14029a7d7  mov     [rsp+0B8h+var_58], bl
0x14029a7db  mov     rdx, [rsp+0B8h+FsContext]
0x14029a7e3  mov     ecx, [rdx+4]
0x14029a7e6  mov     r8d, 800000h
0x14029a7ec  test    r8d, ecx
0x14029a7ef  jnz     short loc_14029A804
0x14029a7f1  or      ecx, r8d
0x14029a7f4  mov     [rdx+4], ecx
0x14029a7f7  lock inc dword ptr [r14+588h]
0x14029a7ff  mov     [rsp+0B8h+var_57], 1
0x14029a804  lea     r9, [r12+188h]; FullDirectoryName
0x14029a80c  lea     rdx, [r14+350h]; NotifyList
0x14029a813  mov     [rsp+0B8h+FilterCallback], 0; FilterCallback
0x14029a81c  mov     [rsp+0B8h+SubjectContext], rbx; SubjectContext
0x14029a821  mov     [rsp+0B8h+TraverseCallback], rsi; TraverseCallback
0x14029a826  mov     [rsp+0B8h+NotifyIrp], r13; NotifyIrp
0x14029a82b  mov     eax, [rsp+0B8h+arg_8]
0x14029a832  mov     [rsp+0B8h+CompletionFilter], eax; CompletionFilter
0x14029a836  mov     [rsp+0B8h+IgnoreBuffer], 0; IgnoreBuffer
0x14029a83b  mov     [rsp+0B8h+WatchTree], r15b; WatchTree
0x14029a840  mov     r8, [rsp+0B8h+FsContext]; FsContext
0x14029a848  mov     rcx, [r14+360h]; NotifySync
0x14029a84f  call    cs:__imp_FsRtlNotifyFilterChangeDirectory
0x14029a856  nop     dword ptr [rax+rax+00h]
0x14029a85b  lea     rax, WPP_GLOBAL_Control
0x14029a862  mov     rcx, cs:WPP_GLOBAL_Control
0x14029a869  cmp     rcx, rax
0x14029a86c  jz      short loc_14029A898
0x14029a86e  test    dword ptr [rcx+2Ch], 100h
0x14029a875  jz      short loc_14029A898
0x14029a877  cmp     byte ptr [rcx+29h], 5
0x14029a87b  jb      short loc_14029A898
0x14029a87d  mov     edx, 1Ch
0x14029a882  mov     r9d, 103h
0x14029a888  lea     r8, WPP_e26d908e4ffc32e449ff298aa90a7990_Traceguids
0x14029a88f  mov     rcx, [rcx+18h]
0x14029a893  call    WPP_SF_d
0x14029a898  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14029a89e  test    al, al
0x14029a8a0  jz      short loc_14029A8BC
0x14029a8a2  mov     r9d, 6BFh; unsigned int
0x14029a8a8  lea     r8, aDirctrlC; "DirCtrl.c"
0x14029a8af  xor     edx, edx; struct _IRP_CONTEXT *
0x14029a8b1  mov     ecx, 103h; Status
0x14029a8b6  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14029a8bb  nop
0x14029a8bc  mov     rdx, r14; struct _VCB *
0x14029a8bf  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14029a8c2  call    ?RefsReleaseVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z; RefsReleaseVcb(_IRP_CONTEXT *,_VCB *)
0x14029a8c7  xor     r8d, r8d; Status
0x14029a8ca  xor     edx, edx; Irp
0x14029a8cc  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14029a8cf  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14029a8d4  mov     eax, 103h
0x14029a8d9  add     rsp, 80h
0x14029a8e0  pop     r15
0x14029a8e2  pop     r14
0x14029a8e4  pop     r13
0x14029a8e6  pop     r12
0x14029a8e8  pop     rdi
0x14029a8e9  pop     rsi
0x14029a8ea  pop     rbx
0x14029a8eb  retn
0x140343dd2  push    rbx
0x140343dd4  push    rbp
0x140343dd5  push    rdi
0x140343dd6  sub     rsp, 60h
0x140343dda  mov     rbp, rdx
0x140343ddd  movzx   ebx, cl
0x140343de0  mov     rdi, [rbp+0D0h]
0x140343de7  mov     rdx, rdi; struct _VCB *
0x140343dea  mov     rcx, [rbp+0C0h]; struct _IRP_CONTEXT *
0x140343df1  call    ?RefsReleaseVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z; RefsReleaseVcb(_IRP_CONTEXT *,_VCB *)
0x140343df6  mov     eax, ebx
0x140343df8  test    bl, bl
0x140343dfa  jz      short loc_140343E2E
0x140343dfc  cmp     byte ptr [rbp+61h], 0
0x140343e00  jz      short loc_140343E15
0x140343e02  mov     rax, [rbp+0E0h]
0x140343e09  btr     dword ptr [rax+4], 17h
0x140343e0e  lock dec dword ptr [rdi+588h]
0x140343e15  cmp     byte ptr [rbp+60h], 0
0x140343e19  jz      short loc_140343E2E
0x140343e1b  xor     edx, edx; Tag
0x140343e1d  mov     rcx, [rbp+68h]; P
0x140343e21  call    cs:__imp_ExFreePoolWithTag
0x140343e28  nop     dword ptr [rax+rax+00h]
0x140343e2d  nop
0x140343e2e  add     rsp, 60h
0x140343e32  pop     rdi
0x140343e33  pop     rbp
0x140343e34  pop     rbx
0x140343e35  retn
```
