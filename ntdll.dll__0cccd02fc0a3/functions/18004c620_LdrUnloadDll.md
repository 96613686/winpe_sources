# LdrUnloadDll

- ea: `0x18004c620`
- end: `0x18004c830`
- name: `LdrUnloadDll`
- size: `528`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180018640`
- `0x18001d4b0`
- `0x18004b9a0`
- `0x18004c500`
- `0x18004d920`
- `0x1800bd96c`
- `0x1800d6508`
- `0x18010c7d0`
- `0x18011f364`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x1800254e0`
- `0x1800259fc`
- `0x18004c620`
- `0x18004c838`
- `0x18004c8f0`
- `0x18004ca78`
- `0x18004cd50`
- `0x180053150`
- `0x180053dd0`
- `0x180054000`
- `0x1800fb270`

## pseudocode

```c
__int64 __fastcall LdrUnloadDll(unsigned __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rsi
  __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int v12; // [rsp+38h] [rbp+10h] BYREF

  result = 0;
  if ( byte_1801CA908 )
    return result;
  if ( !a1 )
    return 3221225781LL;
  if ( a1 == LdrpSystemDllBase )
  {
    v3 = LdrpNtDllDataTableEntry;
    goto LABEL_19;
  }
  v3 = 0;
  RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
  v4 = qword_1801CA478;
  v5 = LdrpModuleBaseAddressIndex;
  if ( (qword_1801CA478 & 1) != 0 )
  {
    if ( !LdrpModuleBaseAddressIndex )
      goto LABEL_18;
    v5 = (unsigned __int64)&LdrpModuleBaseAddressIndex ^ LdrpModuleBaseAddressIndex;
  }
  v4 = qword_1801CA478 & 1;
  if ( !v5 )
    goto LABEL_18;
  while ( a1 > *(_QWORD *)(v5 - 152) )
  {
    v7 = *(_QWORD *)(v5 + 8);
    if ( (qword_1801CA478 & 1) == 0 || !v7 )
      goto LABEL_16;
    v5 ^= v7;
LABEL_17:
    if ( !v5 )
      goto LABEL_18;
  }
  if ( a1 < *(_QWORD *)(v5 - 152) )
  {
    v7 = *(_QWORD *)v5;
    if ( (qword_1801CA478 & 1) != 0 && v7 )
    {
      v5 ^= v7;
      goto LABEL_17;
    }
LABEL_16:
    v5 = v7;
    goto LABEL_17;
  }
  v3 = v5 - 200;
  v6 = *(_QWORD *)(v5 - 48);
  if ( *(_DWORD *)(v6 + 24) != -1 && (*(_DWORD *)(*(_QWORD *)v6 - 56LL) & 0x20) == 0 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 276));
LABEL_18:
  RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v4);
LABEL_19:
  if ( !v3 )
    return 3221225781LL;
  v8 = *(_QWORD *)(v3 + 152);
  v12 = 0;
  if ( *(_DWORD *)(v8 + 24) == 1 )
    goto LABEL_30;
  RtlAcquireSRWLockExclusive(&LdrpModuleDatatableLock);
  v9 = *(_QWORD *)(v3 + 152);
  v10 = LdrpDecrementNodeLoadCountLockHeld(v9, 1, &v12);
  RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
  if ( v12 )
  {
    LdrpAcquireLoaderLock();
    LdrpUnloadNode(v9);
    LdrpReleaseLoaderLock(v11, 8, 0);
  }
  if ( v10 == -1073741267 )
  {
LABEL_30:
    if ( (NtCurrentTeb()->SameTebFlags & 0x1000) != 0 )
    {
      LdrpDecrementModuleLoadCountEx(v3, 0);
    }
    else
    {
      LdrpDrainWorkQueue(0);
      LdrpDecrementModuleLoadCountEx(v3, 0);
      LdrpDropLastInProgressCount();
    }
    v10 = 0;
  }
  LdrpDereferenceModule(v3);
  return v10;
}

```

## disassembly

```asm
0x18004c620  push    rbx
0x18004c622  sub     rsp, 20h
0x18004c626  xor     eax, eax
0x18004c628  mov     rbx, rcx
0x18004c62b  cmp     cs:byte_1801CA908, al
0x18004c631  jnz     short loc_18004C647
0x18004c633  mov     [rsp+28h+arg_0], rsi
0x18004c638  test    rcx, rcx
0x18004c63b  jnz     short loc_18004C64E
0x18004c63d  mov     rsi, [rsp+28h+arg_0]
0x18004c642  mov     eax, 0C0000135h
0x18004c647  add     rsp, 20h
0x18004c64b  pop     rbx
0x18004c64c  retn
0x18004c64e  cmp     rbx, cs:LdrpSystemDllBase
0x18004c655  jz      loc_18004C786
0x18004c65b  lea     rcx, LdrpModuleDatatableLock
0x18004c662  xor     esi, esi
0x18004c664  call    RtlAcquireSRWLockShared
0x18004c669  mov     rdx, cs:qword_1801CA478
0x18004c670  mov     rcx, cs:LdrpModuleBaseAddressIndex
0x18004c677  test    dl, 1
0x18004c67a  jnz     loc_18004C807
0x18004c680  and     edx, 1
0x18004c683  test    rcx, rcx
0x18004c686  jz      short loc_18004C6E3
0x18004c688  nop     dword ptr [rax+rax+00000000h]
0x18004c690  cmp     rbx, [rcx-98h]
0x18004c697  ja      short loc_18004C6BE
0x18004c699  jb      short loc_18004C6D0
0x18004c69b  lea     rsi, [rcx-0C8h]
0x18004c6a2  mov     rcx, [rcx-30h]
0x18004c6a6  mov     eax, [rcx+18h]
0x18004c6a9  cmp     eax, 0FFFFFFFFh
0x18004c6ac  jnz     loc_18004C7B8
0x18004c6b2  mov     rax, [rsi+98h]
0x18004c6b9  mov     ecx, [rax+38h]
0x18004c6bc  jmp     short loc_18004C6E3
0x18004c6be  mov     rax, [rcx+8]
0x18004c6c2  test    edx, edx
0x18004c6c4  jz      short loc_18004C6DB
0x18004c6c6  test    rax, rax
0x18004c6c9  jz      short loc_18004C6DB
0x18004c6cb  xor     rcx, rax
0x18004c6ce  jmp     short loc_18004C6DE
0x18004c6d0  mov     rax, [rcx]
0x18004c6d3  test    edx, edx
0x18004c6d5  jnz     loc_18004C775
0x18004c6db  mov     rcx, rax
0x18004c6de  test    rcx, rcx
0x18004c6e1  jnz     short loc_18004C690
0x18004c6e3  lea     rcx, LdrpModuleDatatableLock
0x18004c6ea  call    RtlReleaseSRWLockShared
0x18004c6ef  test    rsi, rsi
0x18004c6f2  jz      loc_18004C63D
0x18004c6f8  mov     rax, [rsi+98h]
0x18004c6ff  mov     [rsp+28h+arg_8], 0
0x18004c707  mov     edx, [rax+18h]
0x18004c70a  cmp     edx, 1
0x18004c70d  jz      loc_18004C7D3
0x18004c713  lea     rcx, LdrpModuleDatatableLock
0x18004c71a  mov     [rsp+28h+arg_10], rdi
0x18004c71f  call    RtlAcquireSRWLockExclusive
0x18004c724  mov     rdi, [rsi+98h]
0x18004c72b  lea     r8, [rsp+28h+arg_8]
0x18004c730  mov     rcx, rdi
0x18004c733  mov     edx, 1
0x18004c738  call    LdrpDecrementNodeLoadCountLockHeld
0x18004c73d  lea     rcx, LdrpModuleDatatableLock
0x18004c744  mov     ebx, eax
0x18004c746  call    RtlReleaseSRWLockExclusive
0x18004c74b  cmp     [rsp+28h+arg_8], 0
0x18004c750  jnz     short loc_18004C79C
0x18004c752  mov     rdi, [rsp+28h+arg_10]
0x18004c757  cmp     ebx, 0C000022Dh
0x18004c75d  jz      short loc_18004C7D3
0x18004c75f  mov     rcx, rsi
0x18004c762  call    LdrpDereferenceModule
0x18004c767  mov     rsi, [rsp+28h+arg_0]
0x18004c76c  mov     eax, ebx
0x18004c76e  add     rsp, 20h
0x18004c772  pop     rbx
0x18004c773  retn
0x18004c775  test    rax, rax
0x18004c778  jz      loc_18004C6DB
0x18004c77e  xor     rcx, rax
0x18004c781  jmp     loc_18004C6DE
0x18004c786  mov     rsi, cs:LdrpNtDllDataTableEntry
0x18004c78d  mov     rax, [rsi+98h]
0x18004c794  mov     ecx, [rax+38h]
0x18004c797  jmp     loc_18004C6EF
0x18004c79c  call    LdrpAcquireLoaderLock
0x18004c7a1  mov     rcx, rdi
0x18004c7a4  call    LdrpUnloadNode
0x18004c7a9  xor     r8d, r8d
0x18004c7ac  mov     edx, 8
0x18004c7b1  call    LdrpReleaseLoaderLock
0x18004c7b6  jmp     short loc_18004C752
0x18004c7b8  mov     rax, [rcx]
0x18004c7bb  mov     ecx, [rax-38h]
0x18004c7be  test    cl, 20h
0x18004c7c1  jnz     loc_18004C6B2
0x18004c7c7  lock inc dword ptr [rsi+114h]
0x18004c7ce  jmp     loc_18004C6B2
0x18004c7d3  mov     rax, gs:30h
0x18004c7dc  mov     ecx, 1000h
0x18004c7e1  test    [rax+17EEh], cx
0x18004c7e8  jnz     short loc_18004C81F
0x18004c7ea  xor     ecx, ecx
0x18004c7ec  call    LdrpDrainWorkQueue
0x18004c7f1  xor     edx, edx
0x18004c7f3  mov     rcx, rsi
0x18004c7f6  call    LdrpDecrementModuleLoadCountEx
0x18004c7fb  call    LdrpDropLastInProgressCount
0x18004c800  xor     ebx, ebx
0x18004c802  jmp     loc_18004C75F
0x18004c807  test    rcx, rcx
0x18004c80a  jz      loc_18004C6E3
0x18004c810  lea     rax, LdrpModuleBaseAddressIndex
0x18004c817  xor     rcx, rax
0x18004c81a  jmp     loc_18004C680
0x18004c81f  xor     edx, edx
0x18004c821  mov     rcx, rsi
0x18004c824  call    LdrpDecrementModuleLoadCountEx
0x18004c829  xor     ebx, ebx
0x18004c82b  jmp     loc_18004C75F
```
