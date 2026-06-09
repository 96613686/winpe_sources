# GetCanonicalizeProxyNames

- ea: `0x1800019b4`
- end: `0x180001afa`
- name: `GetCanonicalizeProxyNames`
- size: `326`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001560`

## callees

- `0x18000193c`
- `0x1800019b4`
- `0x180001d36`

## import_xrefs

- `ntdll!RtlCanonicalizeDomainName` at `0x180001a7a`
- `ntdll!RtlCanonicalizeDomainName` at `0x180001a7a`
- `ntdll!RtlInitUnicodeString` at `0x180001a55`
- `ntdll!RtlInitUnicodeString` at `0x180001a55`
- `ntdll!RtlAllocateHeap` at `0x1800019fe`
- `ntdll!RtlAllocateHeap` at `0x1800019fe`

## pseudocode

```c
__int64 __fastcall GetCanonicalizeProxyNames(__int64 a1, _QWORD *a2, unsigned __int16 *a3, unsigned int *a4)
{
  char *Heap; // rax
  char *v8; // rbp
  int v9; // ebx
  unsigned int v10; // esi
  unsigned __int16 v11; // cx
  unsigned __int16 v12; // r14
  unsigned __int16 v13; // cx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-58h] BYREF

  *a2 = 0;
  *a4 = 0;
  *a3 = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * *(unsigned __int16 *)(a1 + 8));
  v8 = Heap;
  if ( !Heap )
  {
    v9 = -1073741670;
LABEL_11:
    FreeProxyNameArray(v8);
    return (unsigned int)v9;
  }
  v10 = 0;
  memset_0(Heap, 0, 16LL * *(unsigned __int16 *)(a1 + 8));
  v11 = *(_WORD *)(a1 + 8);
  v12 = 0;
  if ( v11 )
  {
    do
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(a1 + 8LL * v12 + 16));
      v9 = RtlCanonicalizeDomainName(&v8[16 * v12], &DestinationString, 0);
      if ( v9 < 0 )
        goto LABEL_11;
      v13 = *(_WORD *)&v8[16 * v12] >> 1;
      if ( (unsigned __int16)(v13 - 1) > 0xFEu || (v10 += v13 + 1, v10 > 0xFFFF) )
      {
        v9 = -1073741811;
        goto LABEL_11;
      }
      v11 = *(_WORD *)(a1 + 8);
    }
    while ( ++v12 < v11 );
  }
  v9 = 0;
  *a4 = v10;
  *a3 = v11;
  *a2 = v8;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800019b4  mov     [rsp+arg_8], rdx
0x1800019b9  push    rbx
0x1800019ba  push    rbp
0x1800019bb  push    rsi
0x1800019bc  push    rdi
0x1800019bd  push    r12
0x1800019bf  push    r13
0x1800019c1  push    r14
0x1800019c3  push    r15
0x1800019c5  sub     rsp, 38h
0x1800019c9  mov     r13, r8
0x1800019cc  mov     qword ptr [rdx], 0
0x1800019d3  mov     rdi, rcx
0x1800019d6  mov     dword ptr [r9], 0
0x1800019dd  xor     eax, eax
0x1800019df  xor     edx, edx; Flags
0x1800019e1  mov     [r8], ax
0x1800019e5  mov     r12, r9
0x1800019e8  movzx   r8d, word ptr [rcx+8]
0x1800019ed  mov     rcx, gs:60h
0x1800019f6  shl     r8, 4; Size
0x1800019fa  mov     rcx, [rcx+30h]; HeapHandle
0x1800019fe  call    cs:__imp_RtlAllocateHeap
0x180001a05  nop     dword ptr [rax+rax+00h]
0x180001a0a  mov     rbp, rax
0x180001a0d  test    rax, rax
0x180001a10  jnz     short loc_180001A1C
0x180001a12  mov     ebx, 0C000009Ah
0x180001a17  jmp     loc_180001AEC
0x180001a1c  movzx   r8d, word ptr [rdi+8]
0x180001a21  xor     edx, edx; Val
0x180001a23  shl     r8, 4; Size
0x180001a27  mov     rcx, rbp; void *
0x180001a2a  xor     esi, esi
0x180001a2c  call    memset_0
0x180001a31  movzx   ecx, word ptr [rdi+8]
0x180001a35  xor     eax, eax
0x180001a37  xor     r14d, r14d
0x180001a3a  cmp     ax, cx
0x180001a3d  jnb     short loc_180001ABD
0x180001a3f  xorps   xmm0, xmm0
0x180001a42  movzx   ebx, r14w
0x180001a46  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180001a4b  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180001a50  mov     rdx, [rdi+rbx*8+10h]; SourceString
0x180001a55  call    cs:__imp_RtlInitUnicodeString
0x180001a5c  nop     dword ptr [rax+rax+00h]
0x180001a61  add     rbx, rbx
0x180001a64  lea     rdx, [rsp+78h+DestinationString]
0x180001a69  xor     r8d, r8d
0x180001a6c  lea     r15, ds:0[rbx*8]
0x180001a74  add     r15, rbp
0x180001a77  mov     rcx, r15
0x180001a7a  call    cs:__imp_RtlCanonicalizeDomainName
0x180001a81  nop     dword ptr [rax+rax+00h]
0x180001a86  mov     ebx, eax
0x180001a88  test    eax, eax
0x180001a8a  js      short loc_180001AEC
0x180001a8c  movzx   ecx, word ptr [r15]
0x180001a90  mov     edx, 0FEh
0x180001a95  shr     cx, 1
0x180001a98  lea     eax, [rcx-1]
0x180001a9b  cmp     ax, dx
0x180001a9e  ja      short loc_180001AE7
0x180001aa0  inc     esi
0x180001aa2  movzx   eax, cx
0x180001aa5  add     esi, eax
0x180001aa7  cmp     esi, 0FFFFh
0x180001aad  ja      short loc_180001AE7
0x180001aaf  movzx   ecx, word ptr [rdi+8]
0x180001ab3  inc     r14w
0x180001ab7  cmp     r14w, cx
0x180001abb  jb      short loc_180001A3F
0x180001abd  mov     rax, [rsp+78h+arg_8]
0x180001ac5  xor     ebx, ebx
0x180001ac7  mov     [r12], esi
0x180001acb  mov     [r13+0], cx
0x180001ad0  mov     [rax], rbp
0x180001ad3  mov     eax, ebx
0x180001ad5  add     rsp, 38h
0x180001ad9  pop     r15
0x180001adb  pop     r14
0x180001add  pop     r13
0x180001adf  pop     r12
0x180001ae1  pop     rdi
0x180001ae2  pop     rsi
0x180001ae3  pop     rbp
0x180001ae4  pop     rbx
0x180001ae5  retn
0x180001ae7  mov     ebx, 0C000000Dh
0x180001aec  movzx   edx, word ptr [rdi+8]
0x180001af0  mov     rcx, rbp; P
0x180001af3  call    FreeProxyNameArray
0x180001af8  jmp     short loc_180001AD3
```
