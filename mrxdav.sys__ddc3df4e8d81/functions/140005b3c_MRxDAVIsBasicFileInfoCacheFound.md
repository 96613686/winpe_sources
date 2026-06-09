# MRxDAVIsBasicFileInfoCacheFound

- ea: `0x140005b3c`
- end: `0x140005ce0`
- name: `MRxDAVIsBasicFileInfoCacheFound`
- size: `420`
- prototype: `char __fastcall(__int64, __int64, _DWORD *, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400130e0`
- `0x14001e6a0`
- `0x140025a08`

## callees

- `0x1400027ac`
- `0x140005b3c`
- `0x140005ee8`
- `0x140005f88`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140005b87`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005b87`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005cc3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005cc3`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005b9f`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005b9f`
- `rdbss!RxNameCacheActivateEntry` at `0x140005c07`
- `rdbss!RxNameCacheActivateEntry` at `0x140005c07`
- `rdbss!RxNameCacheExpireEntry` at `0x140005c7c`
- `rdbss!RxNameCacheExpireEntry` at `0x140005c7c`
- `rdbss!RxNameCacheCheckEntry` at `0x140005bbd`
- `rdbss!RxNameCacheCheckEntry` at `0x140005bbd`

## pseudocode

```c
char __fastcall MRxDAVIsBasicFileInfoCacheFound(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  __int64 v4; // rax
  char v5; // r14
  __int64 v6; // rbx
  __int64 v9; // rax
  struct _NAME_CACHE_CONTROL_ *v10; // rbp
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v12; // rdi
  int Blink; // ecx
  struct _LIST_ENTRY *Flink; // rax
  int v15; // r8d

  v4 = *(_QWORD *)(a1 + 56);
  v5 = 0;
  v6 = a4;
  if ( !a4 )
    v6 = v4 + 360;
  if ( *(_BYTE *)(a1 + 32) )
    v9 = *(_QWORD *)(v4 + 120);
  else
    v9 = *(_QWORD *)(a1 + 648);
  v10 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v9 + 40) + 16LL);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v10, v6, 0, 0);
  v12 = Entry;
  if ( Entry )
  {
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) )
    {
      RxNameCacheExpireEntry(v10, v12);
    }
    else
    {
      Blink = (int)v12->Link.Blink;
      v5 = 1;
      ++v10->Spare[0];
      Flink = v12->Link.Flink;
      *a3 = Blink;
      *(struct _LIST_ENTRY *)a2 = *Flink;
      *(struct _LIST_ENTRY *)(a2 + 16) = Flink[1];
      *(_QWORD *)(a2 + 32) = Flink[2].Flink;
      RxNameCacheActivateEntry(v10, v12, 0, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
          WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 3), 24, v15, *(_DWORD *)(a2 + 32), v6);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
        {
          WPP_SF_ddZ(*((_QWORD *)WPP_GLOBAL_Control + 3), 25, v15, *(_DWORD *)a2, *(_DWORD *)(a2 + 8), v6);
        }
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 3), 26, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids, v6);
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
  return v5;
}

```

## disassembly

```asm
0x140005b3c  push    rbx
0x140005b3e  push    rbp
0x140005b3f  push    rsi
0x140005b40  push    rdi
0x140005b41  push    r14
0x140005b43  push    r15
0x140005b45  sub     rsp, 38h
0x140005b49  mov     rax, [rcx+38h]
0x140005b4d  xor     r14b, r14b
0x140005b50  mov     rbx, r9
0x140005b53  mov     r15, r8
0x140005b56  mov     rsi, rdx
0x140005b59  test    r9, r9
0x140005b5c  jnz     short loc_140005B65
0x140005b5e  lea     rbx, [rax+168h]
0x140005b65  cmp     [rcx+20h], r14b
0x140005b69  jnz     short loc_140005B74
0x140005b6b  mov     rax, [rcx+288h]
0x140005b72  jmp     short loc_140005B78
0x140005b74  mov     rax, [rax+78h]
0x140005b78  mov     rbp, [rax+28h]
0x140005b7c  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140005b83  add     rbp, 10h
0x140005b87  call    cs:__imp_ExAcquireFastMutex
0x140005b8e  nop     dword ptr [rax+rax+00h]
0x140005b93  xor     r9d, r9d
0x140005b96  xor     r8d, r8d
0x140005b99  mov     rdx, rbx
0x140005b9c  mov     rcx, rbp
0x140005b9f  call    cs:__imp_RxNameCacheFetchEntryEx
0x140005ba6  nop     dword ptr [rax+rax+00h]
0x140005bab  mov     rdi, rax
0x140005bae  test    rax, rax
0x140005bb1  jz      loc_140005C8A
0x140005bb7  mov     edx, [rax+20h]; MRxContext
0x140005bba  mov     rcx, rax; NameCache
0x140005bbd  call    cs:__imp_RxNameCacheCheckEntry
0x140005bc4  nop     dword ptr [rax+rax+00h]
0x140005bc9  mov     rdx, rdi; NameCache
0x140005bcc  test    eax, eax
0x140005bce  jnz     loc_140005C79
0x140005bd4  mov     ecx, [rdi+30h]
0x140005bd7  lea     r14d, [rax+1]
0x140005bdb  add     [rbp+74h], r14d
0x140005bdf  xor     r9d, r9d; MRxContext
0x140005be2  mov     rax, [rdi+28h]
0x140005be6  xor     r8d, r8d; LifeTime
0x140005be9  mov     [r15], ecx
0x140005bec  mov     rcx, rbp; NameCacheCtl
0x140005bef  movups  xmm0, xmmword ptr [rax]
0x140005bf2  movups  xmmword ptr [rsi], xmm0
0x140005bf5  movups  xmm1, xmmword ptr [rax+10h]
0x140005bf9  movups  xmmword ptr [rsi+10h], xmm1
0x140005bfd  movsd   xmm0, qword ptr [rax+20h]
0x140005c02  movsd   qword ptr [rsi+20h], xmm0
0x140005c07  call    cs:__imp_RxNameCacheActivateEntry
0x140005c0e  nop     dword ptr [rax+rax+00h]
0x140005c13  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c1a  lea     rbp, WPP_GLOBAL_Control
0x140005c21  cmp     rcx, rbp
0x140005c24  jz      loc_140005CBC
0x140005c2a  bt      dword ptr [rcx+2Ch], 0Dh
0x140005c2f  jnb     short loc_140005C47
0x140005c31  mov     r9d, [rsi+20h]
0x140005c35  lea     edx, [r14+17h]
0x140005c39  mov     rcx, [rcx+18h]
0x140005c3d  mov     [rsp+68h+var_48], rbx
0x140005c42  call    WPP_SF_DZ
0x140005c47  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c4e  cmp     rcx, rbp
0x140005c51  jz      short loc_140005CBC
0x140005c53  bt      dword ptr [rcx+2Ch], 0Dh
0x140005c58  jnb     short loc_140005CBC
0x140005c5a  mov     eax, [rsi+8]
0x140005c5d  mov     edx, 19h
0x140005c62  mov     r9d, [rsi]
0x140005c65  mov     rcx, [rcx+18h]
0x140005c69  mov     [rsp+68h+var_40], rbx
0x140005c6e  mov     dword ptr [rsp+68h+var_48], eax
0x140005c72  call    WPP_SF_ddZ
0x140005c77  jmp     short loc_140005CBC
0x140005c79  mov     rcx, rbp; NameCacheCtl
0x140005c7c  call    cs:__imp_RxNameCacheExpireEntry
0x140005c83  nop     dword ptr [rax+rax+00h]
0x140005c88  jmp     short loc_140005CBC
0x140005c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c91  lea     rbp, WPP_GLOBAL_Control
0x140005c98  cmp     rcx, rbp
0x140005c9b  jz      short loc_140005CBC
0x140005c9d  bt      dword ptr [rcx+2Ch], 0Dh
0x140005ca2  jnb     short loc_140005CBC
0x140005ca4  mov     rcx, [rcx+18h]
0x140005ca8  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140005caf  mov     edx, 1Ah
0x140005cb4  mov     r9, rbx
0x140005cb7  call    WPP_SF_Z
0x140005cbc  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140005cc3  call    cs:__imp_ExReleaseFastMutex
0x140005cca  nop     dword ptr [rax+rax+00h]
0x140005ccf  mov     al, r14b
0x140005cd2  add     rsp, 38h
0x140005cd6  pop     r15
0x140005cd8  pop     r14
0x140005cda  pop     rdi
0x140005cdb  pop     rsi
0x140005cdc  pop     rbp
0x140005cdd  pop     rbx
0x140005cde  retn
```
