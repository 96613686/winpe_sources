# CldHsmCreateStreamContext

- ea: `0x14006e570`
- end: `0x14006e634`
- name: `CldHsmCreateStreamContext`
- size: `196`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14006e570`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006e59a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006e59a`
- `FLTMGR!FltInitializePushLock` at `0x14006e5c7`
- `FLTMGR!FltInitializePushLock` at `0x14006e5c7`

## pseudocode

```c
__int64 __fastcall CldHsmCreateStreamContext(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // r12
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  unsigned int v11; // edi

  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
  v9 = ExAllocateFromPagedLookasideList(&stru_140028B00);
  v10 = v9;
  if ( v9 )
  {
    v11 = 0;
    v9[3] = 0;
    v9[4] = 0;
    *v9 = a1;
    v9[1] = a2;
    v9[2] = a3;
    FltInitializePushLock(v9 + 3);
    *a4 = v10;
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
        12,
        WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids,
        v8,
        -1073741670);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x14006e570  push    rbx
0x14006e572  push    rbp
0x14006e573  push    rsi
0x14006e574  push    rdi
0x14006e575  push    r12
0x14006e577  push    r14
0x14006e579  push    r15
0x14006e57b  sub     rsp, 30h
0x14006e57f  mov     rax, [rcx+10h]
0x14006e583  mov     rsi, rcx
0x14006e586  lea     rcx, stru_140028B00; Lookaside
0x14006e58d  mov     r14, r9
0x14006e590  mov     rbp, r8
0x14006e593  mov     r15, rdx
0x14006e596  mov     r12, [rax+20h]
0x14006e59a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14006e5a1  nop     dword ptr [rax+rax+00h]
0x14006e5a6  mov     rbx, rax
0x14006e5a9  test    rax, rax
0x14006e5ac  jz      short loc_14006E5E8
0x14006e5ae  xor     edi, edi
0x14006e5b0  lea     rcx, [rax+18h]; PushLock
0x14006e5b4  mov     [rax+18h], rdi
0x14006e5b8  mov     [rax+20h], rdi
0x14006e5bc  mov     [rax], rsi
0x14006e5bf  mov     [rax+8], r15
0x14006e5c3  mov     [rax+10h], rbp
0x14006e5c7  call    cs:__imp_FltInitializePushLock
0x14006e5ce  nop     dword ptr [rax+rax+00h]
0x14006e5d3  mov     [r14], rbx
0x14006e5d6  mov     eax, edi
0x14006e5d8  add     rsp, 30h
0x14006e5dc  pop     r15
0x14006e5de  pop     r14
0x14006e5e0  pop     r12
0x14006e5e2  pop     rdi
0x14006e5e3  pop     rsi
0x14006e5e4  pop     rbp
0x14006e5e5  pop     rbx
0x14006e5e6  retn
0x14006e5e8  mov     edi, 0C000009Ah
0x14006e5ed  mov     ecx, edi
0x14006e5ef  call    HsmDbgBreakOnStatus
0x14006e5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e5fb  lea     rax, WPP_GLOBAL_Control
0x14006e602  cmp     rcx, rax
0x14006e605  jz      short loc_14006E5D6
0x14006e607  test    dword ptr [rcx+2Ch], 100h
0x14006e60e  jz      short loc_14006E5D6
0x14006e610  cmp     byte ptr [rcx+29h], 2
0x14006e614  jb      short loc_14006E5D6
0x14006e616  mov     rcx, [rcx+18h]
0x14006e61a  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x14006e621  mov     edx, 0Ch
0x14006e626  mov     [rsp+68h+var_48], edi
0x14006e62a  mov     r9, r12
0x14006e62d  call    WPP_SF_qd
0x14006e632  jmp     short loc_14006E5D6
```
