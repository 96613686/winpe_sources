# CipGetRegistryValue2

- ea: `0x1800714cc`
- end: `0x1800717fe`
- name: `CipGetRegistryValue2`
- size: `818`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180066330`
- `0x180071114`
- `0x1800dc034`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x1800714cc`
- `0x180071804`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180071741`
- `ntoskrnl!ExAllocatePool2` at `0x180071741`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800717c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800717c5`
- `ntoskrnl!ZwClose` at `0x180071669`
- `ntoskrnl!ZwClose` at `0x1800717ac`
- `ntoskrnl!ZwClose` at `0x180071669`
- `ntoskrnl!ZwClose` at `0x1800717ac`
- `ntoskrnl!ZwOpenKey` at `0x1800715c5`
- `ntoskrnl!ZwOpenKey` at `0x1800716ee`
- `ntoskrnl!ZwOpenKey` at `0x1800715c5`
- `ntoskrnl!ZwOpenKey` at `0x1800716ee`

## pseudocode

```c
__int64 __fastcall CipGetRegistryValue2(__int64 a1, _WORD *a2, __int64 a3, int a4, _QWORD *a5, _DWORD *a6)
{
  void *Pool2; // rdi
  __int64 v9; // r12
  __int64 v10; // rcx
  _WORD *v11; // rax
  NTSTATUS RegistryValueInternal; // ebx
  unsigned __int16 *v13; // rax
  int v14; // ecx
  int v15; // edx
  _WORD *v16; // rax
  __int16 v17; // r12
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v23; // [rsp+80h] [rbp-80h]
  _DWORD *v24; // [rsp+88h] [rbp-78h]
  _BYTE v25[522]; // [rsp+90h] [rbp-70h] BYREF

  v23 = a5;
  v24 = a6;
  LODWORD(v19) = 0;
  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  Pool2 = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  memset(v25, 0, sizeof(v25));
  v9 = 0x7FFF;
  v21 = 0;
  if ( a2 )
  {
    v10 = 0x7FFF;
    v11 = a2;
    while ( *v11 )
    {
      ++v11;
      if ( !--v10 )
        goto LABEL_7;
    }
    *((_QWORD *)&v21 + 1) = a2;
    LOWORD(v21) = -2 - 2 * v10;
    WORD1(v21) = -2 * v10;
  }
LABEL_7:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v21;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  RegistryValueInternal = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( RegistryValueInternal >= 0 )
  {
    if ( !a4 )
    {
      RegistryValueInternal = -1073741582;
      goto LABEL_31;
    }
    if ( (unsigned int)(a4 - 1) >= 2 )
    {
      RegistryValueInternal = -1073741822;
      goto LABEL_31;
    }
    RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, 0, (__int64)&v19);
    if ( RegistryValueInternal == -1073741772 )
    {
      if ( !a2 )
        goto LABEL_31;
      v13 = (unsigned __int16 *)*((_QWORD *)&v21 + 1);
      do
      {
        v14 = *(unsigned __int16 *)((char *)a2 + (_QWORD)v13 - *((_QWORD *)&v21 + 1));
        v15 = *v13 - v14;
        if ( v15 )
          break;
        ++v13;
      }
      while ( v14 );
      if ( !v15 )
        goto LABEL_31;
      ZwClose(KeyHandle);
      KeyHandle = 0;
      v16 = a2;
      v21 = 0;
      while ( *v16 )
      {
        ++v16;
        if ( !--v9 )
          goto LABEL_22;
      }
      v17 = 2 * v9;
      *((_QWORD *)&v21 + 1) = a2;
      LOWORD(v21) = -2 - v17;
      WORD1(v21) = -v17;
LABEL_22:
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v21;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      RegistryValueInternal = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      if ( RegistryValueInternal < 0 )
        goto LABEL_31;
      RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, 0, (__int64)&v19);
    }
    if ( RegistryValueInternal == -2147483643 )
    {
      Pool2 = (void *)ExAllocatePool2(258, (unsigned int)v19, 1668499779);
      if ( !Pool2 )
      {
        RegistryValueInternal = -1073741801;
        goto LABEL_31;
      }
      RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, (__int64)Pool2, (__int64)&v19);
    }
    if ( RegistryValueInternal >= 0 )
    {
      *v23 = Pool2;
      Pool2 = 0;
      *v24 = v19;
    }
  }
LABEL_31:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x63734943u);
  return (unsigned int)RegistryValueInternal;
}

```

## disassembly

```asm
0x1800714cc  mov     [rsp-8+arg_0], rbx
0x1800714d1  push    rbp
0x1800714d2  push    rsi
0x1800714d3  push    rdi
0x1800714d4  push    r12
0x1800714d6  push    r13
0x1800714d8  push    r14
0x1800714da  push    r15
0x1800714dc  lea     rbp, [rsp-1B0h]
0x1800714e4  sub     rsp, 2B0h
0x1800714eb  mov     rax, cs:__security_cookie
0x1800714f2  xor     rax, rsp
0x1800714f5  mov     [rbp+1E0h+var_40], rax
0x1800714fc  mov     rax, [rbp+1E0h+arg_20]
0x180071503  lea     rcx, [rbp+1E0h+var_250]; void *
0x180071507  xor     ebx, ebx
0x180071509  mov     [rbp+1E0h+var_260], rax
0x18007150d  mov     rax, [rbp+1E0h+arg_28]
0x180071514  mov     r13, r8
0x180071517  mov     r14, rdx
0x18007151a  mov     [rbp+1E0h+var_258], rax
0x18007151e  xor     edx, edx; Val
0x180071520  mov     dword ptr [rsp+2E0h+var_2B0], ebx
0x180071524  mov     r8d, 20Ah; Size
0x18007152a  mov     [rsp+2E0h+KeyHandle], rbx
0x18007152f  mov     esi, r9d
0x180071532  mov     dword ptr [rsp+2E0h+ObjectAttributes+4], ebx
0x180071536  mov     edi, ebx
0x180071538  mov     dword ptr [rsp+2E0h+ObjectAttributes+1Ch], ebx
0x18007153c  call    memset
0x180071541  lea     edx, [rbx+2]
0x180071544  xorps   xmm0, xmm0
0x180071547  mov     r12d, 7FFFh
0x18007154d  mov     r15d, 0FFFEh
0x180071553  movups  [rsp+2E0h+var_2A0], xmm0
0x180071558  test    r14, r14
0x18007155b  jz      short loc_18007158E
0x18007155d  mov     ecx, r12d
0x180071560  mov     rax, r14
0x180071563  cmp     [rax], bx
0x180071566  jz      short loc_180071573
0x180071568  add     rax, rdx
0x18007156b  sub     rcx, 1
0x18007156f  jnz     short loc_180071563
0x180071571  jmp     short loc_18007158E
0x180071573  add     cx, cx
0x180071576  mov     qword ptr [rsp+2E0h+var_2A0+8], r14
0x18007157b  mov     eax, r15d
0x18007157e  sub     ax, cx
0x180071581  mov     word ptr [rsp+2E0h+var_2A0], ax
0x180071586  add     ax, dx
0x180071589  mov     word ptr [rsp+2E0h+var_2A0+2], ax
0x18007158e  lea     rax, [rsp+2E0h+var_2A0]
0x180071593  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18007159b  xorps   xmm0, xmm0
0x18007159e  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x1800715a3  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x1800715a8  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rbx
0x1800715ad  mov     edx, 20019h; DesiredAccess
0x1800715b2  mov     [rsp+2E0h+ObjectAttributes.Attributes], 240h
0x1800715ba  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800715bf  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800715c5  call    cs:__imp_ZwOpenKey
0x1800715cc  nop     dword ptr [rax+rax+00h]
0x1800715d1  xor     ecx, ecx
0x1800715d3  mov     ebx, eax
0x1800715d5  test    eax, eax
0x1800715d7  js      loc_1800717A2
0x1800715dd  test    esi, esi
0x1800715df  jz      loc_18007179D
0x1800715e5  sub     esi, 1
0x1800715e8  jz      short loc_180071600
0x1800715ea  cmp     esi, 1
0x1800715ed  jz      short loc_1800715F9
0x1800715ef  mov     ebx, 0C0000002h
0x1800715f4  jmp     loc_1800717A2
0x1800715f9  mov     esi, 1
0x1800715fe  jmp     short loc_180071605
0x180071600  mov     esi, 3
0x180071605  lea     rax, [rsp+2E0h+var_2B0]
0x18007160a  xor     r9d, r9d
0x18007160d  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180071612  mov     r8d, esi
0x180071615  mov     [rsp+2E0h+var_2C0], rcx; __int64
0x18007161a  mov     rdx, r13
0x18007161d  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180071622  call    CipGetRegistryValueInternal
0x180071627  mov     ebx, eax
0x180071629  cmp     eax, 0C0000034h
0x18007162e  jnz     loc_18007172A
0x180071634  test    r14, r14
0x180071637  jz      loc_1800717A2
0x18007163d  mov     rax, qword ptr [rsp+2E0h+var_2A0+8]
0x180071642  mov     r8, r14
0x180071645  sub     r8, rax
0x180071648  movzx   edx, word ptr [rax]
0x18007164b  movzx   ecx, word ptr [rax+r8]
0x180071650  sub     edx, ecx
0x180071652  jnz     short loc_18007165C
0x180071654  add     rax, 2
0x180071658  test    ecx, ecx
0x18007165a  jnz     short loc_180071648
0x18007165c  test    edx, edx
0x18007165e  jz      loc_1800717A2
0x180071664  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x180071669  call    cs:__imp_ZwClose
0x180071670  nop     dword ptr [rax+rax+00h]
0x180071675  xor     ecx, ecx
0x180071677  xorps   xmm0, xmm0
0x18007167a  mov     [rsp+2E0h+KeyHandle], rcx
0x18007167f  mov     rax, r14
0x180071682  movups  [rsp+2E0h+var_2A0], xmm0
0x180071687  lea     edx, [rcx+2]
0x18007168a  cmp     [rax], cx
0x18007168d  jz      short loc_18007169A
0x18007168f  add     rax, rdx
0x180071692  sub     r12, 1
0x180071696  jnz     short loc_18007168A
0x180071698  jmp     short loc_1800716B7
0x18007169a  add     r12w, r12w
0x18007169e  mov     qword ptr [rsp+2E0h+var_2A0+8], r14
0x1800716a3  sub     r15w, r12w
0x1800716a7  mov     word ptr [rsp+2E0h+var_2A0], r15w
0x1800716ad  add     r15w, dx
0x1800716b1  mov     word ptr [rsp+2E0h+var_2A0+2], r15w
0x1800716b7  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rcx
0x1800716bc  lea     rax, [rsp+2E0h+var_2A0]
0x1800716c1  xorps   xmm0, xmm0
0x1800716c4  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x1800716c9  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800716ce  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x1800716d6  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x1800716db  mov     [rsp+2E0h+ObjectAttributes.Attributes], 240h
0x1800716e3  mov     edx, 20019h; DesiredAccess
0x1800716e8  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800716ee  call    cs:__imp_ZwOpenKey
0x1800716f5  nop     dword ptr [rax+rax+00h]
0x1800716fa  xor     ecx, ecx
0x1800716fc  mov     ebx, eax
0x1800716fe  test    eax, eax
0x180071700  js      loc_1800717A2
0x180071706  lea     rax, [rsp+2E0h+var_2B0]
0x18007170b  xor     r9d, r9d
0x18007170e  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180071713  mov     r8d, esi
0x180071716  mov     [rsp+2E0h+var_2C0], rcx; __int64
0x18007171b  mov     rdx, r13
0x18007171e  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180071723  call    CipGetRegistryValueInternal
0x180071728  mov     ebx, eax
0x18007172a  cmp     ebx, 80000005h
0x180071730  jnz     short loc_180071782
0x180071732  mov     edx, dword ptr [rsp+2E0h+var_2B0]
0x180071736  mov     ecx, 102h
0x18007173b  mov     r8d, 63734943h
0x180071741  call    cs:__imp_ExAllocatePool2
0x180071748  nop     dword ptr [rax+rax+00h]
0x18007174d  mov     rdi, rax
0x180071750  test    rax, rax
0x180071753  jnz     short loc_18007175C
0x180071755  mov     ebx, 0C0000017h
0x18007175a  jmp     short loc_1800717A2
0x18007175c  mov     r9d, dword ptr [rsp+2E0h+var_2B0]
0x180071761  lea     rax, [rsp+2E0h+var_2B0]
0x180071766  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18007176b  mov     r8d, esi
0x18007176e  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180071773  mov     rdx, r13
0x180071776  mov     [rsp+2E0h+var_2C0], rdi; __int64
0x18007177b  call    CipGetRegistryValueInternal
0x180071780  mov     ebx, eax
0x180071782  xor     ecx, ecx
0x180071784  test    ebx, ebx
0x180071786  js      short loc_1800717A2
0x180071788  mov     rax, [rbp+1E0h+var_260]
0x18007178c  mov     [rax], rdi
0x18007178f  mov     edi, ecx
0x180071791  mov     rcx, [rbp+1E0h+var_258]
0x180071795  mov     eax, dword ptr [rsp+2E0h+var_2B0]
0x180071799  mov     [rcx], eax
0x18007179b  jmp     short loc_1800717A2
0x18007179d  mov     ebx, 0C00000F2h
0x1800717a2  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x1800717a7  test    rcx, rcx
0x1800717aa  jz      short loc_1800717B8
0x1800717ac  call    cs:__imp_ZwClose
0x1800717b3  nop     dword ptr [rax+rax+00h]
0x1800717b8  test    rdi, rdi
0x1800717bb  jz      short loc_1800717D1
0x1800717bd  mov     edx, 63734943h; Tag
0x1800717c2  mov     rcx, rdi; P
0x1800717c5  call    cs:__imp_ExFreePoolWithTag
0x1800717cc  nop     dword ptr [rax+rax+00h]
0x1800717d1  mov     eax, ebx
0x1800717d3  mov     rcx, [rbp+1E0h+var_40]
0x1800717da  xor     rcx, rsp; StackCookie
0x1800717dd  call    __security_check_cookie
0x1800717e2  mov     rbx, [rsp+2E0h+arg_0]
0x1800717ea  add     rsp, 2B0h
0x1800717f1  pop     r15
0x1800717f3  pop     r14
0x1800717f5  pop     r13
0x1800717f7  pop     r12
0x1800717f9  pop     rdi
0x1800717fa  pop     rsi
0x1800717fb  pop     rbp
0x1800717fc  retn
```
