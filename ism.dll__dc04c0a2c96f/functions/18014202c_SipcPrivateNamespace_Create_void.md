# SipcPrivateNamespace::Create(void)

- ea: `0x18014202c`
- end: `0x180142146`
- name: `?Create@SipcPrivateNamespace@@QEAAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801433e0`

## callees

- `0x18014202c`
- `0x18014265c`
- `0x180142860`
- `0x180142c04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801420df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801420df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801420a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142103`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142123`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801420a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142103`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180142123`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180142072`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180142111`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180142131`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180142072`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180142111`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180142131`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x1801420d1`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x1801420d1`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::Create(SipcPrivateNamespace *this)
{
  __int64 result; // rax
  int BoundaryDescriptorAndInitializeName; // ebx
  HANDLE v4; // rbx
  HLOCAL v5; // rdi
  HANDLE v6; // rax
  signed int LastError; // eax
  unsigned int v8; // esi
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+20h] [rbp-20h] BYREF
  HANDLE BoundaryDescriptor; // [rsp+60h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+28h] BYREF

  result = SipcPrivateNamespaceAttributes::InitializeForCurrentProcess((PUCHAR)this + 84);
  if ( (int)result < 0 )
    return result;
  BoundaryDescriptor = 0;
  BoundaryDescriptorAndInitializeName = SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(
                                          this,
                                          &BoundaryDescriptor);
  if ( BoundaryDescriptorAndInitializeName < 0 )
    goto LABEL_3;
  hMem = 0;
  BoundaryDescriptorAndInitializeName = SipcPrivateNamespace::GetSecurityDescriptor(this, &hMem);
  if ( BoundaryDescriptorAndInitializeName < 0 )
  {
    if ( hMem )
      LocalFree(hMem);
LABEL_3:
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    return (unsigned int)BoundaryDescriptorAndInitializeName;
  }
  v4 = BoundaryDescriptor;
  v5 = hMem;
  *(_QWORD *)&PrivateNamespaceAttributes.nLength = 24;
  PrivateNamespaceAttributes.lpSecurityDescriptor = hMem;
  *(_QWORD *)&PrivateNamespaceAttributes.bInheritHandle = 0;
  v6 = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, BoundaryDescriptor, (LPCWSTR)this + 4);
  *(_QWORD *)this = v6;
  if ( v6 )
  {
    if ( v5 )
      LocalFree(v5);
    if ( v4 )
      DeleteBoundaryDescriptor(v4);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = -2147418113;
    if ( LastError < 0 )
      v8 = LastError;
    if ( v5 )
      LocalFree(v5);
    if ( v4 )
      DeleteBoundaryDescriptor(v4);
    return v8;
  }
}

```

## disassembly

```asm
0x18014202c  mov     [rsp-18h+arg_10], rbx
0x180142031  push    rbp
0x180142032  push    rsi
0x180142033  push    rdi
0x180142034  mov     rbp, rsp
0x180142037  sub     rsp, 40h
0x18014203b  mov     rsi, rcx
0x18014203e  add     rcx, 54h ; 'T'; pbBuffer
0x180142042  call    ?InitializeForCurrentProcess@SipcPrivateNamespaceAttributes@@QEAAJXZ; SipcPrivateNamespaceAttributes::InitializeForCurrentProcess(void)
0x180142047  test    eax, eax
0x180142049  js      loc_180142139
0x18014204f  lea     rdx, [rbp+BoundaryDescriptor]; void **
0x180142053  mov     [rbp+BoundaryDescriptor], 0
0x18014205b  mov     rcx, rsi; this
0x18014205e  call    ?GetBoundaryDescriptorAndInitializeName@SipcPrivateNamespace@@AEAAJPEAPEAX@Z; SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(void * *)
0x180142063  mov     ebx, eax
0x180142065  test    eax, eax
0x180142067  jns     short loc_18014207F
0x180142069  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x18014206d  test    rcx, rcx
0x180142070  jz      short loc_180142078
0x180142072  call    cs:__imp_DeleteBoundaryDescriptor
0x180142078  mov     eax, ebx
0x18014207a  jmp     loc_180142139
0x18014207f  lea     rdx, [rbp+hMem]; void **
0x180142083  mov     [rbp+hMem], 0
0x18014208b  mov     rcx, rsi; this
0x18014208e  call    ?GetSecurityDescriptor@SipcPrivateNamespace@@AEAAJPEAPEAX@Z; SipcPrivateNamespace::GetSecurityDescriptor(void * *)
0x180142093  mov     ebx, eax
0x180142095  test    eax, eax
0x180142097  jns     short loc_1801420AA
0x180142099  mov     rcx, [rbp+hMem]; hMem
0x18014209d  test    rcx, rcx
0x1801420a0  jz      short loc_180142069
0x1801420a2  call    cs:__imp_LocalFree
0x1801420a8  jmp     short loc_180142069
0x1801420aa  mov     rbx, [rbp+BoundaryDescriptor]
0x1801420ae  lea     r8, [rsi+8]; lpAliasPrefix
0x1801420b2  mov     rdi, [rbp+hMem]
0x1801420b6  lea     rcx, [rbp+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x1801420ba  mov     rdx, rbx; lpBoundaryDescriptor
0x1801420bd  mov     qword ptr [rbp+PrivateNamespaceAttributes.nLength], 18h
0x1801420c5  mov     [rbp+PrivateNamespaceAttributes.lpSecurityDescriptor], rdi
0x1801420c9  mov     qword ptr [rbp+PrivateNamespaceAttributes.bInheritHandle], 0
0x1801420d1  call    cs:__imp_CreatePrivateNamespaceW
0x1801420d7  mov     [rsi], rax
0x1801420da  test    rax, rax
0x1801420dd  jnz     short loc_18014211B
0x1801420df  call    cs:__imp_GetLastError
0x1801420e5  test    eax, eax
0x1801420e7  jle     short loc_1801420F1
0x1801420e9  movzx   eax, ax
0x1801420ec  or      eax, 80070000h
0x1801420f1  test    eax, eax
0x1801420f3  mov     esi, 8000FFFFh
0x1801420f8  cmovs   esi, eax
0x1801420fb  test    rdi, rdi
0x1801420fe  jz      short loc_180142109
0x180142100  mov     rcx, rdi; hMem
0x180142103  call    cs:__imp_LocalFree
0x180142109  test    rbx, rbx
0x18014210c  jz      short loc_180142117
0x18014210e  mov     rcx, rbx; BoundaryDescriptor
0x180142111  call    cs:__imp_DeleteBoundaryDescriptor
0x180142117  mov     eax, esi
0x180142119  jmp     short loc_180142139
0x18014211b  test    rdi, rdi
0x18014211e  jz      short loc_180142129
0x180142120  mov     rcx, rdi; hMem
0x180142123  call    cs:__imp_LocalFree
0x180142129  test    rbx, rbx
0x18014212c  jz      short loc_180142137
0x18014212e  mov     rcx, rbx; BoundaryDescriptor
0x180142131  call    cs:__imp_DeleteBoundaryDescriptor
0x180142137  xor     eax, eax
0x180142139  mov     rbx, [rsp+40h+arg_10]
0x18014213e  add     rsp, 40h
0x180142142  pop     rdi
0x180142143  pop     rsi
0x180142144  pop     rbp
0x180142145  retn
```
