# DfscCredGetKeymgrCredentials

- ea: `0x140012158`
- end: `0x1400123af`
- name: `DfscCredGetKeymgrCredentials`
- size: `599`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2, DWORD, struct _LUID *, unsigned __int16 *, __int64, ULONG_PTR *BugCheckParameter3)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140017458`

## callees

- `0x140002340`
- `0x1400026a4`
- `0x1400028f4`
- `0x140012158`
- `0x140012770`
- `0x140024ff0`
- `0x1400252b0`

## import_xrefs

- `ntoskrnl!RtlCopyLuid` at `0x14001219f`
- `ntoskrnl!RtlCopyLuid` at `0x14001219f`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1400121e5`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x1400121e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001233d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001233d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012331`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012331`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400121c8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400121c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400121b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400121b6`

## pseudocode

```c
__int64 __fastcall DfscCredGetKeymgrCredentials(
        ULONG_PTR BugCheckParameter2,
        DWORD a2,
        struct _LUID *a3,
        unsigned __int16 *a4,
        __int64 a5,
        ULONG_PTR *BugCheckParameter3)
{
  ULONG_PTR *v6; // r15
  __int128 v10; // xmm0
  ULONG_PTR v11; // rbx
  _QWORD *v12; // rax
  unsigned int v13; // edi
  unsigned int v14; // eax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int128 Buffer; // [rsp+30h] [rbp-30h] BYREF
  _LUID DestinationLuid[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+50h] [rbp-10h]
  PVOID NodeOrParent; // [rsp+90h] [rbp+30h] BYREF
  TABLE_SEARCH_RESULT SearchResult; // [rsp+98h] [rbp+38h] BYREF

  v6 = BugCheckParameter3;
  v20 = 0;
  NodeOrParent = 0;
  SearchResult = TableEmptyTree;
  *BugCheckParameter3 = 0;
  Buffer = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  RtlCopyLuid((PLUID)&DestinationLuid[0].HighPart, a3);
  v10 = *(_OWORD *)a4;
  DestinationLuid[0].LowPart = a2;
  Buffer = v10;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(BugCheckParameter2 + 104), 1u);
  v11 = 0;
  v12 = RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)BugCheckParameter2, &Buffer, &NodeOrParent, &SearchResult);
  if ( v12 )
  {
    v11 = v12[4];
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 4));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_521f112f0c4c3c3f435a4c29cad4d330_Traceguids,
        v11,
        *(_DWORD *)(v11 + 4));
    }
  }
  BugCheckParameter3 = (ULONG_PTR *)v11;
  if ( v11 )
  {
    v13 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 4));
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
    {
      goto LABEL_20;
    }
    v16 = 14;
LABEL_19:
    WPP_SF_qD(v15->AttachedDevice, v16, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids, v11, *(_DWORD *)(v11 + 4));
LABEL_20:
    *v6 = v11;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(a5 + 40) != 1 )
  {
    v13 = 0;
    goto LABEL_21;
  }
  v14 = DfscCredCreateKeymgrCredentials(a4, a5, &BugCheckParameter3);
  v11 = (ULONG_PTR)BugCheckParameter3;
  v13 = v14;
  if ( !v14 )
  {
    v13 = DfscCredTableStore(BugCheckParameter2, (ULONG_PTR)BugCheckParameter3, &Buffer, NodeOrParent, SearchResult);
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_20;
      if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          (unsigned int)WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids,
          v11,
          (__int64)a4);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
      {
        goto LABEL_20;
      }
      v16 = 13;
      goto LABEL_19;
    }
  }
LABEL_21:
  ExReleaseResourceLite((PERESOURCE)(BugCheckParameter2 + 104));
  KeLeaveCriticalRegion();
  if ( v11 )
    DfscCredRelease(v11);
  if ( v13
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    WPP_SF_DZ(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids,
      v13,
      (__int64)a4);
  }
  return v13;
}

```

## disassembly

```asm
0x140012158  mov     [rsp-28h+arg_10], rbx
0x14001215d  mov     [rsp-28h+arg_18], rsi
0x140012162  push    rbp
0x140012163  push    rdi
0x140012164  push    r12
0x140012166  push    r14
0x140012168  push    r15
0x14001216a  mov     rbp, rsp
0x14001216d  sub     rsp, 60h
0x140012171  mov     r15, [rbp+BugCheckParameter3]
0x140012175  xor     eax, eax
0x140012177  xorps   xmm0, xmm0
0x14001217a  mov     [rbp+var_10], rax
0x14001217e  mov     ebx, edx
0x140012180  mov     [rbp+NodeOrParent], rax
0x140012184  mov     r14, rcx
0x140012187  mov     [rbp+SearchResult], eax
0x14001218a  mov     rdx, r8; SourceLuid
0x14001218d  mov     [r15], rax
0x140012190  lea     rcx, [rbp+DestinationLuid.HighPart]; DestinationLuid
0x140012194  mov     rsi, r9
0x140012197  movups  [rbp+Buffer], xmm0
0x14001219b  movups  xmmword ptr [rbp+DestinationLuid.LowPart], xmm0
0x14001219f  call    cs:__imp_RtlCopyLuid
0x1400121a6  nop     dword ptr [rax+rax+00h]
0x1400121ab  movups  xmm0, xmmword ptr [rsi]
0x1400121ae  mov     [rbp+DestinationLuid.LowPart], ebx
0x1400121b1  movdqu  [rbp+Buffer], xmm0
0x1400121b6  call    cs:__imp_KeEnterCriticalRegion
0x1400121bd  nop     dword ptr [rax+rax+00h]
0x1400121c2  mov     dl, 1; Wait
0x1400121c4  lea     rcx, [r14+68h]; Resource
0x1400121c8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400121cf  nop     dword ptr [rax+rax+00h]
0x1400121d4  lea     r9, [rbp+SearchResult]; SearchResult
0x1400121d8  mov     rcx, r14; Table
0x1400121db  lea     r8, [rbp+NodeOrParent]; NodeOrParent
0x1400121df  xor     ebx, ebx
0x1400121e1  lea     rdx, [rbp+Buffer]; Buffer
0x1400121e5  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x1400121ec  nop     dword ptr [rax+rax+00h]
0x1400121f1  lea     rdx, WPP_GLOBAL_Control
0x1400121f8  test    rax, rax
0x1400121fb  jz      short loc_140012240
0x1400121fd  mov     rbx, [rax+20h]
0x140012201  lock inc dword ptr [rbx+4]
0x140012205  mov     rcx, cs:WPP_GLOBAL_Control
0x14001220c  cmp     rcx, rdx
0x14001220f  jz      short loc_140012240
0x140012211  test    dword ptr [rcx+2Ch], 400000h
0x140012218  jz      short loc_140012240
0x14001221a  mov     eax, [rbx+4]
0x14001221d  lea     r8, WPP_521f112f0c4c3c3f435a4c29cad4d330_Traceguids
0x140012224  mov     rcx, [rcx+18h]
0x140012228  mov     edx, 0Ah
0x14001222d  mov     r9, rbx
0x140012230  mov     [rsp+60h+var_40], eax
0x140012234  call    WPP_SF_qD
0x140012239  lea     rdx, WPP_GLOBAL_Control
0x140012240  mov     [rbp+BugCheckParameter3], rbx
0x140012244  test    rbx, rbx
0x140012247  jnz     loc_1400122F2
0x14001224d  mov     rdx, [rbp+arg_20]
0x140012251  cmp     dword ptr [rdx+28h], 1
0x140012255  jz      short loc_14001225E
0x140012257  xor     edi, edi
0x140012259  jmp     loc_14001232D
0x14001225e  lea     r8, [rbp+BugCheckParameter3]
0x140012262  mov     rcx, rsi
0x140012265  call    DfscCredCreateKeymgrCredentials
0x14001226a  mov     rbx, [rbp+BugCheckParameter3]
0x14001226e  mov     edi, eax
0x140012270  test    eax, eax
0x140012272  jnz     loc_14001232D
0x140012278  mov     eax, [rbp+SearchResult]
0x14001227b  lea     r8, [rbp+Buffer]; Buffer
0x14001227f  mov     r9, [rbp+NodeOrParent]; NodeOrParent
0x140012283  mov     rdx, rbx; BugCheckParameter3
0x140012286  mov     rcx, r14; BugCheckParameter2
0x140012289  mov     [rsp+60h+var_40], eax; TABLE_SEARCH_RESULT
0x14001228d  call    DfscCredTableStore
0x140012292  mov     edi, eax
0x140012294  test    eax, eax
0x140012296  jnz     loc_14001232D
0x14001229c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122a3  lea     rdx, WPP_GLOBAL_Control
0x1400122aa  cmp     rcx, rdx
0x1400122ad  jz      short loc_14001232A
0x1400122af  bt      dword ptr [rcx+2Ch], 16h
0x1400122b4  jnb     short loc_1400122D8
0x1400122b6  mov     rcx, [rcx+18h]
0x1400122ba  lea     edx, [rax+0Ch]
0x1400122bd  mov     r9, rbx
0x1400122c0  mov     qword ptr [rsp+60h+var_40], rsi
0x1400122c5  lea     r8, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids
0x1400122cc  call    WPP_SF_qZ
0x1400122d1  lea     rdx, WPP_GLOBAL_Control
0x1400122d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122df  cmp     rcx, rdx
0x1400122e2  jz      short loc_14001232A
0x1400122e4  bt      dword ptr [rcx+2Ch], 16h
0x1400122e9  jnb     short loc_14001232A
0x1400122eb  mov     edx, 0Dh
0x1400122f0  jmp     short loc_140012310
0x1400122f2  xor     edi, edi
0x1400122f4  lock inc dword ptr [rbx+4]
0x1400122f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122ff  cmp     rcx, rdx
0x140012302  jz      short loc_14001232A
0x140012304  test    dword ptr [rcx+2Ch], 400000h
0x14001230b  jz      short loc_14001232A
0x14001230d  lea     edx, [rdi+0Eh]
0x140012310  mov     eax, [rbx+4]
0x140012313  lea     r8, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids
0x14001231a  mov     rcx, [rcx+18h]
0x14001231e  mov     r9, rbx
0x140012321  mov     [rsp+60h+var_40], eax
0x140012325  call    WPP_SF_qD
0x14001232a  mov     [r15], rbx
0x14001232d  lea     rcx, [r14+68h]; Resource
0x140012331  call    cs:__imp_ExReleaseResourceLite
0x140012338  nop     dword ptr [rax+rax+00h]
0x14001233d  call    cs:__imp_KeLeaveCriticalRegion
0x140012344  nop     dword ptr [rax+rax+00h]
0x140012349  test    rbx, rbx
0x14001234c  jz      short loc_140012356
0x14001234e  mov     rcx, rbx; BugCheckParameter3
0x140012351  call    DfscCredRelease
0x140012356  test    edi, edi
0x140012358  jz      short loc_140012393
0x14001235a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012361  lea     rax, WPP_GLOBAL_Control
0x140012368  cmp     rcx, rax
0x14001236b  jz      short loc_140012393
0x14001236d  test    dword ptr [rcx+2Ch], 100000h
0x140012374  jz      short loc_140012393
0x140012376  mov     rcx, [rcx+18h]
0x14001237a  lea     r8, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids
0x140012381  mov     edx, 0Fh
0x140012386  mov     qword ptr [rsp+60h+var_40], rsi
0x14001238b  mov     r9d, edi
0x14001238e  call    WPP_SF_DZ
0x140012393  lea     r11, [rsp+60h+var_s0]
0x140012398  mov     eax, edi
0x14001239a  mov     rbx, [r11+40h]
0x14001239e  mov     rsi, [r11+48h]
0x1400123a2  mov     rsp, r11
0x1400123a5  pop     r15
0x1400123a7  pop     r14
0x1400123a9  pop     r12
0x1400123ab  pop     rdi
0x1400123ac  pop     rbp
0x1400123ad  retn
```
