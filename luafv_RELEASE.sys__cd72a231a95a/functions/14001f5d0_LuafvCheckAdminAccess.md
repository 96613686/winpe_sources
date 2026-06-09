# LuafvCheckAdminAccess

- ea: `0x14001f5d0`
- end: `0x14001f76d`
- name: `LuafvCheckAdminAccess`
- size: `413`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, __m128i *, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018f20`
- `0x14001fc40`
- `0x140025300`

## callees

- `0x14001dcb0`
- `0x14001dd40`
- `0x14001ded0`
- `0x14001f5d0`
- `0x14001f774`

## import_xrefs

- `ntoskrnl!SeAccessCheckFromState` at `0x14001f6be`
- `ntoskrnl!SeAccessCheckFromState` at `0x14001f6be`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001f66f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001f66f`

## pseudocode

```c
__int64 __fastcall LuafvCheckAdminAccess(__int64 a1, struct _FLT_INSTANCE *a2, __m128i *a3, bool *a4)
{
  bool v4; // zf
  __int64 v6; // r13
  int v10; // edi
  ACCESS_MASK v11; // esi
  bool v12; // bl
  int v13; // eax
  __int64 *v14; // rbp
  void *v15; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  __int64 v18; // [rsp+50h] [rbp-48h] BYREF
  PTOKEN_ACCESS_INFORMATION PrimaryTokenInformation[8]; // [rsp+58h] [rbp-40h] BYREF
  int AccessStatus; // [rsp+A0h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+B0h] [rbp+18h] BYREF

  v4 = (a3[2].m128i_i8[8] & 1) == 0;
  v6 = *(_QWORD *)(a1 + 16);
  PrimaryTokenInformation[0] = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  v18 = 0;
  if ( v4 || (v10 = LuafvReadAndCacheSecurityDescriptor(a2, a3[2].m128i_i64[0], a3, 0, &v18), v10 == -1073741772) )
  {
    if ( (a3[2].m128i_i8[8] & 2) == 0 )
      goto LABEL_16;
    v10 = LuafvReadAndCacheSecurityDescriptor(a2, *(_QWORD *)(a3[2].m128i_i64[0] + 32), a3, 1, &v18);
    v11 = (*(_BYTE *)(v6 + 32) & 1) != 0 ? 4 : 2;
  }
  else
  {
    v11 = 2;
  }
  if ( v10 < 0 )
  {
    if ( (unsigned int)(v10 + 1073741773) > 1 && v10 != -1073741766 )
    {
      if ( v10 != -1073741790 )
        return (unsigned int)v10;
      v12 = 0;
      goto LABEL_17;
    }
LABEL_16:
    v12 = 1;
LABEL_17:
    v10 = 0;
LABEL_8:
    *a4 = v12;
    return (unsigned int)v10;
  }
  v12 = 0;
  v13 = LuafvBuildAdminInformation(a1, PrimaryTokenInformation);
  v14 = (__int64 *)v18;
  v10 = v13;
  if ( v13 >= 0 )
  {
    v15 = *(void **)(v18 + 16);
    GenericMapping = IoGetFileObjectGenericMapping();
    v12 = SeAccessCheckFromState(
            v15,
            PrimaryTokenInformation[0],
            0,
            v11,
            0,
            0,
            GenericMapping,
            1,
            &GrantedAccess,
            &AccessStatus) != 0;
    LuafvFreePool((__int64)PrimaryTokenInformation[0]);
  }
  LuafvDereferenceCachedSecurityDescriptor(v14);
  if ( v10 >= 0 )
    goto LABEL_8;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001f5d0  mov     rax, rsp
0x14001f5d3  mov     [rax+10h], rbx
0x14001f5d7  push    rbp
0x14001f5d8  push    rsi
0x14001f5d9  push    rdi
0x14001f5da  push    r12
0x14001f5dc  push    r13
0x14001f5de  push    r14
0x14001f5e0  push    r15
0x14001f5e2  sub     rsp, 60h
0x14001f5e6  test    byte ptr [r8+28h], 1
0x14001f5eb  mov     r12, r9
0x14001f5ee  mov     r13, [rcx+10h]
0x14001f5f2  mov     rbx, r8
0x14001f5f5  mov     r15, rdx
0x14001f5f8  mov     qword ptr [rax-40h], 0
0x14001f600  mov     rbp, rcx
0x14001f603  mov     dword ptr [rax+18h], 0
0x14001f60a  mov     dword ptr [rax+8], 0
0x14001f611  mov     qword ptr [rax-48h], 0
0x14001f619  jz      loc_14001F704
0x14001f61f  mov     rdx, [r8+20h]
0x14001f623  lea     rax, [rax-48h]
0x14001f627  xor     r9d, r9d
0x14001f62a  mov     qword ptr [rsp+98h+PreviouslyGrantedAccess], rax; __int64
0x14001f62f  mov     rcx, r15; Instance
0x14001f632  call    LuafvReadAndCacheSecurityDescriptor
0x14001f637  mov     edi, eax
0x14001f639  cmp     eax, 0C0000034h
0x14001f63e  jz      loc_14001F704
0x14001f644  mov     esi, 2
0x14001f649  test    edi, edi
0x14001f64b  js      loc_14001F745
0x14001f651  lea     rdx, [rsp+98h+PrimaryTokenInformation]
0x14001f656  mov     rcx, rbp
0x14001f659  xor     bl, bl
0x14001f65b  call    LuafvBuildAdminInformation
0x14001f660  mov     rbp, [rsp+98h+var_48]
0x14001f665  mov     edi, eax
0x14001f667  test    eax, eax
0x14001f669  js      short loc_14001F6D9
0x14001f66b  mov     rbx, [rbp+10h]
0x14001f66f  call    cs:__imp_IoGetFileObjectGenericMapping
0x14001f676  nop     dword ptr [rax+rax+00h]
0x14001f67b  mov     rdx, [rsp+98h+PrimaryTokenInformation]; PrimaryTokenInformation
0x14001f680  lea     rcx, [rsp+98h+arg_0]
0x14001f688  mov     [rsp+98h+AccessStatus], rcx; AccessStatus
0x14001f68d  mov     r9d, esi; DesiredAccess
0x14001f690  lea     rcx, [rsp+98h+arg_10]
0x14001f698  xor     r8d, r8d; ClientTokenInformation
0x14001f69b  mov     [rsp+98h+GrantedAccess], rcx; GrantedAccess
0x14001f6a0  mov     rcx, rbx; SecurityDescriptor
0x14001f6a3  mov     [rsp+98h+AccessMode], 1; AccessMode
0x14001f6a8  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14001f6ad  mov     [rsp+98h+Privileges], 0; Privileges
0x14001f6b6  mov     [rsp+98h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14001f6be  call    cs:__imp_SeAccessCheckFromState
0x14001f6c5  nop     dword ptr [rax+rax+00h]
0x14001f6ca  mov     rcx, [rsp+98h+PrimaryTokenInformation]
0x14001f6cf  test    al, al
0x14001f6d1  setnz   bl
0x14001f6d4  call    LuafvFreePool
0x14001f6d9  mov     rcx, rbp
0x14001f6dc  call    LuafvDereferenceCachedSecurityDescriptor
0x14001f6e1  test    edi, edi
0x14001f6e3  js      short loc_14001F6E9
0x14001f6e5  mov     [r12], bl
0x14001f6e9  mov     rbx, [rsp+98h+arg_8]
0x14001f6f1  mov     eax, edi
0x14001f6f3  add     rsp, 60h
0x14001f6f7  pop     r15
0x14001f6f9  pop     r14
0x14001f6fb  pop     r13
0x14001f6fd  pop     r12
0x14001f6ff  pop     rdi
0x14001f700  pop     rsi
0x14001f701  pop     rbp
0x14001f702  retn
0x14001f704  mov     esi, 2
0x14001f709  test    [rbx+28h], sil
0x14001f70d  jz      short loc_14001F764
0x14001f70f  mov     rdx, [rbx+20h]
0x14001f713  lea     rax, [rsp+98h+var_48]
0x14001f718  mov     r9b, 1
0x14001f71b  mov     qword ptr [rsp+98h+PreviouslyGrantedAccess], rax; __int64
0x14001f720  mov     r8, rbx
0x14001f723  mov     rcx, r15; Instance
0x14001f726  mov     rdx, [rdx+20h]
0x14001f72a  call    LuafvReadAndCacheSecurityDescriptor
0x14001f72f  mov     cl, [r13+20h]
0x14001f733  mov     edi, eax
0x14001f735  and     cl, 1
0x14001f738  neg     cl
0x14001f73a  sbb     edx, edx
0x14001f73c  and     edx, esi
0x14001f73e  add     esi, edx
0x14001f740  jmp     loc_14001F649
0x14001f745  lea     eax, [rdi+3FFFFFCDh]
0x14001f74b  cmp     eax, 1
0x14001f74e  jbe     short loc_14001F764
0x14001f750  cmp     edi, 0C000003Ah
0x14001f756  jz      short loc_14001F764
0x14001f758  cmp     edi, 0C0000022h
0x14001f75e  jnz     short loc_14001F6E9
0x14001f760  xor     bl, bl
0x14001f762  jmp     short loc_14001F766
0x14001f764  mov     bl, 1
0x14001f766  xor     edi, edi
0x14001f768  jmp     loc_14001F6E5
```
