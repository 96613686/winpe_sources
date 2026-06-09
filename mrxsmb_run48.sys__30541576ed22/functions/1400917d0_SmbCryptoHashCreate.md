# SmbCryptoHashCreate

- ea: `0x1400917d0`
- end: `0x1400918c2`
- name: `SmbCryptoHashCreate`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400917d0`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14009182d`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14009182d`
- `ntoskrnl!ExAllocatePool2` at `0x1400917f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400917f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091886`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091886`
- `ksecdd!BCryptCreateHash` at `0x14009186c`
- `ksecdd!BCryptCreateHash` at `0x14009186c`

## pseudocode

```c
__int64 __fastcall SmbCryptoHashCreate(_QWORD *a1, int a2, char a3)
{
  __int64 Pool2; // rax
  void *v6; // rbx
  NTSTATUS Hash; // ebp

  if ( a2 != 1 )
  {
    Hash = -1073741811;
    goto LABEL_6;
  }
  Pool2 = ExAllocatePool2(66, 16, 590500684);
  v6 = (void *)Pool2;
  if ( !Pool2 )
  {
    Hash = -1073741670;
    goto LABEL_6;
  }
  *(_QWORD *)(Pool2 + 8) = &SmbCryptoHashAlgorithms;
  Hash = RtlRunOnceExecuteOnce(&RunOnce, SmbCryptoHashAlgorithmInitialize, &SmbCryptoHashAlgorithms, 0);
  if ( Hash < 0
    || (Hash = BCryptCreateHash(SmbCryptoHashAlgorithms, (BCRYPT_HASH_HANDLE *)v6, 0, 0, 0, 0, a3 != 0 ? 0x20 : 0),
        Hash < 0) )
  {
    ExFreePoolWithTag(v6, 0x2332534Cu);
LABEL_6:
    *a1 = 0;
    return (unsigned int)Hash;
  }
  *a1 = v6;
  return 0;
}

```

## disassembly

```asm
0x1400917d0  push    rbx
0x1400917d2  push    rbp
0x1400917d3  push    rsi
0x1400917d4  push    rdi
0x1400917d5  sub     rsp, 48h
0x1400917d9  movzx   esi, r8b
0x1400917dd  mov     rdi, rcx
0x1400917e0  cmp     edx, 1
0x1400917e3  jnz     loc_1400918BB
0x1400917e9  mov     edx, 10h
0x1400917ee  mov     ecx, 42h ; 'B'
0x1400917f3  mov     r8d, 2332534Ch
0x1400917f9  call    cs:__imp_ExAllocatePool2
0x140091800  nop     dword ptr [rax+rax+00h]
0x140091805  mov     rbx, rax
0x140091808  test    rax, rax
0x14009180b  jz      loc_1400918B4
0x140091811  lea     r8, SmbCryptoHashAlgorithms; Parameter
0x140091818  xor     r9d, r9d; Context
0x14009181b  lea     rdx, SmbCryptoHashAlgorithmInitialize; InitFn
0x140091822  mov     [rax+8], r8
0x140091826  lea     rcx, RunOnce; RunOnce
0x14009182d  call    cs:__imp_RtlRunOnceExecuteOnce
0x140091834  nop     dword ptr [rax+rax+00h]
0x140091839  mov     ebp, eax
0x14009183b  test    eax, eax
0x14009183d  js      short loc_14009187E
0x14009183f  mov     rcx, cs:SmbCryptoHashAlgorithms; hAlgorithm
0x140091846  neg     sil
0x140091849  mov     rdx, rbx; phHash
0x14009184c  sbb     eax, eax
0x14009184e  xor     r9d, r9d; cbHashObject
0x140091851  and     eax, 20h
0x140091854  xor     r8d, r8d; pbHashObject
0x140091857  mov     [rsp+68h+dwFlags], eax; dwFlags
0x14009185b  mov     [rsp+68h+cbSecret], 0; cbSecret
0x140091863  mov     [rsp+68h+pbSecret], 0; pbSecret
0x14009186c  call    cs:__imp_BCryptCreateHash
0x140091873  nop     dword ptr [rax+rax+00h]
0x140091878  mov     ebp, eax
0x14009187a  test    eax, eax
0x14009187c  jns     short loc_1400918A5
0x14009187e  mov     edx, 2332534Ch; Tag
0x140091883  mov     rcx, rbx; P
0x140091886  call    cs:__imp_ExFreePoolWithTag
0x14009188d  nop     dword ptr [rax+rax+00h]
0x140091892  mov     qword ptr [rdi], 0
0x140091899  mov     eax, ebp
0x14009189b  add     rsp, 48h
0x14009189f  pop     rdi
0x1400918a0  pop     rsi
0x1400918a1  pop     rbp
0x1400918a2  pop     rbx
0x1400918a3  retn
0x1400918a5  mov     [rdi], rbx
0x1400918a8  xor     eax, eax
0x1400918aa  add     rsp, 48h
0x1400918ae  pop     rdi
0x1400918af  pop     rsi
0x1400918b0  pop     rbp
0x1400918b1  pop     rbx
0x1400918b2  retn
0x1400918b4  mov     ebp, 0C000009Ah
0x1400918b9  jmp     short loc_140091892
0x1400918bb  mov     ebp, 0C000000Dh
0x1400918c0  jmp     short loc_140091892
```
