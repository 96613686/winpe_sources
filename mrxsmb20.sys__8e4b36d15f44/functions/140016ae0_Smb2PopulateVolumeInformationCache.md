# Smb2PopulateVolumeInformationCache

- ea: `0x140016ae0`
- end: `0x140016c17`
- name: `Smb2PopulateVolumeInformationCache`
- size: `311`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400166f0`

## callees

- `0x140016ae0`

## import_xrefs

- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140016b2e`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140016bcd`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140016b2e`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140016bcd`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140016bbe`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140016bbe`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140016b08`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140016b08`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140016b92`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140016b92`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016bee`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016c06`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016bee`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140016c06`
- `mrxsmb!SmbCeInitiateExchange` at `0x140016bad`
- `mrxsmb!SmbCeInitiateExchange` at `0x140016bad`
- `mrxsmb!SmbCeInitializeExchange` at `0x140016b72`
- `mrxsmb!SmbCeInitializeExchange` at `0x140016b72`

## pseudocode

```c
__int64 __fastcall Smb2PopulateVolumeInformationCache(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  __int64 CompoundingKey; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  __int64 v8; // [rsp+78h] [rbp+10h] BYREF

  v8 = a2;
  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  v8 = 0;
  CompoundingKey = SmbCseAllocateCompoundingKey(32);
  if ( !CompoundingKey )
    return 3221225626LL;
  v6 = SmbCeInitializeExchange(&v8, a1, 0, 0, 0, v3, 5664, &PopulateVolInfoCacheDispatch);
  if ( v6 )
  {
    SmbCseDereferenceCompoundingKey(CompoundingKey);
    return v6;
  }
  else
  {
    SmbCeAssociateExchangeWithCompoundingKeyEx(v8, CompoundingKey, 0xFFFF);
    _InterlockedOr((volatile signed __int32 *)(v8 + 68), 1u);
    v7 = SmbCeInitiateExchange(v8);
    SmbCseReleaseCompoundingKey(CompoundingKey);
    SmbCseDereferenceCompoundingKey(CompoundingKey);
    if ( v7 == 259 )
    {
      return SmbCeWaitForCompletionAndFinalizeExchangeEx(v8, 0, 0, 0);
    }
    else
    {
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v8, 0, 0, 0);
      return v7;
    }
  }
}

```

## disassembly

```asm
0x140016ae0  mov     [rsp+arg_8], rdx
0x140016ae5  push    rbx
0x140016ae6  push    rbp
0x140016ae7  push    rsi
0x140016ae8  push    rdi
0x140016ae9  sub     rsp, 48h
0x140016aed  mov     rax, [rcx+48h]
0x140016af1  mov     rbx, rcx
0x140016af4  xor     ebp, ebp
0x140016af6  mov     rcx, [rax+28h]
0x140016afa  mov     rsi, [rcx+28h]
0x140016afe  mov     ecx, 20h ; ' '
0x140016b03  mov     [rsp+68h+arg_8], rbp
0x140016b08  call    cs:__imp_SmbCseAllocateCompoundingKey
0x140016b0f  nop     dword ptr [rax+rax+00h]
0x140016b14  mov     rdi, rax
0x140016b17  test    rax, rax
0x140016b1a  jnz     short loc_140016B46
0x140016b1c  mov     eax, 0C000009Ah
0x140016b21  add     rsp, 48h
0x140016b25  pop     rdi
0x140016b26  pop     rsi
0x140016b27  pop     rbp
0x140016b28  pop     rbx
0x140016b29  retn
0x140016b2b  mov     rcx, rdi
0x140016b2e  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x140016b35  nop     dword ptr [rax+rax+00h]
0x140016b3a  mov     eax, ebx
0x140016b3c  add     rsp, 48h
0x140016b40  pop     rdi
0x140016b41  pop     rsi
0x140016b42  pop     rbp
0x140016b43  pop     rbx
0x140016b44  retn
0x140016b46  lea     rax, PopulateVolInfoCacheDispatch
0x140016b4d  xor     r9d, r9d
0x140016b50  mov     [rsp+68h+var_30], rax
0x140016b55  lea     rcx, [rsp+68h+arg_8]
0x140016b5a  mov     [rsp+68h+var_38], 1620h
0x140016b62  xor     r8d, r8d
0x140016b65  mov     [rsp+68h+var_40], rsi
0x140016b6a  mov     rdx, rbx
0x140016b6d  mov     [rsp+68h+var_48], rbp
0x140016b72  call    cs:__imp_SmbCeInitializeExchange
0x140016b79  nop     dword ptr [rax+rax+00h]
0x140016b7e  mov     ebx, eax
0x140016b80  test    eax, eax
0x140016b82  jnz     short loc_140016B2B
0x140016b84  mov     rcx, [rsp+68h+arg_8]
0x140016b89  mov     r8d, 0FFFFh
0x140016b8f  mov     rdx, rdi
0x140016b92  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x140016b99  nop     dword ptr [rax+rax+00h]
0x140016b9e  mov     rax, [rsp+68h+arg_8]
0x140016ba3  lock or dword ptr [rax+44h], 1
0x140016ba8  mov     rcx, [rsp+68h+arg_8]
0x140016bad  call    cs:__imp_SmbCeInitiateExchange
0x140016bb4  nop     dword ptr [rax+rax+00h]
0x140016bb9  mov     rcx, rdi
0x140016bbc  mov     ebx, eax
0x140016bbe  call    cs:__imp_SmbCseReleaseCompoundingKey
0x140016bc5  nop     dword ptr [rax+rax+00h]
0x140016bca  mov     rcx, rdi
0x140016bcd  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x140016bd4  nop     dword ptr [rax+rax+00h]
0x140016bd9  mov     rcx, [rsp+68h+arg_8]
0x140016bde  xor     r9d, r9d
0x140016be1  xor     r8d, r8d
0x140016be4  xor     edx, edx
0x140016be6  cmp     ebx, 103h
0x140016bec  jz      short loc_140016C06
0x140016bee  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140016bf5  nop     dword ptr [rax+rax+00h]
0x140016bfa  mov     eax, ebx
0x140016bfc  add     rsp, 48h
0x140016c00  pop     rdi
0x140016c01  pop     rsi
0x140016c02  pop     rbp
0x140016c03  pop     rbx
0x140016c04  retn
0x140016c06  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140016c0d  nop     dword ptr [rax+rax+00h]
0x140016c12  jmp     loc_140016B3C
```
