# RescanInitialize

- ea: `0x180066028`
- end: `0x180066263`
- name: `RescanInitialize`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035120`

## callees

- `0x18000ae68`
- `0x180019fc0`
- `0x180066028`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180066188`
- `ntoskrnl!ZwCreateKey` at `0x180066188`
- `ntoskrnl!ZwClose` at `0x18006622e`
- `ntoskrnl!ZwClose` at `0x18006622e`
- `ntoskrnl!ExDeleteResourceLite` at `0x180066240`
- `ntoskrnl!ExDeleteResourceLite` at `0x180066240`
- `ntoskrnl!ZwNotifyChangeKey` at `0x180066210`
- `ntoskrnl!ZwNotifyChangeKey` at `0x180066210`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800661ba`
- `ntoskrnl!ExInitializeResourceLite` at `0x1800661ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066104`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006619c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066104`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006619c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800660a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800660a4`

## string_xrefs

- `0x1800660d6`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services`

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
0x180066028  push    rbp
0x18006602a  push    rbx
0x18006602b  push    rsi
0x18006602c  push    rdi
0x18006602d  push    r12
0x18006602f  push    r13
0x180066031  push    r14
0x180066033  push    r15
0x180066035  lea     rbp, [rsp-1Fh]
0x18006603a  sub     rsp, 98h
0x180066041  xorps   xmm0, xmm0
0x180066044  lea     r13, aNotify; "Notify"
0x18006604b  xor     eax, eax
0x18006604d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180066051  mov     rax, [rcx+70h]
0x180066055  mov     rsi, rcx
0x180066058  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006605c  xor     r12d, r12d
0x18006605f  movups  xmmword ptr [rbp+57h+P], xmm0
0x180066063  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180066067  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18006606b  mov     rdx, [rax+8]
0x18006606f  mov     rax, rdi
0x180066072  mov     r15, [rdx+30h]
0x180066076  inc     rax
0x180066079  cmp     [r13+rax*2+0], r12w
0x18006607f  jnz     short loc_180066076
0x180066081  add     ax, 35h ; '5'
0x180066085  mov     r8d, 72645753h; Tag
0x18006608b  add     ax, ax
0x18006608e  mov     ecx, 401h; PoolType
0x180066093  add     ax, [r15+1Ah]
0x180066098  movzx   r14d, ax
0x18006609c  mov     edx, r14d; NumberOfBytes
0x18006609f  mov     word ptr [rbp+57h+P+2], r14w
0x1800660a4  call    cs:__imp_ExAllocatePoolWithTag
0x1800660ab  nop     dword ptr [rax+rax+00h]
0x1800660b0  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x1800660b7  mov     rbx, rax
0x1800660ba  jnz     short loc_18006611A
0x1800660bc  test    rax, rax
0x1800660bf  jz      short loc_18006611A
0x1800660c1  mov     r8d, r14d; Size
0x1800660c4  xor     edx, edx; Val
0x1800660c6  mov     rcx, rax; void *
0x1800660c9  call    memset
0x1800660ce  mov     [rbp+57h+P+8], rbx
0x1800660d2  mov     rax, [r15+20h]
0x1800660d6  lea     r9, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800660dd  movzx   edx, word ptr [rbp+57h+P+2]; cbDest
0x1800660e1  lea     r8, aSSS; "%s\\%s\\%s"
0x1800660e8  mov     qword ptr [rsp+0D0h+CreateOptions], r13
0x1800660ed  mov     rcx, rbx; pszDest
0x1800660f0  mov     [rsp+0D0h+Class], rax
0x1800660f5  call    StringCbPrintfW
0x1800660fa  test    eax, eax
0x1800660fc  jns     short loc_18006612D
0x1800660fe  mov     rcx, [rbp+57h+P+8]; P
0x180066102  xor     edx, edx; Tag
0x180066104  call    cs:__imp_ExFreePoolWithTag
0x18006610b  nop     dword ptr [rax+rax+00h]
0x180066110  mov     eax, 0C0000001h
0x180066115  jmp     loc_18006624E
0x18006611a  mov     [rbp+57h+P+8], rbx
0x18006611e  test    rbx, rbx
0x180066121  jnz     short loc_1800660D2
0x180066123  mov     eax, 0C000009Ah
0x180066128  jmp     loc_18006624E
0x18006612d  mov     rax, [rbp+57h+P+8]
0x180066131  inc     rdi
0x180066134  cmp     [rax+rdi*2], r12w
0x180066139  jnz     short loc_180066131
0x18006613b  xor     r9d, r9d; TitleIndex
0x18006613e  mov     [rsp+0D0h+Disposition], r12; Disposition
0x180066143  lea     rax, [rbp+57h+P]
0x180066147  mov     [rsp+0D0h+CreateOptions], r12d; CreateOptions
0x18006614c  xorps   xmm0, xmm0
0x18006614f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180066156  lea     rbx, [rsi+168h]
0x18006615d  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180066161  add     di, di
0x180066164  mov     [rbp+57h+ObjectAttributes.Attributes], 2C0h
0x18006616b  lea     edx, [r9+10h]; DesiredAccess
0x18006616f  mov     word ptr [rbp+57h+P], di
0x180066173  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180066177  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006617b  mov     rcx, rbx; KeyHandle
0x18006617e  mov     [rsp+0D0h+Class], r12; Class
0x180066183  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180066188  call    cs:__imp_ZwCreateKey
0x18006618f  nop     dword ptr [rax+rax+00h]
0x180066194  mov     rcx, [rbp+57h+P+8]; P
0x180066198  xor     edx, edx; Tag
0x18006619a  mov     edi, eax
0x18006619c  call    cs:__imp_ExFreePoolWithTag
0x1800661a3  nop     dword ptr [rax+rax+00h]
0x1800661a8  test    edi, edi
0x1800661aa  js      loc_18006624C
0x1800661b0  lea     r14, [rsi+188h]
0x1800661b7  mov     rcx, r14; Resource
0x1800661ba  call    cs:__imp_ExInitializeResourceLite
0x1800661c1  nop     dword ptr [rax+rax+00h]
0x1800661c6  mov     [rsp+0D0h+Asynchronous], 1; Asynchronous
0x1800661cb  lea     r8, [rsi+2C8h]; ApcRoutine
0x1800661d2  mov     [rsp+0D0h+BufferSize], r12d; BufferSize
0x1800661d7  lea     rax, RescanNotifyChanges
0x1800661de  mov     [r8+10h], rax
0x1800661e2  xor     edx, edx; Event
0x1800661e4  mov     [rsp+0D0h+Buffer], r12; Buffer
0x1800661e9  lea     rax, [rsi+170h]
0x1800661f0  mov     [r8+18h], rsi
0x1800661f4  mov     [r8], r12
0x1800661f7  mov     rcx, [rbx]; KeyHandle
0x1800661fa  lea     r9d, [rdx+1]; ApcContext
0x1800661fe  mov     byte ptr [rsp+0D0h+Disposition], r12b; WatchTree
0x180066203  mov     [rsp+0D0h+CreateOptions], 4; CompletionFilter
0x18006620b  mov     [rsp+0D0h+Class], rax; IoStatusBlock
0x180066210  call    cs:__imp_ZwNotifyChangeKey
0x180066217  nop     dword ptr [rax+rax+00h]
0x18006621c  cmp     eax, 103h
0x180066221  mov     edi, r12d
0x180066224  cmovnz  edi, eax
0x180066227  test    edi, edi
0x180066229  jns     short loc_18006624C
0x18006622b  mov     rcx, [rbx]; Handle
0x18006622e  call    cs:__imp_ZwClose
0x180066235  nop     dword ptr [rax+rax+00h]
0x18006623a  mov     rcx, r14; Resource
0x18006623d  mov     [rbx], r12
0x180066240  call    cs:__imp_ExDeleteResourceLite
0x180066247  nop     dword ptr [rax+rax+00h]
0x18006624c  mov     eax, edi
0x18006624e  add     rsp, 98h
0x180066255  pop     r15
0x180066257  pop     r14
0x180066259  pop     r13
0x18006625b  pop     r12
0x18006625d  pop     rdi
0x18006625e  pop     rsi
0x18006625f  pop     rbx
0x180066260  pop     rbp
0x180066261  retn
```
