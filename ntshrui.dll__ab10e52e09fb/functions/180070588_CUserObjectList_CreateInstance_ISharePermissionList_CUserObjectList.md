# CUserObjectList::CreateInstance(ISharePermissionList *,CUserObjectList * *)

- ea: `0x180070588`
- end: `0x18007071a`
- name: `?CreateInstance@CUserObjectList@@SAJPEAUISharePermissionList@@PEAPEAV1@@Z`
- size: `402`
- prototype: `__int64 __fastcall(struct ISharePermissionList *, struct CUserObjectList **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006ebf0`
- `0x1800719c4`

## callees

- `0x1800098dc`
- `0x1800259bc`
- `0x180053fd4`
- `0x180065e18`
- `0x18007029c`
- `0x180070588`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800706d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800706d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800706e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800706e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007064c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007064c`

## pseudocode

```c
__int64 __fastcall CUserObjectList::CreateInstance(struct ISharePermissionList *a1, struct CUserObjectList **a2)
{
  int Error; // ebx
  CUserObjectList *v5; // rax
  CUserObjectList *v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // edx
  unsigned int v9; // r14d
  __int64 v10; // rax
  PSID *v11; // rsi
  int v12; // edx
  unsigned int v13; // edx
  PSID Sid; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR StringSid; // [rsp+38h] [rbp-18h] BYREF
  PSID *v17; // [rsp+40h] [rbp-10h]
  CUserObjectList *v18; // [rsp+A0h] [rbp+50h] BYREF
  int v19; // [rsp+A8h] [rbp+58h] BYREF

  Error = -2147024882;
  v5 = (CUserObjectList *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v18 = v5;
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *((_DWORD *)v5 + 6) = 0;
    v7 = *(_QWORD *)a1;
    LODWORD(v18) = 0;
    Error = (*(__int64 (__fastcall **)(struct ISharePermissionList *, CUserObjectList **))(v7 + 32))(a1, &v18);
    v9 = 0;
    if ( Error < 0 )
    {
LABEL_13:
      CUserObjectList::`scalar deleting destructor'(v6, v8);
    }
    else
    {
      while ( v9 < (unsigned int)v18 )
      {
        v10 = *(_QWORD *)a1;
        StringSid = 0;
        v19 = 0;
        Error = (*(__int64 (__fastcall **)(struct ISharePermissionList *, _QWORD, LPCWSTR *, int *))(v10 + 40))(
                  a1,
                  v9,
                  &StringSid,
                  &v19);
        if ( Error >= 0 )
        {
          Sid = 0;
          if ( ConvertStringSidToSidW(StringSid, &Sid) || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            v17 = (PSID *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
            v11 = v17;
            if ( v17 )
            {
              v12 = v19;
              *v17 = Sid;
              v11[1] = 0;
              v11[2] = 0;
              v11[3] = 0;
              v11[4] = 0;
              v11[5] = (PSID)8;
              *((_DWORD *)v11 + 13) = 1;
              v11[7] = 0;
              *((_DWORD *)v11 + 12) = v12;
              Error = CUserObjectList::AddUser(v6, (struct CUserObject *)v11);
              if ( Error < 0 )
                CUserObject::`scalar deleting destructor'((CUserObject *)v11, v13);
            }
            else
            {
              Error = -2147024882;
              LocalFree(Sid);
            }
          }
          CoTaskMemFree((LPVOID)StringSid);
        }
        ++v9;
        if ( Error < 0 )
          goto LABEL_13;
      }
      *a2 = v6;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180070588  mov     [rsp-38h+arg_0], rbx
0x18007058d  push    rbp
0x18007058e  push    rsi
0x18007058f  push    rdi
0x180070590  push    r12
0x180070592  push    r13
0x180070594  push    r14
0x180070596  push    r15
0x180070598  mov     rbp, rsp
0x18007059b  sub     rsp, 50h
0x18007059f  mov     r12, rdx
0x1800705a2  mov     r15, rcx
0x1800705a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800705ac  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800705b1  mov     ebx, 8007000Eh
0x1800705b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800705bb  xor     r13d, r13d
0x1800705be  mov     [rbp+arg_10], rax
0x1800705c2  mov     rdi, rax
0x1800705c5  test    rax, rax
0x1800705c8  jz      loc_1800706FA
0x1800705ce  mov     [rax], r13
0x1800705d1  mov     [rax+8], r13
0x1800705d5  mov     [rax+10h], r13
0x1800705d9  mov     [rax+18h], r13d
0x1800705dd  test    rax, rax
0x1800705e0  jz      loc_1800706FA
0x1800705e6  mov     rax, [r15]
0x1800705e9  lea     rdx, [rbp+arg_10]
0x1800705ed  mov     rcx, r15
0x1800705f0  mov     dword ptr [rbp+arg_10], r13d
0x1800705f4  mov     rax, [rax+20h]
0x1800705f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800705fd  mov     ebx, eax
0x1800705ff  mov     r14d, r13d
0x180070602  test    eax, eax
0x180070604  js      loc_1800706F2
0x18007060a  cmp     r14d, dword ptr [rbp+arg_10]
0x18007060e  jnb     loc_180070714
0x180070614  mov     rax, [r15]
0x180070617  lea     r9, [rbp+arg_18]
0x18007061b  lea     r8, [rbp+StringSid]
0x18007061f  mov     [rbp+StringSid], r13
0x180070623  mov     edx, r14d
0x180070626  mov     [rbp+arg_18], r13d
0x18007062a  mov     rcx, r15
0x18007062d  mov     rax, [rax+28h]
0x180070631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070636  mov     ebx, eax
0x180070638  test    eax, eax
0x18007063a  js      loc_1800706E7
0x180070640  mov     rcx, [rbp+StringSid]; StringSid
0x180070644  lea     rdx, [rbp+Sid]; Sid
0x180070648  mov     [rbp+Sid], r13
0x18007064c  call    cs:__imp_ConvertStringSidToSidW
0x180070652  test    eax, eax
0x180070654  jnz     short loc_180070661
0x180070656  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18007065b  mov     ebx, eax
0x18007065d  test    eax, eax
0x18007065f  js      short loc_1800706DD
0x180070661  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180070668  mov     ecx, 40h ; '@'; unsigned __int64
0x18007066d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180070672  mov     [rbp+var_10], rax
0x180070676  mov     rsi, rax
0x180070679  test    rax, rax
0x18007067c  jz      short loc_1800706CE
0x18007067e  mov     rax, [rbp+Sid]
0x180070682  mov     edx, [rbp+arg_18]
0x180070685  mov     [rsi], rax
0x180070688  mov     [rsi+8], r13
0x18007068c  mov     [rsi+10h], r13
0x180070690  mov     [rsi+18h], r13
0x180070694  mov     [rsi+20h], r13
0x180070698  mov     qword ptr [rsi+28h], 8
0x1800706a0  mov     dword ptr [rsi+34h], 1
0x1800706a7  mov     [rsi+38h], r13
0x1800706ab  mov     [rsi+30h], edx
0x1800706ae  test    rsi, rsi
0x1800706b1  jz      short loc_1800706CE
0x1800706b3  mov     rdx, rsi; struct CUserObject *
0x1800706b6  mov     rcx, rdi; this
0x1800706b9  call    ?AddUser@CUserObjectList@@QEAAJPEAVCUserObject@@@Z; CUserObjectList::AddUser(CUserObject *)
0x1800706be  mov     ebx, eax
0x1800706c0  test    eax, eax
0x1800706c2  jns     short loc_1800706DD
0x1800706c4  mov     rcx, rsi; this
0x1800706c7  call    ??_GCUserObject@@QEAAPEAXI@Z; CUserObject::`scalar deleting destructor'(uint)
0x1800706cc  jmp     short loc_1800706DD
0x1800706ce  mov     rcx, [rbp+Sid]; hMem
0x1800706d2  mov     ebx, 8007000Eh
0x1800706d7  call    cs:__imp_LocalFree
0x1800706dd  mov     rcx, [rbp+StringSid]; pv
0x1800706e1  call    cs:__imp_CoTaskMemFree
0x1800706e7  inc     r14d
0x1800706ea  test    ebx, ebx
0x1800706ec  jns     loc_18007060A
0x1800706f2  mov     rcx, rdi; this
0x1800706f5  call    ??_GCUserObjectList@@QEAAPEAXI@Z; CUserObjectList::`scalar deleting destructor'(uint)
0x1800706fa  mov     eax, ebx
0x1800706fc  mov     rbx, [rsp+50h+arg_0]
0x180070704  add     rsp, 50h
0x180070708  pop     r15
0x18007070a  pop     r14
0x18007070c  pop     r13
0x18007070e  pop     r12
0x180070710  pop     rdi
0x180070711  pop     rsi
0x180070712  pop     rbp
0x180070713  retn
0x180070714  mov     [r12], rdi
0x180070718  jmp     short loc_1800706FA
```
