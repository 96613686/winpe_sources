# PEvtSetState(PEvtCommand)

- ea: `0x180012d0c`
- end: `0x180012d92`
- name: `?PEvtSetState@@YA?AW4PEvtCommand@@W41@@Z`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800053f0`
- `0x180012d98`

## callees

- `0x180012d0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012d7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012d43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012d43`

## pseudocode

```c
__int64 __fastcall PEvtSetState(__int32 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  _QWORD *i; // rax

  v2 = *((_DWORD *)g_pPixEvtCtrlBlk + 2);
  if ( v2 != a1 )
  {
    _InterlockedExchange((volatile __int32 *)g_pPixEvtCtrlBlk + 2, a1);
    AcquireSRWLockExclusive(&SRWLock);
    v3 = qword_18001E8A0;
    for ( i = *(_QWORD **)qword_18001E8A0; i != (_QWORD *)v3; i = (_QWORD *)*i )
    {
      i[2] = 0;
      i[3] = a1 == 0;
      i[4] = -1;
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  return v2;
}

```

## disassembly

```asm
0x180012d0c  mov     [rsp+arg_0], rbx
0x180012d11  push    rdi
0x180012d12  sub     rsp, 20h
0x180012d16  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012d1d  mov     ebx, ecx
0x180012d1f  mov     edi, [rax+8]
0x180012d22  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012d29  mov     edx, [rax+8]
0x180012d2c  cmp     edx, ecx
0x180012d2e  jz      short loc_180012D85
0x180012d30  mov     rdx, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012d37  mov     eax, ecx
0x180012d39  lea     rcx, SRWLock; SRWLock
0x180012d40  xchg    eax, [rdx+8]
0x180012d43  call    cs:__imp_AcquireSRWLockExclusive
0x180012d49  mov     rcx, cs:qword_18001E8A0
0x180012d50  mov     rax, [rcx]
0x180012d53  cmp     rax, rcx
0x180012d56  jz      short loc_180012D78
0x180012d58  xor     edx, edx
0x180012d5a  mov     qword ptr [rax+10h], 0
0x180012d62  test    ebx, ebx
0x180012d64  setz    dl
0x180012d67  mov     [rax+18h], rdx
0x180012d6b  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x180012d73  mov     rax, [rax]
0x180012d76  jmp     short loc_180012D53
0x180012d78  lea     rcx, SRWLock; SRWLock
0x180012d7f  call    cs:__imp_ReleaseSRWLockExclusive
0x180012d85  mov     rbx, [rsp+28h+arg_0]
0x180012d8a  mov     eax, edi
0x180012d8c  add     rsp, 20h
0x180012d90  pop     rdi
0x180012d91  retn
```
