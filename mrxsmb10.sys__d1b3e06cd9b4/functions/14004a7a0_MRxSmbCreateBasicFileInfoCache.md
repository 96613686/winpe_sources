# MRxSmbCreateBasicFileInfoCache

- ea: `0x14004a7a0`
- end: `0x14004a921`
- name: `MRxSmbCreateBasicFileInfoCache`
- size: `385`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140048b30`
- `0x1400499e0`
- `0x14004a750`

## callees

- `0x14004a7a0`
- `0x14004a990`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004a8ca`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004a8ca`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004a83a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004a83a`
- `rdbss!RxNameCacheActivateEntry` at `0x14004a8b7`
- `rdbss!RxNameCacheActivateEntry` at `0x14004a8b7`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14004a8ff`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14004a8ff`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004a856`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004a856`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004a7f9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004a89b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004a7f9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004a89b`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14004a88a`

## pseudocode

```c
void __fastcall MRxSmbCreateBasicFileInfoCache(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v8; // r15
  __int64 v9; // rax
  struct _NAME_CACHE_CONTROL_ *v10; // rsi
  __int64 Entry; // rbx
  __int64 v12; // r9
  __int64 v13; // rax
  ULONG v14; // edi
  __int64 ConfigurationBlock; // rax

  if ( MRxSmbInfoCacheLevel )
  {
    if ( !*(_BYTE *)(a3 + 505) )
    {
      v8 = *(_QWORD *)(a1 + 56);
      if ( MRxSmbInfoCacheLevel != 1 || !(unsigned __int8)MRxSmbIsLongFileName() || *(_DWORD *)(a3 + 416) == 4 )
      {
        if ( *(_DWORD *)(MRxSmbGetConfigurationBlock() + 144) )
        {
          if ( *(_BYTE *)(a1 + 32) )
            v9 = *(_QWORD *)(v8 + 120);
          else
            v9 = *(_QWORD *)(a1 + 648);
          v10 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v9 + 40) + 288LL);
          ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
          Entry = RxNameCacheFetchEntryEx(v10, v8 + 360, 0, 0);
          if ( Entry || (LOBYTE(v12) = 1, (Entry = RxNameCacheCreateEntryEx(v10, v8 + 360, 0, v12)) != 0) )
          {
            v13 = *(_QWORD *)(Entry + 40);
            *(_OWORD *)v13 = *(_OWORD *)a2;
            *(_OWORD *)(v13 + 16) = *(_OWORD *)(a2 + 16);
            *(_QWORD *)(v13 + 32) = *(_QWORD *)(a2 + 32);
            *(_DWORD *)(Entry + 48) = a4;
            v14 = *(_DWORD *)(MRxSmbLegacyPerfCtrs + 8LL);
            ConfigurationBlock = MRxSmbGetConfigurationBlock();
            RxNameCacheActivateEntry(v10, (PNAME_CACHE)Entry, *(_DWORD *)(ConfigurationBlock + 144), v14);
          }
          ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14004a7a0  mov     [rsp+arg_10], rbx
0x14004a7a5  push    rsi
0x14004a7a6  push    rdi
0x14004a7a7  push    r14
0x14004a7a9  sub     rsp, 20h
0x14004a7ad  mov     eax, cs:MRxSmbInfoCacheLevel
0x14004a7b3  mov     r14d, r9d
0x14004a7b6  mov     rsi, r8
0x14004a7b9  mov     rdi, rdx
0x14004a7bc  mov     rbx, rcx
0x14004a7bf  test    eax, eax
0x14004a7c1  jz      loc_14004A8E0
0x14004a7c7  cmp     byte ptr [r8+1F9h], 0
0x14004a7cf  jnz     loc_14004A8E0
0x14004a7d5  mov     [rsp+38h+arg_8], r15
0x14004a7da  mov     r15, [rcx+38h]
0x14004a7de  cmp     eax, 1
0x14004a7e1  jnz     short loc_14004A7F9
0x14004a7e3  call    MRxSmbIsLongFileName
0x14004a7e8  test    al, al
0x14004a7ea  jz      short loc_14004A7F9
0x14004a7ec  cmp     dword ptr [rsi+1A0h], 4
0x14004a7f3  jnz     loc_14004A8DB
0x14004a7f9  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14004a800  nop     dword ptr [rax+rax+00h]
0x14004a805  cmp     dword ptr [rax+90h], 0
0x14004a80c  jz      loc_14004A8DB
0x14004a812  cmp     byte ptr [rbx+20h], 0
0x14004a816  mov     [rsp+38h+arg_0], rbp
0x14004a81b  jnz     loc_14004A918
0x14004a821  mov     rax, [rbx+288h]
0x14004a828  mov     rsi, [rax+28h]
0x14004a82c  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004a833  add     rsi, 120h
0x14004a83a  call    cs:__imp_ExAcquireFastMutex
0x14004a841  nop     dword ptr [rax+rax+00h]
0x14004a846  xor     r9d, r9d
0x14004a849  lea     rdx, [r15+168h]
0x14004a850  xor     r8d, r8d
0x14004a853  mov     rcx, rsi
0x14004a856  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004a85d  nop     dword ptr [rax+rax+00h]
0x14004a862  mov     rbx, rax
0x14004a865  test    rax, rax
0x14004a868  jz      loc_14004A8EF
0x14004a86e  movups  xmm0, xmmword ptr [rdi]
0x14004a871  mov     rax, [rbx+28h]
0x14004a875  movups  xmmword ptr [rax], xmm0
0x14004a878  movups  xmm1, xmmword ptr [rdi+10h]
0x14004a87c  movups  xmmword ptr [rax+10h], xmm1
0x14004a880  movsd   xmm0, qword ptr [rdi+20h]
0x14004a885  movsd   qword ptr [rax+20h], xmm0
0x14004a88a  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14004a891  mov     [rbx+30h], r14d
0x14004a895  mov     rdx, [rax]
0x14004a898  mov     edi, [rdx+8]
0x14004a89b  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14004a8a2  nop     dword ptr [rax+rax+00h]
0x14004a8a7  mov     r9d, edi; MRxContext
0x14004a8aa  mov     rdx, rbx; NameCache
0x14004a8ad  mov     rcx, rsi; NameCacheCtl
0x14004a8b0  mov     r8d, [rax+90h]; LifeTime
0x14004a8b7  call    cs:__imp_RxNameCacheActivateEntry
0x14004a8be  nop     dword ptr [rax+rax+00h]
0x14004a8c3  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004a8ca  call    cs:__imp_ExReleaseFastMutex
0x14004a8d1  nop     dword ptr [rax+rax+00h]
0x14004a8d6  mov     rbp, [rsp+38h+arg_0]
0x14004a8db  mov     r15, [rsp+38h+arg_8]
0x14004a8e0  mov     rbx, [rsp+38h+arg_10]
0x14004a8e5  add     rsp, 20h
0x14004a8e9  pop     r14
0x14004a8eb  pop     rdi
0x14004a8ec  pop     rsi
0x14004a8ed  retn
0x14004a8ef  mov     r9b, 1
0x14004a8f2  lea     rdx, [r15+168h]
0x14004a8f9  xor     r8d, r8d
0x14004a8fc  mov     rcx, rsi
0x14004a8ff  call    cs:__imp_RxNameCacheCreateEntryEx
0x14004a906  nop     dword ptr [rax+rax+00h]
0x14004a90b  mov     rbx, rax
0x14004a90e  test    rax, rax
0x14004a911  jz      short loc_14004A8C3
0x14004a913  jmp     loc_14004A86E
0x14004a918  mov     rax, [r15+78h]
0x14004a91c  jmp     loc_14004A828
```
