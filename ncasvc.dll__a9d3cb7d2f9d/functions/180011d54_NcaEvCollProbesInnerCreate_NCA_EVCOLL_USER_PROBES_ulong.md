# NcaEvCollProbesInnerCreate(NCA_EVCOLL_USER_PROBES_ *,ulong)

- ea: `0x180011d54`
- end: `0x180011f0a`
- name: `?NcaEvCollProbesInnerCreate@@YAKPEAUNCA_EVCOLL_USER_PROBES_@@K@Z`
- size: `438`
- prototype: `__int64 __fastcall(struct NCA_EVCOLL_USER_PROBES_ *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800127ec`
- `0x180012b6c`

## callees

- `0x180004f34`
- `0x180011744`
- `0x180011d54`
- `0x180016798`
- `0x180019100`
- `0x180019784`
- `0x18001ac28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011d72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011d72`

## pseudocode

```c
__int64 __fastcall NcaEvCollProbesInnerCreate(struct NCA_EVCOLL_USER_PROBES_ *a1, unsigned int a2)
{
  unsigned int v4; // r14d
  int v5; // r13d
  unsigned int v6; // ebp
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // r12
  unsigned int v11; // eax
  unsigned int v12; // edi

  AcquireSRWLockShared(&SRWLock);
  v4 = xmmword_180028BC8;
  v5 = xmmword_180028BD8;
  v6 = xmmword_180028BC8 + xmmword_180028BD8;
  v7 = NcaHResultToWindowsError((int)xmmword_180028BC8 + xmmword_180028BD8 < (unsigned int)xmmword_180028BC8 ? 0x80070216 : 0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 43;
LABEL_5:
      WPP_SF_d(v8[2], v9, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, v7);
    }
  }
  else
  {
    v10 = (_QWORD *)((char *)a1 + 24);
    v11 = NcaAllocCheckSize(392, v6, (char *)a1 + 24);
    v7 = NcaHResultToWindowsError(v11);
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 44;
        goto LABEL_5;
      }
    }
    else
    {
      *((_DWORD *)a1 + 4) = v6;
      v12 = 0;
      *((_DWORD *)a1 + 8) = a2;
      while ( 1 )
      {
        if ( v12 >= v4 )
        {
          while ( 1 )
          {
            if ( v12 >= v6 )
            {
              NcaDAPEvidenceSnapshotSetUserState(17, v5 != 0, a2);
              goto LABEL_24;
            }
            v7 = NcaEvCollProbeStart(v12 - v4, 1, a1, *v10 + 392LL * v12);
            if ( v7 )
              break;
            ++v12;
          }
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 46;
            goto LABEL_5;
          }
          goto LABEL_24;
        }
        v7 = NcaEvCollProbeStart(v12, 0, a1, *v10 + 392LL * v12);
        if ( v7 )
          break;
        ++v12;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 45;
        goto LABEL_5;
      }
    }
  }
LABEL_24:
  NcaExcludeShareLockLeave(1, &SRWLock);
  return v7;
}

```

## disassembly

```asm
0x180011d54  push    rbx
0x180011d56  push    rbp
0x180011d57  push    rsi
0x180011d58  push    rdi
0x180011d59  push    r12
0x180011d5b  push    r13
0x180011d5d  push    r14
0x180011d5f  push    r15
0x180011d61  sub     rsp, 28h
0x180011d65  mov     rsi, rcx
0x180011d68  mov     r15d, edx
0x180011d6b  lea     rcx, SRWLock; SRWLock
0x180011d72  call    cs:__imp_AcquireSRWLockShared
0x180011d79  nop     dword ptr [rax+rax+00h]
0x180011d7e  mov     r14d, dword ptr cs:xmmword_180028BC8
0x180011d85  mov     r13d, dword ptr cs:xmmword_180028BD8
0x180011d8c  lea     ebp, [r14+r13]
0x180011d90  cmp     ebp, r14d
0x180011d93  sbb     ecx, ecx
0x180011d95  and     ecx, 80070216h
0x180011d9b  call    NcaHResultToWindowsError
0x180011da0  mov     ebx, eax
0x180011da2  test    eax, eax
0x180011da4  jz      short loc_180011DE4
0x180011da6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dad  lea     rax, WPP_GLOBAL_Control
0x180011db4  cmp     rcx, rax
0x180011db7  jz      loc_180011EE5
0x180011dbd  test    byte ptr [rcx+1Ch], 1
0x180011dc1  jz      loc_180011EE5
0x180011dc7  mov     edx, 2Bh ; '+'
0x180011dcc  mov     rcx, [rcx+10h]
0x180011dd0  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180011dd7  mov     r9d, ebx
0x180011dda  call    WPP_SF_d
0x180011ddf  jmp     loc_180011EE5
0x180011de4  lea     r12, [rsi+18h]
0x180011de8  mov     edx, ebp
0x180011dea  mov     r8, r12
0x180011ded  mov     ecx, 188h
0x180011df2  call    NcaAllocCheckSize
0x180011df7  mov     ecx, eax
0x180011df9  call    NcaHResultToWindowsError
0x180011dfe  mov     ebx, eax
0x180011e00  test    eax, eax
0x180011e02  jz      short loc_180011E2C
0x180011e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e0b  lea     rax, WPP_GLOBAL_Control
0x180011e12  cmp     rcx, rax
0x180011e15  jz      loc_180011EE5
0x180011e1b  test    byte ptr [rcx+1Ch], 1
0x180011e1f  jz      loc_180011EE5
0x180011e25  mov     edx, 2Ch ; ','
0x180011e2a  jmp     short loc_180011DCC
0x180011e2c  mov     [rsi+10h], ebp
0x180011e2f  xor     edi, edi
0x180011e31  mov     [rsi+20h], r15d
0x180011e35  cmp     edi, r14d
0x180011e38  jnb     short loc_180011E80
0x180011e3a  mov     eax, edi
0x180011e3c  mov     r8, rsi
0x180011e3f  imul    r9, rax, 188h
0x180011e46  xor     edx, edx
0x180011e48  mov     ecx, edi
0x180011e4a  add     r9, [r12]
0x180011e4e  call    ?NcaEvCollProbeStart@@YAKKW4NCA_EVCOLL_PROBE_ORIGIN_@@PEAUNCA_EVCOLL_USER_PROBES_@@PEAUNCA_EVCOLL_PROBE_@@@Z; NcaEvCollProbeStart(ulong,NCA_EVCOLL_PROBE_ORIGIN_,NCA_EVCOLL_USER_PROBES_ *,NCA_EVCOLL_PROBE_ *)
0x180011e53  mov     ebx, eax
0x180011e55  test    eax, eax
0x180011e57  jnz     short loc_180011E5D
0x180011e59  inc     edi
0x180011e5b  jmp     short loc_180011E35
0x180011e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e64  lea     rax, WPP_GLOBAL_Control
0x180011e6b  cmp     rcx, rax
0x180011e6e  jz      short loc_180011EE5
0x180011e70  test    byte ptr [rcx+1Ch], 1
0x180011e74  jz      short loc_180011EE5
0x180011e76  mov     edx, 2Dh ; '-'
0x180011e7b  jmp     loc_180011DCC
0x180011e80  cmp     edi, ebp
0x180011e82  jnb     short loc_180011ED0
0x180011e84  mov     eax, edi
0x180011e86  mov     ecx, edi
0x180011e88  imul    r9, rax, 188h
0x180011e8f  sub     ecx, r14d
0x180011e92  mov     r8, rsi
0x180011e95  add     r9, [r12]
0x180011e99  mov     edx, 1
0x180011e9e  call    ?NcaEvCollProbeStart@@YAKKW4NCA_EVCOLL_PROBE_ORIGIN_@@PEAUNCA_EVCOLL_USER_PROBES_@@PEAUNCA_EVCOLL_PROBE_@@@Z; NcaEvCollProbeStart(ulong,NCA_EVCOLL_PROBE_ORIGIN_,NCA_EVCOLL_USER_PROBES_ *,NCA_EVCOLL_PROBE_ *)
0x180011ea3  mov     ebx, eax
0x180011ea5  test    eax, eax
0x180011ea7  jnz     short loc_180011EAD
0x180011ea9  inc     edi
0x180011eab  jmp     short loc_180011E80
0x180011ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180011eb4  lea     rax, WPP_GLOBAL_Control
0x180011ebb  cmp     rcx, rax
0x180011ebe  jz      short loc_180011EE5
0x180011ec0  test    byte ptr [rcx+1Ch], 1
0x180011ec4  jz      short loc_180011EE5
0x180011ec6  mov     edx, 2Eh ; '.'
0x180011ecb  jmp     loc_180011DCC
0x180011ed0  xor     edx, edx
0x180011ed2  mov     r8d, r15d
0x180011ed5  test    r13d, r13d
0x180011ed8  mov     ecx, 11h
0x180011edd  setnz   dl
0x180011ee0  call    NcaDAPEvidenceSnapshotSetUserState
0x180011ee5  lea     rdx, SRWLock
0x180011eec  mov     ecx, 1
0x180011ef1  call    NcaExcludeShareLockLeave
0x180011ef6  mov     eax, ebx
0x180011ef8  add     rsp, 28h
0x180011efc  pop     r15
0x180011efe  pop     r14
0x180011f00  pop     r13
0x180011f02  pop     r12
0x180011f04  pop     rdi
0x180011f05  pop     rsi
0x180011f06  pop     rbp
0x180011f07  pop     rbx
0x180011f08  retn
```
