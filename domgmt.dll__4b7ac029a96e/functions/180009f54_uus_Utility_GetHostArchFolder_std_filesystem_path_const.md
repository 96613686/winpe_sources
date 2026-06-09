# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x180009f54`
- end: `0x18000a050`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `252`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009774`

## callees

- `0x180001ba0`
- `0x180008d88`
- `0x180008f94`
- `0x180009ab8`
- `0x180009f54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009f87`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180009f9a`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180009f9a`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, struct std::filesystem::path *a2)
{
  HANDLE CurrentProcess; // rax
  std::filesystem *ArchFolderFromMachine; // rax
  __int64 v6; // rax
  _WORD v8[2]; // [rsp+20h] [rbp-68h] BYREF
  _WORD v9[6]; // [rsp+24h] [rbp-64h] BYREF
  __int64 v10; // [rsp+30h] [rbp-58h]
  _BYTE Src[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-30h] BYREF

  v10 = a1;
  v9[0] = 0;
  v8[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v9, v8) && v8[0] && v8[0] != 0x8664 )
  {
    ArchFolderFromMachine = (std::filesystem *)uus::Utility::GetArchFolderFromMachine(v12, v8[0]);
    v6 = std::filesystem::operator/(Src, a2, ArchFolderFromMachine);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v6;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v6 + 16);
    *(_WORD *)v6 = 0;
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 7;
    *(_BYTE *)(a1 + 32) = 1;
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v12);
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
0x180009f54  mov     [rsp+arg_10], rbx
0x180009f59  push    rdi
0x180009f5a  sub     rsp, 80h
0x180009f61  mov     rax, cs:__security_cookie
0x180009f68  xor     rax, rsp
0x180009f6b  mov     [rsp+88h+var_10], rax
0x180009f70  mov     rdi, rdx
0x180009f73  mov     rbx, rcx
0x180009f76  mov     [rsp+88h+var_58], rcx
0x180009f7b  xor     eax, eax
0x180009f7d  mov     [rsp+88h+var_64], ax
0x180009f82  mov     [rsp+88h+var_68], ax
0x180009f87  call    cs:__imp_GetCurrentProcess
0x180009f8d  mov     rcx, rax
0x180009f90  lea     r8, [rsp+88h+var_68]
0x180009f95  lea     rdx, [rsp+88h+var_64]
0x180009f9a  call    cs:__imp_IsWow64Process2
0x180009fa0  test    eax, eax
0x180009fa2  jz      loc_18000A02B
0x180009fa8  xor     eax, eax
0x180009faa  movzx   ecx, [rsp+88h+var_68]
0x180009faf  cmp     ax, cx
0x180009fb2  jz      short loc_18000A02B
0x180009fb4  mov     eax, 8664h
0x180009fb9  cmp     ax, cx
0x180009fbc  jz      short loc_18000A02B
0x180009fbe  mov     edx, ecx
0x180009fc0  lea     rcx, [rsp+88h+var_30]
0x180009fc5  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x180009fca  nop
0x180009fcb  mov     r8, rax; this
0x180009fce  mov     rdx, rdi; struct std::filesystem::path *
0x180009fd1  lea     rcx, [rsp+88h+Src]; Src
0x180009fd6  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009fdb  xorps   xmm0, xmm0
0x180009fde  movups  xmmword ptr [rbx], xmm0
0x180009fe1  mov     qword ptr [rbx+10h], 0
0x180009fe9  mov     qword ptr [rbx+18h], 0
0x180009ff1  movups  xmm0, xmmword ptr [rax]
0x180009ff4  movups  xmmword ptr [rbx], xmm0
0x180009ff7  movups  xmm1, xmmword ptr [rax+10h]
0x180009ffb  movups  xmmword ptr [rbx+10h], xmm1
0x180009fff  xor     ecx, ecx
0x18000a001  mov     [rax], cx
0x18000a004  mov     [rax+10h], rcx
0x18000a008  mov     qword ptr [rax+18h], 7
0x18000a010  mov     byte ptr [rbx+20h], 1
0x18000a014  lea     rcx, [rsp+88h+Src]
0x18000a019  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a01e  nop
0x18000a01f  lea     rcx, [rsp+88h+var_30]
0x18000a024  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a029  jmp     short loc_18000A02F
0x18000a02b  mov     byte ptr [rbx+20h], 0
0x18000a02f  mov     rax, rbx
0x18000a032  mov     rcx, [rsp+88h+var_10]
0x18000a037  xor     rcx, rsp; StackCookie
0x18000a03a  call    __security_check_cookie
0x18000a03f  mov     rbx, [rsp+88h+arg_10]
0x18000a047  add     rsp, 80h
0x18000a04e  pop     rdi
0x18000a04f  retn
```
