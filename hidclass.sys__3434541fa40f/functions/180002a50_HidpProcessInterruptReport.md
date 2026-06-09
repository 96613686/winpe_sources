# HidpProcessInterruptReport

- ea: `0x180002a50`
- end: `0x180003024`
- name: `HidpProcessInterruptReport`
- size: `1492`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002560`

## callees

- `0x180002a50`
- `0x180003090`
- `0x18000a15c`
- `0x18001c8a0`
- `0x18001fd24`
- `0x180021ac0`
- `0x180021bb0`
- `0x180027d00`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180002ced`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180002c0c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180002c0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002b89`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002b89`
- `ntoskrnl!ExAllocatePool2` at `0x180002b04`
- `ntoskrnl!ExAllocatePool2` at `0x180002b04`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002ba1`
- `ntoskrnl!KeReleaseSpinLock` at `0x180002ba1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180002a7c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180002a7c`

## string_xrefs

- `0x180002de1`: `Keyboard report dropped due to failed buffer copy.`
- `0x180002e8b`: `Keyboard report dropped due to invalid MdlAddress in read IRP.`

## pseudocode

```c
__int64 __fastcall HidpProcessInterruptReport(__int64 a1, __int64 a2, unsigned __int8 *a3, unsigned int a4, _QWORD *a5)
{
  KSPIN_LOCK *v5; // r15
  size_t v6; // rbp
  KIRQL v10; // al
  int v11; // r8d
  _QWORD *v12; // r9
  _QWORD **v13; // rdx
  KIRQL v14; // r13
  _QWORD *v15; // rdi
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  __int64 Pool2; // rax
  int v19; // edx
  int v20; // r8d
  __int64 **v21; // rsi
  __int64 **v22; // rax
  __int64 *v23; // r8
  __int64 *v24; // rcx
  __int64 ***v25; // rcx
  int v26; // esi
  __int64 result; // rax
  __int64 v28; // rcx
  __int64 v29; // rsi
  PVOID v30; // rax
  unsigned int v31; // r12d
  __int64 v32; // r14
  unsigned int v33; // r9d
  __int64 v34; // r8
  __int64 i; // rcx
  unsigned __int8 *v36; // rbx
  __int64 v37; // r9
  __int64 v38; // rbp
  __int64 j; // rdx
  unsigned int v40; // r10d
  char *v41; // rbx
  char *v42; // r8
  unsigned int k; // edx
  char *v44; // rax
  unsigned int v45; // ebx
  PDEVICE_OBJECT v46; // rcx
  _QWORD *v47; // rbx
  PDEVICE_OBJECT v48; // rcx
  void *v49; // [rsp+60h] [rbp-48h]
  _QWORD *v51; // [rsp+B8h] [rbp+10h]

  v5 = (KSPIN_LOCK *)(a2 + 72);
  v6 = a4;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 72));
  v12 = *(_QWORD **)(a2 + 8);
  v13 = (_QWORD **)(a2 + 24);
  v51 = v12;
  v14 = v10;
LABEL_2:
  v15 = 0;
  do
  {
    v16 = *v13;
    if ( *v13 == v13 )
      break;
    if ( (_QWORD **)v16[1] != v13 )
      goto LABEL_70;
    v17 = (_QWORD *)*v16;
    if ( *(_QWORD **)(*v16 + 8LL) != v16 )
      goto LABEL_70;
    *v13 = v17;
    v15 = v16 - 21;
    v17[1] = v13;
    if ( !_InterlockedExchange64(v16 - 8, 0) )
    {
      v16[1] = v16;
      *v16 = v16;
      goto LABEL_2;
    }
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
  }
  while ( v16 == (_QWORD *)168 );
  if ( v15 )
  {
    v28 = v15[1];
    if ( v28
      && ((v29 = v15[23], (*(_BYTE *)(v28 + 10) & 5) != 0)
        ? (v30 = *(PVOID *)(v28 + 24))
        : (v30 = MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000010u), v12 = v51),
          (v49 = v30) != 0) )
    {
      v31 = *(_DWORD *)(v29 + 8);
      v26 = -1073741668;
      v32 = *(_QWORD *)(a2 + 8);
      v33 = *a3;
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 164));
      v34 = *(_QWORD *)(v32 + 176);
      if ( v34 )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v32 + 184); i = (unsigned int)(i + 1) )
        {
          v36 = (unsigned __int8 *)(v34 + 8 * i);
          if ( *v36 == v33 )
          {
            if ( !v36 )
              break;
            v37 = *(_QWORD *)(v32 + 160);
            v38 = 0;
            if ( v37 )
            {
              for ( j = 0; (unsigned int)j < *(_DWORD *)(v32 + 168); j = (unsigned int)(j + 1) )
              {
                if ( *(unsigned __int8 *)(v37 + 40 * j + 4) == v36[1] )
                {
                  v38 = v37 + 40 * j;
                  if ( !v38 )
                    break;
                  goto LABEL_34;
                }
              }
            }
            TraceLoggingGetCollectionDescFailed(v32, v36[1]);
LABEL_34:
            v40 = v36[1];
            v41 = 0;
            v42 = *(char **)(v32 + 152);
            if ( v42 && v42 != MmBadPointer )
            {
              for ( k = 0; k < *(_DWORD *)(v32 + 168); ++k )
              {
                v44 = &v42[424 * k];
                if ( *(_DWORD *)v44 == v40 )
                {
                  v41 = &v42[424 * k];
                  if ( !v44 )
                    break;
                  goto LABEL_40;
                }
              }
            }
            TraceLoggingGetClassCollectionFailed(v32, v40);
LABEL_40:
            if ( v38 && v41 )
            {
              v45 = *(unsigned __int16 *)(v38 + 20);
              if ( v31 < v45 )
              {
                v26 = -1073741306;
              }
              else
              {
                memmove(v49, a3, *(unsigned __int16 *)(v38 + 20));
                v26 = 0;
              }
              v31 = v45;
            }
            goto LABEL_45;
          }
        }
      }
      TraceLoggingGetReportIdentifierFailed(v32, v33);
LABEL_45:
      v15[7] = v31;
      *((_DWORD *)v15 + 12) = v26;
      v46 = WPP_GLOBAL_Control;
      LOBYTE(k) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      LOBYTE(v42) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                 && LOWORD(WPP_GLOBAL_Control->DeviceType);
      if ( (_BYTE)k || (_BYTE)v42 )
      {
        v47 = v51;
        WPP_RECORDER_AND_TRACE_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          k,
          (_DWORD)v42,
          v51[86],
          5,
          5,
          19,
          (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
          *v51,
          (char)v15,
          v26);
      }
      else
      {
        v47 = v51;
      }
      if ( *(_DWORD *)(a1 + 12) == 2 && v26 < 0 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v46,
          v31,
          *((unsigned __int16 *)v47 + 55) | (*((unsigned __int16 *)v47 + 54) << 16),
          "Keyboard report dropped due to failed buffer copy.");
    }
    else
    {
      v26 = -1073741592;
      *((_DWORD *)v15 + 12) = -1073741592;
      v48 = WPP_GLOBAL_Control;
      LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v13,
          v11,
          v12[86],
          2,
          5,
          20,
          (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
          *v12,
          (char)v15,
          232);
        v12 = v51;
      }
      if ( *(_DWORD *)(a1 + 12) == 2 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v48,
          (unsigned int)v6,
          *((unsigned __int16 *)v12 + 55) | (*((unsigned __int16 *)v12 + 54) << 16),
          "Keyboard report dropped due to invalid MdlAddress in read IRP.");
    }
  }
  else
  {
    Pool2 = ExAllocatePool2(64, (unsigned int)(v6 + 20), 1130654024);
    v21 = (__int64 **)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 16) = v6;
      memmove((void *)(Pool2 + 20), a3, v6);
      v22 = (__int64 **)(a2 + 40);
      v23 = 0;
      if ( *(_DWORD *)(a2 + 88) >= *(_DWORD *)(a2 + 92) )
      {
        v23 = *v22;
        if ( (__int64 **)(*v22)[1] != v22 )
          goto LABEL_70;
        v24 = (__int64 *)*v23;
        if ( *(__int64 **)(*v23 + 8) != v23 )
          goto LABEL_70;
        *v22 = v24;
        v24[1] = (__int64)v22;
        --*(_DWORD *)(a2 + 88);
      }
      v25 = *(__int64 ****)(a2 + 48);
      if ( *v25 == v22 )
      {
        *v21 = (__int64 *)v22;
        v21[1] = (__int64 *)v25;
        *v25 = v21;
        *(_QWORD *)(a2 + 48) = v21;
        ++*(_DWORD *)(a2 + 88);
        if ( v23 )
          ExFreePoolWithTag(v23, 0);
        v26 = 259;
        goto LABEL_18;
      }
LABEL_70:
      __fastfail(3u);
    }
    v26 = -1073741670;
    LOBYTE(v19) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdLd(WPP_GLOBAL_Control->AttachedDevice, v19, v20, v51[86]);
    }
  }
LABEL_18:
  KeReleaseSpinLock(v5, v14);
  result = (unsigned int)v26;
  *a5 = v15;
  return result;
}

```

## disassembly

```asm
0x180002a50  mov     [rsp+Src], r8
0x180002a55  mov     [rsp+arg_0], rcx
0x180002a5a  push    rbx
0x180002a5b  push    rbp
0x180002a5c  push    rdi
0x180002a5d  push    r12
0x180002a5f  push    r13
0x180002a61  push    r14
0x180002a63  push    r15
0x180002a65  sub     rsp, 70h
0x180002a69  lea     r15, [rdx+48h]
0x180002a6d  mov     ebp, r9d
0x180002a70  mov     r12, rcx
0x180002a73  mov     r14, r8
0x180002a76  mov     rcx, r15; SpinLock
0x180002a79  mov     rbx, rdx
0x180002a7c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180002a83  nop     dword ptr [rax+rax+00h]
0x180002a88  mov     r9, [rbx+8]
0x180002a8c  lea     rdx, [rbx+18h]
0x180002a90  mov     [rsp+0A8h+arg_8], r9
0x180002a98  movzx   r13d, al
0x180002a9c  mov     [rsp+0A8h+arg_18], rsi
0x180002aa4  xor     edi, edi
0x180002aa6  mov     rcx, [rdx]
0x180002aa9  cmp     rcx, rdx
0x180002aac  jz      short loc_180002AED
0x180002aae  cmp     [rcx+8], rdx
0x180002ab2  jnz     loc_180002EC3
0x180002ab8  mov     rax, [rcx]
0x180002abb  cmp     [rax+8], rcx
0x180002abf  jnz     loc_180002EC3
0x180002ac5  mov     [rdx], rax
0x180002ac8  lea     rdi, [rcx-0A8h]
0x180002acf  mov     [rax+8], rdx
0x180002ad3  xor     eax, eax
0x180002ad5  xchg    rax, [rdi+68h]
0x180002ad9  test    rax, rax
0x180002adc  jz      loc_180002ECA
0x180002ae2  lock dec dword ptr [r12+10h]
0x180002ae8  test    rdi, rdi
0x180002aeb  jz      short loc_180002AA6
0x180002aed  test    rdi, rdi
0x180002af0  jnz     loc_180002BD3
0x180002af6  lea     edx, [rbp+14h]
0x180002af9  mov     ecx, 40h ; '@'
0x180002afe  mov     r8d, 43646948h
0x180002b04  call    cs:__imp_ExAllocatePool2
0x180002b0b  nop     dword ptr [rax+rax+00h]
0x180002b10  mov     rsi, rax
0x180002b13  test    rax, rax
0x180002b16  jz      loc_180002FA9
0x180002b1c  mov     r8, rbp; Size
0x180002b1f  mov     [rax+10h], ebp
0x180002b22  lea     rcx, [rax+14h]; void *
0x180002b26  mov     rdx, r14; Src
0x180002b29  call    memmove
0x180002b2e  mov     ecx, [rbx+5Ch]
0x180002b31  lea     rax, [rbx+28h]
0x180002b35  xor     r8d, r8d
0x180002b38  cmp     [rbx+58h], ecx
0x180002b3b  jb      short loc_180002B61
0x180002b3d  mov     r8, [rax]
0x180002b40  cmp     [r8+8], rax
0x180002b44  jnz     loc_180002EC3
0x180002b4a  mov     rcx, [r8]
0x180002b4d  cmp     [rcx+8], r8
0x180002b51  jnz     loc_180002EC3
0x180002b57  mov     [rax], rcx
0x180002b5a  mov     [rcx+8], rax
0x180002b5e  dec     dword ptr [rbx+58h]
0x180002b61  mov     rcx, [rax+8]
0x180002b65  cmp     [rcx], rax
0x180002b68  jnz     loc_180002EC3
0x180002b6e  mov     [rsi], rax
0x180002b71  mov     [rsi+8], rcx
0x180002b75  mov     [rcx], rsi
0x180002b78  mov     [rax+8], rsi
0x180002b7c  inc     dword ptr [rbx+58h]
0x180002b7f  test    r8, r8
0x180002b82  jz      short loc_180002B95
0x180002b84  xor     edx, edx; Tag
0x180002b86  mov     rcx, r8; P
0x180002b89  call    cs:__imp_ExFreePoolWithTag
0x180002b90  nop     dword ptr [rax+rax+00h]
0x180002b95  mov     esi, 103h
0x180002b9a  movzx   edx, r13b; NewIrql
0x180002b9e  mov     rcx, r15; SpinLock
0x180002ba1  call    cs:__imp_KeReleaseSpinLock
0x180002ba8  nop     dword ptr [rax+rax+00h]
0x180002bad  mov     rcx, [rsp+0A8h+arg_20]
0x180002bb5  mov     eax, esi
0x180002bb7  mov     rsi, [rsp+0A8h+arg_18]
0x180002bbf  mov     [rcx], rdi
0x180002bc2  add     rsp, 70h
0x180002bc6  pop     r15
0x180002bc8  pop     r14
0x180002bca  pop     r13
0x180002bcc  pop     r12
0x180002bce  pop     rdi
0x180002bcf  pop     rbp
0x180002bd0  pop     rbx
0x180002bd1  retn
0x180002bd3  mov     rcx, [rdi+8]; MemoryDescriptorList
0x180002bd7  test    rcx, rcx
0x180002bda  jz      loc_180002E2F
0x180002be0  test    byte ptr [rcx+0Ah], 5
0x180002be4  mov     rsi, [rdi+0B8h]
0x180002beb  jnz     loc_180002E0E
0x180002bf1  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x180002bf9  xor     r9d, r9d; RequestedAddress
0x180002bfc  xor     edx, edx; AccessMode
0x180002bfe  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x180002c06  mov     r8d, 1; CacheType
0x180002c0c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180002c13  nop     dword ptr [rax+rax+00h]
0x180002c18  mov     r9, [rsp+0A8h+arg_8]
0x180002c20  mov     [rsp+0A8h+var_48], rax
0x180002c25  test    rax, rax
0x180002c28  jz      loc_180002E2F
0x180002c2e  mov     rax, [rsp+0A8h+Src]
0x180002c36  mov     r12d, [rsi+8]
0x180002c3a  mov     esi, 0C000009Ch
0x180002c3f  mov     r14, [rbx+8]
0x180002c43  movzx   r9d, byte ptr [rax]
0x180002c47  lock inc dword ptr [rbx+0A4h]
0x180002c4e  mov     r8, [r14+0B0h]
0x180002c55  test    r8, r8
0x180002c58  jz      loc_180002E17
0x180002c5e  mov     edx, [r14+0B8h]
0x180002c65  xor     ecx, ecx
0x180002c67  cmp     ecx, edx
0x180002c69  jnb     loc_180002E17
0x180002c6f  movzx   eax, byte ptr [r8+rcx*8]
0x180002c74  lea     rbx, [r8+rcx*8]
0x180002c78  cmp     eax, r9d
0x180002c7b  jz      short loc_180002C81
0x180002c7d  inc     ecx
0x180002c7f  jmp     short loc_180002C67
0x180002c81  test    rbx, rbx
0x180002c84  jz      loc_180002E17
0x180002c8a  mov     r9, [r14+0A0h]
0x180002c91  xor     ebp, ebp
0x180002c93  movzx   r11d, byte ptr [rbx+1]
0x180002c98  test    r9, r9
0x180002c9b  jz      loc_180002EB3
0x180002ca1  mov     r10d, [r14+0A8h]
0x180002ca8  xor     edx, edx
0x180002caa  cmp     edx, r10d
0x180002cad  jnb     loc_180002EB3
0x180002cb3  lea     rcx, [rdx+rdx*4]
0x180002cb7  movzx   eax, byte ptr [r9+rcx*8+4]
0x180002cbd  lea     r8, [r9+rcx*8]
0x180002cc1  cmp     eax, r11d
0x180002cc4  jnz     loc_180002E00
0x180002cca  mov     rbp, r8
0x180002ccd  test    r8, r8
0x180002cd0  jz      loc_180002EB3
0x180002cd6  movzx   r10d, byte ptr [rbx+1]
0x180002cdb  xor     ebx, ebx
0x180002cdd  mov     r8, [r14+98h]
0x180002ce4  test    r8, r8
0x180002ce7  jz      loc_180002EA3
0x180002ced  mov     rax, cs:MmBadPointer
0x180002cf4  cmp     r8, [rax]
0x180002cf7  jz      loc_180002EA3
0x180002cfd  mov     r9d, [r14+0A8h]
0x180002d04  xor     edx, edx
0x180002d06  cmp     edx, r9d
0x180002d09  jnb     loc_180002EA3
0x180002d0f  mov     eax, edx
0x180002d11  imul    rax, 1A8h
0x180002d18  add     rax, r8
0x180002d1b  cmp     [rax], r10d
0x180002d1e  jnz     loc_180002E07
0x180002d24  mov     rbx, rax
0x180002d27  test    rax, rax
0x180002d2a  jz      loc_180002EA3
0x180002d30  test    rbp, rbp
0x180002d33  jz      short loc_180002D61
0x180002d35  test    rbx, rbx
0x180002d38  jz      short loc_180002D61
0x180002d3a  movzx   ebx, word ptr [rbp+14h]
0x180002d3e  cmp     r12d, ebx
0x180002d41  jb      loc_180002ED6
0x180002d47  mov     rdx, [rsp+0A8h+Src]; Src
0x180002d4f  mov     r8d, ebx; Size
0x180002d52  mov     rcx, [rsp+0A8h+var_48]; void *
0x180002d57  call    memmove
0x180002d5c  xor     esi, esi
0x180002d5e  mov     r12d, ebx
0x180002d61  mov     eax, r12d
0x180002d64  mov     [rdi+38h], rax
0x180002d68  mov     [rdi+30h], esi
0x180002d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d72  lea     rax, WPP_GLOBAL_Control
0x180002d79  cmp     rcx, rax
0x180002d7c  jz      short loc_180002D89
0x180002d7e  mov     eax, [rcx+2Ch]
0x180002d81  test    al, 10h
0x180002d83  jnz     loc_180002EE0
0x180002d89  xor     dl, dl
0x180002d8b  lea     rax, WPP_RECORDER_INITIALIZED
0x180002d92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180002d99  jz      short loc_180002DA6
0x180002d9b  cmp     word ptr [rcx+48h], 0
0x180002da0  jnz     loc_180002E27
0x180002da6  xor     r8b, r8b
0x180002da9  test    dl, dl
0x180002dab  jnz     loc_180002EF1
0x180002db1  test    r8b, r8b
0x180002db4  jnz     loc_180002EF1
0x180002dba  mov     rbx, [rsp+0A8h+arg_8]
0x180002dc2  mov     rax, [rsp+0A8h+arg_0]
0x180002dca  cmp     dword ptr [rax+0Ch], 2
0x180002dce  jnz     loc_180002B9A
0x180002dd4  test    esi, esi
0x180002dd6  jns     loc_180002B9A
0x180002ddc  movzx   r8d, word ptr [rbx+6Ch]; __annotation("Debug", "TelemetryAssert", "NT_SUCCESS(status)", "Keyboard report dropped due to failed buffer copy.")
0x180002de1  lea     r9, aKeyboardReport; "Keyboard report dropped due to failed b"...
0x180002de8  movzx   eax, word ptr [rbx+6Eh]
0x180002dec  mov     edx, r12d
0x180002def  shl     r8d, 10h
0x180002df3  or      r8d, eax
0x180002df6  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180002dfb  jmp     loc_180002B9A
0x180002e00  inc     edx
0x180002e02  jmp     loc_180002CAA
0x180002e07  inc     edx
0x180002e09  jmp     loc_180002D06
0x180002e0e  mov     rax, [rcx+18h]
0x180002e12  jmp     loc_180002C20
0x180002e17  mov     edx, r9d
0x180002e1a  mov     rcx, r14
0x180002e1d  call    TraceLoggingGetReportIdentifierFailed
0x180002e22  jmp     loc_180002D61
0x180002e27  mov     r8b, 1
0x180002e2a  jmp     loc_180002DA9
0x180002e2f  mov     esi, 0C00000E8h
0x180002e34  mov     [rdi+30h], esi
0x180002e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e3e  lea     rax, WPP_GLOBAL_Control
0x180002e45  cmp     rcx, rax
0x180002e48  jnz     loc_180002F3F
0x180002e4e  xor     dl, dl
0x180002e50  lea     rax, WPP_RECORDER_INITIALIZED
0x180002e57  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180002e5e  setnz   r8b
0x180002e62  test    dl, dl
0x180002e64  jnz     loc_180002F5B
0x180002e6a  test    r8b, r8b
0x180002e6d  jnz     loc_180002F5B
0x180002e73  cmp     dword ptr [r12+0Ch], 2
0x180002e79  jnz     loc_180002B9A
0x180002e7f  movzx   r8d, word ptr [r9+6Ch]; __annotation("Debug", "TelemetryAssert", "FALSE", "Keyboard report dropped due to invalid MdlAddress in read IRP.")
0x180002e84  mov     edx, ebp
0x180002e86  movzx   eax, word ptr [r9+6Eh]
0x180002e8b  lea     r9, aKeyboardReport_0; "Keyboard report dropped due to invalid "...
0x180002e92  shl     r8d, 10h
0x180002e96  or      r8d, eax
0x180002e99  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180002e9e  jmp     loc_180002B9A
0x180002ea3  mov     edx, r10d
0x180002ea6  mov     rcx, r14
0x180002ea9  call    TraceLoggingGetClassCollectionFailed
0x180002eae  jmp     loc_180002D30
0x180002eb3  mov     edx, r11d
0x180002eb6  mov     rcx, r14
0x180002eb9  call    TraceLoggingGetCollectionDescFailed
0x180002ebe  jmp     loc_180002CD6
0x180002ec3  mov     ecx, 3
0x180002ec8  int     29h; Win8: RtlFailFast(ecx)
0x180002eca  mov     [rcx+8], rcx
0x180002ece  mov     [rcx], rcx
0x180002ed1  jmp     loc_180002AA4
0x180002ed6  mov     esi, 0C0000206h
0x180002edb  jmp     loc_180002D5E
0x180002ee0  cmp     byte ptr [rcx+29h], 5
0x180002ee4  jb      loc_180002D89
0x180002eea  mov     dl, 1
0x180002eec  jmp     loc_180002D8B
0x180002ef1  mov     rbx, [rsp+0A8h+arg_8]
0x180002ef9  mov     rcx, [rcx+18h]
0x180002efd  mov     [rsp+0A8h+var_58], esi
0x180002f01  mov     [rsp+0A8h+var_60], rdi
0x180002f06  mov     rax, [rbx]
0x180002f09  mov     r9, [rbx+2B0h]
0x180002f10  mov     [rsp+0A8h+var_68], rax
0x180002f15  lea     rax, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x180002f1c  mov     [rsp+0A8h+var_70], rax
0x180002f21  mov     [rsp+0A8h+var_78], 13h
0x180002f28  mov     [rsp+0A8h+Priority], 5
0x180002f30  mov     byte ptr [rsp+0A8h+BugCheckOnFailure], 5
0x180002f35  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180002f3a  jmp     loc_180002DC2
0x180002f3f  mov     eax, [rcx+2Ch]
0x180002f42  test    al, 10h
0x180002f44  jz      loc_180002E4E
0x180002f4a  cmp     byte ptr [rcx+29h], 2
0x180002f4e  jb      loc_180002E4E
  ... truncated ...
```
