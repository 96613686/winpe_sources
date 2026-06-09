# RefsNotifyAccessCheck

- ea: `0x1c014d668`
- end: `0x1c014d914`
- name: `RefsNotifyAccessCheck`
- size: `684`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c014d920`
- `0x1c01c5620`

## callees

- `0x1c0005650`
- `0x1c000f480`
- `0x1c0014110`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c014d668`
- `0x1c016aad0`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c014d789`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c014d789`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c014d7f1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c014d7f1`
- `ntoskrnl!SeLockSubjectContext` at `0x1c014d7b1`
- `ntoskrnl!SeLockSubjectContext` at `0x1c014d7b1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c014d883`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c014d8e3`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c014d883`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c014d8e3`
- `ntoskrnl!SeAccessCheck` at `0x1c014d836`
- `ntoskrnl!SeAccessCheck` at `0x1c014d836`

## pseudocode

```c
char __fastcall RefsNotifyAccessCheck(__int64 a1, _QWORD *a2, struct _SECURITY_SUBJECT_CONTEXT *a3, ACCESS_MASK a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  BOOLEAN v10; // r14
  char v11; // r12
  _BYTE *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r13
  __int64 v16; // rax
  void *v17; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  _BYTE *v20; // [rsp+58h] [rbp-270h] BYREF
  int AccessStatus; // [rsp+60h] [rbp-268h] BYREF
  DWORD GrantedAccess[3]; // [rsp+64h] [rbp-264h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+70h] [rbp-258h] BYREF
  _QWORD *v24; // [rsp+78h] [rbp-250h]
  struct _SECURITY_SUBJECT_CONTEXT *v25; // [rsp+80h] [rbp-248h]
  _BYTE Irp[248]; // [rsp+88h] [rbp-240h] BYREF
  _BYTE v27[256]; // [rsp+180h] [rbp-148h] BYREF

  v25 = a3;
  memset(Irp, 0, 40);
  memset(v27, 0, sizeof(v27));
  memset(&Irp[40], 0, 0xD0u);
  v10 = 0;
  v11 = 0;
  GrantedAccess[0] = 0;
  AccessStatus = 0;
  Privileges = 0;
  if ( !a2 || !a4 )
    return 1;
  v20 = v27;
  LOBYTE(v9) = 1;
  LOBYTE(v8) = 1;
  RefsInitializeIrpContext(0, v8, v9, &v20);
  v12 = v20;
  *((_QWORD *)v20 + 9) = &Irp[40];
  *((_QWORD *)v12 + 8) = a2[11];
  LOBYTE(v13) = 1;
  RefsInitializeTopLevelIrp(Irp, v13, 0);
  v14 = *(_QWORD *)&Irp[32];
  if ( !*(_QWORD *)&Irp[32] )
  {
    *(_DWORD *)&Irp[4] = 1397140410;
    *(_QWORD *)&Irp[32] = v12;
    *((_DWORD *)v12 + 2) |= 0x100000u;
    IoSetTopLevelIrp((PIRP)Irp);
    v14 = *(_QWORD *)&Irp[32];
  }
  *((_QWORD *)v12 + 13) = v14;
  v24 = *(_QWORD **)(*(_QWORD *)(a1 + 72) + 32LL);
  SeLockSubjectContext(a3);
  if ( (_QWORD *)a2[5] != a2 + 5 )
  {
    do
    {
      v15 = a2[5];
      v16 = a2[23];
      if ( !v16 )
      {
        RefsLoadSecurityDescriptor(v12, a2);
        v16 = a2[23];
      }
      v17 = (void *)(v16 + 20);
      GenericMapping = IoGetFileObjectGenericMapping();
      v10 = SeAccessCheck(v17, a3, 1u, a4, 0, &Privileges, GenericMapping, 1, GrantedAccess, &AccessStatus);
      if ( !v11 )
      {
        v11 = 1;
        if ( byte_1C012E6D4 )
        {
          a4 &= ~1u;
          GrantedAccess[1] = a4;
          if ( !a4 )
            break;
        }
      }
      a2 = *(_QWORD **)(*(_QWORD *)(v15 - 16) + 120LL);
      if ( !v10 )
        break;
    }
    while ( a2 != v24 );
  }
  SeUnlockSubjectContext(a3);
  RefsCleanupIrpContext(v12, 1);
  return v10;
}

```

## disassembly

```asm
0x1c014d668  push    rbx
0x1c014d66a  push    rsi
0x1c014d66b  push    rdi
0x1c014d66c  push    r12
0x1c014d66e  push    r13
0x1c014d670  push    r14
0x1c014d672  push    r15
0x1c014d674  sub     rsp, 290h
0x1c014d67b  mov     rax, cs:__security_cookie
0x1c014d682  xor     rax, rsp
0x1c014d685  mov     [rsp+2C8h+var_48], rax
0x1c014d68d  mov     esi, r9d
0x1c014d690  mov     r15, r8
0x1c014d693  mov     rbx, rdx
0x1c014d696  mov     r13, rcx
0x1c014d699  mov     [rsp+2C8h+var_248], r8
0x1c014d6a1  xorps   xmm0, xmm0
0x1c014d6a4  xor     eax, eax
0x1c014d6a6  movups  xmmword ptr [rsp+2C8h+Irp], xmm0
0x1c014d6ae  movups  xmmword ptr [rsp+2C8h+Irp+10h], xmm0
0x1c014d6b6  mov     qword ptr [rsp+2C8h+Irp+20h], rax
0x1c014d6be  xor     edx, edx; Val
0x1c014d6c0  mov     r8d, 100h; Size
0x1c014d6c6  lea     rcx, [rsp+2C8h+var_148]; void *
0x1c014d6ce  call    memset
0x1c014d6d3  xor     edx, edx; Val
0x1c014d6d5  mov     r8d, 0D0h; Size
0x1c014d6db  lea     rcx, [rsp+2C8h+Irp+28h]; void *
0x1c014d6e3  call    memset
0x1c014d6e8  xor     eax, eax
0x1c014d6ea  mov     r14b, al
0x1c014d6ed  mov     [rsp+2C8h+var_278], al
0x1c014d6f1  mov     r12b, al
0x1c014d6f4  mov     [rsp+2C8h+var_264], eax
0x1c014d6f8  mov     [rsp+2C8h+var_268], eax
0x1c014d6fc  mov     [rsp+2C8h+var_258], rax
0x1c014d701  test    rbx, rbx
0x1c014d704  jz      loc_1C014D8AD
0x1c014d70a  test    esi, esi
0x1c014d70c  jz      loc_1C014D8AD
0x1c014d712  lea     rax, [rsp+2C8h+var_148]
0x1c014d71a  mov     [rsp+2C8h+var_270], rax
0x1c014d71f  lea     r9, [rsp+2C8h+var_270]
0x1c014d724  mov     r8b, 1
0x1c014d727  mov     dl, r8b
0x1c014d72a  xor     ecx, ecx
0x1c014d72c  call    RefsInitializeIrpContext
0x1c014d731  lea     rax, [rsp+2C8h+Irp+28h]
0x1c014d739  mov     rdi, [rsp+2C8h+var_270]
0x1c014d73e  mov     [rdi+48h], rax
0x1c014d742  mov     rax, [rbx+58h]
0x1c014d746  mov     [rdi+40h], rax
0x1c014d74a  xor     r8d, r8d
0x1c014d74d  mov     dl, 1
0x1c014d74f  lea     rcx, [rsp+2C8h+Irp]
0x1c014d757  call    RefsInitializeTopLevelIrp
0x1c014d75c  mov     rax, qword ptr [rsp+2C8h+Irp+20h]
0x1c014d764  test    rax, rax
0x1c014d767  jnz     short loc_1C014D79D
0x1c014d769  mov     dword ptr [rsp+2C8h+Irp+4], 5346ABBAh
0x1c014d774  mov     qword ptr [rsp+2C8h+Irp+20h], rdi
0x1c014d77c  bts     dword ptr [rdi+8], 14h
0x1c014d781  lea     rcx, [rsp+2C8h+Irp]; Irp
0x1c014d789  call    cs:__imp_IoSetTopLevelIrp
0x1c014d790  nop     dword ptr [rax+rax+00h]
0x1c014d795  mov     rax, qword ptr [rsp+2C8h+Irp+20h]
0x1c014d79d  mov     [rdi+68h], rax
0x1c014d7a1  mov     rax, [r13+48h]
0x1c014d7a5  mov     rax, [rax+20h]
0x1c014d7a9  mov     [rsp+2C8h+var_250], rax
0x1c014d7ae  mov     rcx, r15; SubjectContext
0x1c014d7b1  call    cs:__imp_SeLockSubjectContext
0x1c014d7b8  nop     dword ptr [rax+rax+00h]
0x1c014d7bd  nop
0x1c014d7be  lea     rax, [rbx+28h]
0x1c014d7c2  cmp     [rax], rax
0x1c014d7c5  jz      loc_1C014D880
0x1c014d7cb  mov     r13, [rbx+28h]
0x1c014d7cf  mov     rax, [rbx+0B8h]
0x1c014d7d6  test    rax, rax
0x1c014d7d9  jnz     short loc_1C014D7ED
0x1c014d7db  mov     rdx, rbx
0x1c014d7de  mov     rcx, rdi
0x1c014d7e1  call    RefsLoadSecurityDescriptor
0x1c014d7e6  mov     rax, [rbx+0B8h]
0x1c014d7ed  lea     rbx, [rax+14h]
0x1c014d7f1  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c014d7f8  nop     dword ptr [rax+rax+00h]
0x1c014d7fd  lea     rcx, [rsp+2C8h+var_268]
0x1c014d802  mov     [rsp+2C8h+AccessStatus], rcx; AccessStatus
0x1c014d807  lea     rcx, [rsp+2C8h+var_264]
0x1c014d80c  mov     [rsp+2C8h+GrantedAccess], rcx; GrantedAccess
0x1c014d811  mov     [rsp+2C8h+AccessMode], 1; AccessMode
0x1c014d816  mov     [rsp+2C8h+GenericMapping], rax; GenericMapping
0x1c014d81b  lea     rax, [rsp+2C8h+var_258]
0x1c014d820  mov     [rsp+2C8h+Privileges], rax; Privileges
0x1c014d825  and     [rsp+2C8h+var_2A8], 0
0x1c014d82a  mov     r9d, esi; DesiredAccess
0x1c014d82d  mov     r8b, 1; SubjectContextLocked
0x1c014d830  mov     rdx, r15; SubjectSecurityContext
0x1c014d833  mov     rcx, rbx; SecurityDescriptor
0x1c014d836  call    cs:__imp_SeAccessCheck
0x1c014d83d  nop     dword ptr [rax+rax+00h]
0x1c014d842  mov     r14b, al
0x1c014d845  mov     [rsp+2C8h+var_278], al
0x1c014d849  test    r12b, r12b
0x1c014d84c  jnz     short loc_1C014D868
0x1c014d84e  mov     r12b, 1
0x1c014d851  mov     [rsp+2C8h+var_277], r12b
0x1c014d856  cmp     cs:byte_1C012E6D4, 0
0x1c014d85d  jz      short loc_1C014D868
0x1c014d85f  and     esi, 0FFFFFFFEh
0x1c014d862  mov     [rsp+2C8h+var_260], esi
0x1c014d866  jz      short loc_1C014D880
0x1c014d868  mov     rax, [r13-10h]
0x1c014d86c  mov     rbx, [rax+78h]
0x1c014d870  test    r14b, r14b
0x1c014d873  jz      short loc_1C014D880
0x1c014d875  cmp     rbx, [rsp+2C8h+var_250]
0x1c014d87a  jnz     loc_1C014D7CB
0x1c014d880  mov     rcx, r15; SubjectContext
0x1c014d883  call    cs:__imp_SeUnlockSubjectContext
0x1c014d88a  nop     dword ptr [rax+rax+00h]
0x1c014d88f  jmp     short loc_1C014D89B
0x1c014d891  mov     rdi, [rsp+2C8h+var_270]
0x1c014d896  mov     r14b, [rsp+2C8h+var_278]
0x1c014d89b  mov     edx, 1
0x1c014d8a0  mov     rcx, rdi
0x1c014d8a3  call    RefsCleanupIrpContext
0x1c014d8a8  mov     al, r14b
0x1c014d8ab  jmp     short loc_1C014D8AF
0x1c014d8ad  mov     al, 1
0x1c014d8af  mov     rcx, [rsp+2C8h+var_48]
0x1c014d8b7  xor     rcx, rsp; StackCookie
0x1c014d8ba  call    __security_check_cookie
0x1c014d8bf  add     rsp, 290h
0x1c014d8c6  pop     r15
0x1c014d8c8  pop     r14
0x1c014d8ca  pop     r13
0x1c014d8cc  pop     r12
0x1c014d8ce  pop     rdi
0x1c014d8cf  pop     rsi
0x1c014d8d0  pop     rbx
0x1c014d8d1  retn
0x1c014d8d3  push    rbp
0x1c014d8d5  sub     rsp, 50h
0x1c014d8d9  mov     rbp, rdx
0x1c014d8dc  mov     rcx, [rbp+80h]; SubjectContext
0x1c014d8e3  call    cs:__imp_SeUnlockSubjectContext
0x1c014d8ea  nop     dword ptr [rax+rax+00h]
0x1c014d8ef  nop
0x1c014d8f0  add     rsp, 50h
0x1c014d8f4  pop     rbp
0x1c014d8f5  retn
0x1c014d8f7  push    rbp
0x1c014d8f9  sub     rsp, 50h
0x1c014d8fd  mov     rbp, rdx
0x1c014d900  mov     rdx, rcx
0x1c014d903  mov     rcx, [rbp+58h]
0x1c014d907  call    RefsExceptionFilter
0x1c014d90c  nop
0x1c014d90d  add     rsp, 50h
0x1c014d911  pop     rbp
0x1c014d912  retn
```
