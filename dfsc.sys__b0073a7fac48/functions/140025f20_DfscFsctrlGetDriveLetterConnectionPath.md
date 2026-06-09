# DfscFsctrlGetDriveLetterConnectionPath

- ea: `0x140025f20`
- end: `0x1400264ce`
- name: `DfscFsctrlGetDriveLetterConnectionPath`
- size: `1454`
- prototype: `__int64 __fastcall(__int64, wint_t *, unsigned int, _WORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x1400027f8`
- `0x1400028f4`
- `0x1400040c8`
- `0x1400042c8`
- `0x140004718`
- `0x140005f70`
- `0x140006080`
- `0x14001f8a0`
- `0x140025d4c`
- `0x140025f20`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025fd1`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025fd1`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400260c5`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002614b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400260c5`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002614b`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140026168`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140026168`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140026128`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002617a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140026128`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002617a`
- `ntoskrnl!towupper` at `0x140025f94`
- `ntoskrnl!towupper` at `0x140025fb1`
- `ntoskrnl!towupper` at `0x140026064`
- `ntoskrnl!towupper` at `0x140025f94`
- `ntoskrnl!towupper` at `0x140025fb1`
- `ntoskrnl!towupper` at `0x140026064`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400261fd`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400261fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026267`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026267`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002625b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002625b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400261e2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400261e2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400261c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400261c1`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400260e5`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400260e5`

## pseudocode

```c
__int64 __fastcall DfscFsctrlGetDriveLetterConnectionPath(
        __int64 a1,
        wint_t *a2,
        unsigned int a3,
        _WORD *a4,
        unsigned int *a5)
{
  wint_t v8; // ax
  __int64 result; // rax
  int v10; // edi
  __int64 v11; // r13
  __int64 v12; // r15
  wint_t v13; // cx
  __int64 v14; // rdx
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rdi
  PACCESS_TOKEN ClientToken; // rcx
  __int64 v17; // rdx
  NTSTATUS SessionIdToken; // ebx
  __int64 v19; // r8
  PACCESS_TOKEN PrimaryToken; // rcx
  struct _RTL_AVL_TABLE *DevicelessNetUseTable; // rdi
  struct _ERESOURCE *p_WaitListHead; // rcx
  _QWORD *v23; // rax
  struct _ERESOURCE *v24; // rax
  unsigned int v25; // edi
  int v26; // r8d
  __int64 v27; // rdi
  int v28; // [rsp+34h] [rbp-8Dh]
  unsigned int v29; // [rsp+38h] [rbp-89h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-81h] BYREF
  __int64 v31; // [rsp+50h] [rbp-71h] BYREF
  struct _UNICODE_STRING Buffer; // [rsp+58h] [rbp-69h] BYREF
  ULONG SessionId[4]; // [rsp+68h] [rbp-59h] BYREF
  __int128 v34; // [rsp+78h] [rbp-49h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+88h] [rbp-39h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT Token; // [rsp+A8h] [rbp-19h] BYREF
  WCHAR SourceString; // [rsp+C8h] [rbp+7h] BYREF
  int v38; // [rsp+CAh] [rbp+9h]

  v31 = 0;
  DestinationString = 0;
  if ( a3 < 6 || !a2 || !a4 || a2[1] != 58 || a2[2] || (unsigned __int16)(towupper(*a2) - 65) > 0x19u )
    return 3221225485LL;
  v8 = towupper(*a2);
  v38 = 58;
  SourceString = v8;
  RtlInitUnicodeStringEx(&DestinationString, &SourceString);
  result = DfscGetContainerContextFromIrp(a1, &v31);
  if ( (int)result < 0 )
    return result;
  v10 = 0;
  v11 = v31;
  v12 = 0;
  v29 = *a5;
  Buffer = 0;
  *(_OWORD *)SessionId = 0;
  v34 = 0;
  if ( !DestinationString.Buffer )
    goto LABEL_52;
  v13 = *DestinationString.Buffer;
  if ( !*DestinationString.Buffer )
    goto LABEL_52;
  if ( v13 != 92 && DestinationString.Buffer[1] == 58 )
  {
    if ( (unsigned __int16)(towupper(v13) - 65) <= 0x19u )
    {
      v28 = 1;
      goto LABEL_14;
    }
LABEL_52:
    SessionIdToken = -1073741811;
    goto LABEL_39;
  }
  v28 = 0;
LABEL_14:
  v14 = *(_QWORD *)(a1 + 184);
  Buffer = 0;
  *(_OWORD *)SessionId = 0;
  v34 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( (!*(_BYTE *)v14 || *(_BYTE *)v14 == 1 || *(_BYTE *)v14 == 19) && (v27 = *(_QWORD *)(v14 + 8)) != 0 )
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(v27 + 8) + 32LL);
  }
  else
  {
    SeCaptureSubjectContext(&SubjectContext);
    p_SubjectContext = &SubjectContext;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  SessionIdToken = SeQuerySessionIdToken(ClientToken, SessionId);
  if ( SessionIdToken < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        (unsigned int)SessionIdToken);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
  {
    WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, v17, v19, SessionId[0]);
  }
  if ( p_SubjectContext == &SubjectContext )
    SeReleaseSubjectContext(&SubjectContext);
  if ( SessionIdToken )
    goto LABEL_65;
  memset(&Token, 0, sizeof(Token));
  SeCaptureSubjectContext(&Token);
  PrimaryToken = Token.ClientToken;
  if ( !Token.ClientToken )
    PrimaryToken = Token.PrimaryToken;
  SessionIdToken = SeQueryAuthenticationIdToken(PrimaryToken, (PLUID)&SessionId[1]);
  SeReleaseSubjectContext(&Token);
  if ( SessionIdToken )
  {
LABEL_65:
    v10 = 0;
    goto LABEL_39;
  }
  if ( v28 )
  {
    if ( v11 )
      DevicelessNetUseTable = *(struct _RTL_AVL_TABLE **)(v11 + 256);
    else
      DevicelessNetUseTable = Table;
    DWORD2(v34) = 1;
  }
  else
  {
    DevicelessNetUseTable = (struct _RTL_AVL_TABLE *)DfscGetDevicelessNetUseTable(v11);
    DWORD2(v34) = 0;
  }
  Buffer = DestinationString;
  KeEnterCriticalRegion();
  p_WaitListHead = (struct _ERESOURCE *)(v11 + 152);
  if ( !v11 )
    p_WaitListHead = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  ExAcquireResourceExclusiveLite(p_WaitListHead, 1u);
  v23 = RtlLookupElementGenericTableAvl(DevicelessNetUseTable, &Buffer);
  if ( v23 )
  {
    v12 = v23[4];
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 4));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_Zq(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids,
        (unsigned int)&Buffer,
        v12);
    }
  }
  if ( !v12 )
  {
    v10 = 1;
    SessionIdToken = -1073741772;
    goto LABEL_39;
  }
  v25 = *(unsigned __int16 *)(v12 + 88) + 4;
  if ( *a5 < v25 )
  {
    *a5 = v25;
    SessionIdToken = -2147483643;
    v10 = 1;
    goto LABEL_39;
  }
  *a4 = 92;
  memmove(a4 + 1, *(const void **)(v12 + 96), *(unsigned __int16 *)(v12 + 88));
  a4[((unsigned __int64)v25 - 2) >> 1] = 0;
  *a5 = v25;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      WPP_SF_ZZD(WPP_GLOBAL_Control->AttachedDevice, 27, v26, v12 + 88, (__int64)&DestinationString, v25);
    v10 = 1;
LABEL_39:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_DZ(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        (unsigned int)WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        SessionIdToken,
        (__int64)&DestinationString);
    }
    if ( !v10 )
      goto LABEL_46;
  }
  if ( v11 )
    v24 = (struct _ERESOURCE *)(v11 + 152);
  else
    v24 = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  ExReleaseResourceLite(v24);
  KeLeaveCriticalRegion();
LABEL_46:
  if ( v12 )
    DfscNetUseRelease(v11, v12, 0, 0);
  if ( SessionIdToken != -2147483643 )
    return (unsigned int)SessionIdToken;
  if ( v29 < 4 )
    return 3221225507LL;
  result = 2147483653LL;
  *(_DWORD *)a4 = *a5;
  *(_QWORD *)(a1 + 56) = 4;
  return result;
}

```

## disassembly

```asm
0x140025f20  push    rbp
0x140025f22  push    rbx
0x140025f23  push    rsi
0x140025f24  push    r12
0x140025f26  push    r14
0x140025f28  lea     rbp, [rsp-2Fh]
0x140025f2d  sub     rsp, 0F0h
0x140025f34  mov     rax, cs:__security_cookie
0x140025f3b  xor     rax, rsp
0x140025f3e  mov     [rbp+4Fh+var_40], rax
0x140025f42  mov     r12, [rbp+4Fh+arg_20]
0x140025f46  xorps   xmm0, xmm0
0x140025f49  mov     [rbp+4Fh+var_C0], 0
0x140025f51  mov     r14, r9
0x140025f54  mov     rbx, rdx
0x140025f57  mov     rsi, rcx
0x140025f5a  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x140025f5f  cmp     r8d, 6
0x140025f63  jb      loc_1400262A4
0x140025f69  test    rdx, rdx
0x140025f6c  jz      loc_1400262A4
0x140025f72  test    r9, r9
0x140025f75  jz      loc_1400262A4
0x140025f7b  cmp     word ptr [rdx+2], 3Ah ; ':'
0x140025f80  jnz     loc_1400262A4
0x140025f86  cmp     word ptr [rdx+4], 0
0x140025f8b  jnz     loc_1400262A4
0x140025f91  movzx   ecx, word ptr [rdx]; C
0x140025f94  call    cs:__imp_towupper
0x140025f9b  nop     dword ptr [rax+rax+00h]
0x140025fa0  sub     ax, 41h ; 'A'
0x140025fa4  cmp     ax, 19h
0x140025fa8  ja      loc_1400262A4
0x140025fae  movzx   ecx, word ptr [rbx]; C
0x140025fb1  call    cs:__imp_towupper
0x140025fb8  nop     dword ptr [rax+rax+00h]
0x140025fbd  lea     rdx, [rbp+4Fh+SourceString]; SourceString
0x140025fc1  mov     [rbp+4Fh+var_46], 3Ah ; ':'
0x140025fc8  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x140025fcd  mov     [rbp+4Fh+SourceString], ax
0x140025fd1  call    cs:__imp_RtlInitUnicodeStringEx
0x140025fd8  nop     dword ptr [rax+rax+00h]
0x140025fdd  lea     rdx, [rbp+4Fh+var_C0]
0x140025fe1  mov     rcx, rsi
0x140025fe4  call    DfscGetContainerContextFromIrp
0x140025fe9  test    eax, eax
0x140025feb  js      loc_1400262A9
0x140025ff1  mov     eax, [r12]
0x140025ff5  xorps   xmm0, xmm0
0x140025ff8  mov     [rsp+110h+arg_10], rdi
0x140026000  xor     edi, edi
0x140026002  mov     [rsp+110h+var_28], r13
0x14002600a  mov     r13, [rbp+4Fh+var_C0]
0x14002600e  mov     [rsp+110h+var_30], r15
0x140026016  xor     r15d, r15d
0x140026019  mov     [rsp+110h+var_D8], eax
0x14002601d  mov     rax, [rbp+4Fh+DestinationString.Buffer]
0x140026021  movups  [rbp+4Fh+Buffer], xmm0
0x140026025  movups  xmmword ptr [rbp+4Fh+SessionId], xmm0
0x140026029  movups  [rbp+4Fh+var_98], xmm0
0x14002602d  test    rax, rax
0x140026030  jz      loc_1400262C5
0x140026036  movzx   ecx, word ptr [rax]; C
0x140026039  test    cx, cx
0x14002603c  jz      loc_1400262C5
0x140026042  cmp     cx, 5Ch ; '\'
0x140026046  jz      loc_1400262CF
0x14002604c  movzx   edx, word ptr [rax+2]
0x140026050  cmp     dx, 5Ch ; '\'
0x140026054  jz      loc_1400262CF
0x14002605a  cmp     dx, 3Ah ; ':'
0x14002605e  jnz     loc_1400262CF
0x140026064  call    cs:__imp_towupper
0x14002606b  nop     dword ptr [rax+rax+00h]
0x140026070  sub     ax, 41h ; 'A'
0x140026074  cmp     ax, 19h
0x140026078  ja      loc_1400262C5
0x14002607e  mov     [rsp+110h+var_DC], 1
0x140026086  mov     rdx, [rsi+0B8h]
0x14002608d  xorps   xmm0, xmm0
0x140026090  movups  [rbp+4Fh+Buffer], xmm0
0x140026094  movups  xmmword ptr [rbp+4Fh+SessionId], xmm0
0x140026098  movups  [rbp+4Fh+var_98], xmm0
0x14002609c  movups  xmmword ptr [rbp+4Fh+SubjectContext.ClientToken], xmm0
0x1400260a0  movups  xmmword ptr [rbp+4Fh+SubjectContext.PrimaryToken], xmm0
0x1400260a4  movzx   ecx, byte ptr [rdx]
0x1400260a7  test    ecx, ecx
0x1400260a9  jz      loc_14002638F
0x1400260af  sub     ecx, 1
0x1400260b2  jz      loc_14002638F
0x1400260b8  cmp     ecx, 12h
0x1400260bb  jz      loc_14002638F
0x1400260c1  lea     rcx, [rbp+4Fh+SubjectContext]; SubjectContext
0x1400260c5  call    cs:__imp_SeCaptureSubjectContext
0x1400260cc  nop     dword ptr [rax+rax+00h]
0x1400260d1  lea     rdi, [rbp+4Fh+SubjectContext]
0x1400260d5  mov     rcx, [rdi]
0x1400260d8  test    rcx, rcx
0x1400260db  jnz     short loc_1400260E1
0x1400260dd  mov     rcx, [rdi+10h]; Token
0x1400260e1  lea     rdx, [rbp+4Fh+SessionId]; SessionId
0x1400260e5  call    cs:__imp_SeQuerySessionIdToken
0x1400260ec  nop     dword ptr [rax+rax+00h]
0x1400260f1  mov     ebx, eax
0x1400260f3  test    eax, eax
0x1400260f5  js      loc_1400263C3
0x1400260fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140026102  lea     rax, WPP_GLOBAL_Control
0x140026109  cmp     rcx, rax
0x14002610c  jz      short loc_14002611B
0x14002610e  test    dword ptr [rcx+2Ch], 400000h
0x140026115  jnz     loc_140026404
0x14002611b  lea     rax, [rbp+4Fh+SubjectContext]
0x14002611f  cmp     rdi, rax
0x140026122  jnz     short loc_140026134
0x140026124  lea     rcx, [rbp+4Fh+SubjectContext]; SubjectContext
0x140026128  call    cs:__imp_SeReleaseSubjectContext
0x14002612f  nop     dword ptr [rax+rax+00h]
0x140026134  test    ebx, ebx
0x140026136  jnz     loc_1400263BB
0x14002613c  xorps   xmm0, xmm0
0x14002613f  lea     rcx, [rbp+4Fh+Token]; SubjectContext
0x140026143  movups  xmmword ptr [rbp+4Fh+Token.ClientToken], xmm0
0x140026147  movups  xmmword ptr [rbp+4Fh+Token.PrimaryToken], xmm0
0x14002614b  call    cs:__imp_SeCaptureSubjectContext
0x140026152  nop     dword ptr [rax+rax+00h]
0x140026157  mov     rcx, [rbp+4Fh+Token.ClientToken]
0x14002615b  lea     rdx, [rbp+4Fh+SessionId+4]; AuthenticationId
0x14002615f  test    rcx, rcx
0x140026162  jnz     short loc_140026168
0x140026164  mov     rcx, [rbp+4Fh+Token.PrimaryToken]; Token
0x140026168  call    cs:__imp_SeQueryAuthenticationIdToken
0x14002616f  nop     dword ptr [rax+rax+00h]
0x140026174  lea     rcx, [rbp+4Fh+Token]; SubjectContext
0x140026178  mov     ebx, eax
0x14002617a  call    cs:__imp_SeReleaseSubjectContext
0x140026181  nop     dword ptr [rax+rax+00h]
0x140026186  test    ebx, ebx
0x140026188  jnz     loc_1400263BB
0x14002618e  cmp     [rsp+110h+var_DC], r15d
0x140026193  jz      loc_140026422
0x140026199  test    r13, r13
0x14002619c  jnz     loc_140026416
0x1400261a2  mov     rdi, cs:Table
0x1400261a9  mov     dword ptr [rbp+4Fh+var_98+8], 1
0x1400261b0  mov     rcx, qword ptr [rsp+110h+DestinationString.Length]
0x1400261b5  mov     qword ptr [rbp+4Fh+Buffer], rcx
0x1400261b9  mov     rcx, [rbp+4Fh+DestinationString.Buffer]
0x1400261bd  mov     qword ptr [rbp+4Fh+Buffer+8], rcx
0x1400261c1  call    cs:__imp_KeEnterCriticalRegion
0x1400261c8  nop     dword ptr [rax+rax+00h]
0x1400261cd  lea     rcx, [r13+98h]
0x1400261d4  test    r13, r13
0x1400261d7  jnz     short loc_1400261E0
0x1400261d9  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Resource
0x1400261e0  mov     dl, 1; Wait
0x1400261e2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400261e9  nop     dword ptr [rax+rax+00h]
0x1400261ee  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x1400261f2  mov     [rsp+110h+var_E0], 1
0x1400261fa  mov     rcx, rdi; Table
0x1400261fd  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140026204  nop     dword ptr [rax+rax+00h]
0x140026209  test    rax, rax
0x14002620c  jnz     loc_1400262D8
0x140026212  test    r15, r15
0x140026215  jnz     loc_140026328
0x14002621b  mov     edi, [rsp+110h+var_E0]
0x14002621f  mov     ebx, 0C0000034h
0x140026224  mov     rcx, cs:WPP_GLOBAL_Control
0x14002622b  lea     rax, WPP_GLOBAL_Control
0x140026232  cmp     rcx, rax
0x140026235  jz      short loc_140026244
0x140026237  test    dword ptr [rcx+2Ch], 100000h
0x14002623e  jnz     loc_14002645B
0x140026244  test    edi, edi
0x140026246  jz      short loc_140026273
0x140026248  test    r13, r13
0x14002624b  jnz     loc_140026482
0x140026251  lea     rax, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140026258  mov     rcx, rax; Resource
0x14002625b  call    cs:__imp_ExReleaseResourceLite
0x140026262  nop     dword ptr [rax+rax+00h]
0x140026267  call    cs:__imp_KeLeaveCriticalRegion
0x14002626e  nop     dword ptr [rax+rax+00h]
0x140026273  mov     rdi, [rsp+110h+arg_10]
0x14002627b  test    r15, r15
0x14002627e  jnz     loc_14002648E
0x140026284  mov     r15, [rsp+110h+var_30]
0x14002628c  mov     r13, [rsp+110h+var_28]
0x140026294  cmp     ebx, 80000005h
0x14002629a  jz      loc_1400264A4
0x1400262a0  mov     eax, ebx
0x1400262a2  jmp     short loc_1400262A9
0x1400262a4  mov     eax, 0C000000Dh
0x1400262a9  mov     rcx, [rbp+4Fh+var_40]
0x1400262ad  xor     rcx, rsp; StackCookie
0x1400262b0  call    __security_check_cookie
0x1400262b5  add     rsp, 0F0h
0x1400262bc  pop     r14
0x1400262be  pop     r12
0x1400262c0  pop     rsi
0x1400262c1  pop     rbx
0x1400262c2  pop     rbp
0x1400262c3  retn
0x1400262c5  mov     ebx, 0C000000Dh
0x1400262ca  jmp     loc_140026224
0x1400262cf  mov     [rsp+110h+var_DC], edi
0x1400262d3  jmp     loc_140026086
0x1400262d8  mov     r15, [rax+20h]
0x1400262dc  lock inc dword ptr [r15+4]
0x1400262e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400262e8  lea     rdi, WPP_GLOBAL_Control
0x1400262ef  cmp     rcx, rdi
0x1400262f2  jz      loc_140026212
0x1400262f8  test    dword ptr [rcx+2Ch], 400000h
0x1400262ff  jz      loc_140026212
0x140026305  mov     rcx, [rcx+18h]
0x140026309  lea     r9, [rbp+4Fh+Buffer]
0x14002630d  mov     edx, 0Ah
0x140026312  mov     [rsp+110h+var_F0], r15
0x140026317  lea     r8, WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids
0x14002631e  call    WPP_SF_Zq
0x140026323  jmp     loc_140026212
0x140026328  movzx   edi, word ptr [r15+58h]
0x14002632d  add     edi, 4
0x140026330  cmp     [r12], edi
0x140026334  jb      short loc_1400263A9
0x140026336  mov     word ptr [r14], 5Ch ; '\'
0x14002633c  lea     rcx, [r14+2]; void *
0x140026340  movzx   r8d, word ptr [r15+58h]; Size
0x140026345  mov     rdx, [r15+60h]; Src
0x140026349  call    memmove
0x14002634e  mov     ecx, edi
0x140026350  sub     rcx, 2
0x140026354  shr     rcx, 1
0x140026357  xor     eax, eax
0x140026359  mov     [r14+rcx*2], ax
0x14002635e  mov     [r12], edi
0x140026362  mov     rcx, cs:WPP_GLOBAL_Control
0x140026369  lea     rax, WPP_GLOBAL_Control
0x140026370  cmp     rcx, rax
0x140026373  jz      loc_140026248
0x140026379  test    dword ptr [rcx+2Ch], 400000h
0x140026380  jnz     loc_140026436
0x140026386  mov     edi, [rsp+110h+var_E0]
0x14002638a  jmp     loc_140026224
0x14002638f  mov     rdi, [rdx+8]
0x140026393  test    rdi, rdi
0x140026396  jz      loc_1400260C1
0x14002639c  mov     rdi, [rdi+8]
0x1400263a0  add     rdi, 20h ; ' '
0x1400263a4  jmp     loc_1400260D5
0x1400263a9  mov     [r12], edi
0x1400263ad  mov     ebx, 80000005h
0x1400263b2  mov     edi, [rsp+110h+var_E0]
0x1400263b6  jmp     loc_140026224
0x1400263bb  mov     edi, r15d
0x1400263be  jmp     loc_140026224
0x1400263c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400263ca  lea     rax, WPP_GLOBAL_Control
0x1400263d1  cmp     rcx, rax
0x1400263d4  jz      loc_14002611B
0x1400263da  test    dword ptr [rcx+2Ch], 100000h
0x1400263e1  jz      loc_14002611B
0x1400263e7  mov     rcx, [rcx+18h]
0x1400263eb  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400263f2  mov     edx, 23h ; '#'
0x1400263f7  mov     r9d, ebx
0x1400263fa  call    WPP_SF_D
0x1400263ff  jmp     loc_14002611B
0x140026404  mov     r9d, [rbp+4Fh+SessionId]
0x140026408  mov     rcx, [rcx+18h]
0x14002640c  call    WPP_SF_l
0x140026411  jmp     loc_14002611B
0x140026416  mov     rdi, [r13+100h]
0x14002641d  jmp     loc_1400261A9
0x140026422  mov     rcx, r13
0x140026425  call    DfscGetDevicelessNetUseTable
0x14002642a  mov     rdi, rax
0x14002642d  mov     dword ptr [rbp+4Fh+var_98+8], r15d
0x140026431  jmp     loc_1400261B0
0x140026436  mov     rcx, [rcx+18h]
0x14002643a  lea     rax, [rsp+110h+DestinationString]
0x14002643f  mov     edx, 1Bh
0x140026444  mov     [rsp+110h+var_E8], edi
0x140026448  lea     r9, [r15+58h]
0x14002644c  mov     [rsp+110h+var_F0], rax
0x140026451  call    WPP_SF_ZZD
0x140026456  jmp     loc_140026386
0x14002645b  mov     rcx, [rcx+18h]
0x14002645f  lea     rax, [rsp+110h+DestinationString]
0x140026464  mov     edx, 1Ch
0x140026469  mov     [rsp+110h+var_F0], rax
0x14002646e  mov     r9d, ebx
0x140026471  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x140026478  call    WPP_SF_DZ
0x14002647d  jmp     loc_140026244
0x140026482  lea     rax, [r13+98h]
0x140026489  jmp     loc_140026258
  ... truncated ...
```
