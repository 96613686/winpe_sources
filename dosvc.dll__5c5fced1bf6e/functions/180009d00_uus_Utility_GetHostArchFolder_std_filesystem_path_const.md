# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x180009d00`
- end: `0x180009dfc`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `252`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001170`

## callees

- `0x1800012a0`
- `0x1800036b4`
- `0x180003700`
- `0x180005020`
- `0x180009d00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009d33`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180009d46`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180009d46`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentProcess; // rax
  std::filesystem *ArchFolderFromMachine; // rax
  _QWORD *v6; // rax
  _WORD v8[2]; // [rsp+20h] [rbp-68h] BYREF
  _WORD v9[6]; // [rsp+24h] [rbp-64h] BYREF
  __int64 v10; // [rsp+30h] [rbp-58h]
  _QWORD Src[4]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-30h] BYREF

  v10 = a1;
  v9[0] = 0;
  v8[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v9, v8) && v8[0] && v8[0] != 0x8664 )
  {
    ArchFolderFromMachine = (std::filesystem *)uus::Utility::GetArchFolderFromMachine((__int64)v12, v8[0]);
    v6 = std::filesystem::operator/(Src, a2, ArchFolderFromMachine);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v6;
    *(_OWORD *)(a1 + 16) = *((_OWORD *)v6 + 1);
    *(_WORD *)v6 = 0;
    v6[2] = 0;
    v6[3] = 7;
    *(_BYTE *)(a1 + 32) = 1;
    std::wstring::_Tidy_deallocate(Src);
    std::wstring::_Tidy_deallocate(v12);
  }
  else
  {
    *(_BYTE *)(a1 + 32) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180009d00  mov     [rsp+arg_10], rbx
0x180009d05  push    rdi
0x180009d06  sub     rsp, 80h
0x180009d0d  mov     rax, cs:__security_cookie
0x180009d14  xor     rax, rsp
0x180009d17  mov     [rsp+88h+var_10], rax
0x180009d1c  mov     rdi, rdx
0x180009d1f  mov     rbx, rcx
0x180009d22  mov     [rsp+88h+var_58], rcx
0x180009d27  xor     eax, eax
0x180009d29  mov     [rsp+88h+var_64], ax
0x180009d2e  mov     [rsp+88h+var_68], ax
0x180009d33  call    cs:__imp_GetCurrentProcess
0x180009d39  mov     rcx, rax
0x180009d3c  lea     r8, [rsp+88h+var_68]
0x180009d41  lea     rdx, [rsp+88h+var_64]
0x180009d46  call    cs:__imp_IsWow64Process2
0x180009d4c  test    eax, eax
0x180009d4e  jz      loc_180009DD7
0x180009d54  xor     eax, eax
0x180009d56  movzx   ecx, [rsp+88h+var_68]
0x180009d5b  cmp     ax, cx
0x180009d5e  jz      short loc_180009DD7
0x180009d60  mov     eax, 8664h
0x180009d65  cmp     ax, cx
0x180009d68  jz      short loc_180009DD7
0x180009d6a  mov     edx, ecx
0x180009d6c  lea     rcx, [rsp+88h+var_30]
0x180009d71  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x180009d76  nop
0x180009d77  mov     r8, rax; this
0x180009d7a  mov     rdx, rdi; void *
0x180009d7d  lea     rcx, [rsp+88h+Src]; Src
0x180009d82  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009d87  xorps   xmm0, xmm0
0x180009d8a  movups  xmmword ptr [rbx], xmm0
0x180009d8d  mov     qword ptr [rbx+10h], 0
0x180009d95  mov     qword ptr [rbx+18h], 0
0x180009d9d  movups  xmm0, xmmword ptr [rax]
0x180009da0  movups  xmmword ptr [rbx], xmm0
0x180009da3  movups  xmm1, xmmword ptr [rax+10h]
0x180009da7  movups  xmmword ptr [rbx+10h], xmm1
0x180009dab  xor     ecx, ecx
0x180009dad  mov     [rax], cx
0x180009db0  mov     [rax+10h], rcx
0x180009db4  mov     qword ptr [rax+18h], 7
0x180009dbc  mov     byte ptr [rbx+20h], 1
0x180009dc0  lea     rcx, [rsp+88h+Src]
0x180009dc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009dca  nop
0x180009dcb  lea     rcx, [rsp+88h+var_30]
0x180009dd0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009dd5  jmp     short loc_180009DDB
0x180009dd7  mov     byte ptr [rbx+20h], 0
0x180009ddb  mov     rax, rbx
0x180009dde  mov     rcx, [rsp+88h+var_10]
0x180009de3  xor     rcx, rsp; StackCookie
0x180009de6  call    __security_check_cookie
0x180009deb  mov     rbx, [rsp+88h+arg_10]
0x180009df3  add     rsp, 80h
0x180009dfa  pop     rdi
0x180009dfb  retn
```
