# CldHsmCreateFileContext

- ea: `0x14006efa0`
- end: `0x14006f07a`
- name: `CldHsmCreateFileContext`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14001e580`
- `0x14006efa0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006efbe`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006efbe`
- `FLTMGR!FltInitializePushLock` at `0x14006efe4`
- `FLTMGR!FltInitializePushLock` at `0x14006eff4`
- `FLTMGR!FltInitializePushLock` at `0x14006efe4`
- `FLTMGR!FltInitializePushLock` at `0x14006eff4`

## pseudocode

```c
__int64 __fastcall CldHsmCreateFileContext(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 **a4)
{
  unsigned __int64 *v8; // rax
  unsigned __int64 *v9; // rbx
  unsigned int v10; // eax
  unsigned int v11; // ebx

  v8 = (unsigned __int64 *)ExAllocateFromPagedLookasideList(&stru_140028A80);
  v9 = v8;
  if ( v8 )
  {
    memset(v8, 0, 0x48u);
    FltInitializePushLock(v9 + 3);
    FltInitializePushLock(v9 + 6);
    v10 = v9[5] & 0xFF133000;
    v9[2] = a3;
    v9[1] = a2;
    *((_DWORD *)v9 + 10) = v10 | 0x133000;
    *v9 = a1;
    *a4 = v9;
    return 0;
  }
  else
  {
    v11 = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids,
        a1,
        -1073741670);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x14006efa0  push    rbx
0x14006efa2  push    rbp
0x14006efa3  push    rsi
0x14006efa4  push    rdi
0x14006efa5  push    r14
0x14006efa7  sub     rsp, 30h
0x14006efab  mov     rdi, rcx
0x14006efae  mov     rsi, r9
0x14006efb1  lea     rcx, stru_140028A80; Lookaside
0x14006efb8  mov     rbp, r8
0x14006efbb  mov     r14, rdx
0x14006efbe  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14006efc5  nop     dword ptr [rax+rax+00h]
0x14006efca  mov     rbx, rax
0x14006efcd  test    rax, rax
0x14006efd0  jz      short loc_14006F02E
0x14006efd2  xor     edx, edx; Val
0x14006efd4  mov     rcx, rax; void *
0x14006efd7  lea     r8d, [rdx+48h]; Size
0x14006efdb  call    memset
0x14006efe0  lea     rcx, [rbx+18h]; PushLock
0x14006efe4  call    cs:__imp_FltInitializePushLock
0x14006efeb  nop     dword ptr [rax+rax+00h]
0x14006eff0  lea     rcx, [rbx+30h]; PushLock
0x14006eff4  call    cs:__imp_FltInitializePushLock
0x14006effb  nop     dword ptr [rax+rax+00h]
0x14006f000  mov     eax, [rbx+28h]
0x14006f003  and     eax, 0FF133000h
0x14006f008  mov     [rbx+10h], rbp
0x14006f00c  or      eax, 133000h
0x14006f011  mov     [rbx+8], r14
0x14006f015  mov     [rbx+28h], eax
0x14006f018  mov     [rbx], rdi
0x14006f01b  mov     [rsi], rbx
0x14006f01e  xor     ebx, ebx
0x14006f020  mov     eax, ebx
0x14006f022  add     rsp, 30h
0x14006f026  pop     r14
0x14006f028  pop     rdi
0x14006f029  pop     rsi
0x14006f02a  pop     rbp
0x14006f02b  pop     rbx
0x14006f02c  retn
0x14006f02e  mov     ebx, 0C000009Ah
0x14006f033  mov     ecx, ebx
0x14006f035  call    HsmDbgBreakOnStatus
0x14006f03a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f041  lea     rax, WPP_GLOBAL_Control
0x14006f048  cmp     rcx, rax
0x14006f04b  jz      short loc_14006F020
0x14006f04d  test    dword ptr [rcx+2Ch], 100h
0x14006f054  jz      short loc_14006F020
0x14006f056  cmp     byte ptr [rcx+29h], 2
0x14006f05a  jb      short loc_14006F020
0x14006f05c  mov     rcx, [rcx+18h]
0x14006f060  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x14006f067  mov     edx, 0Bh
0x14006f06c  mov     [rsp+58h+var_38], ebx
0x14006f070  mov     r9, rdi
0x14006f073  call    WPP_SF_qd
0x14006f078  jmp     short loc_14006F020
```
