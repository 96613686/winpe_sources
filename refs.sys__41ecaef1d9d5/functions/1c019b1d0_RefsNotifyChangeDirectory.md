# RefsNotifyChangeDirectory

- ea: `0x1c019b1d0`
- end: `0x1c019b662`
- name: `RefsNotifyChangeDirectory`
- size: `1170`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID FsContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1c017b25c`

## callees

- `0x1c0005768`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c015d78c`
- `0x1c016154c`
- `0x1c019b1d0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c019b278`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c019b388`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c019b278`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c019b388`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c019b354`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c019b64c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c019b354`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c019b64c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c019b4d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c019b615`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c019b4d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c019b615`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1c019b45e`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1c019b45e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c019b294`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c019b3a4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c019b294`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c019b3a4`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1c019b2ed`
- `ntoskrnl!PsIsThreadImpersonating` at `0x1c019b2ed`
- `ntoskrnl!SeTokenIsAdmin` at `0x1c019b3c1`
- `ntoskrnl!SeTokenIsAdmin` at `0x1c019b3c1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c019b343`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c019b343`

## pseudocode

```c
void __fastcall RefsNotifyChangeDirectory(__int64 a1, IRP *a2, __int64 a3, __int64 a4, _DWORD *FsContext)
{
  __int64 v6; // rdi
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG CompletionFilter; // r12d
  BOOLEAN WatchTree; // r15
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  PACCESS_TOKEN ClientToken; // rcx
  BOOLEAN IsAdmin; // al
  __int64 (__fastcall *v18)(); // rcx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rbp
  char v22; // cl
  char v23; // bl
  __int64 v24; // rdi
  struct _SECURITY_SUBJECT_CONTEXT *v25; // [rsp+68h] [rbp-50h]
  BOOLEAN (__stdcall *TraverseCallback)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT); // [rsp+70h] [rbp-48h]

  v6 = a3;
  SubjectContext = 0;
  v25 = 0;
  TraverseCallback = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CompletionFilter = CurrentStackLocation->Parameters.Create.Options;
  WatchTree = CurrentStackLocation->Flags & 1;
  *(_DWORD *)(a1 + 8) |= 1u;
  LOBYTE(a3) = 1;
  RefsAcquireSharedVcb(a1, v6, a3, a4);
  v14 = *(_QWORD *)(a4 + 120);
  if ( *(_WORD *)(v14 + 172) )
  {
    if ( (unsigned __int8)RefsIsFileOpen(v14, v13, 0) )
    {
      if ( WatchTree )
      {
        if ( (FsContext[1] & 0x80u) != 0 )
        {
          SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag((POOL_TYPE)17, 0x20u, 0x64466552u);
          v25 = SubjectContext;
          SeCaptureSubjectContext(SubjectContext);
          TraverseCallback = (BOOLEAN (__stdcall *)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT))RefsNotifyTraverseCheck;
        }
        if ( byte_1C012E6D4 )
        {
          if ( (FsContext[22] & 0x200) == 0 )
          {
            if ( (unsigned __int8)PsIsThreadImpersonating()
              || (unsigned __int8)RefsEffectiveMode(a2, a2->Tail.Overlay.CurrentStackLocation, v15) == 1 )
            {
              SubjectContext = v25;
              if ( !v25 )
              {
                SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                                       (POOL_TYPE)17,
                                                                       0x20u,
                                                                       0x64466552u);
                v25 = SubjectContext;
                SeCaptureSubjectContext(SubjectContext);
              }
              ClientToken = SubjectContext->ClientToken;
              if ( !SubjectContext->ClientToken )
                ClientToken = SubjectContext->PrimaryToken;
              IsAdmin = SeTokenIsAdmin(ClientToken);
              v18 = (__int64 (__fastcall *)())TraverseCallback;
              if ( !IsAdmin )
                v18 = RefsNotifyTraverseCheckEx;
              TraverseCallback = (BOOLEAN (__stdcall *)(PVOID, PVOID, PSECURITY_SUBJECT_CONTEXT))v18;
            }
            else
            {
              SubjectContext = v25;
            }
          }
          if ( !TraverseCallback && SubjectContext )
          {
            SeReleaseSubjectContext(SubjectContext);
            ExFreePoolWithTag(SubjectContext, 0);
            SubjectContext = 0;
            v25 = 0;
          }
        }
      }
      v19 = FsContext[1];
      if ( (v19 & 0x800000) == 0 )
      {
        FsContext[1] = v19 | 0x800000;
        _InterlockedIncrement((volatile signed __int32 *)(v6 + 1528));
        SubjectContext = v25;
      }
      FsRtlNotifyFilterChangeDirectory(
        *(PNOTIFY_SYNC *)(v6 + 824),
        (PLIST_ENTRY)(v6 + 808),
        FsContext,
        (PSTRING)(a4 + 360),
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
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_fc5bf5604c2538136cf1d0307679aff8_Traceguids, 259);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(259);
      ExReleaseResourceLite((PERESOURCE)(v6 + 1424));
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(0);
      RefsExtendedCompleteRequestInternal(a1, 0, 0);
      return;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_fc5bf5604c2538136cf1d0307679aff8_Traceguids, 3221225558LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741738);
    RefsRaiseStatusInternal(a1, 3221225558LL);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_fc5bf5604c2538136cf1d0307679aff8_Traceguids, 3221225768LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741528);
  RefsRaiseStatusInternal(a1, 3221225768LL);
  __debugbreak();
  v21 = v20;
  v23 = v22;
  *(_BYTE *)(v20 + 98) = v22;
  v24 = *(_QWORD *)(v20 + 208);
  ExReleaseResourceLite((PERESOURCE)(v24 + 1424));
  if ( v23 )
  {
    if ( *(_BYTE *)(v21 + 97) )
    {
      *(_DWORD *)(*(_QWORD *)(v21 + 224) + 4LL) &= ~0x800000u;
      _InterlockedDecrement((volatile signed __int32 *)(v24 + 1528));
    }
    if ( *(_BYTE *)(v21 + 96) )
      ExFreePoolWithTag(*(PVOID *)(v21 + 104), 0);
  }
}

```

## disassembly

```asm
0x1c019b1d0  mov     r11, rsp
0x1c019b1d3  mov     [r11+18h], r8
0x1c019b1d7  mov     [r11+10h], rdx
0x1c019b1db  push    rbx
0x1c019b1dc  push    rsi
0x1c019b1dd  push    rdi
0x1c019b1de  push    r12
0x1c019b1e0  push    r13
0x1c019b1e2  push    r14
0x1c019b1e4  push    r15
0x1c019b1e6  sub     rsp, 80h
0x1c019b1ed  mov     r13, r9
0x1c019b1f0  mov     rdi, r8
0x1c019b1f3  mov     r14, rdx
0x1c019b1f6  mov     rsi, rcx
0x1c019b1f9  xor     eax, eax
0x1c019b1fb  mov     ebx, eax
0x1c019b1fd  mov     [r11-50h], rax
0x1c019b201  mov     [r11-48h], rax
0x1c019b205  mov     [rsp+0B8h+var_58], al
0x1c019b209  mov     [rsp+0B8h+var_57], al
0x1c019b20d  mov     rax, [rdx+0B8h]
0x1c019b214  mov     r12d, [rax+10h]
0x1c019b218  mov     r15b, [rax+2]
0x1c019b21c  and     r15b, 1
0x1c019b220  or      dword ptr [rcx+8], 1
0x1c019b224  mov     r8b, 1
0x1c019b227  mov     rdx, rdi
0x1c019b22a  call    RefsAcquireSharedVcb
0x1c019b22f  nop
0x1c019b230  mov     rcx, [r13+78h]
0x1c019b234  xor     r8d, r8d
0x1c019b237  cmp     [rcx+0ACh], r8w
0x1c019b23f  jz      loc_1C019B520
0x1c019b245  call    RefsIsFileOpen
0x1c019b24a  test    al, al
0x1c019b24c  jz      loc_1C019B589
0x1c019b252  test    r15b, r15b
0x1c019b255  jz      loc_1C019B3E9
0x1c019b25b  mov     rax, [rsp+0B8h+FsContext]
0x1c019b263  mov     ecx, [rax+4]
0x1c019b266  test    cl, cl
0x1c019b268  jns     short loc_1C019B2B4
0x1c019b26a  mov     edx, 20h ; ' '; NumberOfBytes
0x1c019b26f  lea     ecx, [rdx-0Fh]; PoolType
0x1c019b272  mov     r8d, 64466552h; Tag
0x1c019b278  call    cs:__imp_ExAllocatePoolWithTag
0x1c019b27f  nop     dword ptr [rax+rax+00h]
0x1c019b284  mov     rbx, rax
0x1c019b287  mov     [rsp+0B8h+var_50], rax
0x1c019b28c  mov     [rsp+0B8h+var_58], 1
0x1c019b291  mov     rcx, rax; SubjectContext
0x1c019b294  call    cs:__imp_SeCaptureSubjectContext
0x1c019b29b  nop     dword ptr [rax+rax+00h]
0x1c019b2a0  xor     r8d, r8d
0x1c019b2a3  mov     [rsp+0B8h+var_58], r8b
0x1c019b2a8  lea     rax, RefsNotifyTraverseCheck
0x1c019b2af  mov     [rsp+0B8h+var_48], rax
0x1c019b2b4  mov     [rsp+0B8h+var_58], r8b
0x1c019b2b9  cmp     cs:byte_1C012E6D4, 0
0x1c019b2c0  jz      loc_1C019B3E9
0x1c019b2c6  mov     rax, [rsp+0B8h+FsContext]
0x1c019b2ce  movzx   ecx, word ptr [rax+58h]
0x1c019b2d2  mov     eax, 200h
0x1c019b2d7  test    ax, cx
0x1c019b2da  jnz     short loc_1C019B31F
0x1c019b2dc  mov     rcx, gs:188h
0x1c019b2e5  mov     [rsp+0B8h+arg_0], rcx
0x1c019b2ed  call    cs:__imp_PsIsThreadImpersonating
0x1c019b2f4  nop     dword ptr [rax+rax+00h]
0x1c019b2f9  test    al, al
0x1c019b2fb  jnz     short loc_1C019B36F
0x1c019b2fd  mov     rdx, [r14+0B8h]
0x1c019b304  mov     [rsp+0B8h+var_40], rdx
0x1c019b309  mov     rcx, [rsp+0B8h+arg_8]
0x1c019b311  call    RefsEffectiveMode
0x1c019b316  cmp     al, 1
0x1c019b318  jz      short loc_1C019B36F
0x1c019b31a  mov     rbx, [rsp+0B8h+var_50]
0x1c019b31f  xor     r14d, r14d
0x1c019b322  mov     [rsp+0B8h+var_58], r14b
0x1c019b327  cmp     [rsp+0B8h+var_48], r14
0x1c019b32c  jnz     loc_1C019B3EC
0x1c019b332  mov     [rsp+0B8h+var_58], r14b
0x1c019b337  test    rbx, rbx
0x1c019b33a  jz      loc_1C019B3EC
0x1c019b340  mov     rcx, rbx; SubjectContext
0x1c019b343  call    cs:__imp_SeReleaseSubjectContext
0x1c019b34a  nop     dword ptr [rax+rax+00h]
0x1c019b34f  xor     edx, edx; Tag
0x1c019b351  mov     rcx, rbx; P
0x1c019b354  call    cs:__imp_ExFreePoolWithTag
0x1c019b35b  nop     dword ptr [rax+rax+00h]
0x1c019b360  mov     rbx, r14
0x1c019b363  mov     [rsp+0B8h+var_50], rbx
0x1c019b368  mov     [rsp+0B8h+var_58], r14b
0x1c019b36d  jmp     short loc_1C019B3EC
0x1c019b36f  mov     rbx, [rsp+0B8h+var_50]
0x1c019b374  xor     r14d, r14d
0x1c019b377  test    rbx, rbx
0x1c019b37a  jnz     short loc_1C019B3B5
0x1c019b37c  lea     edx, [rbx+20h]; NumberOfBytes
0x1c019b37f  lea     ecx, [rbx+11h]; PoolType
0x1c019b382  mov     r8d, 64466552h; Tag
0x1c019b388  call    cs:__imp_ExAllocatePoolWithTag
0x1c019b38f  nop     dword ptr [rax+rax+00h]
0x1c019b394  mov     rbx, rax
0x1c019b397  mov     [rsp+0B8h+var_50], rax
0x1c019b39c  mov     [rsp+0B8h+var_58], 1
0x1c019b3a1  mov     rcx, rax; SubjectContext
0x1c019b3a4  call    cs:__imp_SeCaptureSubjectContext
0x1c019b3ab  nop     dword ptr [rax+rax+00h]
0x1c019b3b0  mov     [rsp+0B8h+var_58], r14b
0x1c019b3b5  mov     rcx, [rbx]
0x1c019b3b8  test    rcx, rcx
0x1c019b3bb  jnz     short loc_1C019B3C1
0x1c019b3bd  mov     rcx, [rbx+10h]; Token
0x1c019b3c1  call    cs:__imp_SeTokenIsAdmin
0x1c019b3c8  nop     dword ptr [rax+rax+00h]
0x1c019b3cd  mov     rcx, [rsp+0B8h+var_48]
0x1c019b3d2  lea     rdx, RefsNotifyTraverseCheckEx
0x1c019b3d9  test    al, al
0x1c019b3db  cmovz   rcx, rdx
0x1c019b3df  mov     [rsp+0B8h+var_48], rcx
0x1c019b3e4  jmp     loc_1C019B322
0x1c019b3e9  xor     r14d, r14d
0x1c019b3ec  mov     rcx, [rsp+0B8h+FsContext]
0x1c019b3f4  mov     eax, [rcx+4]
0x1c019b3f7  mov     edx, 800000h
0x1c019b3fc  test    edx, eax
0x1c019b3fe  jnz     short loc_1C019B416
0x1c019b400  or      eax, edx
0x1c019b402  mov     [rcx+4], eax
0x1c019b405  lock inc dword ptr [rdi+5F8h]
0x1c019b40c  mov     [rsp+0B8h+var_57], 1
0x1c019b411  mov     rbx, [rsp+0B8h+var_50]
0x1c019b416  lea     r9, [r13+168h]; FullDirectoryName
0x1c019b41d  lea     rdx, [rdi+328h]; NotifyList
0x1c019b424  mov     [rsp+0B8h+FilterCallback], r14; FilterCallback
0x1c019b429  mov     [rsp+0B8h+SubjectContext], rbx; SubjectContext
0x1c019b42e  mov     rax, [rsp+0B8h+var_48]
0x1c019b433  mov     [rsp+0B8h+TraverseCallback], rax; TraverseCallback
0x1c019b438  mov     rax, [rsp+0B8h+arg_8]
0x1c019b440  mov     [rsp+0B8h+NotifyIrp], rax; NotifyIrp
0x1c019b445  mov     [rsp+0B8h+CompletionFilter], r12d; CompletionFilter
0x1c019b44a  mov     [rsp+0B8h+IgnoreBuffer], r14b; IgnoreBuffer
0x1c019b44f  mov     [rsp+0B8h+WatchTree], r15b; WatchTree
0x1c019b454  mov     r8, rcx; FsContext
0x1c019b457  mov     rcx, [rdi+338h]; NotifySync
0x1c019b45e  call    cs:__imp_FsRtlNotifyFilterChangeDirectory
0x1c019b465  nop     dword ptr [rax+rax+00h]
0x1c019b46a  lea     rax, WPP_GLOBAL_Control
0x1c019b471  mov     rcx, cs:WPP_GLOBAL_Control
0x1c019b478  cmp     rcx, rax
0x1c019b47b  jz      short loc_1C019B4A7
0x1c019b47d  test    dword ptr [rcx+2Ch], 100h
0x1c019b484  jz      short loc_1C019B4A7
0x1c019b486  cmp     byte ptr [rcx+29h], 5
0x1c019b48a  jb      short loc_1C019B4A7
0x1c019b48c  mov     edx, 1Dh
0x1c019b491  mov     r9d, 103h
0x1c019b497  lea     r8, WPP_fc5bf5604c2538136cf1d0307679aff8_Traceguids
0x1c019b49e  mov     rcx, [rcx+18h]
0x1c019b4a2  call    WPP_SF_D
0x1c019b4a7  mov     al, cs:RefsStatusDebugEnabled
0x1c019b4ad  test    al, al
0x1c019b4af  jz      short loc_1C019B4C9
0x1c019b4b1  mov     r8d, 67Fh
0x1c019b4b7  lea     rdx, aDirctrlC; "DirCtrl.c"
0x1c019b4be  mov     ecx, 103h; Status
0x1c019b4c3  call    RefsStatusDebug
0x1c019b4c8  nop
0x1c019b4c9  lea     rcx, [rdi+590h]; Resource
0x1c019b4d0  call    cs:__imp_ExReleaseResourceLite
0x1c019b4d7  nop     dword ptr [rax+rax+00h]
0x1c019b4dc  mov     cl, cs:RefsStatusDebugEnabled
0x1c019b4e2  test    cl, cl
0x1c019b4e4  jz      short loc_1C019B4FA
0x1c019b4e6  mov     r8d, 69Dh
0x1c019b4ec  lea     rdx, aDirctrlC; "DirCtrl.c"
0x1c019b4f3  xor     ecx, ecx; Status
0x1c019b4f5  call    RefsStatusDebug
0x1c019b4fa  xor     r8d, r8d
0x1c019b4fd  xor     edx, edx
0x1c019b4ff  mov     rcx, rsi
0x1c019b502  call    RefsExtendedCompleteRequestInternal
0x1c019b507  mov     eax, 103h
0x1c019b50c  add     rsp, 80h
0x1c019b513  pop     r15
0x1c019b515  pop     r14
0x1c019b517  pop     r13
0x1c019b519  pop     r12
0x1c019b51b  pop     rdi
0x1c019b51c  pop     rsi
0x1c019b51d  pop     rbx
0x1c019b51e  retn
0x1c019b520  lea     rax, WPP_GLOBAL_Control
0x1c019b527  mov     rcx, cs:WPP_GLOBAL_Control
0x1c019b52e  cmp     rcx, rax
0x1c019b531  jz      short loc_1C019B55B
0x1c019b533  test    dword ptr [rcx+2Ch], 100h
0x1c019b53a  jz      short loc_1C019B55B
0x1c019b53c  cmp     byte ptr [rcx+29h], 4
0x1c019b540  jb      short loc_1C019B55B
0x1c019b542  lea     edx, [rbx+1Bh]
0x1c019b545  mov     r9d, 0C0000056h
0x1c019b54b  lea     r8, WPP_fc5bf5604c2538136cf1d0307679aff8_Traceguids
0x1c019b552  mov     rcx, [rcx+18h]
0x1c019b556  call    WPP_SF_D
0x1c019b55b  mov     al, cs:RefsStatusDebugEnabled
0x1c019b561  test    al, al
0x1c019b563  jz      short loc_1C019B57C
0x1c019b565  mov     r8d, 60Dh
0x1c019b56b  lea     rdx, aDirctrlC; "DirCtrl.c"
0x1c019b572  mov     ecx, 0C0000056h; Status
0x1c019b577  call    RefsStatusDebug
0x1c019b57c  mov     edx, 0C0000056h
0x1c019b581  mov     rcx, rsi
0x1c019b584  call    RefsRaiseStatusInternal
0x1c019b589  lea     rax, WPP_GLOBAL_Control
0x1c019b590  mov     rcx, cs:WPP_GLOBAL_Control
0x1c019b597  cmp     rcx, rax
0x1c019b59a  jz      short loc_1C019B5C6
0x1c019b59c  test    dword ptr [rcx+2Ch], 100h
0x1c019b5a3  jz      short loc_1C019B5C6
0x1c019b5a5  cmp     byte ptr [rcx+29h], 4
0x1c019b5a9  jb      short loc_1C019B5C6
0x1c019b5ab  mov     edx, 1Ch
0x1c019b5b0  mov     r9d, 0C0000128h
0x1c019b5b6  lea     r8, WPP_fc5bf5604c2538136cf1d0307679aff8_Traceguids
0x1c019b5bd  mov     rcx, [rcx+18h]
0x1c019b5c1  call    WPP_SF_D
0x1c019b5c6  mov     al, cs:RefsStatusDebugEnabled
0x1c019b5cc  test    al, al
0x1c019b5ce  jz      short loc_1C019B5E7
0x1c019b5d0  mov     r8d, 617h
0x1c019b5d6  lea     rdx, aDirctrlC; "DirCtrl.c"
0x1c019b5dd  mov     ecx, 0C0000128h; Status
0x1c019b5e2  call    RefsStatusDebug
0x1c019b5e7  mov     edx, 0C0000128h
0x1c019b5ec  mov     rcx, rsi
0x1c019b5ef  call    RefsRaiseStatusInternal
0x1c019b5f4  nop
0x1c019b5f5  int     3; Trap to Debugger
0x1c019b5f6  push    rbx
0x1c019b5f8  push    rbp
0x1c019b5f9  push    rdi
0x1c019b5fa  sub     rsp, 60h
0x1c019b5fe  mov     rbp, rdx
0x1c019b601  movzx   ebx, cl
0x1c019b604  mov     [rbp+62h], bl
0x1c019b607  mov     rdi, [rbp+0D0h]
0x1c019b60e  lea     rcx, [rdi+590h]; Resource
0x1c019b615  call    cs:__imp_ExReleaseResourceLite
0x1c019b61c  nop     dword ptr [rax+rax+00h]
0x1c019b621  mov     eax, ebx
0x1c019b623  test    bl, bl
0x1c019b625  jz      short loc_1C019B659
0x1c019b627  cmp     byte ptr [rbp+61h], 0
0x1c019b62b  jz      short loc_1C019B640
0x1c019b62d  mov     rax, [rbp+0E0h]
0x1c019b634  btr     dword ptr [rax+4], 17h
0x1c019b639  lock dec dword ptr [rdi+5F8h]
0x1c019b640  cmp     byte ptr [rbp+60h], 0
0x1c019b644  jz      short loc_1C019B659
0x1c019b646  xor     edx, edx; Tag
0x1c019b648  mov     rcx, [rbp+68h]; P
0x1c019b64c  call    cs:__imp_ExFreePoolWithTag
0x1c019b653  nop     dword ptr [rax+rax+00h]
0x1c019b658  nop
0x1c019b659  add     rsp, 60h
0x1c019b65d  pop     rdi
0x1c019b65e  pop     rbp
0x1c019b65f  pop     rbx
0x1c019b660  retn
```
