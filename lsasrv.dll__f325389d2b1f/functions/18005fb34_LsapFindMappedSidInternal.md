# LsapFindMappedSidInternal

- ea: `0x18005fb34`
- end: `0x18005fec3`
- name: `LsapFindMappedSidInternal`
- size: `911`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800043bc`
- `0x18005eda0`
- `0x180060740`
- `0x180061e88`
- `0x180064628`
- `0x18008d958`
- `0x1800cd9e8`
- `0x180124194`
- `0x180126b7c`

## callees

- `0x18000c300`
- `0x18005fb34`
- `0x18005fecc`
- `0x18014d010`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18005fd22`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005fd39`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005fd22`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005fd39`
- `ntdll!RtlSubAuthoritySid` at `0x18005fd65`
- `ntdll!RtlSubAuthoritySid` at `0x18005fd7e`
- `ntdll!RtlSubAuthoritySid` at `0x18005fd65`
- `ntdll!RtlSubAuthoritySid` at `0x18005fd7e`
- `ntdll!RtlReleaseResource` at `0x18005fc01`
- `ntdll!RtlReleaseResource` at `0x18005fc9c`
- `ntdll!RtlReleaseResource` at `0x18005fc01`
- `ntdll!RtlReleaseResource` at `0x18005fc9c`
- `ntdll!RtlAcquireResourceShared` at `0x18005fb89`
- `ntdll!RtlAcquireResourceShared` at `0x18005fc60`
- `ntdll!RtlAcquireResourceShared` at `0x18005fb89`
- `ntdll!RtlAcquireResourceShared` at `0x18005fc60`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005fce5`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005fcf7`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005fce5`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005fcf7`
- `RPCRT4!UuidEqual` at `0x18005fe22`
- `RPCRT4!UuidEqual` at `0x18005fe22`

## string_xrefs

- `0x18005fcc5`: `LsapRefIdProvByInternetSid`
- `0x18005fde8`: `ProvEntry->ProviderTable.FindMappedSid`

## pseudocode

```c
__int64 __fastcall LsapFindMappedSidInternal(PSID Sid, void *a2, struct _RTL_BALANCED_NODE **a3)
{
  PSID v4; // rbx
  struct _LIST_ENTRY *v5; // rsi
  struct _LIST_ENTRY *k; // rax
  unsigned int v7; // ebx
  int v9; // ebp
  __int64 v10; // rcx
  struct _LIST_ENTRY *i; // r14
  int v12; // ebx
  __int64 v13; // rdx
  const char *v14; // rcx
  struct _LIST_ENTRY *Flink; // r12
  PSID_IDENTIFIER_AUTHORITY v16; // rdi
  PSID_IDENTIFIER_AUTHORITY v17; // rax
  int v18; // ecx
  PUCHAR v19; // rdi
  UCHAR j; // r12
  PULONG v21; // rax
  struct _LIST_ENTRY *v22; // rax
  int v23; // eax
  struct _RTL_BALANCED_NODE *Blink; // rcx
  struct _RTL_BALANCED_NODE **v25; // rax
  ULONG_PTR ParentValue; // rdi
  unsigned __int64 v27; // rdi
  struct _RTL_BALANCED_NODE *v28; // [rsp+20h] [rbp-48h] BYREF
  PUCHAR v29; // [rsp+28h] [rbp-40h]
  PSID Sida; // [rsp+88h] [rbp+20h] BYREF

  v28 = 0;
  v4 = Sid;
  if ( !Sid )
    return (unsigned int)-1073741811;
  if ( a3 )
    *a3 = 0;
  v5 = 0;
  if ( (_DWORD)a2 )
  {
    if ( !g_fHasInitIdProvExtension )
      goto LABEL_33;
    if ( !RtlAcquireResourceShared(&g_IdProvRegLock, 1u) )
    {
      v7 = -1073741823;
      v13 = 3221225473LL;
      v14 = "LsapRefIdProvByInternetSid";
LABEL_35:
      CONNECTED_TRACE_ERROR(v14, v13);
      goto LABEL_19;
    }
    for ( i = g_IdProvList.Flink; ; i = i->Flink )
    {
      if ( i == &g_IdProvList )
      {
        v12 = -1073741275;
        goto LABEL_32;
      }
      if ( HIDWORD(i[3].Blink) )
      {
        Flink = i[4].Flink;
        Sida = Flink;
        v16 = RtlIdentifierAuthoritySid(Flink);
        v17 = RtlIdentifierAuthoritySid(v4);
        v18 = *(_DWORD *)v16->Value - *(_DWORD *)v17->Value;
        if ( *(_DWORD *)v16->Value == *(_DWORD *)v17->Value )
          v18 = *(unsigned __int16 *)&v16->Value[4] - *(unsigned __int16 *)&v17->Value[4];
        if ( !v18 )
        {
          v29 = RtlSubAuthorityCountSid(Flink);
          v19 = v29;
          if ( *v29 <= *RtlSubAuthorityCountSid(v4) )
            break;
        }
      }
LABEL_30:
      ;
    }
    for ( j = 0; j < *v19; ++j )
    {
      v21 = RtlSubAuthoritySid(Sida, j);
      v4 = Sid;
      if ( *RtlSubAuthoritySid(Sid, j) != *v21 )
        goto LABEL_30;
      v19 = v29;
    }
    _InterlockedIncrement((volatile signed __int32 *)&i[1].Flink + 1);
    v5 = i;
    v12 = 0;
LABEL_32:
    RtlReleaseResource(&g_IdProvRegLock);
    if ( v12 < 0 )
    {
LABEL_33:
      v7 = -1073741704;
      goto LABEL_19;
    }
    LODWORD(Sida) = 0;
    if ( !UuidEqual((UUID *)&v5[1].Blink, (UUID *)&stru_1801625B0, (RPC_STATUS *)&Sida) )
    {
LABEL_18:
      v7 = -1073741637;
      goto LABEL_19;
    }
    v4 = Sid;
  }
  else
  {
    if ( !g_fHasInitIdProvExtension || !RtlAcquireResourceShared(&g_IdProvRegLock, 1u) )
      goto LABEL_18;
    for ( k = g_IdProvList.Flink; ; k = k->Flink )
    {
      if ( k == &g_IdProvList )
      {
        v9 = -1073741275;
        goto LABEL_17;
      }
      if ( HIDWORD(k[3].Blink) )
      {
        v10 = (__int64)&k[1].Blink[0xFB6985EB74E97673uLL].Blink + 2;
        if ( k[1].Blink == (struct _LIST_ENTRY *)0x4967A148B16898C6LL )
          v10 = (__int64)&k[2].Flink[0xFDF7A25AA289B8E6uLL].Blink + 7;
        if ( !v10 )
          break;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)&k[1].Flink + 1);
    v5 = k;
    v9 = 0;
LABEL_17:
    RtlReleaseResource(&g_IdProvRegLock);
    if ( v9 < 0 )
      goto LABEL_18;
  }
  if ( LODWORD(v5[11].Flink) < 0x88 )
    goto LABEL_18;
  v22 = v5[19].Flink;
  if ( !v22 )
    goto LABEL_18;
  v23 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, PSID, struct _RTL_BALANCED_NODE **))v22)(v5, v4, &v28);
  v7 = v23;
  if ( v23 >= 0 )
  {
    if ( a3 )
    {
      *a3 = v28;
      v28 = 0;
    }
  }
  else if ( v23 != -1073741724 && v23 != -1073741637 )
  {
    v13 = (unsigned int)v23;
    v14 = "ProvEntry->ProviderTable.FindMappedSid";
    goto LABEL_35;
  }
LABEL_19:
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)&v5[1].Flink + 1, 0xFFFFFFFF) == 1 )
  {
    _InterlockedDecrement(&g_cRegisteredIdProv);
    Blink = (struct _RTL_BALANCED_NODE *)v5[19].Blink;
    if ( !Blink )
    {
LABEL_64:
      v5[19].Blink = 0;
      LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v5, a2);
      goto LABEL_13;
    }
    while ( !Blink->Children[0] )
    {
      v25 = &Blink->Children[1];
      if ( Blink->Children[1] )
      {
        Blink = *v25;
LABEL_61:
        *v25 = 0;
      }
      else
      {
        ParentValue = Blink->ParentValue;
        LsapSubProv_FreeRoutine(Blink, 0);
        v27 = ParentValue & 0xFFFFFFFFFFFFFFFCuLL;
        if ( !v27 )
          goto LABEL_64;
        Blink = (struct _RTL_BALANCED_NODE *)v27;
      }
    }
    v25 = (struct _RTL_BALANCED_NODE **)Blink;
    Blink = Blink->Children[0];
    goto LABEL_61;
  }
LABEL_13:
  if ( v28 )
    LsapSubProv_FreeRoutine(v28, a2);
  return v7;
}

```

## disassembly

```asm
0x18005fb34  mov     [rsp+arg_8], rbx
0x18005fb39  mov     [rsp+arg_0], rcx
0x18005fb3e  push    rbp
0x18005fb3f  push    rsi
0x18005fb40  push    rdi
0x18005fb41  push    r12
0x18005fb43  push    r13
0x18005fb45  push    r14
0x18005fb47  push    r15
0x18005fb49  sub     rsp, 30h
0x18005fb4d  xor     r12d, r12d
0x18005fb50  mov     r15, r8
0x18005fb53  mov     [rsp+68h+var_48], r12
0x18005fb58  mov     rbx, rcx
0x18005fb5b  test    rcx, rcx
0x18005fb5e  jz      short loc_18005FBB7
0x18005fb60  test    r8, r8
0x18005fb63  jz      short loc_18005FB68
0x18005fb65  mov     [r8], r12
0x18005fb68  mov     rsi, r12
0x18005fb6b  test    edx, edx
0x18005fb6d  jnz     loc_18005FC4E
0x18005fb73  cmp     cs:?g_fHasInitIdProvExtension@@3HA, r12d; int g_fHasInitIdProvExtension
0x18005fb7a  jz      loc_18005FC15
0x18005fb80  mov     dl, 1; Wait
0x18005fb82  lea     rcx, ?g_IdProvRegLock@@3U_RTL_RESOURCE@@A; Resource
0x18005fb89  call    cs:__imp_RtlAcquireResourceShared
0x18005fb90  nop     dword ptr [rax+rax+00h]
0x18005fb95  test    al, al
0x18005fb97  jz      short loc_18005FC15
0x18005fb99  mov     rax, cs:?g_IdProvList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_IdProvList
0x18005fba0  lea     r13, ?g_IdProvList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_IdProvList
0x18005fba7  cmp     rax, r13
0x18005fbaa  jz      short loc_18005FBF5
0x18005fbac  cmp     [rax+3Ch], r12d
0x18005fbb0  jnz     short loc_18005FC21
0x18005fbb2  mov     rax, [rax]
0x18005fbb5  jmp     short loc_18005FBA7
0x18005fbb7  mov     ebx, 0C000000Dh
0x18005fbbc  jmp     short loc_18005FBDD
0x18005fbbe  or      eax, 0FFFFFFFFh
0x18005fbc1  lock xadd [rsi+14h], eax
0x18005fbc6  cmp     eax, 1
0x18005fbc9  jz      loc_18005FE5B
0x18005fbcf  mov     rcx, [rsp+68h+var_48]; struct _RTL_BALANCED_NODE *
0x18005fbd4  test    rcx, rcx
0x18005fbd7  jnz     loc_18005FEB9
0x18005fbdd  mov     eax, ebx
0x18005fbdf  mov     rbx, [rsp+68h+arg_8]
0x18005fbe4  add     rsp, 30h
0x18005fbe8  pop     r15
0x18005fbea  pop     r14
0x18005fbec  pop     r13
0x18005fbee  pop     r12
0x18005fbf0  pop     rdi
0x18005fbf1  pop     rsi
0x18005fbf2  pop     rbp
0x18005fbf3  retn
0x18005fbf5  mov     ebp, 0C0000225h
0x18005fbfa  lea     rcx, ?g_IdProvRegLock@@3U_RTL_RESOURCE@@A; Resource
0x18005fc01  call    cs:__imp_RtlReleaseResource
0x18005fc08  nop     dword ptr [rax+rax+00h]
0x18005fc0d  test    ebp, ebp
0x18005fc0f  jns     loc_18005FD9A
0x18005fc15  mov     ebx, 0C00000BBh
0x18005fc1a  test    rsi, rsi
0x18005fc1d  jz      short loc_18005FBCF
0x18005fc1f  jmp     short loc_18005FBBE
0x18005fc21  mov     rcx, [rax+18h]
0x18005fc25  sub     rcx, qword ptr cs:stru_1801625B0.Data1
0x18005fc2c  jnz     short loc_18005FC39
0x18005fc2e  mov     rcx, [rax+20h]
0x18005fc32  sub     rcx, qword ptr cs:stru_1801625B0.Data4
0x18005fc39  test    rcx, rcx
0x18005fc3c  jnz     loc_18005FBB2
0x18005fc42  lock inc dword ptr [rax+14h]
0x18005fc46  mov     rsi, rax
0x18005fc49  mov     ebp, r12d
0x18005fc4c  jmp     short loc_18005FBFA
0x18005fc4e  cmp     cs:?g_fHasInitIdProvExtension@@3HA, r12d; int g_fHasInitIdProvExtension
0x18005fc55  jz      short loc_18005FCB4
0x18005fc57  mov     dl, 1; Wait
0x18005fc59  lea     rcx, ?g_IdProvRegLock@@3U_RTL_RESOURCE@@A; Resource
0x18005fc60  call    cs:__imp_RtlAcquireResourceShared
0x18005fc67  nop     dword ptr [rax+rax+00h]
0x18005fc6c  test    al, al
0x18005fc6e  jz      short loc_18005FCBE
0x18005fc70  mov     r14, cs:?g_IdProvList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_IdProvList
0x18005fc77  lea     r13, ?g_IdProvList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_IdProvList
0x18005fc7e  mov     ebp, 0C0000225h
0x18005fc83  cmp     r14, r13
0x18005fc86  jz      short loc_18005FC93
0x18005fc88  cmp     [r14+3Ch], r12d
0x18005fc8c  jnz     short loc_18005FCD6
0x18005fc8e  mov     r14, [r14]
0x18005fc91  jmp     short loc_18005FC7E
0x18005fc93  mov     ebx, ebp
0x18005fc95  lea     rcx, ?g_IdProvRegLock@@3U_RTL_RESOURCE@@A; Resource
0x18005fc9c  call    cs:__imp_RtlReleaseResource
0x18005fca3  nop     dword ptr [rax+rax+00h]
0x18005fca8  test    ebx, ebx
0x18005fcaa  jns     loc_18005FE07
0x18005fcb0  cmp     ebx, ebp
0x18005fcb2  jnz     short loc_18005FCC3
0x18005fcb4  mov     ebx, 0C0000078h
0x18005fcb9  jmp     loc_18005FC1A
0x18005fcbe  mov     ebx, 0C0000001h
0x18005fcc3  mov     edx, ebx
0x18005fcc5  lea     rcx, aLsaprefidprovb; "LsapRefIdProvByInternetSid"
0x18005fccc  call    CONNECTED_TRACE_ERROR
0x18005fcd1  jmp     loc_18005FC1A
0x18005fcd6  mov     r12, [r14+40h]
0x18005fcda  mov     rcx, r12; Sid
0x18005fcdd  mov     [rsp+68h+Sid], r12
0x18005fce5  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005fcec  nop     dword ptr [rax+rax+00h]
0x18005fcf1  mov     rcx, rbx; Sid
0x18005fcf4  mov     rdi, rax
0x18005fcf7  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005fcfe  nop     dword ptr [rax+rax+00h]
0x18005fd03  mov     ecx, [rdi]
0x18005fd05  sub     ecx, [rax]
0x18005fd07  jnz     short loc_18005FD13
0x18005fd09  movzx   ecx, word ptr [rdi+4]
0x18005fd0d  movzx   eax, word ptr [rax+4]
0x18005fd11  sub     ecx, eax
0x18005fd13  test    ecx, ecx
0x18005fd15  jz      short loc_18005FD1F
0x18005fd17  xor     r12d, r12d
0x18005fd1a  jmp     loc_18005FC8E
0x18005fd1f  mov     rcx, r12; Sid
0x18005fd22  call    cs:__imp_RtlSubAuthorityCountSid
0x18005fd29  nop     dword ptr [rax+rax+00h]
0x18005fd2e  mov     rcx, rbx; Sid
0x18005fd31  mov     [rsp+68h+var_40], rax
0x18005fd36  mov     rdi, rax
0x18005fd39  call    cs:__imp_RtlSubAuthorityCountSid
0x18005fd40  nop     dword ptr [rax+rax+00h]
0x18005fd45  mov     cl, [rax]
0x18005fd47  cmp     [rdi], cl
0x18005fd49  ja      short loc_18005FD17
0x18005fd4b  xor     r12b, r12b
0x18005fd4e  cmp     r12b, [rdi]
0x18005fd51  jnb     loc_18005FDF4
0x18005fd57  mov     rcx, [rsp+68h+Sid]; Sid
0x18005fd5f  movzx   ebx, r12b
0x18005fd63  mov     edx, ebx; SubAuthority
0x18005fd65  call    cs:__imp_RtlSubAuthoritySid
0x18005fd6c  nop     dword ptr [rax+rax+00h]
0x18005fd71  mov     edx, ebx; SubAuthority
0x18005fd73  mov     rbx, [rsp+68h+arg_0]
0x18005fd78  mov     rcx, rbx; Sid
0x18005fd7b  mov     rdi, rax
0x18005fd7e  call    cs:__imp_RtlSubAuthoritySid
0x18005fd85  nop     dword ptr [rax+rax+00h]
0x18005fd8a  mov     ecx, [rdi]
0x18005fd8c  cmp     [rax], ecx
0x18005fd8e  jnz     short loc_18005FD17
0x18005fd90  mov     rdi, [rsp+68h+var_40]
0x18005fd95  inc     r12b
0x18005fd98  jmp     short loc_18005FD4E
0x18005fd9a  cmp     dword ptr [rsi+0B0h], 88h
0x18005fda4  jb      loc_18005FC15
0x18005fdaa  mov     rax, [rsi+130h]
0x18005fdb1  test    rax, rax
0x18005fdb4  jz      loc_18005FC15
0x18005fdba  lea     r8, [rsp+68h+var_48]
0x18005fdbf  mov     rdx, rbx
0x18005fdc2  mov     rcx, rsi
0x18005fdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdca  mov     ebx, eax
0x18005fdcc  test    eax, eax
0x18005fdce  jns     short loc_18005FE40
0x18005fdd0  cmp     eax, 0C0000064h
0x18005fdd5  jz      loc_18005FC1A
0x18005fddb  cmp     eax, 0C00000BBh
0x18005fde0  jz      loc_18005FC1A
0x18005fde6  mov     edx, eax
0x18005fde8  lea     rcx, aProventryProvi_0; "ProvEntry->ProviderTable.FindMappedSid"
0x18005fdef  jmp     loc_18005FCCC
0x18005fdf4  lock inc dword ptr [r14+14h]
0x18005fdf9  xor     r12d, r12d
0x18005fdfc  mov     rsi, r14
0x18005fdff  mov     ebx, r12d
0x18005fe02  jmp     loc_18005FC95
0x18005fe07  lea     rcx, [rsi+18h]; Uuid1
0x18005fe0b  mov     dword ptr [rsp+68h+Sid], r12d
0x18005fe13  lea     r8, [rsp+68h+Sid]; Status
0x18005fe1b  lea     rdx, stru_1801625B0; Uuid2
0x18005fe22  call    cs:__imp_UuidEqual
0x18005fe29  nop     dword ptr [rax+rax+00h]
0x18005fe2e  test    eax, eax
0x18005fe30  jz      loc_18005FC15
0x18005fe36  mov     rbx, [rsp+68h+arg_0]
0x18005fe3b  jmp     loc_18005FD9A
0x18005fe40  test    r15, r15
0x18005fe43  jz      loc_18005FC1A
0x18005fe49  mov     rcx, [rsp+68h+var_48]
0x18005fe4e  mov     [r15], rcx
0x18005fe51  mov     [rsp+68h+var_48], r12
0x18005fe56  jmp     loc_18005FC1A
0x18005fe5b  lock dec cs:?g_cRegisteredIdProv@@3JA; long g_cRegisteredIdProv
0x18005fe62  mov     rcx, [rsi+138h]; struct _RTL_BALANCED_NODE *
0x18005fe69  test    rcx, rcx
0x18005fe6c  jz      short loc_18005FEA5
0x18005fe6e  mov     rdx, [rcx]
0x18005fe71  test    rdx, rdx
0x18005fe74  jz      short loc_18005FE7E
0x18005fe76  mov     rax, rcx
0x18005fe79  mov     rcx, rdx
0x18005fe7c  jmp     short loc_18005FE8A
0x18005fe7e  lea     rax, [rcx+8]
0x18005fe82  cmp     [rax], r12
0x18005fe85  jz      short loc_18005FE8F
0x18005fe87  mov     rcx, [rax]
0x18005fe8a  mov     [rax], r12
0x18005fe8d  jmp     short loc_18005FE6E
0x18005fe8f  mov     rdi, [rcx+10h]
0x18005fe93  xor     edx, edx; void *
0x18005fe95  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005fe9a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18005fe9e  jz      short loc_18005FEA5
0x18005fea0  mov     rcx, rdi
0x18005fea3  jmp     short loc_18005FE6E
0x18005fea5  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x18005fea8  mov     [rsi+138h], r12
0x18005feaf  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005feb4  jmp     loc_18005FBCF
0x18005feb9  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005febe  jmp     loc_18005FBDD
```
