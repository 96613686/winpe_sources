# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetUINT32(_GUID const &,uint *)

- ea: `0x180047db0`
- end: `0x180047fc4`
- name: `?GetUINT32@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAI@Z`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180149720`

## callees

- `0x180047db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180047de8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180047de8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180047fb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180047fb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047dd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047dd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047e6f`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetUINT32(
        __int64 a1,
        unsigned int *a2,
        _DWORD *a3)
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
          if ( *(_WORD *)(v11 + 16) == 19 )
          {
            v12 = 0;
            *a3 = *(_DWORD *)(v11 + 24);
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
0x180047db0  mov     [rsp+arg_18], rbx
0x180047db5  push    rbp
0x180047db6  sub     rsp, 20h
0x180047dba  mov     [rsp+28h+arg_0], rsi
0x180047dbf  lea     rbp, [rcx+10h]
0x180047dc3  mov     [rsp+28h+arg_10], r14
0x180047dc8  mov     rbx, rdx
0x180047dcb  mov     r14, r8
0x180047dce  mov     rsi, rcx
0x180047dd1  call    cs:__imp_GetCurrentThreadId
0x180047dd7  mov     r9d, [rbp+8]
0x180047ddb  cmp     r9d, eax
0x180047dde  jnz     short loc_180047DE5
0x180047de0  inc     dword ptr [rbp+0Ch]
0x180047de3  jmp     short loc_180047DEE
0x180047de5  mov     rcx, rbp; SRWLock
0x180047de8  call    cs:__imp_AcquireSRWLockShared
0x180047dee  mov     r9d, [rsi+2Ch]
0x180047df2  mov     [rsp+28h+arg_8], rdi
0x180047df7  test    r9d, r9d
0x180047dfa  jz      short loc_180047E6A
0x180047dfc  mov     edi, [rbx]
0x180047dfe  cmp     r9d, 4
0x180047e02  jge     loc_180047EAC
0x180047e08  test    r9d, r9d
0x180047e0b  jle     short loc_180047E6A
0x180047e0d  mov     r10, [rsi+20h]
0x180047e11  xor     r8d, r8d
0x180047e14  nop     dword ptr [rax+00h]
0x180047e18  nop     dword ptr [rax+rax+00000000h]
0x180047e20  movsxd  rax, r8d
0x180047e23  lea     rcx, [rax+rax*4]
0x180047e27  cmp     [r10+rcx*8], edi
0x180047e2b  lea     rdx, [r10+rcx*8]
0x180047e2f  jnz     short loc_180047E60
0x180047e31  mov     rax, [rbx]
0x180047e34  cmp     rax, [rdx]
0x180047e37  jnz     short loc_180047E62
0x180047e39  mov     rax, [rbx+8]
0x180047e3d  cmp     rax, [rdx+8]
0x180047e41  jnz     short loc_180047E62
0x180047e43  lea     rax, [rdx+10h]
0x180047e47  test    rax, rax
0x180047e4a  jz      short loc_180047E6A
0x180047e4c  cmp     word ptr [rax], 13h
0x180047e50  jnz     loc_180047F87
0x180047e56  mov     eax, [rax+8]
0x180047e59  xor     ebx, ebx
0x180047e5b  mov     [r14], eax
0x180047e5e  jmp     short loc_180047E6F
0x180047e60  ja      short loc_180047E6A
0x180047e62  inc     r8d
0x180047e65  cmp     r8d, r9d
0x180047e68  jl      short loc_180047E20
0x180047e6a  mov     ebx, 0C00D36E6h
0x180047e6f  call    cs:__imp_GetCurrentThreadId
0x180047e75  mov     ecx, [rbp+8]
0x180047e78  mov     r14, [rsp+28h+arg_10]
0x180047e7d  mov     rdi, [rsp+28h+arg_8]
0x180047e82  mov     rsi, [rsp+28h+arg_0]
0x180047e87  cmp     ecx, eax
0x180047e89  jnz     loc_180047FAE
0x180047e8f  mov     ecx, [rbp+0Ch]
0x180047e92  test    ecx, ecx
0x180047e94  jz      loc_180047F91
0x180047e9a  dec     ecx
0x180047e9c  mov     eax, ebx
0x180047e9e  mov     [rbp+0Ch], ecx
0x180047ea1  mov     rbx, [rsp+28h+arg_18]
0x180047ea6  add     rsp, 20h
0x180047eaa  pop     rbp
0x180047eab  retn
0x180047eac  mov     rsi, [rsi+20h]
0x180047eb0  xor     r8d, r8d
0x180047eb3  lea     eax, [r8+r9]
0x180047eb7  cdq
0x180047eb8  sub     eax, edx
0x180047eba  sar     eax, 1
0x180047ebc  movsxd  r10, eax
0x180047ebf  lea     rdx, [r10+r10*4]
0x180047ec3  cmp     edi, [rsi+rdx*8]
0x180047ec6  lea     rdx, [rsi+rdx*8]
0x180047eca  jnb     short loc_180047ED6
0x180047ecc  cmp     r10d, r8d
0x180047ecf  jz      short loc_180047E6A
0x180047ed1  mov     r9d, r10d
0x180047ed4  jmp     short loc_180047EB3
0x180047ed6  jbe     short loc_180047EE3
0x180047ed8  lea     r8d, [r10+1]
0x180047edc  cmp     r8d, r9d
0x180047edf  jnz     short loc_180047EB3
0x180047ee1  jmp     short loc_180047E6A
0x180047ee3  mov     rax, [rbx]
0x180047ee6  cmp     rax, [rdx]
0x180047ee9  jnz     short loc_180047EF9
0x180047eeb  mov     rax, [rbx+8]
0x180047eef  cmp     rax, [rdx+8]
0x180047ef3  jz      loc_180047E43
0x180047ef9  cmp     r10d, r8d
0x180047efc  jle     short loc_180047F3E
0x180047efe  lea     r11d, [r10-1]
0x180047f02  cmp     r11d, r8d
0x180047f05  jl      short loc_180047F3E
0x180047f07  nop     word ptr [rax+rax+00000000h]
0x180047f10  movsxd  rax, r11d
0x180047f13  lea     rcx, [rax+rax*4]
0x180047f17  cmp     edi, [rsi+rcx*8]
0x180047f1a  lea     rdx, [rsi+rcx*8]
0x180047f1e  jnz     short loc_180047F3E
0x180047f20  mov     rax, [rbx]
0x180047f23  cmp     rax, [rdx]
0x180047f26  jnz     short loc_180047F36
0x180047f28  mov     rax, [rbx+8]
0x180047f2c  cmp     rax, [rdx+8]
0x180047f30  jz      loc_180047E43
0x180047f36  dec     r11d
0x180047f39  cmp     r11d, r8d
0x180047f3c  jge     short loc_180047F10
0x180047f3e  lea     r8d, [r10+1]
0x180047f42  cmp     r8d, r9d
0x180047f45  jge     loc_180047E6A
0x180047f4b  nop     dword ptr [rax+rax+00h]
0x180047f50  movsxd  rax, r8d
0x180047f53  lea     rcx, [rax+rax*4]
0x180047f57  cmp     edi, [rsi+rcx*8]
0x180047f5a  lea     rdx, [rsi+rcx*8]
0x180047f5e  jnz     loc_180047E6A
0x180047f64  mov     rax, [rbx]
0x180047f67  cmp     rax, [rdx]
0x180047f6a  jnz     short loc_180047F7A
0x180047f6c  mov     rax, [rbx+8]
0x180047f70  cmp     rax, [rdx+8]
0x180047f74  jz      loc_180047E43
0x180047f7a  inc     r8d
0x180047f7d  cmp     r8d, r9d
0x180047f80  jl      short loc_180047F50
0x180047f82  jmp     loc_180047E6A
0x180047f87  mov     ebx, 0C00D36BDh
0x180047f8c  jmp     loc_180047E6F
0x180047f91  mov     rcx, rbp; SRWLock
0x180047f94  mov     dword ptr [rbp+8], 0
0x180047f9b  call    cs:__imp_ReleaseSRWLockExclusive
0x180047fa1  mov     eax, ebx
0x180047fa3  mov     rbx, [rsp+28h+arg_18]
0x180047fa8  add     rsp, 20h
0x180047fac  pop     rbp
0x180047fad  retn
0x180047fae  mov     rcx, rbp; SRWLock
0x180047fb1  call    cs:__imp_ReleaseSRWLockShared
0x180047fb7  mov     eax, ebx
0x180047fb9  mov     rbx, [rsp+28h+arg_18]
0x180047fbe  add     rsp, 20h
0x180047fc2  pop     rbp
0x180047fc3  retn
```
