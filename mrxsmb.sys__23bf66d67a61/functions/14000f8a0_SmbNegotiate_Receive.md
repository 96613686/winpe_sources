# SmbNegotiate_Receive

- ea: `0x14000f8a0`
- end: `0x14000fad3`
- name: `SmbNegotiate_Receive`
- size: `563`
- prototype: `__int64 __fastcall(PVOID Context, __int64, __int64, int, size_t Size, _DWORD *, void *Src)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x14000f8a0`
- `0x14000fae0`
- `0x14000fbe0`
- `0x14000fcd0`
- `0x1400276f0`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000fa6c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000fa6c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f9d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f9d0`
- `ntoskrnl!ExAllocatePool2` at `0x14000f970`
- `ntoskrnl!ExAllocatePool2` at `0x14000fa01`
- `ntoskrnl!ExAllocatePool2` at `0x14000f970`
- `ntoskrnl!ExAllocatePool2` at `0x14000fa01`
- `rdbss!RxAllocateMdl2` at `0x14000fa4d`
- `rdbss!RxAllocateMdl2` at `0x14000fa4d`

## pseudocode

```c
__int64 __fastcall SmbNegotiate_Receive(
        PVOID Context,
        __int64 a2,
        __int64 a3,
        int a4,
        size_t Size,
        _DWORD *a6,
        void *Src)
{
  unsigned int v7; // r12d
  size_t v11; // rbx
  int DialectInfoFromNegotiateResponse; // edi
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rcx
  PVOID v16; // rax
  void *Pool2; // rax
  struct _MDL *Mdl2; // rax
  __int64 v20; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  if ( *(_DWORD *)(a3 + 16) )
  {
    LODWORD(v11) = Size;
    DialectInfoFromNegotiateResponse = -1073741629;
  }
  else
  {
    v11 = (unsigned int)Size;
    DialectInfoFromNegotiateResponse = 0;
    if ( (_DWORD)Size != a4 )
      goto LABEL_9;
    v13 = *((_QWORD *)Context + 9);
    LOWORD(v20) = 0;
    DialectInfoFromNegotiateResponse = GetDialectInfoFromNegotiateResponse(
                                         *(_QWORD *)(v13 + 24),
                                         (_DWORD)Src,
                                         Size,
                                         v13,
                                         0,
                                         (__int64)&v20,
                                         *((_BYTE *)Context + 1049));
    if ( DialectInfoFromNegotiateResponse < 0 )
      goto LABEL_19;
    if ( (_WORD)v20 == 767 )
    {
      if ( *((_BYTE *)Context + 1048) )
      {
        DialectInfoFromNegotiateResponse = -1073741629;
      }
      else
      {
        *((_BYTE *)Context + 1048) = 1;
        SmbCeContinueExchange(Context);
      }
    }
    else
    {
LABEL_9:
      *(_QWORD *)(*((_QWORD *)Context + 129) + 8LL) = ExAllocatePool2(66, *(unsigned int *)(a2 + 728), 1834182478);
      v14 = *((_QWORD *)Context + 129);
      if ( *(_QWORD *)(v14 + 8) )
      {
        *(_DWORD *)(v14 + 20) = *(_DWORD *)(a2 + 728);
        v15 = *(_QWORD *)(a2 + 96);
        v16 = (*(_BYTE *)(v15 + 10) & 5) != 0
            ? *(PVOID *)(v15 + 24)
            : MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u);
        memmove(*(void **)(*((_QWORD *)Context + 129) + 8LL), v16, *(unsigned int *)(*((_QWORD *)Context + 129) + 20LL));
        Pool2 = (void *)ExAllocatePool2(66, v11, 1834182478);
        if ( Pool2 )
        {
          **((_QWORD **)Context + 129) = Pool2;
          *(_DWORD *)(*((_QWORD *)Context + 129) + 16LL) = v11;
          if ( (_DWORD)v11 == a4 )
          {
            memmove(Pool2, Src, v11);
            goto LABEL_19;
          }
          Mdl2 = (struct _MDL *)RxAllocateMdl2(Pool2, (unsigned int)v11, 0, 0, 0);
          *(_QWORD *)(a2 + 720) = Mdl2;
          if ( Mdl2 )
          {
            MmBuildMdlForNonPagedPool(Mdl2);
            *(_DWORD *)(a2 + 748) = v11;
            v7 = -1073741802;
            LODWORD(v11) = 0;
            goto LABEL_19;
          }
        }
      }
      DialectInfoFromNegotiateResponse = -1073741670;
    }
  }
LABEL_19:
  *a6 = v11;
  v20 = (unsigned int)DialectInfoFromNegotiateResponse;
  SmbCeUpdateExchangeStatus(Context, (unsigned int)DialectInfoFromNegotiateResponse);
  SmbCseUpdateBufferContextStatus(a2, v20);
  return v7;
}

```

## disassembly

```asm
0x14000f8a0  mov     [rsp+arg_8], rbx
0x14000f8a5  mov     [rsp+arg_10], rbp
0x14000f8aa  push    rsi
0x14000f8ab  push    rdi
0x14000f8ac  push    r12
0x14000f8ae  push    r14
0x14000f8b0  push    r15
0x14000f8b2  sub     rsp, 40h
0x14000f8b6  xor     r12d, r12d
0x14000f8b9  mov     r14d, r9d
0x14000f8bc  mov     rbp, rdx
0x14000f8bf  mov     rsi, rcx
0x14000f8c2  cmp     [r8+10h], r12d
0x14000f8c6  jz      short loc_14000F8D9
0x14000f8c8  mov     ebx, dword ptr [rsp+68h+Size]
0x14000f8cf  mov     edi, 0C00000C3h
0x14000f8d4  jmp     loc_14000FA86
0x14000f8d9  mov     ebx, dword ptr [rsp+68h+Size]
0x14000f8e0  xor     edi, edi
0x14000f8e2  cmp     ebx, r14d
0x14000f8e5  jnz     short loc_14000F95F
0x14000f8e7  mov     rcx, [rcx+48h]
0x14000f8eb  xor     eax, eax
0x14000f8ed  mov     rdx, [rsp+68h+Src]
0x14000f8f5  mov     r9, rcx
0x14000f8f8  mov     word ptr [rsp+68h+arg_0], ax
0x14000f8fd  mov     r8d, ebx
0x14000f900  mov     al, [rsi+419h]
0x14000f906  mov     rcx, [rcx+18h]
0x14000f90a  mov     [rsp+68h+var_38], al
0x14000f90e  lea     rax, [rsp+68h+arg_0]
0x14000f913  mov     qword ptr [rsp+68h+Priority], rax
0x14000f918  mov     qword ptr [rsp+68h+BugCheckOnFailure], rdi
0x14000f91d  call    GetDialectInfoFromNegotiateResponse
0x14000f922  mov     edi, eax
0x14000f924  test    eax, eax
0x14000f926  js      loc_14000FA86
0x14000f92c  mov     eax, 2FFh
0x14000f931  cmp     word ptr [rsp+68h+arg_0], ax
0x14000f936  jnz     short loc_14000F95F
0x14000f938  cmp     [rsi+418h], r12b
0x14000f93f  jz      short loc_14000F94B
0x14000f941  mov     edi, 0C00000C3h
0x14000f946  jmp     loc_14000FA86
0x14000f94b  mov     rcx, rsi; Context
0x14000f94e  mov     byte ptr [rsi+418h], 1
0x14000f955  call    SmbCeContinueExchange
0x14000f95a  jmp     loc_14000FA86
0x14000f95f  mov     edx, [rbp+2D8h]
0x14000f965  mov     ecx, 42h ; 'B'
0x14000f96a  mov     r8d, 6D53674Eh
0x14000f970  call    cs:__imp_ExAllocatePool2
0x14000f977  nop     dword ptr [rax+rax+00h]
0x14000f97c  mov     rcx, rax
0x14000f97f  mov     rax, [rsi+408h]
0x14000f986  mov     [rax+8], rcx
0x14000f98a  mov     rcx, [rsi+408h]
0x14000f991  cmp     [rcx+8], r12
0x14000f995  jnz     short loc_14000F9A1
0x14000f997  mov     edi, 0C000009Ah
0x14000f99c  jmp     loc_14000FA86
0x14000f9a1  mov     eax, [rbp+2D8h]
0x14000f9a7  mov     [rcx+14h], eax
0x14000f9aa  mov     rcx, [rbp+60h]; MemoryDescriptorList
0x14000f9ae  test    byte ptr [rcx+0Ah], 5
0x14000f9b2  jz      short loc_14000F9BA
0x14000f9b4  mov     rax, [rcx+18h]
0x14000f9b8  jmp     short loc_14000F9DC
0x14000f9ba  xor     r9d, r9d; RequestedAddress
0x14000f9bd  mov     [rsp+68h+Priority], 40000010h; Priority
0x14000f9c5  xor     edx, edx; AccessMode
0x14000f9c7  mov     [rsp+68h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14000f9cc  lea     r8d, [r9+1]; CacheType
0x14000f9d0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000f9d7  nop     dword ptr [rax+rax+00h]
0x14000f9dc  mov     rcx, [rsi+408h]
0x14000f9e3  mov     rdx, rax; Src
0x14000f9e6  mov     r8d, [rcx+14h]; Size
0x14000f9ea  mov     rcx, [rcx+8]; void *
0x14000f9ee  call    memmove
0x14000f9f3  mov     r8d, 6D53674Eh
0x14000f9f9  mov     rdx, rbx
0x14000f9fc  mov     ecx, 42h ; 'B'
0x14000fa01  call    cs:__imp_ExAllocatePool2
0x14000fa08  nop     dword ptr [rax+rax+00h]
0x14000fa0d  mov     rcx, rax; void *
0x14000fa10  test    rax, rax
0x14000fa13  jz      short loc_14000F997
0x14000fa15  mov     rax, [rsi+408h]
0x14000fa1c  mov     [rax], rcx
0x14000fa1f  mov     rax, [rsi+408h]
0x14000fa26  mov     [rax+10h], ebx
0x14000fa29  cmp     ebx, r14d
0x14000fa2c  jnz     short loc_14000FA40
0x14000fa2e  mov     rdx, [rsp+68h+Src]; Src
0x14000fa36  mov     r8, rbx; Size
0x14000fa39  call    memmove
0x14000fa3e  jmp     short loc_14000FA86
0x14000fa40  xor     r9d, r9d
0x14000fa43  mov     qword ptr [rsp+68h+BugCheckOnFailure], r12
0x14000fa48  xor     r8d, r8d
0x14000fa4b  mov     edx, ebx
0x14000fa4d  call    cs:__imp_RxAllocateMdl2
0x14000fa54  nop     dword ptr [rax+rax+00h]
0x14000fa59  mov     [rbp+2D0h], rax
0x14000fa60  test    rax, rax
0x14000fa63  jz      loc_14000F997
0x14000fa69  mov     rcx, rax; MemoryDescriptorList
0x14000fa6c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000fa73  nop     dword ptr [rax+rax+00h]
0x14000fa78  mov     [rbp+2ECh], ebx
0x14000fa7e  mov     r12d, 0C0000016h
0x14000fa84  xor     ebx, ebx
0x14000fa86  mov     rcx, [rsp+68h+arg_28]
0x14000fa8e  mov     [rcx], ebx
0x14000fa90  mov     rcx, rsi
0x14000fa93  mov     dword ptr [rsp+68h+arg_0], edi
0x14000fa97  mov     dword ptr [rsp+68h+arg_0+4], 0
0x14000fa9f  mov     rdx, [rsp+68h+arg_0]
0x14000faa4  call    SmbCeUpdateExchangeStatus
0x14000faa9  mov     rdx, [rsp+68h+arg_0]
0x14000faae  mov     rcx, rbp
0x14000fab1  call    SmbCseUpdateBufferContextStatus
0x14000fab6  lea     r11, [rsp+68h+var_28]
0x14000fabb  mov     eax, r12d
0x14000fabe  mov     rbx, [r11+38h]
0x14000fac2  mov     rbp, [r11+40h]
0x14000fac6  mov     rsp, r11
0x14000fac9  pop     r15
0x14000facb  pop     r14
0x14000facd  pop     r12
0x14000facf  pop     rdi
0x14000fad0  pop     rsi
0x14000fad1  retn
```
