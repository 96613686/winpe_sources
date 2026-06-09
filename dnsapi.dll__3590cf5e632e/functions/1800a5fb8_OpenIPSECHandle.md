# OpenIPSECHandle

- ea: `0x1800a5fb8`
- end: `0x1800a6084`
- name: `OpenIPSECHandle`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a5890`

## callees

- `0x1800a5fb8`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5fce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5fce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a5fea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a606a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a5fea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a606a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5ff9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a605c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a605c`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800a6025`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800a6025`

## pseudocode

```c
__int64 OpenIPSECHandle()
{
  DWORD v0; // ebx
  DWORD v1; // eax

  v0 = 0;
  AcquireSRWLockShared(&stru_180111D48);
  if ( engineHandle )
  {
    ReleaseSRWLockShared(&stru_180111D48);
  }
  else
  {
    ReleaseSRWLockShared(&stru_180111D48);
    AcquireSRWLockExclusive(&stru_180111D48);
    if ( !engineHandle )
    {
      v1 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
      v0 = v1;
      if ( v1 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 10, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids, v1);
      }
    }
    ReleaseSRWLockExclusive(&stru_180111D48);
  }
  return v0;
}

```

## disassembly

```asm
0x1800a5fb8  mov     [rsp+arg_0], rbx
0x1800a5fbd  push    rdi
0x1800a5fbe  sub     rsp, 30h
0x1800a5fc2  lea     rdi, stru_180111D48
0x1800a5fc9  xor     ebx, ebx
0x1800a5fcb  mov     rcx, rdi; SRWLock
0x1800a5fce  call    cs:__imp_AcquireSRWLockShared
0x1800a5fd5  nop     dword ptr [rax+rax+00h]
0x1800a5fda  cmp     cs:engineHandle, rbx
0x1800a5fe1  mov     rcx, rdi; SRWLock
0x1800a5fe4  jnz     loc_1800A606A
0x1800a5fea  call    cs:__imp_ReleaseSRWLockShared
0x1800a5ff1  nop     dword ptr [rax+rax+00h]
0x1800a5ff6  mov     rcx, rdi; SRWLock
0x1800a5ff9  call    cs:__imp_AcquireSRWLockExclusive
0x1800a6000  nop     dword ptr [rax+rax+00h]
0x1800a6005  cmp     cs:engineHandle, rbx
0x1800a600c  jnz     short loc_1800A6059
0x1800a600e  lea     rax, engineHandle
0x1800a6015  xor     r9d, r9d; session
0x1800a6018  xor     r8d, r8d; authIdentity
0x1800a601b  mov     [rsp+38h+engineHandle], rax; engineHandle
0x1800a6020  lea     edx, [rbx+0Ah]; authnService
0x1800a6023  xor     ecx, ecx; serverName
0x1800a6025  call    cs:__imp_FwpmEngineOpen0
0x1800a602c  nop     dword ptr [rax+rax+00h]
0x1800a6031  mov     ebx, eax
0x1800a6033  test    eax, eax
0x1800a6035  jz      short loc_1800A6059
0x1800a6037  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a603e  jz      short loc_1800A6059
0x1800a6040  mov     edx, 0Ah
0x1800a6045  lea     r8, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids
0x1800a604c  mov     ecx, 40Bh
0x1800a6051  mov     r9d, eax
0x1800a6054  call    WPP_SF_d
0x1800a6059  mov     rcx, rdi; SRWLock
0x1800a605c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a6063  nop     dword ptr [rax+rax+00h]
0x1800a6068  jmp     short loc_1800A6076
0x1800a606a  call    cs:__imp_ReleaseSRWLockShared
0x1800a6071  nop     dword ptr [rax+rax+00h]
0x1800a6076  mov     eax, ebx
0x1800a6078  mov     rbx, [rsp+38h+arg_0]
0x1800a607d  add     rsp, 30h
0x1800a6081  pop     rdi
0x1800a6082  retn
```
