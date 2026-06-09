# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetGUID(_GUID const &,_GUID *)

- ea: `0x180048540`
- end: `0x180048764`
- name: `?GetGUID@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAU2@@Z`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801495e0`

## callees

- `0x180048540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180048578`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180048578`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004873b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004873b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180048751`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180048751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048604`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048604`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetGUID(__int64 a1, unsigned int *a2, _OWORD *a3)
{
  __int64 v3; // rbp
  int v7; // r9d
  unsigned int v8; // edi
  __int64 v9; // r10
  int k; // r8d
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // ecx
  __int64 result; // rax
  __int64 v15; // rsi
  int v16; // r8d
  int v17; // eax
  int i; // r11d
  int j; // r8d

  v3 = a1 + 16;
  if ( *(_DWORD *)(a1 + 24) == GetCurrentThreadId() )
    ++*(_DWORD *)(v3 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v3);
  v7 = *(_DWORD *)(a1 + 44);
  if ( v7 )
  {
    v8 = *a2;
    if ( v7 >= 4 )
    {
      v15 = *(_QWORD *)(a1 + 32);
      v16 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v17 = (v16 + v7) / 2;
          v11 = v15 + 40LL * v17;
          if ( v8 >= *(_DWORD *)v11 )
            break;
          if ( v17 == v16 )
            goto LABEL_16;
          v7 = (v16 + v7) / 2;
        }
        if ( v8 <= *(_DWORD *)(v15 + 40LL * v17) )
          break;
        v16 = v17 + 1;
        if ( v17 + 1 == v7 )
          goto LABEL_16;
      }
      if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
      {
LABEL_11:
        if ( v11 != -16 )
        {
          if ( *(_WORD *)(v11 + 16) == 72 )
          {
            v12 = 0;
            *a3 = *(_OWORD *)*(_QWORD *)(v11 + 24);
          }
          else
          {
            v12 = -1072875843;
          }
          goto LABEL_17;
        }
      }
      else
      {
        if ( v17 > v16 )
        {
          for ( i = v17 - 1; i >= v16; --i )
          {
            v11 = v15 + 40LL * i;
            if ( v8 != *(_DWORD *)v11 )
              break;
            if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
              goto LABEL_11;
          }
        }
        for ( j = v17 + 1; j < v7; ++j )
        {
          v11 = v15 + 40LL * j;
          if ( v8 != *(_DWORD *)v11 )
            break;
          if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
            goto LABEL_11;
        }
      }
    }
    else if ( v7 > 0 )
    {
      v9 = *(_QWORD *)(a1 + 32);
      for ( k = 0; k < v7; ++k )
      {
        v11 = v9 + 40LL * k;
        if ( *(_DWORD *)v11 == v8 )
        {
          if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)(v9 + 40LL * k) > v8 )
        {
          break;
        }
      }
    }
  }
LABEL_16:
  v12 = -1072875802;
LABEL_17:
  if ( *(_DWORD *)(v3 + 8) == GetCurrentThreadId() )
  {
    v13 = *(_DWORD *)(v3 + 12);
    if ( v13 )
    {
      result = v12;
      *(_DWORD *)(v3 + 12) = v13 - 1;
    }
    else
    {
      *(_DWORD *)(v3 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v3);
      return v12;
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v3);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180048540  mov     [rsp+arg_18], rbx
0x180048545  push    rbp
0x180048546  sub     rsp, 20h
0x18004854a  mov     [rsp+28h+arg_0], rsi
0x18004854f  lea     rbp, [rcx+10h]
0x180048553  mov     [rsp+28h+arg_10], r14
0x180048558  mov     rbx, rdx
0x18004855b  mov     r14, r8
0x18004855e  mov     rsi, rcx
0x180048561  call    cs:__imp_GetCurrentThreadId
0x180048567  mov     r9d, [rbp+8]
0x18004856b  cmp     r9d, eax
0x18004856e  jnz     short loc_180048575
0x180048570  inc     dword ptr [rbp+0Ch]
0x180048573  jmp     short loc_18004857E
0x180048575  mov     rcx, rbp; SRWLock
0x180048578  call    cs:__imp_AcquireSRWLockShared
0x18004857e  mov     r9d, [rsi+2Ch]
0x180048582  mov     [rsp+28h+arg_8], rdi
0x180048587  test    r9d, r9d
0x18004858a  jz      short loc_1800485FF
0x18004858c  mov     edi, [rbx]
0x18004858e  cmp     r9d, 4
0x180048592  jge     loc_180048641
0x180048598  test    r9d, r9d
0x18004859b  jle     short loc_1800485FF
0x18004859d  mov     r10, [rsi+20h]
0x1800485a1  xor     r8d, r8d
0x1800485a4  nop     dword ptr [rax+00h]
0x1800485a8  nop     dword ptr [rax+rax+00000000h]
0x1800485b0  movsxd  rax, r8d
0x1800485b3  lea     rcx, [rax+rax*4]
0x1800485b7  cmp     [r10+rcx*8], edi
0x1800485bb  lea     rdx, [r10+rcx*8]
0x1800485bf  jnz     short loc_1800485F5
0x1800485c1  mov     rax, [rbx]
0x1800485c4  cmp     rax, [rdx]
0x1800485c7  jnz     short loc_1800485F7
0x1800485c9  mov     rax, [rbx+8]
0x1800485cd  cmp     rax, [rdx+8]
0x1800485d1  jnz     short loc_1800485F7
0x1800485d3  lea     rax, [rdx+10h]
0x1800485d7  test    rax, rax
0x1800485da  jz      short loc_1800485FF
0x1800485dc  cmp     word ptr [rax], 48h ; 'H'
0x1800485e0  jnz     loc_180048727
0x1800485e6  mov     rax, [rax+8]
0x1800485ea  xor     ebx, ebx
0x1800485ec  movups  xmm0, xmmword ptr [rax]
0x1800485ef  movups  xmmword ptr [r14], xmm0
0x1800485f3  jmp     short loc_180048604
0x1800485f5  ja      short loc_1800485FF
0x1800485f7  inc     r8d
0x1800485fa  cmp     r8d, r9d
0x1800485fd  jl      short loc_1800485B0
0x1800485ff  mov     ebx, 0C00D36E6h
0x180048604  call    cs:__imp_GetCurrentThreadId
0x18004860a  mov     ecx, [rbp+8]
0x18004860d  mov     r14, [rsp+28h+arg_10]
0x180048612  mov     rdi, [rsp+28h+arg_8]
0x180048617  mov     rsi, [rsp+28h+arg_0]
0x18004861c  cmp     ecx, eax
0x18004861e  jnz     loc_18004874E
0x180048624  mov     ecx, [rbp+0Ch]
0x180048627  test    ecx, ecx
0x180048629  jz      loc_180048731
0x18004862f  dec     ecx
0x180048631  mov     eax, ebx
0x180048633  mov     [rbp+0Ch], ecx
0x180048636  mov     rbx, [rsp+28h+arg_18]
0x18004863b  add     rsp, 20h
0x18004863f  pop     rbp
0x180048640  retn
0x180048641  mov     rsi, [rsi+20h]
0x180048645  xor     r8d, r8d
0x180048648  nop     dword ptr [rax+rax+00000000h]
0x180048650  lea     eax, [r8+r9]
0x180048654  cdq
0x180048655  sub     eax, edx
0x180048657  sar     eax, 1
0x180048659  movsxd  r10, eax
0x18004865c  lea     rdx, [r10+r10*4]
0x180048660  cmp     edi, [rsi+rdx*8]
0x180048663  lea     rdx, [rsi+rdx*8]
0x180048667  jnb     short loc_180048673
0x180048669  cmp     r10d, r8d
0x18004866c  jz      short loc_1800485FF
0x18004866e  mov     r9d, r10d
0x180048671  jmp     short loc_180048650
0x180048673  jbe     short loc_180048683
0x180048675  lea     r8d, [r10+1]
0x180048679  cmp     r8d, r9d
0x18004867c  jnz     short loc_180048650
0x18004867e  jmp     loc_1800485FF
0x180048683  mov     rax, [rbx]
0x180048686  cmp     rax, [rdx]
0x180048689  jnz     short loc_180048699
0x18004868b  mov     rax, [rbx+8]
0x18004868f  cmp     rax, [rdx+8]
0x180048693  jz      loc_1800485D3
0x180048699  cmp     r10d, r8d
0x18004869c  jle     short loc_1800486DE
0x18004869e  lea     r11d, [r10-1]
0x1800486a2  cmp     r11d, r8d
0x1800486a5  jl      short loc_1800486DE
0x1800486a7  nop     word ptr [rax+rax+00000000h]
0x1800486b0  movsxd  rax, r11d
0x1800486b3  lea     rcx, [rax+rax*4]
0x1800486b7  cmp     edi, [rsi+rcx*8]
0x1800486ba  lea     rdx, [rsi+rcx*8]
0x1800486be  jnz     short loc_1800486DE
0x1800486c0  mov     rax, [rbx]
0x1800486c3  cmp     rax, [rdx]
0x1800486c6  jnz     short loc_1800486D6
0x1800486c8  mov     rax, [rbx+8]
0x1800486cc  cmp     rax, [rdx+8]
0x1800486d0  jz      loc_1800485D3
0x1800486d6  dec     r11d
0x1800486d9  cmp     r11d, r8d
0x1800486dc  jge     short loc_1800486B0
0x1800486de  lea     r8d, [r10+1]
0x1800486e2  cmp     r8d, r9d
0x1800486e5  jge     loc_1800485FF
0x1800486eb  nop     dword ptr [rax+rax+00h]
0x1800486f0  movsxd  rax, r8d
0x1800486f3  lea     rcx, [rax+rax*4]
0x1800486f7  cmp     edi, [rsi+rcx*8]
0x1800486fa  lea     rdx, [rsi+rcx*8]
0x1800486fe  jnz     loc_1800485FF
0x180048704  mov     rax, [rbx]
0x180048707  cmp     rax, [rdx]
0x18004870a  jnz     short loc_18004871A
0x18004870c  mov     rax, [rbx+8]
0x180048710  cmp     rax, [rdx+8]
0x180048714  jz      loc_1800485D3
0x18004871a  inc     r8d
0x18004871d  cmp     r8d, r9d
0x180048720  jl      short loc_1800486F0
0x180048722  jmp     loc_1800485FF
0x180048727  mov     ebx, 0C00D36BDh
0x18004872c  jmp     loc_180048604
0x180048731  mov     rcx, rbp; SRWLock
0x180048734  mov     dword ptr [rbp+8], 0
0x18004873b  call    cs:__imp_ReleaseSRWLockExclusive
0x180048741  mov     eax, ebx
0x180048743  mov     rbx, [rsp+28h+arg_18]
0x180048748  add     rsp, 20h
0x18004874c  pop     rbp
0x18004874d  retn
0x18004874e  mov     rcx, rbp; SRWLock
0x180048751  call    cs:__imp_ReleaseSRWLockShared
0x180048757  mov     eax, ebx
0x180048759  mov     rbx, [rsp+28h+arg_18]
0x18004875e  add     rsp, 20h
0x180048762  pop     rbp
0x180048763  retn
```
