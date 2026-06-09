# _tlgWriteAgg

- ea: `0x18000ee04`
- end: `0x18000f272`
- name: `_tlgWriteAgg`
- size: `1134`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `12`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001208`
- `0x18000173c`
- `0x180001804`
- `0x1800018cc`
- `0x180001a30`
- `0x180001b3c`
- `0x180001d10`
- `0x180001f94`
- `0x180002520`
- `0x180021070`
- `0x18002c860`

## callees

- `0x18000ee04`
- `0x180014588`
- `0x18001f798`
- `0x18002f088`
- `0x18006bd68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000efca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000efca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f115`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f115`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f264`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f264`

## pseudocode

```c
__int64 __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR a5)
{
  unsigned __int8 v7; // r15
  unsigned int v9; // r12d
  ULONGLONG v10; // rax
  unsigned __int16 *v11; // rdx
  ULONG v12; // ecx
  ULONGLONG Ptr; // rax
  unsigned __int8 v14; // bp
  ULONGLONG v15; // r9
  char *v16; // rcx
  char v17; // al
  char v20; // r8
  char *v21; // rax
  UCHAR v22; // dl
  __int64 v23; // rbx
  signed __int64 v24; // rsi
  unsigned int v25; // edx
  unsigned __int64 i; // r8
  int v27; // eax
  unsigned __int8 v28; // r8
  unsigned __int64 k; // r9
  int v30; // eax
  unsigned int v31; // r13d
  int v32; // edx
  int v33; // r9d
  volatile signed __int64 *v34; // rdi
  volatile signed __int64 v35; // rbp
  __int64 v36; // r13
  int v37; // eax
  unsigned int v38; // eax
  unsigned int m; // edi
  __int64 v40; // rax
  __int64 v41; // r9
  signed __int64 v42; // r8
  __int64 v43; // rax
  int v44; // r10d
  volatile signed __int64 *v45; // rdx
  signed __int64 v46; // rax
  unsigned int v48; // eax
  unsigned int NewEventEntry; // eax
  volatile signed __int64 v50; // rtt
  unsigned int v51; // [rsp+34h] [rbp-64h]
  signed __int64 v52; // [rsp+38h] [rbp-60h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-58h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int8 v55; // [rsp+A0h] [rbp+8h]
  unsigned __int8 j; // [rsp+A8h] [rbp+10h]
  unsigned __int8 v57; // [rsp+C0h] [rbp+28h]

  v7 = 2;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  v9 = -1073741811;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v10;
  a5->Ptr = *(_QWORD *)(a1 + 8);
  v12 = **(unsigned __int16 **)(a1 + 8);
  a5[1].Ptr = (ULONGLONG)v11;
  a5->Size = v12;
  a5->Reserved = 2;
  a5[1].Size = *v11;
  a5[1].Reserved = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = a5[1].Ptr;
    v14 = 0;
    v15 = Ptr + a5[1].Size;
    v16 = (char *)(Ptr + 2);
    do
      v17 = *v16++;
    while ( v17 < 0 );
    while ( *v16++ )
      ;
    while ( (unsigned __int64)v16 < v15 )
    {
      while ( *v16++ )
        ;
      if ( *v16 >= 0 )
        break;
      v20 = *v16 & 0x7F;
      v21 = v16 + 1;
      v16 += 2;
      if ( *v21 >= 0 )
        break;
      while ( 1 )
      {
        v22 = *v16;
        if ( *v16 >= 0 )
          break;
        if ( v22 != 0x80 )
          goto LABEL_12;
        ++v16;
      }
      if ( v20 != 9 || (unsigned __int8)(v22 - 113) > 2u )
        break;
      v40 = v14++;
      a5[v40 + 2].Reserved1 = v22;
    }
LABEL_12:
    v57 = v14;
    if ( v14 )
    {
      v23 = *(_QWORD *)(a1 + 48);
      v24 = 0;
      v9 = 0;
      v52 = 0;
      v25 = 0;
      for ( i = 0; i < 8; ++i )
      {
        v27 = *((unsigned __int8 *)&a5[1].Ptr + i);
        v25 = (1025 * (v25 + v27)) ^ ((1025 * (v25 + v27)) >> 6);
      }
      v55 = v14 + 2;
      v28 = v14 + 2;
      for ( j = a4; v28 < a4; ++v28 )
      {
        for ( k = 0; k < a5[v28].Size; v25 = (1025 * (v25 + v30)) ^ ((1025 * (v25 + v30)) >> 6) )
          v30 = *(unsigned __int8 *)(a5[v28].Ptr + k++);
      }
      v31 = 32769 * ((9 * v25) ^ ((9 * v25) >> 11));
      SRWLock = (PSRWLOCK)(v23 + 264);
      v51 = v31;
      AcquireSRWLockShared((PSRWLOCK)(v23 + 264));
      v34 = (volatile signed __int64 *)(v23 + 8LL * (v31 & 0x1F));
      while ( 1 )
      {
        if ( !*v34 )
        {
          if ( *(_DWORD *)(v23 + 256) >= 0x400u )
          {
            ++*(_DWORD *)(v23 + 300);
            v9 = 234;
            goto LABEL_42;
          }
          if ( !v24 )
          {
            LOBYTE(v32) = j;
            LOBYTE(v33) = v14;
            NewEventEntry = CreateNewEventEntry(
                              (unsigned int)&EventDescriptor,
                              v32,
                              (_DWORD)a5,
                              v33,
                              v31,
                              (__int64)&v52);
            v24 = v52;
            v9 = NewEventEntry;
            if ( !v52 )
            {
              if ( NewEventEntry == 8 )
                ++*(_DWORD *)(v23 + 304);
              else
                ++*(_DWORD *)(v23 + 308);
              goto LABEL_42;
            }
          }
          if ( !_InterlockedCompareExchange64(v34, v24, 0) )
          {
            v24 = 0;
            if ( _InterlockedIncrement((volatile signed __int32 *)(v23 + 256)) == 1 )
              EnableFlushTimer(*(_QWORD *)(v23 + 344), *(unsigned int *)(v23 + 352));
            v48 = *(_DWORD *)(v23 + 256);
            if ( *(_DWORD *)(v23 + 288) < v48 )
              *(_DWORD *)(v23 + 288) = v48;
            goto LABEL_42;
          }
        }
        v35 = *v34;
        if ( v31 == *(_DWORD *)(*v34 + 40) )
        {
          v36 = *(_QWORD *)(v35 + 16);
          v37 = memcmp_0(&a5[1], (const void *)(v36 + 16), 8u);
          if ( !v37 )
          {
            v38 = j;
            for ( m = *(unsigned __int8 *)(v35 + 45) + 2; m < v38; ++m )
            {
              v37 = a5[m].Size - *(_DWORD *)(16LL * m + v36 + 8);
              if ( v37 )
                goto LABEL_28;
              v37 = memcmp_0((const void *)a5[m].Ptr, *(const void **)(16LL * m + v36), a5[m].Size);
              if ( v37 )
                goto LABEL_28;
              v38 = j;
            }
            v37 = 0;
          }
LABEL_28:
          v31 = v51;
        }
        else
        {
          v37 = v31 - *(_DWORD *)(v35 + 40);
        }
        if ( !v37 )
          break;
        v34 = (volatile signed __int64 *)(v35 + (((__int64)v37 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32);
        v14 = v57;
      }
      if ( v35 && v55 > 2u )
      {
        v41 = 2;
        do
        {
          v42 = *(_QWORD *)a5[v41].Ptr;
          v43 = *(_QWORD *)(v35 + 16);
          v44 = *(unsigned __int8 *)(v43 + 16 * v41 + 13);
          v45 = *(volatile signed __int64 **)(v43 + 16 * v41);
          if ( v44 == 113 )
          {
            _InterlockedAdd64(v45, v42);
          }
          else if ( (unsigned int)*(unsigned __int8 *)(v43 + 16 * v41 + 13) - 114 <= 1 )
          {
            do
            {
              v46 = *v45;
              if ( v44 == 114 )
              {
                if ( v42 >= v46 )
                  break;
              }
              else if ( v42 <= v46 )
              {
                break;
              }
              v50 = *v45;
            }
            while ( v50 != _InterlockedCompareExchange64(v45, v42, v46) );
          }
          ++v7;
          ++v41;
        }
        while ( v7 < v55 );
      }
LABEL_42:
      ReleaseSRWLockShared(SRWLock);
      if ( v24 )
        DestroyEventEntry(v24);
    }
    else
    {
      return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, a5);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000ee04  mov     [rsp+arg_10], rbx
0x18000ee09  push    rbp
0x18000ee0a  push    rsi
0x18000ee0b  push    rdi
0x18000ee0c  push    r12
0x18000ee0e  push    r13
0x18000ee10  push    r14
0x18000ee12  push    r15
0x18000ee14  sub     rsp, 60h
0x18000ee18  movzx   eax, byte ptr [rdx]
0x18000ee1b  mov     r10, rcx
0x18000ee1e  mov     r14, [rsp+98h+arg_20]
0x18000ee26  mov     r15d, 2
0x18000ee2c  shl     eax, 18h
0x18000ee2f  mov     r11d, r9d
0x18000ee32  mov     dword ptr [rsp+98h+EventDescriptor.Id], eax
0x18000ee36  mov     r12d, 0C000000Dh
0x18000ee3c  movzx   eax, word ptr [rdx+1]
0x18000ee40  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x18000ee44  lea     r13d, [r15-1]
0x18000ee48  mov     rax, [rdx+3]
0x18000ee4c  add     rdx, 0Bh
0x18000ee50  mov     [rsp+98h+EventDescriptor.Keyword], rax
0x18000ee55  mov     rax, [rcx+8]
0x18000ee59  mov     [r14], rax
0x18000ee5c  mov     rax, [rcx+8]
0x18000ee60  movzx   ecx, word ptr [rax]
0x18000ee63  mov     [r14+10h], rdx
0x18000ee67  mov     [r14+8], ecx
0x18000ee6b  mov     [r14+0Ch], r15d
0x18000ee6f  movzx   eax, word ptr [rdx]
0x18000ee72  lea     rdx, _TraceLoggingMetadata
0x18000ee79  mov     [r14+18h], eax
0x18000ee7d  lea     rax, _TraceLoggingMetadataEnd
0x18000ee84  sub     eax, edx
0x18000ee86  mov     [r14+1Ch], r13d
0x18000ee8a  mov     dword ptr [rsp+98h+arg_20], eax
0x18000ee91  mov     eax, dword ptr [rsp+98h+arg_20]
0x18000ee98  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000ee9f  cmp     [r10+28h], rax
0x18000eea3  jnz     loc_18000F124
0x18000eea9  mov     rax, [r14+10h]
0x18000eead  xor     bpl, bpl
0x18000eeb0  mov     r9d, [r14+18h]
0x18000eeb4  add     r9, rax
0x18000eeb7  lea     rcx, [rax+2]
0x18000eebb  movzx   eax, byte ptr [rcx]
0x18000eebe  add     rcx, r13
0x18000eec1  test    al, al
0x18000eec3  js      short loc_18000EEBB
0x18000eec5  mov     al, [rcx]
0x18000eec7  add     rcx, r13
0x18000eeca  test    al, al
0x18000eecc  jnz     short loc_18000EEC5
0x18000eece  cmp     rcx, r9
0x18000eed1  jnb     short loc_18000EF0A
0x18000eed3  mov     al, [rcx]
0x18000eed5  add     rcx, r13
0x18000eed8  test    al, al
0x18000eeda  jnz     short loc_18000EED3
0x18000eedc  mov     r8b, [rcx]
0x18000eedf  test    r8b, r8b
0x18000eee2  jns     short loc_18000EF0A
0x18000eee4  add     rcx, r13
0x18000eee7  and     r8b, 7Fh
0x18000eeeb  mov     rax, rcx
0x18000eeee  inc     rcx
0x18000eef1  cmp     byte ptr [rax], 0
0x18000eef4  jge     short loc_18000EF0A
0x18000eef6  mov     dl, [rcx]
0x18000eef8  test    dl, dl
0x18000eefa  jns     loc_18000F07F
0x18000ef00  cmp     dl, 80h
0x18000ef03  jnz     short loc_18000EF0A
0x18000ef05  add     rcx, r13
0x18000ef08  jmp     short loc_18000EEF6
0x18000ef0a  mov     byte ptr [rsp+98h+arg_20], bpl
0x18000ef12  test    bpl, bpl
0x18000ef15  jz      loc_18000F248
0x18000ef1b  mov     rbx, [r10+30h]
0x18000ef1f  xor     esi, esi
0x18000ef21  xor     r12d, r12d
0x18000ef24  mov     [rsp+98h+var_60], rsi
0x18000ef29  xor     edx, edx
0x18000ef2b  xor     r8d, r8d
0x18000ef2e  movzx   eax, byte ptr [r14+r8+10h]
0x18000ef34  add     r8, r13
0x18000ef37  add     eax, edx
0x18000ef39  imul    ecx, eax, 401h
0x18000ef3f  mov     edx, ecx
0x18000ef41  shr     edx, 6
0x18000ef44  xor     edx, ecx
0x18000ef46  cmp     r8, 8
0x18000ef4a  jb      short loc_18000EF2E
0x18000ef4c  lea     eax, [r15+rbp]
0x18000ef50  mov     dil, r11b
0x18000ef53  mov     [rsp+98h+arg_0], al
0x18000ef5a  mov     r8b, al
0x18000ef5d  mov     [rsp+98h+arg_8], edi
0x18000ef64  cmp     al, r11b
0x18000ef67  jnb     short loc_18000EFA5
0x18000ef69  movzx   eax, r8b
0x18000ef6d  xor     r9d, r9d
0x18000ef70  add     rax, rax
0x18000ef73  mov     r10d, [r14+rax*8+8]
0x18000ef78  mov     r11, [r14+rax*8]
0x18000ef7c  test    r10, r10
0x18000ef7f  jz      short loc_18000EF9D
0x18000ef81  movzx   eax, byte ptr [r11+r9]
0x18000ef86  add     r9, r13
0x18000ef89  add     eax, edx
0x18000ef8b  imul    ecx, eax, 401h
0x18000ef91  mov     edx, ecx
0x18000ef93  shr     edx, 6
0x18000ef96  xor     edx, ecx
0x18000ef98  cmp     r9, r10
0x18000ef9b  jb      short loc_18000EF81
0x18000ef9d  add     r8b, r13b
0x18000efa0  cmp     r8b, dil
0x18000efa3  jb      short loc_18000EF69
0x18000efa5  lea     eax, [rdx+rdx*8]
0x18000efa8  mov     ecx, eax
0x18000efaa  shr     ecx, 0Bh
0x18000efad  xor     ecx, eax
0x18000efaf  lea     rax, [rbx+108h]
0x18000efb6  imul    r13d, ecx, 8001h
0x18000efbd  mov     rcx, rax; SRWLock
0x18000efc0  mov     [rsp+98h+SRWLock], rax
0x18000efc5  mov     [rsp+98h+var_64], r13d
0x18000efca  call    cs:__imp_AcquireSRWLockShared
0x18000efd0  mov     eax, r13d
0x18000efd3  and     eax, 1Fh
0x18000efd6  lea     rdi, [rbx+rax*8]
0x18000efda  cmp     qword ptr [rdi], 0
0x18000efde  jz      loc_18000F14A
0x18000efe4  mov     rbp, [rdi]
0x18000efe7  cmp     r13d, [rbp+28h]
0x18000efeb  jnz     loc_18000F13F
0x18000eff1  mov     r13, [rbp+10h]
0x18000eff5  lea     rcx, [r14+10h]; Buf1
0x18000eff9  mov     r8d, 8; Size
0x18000efff  lea     rdx, [r13+10h]; Buf2
0x18000f003  call    memcmp_0
0x18000f008  test    eax, eax
0x18000f00a  jnz     short loc_18000F057
0x18000f00c  movzx   edi, byte ptr [rbp+2Dh]
0x18000f010  movzx   eax, byte ptr [rsp+98h+arg_8]
0x18000f018  add     edi, r15d
0x18000f01b  mov     [rsp+98h+var_68], eax
0x18000f01f  cmp     edi, eax
0x18000f021  jnb     loc_18000F1F6
0x18000f027  mov     ecx, edi
0x18000f029  shl     rcx, 4
0x18000f02d  mov     eax, [r14+rcx+8]
0x18000f032  sub     eax, [rcx+r13+8]
0x18000f037  jnz     short loc_18000F057
0x18000f039  mov     r8d, [r14+rcx+8]; Size
0x18000f03e  mov     rdx, [rcx+r13]; Buf2
0x18000f042  mov     rcx, [r14+rcx]; Buf1
0x18000f046  call    memcmp_0
0x18000f04b  test    eax, eax
0x18000f04d  jnz     short loc_18000F057
0x18000f04f  mov     eax, [rsp+98h+var_68]
0x18000f053  inc     edi
0x18000f055  jmp     short loc_18000F01F
0x18000f057  mov     r13d, [rsp+98h+var_64]
0x18000f05c  test    eax, eax
0x18000f05e  jz      short loc_18000F0A9
0x18000f060  movsxd  rdi, eax
0x18000f063  sar     rdi, 3Fh
0x18000f067  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18000f06b  add     rdi, 20h ; ' '
0x18000f06f  add     rdi, rbp
0x18000f072  mov     bpl, byte ptr [rsp+98h+arg_20]
0x18000f07a  jmp     loc_18000EFDA
0x18000f07f  cmp     r8b, 9
0x18000f083  jnz     loc_18000EF0A
0x18000f089  lea     eax, [rdx-71h]
0x18000f08c  cmp     al, r15b
0x18000f08f  ja      loc_18000EF0A
0x18000f095  movzx   eax, bpl
0x18000f099  add     rax, rax
0x18000f09c  add     bpl, r13b
0x18000f09f  mov     [r14+rax*8+2Dh], dl
0x18000f0a4  jmp     loc_18000EECE
0x18000f0a9  test    rbp, rbp
0x18000f0ac  jz      short loc_18000F110
0x18000f0ae  mov     r11b, [rsp+98h+arg_0]
0x18000f0b6  cmp     r11b, r15b
0x18000f0b9  jbe     short loc_18000F110
0x18000f0bb  mov     r9, r15
0x18000f0be  mov     rcx, r9
0x18000f0c1  add     rcx, rcx
0x18000f0c4  mov     rax, [r14+rcx*8]
0x18000f0c8  mov     r8, [rax]
0x18000f0cb  mov     rax, [rbp+10h]
0x18000f0cf  movzx   r10d, byte ptr [rax+rcx*8+0Dh]
0x18000f0d5  mov     rdx, [rax+rcx*8]
0x18000f0d9  mov     ecx, r10d
0x18000f0dc  sub     ecx, 71h ; 'q'
0x18000f0df  jz      loc_18000F232
0x18000f0e5  sub     ecx, 1
0x18000f0e8  jz      short loc_18000F0EF
0x18000f0ea  cmp     ecx, 1
0x18000f0ed  jnz     short loc_18000F105
0x18000f0ef  mov     rax, [rdx]
0x18000f0f2  cmp     r10d, 72h ; 'r'
0x18000f0f6  jnz     loc_18000F219
0x18000f0fc  cmp     r8, rax
0x18000f0ff  jl      loc_18000F222
0x18000f105  inc     r15b
0x18000f108  inc     r9
0x18000f10b  cmp     r15b, r11b
0x18000f10e  jb      short loc_18000F0BE
0x18000f110  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x18000f115  call    cs:__imp_ReleaseSRWLockShared
0x18000f11b  test    rsi, rsi
0x18000f11e  jnz     loc_18000F23B
0x18000f124  mov     rbx, [rsp+98h+arg_10]
0x18000f12c  mov     eax, r12d
0x18000f12f  add     rsp, 60h
0x18000f133  pop     r15
0x18000f135  pop     r14
0x18000f137  pop     r13
0x18000f139  pop     r12
0x18000f13b  pop     rdi
0x18000f13c  pop     rsi
0x18000f13d  pop     rbp
0x18000f13e  retn
0x18000f13f  mov     eax, r13d
0x18000f142  sub     eax, [rbp+28h]
0x18000f145  jmp     loc_18000F05C
0x18000f14a  cmp     dword ptr [rbx+100h], 400h
0x18000f154  jnb     loc_18000F208
0x18000f15a  test    rsi, rsi
0x18000f15d  jz      short loc_18000F1AF
0x18000f15f  xor     eax, eax
0x18000f161  lock cmpxchg [rdi], rsi
0x18000f166  jnz     loc_18000EFE4
0x18000f16c  xor     esi, esi
0x18000f16e  lea     eax, [rsi+1]
0x18000f171  lock xadd [rbx+100h], eax
0x18000f179  inc     eax
0x18000f17b  cmp     eax, 1
0x18000f17e  jnz     short loc_18000F192
0x18000f180  mov     edx, [rbx+160h]
0x18000f186  mov     rcx, [rbx+158h]
0x18000f18d  call    EnableFlushTimer
0x18000f192  mov     eax, [rbx+100h]
0x18000f198  cmp     [rbx+120h], eax
0x18000f19e  jnb     loc_18000F110
0x18000f1a4  mov     [rbx+120h], eax
0x18000f1aa  jmp     loc_18000F110
0x18000f1af  mov     dl, byte ptr [rsp+98h+arg_8]
0x18000f1b6  lea     rax, [rsp+98h+var_60]
0x18000f1bb  mov     [rsp+98h+UserData], rax
0x18000f1c0  lea     rcx, [rsp+98h+EventDescriptor]
0x18000f1c5  mov     r9b, bpl
0x18000f1c8  mov     [rsp+98h+UserDataCount], r13d
0x18000f1cd  mov     r8, r14
0x18000f1d0  call    CreateNewEventEntry
0x18000f1d5  mov     rsi, [rsp+98h+var_60]
0x18000f1da  mov     r12d, eax
0x18000f1dd  test    rsi, rsi
0x18000f1e0  jnz     loc_18000F15F
0x18000f1e6  cmp     eax, 8
0x18000f1e9  jnz     short loc_18000F1FD
0x18000f1eb  inc     dword ptr [rbx+130h]
0x18000f1f1  jmp     loc_18000F110
0x18000f1f6  xor     eax, eax
0x18000f1f8  jmp     loc_18000F057
0x18000f1fd  inc     dword ptr [rbx+134h]
0x18000f203  jmp     loc_18000F110
0x18000f208  inc     dword ptr [rbx+12Ch]
0x18000f20e  mov     r12d, 0EAh
0x18000f214  jmp     loc_18000F110
0x18000f219  cmp     r8, rax
0x18000f21c  jle     loc_18000F105
0x18000f222  lock cmpxchg [rdx], r8
0x18000f227  jnz     loc_18000F0EF
0x18000f22d  jmp     loc_18000F105
0x18000f232  lock add [rdx], r8
0x18000f236  jmp     loc_18000F105
0x18000f23b  mov     rcx, rsi
0x18000f23e  call    DestroyEventEntry
0x18000f243  jmp     loc_18000F124
0x18000f248  mov     rcx, [r10+20h]; RegHandle
0x18000f24c  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x18000f251  movzx   eax, r11b
0x18000f255  xor     r9d, r9d; RelatedActivityId
0x18000f258  mov     [rsp+98h+UserData], r14; UserData
0x18000f25d  xor     r8d, r8d; ActivityId
0x18000f260  mov     [rsp+98h+UserDataCount], eax; UserDataCount
0x18000f264  call    cs:__imp_EventWriteTransfer
0x18000f26a  mov     r12d, eax
0x18000f26d  jmp     loc_18000F124
```
