# GetUserProfilePaths

- ea: `0x140005798`
- end: `0x1400058c6`
- name: `GetUserProfilePaths`
- size: `302`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000459c`
- `0x1400058cc`

## callees

- `0x140005798`
- `0x140005b00`
- `0x140005b84`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140005830`
- `ntoskrnl!ZwOpenKey` at `0x140005830`
- `ntoskrnl!ZwClose` at `0x14000585b`
- `ntoskrnl!ZwClose` at `0x140005870`
- `ntoskrnl!ZwClose` at `0x14000585b`
- `ntoskrnl!ZwClose` at `0x140005870`

## pseudocode

```c
__int64 __fastcall GetUserProfilePaths(struct _UNICODE_STRING *a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  HANDLE v7; // r14
  NTSTATUS ProfilePaths; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+48h] BYREF

  KeyHandle = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)a3 = 0;
  v6 = OpenProfileListKey(&Handle);
  v7 = Handle;
  ProfilePaths = v6;
  if ( v6 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a1;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ProfilePaths = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( ProfilePaths >= 0 )
      ProfilePaths = QueryProfilePaths(KeyHandle);
  }
  if ( v7 )
    ZwClose(v7);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( ProfilePaths < 0 )
  {
    v9 = *(_QWORD *)(a2 + 8);
    if ( v9 )
    {
      LuafvFreePool(v9);
      *(_OWORD *)a2 = 0;
    }
    v10 = *(_QWORD *)(a3 + 8);
    if ( v10 )
    {
      LuafvFreePool(v10);
      *(_OWORD *)a3 = 0;
    }
  }
  return (unsigned int)ProfilePaths;
}

```

## disassembly

```asm
0x140005798  mov     [rsp-28h+arg_8], rbx
0x14000579d  push    rbp
0x14000579e  push    rsi
0x14000579f  push    rdi
0x1400057a0  push    r14
0x1400057a2  push    r15
0x1400057a4  mov     rbp, rsp
0x1400057a7  sub     rsp, 50h
0x1400057ab  xor     eax, eax
0x1400057ad  xorps   xmm0, xmm0
0x1400057b0  mov     [rbp+KeyHandle], rax
0x1400057b4  mov     rbx, r8
0x1400057b7  mov     [rbp+Handle], rax
0x1400057bb  mov     rsi, rdx
0x1400057be  mov     r15, rcx
0x1400057c1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400057c5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400057c9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400057cd  test    rcx, rcx
0x1400057d0  jz      loc_1400058AC
0x1400057d6  test    rdx, rdx
0x1400057d9  jz      loc_1400058AC
0x1400057df  test    rbx, rbx
0x1400057e2  jz      loc_1400058AC
0x1400057e8  xorps   xmm1, xmm1
0x1400057eb  lea     rcx, [rbp+Handle]
0x1400057ef  movups  xmmword ptr [rdx], xmm0
0x1400057f2  movups  xmmword ptr [r8], xmm1
0x1400057f6  call    OpenProfileListKey
0x1400057fb  mov     r14, [rbp+Handle]
0x1400057ff  mov     edi, eax
0x140005801  test    eax, eax
0x140005803  js      short loc_140005853
0x140005805  xorps   xmm0, xmm0
0x140005808  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000580f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140005813  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x140005817  mov     edx, 20019h; DesiredAccess
0x14000581c  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140005823  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140005827  mov     [rbp+ObjectAttributes.ObjectName], r15
0x14000582b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140005830  call    cs:__imp_ZwOpenKey
0x140005837  nop     dword ptr [rax+rax+00h]
0x14000583c  mov     edi, eax
0x14000583e  test    eax, eax
0x140005840  js      short loc_140005853
0x140005842  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140005846  mov     r8, rbx
0x140005849  mov     rdx, rsi
0x14000584c  call    QueryProfilePaths
0x140005851  mov     edi, eax
0x140005853  test    r14, r14
0x140005856  jz      short loc_140005867
0x140005858  mov     rcx, r14; Handle
0x14000585b  call    cs:__imp_ZwClose
0x140005862  nop     dword ptr [rax+rax+00h]
0x140005867  mov     rcx, [rbp+KeyHandle]; Handle
0x14000586b  test    rcx, rcx
0x14000586e  jz      short loc_14000587C
0x140005870  call    cs:__imp_ZwClose
0x140005877  nop     dword ptr [rax+rax+00h]
0x14000587c  test    edi, edi
0x14000587e  jns     short loc_1400058A8
0x140005880  mov     rcx, [rsi+8]
0x140005884  test    rcx, rcx
0x140005887  jz      short loc_140005894
0x140005889  call    LuafvFreePool
0x14000588e  xorps   xmm0, xmm0
0x140005891  movups  xmmword ptr [rsi], xmm0
0x140005894  mov     rcx, [rbx+8]
0x140005898  test    rcx, rcx
0x14000589b  jz      short loc_1400058A8
0x14000589d  call    LuafvFreePool
0x1400058a2  xorps   xmm0, xmm0
0x1400058a5  movups  xmmword ptr [rbx], xmm0
0x1400058a8  mov     eax, edi
0x1400058aa  jmp     short loc_1400058B1
0x1400058ac  mov     eax, 0C000000Dh
0x1400058b1  mov     rbx, [rsp+50h+arg_8]
0x1400058b9  add     rsp, 50h
0x1400058bd  pop     r15
0x1400058bf  pop     r14
0x1400058c1  pop     rdi
0x1400058c2  pop     rsi
0x1400058c3  pop     rbp
0x1400058c4  retn
```
