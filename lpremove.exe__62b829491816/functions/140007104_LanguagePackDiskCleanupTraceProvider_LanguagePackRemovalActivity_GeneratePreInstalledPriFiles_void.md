# LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::GeneratePreInstalledPriFiles(void)

- ea: `0x140007104`
- end: `0x14000717f`
- name: `?GeneratePreInstalledPriFiles@LanguagePackRemovalActivity@LanguagePackDiskCleanupTraceProvider@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000d8b8`

## callees

- `0x140001b9c`
- `0x140002190`
- `0x140007104`
- `0x140007eac`

## pseudocode

```c
void __fastcall LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::GeneratePreInstalledPriFiles(
        LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *this)
{
  __int64 v1; // rcx
  _BYTE v2[32]; // [rsp+30h] [rbp-38h] BYREF

  v1 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v1 > 5u
    && (*(_QWORD *)(v1 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v1 + 24) & 0x200000000000LL) == *(_QWORD *)(v1 + 24) )
  {
    tlgWriteTransfer_EventWriteTransfer(v1, word_14001431A, 0, 0, 2, v2);
  }
}

```

## disassembly

```asm
0x140007104  sub     rsp, 68h
0x140007108  mov     rax, cs:__security_cookie
0x14000710f  xor     rax, rsp
0x140007112  mov     [rsp+68h+var_18], rax
0x140007117  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000711c  mov     rcx, [rax+8]
0x140007120  mov     eax, [rcx]
0x140007122  cmp     eax, 5
0x140007125  jbe     short loc_14000716D
0x140007127  mov     rdx, [rcx+18h]
0x14000712b  mov     r8, 200000000000h
0x140007135  mov     rax, [rcx+10h]
0x140007139  test    r8, rax
0x14000713c  jz      short loc_14000716D
0x14000713e  mov     rax, rdx
0x140007141  and     rax, r8
0x140007144  cmp     rax, rdx
0x140007147  jnz     short loc_14000716D
0x140007149  lea     rax, [rsp+68h+var_38]
0x14000714e  xor     r9d, r9d
0x140007151  mov     [rsp+68h+var_40], rax
0x140007156  lea     rdx, word_14001431A
0x14000715d  xor     r8d, r8d
0x140007160  mov     [rsp+68h+var_48], 2
0x140007168  call    _tlgWriteTransfer_EventWriteTransfer
0x14000716d  mov     rcx, [rsp+68h+var_18]
0x140007172  xor     rcx, rsp; StackCookie
0x140007175  call    __security_check_cookie
0x14000717a  add     rsp, 68h
0x14000717e  retn
```
