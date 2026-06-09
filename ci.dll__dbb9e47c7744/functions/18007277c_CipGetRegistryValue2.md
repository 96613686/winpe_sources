# CipGetRegistryValue2

- ea: `0x18007277c`
- end: `0x180072aae`
- name: `CipGetRegistryValue2`
- size: `818`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180066c24`
- `0x1800723c4`
- `0x1800dd2fc`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18007277c`
- `0x180072ab4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800729f1`
- `ntoskrnl!ExAllocatePool2` at `0x1800729f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072a75`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072a75`
- `ntoskrnl!ZwClose` at `0x180072919`
- `ntoskrnl!ZwClose` at `0x180072a5c`
- `ntoskrnl!ZwClose` at `0x180072919`
- `ntoskrnl!ZwClose` at `0x180072a5c`
- `ntoskrnl!ZwOpenKey` at `0x180072875`
- `ntoskrnl!ZwOpenKey` at `0x18007299e`
- `ntoskrnl!ZwOpenKey` at `0x180072875`
- `ntoskrnl!ZwOpenKey` at `0x18007299e`

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
0x18007277c  mov     [rsp-8+arg_0], rbx
0x180072781  push    rbp
0x180072782  push    rsi
0x180072783  push    rdi
0x180072784  push    r12
0x180072786  push    r13
0x180072788  push    r14
0x18007278a  push    r15
0x18007278c  lea     rbp, [rsp-1B0h]
0x180072794  sub     rsp, 2B0h
0x18007279b  mov     rax, cs:__security_cookie
0x1800727a2  xor     rax, rsp
0x1800727a5  mov     [rbp+1E0h+var_40], rax
0x1800727ac  mov     rax, [rbp+1E0h+arg_20]
0x1800727b3  lea     rcx, [rbp+1E0h+var_250]; void *
0x1800727b7  xor     ebx, ebx
0x1800727b9  mov     [rbp+1E0h+var_260], rax
0x1800727bd  mov     rax, [rbp+1E0h+arg_28]
0x1800727c4  mov     r13, r8
0x1800727c7  mov     r14, rdx
0x1800727ca  mov     [rbp+1E0h+var_258], rax
0x1800727ce  xor     edx, edx; Val
0x1800727d0  mov     dword ptr [rsp+2E0h+var_2B0], ebx
0x1800727d4  mov     r8d, 20Ah; Size
0x1800727da  mov     [rsp+2E0h+KeyHandle], rbx
0x1800727df  mov     esi, r9d
0x1800727e2  mov     dword ptr [rsp+2E0h+ObjectAttributes+4], ebx
0x1800727e6  mov     edi, ebx
0x1800727e8  mov     dword ptr [rsp+2E0h+ObjectAttributes+1Ch], ebx
0x1800727ec  call    memset
0x1800727f1  lea     edx, [rbx+2]
0x1800727f4  xorps   xmm0, xmm0
0x1800727f7  mov     r12d, 7FFFh
0x1800727fd  mov     r15d, 0FFFEh
0x180072803  movups  [rsp+2E0h+var_2A0], xmm0
0x180072808  test    r14, r14
0x18007280b  jz      short loc_18007283E
0x18007280d  mov     ecx, r12d
0x180072810  mov     rax, r14
0x180072813  cmp     [rax], bx
0x180072816  jz      short loc_180072823
0x180072818  add     rax, rdx
0x18007281b  sub     rcx, 1
0x18007281f  jnz     short loc_180072813
0x180072821  jmp     short loc_18007283E
0x180072823  add     cx, cx
0x180072826  mov     qword ptr [rsp+2E0h+var_2A0+8], r14
0x18007282b  mov     eax, r15d
0x18007282e  sub     ax, cx
0x180072831  mov     word ptr [rsp+2E0h+var_2A0], ax
0x180072836  add     ax, dx
0x180072839  mov     word ptr [rsp+2E0h+var_2A0+2], ax
0x18007283e  lea     rax, [rsp+2E0h+var_2A0]
0x180072843  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18007284b  xorps   xmm0, xmm0
0x18007284e  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180072853  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180072858  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rbx
0x18007285d  mov     edx, 20019h; DesiredAccess
0x180072862  mov     [rsp+2E0h+ObjectAttributes.Attributes], 240h
0x18007286a  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18007286f  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180072875  call    cs:__imp_ZwOpenKey
0x18007287c  nop     dword ptr [rax+rax+00h]
0x180072881  xor     ecx, ecx
0x180072883  mov     ebx, eax
0x180072885  test    eax, eax
0x180072887  js      loc_180072A52
0x18007288d  test    esi, esi
0x18007288f  jz      loc_180072A4D
0x180072895  sub     esi, 1
0x180072898  jz      short loc_1800728B0
0x18007289a  cmp     esi, 1
0x18007289d  jz      short loc_1800728A9
0x18007289f  mov     ebx, 0C0000002h
0x1800728a4  jmp     loc_180072A52
0x1800728a9  mov     esi, 1
0x1800728ae  jmp     short loc_1800728B5
0x1800728b0  mov     esi, 3
0x1800728b5  lea     rax, [rsp+2E0h+var_2B0]
0x1800728ba  xor     r9d, r9d
0x1800728bd  mov     [rsp+2E0h+var_2B8], rax; __int64
0x1800728c2  mov     r8d, esi
0x1800728c5  mov     [rsp+2E0h+var_2C0], rcx; __int64
0x1800728ca  mov     rdx, r13
0x1800728cd  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800728d2  call    CipGetRegistryValueInternal
0x1800728d7  mov     ebx, eax
0x1800728d9  cmp     eax, 0C0000034h
0x1800728de  jnz     loc_1800729DA
0x1800728e4  test    r14, r14
0x1800728e7  jz      loc_180072A52
0x1800728ed  mov     rax, qword ptr [rsp+2E0h+var_2A0+8]
0x1800728f2  mov     r8, r14
0x1800728f5  sub     r8, rax
0x1800728f8  movzx   edx, word ptr [rax]
0x1800728fb  movzx   ecx, word ptr [rax+r8]
0x180072900  sub     edx, ecx
0x180072902  jnz     short loc_18007290C
0x180072904  add     rax, 2
0x180072908  test    ecx, ecx
0x18007290a  jnz     short loc_1800728F8
0x18007290c  test    edx, edx
0x18007290e  jz      loc_180072A52
0x180072914  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x180072919  call    cs:__imp_ZwClose
0x180072920  nop     dword ptr [rax+rax+00h]
0x180072925  xor     ecx, ecx
0x180072927  xorps   xmm0, xmm0
0x18007292a  mov     [rsp+2E0h+KeyHandle], rcx
0x18007292f  mov     rax, r14
0x180072932  movups  [rsp+2E0h+var_2A0], xmm0
0x180072937  lea     edx, [rcx+2]
0x18007293a  cmp     [rax], cx
0x18007293d  jz      short loc_18007294A
0x18007293f  add     rax, rdx
0x180072942  sub     r12, 1
0x180072946  jnz     short loc_18007293A
0x180072948  jmp     short loc_180072967
0x18007294a  add     r12w, r12w
0x18007294e  mov     qword ptr [rsp+2E0h+var_2A0+8], r14
0x180072953  sub     r15w, r12w
0x180072957  mov     word ptr [rsp+2E0h+var_2A0], r15w
0x18007295d  add     r15w, dx
0x180072961  mov     word ptr [rsp+2E0h+var_2A0+2], r15w
0x180072967  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rcx
0x18007296c  lea     rax, [rsp+2E0h+var_2A0]
0x180072971  xorps   xmm0, xmm0
0x180072974  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180072979  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18007297e  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180072986  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18007298b  mov     [rsp+2E0h+ObjectAttributes.Attributes], 240h
0x180072993  mov     edx, 20019h; DesiredAccess
0x180072998  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007299e  call    cs:__imp_ZwOpenKey
0x1800729a5  nop     dword ptr [rax+rax+00h]
0x1800729aa  xor     ecx, ecx
0x1800729ac  mov     ebx, eax
0x1800729ae  test    eax, eax
0x1800729b0  js      loc_180072A52
0x1800729b6  lea     rax, [rsp+2E0h+var_2B0]
0x1800729bb  xor     r9d, r9d
0x1800729be  mov     [rsp+2E0h+var_2B8], rax; __int64
0x1800729c3  mov     r8d, esi
0x1800729c6  mov     [rsp+2E0h+var_2C0], rcx; __int64
0x1800729cb  mov     rdx, r13
0x1800729ce  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x1800729d3  call    CipGetRegistryValueInternal
0x1800729d8  mov     ebx, eax
0x1800729da  cmp     ebx, 80000005h
0x1800729e0  jnz     short loc_180072A32
0x1800729e2  mov     edx, dword ptr [rsp+2E0h+var_2B0]
0x1800729e6  mov     ecx, 102h
0x1800729eb  mov     r8d, 63734943h
0x1800729f1  call    cs:__imp_ExAllocatePool2
0x1800729f8  nop     dword ptr [rax+rax+00h]
0x1800729fd  mov     rdi, rax
0x180072a00  test    rax, rax
0x180072a03  jnz     short loc_180072A0C
0x180072a05  mov     ebx, 0C0000017h
0x180072a0a  jmp     short loc_180072A52
0x180072a0c  mov     r9d, dword ptr [rsp+2E0h+var_2B0]
0x180072a11  lea     rax, [rsp+2E0h+var_2B0]
0x180072a16  mov     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180072a1b  mov     r8d, esi
0x180072a1e  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180072a23  mov     rdx, r13
0x180072a26  mov     [rsp+2E0h+var_2C0], rdi; __int64
0x180072a2b  call    CipGetRegistryValueInternal
0x180072a30  mov     ebx, eax
0x180072a32  xor     ecx, ecx
0x180072a34  test    ebx, ebx
0x180072a36  js      short loc_180072A52
0x180072a38  mov     rax, [rbp+1E0h+var_260]
0x180072a3c  mov     [rax], rdi
0x180072a3f  mov     edi, ecx
0x180072a41  mov     rcx, [rbp+1E0h+var_258]
0x180072a45  mov     eax, dword ptr [rsp+2E0h+var_2B0]
0x180072a49  mov     [rcx], eax
0x180072a4b  jmp     short loc_180072A52
0x180072a4d  mov     ebx, 0C00000F2h
0x180072a52  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x180072a57  test    rcx, rcx
0x180072a5a  jz      short loc_180072A68
0x180072a5c  call    cs:__imp_ZwClose
0x180072a63  nop     dword ptr [rax+rax+00h]
0x180072a68  test    rdi, rdi
0x180072a6b  jz      short loc_180072A81
0x180072a6d  mov     edx, 63734943h; Tag
0x180072a72  mov     rcx, rdi; P
0x180072a75  call    cs:__imp_ExFreePoolWithTag
0x180072a7c  nop     dword ptr [rax+rax+00h]
0x180072a81  mov     eax, ebx
0x180072a83  mov     rcx, [rbp+1E0h+var_40]
0x180072a8a  xor     rcx, rsp; StackCookie
0x180072a8d  call    __security_check_cookie
0x180072a92  mov     rbx, [rsp+2E0h+arg_0]
0x180072a9a  add     rsp, 2B0h
0x180072aa1  pop     r15
0x180072aa3  pop     r14
0x180072aa5  pop     r13
0x180072aa7  pop     r12
0x180072aa9  pop     rdi
0x180072aaa  pop     rsi
0x180072aab  pop     rbp
0x180072aac  retn
```
