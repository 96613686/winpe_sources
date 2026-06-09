# LdrpUnloadNode

- ea: `0x180069678`
- end: `0x180069947`
- name: `LdrpUnloadNode`
- size: `719`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x180069220`
- `0x180069678`
- `0x1800fbfb0`

## callees

- `0x180003130`
- `0x180017e90`
- `0x1800183a0`
- `0x18001861c`
- `0x18001eb80`
- `0x180031710`
- `0x180069438`
- `0x180069678`
- `0x18006ffa0`
- `0x180070490`
- `0x1800709e0`
- `0x180073360`
- `0x1800ced58`
- `0x1800dc240`
- `0x1800fe04c`
- `0x18010a0e0`
- `0x1801137b4`
- `0x18016f020`

## string_xrefs

- `0x180069834`: `Unmapping DLL "%wZ"\n`

## pseudocode

```c
__int64 __fastcall LdrpUnloadNode(__int64 a1)
{
  struct _PEB *v1; // rbp
  __int64 result; // rax
  void (__fastcall *v4)(_QWORD *); // rsi
  _QWORD *i; // r14
  __int64 **v6; // rcx
  __int64 *v7; // rdi
  __int64 v8; // rsi
  _QWORD *v9; // rdx
  _QWORD **v10; // rcx
  _QWORD *v11; // r8
  _QWORD **v12; // rax
  _QWORD *v13; // rdi
  _QWORD *v14; // rsi
  int v15; // eax
  _QWORD *v16; // rdi
  __int64 v17; // rdx
  int v18; // [rsp+50h] [rbp+8h] BYREF

  v1 = NtCurrentPeb();
  result = *(unsigned int *)(a1 + 56);
  v18 = 0;
  if ( (_DWORD)result != 7 )
  {
    if ( (_DWORD)result != -4 && (_DWORD)result != 9 )
      goto LABEL_7;
    *(_DWORD *)(a1 + 56) = -1;
    LdrpProcessDetachNode();
  }
  v4 = 0;
  if ( g_ShimsEnabled )
    v4 = (void (__fastcall *)(_QWORD *))(__ROR8__(g_pfnSE_LdrEntryRemoved, 64 - (MEMORY[0x7FFE0330] & 0x3Fu))
                                       ^ MEMORY[0x7FFE0330]);
  RtlEnterCriticalSection(&LdrpDllNotificationLock);
  for ( i = *(_QWORD **)a1; i != (_QWORD *)a1; i = (_QWORD *)*i )
  {
    if ( (*(_DWORD *)(i - 7) & 8) != 0 )
    {
      LdrpSendDllNotifications(i - 20, 2);
      if ( v4 )
        v4(i - 20);
      SbUpdateSwitchContextBasedOnDll(i - 20, v17, 1);
      if ( (v1->NtGlobalFlag & 0x100) != 0 )
        AVrfDllUnloadNotification((__int64)(i - 20));
    }
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrsnap.c",
      4111,
      (int)"LdrpUnloadNode",
      2,
      "Unmapping DLL \"%wZ\"\n",
      (_BYTE)i - 88);
    LdrUnloadAlternateResourceModuleEx(*(i - 14), 0);
  }
  result = RtlLeaveCriticalSection(&LdrpDllNotificationLock);
LABEL_7:
  while ( 1 )
  {
    v6 = *(__int64 ***)(a1 + 40);
    if ( !v6 )
      break;
    v7 = *v6;
    if ( *v6 == (__int64 *)v6 )
    {
      *(_QWORD *)(a1 + 40) = 0;
    }
    else
    {
      result = *v7;
      *v6 = (__int64 *)*v7;
    }
    if ( !v7 )
      break;
    RtlAcquireSRWLockExclusive(LdrpModuleDatatableLock);
    v8 = v7[1];
    v9 = v7 + 2;
    v10 = *(_QWORD ***)(v8 + 48);
    v11 = *v10;
    if ( *v10 != v7 + 2 )
    {
      do
      {
        v10 = (_QWORD **)v11;
        v11 = (_QWORD *)*v11;
      }
      while ( v11 != v9 );
    }
    *v10 = (_QWORD *)*v9;
    if ( *(_QWORD **)(v8 + 48) == v9 )
    {
      v12 = 0;
      if ( v10 != v9 )
        v12 = v10;
      *(_QWORD *)(v8 + 48) = v12;
    }
    LdrpDecrementNodeLoadCountLockHeld(v8, 0, &v18);
    RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
    if ( v18 )
      LdrpUnloadNode(v8);
    result = RtlFreeHeap_0(LdrpHeap, 0, v7);
  }
  *(_DWORD *)(a1 + 56) = -2;
  v13 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 != a1 )
  {
    do
    {
      v14 = (_QWORD *)*v13;
      v15 = *((_DWORD *)v13 - 14);
      v16 = v13 - 20;
      *((_DWORD *)v16 + 26) = v15 | 2;
      RtlAcquireSRWLockExclusive(LdrpModuleDatatableLock);
      LdrpRemoveDataTableEntry(v16);
      if ( (*((_DWORD *)v16 + 26) & 0x80u) != 0 )
      {
        RtlRbRemoveNode(&LdrpMappingInfoIndex, v16 + 28);
        RtlRbRemoveNode(&LdrpModuleBaseAddressIndex, v16 + 25);
        *((_DWORD *)v16 + 16) = 0;
      }
      RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
      if ( LdrpIsSecureProcess )
        LdrpUnmapModule(v16);
      result = LdrpDereferenceModule(v16);
      v13 = v14;
    }
    while ( v14 != (_QWORD *)a1 );
  }
  return result;
}

```

## disassembly

```asm
0x180069678  mov     [rsp+arg_8], rbx
0x18006967d  mov     [rsp+arg_10], rbp
0x180069682  push    rsi
0x180069683  push    rdi
0x180069684  push    r14
0x180069686  sub     rsp, 30h
0x18006968a  mov     rbp, gs:60h
0x180069693  mov     rbx, rcx
0x180069696  mov     eax, [rcx+38h]
0x180069699  mov     [rsp+48h+arg_0], 0
0x1800696a1  cmp     eax, 7
0x1800696a4  jnz     loc_180069864
0x1800696aa  xor     esi, esi
0x1800696ac  cmp     cs:g_ShimsEnabled, sil
0x1800696b3  jnz     loc_180069908
0x1800696b9  lea     rcx, LdrpDllNotificationLock
0x1800696c0  call    RtlEnterCriticalSection
0x1800696c5  mov     r14, [rbx]
0x1800696c8  cmp     r14, rbx
0x1800696cb  jnz     loc_18006980C
0x1800696d1  lea     rcx, LdrpDllNotificationLock
0x1800696d8  call    RtlLeaveCriticalSection
0x1800696dd  lea     rbp, LdrpModuleDatatableLock
0x1800696e4  mov     rcx, [rbx+28h]
0x1800696e8  test    rcx, rcx
0x1800696eb  jz      loc_180069794
0x1800696f1  mov     rdi, [rcx]
0x1800696f4  cmp     rdi, rcx
0x1800696f7  jz      loc_180069787
0x1800696fd  mov     rax, [rdi]
0x180069700  mov     [rcx], rax
0x180069703  test    rdi, rdi
0x180069706  jz      loc_180069794
0x18006970c  mov     rcx, rbp
0x18006970f  call    RtlAcquireSRWLockExclusive
0x180069714  mov     rsi, [rdi+8]
0x180069718  lea     rdx, [rdi+10h]
0x18006971c  mov     rcx, [rsi+30h]
0x180069720  mov     r8, [rcx]
0x180069723  cmp     r8, rdx
0x180069726  jz      short loc_180069736
0x180069728  mov     rax, [r8]
0x18006972b  mov     rcx, r8
0x18006972e  mov     r8, rax
0x180069731  cmp     rax, rdx
0x180069734  jnz     short loc_180069728
0x180069736  mov     rax, [rdx]
0x180069739  mov     [rcx], rax
0x18006973c  cmp     [rsi+30h], rdx
0x180069740  jnz     short loc_18006974F
0x180069742  xor     eax, eax
0x180069744  cmp     rcx, rdx
0x180069747  cmovnz  rax, rcx
0x18006974b  mov     [rsi+30h], rax
0x18006974f  lea     r8, [rsp+48h+arg_0]
0x180069754  xor     edx, edx
0x180069756  mov     rcx, rsi
0x180069759  call    LdrpDecrementNodeLoadCountLockHeld
0x18006975e  mov     rcx, rbp
0x180069761  call    RtlReleaseSRWLockExclusive
0x180069766  cmp     [rsp+48h+arg_0], 0
0x18006976b  jnz     loc_1800698ED
0x180069771  mov     rcx, cs:LdrpHeap
0x180069778  mov     r8, rdi
0x18006977b  xor     edx, edx
0x18006977d  call    RtlFreeHeap_0
0x180069782  jmp     loc_1800696E4
0x180069787  mov     qword ptr [rbx+28h], 0
0x18006978f  jmp     loc_180069703
0x180069794  mov     dword ptr [rbx+38h], 0FFFFFFFEh
0x18006979b  mov     rdi, [rbx]
0x18006979e  cmp     rdi, rbx
0x1800697a1  jz      short loc_1800697F8
0x1800697a3  mov     rsi, [rdi]
0x1800697a6  mov     rcx, rbp
0x1800697a9  mov     eax, [rdi-38h]
0x1800697ac  add     rdi, 0FFFFFFFFFFFFFF60h
0x1800697b3  or      eax, 2
0x1800697b6  mov     [rdi+68h], eax
0x1800697b9  call    RtlAcquireSRWLockExclusive
0x1800697be  mov     rcx, rdi
0x1800697c1  call    LdrpRemoveDataTableEntry
0x1800697c6  mov     r9d, [rdi+68h]
0x1800697ca  test    r9b, r9b
0x1800697cd  js      loc_18006987E
0x1800697d3  mov     rcx, rbp
0x1800697d6  call    RtlReleaseSRWLockExclusive
0x1800697db  cmp     cs:LdrpIsSecureProcess, 0
0x1800697e2  jnz     loc_18006993A
0x1800697e8  mov     rcx, rdi
0x1800697eb  call    LdrpDereferenceModule
0x1800697f0  mov     rdi, rsi
0x1800697f3  cmp     rsi, rbx
0x1800697f6  jnz     short loc_1800697A3
0x1800697f8  mov     rbx, [rsp+48h+arg_8]
0x1800697fd  mov     rbp, [rsp+48h+arg_10]
0x180069802  add     rsp, 30h
0x180069806  pop     r14
0x180069808  pop     rdi
0x180069809  pop     rsi
0x18006980a  retn
0x18006980c  lea     rdi, [r14-0A0h]
0x180069813  mov     eax, [rdi+68h]
0x180069816  test    al, 8
0x180069818  jnz     loc_1800698B0
0x18006981e  lea     rax, [rdi+48h]
0x180069822  mov     r9d, 2; int
0x180069828  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x18006982d  lea     r8, aLdrpunloadnode; "LdrpUnloadNode"
0x180069834  lea     rax, aUnmappingDllWz; "Unmapping DLL \"%wZ\"\n"
0x18006983b  mov     edx, 100Fh; int
0x180069840  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x180069847  mov     [rsp+48h+Format], rax; Format
0x18006984c  call    LdrpLogInternal
0x180069851  mov     rcx, [rdi+30h]
0x180069855  xor     edx, edx
0x180069857  call    LdrUnloadAlternateResourceModuleEx
0x18006985c  mov     r14, [r14]
0x18006985f  jmp     loc_1800696C8
0x180069864  cmp     eax, 0FFFFFFFCh
0x180069867  jnz     loc_1800698FA
0x18006986d  mov     dword ptr [rcx+38h], 0FFFFFFFFh
0x180069874  call    LdrpProcessDetachNode
0x180069879  jmp     loc_1800696AA
0x18006987e  lea     rdx, [rdi+0E0h]
0x180069885  lea     rcx, LdrpMappingInfoIndex
0x18006988c  call    RtlRbRemoveNode
0x180069891  lea     rdx, [rdi+0C8h]
0x180069898  lea     rcx, LdrpModuleBaseAddressIndex
0x18006989f  call    RtlRbRemoveNode
0x1800698a4  mov     dword ptr [rdi+40h], 0
0x1800698ab  jmp     loc_1800697D3
0x1800698b0  mov     edx, 2
0x1800698b5  mov     rcx, rdi
0x1800698b8  call    LdrpSendDllNotifications
0x1800698bd  test    rsi, rsi
0x1800698c0  jnz     short loc_18006992D
0x1800698c2  mov     r8d, 1
0x1800698c8  mov     rcx, rdi
0x1800698cb  call    SbUpdateSwitchContextBasedOnDll
0x1800698d0  test    dword ptr [rbp+0BCh], 100h
0x1800698da  jz      loc_18006981E
0x1800698e0  mov     rcx, rdi
0x1800698e3  call    AVrfDllUnloadNotification
0x1800698e8  jmp     loc_18006981E
0x1800698ed  mov     rcx, rsi
0x1800698f0  call    LdrpUnloadNode
0x1800698f5  jmp     loc_180069771
0x1800698fa  cmp     eax, 9
0x1800698fd  jnz     loc_1800696DD
0x180069903  jmp     loc_18006986D
0x180069908  mov     esi, ds:7FFE0330h
0x18006990f  mov     ecx, 40h ; '@'
0x180069914  mov     eax, esi
0x180069916  and     eax, 3Fh
0x180069919  sub     ecx, eax
0x18006991b  mov     rax, cs:g_pfnSE_LdrEntryRemoved
0x180069922  ror     rax, cl
0x180069925  xor     rsi, rax
0x180069928  jmp     loc_1800696B9
0x18006992d  mov     rcx, rdi
0x180069930  mov     rax, rsi
0x180069933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069938  jmp     short loc_1800698C2
0x18006993a  mov     rcx, rdi
0x18006993d  call    LdrpUnmapModule
0x180069942  jmp     loc_1800697E8
```
