# FIPfFileFSOpPostCallbackCleanup

- ea: `0x140001790`
- end: `0x1400018c2`
- name: `FIPfFileFSOpPostCallbackCleanup`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001480`
- `0x140016bc0`

## callees

- `0x140001790`
- `0x140002548`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x14000183c`
- `FLTMGR!FltReleaseContext` at `0x14000183c`

## pseudocode

```c
void __fastcall FIPfFileFSOpPostCallbackCleanup(__int64 a1)
{
  __int64 v1; // rax
  volatile signed __int32 *v2; // r10

  v1 = a1 & 7;
  if ( v1 == 2 )
  {
    _InterlockedIncrement(&dword_14000990C);
    _InterlockedIncrement(&dword_140009880);
    if ( _InterlockedExchangeAdd(&dword_14000953C, 0xFFFFFFFF) == 1 )
    {
      dword_140009524 = _InterlockedIncrement(&dword_140009640);
      dword_140009520 = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
                      + ((MEMORY[0xFFFFF78000000004] * (unsigned __int64)MEMORY[0xFFFFF78000000320]) >> 24);
    }
    FIPfOpenAttemptsRundownEnd(a1 & 0xFFFFFFFFFFFFFFF8uLL);
    _InterlockedIncrement(v2 + 118);
    _InterlockedIncrement(&dword_1400098A8);
    _InterlockedIncrement(v2 + 123);
    _InterlockedIncrement(&dword_1400098BC);
    FltReleaseContext((PFLT_CONTEXT)v2);
  }
  else if ( v1 == 1 )
  {
    _InterlockedIncrement(&dword_140009910);
    _InterlockedIncrement(&dword_14000986C);
    if ( _InterlockedExchangeAdd(&dword_14000956C, 0xFFFFFFFF) == 1 )
    {
      dword_140009554 = _InterlockedIncrement(&dword_140009640);
      dword_140009550 = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
                      + ((MEMORY[0xFFFFF78000000004] * (unsigned __int64)MEMORY[0xFFFFF78000000320]) >> 24);
    }
  }
}

```

## disassembly

```asm
0x140001790  sub     rsp, 28h
0x140001794  mov     rax, rcx
0x140001797  mov     r10, rcx
0x14000179a  and     eax, 7
0x14000179d  cmp     rax, 2
0x1400017a1  jnz     loc_14000184E
0x1400017a7  lock inc cs:dword_14000990C
0x1400017ae  and     r10, 0FFFFFFFFFFFFFFF8h
0x1400017b2  lock inc cs:dword_140009880
0x1400017b9  mov     eax, 0FFFFFFFFh
0x1400017be  lock xadd cs:dword_14000953C, eax
0x1400017c6  cmp     eax, 1
0x1400017c9  jnz     short loc_140001813
0x1400017cb  mov     r8d, eax
0x1400017ce  lock xadd cs:dword_140009640, r8d
0x1400017d7  inc     r8d
0x1400017da  mov     rdx, 0FFFFF78000000320h
0x1400017e4  mov     rdx, [rdx]
0x1400017e7  mov     eax, ds:0FFFFF78000000004h
0x1400017f0  mov     ecx, edx
0x1400017f2  shr     rdx, 20h
0x1400017f6  imul    rcx, rax
0x1400017fa  imul    edx, eax
0x1400017fd  mov     cs:dword_140009524, r8d
0x140001804  shr     rcx, 18h
0x140001808  shl     edx, 8
0x14000180b  add     ecx, edx
0x14000180d  mov     cs:dword_140009520, ecx
0x140001813  mov     rcx, r10
0x140001816  call    FIPfOpenAttemptsRundownEnd
0x14000181b  lock inc dword ptr [r10+1D8h]
0x140001823  lock inc cs:dword_1400098A8
0x14000182a  lock inc dword ptr [r10+1ECh]
0x140001832  lock inc cs:dword_1400098BC
0x140001839  mov     rcx, r10; Context
0x14000183c  call    cs:__imp_FltReleaseContext
0x140001843  nop     dword ptr [rax+rax+00h]
0x140001848  add     rsp, 28h
0x14000184c  retn
0x14000184e  cmp     rax, 1
0x140001852  jnz     short loc_1400018BC
0x140001854  lock inc cs:dword_140009910
0x14000185b  lock inc cs:dword_14000986C
0x140001862  mov     eax, 0FFFFFFFFh
0x140001867  lock xadd cs:dword_14000956C, eax
0x14000186f  cmp     eax, 1
0x140001872  jnz     short loc_1400018BC
0x140001874  mov     r8d, eax
0x140001877  lock xadd cs:dword_140009640, r8d
0x140001880  inc     r8d
0x140001883  mov     rdx, 0FFFFF78000000320h
0x14000188d  mov     rdx, [rdx]
0x140001890  mov     eax, ds:0FFFFF78000000004h
0x140001899  mov     ecx, edx
0x14000189b  shr     rdx, 20h
0x14000189f  imul    rcx, rax
0x1400018a3  imul    edx, eax
0x1400018a6  mov     cs:dword_140009554, r8d
0x1400018ad  shr     rcx, 18h
0x1400018b1  shl     edx, 8
0x1400018b4  add     ecx, edx
0x1400018b6  mov     cs:dword_140009550, ecx
0x1400018bc  add     rsp, 28h
0x1400018c0  retn
```
