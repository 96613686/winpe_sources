# LsapProfileDeletedNotification(ushort const *)

- ea: `0x1800cd9e8`
- end: `0x1800cdc59`
- name: `?LsapProfileDeletedNotification@@YAJPEBG@Z`
- size: `625`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cee20`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x18005eda0`
- `0x18005f550`
- `0x18005fb34`
- `0x1800cd9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdbf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdc14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdbf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdc14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cdc32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cdc32`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800cdbdc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800cdbdc`
- `ntdll!RtlCopySid` at `0x1800cdb5c`
- `ntdll!RtlCopySid` at `0x1800cdbba`
- `ntdll!RtlCopySid` at `0x1800cdb5c`
- `ntdll!RtlCopySid` at `0x1800cdbba`
- `ntdll!RtlLengthSid` at `0x1800cdafc`
- `ntdll!RtlLengthSid` at `0x1800cdb12`
- `ntdll!RtlLengthSid` at `0x1800cdb47`
- `ntdll!RtlLengthSid` at `0x1800cdb7b`
- `ntdll!RtlLengthSid` at `0x1800cdb91`
- `ntdll!RtlLengthSid` at `0x1800cdba2`
- `ntdll!RtlLengthSid` at `0x1800cdafc`
- `ntdll!RtlLengthSid` at `0x1800cdb12`
- `ntdll!RtlLengthSid` at `0x1800cdb47`
- `ntdll!RtlLengthSid` at `0x1800cdb7b`
- `ntdll!RtlLengthSid` at `0x1800cdb91`
- `ntdll!RtlLengthSid` at `0x1800cdba2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800cda1a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800cda1a`

## pseudocode

```c
__int64 __fastcall LsapProfileDeletedNotification(const unsigned __int16 *a1)
{
  struct _RTL_BALANCED_NODE *v1; // rdi
  int ConnectedUserByLocalSid; // ebx
  void *v3; // rdx
  struct _UNICODE_STRING *v4; // r9
  int v5; // r14d
  int MappedSidInternal; // eax
  ULONG v7; // ebx
  struct _RTL_BALANCED_NODE *v8; // rax
  struct _RTL_BALANCED_NODE *v9; // rsi
  PSID v10; // rbx
  ULONG v11; // eax
  __int64 v12; // rbx
  ULONG v13; // eax
  int v15; // [rsp+60h] [rbp+30h] BYREF
  PSID Sid; // [rsp+68h] [rbp+38h] BYREF
  void *v17; // [rsp+70h] [rbp+40h] BYREF

  v1 = 0;
  Sid = 0;
  v17 = 0;
  v15 = 0;
  if ( !a1 )
    return (unsigned int)-1073741811;
  if ( !ConvertStringSidToSidW(a1, &Sid) )
    goto LABEL_26;
  ConnectedUserByLocalSid = LsapLookupUserAccountType(0, (struct _LSAPR_SID *)Sid, (enum _LSA_USER_ACCOUNT_TYPE *)&v15);
  if ( ConnectedUserByLocalSid >= 0 )
  {
    v5 = v15;
    if ( v15 == 4 )
    {
      ConnectedUserByLocalSid = LsapFindConnectedUserByLocalSid(Sid, 0, 0, v4, &v17);
      if ( ConnectedUserByLocalSid < 0 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            66,
            WPP_05668a43f07036cee45d35059337a059_Traceguids,
            (unsigned int)ConnectedUserByLocalSid);
        }
        v1 = (struct _RTL_BALANCED_NODE *)v17;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v15 != 5 )
      {
LABEL_17:
        v7 = RtlLengthSid(Sid);
        if ( v1 )
          v7 += RtlLengthSid(v1);
        v8 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v7 + 8LL);
        v9 = v8;
        if ( !v8 )
        {
          ConnectedUserByLocalSid = -1073741801;
          goto LABEL_29;
        }
        LODWORD(v8->Children[0]) = v5;
        v10 = Sid;
        v11 = RtlLengthSid(Sid);
        ConnectedUserByLocalSid = RtlCopySid(v11, &v9->Right, v10);
        if ( ConnectedUserByLocalSid < 0 )
          goto LABEL_29;
        if ( v1 )
        {
          HIDWORD(v9->Left) = RtlLengthSid(Sid) + 8;
          v12 = RtlLengthSid(Sid);
          v13 = RtlLengthSid(v1);
          ConnectedUserByLocalSid = RtlCopySid(v13, (char *)&v9->Right + v12, v1);
          if ( ConnectedUserByLocalSid < 0 )
            goto LABEL_29;
        }
        if ( QueueUserWorkItem(LsapProfileDeletedNotificationWorker, v9, 0x10u) )
          goto LABEL_29;
        LsapSubProv_FreeRoutine(v9, v3);
LABEL_26:
        if ( (int)GetLastError() > 0 )
          ConnectedUserByLocalSid = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          ConnectedUserByLocalSid = GetLastError();
        goto LABEL_29;
      }
      MappedSidInternal = LsapFindMappedSidInternal(Sid);
      if ( MappedSidInternal < 0
        && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_05668a43f07036cee45d35059337a059_Traceguids,
          (unsigned int)MappedSidInternal);
      }
    }
    v1 = (struct _RTL_BALANCED_NODE *)v17;
    goto LABEL_17;
  }
LABEL_29:
  if ( Sid )
    LocalFree(Sid);
  if ( v1 )
    LsapSubProv_FreeRoutine(v1, v3);
  return (unsigned int)ConnectedUserByLocalSid;
}

```

## disassembly

```asm
0x1800cd9e8  push    rbp
0x1800cd9ea  push    rbx
0x1800cd9eb  push    rsi
0x1800cd9ec  push    rdi
0x1800cd9ed  push    r14
0x1800cd9ef  mov     rbp, rsp
0x1800cd9f2  sub     rsp, 30h
0x1800cd9f6  xor     edi, edi
0x1800cd9f8  mov     [rbp+Sid], 0
0x1800cda00  mov     [rbp+arg_10], rdi
0x1800cda04  mov     [rbp+arg_0], edi
0x1800cda07  test    rcx, rcx
0x1800cda0a  jnz     short loc_1800CDA16
0x1800cda0c  mov     ebx, 0C000000Dh
0x1800cda11  jmp     loc_1800CDC4B
0x1800cda16  lea     rdx, [rbp+Sid]; Sid
0x1800cda1a  call    cs:__imp_ConvertStringSidToSidW
0x1800cda21  nop     dword ptr [rax+rax+00h]
0x1800cda26  test    eax, eax
0x1800cda28  jz      loc_1800CDBF4
0x1800cda2e  mov     rdx, [rbp+Sid]; struct _LSAPR_SID *
0x1800cda32  lea     r8, [rbp+arg_0]; enum _LSA_USER_ACCOUNT_TYPE *
0x1800cda36  xor     ecx, ecx; unsigned __int16 *
0x1800cda38  call    ?LsapLookupUserAccountType@@YAJPEAGPEAU_LSAPR_SID@@PEAW4_LSA_USER_ACCOUNT_TYPE@@@Z; LsapLookupUserAccountType(ushort *,_LSAPR_SID *,_LSA_USER_ACCOUNT_TYPE *)
0x1800cda3d  mov     ebx, eax
0x1800cda3f  test    eax, eax
0x1800cda41  js      loc_1800CDC29
0x1800cda47  mov     r14d, [rbp+arg_0]
0x1800cda4b  cmp     r14d, 4
0x1800cda4f  jnz     short loc_1800CDAAB
0x1800cda51  mov     rcx, [rbp+Sid]; SourceSid
0x1800cda55  lea     rax, [rbp+arg_10]
0x1800cda59  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800cda5c  mov     [rsp+30h+var_10], rax; void **
0x1800cda61  xor     edx, edx; struct _UNICODE_STRING *
0x1800cda63  call    ?LsapFindConnectedUserByLocalSid@@YAJPEAXPEAU_UNICODE_STRING@@11PEAPEAX@Z; LsapFindConnectedUserByLocalSid(void *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void * *)
0x1800cda68  mov     ebx, eax
0x1800cda6a  test    eax, eax
0x1800cda6c  jns     loc_1800CDAF4
0x1800cda72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cda79  lea     rax, WPP_GLOBAL_Control
0x1800cda80  cmp     rcx, rax
0x1800cda83  jz      short loc_1800CDAA2
0x1800cda85  test    [rcx+1Ch], r14b
0x1800cda89  jz      short loc_1800CDAA2
0x1800cda8b  mov     rcx, [rcx+10h]
0x1800cda8f  lea     edx, [r14+3Eh]
0x1800cda93  mov     r9d, ebx
0x1800cda96  lea     r8, WPP_05668a43f07036cee45d35059337a059_Traceguids
0x1800cda9d  call    WPP_SF_d
0x1800cdaa2  mov     rdi, [rbp+arg_10]
0x1800cdaa6  jmp     loc_1800CDC29
0x1800cdaab  cmp     r14d, 5
0x1800cdaaf  jnz     short loc_1800CDAF8
0x1800cdab1  mov     rcx, [rbp+Sid]; Sid
0x1800cdab5  lea     r8, [rbp+arg_10]
0x1800cdab9  xor     edx, edx
0x1800cdabb  call    LsapFindMappedSidInternal
0x1800cdac0  mov     r9d, eax
0x1800cdac3  test    eax, eax
0x1800cdac5  jns     short loc_1800CDAF4
0x1800cdac7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cdace  lea     rax, WPP_GLOBAL_Control
0x1800cdad5  cmp     rcx, rax
0x1800cdad8  jz      short loc_1800CDAF4
0x1800cdada  test    byte ptr [rcx+1Ch], 1
0x1800cdade  jz      short loc_1800CDAF4
0x1800cdae0  mov     rcx, [rcx+10h]
0x1800cdae4  lea     edx, [r14+3Eh]
0x1800cdae8  lea     r8, WPP_05668a43f07036cee45d35059337a059_Traceguids
0x1800cdaef  call    WPP_SF_d
0x1800cdaf4  mov     rdi, [rbp+arg_10]
0x1800cdaf8  mov     rcx, [rbp+Sid]; Sid
0x1800cdafc  call    cs:__imp_RtlLengthSid
0x1800cdb03  nop     dword ptr [rax+rax+00h]
0x1800cdb08  mov     ebx, eax
0x1800cdb0a  test    rdi, rdi
0x1800cdb0d  jz      short loc_1800CDB20
0x1800cdb0f  mov     rcx, rdi; Sid
0x1800cdb12  call    cs:__imp_RtlLengthSid
0x1800cdb19  nop     dword ptr [rax+rax+00h]
0x1800cdb1e  add     ebx, eax
0x1800cdb20  mov     ecx, ebx
0x1800cdb22  add     rcx, 8
0x1800cdb26  call    LsapAllocate
0x1800cdb2b  mov     rsi, rax
0x1800cdb2e  test    rax, rax
0x1800cdb31  jnz     short loc_1800CDB3D
0x1800cdb33  mov     ebx, 0C0000017h
0x1800cdb38  jmp     loc_1800CDC29
0x1800cdb3d  mov     [rax], r14d
0x1800cdb40  mov     rbx, [rbp+Sid]
0x1800cdb44  mov     rcx, rbx; Sid
0x1800cdb47  call    cs:__imp_RtlLengthSid
0x1800cdb4e  nop     dword ptr [rax+rax+00h]
0x1800cdb53  lea     rdx, [rsi+8]; DestinationSid
0x1800cdb57  mov     r8, rbx; SourceSid
0x1800cdb5a  mov     ecx, eax; DestinationSidLength
0x1800cdb5c  call    cs:__imp_RtlCopySid
0x1800cdb63  nop     dword ptr [rax+rax+00h]
0x1800cdb68  mov     ebx, eax
0x1800cdb6a  test    eax, eax
0x1800cdb6c  js      loc_1800CDC29
0x1800cdb72  test    rdi, rdi
0x1800cdb75  jz      short loc_1800CDBCC
0x1800cdb77  mov     rcx, [rbp+Sid]; Sid
0x1800cdb7b  call    cs:__imp_RtlLengthSid
0x1800cdb82  nop     dword ptr [rax+rax+00h]
0x1800cdb87  add     eax, 8
0x1800cdb8a  mov     [rsi+4], eax
0x1800cdb8d  mov     rcx, [rbp+Sid]; Sid
0x1800cdb91  call    cs:__imp_RtlLengthSid
0x1800cdb98  nop     dword ptr [rax+rax+00h]
0x1800cdb9d  mov     rcx, rdi; Sid
0x1800cdba0  mov     ebx, eax
0x1800cdba2  call    cs:__imp_RtlLengthSid
0x1800cdba9  nop     dword ptr [rax+rax+00h]
0x1800cdbae  lea     rdx, [rbx+8]
0x1800cdbb2  mov     r8, rdi; SourceSid
0x1800cdbb5  add     rdx, rsi; DestinationSid
0x1800cdbb8  mov     ecx, eax; DestinationSidLength
0x1800cdbba  call    cs:__imp_RtlCopySid
0x1800cdbc1  nop     dword ptr [rax+rax+00h]
0x1800cdbc6  mov     ebx, eax
0x1800cdbc8  test    eax, eax
0x1800cdbca  js      short loc_1800CDC29
0x1800cdbcc  mov     r8d, 10h; Flags
0x1800cdbd2  lea     rcx, ?LsapProfileDeletedNotificationWorker@@YAKPEAX@Z; Function
0x1800cdbd9  mov     rdx, rsi; Context
0x1800cdbdc  call    cs:__imp_QueueUserWorkItem
0x1800cdbe3  nop     dword ptr [rax+rax+00h]
0x1800cdbe8  test    eax, eax
0x1800cdbea  jnz     short loc_1800CDC29
0x1800cdbec  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x1800cdbef  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800cdbf4  call    cs:__imp_GetLastError
0x1800cdbfb  nop     dword ptr [rax+rax+00h]
0x1800cdc00  test    eax, eax
0x1800cdc02  jg      short loc_1800CDC14
0x1800cdc04  call    cs:__imp_GetLastError
0x1800cdc0b  nop     dword ptr [rax+rax+00h]
0x1800cdc10  mov     ebx, eax
0x1800cdc12  jmp     short loc_1800CDC29
0x1800cdc14  call    cs:__imp_GetLastError
0x1800cdc1b  nop     dword ptr [rax+rax+00h]
0x1800cdc20  movzx   ebx, ax
0x1800cdc23  or      ebx, 0C0070000h
0x1800cdc29  mov     rcx, [rbp+Sid]; hMem
0x1800cdc2d  test    rcx, rcx
0x1800cdc30  jz      short loc_1800CDC3E
0x1800cdc32  call    cs:__imp_LocalFree
0x1800cdc39  nop     dword ptr [rax+rax+00h]
0x1800cdc3e  test    rdi, rdi
0x1800cdc41  jz      short loc_1800CDC4B
0x1800cdc43  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x1800cdc46  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800cdc4b  mov     eax, ebx
0x1800cdc4d  add     rsp, 30h
0x1800cdc51  pop     r14
0x1800cdc53  pop     rdi
0x1800cdc54  pop     rsi
0x1800cdc55  pop     rbx
0x1800cdc56  pop     rbp
0x1800cdc57  retn
```
