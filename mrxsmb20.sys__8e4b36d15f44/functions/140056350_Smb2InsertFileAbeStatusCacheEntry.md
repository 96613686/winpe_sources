# Smb2InsertFileAbeStatusCacheEntry

- ea: `0x140056350`
- end: `0x1400564c9`
- name: `Smb2InsertFileAbeStatusCacheEntry`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD *, struct _NAME_CACHE_CONTROL_ *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003840`
- `0x140005820`

## callees

- `0x140010230`
- `0x140037120`
- `0x140056350`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400564a8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400564a8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140056422`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140056422`
- `rdbss!RxNameCacheActivateEntry` at `0x140056493`
- `rdbss!RxNameCacheActivateEntry` at `0x140056493`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140056462`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140056462`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14005643e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14005643e`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14005647a`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14005647a`

## pseudocode

```c
__int64 __fastcall Smb2InsertFileAbeStatusCacheEntry(_QWORD *a1, struct _NAME_CACHE_CONTROL_ *a2)
{
  __int64 v2; // rax
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 result; // rax
  int v8; // edx
  __int64 v9; // rcx
  __int64 v10; // rsi
  ULONG v11; // ebp
  struct _NAME_CACHE *Entry; // rsi
  __int64 v13; // r9
  __int64 InstanceConfigurationBlock; // rax
  __int64 v15; // [rsp+20h] [rbp-148h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+28h] [rbp-140h] BYREF
  _BYTE v17[256]; // [rsp+40h] [rbp-128h] BYREF

  v2 = a1[7];
  v5 = *(_QWORD *)(v2 + 136);
  v6 = *(_QWORD *)(*(_QWORD *)(v2 + 120) + 40LL);
  result = (__int64)v17;
  v8 = *(_DWORD *)(v6 + 184);
  v15 = 0;
  *(_QWORD *)&Destination.Length = 0x1000000;
  Destination.Buffer = (PWSTR)v17;
  if ( (v8 & 0x800) != 0 )
  {
    v9 = a1[9];
    if ( v9 )
    {
      result = *(unsigned int *)(v5 + 8);
      if ( (result & 2) != 0 )
      {
        v10 = *(_QWORD *)(*(_QWORD *)(v9 + 40) + 40LL);
        v15 = *(_QWORD *)(v10 + 96);
        result = Smb2GenerateFileIdString(&Destination);
        if ( (int)result >= 0 )
        {
          v11 = *(_DWORD *)(v10 + 264);
          ExAcquirePushLockExclusiveEx(&Smb2FileAbeStatusCacheLock, 0);
          Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &Destination, &v15, 0);
          if ( Entry
            || (LOBYTE(v13) = 1,
                (Entry = (struct _NAME_CACHE *)RxNameCacheCreateEntryEx(a2, &Destination, &v15, v13)) != 0) )
          {
            InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(a1[10]);
            RxNameCacheActivateEntry(a2, Entry, *(_DWORD *)(InstanceConfigurationBlock + 52), v11);
          }
          return ExReleasePushLockExclusiveEx(&Smb2FileAbeStatusCacheLock, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140056350  push    rbx
0x140056352  push    rdi
0x140056353  sub     rsp, 158h
0x14005635a  mov     rax, cs:__security_cookie
0x140056361  xor     rax, rsp
0x140056364  mov     [rsp+168h+var_28], rax
0x14005636c  mov     rax, [rcx+38h]
0x140056370  mov     rbx, rcx
0x140056373  mov     rdi, rdx
0x140056376  mov     r8, [rax+88h]
0x14005637d  mov     rax, [rax+78h]
0x140056381  mov     rcx, [rax+28h]
0x140056385  lea     rax, [rsp+168h+var_128]
0x14005638a  mov     edx, [rcx+0B8h]
0x140056390  mov     [rsp+168h+var_148], 0
0x140056399  mov     qword ptr [rsp+168h+Destination.Length], 1000000h
0x1400563a2  mov     [rsp+168h+Destination.Buffer], rax
0x1400563a7  bt      edx, 0Bh
0x1400563ab  jb      short loc_1400563C8
0x1400563ad  mov     rcx, [rsp+168h+var_28]
0x1400563b5  xor     rcx, rsp; StackCookie
0x1400563b8  call    __security_check_cookie
0x1400563bd  add     rsp, 158h
0x1400563c4  pop     rdi
0x1400563c5  pop     rbx
0x1400563c6  retn
0x1400563c8  mov     rcx, [rbx+48h]
0x1400563cc  test    rcx, rcx
0x1400563cf  jz      short loc_1400563AD
0x1400563d1  mov     eax, [r8+8]
0x1400563d5  test    al, 2
0x1400563d7  jz      short loc_1400563AD
0x1400563d9  mov     rax, [rcx+28h]
0x1400563dd  lea     rdx, [r8+18h]
0x1400563e1  mov     [rsp+168h+var_18], rsi
0x1400563e9  lea     rcx, [rsp+168h+Destination]; Destination
0x1400563ee  xor     r8d, r8d
0x1400563f1  mov     rsi, [rax+28h]
0x1400563f5  mov     rax, [rsi+60h]
0x1400563f9  mov     [rsp+168h+var_148], rax
0x1400563fe  call    Smb2GenerateFileIdString
0x140056403  test    eax, eax
0x140056405  js      loc_1400564BC
0x14005640b  mov     [rsp+168h+arg_10], rbp
0x140056413  lea     rcx, Smb2FileAbeStatusCacheLock
0x14005641a  mov     ebp, [rsi+108h]
0x140056420  xor     edx, edx
0x140056422  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140056429  nop     dword ptr [rax+rax+00h]
0x14005642e  xor     r9d, r9d
0x140056431  lea     r8, [rsp+168h+var_148]
0x140056436  lea     rdx, [rsp+168h+Destination]
0x14005643b  mov     rcx, rdi
0x14005643e  call    cs:__imp_RxNameCacheFetchEntryEx
0x140056445  nop     dword ptr [rax+rax+00h]
0x14005644a  mov     rsi, rax
0x14005644d  test    rax, rax
0x140056450  jnz     short loc_140056476
0x140056452  mov     r9b, 1
0x140056455  lea     r8, [rsp+168h+var_148]
0x14005645a  lea     rdx, [rsp+168h+Destination]
0x14005645f  mov     rcx, rdi
0x140056462  call    cs:__imp_RxNameCacheCreateEntryEx
0x140056469  nop     dword ptr [rax+rax+00h]
0x14005646e  mov     rsi, rax
0x140056471  test    rax, rax
0x140056474  jz      short loc_14005649F
0x140056476  mov     rcx, [rbx+50h]
0x14005647a  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140056481  nop     dword ptr [rax+rax+00h]
0x140056486  mov     r9d, ebp; MRxContext
0x140056489  mov     rdx, rsi; NameCache
0x14005648c  mov     rcx, rdi; NameCacheCtl
0x14005648f  mov     r8d, [rax+34h]; LifeTime
0x140056493  call    cs:__imp_RxNameCacheActivateEntry
0x14005649a  nop     dword ptr [rax+rax+00h]
0x14005649f  xor     edx, edx
0x1400564a1  lea     rcx, Smb2FileAbeStatusCacheLock
0x1400564a8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400564af  nop     dword ptr [rax+rax+00h]
0x1400564b4  mov     rbp, [rsp+168h+arg_10]
0x1400564bc  mov     rsi, [rsp+168h+var_18]
0x1400564c4  jmp     loc_1400563AD
```
