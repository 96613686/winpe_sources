# MRxSmbBuildRename

- ea: `0x14003c2e8`
- end: `0x14003c3f1`
- name: `MRxSmbBuildRename`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003c550`

## callees

- `0x14000dfa8`
- `0x14003c2e8`
- `0x140046380`
- `0x14004a590`

## pseudocode

```c
__int64 __fastcall MRxSmbBuildRename(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 result; // rax
  __int64 v6; // [rsp+20h] [rbp-78h]
  __int128 v7; // [rsp+60h] [rbp-38h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  v3 = *(_QWORD *)(v1 + 56);
  v4 = *(_QWORD *)(v1 + 456);
  v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids);
  *((_QWORD *)&v7 + 1) = v4 + 20;
  LOWORD(v7) = *(_WORD *)(v4 + 16);
  if ( *(_DWORD *)(v1 + 448) == 10 )
  {
    result = MRxSmbStartSMBCommand(a1, 1, 7, 5, v6, 0x10000u);
    if ( (_DWORD)result )
      return result;
    MRxSmbStuffSMB(a1, (__int64)"0wB", 22, 0);
  }
  else
  {
    result = MRxSmbStartSMBCommand(a1, 1, 165, 11, v6, 0x10000u);
    if ( (_DWORD)result )
      return result;
    MRxSmbStuffSMB(a1, (__int64)"0wwdB", 22, 259);
  }
  return MRxSmbStuffSMB(a1, (__int64)"44!", v3 + 360, (__int64)&v7);
}

```

## disassembly

```asm
0x14003c2e8  push    rbx
0x14003c2ea  push    rbp
0x14003c2eb  push    rsi
0x14003c2ec  push    rdi
0x14003c2ed  sub     rsp, 78h
0x14003c2f1  mov     rdi, [rcx+30h]
0x14003c2f5  xorps   xmm0, xmm0
0x14003c2f8  mov     rbx, rcx
0x14003c2fb  mov     rbp, [rdi+38h]
0x14003c2ff  mov     rsi, [rdi+1C8h]
0x14003c306  movups  [rsp+98h+var_38], xmm0
0x14003c30b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c312  lea     rax, WPP_GLOBAL_Control
0x14003c319  cmp     rcx, rax
0x14003c31c  jz      short loc_14003C33C
0x14003c31e  test    dword ptr [rcx+2Ch], 400h
0x14003c325  jz      short loc_14003C33C
0x14003c327  mov     rcx, [rcx+18h]
0x14003c32b  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c332  mov     edx, 0Dh
0x14003c337  call    WPP_SF_
0x14003c33c  lea     rax, [rsi+14h]
0x14003c340  mov     dword ptr [rsp+98h+var_70], 10000h
0x14003c348  mov     qword ptr [rsp+98h+var_38+8], rax
0x14003c34d  mov     edx, 1
0x14003c352  movzx   eax, word ptr [rsi+10h]
0x14003c356  mov     rcx, rbx
0x14003c359  mov     word ptr [rsp+98h+var_38], ax
0x14003c35e  cmp     dword ptr [rdi+1C0h], 0Ah
0x14003c365  jnz     short loc_14003C38F
0x14003c367  lea     r9d, [rdx+4]
0x14003c36b  mov     r8b, 7
0x14003c36e  call    MRxSmbStartSMBCommand
0x14003c373  test    eax, eax
0x14003c375  jnz     short loc_14003C3E7
0x14003c377  xor     r9d, r9d
0x14003c37a  lea     r8d, [rax+16h]
0x14003c37e  lea     rdx, a0wb_0; "0wB"
0x14003c385  mov     rcx, rbx
0x14003c388  call    MRxSmbStuffSMB
0x14003c38d  jmp     short loc_14003C3CC
0x14003c38f  mov     r9d, 0Bh
0x14003c395  mov     r8b, 0A5h
0x14003c398  call    MRxSmbStartSMBCommand
0x14003c39d  test    eax, eax
0x14003c39f  jnz     short loc_14003C3E7
0x14003c3a1  mov     [rsp+98h+var_70], 0
0x14003c3aa  lea     r8d, [rax+16h]
0x14003c3ae  mov     r9d, 103h
0x14003c3b4  mov     [rsp+98h+var_78], 0
0x14003c3bd  lea     rdx, a0wwdb; "0wwdB"
0x14003c3c4  mov     rcx, rbx
0x14003c3c7  call    MRxSmbStuffSMB
0x14003c3cc  lea     r8, [rbp+168h]
0x14003c3d3  mov     rcx, rbx
0x14003c3d6  lea     r9, [rsp+98h+var_38]
0x14003c3db  lea     rdx, a44; "44!"
0x14003c3e2  call    MRxSmbStuffSMB
0x14003c3e7  add     rsp, 78h
0x14003c3eb  pop     rdi
0x14003c3ec  pop     rsi
0x14003c3ed  pop     rbp
0x14003c3ee  pop     rbx
0x14003c3ef  retn
```
