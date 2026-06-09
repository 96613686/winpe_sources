# RxCheckVNetRootCredentials

- ea: `0x140069680`
- end: `0x1400697f2`
- name: `RxCheckVNetRootCredentials`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140078fe0`

## callees

- `0x140021dc0`
- `0x140025c20`
- `0x140069680`
- `0x140069800`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x14007e7f7`
- `ntoskrnl!SeAccessCheck` at `0x14007e7f7`

## pseudocode

```c
__int64 __fastcall RxCheckVNetRootCredentials(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // al
  bool v6; // bp
  char v7; // r14
  int IsCompatibleSecurityContext; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // esi
  __int64 v13; // rax
  void *v14; // rcx
  unsigned int v16; // eax
  int AccessStatus; // [rsp+50h] [rbp-38h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-34h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-30h] BYREF

  v3 = *(_BYTE *)(a1 + 749);
  v6 = (v3 & 8) != 0 && (v3 & 0x20) == 0;
  if ( (((unsigned __int8)(*(_DWORD *)(a2 + 56) >> 6) ^ (unsigned __int8)(*(_DWORD *)(a1 + 120) >> 11)) & 1) != 0 )
    return 3221225494LL;
  v7 = *(_BYTE *)(a1 + 746) & 1;
  IsCompatibleSecurityContext = RxIsCompatibleSecurityContext((PLUID)(a2 + 72), (int *)(a1 + 760), a3);
  v11 = IsCompatibleSecurityContext;
  if ( IsCompatibleSecurityContext == -1073741419 )
  {
    if ( v7 && !v6 )
      return (unsigned int)-1073741802;
  }
  else if ( IsCompatibleSecurityContext >= 0 )
  {
    v13 = *(_QWORD *)(a2 + 104);
    v11 = 0;
    AccessStatus = -1073741790;
    GrantedAccess = 0;
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    if ( v13 )
    {
      v14 = *(void **)(v13 + 56);
      if ( v14 )
      {
        if ( !SeAccessCheck(
                v14,
                (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(*(_QWORD *)(a1 + 544) + 8LL) + 32LL),
                0,
                1u,
                0,
                0,
                &GenericMapping,
                *(_BYTE *)(a1 + 36),
                &GrantedAccess,
                &AccessStatus) )
          v11 = AccessStatus;
      }
    }
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qdqd(WPP_GLOBAL_Control->AttachedDevice, v9, v10, a1, *(char *)(a1 + 36), a2, v11);
      }
      if ( v11 == -1073741790 && v7 )
      {
        v16 = -1073741790;
        if ( !v6 )
          return (unsigned int)-1073741802;
        return v16;
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140069680  push    rbx
0x140069682  push    rbp
0x140069683  push    rdi
0x140069684  sub     rsp, 70h
0x140069688  mov     rax, cs:__security_cookie
0x14006968f  xor     rax, rsp
0x140069692  mov     [rsp+88h+var_20], rax
0x140069697  movzx   eax, byte ptr [rcx+2EDh]
0x14006969e  mov     rdi, rdx
0x1400696a1  mov     rbx, rcx
0x1400696a4  test    al, 8
0x1400696a6  jnz     loc_1400697C6
0x1400696ac  xor     bpl, bpl
0x1400696af  mov     ecx, [rcx+78h]
0x1400696b2  mov     eax, [rdx+38h]
0x1400696b5  shr     ecx, 0Bh
0x1400696b8  shr     eax, 6
0x1400696bb  xor     cl, al
0x1400696bd  mov     [rsp+88h+arg_10], rsi
0x1400696c5  test    cl, 1
0x1400696c8  jnz     short loc_140069727
0x1400696ca  mov     [rsp+88h+arg_18], r14
0x1400696d2  lea     rdx, [rbx+2F8h]
0x1400696d9  movzx   r14d, byte ptr [rbx+2EAh]
0x1400696e1  lea     rcx, [rdi+48h]; LogonId
0x1400696e5  and     r14b, 1
0x1400696e9  call    RxIsCompatibleSecurityContext
0x1400696ee  mov     esi, eax
0x1400696f0  cmp     eax, 0C0000195h
0x1400696f5  jz      loc_1400697D6
0x1400696fb  test    eax, eax
0x1400696fd  jns     short loc_14006972E
0x1400696ff  mov     r14, [rsp+88h+arg_18]
0x140069707  mov     eax, esi
0x140069709  mov     rsi, [rsp+88h+arg_10]
0x140069711  mov     rcx, [rsp+88h+var_20]
0x140069716  xor     rcx, rsp; StackCookie
0x140069719  call    __security_check_cookie
0x14006971e  add     rsp, 70h
0x140069722  pop     rdi
0x140069723  pop     rbp
0x140069724  pop     rbx
0x140069725  retn
0x140069727  mov     eax, 0C0000016h
0x14006972c  jmp     short loc_140069709
0x14006972e  mov     rax, [rdi+68h]
0x140069732  xor     esi, esi
0x140069734  mov     [rsp+88h+var_38], 0C0000022h
0x14006973c  mov     [rsp+88h+var_34], esi
0x140069740  mov     [rsp+88h+var_30.GenericRead], 120089h
0x140069748  mov     [rsp+88h+var_30.GenericWrite], 120116h
0x140069750  mov     [rsp+88h+var_30.GenericExecute], 1200A0h
0x140069758  mov     [rsp+88h+var_30.GenericAll], 1F01FFh
0x140069760  test    rax, rax
0x140069763  jnz     short loc_1400697B8
0x140069765  test    esi, esi
0x140069767  jns     short loc_1400696FF
0x140069769  mov     rcx, cs:WPP_GLOBAL_Control
0x140069770  lea     rax, WPP_GLOBAL_Control
0x140069777  cmp     rcx, rax
0x14006977a  jz      loc_14007E814
0x140069780  mov     eax, [rcx+2Ch]
0x140069783  test    al, 1
0x140069785  jz      loc_14007E814
0x14006978b  cmp     byte ptr [rcx+29h], 1
0x14006978f  jb      loc_14007E814
0x140069795  movsx   eax, byte ptr [rbx+24h]
0x140069799  mov     r9, rbx
0x14006979c  mov     rcx, [rcx+18h]
0x1400697a0  mov     dword ptr [rsp+88h+GenericMapping], esi
0x1400697a4  mov     [rsp+88h+Privileges], rdi
0x1400697a9  mov     [rsp+88h+PreviouslyGrantedAccess], eax
0x1400697ad  call    WPP_SF_qdqd
0x1400697b2  nop
0x1400697b3  jmp     loc_14007E814
0x1400697b8  mov     rcx, [rax+38h]; SecurityDescriptor
0x1400697bc  test    rcx, rcx
0x1400697bf  jz      short loc_140069765
0x1400697c1  jmp     loc_14007E7B0
0x1400697c6  test    al, 20h
0x1400697c8  jnz     loc_1400696AC
0x1400697ce  mov     bpl, 1
0x1400697d1  jmp     loc_1400696AF
0x1400697d6  test    r14b, r14b
0x1400697d9  jz      loc_1400696FF
0x1400697df  test    bpl, bpl
0x1400697e2  jnz     loc_1400696FF
0x1400697e8  mov     esi, 0C0000016h
0x1400697ed  jmp     loc_1400696FF
0x14007e7b0  mov     rax, [rbx+220h]
0x14007e7b7  mov     r9d, 1; DesiredAccess
0x14007e7bd  xor     r8d, r8d; SubjectContextLocked
0x14007e7c0  mov     rdx, [rax+8]
0x14007e7c4  lea     rax, [rsp+88h+var_38]
0x14007e7c9  mov     [rsp+88h+AccessStatus], rax; AccessStatus
0x14007e7ce  add     rdx, 20h ; ' '; SubjectSecurityContext
0x14007e7d2  lea     rax, [rsp+88h+var_34]
0x14007e7d7  mov     [rsp+88h+GrantedAccess], rax; GrantedAccess
0x14007e7dc  movzx   eax, byte ptr [rbx+24h]
0x14007e7e0  mov     [rsp+88h+AccessMode], al; AccessMode
0x14007e7e4  lea     rax, [rsp+88h+var_30]
0x14007e7e9  mov     [rsp+88h+GenericMapping], rax; GenericMapping
0x14007e7ee  mov     [rsp+88h+Privileges], rsi; Privileges
0x14007e7f3  mov     [rsp+88h+PreviouslyGrantedAccess], esi; PreviouslyGrantedAccess
0x14007e7f7  call    cs:__imp_SeAccessCheck
0x14007e7fe  nop     dword ptr [rax+rax+00h]
0x14007e803  test    al, al
0x14007e805  jnz     loc_140069765
0x14007e80b  mov     esi, [rsp+88h+var_38]
0x14007e80f  jmp     loc_140069765
0x14007e814  cmp     esi, 0C0000022h
0x14007e81a  jnz     loc_1400696FF
0x14007e820  test    r14b, r14b
0x14007e823  jz      loc_1400696FF
0x14007e829  mov     eax, esi
0x14007e82b  test    bpl, bpl
0x14007e82e  mov     esi, 0C0000016h
0x14007e833  cmovz   eax, esi
0x14007e836  mov     esi, eax
0x14007e838  jmp     loc_1400696FF
```
