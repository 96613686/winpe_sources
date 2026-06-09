# CdCreateInternalStream

- ea: `0x14000b684`
- end: `0x14000bc12`
- name: `CdCreateInternalStream`
- size: `1422`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x14000b1a4`
- `0x14000dc38`
- `0x140011138`
- `0x1400120cc`
- `0x140012198`
- `0x14001233c`
- `0x140012d24`
- `0x1400135d0`
- `0x140019a00`

## callees

- `0x140001114`
- `0x140002df0`
- `0x140003300`
- `0x14000b684`
- `0x140012464`
- `0x14001292c`
- `0x140012a14`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000b719`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b7bf`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000bb23`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b3de`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b719`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b7bf`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000bb23`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b3de`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b80d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bb60`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bb86`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b41e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b44d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b80d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bb60`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bb86`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b41e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b44d`
- `ntoskrnl!CcUnpinData` at `0x14000bab5`
- `ntoskrnl!CcUnpinData` at `0x14001b354`
- `ntoskrnl!CcUnpinData` at `0x14000bab5`
- `ntoskrnl!CcUnpinData` at `0x14001b354`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000badf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b37f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000badf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b37f`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14000b75c`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x14000b75c`
- `ntoskrnl!CcInitializeCacheMap` at `0x14000b837`
- `ntoskrnl!CcInitializeCacheMap` at `0x14000b837`
- `ntoskrnl!CcSetFileSizes` at `0x14000b91f`
- `ntoskrnl!CcSetFileSizes` at `0x14000b91f`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14000ba5b`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14000ba5b`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000bb0c`
- `ntoskrnl!CcPurgeCacheSection` at `0x14000bb0c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b3ac`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b3ac`

## pseudocode

```c
void __fastcall CdCreateInternalStream(__int64 a1, __int64 a2, __int64 a3, UNICODE_STRING *a4)
{
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v9; // rdi
  int v10; // ecx
  bool v11; // zf
  PFILE_OBJECT StreamFileObjectLite; // rax
  struct _FILE_OBJECT *v13; // rsi
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned __int64 v16; // rsi
  unsigned int v17; // edx
  __int64 i; // rcx
  unsigned __int64 *v19; // r8
  unsigned __int64 v20; // rdx
  char v21; // r13
  int v22; // ecx
  __int128 v23; // [rsp+58h] [rbp-140h] BYREF
  PVOID Bcb[3]; // [rsp+68h] [rbp-130h]
  _QWORD v25[24]; // [rsp+80h] [rbp-118h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+140h] [rbp-58h] BYREF

  memset(v25, 0, sizeof(v25));
  v23 = 0;
  *(_OWORD *)Bcb = 0;
  CurrentThread = KeGetCurrentThread();
  v9 = a3 + 200;
  if ( CurrentThread != *(struct _KTHREAD **)(a3 + 184) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)v9 + 136LL));
    *(_QWORD *)(a3 + 184) = CurrentThread;
  }
  v10 = *(_DWORD *)(a3 + 192);
  *(_DWORD *)(a3 + 192) = v10 + 1;
  if ( *(_QWORD *)(a3 + 472) )
  {
    *(_DWORD *)(a3 + 192) = v10;
    v11 = v10 == 0;
  }
  else
  {
    StreamFileObjectLite = IoCreateStreamFileObjectLite(0, *(PDEVICE_OBJECT *)(*(_QWORD *)(a2 + 8) + 16LL));
    v13 = StreamFileObjectLite;
    if ( !StreamFileObjectLite )
      CdRaiseStatusEx(a1, 3221225626LL, 0, 196608, 118);
    *(_WORD *)&StreamFileObjectLite->ReadAccess = 1;
    StreamFileObjectLite->DeleteAccess = 0;
    StreamFileObjectLite->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)(*(_QWORD *)v9 + 8LL);
    StreamFileObjectLite->FsContext = (PVOID)a3;
    StreamFileObjectLite->FsContext2 = 0;
    StreamFileObjectLite->FsContext2 = (PVOID)1;
    StreamFileObjectLite->Vpb = *(PVPB *)(*(_QWORD *)(a3 + 120) + 8LL);
    StreamFileObjectLite->FileName = *a4;
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
    *(_DWORD *)(a3 + 164) += 2;
    *(_DWORD *)(a3 + 168) = *(_DWORD *)(a3 + 168);
    *(_DWORD *)(*(_QWORD *)(a3 + 120) + 60LL) += 2;
    *(_DWORD *)(*(_QWORD *)(a3 + 120) + 64LL) = *(_DWORD *)(*(_QWORD *)(a3 + 120) + 64LL);
    *(_QWORD *)(a2 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
    CcInitializeCacheMap(v13, (PCC_FILE_SIZES)(a3 + 24), 1u, &Callbacks, (PVOID)a3);
    *(_QWORD *)(a3 + 472) = v13;
    if ( (*(_DWORD *)(a3 + 172) & 1) == 0 )
    {
      v23 = 0;
      *(_OWORD *)Bcb = 0;
      memset(v25, 0, sizeof(v25));
      CdLookupDirent(a1, a3, *(_DWORD *)(a3 + 480), (__int64)&v23);
      CdUpdateDirentFromRawDirent(a1, v14, (__int64)&v23, (__int64)v25);
      CdUpdateDirentName(a1, (__int64)v25, 0);
      if ( (__int64 *)v25[8] != &CdUnicodeSelfArray )
        CdRaiseStatusEx(a1, 3221225730LL, 0, 196608, 219);
      v15 = *(_DWORD *)(a2 + 444) & (*(_DWORD *)(a3 + 480) + HIDWORD(v25[1]) + *(_DWORD *)(a2 + 440));
      if ( !v15 )
        CdRaiseStatusEx(a1, 3221225730LL, 0, 196608, 231);
      v16 = v15;
      if ( v15 == *(_QWORD *)(a3 + 32) )
      {
        v21 = 0;
      }
      else
      {
        *(_QWORD *)(a3 + 40) = v15;
        *(_QWORD *)(a3 + 32) = v15;
        *(_QWORD *)(a3 + 24) = v15;
        CcSetFileSizes(*(PFILE_OBJECT *)(a3 + 472), (PCC_FILE_SIZES)(a3 + 24));
        v17 = 0;
        for ( i = *(_QWORD *)(a3 + 288);
              v17 < *(_DWORD *)(a3 + 284) && (__int64)(*(_QWORD *)(i + 8) + *(_QWORD *)(i + 16)) <= 0;
              i += 40 )
        {
          ++v17;
        }
        *(_DWORD *)(a3 + 284) = v17;
        v19 = *(unsigned __int64 **)(a3 + 288);
        v20 = (unsigned __int64)LODWORD(v25[1]) << *(_DWORD *)(*(_QWORD *)(a3 + 120) + 432LL);
        *v19 = v20;
        *v19 = v20 - *(unsigned int *)(a3 + 480);
        v19[1] = v16;
        v19[2] = 0;
        v19[4] = v16;
        v19[3] = v16;
        *(_DWORD *)(a3 + 284) = 1;
        v21 = 1;
      }
      if ( (v25[3] & 1) != 0 )
        *(_DWORD *)(a3 + 176) |= 2u;
      TimeFields = 0;
      TimeFields.Year = *(char *)v25[2] + 1900;
      TimeFields.Month = *(char *)(v25[2] + 1LL);
      TimeFields.Day = *(char *)(v25[2] + 2LL);
      TimeFields.Hour = *(char *)(v25[2] + 3LL);
      TimeFields.Minute = *(char *)(v25[2] + 4LL);
      TimeFields.Second = *(char *)(v25[2] + 5LL);
      TimeFields.Milliseconds = 0;
      RtlTimeFieldsToTime(&TimeFields, (PLARGE_INTEGER)(a3 + 464));
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 1) == 0 )
      {
        v22 = *(char *)(v25[2] + 6LL);
        if ( *(_BYTE *)(v25[2] + 6LL) )
        {
          if ( (unsigned __int8)(v22 + 48) <= 0x64u )
            *(_QWORD *)(a3 + 464) += 9000000000LL * -v22;
        }
      }
      *(_DWORD *)(a3 + 172) |= 1u;
      if ( Bcb[0] )
      {
        CcUnpinData(Bcb[0]);
        Bcb[0] = 0;
      }
      if ( (v25[3] & 0x100LL) != 0 && v25[8] )
      {
        ExFreePoolWithTag((PVOID)v25[8], 0);
        v25[8] = 0;
      }
      if ( v21 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)v9 + 8LL), 0, 0, 0);
    }
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
    *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
    --*(_DWORD *)(a3 + 164);
    --*(_DWORD *)(*(_QWORD *)(a3 + 120) + 60LL);
    *(_QWORD *)(a2 + 392) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
    v11 = (*(_DWORD *)(a3 + 192))-- == 1;
  }
  if ( v11 )
  {
    *(_QWORD *)(a3 + 184) = 0;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)v9 + 136LL));
  }
}

```

## disassembly

```asm
0x14000b684  push    rbx
0x14000b686  push    rsi
0x14000b687  push    rdi
0x14000b688  push    r12
0x14000b68a  push    r13
0x14000b68c  push    r14
0x14000b68e  push    r15
0x14000b690  sub     rsp, 160h
0x14000b697  mov     rax, cs:__security_cookie
0x14000b69e  xor     rax, rsp
0x14000b6a1  mov     [rsp+198h+var_48], rax
0x14000b6a9  mov     r13, r9
0x14000b6ac  mov     rbx, r8
0x14000b6af  mov     r15, rdx
0x14000b6b2  mov     r14, rcx
0x14000b6b5  mov     [rsp+198h+var_150], rdx
0x14000b6ba  mov     [rsp+198h+var_160], rbx
0x14000b6bf  xor     eax, eax
0x14000b6c1  mov     [rsp+198h+var_158], rax
0x14000b6c6  mov     [rsp+198h+var_167], al
0x14000b6ca  mov     [rsp+198h+var_168], al
0x14000b6ce  mov     [rsp+198h+var_166], al
0x14000b6d2  xor     edx, edx; Val
0x14000b6d4  mov     r8d, 0C0h; Size
0x14000b6da  lea     rcx, [rsp+198h+var_118]; void *
0x14000b6e2  call    memset
0x14000b6e7  xorps   xmm0, xmm0
0x14000b6ea  movups  [rsp+198h+var_140], xmm0
0x14000b6ef  movups  xmmword ptr [rsp+198h+Bcb], xmm0
0x14000b6f4  mov     rsi, gs:188h
0x14000b6fd  lea     rdi, [rbx+0C8h]
0x14000b704  mov     r12d, 88h
0x14000b70a  cmp     rsi, [rbx+0B8h]
0x14000b711  jz      short loc_14000B72C
0x14000b713  mov     rcx, [rdi]
0x14000b716  add     rcx, r12; FastMutex
0x14000b719  call    cs:__imp_ExAcquireFastMutex
0x14000b720  nop     dword ptr [rax+rax+00h]
0x14000b725  mov     [rbx+0B8h], rsi
0x14000b72c  mov     ecx, [rbx+0C0h]
0x14000b732  lea     eax, [rcx+1]
0x14000b735  mov     [rbx+0C0h], eax
0x14000b73b  cmp     qword ptr [rbx+1D8h], 0
0x14000b743  jz      short loc_14000B752
0x14000b745  mov     [rbx+0C0h], ecx
0x14000b74b  test    ecx, ecx
0x14000b74d  jmp     loc_14000BB73
0x14000b752  mov     rdx, [r15+8]
0x14000b756  mov     rdx, [rdx+10h]; DeviceObject
0x14000b75a  xor     ecx, ecx; FileObject
0x14000b75c  call    cs:__imp_IoCreateStreamFileObjectLite
0x14000b763  nop     dword ptr [rax+rax+00h]
0x14000b768  mov     rsi, rax
0x14000b76b  mov     [rsp+198h+var_158], rax
0x14000b770  xor     ecx, ecx
0x14000b772  test    rax, rax
0x14000b775  jz      loc_14000BBB6
0x14000b77b  mov     word ptr [rax+4Ah], 1
0x14000b781  mov     [rax+4Ch], cl
0x14000b784  mov     rax, [rdi]
0x14000b787  add     rax, 8
0x14000b78b  mov     [rsi+28h], rax
0x14000b78f  mov     [rsi+18h], rbx
0x14000b793  mov     [rsi+20h], rcx
0x14000b797  mov     qword ptr [rsi+20h], 1
0x14000b79f  mov     rax, [rbx+78h]
0x14000b7a3  mov     rcx, [rax+8]
0x14000b7a7  mov     [rsi+10h], rcx
0x14000b7ab  movups  xmm0, xmmword ptr [r13+0]
0x14000b7b0  movdqu  xmmword ptr [rsi+58h], xmm0
0x14000b7b5  lea     r13, [r15+150h]
0x14000b7bc  mov     rcx, r13; FastMutex
0x14000b7bf  call    cs:__imp_ExAcquireFastMutex
0x14000b7c6  nop     dword ptr [rax+rax+00h]
0x14000b7cb  mov     rax, gs:188h
0x14000b7d4  mov     [r15+188h], rax
0x14000b7db  add     dword ptr [rbx+0A4h], 2
0x14000b7e2  lea     rcx, [rbx+0A8h]
0x14000b7e9  mov     eax, [rcx]
0x14000b7eb  mov     [rcx], eax
0x14000b7ed  mov     rax, [rbx+78h]
0x14000b7f1  add     dword ptr [rax+3Ch], 2
0x14000b7f5  mov     rcx, [rbx+78h]
0x14000b7f9  mov     eax, [rcx+40h]
0x14000b7fc  mov     [rcx+40h], eax
0x14000b7ff  mov     qword ptr [r15+188h], 0
0x14000b80a  mov     rcx, r13; FastMutex
0x14000b80d  call    cs:__imp_ExReleaseFastMutex
0x14000b814  nop     dword ptr [rax+rax+00h]
0x14000b819  mov     [rsp+198h+var_167], 1
0x14000b81e  lea     r13, [rbx+18h]
0x14000b822  mov     [rsp+198h+LazyWriteContext], rbx; LazyWriteContext
0x14000b827  lea     r9, Callbacks; Callbacks
0x14000b82e  mov     r8b, 1; PinAccess
0x14000b831  mov     rdx, r13; FileSizes
0x14000b834  mov     rcx, rsi; FileObject
0x14000b837  call    cs:__imp_CcInitializeCacheMap
0x14000b83e  nop     dword ptr [rax+rax+00h]
0x14000b843  mov     [rbx+1D8h], rsi
0x14000b84a  mov     [rsp+198h+var_158], 0
0x14000b853  mov     eax, [rbx+0ACh]
0x14000b859  test    al, 1
0x14000b85b  jnz     loc_14000BB19
0x14000b861  xorps   xmm0, xmm0
0x14000b864  movups  [rsp+198h+var_140], xmm0
0x14000b869  movups  xmmword ptr [rsp+198h+Bcb], xmm0
0x14000b86e  xor     edx, edx; Val
0x14000b870  mov     r8d, 0C0h; Size
0x14000b876  lea     rcx, [rsp+198h+var_118]; void *
0x14000b87e  call    memset
0x14000b883  mov     [rsp+198h+var_168], 1
0x14000b888  lea     r9, [rsp+198h+var_140]
0x14000b88d  mov     r8d, [rbx+1E0h]
0x14000b894  mov     rdx, rbx
0x14000b897  mov     rcx, r14
0x14000b89a  call    CdLookupDirent
0x14000b89f  lea     r9, [rsp+198h+var_118]
0x14000b8a7  lea     r8, [rsp+198h+var_140]
0x14000b8ac  mov     rcx, r14
0x14000b8af  call    CdUpdateDirentFromRawDirent
0x14000b8b4  xor     r8d, r8d
0x14000b8b7  lea     rdx, [rsp+198h+var_118]
0x14000b8bf  mov     rcx, r14
0x14000b8c2  call    CdUpdateDirentName
0x14000b8c7  lea     rax, CdUnicodeSelfArray
0x14000b8ce  cmp     [rsp+198h+P], rax
0x14000b8d6  jnz     loc_14000BBD4
0x14000b8dc  mov     eax, [r15+1B8h]
0x14000b8e3  add     eax, [rsp+198h+var_10C]
0x14000b8ea  add     eax, [rbx+1E0h]
0x14000b8f0  and     eax, [r15+1BCh]
0x14000b8f7  jz      loc_14000BBF2
0x14000b8fd  mov     esi, eax
0x14000b8ff  cmp     rsi, [rbx+20h]
0x14000b903  jz      loc_14000B9C7
0x14000b909  mov     [rbx+28h], rsi
0x14000b90d  mov     [rbx+20h], rsi
0x14000b911  mov     [r13+0], rsi
0x14000b915  mov     rdx, r13; FileSizes
0x14000b918  mov     rcx, [rbx+1D8h]; FileObject
0x14000b91f  call    cs:__imp_CcSetFileSizes
0x14000b926  nop     dword ptr [rax+rax+00h]
0x14000b92b  mov     [rsp+198h+var_164], 0
0x14000b933  mov     [rsp+198h+var_148], 0
0x14000b93c  xor     edx, edx
0x14000b93e  mov     [rsp+198h+var_164], edx
0x14000b942  mov     rcx, [rbx+120h]
0x14000b949  mov     [rsp+198h+var_148], rcx
0x14000b94e  cmp     edx, [rbx+11Ch]
0x14000b954  jnb     short loc_14000B974
0x14000b956  mov     rax, [rcx+10h]
0x14000b95a  add     rax, [rcx+8]
0x14000b95e  test    rax, rax
0x14000b961  jg      short loc_14000B974
0x14000b963  inc     edx
0x14000b965  mov     [rsp+198h+var_164], edx
0x14000b969  add     rcx, 28h ; '('
0x14000b96d  mov     [rsp+198h+var_148], rcx
0x14000b972  jmp     short loc_14000B94E
0x14000b974  mov     [rbx+11Ch], edx
0x14000b97a  mov     r8, [rbx+120h]
0x14000b981  mov     rcx, [rbx+78h]
0x14000b985  mov     edx, [rsp+198h+var_110]
0x14000b98c  mov     ecx, [rcx+1B0h]
0x14000b992  shl     rdx, cl
0x14000b995  mov     [r8], rdx
0x14000b998  mov     eax, [rbx+1E0h]
0x14000b99e  sub     rdx, rax
0x14000b9a1  mov     [r8], rdx
0x14000b9a4  mov     [r8+8], rsi
0x14000b9a8  mov     qword ptr [r8+10h], 0
0x14000b9b0  mov     [r8+20h], rsi
0x14000b9b4  mov     [r8+18h], rsi
0x14000b9b8  mov     dword ptr [rbx+11Ch], 1
0x14000b9c2  mov     r13b, 1
0x14000b9c5  jmp     short loc_14000B9CC
0x14000b9c7  mov     r13b, [rsp+198h+var_166]
0x14000b9cc  test    [rsp+198h+var_100], 1
0x14000b9d4  jz      short loc_14000B9DD
0x14000b9d6  or      dword ptr [rbx+0B0h], 2
0x14000b9dd  xorps   xmm0, xmm0
0x14000b9e0  movups  xmmword ptr [rsp+198h+TimeFields.Year], xmm0
0x14000b9e8  mov     rcx, [rsp+198h+var_108]
0x14000b9f0  movsx   eax, byte ptr [rcx]
0x14000b9f3  mov     edx, 76Ch
0x14000b9f8  add     ax, dx
0x14000b9fb  mov     [rsp+198h+TimeFields.Year], ax
0x14000ba03  movsx   eax, byte ptr [rcx+1]
0x14000ba07  mov     [rsp+198h+TimeFields.Month], ax
0x14000ba0f  movsx   eax, byte ptr [rcx+2]
0x14000ba13  mov     [rsp+198h+TimeFields.Day], ax
0x14000ba1b  movsx   eax, byte ptr [rcx+3]
0x14000ba1f  mov     [rsp+198h+TimeFields.Hour], ax
0x14000ba27  movsx   eax, byte ptr [rcx+4]
0x14000ba2b  mov     [rsp+198h+TimeFields.Minute], ax
0x14000ba33  movsx   eax, byte ptr [rcx+5]
0x14000ba37  mov     [rsp+198h+TimeFields.Second], ax
0x14000ba3f  xor     eax, eax
0x14000ba41  mov     [rsp+198h+TimeFields.Milliseconds], ax
0x14000ba49  lea     rsi, [rbx+1D0h]
0x14000ba50  mov     rdx, rsi; Time
0x14000ba53  lea     rcx, [rsp+198h+TimeFields]; TimeFields
0x14000ba5b  call    cs:__imp_RtlTimeFieldsToTime
0x14000ba62  nop     dword ptr [rax+rax+00h]
0x14000ba67  mov     rax, [r14+10h]
0x14000ba6b  mov     ecx, [rax+30h]
0x14000ba6e  test    cl, 1
0x14000ba71  jnz     short loc_14000BAA2
0x14000ba73  mov     rax, [rsp+198h+var_108]
0x14000ba7b  movsx   ecx, byte ptr [rax+6]
0x14000ba7f  test    cl, cl
0x14000ba81  jz      short loc_14000BAA2
0x14000ba83  lea     eax, [rcx+30h]
0x14000ba86  cmp     al, 64h ; 'd'
0x14000ba88  ja      short loc_14000BAA2
0x14000ba8a  mov     eax, ecx
0x14000ba8c  neg     eax
0x14000ba8e  movsxd  rcx, eax
0x14000ba91  mov     rax, 218711A00h
0x14000ba9b  imul    rcx, rax
0x14000ba9f  add     [rsi], rcx
0x14000baa2  or      dword ptr [rbx+0ACh], 1
0x14000baa9  mov     rcx, [rsp+198h+Bcb]; Bcb
0x14000baae  xor     esi, esi
0x14000bab0  test    rcx, rcx
0x14000bab3  jz      short loc_14000BAC6
0x14000bab5  call    cs:__imp_CcUnpinData
0x14000babc  nop     dword ptr [rax+rax+00h]
0x14000bac1  mov     [rsp+198h+Bcb], rsi
0x14000bac6  test    [rsp+198h+var_FF], 1
0x14000bace  jz      short loc_14000BAF3
0x14000bad0  mov     rcx, [rsp+198h+P]; P
0x14000bad8  test    rcx, rcx
0x14000badb  jz      short loc_14000BAF3
0x14000badd  xor     edx, edx; Tag
0x14000badf  call    cs:__imp_ExFreePoolWithTag
0x14000bae6  nop     dword ptr [rax+rax+00h]
0x14000baeb  mov     [rsp+198h+P], rsi
0x14000baf3  mov     [rsp+198h+var_168], sil
0x14000baf8  test    r13b, r13b
0x14000bafb  jz      short loc_14000BB19
0x14000bafd  mov     rcx, [rdi]
0x14000bb00  add     rcx, 8; SectionObjectPointer
0x14000bb04  xor     r9d, r9d; Flags
0x14000bb07  xor     r8d, r8d; Length
0x14000bb0a  xor     edx, edx; FileOffset
0x14000bb0c  call    cs:__imp_CcPurgeCacheSection
0x14000bb13  nop     dword ptr [rax+rax+00h]
0x14000bb18  nop
0x14000bb19  lea     rsi, [r15+150h]
0x14000bb20  mov     rcx, rsi; FastMutex
0x14000bb23  call    cs:__imp_ExAcquireFastMutex
0x14000bb2a  nop     dword ptr [rax+rax+00h]
0x14000bb2f  mov     rax, gs:188h
0x14000bb38  mov     [r15+188h], rax
0x14000bb3f  or      r14d, 0FFFFFFFFh
0x14000bb43  add     [rbx+0A4h], r14d
0x14000bb4a  mov     rax, [rbx+78h]
0x14000bb4e  add     [rax+3Ch], r14d
0x14000bb52  mov     qword ptr [r15+188h], 0
0x14000bb5d  mov     rcx, rsi; FastMutex
0x14000bb60  call    cs:__imp_ExReleaseFastMutex
0x14000bb67  nop     dword ptr [rax+rax+00h]
0x14000bb6c  add     [rbx+0C0h], r14d
0x14000bb73  jnz     short loc_14000BB92
0x14000bb75  mov     qword ptr [rbx+0B8h], 0
0x14000bb80  mov     rcx, [rdi]
0x14000bb83  add     rcx, r12; FastMutex
0x14000bb86  call    cs:__imp_ExReleaseFastMutex
0x14000bb8d  nop     dword ptr [rax+rax+00h]
0x14000bb92  mov     rcx, [rsp+198h+var_48]
0x14000bb9a  xor     rcx, rsp; StackCookie
0x14000bb9d  call    __security_check_cookie
0x14000bba2  add     rsp, 160h
0x14000bba9  pop     r15
0x14000bbab  pop     r14
0x14000bbad  pop     r13
0x14000bbaf  pop     r12
0x14000bbb1  pop     rdi
0x14000bbb2  pop     rsi
0x14000bbb3  pop     rbx
0x14000bbb4  retn
0x14000bbb6  mov     dword ptr [rsp+198h+LazyWriteContext], 76h ; 'v'
0x14000bbbe  mov     r9d, 30000h
0x14000bbc4  xor     r8d, r8d
0x14000bbc7  mov     edx, 0C000009Ah
0x14000bbcc  mov     rcx, r14
0x14000bbcf  call    CdRaiseStatusEx
0x14000bbd4  mov     dword ptr [rsp+198h+LazyWriteContext], 0DBh
0x14000bbdc  mov     r9d, 30000h
0x14000bbe2  xor     r8d, r8d
0x14000bbe5  mov     edx, 0C0000102h
0x14000bbea  mov     rcx, r14
0x14000bbed  call    CdRaiseStatusEx
0x14000bbf2  mov     dword ptr [rsp+198h+LazyWriteContext], 0E7h
0x14000bbfa  mov     r9d, 30000h
0x14000bc00  xor     r8d, r8d
0x14000bc03  mov     edx, 0C0000102h
0x14000bc08  mov     rcx, r14
0x14000bc0b  call    CdRaiseStatusEx
  ... truncated ...
```
