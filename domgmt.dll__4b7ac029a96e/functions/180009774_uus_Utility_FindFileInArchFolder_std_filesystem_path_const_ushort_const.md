# uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)

- ea: `0x180009774`
- end: `0x180009863`
- name: `?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `239`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800084c8`

## callees

- `0x180001ba0`
- `0x180008d88`
- `0x180009774`
- `0x18000986c`
- `0x18000993c`
- `0x180009ec0`
- `0x180009f54`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInArchFolder(__int64 a1, __int64 a2)
{
  struct std::filesystem::path *GuestOrNativeArchFolder; // rax
  __int64 HostArchFolder; // rax
  _QWORD v7[2]; // [rsp+20h] [rbp-39h] BYREF
  __m128i si128; // [rsp+30h] [rbp-29h]
  char v9; // [rsp+40h] [rbp-19h]
  __int64 v10; // [rsp+50h] [rbp-9h]
  _BYTE v11[40]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v12[32]; // [rsp+80h] [rbp+27h] BYREF

  v10 = a1;
  GuestOrNativeArchFolder = (struct std::filesystem::path *)uus::Utility::GetGuestOrNativeArchFolder(v12, a2);
  uus::Utility::FindFileInSubFolder((std::filesystem::path *)v7, GuestOrNativeArchFolder);
  std::wstring::~wstring(v12);
  if ( v9 )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)a1 = v7[0];
    *(_QWORD *)(a1 + 8) = v7[1];
    *(__m128i *)(a1 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v7[0]) = 0;
    *(_BYTE *)(a1 + 32) = 1;
LABEL_6:
    std::wstring::~wstring(v7);
    return a1;
  }
  HostArchFolder = uus::Utility::GetHostArchFolder(v11, a2);
  uus::Utility::FindFileInSubFolder(a1, HostArchFolder);
  if ( v11[32] )
    std::wstring::~wstring(v11);
  if ( v9 )
    goto LABEL_6;
  return a1;
}

```

## disassembly

```asm
0x180009774  mov     [rsp-8+arg_10], rbx
0x180009779  mov     [rsp-8+arg_18], rdi
0x18000977e  push    rbp
0x18000977f  lea     rbp, [rsp-57h]
0x180009784  sub     rsp, 0B0h
0x18000978b  mov     rax, cs:__security_cookie
0x180009792  xor     rax, rsp
0x180009795  mov     [rbp+57h+var_10], rax
0x180009799  mov     rdi, rdx
0x18000979c  mov     rbx, rcx
0x18000979f  mov     [rbp+57h+var_60], rcx
0x1800097a3  lea     rcx, [rbp+57h+var_30]
0x1800097a7  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x1800097ac  nop
0x1800097ad  mov     rdx, rax; struct std::filesystem::path *
0x1800097b0  lea     rcx, [rbp+57h+var_90]; this
0x1800097b4  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x1800097b9  nop
0x1800097ba  lea     rcx, [rbp+57h+var_30]
0x1800097be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800097c3  cmp     [rbp+57h+var_70], 0
0x1800097c7  jz      short loc_180009807
0x1800097c9  xorps   xmm0, xmm0
0x1800097cc  movups  xmmword ptr [rbx], xmm0
0x1800097cf  mov     rax, [rbp+57h+var_90]
0x1800097d3  mov     [rbx], rax
0x1800097d6  mov     rax, [rbp+57h+var_88]
0x1800097da  mov     [rbx+8], rax
0x1800097de  mov     rcx, qword ptr [rbp+57h+var_80]
0x1800097e2  mov     [rbx+10h], rcx
0x1800097e6  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1800097ea  mov     [rbx+18h], rcx
0x1800097ee  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800097f6  movdqu  [rbp+57h+var_80], xmm0
0x1800097fb  xor     ecx, ecx
0x1800097fd  mov     word ptr [rbp+57h+var_90], cx
0x180009801  mov     byte ptr [rbx+20h], 1
0x180009805  jmp     short loc_180009836
0x180009807  mov     rdx, rdi
0x18000980a  lea     rcx, [rbp+57h+var_58]
0x18000980e  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x180009813  nop
0x180009814  mov     rdx, rax
0x180009817  mov     rcx, rbx
0x18000981a  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)
0x18000981f  nop
0x180009820  cmp     [rbp+57h+var_38], 0
0x180009824  jz      short loc_180009830
0x180009826  lea     rcx, [rbp+57h+var_58]
0x18000982a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000982f  nop
0x180009830  cmp     [rbp+57h+var_70], 0
0x180009834  jz      short loc_18000983F
0x180009836  lea     rcx, [rbp+57h+var_90]
0x18000983a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000983f  mov     rax, rbx
0x180009842  mov     rcx, [rbp+57h+var_10]
0x180009846  xor     rcx, rsp; StackCookie
0x180009849  call    __security_check_cookie
0x18000984e  lea     r11, [rsp+0B0h+var_s0]
0x180009856  mov     rbx, [r11+20h]
0x18000985a  mov     rdi, [r11+28h]
0x18000985e  mov     rsp, r11
0x180009861  pop     rbp
0x180009862  retn
```
