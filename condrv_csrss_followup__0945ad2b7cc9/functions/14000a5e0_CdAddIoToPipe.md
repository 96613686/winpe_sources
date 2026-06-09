# CdAddIoToPipe

- ea: `0x14000a5e0`
- end: `0x14000a9f0`
- name: `CdAddIoToPipe`
- size: `1040`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008230`
- `0x140009420`
- `0x140009760`
- `0x140009af0`
- `0x14000ae70`
- `0x14000b4d0`
- `0x14000b820`
- `0x14000c0f0`
- `0x14000c5c0`

## callees

- `0x14000a5e0`
- `0x14000aa00`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a617`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a617`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a940`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a940`
- `ntoskrnl!IofCompleteRequest` at `0x14000a90c`
- `ntoskrnl!IofCompleteRequest` at `0x14000a90c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a607`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a607`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a62b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a62b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a92f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a92f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a673`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a6cb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a79c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a673`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a6cb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a79c`

## pseudocode

```c
__int64 __fastcall CdAddIoToPipe(__int64 a1)
{
  __int64 v1; // rbp
  char v3; // r12
  _QWORD *v4; // r14
  struct _MDL *v5; // rbx
  unsigned int v6; // esi
  PVOID MappedSystemVa; // rax
  unsigned int ByteCount; // eax
  struct _MDL *v9; // rbx
  unsigned int v10; // esi
  PVOID v11; // rax
  unsigned int v12; // eax
  char v13; // al
  _QWORD *v14; // rcx
  _QWORD **v15; // rbx
  __int64 v16; // rcx
  IRP *v17; // rbp
  PMDL MdlAddress; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  _OWORD *v20; // rdx
  _QWORD *v21; // rbx
  int v22; // ecx
  __int64 Length; // r9
  __int64 v24; // r8
  __int64 *i; // rax
  __int64 *v26; // rax
  unsigned int j; // ecx
  __int128 v28; // xmm1
  __int64 v29; // r8
  __int64 v30; // xmm0_8
  int v31; // esi
  __int64 v32; // rax
  _QWORD *v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rax
  unsigned int v36; // esi
  char *v38; // [rsp+30h] [rbp-68h] BYREF
  int v39; // [rsp+38h] [rbp-60h]
  int v40; // [rsp+3Ch] [rbp-5Ch]
  __int128 v41; // [rsp+40h] [rbp-58h]
  __int128 v42; // [rsp+50h] [rbp-48h]
  __int64 v43; // [rsp+60h] [rbp-38h]
  __int64 v44; // [rsp+A0h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 184);
  v3 = 0;
  v4 = *(_QWORD **)(v1 - 64);
  if ( KeGetCurrentIrql() <= 1u )
  {
    KeEnterCriticalRegion();
    v3 = 1;
  }
  ExAcquirePushLockExclusiveEx(*v4, 0);
  v5 = *(struct _MDL **)(v1 - 40);
  v6 = 0;
  while ( v5 )
  {
    if ( (v5->MdlFlags & 5) != 0 )
      MappedSystemVa = v5->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v5, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
    {
LABEL_46:
      v36 = -1073741670;
      goto LABEL_42;
    }
    ByteCount = v5->ByteCount;
    v6 += ByteCount;
    if ( v6 < ByteCount )
    {
LABEL_51:
      v36 = -1073741675;
      goto LABEL_42;
    }
    v5 = v5->Next;
  }
  v9 = *(struct _MDL **)(v1 - 48);
  v10 = 0;
  while ( v9 )
  {
    if ( (v9->MdlFlags & 5) != 0 )
      v11 = v9->MappedSystemVa;
    else
      v11 = MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v11 )
      goto LABEL_46;
    v12 = v9->ByteCount;
    v10 += v12;
    if ( v10 < v12 )
      goto LABEL_51;
    v9 = v9->Next;
  }
  if ( !*((_BYTE *)v4 + 8) )
  {
    v36 = -1073741648;
    goto LABEL_42;
  }
  --*(_BYTE *)(a1 + 67);
  *(_QWORD *)(a1 + 184) -= 72LL;
  v13 = *(_BYTE *)(v1 - 71);
  if ( v13 == 4
    || v13 == 2
    || (_InterlockedExchange64((volatile __int64 *)(a1 + 104), (__int64)&CdpCancelIoIrp), !*(_BYTE *)(a1 + 68))
    || !_InterlockedExchange64((volatile __int64 *)(a1 + 104), 0) )
  {
    v14 = (_QWORD *)v4[4];
    v15 = (_QWORD **)(v4 + 3);
    if ( (_QWORD *)*v14 != v4 + 3 )
      goto LABEL_56;
    *(_QWORD *)(a1 + 168) = v15;
    *(_QWORD *)(a1 + 176) = v14;
    *v14 = a1 + 168;
    v4[4] = a1 + 168;
    v16 = v4[2];
    if ( !v16 || !_InterlockedExchange64((volatile __int64 *)(v16 + 104), 0) )
      goto LABEL_41;
    v17 = (IRP *)v4[2];
    MdlAddress = v17->MdlAddress;
    CurrentStackLocation = v17->Tail.Overlay.CurrentStackLocation;
    if ( (MdlAddress->MdlFlags & 5) != 0 )
      v20 = MdlAddress->MappedSystemVa;
    else
      v20 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
    if ( v20 )
    {
      v21 = *v15;
      v22 = 0;
      Length = CurrentStackLocation->Parameters.Read.Length;
      HIDWORD(v43) = 0;
      v24 = v21[2];
      *(_QWORD *)&v41 = *(v21 - 4);
      *((_QWORD *)&v41 + 1) = *(v21 - 6);
      *(_QWORD *)&v42 = *(_QWORD *)(v24 + 16);
      DWORD2(v42) = *(unsigned __int8 *)(v24 + 1);
      for ( i = *(__int64 **)(v24 + 32); i; i = (__int64 *)*i )
        v22 += *((_DWORD *)i + 10);
      v26 = *(__int64 **)(v24 + 24);
      LODWORD(v43) = v22;
      for ( j = 0; v26; v26 = (__int64 *)*v26 )
        j += *((_DWORD *)v26 + 10);
      HIDWORD(v42) = j;
      v28 = v42;
      v29 = j;
      *v20 = v41;
      v30 = v43;
      v20[1] = v28;
      *((_QWORD *)v20 + 4) = v30;
      if ( j >= (unsigned __int64)(Length - 40) )
      {
        v29 = Length - 40;
        v44 = Length - 40;
      }
      else
      {
        v44 = j;
      }
      if ( !v29 )
      {
LABEL_36:
        v32 = *v21;
        if ( *(_QWORD **)(*v21 + 8LL) == v21 )
        {
          v33 = (_QWORD *)v21[1];
          if ( (_QWORD *)*v33 == v21 )
          {
            *v33 = v32;
            *(_QWORD *)(v32 + 8) = v33;
            v34 = &v4[2 * (*((_DWORD *)v21 - 8) % 5u) + 5];
            v35 = *v34;
            if ( *(_QWORD **)(*v34 + 8LL) == v34 )
            {
              *v21 = v35;
              v21[1] = v34;
              *(_QWORD *)(v35 + 8) = v21;
              *v34 = v21;
              v17->IoStatus.Information = v29 + 40;
              v17->IoStatus.Status = 0;
LABEL_40:
              IofCompleteRequest(v17, 0);
              v4[2] = 0;
LABEL_41:
              v36 = 0;
              *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
              goto LABEL_42;
            }
          }
        }
LABEL_56:
        __fastfail(3u);
      }
      v39 = v29;
      v38 = (char *)v20 + 40;
      v40 = 0;
      v31 = CdpReadIoInput(v21 - 21, 0, &v38, &v44);
      if ( v31 >= 0 )
      {
        v29 = v44;
        goto LABEL_36;
      }
    }
    else
    {
      v31 = -1073741670;
    }
    v17->IoStatus.Status = v31;
    v17->IoStatus.Information = 0;
    goto LABEL_40;
  }
  ++*(_BYTE *)(a1 + 67);
  v36 = -1073741536;
  *(_QWORD *)(a1 + 184) += 72LL;
LABEL_42:
  ExReleasePushLockExclusiveEx(*v4, 0);
  if ( v3 )
    KeLeaveCriticalRegion();
  return v36;
}

```

## disassembly

```asm
0x14000a5e0  mov     [rsp+arg_10], rbx
0x14000a5e5  mov     [rsp+arg_18], rbp
0x14000a5ea  push    rsi
0x14000a5eb  push    rdi
0x14000a5ec  push    r12
0x14000a5ee  push    r13
0x14000a5f0  push    r14
0x14000a5f2  sub     rsp, 70h
0x14000a5f6  mov     rbp, [rcx+0B8h]
0x14000a5fd  mov     rdi, rcx
0x14000a600  xor     r12b, r12b
0x14000a603  mov     r14, [rbp-40h]
0x14000a607  call    cs:__imp_KeGetCurrentIrql
0x14000a60e  nop     dword ptr [rax+rax+00h]
0x14000a613  cmp     al, 1
0x14000a615  ja      short loc_14000A626
0x14000a617  call    cs:__imp_KeEnterCriticalRegion
0x14000a61e  nop     dword ptr [rax+rax+00h]
0x14000a623  mov     r12b, 1
0x14000a626  mov     rcx, [r14]
0x14000a629  xor     edx, edx
0x14000a62b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000a632  nop     dword ptr [rax+rax+00h]
0x14000a637  mov     rbx, [rbp-28h]
0x14000a63b  xor     r13d, r13d
0x14000a63e  mov     esi, r13d
0x14000a641  mov     [rsp+98h+arg_8], r15
0x14000a649  test    rbx, rbx
0x14000a64c  jz      short loc_14000A69A
0x14000a64e  test    byte ptr [rbx+0Ah], 5
0x14000a652  jnz     loc_14000A970
0x14000a658  mov     [rsp+98h+Priority], 40000010h; Priority
0x14000a660  xor     r9d, r9d; RequestedAddress
0x14000a663  xor     edx, edx; AccessMode
0x14000a665  mov     [rsp+98h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000a66a  mov     r8d, 1; CacheType
0x14000a670  mov     rcx, rbx; MemoryDescriptorList
0x14000a673  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a67a  nop     dword ptr [rax+rax+00h]
0x14000a67f  test    rax, rax
0x14000a682  jz      loc_14000A979
0x14000a688  mov     eax, [rbx+28h]
0x14000a68b  add     esi, eax
0x14000a68d  cmp     esi, eax
0x14000a68f  jb      loc_14000A9A9
0x14000a695  mov     rbx, [rbx]
0x14000a698  jmp     short loc_14000A649
0x14000a69a  mov     rbx, [rbp-30h]
0x14000a69e  mov     esi, r13d
0x14000a6a1  test    rbx, rbx
0x14000a6a4  jz      short loc_14000A6F2
0x14000a6a6  test    byte ptr [rbx+0Ah], 5
0x14000a6aa  jnz     loc_14000A980
0x14000a6b0  mov     [rsp+98h+Priority], 40000010h; Priority
0x14000a6b8  xor     r9d, r9d; RequestedAddress
0x14000a6bb  xor     edx, edx; AccessMode
0x14000a6bd  mov     [rsp+98h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000a6c2  mov     r8d, 1; CacheType
0x14000a6c8  mov     rcx, rbx; MemoryDescriptorList
0x14000a6cb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a6d2  nop     dword ptr [rax+rax+00h]
0x14000a6d7  test    rax, rax
0x14000a6da  jz      loc_14000A979
0x14000a6e0  mov     eax, [rbx+28h]
0x14000a6e3  add     esi, eax
0x14000a6e5  cmp     esi, eax
0x14000a6e7  jb      loc_14000A9A9
0x14000a6ed  mov     rbx, [rbx]
0x14000a6f0  jmp     short loc_14000A6A1
0x14000a6f2  cmp     [r14+8], r13b
0x14000a6f6  jz      loc_14000A989
0x14000a6fc  dec     byte ptr [rdi+43h]
0x14000a6ff  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000a707  movzx   eax, byte ptr [rbp-47h]
0x14000a70b  cmp     al, 4
0x14000a70d  jz      short loc_14000A728
0x14000a70f  cmp     al, 2
0x14000a711  jz      short loc_14000A728
0x14000a713  lea     rax, CdpCancelIoIrp
0x14000a71a  xchg    rax, [rdi+68h]
0x14000a71e  cmp     [rdi+44h], r13b
0x14000a722  jnz     loc_14000A9B3
0x14000a728  mov     rcx, [r14+20h]
0x14000a72c  lea     rbx, [r14+18h]
0x14000a730  cmp     [rcx], rbx
0x14000a733  jnz     loc_14000A9E9
0x14000a739  lea     rax, [rdi+0A8h]
0x14000a740  mov     [rax], rbx
0x14000a743  mov     [rax+8], rcx
0x14000a747  mov     [rcx], rax
0x14000a74a  mov     [rbx+8], rax
0x14000a74e  mov     rcx, [r14+10h]
0x14000a752  test    rcx, rcx
0x14000a755  jz      loc_14000A91C
0x14000a75b  mov     rax, r13
0x14000a75e  xchg    rax, [rcx+68h]
0x14000a762  test    rax, rax
0x14000a765  jz      loc_14000A91C
0x14000a76b  mov     rbp, [r14+10h]
0x14000a76f  mov     rcx, [rbp+8]; MemoryDescriptorList
0x14000a773  mov     rsi, [rbp+0B8h]
0x14000a77a  test    byte ptr [rcx+0Ah], 5
0x14000a77e  jnz     loc_14000A990
0x14000a784  mov     [rsp+98h+Priority], 40000010h; Priority
0x14000a78c  xor     r9d, r9d; RequestedAddress
0x14000a78f  xor     edx, edx; AccessMode
0x14000a791  mov     [rsp+98h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000a796  mov     r8d, 1; CacheType
0x14000a79c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a7a3  nop     dword ptr [rax+rax+00h]
0x14000a7a8  mov     rdx, rax
0x14000a7ab  test    rdx, rdx
0x14000a7ae  jz      loc_14000A9D8
0x14000a7b4  mov     rbx, [rbx]
0x14000a7b7  mov     ecx, r13d
0x14000a7ba  mov     r9d, [rsi+8]
0x14000a7be  mov     dword ptr [rsp+98h+var_38+4], r13d
0x14000a7c3  mov     r8, [rbx+10h]
0x14000a7c7  mov     rax, [rbx-20h]
0x14000a7cb  mov     qword ptr [rsp+98h+var_58], rax
0x14000a7d0  mov     rax, [rbx-30h]
0x14000a7d4  mov     qword ptr [rsp+98h+var_58+8], rax
0x14000a7d9  mov     rax, [r8+10h]
0x14000a7dd  mov     qword ptr [rsp+98h+var_48], rax
0x14000a7e2  movzx   eax, byte ptr [r8+1]
0x14000a7e7  mov     dword ptr [rsp+98h+var_48+8], eax
0x14000a7eb  mov     rax, [r8+20h]
0x14000a7ef  test    rax, rax
0x14000a7f2  jz      short loc_14000A7FF
0x14000a7f4  add     ecx, [rax+28h]
0x14000a7f7  mov     rax, [rax]
0x14000a7fa  test    rax, rax
0x14000a7fd  jnz     short loc_14000A7F4
0x14000a7ff  mov     rax, [r8+18h]
0x14000a803  mov     dword ptr [rsp+98h+var_38], ecx
0x14000a807  mov     ecx, r13d
0x14000a80a  test    rax, rax
0x14000a80d  jz      short loc_14000A81A
0x14000a80f  add     ecx, [rax+28h]
0x14000a812  mov     rax, [rax]
0x14000a815  test    rax, rax
0x14000a818  jnz     short loc_14000A80F
0x14000a81a  movups  xmm0, [rsp+98h+var_58]
0x14000a81f  mov     dword ptr [rsp+98h+var_48+0Ch], ecx
0x14000a823  lea     rax, [r9-28h]
0x14000a827  movups  xmm1, [rsp+98h+var_48]
0x14000a82c  mov     r8d, ecx
0x14000a82f  movups  xmmword ptr [rdx], xmm0
0x14000a832  movsd   xmm0, [rsp+98h+var_38]
0x14000a838  movups  xmmword ptr [rdx+10h], xmm1
0x14000a83c  movsd   qword ptr [rdx+20h], xmm0
0x14000a841  cmp     r8, rax
0x14000a844  jnb     loc_14000A999
0x14000a84a  mov     [rsp+98h+arg_0], r8
0x14000a852  test    r8, r8
0x14000a855  jz      short loc_14000A897
0x14000a857  lea     rax, [rdx+28h]
0x14000a85b  mov     [rsp+98h+var_60], r8d
0x14000a860  lea     r8, [rsp+98h+var_68]
0x14000a865  mov     [rsp+98h+var_68], rax
0x14000a86a  xor     edx, edx
0x14000a86c  mov     [rsp+98h+var_5C], r13d
0x14000a871  lea     r9, [rsp+98h+arg_0]
0x14000a879  lea     rcx, [rbx-0A8h]
0x14000a880  call    CdpReadIoInput
0x14000a885  mov     esi, eax
0x14000a887  test    eax, eax
0x14000a889  js      loc_14000A9DD
0x14000a88f  mov     r8, [rsp+98h+arg_0]
0x14000a897  mov     rax, [rbx]
0x14000a89a  cmp     [rax+8], rbx
0x14000a89e  jnz     loc_14000A9E9
0x14000a8a4  mov     rcx, [rbx+8]
0x14000a8a8  cmp     [rcx], rbx
0x14000a8ab  jnz     loc_14000A9E9
0x14000a8b1  mov     [rcx], rax
0x14000a8b4  mov     [rax+8], rcx
0x14000a8b8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000a8c2  mov     ecx, [rbx-20h]
0x14000a8c5  mul     rcx
0x14000a8c8  shr     rdx, 2
0x14000a8cc  lea     rax, [rdx+rdx*4]
0x14000a8d0  sub     rcx, rax
0x14000a8d3  mov     ecx, ecx
0x14000a8d5  shl     rcx, 4
0x14000a8d9  add     rcx, 28h ; '('
0x14000a8dd  add     rcx, r14
0x14000a8e0  mov     rax, [rcx]
0x14000a8e3  cmp     [rax+8], rcx
0x14000a8e7  jnz     loc_14000A9E9
0x14000a8ed  mov     [rbx], rax
0x14000a8f0  mov     [rbx+8], rcx
0x14000a8f4  mov     [rax+8], rbx
0x14000a8f8  lea     rax, [r8+28h]
0x14000a8fc  mov     [rcx], rbx
0x14000a8ff  mov     [rbp+38h], rax
0x14000a903  mov     [rbp+30h], r13d
0x14000a907  xor     edx, edx; PriorityBoost
0x14000a909  mov     rcx, rbp; Irp
0x14000a90c  call    cs:__imp_IofCompleteRequest
0x14000a913  nop     dword ptr [rax+rax+00h]
0x14000a918  mov     [r14+10h], r13
0x14000a91c  mov     rax, [rdi+0B8h]
0x14000a923  mov     esi, r13d
0x14000a926  or      byte ptr [rax+3], 1
0x14000a92a  mov     rcx, [r14]
0x14000a92d  xor     edx, edx
0x14000a92f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000a936  nop     dword ptr [rax+rax+00h]
0x14000a93b  test    r12b, r12b
0x14000a93e  jz      short loc_14000A94C
0x14000a940  call    cs:__imp_KeLeaveCriticalRegion
0x14000a947  nop     dword ptr [rax+rax+00h]
0x14000a94c  mov     r15, [rsp+98h+arg_8]
0x14000a954  lea     r11, [rsp+98h+var_28]
0x14000a959  mov     rbx, [r11+40h]
0x14000a95d  mov     eax, esi
0x14000a95f  mov     rbp, [r11+48h]
0x14000a963  mov     rsp, r11
0x14000a966  pop     r14
0x14000a968  pop     r13
0x14000a96a  pop     r12
0x14000a96c  pop     rdi
0x14000a96d  pop     rsi
0x14000a96e  retn
0x14000a970  mov     rax, [rbx+18h]
0x14000a974  jmp     loc_14000A67F
0x14000a979  mov     esi, 0C000009Ah
0x14000a97e  jmp     short loc_14000A92A
0x14000a980  mov     rax, [rbx+18h]
0x14000a984  jmp     loc_14000A6D7
0x14000a989  mov     esi, 0C00000B0h
0x14000a98e  jmp     short loc_14000A92A
0x14000a990  mov     rdx, [rcx+18h]
0x14000a994  jmp     loc_14000A7AB
0x14000a999  mov     r8, rax
0x14000a99c  mov     [rsp+98h+arg_0], rax
0x14000a9a4  jmp     loc_14000A852
0x14000a9a9  mov     esi, 0C0000095h
0x14000a9ae  jmp     loc_14000A92A
0x14000a9b3  mov     rax, r13
0x14000a9b6  xchg    rax, [rdi+68h]
0x14000a9ba  test    rax, rax
0x14000a9bd  jz      loc_14000A728
0x14000a9c3  inc     byte ptr [rdi+43h]
0x14000a9c6  mov     esi, 0C0000120h
0x14000a9cb  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x14000a9d3  jmp     loc_14000A92A
0x14000a9d8  mov     esi, 0C000009Ah
0x14000a9dd  mov     [rbp+30h], esi
0x14000a9e0  mov     [rbp+38h], r13
0x14000a9e4  jmp     loc_14000A907
0x14000a9e9  mov     ecx, 3
0x14000a9ee  int     29h; Win8: RtlFailFast(ecx)
```
