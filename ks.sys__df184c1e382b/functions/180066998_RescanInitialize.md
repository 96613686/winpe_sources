# RescanInitialize

- ea: `0x180066998`
- end: `0x180066bd3`
- name: `RescanInitialize`
- size: `571`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035230`

## callees

- `0x18000ae68`
- `0x18001a000`
- `0x180066998`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180066af8`
- `ntoskrnl!ZwCreateKey` at `0x180066af8`
- `ntoskrnl!ZwClose` at `0x180066b9e`
- `ntoskrnl!ZwClose` at `0x180066b9e`
- `ntoskrnl!ExDeleteResourceLite` at `0x180066bb0`
- `ntoskrnl!ExDeleteResourceLite` at `0x180066bb0`
- `ntoskrnl!ZwNotifyChangeKey` at `0x180066b80`
- `ntoskrnl!ZwNotifyChangeKey` at `0x180066b80`
- `ntoskrnl!ExInitializeResourceLite` at `0x180066b2a`
- `ntoskrnl!ExInitializeResourceLite` at `0x180066b2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066a74`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066b0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066a74`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066b0c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066a14`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180066a14`

## string_xrefs

- `0x180066a46`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall RescanInitialize(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rax
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // r15
  unsigned __int16 v7; // ax
  unsigned int v8; // r14d
  PVOID PoolWithTag; // rax
  void *v10; // rbx
  HANDLE *v12; // rbx
  NTSTATUS v13; // edi
  NTSTATUS v14; // eax
  PVOID P[2]; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF

  v1 = -1;
  v2 = *(_QWORD *)(a1 + 112);
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, 44);
  v4 = *(_QWORD *)(v2 + 8);
  v5 = -1;
  v6 = *(_QWORD *)(v4 + 48);
  do
    ++v5;
  while ( aNotify[v5] );
  v7 = *(_WORD *)(v6 + 26) + 2 * (v5 + 53);
  v8 = v7;
  WORD1(P[0]) = v7;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v7, 0x72645753u);
  v10 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported || !PoolWithTag )
  {
    P[1] = PoolWithTag;
    if ( !PoolWithTag )
      return 3221225626LL;
  }
  else
  {
    memset(PoolWithTag, 0, v8);
    P[1] = v10;
  }
  if ( StringCbPrintfW(
         (STRSAFE_LPWSTR)v10,
         WORD1(P[0]),
         L"%s\\%s\\%s",
         L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Services",
         *(_QWORD *)(v6 + 32),
         L"Notify") >= 0 )
  {
    do
      ++v1;
    while ( *((_WORD *)P[1] + v1) );
    ObjectAttributes.Length = 48;
    v12 = (HANDLE *)(a1 + 360);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 704;
    LOWORD(P[0]) = 2 * v1;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = ZwCreateKey((PHANDLE)(a1 + 360), 0x10u, &ObjectAttributes, 0, 0, 0, 0);
    ExFreePoolWithTag(P[1], 0);
    if ( v13 >= 0 )
    {
      ExInitializeResourceLite((PERESOURCE)(a1 + 392));
      *(_QWORD *)(a1 + 728) = RescanNotifyChanges;
      *(_QWORD *)(a1 + 736) = a1;
      *(_QWORD *)(a1 + 712) = 0;
      v14 = ZwNotifyChangeKey(
              *v12,
              0,
              (PIO_APC_ROUTINE)(a1 + 712),
              (PVOID)1,
              (PIO_STATUS_BLOCK)(a1 + 368),
              4u,
              0,
              0,
              0,
              1u);
      v13 = 0;
      if ( v14 != 259 )
        v13 = v14;
      if ( v13 < 0 )
      {
        ZwClose(*v12);
        *v12 = 0;
        ExDeleteResourceLite((PERESOURCE)(a1 + 392));
      }
    }
    return (unsigned int)v13;
  }
  else
  {
    ExFreePoolWithTag(P[1], 0);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x180066998  push    rbp
0x18006699a  push    rbx
0x18006699b  push    rsi
0x18006699c  push    rdi
0x18006699d  push    r12
0x18006699f  push    r13
0x1800669a1  push    r14
0x1800669a3  push    r15
0x1800669a5  lea     rbp, [rsp-1Fh]
0x1800669aa  sub     rsp, 98h
0x1800669b1  xorps   xmm0, xmm0
0x1800669b4  lea     r13, aNotify; "Notify"
0x1800669bb  xor     eax, eax
0x1800669bd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800669c1  mov     rax, [rcx+70h]
0x1800669c5  mov     rsi, rcx
0x1800669c8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800669cc  xor     r12d, r12d
0x1800669cf  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800669d3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800669d7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800669db  mov     rdx, [rax+8]
0x1800669df  mov     rax, rdi
0x1800669e2  mov     r15, [rdx+30h]
0x1800669e6  inc     rax
0x1800669e9  cmp     [r13+rax*2+0], r12w
0x1800669ef  jnz     short loc_1800669E6
0x1800669f1  add     ax, 35h ; '5'
0x1800669f5  mov     r8d, 72645753h; Tag
0x1800669fb  add     ax, ax
0x1800669fe  mov     ecx, 401h; PoolType
0x180066a03  add     ax, [r15+1Ah]
0x180066a08  movzx   r14d, ax
0x180066a0c  mov     edx, r14d; NumberOfBytes
0x180066a0f  mov     word ptr [rbp+57h+P+2], r14w
0x180066a14  call    cs:__imp_ExAllocatePoolWithTag
0x180066a1b  nop     dword ptr [rax+rax+00h]
0x180066a20  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x180066a27  mov     rbx, rax
0x180066a2a  jnz     short loc_180066A8A
0x180066a2c  test    rax, rax
0x180066a2f  jz      short loc_180066A8A
0x180066a31  mov     r8d, r14d; Size
0x180066a34  xor     edx, edx; Val
0x180066a36  mov     rcx, rax; void *
0x180066a39  call    memset
0x180066a3e  mov     [rbp+57h+P+8], rbx
0x180066a42  mov     rax, [r15+20h]
0x180066a46  lea     r9, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x180066a4d  movzx   edx, word ptr [rbp+57h+P+2]; cbDest
0x180066a51  lea     r8, aSSS; "%s\\%s\\%s"
0x180066a58  mov     qword ptr [rsp+0D0h+CreateOptions], r13
0x180066a5d  mov     rcx, rbx; pszDest
0x180066a60  mov     [rsp+0D0h+Class], rax
0x180066a65  call    StringCbPrintfW
0x180066a6a  test    eax, eax
0x180066a6c  jns     short loc_180066A9D
0x180066a6e  mov     rcx, [rbp+57h+P+8]; P
0x180066a72  xor     edx, edx; Tag
0x180066a74  call    cs:__imp_ExFreePoolWithTag
0x180066a7b  nop     dword ptr [rax+rax+00h]
0x180066a80  mov     eax, 0C0000001h
0x180066a85  jmp     loc_180066BBE
0x180066a8a  mov     [rbp+57h+P+8], rbx
0x180066a8e  test    rbx, rbx
0x180066a91  jnz     short loc_180066A42
0x180066a93  mov     eax, 0C000009Ah
0x180066a98  jmp     loc_180066BBE
0x180066a9d  mov     rax, [rbp+57h+P+8]
0x180066aa1  inc     rdi
0x180066aa4  cmp     [rax+rdi*2], r12w
0x180066aa9  jnz     short loc_180066AA1
0x180066aab  xor     r9d, r9d; TitleIndex
0x180066aae  mov     [rsp+0D0h+Disposition], r12; Disposition
0x180066ab3  lea     rax, [rbp+57h+P]
0x180066ab7  mov     [rsp+0D0h+CreateOptions], r12d; CreateOptions
0x180066abc  xorps   xmm0, xmm0
0x180066abf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180066ac6  lea     rbx, [rsi+168h]
0x180066acd  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180066ad1  add     di, di
0x180066ad4  mov     [rbp+57h+ObjectAttributes.Attributes], 2C0h
0x180066adb  lea     edx, [r9+10h]; DesiredAccess
0x180066adf  mov     word ptr [rbp+57h+P], di
0x180066ae3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180066ae7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180066aeb  mov     rcx, rbx; KeyHandle
0x180066aee  mov     [rsp+0D0h+Class], r12; Class
0x180066af3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180066af8  call    cs:__imp_ZwCreateKey
0x180066aff  nop     dword ptr [rax+rax+00h]
0x180066b04  mov     rcx, [rbp+57h+P+8]; P
0x180066b08  xor     edx, edx; Tag
0x180066b0a  mov     edi, eax
0x180066b0c  call    cs:__imp_ExFreePoolWithTag
0x180066b13  nop     dword ptr [rax+rax+00h]
0x180066b18  test    edi, edi
0x180066b1a  js      loc_180066BBC
0x180066b20  lea     r14, [rsi+188h]
0x180066b27  mov     rcx, r14; Resource
0x180066b2a  call    cs:__imp_ExInitializeResourceLite
0x180066b31  nop     dword ptr [rax+rax+00h]
0x180066b36  mov     [rsp+0D0h+Asynchronous], 1; Asynchronous
0x180066b3b  lea     r8, [rsi+2C8h]; ApcRoutine
0x180066b42  mov     [rsp+0D0h+BufferSize], r12d; BufferSize
0x180066b47  lea     rax, RescanNotifyChanges
0x180066b4e  mov     [r8+10h], rax
0x180066b52  xor     edx, edx; Event
0x180066b54  mov     [rsp+0D0h+Buffer], r12; Buffer
0x180066b59  lea     rax, [rsi+170h]
0x180066b60  mov     [r8+18h], rsi
0x180066b64  mov     [r8], r12
0x180066b67  mov     rcx, [rbx]; KeyHandle
0x180066b6a  lea     r9d, [rdx+1]; ApcContext
0x180066b6e  mov     byte ptr [rsp+0D0h+Disposition], r12b; WatchTree
0x180066b73  mov     [rsp+0D0h+CreateOptions], 4; CompletionFilter
0x180066b7b  mov     [rsp+0D0h+Class], rax; IoStatusBlock
0x180066b80  call    cs:__imp_ZwNotifyChangeKey
0x180066b87  nop     dword ptr [rax+rax+00h]
0x180066b8c  cmp     eax, 103h
0x180066b91  mov     edi, r12d
0x180066b94  cmovnz  edi, eax
0x180066b97  test    edi, edi
0x180066b99  jns     short loc_180066BBC
0x180066b9b  mov     rcx, [rbx]; Handle
0x180066b9e  call    cs:__imp_ZwClose
0x180066ba5  nop     dword ptr [rax+rax+00h]
0x180066baa  mov     rcx, r14; Resource
0x180066bad  mov     [rbx], r12
0x180066bb0  call    cs:__imp_ExDeleteResourceLite
0x180066bb7  nop     dword ptr [rax+rax+00h]
0x180066bbc  mov     eax, edi
0x180066bbe  add     rsp, 98h
0x180066bc5  pop     r15
0x180066bc7  pop     r14
0x180066bc9  pop     r13
0x180066bcb  pop     r12
0x180066bcd  pop     rdi
0x180066bce  pop     rsi
0x180066bcf  pop     rbx
0x180066bd0  pop     rbp
0x180066bd1  retn
```
