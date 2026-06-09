# FCpAccessCheck

- ea: `0x1400111f0`
- end: `0x140011340`
- name: `FCpAccessCheck`
- size: `336`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f9a0`

## callees

- `0x1400111f0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140011284`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140011284`
- `ntoskrnl!SeAccessCheck` at `0x1400112ca`
- `ntoskrnl!SeAccessCheck` at `0x1400112ca`

## pseudocode

```c
__int64 __fastcall FCpAccessCheck(__int64 a1, void *a2, DWORD *a3)
{
  __int64 v3; // r10
  KPROCESSOR_MODE v4; // r11
  unsigned int v7; // edi
  __int64 v8; // r14
  unsigned int v9; // ecx
  ACCESS_MASK v10; // ebx
  KPROCESSOR_MODE AccessMode; // bp
  __int64 v12; // rdi
  ACCESS_MASK PreviouslyGrantedAccess; // esi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  __int64 result; // rax
  int AccessStatus; // [rsp+90h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+A8h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  v4 = *(_BYTE *)(a1 + 80);
  AccessStatus = 0;
  GrantedAccess = 0;
  v7 = *(_DWORD *)(v3 + 32);
  v8 = *(_QWORD *)(v3 + 24);
  v9 = HIBYTE(v7);
  v10 = *(_DWORD *)(v8 + 16) | 0x10000;
  if ( (v7 & 0x1000) == 0 )
    v10 = *(_DWORD *)(v8 + 16);
  if ( v9 - 4 <= 1 )
  {
    v10 |= 0x112u;
  }
  else if ( v9 - 2 <= 1 )
  {
    v10 |= 2 * (v7 & 1) + 2;
  }
  else if ( !v9 )
  {
    v10 |= 0x10000u;
  }
  AccessMode = v4;
  if ( (*(_BYTE *)v3 & 1) != 0 )
    AccessMode = 1;
  if ( (gFCFlags & 0x10) != 0 )
    return 0;
  v12 = *(_QWORD *)(v8 + 8);
  PreviouslyGrantedAccess = *(_DWORD *)(v12 + 20);
  GenericMapping = IoGetFileObjectGenericMapping();
  if ( SeAccessCheck(
         a2,
         (PSECURITY_SUBJECT_CONTEXT)(v12 + 32),
         0,
         v10,
         PreviouslyGrantedAccess,
         0,
         GenericMapping,
         AccessMode,
         &GrantedAccess,
         &AccessStatus) )
  {
    *a3 = GrantedAccess;
    return (unsigned int)AccessStatus;
  }
  else
  {
    result = (unsigned int)AccessStatus;
    if ( AccessStatus >= 0 )
      return 3221225506LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400111f0  mov     rax, rsp
0x1400111f3  mov     [rax+10h], rbx
0x1400111f7  push    rbp
0x1400111f8  push    rsi
0x1400111f9  push    rdi
0x1400111fa  push    r12
0x1400111fc  push    r13
0x1400111fe  push    r14
0x140011200  push    r15
0x140011202  sub     rsp, 50h
0x140011206  mov     r10, [rcx+10h]
0x14001120a  xor     r13d, r13d
0x14001120d  movzx   r11d, byte ptr [rcx+50h]
0x140011212  mov     r15, r8
0x140011215  mov     [rax+8], r13d
0x140011219  mov     r12, rdx
0x14001121c  mov     [rax+20h], r13d
0x140011220  mov     edi, [r10+20h]
0x140011224  mov     ecx, edi
0x140011226  mov     r14, [r10+18h]
0x14001122a  shr     ecx, 18h
0x14001122d  mov     r9d, [r14+10h]
0x140011231  mov     ebx, r9d
0x140011234  bts     ebx, 10h
0x140011238  lea     eax, [rcx-4]
0x14001123b  bt      edi, 0Ch
0x14001123f  cmovnb  ebx, r9d
0x140011243  cmp     eax, 1
0x140011246  jbe     loc_140011304
0x14001124c  lea     eax, [rcx-2]
0x14001124f  cmp     eax, 1
0x140011252  jbe     loc_140011314
0x140011258  test    ecx, ecx
0x14001125a  jz      loc_140011325
0x140011260  test    byte ptr [r10], 1
0x140011264  mov     eax, 1
0x140011269  mov     ebp, r11d
0x14001126c  cmovnz  ebp, eax
0x14001126f  mov     eax, cs:gFCFlags
0x140011275  test    al, 10h
0x140011277  jnz     loc_14001130F
0x14001127d  mov     rdi, [r14+8]
0x140011281  mov     esi, [rdi+14h]
0x140011284  call    cs:__imp_IoGetFileObjectGenericMapping
0x14001128b  nop     dword ptr [rax+rax+00h]
0x140011290  lea     rcx, [rsp+88h+arg_0]
0x140011298  mov     r9d, ebx; DesiredAccess
0x14001129b  mov     [rsp+88h+AccessStatus], rcx; AccessStatus
0x1400112a0  lea     rdx, [rdi+20h]; SubjectSecurityContext
0x1400112a4  lea     rcx, [rsp+88h+arg_18]
0x1400112ac  xor     r8d, r8d; SubjectContextLocked
0x1400112af  mov     [rsp+88h+GrantedAccess], rcx; GrantedAccess
0x1400112b4  mov     rcx, r12; SecurityDescriptor
0x1400112b7  mov     [rsp+88h+AccessMode], bpl; AccessMode
0x1400112bc  mov     [rsp+88h+GenericMapping], rax; GenericMapping
0x1400112c1  mov     [rsp+88h+Privileges], r13; Privileges
0x1400112c6  mov     [rsp+88h+PreviouslyGrantedAccess], esi; PreviouslyGrantedAccess
0x1400112ca  call    cs:__imp_SeAccessCheck
0x1400112d1  nop     dword ptr [rax+rax+00h]
0x1400112d6  test    al, al
0x1400112d8  jz      short loc_14001132E
0x1400112da  mov     eax, [rsp+88h+arg_18]
0x1400112e1  mov     [r15], eax
0x1400112e4  mov     eax, [rsp+88h+arg_0]
0x1400112eb  mov     rbx, [rsp+88h+arg_8]
0x1400112f3  add     rsp, 50h
0x1400112f7  pop     r15
0x1400112f9  pop     r14
0x1400112fb  pop     r13
0x1400112fd  pop     r12
0x1400112ff  pop     rdi
0x140011300  pop     rsi
0x140011301  pop     rbp
0x140011302  retn
0x140011304  or      ebx, 112h
0x14001130a  jmp     loc_140011260
0x14001130f  mov     eax, r13d
0x140011312  jmp     short loc_1400112EB
0x140011314  and     edi, 1
0x140011317  lea     eax, ds:2[rdi*2]
0x14001131e  or      ebx, eax
0x140011320  jmp     loc_140011260
0x140011325  bts     ebx, 10h
0x140011329  jmp     loc_140011260
0x14001132e  mov     eax, [rsp+88h+arg_0]
0x140011335  test    eax, eax
0x140011337  js      short loc_1400112EB
0x140011339  mov     eax, 0C0000022h
0x14001133e  jmp     short loc_1400112EB
```
