# MRxSmb2ProcessSmbCopyData

- ea: `0x14000cfa0`
- end: `0x14000d136`
- name: `MRxSmb2ProcessSmbCopyData`
- size: `406`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000cfa0`
- `0x14000d4e0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d0ee`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d11d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d0ee`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d11d`
- `ksecdd!BCryptHashData` at `0x14000d03c`
- `ksecdd!BCryptHashData` at `0x14000d03c`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14000d068`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14000d068`

## pseudocode

```c
__int64 __fastcall MRxSmb2ProcessSmbCopyData(__int64 a1, int a2, unsigned int a3)
{
  __int64 result; // rax
  int v6; // ecx
  struct _MDL *v7; // rbp
  ULONG v8; // r12d
  struct _MDL *v9; // r14
  int v10; // r15d
  UCHAR *MappedSystemVa; // rax
  ULONG ByteCount; // edi
  NTSTATUS v13; // eax
  unsigned int v14; // edi
  PVOID v15; // rax

  result = 0;
  if ( a2 >= 0 )
  {
    v6 = *(_DWORD *)(a1 + 4);
    if ( (v6 & 0x8000) == 0 && (v6 & 0x1000) != 0 )
    {
      v7 = *(struct _MDL **)(a1 + 752);
      if ( !v7 )
        v7 = *(struct _MDL **)(a1 + 720);
      v8 = a3;
      v9 = v7;
      v10 = 0;
      while ( v9 )
      {
        if ( (v9->MdlFlags & 5) != 0 )
          MappedSystemVa = (UCHAR *)v9->MappedSystemVa;
        else
          MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000010u);
        if ( !MappedSystemVa )
        {
          v10 = -1073741670;
          break;
        }
        ByteCount = v9->ByteCount;
        if ( ByteCount >= v8 )
          ByteCount = v8;
        v13 = BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a1 + 792), MappedSystemVa, ByteCount, 0);
        v9 = v9->Next;
        v8 -= ByteCount;
        v10 = v13;
      }
      SmbCseUpdateBufferContextStatus(a1, (unsigned int)v10);
      if ( v10 >= 0 )
      {
        v14 = v7->ByteCount;
        if ( a3 < v14 )
          v14 = a3;
        if ( (v7->MdlFlags & 5) != 0 )
          v15 = v7->MappedSystemVa;
        else
          v15 = MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000010u);
        return Smb2ValidateIncomingSignature(a1, 0, v14, (__int64)v15);
      }
      else
      {
        return (unsigned int)v10;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000cfa0  push    rbx
0x14000cfa2  push    rsi
0x14000cfa3  sub     rsp, 48h
0x14000cfa7  xor     eax, eax
0x14000cfa9  mov     esi, r8d
0x14000cfac  mov     rbx, rcx
0x14000cfaf  test    edx, edx
0x14000cfb1  js      short loc_14000CFC2
0x14000cfb3  mov     ecx, [rcx+4]
0x14000cfb6  bt      ecx, 0Fh
0x14000cfba  jb      short loc_14000CFC2
0x14000cfbc  bt      ecx, 0Ch
0x14000cfc0  jb      short loc_14000CFCA
0x14000cfc2  add     rsp, 48h
0x14000cfc6  pop     rsi
0x14000cfc7  pop     rbx
0x14000cfc8  retn
0x14000cfca  mov     [rsp+58h+arg_0], rbp
0x14000cfcf  mov     rbp, [rbx+2F0h]
0x14000cfd6  mov     [rsp+58h+var_18], r12
0x14000cfdb  mov     [rsp+58h+var_20], r14
0x14000cfe0  mov     [rsp+58h+var_28], r15
0x14000cfe5  test    rbp, rbp
0x14000cfe8  jnz     short loc_14000CFF1
0x14000cfea  mov     rbp, [rbx+2D0h]
0x14000cff1  mov     r12d, esi
0x14000cff4  mov     [rsp+58h+arg_18], rax
0x14000cff9  mov     r14, rbp
0x14000cffc  mov     [rsp+58h+arg_8], rdi
0x14000d001  xor     r15d, r15d
0x14000d004  test    r14, r14
0x14000d007  jz      short loc_14000D053
0x14000d009  test    byte ptr [r14+0Ah], 5
0x14000d00e  jz      loc_14000D0D0
0x14000d014  mov     rax, [r14+18h]
0x14000d018  test    rax, rax
0x14000d01b  jz      loc_14000D12B
0x14000d021  mov     edi, [r14+28h]
0x14000d025  mov     rdx, rax; pbInput
0x14000d028  mov     rcx, [rbx+318h]; hHash
0x14000d02f  cmp     edi, r12d
0x14000d032  cmovnb  edi, r12d
0x14000d036  xor     r9d, r9d; dwFlags
0x14000d039  mov     r8d, edi; cbInput
0x14000d03c  call    cs:__imp_BCryptHashData
0x14000d043  nop     dword ptr [rax+rax+00h]
0x14000d048  mov     r14, [r14]
0x14000d04b  sub     r12d, edi
0x14000d04e  mov     r15d, eax
0x14000d051  jmp     short loc_14000D004
0x14000d053  mov     dword ptr [rsp+58h+arg_18], r15d
0x14000d058  mov     rcx, rbx
0x14000d05b  mov     dword ptr [rsp+58h+arg_18+4], 0
0x14000d063  mov     rdx, [rsp+58h+arg_18]
0x14000d068  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14000d06f  nop     dword ptr [rax+rax+00h]
0x14000d074  mov     r14, [rsp+58h+var_20]
0x14000d079  mov     r12, [rsp+58h+var_18]
0x14000d07e  test    r15d, r15d
0x14000d081  jns     short loc_14000D09A
0x14000d083  mov     rdi, [rsp+58h+arg_8]
0x14000d088  mov     eax, r15d
0x14000d08b  mov     r15, [rsp+58h+var_28]
0x14000d090  mov     rbp, [rsp+58h+arg_0]
0x14000d095  jmp     loc_14000CFC2
0x14000d09a  mov     edi, [rbp+28h]
0x14000d09d  cmp     esi, edi
0x14000d09f  cmovb   edi, esi
0x14000d0a2  test    byte ptr [rbp+0Ah], 5
0x14000d0a6  jz      short loc_14000D0FF
0x14000d0a8  mov     rax, [rbp+18h]
0x14000d0ac  mov     r9, rax
0x14000d0af  mov     r8d, edi
0x14000d0b2  xor     edx, edx
0x14000d0b4  mov     rcx, rbx
0x14000d0b7  call    Smb2ValidateIncomingSignature
0x14000d0bc  mov     rdi, [rsp+58h+arg_8]
0x14000d0c1  mov     rbp, [rsp+58h+arg_0]
0x14000d0c6  mov     r15, [rsp+58h+var_28]
0x14000d0cb  jmp     loc_14000CFC2
0x14000d0d0  mov     [rsp+58h+Priority], 40000010h; Priority
0x14000d0d8  xor     r9d, r9d; RequestedAddress
0x14000d0db  xor     edx, edx; AccessMode
0x14000d0dd  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000d0e5  mov     r8d, 1; CacheType
0x14000d0eb  mov     rcx, r14; MemoryDescriptorList
0x14000d0ee  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000d0f5  nop     dword ptr [rax+rax+00h]
0x14000d0fa  jmp     loc_14000D018
0x14000d0ff  mov     [rsp+58h+Priority], 40000010h; Priority
0x14000d107  xor     r9d, r9d; RequestedAddress
0x14000d10a  xor     edx, edx; AccessMode
0x14000d10c  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000d114  mov     r8d, 1; CacheType
0x14000d11a  mov     rcx, rbp; MemoryDescriptorList
0x14000d11d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000d124  nop     dword ptr [rax+rax+00h]
0x14000d129  jmp     short loc_14000D0AC
0x14000d12b  mov     r15d, 0C000009Ah
0x14000d131  jmp     loc_14000D053
```
