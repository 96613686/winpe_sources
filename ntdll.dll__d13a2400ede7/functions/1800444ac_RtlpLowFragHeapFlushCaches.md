# RtlpLowFragHeapFlushCaches

- ea: `0x1800444ac`
- end: `0x180044c07`
- name: `RtlpLowFragHeapFlushCaches`
- size: `1883`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004428c`

## callees

- `0x1800444ac`
- `0x180044c10`
- `0x180044fbc`
- `0x180045060`
- `0x1800451b0`
- `0x18004be50`
- `0x18004cbd0`
- `0x18006f0d0`
- `0x180081540`
- `0x1800b1904`
- `0x1800c8430`
- `0x18011d208`
- `0x18015f4e0`
- `0x180162890`
- `0x1801628d0`

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
0x1800444ac  push    rbx
0x1800444ae  push    rbp
0x1800444af  push    rsi
0x1800444b0  push    rdi
0x1800444b1  push    r12
0x1800444b3  push    r13
0x1800444b5  push    r14
0x1800444b7  push    r15
0x1800444b9  sub     rsp, 48h
0x1800444bd  xor     ebp, ebp
0x1800444bf  mov     r13, rcx
0x1800444c2  mov     edx, ebp
0x1800444c4  mov     r12d, ebp
0x1800444c7  mov     [rsp+88h+arg_10], rdx
0x1800444cf  lea     r14d, [rbp+1]
0x1800444d3  mov     al, [r13+rdx*4+2A7h]
0x1800444db  mov     r15d, ebp
0x1800444de  test    r14b, al
0x1800444e1  jnz     loc_180044673
0x1800444e7  mov     dword ptr [rsp+88h+arg_0], r14d
0x1800444ef  test    r15d, r15d
0x1800444f2  jnz     loc_180044BD6
0x1800444f8  mov     rbx, [r13+rdx*8+4A8h]
0x180044500  test    rbx, rbx
0x180044503  jz      short loc_180044514
0x180044505  mov     eax, [rbx+0A4h]
0x18004450b  cmp     eax, r14d
0x18004450e  jz      loc_180044615
0x180044514  add     r15d, r14d
0x180044517  cmp     r15d, dword ptr [rsp+88h+arg_0]
0x18004451f  jb      short loc_1800444EF
0x180044521  inc     rdx
0x180044524  mov     [rsp+88h+arg_10], rdx
0x18004452c  cmp     rdx, 81h
0x180044533  jnz     short loc_1800444D3
0x180044535  mov     rdi, rbp
0x180044538  mov     [rsp+88h+arg_0], rbp
0x180044540  lea     r14, [rdi+rdi*2]
0x180044544  mov     ebx, ebp
0x180044546  shl     r14, 4
0x18004454a  add     r14, 60h ; '`'
0x18004454e  add     r14, r13
0x180044551  mov     rcx, r14
0x180044554  mov     [rsp+88h+arg_8], r14
0x18004455c  call    RtlpInterlockedFlushSList
0x180044561  mov     rsi, rax
0x180044564  test    rax, rax
0x180044567  jz      short loc_1800445E1
0x180044569  mov     edi, 0F0000h
0x18004456e  mov     r14d, 1
0x180044574  mov     rbp, rsi
0x180044577  mov     rdx, r14
0x18004457a  mov     rsi, [rsi]
0x18004457d  mov     cl, [rbp+10h]
0x180044580  movzx   r15d, word ptr [rbp+12h]
0x180044585  shl     rdx, cl
0x180044588  mov     rcx, [r13+18h]
0x18004458c  cmp     rdx, rdi
0x18004458f  cmova   rdx, rdi
0x180044593  add     r15, rdx
0x180044596  mov     rdx, rbp
0x180044599  add     r12, r15
0x18004459c  call    RtlpFreeUserBlockToHeap
0x1800445a1  add     ebx, r14d
0x1800445a4  call    RtlGetCurrentServiceSessionId
0x1800445a9  test    eax, eax
0x1800445ab  jnz     loc_180044A85
0x1800445b1  mov     ecx, 7FFE0380h
0x1800445b6  cmp     byte ptr [rcx], 0
0x1800445b9  jnz     loc_180044A41
0x1800445bf  xor     ebp, ebp
0x1800445c1  test    rsi, rsi
0x1800445c4  jnz     short loc_180044574
0x1800445c6  mov     rdi, [rsp+88h+arg_0]
0x1800445ce  mov     r14, [rsp+88h+arg_8]
0x1800445d6  test    ebx, ebx
0x1800445d8  jz      short loc_1800445E1
0x1800445da  neg     ebx
0x1800445dc  lock add [r14+10h], ebx
0x1800445e1  inc     rdi
0x1800445e4  mov     [rsp+88h+arg_0], rdi
0x1800445ec  cmp     rdi, 0Ch
0x1800445f0  jnz     loc_180044540
0x1800445f6  test    r12, r12
0x1800445f9  jz      short loc_180044603
0x1800445fb  neg     r12
0x1800445fe  lock add [r13+48h], r12
0x180044603  add     rsp, 48h
0x180044607  pop     r15
0x180044609  pop     r14
0x18004460b  pop     r13
0x18004460d  pop     r12
0x18004460f  pop     rdi
0x180044610  pop     rsi
0x180044611  pop     rbp
0x180044612  pop     rbx
0x180044613  retn
0x180044615  mov     edx, r15d
0x180044618  mov     rcx, rbx
0x18004461b  call    RtlpLocalInfoAllocFromCache
0x180044620  mov     rdi, rax
0x180044623  test    rax, rax
0x180044626  jz      short loc_180044666
0x180044628  mov     rcx, [rbx]
0x18004462b  mov     [rcx+24h], ebp
0x18004462e  mov     rcx, rax
0x180044631  mov     rdx, [r13+18h]
0x180044635  mov     r8d, dword ptr cs:RtlpLFHKey
0x18004463c  shr     rcx, 4
0x180044640  xor     ecx, [rax+8]
0x180044643  xor     ecx, edx
0x180044645  xor     ecx, r8d
0x180044648  test    cx, cx
0x18004464b  jz      short loc_180044698
0x18004464d  xor     r9d, r9d
0x180044650  mov     [rsp+88h+var_60], rbp
0x180044655  mov     r8, rdi
0x180044658  mov     [rsp+88h+var_68], rbp
0x18004465d  lea     ecx, [r9+3]
0x180044661  call    RtlpLogHeapFailure
0x180044666  mov     rdx, [rsp+88h+arg_10]
0x18004466e  jmp     loc_180044514
0x180044673  test    [r13+2A0h], r14b
0x18004467a  mov     eax, dword ptr cs:RtlpAffinityState
0x180044680  cmovnz  eax, r14d
0x180044684  mov     dword ptr [rsp+88h+arg_0], eax
0x18004468b  test    eax, eax
0x18004468d  jnz     loc_1800444EF
0x180044693  jmp     loc_180044521
0x180044698  shr     rcx, 0Ch
0x18004469c  sub     rax, rcx
0x18004469f  mov     rbx, [rax]
0x1800446a2  test    rbx, rbx
0x1800446a5  jz      short loc_18004464D
0x1800446a7  prefetchw byte ptr [rbx]
0x1800446aa  mov     r14, [rbx+8]
0x1800446ae  mov     eax, [rdi+0Ch]
0x1800446b1  shr     eax, 8
0x1800446b4  movzx   ebp, ax
0x1800446b7  mov     rax, [rbx]
0x1800446ba  mov     rcx, [rax]
0x1800446bd  mov     eax, r14d
0x1800446c0  xor     eax, [r14+18h]
0x1800446c4  mov     rsi, [rcx+18h]
0x1800446c8  xor     eax, esi
0x1800446ca  xor     eax, r8d
0x1800446cd  mov     ecx, eax
0x1800446cf  movzx   edx, ax
0x1800446d2  shr     ecx, 10h
0x1800446d5  imul    ecx, ebp
0x1800446d8  lea     rax, [r14+rcx]
0x1800446dc  add     rdx, rax
0x1800446df  cmp     rdx, rdi
0x1800446e2  jnz     loc_180044AA1
0x1800446e8  call    RtlGetCurrentServiceSessionId
0x1800446ed  xor     r9d, r9d
0x1800446f0  test    eax, eax
0x1800446f2  jnz     loc_18004485D
0x1800446f8  mov     ecx, 7FFE0380h
0x1800446fd  cmp     [rcx], r9b
0x180044700  jnz     loc_180044B05
0x180044706  mov     eax, 1
0x18004470b  mov     edx, r9d
0x18004470e  cmp     ax, ds:7FFE036Ah
0x180044716  sbb     r8d, r8d
0x180044719  and     r8d, 64h
0x18004471d  cmp     edx, r8d
0x180044720  ja      short loc_180044748
0x180044722  mov     esi, [rbx+20h]
0x180044725  mov     eax, esi
0x180044727  shr     eax, 10h
0x18004472a  bt      ax, 0Fh
0x18004472f  jb      short loc_180044744
0x180044731  mov     ecx, esi
0x180044733  mov     eax, esi
0x180044735  or      ecx, 80000000h
0x18004473b  lock cmpxchg [rbx+20h], ecx
0x180044740  cmp     eax, esi
0x180044742  jz      short loc_18004474B
0x180044744  inc     edx
0x180044746  jmp     short loc_18004471D
0x180044748  or      esi, 0FFFFFFFFh
0x18004474b  mov     byte ptr [rdi+0Fh], 80h
0x18004474f  lea     rcx, [rbx+10h]
0x180044753  cmp     esi, 0FFFFFFFFh
0x180044756  jz      loc_180044847
0x18004475c  mov     rax, [r14+28h]
0x180044760  mov     edi, r9d
0x180044763  btr     [rax], ebp
0x180044766  cmp     [rcx], r9w
0x18004476a  jnz     loc_180044ADF
0x180044770  mov     r8, [rbx]
0x180044773  mov     r14d, 1
0x180044779  shl     ebp, 10h
0x18004477c  movzx   eax, si
0x18004477f  inc     eax
0x180044781  add     eax, edi
0x180044783  or      eax, ebp
0x180044785  cmp     ax, [rbx+28h]
0x180044789  jz      loc_180044879
0x18004478f  mov     [rbx+20h], eax
0x180044792  mov     eax, [rbx+2Ch]
0x180044795  test    al, 2
0x180044797  jnz     loc_180044856
0x18004479d  mov     rdx, rbx
0x1800447a0  mov     rcx, r8
0x1800447a3  call    RtlpIsSubSegmentReuseable
0x1800447a8  xor     ebp, ebp
0x1800447aa  test    al, al
0x1800447ac  jz      loc_180044666
0x1800447b2  mov     eax, [rbx+2Ch]
0x1800447b5  test    eax, eax
0x1800447b7  jz      loc_180044666
0x1800447bd  test    al, 2
0x1800447bf  jnz     loc_180044666
0x1800447c5  mov     ecx, eax
0x1800447c7  or      ecx, 2
0x1800447ca  lock cmpxchg [rbx+2Ch], ecx
0x1800447cf  jnz     short loc_1800447B2
0x1800447d1  mov     r8, [rbx]
0x1800447d4  mov     r9d, ebp
0x1800447d7  cmp     r9d, 10h
0x1800447db  jnb     loc_180044BB0
0x1800447e1  movzx   ecx, word ptr [r8+0AEh]
0x1800447e9  add     ecx, r9d
0x1800447ec  and     ecx, 0Fh
0x1800447ef  mov     rdx, [r8+rcx*8+10h]
0x1800447f4  test    rdx, rdx
0x1800447f7  jz      loc_180044B99
0x1800447fd  mov     eax, [rdx+2Ch]
0x180044800  test    r14b, al
0x180044803  jnz     loc_180044BA8
0x180044809  mov     rax, rdx
0x18004480c  lock cmpxchg [r8+rcx*8+10h], rbx
0x180044813  jnz     loc_180044BA8
0x180044819  prefetchw byte ptr [rdx+2Ch]
0x18004481d  mov     eax, [rdx+2Ch]
0x180044820  mov     ecx, eax
0x180044822  and     ecx, 0FFFFFFFDh
0x180044825  lock cmpxchg [rdx+2Ch], ecx
0x18004482a  jnz     short loc_180044820
0x18004482c  cmp     eax, 2
0x18004482f  jnz     loc_180044666
0x180044835  mov     rax, [rdx]
0x180044838  mov     rcx, [rax]
0x18004483b  mov     [rdx], rbp
0x18004483e  add     rdx, 30h ; '0'
0x180044842  jmp     loc_180044A37
0x180044847  lea     rdx, [rdi+10h]
0x18004484b  call    RtlpInterlockedPushEntrySList
0x180044850  mov     r14d, 1
0x180044856  xor     ebp, ebp
0x180044858  jmp     loc_180044666
0x18004485d  mov     rax, gs:60h
0x180044866  mov     rcx, [rax+90h]
0x18004486d  add     rcx, 226h
0x180044874  jmp     loc_1800446FD
0x180044879  mov     rcx, [r8]
0x18004487c  mov     r9d, [r8+0A8h]
0x180044883  mov     edx, [rcx+20h]
0x180044886  mov     ecx, [r8+0A4h]
0x18004488d  cmp     ecx, r14d
0x180044890  jnz     short loc_1800448A6
0x180044892  cmp     edx, r9d
0x180044895  jb      short loc_1800448A6
0x180044897  mov     rcx, [r8]
0x18004489a  sub     edx, r9d
0x18004489d  cmp     edx, [rcx+24h]
0x1800448a0  jb      loc_18004478F
0x1800448a6  mov     rsi, [rbx]
0x1800448a9  xor     ebp, ebp
0x1800448ab  mov     edi, ebp
0x1800448ad  xchg    rdi, [rsi+8]
0x1800448b1  test    rdi, rdi
0x1800448b4  jz      short loc_18004492F
0x1800448b6  prefetchw byte ptr [rdi+2Ch]
0x1800448ba  mov     eax, [rdi+2Ch]
0x1800448bd  mov     ecx, eax
0x1800448bf  and     ecx, 0FFFFFFF9h
0x1800448c2  lock cmpxchg [rdi+2Ch], ecx
0x1800448c7  jnz     short loc_1800448BD
0x1800448c9  cmp     eax, 6
0x1800448cc  jz      loc_180044AC8
0x1800448d2  mov     rdx, rdi
0x1800448d5  mov     rcx, rsi
0x1800448d8  call    RtlpIsSubSegmentReuseable
0x1800448dd  test    al, al
0x1800448df  jz      short loc_18004492F
0x1800448e1  mov     eax, [rdi+2Ch]
0x1800448e4  test    eax, eax
0x1800448e6  jz      short loc_18004492F
0x1800448e8  test    al, 2
0x1800448ea  jnz     short loc_18004492F
0x1800448ec  mov     ecx, eax
0x1800448ee  or      ecx, 2
0x1800448f1  lock cmpxchg [rdi+2Ch], ecx
0x1800448f6  jnz     short loc_1800448E1
0x1800448f8  mov     r8, [rdi]
0x1800448fb  mov     r9d, ebp
0x1800448fe  jmp     loc_180044B48
  ... truncated ...
```
