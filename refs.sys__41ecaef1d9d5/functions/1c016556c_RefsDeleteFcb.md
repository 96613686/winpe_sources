# RefsDeleteFcb

- ea: `0x1c016556c`
- end: `0x1c0165985`
- name: `RefsDeleteFcb`
- size: `1049`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00588cc`
- `0x1c0164f98`
- `0x1c0179614`

## callees

- `0x1c000384c`
- `0x1c0003be0`
- `0x1c00058c0`
- `0x1c003aa9c`
- `0x1c003ab30`
- `0x1c003fa08`
- `0x1c0068960`
- `0x1c00a7bb8`
- `0x1c014d624`
- `0x1c0163094`
- `0x1c016556c`
- `0x1c016598c`
- `0x1c01659f4`
- `0x1c01c70d8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c0165929`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0165929`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01656b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0165741`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01656b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0165741`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c0165657`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c0165657`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0165840`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0165840`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01657fa`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0165865`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01657fa`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0165865`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1c0165672`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1c0165672`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1c01657c2`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1c01657c2`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x1c01658ec`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x1c01658ec`

## pseudocode

```c
void __fastcall RefsDeleteFcb(__int64 a1, PVOID *a2, _BYTE *a3)
{
  _DWORD *v4; // rdx
  __int64 v6; // rsi
  bool v7; // r12
  __int64 **v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // r15
  __int64 *v13; // rdi
  int v14; // r14d
  _QWORD *v15; // rcx
  __int64 v16; // rcx
  struct _ERESOURCE *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rcx
  PVOID *v21; // rcx
  char *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD *v24; // r8
  CmsReferenced *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  PVOID v31; // rcx
  _BYTE *v32; // rax
  __int64 *v33; // rcx
  _DWORD *v34; // rcx
  int v35; // eax
  struct _PAGED_LOOKASIDE_LIST *v36; // rcx
  __int128 Buffer; // [rsp+28h] [rbp-60h] BYREF
  __int64 v39; // [rsp+38h] [rbp-50h]

  v4 = *a2;
  v6 = a1;
  v7 = (*(_DWORD *)(a1 + 12) & 0x20) != 0 && (v4[1] & 0x2000000) != 0;
  if ( (*(_DWORD *)(*((_QWORD *)v4 + 11) + 4LL) & 0x2000) != 0 && (*(_DWORD *)(a1 + 4) & 0x40000000) == 0 )
    __int2c();
  RefsFreeSnapshotsForFcb(a1);
  v9 = 0;
  if ( !v7 )
  {
    v10 = (__int64 *)((char *)*a2 + 72);
    v11 = *v10;
    if ( *v10 )
    {
      if ( *(__int64 **)(v11 + 8) != v10 || (v8 = (__int64 **)*((_QWORD *)*a2 + 10), *v8 != v10) )
        __fastfail(3u);
      *v8 = (__int64 *)v11;
      *(_QWORD *)(v11 + 8) = v8;
      *((_QWORD *)*a2 + 9) = 0;
    }
  }
  do
  {
    v12 = *a2;
    v13 = *(__int64 **)(v6 + 48);
    v14 = *(unsigned __int16 *)(v6 + 42);
    if ( v13 )
    {
      if ( v14 == 1 )
        v13 = (__int64 *)(v6 + 48);
      do
      {
        v15 = (_QWORD *)*v13;
        if ( *v13 && v15 == v12 )
        {
          if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v15[12] + 64LL))
            && ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*v13 + 96) + 64LL)) == 1 )
          {
            RefsFreeSnapshotsForFcb(v6);
          }
          v16 = *v13;
          if ( *(_WORD *)*v13 == 2050 )
            v17 = (struct _ERESOURCE *)(*(_QWORD *)(v16 + 96) + 64LL);
          else
            v17 = *(struct _ERESOURCE **)(v16 + 8);
          ExReleaseResourceLite(v17);
          v9 = 0;
          *v13 = 0;
          if ( *(_WORD *)(v6 + 42) == 1 )
            *(_WORD *)(v6 + 42) = 0;
        }
        ++v13;
        --v14;
      }
      while ( v14 );
    }
    v18 = *(_QWORD *)(v6 + 104);
    if ( v6 == v18 )
      break;
    v6 = *(_QWORD *)(v6 + 104);
  }
  while ( v18 );
  if ( !v7 )
  {
    if ( *(PVOID *)(a1 + 56) == *a2 )
    {
      *(_QWORD *)(a1 + 56) = 0;
    }
    else
    {
      v19 = *(_QWORD *)(a1 + 104);
      if ( *(PVOID *)(v19 + 56) == *a2 )
        *(_QWORD *)(v19 + 56) = 0;
    }
    v20 = *a2;
    if ( *((_QWORD *)*a2 + 13) )
    {
      if ( !v20[36] )
        goto LABEL_40;
      RefsReleaseOneFilePagingIo(v20, *a2, 0);
      while ( 1 )
      {
        v20 = *a2;
LABEL_40:
        if ( !(unsigned __int8)MsIsFastResourceHeld(v20[13], v8, v9) )
          break;
        ExReleaseResourceLite(*((PERESOURCE *)*a2 + 13));
      }
    }
    v21 = (PVOID *)*a2;
    if ( **((_WORD **)*a2 + 12) == 2117 && v21[13] )
    {
      RefsFreeEresource(v21[13]);
      *((_QWORD *)*a2 + 13) = 0;
      v21 = (PVOID *)*a2;
    }
    RefsDeleteNonpagedFcb(v21[12]);
    *((_QWORD *)*a2 + 12) = 0;
    v22 = (char *)*a2;
    if ( (*((_DWORD *)*a2 + 1) & 0x40) != 0 )
    {
      v39 = 0;
      Buffer = *(_OWORD *)(v22 + 8);
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(*((_QWORD *)v22 + 11) + 704LL), &Buffer);
      *((_DWORD *)*a2 + 1) &= ~0x40u;
    }
  }
  v23 = *a2;
  if ( *((_QWORD *)*a2 + 27) )
  {
    RefsFreeFcbUsnRecord(a1, a2, v9);
    v23 = *a2;
  }
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v23[11] + 536LL));
  *a3 = 0;
  v24 = *a2;
  v25 = (CmsReferenced *)*((_QWORD *)*a2 + 30);
  if ( v25 )
  {
    MsReleaseTable(v25);
    *((_QWORD *)*a2 + 30) = 0;
    v24 = *a2;
  }
  if ( v24[23] )
  {
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v24[11] + 592LL));
    RemoveReferenceSharedSecurityUnsafe((char *)*a2 + 184);
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*((_QWORD *)*a2 + 11) + 592LL));
    v24 = *a2;
  }
  v26 = RefsAddStructToRollbackList(a1, 2083, v24, 0);
  if ( v26 )
    RefsProcessRollbackStruct(v27, v26, 16);
  v28 = *(_QWORD *)(a1 + 104);
  if ( a1 != v28 )
  {
    v29 = RefsAddStructToRollbackList(v28, 2083, *a2, 0);
    if ( v29 )
      RefsProcessRollbackStruct(v30, v29, 16);
  }
  if ( !v7 )
  {
    v31 = *a2;
    v32 = (_BYTE *)*((_QWORD *)*a2 + 28);
    if ( v32 )
    {
      *v32 = 1;
      v31 = *a2;
    }
    if ( (*((_DWORD *)v31 + 1) & 4) == 0 )
    {
      FsRtlTeardownPerFileContexts((PVOID *)v31 + 29);
      v31 = *a2;
    }
    v33 = (__int64 *)*((_QWORD *)v31 + 32);
    if ( v33 && v33 != &ProtogonIndexFileKey )
      RefsFreeFileKey();
  }
  v34 = *a2;
  v35 = *((_DWORD *)*a2 + 1);
  if ( v7 )
  {
    v34[1] = v35 | 0x4000000;
  }
  else if ( (v35 & 2) != 0 )
  {
    ExFreePoolWithTag(v34, 0);
  }
  else
  {
    v36 = &RefsFcbIndexLookasideList;
    if ( (v35 & 0x400) == 0 )
      v36 = &RefsFcbDataLookasideList;
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v36, *a2);
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x1c016556c  mov     [rsp+arg_18], rbx
0x1c0165571  push    rbp
0x1c0165572  push    rsi
0x1c0165573  push    rdi
0x1c0165574  push    r12
0x1c0165576  push    r13
0x1c0165578  push    r14
0x1c016557a  push    r15
0x1c016557c  sub     rsp, 50h
0x1c0165580  mov     rax, cs:__security_cookie
0x1c0165587  xor     rax, rsp
0x1c016558a  mov     [rsp+88h+var_48], rax
0x1c016558f  mov     eax, [rcx+0Ch]
0x1c0165592  mov     rbx, rdx
0x1c0165595  mov     rdx, [rdx]
0x1c0165598  mov     rbp, rcx
0x1c016559b  mov     [rsp+88h+var_68], r8
0x1c01655a0  mov     rsi, rcx
0x1c01655a3  mov     ecx, 1
0x1c01655a8  test    al, 20h
0x1c01655aa  jz      short loc_1C01655BA
0x1c01655ac  test    dword ptr [rdx+4], 2000000h
0x1c01655b3  jz      short loc_1C01655BA
0x1c01655b5  mov     r12b, cl
0x1c01655b8  jmp     short loc_1C01655BD
0x1c01655ba  xor     r12b, r12b
0x1c01655bd  mov     rax, [rdx+58h]
0x1c01655c1  test    dword ptr [rax+4], 2000h
0x1c01655c8  jz      short loc_1C01655D5
0x1c01655ca  test    dword ptr [rbp+4], 40000000h
0x1c01655d1  jnz     short loc_1C01655D5
0x1c01655d3  int     2Ch; Windows NT - assertion failure
0x1c01655d5  mov     rcx, rbp
0x1c01655d8  call    RefsFreeSnapshotsForFcb
0x1c01655dd  xor     r8d, r8d
0x1c01655e0  test    r12b, r12b
0x1c01655e3  jnz     short loc_1C0165619
0x1c01655e5  mov     rax, [rbx]
0x1c01655e8  add     rax, 48h ; 'H'
0x1c01655ec  mov     rcx, [rax]
0x1c01655ef  test    rcx, rcx
0x1c01655f2  jz      short loc_1C0165619
0x1c01655f4  cmp     [rcx+8], rax
0x1c01655f8  jnz     loc_1C01656A5
0x1c01655fe  mov     rdx, [rax+8]
0x1c0165602  cmp     [rdx], rax
0x1c0165605  jnz     loc_1C01656A5
0x1c016560b  mov     [rdx], rcx
0x1c016560e  mov     [rcx+8], rdx
0x1c0165612  mov     rax, [rbx]
0x1c0165615  mov     [rax+48h], r8
0x1c0165619  mov     r13d, 1
0x1c016561f  mov     r15, [rbx]
0x1c0165622  lea     rax, [rsi+30h]
0x1c0165626  mov     rdi, [rax]
0x1c0165629  movzx   r14d, word ptr [rsi+2Ah]
0x1c016562e  test    rdi, rdi
0x1c0165631  jz      loc_1C01656DC
0x1c0165637  cmp     r14d, r13d
0x1c016563a  cmovz   rdi, rax
0x1c016563e  mov     rcx, [rdi]
0x1c0165641  test    rcx, rcx
0x1c0165644  jz      loc_1C01656CE
0x1c016564a  cmp     rcx, r15
0x1c016564d  jnz     short loc_1C01656CE
0x1c016564f  mov     rcx, [rcx+60h]
0x1c0165653  add     rcx, 40h ; '@'; Resource
0x1c0165657  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1c016565e  nop     dword ptr [rax+rax+00h]
0x1c0165663  test    al, al
0x1c0165665  jz      short loc_1C016568E
0x1c0165667  mov     rax, [rdi]
0x1c016566a  mov     rcx, [rax+60h]
0x1c016566e  add     rcx, 40h ; '@'; Resource
0x1c0165672  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1c0165679  nop     dword ptr [rax+rax+00h]
0x1c016567e  cmp     eax, r13d
0x1c0165681  jnz     short loc_1C016568E
0x1c0165683  mov     rdx, [rdi]
0x1c0165686  mov     rcx, rsi
0x1c0165689  call    RefsFreeSnapshotsForFcb
0x1c016568e  mov     rcx, [rdi]
0x1c0165691  mov     eax, 802h
0x1c0165696  cmp     ax, [rcx]
0x1c0165699  jnz     short loc_1C01656AC
0x1c016569b  mov     rcx, [rcx+60h]
0x1c016569f  add     rcx, 40h ; '@'
0x1c01656a3  jmp     short loc_1C01656B0
0x1c01656a5  mov     ecx, 3
0x1c01656aa  int     29h; Win8: RtlFailFast(ecx)
0x1c01656ac  mov     rcx, [rcx+8]; Resource
0x1c01656b0  call    cs:__imp_ExReleaseResourceLite
0x1c01656b7  nop     dword ptr [rax+rax+00h]
0x1c01656bc  xor     r8d, r8d
0x1c01656bf  mov     [rdi], r8
0x1c01656c2  cmp     [rsi+2Ah], r13w
0x1c01656c7  jnz     short loc_1C01656CE
0x1c01656c9  mov     [rsi+2Ah], r8w
0x1c01656ce  add     rdi, 8
0x1c01656d2  add     r14d, 0FFFFFFFFh
0x1c01656d6  jnz     loc_1C016563E
0x1c01656dc  mov     rax, [rsi+68h]
0x1c01656e0  cmp     rsi, rax
0x1c01656e3  jz      short loc_1C01656F1
0x1c01656e5  mov     rsi, rax
0x1c01656e8  test    rax, rax
0x1c01656eb  jnz     loc_1C016561F
0x1c01656f1  mov     r13, [rsp+88h+var_68]
0x1c01656f6  xor     esi, esi
0x1c01656f8  test    r12b, r12b
0x1c01656fb  jnz     loc_1C01657D5
0x1c0165701  mov     rcx, [rbx]
0x1c0165704  cmp     [rbp+38h], rcx
0x1c0165708  jnz     short loc_1C0165710
0x1c016570a  mov     [rbp+38h], rsi
0x1c016570e  jmp     short loc_1C016571E
0x1c0165710  mov     rax, [rbp+68h]
0x1c0165714  cmp     [rax+38h], rcx
0x1c0165718  jnz     short loc_1C016571E
0x1c016571a  mov     [rax+38h], rsi
0x1c016571e  mov     rcx, [rbx]
0x1c0165721  cmp     [rcx+68h], rsi
0x1c0165725  jz      short loc_1C016575D
0x1c0165727  cmp     [rcx+120h], rsi
0x1c016572e  jz      short loc_1C0165750
0x1c0165730  mov     rdx, rcx
0x1c0165733  call    RefsReleaseOneFilePagingIo
0x1c0165738  jmp     short loc_1C016574D
0x1c016573a  mov     rcx, [rbx]
0x1c016573d  mov     rcx, [rcx+68h]; Resource
0x1c0165741  call    cs:__imp_ExReleaseResourceLite
0x1c0165748  nop     dword ptr [rax+rax+00h]
0x1c016574d  mov     rcx, [rbx]
0x1c0165750  mov     rcx, [rcx+68h]
0x1c0165754  call    MsIsFastResourceHeld
0x1c0165759  test    al, al
0x1c016575b  jnz     short loc_1C016573A
0x1c016575d  mov     rcx, [rbx]
0x1c0165760  mov     edx, 845h
0x1c0165765  mov     rax, [rcx+60h]
0x1c0165769  cmp     [rax], dx
0x1c016576c  jnz     short loc_1C0165789
0x1c016576e  mov     rax, [rcx+68h]
0x1c0165772  test    rax, rax
0x1c0165775  jz      short loc_1C0165789
0x1c0165777  mov     rcx, rax; P
0x1c016577a  call    RefsFreeEresource
0x1c016577f  mov     rax, [rbx]
0x1c0165782  mov     [rax+68h], rsi
0x1c0165786  mov     rcx, [rbx]
0x1c0165789  mov     rcx, [rcx+60h]; Entry
0x1c016578d  call    RefsDeleteNonpagedFcb
0x1c0165792  mov     rax, [rbx]
0x1c0165795  mov     [rax+60h], rsi
0x1c0165799  mov     rcx, [rbx]
0x1c016579c  mov     eax, [rcx+4]
0x1c016579f  test    al, 40h
0x1c01657a1  jz      short loc_1C01657D5
0x1c01657a3  mov     [rsp+88h+var_50], rsi
0x1c01657a8  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1c01657ad  movups  xmm0, xmmword ptr [rcx+8]
0x1c01657b1  movdqu  [rsp+88h+Buffer], xmm0
0x1c01657b7  mov     rcx, [rcx+58h]
0x1c01657bb  add     rcx, 2C0h; Table
0x1c01657c2  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1c01657c9  nop     dword ptr [rax+rax+00h]
0x1c01657ce  mov     rax, [rbx]
0x1c01657d1  and     dword ptr [rax+4], 0FFFFFFBFh
0x1c01657d5  mov     rcx, [rbx]
0x1c01657d8  cmp     [rcx+0D8h], rsi
0x1c01657df  jz      short loc_1C01657EF
0x1c01657e1  mov     rdx, rbx
0x1c01657e4  mov     rcx, rbp
0x1c01657e7  call    RefsFreeFcbUsnRecord
0x1c01657ec  mov     rcx, [rbx]
0x1c01657ef  mov     rcx, [rcx+58h]
0x1c01657f3  add     rcx, 218h; Mutex
0x1c01657fa  call    cs:__imp_KeReleaseGuardedMutex
0x1c0165801  nop     dword ptr [rax+rax+00h]
0x1c0165806  mov     [r13+0], sil
0x1c016580a  mov     r8, [rbx]
0x1c016580d  mov     rcx, [r8+0F0h]; this
0x1c0165814  test    rcx, rcx
0x1c0165817  jz      short loc_1C016582B
0x1c0165819  call    MsReleaseTable
0x1c016581e  mov     rax, [rbx]
0x1c0165821  mov     [rax+0F0h], rsi
0x1c0165828  mov     r8, [rbx]
0x1c016582b  cmp     [r8+0B8h], rsi
0x1c0165832  jz      short loc_1C0165874
0x1c0165834  mov     rcx, [r8+58h]
0x1c0165838  mov     edi, 250h
0x1c016583d  add     rcx, rdi; Mutex
0x1c0165840  call    cs:__imp_KeAcquireGuardedMutex
0x1c0165847  nop     dword ptr [rax+rax+00h]
0x1c016584c  mov     rcx, [rbx]
0x1c016584f  add     rcx, 0B8h
0x1c0165856  call    RemoveReferenceSharedSecurityUnsafe
0x1c016585b  mov     rax, [rbx]
0x1c016585e  mov     rcx, [rax+58h]
0x1c0165862  add     rcx, rdi; Mutex
0x1c0165865  call    cs:__imp_KeReleaseGuardedMutex
0x1c016586c  nop     dword ptr [rax+rax+00h]
0x1c0165871  mov     r8, [rbx]
0x1c0165874  mov     r14d, 823h
0x1c016587a  xor     r9d, r9d
0x1c016587d  mov     edx, r14d
0x1c0165880  mov     rcx, rbp
0x1c0165883  call    RefsAddStructToRollbackList
0x1c0165888  mov     edi, 10h
0x1c016588d  test    rax, rax
0x1c0165890  jz      short loc_1C016589D
0x1c0165892  mov     r8d, edi
0x1c0165895  mov     rdx, rax
0x1c0165898  call    RefsProcessRollbackStruct
0x1c016589d  mov     rcx, [rbp+68h]
0x1c01658a1  cmp     rbp, rcx
0x1c01658a4  jz      short loc_1C01658C4
0x1c01658a6  mov     r8, [rbx]
0x1c01658a9  mov     edx, r14d
0x1c01658ac  xor     r9d, r9d
0x1c01658af  call    RefsAddStructToRollbackList
0x1c01658b4  test    rax, rax
0x1c01658b7  jz      short loc_1C01658C4
0x1c01658b9  mov     r8d, edi
0x1c01658bc  mov     rdx, rax
0x1c01658bf  call    RefsProcessRollbackStruct
0x1c01658c4  test    r12b, r12b
0x1c01658c7  jnz     short loc_1C0165918
0x1c01658c9  mov     rcx, [rbx]
0x1c01658cc  mov     rax, [rcx+0E0h]
0x1c01658d3  test    rax, rax
0x1c01658d6  jz      short loc_1C01658DE
0x1c01658d8  mov     byte ptr [rax], 1
0x1c01658db  mov     rcx, [rbx]
0x1c01658de  mov     eax, [rcx+4]
0x1c01658e1  test    al, 4
0x1c01658e3  jnz     short loc_1C01658FB
0x1c01658e5  add     rcx, 0E8h; PerFileContextPointer
0x1c01658ec  call    cs:__imp_FsRtlTeardownPerFileContexts
0x1c01658f3  nop     dword ptr [rax+rax+00h]
0x1c01658f8  mov     rcx, [rbx]
0x1c01658fb  mov     rcx, [rcx+100h]
0x1c0165902  test    rcx, rcx
0x1c0165905  jz      short loc_1C0165918
0x1c0165907  lea     rax, ProtogonIndexFileKey
0x1c016590e  cmp     rcx, rax
0x1c0165911  jz      short loc_1C0165918
0x1c0165913  call    RefsFreeFileKey
0x1c0165918  mov     rcx, [rbx]; P
0x1c016591b  mov     eax, [rcx+4]
0x1c016591e  test    r12b, r12b
0x1c0165921  jnz     short loc_1C0165955
0x1c0165923  test    al, 2
0x1c0165925  jz      short loc_1C0165937
0x1c0165927  xor     edx, edx; Tag
0x1c0165929  call    cs:__imp_ExFreePoolWithTag
0x1c0165930  nop     dword ptr [rax+rax+00h]
0x1c0165935  jmp     short loc_1C016595C
0x1c0165937  mov     rdx, rcx; Entry
0x1c016593a  lea     rcx, RefsFcbIndexLookasideList
0x1c0165941  bt      eax, 0Ah
0x1c0165945  jb      short loc_1C016594E
0x1c0165947  lea     rcx, RefsFcbDataLookasideList; Lookaside
0x1c016594e  call    ExFreeToNPagedLookasideList
0x1c0165953  jmp     short loc_1C016595C
0x1c0165955  bts     eax, 1Ah
0x1c0165959  mov     [rcx+4], eax
0x1c016595c  mov     [rbx], rsi
0x1c016595f  mov     rcx, [rsp+88h+var_48]
0x1c0165964  xor     rcx, rsp; StackCookie
0x1c0165967  call    __security_check_cookie
0x1c016596c  mov     rbx, [rsp+88h+arg_18]
0x1c0165974  add     rsp, 50h
0x1c0165978  pop     r15
0x1c016597a  pop     r14
0x1c016597c  pop     r13
0x1c016597e  pop     r12
0x1c0165980  pop     rdi
0x1c0165981  pop     rsi
0x1c0165982  pop     rbp
0x1c0165983  retn
```
