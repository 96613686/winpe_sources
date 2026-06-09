# RegistryBasedBackupStatusCache::ClearAll(void)

- ea: `0x180015790`
- end: `0x180015818`
- name: `?ClearAll@RegistryBasedBackupStatusCache@@UEBAJXZ`
- size: `136`
- prototype: `__int64 __fastcall(RegistryBasedBackupStatusCache *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800037a0`
- `0x180015790`
- `0x18002d010`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x1800157c1`
- `ADVAPI32!RegDeleteTreeW` at `0x1800157c1`

## pseudocode

```c
__int64 __fastcall RegistryBasedBackupStatusCache::ClearAll(RegistryBasedBackupStatusCache *this)
{
  const WCHAR *v2; // rbx
  HKEY v3; // rax
  LSTATUS v4; // eax
  unsigned int v5; // ebx

  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(RegistryBasedBackupStatusCache *))(*(_QWORD *)this + 32LL))(this);
  v3 = (HKEY)(*(__int64 (__fastcall **)(RegistryBasedBackupStatusCache *))(*(_QWORD *)this + 24LL))(this);
  v4 = RegDeleteTreeW(v3, v2);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180015790  mov     [rsp+arg_0], rbx
0x180015795  push    rdi
0x180015796  sub     rsp, 20h
0x18001579a  mov     rax, [rcx]
0x18001579d  mov     rdi, rcx
0x1800157a0  mov     rax, [rax+20h]
0x1800157a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157a9  mov     rdx, [rdi]
0x1800157ac  mov     rbx, rax
0x1800157af  mov     rcx, rdi
0x1800157b2  mov     rax, [rdx+18h]
0x1800157b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157bb  mov     rdx, rbx; lpSubKey
0x1800157be  mov     rcx, rax; hKey
0x1800157c1  call    cs:__imp_RegDeleteTreeW
0x1800157c7  mov     ebx, eax
0x1800157c9  test    eax, eax
0x1800157cb  jle     short loc_1800157D6
0x1800157cd  movzx   ebx, ax
0x1800157d0  or      ebx, 80070000h
0x1800157d6  test    ebx, ebx
0x1800157d8  jz      short loc_18001580B
0x1800157da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157e1  lea     rax, WPP_GLOBAL_Control
0x1800157e8  cmp     rcx, rax
0x1800157eb  jz      short loc_18001580B
0x1800157ed  test    byte ptr [rcx+1Ch], 40h
0x1800157f1  jz      short loc_18001580B
0x1800157f3  mov     rcx, [rcx+10h]
0x1800157f7  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800157fe  mov     edx, 86h
0x180015803  mov     r9d, ebx
0x180015806  call    WPP_SF_d
0x18001580b  mov     eax, ebx
0x18001580d  mov     rbx, [rsp+28h+arg_0]
0x180015812  add     rsp, 20h
0x180015816  pop     rdi
0x180015817  retn
```
