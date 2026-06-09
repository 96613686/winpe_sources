# MQSec_GetLocalMachineSid(int,ulong *)

- ea: `0x180021890`
- end: `0x180021924`
- name: `?MQSec_GetLocalMachineSid@@YAPEAXHPEAK@Z`
- size: `148`
- prototype: `void *__fastcall(int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001f5c0`

## callees

- `0x18000b95c`
- `0x18001722c`
- `0x18002148c`
- `0x180021890`
- `0x18002f0a2`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180021911`
- `KERNEL32!LeaveCriticalSection` at `0x180021911`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PSID __fastcall MQSec_GetLocalMachineSid(int a1, unsigned int *a2)
{
  PSID v4; // rdi
  unsigned int v5; // ebx

  CCriticalSection::Lock((CCriticalSection *)&stru_180042DC0);
  if ( !byte_180043174 )
  {
    InitializeMachineSidFromRegistry();
    byte_180043174 = 1;
  }
  v4 = g_pLocalMachineSid;
  if ( a1 )
  {
    v5 = g_dwLocalMachineSidLen;
    if ( (_DWORD)g_dwLocalMachineSidLen )
    {
      v4 = MmAllocate((unsigned int)g_dwLocalMachineSidLen);
      v5 = g_dwLocalMachineSidLen;
      memcpy_0(v4, g_pLocalMachineSid, (unsigned int)g_dwLocalMachineSidLen);
    }
  }
  else
  {
    v5 = g_dwLocalMachineSidLen;
  }
  if ( a2 )
    *a2 = v5;
  LeaveCriticalSection(&stru_180042DC0);
  return v4;
}

```

## disassembly

```asm
0x180021890  push    rbx
0x180021892  push    rbp
0x180021893  push    rsi
0x180021894  push    rdi
0x180021895  sub     rsp, 28h
0x180021899  mov     rsi, rdx
0x18002189c  mov     ebx, ecx
0x18002189e  lea     rbp, stru_180042DC0
0x1800218a5  mov     [rsp+48h+arg_8], rbp
0x1800218aa  mov     rcx, rbp; this
0x1800218ad  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800218b2  nop
0x1800218b3  cmp     cs:byte_180043174, 0
0x1800218ba  jnz     short loc_1800218C8
0x1800218bc  call    InitializeMachineSidFromRegistry
0x1800218c1  mov     cs:byte_180043174, 1
0x1800218c8  mov     rdi, cs:?g_pLocalMachineSid@@3PEAXEA; void * g_pLocalMachineSid
0x1800218cf  test    ebx, ebx
0x1800218d1  jz      short loc_180021901
0x1800218d3  mov     ebx, cs:?g_dwLocalMachineSidLen@@3KA; ulong g_dwLocalMachineSidLen
0x1800218d9  test    ebx, ebx
0x1800218db  jz      short loc_180021907
0x1800218dd  mov     ecx, ebx; unsigned __int64
0x1800218df  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800218e4  mov     rdi, rax
0x1800218e7  mov     ebx, cs:?g_dwLocalMachineSidLen@@3KA; ulong g_dwLocalMachineSidLen
0x1800218ed  mov     r8d, ebx; Size
0x1800218f0  mov     rdx, cs:?g_pLocalMachineSid@@3PEAXEA; Src
0x1800218f7  mov     rcx, rax; void *
0x1800218fa  call    memcpy_0
0x1800218ff  jmp     short loc_180021907
0x180021901  mov     ebx, cs:?g_dwLocalMachineSidLen@@3KA; ulong g_dwLocalMachineSidLen
0x180021907  test    rsi, rsi
0x18002190a  jz      short loc_18002190E
0x18002190c  mov     [rsi], ebx
0x18002190e  mov     rcx, rbp; lpCriticalSection
0x180021911  call    cs:__imp_LeaveCriticalSection
0x180021917  nop
0x180021918  mov     rax, rdi
0x18002191b  add     rsp, 28h
0x18002191f  pop     rdi
0x180021920  pop     rsi
0x180021921  pop     rbp
0x180021922  pop     rbx
0x180021923  retn
```
