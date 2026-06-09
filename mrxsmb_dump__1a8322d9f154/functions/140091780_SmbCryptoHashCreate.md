# SmbCryptoHashCreate

- ea: `0x140091780`
- end: `0x140091872`
- name: `SmbCryptoHashCreate`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140091780`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400917dd`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400917dd`
- `ntoskrnl!ExAllocatePool2` at `0x1400917a9`
- `ntoskrnl!ExAllocatePool2` at `0x1400917a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091836`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091836`
- `ksecdd!BCryptCreateHash` at `0x14009181c`
- `ksecdd!BCryptCreateHash` at `0x14009181c`

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
0x140091780  push    rbx
0x140091782  push    rbp
0x140091783  push    rsi
0x140091784  push    rdi
0x140091785  sub     rsp, 48h
0x140091789  movzx   esi, r8b
0x14009178d  mov     rdi, rcx
0x140091790  cmp     edx, 1
0x140091793  jnz     loc_14009186B
0x140091799  mov     edx, 10h
0x14009179e  mov     ecx, 42h ; 'B'
0x1400917a3  mov     r8d, 2332534Ch
0x1400917a9  call    cs:__imp_ExAllocatePool2
0x1400917b0  nop     dword ptr [rax+rax+00h]
0x1400917b5  mov     rbx, rax
0x1400917b8  test    rax, rax
0x1400917bb  jz      loc_140091864
0x1400917c1  lea     r8, SmbCryptoHashAlgorithms; Parameter
0x1400917c8  xor     r9d, r9d; Context
0x1400917cb  lea     rdx, SmbCryptoHashAlgorithmInitialize; InitFn
0x1400917d2  mov     [rax+8], r8
0x1400917d6  lea     rcx, RunOnce; RunOnce
0x1400917dd  call    cs:__imp_RtlRunOnceExecuteOnce
0x1400917e4  nop     dword ptr [rax+rax+00h]
0x1400917e9  mov     ebp, eax
0x1400917eb  test    eax, eax
0x1400917ed  js      short loc_14009182E
0x1400917ef  mov     rcx, cs:SmbCryptoHashAlgorithms; hAlgorithm
0x1400917f6  neg     sil
0x1400917f9  mov     rdx, rbx; phHash
0x1400917fc  sbb     eax, eax
0x1400917fe  xor     r9d, r9d; cbHashObject
0x140091801  and     eax, 20h
0x140091804  xor     r8d, r8d; pbHashObject
0x140091807  mov     [rsp+68h+dwFlags], eax; dwFlags
0x14009180b  mov     [rsp+68h+cbSecret], 0; cbSecret
0x140091813  mov     [rsp+68h+pbSecret], 0; pbSecret
0x14009181c  call    cs:__imp_BCryptCreateHash
0x140091823  nop     dword ptr [rax+rax+00h]
0x140091828  mov     ebp, eax
0x14009182a  test    eax, eax
0x14009182c  jns     short loc_140091855
0x14009182e  mov     edx, 2332534Ch; Tag
0x140091833  mov     rcx, rbx; P
0x140091836  call    cs:__imp_ExFreePoolWithTag
0x14009183d  nop     dword ptr [rax+rax+00h]
0x140091842  mov     qword ptr [rdi], 0
0x140091849  mov     eax, ebp
0x14009184b  add     rsp, 48h
0x14009184f  pop     rdi
0x140091850  pop     rsi
0x140091851  pop     rbp
0x140091852  pop     rbx
0x140091853  retn
0x140091855  mov     [rdi], rbx
0x140091858  xor     eax, eax
0x14009185a  add     rsp, 48h
0x14009185e  pop     rdi
0x14009185f  pop     rsi
0x140091860  pop     rbp
0x140091861  pop     rbx
0x140091862  retn
0x140091864  mov     ebp, 0C000009Ah
0x140091869  jmp     short loc_140091842
0x14009186b  mov     ebp, 0C000000Dh
0x140091870  jmp     short loc_140091842
```
