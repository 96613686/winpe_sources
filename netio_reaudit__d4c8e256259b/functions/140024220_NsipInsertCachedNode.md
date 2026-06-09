# NsipInsertCachedNode

- ea: `0x140024220`
- end: `0x1400244d8`
- name: `NsipInsertCachedNode`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140023c30`

## callees

- `0x140024220`
- `0x140025a60`
- `0x14004395c`
- `0x1400468f4`
- `0x14005f99c`
- `0x140078920`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002437a`
- `ntoskrnl!ObfDereferenceObject` at `0x14002437a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024307`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024307`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140024349`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140024349`
- `ntoskrnl!ObGetObjectSecurity` at `0x140024368`
- `ntoskrnl!ObGetObjectSecurity` at `0x140024368`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140024429`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140024429`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400242fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400242fb`

## pseudocode

```c
NTSTATUS __fastcall NsipInsertCachedNode(void *a1, int a2, int a3, int a4, __int64 *a5)
{
  _QWORD *v5; // rsi
  __int64 *v6; // rdi
  PSECURITY_DESCRIPTOR v7; // r14
  unsigned __int8 v8; // bl
  int v10; // r15d
  __int64 LowPriority; // rax
  __int64 v12; // rcx
  int v13; // ebx
  __int64 **v14; // rdi
  __int64 *v15; // rcx
  unsigned int v16; // eax
  NTSTATUS result; // eax
  PVOID v18; // rbx
  NTSTATUS ObjectSecurity; // r14d
  __int64 ***v20; // rax
  __int64 **v21; // rax
  int v22; // ecx
  int v23; // r9d
  _QWORD *v24; // rax
  int v25; // eax
  PVOID *i; // rbx
  __int64 v27; // rax
  int v28; // eax
  void *v29; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v31; // [rsp+38h] [rbp-18h] BYREF
  PVOID Object; // [rsp+40h] [rbp-10h] BYREF
  _QWORD *v33; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+88h] [rbp+38h] BYREF
  int v35; // [rsp+98h] [rbp+48h]

  v35 = a4;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v33 = 0;
  v8 = 0;
  v31 = 0;
  SecurityDescriptor = 0;
  MemoryAllocated = 0;
  v10 = a2;
  if ( a2 )
  {
    Object = 0;
    result = ObReferenceObjectByHandle(a1, 0, 0, 0, &Object, 0);
    if ( result < 0 )
      return result;
    v18 = Object;
    ObjectSecurity = ObGetObjectSecurity(Object, &SecurityDescriptor, &MemoryAllocated);
    ObfDereferenceObject(v18);
    if ( ObjectSecurity < 0 )
      return ObjectSecurity;
    v7 = SecurityDescriptor;
    v8 = MemoryAllocated;
  }
  if ( a5 == &NsipCachedRegistryKeyList )
  {
    if ( v10 == 1 )
    {
      LOBYTE(a2) = v8;
      v22 = (int)v7;
    }
    else
    {
      a2 = 0;
      v22 = 0;
    }
    v13 = NsipAllocateAndInitializeNode(v22, a2, a3, 0, (__int64)&v31);
    if ( v13 < 0 )
    {
LABEL_32:
      if ( SecurityDescriptor )
        ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
      return v13;
    }
    v6 = v31;
    v7 = SecurityDescriptor;
    v8 = MemoryAllocated;
  }
  if ( v10 == 2 )
  {
    LowPriority = NsipAllocateLowPriority(72);
    v12 = LowPriority;
    if ( LowPriority )
    {
      v23 = v35;
      v24 = (_QWORD *)(LowPriority + 16);
      v5 = (_QWORD *)v12;
      v24[1] = v24;
      *v24 = v24;
      *(_QWORD *)(v12 + 8) = v12;
      *(_QWORD *)v12 = v12;
      *(_BYTE *)(v12 + 40) = v8;
      v13 = 0;
      *(_QWORD *)(v12 + 32) = v7;
      *(_DWORD *)(v12 + 44) = v23;
    }
    else
    {
      v13 = -1073741670;
    }
  }
  else
  {
    v25 = NsipAllocateAndInitializeNode(0, 0, 0, v35, (__int64)&v33);
    v5 = v33;
    v13 = v25;
  }
  if ( v13 < 0 )
  {
    if ( v6 )
      NsipFreeAndCleanupNode(v6);
    if ( v10 == 1 )
      return v13;
    goto LABEL_32;
  }
  NsipLockCacheListExclusive(v12);
  if ( a5 != &NsipCachedRegistryKeyList )
  {
    v6 = a5;
    goto LABEL_9;
  }
  for ( i = (PVOID *)qword_14009ADF0; ; i = (PVOID *)*i )
  {
    if ( i == &qword_14009ADF0 )
    {
      v21 = (__int64 **)qword_14009ADF8;
      if ( *(PVOID **)qword_14009ADF8 == &qword_14009ADF0 )
      {
        *v6 = (__int64)&qword_14009ADF0;
        v6[1] = (__int64)v21;
        *v21 = v6;
        qword_14009ADF8 = (__int64)v6;
        goto LABEL_9;
      }
LABEL_25:
      __fastfail(3u);
    }
    v28 = memcmp((char *)v6 + 44, (char *)i + 44, 0x18u);
    if ( v28 <= 0 )
      break;
  }
  if ( v28 )
  {
    v6[1] = (__int64)i[1];
    *v6 = (__int64)i;
    *(_QWORD *)i[1] = v6;
    i[1] = v6;
  }
  else
  {
    if ( !i[4] )
    {
      v29 = (void *)v6[4];
      if ( v29 )
      {
        i[4] = v29;
        *((_BYTE *)i + 40) = *((_BYTE *)v6 + 40);
        v6[4] = 0;
      }
    }
    NsipFreeAndCleanupNode(v6);
    v6 = (__int64 *)i;
  }
LABEL_9:
  v14 = (__int64 **)(v6 + 2);
  v15 = *v14;
  while ( 2 )
  {
    if ( v15 == (__int64 *)v14 )
    {
      v20 = (__int64 ***)v14[1];
      if ( *v20 == v14 )
      {
        *v5 = v14;
        v5[1] = v20;
        *v20 = (__int64 **)v5;
        v14[1] = v5;
        goto LABEL_15;
      }
      goto LABEL_25;
    }
    v16 = *((_DWORD *)v5 + 11);
    if ( v16 > *((_DWORD *)v15 + 11) )
    {
      v15 = (__int64 *)*v15;
      continue;
    }
    break;
  }
  if ( v16 == *((_DWORD *)v15 + 11) )
  {
    if ( !v15[4] )
    {
      v27 = v5[4];
      if ( v27 )
      {
        v15[4] = v27;
        *((_BYTE *)v15 + 40) = *((_BYTE *)v5 + 40);
        v5[4] = 0;
      }
    }
    NsipFreeAndCleanupNode(v5);
  }
  else
  {
    v5[1] = v15[1];
    *v5 = v15;
    *(_QWORD *)v15[1] = v5;
    v15[1] = (__int64)v5;
  }
LABEL_15:
  ExReleaseResourceLite(&NsipCachedRegistryKeyListLock);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x140024220  mov     [rsp-28h+arg_0], rbx
0x140024225  mov     [rsp-28h+arg_10], rsi
0x14002422a  mov     [rsp-28h+arg_18], r9d
0x14002422f  push    rbp
0x140024230  push    rdi
0x140024231  push    r13
0x140024233  push    r14
0x140024235  push    r15
0x140024237  mov     rbp, rsp
0x14002423a  sub     rsp, 50h
0x14002423e  xor     esi, esi
0x140024240  xor     edi, edi
0x140024242  xor     r14d, r14d
0x140024245  mov     [rbp+var_8], rsi
0x140024249  xor     bl, bl
0x14002424b  mov     [rbp+var_18], rdi
0x14002424f  mov     [rbp+SecurityDescriptor], r14
0x140024253  mov     r13, r8
0x140024256  mov     [rbp+MemoryAllocated], bl
0x140024259  mov     r15d, edx
0x14002425c  test    edx, edx
0x14002425e  jnz     loc_14002432F
0x140024264  lea     rax, NsipCachedRegistryKeyList
0x14002426b  cmp     [rbp+arg_20], rax
0x14002426f  jz      loc_1400243FA
0x140024275  cmp     r15d, 2
0x140024279  jnz     loc_140024465
0x14002427f  lea     ecx, [r15+46h]
0x140024283  call    NsipAllocateLowPriority
0x140024288  mov     rcx, rax
0x14002428b  test    rax, rax
0x14002428e  jnz     loc_14002443A
0x140024294  mov     ebx, 0C000009Ah
0x140024299  test    ebx, ebx
0x14002429b  js      loc_140024397
0x1400242a1  call    NsipLockCacheListExclusive
0x1400242a6  lea     rax, NsipCachedRegistryKeyList
0x1400242ad  cmp     [rbp+arg_20], rax
0x1400242b1  jz      loc_140024496
0x1400242b7  mov     rdi, [rbp+arg_20]
0x1400242bb  add     rdi, 10h
0x1400242bf  mov     rcx, [rdi]
0x1400242c2  cmp     rcx, rdi
0x1400242c5  jz      loc_1400243AD
0x1400242cb  mov     eax, [rsi+2Ch]
0x1400242ce  cmp     eax, [rcx+2Ch]
0x1400242d1  jbe     short loc_1400242D8
0x1400242d3  mov     rcx, [rcx]
0x1400242d6  jmp     short loc_1400242C2
0x1400242d8  jz      loc_1400244A9
0x1400242de  mov     rax, [rcx+8]
0x1400242e2  mov     [rsi+8], rax
0x1400242e6  mov     [rsi], rcx
0x1400242e9  mov     rax, [rcx+8]
0x1400242ed  mov     [rax], rsi
0x1400242f0  mov     [rcx+8], rsi
0x1400242f4  lea     rcx, NsipCachedRegistryKeyListLock; Resource
0x1400242fb  call    cs:__imp_ExReleaseResourceLite
0x140024302  nop     dword ptr [rax+rax+00h]
0x140024307  call    cs:__imp_KeLeaveCriticalRegion
0x14002430e  nop     dword ptr [rax+rax+00h]
0x140024313  xor     eax, eax
0x140024315  lea     r11, [rsp+50h+var_s0]
0x14002431a  mov     rbx, [r11+30h]
0x14002431e  mov     rsi, [r11+40h]
0x140024322  mov     rsp, r11
0x140024325  pop     r15
0x140024327  pop     r14
0x140024329  pop     r13
0x14002432b  pop     rdi
0x14002432c  pop     rbp
0x14002432d  retn
0x14002432f  lea     rax, [rbp+var_10]
0x140024333  mov     [rsp+50h+HandleInformation], rsi; HandleInformation
0x140024338  xor     r9d, r9d; AccessMode
0x14002433b  mov     [rsp+50h+Object], rax; Object
0x140024340  xor     r8d, r8d; ObjectType
0x140024343  mov     [rbp+var_10], rsi
0x140024347  xor     edx, edx; DesiredAccess
0x140024349  call    cs:__imp_ObReferenceObjectByHandle
0x140024350  nop     dword ptr [rax+rax+00h]
0x140024355  test    eax, eax
0x140024357  js      short loc_140024315
0x140024359  mov     rbx, [rbp+var_10]
0x14002435d  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x140024361  mov     rcx, rbx; Object
0x140024364  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140024368  call    cs:__imp_ObGetObjectSecurity
0x14002436f  nop     dword ptr [rax+rax+00h]
0x140024374  mov     rcx, rbx; Object
0x140024377  mov     r14d, eax
0x14002437a  call    cs:__imp_ObfDereferenceObject
0x140024381  nop     dword ptr [rax+rax+00h]
0x140024386  test    r14d, r14d
0x140024389  js      short loc_1400243F2
0x14002438b  mov     r14, [rbp+SecurityDescriptor]
0x14002438f  mov     bl, [rbp+MemoryAllocated]
0x140024392  jmp     loc_140024264
0x140024397  test    rdi, rdi
0x14002439a  jnz     loc_140024489
0x1400243a0  cmp     r15d, 1
0x1400243a4  jnz     short loc_14002441D
0x1400243a6  mov     eax, ebx
0x1400243a8  jmp     loc_140024315
0x1400243ad  mov     rax, [rdi+8]
0x1400243b1  cmp     [rax], rdi
0x1400243b4  jz      short loc_1400243BD
0x1400243b6  mov     ecx, 3
0x1400243bb  int     29h; Win8: RtlFailFast(ecx)
0x1400243bd  mov     [rsi], rdi
0x1400243c0  mov     [rsi+8], rax
0x1400243c4  mov     [rax], rsi
0x1400243c7  mov     [rdi+8], rsi
0x1400243cb  jmp     loc_1400242F4
0x1400243d0  mov     rax, cs:qword_14009ADF8
0x1400243d7  cmp     [rax], r14
0x1400243da  jnz     short loc_1400243B6
0x1400243dc  mov     [rdi], r14
0x1400243df  mov     [rdi+8], rax
0x1400243e3  mov     [rax], rdi
0x1400243e6  mov     cs:qword_14009ADF8, rdi
0x1400243ed  jmp     loc_1400242BB
0x1400243f2  mov     eax, r14d
0x1400243f5  jmp     loc_140024315
0x1400243fa  xor     r9d, r9d
0x1400243fd  lea     rax, [rbp+var_18]
0x140024401  mov     [rsp+50h+Object], rax
0x140024406  mov     r8, r13
0x140024409  cmp     r15d, 1
0x14002440d  jnz     loc_14007B490
0x140024413  mov     dl, bl
0x140024415  mov     rcx, r14
0x140024418  jmp     loc_14007B494
0x14002441d  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140024421  test    rcx, rcx
0x140024424  jz      short loc_1400243A6
0x140024426  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x140024429  call    cs:__imp_ObReleaseObjectSecurity
0x140024430  nop     dword ptr [rax+rax+00h]
0x140024435  jmp     loc_1400243A6
0x14002443a  mov     r9d, [rbp+arg_18]
0x14002443e  add     rax, 10h
0x140024442  mov     rsi, rcx
0x140024445  mov     [rax+8], rax
0x140024449  mov     [rax], rax
0x14002444c  mov     [rcx+8], rcx
0x140024450  mov     [rcx], rcx
0x140024453  mov     [rcx+28h], bl
0x140024456  xor     ebx, ebx
0x140024458  mov     [rcx+20h], r14
0x14002445c  mov     [rcx+2Ch], r9d
0x140024460  jmp     loc_140024299
0x140024465  mov     r9d, [rbp+arg_18]
0x140024469  lea     rax, [rbp+var_8]
0x14002446d  xor     r8d, r8d
0x140024470  mov     [rsp+50h+Object], rax
0x140024475  xor     edx, edx
0x140024477  xor     ecx, ecx
0x140024479  call    NsipAllocateAndInitializeNode
0x14002447e  mov     rsi, [rbp+var_8]
0x140024482  mov     ebx, eax
0x140024484  jmp     loc_140024299
0x140024489  mov     rcx, rdi; P
0x14002448c  call    NsipFreeAndCleanupNode
0x140024491  jmp     loc_1400243A0
0x140024496  mov     rbx, cs:qword_14009ADF0
0x14002449d  lea     r14, qword_14009ADF0
0x1400244a4  jmp     loc_14007B4B3
0x1400244a9  cmp     qword ptr [rcx+20h], 0
0x1400244ae  jnz     loc_14007B527
0x1400244b4  mov     rax, [rsi+20h]
0x1400244b8  test    rax, rax
0x1400244bb  jz      loc_14007B527
0x1400244c1  mov     [rcx+20h], rax
0x1400244c5  mov     al, [rsi+28h]
0x1400244c8  mov     [rcx+28h], al
0x1400244cb  mov     qword ptr [rsi+20h], 0
0x1400244d3  jmp     loc_14007B527
0x14007b490  xor     edx, edx
0x14007b492  xor     ecx, ecx
0x14007b494  call    NsipAllocateAndInitializeNode
0x14007b499  mov     ebx, eax
0x14007b49b  test    eax, eax
0x14007b49d  js      loc_14002441D
0x14007b4a3  mov     rdi, [rbp+var_18]
0x14007b4a7  mov     r14, [rbp+SecurityDescriptor]
0x14007b4ab  mov     bl, [rbp+MemoryAllocated]
0x14007b4ae  jmp     loc_140024275
0x14007b4b3  cmp     rbx, r14
0x14007b4b6  jz      loc_1400243D0
0x14007b4bc  lea     rdx, [rbx+2Ch]; Buf2
0x14007b4c0  mov     r8d, 18h; Size
0x14007b4c6  lea     rcx, [rdi+2Ch]; Buf1
0x14007b4ca  call    memcmp
0x14007b4cf  test    eax, eax
0x14007b4d1  jle     short loc_14007B4D8
0x14007b4d3  mov     rbx, [rbx]
0x14007b4d6  jmp     short loc_14007B4B3
0x14007b4d8  jnz     short loc_14007B50C
0x14007b4da  cmp     qword ptr [rbx+20h], 0
0x14007b4df  jnz     short loc_14007B4FC
0x14007b4e1  mov     rax, [rdi+20h]
0x14007b4e5  test    rax, rax
0x14007b4e8  jz      short loc_14007B4FC
0x14007b4ea  mov     [rbx+20h], rax
0x14007b4ee  mov     al, [rdi+28h]
0x14007b4f1  mov     [rbx+28h], al
0x14007b4f4  mov     qword ptr [rdi+20h], 0
0x14007b4fc  mov     rcx, rdi; P
0x14007b4ff  call    NsipFreeAndCleanupNode
0x14007b504  mov     rdi, rbx
0x14007b507  jmp     loc_1400242BB
0x14007b50c  mov     rax, [rbx+8]
0x14007b510  mov     [rdi+8], rax
0x14007b514  mov     [rdi], rbx
0x14007b517  mov     rax, [rbx+8]
0x14007b51b  mov     [rax], rdi
0x14007b51e  mov     [rbx+8], rdi
0x14007b522  jmp     loc_1400242BB
0x14007b527  mov     rcx, rsi; P
0x14007b52a  call    NsipFreeAndCleanupNode
0x14007b52f  nop
0x14007b530  jmp     loc_1400242F4
```
