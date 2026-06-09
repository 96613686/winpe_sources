# MountMgrBootDriveLetterAssignment

- ea: `0x14001a190`
- end: `0x14001a2a2`
- name: `MountMgrBootDriveLetterAssignment`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400147a0`

## callees

- `0x14000a010`
- `0x14000bbe4`
- `0x14001a190`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001a1f5`
- `ntoskrnl!KeReleaseMutex` at `0x14001a1f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a215`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a232`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a215`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a232`

## pseudocode

```c
__int64 __fastcall MountMgrBootDriveLetterAssignment(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 *v5; // r8
  __int64 v6; // rbp
  unsigned int v7; // ebx
  char v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 *v9; // [rsp+58h] [rbp+10h] BYREF

  v8 = 0;
  result = 0;
  if ( !*(_BYTE *)(a1 + 144) )
  {
    v5 = *(__int64 **)(a1 + 16);
    v6 = *(_QWORD *)(a2 + 184);
    v9 = 0;
    if ( v5 == (__int64 *)(a1 + 16) )
    {
LABEL_5:
      KeReleaseMutex((PRKMUTEX)(a1 + 56), 0);
      KeWaitForSingleObject((PVOID)(a1 + 344), Executive, 0, 0, 0);
      KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
      result = MountMgrFindBootVolume(a1, &v9);
      v7 = result;
      if ( (int)result < 0 )
        return result;
      v5 = v9;
    }
    else
    {
      while ( (v5[15] & 0x100) == 0 )
      {
        v5 = (__int64 *)*v5;
        if ( v5 == (__int64 *)(a1 + 16) )
          goto LABEL_5;
      }
      v7 = 0;
    }
    if ( (unsigned __int8)HasDriveLetter(v5, &v8) )
    {
      if ( *(_DWORD *)(v6 + 8) == 1 )
      {
        **(_BYTE **)(a2 + 24) = v8;
        *(_QWORD *)(a2 + 56) = 1;
      }
      return v7;
    }
    else
    {
      return 3221225524LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a190  push    rsi
0x14001a192  push    rdi
0x14001a193  push    r14
0x14001a195  sub     rsp, 30h
0x14001a199  xor     r14d, r14d
0x14001a19c  mov     [rsp+48h+arg_0], 0
0x14001a1a1  mov     eax, r14d
0x14001a1a4  mov     rsi, rdx
0x14001a1a7  mov     rdi, rcx
0x14001a1aa  cmp     [rcx+90h], al
0x14001a1b0  jnz     loc_14001A298
0x14001a1b6  mov     r8, [rcx+10h]
0x14001a1ba  lea     rax, [rcx+10h]
0x14001a1be  mov     [rsp+48h+arg_18], rbp
0x14001a1c3  mov     rbp, [rdx+0B8h]
0x14001a1ca  mov     [rsp+48h+arg_10], rbx
0x14001a1cf  mov     [rsp+48h+arg_8], r14
0x14001a1d4  cmp     r8, rax
0x14001a1d7  jz      short loc_14001A1EF
0x14001a1d9  test    dword ptr [r8+78h], 100h
0x14001a1e1  jnz     loc_14001A26E
0x14001a1e7  mov     r8, [r8]
0x14001a1ea  cmp     r8, rax
0x14001a1ed  jnz     short loc_14001A1D9
0x14001a1ef  xor     edx, edx; Wait
0x14001a1f1  add     rcx, 38h ; '8'; Mutex
0x14001a1f5  call    cs:__imp_KeReleaseMutex
0x14001a1fc  nop     dword ptr [rax+rax+00h]
0x14001a201  lea     rcx, [rdi+158h]; Object
0x14001a208  mov     [rsp+48h+Timeout], r14; Timeout
0x14001a20d  xor     r9d, r9d; Alertable
0x14001a210  xor     r8d, r8d; WaitMode
0x14001a213  xor     edx, edx; WaitReason
0x14001a215  call    cs:__imp_KeWaitForSingleObject
0x14001a21c  nop     dword ptr [rax+rax+00h]
0x14001a221  xor     r9d, r9d; Alertable
0x14001a224  mov     [rsp+48h+Timeout], r14; Timeout
0x14001a229  xor     r8d, r8d; WaitMode
0x14001a22c  lea     rcx, [rdi+38h]; Object
0x14001a230  xor     edx, edx; WaitReason
0x14001a232  call    cs:__imp_KeWaitForSingleObject
0x14001a239  nop     dword ptr [rax+rax+00h]
0x14001a23e  lea     rdx, [rsp+48h+arg_8]
0x14001a243  mov     rcx, rdi
0x14001a246  call    MountMgrFindBootVolume
0x14001a24b  mov     ebx, eax
0x14001a24d  test    eax, eax
0x14001a24f  js      short loc_14001A28E
0x14001a251  mov     r8, [rsp+48h+arg_8]
0x14001a256  lea     rdx, [rsp+48h+arg_0]
0x14001a25b  mov     rcx, r8
0x14001a25e  call    HasDriveLetter
0x14001a263  test    al, al
0x14001a265  jnz     short loc_14001A273
0x14001a267  mov     eax, 0C0000034h
0x14001a26c  jmp     short loc_14001A28E
0x14001a26e  mov     ebx, r14d
0x14001a271  jmp     short loc_14001A256
0x14001a273  cmp     dword ptr [rbp+8], 1
0x14001a277  jnz     short loc_14001A28C
0x14001a279  mov     rcx, [rsi+18h]
0x14001a27d  movzx   eax, [rsp+48h+arg_0]
0x14001a282  mov     [rcx], al
0x14001a284  mov     qword ptr [rsi+38h], 1
0x14001a28c  mov     eax, ebx
0x14001a28e  mov     rbx, [rsp+48h+arg_10]
0x14001a293  mov     rbp, [rsp+48h+arg_18]
0x14001a298  add     rsp, 30h
0x14001a29c  pop     r14
0x14001a29e  pop     rdi
0x14001a29f  pop     rsi
0x14001a2a0  retn
```
