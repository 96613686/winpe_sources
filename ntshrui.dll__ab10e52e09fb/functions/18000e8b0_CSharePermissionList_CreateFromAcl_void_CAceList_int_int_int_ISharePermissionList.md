# CSharePermissionList_CreateFromAcl(void *,CAceList *,int,int,int,ISharePermissionList * *)

- ea: `0x18000e8b0`
- end: `0x18000edbd`
- name: `?CSharePermissionList_CreateFromAcl@@YAJPEAXPEAVCAceList@@HHHPEAPEAUISharePermissionList@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(void *, struct CAceList *, int, int, int, struct ISharePermissionList **)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800093d0`
- `0x180054470`
- `0x18005a228`
- `0x18005a664`
- `0x18005a9ec`

## callees

- `0x1800098dc`
- `0x18000e8b0`
- `0x18000edd0`
- `0x18000f09c`
- `0x18000f0c8`
- `0x18000f250`
- `0x18000f7a0`
- `0x18000f7f0`
- `0x1800259bc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ed09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ed40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ed09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ed40`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000eac7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000eaf7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000ec07`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000ec67`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000eac7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000eaf7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000ec07`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000ec67`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000ea8c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000ebca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000ea8c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000ebca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000ea9c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000ebda`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000ea9c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000ebda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e983`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e983`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e954`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e954`

## pseudocode

```c
__int64 __fastcall CSharePermissionList_CreateFromAcl(
        void *a1,
        struct CAceList *a2,
        int a3,
        int a4,
        int a5,
        struct ISharePermissionList **a6)
{
  int Error; // ebp
  CSharePermissionList *v8; // rax
  CSharePermissionList *v9; // r15
  __int64 (__fastcall *v10)(__int64, __int64); // rax
  __int64 v12; // rax
  int v13; // esi
  int *v14; // rbx
  int v15; // eax
  __int64 v16; // r14
  void *v17; // rbx
  __int64 k; // rbx
  __int64 m; // rbx
  enum SHARE_ROLE v20; // eax
  int v21; // esi
  int *v22; // rbx
  int v23; // eax
  __int64 v24; // rdi
  void *v25; // rbx
  __int64 i; // rbx
  int v27; // eax
  char v28; // al
  __int64 j; // rbx
  enum SHARE_ROLE RoleForItemAccessMask; // eax
  int v31; // eax
  char v32; // al
  LPWSTR StringSid; // [rsp+20h] [rbp-48h] BYREF

  Error = -2147024882;
  *a6 = 0;
  v8 = (CSharePermissionList *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v8 )
    return 2147942414LL;
  v9 = CSharePermissionList::CSharePermissionList(v8);
  if ( !v9 )
    return 2147942414LL;
  v10 = (__int64 (__fastcall *)(__int64, __int64))qword_180095A50;
  if ( qword_180095A50 == -1 )
  {
    GetProcFromComCtl32(&qword_180095A50, 320);
    v10 = (__int64 (__fastcall *)(__int64, __int64))qword_180095A50;
  }
  if ( !v10 )
  {
    *((_QWORD *)v9 + 2) = 0;
    goto LABEL_10;
  }
  v12 = v10(16, 5);
  *((_QWORD *)v9 + 2) = v12;
  if ( v12 )
  {
    Error = 0;
    v13 = 0;
    while ( 1 )
    {
      v14 = (int *)*((_QWORD *)a2 + 1);
      if ( v14 )
        v15 = *v14;
      else
        v15 = 0;
      if ( v13 >= v15 )
      {
LABEL_36:
        if ( Error < 0 )
          break;
        if ( !a4 )
          goto LABEL_68;
        Error = 0;
        v21 = 0;
LABEL_39:
        v22 = (int *)*((_QWORD *)a2 + 2);
        if ( v22 )
          v23 = *v22;
        else
          v23 = 0;
        if ( v21 >= v23 )
        {
LABEL_67:
          if ( Error >= 0 )
          {
LABEL_68:
            if ( !a1
              || ((StringSid = 0, ConvertSidToStringSidW(a1, &StringSid))
               || (Error = ResultFromKnownLastError(), Error >= 0))
              && (Error = (*(__int64 (__fastcall **)(CSharePermissionList *, LPWSTR, __int64))(*(_QWORD *)v9 + 56LL))(
                            v9,
                            StringSid,
                            3),
                  LocalFree(StringSid),
                  Error >= 0) )
            {
              Error = (**(__int64 (__fastcall ***)(CSharePermissionList *, GUID *, struct ISharePermissionList **))v9)(
                        v9,
                        &GUID_4c62a9fa_2437_49ca_8eb4_5238205afeaa,
                        a6);
            }
          }
          break;
        }
        if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
        {
          if ( g_hinstCC || (DelayLoadCC(), g_hinstCC) )
          {
            qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
            goto LABEL_43;
          }
          qword_180095A20 = 0;
        }
        else
        {
LABEL_43:
          if ( qword_180095A20 )
          {
            v24 = qword_180095A20(v22, v21);
            goto LABEL_45;
          }
        }
        v24 = 0;
LABEL_45:
        if ( a5 )
        {
          if ( (*(_BYTE *)(v24 + 28) & 1) != 0 )
          {
            v25 = *(void **)(v24 + 8);
            if ( !(unsigned int)IsSidLocalMachineAndUnknown(v25) )
            {
              if ( !a3
                || (v31 = *(_DWORD *)(v24 + 28), (v31 & 0x20) != 0)
                || (v31 & 1) == 0
                || (v32 = *(_BYTE *)(v24 + 1)) != 0 && v32 != 9 )
              {
                if ( !GetSidSubAuthorityCount(v25) || *GetSidSubAuthority(v25, 0) != 80 )
                {
                  for ( i = 0; (unsigned int)i < 0xB; i = (unsigned int)(i + 1) )
                  {
                    if ( IsWellKnownSid(*(PSID *)(v24 + 8), (WELL_KNOWN_SID_TYPE)dword_180082BA0[i]) )
                      goto LABEL_66;
                  }
                  if ( (*(_BYTE *)(v24 + 28) & 0x20) != 0 )
                  {
                    for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
                    {
                      if ( IsWellKnownSid(*(PSID *)(v24 + 8), (WELL_KNOWN_SID_TYPE)dword_180082B98[j]) )
                        goto LABEL_66;
                    }
                  }
                  goto LABEL_65;
                }
              }
            }
          }
        }
        else
        {
LABEL_65:
          RoleForItemAccessMask = GetRoleForItemAccessMask(*(_DWORD *)(v24 + 4));
          Error = CSharePermissionList::_MergePermission(v9, *(void **)(v24 + 8), RoleForItemAccessMask);
        }
LABEL_66:
        ++v21;
        if ( Error < 0 )
          goto LABEL_67;
        goto LABEL_39;
      }
      if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
      {
        if ( !g_hinstCC )
        {
          DelayLoadCC();
          if ( !g_hinstCC )
          {
            qword_180095A20 = 0;
            goto LABEL_83;
          }
        }
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      }
      if ( qword_180095A20 )
      {
        v16 = qword_180095A20(v14, v13);
        goto LABEL_19;
      }
LABEL_83:
      v16 = 0;
LABEL_19:
      if ( a5 )
      {
        if ( (*(_BYTE *)(v16 + 28) & 1) == 0 )
          goto LABEL_35;
        v17 = *(void **)(v16 + 8);
        if ( (unsigned int)IsSidLocalMachineAndUnknown(v17) )
          goto LABEL_35;
        if ( a3 )
        {
          v27 = *(_DWORD *)(v16 + 28);
          if ( (v27 & 0x20) == 0 && (v27 & 1) != 0 )
          {
            v28 = *(_BYTE *)(v16 + 1);
            if ( !v28 || v28 == 9 )
              goto LABEL_35;
          }
        }
        if ( GetSidSubAuthorityCount(v17) && *GetSidSubAuthority(v17, 0) == 80 )
          goto LABEL_35;
        for ( k = 0; (unsigned int)k < 0xB; k = (unsigned int)(k + 1) )
        {
          if ( IsWellKnownSid(*(PSID *)(v16 + 8), (WELL_KNOWN_SID_TYPE)dword_180082BA0[k]) )
            goto LABEL_35;
        }
        if ( (*(_BYTE *)(v16 + 28) & 0x20) != 0 )
        {
          for ( m = 0; (unsigned int)m < 2; m = (unsigned int)(m + 1) )
          {
            if ( IsWellKnownSid(*(PSID *)(v16 + 8), (WELL_KNOWN_SID_TYPE)dword_180082B98[m]) )
              goto LABEL_35;
          }
        }
      }
      v20 = GetRoleForItemAccessMask(*(_DWORD *)(v16 + 4));
      Error = CSharePermissionList::_MergePermission(v9, *(void **)(v16 + 8), v20);
LABEL_35:
      ++v13;
      if ( Error < 0 )
        goto LABEL_36;
    }
  }
LABEL_10:
  (*(void (__fastcall **)(CSharePermissionList *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000e8b0  mov     [rsp+arg_18], r9d
0x18000e8b5  mov     [rsp+arg_10], r8d
0x18000e8ba  mov     [rsp+Sid], rcx
0x18000e8bf  push    rbp
0x18000e8c0  push    r12
0x18000e8c2  push    r13
0x18000e8c4  sub     rsp, 50h
0x18000e8c8  mov     rax, [rsp+68h+arg_28]
0x18000e8d0  mov     r13, rdx
0x18000e8d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e8da  mov     ecx, 18h; unsigned __int64
0x18000e8df  mov     ebp, 8007000Eh
0x18000e8e4  mov     qword ptr [rax], 0
0x18000e8eb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e8f0  test    rax, rax
0x18000e8f3  jz      loc_18000ECD8
0x18000e8f9  mov     rcx, rax; this
0x18000e8fc  mov     [rsp+68h+var_38], r15
0x18000e901  call    ??0CSharePermissionList@@QEAA@XZ; CSharePermissionList::CSharePermissionList(void)
0x18000e906  mov     r15, rax
0x18000e909  test    rax, rax
0x18000e90c  jz      loc_18000EDB6
0x18000e912  mov     rax, cs:qword_180095A50
0x18000e919  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e91d  jz      loc_18000ED77
0x18000e923  mov     [rsp+68h+arg_8], rbx
0x18000e928  mov     [rsp+68h+var_20], rsi
0x18000e92d  mov     [rsp+68h+var_28], rdi
0x18000e932  mov     [rsp+68h+var_30], r14
0x18000e937  test    rax, rax
0x18000e93a  jnz     loc_18000E9E0
0x18000e940  mov     [r15+10h], rax
0x18000e944  jmp     short loc_18000E9AC
0x18000e946  lea     rdx, [rsp+68h+StringSid]; StringSid
0x18000e94b  mov     [rsp+68h+StringSid], 0
0x18000e954  call    cs:__imp_ConvertSidToStringSidW
0x18000e95a  test    eax, eax
0x18000e95c  jz      loc_18000EDA2
0x18000e962  mov     rax, [r15]
0x18000e965  mov     r8d, 3
0x18000e96b  mov     rdx, [rsp+68h+StringSid]
0x18000e970  mov     rcx, r15
0x18000e973  mov     rax, [rax+38h]
0x18000e977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e97c  mov     rcx, [rsp+68h+StringSid]; hMem
0x18000e981  mov     ebp, eax
0x18000e983  call    cs:__imp_LocalFree
0x18000e989  test    ebp, ebp
0x18000e98b  js      short loc_18000E9AC
0x18000e98d  mov     rax, [r15]
0x18000e990  lea     rdx, _GUID_4c62a9fa_2437_49ca_8eb4_5238205afeaa
0x18000e997  mov     r8, [rsp+68h+arg_28]
0x18000e99f  mov     rcx, r15
0x18000e9a2  mov     rax, [rax]
0x18000e9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9aa  mov     ebp, eax
0x18000e9ac  mov     rax, [r15]
0x18000e9af  mov     rcx, r15
0x18000e9b2  mov     rax, [rax+10h]
0x18000e9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9bb  mov     r14, [rsp+68h+var_30]
0x18000e9c0  mov     eax, ebp
0x18000e9c2  mov     rdi, [rsp+68h+var_28]
0x18000e9c7  mov     rsi, [rsp+68h+var_20]
0x18000e9cc  mov     rbx, [rsp+68h+arg_8]
0x18000e9d1  mov     r15, [rsp+68h+var_38]
0x18000e9d6  add     rsp, 50h
0x18000e9da  pop     r13
0x18000e9dc  pop     r12
0x18000e9de  pop     rbp
0x18000e9df  retn
0x18000e9e0  mov     edx, 5
0x18000e9e5  mov     ecx, 10h
0x18000e9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ef  mov     [r15+10h], rax
0x18000e9f3  test    rax, rax
0x18000e9f6  jz      short loc_18000E9AC
0x18000e9f8  mov     r12d, [rsp+68h+arg_10]
0x18000ea00  xor     ebp, ebp
0x18000ea02  xor     esi, esi
0x18000ea04  nop     dword ptr [rax+00h]
0x18000ea08  nop     dword ptr [rax+rax+00000000h]
0x18000ea10  mov     rbx, [r13+8]
0x18000ea14  test    rbx, rbx
0x18000ea17  jz      loc_18000ED94
0x18000ea1d  mov     eax, [rbx]
0x18000ea1f  cmp     esi, eax
0x18000ea21  jge     loc_18000EB29
0x18000ea27  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000ea2f  jz      loc_18000ECE4
0x18000ea35  mov     rax, cs:qword_180095A20
0x18000ea3c  test    rax, rax
0x18000ea3f  jz      loc_18000ED5D
0x18000ea45  movsxd  rdx, esi
0x18000ea48  mov     rcx, rbx
0x18000ea4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea50  mov     r14, rax
0x18000ea53  cmp     [rsp+68h+arg_20], 0
0x18000ea5b  jz      loc_18000EB05
0x18000ea61  test    byte ptr [r14+1Ch], 1
0x18000ea66  jz      loc_18000EB1F
0x18000ea6c  mov     rbx, [r14+8]
0x18000ea70  mov     rcx, rbx; Sid
0x18000ea73  call    ?IsSidLocalMachineAndUnknown@@YAHPEAX@Z; IsSidLocalMachineAndUnknown(void *)
0x18000ea78  test    eax, eax
0x18000ea7a  jnz     loc_18000EB1F
0x18000ea80  test    r12d, r12d
0x18000ea83  jnz     loc_18000EC15
0x18000ea89  mov     rcx, rbx; pSid
0x18000ea8c  call    cs:__imp_GetSidSubAuthorityCount
0x18000ea92  test    rax, rax
0x18000ea95  jz      short loc_18000EAA7
0x18000ea97  xor     edx, edx; nSubAuthority
0x18000ea99  mov     rcx, rbx; pSid
0x18000ea9c  call    cs:__imp_GetSidSubAuthority
0x18000eaa2  cmp     dword ptr [rax], 50h ; 'P'
0x18000eaa5  jz      short loc_18000EB1F
0x18000eaa7  xor     ebx, ebx
0x18000eaa9  nop     dword ptr [rax+00000000h]
0x18000eab0  cmp     ebx, 0Bh
0x18000eab3  jnb     short loc_18000EAD5
0x18000eab5  mov     rcx, [r14+8]; pSid
0x18000eab9  lea     rax, __ImageBase
0x18000eac0  mov     edx, ds:rva dword_180082BA0[rax+rbx*4]; WellKnownSidType
0x18000eac7  call    cs:__imp_IsWellKnownSid
0x18000eacd  test    eax, eax
0x18000eacf  jnz     short loc_18000EB1F
0x18000ead1  inc     ebx
0x18000ead3  jmp     short loc_18000EAB0
0x18000ead5  test    byte ptr [r14+1Ch], 20h
0x18000eada  jz      short loc_18000EB05
0x18000eadc  xor     ebx, ebx
0x18000eade  xchg    ax, ax
0x18000eae0  cmp     ebx, 2
0x18000eae3  jnb     short loc_18000EB05
0x18000eae5  mov     rcx, [r14+8]; pSid
0x18000eae9  lea     rax, __ImageBase
0x18000eaf0  mov     edx, ds:rva dword_180082B98[rax+rbx*4]; WellKnownSidType
0x18000eaf7  call    cs:__imp_IsWellKnownSid
0x18000eafd  test    eax, eax
0x18000eaff  jnz     short loc_18000EB1F
0x18000eb01  inc     ebx
0x18000eb03  jmp     short loc_18000EAE0
0x18000eb05  mov     ecx, [r14+4]; unsigned int
0x18000eb09  call    ?GetRoleForItemAccessMask@@YA?AW4SHARE_ROLE@@K@Z; GetRoleForItemAccessMask(ulong)
0x18000eb0e  mov     rdx, [r14+8]; void *
0x18000eb12  mov     r8d, eax; enum SHARE_ROLE
0x18000eb15  mov     rcx, r15; this
0x18000eb18  call    ?_MergePermission@CSharePermissionList@@AEAAJPEAXW4SHARE_ROLE@@@Z; CSharePermissionList::_MergePermission(void *,SHARE_ROLE)
0x18000eb1d  mov     ebp, eax
0x18000eb1f  inc     esi
0x18000eb21  test    ebp, ebp
0x18000eb23  jns     loc_18000EA10
0x18000eb29  mov     r12d, [rsp+68h+arg_18]
0x18000eb31  test    ebp, ebp
0x18000eb33  js      loc_18000E9AC
0x18000eb39  test    r12d, r12d
0x18000eb3c  jz      loc_18000ECA0
0x18000eb42  mov     r12d, [rsp+68h+arg_20]
0x18000eb4a  xor     ebp, ebp
0x18000eb4c  xor     esi, esi
0x18000eb4e  xchg    ax, ax
0x18000eb50  mov     rbx, [r13+10h]
0x18000eb54  test    rbx, rbx
0x18000eb57  jz      loc_18000ED9B
0x18000eb5d  mov     eax, [rbx]
0x18000eb5f  cmp     esi, eax
0x18000eb61  jge     loc_18000EC98
0x18000eb67  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000eb6f  jz      loc_18000ED1B
0x18000eb75  mov     rax, cs:qword_180095A20
0x18000eb7c  test    rax, rax
0x18000eb7f  jz      loc_18000ED70
0x18000eb85  movsxd  rdx, esi
0x18000eb88  mov     rcx, rbx
0x18000eb8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb90  mov     rdi, rax
0x18000eb93  test    r12d, r12d
0x18000eb96  jz      loc_18000EC75
0x18000eb9c  test    byte ptr [rdi+1Ch], 1
0x18000eba0  jz      loc_18000EC8E
0x18000eba6  mov     rbx, [rdi+8]
0x18000ebaa  mov     rcx, rbx; Sid
0x18000ebad  call    ?IsSidLocalMachineAndUnknown@@YAHPEAX@Z; IsSidLocalMachineAndUnknown(void *)
0x18000ebb2  test    eax, eax
0x18000ebb4  jnz     loc_18000EC8E
0x18000ebba  cmp     [rsp+68h+arg_10], eax
0x18000ebc1  jnz     loc_18000ECB3
0x18000ebc7  mov     rcx, rbx; pSid
0x18000ebca  call    cs:__imp_GetSidSubAuthorityCount
0x18000ebd0  test    rax, rax
0x18000ebd3  jz      short loc_18000EBE9
0x18000ebd5  xor     edx, edx; nSubAuthority
0x18000ebd7  mov     rcx, rbx; pSid
0x18000ebda  call    cs:__imp_GetSidSubAuthority
0x18000ebe0  cmp     dword ptr [rax], 50h ; 'P'
0x18000ebe3  jz      loc_18000EC8E
0x18000ebe9  xor     ebx, ebx
0x18000ebeb  nop     dword ptr [rax+rax+00h]
0x18000ebf0  cmp     ebx, 0Bh
0x18000ebf3  jnb     short loc_18000EC43
0x18000ebf5  mov     rcx, [rdi+8]; pSid
0x18000ebf9  lea     rax, __ImageBase
0x18000ec00  mov     edx, ds:rva dword_180082BA0[rax+rbx*4]; WellKnownSidType
0x18000ec07  call    cs:__imp_IsWellKnownSid
0x18000ec0d  test    eax, eax
0x18000ec0f  jnz     short loc_18000EC8E
0x18000ec11  inc     ebx
0x18000ec13  jmp     short loc_18000EBF0
0x18000ec15  mov     eax, [r14+1Ch]
0x18000ec19  test    al, 20h
0x18000ec1b  jnz     loc_18000EA89
0x18000ec21  test    al, 1
0x18000ec23  jz      loc_18000EA89
0x18000ec29  movzx   eax, byte ptr [r14+1]
0x18000ec2e  test    al, al
0x18000ec30  jz      loc_18000EB1F
0x18000ec36  cmp     al, 9
0x18000ec38  jnz     loc_18000EA89
0x18000ec3e  jmp     loc_18000EB1F
0x18000ec43  test    byte ptr [rdi+1Ch], 20h
0x18000ec47  jz      short loc_18000EC75
0x18000ec49  xor     ebx, ebx
0x18000ec4b  nop     dword ptr [rax+rax+00h]
0x18000ec50  cmp     ebx, 2
0x18000ec53  jnb     short loc_18000EC75
0x18000ec55  mov     rcx, [rdi+8]; pSid
0x18000ec59  lea     rax, __ImageBase
0x18000ec60  mov     edx, ds:rva dword_180082B98[rax+rbx*4]; WellKnownSidType
0x18000ec67  call    cs:__imp_IsWellKnownSid
0x18000ec6d  test    eax, eax
0x18000ec6f  jnz     short loc_18000EC8E
0x18000ec71  inc     ebx
0x18000ec73  jmp     short loc_18000EC50
0x18000ec75  mov     ecx, [rdi+4]; unsigned int
0x18000ec78  call    ?GetRoleForItemAccessMask@@YA?AW4SHARE_ROLE@@K@Z; GetRoleForItemAccessMask(ulong)
0x18000ec7d  mov     rdx, [rdi+8]; void *
0x18000ec81  mov     r8d, eax; enum SHARE_ROLE
0x18000ec84  mov     rcx, r15; this
0x18000ec87  call    ?_MergePermission@CSharePermissionList@@AEAAJPEAXW4SHARE_ROLE@@@Z; CSharePermissionList::_MergePermission(void *,SHARE_ROLE)
0x18000ec8c  mov     ebp, eax
0x18000ec8e  inc     esi
0x18000ec90  test    ebp, ebp
0x18000ec92  jns     loc_18000EB50
0x18000ec98  test    ebp, ebp
0x18000ec9a  js      loc_18000E9AC
0x18000eca0  mov     rcx, [rsp+68h+Sid]; Sid
0x18000eca5  test    rcx, rcx
0x18000eca8  jz      loc_18000E98D
0x18000ecae  jmp     loc_18000E946
0x18000ecb3  mov     eax, [rdi+1Ch]
0x18000ecb6  test    al, 20h
0x18000ecb8  jnz     loc_18000EBC7
0x18000ecbe  test    al, 1
0x18000ecc0  jz      loc_18000EBC7
0x18000ecc6  movzx   eax, byte ptr [rdi+1]
0x18000ecca  test    al, al
0x18000eccc  jz      short loc_18000EC8E
0x18000ecce  cmp     al, 9
0x18000ecd0  jnz     loc_18000EBC7
0x18000ecd6  jmp     short loc_18000EC8E
0x18000ecd8  mov     eax, ebp
0x18000ecda  add     rsp, 50h
0x18000ecde  pop     r13
0x18000ece0  pop     r12
0x18000ece2  pop     rbp
0x18000ece3  retn
0x18000ece4  cmp     cs:g_hinstCC, 0
0x18000ecec  jnz     short loc_18000ECFD
0x18000ecee  call    DelayLoadCC
0x18000ecf3  cmp     cs:g_hinstCC, 0
0x18000ecfb  jz      short loc_18000ED52
0x18000ecfd  mov     rcx, cs:g_hinstCC; hModule
0x18000ed04  mov     edx, 14Ch; lpProcName
0x18000ed09  call    cs:__imp_GetProcAddress
0x18000ed0f  mov     cs:qword_180095A20, rax
0x18000ed16  jmp     loc_18000EA35
0x18000ed1b  cmp     cs:g_hinstCC, 0
0x18000ed23  jnz     short loc_18000ED34
0x18000ed25  call    DelayLoadCC
0x18000ed2a  cmp     cs:g_hinstCC, 0
0x18000ed32  jz      short loc_18000ED65
0x18000ed34  mov     rcx, cs:g_hinstCC; hModule
0x18000ed3b  mov     edx, 14Ch; lpProcName
0x18000ed40  call    cs:__imp_GetProcAddress
0x18000ed46  mov     cs:qword_180095A20, rax
0x18000ed4d  jmp     loc_18000EB75
0x18000ed52  mov     cs:qword_180095A20, 0
0x18000ed5d  xor     r14d, r14d
0x18000ed60  jmp     loc_18000EA53
0x18000ed65  mov     cs:qword_180095A20, 0
0x18000ed70  xor     edi, edi
0x18000ed72  jmp     loc_18000EB93
0x18000ed77  mov     edx, 140h
0x18000ed7c  lea     rcx, qword_180095A50
0x18000ed83  call    _GetProcFromComCtl32
0x18000ed88  mov     rax, cs:qword_180095A50
0x18000ed8f  jmp     loc_18000E923
0x18000ed94  xor     eax, eax
0x18000ed96  jmp     loc_18000EA1F
  ... truncated ...
```
