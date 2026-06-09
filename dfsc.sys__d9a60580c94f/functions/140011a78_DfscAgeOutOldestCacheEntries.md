# DfscAgeOutOldestCacheEntries

- ea: `0x140011a78`
- end: `0x140011b72`
- name: `DfscAgeOutOldestCacheEntries`
- size: `250`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14001c310`

## callees

- `0x1400026a4`
- `0x140011a78`
- `0x1400199e4`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011b58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011b58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011b4c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011b4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140011a9e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140011a9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011a86`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011a86`

## pseudocode

```c
__int64 __fastcall DfscAgeOutOldestCacheEntries(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rsi
  unsigned int v4; // ebp
  __int64 v5; // rbx

  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 160), 1u);
  v2 = *(_DWORD *)(a1 + 52);
  if ( v2 )
  {
    v3 = *(_QWORD *)(a1 + 32);
    v4 = 0;
    do
    {
      if ( *(_DWORD *)(a1 + 48) <= v2 || v4 >= dword_14000C768 || v3 == *(_QWORD *)(a1 + 24) )
        break;
      v5 = v3 - 48;
      v3 = *(_QWORD *)(v3 + 8);
      if ( (*(_BYTE *)(v5 + 12) & 1) != 0 && *(int *)(v5 + 4) <= 1 && *(_BYTE *)(v5 + 16) != 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            (unsigned int)WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids,
            v5,
            v5 + 144);
        }
        ++v4;
        DfscRmUnlinkReferral(v5);
        DfscRmDereferenceReferral((volatile signed __int32 *)v5);
      }
      v2 = *(_DWORD *)(a1 + 52);
    }
    while ( v2 );
  }
  ExReleaseResourceLite((PERESOURCE)(a1 + 160));
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x140011a78  push    rbx
0x140011a7a  push    rbp
0x140011a7b  push    rsi
0x140011a7c  push    rdi
0x140011a7d  push    r14
0x140011a7f  sub     rsp, 30h
0x140011a83  mov     rdi, rcx
0x140011a86  call    cs:__imp_KeEnterCriticalRegion
0x140011a8d  nop     dword ptr [rax+rax+00h]
0x140011a92  lea     r14, [rdi+0A0h]
0x140011a99  mov     dl, 1; Wait
0x140011a9b  mov     rcx, r14; Resource
0x140011a9e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140011aa5  nop     dword ptr [rax+rax+00h]
0x140011aaa  mov     eax, [rdi+34h]
0x140011aad  test    eax, eax
0x140011aaf  jz      loc_140011B49
0x140011ab5  mov     rsi, [rdi+20h]
0x140011ab9  xor     ebp, ebp
0x140011abb  cmp     [rdi+30h], eax
0x140011abe  jbe     loc_140011B49
0x140011ac4  cmp     ebp, cs:dword_14000C768
0x140011aca  jnb     short loc_140011B49
0x140011acc  cmp     rsi, [rdi+18h]
0x140011ad0  jz      short loc_140011B49
0x140011ad2  lea     rbx, [rsi-30h]
0x140011ad6  mov     rsi, [rsi+8]
0x140011ada  test    byte ptr [rbx+0Ch], 1
0x140011ade  jz      short loc_140011B3E
0x140011ae0  cmp     dword ptr [rbx+4], 1
0x140011ae4  jg      short loc_140011B3E
0x140011ae6  cmp     byte ptr [rbx+10h], 1
0x140011aea  jz      short loc_140011B3E
0x140011aec  mov     rcx, cs:WPP_GLOBAL_Control
0x140011af3  lea     rax, WPP_GLOBAL_Control
0x140011afa  cmp     rcx, rax
0x140011afd  jz      short loc_140011B2C
0x140011aff  test    dword ptr [rcx+2Ch], 400000h
0x140011b06  jz      short loc_140011B2C
0x140011b08  mov     rcx, [rcx+18h]
0x140011b0c  lea     rax, [rbx+90h]
0x140011b13  mov     edx, 1Fh
0x140011b18  mov     [rsp+58h+var_38], rax
0x140011b1d  mov     r9, rbx
0x140011b20  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x140011b27  call    WPP_SF_qZ
0x140011b2c  mov     rcx, rbx
0x140011b2f  inc     ebp
0x140011b31  call    DfscRmUnlinkReferral
0x140011b36  mov     rcx, rbx; P
0x140011b39  call    DfscRmDereferenceReferral
0x140011b3e  mov     eax, [rdi+34h]
0x140011b41  test    eax, eax
0x140011b43  jnz     loc_140011ABB
0x140011b49  mov     rcx, r14; Resource
0x140011b4c  call    cs:__imp_ExReleaseResourceLite
0x140011b53  nop     dword ptr [rax+rax+00h]
0x140011b58  call    cs:__imp_KeLeaveCriticalRegion
0x140011b5f  nop     dword ptr [rax+rax+00h]
0x140011b64  xor     eax, eax
0x140011b66  add     rsp, 30h
0x140011b6a  pop     r14
0x140011b6c  pop     rdi
0x140011b6d  pop     rsi
0x140011b6e  pop     rbp
0x140011b6f  pop     rbx
0x140011b70  retn
```
