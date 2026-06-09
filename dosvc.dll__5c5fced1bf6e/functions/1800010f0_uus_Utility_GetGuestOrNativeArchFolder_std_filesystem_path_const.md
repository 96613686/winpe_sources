# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x1800010f0`
- end: `0x18000115d`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `109`
- prototype: `void *__fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800035b0`

## callees

- `0x1800012a0`
- `0x1800036b4`
- `0x180003700`
- `0x180005020`

## pseudocode

```c
void *__fastcall uus::Utility::GetGuestOrNativeArchFolder(void *a1, void *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  uus::Utility::GetArchFolderFromMachine(v5, 34404);
  std::filesystem::operator/(a1, a2, (std::filesystem *)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a1;
}

```

## disassembly

```asm
0x1800010f0  mov     [rsp+arg_10], rbx
0x1800010f5  push    rdi
0x1800010f6  sub     rsp, 60h
0x1800010fa  mov     rax, cs:__security_cookie
0x180001101  xor     rax, rsp
0x180001104  mov     [rsp+68h+var_18], rax
0x180001109  mov     rbx, rdx
0x18000110c  mov     rdi, rcx
0x18000110f  mov     [rsp+68h+var_40], rcx
0x180001114  mov     edx, 8664h
0x180001119  lea     rcx, [rsp+68h+var_38]
0x18000111e  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x180001123  nop
0x180001124  lea     r8, [rsp+68h+var_38]; this
0x180001129  mov     rdx, rbx; void *
0x18000112c  mov     rcx, rdi; Src
0x18000112f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180001134  nop
0x180001135  lea     rcx, [rsp+68h+var_38]
0x18000113a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000113f  mov     rax, rdi
0x180001142  mov     rcx, [rsp+68h+var_18]
0x180001147  xor     rcx, rsp; StackCookie
0x18000114a  call    __security_check_cookie
0x18000114f  mov     rbx, [rsp+68h+arg_10]
0x180001157  add     rsp, 60h
0x18000115b  pop     rdi
0x18000115c  retn
```
