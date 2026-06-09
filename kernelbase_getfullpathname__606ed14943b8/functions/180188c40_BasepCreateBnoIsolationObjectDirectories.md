# BasepCreateBnoIsolationObjectDirectories

- ea: `0x180188c40`
- end: `0x180188e2c`
- name: `BasepCreateBnoIsolationObjectDirectories`
- size: `492`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x18008e220`

## callees

- `0x1800731a0`
- `0x180188c40`
- `0x180188e34`

## import_xrefs

- `ntdll!NtClose` at `0x180188dad`
- `ntdll!NtClose` at `0x180188dc2`
- `ntdll!NtClose` at `0x180188de3`
- `ntdll!NtClose` at `0x180188dad`
- `ntdll!NtClose` at `0x180188dc2`
- `ntdll!NtClose` at `0x180188de3`
- `ntdll!RtlFreeHeap` at `0x180188e08`
- `ntdll!RtlFreeHeap` at `0x180188e08`
- `ntdll!NtOpenProcessToken` at `0x180188c9d`
- `ntdll!NtOpenProcessToken` at `0x180188c9d`
- `ntdll!NtCreateDirectoryObjectEx` at `0x180188d54`
- `ntdll!NtCreateDirectoryObjectEx` at `0x180188d54`
- `ntdll!RtlAllocateHeap` at `0x180188ccc`
- `ntdll!RtlAllocateHeap` at `0x180188ccc`

## pseudocode

```c
__int64 __fastcall BasepCreateBnoIsolationObjectDirectories(HANDLE TokenHandle, __int64 a2)
{
  HANDLE v3; // rdi
  int NamedObjectDirectoryForToken; // edi
  unsigned int v5; // r14d
  void **Heap; // rbx
  __int64 i; // rsi
  void *v8; // rcx
  __int128 v10; // [rsp+40h] [rbp-30h] BYREF
  __int128 v11; // [rsp+50h] [rbp-20h]
  __int128 v12; // [rsp+60h] [rbp-10h]
  HANDLE Handle; // [rsp+90h] [rbp+20h] BYREF
  HANDLE TokenHandlea; // [rsp+98h] [rbp+28h] BYREF

  *(_QWORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 16) = 0;
  TokenHandlea = 0;
  v3 = TokenHandle;
  Handle = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( !TokenHandle )
  {
    NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandlea);
    if ( NamedObjectDirectoryForToken < 0 )
    {
      Heap = 0;
      v5 = 0;
      goto LABEL_11;
    }
    v3 = TokenHandlea;
  }
  v5 = 5;
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x28u);
  if ( Heap )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(v3, 1, 0, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      LODWORD(v10) = 48;
      *((_QWORD *)&v10 + 1) = Handle;
      DWORD2(v11) = 128;
      *(_QWORD *)&v11 = a2;
      v12 = 0;
      NamedObjectDirectoryForToken = NtCreateDirectoryObjectEx(Heap, 15, &v10, 0, 1);
      if ( NamedObjectDirectoryForToken >= 0 )
      {
        NamedObjectDirectoryForToken = BasepCreateBnoIsolationSymbolicLinks(
                                         Handle,
                                         *Heap,
                                         a2,
                                         Heap + 1,
                                         Heap + 2,
                                         Heap + 3,
                                         Heap + 4);
        if ( NamedObjectDirectoryForToken >= 0 )
        {
          *(_QWORD *)(a2 + 24) = Heap;
          Heap = 0;
          *(_DWORD *)(a2 + 16) = 5;
        }
      }
    }
  }
  else
  {
    NamedObjectDirectoryForToken = -1073741801;
  }
LABEL_11:
  if ( TokenHandlea )
    NtClose(TokenHandlea);
  if ( Handle )
    NtClose(Handle);
  if ( Heap )
  {
    for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
    {
      v8 = Heap[i];
      if ( v8 )
        NtClose(v8);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  return (unsigned int)NamedObjectDirectoryForToken;
}

```

## disassembly

```asm
0x180188c40  mov     [rsp-18h+arg_10], rbx
0x180188c45  mov     [rsp-18h+arg_18], rsi
0x180188c4a  push    rbp
0x180188c4b  push    rdi
0x180188c4c  push    r14
0x180188c4e  mov     rbp, rsp
0x180188c51  sub     rsp, 70h
0x180188c55  mov     qword ptr [rdx+18h], 0
0x180188c5d  xorps   xmm0, xmm0
0x180188c60  mov     dword ptr [rdx+10h], 0
0x180188c67  mov     rsi, rdx
0x180188c6a  mov     [rbp+TokenHandle], 0
0x180188c72  mov     rdi, rcx
0x180188c75  mov     [rbp+Handle], 0
0x180188c7d  mov     ebx, 8
0x180188c82  movups  [rbp+var_30], xmm0
0x180188c86  movups  [rbp+var_20], xmm0
0x180188c8a  movups  [rbp+var_10], xmm0
0x180188c8e  test    rcx, rcx
0x180188c91  jnz     short loc_180188CB3
0x180188c93  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180188c97  mov     edx, ebx; DesiredAccess
0x180188c99  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180188c9d  call    cs:__imp_NtOpenProcessToken
0x180188ca4  nop     dword ptr [rax+rax+00h]
0x180188ca9  mov     edi, eax
0x180188cab  test    eax, eax
0x180188cad  js      short loc_180188CEA
0x180188caf  mov     rdi, [rbp+TokenHandle]
0x180188cb3  mov     rcx, gs:60h
0x180188cbc  mov     r14d, 5
0x180188cc2  mov     edx, ebx; Flags
0x180188cc4  mov     rcx, [rcx+30h]; HeapHandle
0x180188cc8  lea     r8d, [r14+23h]; Size
0x180188ccc  call    cs:__imp_RtlAllocateHeap
0x180188cd3  nop     dword ptr [rax+rax+00h]
0x180188cd8  mov     rbx, rax
0x180188cdb  test    rax, rax
0x180188cde  jnz     short loc_180188CF4
0x180188ce0  mov     edi, 0C0000017h
0x180188ce5  jmp     loc_180188DA4
0x180188cea  xor     ebx, ebx
0x180188cec  xor     r14d, r14d
0x180188cef  jmp     loc_180188DA4
0x180188cf4  mov     r9d, 0Fh
0x180188cfa  lea     rax, [rbp+Handle]
0x180188cfe  xor     r8d, r8d
0x180188d01  mov     [rsp+70h+var_50], rax; __int64
0x180188d06  mov     rcx, rdi; TokenHandle
0x180188d09  lea     edx, [r9-0Eh]
0x180188d0d  call    BasepGetNamedObjectDirectoryForToken
0x180188d12  mov     edi, eax
0x180188d14  test    eax, eax
0x180188d16  js      loc_180188DA4
0x180188d1c  mov     rax, [rbp+Handle]
0x180188d20  lea     r8, [rbp+var_30]
0x180188d24  xor     r9d, r9d
0x180188d27  mov     dword ptr [rbp+var_30], 30h ; '0'
0x180188d2e  xorps   xmm0, xmm0
0x180188d31  mov     qword ptr [rbp+var_30+8], rax
0x180188d35  mov     rcx, rbx
0x180188d38  mov     dword ptr [rbp+var_20+8], 80h
0x180188d3f  mov     qword ptr [rbp+var_20], rsi
0x180188d43  lea     edx, [r9+0Fh]
0x180188d47  mov     dword ptr [rsp+70h+var_50], 1
0x180188d4f  movdqu  [rbp+var_10], xmm0
0x180188d54  call    cs:__imp_NtCreateDirectoryObjectEx
0x180188d5b  nop     dword ptr [rax+rax+00h]
0x180188d60  mov     edi, eax
0x180188d62  test    eax, eax
0x180188d64  js      short loc_180188DA4
0x180188d66  lea     rax, [rbx+20h]
0x180188d6a  mov     r8, rsi
0x180188d6d  mov     [rsp+70h+var_40], rax; __int64
0x180188d72  lea     rcx, [rbx+18h]
0x180188d76  mov     [rsp+70h+var_48], rcx; __int64
0x180188d7b  lea     rdx, [rbx+10h]
0x180188d7f  mov     rcx, [rbp+Handle]; Handle
0x180188d83  lea     r9, [rbx+8]
0x180188d87  mov     [rsp+70h+var_50], rdx; __int64
0x180188d8c  mov     rdx, [rbx]
0x180188d8f  call    BasepCreateBnoIsolationSymbolicLinks
0x180188d94  mov     edi, eax
0x180188d96  test    eax, eax
0x180188d98  js      short loc_180188DA4
0x180188d9a  mov     [rsi+18h], rbx
0x180188d9e  xor     ebx, ebx
0x180188da0  mov     [rsi+10h], r14d
0x180188da4  mov     rcx, [rbp+TokenHandle]; Handle
0x180188da8  test    rcx, rcx
0x180188dab  jz      short loc_180188DB9
0x180188dad  call    cs:__imp_NtClose
0x180188db4  nop     dword ptr [rax+rax+00h]
0x180188db9  mov     rcx, [rbp+Handle]; Handle
0x180188dbd  test    rcx, rcx
0x180188dc0  jz      short loc_180188DCE
0x180188dc2  call    cs:__imp_NtClose
0x180188dc9  nop     dword ptr [rax+rax+00h]
0x180188dce  test    rbx, rbx
0x180188dd1  jz      short loc_180188E14
0x180188dd3  xor     esi, esi
0x180188dd5  test    r14d, r14d
0x180188dd8  jz      short loc_180188DF6
0x180188dda  mov     rcx, [rbx+rsi*8]; Handle
0x180188dde  test    rcx, rcx
0x180188de1  jz      short loc_180188DEF
0x180188de3  call    cs:__imp_NtClose
0x180188dea  nop     dword ptr [rax+rax+00h]
0x180188def  inc     esi
0x180188df1  cmp     esi, r14d
0x180188df4  jb      short loc_180188DDA
0x180188df6  mov     rcx, gs:60h
0x180188dff  mov     r8, rbx; P
0x180188e02  xor     edx, edx; Flags
0x180188e04  mov     rcx, [rcx+30h]; HeapHandle
0x180188e08  call    cs:__imp_RtlFreeHeap
0x180188e0f  nop     dword ptr [rax+rax+00h]
0x180188e14  lea     r11, [rsp+70h+var_s0]
0x180188e19  mov     eax, edi
0x180188e1b  mov     rbx, [r11+30h]
0x180188e1f  mov     rsi, [r11+38h]
0x180188e23  mov     rsp, r11
0x180188e26  pop     r14
0x180188e28  pop     rdi
0x180188e29  pop     rbp
0x180188e2a  retn
```
