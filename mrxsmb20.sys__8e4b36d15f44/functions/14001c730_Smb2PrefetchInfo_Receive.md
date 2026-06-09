# Smb2PrefetchInfo_Receive

- ea: `0x14001c730`
- end: `0x14001c8de`
- name: `Smb2PrefetchInfo_Receive`
- size: `430`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001c730`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001c7f9`
- `ntoskrnl!ExAllocatePool2` at `0x14001c7f9`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001c8c3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001c8c3`
- `rdbss!RxAllocateMdl2` at `0x14001c8a4`
- `rdbss!RxAllocateMdl2` at `0x14001c8a4`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001c7a3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001c7a3`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001c83c`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001c83c`

## pseudocode

```c
__int64 __fastcall Smb2PrefetchInfo_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  int v7; // ebx
  unsigned int v8; // r14d
  unsigned int v12; // edi
  unsigned int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // eax
  void *Pool2; // rax
  __int64 v18; // rdx
  size_t v19; // r8
  __int64 v20; // r9
  struct _MDL *Mdl2; // rax

  v7 = *(_DWORD *)(a3 + 16);
  v8 = 0;
  if ( v7 < 0 )
    goto LABEL_14;
  if ( a4 < 0x48 )
  {
    v7 = -1073741629;
LABEL_14:
    v12 = a5;
    goto LABEL_12;
  }
  v12 = a5;
  if ( *(_WORD *)(a7 + 64) != 9
    || (v13 = *(unsigned __int16 *)(a7 + 66), v13 > a5)
    || (v14 = *(unsigned int *)(a7 + 68), (unsigned int)v14 > a5)
    || (unsigned int)v14 + v13 > a5 )
  {
    v7 = -1073741629;
    goto LABEL_12;
  }
  if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v14) + 64) & 1) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                    * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                   % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL)
                                                                               + 1488LL))
                                                    + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                    + 84));
  v15 = *(_DWORD *)(a7 + 68);
  if ( v15 )
  {
    Pool2 = (void *)ExAllocatePool2(66, v15, 1834182224);
    *(_QWORD *)(a2 + 712) = Pool2;
    if ( Pool2 )
    {
      v18 = *(unsigned int *)(a7 + 68);
      *(_DWORD *)(a2 + 748) = v18;
      v19 = *(unsigned int *)(a7 + 68);
      v20 = *(unsigned __int16 *)(a7 + 66);
      if ( (int)v19 + (int)v20 <= a4 )
      {
        memmove(Pool2, (const void *)(v20 + a7), v19);
        goto LABEL_12;
      }
      Mdl2 = (struct _MDL *)RxAllocateMdl2(Pool2, v18, 0, 0, 0);
      *(_QWORD *)(a2 + 720) = Mdl2;
      if ( Mdl2 )
      {
        MmBuildMdlForNonPagedPool(Mdl2);
        v12 = *(unsigned __int16 *)(a7 + 66);
        v8 = -1073741802;
        goto LABEL_12;
      }
    }
    v7 = -1073741670;
  }
LABEL_12:
  *a6 = v12;
  SmbCseUpdateBufferContextStatus(a2, (unsigned int)v7);
  return v8;
}

```

## disassembly

```asm
0x14001c730  mov     [rsp+arg_8], rbx
0x14001c735  push    rsi
0x14001c736  push    rdi
0x14001c737  push    r13
0x14001c739  push    r14
0x14001c73b  push    r15
0x14001c73d  sub     rsp, 30h
0x14001c741  mov     ebx, [r8+10h]
0x14001c745  xor     r14d, r14d
0x14001c748  mov     r15d, r9d
0x14001c74b  mov     rsi, rdx
0x14001c74e  mov     r13, rcx
0x14001c751  test    ebx, ebx
0x14001c753  js      loc_14001C863
0x14001c759  cmp     r9d, 48h ; 'H'
0x14001c75d  jb      loc_14001C85E
0x14001c763  mov     edi, [rsp+58h+arg_20]
0x14001c76a  mov     [rsp+58h+arg_0], rbp
0x14001c76f  mov     rbp, [rsp+58h+arg_30]
0x14001c777  cmp     word ptr [rbp+40h], 9
0x14001c77c  jnz     loc_14001C892
0x14001c782  movzx   eax, word ptr [rbp+42h]
0x14001c786  cmp     eax, edi
0x14001c788  ja      loc_14001C892
0x14001c78e  mov     ecx, [rbp+44h]
0x14001c791  cmp     ecx, edi
0x14001c793  ja      loc_14001C892
0x14001c799  add     eax, ecx
0x14001c79b  cmp     eax, edi
0x14001c79d  ja      loc_14001C892
0x14001c7a3  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001c7aa  nop     dword ptr [rax+rax+00h]
0x14001c7af  test    byte ptr [rax+40h], 1
0x14001c7b3  jz      short loc_14001C7E5
0x14001c7b5  mov     rax, [r13+58h]
0x14001c7b9  xor     edx, edx
0x14001c7bb  mov     r8, [rax+1A8h]
0x14001c7c2  mov     eax, gs:1A4h
0x14001c7ca  div     dword ptr [r8+5D0h]
0x14001c7d1  mov     rax, [r8+5C8h]
0x14001c7d8  lea     rdx, [rdx+rdx*2]
0x14001c7dc  shl     rdx, 6
0x14001c7e0  lock inc dword ptr [rdx+rax+54h]
0x14001c7e5  mov     eax, [rbp+44h]
0x14001c7e8  test    eax, eax
0x14001c7ea  jz      short loc_14001C819
0x14001c7ec  mov     edx, eax
0x14001c7ee  mov     ecx, 42h ; 'B'
0x14001c7f3  mov     r8d, 6D536650h
0x14001c7f9  call    cs:__imp_ExAllocatePool2
0x14001c800  nop     dword ptr [rax+rax+00h]
0x14001c805  mov     [rsi+2C8h], rax
0x14001c80c  mov     rcx, rax; void *
0x14001c80f  test    rax, rax
0x14001c812  jnz     short loc_14001C86C
0x14001c814  mov     ebx, 0C000009Ah
0x14001c819  mov     rbp, [rsp+58h+arg_0]
0x14001c81e  mov     rcx, [rsp+58h+arg_28]
0x14001c826  mov     dword ptr [rsp+58h+arg_10], ebx
0x14001c82a  mov     dword ptr [rsp+58h+arg_10+4], 0
0x14001c832  mov     rdx, [rsp+58h+arg_10]
0x14001c837  mov     [rcx], edi
0x14001c839  mov     rcx, rsi
0x14001c83c  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001c843  nop     dword ptr [rax+rax+00h]
0x14001c848  mov     rbx, [rsp+58h+arg_8]
0x14001c84d  mov     eax, r14d
0x14001c850  add     rsp, 30h
0x14001c854  pop     r15
0x14001c856  pop     r14
0x14001c858  pop     r13
0x14001c85a  pop     rdi
0x14001c85b  pop     rsi
0x14001c85c  retn
0x14001c85e  mov     ebx, 0C00000C3h
0x14001c863  mov     edi, [rsp+58h+arg_20]
0x14001c86a  jmp     short loc_14001C81E
0x14001c86c  mov     edx, [rbp+44h]
0x14001c86f  mov     [rsi+2ECh], edx
0x14001c875  mov     r8d, [rbp+44h]; Size
0x14001c879  movzx   r9d, word ptr [rbp+42h]
0x14001c87e  lea     eax, [r8+r9]
0x14001c882  cmp     eax, r15d
0x14001c885  ja      short loc_14001C899
0x14001c887  lea     rdx, [r9+rbp]; Src
0x14001c88b  call    memmove
0x14001c890  jmp     short loc_14001C819
0x14001c892  mov     ebx, 0C00000C3h
0x14001c897  jmp     short loc_14001C819
0x14001c899  xor     r9d, r9d
0x14001c89c  mov     [rsp+58h+var_38], r14
0x14001c8a1  xor     r8d, r8d
0x14001c8a4  call    cs:__imp_RxAllocateMdl2
0x14001c8ab  nop     dword ptr [rax+rax+00h]
0x14001c8b0  mov     [rsi+2D0h], rax
0x14001c8b7  test    rax, rax
0x14001c8ba  jz      loc_14001C814
0x14001c8c0  mov     rcx, rax; MemoryDescriptorList
0x14001c8c3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001c8ca  nop     dword ptr [rax+rax+00h]
0x14001c8cf  movzx   edi, word ptr [rbp+42h]
0x14001c8d3  mov     r14d, 0C0000016h
0x14001c8d9  jmp     loc_14001C819
```
