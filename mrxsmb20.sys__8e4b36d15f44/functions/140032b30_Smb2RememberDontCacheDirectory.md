# Smb2RememberDontCacheDirectory

- ea: `0x140032b30`
- end: `0x140032c94`
- name: `Smb2RememberDontCacheDirectory`
- size: `356`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140001c70`

## callees

- `0x140010230`
- `0x140032b30`
- `0x140032dbc`
- `0x140037120`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140032c5f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140032c5f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140032b9f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140032b9f`
- `rdbss!RxNameCacheActivateEntry` at `0x140032c4a`
- `rdbss!RxNameCacheActivateEntry` at `0x140032c4a`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140032c23`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140032c23`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140032c04`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140032c04`

## pseudocode

```c
__int64 __fastcall Smb2RememberDontCacheDirectory(__int64 a1)
{
  __int64 v1; // rdi
  struct _NAME_CACHE_CONTROL_ *v2; // rbx
  __int64 v3; // rsi
  int v4; // r8d
  __int64 Entry; // rax
  __int64 v6; // r9
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-B8h] BYREF
  char v9; // [rsp+50h] [rbp-A8h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v2 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(a1 + 80) + 2416LL);
  v3 = *(_QWORD *)(v1 + 136);
  *(_QWORD *)&Destination.Length = 0x800000;
  Destination.Buffer = (PWSTR)&v9;
  Smb2GenerateFileIdString(&Destination, (ULONGLONG *)(v3 + 24), 0);
  ExAcquirePushLockExclusiveEx(&Smb2GlobalFilePropertyCacheLock, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Ziiq(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      v4,
      v1 + 360,
      *(_QWORD *)(v3 + 32),
      *(_QWORD *)(v3 + 24),
      (char)v2);
  }
  Entry = RxNameCacheFetchEntryEx(v2, &Destination, 0, 0);
  if ( Entry || (LOBYTE(v6) = 1, (Entry = RxNameCacheCreateEntryEx(v2, &Destination, 0, v6)) != 0) )
  {
    *(_DWORD *)(Entry + 48) = -1073741772;
    RxNameCacheActivateEntry(v2, (PNAME_CACHE)Entry, 0xE10u, 0);
  }
  return ExReleasePushLockExclusiveEx(&Smb2GlobalFilePropertyCacheLock, 0);
}

```

## disassembly

```asm
0x140032b30  mov     [rsp+arg_8], rbx
0x140032b35  mov     [rsp+arg_10], rbp
0x140032b3a  push    rsi
0x140032b3b  push    rdi
0x140032b3c  push    r14
0x140032b3e  sub     rsp, 0E0h
0x140032b45  mov     rax, cs:__security_cookie
0x140032b4c  xor     rax, rsp
0x140032b4f  mov     [rsp+0F8h+var_28], rax
0x140032b57  mov     rdi, [rcx+38h]
0x140032b5b  lea     rax, [rsp+0F8h+var_A8]
0x140032b60  mov     rbx, [rcx+50h]
0x140032b64  xor     r8d, r8d
0x140032b67  lea     rcx, [rsp+0F8h+Destination]; Destination
0x140032b6c  add     rbx, 970h
0x140032b73  mov     ebp, 80h
0x140032b78  mov     rsi, [rdi+88h]
0x140032b7f  mov     qword ptr [rsp+0F8h+Destination.Length], 800000h
0x140032b88  mov     [rsp+0F8h+Destination.Buffer], rax
0x140032b8d  lea     rdx, [rsi+18h]
0x140032b91  call    Smb2GenerateFileIdString
0x140032b96  xor     edx, edx
0x140032b98  lea     rcx, Smb2GlobalFilePropertyCacheLock
0x140032b9f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140032ba6  nop     dword ptr [rax+rax+00h]
0x140032bab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140032bb2  lea     rax, WPP_GLOBAL_Control
0x140032bb9  cmp     rcx, rax
0x140032bbc  jz      short loc_140032BF6
0x140032bbe  mov     eax, [rcx+2Ch]
0x140032bc1  test    bpl, al
0x140032bc4  jz      short loc_140032BF6
0x140032bc6  cmp     byte ptr [rcx+29h], 2
0x140032bca  jb      short loc_140032BF6
0x140032bcc  mov     rax, [rsi+18h]
0x140032bd0  lea     r9, [rdi+168h]
0x140032bd7  mov     rcx, [rcx+18h]
0x140032bdb  lea     edx, [rbp-6Fh]
0x140032bde  mov     [rsp+0F8h+var_C8], rbx
0x140032be3  mov     [rsp+0F8h+var_D0], rax
0x140032be8  mov     rax, [rsi+20h]
0x140032bec  mov     [rsp+0F8h+var_D8], rax
0x140032bf1  call    WPP_SF_Ziiq
0x140032bf6  xor     r9d, r9d
0x140032bf9  lea     rdx, [rsp+0F8h+Destination]
0x140032bfe  xor     r8d, r8d
0x140032c01  mov     rcx, rbx
0x140032c04  call    cs:__imp_RxNameCacheFetchEntryEx
0x140032c0b  nop     dword ptr [rax+rax+00h]
0x140032c10  test    rax, rax
0x140032c13  jnz     short loc_140032C34
0x140032c15  mov     r9b, 1
0x140032c18  lea     rdx, [rsp+0F8h+Destination]
0x140032c1d  xor     r8d, r8d
0x140032c20  mov     rcx, rbx
0x140032c23  call    cs:__imp_RxNameCacheCreateEntryEx
0x140032c2a  nop     dword ptr [rax+rax+00h]
0x140032c2f  test    rax, rax
0x140032c32  jz      short loc_140032C56
0x140032c34  xor     r9d, r9d; MRxContext
0x140032c37  mov     dword ptr [rax+30h], 0C0000034h
0x140032c3e  mov     r8d, 0E10h; LifeTime
0x140032c44  mov     rdx, rax; NameCache
0x140032c47  mov     rcx, rbx; NameCacheCtl
0x140032c4a  call    cs:__imp_RxNameCacheActivateEntry
0x140032c51  nop     dword ptr [rax+rax+00h]
0x140032c56  xor     edx, edx
0x140032c58  lea     rcx, Smb2GlobalFilePropertyCacheLock
0x140032c5f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140032c66  nop     dword ptr [rax+rax+00h]
0x140032c6b  mov     rcx, [rsp+0F8h+var_28]
0x140032c73  xor     rcx, rsp; StackCookie
0x140032c76  call    __security_check_cookie
0x140032c7b  lea     r11, [rsp+0F8h+var_18]
0x140032c83  mov     rbx, [r11+28h]
0x140032c87  mov     rbp, [r11+30h]
0x140032c8b  mov     rsp, r11
0x140032c8e  pop     r14
0x140032c90  pop     rdi
0x140032c91  pop     rsi
0x140032c92  retn
```
