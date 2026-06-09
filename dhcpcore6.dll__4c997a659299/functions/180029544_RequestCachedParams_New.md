# RequestCachedParams_New

- ea: `0x180029544`
- end: `0x180029811`
- name: `RequestCachedParams_New`
- size: `717`
- prototype: `__int64 __fastcall(__int64, char, __int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027540`

## callees

- `0x18000c740`
- `0x1800284d4`
- `0x180029544`
- `0x18002a1d8`
- `0x18002de2c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180029688`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002973c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180029688`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002973c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800297b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800297b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800295bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800295bb`

## pseudocode

```c
__int64 __fastcall RequestCachedParams_New(__int64 a1, char a2, __int64 a3, __int64 a4, _OWORD *a5)
{
  _OWORD *v5; // r15
  __int64 v9; // rbx
  __int64 v10; // rdi
  int v11; // r12d
  __int64 v12; // r8
  int v13; // r9d
  _QWORD **v14; // r10
  __int64 v15; // r14
  __int64 i; // rsi
  unsigned int AllOptions; // eax
  unsigned int v18; // r14d
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  HLOCAL v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int128 v25; // xmm0
  __int64 j; // rdi
  int v28; // [rsp+40h] [rbp-41h]
  __int64 v29; // [rsp+48h] [rbp-39h] BYREF
  __int64 v30; // [rsp+50h] [rbp-31h]
  _QWORD **v31; // [rsp+58h] [rbp-29h]
  __int64 v32; // [rsp+60h] [rbp-21h]
  __int64 v33; // [rsp+68h] [rbp-19h]
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-11h]
  __int128 v35; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v36; // [rsp+E0h] [rbp+5Fh] BYREF

  v5 = a5;
  v29 = 0;
  v36 = 0;
  v35 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a1 && a4 && v5 )
  {
    v10 = 0;
    SRWLock = (PSRWLOCK)(a1 + 608);
    LODWORD(v9) = 0;
    v11 = a2 & 1;
    AcquireSRWLockShared((PSRWLOCK)(a1 + 608));
    if ( a3 )
    {
      v12 = *(_QWORD *)(a3 + 8);
      v13 = *(_DWORD *)(a3 + 16);
    }
    else
    {
      v12 = *(_QWORD *)(a1 + 656);
      v13 = *(_DWORD *)(a1 + 664);
    }
    v14 = (_QWORD **)(a1 + 632);
    v28 = v13;
    v31 = (_QWORD **)(a1 + 632);
    v15 = 0;
    v30 = v12;
    while ( (unsigned int)v15 < *(_DWORD *)a4 )
    {
      LODWORD(v9) = Dhcpv6FindAllOptions(
                      v14,
                      *(unsigned int *)(*(_QWORD *)(a4 + 8) + 24 * v15 + 4),
                      *(unsigned int *)(*(_QWORD *)(a4 + 8) + 24 * v15 + 8),
                      v12,
                      v13,
                      &v29,
                      &v36);
      if ( (_DWORD)v9 )
        goto LABEL_35;
      if ( v36 )
      {
        if ( v11 )
          v10 = v36 + (unsigned int)v10;
        else
          v10 = (unsigned int)(v10 + 1);
        DhcpFree(&v29);
      }
      v12 = v30;
      v15 = (unsigned int)(v15 + 1);
      v13 = v28;
      v14 = v31;
    }
    if ( (_DWORD)v10 )
    {
      LODWORD(a5) = 0;
      LODWORD(v35) = v10;
      *((_QWORD *)&v35 + 1) = LocalAlloc(0x40u, 24 * v10);
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= *(_DWORD *)a4 )
        {
          if ( (_DWORD)a5 == (_DWORD)v10 )
          {
            v25 = v35;
            LODWORD(v9) = 0;
            *((_QWORD *)&v35 + 1) = 0;
            *v5 = v25;
            LODWORD(v35) = 0;
          }
          else
          {
            LODWORD(v9) = 1359;
          }
          goto LABEL_35;
        }
        AllOptions = Dhcpv6FindAllOptions(
                       v31,
                       *(unsigned int *)(*(_QWORD *)(a4 + 8) + 24 * i + 4),
                       *(unsigned int *)(*(_QWORD *)(a4 + 8) + 24 * i + 8),
                       v30,
                       v28,
                       &v29,
                       &v36);
        v9 = AllOptions;
        if ( AllOptions )
          goto LABEL_35;
        v18 = v36;
        if ( v36 )
          break;
LABEL_30:
        ;
      }
      if ( !v11 )
        v9 = v36 - 1;
      while ( 1 )
      {
        if ( (unsigned int)v9 >= v18 )
        {
          DhcpFree(&v29);
          goto LABEL_30;
        }
        v19 = *((_QWORD *)&v35 + 1);
        v20 = 3LL * (unsigned int)a5;
        v21 = *(_QWORD *)(v29 + 8 * v9);
        v32 = v20;
        v33 = v21;
        *(_DWORD *)(*((_QWORD *)&v35 + 1) + 8 * v20 + 4) = *(unsigned __int16 *)(v21 + 16);
        *(_DWORD *)(v19 + 8 * v20 + 8) = *(_DWORD *)(v21 + 20);
        *(_DWORD *)(v19 + 8 * v20 + 12) = *(_DWORD *)(v21 + 56);
        v22 = LocalAlloc(0x40u, *(unsigned int *)(v21 + 56));
        v23 = v32;
        v24 = *((_QWORD *)&v35 + 1);
        *(_QWORD *)(*((_QWORD *)&v35 + 1) + 8 * v32 + 16) = v22;
        if ( !v22 )
          break;
        memcpy_s(
          v22,
          *(unsigned int *)(v24 + 8 * v23 + 12),
          *(const void *const *)(v33 + 48),
          *(unsigned int *)(v33 + 56));
        LODWORD(a5) = (_DWORD)a5 + 1;
        v9 = (unsigned int)(v9 + 1);
      }
      LODWORD(v9) = 8;
    }
LABEL_35:
    ReleaseSRWLockShared(SRWLock);
  }
  else
  {
    LODWORD(v9) = 87;
  }
  DhcpFree(&v29);
  if ( *((_QWORD *)&v35 + 1) )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)v35; j = (unsigned int)(j + 1) )
      DhcpMidlUserFree(*((_QWORD *)&v35 + 1) + 8 * (j + 2 * (j + 1)));
    DhcpMidlUserFree((char *)&v35 + 8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029544  push    rbp
0x180029546  push    rbx
0x180029547  push    rsi
0x180029548  push    rdi
0x180029549  push    r12
0x18002954b  push    r13
0x18002954d  push    r14
0x18002954f  push    r15
0x180029551  lea     rbp, [rsp-17h]
0x180029556  sub     rsp, 98h
0x18002955d  mov     r15, [rbp+4Fh+arg_20]
0x180029561  xorps   xmm0, xmm0
0x180029564  mov     [rbp+4Fh+var_88], 0
0x18002956c  mov     r13, r9
0x18002956f  mov     [rbp+4Fh+arg_0], 0
0x180029576  mov     r14, r8
0x180029579  mov     r12d, edx
0x18002957c  mov     rsi, rcx
0x18002957f  movups  [rbp+4Fh+var_58], xmm0
0x180029583  test    r15, r15
0x180029586  jz      short loc_18002958C
0x180029588  movups  xmmword ptr [r15], xmm0
0x18002958c  test    rsi, rsi
0x18002958f  jnz     short loc_18002959B
0x180029591  mov     ebx, 57h ; 'W'
0x180029596  jmp     loc_1800297BE
0x18002959b  test    r13, r13
0x18002959e  jz      short loc_180029591
0x1800295a0  test    r15, r15
0x1800295a3  jz      short loc_180029591
0x1800295a5  lea     rax, [rcx+260h]
0x1800295ac  xor     edi, edi
0x1800295ae  mov     rcx, rax; SRWLock
0x1800295b1  mov     [rbp+4Fh+SRWLock], rax
0x1800295b5  xor     ebx, ebx
0x1800295b7  and     r12d, 1
0x1800295bb  call    cs:__imp_AcquireSRWLockShared
0x1800295c2  nop     dword ptr [rax+rax+00h]
0x1800295c7  test    r14, r14
0x1800295ca  jz      short loc_1800295D6
0x1800295cc  mov     r8, [r14+8]
0x1800295d0  mov     r9d, [r14+10h]
0x1800295d4  jmp     short loc_1800295E4
0x1800295d6  mov     r8, [rsi+290h]
0x1800295dd  mov     r9d, [rsi+298h]
0x1800295e4  lea     r10, [rsi+278h]
0x1800295eb  mov     [rbp+4Fh+var_90], r9d
0x1800295ef  mov     [rbp+4Fh+var_78], r10
0x1800295f3  xor     r14d, r14d
0x1800295f6  mov     [rbp+4Fh+var_80], r8
0x1800295fa  cmp     r14d, [r13+0]
0x1800295fe  jnb     short loc_180029669
0x180029600  mov     rdx, [r13+8]
0x180029604  lea     rcx, [r14+r14*2]
0x180029608  lea     rax, [rbp+4Fh+arg_0]
0x18002960c  mov     [rsp+0D0h+var_A0], rax
0x180029611  lea     rax, [rbp+4Fh+var_88]
0x180029615  mov     [rsp+0D0h+var_A8], rax
0x18002961a  mov     [rsp+0D0h+var_B0], r9d
0x18002961f  mov     r9, r8
0x180029622  mov     r8d, [rdx+rcx*8+8]
0x180029627  mov     edx, [rdx+rcx*8+4]
0x18002962b  mov     rcx, r10
0x18002962e  call    Dhcpv6FindAllOptions
0x180029633  mov     ebx, eax
0x180029635  test    eax, eax
0x180029637  jnz     loc_1800297AE
0x18002963d  mov     eax, [rbp+4Fh+arg_0]
0x180029640  test    eax, eax
0x180029642  jz      short loc_180029658
0x180029644  test    r12d, r12d
0x180029647  jz      short loc_18002964D
0x180029649  add     edi, eax
0x18002964b  jmp     short loc_18002964F
0x18002964d  inc     edi
0x18002964f  lea     rcx, [rbp+4Fh+var_88]
0x180029653  call    DhcpFree
0x180029658  mov     r8, [rbp+4Fh+var_80]
0x18002965c  inc     r14d
0x18002965f  mov     r9d, [rbp+4Fh+var_90]
0x180029663  mov     r10, [rbp+4Fh+var_78]
0x180029667  jmp     short loc_1800295FA
0x180029669  test    edi, edi
0x18002966b  jz      loc_1800297AE
0x180029671  lea     rdx, [rdi+rdi*2]
0x180029675  mov     dword ptr [rbp+4Fh+arg_20], 0
0x18002967c  shl     rdx, 3; uBytes
0x180029680  mov     ecx, 40h ; '@'; uFlags
0x180029685  mov     dword ptr [rbp+4Fh+var_58], edi
0x180029688  call    cs:__imp_LocalAlloc
0x18002968f  nop     dword ptr [rax+rax+00h]
0x180029694  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x180029698  xor     esi, esi
0x18002969a  cmp     esi, [r13+0]
0x18002969e  jnb     loc_180029790
0x1800296a4  mov     rdx, [r13+8]
0x1800296a8  lea     rcx, [rsi+rsi*2]
0x1800296ac  mov     r9, [rbp+4Fh+var_80]
0x1800296b0  lea     rax, [rbp+4Fh+arg_0]
0x1800296b4  mov     [rsp+0D0h+var_A0], rax
0x1800296b9  lea     rax, [rbp+4Fh+var_88]
0x1800296bd  mov     [rsp+0D0h+var_A8], rax
0x1800296c2  mov     r8d, [rdx+rcx*8+8]
0x1800296c7  mov     edx, [rdx+rcx*8+4]
0x1800296cb  mov     eax, [rbp+4Fh+var_90]
0x1800296ce  mov     rcx, [rbp+4Fh+var_78]
0x1800296d2  mov     [rsp+0D0h+var_B0], eax
0x1800296d6  call    Dhcpv6FindAllOptions
0x1800296db  mov     ebx, eax
0x1800296dd  test    eax, eax
0x1800296df  jnz     loc_1800297AE
0x1800296e5  mov     r14d, [rbp+4Fh+arg_0]
0x1800296e9  test    r14d, r14d
0x1800296ec  jz      loc_180029782
0x1800296f2  test    r12d, r12d
0x1800296f5  jnz     short loc_1800296FB
0x1800296f7  lea     ebx, [r14-1]
0x1800296fb  cmp     ebx, r14d
0x1800296fe  jnb     short loc_180029779
0x180029700  mov     r8, qword ptr [rbp+4Fh+var_58+8]
0x180029704  mov     eax, dword ptr [rbp+4Fh+arg_20]
0x180029707  mov     rcx, [rbp+4Fh+var_88]
0x18002970b  lea     rdx, [rax+rax*2]
0x18002970f  mov     rcx, [rcx+rbx*8]
0x180029713  mov     [rbp+4Fh+var_70], rdx
0x180029717  mov     [rbp+4Fh+var_68], rcx
0x18002971b  movzx   eax, word ptr [rcx+10h]
0x18002971f  mov     [r8+rdx*8+4], eax
0x180029724  mov     eax, [rcx+14h]
0x180029727  mov     [r8+rdx*8+8], eax
0x18002972c  mov     eax, [rcx+38h]
0x18002972f  mov     [r8+rdx*8+0Ch], eax
0x180029734  mov     edx, [rcx+38h]; uBytes
0x180029737  mov     ecx, 40h ; '@'; uFlags
0x18002973c  call    cs:__imp_LocalAlloc
0x180029743  nop     dword ptr [rax+rax+00h]
0x180029748  mov     rcx, [rbp+4Fh+var_70]
0x18002974c  mov     rdx, qword ptr [rbp+4Fh+var_58+8]
0x180029750  mov     [rdx+rcx*8+10h], rax
0x180029755  test    rax, rax
0x180029758  jz      short loc_180029789
0x18002975a  mov     r8, [rbp+4Fh+var_68]
0x18002975e  mov     edx, [rdx+rcx*8+0Ch]; DestinationSize
0x180029762  mov     rcx, rax; Destination
0x180029765  mov     r9d, [r8+38h]; SourceSize
0x180029769  mov     r8, [r8+30h]; Source
0x18002976d  call    memcpy_s
0x180029772  inc     dword ptr [rbp+4Fh+arg_20]
0x180029775  inc     ebx
0x180029777  jmp     short loc_1800296FB
0x180029779  lea     rcx, [rbp+4Fh+var_88]
0x18002977d  call    DhcpFree
0x180029782  inc     esi
0x180029784  jmp     loc_18002969A
0x180029789  mov     ebx, 8
0x18002978e  jmp     short loc_1800297AE
0x180029790  cmp     dword ptr [rbp+4Fh+arg_20], edi
0x180029793  jz      short loc_18002979C
0x180029795  mov     ebx, 54Fh
0x18002979a  jmp     short loc_1800297AE
0x18002979c  movups  xmm0, [rbp+4Fh+var_58]
0x1800297a0  xor     ebx, ebx
0x1800297a2  mov     qword ptr [rbp+4Fh+var_58+8], rbx
0x1800297a6  movdqu  xmmword ptr [r15], xmm0
0x1800297ab  mov     dword ptr [rbp+4Fh+var_58], ebx
0x1800297ae  mov     rcx, [rbp+4Fh+SRWLock]; SRWLock
0x1800297b2  call    cs:__imp_ReleaseSRWLockShared
0x1800297b9  nop     dword ptr [rax+rax+00h]
0x1800297be  lea     rcx, [rbp+4Fh+var_88]
0x1800297c2  call    DhcpFree
0x1800297c7  cmp     qword ptr [rbp+4Fh+var_58+8], 0
0x1800297cc  jz      short loc_1800297FA
0x1800297ce  xor     edi, edi
0x1800297d0  cmp     dword ptr [rbp+4Fh+var_58], edi
0x1800297d3  jbe     short loc_1800297F1
0x1800297d5  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x1800297d9  lea     rcx, [rdi+1]
0x1800297dd  lea     rcx, [rdi+rcx*2]
0x1800297e1  lea     rcx, [rax+rcx*8]
0x1800297e5  call    DhcpMidlUserFree
0x1800297ea  inc     edi
0x1800297ec  cmp     edi, dword ptr [rbp+4Fh+var_58]
0x1800297ef  jb      short loc_1800297D5
0x1800297f1  lea     rcx, [rbp+4Fh+var_58+8]
0x1800297f5  call    DhcpMidlUserFree
0x1800297fa  mov     eax, ebx
0x1800297fc  add     rsp, 98h
0x180029803  pop     r15
0x180029805  pop     r14
0x180029807  pop     r13
0x180029809  pop     r12
0x18002980b  pop     rdi
0x18002980c  pop     rsi
0x18002980d  pop     rbx
0x18002980e  pop     rbp
0x18002980f  retn
```
