# CldHsmCreateFileContext

- ea: `0x14006f0c0`
- end: `0x14006f19a`
- name: `CldHsmCreateFileContext`
- size: `218`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14001e600`
- `0x14006f0c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006f0de`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006f0de`
- `FLTMGR!FltInitializePushLock` at `0x14006f104`
- `FLTMGR!FltInitializePushLock` at `0x14006f114`
- `FLTMGR!FltInitializePushLock` at `0x14006f104`
- `FLTMGR!FltInitializePushLock` at `0x14006f114`

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
0x14006f0c0  push    rbx
0x14006f0c2  push    rbp
0x14006f0c3  push    rsi
0x14006f0c4  push    rdi
0x14006f0c5  push    r14
0x14006f0c7  sub     rsp, 30h
0x14006f0cb  mov     rdi, rcx
0x14006f0ce  mov     rsi, r9
0x14006f0d1  lea     rcx, stru_140028A80; Lookaside
0x14006f0d8  mov     rbp, r8
0x14006f0db  mov     r14, rdx
0x14006f0de  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14006f0e5  nop     dword ptr [rax+rax+00h]
0x14006f0ea  mov     rbx, rax
0x14006f0ed  test    rax, rax
0x14006f0f0  jz      short loc_14006F14E
0x14006f0f2  xor     edx, edx; Val
0x14006f0f4  mov     rcx, rax; void *
0x14006f0f7  lea     r8d, [rdx+48h]; Size
0x14006f0fb  call    memset
0x14006f100  lea     rcx, [rbx+18h]; PushLock
0x14006f104  call    cs:__imp_FltInitializePushLock
0x14006f10b  nop     dword ptr [rax+rax+00h]
0x14006f110  lea     rcx, [rbx+30h]; PushLock
0x14006f114  call    cs:__imp_FltInitializePushLock
0x14006f11b  nop     dword ptr [rax+rax+00h]
0x14006f120  mov     eax, [rbx+28h]
0x14006f123  and     eax, 0FF133000h
0x14006f128  mov     [rbx+10h], rbp
0x14006f12c  or      eax, 133000h
0x14006f131  mov     [rbx+8], r14
0x14006f135  mov     [rbx+28h], eax
0x14006f138  mov     [rbx], rdi
0x14006f13b  mov     [rsi], rbx
0x14006f13e  xor     ebx, ebx
0x14006f140  mov     eax, ebx
0x14006f142  add     rsp, 30h
0x14006f146  pop     r14
0x14006f148  pop     rdi
0x14006f149  pop     rsi
0x14006f14a  pop     rbp
0x14006f14b  pop     rbx
0x14006f14c  retn
0x14006f14e  mov     ebx, 0C000009Ah
0x14006f153  mov     ecx, ebx
0x14006f155  call    HsmDbgBreakOnStatus
0x14006f15a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f161  lea     rax, WPP_GLOBAL_Control
0x14006f168  cmp     rcx, rax
0x14006f16b  jz      short loc_14006F140
0x14006f16d  test    dword ptr [rcx+2Ch], 100h
0x14006f174  jz      short loc_14006F140
0x14006f176  cmp     byte ptr [rcx+29h], 2
0x14006f17a  jb      short loc_14006F140
0x14006f17c  mov     rcx, [rcx+18h]
0x14006f180  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x14006f187  mov     edx, 0Bh
0x14006f18c  mov     [rsp+58h+var_38], ebx
0x14006f190  mov     r9, rdi
0x14006f193  call    WPP_SF_qd
0x14006f198  jmp     short loc_14006F140
```
