# Smb2InitializeBindingObjectHash

- ea: `0x14001fc10`
- end: `0x14001fcf6`
- name: `Smb2InitializeBindingObjectHash`
- size: `230`
- prototype: `NTSTATUS __fastcall(__int64, UCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140026bd0`
- `0x140055fb0`

## callees

- `0x14001fc10`
- `0x14002a6a8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001fc73`
- `ntoskrnl!ExAllocatePool2` at `0x14001fc73`
- `ksecdd!BCryptCreateHash` at `0x14001fcb5`
- `ksecdd!BCryptCreateHash` at `0x14001fcb5`
- `mrxsmb!SmbCryptoKeyedHashGetHashAlgorithmMetadata` at `0x14001fc37`
- `mrxsmb!SmbCryptoKeyedHashGetHashAlgorithmMetadata` at `0x14001fc37`

## pseudocode

```c
NTSTATUS __fastcall Smb2InitializeBindingObjectHash(__int64 a1, UCHAR *a2)
{
  __int64 v2; // r15
  __int64 HashAlgorithmMetadata; // rax
  void *v6; // rbp
  __int64 v7; // rdx
  UCHAR *Pool2; // rax
  NTSTATUS result; // eax
  int v10; // edi

  v2 = *(_QWORD *)(a1 + 384);
  HashAlgorithmMetadata = SmbCryptoKeyedHashGetHashAlgorithmMetadata(*(unsigned int *)(*(_QWORD *)(a1 + 392) + 600LL));
  v6 = *(void **)HashAlgorithmMetadata;
  v7 = *(unsigned int *)(HashAlgorithmMetadata + 12);
  *(_DWORD *)(a1 + 512) = v7;
  *(_DWORD *)(a1 + 516) = *(_DWORD *)(HashAlgorithmMetadata + 8);
  *(_WORD *)(a1 + 520) = *(_WORD *)(HashAlgorithmMetadata + 16);
  Pool2 = (UCHAR *)ExAllocatePool2(66, v7, 1834184520);
  *(_QWORD *)(a1 + 504) = Pool2;
  if ( Pool2 )
  {
    result = BCryptCreateHash(v6, (BCRYPT_HASH_HANDLE *)(a1 + 496), Pool2, *(_DWORD *)(a1 + 512), a2, 0x10u, 0);
    v10 = result;
    if ( result >= 0 )
      return result;
  }
  else
  {
    v10 = -1073741670;
  }
  *(_QWORD *)(a1 + 496) = 0;
  if ( v2 && !*(_BYTE *)(v2 + 464) )
    v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_60db1590be613abca80435fd5891bee8_Traceguids, v2, a1, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x14001fc10  push    rbx
0x14001fc12  push    rbp
0x14001fc13  push    rsi
0x14001fc14  push    rdi
0x14001fc15  push    r14
0x14001fc17  push    r15
0x14001fc19  sub     rsp, 48h
0x14001fc1d  mov     r15, [rcx+180h]
0x14001fc24  mov     rbx, rcx
0x14001fc27  mov     rcx, [rcx+188h]
0x14001fc2e  mov     rdi, rdx
0x14001fc31  mov     ecx, [rcx+258h]
0x14001fc37  call    cs:__imp_SmbCryptoKeyedHashGetHashAlgorithmMetadata
0x14001fc3e  nop     dword ptr [rax+rax+00h]
0x14001fc43  mov     r8d, [rax+0Ch]
0x14001fc47  mov     rbp, [rax]
0x14001fc4a  mov     edx, r8d
0x14001fc4d  mov     [rbx+200h], r8d
0x14001fc54  mov     r8d, 6D536F48h
0x14001fc5a  mov     ecx, [rax+8]
0x14001fc5d  mov     [rbx+204h], ecx
0x14001fc63  mov     ecx, 42h ; 'B'
0x14001fc68  movzx   eax, word ptr [rax+10h]
0x14001fc6c  mov     [rbx+208h], ax
0x14001fc73  call    cs:__imp_ExAllocatePool2
0x14001fc7a  nop     dword ptr [rax+rax+00h]
0x14001fc7f  xor     esi, esi
0x14001fc81  mov     [rbx+1F8h], rax
0x14001fc88  lea     r14, [rbx+1F0h]
0x14001fc8f  test    rax, rax
0x14001fc92  jz      short loc_14001FCD5
0x14001fc94  mov     r9d, [rbx+200h]; cbHashObject
0x14001fc9b  mov     r8, rax; pbHashObject
0x14001fc9e  mov     [rsp+78h+dwFlags], esi; dwFlags
0x14001fca2  mov     rdx, r14; phHash
0x14001fca5  mov     [rsp+78h+cbSecret], 10h; cbSecret
0x14001fcad  mov     rcx, rbp; hAlgorithm
0x14001fcb0  mov     [rsp+78h+pbSecret], rdi; pbSecret
0x14001fcb5  call    cs:__imp_BCryptCreateHash
0x14001fcbc  nop     dword ptr [rax+rax+00h]
0x14001fcc1  mov     edi, eax
0x14001fcc3  test    eax, eax
0x14001fcc5  js      short loc_14001FCDA
0x14001fcc7  add     rsp, 48h
0x14001fccb  pop     r15
0x14001fccd  pop     r14
0x14001fccf  pop     rdi
0x14001fcd0  pop     rsi
0x14001fcd1  pop     rbp
0x14001fcd2  pop     rbx
0x14001fcd3  retn
0x14001fcd5  mov     edi, 0C000009Ah
0x14001fcda  mov     [r14], rsi
0x14001fcdd  test    r15, r15
0x14001fce0  jz      loc_14003C30C
0x14001fce6  cmp     byte ptr [r15+1D0h], 0
0x14001fcee  cmovz   edi, esi
0x14001fcf1  jmp     loc_14003C30C
0x14003c30c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c313  lea     rax, WPP_GLOBAL_Control
0x14003c31a  cmp     rcx, rax
0x14003c31d  jz      short loc_14003C34D
0x14003c31f  mov     eax, [rcx+2Ch]
0x14003c322  test    al, 1
0x14003c324  jz      short loc_14003C34D
0x14003c326  cmp     byte ptr [rcx+29h], 1
0x14003c32a  jb      short loc_14003C34D
0x14003c32c  mov     rcx, [rcx+18h]
0x14003c330  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14003c337  mov     edx, 0Ah
0x14003c33c  mov     [rsp+78h+cbSecret], edi
0x14003c340  mov     r9, r15
0x14003c343  mov     [rsp+78h+pbSecret], rbx
0x14003c348  call    WPP_SF_qqD
0x14003c34d  mov     eax, edi
0x14003c34f  jmp     loc_14001FCC7
```
