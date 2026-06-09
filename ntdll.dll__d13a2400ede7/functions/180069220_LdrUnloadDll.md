# LdrUnloadDll

- ea: `0x180069220`
- end: `0x180069430`
- name: `LdrUnloadDll`
- size: `528`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180018640`
- `0x18001d4b0`
- `0x180050718`
- `0x1800685a0`
- `0x180069100`
- `0x18006a300`
- `0x1800c1c4c`
- `0x18010db20`
- `0x18011fe54`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x1800254d0`
- `0x1800259ec`
- `0x180069220`
- `0x180069438`
- `0x1800694f0`
- `0x180069678`
- `0x180069950`
- `0x18006fb30`
- `0x1800707b0`
- `0x1800709e0`
- `0x1800fbfb0`

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
  RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
  v4 = qword_1801CA470;
  v5 = LdrpModuleBaseAddressIndex;
  if ( (qword_1801CA470 & 1) != 0 )
  {
    if ( !LdrpModuleBaseAddressIndex )
      goto LABEL_18;
    v5 = (unsigned __int64)&LdrpModuleBaseAddressIndex ^ LdrpModuleBaseAddressIndex;
  }
  v4 = qword_1801CA470 & 1;
  if ( !v5 )
    goto LABEL_18;
  while ( a1 > *(_QWORD *)(v5 - 152) )
  {
    v7 = *(_QWORD *)(v5 + 8);
    if ( (qword_1801CA470 & 1) == 0 || !v7 )
      goto LABEL_16;
    v5 ^= v7;
LABEL_17:
    if ( !v5 )
      goto LABEL_18;
  }
  if ( a1 < *(_QWORD *)(v5 - 152) )
  {
    v7 = *(_QWORD *)v5;
    if ( (qword_1801CA470 & 1) != 0 && v7 )
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
  RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v4);
LABEL_19:
  if ( !v3 )
    return 3221225781LL;
  v8 = *(_QWORD *)(v3 + 152);
  v12 = 0;
  if ( *(_DWORD *)(v8 + 24) == 1 )
    goto LABEL_30;
  RtlAcquireSRWLockExclusive(LdrpModuleDatatableLock);
  v9 = *(_QWORD *)(v3 + 152);
  v10 = LdrpDecrementNodeLoadCountLockHeld(v9, 1, &v12);
  RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
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
0x180069220  push    rbx
0x180069222  sub     rsp, 20h
0x180069226  xor     eax, eax
0x180069228  mov     rbx, rcx
0x18006922b  cmp     cs:byte_1801CA908, al
0x180069231  jnz     short loc_180069247
0x180069233  mov     [rsp+28h+arg_0], rsi
0x180069238  test    rcx, rcx
0x18006923b  jnz     short loc_18006924E
0x18006923d  mov     rsi, [rsp+28h+arg_0]
0x180069242  mov     eax, 0C0000135h
0x180069247  add     rsp, 20h
0x18006924b  pop     rbx
0x18006924c  retn
0x18006924e  cmp     rbx, cs:LdrpSystemDllBase
0x180069255  jz      loc_180069386
0x18006925b  lea     rcx, LdrpModuleDatatableLock
0x180069262  xor     esi, esi
0x180069264  call    RtlAcquireSRWLockShared
0x180069269  mov     rdx, cs:qword_1801CA470
0x180069270  mov     rcx, cs:LdrpModuleBaseAddressIndex
0x180069277  test    dl, 1
0x18006927a  jnz     loc_180069407
0x180069280  and     edx, 1
0x180069283  test    rcx, rcx
0x180069286  jz      short loc_1800692E3
0x180069288  nop     dword ptr [rax+rax+00000000h]
0x180069290  cmp     rbx, [rcx-98h]
0x180069297  ja      short loc_1800692BE
0x180069299  jb      short loc_1800692D0
0x18006929b  lea     rsi, [rcx-0C8h]
0x1800692a2  mov     rcx, [rcx-30h]
0x1800692a6  mov     eax, [rcx+18h]
0x1800692a9  cmp     eax, 0FFFFFFFFh
0x1800692ac  jnz     loc_1800693B8
0x1800692b2  mov     rax, [rsi+98h]
0x1800692b9  mov     ecx, [rax+38h]
0x1800692bc  jmp     short loc_1800692E3
0x1800692be  mov     rax, [rcx+8]
0x1800692c2  test    edx, edx
0x1800692c4  jz      short loc_1800692DB
0x1800692c6  test    rax, rax
0x1800692c9  jz      short loc_1800692DB
0x1800692cb  xor     rcx, rax
0x1800692ce  jmp     short loc_1800692DE
0x1800692d0  mov     rax, [rcx]
0x1800692d3  test    edx, edx
0x1800692d5  jnz     loc_180069375
0x1800692db  mov     rcx, rax
0x1800692de  test    rcx, rcx
0x1800692e1  jnz     short loc_180069290
0x1800692e3  lea     rcx, LdrpModuleDatatableLock
0x1800692ea  call    RtlReleaseSRWLockShared
0x1800692ef  test    rsi, rsi
0x1800692f2  jz      loc_18006923D
0x1800692f8  mov     rax, [rsi+98h]
0x1800692ff  mov     [rsp+28h+arg_8], 0
0x180069307  mov     edx, [rax+18h]
0x18006930a  cmp     edx, 1
0x18006930d  jz      loc_1800693D3
0x180069313  lea     rcx, LdrpModuleDatatableLock
0x18006931a  mov     [rsp+28h+arg_10], rdi
0x18006931f  call    RtlAcquireSRWLockExclusive
0x180069324  mov     rdi, [rsi+98h]
0x18006932b  lea     r8, [rsp+28h+arg_8]
0x180069330  mov     rcx, rdi
0x180069333  mov     edx, 1
0x180069338  call    LdrpDecrementNodeLoadCountLockHeld
0x18006933d  lea     rcx, LdrpModuleDatatableLock
0x180069344  mov     ebx, eax
0x180069346  call    RtlReleaseSRWLockExclusive
0x18006934b  cmp     [rsp+28h+arg_8], 0
0x180069350  jnz     short loc_18006939C
0x180069352  mov     rdi, [rsp+28h+arg_10]
0x180069357  cmp     ebx, 0C000022Dh
0x18006935d  jz      short loc_1800693D3
0x18006935f  mov     rcx, rsi
0x180069362  call    LdrpDereferenceModule
0x180069367  mov     rsi, [rsp+28h+arg_0]
0x18006936c  mov     eax, ebx
0x18006936e  add     rsp, 20h
0x180069372  pop     rbx
0x180069373  retn
0x180069375  test    rax, rax
0x180069378  jz      loc_1800692DB
0x18006937e  xor     rcx, rax
0x180069381  jmp     loc_1800692DE
0x180069386  mov     rsi, cs:LdrpNtDllDataTableEntry
0x18006938d  mov     rax, [rsi+98h]
0x180069394  mov     ecx, [rax+38h]
0x180069397  jmp     loc_1800692EF
0x18006939c  call    LdrpAcquireLoaderLock
0x1800693a1  mov     rcx, rdi
0x1800693a4  call    LdrpUnloadNode
0x1800693a9  xor     r8d, r8d
0x1800693ac  mov     edx, 8
0x1800693b1  call    LdrpReleaseLoaderLock
0x1800693b6  jmp     short loc_180069352
0x1800693b8  mov     rax, [rcx]
0x1800693bb  mov     ecx, [rax-38h]
0x1800693be  test    cl, 20h
0x1800693c1  jnz     loc_1800692B2
0x1800693c7  lock inc dword ptr [rsi+114h]
0x1800693ce  jmp     loc_1800692B2
0x1800693d3  mov     rax, gs:30h
0x1800693dc  mov     ecx, 1000h
0x1800693e1  test    [rax+17EEh], cx
0x1800693e8  jnz     short loc_18006941F
0x1800693ea  xor     ecx, ecx
0x1800693ec  call    LdrpDrainWorkQueue
0x1800693f1  xor     edx, edx
0x1800693f3  mov     rcx, rsi
0x1800693f6  call    LdrpDecrementModuleLoadCountEx
0x1800693fb  call    LdrpDropLastInProgressCount
0x180069400  xor     ebx, ebx
0x180069402  jmp     loc_18006935F
0x180069407  test    rcx, rcx
0x18006940a  jz      loc_1800692E3
0x180069410  lea     rax, LdrpModuleBaseAddressIndex
0x180069417  xor     rcx, rax
0x18006941a  jmp     loc_180069280
0x18006941f  xor     edx, edx
0x180069421  mov     rcx, rsi
0x180069424  call    LdrpDecrementModuleLoadCountEx
0x180069429  xor     ebx, ebx
0x18006942b  jmp     loc_18006935F
```
