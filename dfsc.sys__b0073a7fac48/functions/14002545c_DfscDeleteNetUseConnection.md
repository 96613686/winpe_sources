# DfscDeleteNetUseConnection

- ea: `0x14002545c`
- end: `0x140025912`
- name: `DfscDeleteNetUseConnection`
- size: `1206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, _DWORD *, _DWORD *, char)`
- caller_count: `3`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140014520`
- `0x140014810`
- `0x140028004`

## callees

- `0x1400025a0`
- `0x1400026a4`
- `0x1400027f8`
- `0x1400028f4`
- `0x140002aa0`
- `0x14000328c`
- `0x140003fa0`
- `0x140006080`
- `0x140011a34`
- `0x1400120f4`
- `0x140013cbc`
- `0x1400140bc`
- `0x140017fb8`
- `0x14001f8a0`
- `0x14002545c`
- `0x140025918`
- `0x140025aa0`
- `0x140025d4c`
- `0x140025d6c`
- `0x140025efc`
- `0x140026ed0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400254e4`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400254e4`
- `ntoskrnl!PsRevertToSelf` at `0x140025884`
- `ntoskrnl!PsRevertToSelf` at `0x140025884`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025647`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002569c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025647`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002569c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002563b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025690`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002563b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025690`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025569`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025569`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025543`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025543`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400258b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400258b4`

## pseudocode

```c
__int64 __fastcall DfscDeleteNetUseConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        _DWORD *a6,
        char a7)
{
  int v7; // ebx
  unsigned int SearchKey; // edi
  struct _ERESOURCE *p_WaitListHead; // rbx
  struct _ERESOURCE *v13; // rcx
  __int64 v14; // rax
  ULONG_PTR v15; // r15
  __int64 v16; // rcx
  int v17; // r14d
  __int64 v18; // r8
  int v19; // ebx
  const wchar_t *v20; // r9
  unsigned int Length; // r13d
  int v22; // edx
  int v23; // r8d
  __int64 DriveLetterNetUseTable; // rax
  __int64 v25; // rcx
  __int64 DevicelessNetUseTable; // rax
  __int64 v27; // rcx
  struct _RTL_AVL_TABLE *CredTable; // rax
  _BYTE v30[4]; // [rsp+30h] [rbp-50h] BYREF
  int v31; // [rsp+34h] [rbp-4Ch] BYREF
  ULONG_PTR BugCheckParameter2; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  _OWORD v34[3]; // [rsp+50h] [rbp-30h] BYREF
  int v37; // [rsp+E0h] [rbp+60h]

  BugCheckParameter2 = 0;
  v7 = a3;
  memset(v34, 0, sizeof(v34));
  v31 = 0;
  v30[0] = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids, a2);
  RtlInitUnicodeStringEx(&DestinationString, 0);
  if ( a5 )
  {
    if ( *a6 < 8u )
    {
      *a6 = 8;
      SearchKey = -2147483643;
      goto LABEL_63;
    }
    v31 = *a6 - 4;
  }
  SearchKey = DfscNetUseGetSearchKey(a1, a2, v7, (unsigned int)&BugCheckParameter2, (__int64)v34);
  if ( !SearchKey )
  {
    KeEnterCriticalRegion();
    p_WaitListHead = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v13 = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    if ( a1 )
      v13 = (struct _ERESOURCE *)(a1 + 152);
    ExAcquireResourceExclusiveLite(v13, 1u);
    v14 = DfscNetUseTableLookup(BugCheckParameter2, v34, 0, 0);
    v15 = v14;
    if ( v14 )
    {
      if ( a4 || !*(_DWORD *)(v14 + 144) )
      {
        v16 = *(_QWORD *)(v14 + 112);
        v37 = 0;
        if ( v16 && *(_DWORD *)(v16 + 52) != 1 )
        {
          SearchKey = DfscCredCreateTargetNameCopy(v16, &DestinationString, &v31);
          if ( SearchKey )
          {
            v17 = v31;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
            {
              WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids);
            }
            if ( SearchKey == -2147483643 )
              *a6 = v17 + 4;
            goto LABEL_24;
          }
          v37 = *(_DWORD *)(*(_QWORD *)(v15 + 112) + 48LL);
        }
        DfscNetUseTableDelete(BugCheckParameter2, v15);
        DfscNetUseRelease(a1, v15, 0, 0);
        if ( a1 )
          p_WaitListHead = (struct _ERESOURCE *)(a1 + 152);
        ExReleaseResourceLite(p_WaitListHead);
        KeLeaveCriticalRegion();
        if ( a7 || (SearchKey = DfscImpersonateCaller(a3, v30)) == 0 )
        {
          SearchKey = DfscDeleteSymbolicLink(**(unsigned __int16 **)(a2 + 8));
          if ( SearchKey )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
            {
              WPP_SF_DZ(
                WPP_GLOBAL_Control->AttachedDevice,
                19,
                (unsigned int)WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
                SearchKey,
                a2);
            }
            SearchKey = 0;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            WPP_SF_qZ(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              (unsigned int)WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
              v15,
              a2);
          }
          LOBYTE(v18) = 1;
          v19 = DfscNetUseRelease(a1, v15, v18, 0);
          v15 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            v20 = L"WAS";
            if ( !v19 )
              v20 = L"WAS NOT";
            WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids, v20);
          }
          if ( v19
            && (Length = DestinationString.Length) != 0
            && DestinationString.Buffer
            && *DestinationString.Buffer
            && a5 )
          {
            memmove(a5 + 1, DestinationString.Buffer, DestinationString.Length);
            *a5 = v37;
            *a6 = Length + 6;
            *((_WORD *)a5 + ((unsigned __int64)Length >> 1) + 2) = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_SD(WPP_GLOBAL_Control->AttachedDevice, v22, v23, (_DWORD)a5 + 4, *a6);
            }
          }
          else
          {
            *a6 = 0;
            if ( a5 )
            {
              *((_WORD *)a5 + 2) = 0;
              *a5 = 0;
            }
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids, SearchKey);
        }
        goto LABEL_59;
      }
      SearchKey = -2147483631;
    }
    else
    {
      SearchKey = -1073741772;
    }
LABEL_24:
    if ( a1 )
      p_WaitListHead = (struct _ERESOURCE *)(a1 + 152);
    ExReleaseResourceLite(p_WaitListHead);
    KeLeaveCriticalRegion();
LABEL_59:
    if ( v30[0] )
      PsRevertToSelf();
    if ( v15 )
      DfscNetUseRelease(a1, v15, 0, 0);
  }
LABEL_63:
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
  }
  DriveLetterNetUseTable = DfscGetDriveLetterNetUseTable(a1);
  DfscNetUseTableDump(v25, DriveLetterNetUseTable);
  DevicelessNetUseTable = DfscGetDevicelessNetUseTable(a1);
  DfscNetUseTableDump(v27, DevicelessNetUseTable);
  CredTable = (struct _RTL_AVL_TABLE *)DfscGetCredTable(a1);
  DfscCredTableDump(CredTable);
  return SearchKey;
}

```

## disassembly

```asm
0x14002545c  mov     [rsp-38h+arg_0], rbx
0x140025461  mov     [rsp-38h+arg_18], r9d
0x140025466  mov     [rsp-38h+arg_10], r8
0x14002546b  push    rbp
0x14002546c  push    rsi
0x14002546d  push    rdi
0x14002546e  push    r12
0x140025470  push    r13
0x140025472  push    r14
0x140025474  push    r15
0x140025476  mov     rbp, rsp
0x140025479  sub     rsp, 80h
0x140025480  xorps   xmm0, xmm0
0x140025483  xor     r15d, r15d
0x140025486  mov     [rbp+BugCheckParameter2], r15
0x14002548a  mov     rbx, r8
0x14002548d  movups  [rbp+var_30], xmm0
0x140025491  mov     [rbp+var_4C], r15d
0x140025495  mov     r13, rdx
0x140025498  movups  [rbp+var_20], xmm0
0x14002549c  mov     [rbp+var_50], r15b
0x1400254a0  mov     rsi, rcx
0x1400254a3  movups  [rbp+var_10], xmm0
0x1400254a7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400254ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254b2  lea     rax, WPP_GLOBAL_Control
0x1400254b9  cmp     rcx, rax
0x1400254bc  jz      short loc_1400254DE
0x1400254be  test    dword ptr [rcx+2Ch], 400000h
0x1400254c5  jz      short loc_1400254DE
0x1400254c7  mov     rcx, [rcx+18h]
0x1400254cb  lea     edx, [r15+10h]
0x1400254cf  mov     r9, r13
0x1400254d2  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400254d9  call    WPP_SF_Z
0x1400254de  xor     edx, edx; SourceString
0x1400254e0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400254e4  call    cs:__imp_RtlInitUnicodeStringEx
0x1400254eb  nop     dword ptr [rax+rax+00h]
0x1400254f0  mov     r14, [rbp+arg_20]
0x1400254f4  mov     r12, [rbp+arg_28]
0x1400254f8  test    r14, r14
0x1400254fb  jz      short loc_14002551E
0x1400254fd  mov     eax, [r12]
0x140025501  cmp     eax, 8
0x140025504  jnb     short loc_140025518
0x140025506  mov     dword ptr [r12], 8
0x14002550e  mov     edi, 80000005h
0x140025513  jmp     loc_1400258A9
0x140025518  add     eax, 0FFFFFFFCh
0x14002551b  mov     [rbp+var_4C], eax
0x14002551e  lea     rax, [rbp+var_30]
0x140025522  mov     r8, rbx
0x140025525  lea     r9, [rbp+BugCheckParameter2]
0x140025529  mov     [rsp+80h+var_60], rax
0x14002552e  mov     rdx, r13
0x140025531  mov     rcx, rsi
0x140025534  call    DfscNetUseGetSearchKey
0x140025539  mov     edi, eax
0x14002553b  test    eax, eax
0x14002553d  jnz     loc_1400258A9
0x140025543  call    cs:__imp_KeEnterCriticalRegion
0x14002554a  nop     dword ptr [rax+rax+00h]
0x14002554f  lea     rax, [rsi+98h]
0x140025556  test    rsi, rsi
0x140025559  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140025560  mov     dl, 1; Wait
0x140025562  mov     rcx, rbx
0x140025565  cmovnz  rcx, rax; Resource
0x140025569  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140025570  nop     dword ptr [rax+rax+00h]
0x140025575  mov     rcx, [rbp+BugCheckParameter2]
0x140025579  lea     rdx, [rbp+var_30]
0x14002557d  xor     r9d, r9d
0x140025580  xor     r8d, r8d
0x140025583  call    DfscNetUseTableLookup
0x140025588  xor     edi, edi
0x14002558a  mov     r15, rax
0x14002558d  test    rax, rax
0x140025590  jnz     short loc_14002559C
0x140025592  mov     edi, 0C0000034h
0x140025597  jmp     loc_14002562A
0x14002559c  cmp     [rbp+arg_18], edi
0x14002559f  jnz     short loc_1400255B0
0x1400255a1  cmp     [rax+90h], edi
0x1400255a7  jz      short loc_1400255B0
0x1400255a9  mov     edi, 80000011h
0x1400255ae  jmp     short loc_14002562A
0x1400255b0  mov     rcx, [rax+70h]
0x1400255b4  mov     dword ptr [rbp+arg_20], edi
0x1400255b7  test    rcx, rcx
0x1400255ba  jz      loc_140025662
0x1400255c0  cmp     dword ptr [rcx+34h], 1
0x1400255c4  jz      loc_140025662
0x1400255ca  lea     r8, [rbp+var_4C]
0x1400255ce  lea     rdx, [rbp+DestinationString]
0x1400255d2  call    DfscCredCreateTargetNameCopy
0x1400255d7  mov     edi, eax
0x1400255d9  test    eax, eax
0x1400255db  jz      short loc_140025658
0x1400255dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255e4  lea     rax, WPP_GLOBAL_Control
0x1400255eb  mov     r14d, [rbp+var_4C]
0x1400255ef  cmp     rcx, rax
0x1400255f2  jz      short loc_14002561A
0x1400255f4  test    dword ptr [rcx+2Ch], 100000h
0x1400255fb  jz      short loc_14002561A
0x1400255fd  mov     rcx, [rcx+18h]
0x140025601  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x140025608  mov     edx, 11h
0x14002560d  mov     dword ptr [rsp+80h+var_60], r14d
0x140025612  mov     r9d, edi
0x140025615  call    WPP_SF_dd
0x14002561a  cmp     edi, 80000005h
0x140025620  jnz     short loc_14002562A
0x140025622  lea     eax, [r14+4]
0x140025626  mov     [r12], eax
0x14002562a  lea     rax, [rsi+98h]
0x140025631  test    rsi, rsi
0x140025634  cmovnz  rbx, rax
0x140025638  mov     rcx, rbx; Resource
0x14002563b  call    cs:__imp_ExReleaseResourceLite
0x140025642  nop     dword ptr [rax+rax+00h]
0x140025647  call    cs:__imp_KeLeaveCriticalRegion
0x14002564e  nop     dword ptr [rax+rax+00h]
0x140025653  jmp     loc_140025868
0x140025658  mov     rax, [r15+70h]
0x14002565c  mov     eax, [rax+30h]
0x14002565f  mov     dword ptr [rbp+arg_20], eax
0x140025662  mov     rcx, [rbp+BugCheckParameter2]; BugCheckParameter2
0x140025666  mov     rdx, r15; BugCheckParameter3
0x140025669  call    DfscNetUseTableDelete
0x14002566e  xor     r9d, r9d
0x140025671  xor     r8d, r8d
0x140025674  mov     rdx, r15
0x140025677  mov     rcx, rsi
0x14002567a  call    DfscNetUseRelease
0x14002567f  lea     rax, [rsi+98h]
0x140025686  test    rsi, rsi
0x140025689  cmovnz  rbx, rax
0x14002568d  mov     rcx, rbx; Resource
0x140025690  call    cs:__imp_ExReleaseResourceLite
0x140025697  nop     dword ptr [rax+rax+00h]
0x14002569c  call    cs:__imp_KeLeaveCriticalRegion
0x1400256a3  nop     dword ptr [rax+rax+00h]
0x1400256a8  xor     ebx, ebx
0x1400256aa  cmp     [rbp+arg_30], bl
0x1400256ad  jnz     short loc_140025701
0x1400256af  mov     rcx, [rbp+arg_10]
0x1400256b3  lea     rdx, [rbp+var_50]
0x1400256b7  call    DfscImpersonateCaller
0x1400256bc  mov     edi, eax
0x1400256be  test    eax, eax
0x1400256c0  jz      short loc_140025701
0x1400256c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400256c9  lea     rax, WPP_GLOBAL_Control
0x1400256d0  cmp     rcx, rax
0x1400256d3  jz      loc_14002587F
0x1400256d9  test    dword ptr [rcx+2Ch], 400000h
0x1400256e0  jz      loc_14002587F
0x1400256e6  mov     rcx, [rcx+18h]
0x1400256ea  lea     edx, [rbx+12h]
0x1400256ed  mov     r9d, edi
0x1400256f0  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400256f7  call    WPP_SF_D
0x1400256fc  jmp     loc_14002587F
0x140025701  mov     rcx, [r13+8]
0x140025705  movzx   ecx, word ptr [rcx]
0x140025708  call    DfscDeleteSymbolicLink
0x14002570d  mov     edi, eax
0x14002570f  test    eax, eax
0x140025711  jz      short loc_14002574E
0x140025713  mov     rcx, cs:WPP_GLOBAL_Control
0x14002571a  lea     rax, WPP_GLOBAL_Control
0x140025721  cmp     rcx, rax
0x140025724  jz      short loc_14002574C
0x140025726  test    dword ptr [rcx+2Ch], 100000h
0x14002572d  jz      short loc_14002574C
0x14002572f  mov     rcx, [rcx+18h]
0x140025733  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x14002573a  mov     edx, 13h
0x14002573f  mov     [rsp+80h+var_60], r13
0x140025744  mov     r9d, edi
0x140025747  call    WPP_SF_DZ
0x14002574c  mov     edi, ebx
0x14002574e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025755  lea     rax, WPP_GLOBAL_Control
0x14002575c  cmp     rcx, rax
0x14002575f  jz      short loc_140025787
0x140025761  test    dword ptr [rcx+2Ch], 400000h
0x140025768  jz      short loc_140025787
0x14002576a  mov     rcx, [rcx+18h]
0x14002576e  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x140025775  mov     edx, 14h
0x14002577a  mov     [rsp+80h+var_60], r13
0x14002577f  mov     r9, r15
0x140025782  call    WPP_SF_qZ
0x140025787  xor     r9d, r9d
0x14002578a  mov     r8b, 1
0x14002578d  mov     rdx, r15
0x140025790  mov     rcx, rsi
0x140025793  call    DfscNetUseRelease
0x140025798  xor     r13d, r13d
0x14002579b  mov     ebx, eax
0x14002579d  mov     r15d, r13d
0x1400257a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400257a7  lea     rax, WPP_GLOBAL_Control
0x1400257ae  cmp     rcx, rax
0x1400257b1  jz      short loc_1400257E4
0x1400257b3  test    dword ptr [rcx+2Ch], 400000h
0x1400257ba  jz      short loc_1400257E4
0x1400257bc  mov     rcx, [rcx+18h]
0x1400257c0  lea     rax, aWasNot; "WAS NOT"
0x1400257c7  test    ebx, ebx
0x1400257c9  lea     r9, aWas; "WAS"
0x1400257d0  lea     edx, [r13+15h]
0x1400257d4  cmovz   r9, rax
0x1400257d8  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400257df  call    WPP_SF_S
0x1400257e4  test    ebx, ebx
0x1400257e6  jz      loc_14002586C
0x1400257ec  movzx   r13d, [rbp+DestinationString.Length]
0x1400257f1  xor     ebx, ebx
0x1400257f3  test    r13w, r13w
0x1400257f7  jz      short loc_14002586E
0x1400257f9  mov     rcx, [rbp+DestinationString.Buffer]
0x1400257fd  test    rcx, rcx
0x140025800  jz      short loc_14002586E
0x140025802  cmp     [rcx], bx
0x140025805  jz      short loc_14002586E
0x140025807  test    r14, r14
0x14002580a  jz      short loc_14002586E
0x14002580c  mov     rdx, rcx; Src
0x14002580f  mov     r8d, r13d; Size
0x140025812  lea     rcx, [r14+4]; void *
0x140025816  mov     ebx, r13d
0x140025819  call    memmove
0x14002581e  mov     eax, dword ptr [rbp+arg_20]
0x140025821  mov     [r14], eax
0x140025824  lea     eax, [r13+6]
0x140025828  shr     rbx, 1
0x14002582b  mov     [r12], eax
0x14002582f  xor     eax, eax
0x140025831  mov     [r14+rbx*2+4], ax
0x140025837  mov     rcx, cs:WPP_GLOBAL_Control
0x14002583e  lea     rax, WPP_GLOBAL_Control
0x140025845  cmp     rcx, rax
0x140025848  jz      short loc_140025868
0x14002584a  test    dword ptr [rcx+2Ch], 400000h
0x140025851  jz      short loc_140025868
0x140025853  mov     eax, [r12]
0x140025857  lea     r9, [r14+4]
0x14002585b  mov     rcx, [rcx+18h]
0x14002585f  mov     dword ptr [rsp+80h+var_60], eax
0x140025863  call    WPP_SF_SD
0x140025868  xor     ebx, ebx
0x14002586a  jmp     short loc_14002587F
0x14002586c  xor     ebx, ebx
0x14002586e  mov     [r12], ebx
0x140025872  test    r14, r14
0x140025875  jz      short loc_14002587F
0x140025877  mov     [r14+4], bx
0x14002587c  mov     [r14], ebx
0x14002587f  cmp     [rbp+var_50], bl
0x140025882  jz      short loc_140025890
0x140025884  call    cs:__imp_PsRevertToSelf
0x14002588b  nop     dword ptr [rax+rax+00h]
0x140025890  test    r15, r15
0x140025893  jz      short loc_1400258A6
0x140025895  xor     r9d, r9d
0x140025898  xor     r8d, r8d
0x14002589b  mov     rdx, r15
0x14002589e  mov     rcx, rsi
0x1400258a1  call    DfscNetUseRelease
0x1400258a6  xor     r15d, r15d
0x1400258a9  mov     rcx, [rbp+DestinationString.Buffer]; P
0x1400258ad  test    rcx, rcx
0x1400258b0  jz      short loc_1400258C4
0x1400258b2  xor     edx, edx; Tag
0x1400258b4  call    cs:__imp_ExFreePoolWithTag
0x1400258bb  nop     dword ptr [rax+rax+00h]
0x1400258c0  mov     [rbp+DestinationString.Buffer], r15
0x1400258c4  mov     rcx, rsi
0x1400258c7  call    DfscGetDriveLetterNetUseTable
0x1400258cc  mov     rdx, rax
0x1400258cf  call    DfscNetUseTableDump
0x1400258d4  mov     rcx, rsi
0x1400258d7  call    DfscGetDevicelessNetUseTable
0x1400258dc  mov     rdx, rax
0x1400258df  call    DfscNetUseTableDump
0x1400258e4  mov     rcx, rsi
0x1400258e7  call    DfscGetCredTable
0x1400258ec  mov     rcx, rax; Table
0x1400258ef  call    DfscCredTableDump
0x1400258f4  mov     rbx, [rsp+80h+arg_0]
0x1400258fc  mov     eax, edi
0x1400258fe  add     rsp, 80h
0x140025905  pop     r15
0x140025907  pop     r14
0x140025909  pop     r13
  ... truncated ...
```
