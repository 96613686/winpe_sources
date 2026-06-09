# RefsWatchForRegistryChanges

- ea: `0x1c0175740`
- end: `0x1c01758c6`
- name: `RefsWatchForRegistryChanges`
- size: `390`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1c01d7324`

## callees

- `0x1c006ac80`
- `0x1c0175740`
- `0x1c01758cc`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01757b7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01757ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01757b7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01757ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01809a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0188ebc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0188f23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01809a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0188ebc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0188f23`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c0175812`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c0175812`
- `ntoskrnl!ZwClose` at `0x1c01809ba`
- `ntoskrnl!ZwClose` at `0x1c0188ed9`
- `ntoskrnl!ZwClose` at `0x1c0188efc`
- `ntoskrnl!ZwClose` at `0x1c01809ba`
- `ntoskrnl!ZwClose` at `0x1c0188ed9`
- `ntoskrnl!ZwClose` at `0x1c0188efc`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1c0175882`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1c0175882`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c018098f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0188eab`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0188f12`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c018098f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0188eab`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1c0188f12`

## pseudocode

```c
void __fastcall RefsWatchForRegistryChanges(char *P)
{
  _WORD *v2; // rdi
  char v3; // r14
  bool v4; // si
  const UNICODE_STRING *v5; // r15
  _WORD *PoolWithTag; // rax
  unsigned int Length; // ecx
  PVOID v8; // rax
  HANDLE v9; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-38h] BYREF
  bool v11; // [rsp+A0h] [rbp+8h] BYREF
  HANDLE KeyHandle; // [rsp+A8h] [rbp+10h] BYREF

  IoStatusBlock = 0;
  KeyHandle = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  if ( !P[32] || P[33] )
  {
    v5 = (const UNICODE_STRING *)(P + 40);
    if ( (int)RefsRegistryOpenDeepestPath((__int128 *)(P + 40), &KeyHandle, &v11) >= 0 )
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x4A666552u);
      v2 = PoolWithTag;
      if ( PoolWithTag )
      {
        Length = v5->Length;
        PoolWithTag[21] = Length;
        v8 = ExAllocatePoolWithTag(PagedPool, Length, 0x4A666552u);
        *((_QWORD *)v2 + 6) = v8;
        if ( v8 )
        {
          v3 = 1;
          RtlCopyUnicodeString((PUNICODE_STRING)(v2 + 20), v5);
          *((_BYTE *)v2 + 32) = 1;
          *((_BYTE *)v2 + 33) = P[33];
          *((_BYTE *)v2 + 34) = 1;
          v9 = KeyHandle;
          *((_QWORD *)v2 + 7) = KeyHandle;
          *((_QWORD *)v2 + 8) = *((_QWORD *)P + 8);
          *((_QWORD *)v2 + 2) = RefsWatchForRegistryChanges;
          *((_QWORD *)v2 + 3) = v2;
          *(_QWORD *)v2 = 0;
          v4 = ZwNotifyChangeKey(v9, 0, (PIO_APC_ROUTINE)v2, (PVOID)1, &IoStatusBlock, 5u, 1u, 0, 0, 1u) >= 0;
        }
      }
    }
    if ( !v4 )
    {
      if ( v2 )
      {
        if ( v3 )
          RtlFreeUnicodeString((PUNICODE_STRING)(v2 + 20));
        ExFreePoolWithTag(v2, 0);
      }
      if ( KeyHandle )
        ZwClose(KeyHandle);
    }
  }
  if ( P[32] )
  {
    (*((void (__fastcall **)(char *))P + 8))(P);
    ZwClose(*((HANDLE *)P + 7));
    if ( P[34] )
      RtlFreeUnicodeString((PUNICODE_STRING)(P + 40));
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x1c0175740  mov     rax, rsp
0x1c0175743  mov     [rax+18h], rbx
0x1c0175747  push    rsi
0x1c0175748  push    rdi
0x1c0175749  push    r13
0x1c017574b  push    r14
0x1c017574d  push    r15
0x1c017574f  sub     rsp, 70h
0x1c0175753  mov     rbx, rcx
0x1c0175756  xorps   xmm0, xmm0
0x1c0175759  movups  xmmword ptr [rax-38h], xmm0
0x1c017575d  and     qword ptr [rax+10h], 0
0x1c0175762  xor     edi, edi
0x1c0175764  mov     [rax-40h], rdi
0x1c0175768  xor     r14b, r14b
0x1c017576b  mov     [rax-47h], r14b
0x1c017576f  xor     sil, sil
0x1c0175772  mov     [rax-48h], sil
0x1c0175776  cmp     [rcx+20h], sil
0x1c017577a  jnz     loc_1C0188E8E
0x1c0175780  lea     r15, [rcx+28h]
0x1c0175784  lea     r8, [rsp+98h+arg_0]
0x1c017578c  lea     rdx, [rsp+98h+KeyHandle]
0x1c0175794  mov     rcx, r15
0x1c0175797  call    RefsRegistryOpenDeepestPath
0x1c017579c  test    eax, eax
0x1c017579e  js      loc_1C017589D
0x1c01757a4  mov     r13d, 4A666552h
0x1c01757aa  mov     r8d, r13d; Tag
0x1c01757ad  mov     edx, 48h ; 'H'; NumberOfBytes
0x1c01757b2  mov     ecx, 200h; PoolType
0x1c01757b7  call    cs:__imp_ExAllocatePoolWithTag
0x1c01757be  nop     dword ptr [rax+rax+00h]
0x1c01757c3  mov     rdi, rax
0x1c01757c6  mov     [rsp+98h+var_40], rax
0x1c01757cb  test    rax, rax
0x1c01757ce  jz      loc_1C017589D
0x1c01757d4  movzx   ecx, word ptr [r15]
0x1c01757d8  mov     [rax+2Ah], cx
0x1c01757dc  mov     edx, ecx; NumberOfBytes
0x1c01757de  mov     r8d, r13d; Tag
0x1c01757e1  mov     r13d, 1
0x1c01757e7  mov     ecx, r13d; PoolType
0x1c01757ea  call    cs:__imp_ExAllocatePoolWithTag
0x1c01757f1  nop     dword ptr [rax+rax+00h]
0x1c01757f6  mov     [rdi+30h], rax
0x1c01757fa  test    rax, rax
0x1c01757fd  jz      loc_1C017589D
0x1c0175803  mov     r14b, r13b
0x1c0175806  mov     [rsp+98h+var_47], r13b
0x1c017580b  lea     rcx, [rdi+28h]; DestinationString
0x1c017580f  mov     rdx, r15; SourceString
0x1c0175812  call    cs:__imp_RtlCopyUnicodeString
0x1c0175819  nop     dword ptr [rax+rax+00h]
0x1c017581e  mov     [rdi+20h], r13b
0x1c0175822  mov     al, [rbx+21h]
0x1c0175825  mov     [rdi+21h], al
0x1c0175828  mov     [rdi+22h], r13b
0x1c017582c  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x1c0175834  mov     [rdi+38h], rcx
0x1c0175838  mov     rax, [rbx+40h]
0x1c017583c  mov     [rdi+40h], rax
0x1c0175840  lea     rax, RefsWatchForRegistryChanges
0x1c0175847  mov     [rdi+10h], rax
0x1c017584b  mov     [rdi+18h], rdi
0x1c017584f  and     qword ptr [rdi], 0
0x1c0175853  mov     [rsp+98h+Asynchronous], r13b; Asynchronous
0x1c0175858  and     [rsp+98h+var_58], 0
0x1c017585d  and     [rsp+98h+var_60], 0
0x1c0175863  mov     [rsp+98h+WatchTree], r13b; WatchTree
0x1c0175868  mov     [rsp+98h+CompletionFilter], 5; CompletionFilter
0x1c0175870  lea     rax, [rsp+98h+var_38]
0x1c0175875  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x1c017587a  mov     r9d, r13d; ApcContext
0x1c017587d  mov     r8, rdi; ApcRoutine
0x1c0175880  xor     edx, edx; Event
0x1c0175882  call    cs:__imp_ZwNotifyChangeKey
0x1c0175889  nop     dword ptr [rax+rax+00h]
0x1c017588e  movzx   esi, sil
0x1c0175892  test    eax, eax
0x1c0175894  cmovns  esi, r13d
0x1c0175898  mov     [rsp+98h+var_48], sil
0x1c017589d  test    sil, sil
0x1c01758a0  jz      loc_1C0188E9D
0x1c01758a6  cmp     byte ptr [rbx+20h], 0
0x1c01758aa  jnz     loc_1C0188EEB
0x1c01758b0  mov     rbx, [rsp+98h+arg_10]
0x1c01758b8  add     rsp, 70h
0x1c01758bc  pop     r15
0x1c01758be  pop     r14
0x1c01758c0  pop     r13
0x1c01758c2  pop     rdi
0x1c01758c3  pop     rsi
0x1c01758c4  retn
0x1c018096c  push    rbx
0x1c018096e  push    rbp
0x1c018096f  sub     rsp, 58h
0x1c0180973  mov     rbp, rdx
0x1c0180976  cmp     byte ptr [rbp+50h], 0
0x1c018097a  jnz     short loc_1C01809C7
0x1c018097c  mov     rbx, [rbp+58h]
0x1c0180980  test    rbx, rbx
0x1c0180983  jz      short loc_1C01809AE
0x1c0180985  cmp     byte ptr [rbp+51h], 0
0x1c0180989  jz      short loc_1C018099C
0x1c018098b  lea     rcx, [rbx+28h]; UnicodeString
0x1c018098f  call    cs:__imp_RtlFreeUnicodeString
0x1c0180996  nop     dword ptr [rax+rax+00h]
0x1c018099b  nop
0x1c018099c  xor     edx, edx; Tag
0x1c018099e  mov     rcx, rbx; P
0x1c01809a1  call    cs:__imp_ExFreePoolWithTag
0x1c01809a8  nop     dword ptr [rax+rax+00h]
0x1c01809ad  nop
0x1c01809ae  mov     rcx, [rbp+0A8h]; Handle
0x1c01809b5  test    rcx, rcx
0x1c01809b8  jz      short loc_1C01809C7
0x1c01809ba  call    cs:__imp_ZwClose
0x1c01809c1  nop     dword ptr [rax+rax+00h]
0x1c01809c6  nop
0x1c01809c7  add     rsp, 58h
0x1c01809cb  pop     rbp
0x1c01809cc  pop     rbx
0x1c01809cd  retn
0x1c0188e8e  cmp     [rcx+21h], sil
0x1c0188e92  jz      loc_1C01758A6
0x1c0188e98  jmp     loc_1C0175780
0x1c0188e9d  test    rdi, rdi
0x1c0188ea0  jz      short loc_1C0188EC8
0x1c0188ea2  test    r14b, r14b
0x1c0188ea5  jz      short loc_1C0188EB7
0x1c0188ea7  lea     rcx, [rdi+28h]; UnicodeString
0x1c0188eab  call    cs:__imp_RtlFreeUnicodeString
0x1c0188eb2  nop     dword ptr [rax+rax+00h]
0x1c0188eb7  xor     edx, edx; Tag
0x1c0188eb9  mov     rcx, rdi; P
0x1c0188ebc  call    cs:__imp_ExFreePoolWithTag
0x1c0188ec3  nop     dword ptr [rax+rax+00h]
0x1c0188ec8  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x1c0188ed0  test    rcx, rcx
0x1c0188ed3  jz      loc_1C01758A6
0x1c0188ed9  call    cs:__imp_ZwClose
0x1c0188ee0  nop     dword ptr [rax+rax+00h]
0x1c0188ee5  nop
0x1c0188ee6  jmp     loc_1C01758A6
0x1c0188eeb  mov     rax, [rbx+40h]
0x1c0188eef  mov     rcx, rbx
0x1c0188ef2  call    cs:__guard_dispatch_icall_fptr
0x1c0188ef8  mov     rcx, [rbx+38h]; Handle
0x1c0188efc  call    cs:__imp_ZwClose
0x1c0188f03  nop     dword ptr [rax+rax+00h]
0x1c0188f08  cmp     byte ptr [rbx+22h], 0
0x1c0188f0c  jz      short loc_1C0188F1E
0x1c0188f0e  lea     rcx, [rbx+28h]; UnicodeString
0x1c0188f12  call    cs:__imp_RtlFreeUnicodeString
0x1c0188f19  nop     dword ptr [rax+rax+00h]
0x1c0188f1e  xor     edx, edx; Tag
0x1c0188f20  mov     rcx, rbx; P
0x1c0188f23  call    cs:__imp_ExFreePoolWithTag
0x1c0188f2a  nop     dword ptr [rax+rax+00h]
0x1c0188f2f  nop
0x1c0188f30  jmp     loc_1C01758B0
```
