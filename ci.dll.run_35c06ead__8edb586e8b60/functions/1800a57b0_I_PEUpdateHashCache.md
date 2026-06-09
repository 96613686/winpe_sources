# I_PEUpdateHashCache

- ea: `0x1800a57b0`
- end: `0x1800a59fc`
- name: `I_PEUpdateHashCache`
- size: `588`
- prototype: `__int64 __usercall@<rax>(void *Source2@<rcx>, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180080078`
- `0x18009f510`
- `0x1800a4f74`

## callees

- `0x1800a57b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a57d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a57d8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a595c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800a595c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800a5821`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800a5821`
- `ntoskrnl!ExAllocatePool2` at `0x1800a585d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5905`
- `ntoskrnl!ExAllocatePool2` at `0x1800a585d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5905`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5991`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5991`
- `ntoskrnl!RtlCompareMemory` at `0x1800a58c3`
- `ntoskrnl!RtlCompareMemory` at `0x1800a58c3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800a57ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800a57ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5985`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5985`

## pseudocode

```c
void __fastcall I_PEUpdateHashCache(_DWORD *Source2, __int64 a2, const UNICODE_STRING *a3, int a4, int a5, int a6)
{
  __int64 Pool2; // rsi
  int *v7; // rbp
  __int64 *v12; // r14
  HANDLE CurrentProcessId; // rax
  char *v14; // rcx
  HANDLE v15; // rbx
  char *v16; // rax
  __int64 i; // rbx
  int v18; // [rsp+20h] [rbp-58h] BYREF

  Pool2 = 0;
  v7 = &v18;
  v18 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&g_HashCacheLock, 1u);
  if ( a5 )
  {
    v12 = &g_KernelHashBucketList;
LABEL_17:
    if ( a4 )
      ++g_ulPEFailedComponentsCount;
    if ( Pool2 || (Pool2 = ExAllocatePool2(258, a3->Length + 82LL, 1430340944)) != 0 )
    {
      *(_OWORD *)(Pool2 + 24) = *(_OWORD *)Source2;
      *(_DWORD *)(Pool2 + 40) = Source2[4];
      *(_OWORD *)(Pool2 + 44) = *(_OWORD *)a2;
      *(_DWORD *)(Pool2 + 60) = *(_DWORD *)(a2 + 16);
      *(_WORD *)(Pool2 + 10) = a3->Length + 2;
      *(_WORD *)(Pool2 + 8) = a3->Length;
      *(_QWORD *)(Pool2 + 16) = Pool2 + 72;
      RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 8), a3);
      *(_DWORD *)(Pool2 + 64) = a4;
      *(_DWORD *)(Pool2 + 68) = 0;
      *(_QWORD *)Pool2 = *v12;
      *v12 = Pool2;
      ++*v7;
    }
    goto LABEL_22;
  }
  if ( a6 == 1 )
  {
    v12 = &g_PEProcessList;
LABEL_12:
    for ( i = *v12; i; i = *(_QWORD *)i )
    {
      if ( RtlCompareMemory((const void *)(i + 24), Source2, 0x14u) == 20 )
      {
        if ( a4 && !*(_DWORD *)(i + 64) )
          ++g_ulPEFailedComponentsCount;
        *(_DWORD *)(i + 64) = a4;
        *(_DWORD *)(i + 68) = 0;
        goto LABEL_22;
      }
    }
    goto LABEL_17;
  }
  v12 = 0;
  if ( a6 )
    goto LABEL_12;
  CurrentProcessId = PsGetCurrentProcessId();
  v14 = (char *)g_PEProcessHashBucketList;
  v15 = CurrentProcessId;
  while ( v14 )
  {
    if ( CurrentProcessId == *((HANDLE *)v14 + 1) )
      goto LABEL_10;
    v14 = *(char **)v14;
  }
  v16 = (char *)ExAllocatePool2(256, a3->Length + 138LL, 1430340944);
  v14 = v16;
  if ( v16 )
  {
    *((_QWORD *)v16 + 1) = v15;
    Pool2 = (__int64)(v16 + 56);
    *((_DWORD *)v16 + 10) = 1;
    *((_DWORD *)v16 + 11) = dword_180049420;
    *(_QWORD *)v16 = g_PEProcessHashBucketList;
    g_PEProcessHashBucketList = v16;
LABEL_10:
    v12 = (__int64 *)(v14 + 24);
    v7 = (int *)(v14 + 32);
    if ( a4 )
      *((_DWORD *)v14 + 4) = 1;
    goto LABEL_12;
  }
  if ( a4 )
    ++g_ulPEFailedComponentsCount;
LABEL_22:
  ExReleaseResourceLite(&g_HashCacheLock);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1800a57b0  push    rbx
0x1800a57b2  push    rbp
0x1800a57b3  push    rsi
0x1800a57b4  push    rdi
0x1800a57b5  push    r12
0x1800a57b7  push    r13
0x1800a57b9  push    r14
0x1800a57bb  push    r15
0x1800a57bd  sub     rsp, 38h
0x1800a57c1  xor     esi, esi
0x1800a57c3  lea     rbp, [rsp+78h+var_58]
0x1800a57c8  mov     [rsp+78h+var_58], esi
0x1800a57cc  mov     edi, r9d
0x1800a57cf  mov     r15, r8
0x1800a57d2  mov     r12, rdx
0x1800a57d5  mov     r13, rcx
0x1800a57d8  call    cs:__imp_KeEnterCriticalRegion
0x1800a57df  nop     dword ptr [rax+rax+00h]
0x1800a57e4  mov     dl, 1; Wait
0x1800a57e6  lea     rcx, g_HashCacheLock; Resource
0x1800a57ed  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800a57f4  nop     dword ptr [rax+rax+00h]
0x1800a57f9  cmp     [rsp+78h+arg_20], esi
0x1800a5800  jnz     loc_1800A58DE
0x1800a5806  mov     eax, [rsp+78h+arg_28]
0x1800a580d  cmp     eax, 1
0x1800a5810  jz      loc_1800A59BF
0x1800a5816  xor     r14d, r14d
0x1800a5819  test    eax, eax
0x1800a581b  jnz     loc_1800A58AE
0x1800a5821  call    cs:__imp_PsGetCurrentProcessId
0x1800a5828  nop     dword ptr [rax+rax+00h]
0x1800a582d  mov     rcx, cs:g_PEProcessHashBucketList
0x1800a5834  mov     rbx, rax
0x1800a5837  jmp     short loc_1800A5842
0x1800a5839  cmp     rbx, [rcx+8]
0x1800a583d  jz      short loc_1800A589E
0x1800a583f  mov     rcx, [rcx]
0x1800a5842  test    rcx, rcx
0x1800a5845  jnz     short loc_1800A5839
0x1800a5847  movzx   edx, word ptr [r15]
0x1800a584b  mov     ecx, 100h
0x1800a5850  add     rdx, 8Ah
0x1800a5857  mov     r8d, 55414550h
0x1800a585d  call    cs:__imp_ExAllocatePool2
0x1800a5864  nop     dword ptr [rax+rax+00h]
0x1800a5869  mov     rcx, rax
0x1800a586c  test    rax, rax
0x1800a586f  jz      loc_1800A59CB
0x1800a5875  mov     [rax+8], rbx
0x1800a5879  lea     rsi, [rcx+38h]
0x1800a587d  mov     dword ptr [rax+28h], 1
0x1800a5884  mov     eax, cs:dword_180049420
0x1800a588a  mov     [rcx+2Ch], eax
0x1800a588d  mov     rax, cs:g_PEProcessHashBucketList
0x1800a5894  mov     [rcx], rax
0x1800a5897  mov     cs:g_PEProcessHashBucketList, rcx
0x1800a589e  lea     r14, [rcx+18h]
0x1800a58a2  lea     rbp, [rcx+20h]
0x1800a58a6  test    edi, edi
0x1800a58a8  jnz     loc_1800A59D7
0x1800a58ae  mov     rbx, [r14]
0x1800a58b1  test    rbx, rbx
0x1800a58b4  jz      short loc_1800A58E5
0x1800a58b6  lea     rcx, [rbx+18h]; Source1
0x1800a58ba  mov     r8d, 14h; Length
0x1800a58c0  mov     rdx, r13; Source2
0x1800a58c3  call    cs:__imp_RtlCompareMemory
0x1800a58ca  nop     dword ptr [rax+rax+00h]
0x1800a58cf  cmp     rax, 14h
0x1800a58d3  jz      loc_1800A59AF
0x1800a58d9  mov     rbx, [rbx]
0x1800a58dc  jmp     short loc_1800A58B1
0x1800a58de  lea     r14, g_KernelHashBucketList
0x1800a58e5  test    edi, edi
0x1800a58e7  jnz     loc_1800A59F1
0x1800a58ed  test    rsi, rsi
0x1800a58f0  jnz     short loc_1800A5919
0x1800a58f2  movzx   edx, word ptr [r15]
0x1800a58f6  mov     ecx, 102h
0x1800a58fb  add     rdx, 52h ; 'R'
0x1800a58ff  mov     r8d, 55414550h
0x1800a5905  call    cs:__imp_ExAllocatePool2
0x1800a590c  nop     dword ptr [rax+rax+00h]
0x1800a5911  mov     rsi, rax
0x1800a5914  test    rax, rax
0x1800a5917  jz      short loc_1800A597E
0x1800a5919  movups  xmm0, xmmword ptr [r13+0]
0x1800a591e  mov     rdx, r15; SourceString
0x1800a5921  movups  xmmword ptr [rsi+18h], xmm0
0x1800a5925  mov     ecx, [r13+10h]
0x1800a5929  mov     [rsi+28h], ecx
0x1800a592c  lea     rcx, [rsi+8]; DestinationString
0x1800a5930  movups  xmm0, xmmword ptr [r12]
0x1800a5935  movups  xmmword ptr [rsi+2Ch], xmm0
0x1800a5939  mov     eax, [r12+10h]
0x1800a593e  mov     [rsi+3Ch], eax
0x1800a5941  movzx   eax, word ptr [r15]
0x1800a5945  add     ax, 2
0x1800a5949  mov     [rsi+0Ah], ax
0x1800a594d  movzx   eax, word ptr [r15]
0x1800a5951  mov     [rcx], ax
0x1800a5954  lea     rax, [rsi+48h]
0x1800a5958  mov     [rsi+10h], rax
0x1800a595c  call    cs:__imp_RtlCopyUnicodeString
0x1800a5963  nop     dword ptr [rax+rax+00h]
0x1800a5968  mov     [rsi+40h], edi
0x1800a596b  mov     dword ptr [rsi+44h], 0
0x1800a5972  mov     rax, [r14]
0x1800a5975  mov     [rsi], rax
0x1800a5978  mov     [r14], rsi
0x1800a597b  inc     dword ptr [rbp+0]
0x1800a597e  lea     rcx, g_HashCacheLock; Resource
0x1800a5985  call    cs:__imp_ExReleaseResourceLite
0x1800a598c  nop     dword ptr [rax+rax+00h]
0x1800a5991  call    cs:__imp_KeLeaveCriticalRegion
0x1800a5998  nop     dword ptr [rax+rax+00h]
0x1800a599d  add     rsp, 38h
0x1800a59a1  pop     r15
0x1800a59a3  pop     r14
0x1800a59a5  pop     r13
0x1800a59a7  pop     r12
0x1800a59a9  pop     rdi
0x1800a59aa  pop     rsi
0x1800a59ab  pop     rbp
0x1800a59ac  pop     rbx
0x1800a59ad  retn
0x1800a59af  test    edi, edi
0x1800a59b1  jnz     short loc_1800A59E3
0x1800a59b3  mov     [rbx+40h], edi
0x1800a59b6  mov     dword ptr [rbx+44h], 0
0x1800a59bd  jmp     short loc_1800A597E
0x1800a59bf  lea     r14, g_PEProcessList
0x1800a59c6  jmp     loc_1800A58AE
0x1800a59cb  test    edi, edi
0x1800a59cd  jz      short loc_1800A597E
0x1800a59cf  inc     cs:g_ulPEFailedComponentsCount
0x1800a59d5  jmp     short loc_1800A597E
0x1800a59d7  mov     dword ptr [rcx+10h], 1
0x1800a59de  jmp     loc_1800A58AE
0x1800a59e3  cmp     dword ptr [rbx+40h], 0
0x1800a59e7  jnz     short loc_1800A59B3
0x1800a59e9  inc     cs:g_ulPEFailedComponentsCount
0x1800a59ef  jmp     short loc_1800A59B3
0x1800a59f1  inc     cs:g_ulPEFailedComponentsCount
0x1800a59f7  jmp     loc_1800A58ED
```
