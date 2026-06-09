# SecCryptComputeFileHash

- ea: `0x140032adc`
- end: `0x140032dca`
- name: `SecCryptComputeFileHash`
- size: `750`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140031c88`

## callees

- `0x1400011c0`
- `0x1400011e0`
- `0x140001c50`
- `0x140001c70`
- `0x140002fa8`
- `0x14000307c`
- `0x14000a33c`
- `0x14000a490`
- `0x140011610`
- `0x140011650`
- `0x1400119c0`
- `0x140029b88`
- `0x1400328b4`
- `0x140032948`
- `0x140032adc`
- `0x140032e14`
- `0x14003b8a4`

## import_xrefs

- `ntoskrnl!ZwReadFile` at `0x140032bba`
- `ntoskrnl!ZwReadFile` at `0x140032bba`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140032d98`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140032d98`
- `ntoskrnl!ExQueryDepthSList` at `0x140032d6c`
- `ntoskrnl!ExQueryDepthSList` at `0x140032d6c`

## pseudocode

```c
__int64 __fastcall SecCryptComputeFileHash(HANDLE FileHandle, ULONG *a2, _BYTE *a3)
{
  HANDLE v3; // rbx
  ULONG Length; // edi
  unsigned __int64 v6; // r15
  struct _SLIST_ENTRY *HashContext; // r14
  unsigned int v9; // eax
  int v10; // esi
  char *v11; // rdi
  USHORT v12; // bx
  union _LARGE_INTEGER ByteOffset; // [rsp+B0h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-50h] BYREF

  v3 = FileHandle;
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  Length = *a2;
  if ( *a2 > 0x100000 )
    Length = 0x100000;
  v6 = *(_QWORD *)a2;
  HashContext = (struct _SLIST_ENTRY *)SecAllocateHashContext();
  if ( !HashContext )
    return 3221225626LL;
  while ( 1 )
  {
    v9 = ZwReadFile(v3, 0, 0, 0, &IoStatusBlock, &HashContext[152], Length, &ByteOffset, 0);
    v10 = SecWaitForIo(v9, v3, &IoStatusBlock);
    if ( v10 < 0 || IoStatusBlock.Information != Length )
      break;
    SymCryptMd5Append(HashContext, &HashContext[152], Length);
    SymCryptSha1Append(&HashContext[7], &HashContext[152], Length);
    SymCryptSha256Append(&HashContext[15], &HashContext[152], Length);
    if ( (unsigned __int8)SecIsLshashCalculationEnabled() )
      LshashUpdate(&HashContext[23], &HashContext[152], Length);
    SecCryptCRC((_DWORD)HashContext + 2432, Length, ByteOffset.LowPart, *(_QWORD *)a2, (__int64)a3);
    ByteOffset.QuadPart += Length;
    if ( Length <= v6 )
    {
      v6 -= Length;
      if ( Length > v6 )
        Length = v6;
    }
    v3 = FileHandle;
    if ( !v6 )
      goto LABEL_16;
  }
  if ( v10 >= 0 )
    v10 = -1073741761;
LABEL_16:
  if ( v10 >= 0 )
  {
    *a3 = 3;
    SymCryptMd5Result(HashContext, a3 + 53);
    SymCryptSha1Result(&HashContext[7], a3 + 33);
    SymCryptSha256Result(&HashContext[15], a3 + 1);
    if ( (unsigned __int8)SecIsLshashCalculationEnabled() )
      LshashFinalLong(&HashContext[23], a3 + 69);
    else
      memset(a3 + 69, 0, 0x40u);
  }
  v11 = (char *)SecData + 768;
  ++*((_DWORD *)SecData + 199);
  v12 = *((_WORD *)v11 + 8);
  if ( ExQueryDepthSList((PSLIST_HEADER)v11) < v12 )
  {
    _mm_lfence();
    ExpInterlockedPushEntrySList((PSLIST_HEADER)v11, HashContext);
  }
  else
  {
    ++*((_DWORD *)v11 + 8);
    (*((void (__fastcall **)(struct _SLIST_ENTRY *))v11 + 7))(HashContext);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140032adc  mov     r11, rsp
0x140032adf  push    rbx
0x140032ae0  push    rsi
0x140032ae1  push    rdi
0x140032ae2  push    r12
0x140032ae4  push    r13
0x140032ae6  push    r14
0x140032ae8  push    r15
0x140032aea  sub     rsp, 0D0h
0x140032af1  mov     rax, cs:__security_cookie
0x140032af8  xor     rax, rsp
0x140032afb  mov     [rsp+108h+var_40], rax
0x140032b03  mov     [rsp+108h+var_98], r8
0x140032b08  mov     [rsp+108h+var_B0], rdx
0x140032b0d  mov     rbx, rcx
0x140032b10  mov     [rsp+108h+var_A0], rcx
0x140032b15  mov     [rsp+108h+var_70], rdx
0x140032b1d  mov     [rsp+108h+var_88], rcx
0x140032b25  mov     r13, r8
0x140032b28  mov     [rsp+108h+var_80], r8
0x140032b30  mov     [rsp+108h+var_60], r8
0x140032b38  xorps   xmm0, xmm0
0x140032b3b  movups  xmmword ptr [r11-50h], xmm0
0x140032b40  mov     qword ptr [r11-58h], 0
0x140032b48  mov     edi, [rdx]
0x140032b4a  mov     ecx, 100000h
0x140032b4f  cmp     edi, ecx
0x140032b51  cmova   edi, ecx
0x140032b54  mov     [rsp+108h+var_B4], edi
0x140032b58  mov     r15, [rdx]
0x140032b5b  mov     [rsp+108h+var_A8], r15
0x140032b60  call    SecAllocateHashContext
0x140032b65  mov     r14, rax
0x140032b68  mov     [rsp+108h+var_90], rax
0x140032b6d  test    rax, rax
0x140032b70  jnz     short loc_140032B7C
0x140032b72  mov     eax, 0C000009Ah
0x140032b77  jmp     loc_140032DA6
0x140032b7c  lea     r12, [r14+980h]
0x140032b83  mov     [rsp+108h+Key], 0; Key
0x140032b8c  lea     rax, [rsp+108h+var_58]
0x140032b94  mov     [rsp+108h+ByteOffset], rax; ByteOffset
0x140032b99  mov     [rsp+108h+Length], edi; Length
0x140032b9d  mov     [rsp+108h+Buffer], r12; Buffer
0x140032ba2  lea     rax, [rsp+108h+var_50]
0x140032baa  mov     [rsp+108h+IoStatusBlock], rax; IoStatusBlock
0x140032baf  xor     r9d, r9d; ApcContext
0x140032bb2  xor     r8d, r8d; ApcRoutine
0x140032bb5  xor     edx, edx; Event
0x140032bb7  mov     rcx, rbx; FileHandle
0x140032bba  call    cs:__imp_ZwReadFile
0x140032bc1  nop     dword ptr [rax+rax+00h]
0x140032bc6  lea     r8, [rsp+108h+var_50]
0x140032bce  mov     rdx, rbx
0x140032bd1  mov     ecx, eax
0x140032bd3  call    SecWaitForIo
0x140032bd8  mov     esi, eax
0x140032bda  mov     [rsp+108h+var_B8], eax
0x140032bde  test    eax, eax
0x140032be0  js      loc_140032CE3
0x140032be6  mov     ebx, edi
0x140032be8  mov     [rsp+108h+var_68], rbx
0x140032bf0  cmp     [rsp+108h+var_50.Information], rbx
0x140032bf8  jnz     loc_140032CE3
0x140032bfe  mov     r8d, ebx
0x140032c01  mov     rdx, r12
0x140032c04  mov     rcx, r14
0x140032c07  call    SymCryptMd5Append
0x140032c0c  lea     rcx, [r14+70h]
0x140032c10  mov     r8d, ebx
0x140032c13  mov     rdx, r12
0x140032c16  call    SymCryptSha1Append
0x140032c1b  lea     rcx, [r14+0F0h]
0x140032c22  mov     r8d, ebx
0x140032c25  mov     rdx, r12
0x140032c28  call    SymCryptSha256Append
0x140032c2d  call    SecIsLshashCalculationEnabled
0x140032c32  test    al, al
0x140032c34  jz      short loc_140032C48
0x140032c36  lea     rcx, [r14+170h]
0x140032c3d  mov     r8d, ebx
0x140032c40  mov     rdx, r12
0x140032c43  call    LshashUpdate
0x140032c48  mov     [rsp+108h+IoStatusBlock], r13
0x140032c4d  mov     rax, [rsp+108h+var_B0]
0x140032c52  mov     r9, [rax]
0x140032c55  mov     r8, qword ptr [rsp+108h+var_58]
0x140032c5d  mov     rdx, rbx
0x140032c60  mov     rcx, r12
0x140032c63  call    SecCryptCRC
0x140032c68  jmp     short loc_140032CAB
0x140032c6a  mov     esi, [rsp+108h+var_B8]
0x140032c6e  mov     edi, [rsp+108h+var_B4]
0x140032c72  mov     r14, [rsp+108h+var_90]
0x140032c77  mov     r15, [rsp+108h+var_A8]
0x140032c7c  mov     rax, [rsp+108h+var_88]
0x140032c84  mov     [rsp+108h+var_A0], rax
0x140032c89  mov     r13, [rsp+108h+var_80]
0x140032c91  mov     [rsp+108h+var_98], r13
0x140032c96  mov     rax, [rsp+108h+var_70]
0x140032c9e  mov     [rsp+108h+var_B0], rax
0x140032ca3  mov     rbx, [rsp+108h+var_68]
0x140032cab  test    esi, esi
0x140032cad  js      loc_140032D54
0x140032cb3  add     qword ptr [rsp+108h+var_58], rbx
0x140032cbb  cmp     rbx, r15
0x140032cbe  ja      short loc_140032CD3
0x140032cc0  sub     r15, rbx
0x140032cc3  mov     [rsp+108h+var_A8], r15
0x140032cc8  cmp     rbx, r15
0x140032ccb  cmova   edi, r15d
0x140032ccf  mov     [rsp+108h+var_B4], edi
0x140032cd3  test    r15, r15
0x140032cd6  mov     rbx, [rsp+108h+var_A0]
0x140032cdb  jnz     loc_140032B7C
0x140032ce1  jmp     short loc_140032CED
0x140032ce3  mov     eax, 0C000003Fh
0x140032ce8  test    esi, esi
0x140032cea  cmovns  esi, eax
0x140032ced  test    esi, esi
0x140032cef  js      short loc_140032D54
0x140032cf1  mov     rax, [rsp+108h+var_98]
0x140032cf6  mov     byte ptr [rax], 3
0x140032cf9  lea     rdx, [r13+35h]
0x140032cfd  mov     rcx, r14
0x140032d00  call    SymCryptMd5Result
0x140032d05  lea     rdx, [r13+21h]
0x140032d09  lea     rcx, [r14+70h]
0x140032d0d  call    SymCryptSha1Result
0x140032d12  lea     rdx, [r13+1]
0x140032d16  lea     rcx, [r14+0F0h]
0x140032d1d  call    SymCryptSha256Result
0x140032d22  mov     rbx, [rsp+108h+var_60]
0x140032d2a  call    SecIsLshashCalculationEnabled
0x140032d2f  test    al, al
0x140032d31  jz      short loc_140032D45
0x140032d33  lea     rcx, [r14+170h]; Src
0x140032d3a  lea     rdx, [rbx+45h]; void *
0x140032d3e  call    LshashFinalLong
0x140032d43  jmp     short loc_140032D54
0x140032d45  xor     edx, edx; Val
0x140032d47  lea     r8d, [rdx+40h]; Size
0x140032d4b  lea     rcx, [rbx+45h]; void *
0x140032d4f  call    memset
0x140032d54  mov     rdi, cs:SecData
0x140032d5b  add     rdi, 300h
0x140032d62  inc     dword ptr [rdi+1Ch]
0x140032d65  movzx   ebx, word ptr [rdi+10h]
0x140032d69  mov     rcx, rdi; SListHead
0x140032d6c  call    cs:__imp_ExQueryDepthSList
0x140032d73  nop     dword ptr [rax+rax+00h]
0x140032d78  cmp     ax, bx
0x140032d7b  jb      short loc_140032D8F
0x140032d7d  inc     dword ptr [rdi+20h]
0x140032d80  mov     rax, [rdi+38h]
0x140032d84  mov     rcx, r14
0x140032d87  call    cs:__guard_dispatch_icall_fptr
0x140032d8d  jmp     short loc_140032DA4
0x140032d8f  lfence
0x140032d92  mov     rdx, r14; ListEntry
0x140032d95  mov     rcx, rdi; ListHead
0x140032d98  call    cs:__imp_ExpInterlockedPushEntrySList
0x140032d9f  nop     dword ptr [rax+rax+00h]
0x140032da4  mov     eax, esi
0x140032da6  mov     rcx, [rsp+108h+var_40]
0x140032dae  xor     rcx, rsp; StackCookie
0x140032db1  call    __security_check_cookie
0x140032db6  add     rsp, 0D0h
0x140032dbd  pop     r15
0x140032dbf  pop     r14
0x140032dc1  pop     r13
0x140032dc3  pop     r12
0x140032dc5  pop     rdi
0x140032dc6  pop     rsi
0x140032dc7  pop     rbx
0x140032dc8  retn
0x14004471a  push    rbp
0x14004471c  sub     rsp, 50h
0x140044720  mov     rbp, rdx
0x140044723  lea     rdx, [rbp+50h]
0x140044727  call    SecCryptInpageExceptionFilter
0x14004472c  nop
0x14004472d  add     rsp, 50h
0x140044731  pop     rbp
0x140044732  retn
```
