# LuafvCheckAdminAccess

- ea: `0x14001f620`
- end: `0x14001f7bd`
- name: `LuafvCheckAdminAccess`
- size: `413`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018f70`
- `0x14001fc90`
- `0x140025350`

## callees

- `0x14001dd00`
- `0x14001dd90`
- `0x14001df20`
- `0x14001f620`
- `0x14001f7c4`

## import_xrefs

- `ntoskrnl!SeAccessCheckFromState` at `0x14001f70e`
- `ntoskrnl!SeAccessCheckFromState` at `0x14001f70e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001f6bf`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001f6bf`

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
  __int64 v14; // rbp
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
  v14 = v18;
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
    LuafvFreePool(PrimaryTokenInformation[0]);
  }
  LuafvDereferenceCachedSecurityDescriptor(v14);
  if ( v10 >= 0 )
    goto LABEL_8;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001f620  mov     rax, rsp
0x14001f623  mov     [rax+10h], rbx
0x14001f627  push    rbp
0x14001f628  push    rsi
0x14001f629  push    rdi
0x14001f62a  push    r12
0x14001f62c  push    r13
0x14001f62e  push    r14
0x14001f630  push    r15
0x14001f632  sub     rsp, 60h
0x14001f636  test    byte ptr [r8+28h], 1
0x14001f63b  mov     r12, r9
0x14001f63e  mov     r13, [rcx+10h]
0x14001f642  mov     rbx, r8
0x14001f645  mov     r15, rdx
0x14001f648  mov     qword ptr [rax-40h], 0
0x14001f650  mov     rbp, rcx
0x14001f653  mov     dword ptr [rax+18h], 0
0x14001f65a  mov     dword ptr [rax+8], 0
0x14001f661  mov     qword ptr [rax-48h], 0
0x14001f669  jz      loc_14001F754
0x14001f66f  mov     rdx, [r8+20h]
0x14001f673  lea     rax, [rax-48h]
0x14001f677  xor     r9d, r9d
0x14001f67a  mov     qword ptr [rsp+98h+PreviouslyGrantedAccess], rax; __int64
0x14001f67f  mov     rcx, r15; Instance
0x14001f682  call    LuafvReadAndCacheSecurityDescriptor
0x14001f687  mov     edi, eax
0x14001f689  cmp     eax, 0C0000034h
0x14001f68e  jz      loc_14001F754
0x14001f694  mov     esi, 2
0x14001f699  test    edi, edi
0x14001f69b  js      loc_14001F795
0x14001f6a1  lea     rdx, [rsp+98h+PrimaryTokenInformation]
0x14001f6a6  mov     rcx, rbp
0x14001f6a9  xor     bl, bl
0x14001f6ab  call    LuafvBuildAdminInformation
0x14001f6b0  mov     rbp, [rsp+98h+var_48]
0x14001f6b5  mov     edi, eax
0x14001f6b7  test    eax, eax
0x14001f6b9  js      short loc_14001F729
0x14001f6bb  mov     rbx, [rbp+10h]
0x14001f6bf  call    cs:__imp_IoGetFileObjectGenericMapping
0x14001f6c6  nop     dword ptr [rax+rax+00h]
0x14001f6cb  mov     rdx, [rsp+98h+PrimaryTokenInformation]; PrimaryTokenInformation
0x14001f6d0  lea     rcx, [rsp+98h+arg_0]
0x14001f6d8  mov     [rsp+98h+AccessStatus], rcx; AccessStatus
0x14001f6dd  mov     r9d, esi; DesiredAccess
0x14001f6e0  lea     rcx, [rsp+98h+arg_10]
0x14001f6e8  xor     r8d, r8d; ClientTokenInformation
0x14001f6eb  mov     [rsp+98h+GrantedAccess], rcx; GrantedAccess
0x14001f6f0  mov     rcx, rbx; SecurityDescriptor
0x14001f6f3  mov     [rsp+98h+AccessMode], 1; AccessMode
0x14001f6f8  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x14001f6fd  mov     [rsp+98h+Privileges], 0; Privileges
0x14001f706  mov     [rsp+98h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14001f70e  call    cs:__imp_SeAccessCheckFromState
0x14001f715  nop     dword ptr [rax+rax+00h]
0x14001f71a  mov     rcx, [rsp+98h+PrimaryTokenInformation]
0x14001f71f  test    al, al
0x14001f721  setnz   bl
0x14001f724  call    LuafvFreePool
0x14001f729  mov     rcx, rbp
0x14001f72c  call    LuafvDereferenceCachedSecurityDescriptor
0x14001f731  test    edi, edi
0x14001f733  js      short loc_14001F739
0x14001f735  mov     [r12], bl
0x14001f739  mov     rbx, [rsp+98h+arg_8]
0x14001f741  mov     eax, edi
0x14001f743  add     rsp, 60h
0x14001f747  pop     r15
0x14001f749  pop     r14
0x14001f74b  pop     r13
0x14001f74d  pop     r12
0x14001f74f  pop     rdi
0x14001f750  pop     rsi
0x14001f751  pop     rbp
0x14001f752  retn
0x14001f754  mov     esi, 2
0x14001f759  test    [rbx+28h], sil
0x14001f75d  jz      short loc_14001F7B4
0x14001f75f  mov     rdx, [rbx+20h]
0x14001f763  lea     rax, [rsp+98h+var_48]
0x14001f768  mov     r9b, 1
0x14001f76b  mov     qword ptr [rsp+98h+PreviouslyGrantedAccess], rax; __int64
0x14001f770  mov     r8, rbx
0x14001f773  mov     rcx, r15; Instance
0x14001f776  mov     rdx, [rdx+20h]
0x14001f77a  call    LuafvReadAndCacheSecurityDescriptor
0x14001f77f  mov     cl, [r13+20h]
0x14001f783  mov     edi, eax
0x14001f785  and     cl, 1
0x14001f788  neg     cl
0x14001f78a  sbb     edx, edx
0x14001f78c  and     edx, esi
0x14001f78e  add     esi, edx
0x14001f790  jmp     loc_14001F699
0x14001f795  lea     eax, [rdi+3FFFFFCDh]
0x14001f79b  cmp     eax, 1
0x14001f79e  jbe     short loc_14001F7B4
0x14001f7a0  cmp     edi, 0C000003Ah
0x14001f7a6  jz      short loc_14001F7B4
0x14001f7a8  cmp     edi, 0C0000022h
0x14001f7ae  jnz     short loc_14001F739
0x14001f7b0  xor     bl, bl
0x14001f7b2  jmp     short loc_14001F7B6
0x14001f7b4  mov     bl, 1
0x14001f7b6  xor     edi, edi
0x14001f7b8  jmp     loc_14001F735
```
