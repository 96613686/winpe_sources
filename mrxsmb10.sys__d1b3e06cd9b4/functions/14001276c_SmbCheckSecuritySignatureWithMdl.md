# SmbCheckSecuritySignatureWithMdl

- ea: `0x14001276c`
- end: `0x14001282d`
- name: `SmbCheckSecuritySignatureWithMdl`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008840`
- `0x14000b524`

## callees

- `0x14000fd40`
- `0x14001260c`
- `0x1400126a4`
- `0x14001276c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400127aa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400127aa`

## pseudocode

```c
bool __fastcall SmbCheckSecuritySignatureWithMdl(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  PVOID v8; // rax
  __int64 v9; // r8
  __int64 v11; // rdx

  if ( (*(_BYTE *)(a4 + 10) & 5) != 0 )
    v8 = *(PVOID *)(a4 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)a4, 0, MmCached, 0, 0, 0x40000000u);
  if ( v8 )
  {
    v9 = *(unsigned int *)(a4 + 40);
    if ( (unsigned int)v9 < a3 )
    {
      if ( (int)SmbCheckSecuritySignature(a1, a2, v9, v8) >= 0 )
        return SmbCheckSecuritySignaturePartial(a1, v11, a3 - *(_DWORD *)(a4 + 40), *(__int64 **)a4) != 0;
    }
    else if ( (int)SmbCheckSecuritySignature(a1, a2, a3, v8) >= 0 )
    {
      CngRsa32Compat_MD5Final(a1 + 272);
      *(_BYTE *)(a1 + 255) = 0;
      if ( *(_QWORD *)(a1 + 288) == *(_QWORD *)(a1 + 305) )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001276c  push    rbx
0x14001276e  push    rbp
0x14001276f  push    rsi
0x140012770  push    rdi
0x140012771  sub     rsp, 38h
0x140012775  test    byte ptr [r9+0Ah], 5
0x14001277a  mov     rbx, r9
0x14001277d  mov     esi, r8d
0x140012780  mov     rbp, rdx
0x140012783  mov     rdi, rcx
0x140012786  jz      short loc_14001278E
0x140012788  mov     rax, [r9+18h]
0x14001278c  jmp     short loc_1400127B6
0x14001278e  xor     r9d, r9d; RequestedAddress
0x140012791  mov     [rsp+58h+Priority], 40000000h; Priority
0x140012799  xor     edx, edx; AccessMode
0x14001279b  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400127a3  mov     rcx, rbx; MemoryDescriptorList
0x1400127a6  lea     r8d, [r9+1]; CacheType
0x1400127aa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400127b1  nop     dword ptr [rax+rax+00h]
0x1400127b6  test    rax, rax
0x1400127b9  jz      short loc_140012821
0x1400127bb  mov     r8d, [rbx+28h]
0x1400127bf  mov     r9, rax
0x1400127c2  mov     rdx, rbp
0x1400127c5  mov     rcx, rdi
0x1400127c8  cmp     r8d, esi
0x1400127cb  jb      short loc_140012800
0x1400127cd  mov     r8d, esi
0x1400127d0  call    SmbCheckSecuritySignature
0x1400127d5  test    eax, eax
0x1400127d7  js      short loc_140012821
0x1400127d9  lea     rbx, [rdi+110h]
0x1400127e0  mov     rcx, rbx
0x1400127e3  call    CngRsa32Compat_MD5Final
0x1400127e8  mov     byte ptr [rdi+0FFh], 0
0x1400127ef  mov     rdx, [rbx+10h]
0x1400127f3  cmp     rdx, [rdi+131h]
0x1400127fa  jnz     short loc_140012821
0x1400127fc  mov     al, 1
0x1400127fe  jmp     short loc_140012823
0x140012800  call    SmbCheckSecuritySignature
0x140012805  test    eax, eax
0x140012807  js      short loc_140012821
0x140012809  sub     esi, [rbx+28h]
0x14001280c  mov     rcx, rdi
0x14001280f  mov     r9, [rbx]
0x140012812  mov     r8d, esi
0x140012815  call    SmbCheckSecuritySignaturePartial
0x14001281a  test    al, al
0x14001281c  setnz   al
0x14001281f  jmp     short loc_140012823
0x140012821  xor     al, al
0x140012823  add     rsp, 38h
0x140012827  pop     rdi
0x140012828  pop     rsi
0x140012829  pop     rbp
0x14001282a  pop     rbx
0x14001282b  retn
```
