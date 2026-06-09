# RtlpLowFragHeapFlushCaches

- ea: `0x18003ee4c`
- end: `0x18003f5a7`
- name: `RtlpLowFragHeapFlushCaches`
- size: `1883`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003e93c`

## callees

- `0x1800370b0`
- `0x18003d5f0`
- `0x18003e370`
- `0x18003ee4c`
- `0x18003f5b0`
- `0x18003f700`
- `0x18003f734`
- `0x18003f7f4`
- `0x1800526f0`
- `0x180064b60`
- `0x1800a8f34`
- `0x18011c718`
- `0x18015ecd0`
- `0x180162080`
- `0x1801620c0`

## pseudocode

```c
struct _PEB *__fastcall RtlpLowFragHeapFlushCaches(__int64 a1, __int64 a2, __int64 *a3, __int64 i)
{
  __int64 v5; // rdx
  __int64 v6; // r12
  unsigned int v7; // r15d
  __int64 v8; // rbx
  __int64 v9; // rdi
  int v10; // ebx
  struct _PEB *result; // rax
  struct _PEB *v12; // rsi
  struct _PEB *v13; // rbp
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // r15
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rdi
  __int64 v23; // rdx
  int v24; // eax
  _QWORD **v25; // rbx
  _QWORD *v26; // r14
  unsigned int v27; // ebp
  __int64 v28; // rsi
  unsigned int v29; // ecx
  __int64 v30; // rdx
  __int64 v31; // rcx
  char *v32; // rdx
  int CurrentServiceSessionId; // eax
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  signed __int32 v37; // esi
  _WORD *v38; // rcx
  int v39; // edi
  unsigned int v40; // ebp
  signed __int32 v41; // eax
  __int64 v42; // rcx
  volatile signed __int32 *v43; // rdx
  __int64 v44; // rcx
  _QWORD **v45; // rdx
  signed __int64 v46; // rdx
  __int64 *v47; // rsi
  volatile signed __int32 *v48; // rdi
  signed __int32 v49; // eax
  __int64 v50; // rax
  unsigned __int16 *v51; // rsi
  __int64 v52; // rdi
  __int64 v53; // rax
  unsigned __int16 ReservedBlockSize; // ax
  __int64 v55; // rcx
  unsigned int HeapProtection; // eax
  signed __int64 v57; // rcx
  __int64 v58; // rcx
  volatile signed __int32 *v59; // rdx
  _QWORD *v60; // rax
  unsigned int v61; // edx
  __int64 v62; // rcx
  signed __int64 v63; // [rsp+30h] [rbp-58h]
  unsigned __int64 v64[10]; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v65; // [rsp+90h] [rbp+8h]
  __int64 v66; // [rsp+90h] [rbp+8h]
  __int64 v67; // [rsp+98h] [rbp+10h] BYREF
  __int64 v68; // [rsp+A0h] [rbp+18h]
  unsigned __int64 v69; // [rsp+A8h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  v68 = 0;
  do
  {
    v7 = 0;
    if ( (*(_BYTE *)(a1 + 4 * v5 + 679) & 1) != 0 )
    {
      v24 = RtlpAffinityState;
      if ( (*(_BYTE *)(a1 + 672) & 1) != 0 )
        v24 = 1;
      v65 = v24;
      if ( !v24 )
        goto LABEL_9;
    }
    else
    {
      v65 = 1;
    }
    do
    {
      if ( v7 )
        v8 = *(_QWORD *)(a1 + 8 * v5 + 2224) + 192LL * v7 - 192;
      else
        v8 = *(_QWORD *)(a1 + 8 * v5 + 1192);
      if ( v8 && *(_DWORD *)(v8 + 164) == 1 )
      {
        v21 = RtlpLocalInfoAllocFromCache((unsigned __int16 *)v8, v7);
        v22 = v21;
        if ( v21 )
        {
          *(_DWORD *)(*(_QWORD *)v8 + 36LL) = 0;
          v23 = *(_QWORD *)(a1 + 24);
          if ( (unsigned __int16)RtlpLFHKey ^ (unsigned __int16)(v23 ^ *(_WORD *)(v21 + 8) ^ (v21 >> 4))
            || (v25 = *(_QWORD ***)(v21
                                  - ((unsigned __int64)((unsigned int)RtlpLFHKey
                                                      ^ (unsigned int)v23
                                                      ^ *(_DWORD *)(v21 + 8)
                                                      ^ (unsigned int)(v21 >> 4)) >> 12))) == 0 )
          {
            RtlpLogHeapFailure(3, v23, v21, 0, 0, 0);
          }
          else
          {
            _m_prefetchw(v25);
            v26 = v25[1];
            v27 = (unsigned __int16)(*(_DWORD *)(v21 + 12) >> 8);
            v28 = *(_QWORD *)(**v25 + 24LL);
            v29 = RtlpLFHKey ^ v28 ^ *((_DWORD *)v26 + 6) ^ (unsigned int)v26;
            v30 = (unsigned __int16)v29;
            v31 = v27 * HIWORD(v29);
            v32 = (char *)v26 + v31 + v30;
            if ( v32 == (char *)v21 )
            {
              CurrentServiceSessionId = RtlGetCurrentServiceSessionId(v31, v32, (unsigned int)RtlpLFHKey, i);
              i = 0;
              if ( CurrentServiceSessionId )
                v34 = (__int64)NtCurrentPeb()->SharedData + 550;
              else
                v34 = 2147353472;
              if ( *(_BYTE *)v34 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
              {
                RtlpLogHeapFreeEvent(*(_QWORD *)(v28 + 24), v22 + 16, 2, 0);
                i = 0;
              }
              v35 = 0;
              v36 = MEMORY[0x7FFE036A] > 1u ? 0x64 : 0;
              while ( (unsigned int)v35 <= (unsigned int)v36 )
              {
                v37 = *((_DWORD *)v25 + 8);
                if ( v37 >= 0
                  && _InterlockedCompareExchange((volatile signed __int32 *)v25 + 8, v37 | 0x80000000, v37) == v37 )
                {
                  goto LABEL_43;
                }
                v35 = (unsigned int)(v35 + 1);
              }
              v37 = -1;
LABEL_43:
              *(_BYTE *)(v22 + 15) = 0x80;
              v38 = v25 + 2;
              if ( v37 == -1 )
              {
                RtlpInterlockedPushEntrySList(v38, v22 + 16);
              }
              else
              {
                v39 = 0;
                _bittestandreset((signed __int32 *)v26[5], v27);
                if ( *v38 )
                {
                  v60 = (_QWORD *)RtlpInterlockedFlushSList(v38, v35, v36, 0);
                  while ( v60 )
                  {
                    v61 = *((_DWORD *)v60 - 1);
                    v60 = (_QWORD *)*v60;
                    v27 = (unsigned __int16)(v61 >> 8);
                    _bittestandreset((signed __int32 *)v26[5], v27);
                    ++v39;
                  }
                }
                a3 = *v25;
                v40 = v27 << 16;
                if ( ((unsigned __int16)v40 | (unsigned __int16)(v39 + v37 + 1)) != *((_WORD *)v25 + 20)
                  || (i = *((unsigned int *)a3 + 42), v46 = *(unsigned int *)(*a3 + 32), *((_DWORD *)a3 + 41) == 1)
                  && (unsigned int)v46 >= (unsigned int)i
                  && (v46 = (unsigned int)(v46 - i), (unsigned int)v46 < *(_DWORD *)(*a3 + 36)) )
                {
                  *((_DWORD *)v25 + 8) = v40 | (v39 + (unsigned __int16)v37 + 1);
                  if ( (*((_DWORD *)v25 + 11) & 2) == 0 && (unsigned __int8)RtlpIsSubSegmentReuseable(a3, v25) )
                  {
                    while ( 1 )
                    {
                      v41 = *((_DWORD *)v25 + 11);
                      if ( !v41 || (v41 & 2) != 0 )
                        break;
                      if ( v41 == _InterlockedCompareExchange((volatile signed __int32 *)v25 + 11, v41 | 2, v41) )
                      {
                        a3 = *v25;
                        for ( i = 0; ; i = (unsigned int)(i + 1) )
                        {
                          if ( (unsigned int)i >= 0x10 )
                          {
                            v44 = *(_QWORD *)(*(_QWORD *)(**v25 + 24LL) + 8LL * *((unsigned __int16 *)*v25 + 86) + 1192)
                                + 144LL;
                            goto LABEL_79;
                          }
                          v42 = ((_BYTE)i + (unsigned __int8)*((_WORD *)a3 + 87)) & 0xF;
                          v43 = (volatile signed __int32 *)a3[v42 + 2];
                          if ( v43 )
                          {
                            if ( (v43[11] & 1) == 0
                              && v43 == (volatile signed __int32 *)_InterlockedCompareExchange64(
                                                                     &a3[v42 + 2],
                                                                     (signed __int64)v25,
                                                                     (signed __int64)v43) )
                            {
                              _m_prefetchw((const void *)(v43 + 11));
                              if ( _InterlockedAnd(v43 + 11, 0xFFFFFFFD) != 2 )
                                goto LABEL_27;
                              v44 = **(_QWORD **)v43;
                              *(_QWORD *)v43 = 0;
                              v45 = (_QWORD **)(v43 + 12);
                              goto LABEL_80;
                            }
                          }
                          else if ( !_InterlockedCompareExchange64(&a3[v42 + 2], (signed __int64)v25, 0) )
                          {
                            goto LABEL_27;
                          }
                        }
                      }
                    }
                  }
                }
                else
                {
                  v47 = *v25;
                  v48 = (volatile signed __int32 *)_InterlockedExchange64(*v25 + 1, 0);
                  if ( v48 )
                  {
                    _m_prefetchw((const void *)(v48 + 11));
                    if ( _InterlockedAnd(v48 + 11, 0xFFFFFFF9) == 6 )
                    {
                      v58 = **(_QWORD **)v48;
                      *(_QWORD *)v48 = 0;
LABEL_86:
                      v59 = v48 + 12;
LABEL_87:
                      RtlpInterlockedPushEntrySList(v58, v59);
                    }
                    else if ( (unsigned __int8)RtlpIsSubSegmentReuseable(v47, v48) )
                    {
                      while ( 1 )
                      {
                        v49 = *((_DWORD *)v48 + 11);
                        if ( !v49 || (v49 & 2) != 0 )
                          break;
                        if ( v49 == _InterlockedCompareExchange(v48 + 11, v49 | 2, v49) )
                        {
                          a3 = *(__int64 **)v48;
                          for ( i = 0; ; i = (unsigned int)(i + 1) )
                          {
                            if ( (unsigned int)i >= 0x10 )
                            {
                              v58 = *(_QWORD *)(*(_QWORD *)(**(_QWORD **)v48 + 24LL)
                                              + 8LL * *(unsigned __int16 *)(*(_QWORD *)v48 + 172LL)
                                              + 1192)
                                  + 144LL;
                              goto LABEL_86;
                            }
                            v62 = ((_BYTE)i + (unsigned __int8)*((_WORD *)a3 + 87)) & 0xF;
                            v46 = a3[v62 + 2];
                            if ( v46 )
                            {
                              if ( (*(_DWORD *)(v46 + 44) & 1) == 0
                                && v46 == _InterlockedCompareExchange64(&a3[v62 + 2], (signed __int64)v48, v46) )
                              {
                                _m_prefetchw((const void *)(v46 + 44));
                                if ( _InterlockedAnd((volatile signed __int32 *)(v46 + 44), 0xFFFFFFFD) != 2 )
                                  goto LABEL_73;
                                v58 = **(_QWORD **)v46;
                                *(_QWORD *)v46 = 0;
                                v59 = (volatile signed __int32 *)(v46 + 48);
                                goto LABEL_87;
                              }
                            }
                            else if ( !_InterlockedCompareExchange64(&a3[v62 + 2], (signed __int64)v48, 0) )
                            {
                              goto LABEL_73;
                            }
                          }
                        }
                      }
                    }
                  }
LABEL_73:
                  v50 = *v47;
                  v51 = (unsigned __int16 *)*v25;
                  v52 = *(_QWORD *)(v50 + 24);
                  if ( (*((_BYTE *)v25 + 38) & 3) != 0 )
                  {
                    v53 = (__int64)v25[1] + 4151;
                    v69 = 0;
                    LODWORD(v67) = 0;
                    v64[0] = v53 & 0xFFFFFFFFFFFFF000uLL;
                    ReservedBlockSize = RtlpGetReservedBlockSize(v25, v46, a3, i);
                    v55 = *(_QWORD *)(v52 + 24);
                    v69 = 16 * ReservedBlockSize * (unsigned __int64)*((unsigned __int16 *)v25 + 20);
                    HeapProtection = RtlpGetHeapProtection(v55, 1);
                    ZwProtectVirtualMemory(-1, v64, &v69, HeapProtection, &v67);
                  }
                  *((_DWORD *)v25[1] + 5) = 0;
                  RtlpFreeUserBlock(v52, v25[1], a3, i);
                  a3 = (__int64 *)(unsigned int)-*((unsigned __int16 *)v25 + 20);
                  do
                  {
                    v57 = *((_QWORD *)v51 + 20);
                    LODWORD(v63) = v57 + (_DWORD)a3;
                    HIDWORD(v63) = HIDWORD(v57) - 1;
                  }
                  while ( _InterlockedCompareExchange64((volatile signed __int64 *)v51 + 20, v63, v57) != v57 );
                  v25[1] = 0;
                  _InterlockedAdd((volatile signed __int32 *)(v52 + 60), 1u);
                  *((_DWORD *)v25 + 8) = 0;
                  _m_prefetchw((char *)v25 + 44);
                  if ( _InterlockedAnd((volatile signed __int32 *)v25 + 11, 0xFFFFFFFE) == 1 )
                  {
                    v44 = **v25;
                    *v25 = 0;
LABEL_79:
                    v45 = v25 + 6;
LABEL_80:
                    RtlpInterlockedPushEntrySList(v44, v45);
                  }
                }
              }
            }
            else
            {
              RtlpLogHeapFailure(3, *(_QWORD *)(v28 + 24), v21, 0, 0, 0);
            }
          }
        }
LABEL_27:
        v5 = v68;
      }
      ++v7;
    }
    while ( v7 < v65 );
LABEL_9:
    v68 = ++v5;
  }
  while ( v5 != 129 );
  v9 = 0;
  v66 = 0;
  do
  {
    v10 = 0;
    v67 = a1 + 48 * v9 + 96;
    result = (struct _PEB *)RtlpInterlockedFlushSList(v67, v5, a3, i);
    v12 = result;
    if ( result )
    {
      do
      {
        v13 = v12;
        v12 = *(struct _PEB **)&v12->InheritedAddressSpace;
        v14 = 1LL << LOBYTE(v13->ImageBaseAddress);
        if ( v14 > 0xF0000 )
          v14 = 983040;
        v15 = v14 + WORD1(v13->ImageBaseAddress);
        v6 += v15;
        RtlpFreeUserBlockToHeap(*(_QWORD *)(a1 + 24), v13);
        ++v10;
        result = (struct _PEB *)RtlGetCurrentServiceSessionId(v17, v16, v18, v19);
        if ( (_DWORD)result )
        {
          result = NtCurrentPeb();
          v20 = (__int64)result->SharedData + 550;
        }
        else
        {
          v20 = 2147353472;
        }
        if ( *(_BYTE *)v20 )
        {
          result = NtCurrentPeb();
          if ( (result->TracingFlags & 1) != 0 )
          {
            RtlpLogHeapSubSegmentAllocCached(*(_QWORD *)(a1 + 24), v13, v15, 0);
            result = (struct _PEB *)RtlpLogHeapSubSegmentFree(*(_QWORD *)(a1 + 24), (_DWORD)v13, v15, 0, 1);
          }
        }
      }
      while ( v12 );
      v9 = v66;
      if ( v10 )
        _InterlockedAdd((volatile signed __int32 *)(v67 + 16), -v10);
    }
    v66 = ++v9;
  }
  while ( v9 != 12 );
  if ( v6 )
    _InterlockedAdd64((volatile signed __int64 *)(a1 + 72), -v6);
  return result;
}

```

## disassembly

```asm
0x18003ee4c  push    rbx
0x18003ee4e  push    rbp
0x18003ee4f  push    rsi
0x18003ee50  push    rdi
0x18003ee51  push    r12
0x18003ee53  push    r13
0x18003ee55  push    r14
0x18003ee57  push    r15
0x18003ee59  sub     rsp, 48h
0x18003ee5d  xor     ebp, ebp
0x18003ee5f  mov     r13, rcx
0x18003ee62  mov     edx, ebp
0x18003ee64  mov     r12d, ebp
0x18003ee67  mov     [rsp+88h+arg_10], rdx
0x18003ee6f  lea     r14d, [rbp+1]
0x18003ee73  mov     al, [r13+rdx*4+2A7h]
0x18003ee7b  mov     r15d, ebp
0x18003ee7e  test    r14b, al
0x18003ee81  jnz     loc_18003F013
0x18003ee87  mov     dword ptr [rsp+88h+arg_0], r14d
0x18003ee8f  test    r15d, r15d
0x18003ee92  jnz     loc_18003F576
0x18003ee98  mov     rbx, [r13+rdx*8+4A8h]
0x18003eea0  test    rbx, rbx
0x18003eea3  jz      short loc_18003EEB4
0x18003eea5  mov     eax, [rbx+0A4h]
0x18003eeab  cmp     eax, r14d
0x18003eeae  jz      loc_18003EFB5
0x18003eeb4  add     r15d, r14d
0x18003eeb7  cmp     r15d, dword ptr [rsp+88h+arg_0]
0x18003eebf  jb      short loc_18003EE8F
0x18003eec1  inc     rdx
0x18003eec4  mov     [rsp+88h+arg_10], rdx
0x18003eecc  cmp     rdx, 81h
0x18003eed3  jnz     short loc_18003EE73
0x18003eed5  mov     rdi, rbp
0x18003eed8  mov     [rsp+88h+arg_0], rbp
0x18003eee0  lea     r14, [rdi+rdi*2]
0x18003eee4  mov     ebx, ebp
0x18003eee6  shl     r14, 4
0x18003eeea  add     r14, 60h ; '`'
0x18003eeee  add     r14, r13
0x18003eef1  mov     rcx, r14
0x18003eef4  mov     [rsp+88h+arg_8], r14
0x18003eefc  call    RtlpInterlockedFlushSList
0x18003ef01  mov     rsi, rax
0x18003ef04  test    rax, rax
0x18003ef07  jz      short loc_18003EF81
0x18003ef09  mov     edi, 0F0000h
0x18003ef0e  mov     r14d, 1
0x18003ef14  mov     rbp, rsi
0x18003ef17  mov     rdx, r14
0x18003ef1a  mov     rsi, [rsi]
0x18003ef1d  mov     cl, [rbp+10h]
0x18003ef20  movzx   r15d, word ptr [rbp+12h]
0x18003ef25  shl     rdx, cl
0x18003ef28  mov     rcx, [r13+18h]
0x18003ef2c  cmp     rdx, rdi
0x18003ef2f  cmova   rdx, rdi
0x18003ef33  add     r15, rdx
0x18003ef36  mov     rdx, rbp
0x18003ef39  add     r12, r15
0x18003ef3c  call    RtlpFreeUserBlockToHeap
0x18003ef41  add     ebx, r14d
0x18003ef44  call    RtlGetCurrentServiceSessionId
0x18003ef49  test    eax, eax
0x18003ef4b  jnz     loc_18003F425
0x18003ef51  mov     ecx, 7FFE0380h
0x18003ef56  cmp     byte ptr [rcx], 0
0x18003ef59  jnz     loc_18003F3E1
0x18003ef5f  xor     ebp, ebp
0x18003ef61  test    rsi, rsi
0x18003ef64  jnz     short loc_18003EF14
0x18003ef66  mov     rdi, [rsp+88h+arg_0]
0x18003ef6e  mov     r14, [rsp+88h+arg_8]
0x18003ef76  test    ebx, ebx
0x18003ef78  jz      short loc_18003EF81
0x18003ef7a  neg     ebx
0x18003ef7c  lock add [r14+10h], ebx
0x18003ef81  inc     rdi
0x18003ef84  mov     [rsp+88h+arg_0], rdi
0x18003ef8c  cmp     rdi, 0Ch
0x18003ef90  jnz     loc_18003EEE0
0x18003ef96  test    r12, r12
0x18003ef99  jz      short loc_18003EFA3
0x18003ef9b  neg     r12
0x18003ef9e  lock add [r13+48h], r12
0x18003efa3  add     rsp, 48h
0x18003efa7  pop     r15
0x18003efa9  pop     r14
0x18003efab  pop     r13
0x18003efad  pop     r12
0x18003efaf  pop     rdi
0x18003efb0  pop     rsi
0x18003efb1  pop     rbp
0x18003efb2  pop     rbx
0x18003efb3  retn
0x18003efb5  mov     edx, r15d
0x18003efb8  mov     rcx, rbx
0x18003efbb  call    RtlpLocalInfoAllocFromCache
0x18003efc0  mov     rdi, rax
0x18003efc3  test    rax, rax
0x18003efc6  jz      short loc_18003F006
0x18003efc8  mov     rcx, [rbx]
0x18003efcb  mov     [rcx+24h], ebp
0x18003efce  mov     rcx, rax
0x18003efd1  mov     rdx, [r13+18h]
0x18003efd5  mov     r8d, dword ptr cs:RtlpLFHKey
0x18003efdc  shr     rcx, 4
0x18003efe0  xor     ecx, [rax+8]
0x18003efe3  xor     ecx, edx
0x18003efe5  xor     ecx, r8d
0x18003efe8  test    cx, cx
0x18003efeb  jz      short loc_18003F038
0x18003efed  xor     r9d, r9d
0x18003eff0  mov     [rsp+88h+var_60], rbp
0x18003eff5  mov     r8, rdi
0x18003eff8  mov     [rsp+88h+var_68], rbp
0x18003effd  lea     ecx, [r9+3]
0x18003f001  call    RtlpLogHeapFailure
0x18003f006  mov     rdx, [rsp+88h+arg_10]
0x18003f00e  jmp     loc_18003EEB4
0x18003f013  test    [r13+2A0h], r14b
0x18003f01a  mov     eax, dword ptr cs:RtlpAffinityState
0x18003f020  cmovnz  eax, r14d
0x18003f024  mov     dword ptr [rsp+88h+arg_0], eax
0x18003f02b  test    eax, eax
0x18003f02d  jnz     loc_18003EE8F
0x18003f033  jmp     loc_18003EEC1
0x18003f038  shr     rcx, 0Ch
0x18003f03c  sub     rax, rcx
0x18003f03f  mov     rbx, [rax]
0x18003f042  test    rbx, rbx
0x18003f045  jz      short loc_18003EFED
0x18003f047  prefetchw byte ptr [rbx]
0x18003f04a  mov     r14, [rbx+8]
0x18003f04e  mov     eax, [rdi+0Ch]
0x18003f051  shr     eax, 8
0x18003f054  movzx   ebp, ax
0x18003f057  mov     rax, [rbx]
0x18003f05a  mov     rcx, [rax]
0x18003f05d  mov     eax, r14d
0x18003f060  xor     eax, [r14+18h]
0x18003f064  mov     rsi, [rcx+18h]
0x18003f068  xor     eax, esi
0x18003f06a  xor     eax, r8d
0x18003f06d  mov     ecx, eax
0x18003f06f  movzx   edx, ax
0x18003f072  shr     ecx, 10h
0x18003f075  imul    ecx, ebp
0x18003f078  lea     rax, [r14+rcx]
0x18003f07c  add     rdx, rax
0x18003f07f  cmp     rdx, rdi
0x18003f082  jnz     loc_18003F441
0x18003f088  call    RtlGetCurrentServiceSessionId
0x18003f08d  xor     r9d, r9d
0x18003f090  test    eax, eax
0x18003f092  jnz     loc_18003F1FD
0x18003f098  mov     ecx, 7FFE0380h
0x18003f09d  cmp     [rcx], r9b
0x18003f0a0  jnz     loc_18003F4A5
0x18003f0a6  mov     eax, 1
0x18003f0ab  mov     edx, r9d
0x18003f0ae  cmp     ax, ds:7FFE036Ah
0x18003f0b6  sbb     r8d, r8d
0x18003f0b9  and     r8d, 64h
0x18003f0bd  cmp     edx, r8d
0x18003f0c0  ja      short loc_18003F0E8
0x18003f0c2  mov     esi, [rbx+20h]
0x18003f0c5  mov     eax, esi
0x18003f0c7  shr     eax, 10h
0x18003f0ca  bt      ax, 0Fh
0x18003f0cf  jb      short loc_18003F0E4
0x18003f0d1  mov     ecx, esi
0x18003f0d3  mov     eax, esi
0x18003f0d5  or      ecx, 80000000h
0x18003f0db  lock cmpxchg [rbx+20h], ecx
0x18003f0e0  cmp     eax, esi
0x18003f0e2  jz      short loc_18003F0EB
0x18003f0e4  inc     edx
0x18003f0e6  jmp     short loc_18003F0BD
0x18003f0e8  or      esi, 0FFFFFFFFh
0x18003f0eb  mov     byte ptr [rdi+0Fh], 80h
0x18003f0ef  lea     rcx, [rbx+10h]
0x18003f0f3  cmp     esi, 0FFFFFFFFh
0x18003f0f6  jz      loc_18003F1E7
0x18003f0fc  mov     rax, [r14+28h]
0x18003f100  mov     edi, r9d
0x18003f103  btr     [rax], ebp
0x18003f106  cmp     [rcx], r9w
0x18003f10a  jnz     loc_18003F47F
0x18003f110  mov     r8, [rbx]
0x18003f113  mov     r14d, 1
0x18003f119  shl     ebp, 10h
0x18003f11c  movzx   eax, si
0x18003f11f  inc     eax
0x18003f121  add     eax, edi
0x18003f123  or      eax, ebp
0x18003f125  cmp     ax, [rbx+28h]
0x18003f129  jz      loc_18003F219
0x18003f12f  mov     [rbx+20h], eax
0x18003f132  mov     eax, [rbx+2Ch]
0x18003f135  test    al, 2
0x18003f137  jnz     loc_18003F1F6
0x18003f13d  mov     rdx, rbx
0x18003f140  mov     rcx, r8
0x18003f143  call    RtlpIsSubSegmentReuseable
0x18003f148  xor     ebp, ebp
0x18003f14a  test    al, al
0x18003f14c  jz      loc_18003F006
0x18003f152  mov     eax, [rbx+2Ch]
0x18003f155  test    eax, eax
0x18003f157  jz      loc_18003F006
0x18003f15d  test    al, 2
0x18003f15f  jnz     loc_18003F006
0x18003f165  mov     ecx, eax
0x18003f167  or      ecx, 2
0x18003f16a  lock cmpxchg [rbx+2Ch], ecx
0x18003f16f  jnz     short loc_18003F152
0x18003f171  mov     r8, [rbx]
0x18003f174  mov     r9d, ebp
0x18003f177  cmp     r9d, 10h
0x18003f17b  jnb     loc_18003F550
0x18003f181  movzx   ecx, word ptr [r8+0AEh]
0x18003f189  add     ecx, r9d
0x18003f18c  and     ecx, 0Fh
0x18003f18f  mov     rdx, [r8+rcx*8+10h]
0x18003f194  test    rdx, rdx
0x18003f197  jz      loc_18003F539
0x18003f19d  mov     eax, [rdx+2Ch]
0x18003f1a0  test    r14b, al
0x18003f1a3  jnz     loc_18003F548
0x18003f1a9  mov     rax, rdx
0x18003f1ac  lock cmpxchg [r8+rcx*8+10h], rbx
0x18003f1b3  jnz     loc_18003F548
0x18003f1b9  prefetchw byte ptr [rdx+2Ch]
0x18003f1bd  mov     eax, [rdx+2Ch]
0x18003f1c0  mov     ecx, eax
0x18003f1c2  and     ecx, 0FFFFFFFDh
0x18003f1c5  lock cmpxchg [rdx+2Ch], ecx
0x18003f1ca  jnz     short loc_18003F1C0
0x18003f1cc  cmp     eax, 2
0x18003f1cf  jnz     loc_18003F006
0x18003f1d5  mov     rax, [rdx]
0x18003f1d8  mov     rcx, [rax]
0x18003f1db  mov     [rdx], rbp
0x18003f1de  add     rdx, 30h ; '0'
0x18003f1e2  jmp     loc_18003F3D7
0x18003f1e7  lea     rdx, [rdi+10h]
0x18003f1eb  call    RtlpInterlockedPushEntrySList
0x18003f1f0  mov     r14d, 1
0x18003f1f6  xor     ebp, ebp
0x18003f1f8  jmp     loc_18003F006
0x18003f1fd  mov     rax, gs:60h
0x18003f206  mov     rcx, [rax+90h]
0x18003f20d  add     rcx, 226h
0x18003f214  jmp     loc_18003F09D
0x18003f219  mov     rcx, [r8]
0x18003f21c  mov     r9d, [r8+0A8h]
0x18003f223  mov     edx, [rcx+20h]
0x18003f226  mov     ecx, [r8+0A4h]
0x18003f22d  cmp     ecx, r14d
0x18003f230  jnz     short loc_18003F246
0x18003f232  cmp     edx, r9d
0x18003f235  jb      short loc_18003F246
0x18003f237  mov     rcx, [r8]
0x18003f23a  sub     edx, r9d
0x18003f23d  cmp     edx, [rcx+24h]
0x18003f240  jb      loc_18003F12F
0x18003f246  mov     rsi, [rbx]
0x18003f249  xor     ebp, ebp
0x18003f24b  mov     edi, ebp
0x18003f24d  xchg    rdi, [rsi+8]
0x18003f251  test    rdi, rdi
0x18003f254  jz      short loc_18003F2CF
0x18003f256  prefetchw byte ptr [rdi+2Ch]
0x18003f25a  mov     eax, [rdi+2Ch]
0x18003f25d  mov     ecx, eax
0x18003f25f  and     ecx, 0FFFFFFF9h
0x18003f262  lock cmpxchg [rdi+2Ch], ecx
0x18003f267  jnz     short loc_18003F25D
0x18003f269  cmp     eax, 6
0x18003f26c  jz      loc_18003F468
0x18003f272  mov     rdx, rdi
0x18003f275  mov     rcx, rsi
0x18003f278  call    RtlpIsSubSegmentReuseable
0x18003f27d  test    al, al
0x18003f27f  jz      short loc_18003F2CF
0x18003f281  mov     eax, [rdi+2Ch]
0x18003f284  test    eax, eax
0x18003f286  jz      short loc_18003F2CF
0x18003f288  test    al, 2
0x18003f28a  jnz     short loc_18003F2CF
0x18003f28c  mov     ecx, eax
0x18003f28e  or      ecx, 2
0x18003f291  lock cmpxchg [rdi+2Ch], ecx
0x18003f296  jnz     short loc_18003F281
0x18003f298  mov     r8, [rdi]
0x18003f29b  mov     r9d, ebp
0x18003f29e  jmp     loc_18003F4E8
  ... truncated ...
```
