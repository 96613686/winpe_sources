# NpCommonFlushBuffers

- ea: `0x14000e490`
- end: `0x14000e569`
- name: `NpCommonFlushBuffers`
- size: `217`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e430`
- `0x14000efb0`

## callees

- `0x14000deb8`
- `0x14000e490`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e4e9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e4e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000e510`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000e510`

## pseudocode

```c
__int64 __fastcall NpCommonFlushBuffers(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rsi
  unsigned int v9; // ebx
  size_t Size; // [rsp+28h] [rbp-60h]

  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL);
  if ( **(_WORD **)(v5 + 24) != 514 || (*(_QWORD *)(v5 + 32) & 1) == 0 )
    return 3221225648LL;
  v6 = *(_QWORD *)(v5 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
  v7 = (*(_QWORD *)(v5 + 32) >> 1) & 1LL;
  v8 = ((*(_QWORD *)(v5 + 32) >> 1) & 1) != 0 ? 168LL : 72LL;
  ExAcquirePushLockExclusiveEx(v6 + 64, 0, a3, a4);
  if ( (*(_QWORD *)(v5 + 32) & 1) != 0 )
  {
    v9 = 0;
    if ( *(_DWORD *)(v8 + v6 + 16) == 1 )
    {
      LODWORD(Size) = 0;
      v9 = NpAddDataQueueEntry((unsigned int)v7, v6, v8 + v6, 1, 2, Size, a2, 0, 0);
    }
  }
  else
  {
    v9 = -1073741648;
  }
  ExReleasePushLockExclusiveEx(v6 + 64, 0);
  return v9;
}

```

## disassembly

```asm
0x14000e490  push    rbx
0x14000e492  push    rbp
0x14000e493  push    rsi
0x14000e494  push    rdi
0x14000e495  push    r14
0x14000e497  push    r15
0x14000e499  sub     rsp, 58h
0x14000e49d  mov     rax, [rdx+0B8h]
0x14000e4a4  mov     ecx, 202h
0x14000e4a9  mov     rbp, rdx
0x14000e4ac  mov     rbx, [rax+30h]
0x14000e4b0  mov     rax, [rbx+18h]
0x14000e4b4  cmp     [rax], cx
0x14000e4b7  jnz     short loc_14000E52C
0x14000e4b9  mov     rax, [rbx+20h]
0x14000e4bd  test    al, 1
0x14000e4bf  jz      short loc_14000E52C
0x14000e4c1  mov     r14, [rbx+20h]
0x14000e4c5  mov     rdi, [rbx+20h]
0x14000e4c9  shr     r14, 1
0x14000e4cc  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14000e4d0  and     r14d, 1
0x14000e4d4  mov     eax, r14d
0x14000e4d7  neg     eax
0x14000e4d9  lea     rcx, [rdi+40h]
0x14000e4dd  sbb     rsi, rsi
0x14000e4e0  xor     edx, edx
0x14000e4e2  and     esi, 60h
0x14000e4e5  add     rsi, 48h ; 'H'
0x14000e4e9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000e4f0  nop     dword ptr [rax+rax+00h]
0x14000e4f5  mov     rax, [rbx+20h]
0x14000e4f9  test    al, 1
0x14000e4fb  jz      short loc_14000E562
0x14000e4fd  lea     r8, [rsi+rdi]; int
0x14000e501  xor     ebx, ebx
0x14000e503  cmp     dword ptr [r8+10h], 1
0x14000e508  jz      short loc_14000E533
0x14000e50a  xor     edx, edx
0x14000e50c  lea     rcx, [rdi+40h]
0x14000e510  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000e517  nop     dword ptr [rax+rax+00h]
0x14000e51c  mov     eax, ebx
0x14000e51e  add     rsp, 58h
0x14000e522  pop     r15
0x14000e524  pop     r14
0x14000e526  pop     rdi
0x14000e527  pop     rsi
0x14000e528  pop     rbp
0x14000e529  pop     rbx
0x14000e52a  retn
0x14000e52c  mov     eax, 0C00000B0h
0x14000e531  jmp     short loc_14000E51E
0x14000e533  mov     [rsp+88h+var_48], ebx; int
0x14000e537  mov     r9d, 1; int
0x14000e53d  mov     [rsp+88h+Src], rbx; Src
0x14000e542  mov     rdx, rdi; int
0x14000e545  mov     [rsp+88h+var_58], rbp; __int64
0x14000e54a  mov     ecx, r14d; int
0x14000e54d  mov     dword ptr [rsp+88h+Size], ebx; Size
0x14000e551  mov     [rsp+88h+var_68], 2; int
0x14000e559  call    NpAddDataQueueEntry
0x14000e55e  mov     ebx, eax
0x14000e560  jmp     short loc_14000E50A
0x14000e562  mov     ebx, 0C00000B0h
0x14000e567  jmp     short loc_14000E50A
```
