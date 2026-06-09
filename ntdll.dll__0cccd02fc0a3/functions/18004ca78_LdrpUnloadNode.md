# LdrpUnloadNode

- ea: `0x18004ca78`
- end: `0x18004cd47`
- name: `LdrpUnloadNode`
- size: `719`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x18004c620`
- `0x18004ca78`
- `0x1800fb270`

## callees

- `0x180003130`
- `0x180017e90`
- `0x1800183a0`
- `0x18001861c`
- `0x18001eb80`
- `0x180032410`
- `0x18004c838`
- `0x18004ca78`
- `0x1800535c0`
- `0x180053ab0`
- `0x180054000`
- `0x180056980`
- `0x1800cd1c8`
- `0x1800db7c0`
- `0x1800fda2c`
- `0x180109150`
- `0x1801123c4`
- `0x18016f020`

## string_xrefs

- `0x18004cc34`: `Unmapping DLL "%wZ"\n`

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
    RtlAcquireSRWLockExclusive(&LdrpModuleDatatableLock);
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
    RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
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
      RtlAcquireSRWLockExclusive(&LdrpModuleDatatableLock);
      LdrpRemoveDataTableEntry(v16);
      if ( (*((_DWORD *)v16 + 26) & 0x80u) != 0 )
      {
        RtlRbRemoveNode(&LdrpMappingInfoIndex, v16 + 28);
        RtlRbRemoveNode(&LdrpModuleBaseAddressIndex, v16 + 25);
        *((_DWORD *)v16 + 16) = 0;
      }
      RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
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
0x18004ca78  mov     [rsp+arg_8], rbx
0x18004ca7d  mov     [rsp+arg_10], rbp
0x18004ca82  push    rsi
0x18004ca83  push    rdi
0x18004ca84  push    r14
0x18004ca86  sub     rsp, 30h
0x18004ca8a  mov     rbp, gs:60h
0x18004ca93  mov     rbx, rcx
0x18004ca96  mov     eax, [rcx+38h]
0x18004ca99  mov     [rsp+48h+arg_0], 0
0x18004caa1  cmp     eax, 7
0x18004caa4  jnz     loc_18004CC64
0x18004caaa  xor     esi, esi
0x18004caac  cmp     cs:g_ShimsEnabled, sil
0x18004cab3  jnz     loc_18004CD08
0x18004cab9  lea     rcx, LdrpDllNotificationLock
0x18004cac0  call    RtlEnterCriticalSection
0x18004cac5  mov     r14, [rbx]
0x18004cac8  cmp     r14, rbx
0x18004cacb  jnz     loc_18004CC0C
0x18004cad1  lea     rcx, LdrpDllNotificationLock
0x18004cad8  call    RtlLeaveCriticalSection
0x18004cadd  lea     rbp, LdrpModuleDatatableLock
0x18004cae4  mov     rcx, [rbx+28h]
0x18004cae8  test    rcx, rcx
0x18004caeb  jz      loc_18004CB94
0x18004caf1  mov     rdi, [rcx]
0x18004caf4  cmp     rdi, rcx
0x18004caf7  jz      loc_18004CB87
0x18004cafd  mov     rax, [rdi]
0x18004cb00  mov     [rcx], rax
0x18004cb03  test    rdi, rdi
0x18004cb06  jz      loc_18004CB94
0x18004cb0c  mov     rcx, rbp
0x18004cb0f  call    RtlAcquireSRWLockExclusive
0x18004cb14  mov     rsi, [rdi+8]
0x18004cb18  lea     rdx, [rdi+10h]
0x18004cb1c  mov     rcx, [rsi+30h]
0x18004cb20  mov     r8, [rcx]
0x18004cb23  cmp     r8, rdx
0x18004cb26  jz      short loc_18004CB36
0x18004cb28  mov     rax, [r8]
0x18004cb2b  mov     rcx, r8
0x18004cb2e  mov     r8, rax
0x18004cb31  cmp     rax, rdx
0x18004cb34  jnz     short loc_18004CB28
0x18004cb36  mov     rax, [rdx]
0x18004cb39  mov     [rcx], rax
0x18004cb3c  cmp     [rsi+30h], rdx
0x18004cb40  jnz     short loc_18004CB4F
0x18004cb42  xor     eax, eax
0x18004cb44  cmp     rcx, rdx
0x18004cb47  cmovnz  rax, rcx
0x18004cb4b  mov     [rsi+30h], rax
0x18004cb4f  lea     r8, [rsp+48h+arg_0]
0x18004cb54  xor     edx, edx
0x18004cb56  mov     rcx, rsi
0x18004cb59  call    LdrpDecrementNodeLoadCountLockHeld
0x18004cb5e  mov     rcx, rbp
0x18004cb61  call    RtlReleaseSRWLockExclusive
0x18004cb66  cmp     [rsp+48h+arg_0], 0
0x18004cb6b  jnz     loc_18004CCED
0x18004cb71  mov     rcx, cs:LdrpHeap
0x18004cb78  mov     r8, rdi
0x18004cb7b  xor     edx, edx
0x18004cb7d  call    RtlFreeHeap_0
0x18004cb82  jmp     loc_18004CAE4
0x18004cb87  mov     qword ptr [rbx+28h], 0
0x18004cb8f  jmp     loc_18004CB03
0x18004cb94  mov     dword ptr [rbx+38h], 0FFFFFFFEh
0x18004cb9b  mov     rdi, [rbx]
0x18004cb9e  cmp     rdi, rbx
0x18004cba1  jz      short loc_18004CBF8
0x18004cba3  mov     rsi, [rdi]
0x18004cba6  mov     rcx, rbp
0x18004cba9  mov     eax, [rdi-38h]
0x18004cbac  add     rdi, 0FFFFFFFFFFFFFF60h
0x18004cbb3  or      eax, 2
0x18004cbb6  mov     [rdi+68h], eax
0x18004cbb9  call    RtlAcquireSRWLockExclusive
0x18004cbbe  mov     rcx, rdi
0x18004cbc1  call    LdrpRemoveDataTableEntry
0x18004cbc6  mov     r9d, [rdi+68h]
0x18004cbca  test    r9b, r9b
0x18004cbcd  js      loc_18004CC7E
0x18004cbd3  mov     rcx, rbp
0x18004cbd6  call    RtlReleaseSRWLockExclusive
0x18004cbdb  cmp     cs:LdrpIsSecureProcess, 0
0x18004cbe2  jnz     loc_18004CD3A
0x18004cbe8  mov     rcx, rdi
0x18004cbeb  call    LdrpDereferenceModule
0x18004cbf0  mov     rdi, rsi
0x18004cbf3  cmp     rsi, rbx
0x18004cbf6  jnz     short loc_18004CBA3
0x18004cbf8  mov     rbx, [rsp+48h+arg_8]
0x18004cbfd  mov     rbp, [rsp+48h+arg_10]
0x18004cc02  add     rsp, 30h
0x18004cc06  pop     r14
0x18004cc08  pop     rdi
0x18004cc09  pop     rsi
0x18004cc0a  retn
0x18004cc0c  lea     rdi, [r14-0A0h]
0x18004cc13  mov     eax, [rdi+68h]
0x18004cc16  test    al, 8
0x18004cc18  jnz     loc_18004CCB0
0x18004cc1e  lea     rax, [rdi+48h]
0x18004cc22  mov     r9d, 2; int
0x18004cc28  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x18004cc2d  lea     r8, aLdrpunloadnode; "LdrpUnloadNode"
0x18004cc34  lea     rax, aUnmappingDllWz; "Unmapping DLL \"%wZ\"\n"
0x18004cc3b  mov     edx, 100Fh; int
0x18004cc40  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x18004cc47  mov     [rsp+48h+Format], rax; Format
0x18004cc4c  call    LdrpLogInternal
0x18004cc51  mov     rcx, [rdi+30h]
0x18004cc55  xor     edx, edx
0x18004cc57  call    LdrUnloadAlternateResourceModuleEx
0x18004cc5c  mov     r14, [r14]
0x18004cc5f  jmp     loc_18004CAC8
0x18004cc64  cmp     eax, 0FFFFFFFCh
0x18004cc67  jnz     loc_18004CCFA
0x18004cc6d  mov     dword ptr [rcx+38h], 0FFFFFFFFh
0x18004cc74  call    LdrpProcessDetachNode
0x18004cc79  jmp     loc_18004CAAA
0x18004cc7e  lea     rdx, [rdi+0E0h]
0x18004cc85  lea     rcx, LdrpMappingInfoIndex
0x18004cc8c  call    RtlRbRemoveNode
0x18004cc91  lea     rdx, [rdi+0C8h]
0x18004cc98  lea     rcx, LdrpModuleBaseAddressIndex
0x18004cc9f  call    RtlRbRemoveNode
0x18004cca4  mov     dword ptr [rdi+40h], 0
0x18004ccab  jmp     loc_18004CBD3
0x18004ccb0  mov     edx, 2
0x18004ccb5  mov     rcx, rdi
0x18004ccb8  call    LdrpSendDllNotifications
0x18004ccbd  test    rsi, rsi
0x18004ccc0  jnz     short loc_18004CD2D
0x18004ccc2  mov     r8d, 1
0x18004ccc8  mov     rcx, rdi
0x18004cccb  call    SbUpdateSwitchContextBasedOnDll
0x18004ccd0  test    dword ptr [rbp+0BCh], 100h
0x18004ccda  jz      loc_18004CC1E
0x18004cce0  mov     rcx, rdi
0x18004cce3  call    AVrfDllUnloadNotification
0x18004cce8  jmp     loc_18004CC1E
0x18004cced  mov     rcx, rsi
0x18004ccf0  call    LdrpUnloadNode
0x18004ccf5  jmp     loc_18004CB71
0x18004ccfa  cmp     eax, 9
0x18004ccfd  jnz     loc_18004CADD
0x18004cd03  jmp     loc_18004CC6D
0x18004cd08  mov     esi, ds:7FFE0330h
0x18004cd0f  mov     ecx, 40h ; '@'
0x18004cd14  mov     eax, esi
0x18004cd16  and     eax, 3Fh
0x18004cd19  sub     ecx, eax
0x18004cd1b  mov     rax, cs:g_pfnSE_LdrEntryRemoved
0x18004cd22  ror     rax, cl
0x18004cd25  xor     rsi, rax
0x18004cd28  jmp     loc_18004CAB9
0x18004cd2d  mov     rcx, rdi
0x18004cd30  mov     rax, rsi
0x18004cd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd38  jmp     short loc_18004CCC2
0x18004cd3a  mov     rcx, rdi
0x18004cd3d  call    LdrpUnmapModule
0x18004cd42  jmp     loc_18004CBE8
```
