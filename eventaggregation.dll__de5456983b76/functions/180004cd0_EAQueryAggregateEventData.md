# EAQueryAggregateEventData

- ea: `0x180004cd0`
- end: `0x180005026`
- name: `EAQueryAggregateEventData`
- size: `854`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001730`
- `0x180004cd0`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x180004db1`
- `ntdll!RtlAcquireSRWLockShared` at `0x180004dff`
- `ntdll!RtlAcquireSRWLockShared` at `0x180004db1`
- `ntdll!RtlAcquireSRWLockShared` at `0x180004dff`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004df5`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004f1a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004f39`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004df5`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004f1a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004f39`
- `ntdll!RtlLookupEntryHashTable` at `0x180004dcd`
- `ntdll!RtlLookupEntryHashTable` at `0x180004dcd`
- `ntdll!RtlNtStatusToDosError` at `0x180005003`
- `ntdll!RtlNtStatusToDosError` at `0x180005003`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004d8a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004ffb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004d8a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004ffb`

## pseudocode

```c
ULONG __fastcall EAQueryAggregateEventData(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r11
  NTSTATUS v8; // ebx
  __int64 v9; // r11
  unsigned int v10; // r10d
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // r8d
  __int64 v15; // r9
  _DWORD *v16; // rdx
  _DWORD v18[2]; // [rsp+30h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-51h] BYREF
  char *v21; // [rsp+58h] [rbp-41h]
  int v22; // [rsp+60h] [rbp-39h]
  int v23; // [rsp+64h] [rbp-35h]
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+70h] [rbp-29h] BYREF
  char *v25; // [rsp+80h] [rbp-19h]
  int v26; // [rsp+88h] [rbp-11h]
  int v27; // [rsp+8Ch] [rbp-Dh]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+90h] [rbp-9h]
  __int64 v29; // [rsp+98h] [rbp-1h]
  _DWORD *v30; // [rsp+A0h] [rbp+7h]
  __int64 v31; // [rsp+A8h] [rbp+Fh]

  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v21 = byte_18000F645;
    UserData.Reserved = 2;
    v22 = 20;
    v23 = 1;
    v18[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( a1 && a2 )
  {
    RtlAcquireSRWLockShared(AggregateEventListLock, a2);
    if ( qword_180012148 )
    {
      v4 = RtlLookupEntryHashTable(qword_180012148, a1, 0);
      v5 = v4;
      if ( v4 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 136));
        RtlReleaseSRWLockShared(AggregateEventListLock);
        RtlAcquireSRWLockShared(v5 + 80, v6);
        v7 = *(_QWORD *)(v5 + 56);
        if ( v7 )
        {
          v9 = *(_QWORD *)(v7 + 8);
          v10 = 0;
          if ( v9 )
          {
            if ( *(_DWORD *)v9 != 1 )
            {
              v8 = -1073741595;
              goto LABEL_30;
            }
            v10 = *(_DWORD *)(v9 + 12);
            if ( v10 )
            {
              if ( v10 > *(_DWORD *)(a2 + 12) )
              {
                *(_DWORD *)(a2 + 12) = v10;
                v8 = -1073741789;
                goto LABEL_30;
              }
              if ( !*(_QWORD *)(a2 + 16) )
              {
                v8 = -1073741811;
                goto LABEL_30;
              }
            }
          }
          *(_QWORD *)(a2 + 32) = *(_QWORD *)(v5 + 24);
          *(_QWORD *)(a2 + 40) = *(_QWORD *)(v5 + 32);
          *(_QWORD *)(a2 + 48) = *(_QWORD *)(v5 + 72);
          *(_DWORD *)(a2 + 12) = v10;
          if ( v9 )
            v11 = *(_DWORD *)(v9 + 8);
          else
            v11 = 0;
          *(_DWORD *)(a2 + 24) = v11;
          v12 = **(_QWORD **)(v5 + 56);
          if ( v12 )
            v12 = *(_QWORD *)(v12 + 8);
          *(_QWORD *)a2 = v12;
          v13 = 0;
          *(_DWORD *)(a2 + 8) = 0;
          if ( (*(_BYTE *)(v5 + 140) & 1) != 0 )
          {
            *(_DWORD *)(a2 + 8) = 1;
            v13 = 1;
          }
          if ( (*(_BYTE *)(v5 + 140) & 2) != 0 )
            *(_DWORD *)(a2 + 8) = v13 | 2;
          v14 = 0;
          if ( !v10 )
          {
LABEL_29:
            v8 = 0;
            goto LABEL_30;
          }
          while ( 1 )
          {
            v15 = v14;
            v16 = (_DWORD *)(*(_QWORD *)(v9 + 16) + 56LL * v14);
            if ( *v16 )
              break;
            ++v14;
            *(_DWORD *)(*(_QWORD *)(a2 + 16) + 8 * v15) = v16[4];
            *(_DWORD *)(*(_QWORD *)(a2 + 16) + 8 * v15 + 4) = v16[5];
            if ( v14 >= v10 )
              goto LABEL_29;
          }
        }
        v8 = -1073741595;
LABEL_30:
        RtlReleaseSRWLockShared(v5 + 80);
        EaiReleaseAggregateEvent(v5);
        goto LABEL_33;
      }
    }
    RtlReleaseSRWLockShared(AggregateEventListLock);
    v8 = -1073741816;
  }
  else
  {
    v8 = -1073741811;
  }
LABEL_33:
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_QWORD *)&EventDescriptor.Id = a1;
    p_EventDescriptor = &EventDescriptor;
    v29 = 8;
    v30 = v18;
    v24.Ptr = (ULONGLONG)off_180012008;
    v18[0] = v8;
    v31 = 4;
    UserData.Ptr = 0x2040B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    v24.Size = *(unsigned __int16 *)off_180012008;
    v25 = byte_18000EE49;
    v24.Reserved = 2;
    v26 = 42;
    v27 = 1;
    v18[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v24);
  }
  return RtlNtStatusToDosError(v8);
}

```

## disassembly

```asm
0x180004cd0  push    rbp
0x180004cd2  push    rbx
0x180004cd3  push    rsi
0x180004cd4  push    r12
0x180004cd6  push    r13
0x180004cd8  push    r15
0x180004cda  lea     rbp, [rsp-2Fh]
0x180004cdf  sub     rsp, 0C8h
0x180004ce6  mov     rax, cs:__security_cookie
0x180004ced  xor     rax, rsp
0x180004cf0  mov     [rbp+57h+var_40], rax
0x180004cf4  mov     eax, cs:dword_180012000
0x180004cfa  lea     r15, _TraceLoggingMetadataEnd
0x180004d01  xor     r12d, r12d
0x180004d04  lea     r13, _TraceLoggingMetadata
0x180004d0b  mov     rbx, rdx
0x180004d0e  mov     rsi, rcx
0x180004d11  cmp     eax, 4
0x180004d14  jbe     short loc_180004D90
0x180004d16  movzx   eax, cs:word_18000F63B
0x180004d1d  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180004d21  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180004d24  xor     r9d, r9d; RelatedActivityId
0x180004d27  mov     rax, cs:off_180012008
0x180004d2e  xor     r8d, r8d; ActivityId
0x180004d31  mov     [rbp+57h+var_A8.Ptr], rax
0x180004d35  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180004d3c  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x180004d40  movzx   eax, word ptr [rax]
0x180004d43  mov     [rbp+57h+var_A8.Size], eax
0x180004d46  lea     rax, byte_18000F645
0x180004d4d  mov     [rbp+57h+var_98], rax
0x180004d51  mov     rax, r15
0x180004d54  sub     eax, r13d
0x180004d57  mov     dword ptr [rbp+57h+var_A8.0Ch], 2
0x180004d5e  mov     [rbp+57h+var_90], 14h
0x180004d65  mov     [rbp+57h+var_8C], 1
0x180004d6c  mov     [rbp+57h+var_C0], eax
0x180004d6f  mov     eax, [rbp+57h+var_C0]
0x180004d72  mov     rcx, cs:RegHandle; RegHandle
0x180004d79  lea     rax, [rbp+57h+var_A8]
0x180004d7d  mov     [rsp+0F0h+UserData], rax; UserData
0x180004d82  mov     [rsp+0F0h+UserDataCount], 2; UserDataCount
0x180004d8a  call    cs:__imp_EventWriteTransfer
0x180004d90  mov     [rsp+0F0h+arg_10], rdi
0x180004d98  test    rsi, rsi
0x180004d9b  jz      loc_180004F46
0x180004da1  test    rbx, rbx
0x180004da4  jz      loc_180004F46
0x180004daa  lea     rcx, AggregateEventListLock
0x180004db1  call    cs:__imp_RtlAcquireSRWLockShared
0x180004db7  mov     rcx, cs:qword_180012148
0x180004dbe  test    rcx, rcx
0x180004dc1  jz      loc_180004F32
0x180004dc7  xor     r8d, r8d
0x180004dca  mov     rdx, rsi
0x180004dcd  call    cs:__imp_RtlLookupEntryHashTable
0x180004dd3  mov     rdi, rax
0x180004dd6  test    rax, rax
0x180004dd9  jz      loc_180004F32
0x180004ddf  mov     [rsp+0F0h+var_30], r14
0x180004de7  lock inc dword ptr [rax+88h]
0x180004dee  lea     rcx, AggregateEventListLock
0x180004df5  call    cs:__imp_RtlReleaseSRWLockShared
0x180004dfb  lea     rcx, [rdi+50h]
0x180004dff  call    cs:__imp_RtlAcquireSRWLockShared
0x180004e05  mov     r11, [rdi+38h]
0x180004e09  test    r11, r11
0x180004e0c  jnz     short loc_180004E18
0x180004e0e  mov     ebx, 0C00000E5h
0x180004e13  jmp     loc_180004F16
0x180004e18  mov     r11, [r11+8]
0x180004e1c  mov     r10d, r12d
0x180004e1f  test    r11, r11
0x180004e22  jz      short loc_180004E61
0x180004e24  cmp     dword ptr [r11], 1
0x180004e28  jz      short loc_180004E34
0x180004e2a  mov     ebx, 0C00000E5h
0x180004e2f  jmp     loc_180004F16
0x180004e34  mov     r10d, [r11+0Ch]
0x180004e38  test    r10d, r10d
0x180004e3b  jz      short loc_180004E61
0x180004e3d  cmp     r10d, [rbx+0Ch]
0x180004e41  jbe     short loc_180004E51
0x180004e43  mov     [rbx+0Ch], r10d
0x180004e47  mov     ebx, 0C0000023h
0x180004e4c  jmp     loc_180004F16
0x180004e51  cmp     [rbx+10h], r12
0x180004e55  jnz     short loc_180004E61
0x180004e57  mov     ebx, 0C000000Dh
0x180004e5c  jmp     loc_180004F16
0x180004e61  mov     rax, [rdi+18h]
0x180004e65  mov     [rbx+20h], rax
0x180004e69  mov     rax, [rdi+20h]
0x180004e6d  mov     [rbx+28h], rax
0x180004e71  mov     rax, [rdi+48h]
0x180004e75  mov     [rbx+30h], rax
0x180004e79  mov     [rbx+0Ch], r10d
0x180004e7d  test    r11, r11
0x180004e80  jz      short loc_180004E88
0x180004e82  mov     eax, [r11+8]
0x180004e86  jmp     short loc_180004E8B
0x180004e88  mov     eax, r12d
0x180004e8b  mov     [rbx+18h], eax
0x180004e8e  mov     rax, [rdi+38h]
0x180004e92  mov     rax, [rax]
0x180004e95  test    rax, rax
0x180004e98  jz      short loc_180004E9E
0x180004e9a  mov     rax, [rax+8]
0x180004e9e  mov     [rbx], rax
0x180004ea1  mov     eax, r12d
0x180004ea4  mov     [rbx+8], r12d
0x180004ea8  test    byte ptr [rdi+8Ch], 1
0x180004eaf  jz      short loc_180004EBD
0x180004eb1  mov     dword ptr [rbx+8], 1
0x180004eb8  mov     eax, 1
0x180004ebd  test    byte ptr [rdi+8Ch], 2
0x180004ec4  jz      short loc_180004ECC
0x180004ec6  or      eax, 2
0x180004ec9  mov     [rbx+8], eax
0x180004ecc  mov     r8d, r12d
0x180004ecf  test    r10d, r10d
0x180004ed2  jz      short loc_180004F13
0x180004ed4  nop     dword ptr [rax+00h]
0x180004ed8  nop     dword ptr [rax+rax+00000000h]
0x180004ee0  mov     r9d, r8d
0x180004ee3  imul    rdx, r9, 38h ; '8'
0x180004ee7  add     rdx, [r11+10h]
0x180004eeb  cmp     [rdx], r12d
0x180004eee  jnz     loc_180004E0E
0x180004ef4  mov     rcx, [rbx+10h]
0x180004ef8  inc     r8d
0x180004efb  mov     eax, [rdx+10h]
0x180004efe  mov     [rcx+r9*8], eax
0x180004f02  mov     rcx, [rbx+10h]
0x180004f06  mov     eax, [rdx+14h]
0x180004f09  mov     [rcx+r9*8+4], eax
0x180004f0e  cmp     r8d, r10d
0x180004f11  jb      short loc_180004EE0
0x180004f13  mov     ebx, r12d
0x180004f16  lea     rcx, [rdi+50h]
0x180004f1a  call    cs:__imp_RtlReleaseSRWLockShared
0x180004f20  mov     rcx, rdi
0x180004f23  call    EaiReleaseAggregateEvent
0x180004f28  mov     r14, [rsp+0F0h+var_30]
0x180004f30  jmp     short loc_180004F4B
0x180004f32  lea     rcx, AggregateEventListLock
0x180004f39  call    cs:__imp_RtlReleaseSRWLockShared
0x180004f3f  mov     ebx, 0C0000008h
0x180004f44  jmp     short loc_180004F4B
0x180004f46  mov     ebx, 0C000000Dh
0x180004f4b  mov     eax, cs:dword_180012000
0x180004f51  mov     rdi, [rsp+0F0h+arg_10]
0x180004f59  cmp     eax, 4
0x180004f5c  jbe     loc_180005001
0x180004f62  mov     qword ptr [rbp+57h+EventDescriptor.Id], rsi
0x180004f66  lea     rax, [rbp+57h+EventDescriptor]
0x180004f6a  mov     [rbp+57h+var_60], rax
0x180004f6e  lea     rdx, [rbp+57h+var_A8]; EventDescriptor
0x180004f72  lea     rax, [rbp+57h+var_C0]
0x180004f76  mov     [rbp+57h+var_58], 8
0x180004f7e  mov     [rbp+57h+var_50], rax
0x180004f82  sub     r15d, r13d
0x180004f85  movzx   eax, cs:word_18000EE3F
0x180004f8c  xor     r9d, r9d; RelatedActivityId
0x180004f8f  mov     dword ptr [rbp+57h+var_A8.Ptr+4], eax
0x180004f92  xor     r8d, r8d; ActivityId
0x180004f95  mov     rax, cs:off_180012008
0x180004f9c  mov     [rbp+57h+var_80.Ptr], rax
0x180004fa0  mov     [rbp+57h+var_C0], ebx
0x180004fa3  mov     [rbp+57h+var_48], 4
0x180004fab  mov     dword ptr [rbp+57h+var_A8.Ptr], 0B000000h
0x180004fb2  mov     qword ptr [rbp+57h+var_A8.Size], r12
0x180004fb6  movzx   eax, word ptr [rax]
0x180004fb9  mov     [rbp+57h+var_80.Size], eax
0x180004fbc  lea     rax, byte_18000EE49
0x180004fc3  mov     [rbp+57h+var_70], rax
0x180004fc7  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180004fce  mov     [rbp+57h+var_68], 2Ah ; '*'
0x180004fd5  mov     [rbp+57h+var_64], 1
0x180004fdc  mov     [rbp+57h+var_BC], r15d
0x180004fe0  mov     eax, [rbp+57h+var_BC]
0x180004fe3  mov     rcx, cs:RegHandle; RegHandle
0x180004fea  lea     rax, [rbp+57h+var_80]
0x180004fee  mov     [rsp+0F0h+UserData], rax; UserData
0x180004ff3  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x180004ffb  call    cs:__imp_EventWriteTransfer
0x180005001  mov     ecx, ebx; Status
0x180005003  call    cs:__imp_RtlNtStatusToDosError
0x180005009  mov     rcx, [rbp+57h+var_40]
0x18000500d  xor     rcx, rsp; StackCookie
0x180005010  call    __security_check_cookie
0x180005015  add     rsp, 0C8h
0x18000501c  pop     r15
0x18000501e  pop     r13
0x180005020  pop     r12
0x180005022  pop     rsi
0x180005023  pop     rbx
0x180005024  pop     rbp
0x180005025  retn
```
