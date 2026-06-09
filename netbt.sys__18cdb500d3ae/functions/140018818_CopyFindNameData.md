# CopyFindNameData

- ea: `0x140018818`
- end: `0x140018a5e`
- name: `CopyFindNameData`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ba70`
- `0x1400485e8`

## callees

- `0x14001854c`
- `0x140018818`
- `0x140018a64`
- `0x140031440`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001886c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001886c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400188b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018a06`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400188b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018a06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018996`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400189a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018a50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018996`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400189a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018a50`
- `ntoskrnl!ExAllocatePool2` at `0x140018902`
- `ntoskrnl!ExAllocatePool2` at `0x140018902`
- `TDI!TdiCopyBufferToMdl` at `0x140018973`
- `TDI!TdiCopyBufferToMdl` at `0x140018973`

## pseudocode

```c
__int64 __fastcall CopyFindNameData(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  unsigned __int32 v7; // r12d
  KIRQL v8; // si
  int ListOfAllAddrs; // ebx
  char v10; // r14
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  ULONG v13; // edi
  void *Pool2; // rax
  _BYTE *v15; // rsi
  __int64 v16; // r8
  _DWORD *v17; // r14
  char *v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // ebx
  __int64 NameRemoteThenLocal; // rax
  int v23; // [rsp+30h] [rbp-10h] BYREF
  PVOID P; // [rsp+38h] [rbp-8h] BYREF
  ULONG BytesCopied; // [rsp+80h] [rbp+40h] BYREF
  int v26; // [rsp+90h] [rbp+50h] BYREF
  int v27; // [rsp+98h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a3 + 32);
  BytesCopied = 0;
  P = 0;
  v27 = 0;
  v7 = _byteswap_ulong(*(_DWORD *)(v3 + 488));
  v23 = 0;
  v26 = 0;
  v8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( !a1 )
  {
    NameRemoteThenLocal = FindNameRemoteThenLocal(a3, &v26, &v23);
    a1 = NameRemoteThenLocal;
    if ( !v26 || !NameRemoteThenLocal )
    {
      KeReleaseSpinLock(&SpinLock, v8);
      return 3221225653LL;
    }
    *(_DWORD *)(NameRemoteThenLocal + 32) = v26;
  }
  ListOfAllAddrs = GetListOfAllAddrs(a1, 0, &P, &v27);
  v10 = ~(*(_BYTE *)(a1 + 72) << 6) & 0x80;
  KeReleaseSpinLock(&SpinLock, v8);
  if ( ListOfAllAddrs )
    return 3221225653LL;
  LODWORD(v11) = v27;
  v12 = *(unsigned int *)(*(_QWORD *)(a2 + 8) + 40LL);
  BytesCopied = v12;
  v13 = 33 * v27 + 4;
  if ( v13 > (unsigned int)v12 )
  {
    if ( (unsigned int)v12 > 4 )
      v11 = (v12 - 4) / 0x21uLL;
    else
      LODWORD(v11) = 0;
    v13 = 33 * v11 + 4;
  }
  if ( v13 > 0xFFFF )
    return 3221225473LL;
  if ( (_DWORD)v11 && (Pool2 = (void *)ExAllocatePool2(64, (unsigned __int16)v13, 1316250190), (v15 = Pool2) != 0) )
  {
    memset(Pool2, 0, v13);
    v16 = 0;
    v15[3] = v10;
    v17 = P;
    v18 = v15 + 4;
    *(_WORD *)v15 = v11;
    do
    {
      v19 = v17[v16];
      v16 = (unsigned int)(v16 + 1);
      *(_DWORD *)(v18 + 5) = v7;
      v18 += 33;
      *(_DWORD *)(v18 - 22) = _byteswap_ulong(v19);
    }
    while ( (unsigned int)v16 < (unsigned int)v11 );
    v20 = TdiCopyBufferToMdl(v15, 0, v13, *(PMDL *)(a2 + 8), 0, &BytesCopied);
    *(_QWORD *)(a2 + 56) = BytesCopied;
    *(_DWORD *)(a2 + 48) = v20;
    if ( v17 )
      ExFreePoolWithTag(v17, 0);
    ExFreePoolWithTag(v15, 0);
    return v20;
  }
  else
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140018818  push    rbp
0x14001881a  push    rbx
0x14001881b  push    rsi
0x14001881c  push    rdi
0x14001881d  push    r12
0x14001881f  push    r14
0x140018821  push    r15
0x140018823  mov     rbp, rsp
0x140018826  sub     rsp, 40h
0x14001882a  mov     rax, [r8+20h]
0x14001882e  mov     rdi, rcx
0x140018831  mov     [rbp+arg_0], 0
0x140018838  lea     rcx, SpinLock; SpinLock
0x14001883f  mov     rbx, r8
0x140018842  mov     [rbp+P], 0
0x14001884a  mov     r15, rdx
0x14001884d  mov     [rbp+arg_18], 0
0x140018854  mov     r12d, [rax+1E8h]
0x14001885b  bswap   r12d
0x14001885e  mov     [rbp+var_10], 0
0x140018865  mov     [rbp+arg_10], 0
0x14001886c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018873  nop     dword ptr [rax+rax+00h]
0x140018878  mov     sil, al
0x14001887b  test    rdi, rdi
0x14001887e  jz      loc_1400189C5
0x140018884  lea     r9, [rbp+arg_18]
0x140018888  xor     edx, edx
0x14001888a  lea     r8, [rbp+P]
0x14001888e  mov     rcx, rdi
0x140018891  call    GetListOfAllAddrs
0x140018896  mov     r14b, [rdi+48h]
0x14001889a  lea     rcx, SpinLock; SpinLock
0x1400188a1  shl     r14b, 6
0x1400188a5  mov     dl, sil; NewIrql
0x1400188a8  not     r14b
0x1400188ab  mov     ebx, eax
0x1400188ad  and     r14b, 80h
0x1400188b1  call    cs:__imp_KeReleaseSpinLock
0x1400188b8  nop     dword ptr [rax+rax+00h]
0x1400188bd  test    ebx, ebx
0x1400188bf  jnz     loc_140018A12
0x1400188c5  mov     ebx, [rbp+arg_18]
0x1400188c8  mov     rax, [r15+8]
0x1400188cc  imul    edi, ebx, 21h ; '!'
0x1400188cf  mov     ecx, [rax+28h]
0x1400188d2  mov     [rbp+arg_0], ecx
0x1400188d5  add     edi, 4
0x1400188d8  cmp     edi, ecx
0x1400188da  ja      loc_140018A19
0x1400188e0  cmp     edi, 0FFFFh
0x1400188e6  ja      loc_140018A44
0x1400188ec  test    ebx, ebx
0x1400188ee  jz      loc_1400189EC
0x1400188f4  movzx   edx, di
0x1400188f7  mov     ecx, 40h ; '@'
0x1400188fc  mov     r8d, 4E74624Eh
0x140018902  call    cs:__imp_ExAllocatePool2
0x140018909  nop     dword ptr [rax+rax+00h]
0x14001890e  mov     rsi, rax
0x140018911  test    rax, rax
0x140018914  jz      loc_1400189EC
0x14001891a  mov     r8d, edi; Size
0x14001891d  xor     edx, edx; Val
0x14001891f  mov     rcx, rax; void *
0x140018922  call    memset
0x140018927  xor     r8d, r8d
0x14001892a  mov     [rsi+3], r14b
0x14001892e  mov     r14, [rbp+P]
0x140018932  lea     rdx, [rsi+4]
0x140018936  mov     [rsi], bx
0x140018939  test    ebx, ebx
0x14001893b  jz      short loc_140018956
0x14001893d  mov     ecx, [r14+r8*4]
0x140018941  inc     r8d
0x140018944  mov     [rdx+5], r12d
0x140018948  lea     rdx, [rdx+21h]
0x14001894c  bswap   ecx
0x14001894e  mov     [rdx-16h], ecx
0x140018951  cmp     r8d, ebx
0x140018954  jb      short loc_14001893D
0x140018956  mov     r9, [r15+8]; DestinationMdlChain
0x14001895a  lea     rax, [rbp+arg_0]
0x14001895e  mov     [rsp+40h+BytesCopied], rax; BytesCopied
0x140018963  mov     r8d, edi; SourceBytesToCopy
0x140018966  xor     edx, edx; SourceOffset
0x140018968  mov     [rsp+40h+DestinationOffset], 0; DestinationOffset
0x140018970  mov     rcx, rsi; SourceBuffer
0x140018973  call    cs:__imp_TdiCopyBufferToMdl
0x14001897a  nop     dword ptr [rax+rax+00h]
0x14001897f  mov     edx, [rbp+arg_0]
0x140018982  mov     ebx, eax
0x140018984  mov     [r15+38h], rdx
0x140018988  mov     [r15+30h], eax
0x14001898c  test    r14, r14
0x14001898f  jz      short loc_1400189A2
0x140018991  xor     edx, edx; Tag
0x140018993  mov     rcx, r14; P
0x140018996  call    cs:__imp_ExFreePoolWithTag
0x14001899d  nop     dword ptr [rax+rax+00h]
0x1400189a2  xor     edx, edx; Tag
0x1400189a4  mov     rcx, rsi; P
0x1400189a7  call    cs:__imp_ExFreePoolWithTag
0x1400189ae  nop     dword ptr [rax+rax+00h]
0x1400189b3  mov     eax, ebx
0x1400189b5  add     rsp, 40h
0x1400189b9  pop     r15
0x1400189bb  pop     r14
0x1400189bd  pop     r12
0x1400189bf  pop     rdi
0x1400189c0  pop     rsi
0x1400189c1  pop     rbx
0x1400189c2  pop     rbp
0x1400189c3  retn
0x1400189c5  lea     r8, [rbp+var_10]
0x1400189c9  mov     rcx, rbx
0x1400189cc  lea     rdx, [rbp+arg_10]
0x1400189d0  call    FindNameRemoteThenLocal
0x1400189d5  mov     ecx, [rbp+arg_10]
0x1400189d8  mov     rdi, rax
0x1400189db  test    ecx, ecx
0x1400189dd  jz      short loc_1400189FC
0x1400189df  test    rax, rax
0x1400189e2  jz      short loc_1400189FC
0x1400189e4  mov     [rax+20h], ecx
0x1400189e7  jmp     loc_140018884
0x1400189ec  mov     rcx, [rbp+P]; P
0x1400189f0  test    rcx, rcx
0x1400189f3  jnz     short loc_140018A4E
0x1400189f5  mov     eax, 0C000009Ah
0x1400189fa  jmp     short loc_1400189B5
0x1400189fc  mov     dl, sil; NewIrql
0x1400189ff  lea     rcx, SpinLock; SpinLock
0x140018a06  call    cs:__imp_KeReleaseSpinLock
0x140018a0d  nop     dword ptr [rax+rax+00h]
0x140018a12  mov     eax, 0C00000B5h
0x140018a17  jmp     short loc_1400189B5
0x140018a19  cmp     ecx, 4
0x140018a1c  ja      short loc_140018A22
0x140018a1e  xor     ebx, ebx
0x140018a20  jmp     short loc_140018A39
0x140018a22  sub     rcx, 4
0x140018a26  mov     rax, 0F83E0F83E0F83E1h
0x140018a30  mul     rcx
0x140018a33  mov     rbx, rdx
0x140018a36  shr     rbx, 1
0x140018a39  imul    edi, ebx, 21h ; '!'
0x140018a3c  add     edi, 4
0x140018a3f  jmp     loc_1400188E0
0x140018a44  mov     eax, 0C0000001h
0x140018a49  jmp     loc_1400189B5
0x140018a4e  xor     edx, edx; Tag
0x140018a50  call    cs:__imp_ExFreePoolWithTag
0x140018a57  nop     dword ptr [rax+rax+00h]
0x140018a5c  jmp     short loc_1400189F5
```
