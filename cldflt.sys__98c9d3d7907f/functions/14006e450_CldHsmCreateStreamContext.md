# CldHsmCreateStreamContext

- ea: `0x14006e450`
- end: `0x14006e514`
- name: `CldHsmCreateStreamContext`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14006e450`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006e47a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006e47a`
- `FLTMGR!FltInitializePushLock` at `0x14006e4a7`
- `FLTMGR!FltInitializePushLock` at `0x14006e4a7`

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
0x14006e450  push    rbx
0x14006e452  push    rbp
0x14006e453  push    rsi
0x14006e454  push    rdi
0x14006e455  push    r12
0x14006e457  push    r14
0x14006e459  push    r15
0x14006e45b  sub     rsp, 30h
0x14006e45f  mov     rax, [rcx+10h]
0x14006e463  mov     rsi, rcx
0x14006e466  lea     rcx, stru_140028B00; Lookaside
0x14006e46d  mov     r14, r9
0x14006e470  mov     rbp, r8
0x14006e473  mov     r15, rdx
0x14006e476  mov     r12, [rax+20h]
0x14006e47a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14006e481  nop     dword ptr [rax+rax+00h]
0x14006e486  mov     rbx, rax
0x14006e489  test    rax, rax
0x14006e48c  jz      short loc_14006E4C8
0x14006e48e  xor     edi, edi
0x14006e490  lea     rcx, [rax+18h]; PushLock
0x14006e494  mov     [rax+18h], rdi
0x14006e498  mov     [rax+20h], rdi
0x14006e49c  mov     [rax], rsi
0x14006e49f  mov     [rax+8], r15
0x14006e4a3  mov     [rax+10h], rbp
0x14006e4a7  call    cs:__imp_FltInitializePushLock
0x14006e4ae  nop     dword ptr [rax+rax+00h]
0x14006e4b3  mov     [r14], rbx
0x14006e4b6  mov     eax, edi
0x14006e4b8  add     rsp, 30h
0x14006e4bc  pop     r15
0x14006e4be  pop     r14
0x14006e4c0  pop     r12
0x14006e4c2  pop     rdi
0x14006e4c3  pop     rsi
0x14006e4c4  pop     rbp
0x14006e4c5  pop     rbx
0x14006e4c6  retn
0x14006e4c8  mov     edi, 0C000009Ah
0x14006e4cd  mov     ecx, edi
0x14006e4cf  call    HsmDbgBreakOnStatus
0x14006e4d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e4db  lea     rax, WPP_GLOBAL_Control
0x14006e4e2  cmp     rcx, rax
0x14006e4e5  jz      short loc_14006E4B6
0x14006e4e7  test    dword ptr [rcx+2Ch], 100h
0x14006e4ee  jz      short loc_14006E4B6
0x14006e4f0  cmp     byte ptr [rcx+29h], 2
0x14006e4f4  jb      short loc_14006E4B6
0x14006e4f6  mov     rcx, [rcx+18h]
0x14006e4fa  lea     r8, WPP_5e5855279aa4383ccc01a81481f663d4_Traceguids
0x14006e501  mov     edx, 0Ch
0x14006e506  mov     [rsp+68h+var_48], edi
0x14006e50a  mov     r9, r12
0x14006e50d  call    WPP_SF_qd
0x14006e512  jmp     short loc_14006E4B6
```
