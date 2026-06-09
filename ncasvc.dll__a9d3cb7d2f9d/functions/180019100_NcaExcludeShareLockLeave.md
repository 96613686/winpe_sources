# NcaExcludeShareLockLeave

- ea: `0x180019100`
- end: `0x180019172`
- name: `NcaExcludeShareLockLeave`
- size: `114`
- prototype: `void __fastcall(int, RTL_SRWLOCK *)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180001400`
- `0x1800025c0`
- `0x180002e90`
- `0x180005180`
- `0x180005c20`
- `0x180006190`
- `0x180006940`
- `0x180007b58`
- `0x180009714`
- `0x18000a398`
- `0x18000ae34`
- `0x180011d54`
- `0x180012d78`
- `0x180013f60`
- `0x180014620`
- `0x1800164e0`
- `0x180018c40`

## callees

- `0x180004f04`
- `0x180019100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019144`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019144`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001915a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001915a`

## pseudocode

```c
void __fastcall NcaExcludeShareLockLeave(int a1, RTL_SRWLOCK *a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  if ( a1 )
  {
    if ( a1 == 1 )
      ReleaseSRWLockShared(a2);
  }
  else
  {
    ReleaseSRWLockExclusive(a2);
  }
}

```

## disassembly

```asm
0x180019100  mov     [rsp+arg_0], rbx
0x180019105  push    rdi
0x180019106  sub     rsp, 20h
0x18001910a  mov     rdi, rdx
0x18001910d  mov     ebx, ecx
0x18001910f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019116  lea     rax, WPP_GLOBAL_Control
0x18001911d  cmp     rcx, rax
0x180019120  jz      short loc_18001913D
0x180019122  test    byte ptr [rcx+1Ch], 8
0x180019126  jz      short loc_18001913D
0x180019128  mov     rcx, [rcx+10h]
0x18001912c  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x180019133  mov     edx, 27h ; '''
0x180019138  call    WPP_SF_
0x18001913d  test    ebx, ebx
0x18001913f  jnz     short loc_180019152
0x180019141  mov     rcx, rdi; SRWLock
0x180019144  call    cs:__imp_ReleaseSRWLockExclusive
0x18001914b  nop     dword ptr [rax+rax+00h]
0x180019150  jmp     short loc_180019166
0x180019152  cmp     ebx, 1
0x180019155  jnz     short loc_180019166
0x180019157  mov     rcx, rdi; SRWLock
0x18001915a  call    cs:__imp_ReleaseSRWLockShared
0x180019161  nop     dword ptr [rax+rax+00h]
0x180019166  mov     rbx, [rsp+28h+arg_0]
0x18001916b  add     rsp, 20h
0x18001916f  pop     rdi
0x180019170  retn
```
