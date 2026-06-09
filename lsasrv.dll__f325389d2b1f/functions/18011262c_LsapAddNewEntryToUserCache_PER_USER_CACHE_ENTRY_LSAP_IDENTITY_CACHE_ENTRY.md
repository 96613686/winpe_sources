# LsapAddNewEntryToUserCache(_PER_USER_CACHE_ENTRY *,_LSAP_IDENTITY_CACHE_ENTRY *)

- ea: `0x18011262c`
- end: `0x180112887`
- name: `?LsapAddNewEntryToUserCache@@YAJPEAU_PER_USER_CACHE_ENTRY@@PEAU_LSAP_IDENTITY_CACHE_ENTRY@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(struct _PER_USER_CACHE_ENTRY *, struct _LSAP_IDENTITY_CACHE_ENTRY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1801124b4`
- `0x180112978`
- `0x180113fd0`

## callees

- `0x1800626ac`
- `0x18011262c`
- `0x180114630`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801126f2`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18011275e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18011277b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180112803`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180112820`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18011284e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801126f2`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18011275e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18011277b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180112803`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180112820`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18011284e`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180112670`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801126c7`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18011273d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801127e2`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180112670`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801126c7`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18011273d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1801127e2`

## pseudocode

```c
__int64 __fastcall LsapAddNewEntryToUserCache(struct _RTL_AVL_TABLE *a1, struct _LSAP_IDENTITY_CACHE_ENTRY *a2)
{
  char v3; // bl
  struct _RTL_AVL_TABLE *v4; // rsi
  struct _LSAP_IDENTITY_CACHE_ENTRY **v5; // rax
  unsigned int v6; // ebx
  _WORD *v7; // rdx
  PVOID inserted; // rbx
  bool v9; // cf
  struct _LSAP_IDENTITY_CACHE_ENTRY *v10; // rcx
  _WORD *v11; // rdx
  PVOID v12; // r14
  struct _LSAP_IDENTITY_CACHE_ENTRY *v13; // rcx
  _WORD *v14; // rdx
  struct _LSAP_IDENTITY_CACHE_ENTRY *Buffer; // [rsp+58h] [rbp+38h] BYREF
  unsigned __int8 NewElement; // [rsp+60h] [rbp+40h] BYREF

  Buffer = a2;
  NewElement = 0;
  v3 = 0;
  if ( !*((_QWORD *)a2 + 8) )
  {
    v4 = a1 + 2;
LABEL_9:
    NewElement = 0;
    if ( !RtlInsertElementGenericTableAvl(a1, &Buffer, 8u, &NewElement) )
    {
      v6 = -1073741801;
      goto LABEL_11;
    }
    if ( !NewElement )
    {
      v6 = -1073741823;
LABEL_11:
      if ( *((_QWORD *)Buffer + 8) )
        RtlDeleteElementGenericTableAvl(v4, &Buffer);
      return v6;
    }
    if ( *((_WORD *)Buffer + 20) )
    {
      v7 = (_WORD *)*((_QWORD *)Buffer + 6);
      if ( v7 )
      {
        if ( *v7 )
        {
          NewElement = 0;
          inserted = RtlInsertElementGenericTableAvl(a1 + 1, &Buffer, 8u, &NewElement);
          if ( !inserted || !NewElement )
          {
            RtlDeleteElementGenericTableAvl(a1, &Buffer);
            if ( *((_QWORD *)Buffer + 8) )
              RtlDeleteElementGenericTableAvl(v4, &Buffer);
            v9 = inserted != 0;
            return v9 ? -1073741823 : -1073741801;
          }
        }
      }
    }
    v6 = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
    {
      v10 = Buffer;
      if ( !*((_WORD *)Buffer + 40) )
        goto LABEL_38;
      v11 = (_WORD *)*((_QWORD *)Buffer + 11);
      if ( !v11 || !*v11 )
        goto LABEL_38;
      NewElement = 0;
      v12 = RtlInsertElementGenericTableAvl(a1 + 3, &Buffer, 8u, &NewElement);
      if ( !v12 || !NewElement )
      {
        RtlDeleteElementGenericTableAvl(a1, &Buffer);
        v13 = Buffer;
        if ( *((_QWORD *)Buffer + 8) )
        {
          RtlDeleteElementGenericTableAvl(v4, &Buffer);
          v13 = Buffer;
        }
        if ( *((_WORD *)v13 + 20) )
        {
          v14 = (_WORD *)*((_QWORD *)v13 + 6);
          if ( v14 )
          {
            if ( *v14 )
              RtlDeleteElementGenericTableAvl(a1 + 1, &Buffer);
          }
        }
        v9 = v12 != 0;
        return v9 ? -1073741823 : -1073741801;
      }
    }
    v10 = Buffer;
LABEL_38:
    _InterlockedIncrement((volatile signed __int32 *)v10 + 1);
    return v6;
  }
  while ( 1 )
  {
    v4 = a1 + 2;
    v5 = (struct _LSAP_IDENTITY_CACHE_ENTRY **)RtlInsertElementGenericTableAvl(a1 + 2, &Buffer, 8u, &NewElement);
    if ( !v5 )
      return (unsigned int)-1073741801;
    if ( NewElement )
      goto LABEL_9;
    if ( v3 )
      return (unsigned int)-1073741823;
    LsapRemoveIdentityCacheEntry((struct _PER_USER_CACHE_ENTRY *)a1, v5);
    v3 = 1;
  }
}

```

## disassembly

```asm
0x18011262c  mov     [rsp-28h+arg_0], rbx
0x180112631  mov     [rsp-28h+Buffer], rdx
0x180112636  push    rbp
0x180112637  push    rsi
0x180112638  push    rdi
0x180112639  push    r14
0x18011263b  push    r15
0x18011263d  mov     rbp, rsp
0x180112640  sub     rsp, 20h
0x180112644  xor     r15d, r15d
0x180112647  mov     rdi, rcx
0x18011264a  mov     [rbp+NewElement], r15b
0x18011264e  mov     bl, r15b
0x180112651  lea     r14d, [r15+8]
0x180112655  cmp     [rdx+40h], r15
0x180112659  jz      short loc_1801126AE
0x18011265b  lea     rsi, [rdi+0D0h]
0x180112662  mov     r8d, r14d; BufferSize
0x180112665  mov     rcx, rsi; Table
0x180112668  lea     r9, [rbp+NewElement]; NewElement
0x18011266c  lea     rdx, [rbp+Buffer]; Buffer
0x180112670  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180112677  nop     dword ptr [rax+rax+00h]
0x18011267c  test    rax, rax
0x18011267f  jz      short loc_1801126A4
0x180112681  cmp     [rbp+NewElement], r15b
0x180112685  jnz     short loc_1801126B5
0x180112687  test    bl, bl
0x180112689  jnz     short loc_18011269A
0x18011268b  mov     rdx, rax; struct _LSAP_IDENTITY_CACHE_ENTRY **
0x18011268e  mov     rcx, rdi; struct _PER_USER_CACHE_ENTRY *
0x180112691  call    ?LsapRemoveIdentityCacheEntry@@YAXPEAU_PER_USER_CACHE_ENTRY@@PEAPEAU_LSAP_IDENTITY_CACHE_ENTRY@@@Z; LsapRemoveIdentityCacheEntry(_PER_USER_CACHE_ENTRY *,_LSAP_IDENTITY_CACHE_ENTRY * *)
0x180112696  mov     bl, 1
0x180112698  jmp     short loc_18011265B
0x18011269a  mov     ebx, 0C0000001h
0x18011269f  jmp     loc_180112873
0x1801126a4  mov     ebx, 0C0000017h
0x1801126a9  jmp     loc_180112873
0x1801126ae  lea     rsi, [rcx+0D0h]
0x1801126b5  lea     r9, [rbp+NewElement]; NewElement
0x1801126b9  mov     [rbp+NewElement], r15b
0x1801126bd  mov     r8d, r14d; BufferSize
0x1801126c0  lea     rdx, [rbp+Buffer]; Buffer
0x1801126c4  mov     rcx, rdi; Table
0x1801126c7  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1801126ce  nop     dword ptr [rax+rax+00h]
0x1801126d3  test    rax, rax
0x1801126d6  jnz     short loc_180112703
0x1801126d8  mov     ebx, 0C0000017h
0x1801126dd  mov     rax, [rbp+Buffer]
0x1801126e1  cmp     [rax+40h], r15
0x1801126e5  jz      loc_180112873
0x1801126eb  lea     rdx, [rbp+Buffer]; Buffer
0x1801126ef  mov     rcx, rsi; Table
0x1801126f2  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1801126f9  nop     dword ptr [rax+rax+00h]
0x1801126fe  jmp     loc_180112873
0x180112703  cmp     [rbp+NewElement], r15b
0x180112707  jnz     short loc_180112710
0x180112709  mov     ebx, 0C0000001h
0x18011270e  jmp     short loc_1801126DD
0x180112710  mov     rcx, [rbp+Buffer]
0x180112714  cmp     r15w, [rcx+28h]
0x180112719  jz      short loc_18011278F
0x18011271b  mov     rdx, [rcx+30h]
0x18011271f  test    rdx, rdx
0x180112722  jz      short loc_18011278F
0x180112724  cmp     r15w, [rdx]
0x180112728  jz      short loc_18011278F
0x18011272a  lea     rcx, [rdi+68h]; Table
0x18011272e  mov     [rbp+NewElement], r15b
0x180112732  lea     r9, [rbp+NewElement]; NewElement
0x180112736  mov     r8d, r14d; BufferSize
0x180112739  lea     rdx, [rbp+Buffer]; Buffer
0x18011273d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180112744  nop     dword ptr [rax+rax+00h]
0x180112749  mov     rbx, rax
0x18011274c  test    rax, rax
0x18011274f  jz      short loc_180112757
0x180112751  cmp     [rbp+NewElement], r15b
0x180112755  jnz     short loc_18011278F
0x180112757  lea     rdx, [rbp+Buffer]; Buffer
0x18011275b  mov     rcx, rdi; Table
0x18011275e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180112765  nop     dword ptr [rax+rax+00h]
0x18011276a  mov     rcx, [rbp+Buffer]
0x18011276e  cmp     [rcx+40h], r15
0x180112772  jz      short loc_180112787
0x180112774  lea     rdx, [rbp+Buffer]; Buffer
0x180112778  mov     rcx, rsi; Table
0x18011277b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180112782  nop     dword ptr [rax+rax+00h]
0x180112787  neg     rbx
0x18011278a  jmp     loc_18011285D
0x18011278f  mov     ebx, r15d
0x180112792  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x180112799  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x18011279e  test    al, al
0x1801127a0  jz      loc_18011286B
0x1801127a6  mov     rcx, [rbp+Buffer]
0x1801127aa  cmp     r15w, [rcx+50h]
0x1801127af  jz      loc_18011286F
0x1801127b5  mov     rdx, [rcx+58h]
0x1801127b9  test    rdx, rdx
0x1801127bc  jz      loc_18011286F
0x1801127c2  cmp     r15w, [rdx]
0x1801127c6  jz      loc_18011286F
0x1801127cc  lea     rcx, [rdi+138h]; Table
0x1801127d3  mov     [rbp+NewElement], r15b
0x1801127d7  lea     r9, [rbp+NewElement]; NewElement
0x1801127db  mov     r8d, r14d; BufferSize
0x1801127de  lea     rdx, [rbp+Buffer]; Buffer
0x1801127e2  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1801127e9  nop     dword ptr [rax+rax+00h]
0x1801127ee  mov     r14, rax
0x1801127f1  test    rax, rax
0x1801127f4  jz      short loc_1801127FC
0x1801127f6  cmp     [rbp+NewElement], r15b
0x1801127fa  jnz     short loc_18011286B
0x1801127fc  lea     rdx, [rbp+Buffer]; Buffer
0x180112800  mov     rcx, rdi; Table
0x180112803  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18011280a  nop     dword ptr [rax+rax+00h]
0x18011280f  mov     rcx, [rbp+Buffer]
0x180112813  cmp     [rcx+40h], r15
0x180112817  jz      short loc_180112830
0x180112819  lea     rdx, [rbp+Buffer]; Buffer
0x18011281d  mov     rcx, rsi; Table
0x180112820  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180112827  nop     dword ptr [rax+rax+00h]
0x18011282c  mov     rcx, [rbp+Buffer]
0x180112830  cmp     r15w, [rcx+28h]
0x180112835  jz      short loc_18011285A
0x180112837  mov     rdx, [rcx+30h]
0x18011283b  test    rdx, rdx
0x18011283e  jz      short loc_18011285A
0x180112840  cmp     r15w, [rdx]
0x180112844  jz      short loc_18011285A
0x180112846  lea     rcx, [rdi+68h]; Table
0x18011284a  lea     rdx, [rbp+Buffer]; Buffer
0x18011284e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180112855  nop     dword ptr [rax+rax+00h]
0x18011285a  neg     r14
0x18011285d  sbb     eax, eax
0x18011285f  mov     ebx, 0C0000017h
0x180112864  and     eax, 0FFFFFFEAh
0x180112867  add     ebx, eax
0x180112869  jmp     short loc_180112873
0x18011286b  mov     rcx, [rbp+Buffer]
0x18011286f  lock inc dword ptr [rcx+4]
0x180112873  mov     eax, ebx
0x180112875  mov     rbx, [rsp+20h+arg_0]
0x18011287a  add     rsp, 20h
0x18011287e  pop     r15
0x180112880  pop     r14
0x180112882  pop     rdi
0x180112883  pop     rsi
0x180112884  pop     rbp
0x180112885  retn
```
