# RegCreateKeyExInternalW

- ea: `0x18005d410`
- end: `0x18005da50`
- name: `RegCreateKeyExInternalW`
- size: `1600`
- prototype: ``
- caller_count: `22`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ecb4`
- `0x18005c090`
- `0x18006b4a8`
- `0x1800a04b0`
- `0x1800a0f1c`
- `0x1800a1c08`
- `0x1800a4384`
- `0x1800a5620`
- `0x1800a6540`
- `0x1800a7ad0`
- `0x1800a85ec`
- `0x1800ad900`
- `0x1800ae0a0`
- `0x1801081a0`
- `0x180114f10`
- `0x18012ad40`
- `0x180133504`
- `0x18013cf50`
- `0x18014c5f0`
- `0x18014c974`
- `0x18014dc2c`
- `0x1801773b4`

## callees

- `0x18002e0c4`
- `0x18005cc70`
- `0x18005d410`
- `0x18005e040`
- `0x18005e7e0`
- `0x180060124`
- `0x180136e28`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18005d603`
- `ntdll!RtlEnterCriticalSection` at `0x18005d603`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d639`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d639`
- `ntdll!RtlNtStatusToDosError` at `0x18005d82d`
- `ntdll!RtlNtStatusToDosError` at `0x18005d901`
- `ntdll!RtlNtStatusToDosError` at `0x18005da3c`
- `ntdll!RtlNtStatusToDosError` at `0x18005d82d`
- `ntdll!RtlNtStatusToDosError` at `0x18005d901`
- `ntdll!RtlNtStatusToDosError` at `0x18005da3c`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005d5eb`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005d5eb`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005d4c6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005d877`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005d4c6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005d877`
- `ntdll!NtClose` at `0x18005d64a`
- `ntdll!NtClose` at `0x18005d64a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005d6d3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005d6d3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005d70a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005d70a`
- `ntdll!RtlValidSecurityDescriptor` at `0x18005d79b`
- `ntdll!RtlValidSecurityDescriptor` at `0x18005d79b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18005d7b2`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18005d7b2`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18005d81f`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18005d81f`
- `ntdll!RtlFreeHeap` at `0x18005d587`
- `ntdll!RtlFreeHeap` at `0x18005d6bb`
- `ntdll!RtlFreeHeap` at `0x18005d739`
- `ntdll!RtlFreeHeap` at `0x18005d587`
- `ntdll!RtlFreeHeap` at `0x18005d6bb`
- `ntdll!RtlFreeHeap` at `0x18005d739`
- `ntdll!RtlAllocateHeap` at `0x18005d7e4`
- `ntdll!RtlAllocateHeap` at `0x18005d7e4`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005d9f9`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005d9f9`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005d8b0`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005d8b0`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x18005d983`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x18005d983`

## pseudocode

```c
__int64 __fastcall RegCreateKeyExInternalW(
        void *a1,
        const WCHAR *a2,
        int a3,
        const WCHAR *a4,
        ULONG a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  HKEY *v12; // rsi
  HANDLE *v13; // r14
  ULONG v14; // r12d
  int inited; // eax
  __int64 v16; // rbx
  PVOID *v17; // rbx
  unsigned __int64 v18; // rdi
  HANDLE v19; // rcx
  __int64 v20; // r15
  HANDLE v21; // r14
  _QWORD *v22; // rcx
  _QWORD *v23; // rdi
  _QWORD *i; // rbx
  int v25; // eax
  _QWORD *v27; // rax
  __int64 v28; // r8
  _QWORD *v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  __int64 v34; // rax
  void *v35; // rdi
  ULONG v36; // r15d
  PVOID Heap; // rax
  NTSTATUS SelfRelativeSD; // eax
  unsigned __int64 v39; // rdi
  bool v40; // dl
  unsigned int v41; // ecx
  __int64 v42; // rax
  __int64 v43; // r9
  int v44; // [rsp+30h] [rbp-B8h]
  HANDLE Handle; // [rsp+58h] [rbp-90h] BYREF
  void *v46; // [rsp+60h] [rbp-88h] BYREF
  __int64 v47; // [rsp+68h] [rbp-80h] BYREF
  struct _UNICODE_STRING v48; // [rsp+70h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-68h] BYREF
  _QWORD v50[11]; // [rsp+90h] [rbp-58h] BYREF
  HANDLE KeyHandle; // [rsp+F0h] [rbp+8h] BYREF

  KeyHandle = a1;
  DestinationString = 0;
  v48 = 0;
  memset(v50, 0, 28);
  v12 = 0;
  v46 = 0;
  v47 = 0;
  if ( a1 == (void *)-2147483644LL || a1 == (void *)-2147483568LL || a1 == (void *)-2147483552LL )
    return 6;
  if ( a3 )
    return 87;
  if ( !a2 )
    return 1010;
  v13 = (HANDLE *)a8;
  if ( !a8 )
    return 1010;
  v14 = MapPredefinedHandleInternal(a1, &KeyHandle, &v46, &v47);
  if ( v14 )
    goto LABEL_17;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  if ( inited < 0 )
    goto LABEL_82;
  DestinationString.Length += 2;
  if ( !a4 )
  {
    *(_DWORD *)&v48.Length = 0;
    v48.Buffer = 0;
    goto LABEL_11;
  }
  inited = RtlInitUnicodeStringEx(&v48, a4);
  if ( inited < 0 )
  {
LABEL_82:
    v14 = RtlNtStatusToDosError(inited);
    goto LABEL_17;
  }
  v48.Length += 2;
LABEL_11:
  v16 = a7;
  if ( !a7 )
  {
    v17 = 0;
LABEL_13:
    Handle = v17;
    v18 = (unsigned __int64)KeyHandle;
    if ( ((unsigned __int8)KeyHandle & 1) != 0 )
    {
      if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
      {
        LODWORD(KeyHandle) = 0;
        v39 = v18 & 0xFFFFFFFFFFFFFFFEuLL;
        v40 = (unsigned __int8)IsBaseRegCloseKeyPresent()
           && !(unsigned int)BaseRegGetVersion(v39, &KeyHandle)
           && (_DWORD)KeyHandle == 6;
        v41 = a6 & 0xFFFFFCFF;
        if ( v40 )
          v41 = a6;
        v14 = BaseRegCreateKey(v39, &DestinationString, &v48, a5, v41, v17, v13, a9);
        if ( !v14 )
          *v13 = (HANDLE)((unsigned __int64)*v13 | 1);
      }
    }
    else
    {
      v14 = BaseRegCreateKeyInternal(
              KeyHandle,
              &DestinationString,
              &v48,
              a5,
              a6,
              (__int64)v17,
              v44,
              v13,
              (_DWORD *)a9,
              (void *)a10);
    }
    if ( v17 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17[1]);
    goto LABEL_17;
  }
  v50[1] = 0;
  v35 = *(void **)(a7 + 8);
  if ( !v35 )
  {
    v50[2] = 0;
    v14 = 0;
LABEL_56:
    LODWORD(v50[0]) = *(_DWORD *)v16;
    LOBYTE(v50[3]) = *(_BYTE *)(v16 + 16);
    v17 = (PVOID *)v50;
    goto LABEL_13;
  }
  if ( RtlValidSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a7 + 8)) )
  {
    v36 = RtlLengthSecurityDescriptor(v35);
    Heap = (PVOID)v50[1];
    if ( v50[1] )
    {
      if ( LODWORD(v50[2]) >= v36 )
        goto LABEL_54;
      v14 = 14;
    }
    else
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v36);
      v50[1] = Heap;
      if ( Heap )
      {
        LODWORD(v50[2]) = v36;
LABEL_54:
        HIDWORD(v50[2]) = v36;
        SelfRelativeSD = RtlMakeSelfRelativeSD(v35, Heap, (PULONG)&v50[2]);
        v14 = RtlNtStatusToDosError(SelfRelativeSD);
        goto LABEL_55;
      }
      v14 = 14;
    }
  }
  else
  {
    v14 = 87;
  }
LABEL_55:
  if ( !v14 )
    goto LABEL_56;
LABEL_17:
  v19 = v46;
  Handle = v46;
  v20 = v47;
  if ( v46 )
  {
    if ( v46 == (void *)-2147483644LL || v46 == (void *)-2147483568LL || v46 == (void *)-2147483552LL )
    {
      if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
        PerfRegCloseKey(&Handle);
    }
    else
    {
      if ( ((unsigned __int8)v46 & 2) != 0 )
      {
        RtlRunOnceExecuteOnce(&gClassesEnumTableInit, ClassesEnumTableInitFn, 0, 0);
        v21 = Handle;
        RtlEnterCriticalSection(&CriticalSection);
        v22 = (_QWORD *)qword_1803A7248;
        if ( qword_1803A7248 )
        {
          do
          {
            v23 = (_QWORD *)*v22;
            for ( i = (_QWORD *)v22[3]; i; i = (_QWORD *)*i )
            {
              if ( v21 == (HANDLE)i[2] )
              {
                if ( i != (_QWORD *)v22[3] )
                {
                  v32 = (_QWORD *)i[1];
                  v33 = (_QWORD *)*i;
                  if ( v32 )
                    *v32 = v33;
                  if ( v33 )
                    v33[1] = v32;
                  v34 = v22[3];
                  if ( v34 )
                  {
                    *i = v34;
                    *(_QWORD *)(v22[3] + 8LL) = i;
                  }
                  v22[3] = i;
                  i[1] = 0;
                }
                v27 = (_QWORD *)*i;
                v22[3] = *i;
                if ( v27 )
                  v27[1] = 0;
                EnumStateClear(i);
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, i);
                break;
              }
            }
            v22 = v23;
          }
          while ( v23 );
        }
        RtlLeaveCriticalSection(&CriticalSection);
        v19 = Handle;
      }
      v25 = NtClose(v19);
      if ( v25 < 0 )
        RtlNtStatusToDosError(v25);
      else
        Handle = 0;
    }
  }
  if ( v20 )
  {
    RtlAcquireSRWLockExclusive(&PredefinedHandleTableSRWLock);
    if ( (*(_DWORD *)(v20 + 8))-- == 1 )
    {
      v30 = *(_QWORD **)(v20 + 16);
      v31 = v30[1];
      if ( v20 != v31 || *(_QWORD *)v20 != *v30 )
      {
        v12 = (HKEY *)v20;
        v42 = RemoveUnitFromList(v31, v20, v28);
        *(_QWORD *)(v43 + 8) = v42;
      }
    }
    RtlReleaseSRWLockExclusive(&PredefinedHandleTableSRWLock);
    if ( v12 )
    {
      RegCloseKey(*v12);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18005d410  mov     r11, rsp
0x18005d413  mov     [r11+8], rcx
0x18005d417  push    rbx
0x18005d418  push    rsi
0x18005d419  push    rdi
0x18005d41a  push    r12
0x18005d41c  push    r14
0x18005d41e  push    r15
0x18005d420  sub     rsp, 0B8h
0x18005d427  mov     rdi, r9
0x18005d42a  mov     rbx, rdx
0x18005d42d  xorps   xmm0, xmm0
0x18005d430  movups  xmmword ptr [r11-68h], xmm0
0x18005d435  xorps   xmm1, xmm1
0x18005d438  movups  xmmword ptr [rsp+0E8h+var_78.Length], xmm1
0x18005d43d  xor     eax, eax
0x18005d43f  movups  xmmword ptr [r11-58h], xmm0
0x18005d444  movups  xmmword ptr [r11-4Ch], xmm0
0x18005d449  xor     esi, esi
0x18005d44b  mov     [rsp+0E8h+var_88], rsi
0x18005d450  mov     [r11-80h], rsi
0x18005d454  cmp     rcx, 0FFFFFFFF80000004h
0x18005d45b  jz      loc_18005D8F5
0x18005d461  cmp     rcx, 0FFFFFFFF80000050h
0x18005d468  jz      loc_18005D8F5
0x18005d46e  cmp     rcx, 0FFFFFFFF80000060h
0x18005d475  jz      loc_18005D8F5
0x18005d47b  test    r8d, r8d
0x18005d47e  jnz     loc_18005D9C0
0x18005d484  test    rdx, rdx
0x18005d487  jz      loc_18005D9D7
0x18005d48d  mov     r14, [rsp+0E8h+arg_38]
0x18005d495  test    r14, r14
0x18005d498  jz      loc_18005D9D7
0x18005d49e  lea     r9, [r11-80h]
0x18005d4a2  lea     r8, [rsp+0E8h+var_88]
0x18005d4a7  lea     rdx, [r11+8]
0x18005d4ab  call    MapPredefinedHandleInternal
0x18005d4b0  mov     r12d, eax
0x18005d4b3  test    eax, eax
0x18005d4b5  jnz     loc_18005D593
0x18005d4bb  mov     rdx, rbx; SourceString
0x18005d4be  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x18005d4c6  call    cs:__imp_RtlInitUnicodeStringEx
0x18005d4cd  nop     dword ptr [rax+rax+00h]
0x18005d4d2  test    eax, eax
0x18005d4d4  js      loc_18005DA3A
0x18005d4da  add     [rsp+0E8h+DestinationString.Length], 2
0x18005d4e3  test    rdi, rdi
0x18005d4e6  jnz     loc_18005D86F
0x18005d4ec  mov     dword ptr [rsp+0E8h+var_78.Length], esi
0x18005d4f0  mov     [rsp+0E8h+var_78.Buffer], rsi
0x18005d4f5  mov     rbx, [rsp+0E8h+arg_30]
0x18005d4fd  test    rbx, rbx
0x18005d500  jnz     loc_18005D783
0x18005d506  mov     rbx, rsi
0x18005d509  mov     [rsp+0E8h+Handle], rbx
0x18005d50e  mov     rdi, [rsp+0E8h+KeyHandle]
0x18005d516  test    dil, 1
0x18005d51a  jnz     loc_18005D912
0x18005d520  mov     rax, [rsp+0E8h+arg_48]
0x18005d528  mov     [rsp+0E8h+var_A0], rax; __int64
0x18005d52d  mov     rax, [rsp+0E8h+arg_40]
0x18005d535  mov     [rsp+0E8h+var_A8], rax; __int64
0x18005d53a  mov     [rsp+0E8h+var_B0], r14; __int64
0x18005d53f  mov     [rsp+0E8h+var_C0], rbx; __int64
0x18005d544  mov     eax, [rsp+0E8h+arg_28]
0x18005d54b  mov     [rsp+0E8h+var_C8], eax; int
0x18005d54f  mov     r9d, [rsp+0E8h+arg_20]
0x18005d557  lea     r8, [rsp+0E8h+var_78]
0x18005d55c  lea     rdx, [rsp+0E8h+DestinationString]; Source
0x18005d564  mov     rcx, rdi; KeyHandle
0x18005d567  call    BaseRegCreateKeyInternal
0x18005d56c  mov     r12d, eax
0x18005d56f  test    rbx, rbx
0x18005d572  jz      short loc_18005D593
0x18005d574  mov     rcx, gs:60h
0x18005d57d  mov     r8, [rbx+8]; P
0x18005d581  xor     edx, edx; Flags
0x18005d583  mov     rcx, [rcx+30h]; HeapHandle
0x18005d587  call    cs:__imp_RtlFreeHeap
0x18005d58e  nop     dword ptr [rax+rax+00h]
0x18005d593  mov     rcx, [rsp+0E8h+var_88]
0x18005d598  mov     [rsp+0E8h+Handle], rcx
0x18005d59d  mov     r15, [rsp+0E8h+var_80]
0x18005d5a2  test    rcx, rcx
0x18005d5a5  jz      loc_18005D663
0x18005d5ab  cmp     rcx, 0FFFFFFFF80000004h
0x18005d5b2  jz      loc_18005D89E
0x18005d5b8  cmp     rcx, 0FFFFFFFF80000050h
0x18005d5bf  jz      loc_18005D89E
0x18005d5c5  cmp     rcx, 0FFFFFFFF80000060h
0x18005d5cc  jz      loc_18005D89E
0x18005d5d2  test    cl, 2
0x18005d5d5  jz      short loc_18005D64A
0x18005d5d7  xor     r9d, r9d
0x18005d5da  xor     r8d, r8d
0x18005d5dd  lea     rdx, ClassesEnumTableInitFn
0x18005d5e4  lea     rcx, gClassesEnumTableInit
0x18005d5eb  call    cs:__imp_RtlRunOnceExecuteOnce
0x18005d5f2  nop     dword ptr [rax+rax+00h]
0x18005d5f7  mov     r14, [rsp+0E8h+Handle]
0x18005d5fc  lea     rcx, CriticalSection; CriticalSection
0x18005d603  call    cs:__imp_RtlEnterCriticalSection
0x18005d60a  nop     dword ptr [rax+rax+00h]
0x18005d60f  mov     rcx, cs:qword_1803A7248
0x18005d616  test    rcx, rcx
0x18005d619  jz      short loc_18005D632
0x18005d61b  mov     rdi, [rcx]
0x18005d61e  mov     rax, [rcx+18h]
0x18005d622  mov     rbx, rax
0x18005d625  test    rbx, rbx
0x18005d628  jnz     short loc_18005D67D
0x18005d62a  mov     rcx, rdi
0x18005d62d  test    rdi, rdi
0x18005d630  jnz     short loc_18005D61B
0x18005d632  lea     rcx, CriticalSection; CriticalSection
0x18005d639  call    cs:__imp_RtlLeaveCriticalSection
0x18005d640  nop     dword ptr [rax+rax+00h]
0x18005d645  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18005d64a  call    cs:__imp_NtClose
0x18005d651  nop     dword ptr [rax+rax+00h]
0x18005d656  test    eax, eax
0x18005d658  js      loc_18005D8FF
0x18005d65e  mov     [rsp+0E8h+Handle], rsi
0x18005d663  test    r15, r15
0x18005d666  jnz     short loc_18005D6CC
0x18005d668  mov     eax, r12d
0x18005d66b  add     rsp, 0B8h
0x18005d672  pop     r15
0x18005d674  pop     r14
0x18005d676  pop     r12
0x18005d678  pop     rdi
0x18005d679  pop     rsi
0x18005d67a  pop     rbx
0x18005d67b  retn
0x18005d67d  cmp     r14, [rbx+10h]
0x18005d681  jz      short loc_18005D688
0x18005d683  mov     rbx, [rbx]
0x18005d686  jmp     short loc_18005D625
0x18005d688  cmp     rbx, rax
0x18005d68b  jnz     loc_18005D74A
0x18005d691  mov     rax, [rbx]
0x18005d694  mov     [rcx+18h], rax
0x18005d698  test    rax, rax
0x18005d69b  jz      short loc_18005D6A1
0x18005d69d  mov     [rax+8], rsi
0x18005d6a1  mov     rcx, rbx; void *
0x18005d6a4  call    EnumStateClear
0x18005d6a9  mov     rcx, gs:60h
0x18005d6b2  mov     r8, rbx; P
0x18005d6b5  xor     edx, edx; Flags
0x18005d6b7  mov     rcx, [rcx+30h]; HeapHandle
0x18005d6bb  call    cs:__imp_RtlFreeHeap
0x18005d6c2  nop     dword ptr [rax+rax+00h]
0x18005d6c7  jmp     loc_18005D62A
0x18005d6cc  lea     rcx, PredefinedHandleTableSRWLock
0x18005d6d3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005d6da  nop     dword ptr [rax+rax+00h]
0x18005d6df  add     dword ptr [r15+8], 0FFFFFFFFh
0x18005d6e4  jnz     short loc_18005D703
0x18005d6e6  mov     rax, [r15+10h]
0x18005d6ea  mov     rcx, [rax+8]
0x18005d6ee  cmp     r15, rcx
0x18005d6f1  jnz     loc_18005DA22
0x18005d6f7  mov     rax, [rax]
0x18005d6fa  cmp     [r15], rax
0x18005d6fd  jnz     loc_18005DA22
0x18005d703  lea     rcx, PredefinedHandleTableSRWLock
0x18005d70a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005d711  nop     dword ptr [rax+rax+00h]
0x18005d716  test    rsi, rsi
0x18005d719  jz      loc_18005D668
0x18005d71f  mov     rcx, [rsi]; hKey
0x18005d722  call    RegCloseKey
0x18005d727  mov     rcx, gs:60h
0x18005d730  mov     r8, rsi; P
0x18005d733  xor     edx, edx; Flags
0x18005d735  mov     rcx, [rcx+30h]; HeapHandle
0x18005d739  call    cs:__imp_RtlFreeHeap
0x18005d740  nop     dword ptr [rax+rax+00h]
0x18005d745  jmp     loc_18005D668
0x18005d74a  mov     rdx, [rbx+8]
0x18005d74e  mov     rax, [rbx]
0x18005d751  test    rdx, rdx
0x18005d754  jz      short loc_18005D759
0x18005d756  mov     [rdx], rax
0x18005d759  test    rax, rax
0x18005d75c  jz      short loc_18005D762
0x18005d75e  mov     [rax+8], rdx
0x18005d762  mov     rax, [rcx+18h]
0x18005d766  test    rax, rax
0x18005d769  jz      short loc_18005D776
0x18005d76b  mov     [rbx], rax
0x18005d76e  mov     rax, [rcx+18h]
0x18005d772  mov     [rax+8], rbx
0x18005d776  mov     [rcx+18h], rbx
0x18005d77a  mov     [rbx+8], rsi
0x18005d77e  jmp     loc_18005D691
0x18005d783  mov     [rsp+0E8h+var_50], rsi
0x18005d78b  mov     rdi, [rbx+8]
0x18005d78f  test    rdi, rdi
0x18005d792  jz      loc_18005D8DA
0x18005d798  mov     rcx, rdi; SecurityDescriptor
0x18005d79b  call    cs:__imp_RtlValidSecurityDescriptor
0x18005d7a2  nop     dword ptr [rax+rax+00h]
0x18005d7a7  test    al, al
0x18005d7a9  jz      loc_18005D896
0x18005d7af  mov     rcx, rdi; SecurityDescriptor
0x18005d7b2  call    cs:__imp_RtlLengthSecurityDescriptor
0x18005d7b9  nop     dword ptr [rax+rax+00h]
0x18005d7be  mov     r15d, eax
0x18005d7c1  mov     rax, [rsp+0E8h+var_50]
0x18005d7c9  test    rax, rax
0x18005d7cc  jnz     loc_18005D8C1
0x18005d7d2  mov     r8d, r15d; Size
0x18005d7d5  mov     rcx, gs:60h
0x18005d7de  xor     edx, edx; Flags
0x18005d7e0  mov     rcx, [rcx+30h]; HeapHandle
0x18005d7e4  call    cs:__imp_RtlAllocateHeap
0x18005d7eb  nop     dword ptr [rax+rax+00h]
0x18005d7f0  mov     [rsp+0E8h+var_50], rax
0x18005d7f8  test    rax, rax
0x18005d7fb  jz      loc_18005D8EA
0x18005d801  mov     [rsp+0E8h+BufferLength], r15d
0x18005d809  mov     [rsp+0E8h+BufferLength+4], r15d
0x18005d811  lea     r8, [rsp+0E8h+BufferLength]; BufferLength
0x18005d819  mov     rdx, rax; SelfRelativeSD
0x18005d81c  mov     rcx, rdi; AbsoluteSD
0x18005d81f  call    cs:__imp_RtlMakeSelfRelativeSD
0x18005d826  nop     dword ptr [rax+rax+00h]
0x18005d82b  mov     ecx, eax; Status
0x18005d82d  call    cs:__imp_RtlNtStatusToDosError
0x18005d834  nop     dword ptr [rax+rax+00h]
0x18005d839  mov     r12d, eax
0x18005d83c  test    r12d, r12d
0x18005d83f  jnz     loc_18005D593
0x18005d845  mov     eax, [rbx]
0x18005d847  mov     [rsp+0E8h+var_58], eax
0x18005d84e  movzx   eax, byte ptr [rbx+10h]
0x18005d852  mov     [rsp+0E8h+var_40], al
0x18005d859  test    r12d, r12d
0x18005d85c  jnz     loc_18005D593
0x18005d862  lea     rbx, [rsp+0E8h+var_58]
0x18005d86a  jmp     loc_18005D509
0x18005d86f  mov     rdx, rdi; SourceString
0x18005d872  lea     rcx, [rsp+0E8h+var_78]; DestinationString
0x18005d877  call    cs:__imp_RtlInitUnicodeStringEx
0x18005d87e  nop     dword ptr [rax+rax+00h]
0x18005d883  test    eax, eax
0x18005d885  js      loc_18005DA3A
0x18005d88b  add     [rsp+0E8h+var_78.Length], 2
0x18005d891  jmp     loc_18005D4F5
0x18005d896  mov     r12d, 57h ; 'W'
0x18005d89c  jmp     short loc_18005D83C
0x18005d89e  call    IsBaseRegCloseKeyPresent
0x18005d8a3  test    al, al
0x18005d8a5  jz      loc_18005D663
0x18005d8ab  lea     rcx, [rsp+0E8h+Handle]
0x18005d8b0  call    cs:__imp_PerfRegCloseKey
0x18005d8b7  nop     dword ptr [rax+rax+00h]
0x18005d8bc  jmp     loc_18005D663
0x18005d8c1  cmp     [rsp+0E8h+BufferLength], r15d
0x18005d8c9  jnb     loc_18005D809
0x18005d8cf  mov     r12d, 0Eh
0x18005d8d5  jmp     loc_18005D83C
0x18005d8da  mov     qword ptr [rsp+0E8h+BufferLength], rsi
0x18005d8e2  mov     r12d, esi
0x18005d8e5  jmp     loc_18005D845
0x18005d8ea  mov     r12d, 0Eh
0x18005d8f0  jmp     loc_18005D83C
0x18005d8f5  mov     eax, 6
0x18005d8fa  jmp     loc_18005D66B
0x18005d8ff  mov     ecx, eax; Status
0x18005d901  call    cs:__imp_RtlNtStatusToDosError
0x18005d908  nop     dword ptr [rax+rax+00h]
0x18005d90d  jmp     loc_18005D663
0x18005d912  call    IsBaseRegCloseKeyPresent
0x18005d917  test    al, al
0x18005d919  jz      loc_18005D56F
0x18005d91f  mov     dword ptr [rsp+0E8h+KeyHandle], esi
0x18005d926  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18005d92a  call    IsBaseRegCloseKeyPresent
0x18005d92f  test    al, al
0x18005d931  jnz     loc_18005D9EE
0x18005d937  xor     dl, dl
0x18005d939  mov     ecx, [rsp+0E8h+arg_28]
0x18005d940  and     ecx, 0FFFFFCFFh
0x18005d946  test    dl, dl
0x18005d948  cmovnz  ecx, [rsp+0E8h+arg_28]
0x18005d950  mov     rax, [rsp+0E8h+arg_40]
0x18005d958  mov     [rsp+0E8h+var_B0], rax
0x18005d95d  mov     [rsp+0E8h+var_B8], r14
0x18005d962  mov     [rsp+0E8h+var_C0], rbx
0x18005d967  mov     [rsp+0E8h+var_C8], ecx
0x18005d96b  mov     r9d, [rsp+0E8h+arg_20]
0x18005d973  lea     r8, [rsp+0E8h+var_78]
0x18005d978  lea     rdx, [rsp+0E8h+DestinationString]
0x18005d980  mov     rcx, rdi
0x18005d983  call    cs:__imp_BaseRegCreateKey
  ... truncated ...
```
