# CscPathPrefixInsertEntries

- ea: `0x140053338`
- end: `0x1400536ee`
- name: `CscPathPrefixInsertEntries`
- size: `950`
- prototype: `__int64 __fastcall(PERESOURCE Resource, char, char, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140048b74`

## callees

- `0x1400190ec`
- `0x14001a494`
- `0x14001a624`
- `0x14004ae48`
- `0x140053338`
- `0x1400536f4`
- `0x140053870`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140053681`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053681`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140053471`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005351d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140053471`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005351d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400534e5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400534e5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005366e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005366e`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140053498`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140053498`

## pseudocode

```c
__int64 __fastcall CscPathPrefixInsertEntries(
        PERESOURCE Resource,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  struct _ERESOURCE *v6; // rsi
  char v7; // bl
  int v9; // r14d
  int v10; // r15d
  int v11; // r15d
  unsigned int v12; // edi
  unsigned int i; // r12d
  UNICODE_STRING *v14; // r15
  unsigned int Length; // edx
  struct _UNICODE_STRING *v16; // rax
  struct _LIST_ENTRY *v17; // rdi
  struct _LIST_ENTRY *Blink; // rax
  PERESOURCE v19; // rdi
  __int64 UserInList; // rax
  char *v21; // rax
  PERESOURCE *v22; // rcx
  _QWORD *p_Flink; // r12
  _QWORD *v24; // r9
  LIST_ENTRY v26; // [rsp+30h] [rbp-10h] BYREF

  v6 = 0;
  v7 = 0;
  v26 = 0;
  if ( (a2 != 0) == (a4 != 0) )
  {
    v9 = -1073741811;
    v10 = 437;
    goto LABEL_43;
  }
  v9 = 0;
  if ( !a6 )
  {
    v10 = 442;
    goto LABEL_43;
  }
  v11 = 0;
  v26.Blink = &v26;
  v12 = 0;
  v26.Flink = &v26;
  while ( v12 < a6 )
  {
    v9 = CscPathPrefixInserverEntrypValidatePath(a5 + 16LL * v12);
    if ( v9 < 0 )
    {
      v11 = 396;
      break;
    }
    ++v12;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_0447301b51063eaec2a18d83656e135e_Traceguids, v12, v9, v11);
  if ( v9 < 0 )
  {
    v10 = 451;
    goto LABEL_43;
  }
  for ( i = 0; i < a6; ++i )
  {
    v14 = (UNICODE_STRING *)(a5 + 16LL * i);
    Length = v14->Length;
    if ( Length > 4 && v14->Buffer[((unsigned __int64)v14->Length >> 1) - 1] == 92 )
      v14->Length = Length - 2;
    v16 = (struct _UNICODE_STRING *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&Resource[1].Address);
    v17 = (struct _LIST_ENTRY *)v16;
    if ( !v16 )
    {
      v9 = -1073741670;
      v10 = 474;
      goto LABEL_43;
    }
    *v16 = 0;
    v16[1] = 0;
    RtlDuplicateUnicodeString(0, v14, v16 + 1);
    Blink = v26.Blink;
    if ( v26.Blink->Flink != &v26 )
      goto LABEL_36;
    v17->Blink = v26.Blink;
    v17->Flink = &v26;
    Blink->Flink = v17;
    v26.Blink = v17;
  }
  ExAcquireResourceExclusiveLite(Resource, 1u);
  v7 = 1;
  if ( a2 )
  {
    v19 = Resource + 1;
  }
  else
  {
    UserInList = CscPathPrefixpFindUserInList(Resource, a4);
    if ( UserInList )
    {
      v19 = (PERESOURCE)(UserInList + 88);
    }
    else
    {
      v21 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&Resource[1].Address);
      v6 = (struct _ERESOURCE *)v21;
      if ( !v21 )
      {
        v9 = -1073741670;
        v10 = 508;
        goto LABEL_43;
      }
      *((_QWORD *)v21 + 1) = v21;
      v19 = (PERESOURCE)(v21 + 88);
      *(_QWORD *)v21 = v21;
      *((_OWORD *)v21 + 1) = *(_OWORD *)a4;
      *((_OWORD *)v21 + 2) = *(_OWORD *)(a4 + 16);
      *((_OWORD *)v21 + 3) = *(_OWORD *)(a4 + 32);
      *((_OWORD *)v21 + 4) = *(_OWORD *)(a4 + 48);
      *((_DWORD *)v21 + 20) = *(_DWORD *)(a4 + 64);
      *((_QWORD *)v21 + 12) = v21 + 88;
      *((_QWORD *)v21 + 11) = v21 + 88;
    }
  }
  if ( a3 )
  {
    v26.Flink->Blink = v19->SystemResourcesList.Blink;
    v26.Blink->Flink = &v19->SystemResourcesList;
    v19->SystemResourcesList.Blink->Flink = v26.Flink;
    v19->SystemResourcesList.Blink = v26.Blink;
  }
  else
  {
    CscPathPrefixpDeletePrefixList(Resource, v19, 0);
    v19->SystemResourcesList = v26;
    v26.Flink->Blink = &v19->SystemResourcesList;
    v26.Blink->Flink = &v19->SystemResourcesList;
  }
  if ( v6 )
  {
    v22 = *(PERESOURCE **)&Resource[1].ActiveCount;
    if ( *v22 != (PERESOURCE)&Resource[1].OwnerTable )
LABEL_36:
      __fastfail(3u);
    v6->SystemResourcesList.Flink = (struct _LIST_ENTRY *)&Resource[1].OwnerTable;
    v6->SystemResourcesList.Blink = (struct _LIST_ENTRY *)v22;
    *v22 = v6;
    *(_QWORD *)&Resource[1].ActiveCount = v6;
  }
  p_Flink = &v19->SystemResourcesList.Flink->Flink;
  v10 = 0;
  while ( p_Flink != (_QWORD *)v19 )
  {
    v24 = p_Flink;
    p_Flink = (_QWORD *)*p_Flink;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_0447301b51063eaec2a18d83656e135e_Traceguids, v24 + 2);
  }
LABEL_43:
  if ( v7 )
    ExReleaseResourceLite(Resource);
  if ( v9 < 0 )
    CscPathPrefixpDeletePrefixList(Resource, &v26, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_0447301b51063eaec2a18d83656e135e_Traceguids,
      (unsigned int)v9,
      v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140053338  mov     rax, rsp
0x14005333b  mov     [rax+8], rbx
0x14005333f  mov     [rax+20h], r9
0x140053343  mov     [rax+18h], r8b
0x140053347  mov     [rax+10h], dl
0x14005334a  push    rbp
0x14005334b  push    rsi
0x14005334c  push    rdi
0x14005334d  push    r12
0x14005334f  push    r13
0x140053351  push    r14
0x140053353  push    r15
0x140053355  mov     rbp, rsp
0x140053358  sub     rsp, 40h
0x14005335c  xor     r10d, r10d
0x14005335f  lea     r12, WPP_GLOBAL_Control
0x140053366  xor     esi, esi
0x140053368  xor     bl, bl
0x14005336a  test    dl, dl
0x14005336c  xorps   xmm0, xmm0
0x14005336f  mov     r13, rcx
0x140053372  setnz   r10b
0x140053376  xor     eax, eax
0x140053378  test    r9, r9
0x14005337b  movups  [rbp+var_10], xmm0
0x14005337f  setnz   al
0x140053382  cmp     r10d, eax
0x140053385  jnz     short loc_140053398
0x140053387  mov     r14d, 0C000000Dh
0x14005338d  mov     r15d, 1B5h
0x140053393  jmp     loc_14005365F
0x140053398  xor     r14d, r14d
0x14005339b  cmp     [rbp+arg_28], esi
0x14005339e  jnz     short loc_1400533AB
0x1400533a0  mov     r15d, 1BAh
0x1400533a6  jmp     loc_14005365F
0x1400533ab  lea     rax, [rbp+var_10]
0x1400533af  xor     r15d, r15d
0x1400533b2  mov     qword ptr [rbp+var_10+8], rax
0x1400533b6  xor     edi, edi
0x1400533b8  lea     rax, [rbp+var_10]
0x1400533bc  mov     qword ptr [rbp+var_10], rax
0x1400533c0  cmp     edi, [rbp+arg_28]
0x1400533c3  jnb     short loc_1400533E5
0x1400533c5  mov     ecx, edi
0x1400533c7  shl     rcx, 4
0x1400533cb  add     rcx, [rbp+arg_20]
0x1400533cf  call    CscPathPrefixInserverEntrypValidatePath
0x1400533d4  mov     r14d, eax
0x1400533d7  test    eax, eax
0x1400533d9  js      short loc_1400533DF
0x1400533db  inc     edi
0x1400533dd  jmp     short loc_1400533C0
0x1400533df  mov     r15d, 18Ch
0x1400533e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400533ec  cmp     rcx, r12
0x1400533ef  jz      short loc_14005341A
0x1400533f1  mov     eax, [rcx+2Ch]
0x1400533f4  test    al, 20h
0x1400533f6  jz      short loc_14005341A
0x1400533f8  mov     rcx, [rcx+18h]
0x1400533fc  lea     r8, WPP_0447301b51063eaec2a18d83656e135e_Traceguids
0x140053403  mov     edx, 0Ch
0x140053408  mov     [rsp+40h+var_18], r15d
0x14005340d  mov     r9d, edi
0x140053410  mov     [rsp+40h+var_20], r14d
0x140053415  call    WPP_SF_DDd
0x14005341a  test    r14d, r14d
0x14005341d  jns     short loc_14005342A
0x14005341f  mov     r15d, 1C3h
0x140053425  jmp     loc_14005365F
0x14005342a  xor     r12d, r12d
0x14005342d  cmp     r12d, [rbp+arg_28]
0x140053431  jnb     loc_1400534E0
0x140053437  mov     r15d, r12d
0x14005343a  shl     r15, 4
0x14005343e  add     r15, [rbp+arg_20]
0x140053442  movzx   edx, word ptr [r15]
0x140053446  cmp     edx, 4
0x140053449  jbe     short loc_14005346A
0x14005344b  mov     rax, [r15+8]
0x14005344f  mov     ecx, edx
0x140053451  shr     rcx, 1
0x140053454  mov     r8d, 5Ch ; '\'
0x14005345a  cmp     r8w, [rax+rcx*2-2]
0x140053460  jnz     short loc_14005346A
0x140053462  sub     dx, 2
0x140053466  mov     [r15], dx
0x14005346a  lea     rcx, [r13+0C0h]; Lookaside
0x140053471  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140053478  nop     dword ptr [rax+rax+00h]
0x14005347d  mov     rdi, rax
0x140053480  test    rax, rax
0x140053483  jz      short loc_1400534CF
0x140053485  xorps   xmm0, xmm0
0x140053488  lea     r8, [rax+10h]; StringOut
0x14005348c  movups  xmmword ptr [rax], xmm0
0x14005348f  mov     rdx, r15; StringIn
0x140053492  xor     ecx, ecx; Flags
0x140053494  movups  xmmword ptr [rax+10h], xmm0
0x140053498  call    cs:__imp_RtlDuplicateUnicodeString
0x14005349f  nop     dword ptr [rax+rax+00h]
0x1400534a4  mov     rax, qword ptr [rbp+var_10+8]
0x1400534a8  lea     rcx, [rbp+var_10]
0x1400534ac  cmp     [rax], rcx
0x1400534af  jnz     loc_1400535F0
0x1400534b5  mov     [rdi+8], rax
0x1400534b9  lea     rcx, [rbp+var_10]
0x1400534bd  mov     [rdi], rcx
0x1400534c0  inc     r12d
0x1400534c3  mov     [rax], rdi
0x1400534c6  mov     qword ptr [rbp+var_10+8], rdi
0x1400534ca  jmp     loc_14005342D
0x1400534cf  mov     r14d, 0C000009Ah
0x1400534d5  mov     r15d, 1DAh
0x1400534db  jmp     loc_140053658
0x1400534e0  mov     dl, 1; Wait
0x1400534e2  mov     rcx, r13; Resource
0x1400534e5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400534ec  nop     dword ptr [rax+rax+00h]
0x1400534f1  mov     bl, 1
0x1400534f3  cmp     [rbp+arg_8], sil
0x1400534f7  jz      short loc_140053502
0x1400534f9  lea     rdi, [r13+68h]
0x1400534fd  jmp     loc_140053584
0x140053502  mov     r15, [rbp+arg_18]
0x140053506  mov     rcx, r13
0x140053509  mov     rdx, r15
0x14005350c  call    CscPathPrefixpFindUserInList
0x140053511  test    rax, rax
0x140053514  jnz     short loc_140053580
0x140053516  lea     rcx, [r13+0C0h]; Lookaside
0x14005351d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140053524  nop     dword ptr [rax+rax+00h]
0x140053529  mov     rsi, rax
0x14005352c  test    rax, rax
0x14005352f  jnz     short loc_140053542
0x140053531  mov     r14d, 0C000009Ah
0x140053537  mov     r15d, 1FCh
0x14005353d  jmp     loc_140053658
0x140053542  mov     [rax+8], rsi
0x140053546  lea     rdi, [rsi+58h]
0x14005354a  mov     [rax], rsi
0x14005354d  movups  xmm0, xmmword ptr [r15]
0x140053551  movups  xmmword ptr [rax+10h], xmm0
0x140053555  movups  xmm1, xmmword ptr [r15+10h]
0x14005355a  movups  xmmword ptr [rax+20h], xmm1
0x14005355e  movups  xmm0, xmmword ptr [r15+20h]
0x140053563  movups  xmmword ptr [rax+30h], xmm0
0x140053567  movups  xmm1, xmmword ptr [r15+30h]
0x14005356c  movups  xmmword ptr [rax+40h], xmm1
0x140053570  mov     eax, [r15+40h]
0x140053574  mov     [rsi+50h], eax
0x140053577  mov     [rdi+8], rdi
0x14005357b  mov     [rdi], rdi
0x14005357e  jmp     short loc_140053584
0x140053580  lea     rdi, [rax+58h]
0x140053584  cmp     [rbp+arg_10], 0
0x140053588  jz      short loc_1400535B2
0x14005358a  mov     rax, qword ptr [rbp+var_10]
0x14005358e  mov     rcx, [rdi+8]
0x140053592  mov     [rax+8], rcx
0x140053596  mov     rax, qword ptr [rbp+var_10+8]
0x14005359a  mov     [rax], rdi
0x14005359d  mov     rax, qword ptr [rbp+var_10]
0x1400535a1  mov     rcx, [rdi+8]
0x1400535a5  mov     [rcx], rax
0x1400535a8  mov     rax, qword ptr [rbp+var_10+8]
0x1400535ac  mov     [rdi+8], rax
0x1400535b0  jmp     short loc_1400535DE
0x1400535b2  xor     r8d, r8d
0x1400535b5  mov     rdx, rdi
0x1400535b8  mov     rcx, r13
0x1400535bb  call    CscPathPrefixpDeletePrefixList
0x1400535c0  mov     rax, qword ptr [rbp+var_10]
0x1400535c4  mov     [rdi], rax
0x1400535c7  mov     rax, qword ptr [rbp+var_10+8]
0x1400535cb  mov     [rdi+8], rax
0x1400535cf  mov     rax, qword ptr [rbp+var_10]
0x1400535d3  mov     [rax+8], rdi
0x1400535d7  mov     rax, qword ptr [rbp+var_10+8]
0x1400535db  mov     [rax], rdi
0x1400535de  test    rsi, rsi
0x1400535e1  jz      short loc_140053607
0x1400535e3  lea     rax, [r13+78h]
0x1400535e7  mov     rcx, [rax+8]
0x1400535eb  cmp     [rcx], rax
0x1400535ee  jz      short loc_1400535F7
0x1400535f0  mov     ecx, 3
0x1400535f5  int     29h; Win8: RtlFailFast(ecx)
0x1400535f7  mov     [rsi], rax
0x1400535fa  mov     [rsi+8], rcx
0x1400535fe  mov     [rcx], rsi
0x140053601  mov     [rax+8], rsi
0x140053605  xor     esi, esi
0x140053607  mov     r12, [rdi]
0x14005360a  xor     r15d, r15d
0x14005360d  cmp     r12, rdi
0x140053610  jz      short loc_140053658
0x140053612  lea     rax, WPP_GLOBAL_Control
0x140053619  mov     r9, r12
0x14005361c  mov     r12, [r12]
0x140053620  mov     rcx, cs:WPP_GLOBAL_Control
0x140053627  cmp     rcx, rax
0x14005362a  jz      short loc_140053653
0x14005362c  mov     eax, [rcx+2Ch]
0x14005362f  test    al, 20h
0x140053631  jz      short loc_14005364C
0x140053633  mov     rcx, [rcx+18h]
0x140053637  lea     r8, WPP_0447301b51063eaec2a18d83656e135e_Traceguids
0x14005363e  add     r9, 10h
0x140053642  mov     edx, 0Ah
0x140053647  call    WPP_SF_Z
0x14005364c  lea     rax, WPP_GLOBAL_Control
0x140053653  cmp     r12, rdi
0x140053656  jnz     short loc_140053619
0x140053658  lea     r12, WPP_GLOBAL_Control
0x14005365f  test    rsi, rsi
0x140053662  jz      short loc_14005367A
0x140053664  lea     rcx, [r13+0C0h]; Lookaside
0x14005366b  mov     rdx, rsi; Entry
0x14005366e  call    cs:__imp_ExFreeToPagedLookasideList
0x140053675  nop     dword ptr [rax+rax+00h]
0x14005367a  test    bl, bl
0x14005367c  jz      short loc_14005368D
0x14005367e  mov     rcx, r13; Resource
0x140053681  call    cs:__imp_ExReleaseResourceLite
0x140053688  nop     dword ptr [rax+rax+00h]
0x14005368d  test    r14d, r14d
0x140053690  jns     short loc_1400536A1
0x140053692  xor     r8d, r8d
0x140053695  lea     rdx, [rbp+var_10]
0x140053699  mov     rcx, r13
0x14005369c  call    CscPathPrefixpDeletePrefixList
0x1400536a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400536a8  cmp     rcx, r12
0x1400536ab  jz      short loc_1400536D2
0x1400536ad  mov     edx, [rcx+2Ch]
0x1400536b0  test    dl, 40h
0x1400536b3  jz      short loc_1400536D2
0x1400536b5  mov     rcx, [rcx+18h]
0x1400536b9  lea     r8, WPP_0447301b51063eaec2a18d83656e135e_Traceguids
0x1400536c0  mov     edx, 0Dh
0x1400536c5  mov     [rsp+40h+var_20], r15d
0x1400536ca  mov     r9d, r14d
0x1400536cd  call    WPP_SF_Dd
0x1400536d2  mov     rbx, [rsp+40h+arg_0]
0x1400536da  mov     eax, r14d
0x1400536dd  add     rsp, 40h
0x1400536e1  pop     r15
0x1400536e3  pop     r14
0x1400536e5  pop     r13
0x1400536e7  pop     r12
0x1400536e9  pop     rdi
0x1400536ea  pop     rsi
0x1400536eb  pop     rbp
0x1400536ec  retn
```
