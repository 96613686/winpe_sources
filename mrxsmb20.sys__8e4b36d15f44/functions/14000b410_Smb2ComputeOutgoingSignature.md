# Smb2ComputeOutgoingSignature

- ea: `0x14000b410`
- end: `0x14000b751`
- name: `Smb2ComputeOutgoingSignature`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000ae40`

## callees

- `0x14000b410`
- `0x14000b760`
- `0x140029764`
- `0x1400297fc`
- `0x140029840`
- `0x14002a1dc`
- `0x140037120`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b590`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b5bc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b590`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b5bc`
- `ksecdd!BCryptHashData` at `0x14000b4e8`
- `ksecdd!BCryptHashData` at `0x14000b4e8`
- `ksecdd!BCryptFinishHash` at `0x14000b518`
- `ksecdd!BCryptFinishHash` at `0x14000b518`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x14000b5ea`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x14000b5ea`

## pseudocode

```c
NTSTATUS __fastcall Smb2ComputeOutgoingSignature(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v3; // rcx
  _OWORD *v4; // r12
  NTSTATUS HashHandleForOutgoingSignature; // esi
  struct _MDL *v6; // rbx
  BCRYPT_HASH_HANDLE *v7; // r14
  ULONG i; // ebp
  UCHAR *MappedSystemVa; // rax
  ULONG ByteCount; // r15d
  NTSTATUS result; // eax
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  UCHAR pbOutput[16]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v16; // [rsp+40h] [rbp-48h]

  v1 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 96);
  *(_OWORD *)pbOutput = 0;
  v16 = 0;
  if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    v4 = *(_OWORD **)(v3 + 24);
  else
    v4 = MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000010u);
  if ( (*(_DWORD *)(a1 + 4) & 0x8000) == 0
    || (v14 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 96LL) + 392LL) + 320LL),
        ((v14 - 1) & 0xFFFFFFFC) != 0)
    || v14 == 3 )
  {
    HashHandleForOutgoingSignature = Smb2GenerateHashHandleForOutgoingSignature(a1, v4);
    if ( HashHandleForOutgoingSignature < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_60db1590be613abca80435fd5891bee8_Traceguids,
          v1,
          HashHandleForOutgoingSignature);
      }
    }
    else
    {
      v6 = *(struct _MDL **)(a1 + 96);
      v7 = (BCRYPT_HASH_HANDLE *)(a1 + 792);
      for ( i = *(_DWORD *)(a1 + 728); v6; i -= ByteCount )
      {
        v7 = (BCRYPT_HASH_HANDLE *)(a1 + 792);
        if ( !i )
          break;
        if ( (v6->MdlFlags & 5) != 0 )
          MappedSystemVa = (UCHAR *)v6->MappedSystemVa;
        else
          MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u);
        if ( !MappedSystemVa )
        {
          HashHandleForOutgoingSignature = -1073741670;
          goto LABEL_21;
        }
        ByteCount = v6->ByteCount;
        v7 = (BCRYPT_HASH_HANDLE *)(a1 + 792);
        if ( ByteCount >= i )
          ByteCount = i;
        HashHandleForOutgoingSignature = BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a1 + 792), MappedSystemVa, ByteCount, 0);
        if ( HashHandleForOutgoingSignature < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v13 = 18;
LABEL_45:
            WPP_SF_qq(
              v12->AttachedDevice,
              v13,
              WPP_60db1590be613abca80435fd5891bee8_Traceguids,
              *(_QWORD *)(a1 + 56),
              a1);
            goto LABEL_21;
          }
          goto LABEL_21;
        }
        v6 = v6->Next;
      }
      result = BCryptFinishHash(*v7, pbOutput, *(_DWORD *)(a1 + 800), 0);
      HashHandleForOutgoingSignature = result;
      if ( result >= 0 )
      {
        v4[3] = *(_OWORD *)pbOutput;
        return result;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v13 = 19;
        goto LABEL_45;
      }
    }
LABEL_21:
    SmbCseDestroyHashHandle(a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_60db1590be613abca80435fd5891bee8_Traceguids,
          (unsigned int)HashHandleForOutgoingSignature);
    }
    return HashHandleForOutgoingSignature;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_60db1590be613abca80435fd5891bee8_Traceguids, v1);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14000b410  push    rbp
0x14000b412  push    rdi
0x14000b413  push    r12
0x14000b415  sub     rsp, 70h
0x14000b419  mov     rax, cs:__security_cookie
0x14000b420  xor     rax, rsp
0x14000b423  mov     [rsp+88h+var_38], rax
0x14000b428  mov     rbp, [rcx+38h]
0x14000b42c  xorps   xmm0, xmm0
0x14000b42f  mov     rdi, rcx
0x14000b432  mov     rcx, [rcx+60h]; MemoryDescriptorList
0x14000b436  movups  xmmword ptr [rsp+88h+pbOutput], xmm0
0x14000b43b  movups  [rsp+88h+var_48], xmm0
0x14000b440  test    byte ptr [rcx+0Ah], 5
0x14000b444  jz      loc_14000B5A1
0x14000b44a  mov     r12, [rcx+18h]
0x14000b44e  test    dword ptr [rdi+4], 8000h
0x14000b455  mov     [rsp+88h+arg_8], rbx
0x14000b45d  jnz     loc_14000B67D
0x14000b463  mov     [rsp+88h+arg_10], rsi
0x14000b46b  mov     rdx, r12
0x14000b46e  mov     [rsp+88h+arg_18], r13
0x14000b476  mov     rcx, rdi
0x14000b479  mov     [rsp+88h+var_20], r14
0x14000b47e  mov     [rsp+88h+var_28], r15
0x14000b483  call    Smb2GenerateHashHandleForOutgoingSignature
0x14000b488  mov     esi, eax
0x14000b48a  test    eax, eax
0x14000b48c  js      loc_14000B5D0
0x14000b492  mov     rbx, [rdi+60h]
0x14000b496  lea     r14, [rdi+318h]
0x14000b49d  mov     ebp, [rdi+2D8h]
0x14000b4a3  test    rbx, rbx
0x14000b4a6  jz      short loc_14000B506
0x14000b4a8  lea     r14, [rdi+318h]
0x14000b4af  test    ebp, ebp
0x14000b4b1  jz      short loc_14000B506
0x14000b4b3  test    byte ptr [rbx+0Ah], 5
0x14000b4b7  jz      loc_14000B572
0x14000b4bd  mov     rax, [rbx+18h]
0x14000b4c1  test    rax, rax
0x14000b4c4  jz      loc_14000B70A
0x14000b4ca  mov     r15d, [rbx+28h]
0x14000b4ce  lea     r14, [rdi+318h]
0x14000b4d5  mov     rcx, [r14]; hHash
0x14000b4d8  cmp     r15d, ebp
0x14000b4db  mov     rdx, rax; pbInput
0x14000b4de  cmovnb  r15d, ebp
0x14000b4e2  xor     r9d, r9d; dwFlags
0x14000b4e5  mov     r8d, r15d; cbInput
0x14000b4e8  call    cs:__imp_BCryptHashData
0x14000b4ef  nop     dword ptr [rax+rax+00h]
0x14000b4f4  mov     esi, eax
0x14000b4f6  test    eax, eax
0x14000b4f8  js      loc_14000B639
0x14000b4fe  mov     rbx, [rbx]
0x14000b501  sub     ebp, r15d
0x14000b504  jmp     short loc_14000B4A3
0x14000b506  mov     r8d, [rdi+320h]; cbOutput
0x14000b50d  lea     rdx, [rsp+88h+pbOutput]; pbOutput
0x14000b512  mov     rcx, [r14]; hHash
0x14000b515  xor     r9d, r9d; dwFlags
0x14000b518  call    cs:__imp_BCryptFinishHash
0x14000b51f  nop     dword ptr [rax+rax+00h]
0x14000b524  mov     esi, eax
0x14000b526  test    eax, eax
0x14000b528  js      loc_14000B71B
0x14000b52e  movups  xmm0, xmmword ptr [rsp+88h+pbOutput]
0x14000b533  movups  xmmword ptr [r12+30h], xmm0
0x14000b539  mov     r14, [rsp+88h+var_20]
0x14000b53e  mov     r13, [rsp+88h+arg_18]
0x14000b546  mov     rsi, [rsp+88h+arg_10]
0x14000b54e  mov     r15, [rsp+88h+var_28]
0x14000b553  mov     rbx, [rsp+88h+arg_8]
0x14000b55b  mov     rcx, [rsp+88h+var_38]
0x14000b560  xor     rcx, rsp; StackCookie
0x14000b563  call    __security_check_cookie
0x14000b568  add     rsp, 70h
0x14000b56c  pop     r12
0x14000b56e  pop     rdi
0x14000b56f  pop     rbp
0x14000b570  retn
0x14000b572  mov     [rsp+88h+Priority], 40000010h; Priority
0x14000b57a  xor     r9d, r9d; RequestedAddress
0x14000b57d  xor     edx, edx; AccessMode
0x14000b57f  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000b587  mov     r8d, 1; CacheType
0x14000b58d  mov     rcx, rbx; MemoryDescriptorList
0x14000b590  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000b597  nop     dword ptr [rax+rax+00h]
0x14000b59c  jmp     loc_14000B4C1
0x14000b5a1  mov     [rsp+88h+Priority], 40000010h; Priority
0x14000b5a9  xor     r9d, r9d; RequestedAddress
0x14000b5ac  xor     edx, edx; AccessMode
0x14000b5ae  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000b5b6  mov     r8d, 1; CacheType
0x14000b5bc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000b5c3  nop     dword ptr [rax+rax+00h]
0x14000b5c8  mov     r12, rax
0x14000b5cb  jmp     loc_14000B44E
0x14000b5d0  mov     rax, cs:WPP_GLOBAL_Control
0x14000b5d7  lea     rbx, WPP_GLOBAL_Control
0x14000b5de  cmp     rax, rbx
0x14000b5e1  jnz     loc_14000B6D3
0x14000b5e7  mov     rcx, rdi
0x14000b5ea  call    cs:__imp_SmbCseDestroyHashHandle
0x14000b5f1  nop     dword ptr [rax+rax+00h]
0x14000b5f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5fd  cmp     rcx, rbx
0x14000b600  jz      loc_140039705
0x14000b606  mov     eax, [rcx+2Ch]
0x14000b609  test    al, 1
0x14000b60b  jz      loc_140039705
0x14000b611  cmp     byte ptr [rcx+29h], 1
0x14000b615  jb      loc_140039705
0x14000b61b  mov     rcx, [rcx+18h]
0x14000b61f  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14000b626  mov     edx, 14h
0x14000b62b  mov     r9d, esi
0x14000b62e  call    WPP_SF_d
0x14000b633  nop
0x14000b634  jmp     loc_140039705
0x14000b639  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b640  lea     rbx, WPP_GLOBAL_Control
0x14000b647  cmp     rcx, rbx
0x14000b64a  jz      short loc_14000B5E7
0x14000b64c  mov     eax, [rcx+2Ch]
0x14000b64f  test    al, 1
0x14000b651  jz      short loc_14000B5E7
0x14000b653  cmp     byte ptr [rcx+29h], 1
0x14000b657  jb      short loc_14000B5E7
0x14000b659  mov     edx, 12h
0x14000b65e  jmp     loc_1400396E6
0x14000b663  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b66a  lea     rbx, WPP_GLOBAL_Control
0x14000b671  cmp     rcx, rbx
0x14000b674  jnz     short loc_14000B6AC
0x14000b676  xor     eax, eax
0x14000b678  jmp     loc_14000B553
0x14000b67d  mov     rcx, [rdi+38h]
0x14000b681  mov     rdx, [rcx+60h]
0x14000b685  mov     rcx, [rdx+188h]
0x14000b68c  mov     eax, [rcx+140h]
0x14000b692  lea     ecx, [rax-1]
0x14000b695  test    ecx, 0FFFFFFFCh
0x14000b69b  jnz     loc_14000B463
0x14000b6a1  cmp     eax, 3
0x14000b6a4  jz      loc_14000B463
0x14000b6aa  jmp     short loc_14000B663
0x14000b6ac  mov     eax, [rcx+2Ch]
0x14000b6af  test    al, 8
0x14000b6b1  jz      short loc_14000B676
0x14000b6b3  cmp     byte ptr [rcx+29h], 4
0x14000b6b7  jb      short loc_14000B676
0x14000b6b9  mov     rcx, [rcx+18h]
0x14000b6bd  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14000b6c4  mov     edx, 10h
0x14000b6c9  mov     r9, rbp
0x14000b6cc  call    WPP_SF_q
0x14000b6d1  jmp     short loc_14000B676
0x14000b6d3  mov     ecx, [rax+2Ch]
0x14000b6d6  test    cl, 8
0x14000b6d9  jz      loc_14000B5E7
0x14000b6df  cmp     byte ptr [rax+29h], 4
0x14000b6e3  jb      loc_14000B5E7
0x14000b6e9  mov     rcx, [rax+18h]
0x14000b6ed  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14000b6f4  mov     edx, 11h
0x14000b6f9  mov     [rsp+88h+BugCheckOnFailure], esi
0x14000b6fd  mov     r9, rbp
0x14000b700  call    WPP_SF_qD
0x14000b705  jmp     loc_14000B5E7
0x14000b70a  mov     esi, 0C000009Ah
0x14000b70f  lea     rbx, WPP_GLOBAL_Control
0x14000b716  jmp     loc_14000B5E7
0x14000b71b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b722  lea     rbx, WPP_GLOBAL_Control
0x14000b729  cmp     rcx, rbx
0x14000b72c  jz      loc_14000B5E7
0x14000b732  mov     eax, [rcx+2Ch]
0x14000b735  test    al, 1
0x14000b737  jz      loc_14000B5E7
0x14000b73d  cmp     byte ptr [rcx+29h], 1
0x14000b741  jb      loc_14000B5E7
0x14000b747  mov     edx, 13h
0x14000b74c  jmp     loc_1400396E6
0x1400396e6  mov     r9, [rdi+38h]
0x1400396ea  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x1400396f1  mov     rcx, [rcx+18h]
0x1400396f5  mov     qword ptr [rsp+88h+BugCheckOnFailure], rdi
0x1400396fa  call    WPP_SF_qq
0x1400396ff  nop
0x140039700  jmp     loc_14000B5E7
0x140039705  mov     eax, esi
0x140039707  jmp     loc_14000B539
```
