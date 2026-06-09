# uus::Utility::FindFileInPackage(std::filesystem::path const &,ushort const *,uint)

- ea: `0x180001170`
- end: `0x180001297`
- name: `?FindFileInPackage@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBGI@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800087c0`

## callees

- `0x180001170`
- `0x1800012a0`
- `0x180001380`
- `0x1800036b4`
- `0x180003700`
- `0x180005020`
- `0x180009c4c`
- `0x180009d00`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInPackage(__int64 a1, void *a2)
{
  __int64 HostArchFolder; // rax
  _QWORD v6[2]; // [rsp+20h] [rbp-98h] BYREF
  __m128i si128; // [rsp+30h] [rbp-88h]
  char v8; // [rsp+40h] [rbp-78h]
  __int64 v9; // [rsp+50h] [rbp-68h]
  _BYTE v10[40]; // [rsp+58h] [rbp-60h] BYREF
  _BYTE Src[32]; // [rsp+80h] [rbp-38h] BYREF

  v9 = a1;
  uus::Utility::GetArchFolderFromMachine(v10, 34404);
  std::filesystem::operator/(Src, a2, (std::filesystem *)v10);
  std::wstring::_Tidy_deallocate(v10);
  uus::Utility::FindFileInSubFolder(v6, Src);
  std::wstring::_Tidy_deallocate(Src);
  if ( v8 )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)a1 = v6[0];
    *(_QWORD *)(a1 + 8) = v6[1];
    *(__m128i *)(a1 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v6[0]) = 0;
    *(_BYTE *)(a1 + 32) = 1;
LABEL_6:
    std::wstring::_Tidy_deallocate(v6);
    return a1;
  }
  HostArchFolder = uus::Utility::GetHostArchFolder(v10, a2);
  uus::Utility::FindFileInSubFolder(a1, HostArchFolder);
  if ( v10[32] )
    std::wstring::_Tidy_deallocate(v10);
  if ( v8 )
    goto LABEL_6;
  return a1;
}

```

## disassembly

```asm
0x180001170  mov     [rsp+arg_10], rbx
0x180001175  push    rdi
0x180001176  sub     rsp, 0B0h
0x18000117d  mov     rax, cs:__security_cookie
0x180001184  xor     rax, rsp
0x180001187  mov     [rsp+0B8h+var_18], rax
0x18000118f  mov     rdi, rdx
0x180001192  mov     rbx, rcx
0x180001195  mov     [rsp+0B8h+var_68], rcx
0x18000119a  mov     edx, 8664h
0x18000119f  lea     rcx, [rsp+0B8h+var_60]
0x1800011a4  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x1800011a9  nop
0x1800011aa  lea     r8, [rsp+0B8h+var_60]; this
0x1800011af  mov     rdx, rdi; void *
0x1800011b2  lea     rcx, [rsp+0B8h+Src]; Src
0x1800011ba  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800011bf  nop
0x1800011c0  lea     rcx, [rsp+0B8h+var_60]
0x1800011c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800011ca  nop
0x1800011cb  lea     rdx, [rsp+0B8h+Src]
0x1800011d3  lea     rcx, [rsp+0B8h+var_98]
0x1800011d8  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x1800011dd  nop
0x1800011de  lea     rcx, [rsp+0B8h+Src]
0x1800011e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800011eb  cmp     [rsp+0B8h+var_78], 0
0x1800011f0  jz      short loc_180001236
0x1800011f2  xorps   xmm0, xmm0
0x1800011f5  movups  xmmword ptr [rbx], xmm0
0x1800011f8  mov     rax, [rsp+0B8h+var_98]
0x1800011fd  mov     [rbx], rax
0x180001200  mov     rax, [rsp+0B8h+var_90]
0x180001205  mov     [rbx+8], rax
0x180001209  mov     rax, qword ptr [rsp+0B8h+var_88]
0x18000120e  mov     [rbx+10h], rax
0x180001212  mov     rax, qword ptr [rsp+0B8h+var_88+8]
0x180001217  mov     [rbx+18h], rax
0x18000121b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180001223  movdqu  [rsp+0B8h+var_88], xmm0
0x180001229  xor     eax, eax
0x18000122b  mov     word ptr [rsp+0B8h+var_98], ax
0x180001230  mov     byte ptr [rbx+20h], 1
0x180001234  jmp     short loc_180001269
0x180001236  mov     rdx, rdi
0x180001239  lea     rcx, [rsp+0B8h+var_60]
0x18000123e  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x180001243  nop
0x180001244  mov     rdx, rax
0x180001247  mov     rcx, rbx
0x18000124a  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)
0x18000124f  nop
0x180001250  cmp     [rsp+0B8h+var_40], 0
0x180001255  jz      short loc_180001262
0x180001257  lea     rcx, [rsp+0B8h+var_60]
0x18000125c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180001261  nop
0x180001262  cmp     [rsp+0B8h+var_78], 0
0x180001267  jz      short loc_180001273
0x180001269  lea     rcx, [rsp+0B8h+var_98]
0x18000126e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180001273  mov     rax, rbx
0x180001276  mov     rcx, [rsp+0B8h+var_18]
0x18000127e  xor     rcx, rsp; StackCookie
0x180001281  call    __security_check_cookie
0x180001286  mov     rbx, [rsp+0B8h+arg_10]
0x18000128e  add     rsp, 0B0h
0x180001295  pop     rdi
0x180001296  retn
```
