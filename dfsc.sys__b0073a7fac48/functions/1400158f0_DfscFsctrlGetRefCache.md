# DfscFsctrlGetRefCache

- ea: `0x1400158f0`
- end: `0x140015f27`
- name: `DfscFsctrlGetRefCache`
- size: `1591`
- prototype: `__int64 __fastcall(PIRP Irp, void *, size_t Size)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x140002570`
- `0x1400048b4`
- `0x140006080`
- `0x140006380`
- `0x1400158f0`
- `0x140016f74`
- `0x14001a79c`
- `0x140026c90`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x140015963`
- `ntoskrnl!IoIs32bitProcess` at `0x140015963`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140015c9c`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140015c9c`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015a4c`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015b39`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015e8c`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015a4c`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015b39`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015e8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400159c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015efd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400159c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015efd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400159b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015ef1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400159b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015ef1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001598b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001598b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015972`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015972`

## pseudocode

```c
__int64 __fastcall DfscFsctrlGetRefCache(PIRP Irp, void *a2, size_t Size)
{
  size_t v3; // rsi
  __int64 result; // rax
  PUNICODE_PREFIX_TABLE PrefixTable; // [rsp+48h] [rbp-39h]
  _QWORD v8[2]; // [rsp+70h] [rbp-11h] BYREF
  PERESOURCE Resource; // [rsp+88h] [rbp+7h]
  size_t v10; // [rsp+98h] [rbp+17h]

  v3 = (unsigned int)Size;
  v8[1] = 0;
  v8[0] = 0;
  if ( !a2 )
    return 3221225485LL;
  result = DfscGetContainerContextFromIrp(Irp, v8);
  if ( (int)result >= 0 )
  {
    PrefixTable = (PUNICODE_PREFIX_TABLE)DfscGetReferralCache(v8[0]);
    IoIs32bitProcess(Irp);
    KeEnterCriticalRegion();
    Resource = (PERESOURCE)&PrefixTable[2].NextPrefixTree;
    ExAcquireResourceExclusiveLite((PERESOURCE)&PrefixTable[2].NextPrefixTree, 1u);
    DfscGetRefCacheSizeLocked(PrefixTable);
    v10 = v3;
    memset(a2, 0, v3);
    ExReleaseResourceLite(Resource);
    KeLeaveCriticalRegion();
    return 3221225701LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400158f0  mov     rax, rsp
0x1400158f3  mov     [rax+18h], rbx
0x1400158f7  mov     [rax+20h], r9d
0x1400158fb  mov     [rax+8], rcx
0x1400158ff  push    rbp
0x140015900  push    rsi
0x140015901  push    rdi
0x140015902  push    r12
0x140015904  push    r13
0x140015906  push    r14
0x140015908  push    r15
0x14001590a  lea     rbp, [rax-5Fh]
0x14001590e  sub     rsp, 0A0h
0x140015915  xor     r13d, r13d
0x140015918  mov     esi, r8d
0x14001591b  mov     [rbp+57h+arg_8], r13d
0x14001591f  mov     r12d, r9d
0x140015922  mov     [rbp+57h+var_60], r13
0x140015926  mov     rdi, rdx
0x140015929  mov     [rbp+57h+var_68], r13
0x14001592d  mov     r14, rcx
0x140015930  test    rdx, rdx
0x140015933  jnz     short loc_14001593F
0x140015935  mov     eax, 0C000000Dh
0x14001593a  jmp     loc_140015F0B
0x14001593f  lea     rdx, [rbp+57h+var_68]
0x140015943  call    DfscGetContainerContextFromIrp
0x140015948  test    eax, eax
0x14001594a  js      loc_140015F0B
0x140015950  mov     rcx, [rbp+57h+var_68]
0x140015954  call    DfscGetReferralCache
0x140015959  mov     rcx, r14; Irp
0x14001595c  mov     [rbp+57h+PrefixTable], rax
0x140015960  mov     rbx, rax
0x140015963  call    cs:__imp_IoIs32bitProcess
0x14001596a  nop     dword ptr [rax+rax+00h]
0x14001596f  mov     r15b, al
0x140015972  call    cs:__imp_KeEnterCriticalRegion
0x140015979  nop     dword ptr [rax+rax+00h]
0x14001597e  lea     rax, [rbx+38h]
0x140015982  mov     dl, 1; Wait
0x140015984  mov     rcx, rax; Resource
0x140015987  mov     [rbp+57h+Resource], rax
0x14001598b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140015992  nop     dword ptr [rax+rax+00h]
0x140015997  test    r15b, r15b
0x14001599a  lea     rdx, [rbp+57h+arg_8]
0x14001599e  mov     r9d, r12d
0x1400159a1  mov     rcx, rbx; PrefixTable
0x1400159a4  setnz   r8b
0x1400159a8  call    DfscGetRefCacheSizeLocked
0x1400159ad  mov     ebx, [rbp+57h+arg_8]
0x1400159b0  cmp     ebx, esi
0x1400159b2  jbe     short loc_1400159F3
0x1400159b4  mov     rcx, [rbp+57h+Resource]; Resource
0x1400159b8  call    cs:__imp_ExReleaseResourceLite
0x1400159bf  nop     dword ptr [rax+rax+00h]
0x1400159c4  call    cs:__imp_KeLeaveCriticalRegion
0x1400159cb  nop     dword ptr [rax+rax+00h]
0x1400159d0  cmp     esi, 4
0x1400159d3  jnb     short loc_1400159DF
0x1400159d5  mov     eax, 0C0000023h
0x1400159da  jmp     loc_140015F0B
0x1400159df  mov     [rdi], ebx
0x1400159e1  mov     eax, 80000005h
0x1400159e6  mov     qword ptr [r14+38h], 4
0x1400159ee  jmp     loc_140015F0B
0x1400159f3  mov     r8, rsi; Size
0x1400159f6  mov     [rbp+57h+var_40], rsi
0x1400159fa  xor     edx, edx; Val
0x1400159fc  mov     rcx, rdi; void *
0x1400159ff  call    memset
0x140015a04  test    r15b, r15b
0x140015a07  jz      short loc_140015A22
0x140015a09  cmp     ebx, 34h ; '4'
0x140015a0c  jnb     short loc_140015A18
0x140015a0e  mov     ebx, 0C00000E5h
0x140015a13  jmp     loc_140015EED
0x140015a18  mov     [rbp+57h+var_80], r13
0x140015a1c  mov     [rbp+57h+var_88], rdi
0x140015a20  jmp     short loc_140015A2F
0x140015a22  cmp     ebx, 48h ; 'H'
0x140015a25  jb      short loc_140015A0E
0x140015a27  mov     [rbp+57h+var_88], r13
0x140015a2b  mov     [rbp+57h+var_80], rdi
0x140015a2f  mov     rax, rdi
0x140015a32  mov     [rbp+57h+var_70], rbx
0x140015a36  mov     rsi, rbx
0x140015a39  mov     [rbp+57h+var_98], r13
0x140015a3d  mov     r12, r13
0x140015a40  mov     dl, 1; Restart
0x140015a42  lea     r14, [rbx+rax]
0x140015a46  xor     ebx, ebx
0x140015a48  mov     rcx, [rbp+57h+PrefixTable]; PrefixTable
0x140015a4c  call    cs:__imp_RtlNextUnicodePrefix
0x140015a53  nop     dword ptr [rax+rax+00h]
0x140015a58  mov     rdx, rax
0x140015a5b  test    rax, rax
0x140015a5e  jz      loc_140015AF5
0x140015a64  test    byte ptr [rax-3Ch], 1
0x140015a68  jz      loc_140015AEE
0x140015a6e  mov     ecx, ebx
0x140015a70  test    r15b, r15b
0x140015a73  jz      short loc_140015A8A
0x140015a75  mov     r13, [rbp+57h+var_88]
0x140015a79  lea     rax, [rbx+rbx*2]
0x140015a7d  shl     rax, 4
0x140015a81  add     r13, 4
0x140015a85  add     r13, rax
0x140015a88  jmp     short loc_140015A9D
0x140015a8a  mov     r12, [rbp+57h+var_80]
0x140015a8e  add     r12, 8
0x140015a92  shl     rcx, 6
0x140015a96  add     r12, rcx
0x140015a99  mov     [rbp+57h+var_98], r12
0x140015a9d  movzx   eax, word ptr [rdx-30h]
0x140015aa1  neg     rax
0x140015aa4  test    r15b, r15b
0x140015aa7  jz      short loc_140015ACB
0x140015aa9  lea     r14, [r14+rax*4]
0x140015aad  mov     rax, r13
0x140015ab0  sub     rax, rdi
0x140015ab3  add     rax, 30h ; '0'
0x140015ab7  cmp     rsi, rax
0x140015aba  jb      loc_140015A0E
0x140015ac0  mov     eax, r14d
0x140015ac3  sub     eax, edi
0x140015ac5  mov     [r13+2Ch], eax
0x140015ac9  jmp     short loc_140015AEC
0x140015acb  lea     r14, [r14+rax*8]
0x140015acf  mov     rax, r12
0x140015ad2  sub     rax, rdi
0x140015ad5  add     rax, 40h ; '@'
0x140015ad9  cmp     rsi, rax
0x140015adc  jb      loc_140015A0E
0x140015ae2  mov     eax, r14d
0x140015ae5  sub     eax, edi
0x140015ae7  mov     [r12+38h], rax
0x140015aec  inc     ebx
0x140015aee  xor     edx, edx
0x140015af0  jmp     loc_140015A48
0x140015af5  mov     rcx, cs:WPP_GLOBAL_Control
0x140015afc  lea     rax, WPP_GLOBAL_Control
0x140015b03  xor     esi, esi
0x140015b05  mov     [rbp+57h+var_58], rsi
0x140015b09  mov     [rbp+57h+var_78], rsi
0x140015b0d  cmp     rcx, rax
0x140015b10  jz      short loc_140015B2E
0x140015b12  test    dword ptr [rcx+2Ch], 400000h
0x140015b19  jz      short loc_140015B2E
0x140015b1b  mov     rcx, [rcx+18h]
0x140015b1f  lea     edx, [rsi+0Dh]
0x140015b22  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140015b29  call    WPP_SF_
0x140015b2e  mov     rcx, [rbp+57h+PrefixTable]; PrefixTable
0x140015b32  mov     ebx, esi
0x140015b34  mov     dl, 1; Restart
0x140015b36  mov     [rbp+57h+arg_8], ebx
0x140015b39  call    cs:__imp_RtlNextUnicodePrefix
0x140015b40  nop     dword ptr [rax+rax+00h]
0x140015b45  mov     edx, 5
0x140015b4a  test    rax, rax
0x140015b4d  jz      loc_140015E9F
0x140015b53  lea     rsi, [rax-48h]
0x140015b57  test    byte ptr [rsi+0Ch], 1
0x140015b5b  jz      loc_140015E86
0x140015b61  mov     eax, ebx
0x140015b63  xor     ebx, ebx
0x140015b65  test    r15b, r15b
0x140015b68  jz      short loc_140015B7F
0x140015b6a  mov     r13, [rbp+57h+var_88]
0x140015b6e  lea     rax, [rax+rax*2]
0x140015b72  shl     rax, 4
0x140015b76  add     r13, 4
0x140015b7a  add     r13, rax
0x140015b7d  jmp     short loc_140015B92
0x140015b7f  mov     r12, [rbp+57h+var_80]
0x140015b83  add     r12, 8
0x140015b87  shl     rax, 6
0x140015b8b  add     r12, rax
0x140015b8e  mov     [rbp+57h+var_98], r12
0x140015b92  movzx   eax, word ptr [rsi+90h]
0x140015b99  add     rax, rdx
0x140015b9c  and     rax, 0FFFFFFFFFFFFFFFCh
0x140015ba0  sub     r14, rax
0x140015ba3  test    r15b, r15b
0x140015ba6  jz      short loc_140015BCB
0x140015ba8  mov     rax, r13
0x140015bab  sub     rax, rdi
0x140015bae  add     rax, 30h ; '0'
0x140015bb2  cmp     [rbp+57h+var_70], rax
0x140015bb6  jb      loc_140015A0E
0x140015bbc  mov     eax, r14d
0x140015bbf  sub     eax, edi
0x140015bc1  mov     [r13+0], eax
0x140015bc5  mov     [r13+4], eax
0x140015bc9  jmp     short loc_140015BED
0x140015bcb  mov     rax, r12
0x140015bce  sub     rax, rdi
0x140015bd1  add     rax, 40h ; '@'
0x140015bd5  cmp     [rbp+57h+var_70], rax
0x140015bd9  jb      loc_140015A0E
0x140015bdf  mov     ecx, r14d
0x140015be2  sub     ecx, edi
0x140015be4  mov     [r12], rcx
0x140015be8  mov     [r12+8], rcx
0x140015bed  movzx   r8d, word ptr [rsi+90h]; Size
0x140015bf5  mov     rcx, r14; void *
0x140015bf8  mov     rdx, [rsi+98h]; Src
0x140015bff  call    memmove
0x140015c04  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c0b  lea     rax, WPP_GLOBAL_Control
0x140015c12  cmp     rcx, rax
0x140015c15  jz      short loc_140015C3D
0x140015c17  test    dword ptr [rcx+2Ch], 400000h
0x140015c1e  jz      short loc_140015C3D
0x140015c20  mov     rcx, [rcx+18h]
0x140015c24  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x140015c2b  mov     edx, 0Eh
0x140015c30  mov     [rsp+20h], r14
0x140015c35  mov     r9, rsi
0x140015c38  call    WPP_SF_qS
0x140015c3d  mov     eax, [rsi+4]
0x140015c40  dec     eax
0x140015c42  test    r15b, r15b
0x140015c45  jz      short loc_140015C4D
0x140015c47  mov     [r13+14h], eax
0x140015c4b  jmp     short loc_140015C52
0x140015c4d  mov     [r12+1Ch], eax
0x140015c52  lea     r8, [rbp+57h+var_60]
0x140015c56  xor     edx, edx
0x140015c58  mov     rcx, rsi
0x140015c5b  call    DfscRmGetReferralTtlTickCounts
0x140015c60  cmp     [rbp+57h+var_60], rbx
0x140015c64  jnz     short loc_140015C6D
0x140015c66  mov     edx, 0FFFFFFFFh
0x140015c6b  jmp     short loc_140015CDD
0x140015c6d  xor     r8d, r8d
0x140015c70  mov     [rbp+57h+var_A0], rbx
0x140015c74  lea     rdx, [rbp+57h+var_A0]
0x140015c78  mov     rcx, rsi
0x140015c7b  call    DfscRmGetReferralTtlTickCounts
0x140015c80  mov     r12, [rbp+57h+var_A0]
0x140015c84  mov     rbx, 0FFFFF78000000320h
0x140015c8e  mov     rbx, [rbx]
0x140015c91  cmp     rbx, r12
0x140015c94  jl      short loc_140015C9C
0x140015c96  xor     ebx, ebx
0x140015c98  mov     edx, ebx
0x140015c9a  jmp     short loc_140015CDD
0x140015c9c  call    cs:__imp_KeQueryTimeIncrement
0x140015ca3  nop     dword ptr [rax+rax+00h]
0x140015ca8  mov     ecx, eax
0x140015caa  sub     r12, rbx
0x140015cad  mov     rax, 0D6BF94D5E57A42BDh
0x140015cb7  xor     ebx, ebx
0x140015cb9  imul    rcx, r12
0x140015cbd  imul    rcx
0x140015cc0  add     rdx, rcx
0x140015cc3  sar     rdx, 17h
0x140015cc7  mov     rax, rdx
0x140015cca  shr     rax, 3Fh
0x140015cce  add     rdx, rax
0x140015cd1  mov     eax, 0FFFFFFFFh
0x140015cd6  cmp     rdx, rax
0x140015cd9  jb      short loc_140015CDD
0x140015cdb  mov     edx, eax
0x140015cdd  mov     r12, [rbp+57h+var_98]
0x140015ce1  test    r15b, r15b
0x140015ce4  jz      short loc_140015CEC
0x140015ce6  mov     [r13+10h], edx
0x140015cea  jmp     short loc_140015CF1
0x140015cec  mov     [r12+18h], edx
0x140015cf1  movzx   eax, word ptr [rsi+18h]
0x140015cf5  test    r15b, r15b
0x140015cf8  jz      short loc_140015D00
0x140015cfa  mov     [r13+28h], eax
0x140015cfe  jmp     short loc_140015D05
0x140015d00  mov     [r12+30h], eax
0x140015d05  cmp     [rsi+18h], bx
0x140015d09  jbe     short loc_140015D1D
0x140015d0b  mov     eax, [rsi+0A0h]
0x140015d11  test    al, 1
0x140015d13  jz      short loc_140015D1D
0x140015d15  mov     r8d, 10h
0x140015d1b  jmp     short loc_140015D36
0x140015d1d  mov     r8d, 1
0x140015d23  cmp     [rsi+8], r8d
0x140015d27  jnz     short loc_140015D36
0x140015d29  test    byte ptr [rsi+0Ch], 2
0x140015d2d  mov     eax, 81h
0x140015d32  cmovnz  r8d, eax
0x140015d36  movzx   edx, word ptr [rsi+0Ch]
0x140015d3a  mov     ecx, r8d
0x140015d3d  bts     ecx, 0Fh
0x140015d41  test    dl, 4
0x140015d44  cmovz   ecx, r8d
0x140015d48  mov     r9d, ecx
0x140015d4b  bts     r9d, 9
0x140015d50  test    dl, 1
  ... truncated ...
```
