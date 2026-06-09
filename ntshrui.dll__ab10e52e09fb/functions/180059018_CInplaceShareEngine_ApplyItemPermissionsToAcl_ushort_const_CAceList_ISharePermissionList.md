# CInplaceShareEngine::_ApplyItemPermissionsToAcl(ushort const *,CAceList *,ISharePermissionList *)

- ea: `0x180059018`
- end: `0x18005920c`
- name: `?_ApplyItemPermissionsToAcl@CInplaceShareEngine@@AEAAJPEBGPEAVCAceList@@PEAUISharePermissionList@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(CInplaceShareEngine *__hidden this, const unsigned __int16 *, struct CAceList *, struct ISharePermissionList *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18005c1d0`

## callees

- `0x1800098dc`
- `0x18000f250`
- `0x18000f720`
- `0x18000f840`
- `0x1800553a4`
- `0x1800564bc`
- `0x180059018`
- `0x18005dd18`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180059119`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180059119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800591d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800591d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800591e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800591e6`
- `SHLWAPI!PathIsDirectoryW` at `0x180059142`
- `SHLWAPI!PathIsDirectoryW` at `0x180059142`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800590c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800590c3`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::_ApplyItemPermissionsToAcl(
        CInplaceShareEngine *this,
        const unsigned __int16 *a2,
        struct CAceList *a3,
        struct ISharePermissionList *a4)
{
  __int64 v4; // rax
  CInplaceShareEngine *v5; // rsi
  struct ISharePermissionList *v6; // rdi
  struct CAceList *v7; // r13
  int updated; // ebx
  unsigned int v9; // r12d
  __int64 v10; // rax
  SHARE_ROLE v11; // edi
  int i; // esi
  struct _DPA *v13; // rcx
  int v14; // eax
  PVOID Ptr; // r15
  enum SHARE_ROLE RoleForItemAccessMask; // r14d
  BOOL IsDirectoryW; // eax
  __int64 v18; // r8
  __int64 v19; // rcx
  char v20; // si
  PSID v21; // rdx
  char *v22; // r9
  int v23; // eax
  CAceList *v24; // rcx
  int v25; // r10d
  PSID v26; // rdi
  int ItemAccessMaskForRole; // eax
  SHARE_ROLE v29; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-24h] BYREF
  PSID Sid; // [rsp+38h] [rbp-20h] BYREF
  LPCWSTR StringSid[3]; // [rsp+40h] [rbp-18h] BYREF

  v4 = *(_QWORD *)a4;
  v5 = this;
  v30 = 0;
  v6 = a4;
  v7 = a3;
  updated = (*(__int64 (__fastcall **)(struct ISharePermissionList *, unsigned int *))(v4 + 32))(a4, &v30);
  v9 = 0;
  if ( v30 )
  {
    while ( 1 )
    {
      v10 = *(_QWORD *)v6;
      StringSid[0] = 0;
      v29 = SHARE_ROLE_READER;
      updated = (*(__int64 (__fastcall **)(struct ISharePermissionList *, _QWORD, LPCWSTR *, SHARE_ROLE *))(v10 + 40))(
                  v6,
                  v9,
                  StringSid,
                  &v29);
      if ( updated >= 0 )
        break;
LABEL_31:
      if ( ++v9 >= v30 )
        return (unsigned int)updated;
    }
    if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v5 + 2) + 8LL))(
            (__int64)v5 + 16,
            (unsigned int)v29) )
    {
      Sid = 0;
      if ( ConvertStringSidToSidW(StringSid[0], &Sid) )
      {
        updated = 0;
LABEL_7:
        v11 = SHARE_ROLE_INVALID;
        for ( i = 0; ; ++i )
        {
          v13 = (struct _DPA *)*((_QWORD *)v7 + 2);
          v14 = v13 ? *(_DWORD *)v13 : 0;
          if ( i >= v14 )
            break;
          Ptr = DPA_GetPtr(v13, i);
          RoleForItemAccessMask = GetRoleForItemAccessMask(*((_DWORD *)Ptr + 1));
          if ( EqualSid(*((PSID *)Ptr + 1), Sid)
            && (*((_BYTE *)Ptr + 28) & 1) != 0
            && RoleForItemAccessMask != SHARE_ROLE_CUSTOM
            && v11 < RoleForItemAccessMask )
          {
            v11 = RoleForItemAccessMask;
          }
        }
        IsDirectoryW = PathIsDirectoryW(a2);
        v19 = (unsigned int)v29;
        v7 = a3;
        v20 = IsDirectoryW ? 3 : 0;
        if ( v11 == SHARE_ROLE_INVALID || v11 < v29 )
        {
          ItemAccessMaskForRole = GetItemAccessMaskForRole(v29);
          v23 = CAceList::SetExplicitAllowAce(a3, Sid, ItemAccessMaskForRole, v20);
        }
        else
        {
          if ( v11 == v29 )
          {
            v21 = Sid;
            v22 = (char *)a3 + 8;
          }
          else
          {
            if ( v11 <= v29 )
              goto LABEL_29;
            GetItemAccessMaskForRole(v29);
            updated = CAceList::_UpdateInheritanceFlag(a3);
            if ( updated < 0 )
              goto LABEL_29;
            v26 = Sid;
            updated = CAceList::SetExplicitAllowAce(v24, Sid, v25, v20);
            if ( updated < 0 )
              goto LABEL_29;
            v20 |= 0x10u;
            v22 = (char *)a3 + 16;
            v21 = v26;
          }
          LOBYTE(v18) = v20;
          v23 = CAceList::_RemoveExplicitAcesHelper(v19, v21, v18, v22, 0);
        }
        updated = v23;
LABEL_29:
        LocalFree(Sid);
        v6 = a4;
        v5 = this;
        goto LABEL_30;
      }
      updated = ResultFromKnownLastError();
      if ( updated >= 0 )
        goto LABEL_7;
    }
LABEL_30:
    CoTaskMemFree((LPVOID)StringSid[0]);
    goto LABEL_31;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180059018  mov     rax, rsp
0x18005901b  mov     [rax+20h], r9
0x18005901f  mov     [rax+18h], r8
0x180059023  mov     [rax+10h], rdx
0x180059027  mov     [rax+8], rcx
0x18005902b  push    rbp
0x18005902c  push    rbx
0x18005902d  push    rsi
0x18005902e  push    rdi
0x18005902f  push    r12
0x180059031  push    r13
0x180059033  push    r14
0x180059035  push    r15
0x180059037  mov     rbp, rsp
0x18005903a  sub     rsp, 58h
0x18005903e  mov     rax, [r9]
0x180059041  lea     rdx, [rbp+var_24]
0x180059045  mov     rsi, rcx
0x180059048  xor     r14d, r14d
0x18005904b  mov     rcx, r9
0x18005904e  mov     [rbp+var_24], r14d
0x180059052  mov     rdi, r9
0x180059055  mov     r13, r8
0x180059058  mov     rax, [rax+20h]
0x18005905c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059061  mov     ebx, eax
0x180059063  mov     r12d, r14d
0x180059066  cmp     [rbp+var_24], r14d
0x18005906a  jbe     loc_1800591F9
0x180059070  mov     rax, [rdi]
0x180059073  lea     r9, [rbp+var_28]
0x180059077  lea     r8, [rbp+StringSid]
0x18005907b  mov     [rbp+StringSid], r14
0x18005907f  mov     edx, r12d
0x180059082  mov     [rbp+var_28], r14d
0x180059086  mov     rcx, rdi
0x180059089  mov     rax, [rax+28h]
0x18005908d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059092  mov     ebx, eax
0x180059094  test    eax, eax
0x180059096  js      loc_1800591EC
0x18005909c  lea     rcx, [rsi+10h]
0x1800590a0  mov     rdx, [rcx]
0x1800590a3  mov     rax, [rdx+8]
0x1800590a7  mov     edx, [rbp+var_28]
0x1800590aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800590af  test    eax, eax
0x1800590b1  jnz     loc_1800591E2
0x1800590b7  mov     rcx, [rbp+StringSid]; StringSid
0x1800590bb  lea     rdx, [rbp+Sid]; Sid
0x1800590bf  mov     [rbp+Sid], r14
0x1800590c3  call    cs:__imp_ConvertStringSidToSidW
0x1800590c9  test    eax, eax
0x1800590cb  jz      short loc_1800590D2
0x1800590cd  mov     ebx, r14d
0x1800590d0  jmp     short loc_1800590E1
0x1800590d2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800590d7  mov     ebx, eax
0x1800590d9  test    eax, eax
0x1800590db  js      loc_1800591E2
0x1800590e1  or      edi, 0FFFFFFFFh
0x1800590e4  mov     esi, r14d
0x1800590e7  mov     rcx, [r13+10h]; hdpa
0x1800590eb  test    rcx, rcx
0x1800590ee  jz      short loc_1800590F4
0x1800590f0  mov     eax, [rcx]
0x1800590f2  jmp     short loc_1800590F7
0x1800590f4  mov     eax, r14d
0x1800590f7  cmp     esi, eax
0x1800590f9  jge     short loc_18005913E
0x1800590fb  movsxd  rdx, esi; i
0x1800590fe  call    DPA_GetPtr
0x180059103  mov     r15, rax
0x180059106  mov     ecx, [rax+4]; unsigned int
0x180059109  call    ?GetRoleForItemAccessMask@@YA?AW4SHARE_ROLE@@K@Z; GetRoleForItemAccessMask(ulong)
0x18005910e  mov     rdx, [rbp+Sid]; pSid2
0x180059112  mov     r14d, eax
0x180059115  mov     rcx, [r15+8]; pSid1
0x180059119  call    cs:__imp_EqualSid
0x18005911f  test    eax, eax
0x180059121  jz      short loc_180059137
0x180059123  test    byte ptr [r15+1Ch], 1
0x180059128  jz      short loc_180059137
0x18005912a  cmp     r14d, 4
0x18005912e  jz      short loc_180059137
0x180059130  cmp     edi, r14d
0x180059133  cmovl   edi, r14d
0x180059137  inc     esi
0x180059139  xor     r14d, r14d
0x18005913c  jmp     short loc_1800590E7
0x18005913e  mov     rcx, [rbp+pszPath]; pszPath
0x180059142  call    cs:__imp_PathIsDirectoryW
0x180059148  mov     ecx, [rbp+var_28]; enum SHARE_ROLE
0x18005914b  neg     eax
0x18005914d  mov     r13, [rbp+arg_10]
0x180059151  sbb     sil, sil
0x180059154  and     sil, 3
0x180059158  cmp     edi, 0FFFFFFFFh
0x18005915b  jz      short loc_1800591B7
0x18005915d  cmp     edi, ecx
0x18005915f  jl      short loc_1800591B7
0x180059161  jnz     short loc_18005917A
0x180059163  mov     rdx, [rbp+Sid]
0x180059167  lea     r9, [r13+8]
0x18005916b  mov     r8b, sil
0x18005916e  mov     [rsp+58h+var_38], r14d
0x180059173  call    ?_RemoveExplicitAcesHelper@CAceList@@AEAAJPEAXEAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@H@Z; CAceList::_RemoveExplicitAcesHelper(void *,uchar,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,int)
0x180059178  jmp     short loc_1800591CE
0x18005917a  jle     short loc_1800591D0
0x18005917c  call    ?GetItemAccessMaskForRole@@YAKW4SHARE_ROLE@@@Z; GetItemAccessMaskForRole(SHARE_ROLE)
0x180059181  mov     rcx, r13; this
0x180059184  mov     r10d, eax
0x180059187  call    ?_UpdateInheritanceFlag@CAceList@@AEAAJXZ; CAceList::_UpdateInheritanceFlag(void)
0x18005918c  mov     ebx, eax
0x18005918e  test    eax, eax
0x180059190  js      short loc_1800591D0
0x180059192  mov     rdi, [rbp+Sid]
0x180059196  mov     r9b, sil; unsigned __int8
0x180059199  mov     rdx, rdi; void *
0x18005919c  mov     r8d, r10d; unsigned int
0x18005919f  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x1800591a4  mov     ebx, eax
0x1800591a6  test    eax, eax
0x1800591a8  js      short loc_1800591D0
0x1800591aa  or      sil, 10h
0x1800591ae  lea     r9, [r13+10h]
0x1800591b2  mov     rdx, rdi
0x1800591b5  jmp     short loc_18005916B
0x1800591b7  call    ?GetItemAccessMaskForRole@@YAKW4SHARE_ROLE@@@Z; GetItemAccessMaskForRole(SHARE_ROLE)
0x1800591bc  mov     rdx, [rbp+Sid]; void *
0x1800591c0  mov     r8d, eax; unsigned int
0x1800591c3  mov     rcx, r13; this
0x1800591c6  mov     r9b, sil; unsigned __int8
0x1800591c9  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x1800591ce  mov     ebx, eax
0x1800591d0  mov     rcx, [rbp+Sid]; hMem
0x1800591d4  call    cs:__imp_LocalFree
0x1800591da  mov     rdi, [rbp+arg_18]
0x1800591de  mov     rsi, [rbp+arg_0]
0x1800591e2  mov     rcx, [rbp+StringSid]; pv
0x1800591e6  call    cs:__imp_CoTaskMemFree
0x1800591ec  inc     r12d
0x1800591ef  cmp     r12d, [rbp+var_24]
0x1800591f3  jb      loc_180059070
0x1800591f9  mov     eax, ebx
0x1800591fb  add     rsp, 58h
0x1800591ff  pop     r15
0x180059201  pop     r14
0x180059203  pop     r13
0x180059205  pop     r12
0x180059207  pop     rdi
0x180059208  pop     rsi
0x180059209  pop     rbx
0x18005920a  pop     rbp
0x18005920b  retn
```
