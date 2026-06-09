# SmbCeSendEchoProbe

- ea: `0x1400113f4`
- end: `0x140011582`
- name: `SmbCeSendEchoProbe`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002050`

## callees

- `0x140001cd0`
- `0x14000b140`
- `0x1400113f4`
- `0x1400166c0`
- `0x14003df64`
- `0x14003e364`
- `0x14004dd50`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14001145a`
- `ntoskrnl!MmSizeOfMdl` at `0x14001145a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140011535`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140011535`
- `ntoskrnl!ExAllocatePool2` at `0x140011477`
- `ntoskrnl!ExAllocatePool2` at `0x140011477`

## pseudocode

```c
__int64 __fastcall SmbCeSendEchoProbe(__int64 a1, __int64 a2)
{
  unsigned __int8 *Exchange; // rax
  unsigned __int8 *v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v8; // r14d
  __int64 Pool2; // rax
  __int64 v10; // rbx
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rax

  Exchange = SmbMmAllocateExchange(4);
  v5 = Exchange;
  if ( Exchange )
  {
    v6 = SmbCeInitializeAdminExchange((__int64)Exchange, a1, 0, 0, 43);
    if ( v6 )
    {
      SmbMmFreeExchange(v5);
    }
    else
    {
      *((_WORD *)v5 + 32) = -2;
      *((_DWORD *)v5 + 18) = 4099;
      v7 = *(_DWORD *)(a2 + 288) + 32;
      v8 = MmSizeOfMdl(*(PVOID *)(a2 + 280), v7);
      Pool2 = ExAllocatePool2(66, v8 + v7, 1682009427);
      *((_QWORD *)v5 + 49) = Pool2;
      if ( !Pool2 )
        return (unsigned int)SmbCeCompleteAdminExchange(v5);
      v10 = Pool2 + v8 + 32LL;
      *((_DWORD *)v5 + 100) = *(_DWORD *)(a2 + 288);
      memmove((void *)v10, *(const void **)(a2 + 280), *(unsigned int *)(a2 + 288));
      v11 = *(unsigned int *)(a2 + 288);
      v12 = *((_QWORD *)v5 + 49);
      *(_QWORD *)v12 = 0;
      *(_WORD *)(v12 + 10) = 0;
      *(_WORD *)(v12 + 8) = 8 * ((((unsigned __int64)(v10 & 0xFFF) + v11 + 4095) >> 12) + 6);
      *(_QWORD *)(v12 + 32) = v10 & 0xFFFFFFFFFFFFF000uLL;
      *(_DWORD *)(v12 + 44) = v10 & 0xFFF;
      *(_DWORD *)(v12 + 40) = v11;
      v13 = *((_QWORD *)v5 + 49);
      if ( *(_DWORD *)(v13 + 44) >= 0x20u )
        *(_WORD *)(v13 + 10) |= 0x1000u;
      MmBuildMdlForNonPagedPool(*((PMDL *)v5 + 49));
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 464));
      v6 = SmbCeInitiateExchange(v5);
      if ( v6 != 259 )
        return (unsigned int)SmbCeCompleteAdminExchange(v5);
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v6;
}

```

## disassembly

```asm
0x1400113f4  push    rbx
0x1400113f6  push    rbp
0x1400113f7  push    rsi
0x1400113f8  push    rdi
0x1400113f9  push    r14
0x1400113fb  sub     rsp, 30h
0x1400113ff  mov     rsi, rcx
0x140011402  mov     rbp, rdx
0x140011405  mov     ecx, 4
0x14001140a  call    SmbMmAllocateExchange
0x14001140f  mov     rdi, rax
0x140011412  test    rax, rax
0x140011415  jz      loc_14001156F
0x14001141b  xor     r9d, r9d
0x14001141e  mov     [rsp+58h+var_38], 2Bh ; '+'
0x140011423  xor     r8d, r8d
0x140011426  mov     rdx, rsi
0x140011429  mov     rcx, rax
0x14001142c  call    SmbCeInitializeAdminExchange
0x140011431  mov     ebx, eax
0x140011433  test    eax, eax
0x140011435  jnz     loc_140011565
0x14001143b  mov     word ptr [rdi+40h], 0FFFEh
0x140011441  mov     dword ptr [rdi+48h], 1003h
0x140011448  mov     ebx, [rbp+120h]
0x14001144e  mov     rcx, [rbp+118h]; Base
0x140011455  add     ebx, 20h ; ' '
0x140011458  mov     edx, ebx; Length
0x14001145a  call    cs:__imp_MmSizeOfMdl
0x140011461  nop     dword ptr [rax+rax+00h]
0x140011466  mov     ecx, 42h ; 'B'
0x14001146b  mov     r8d, 64416D53h
0x140011471  mov     r14, rax
0x140011474  lea     edx, [rax+rbx]
0x140011477  call    cs:__imp_ExAllocatePool2
0x14001147e  nop     dword ptr [rax+rax+00h]
0x140011483  mov     [rdi+188h], rax
0x14001148a  test    rax, rax
0x14001148d  jz      loc_140011559
0x140011493  mov     ebx, r14d
0x140011496  add     rbx, 20h ; ' '
0x14001149a  add     rbx, rax
0x14001149d  mov     eax, [rbp+120h]
0x1400114a3  mov     [rdi+190h], eax
0x1400114a9  mov     rcx, rbx; void *
0x1400114ac  mov     r8d, [rbp+120h]; Size
0x1400114b3  mov     rdx, [rbp+118h]; Src
0x1400114ba  call    memmove
0x1400114bf  mov     r9d, [rbp+120h]
0x1400114c6  mov     edx, ebx
0x1400114c8  mov     r8, [rdi+188h]
0x1400114cf  mov     eax, edx
0x1400114d1  mov     r10d, 0FFFh
0x1400114d7  and     rbx, 0FFFFFFFFFFFFF000h
0x1400114de  and     rax, r10
0x1400114e1  and     edx, r10d
0x1400114e4  lea     rcx, [r9+0FFFh]
0x1400114eb  add     rcx, rax
0x1400114ee  mov     qword ptr [r8], 0
0x1400114f5  shr     rcx, 0Ch
0x1400114f9  xor     eax, eax
0x1400114fb  add     cx, 6
0x1400114ff  mov     [r8+0Ah], ax
0x140011504  shl     cx, 3
0x140011508  mov     [r8+8], cx
0x14001150d  mov     [r8+20h], rbx
0x140011511  mov     [r8+2Ch], edx
0x140011515  mov     [r8+28h], r9d
0x140011519  mov     rax, [rdi+188h]
0x140011520  cmp     dword ptr [rax+2Ch], 20h ; ' '
0x140011524  jb      short loc_14001152E
0x140011526  lea     ecx, [r10+1]
0x14001152a  or      [rax+0Ah], cx
0x14001152e  mov     rcx, [rdi+188h]; MemoryDescriptorList
0x140011535  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001153c  nop     dword ptr [rax+rax+00h]
0x140011541  lock inc dword ptr [rsi+1D0h]
0x140011548  mov     rcx, rdi
0x14001154b  call    SmbCeInitiateExchange
0x140011550  mov     ebx, eax
0x140011552  cmp     eax, 103h
0x140011557  jz      short loc_140011574
0x140011559  mov     rcx, rdi; Entry
0x14001155c  call    SmbCeCompleteAdminExchange
0x140011561  mov     ebx, eax
0x140011563  jmp     short loc_140011574
0x140011565  mov     rcx, rdi; Entry
0x140011568  call    SmbMmFreeExchange
0x14001156d  jmp     short loc_140011574
0x14001156f  mov     ebx, 0C000009Ah
0x140011574  mov     eax, ebx
0x140011576  add     rsp, 30h
0x14001157a  pop     r14
0x14001157c  pop     rdi
0x14001157d  pop     rsi
0x14001157e  pop     rbp
0x14001157f  pop     rbx
0x140011580  retn
```
