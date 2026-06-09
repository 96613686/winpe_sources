# GetFirmwareResourceRegPath(ushort const *,ushort * *)

- ea: `0x18004f6e8`
- end: `0x18004f9a5`
- name: `?GetFirmwareResourceRegPath@@YAJPEBGPEAPEAG@Z`
- size: `701`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18004fe98`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000c6d0`
- `0x18000dfe0`
- `0x18000f0c8`
- `0x18000f8cc`
- `0x18002a92c`
- `0x18002d5ec`
- `0x18004f6e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f959`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f84c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f96d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f84c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f96d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004f734`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004f80a`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004f734`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004f80a`

## string_xrefs

- `0x18004f756`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f78f`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f7d3`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f825`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f8e6`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f93f`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004f933`: `GetFirmwareResourceRegPath`
- `0x18004f92c`: `firmwareResourcesRegPath = '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall GetFirmwareResourceRegPath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v5; // ebx
  void *v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v11; // r8
  __int128 *p_Src; // rdx
  unsigned __int16 *v13; // rbx
  HANDLE v14; // rax
  HANDLE v15; // rax
  unsigned int v16; // [rsp+30h] [rbp-58h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int16 *v18; // [rsp+40h] [rbp-48h] BYREF
  __int128 Src; // [rsp+48h] [rbp-40h] BYREF
  __int128 v20; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v16 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"FirmwareResources",
                                 L"SYSTEM\\CurrentControlSet\\Control\\FirmwareResources",
                                 0,
                                 0);
  v5 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW == 234 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpMem,
        0,
        v16);
      v7 = lpMem;
      if ( lpMem )
      {
        v8 = GetPersistedRegistryLocationW(
               L"FirmwareResources",
               L"SYSTEM\\CurrentControlSet\\Control\\FirmwareResources",
               lpMem,
               v16);
        if ( v8 )
        {
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x5D,
                 (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
                 (const char *)v8,
                 (unsigned int)&v16);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
          return v9;
        }
        else
        {
          Src = 0;
          v20 = 0;
          v11 = -1;
          do
            ++v11;
          while ( *((_WORD *)v7 + v11) );
          std::wstring::_Construct<1,unsigned short const *>(&Src, v7);
          std::wstring::operator+=(&Src, (void *)L"\\");
          std::wstring::operator+=(&Src, a1);
          p_Src = &Src;
          if ( *((_QWORD *)&v20 + 1) > 7u )
            p_Src = (__int128 *)Src;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v18,
            p_Src,
            -1);
          v13 = v18;
          if ( v18 )
          {
            PpfTraceLogFormat(
              "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
              0x66u,
              "GetFirmwareResourceRegPath",
              "firmwareResourcesRegPath = '%ws'",
              v18);
            *a2 = v13;
            std::wstring::~wstring(&Src);
            v15 = GetProcessHeap();
            HeapFree(v15, 0, v7);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x64,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
              (const char *)0x8007000ELL,
              (int)&v16);
            std::wstring::~wstring(&Src);
            v14 = GetProcessHeap();
            HeapFree(v14, 0, v7);
            return 2147942414LL;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
          (const char *)0x8007000ELL,
          (int)&v16);
        return 2147942414LL;
      }
    }
    else
    {
      if ( PersistedRegistryLocationW > 0 )
        v5 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x59,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
          (const char *)v5,
          (int)&v16);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v16);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18004f6e8  mov     r11, rsp
0x18004f6eb  mov     [r11+18h], rbx
0x18004f6ef  mov     [r11+20h], rsi
0x18004f6f3  push    rdi
0x18004f6f4  push    r14
0x18004f6f6  push    r15
0x18004f6f8  sub     rsp, 70h
0x18004f6fc  mov     rax, cs:__security_cookie
0x18004f703  xor     rax, rsp
0x18004f706  mov     [rsp+88h+var_20], rax
0x18004f70b  mov     r14, rdx
0x18004f70e  mov     rsi, rcx
0x18004f711  xor     r15d, r15d
0x18004f714  mov     [r11-58h], r15d
0x18004f718  lea     rax, [r11-58h]
0x18004f71c  mov     [r11-68h], rax
0x18004f720  xor     r9d, r9d
0x18004f723  xor     r8d, r8d
0x18004f726  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Fir"...
0x18004f72d  lea     rcx, aFirmwareresour; "FirmwareResources"
0x18004f734  call    cs:__imp_GetPersistedRegistryLocationW
0x18004f73b  nop     dword ptr [rax+rax+00h]
0x18004f740  mov     ebx, eax
0x18004f742  test    eax, eax
0x18004f744  jnz     short loc_18004F76C
0x18004f746  mov     rcx, [rsp+88h]; this
0x18004f74e  mov     ebx, 8000FFFFh
0x18004f753  mov     r9d, ebx; char *
0x18004f756  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f75d  lea     edx, [rax+58h]; void *
0x18004f760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f765  mov     eax, ebx
0x18004f767  jmp     loc_18004F981
0x18004f76c  cmp     eax, 0EAh
0x18004f771  jz      short loc_18004F7A7
0x18004f773  test    eax, eax
0x18004f775  jle     short loc_18004F780
0x18004f777  movzx   ebx, ax
0x18004f77a  or      ebx, 80070000h
0x18004f780  test    ebx, ebx
0x18004f782  jns     short loc_18004F7A0
0x18004f784  mov     rcx, [rsp+88h]; this
0x18004f78c  mov     r9d, ebx; char *
0x18004f78f  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f796  mov     edx, 59h ; 'Y'; void *
0x18004f79b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f7a0  mov     eax, ebx
0x18004f7a2  jmp     loc_18004F981
0x18004f7a7  mov     r8d, [rsp+88h+var_58]
0x18004f7ac  xor     edx, edx
0x18004f7ae  lea     rcx, [rsp+88h+lpMem]
0x18004f7b3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004f7b8  nop
0x18004f7b9  mov     rdi, [rsp+88h+lpMem]
0x18004f7be  test    rdi, rdi
0x18004f7c1  jnz     short loc_18004F7EA
0x18004f7c3  mov     rcx, [rsp+88h]; this
0x18004f7cb  mov     ebx, 8007000Eh
0x18004f7d0  mov     r9d, ebx; char *
0x18004f7d3  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f7da  lea     edx, [rdi+5Bh]; void *
0x18004f7dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f7e2  nop
0x18004f7e3  mov     eax, ebx
0x18004f7e5  jmp     loc_18004F981
0x18004f7ea  lea     rax, [rsp+88h+var_58]
0x18004f7ef  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004f7f4  mov     r9d, [rsp+88h+var_58]
0x18004f7f9  mov     r8, rdi
0x18004f7fc  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Fir"...
0x18004f803  lea     rcx, aFirmwareresour; "FirmwareResources"
0x18004f80a  call    cs:__imp_GetPersistedRegistryLocationW
0x18004f811  nop     dword ptr [rax+rax+00h]
0x18004f816  test    eax, eax
0x18004f818  jz      short loc_18004F85F
0x18004f81a  mov     rcx, [rsp+88h]; this
0x18004f822  mov     r9d, eax; char *
0x18004f825  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f82c  mov     edx, 5Dh ; ']'; void *
0x18004f831  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f836  mov     ebx, eax
0x18004f838  call    cs:__imp_GetProcessHeap
0x18004f83f  nop     dword ptr [rax+rax+00h]
0x18004f844  mov     rcx, rax; hHeap
0x18004f847  mov     r8, rdi; lpMem
0x18004f84a  xor     edx, edx; dwFlags
0x18004f84c  call    cs:__imp_HeapFree
0x18004f853  nop     dword ptr [rax+rax+00h]
0x18004f858  mov     eax, ebx
0x18004f85a  jmp     loc_18004F981
0x18004f85f  xorps   xmm0, xmm0
0x18004f862  movups  [rsp+88h+Src], xmm0
0x18004f867  xorps   xmm1, xmm1
0x18004f86a  movdqu  [rsp+88h+var_30], xmm1
0x18004f870  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004f874  mov     r8, rbx
0x18004f877  inc     r8
0x18004f87a  cmp     [rdi+r8*2], r15w
0x18004f87f  jnz     short loc_18004F877
0x18004f881  mov     rdx, rdi
0x18004f884  lea     rcx, [rsp+88h+Src]
0x18004f889  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004f88e  nop
0x18004f88f  lea     rdx, asc_18005C2E0; "\\"
0x18004f896  lea     rcx, [rsp+88h+Src]; Src
0x18004f89b  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004f8a0  mov     rdx, rsi; void *
0x18004f8a3  lea     rcx, [rsp+88h+Src]; Src
0x18004f8a8  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18004f8ad  lea     rdx, [rsp+88h+Src]
0x18004f8b2  cmp     qword ptr [rsp+88h+var_30+8], 7
0x18004f8b8  cmova   rdx, qword ptr [rsp+88h+Src]
0x18004f8be  mov     r8, rbx
0x18004f8c1  lea     rcx, [rsp+88h+var_48]
0x18004f8c6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004f8cb  nop
0x18004f8cc  mov     rbx, [rsp+88h+var_48]
0x18004f8d1  test    rbx, rbx
0x18004f8d4  jnz     short loc_18004F927
0x18004f8d6  mov     rcx, [rsp+88h]; this
0x18004f8de  mov     ebx, 8007000Eh
0x18004f8e3  mov     r9d, ebx; char *
0x18004f8e6  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f8ed  mov     edx, 64h ; 'd'; void *
0x18004f8f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f8f7  nop
0x18004f8f8  lea     rcx, [rsp+88h+Src]
0x18004f8fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f902  nop
0x18004f903  call    cs:__imp_GetProcessHeap
0x18004f90a  nop     dword ptr [rax+rax+00h]
0x18004f90f  mov     rcx, rax; hHeap
0x18004f912  mov     r8, rdi; lpMem
0x18004f915  xor     edx, edx; dwFlags
0x18004f917  call    cs:__imp_HeapFree
0x18004f91e  nop     dword ptr [rax+rax+00h]
0x18004f923  mov     eax, ebx
0x18004f925  jmp     short loc_18004F981
0x18004f927  mov     qword ptr [rsp+88h+var_68], rbx
0x18004f92c  lea     r9, aFirmwareresour_1; "firmwareResourcesRegPath = '%ws'"
0x18004f933  lea     r8, aGetfirmwareres; "GetFirmwareResourceRegPath"
0x18004f93a  mov     edx, 66h ; 'f'; unsigned int
0x18004f93f  lea     rcx, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004f946  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004f94b  mov     [r14], rbx
0x18004f94e  lea     rcx, [rsp+88h+Src]
0x18004f953  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f958  nop
0x18004f959  call    cs:__imp_GetProcessHeap
0x18004f960  nop     dword ptr [rax+rax+00h]
0x18004f965  mov     rcx, rax; hHeap
0x18004f968  mov     r8, rdi; lpMem
0x18004f96b  xor     edx, edx; dwFlags
0x18004f96d  call    cs:__imp_HeapFree
0x18004f974  nop     dword ptr [rax+rax+00h]
0x18004f979  xor     eax, eax
0x18004f97b  jmp     short loc_18004F981
0x18004f97d  mov     eax, [rsp+88h+var_58]
0x18004f981  mov     rcx, [rsp+88h+var_20]
0x18004f986  xor     rcx, rsp; StackCookie
0x18004f989  call    __security_check_cookie
0x18004f98e  lea     r11, [rsp+88h+var_18]
0x18004f993  mov     rbx, [r11+30h]
0x18004f997  mov     rsi, [r11+38h]
0x18004f99b  mov     rsp, r11
0x18004f99e  pop     r15
0x18004f9a0  pop     r14
0x18004f9a2  pop     rdi
0x18004f9a3  retn
```
