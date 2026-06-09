# CModule::IsPresentEffectsBlocked(void)

- ea: `0x18008ef20`
- end: `0x18008f193`
- name: `?IsPresentEffectsBlocked@CModule@@QEAA_NXZ`
- size: `627`
- prototype: `bool __fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18006579c`

## callees

- `0x18000c6b0`
- `0x18005ffa8`
- `0x180061f40`
- `0x180069768`
- `0x180075fa0`
- `0x180075fc4`
- `0x180076f20`
- `0x180089cc8`
- `0x18008a4c8`
- `0x18008ef20`
- `0x180091ec0`
- `0x180092bac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18008f04d`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18008f0ed`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18008f04d`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18008f0ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008f099`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008f099`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008eff9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008eff9`

## string_xrefs

- `0x18008ef59`: `c:\windows\system32`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall CModule::IsPresentEffectsBlocked(CModule *this)
{
  _WORD *v2; // rsi
  unsigned __int16 *v3; // rbx
  unsigned __int16 *v4; // rdi
  char v5; // si
  _WORD *v6; // r14
  unsigned __int16 *v7; // rbx
  unsigned __int16 *v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rdi
  CModule *v11; // rcx
  char v13; // [rsp+20h] [rbp-E0h]
  _QWORD v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v15[3]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v17; // [rsp+70h] [rbp-90h]
  _QWORD v18[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v19; // [rsp+90h] [rbp-70h]
  _BYTE v20[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v21[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v22[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v24[32]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Filename[264]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Buffer[264]; // [rsp+350h] [rbp+250h] BYREF

  if ( (*((_BYTE *)this + 648) & 1) == 0 )
  {
    std::wstring::wstring(v20, L"c:\\windows\\system32");
    std::wstring::wstring(v21, L"wudfhost.exe");
    std::wstring::wstring(v22, L"svchost.exe");
    std::wstring::wstring(v23, L"winlogon.exe");
    std::wstring::wstring(v24, L"dwm.exe");
    v14[0] = v20;
    v14[1] = Filename;
    std::vector<std::wstring>::vector<std::wstring>(v15, v14);
    `eh vector destructor iterator'(v20, 0x20u, 5u, std::wstring::~wstring);
    if ( GetSystemDirectoryW(Buffer, 0x104u) )
    {
      std::wstring::wstring(v16, Buffer);
      v2 = v16;
      if ( v17 > 7 )
        v2 = (_WORD *)v16[0];
      v3 = *(unsigned __int16 **)std::wstring::end(v16, v14);
      v4 = (unsigned __int16 *)v16;
      if ( v17 > 7 )
        v4 = (unsigned __int16 *)v16[0];
      while ( v4 != v3 )
        *v2++ = _o_towlower(*v4++);
      std::wstring::operator=(v15[0], v16);
      std::wstring::_Tidy_deallocate(v16);
    }
    v5 = 0;
    memset_0(Filename, 0, 0x208u);
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      std::wstring::wstring(v18, Filename);
      v6 = v18;
      if ( v19 > 7 )
        v6 = (_WORD *)v18[0];
      v7 = *(unsigned __int16 **)std::wstring::end(v18, v14);
      v8 = (unsigned __int16 *)v18;
      if ( v19 > 7 )
        v8 = (unsigned __int16 *)v18[0];
      while ( v8 != v7 )
        *v6++ = _o_towlower(*v8++);
      v9 = v15[0];
      v10 = v15[1];
      while ( v9 != v10 )
      {
        if ( std::wstring::find(v18, v9) != -1 )
        {
          v5 = 1;
          CModule::RecordJournalImpl(v11, 0, "Effects blocked in process");
          break;
        }
        v9 += 32;
      }
      std::wstring::_Tidy_deallocate(v18);
    }
    *((_BYTE *)this + 648) = (2 * v5) | v13 & 0xFD | 1;
    std::vector<std::wstring>::_Tidy(v15);
  }
  return (*((_BYTE *)this + 648) & 2) != 0;
}

```

## disassembly

```asm
0x18008ef20  push    rbp
0x18008ef22  push    rbx
0x18008ef23  push    rsi
0x18008ef24  push    rdi
0x18008ef25  push    r14
0x18008ef27  push    r15
0x18008ef29  lea     rbp, [rsp-478h]
0x18008ef31  sub     rsp, 578h
0x18008ef38  mov     rax, cs:__security_cookie
0x18008ef3f  xor     rax, rsp
0x18008ef42  mov     [rbp+4A0h+var_40], rax
0x18008ef49  mov     r15, rcx
0x18008ef4c  test    byte ptr [rcx+288h], 1
0x18008ef53  jnz     loc_18008F169
0x18008ef59  lea     rdx, aCWindowsSystem; "c:\\windows\\system32"
0x18008ef60  lea     rcx, [rbp+4A0h+var_500]
0x18008ef64  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008ef69  nop
0x18008ef6a  lea     rdx, aWudfhostExe; "wudfhost.exe"
0x18008ef71  lea     rcx, [rbp+4A0h+var_4E0]
0x18008ef75  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008ef7a  nop
0x18008ef7b  lea     rdx, aSvchostExe; "svchost.exe"
0x18008ef82  lea     rcx, [rbp+4A0h+var_4C0]
0x18008ef86  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008ef8b  nop
0x18008ef8c  lea     rdx, aWinlogonExe; "winlogon.exe"
0x18008ef93  lea     rcx, [rbp+4A0h+var_4A0]
0x18008ef97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008ef9c  nop
0x18008ef9d  lea     rdx, aDwmExe; "dwm.exe"
0x18008efa4  lea     rcx, [rbp+4A0h+var_480]
0x18008efa8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008efad  nop
0x18008efae  lea     rax, [rbp+4A0h+var_500]
0x18008efb2  mov     [rsp+5A0h+var_570], rax
0x18008efb7  lea     rax, [rbp+4A0h+Filename]
0x18008efbb  mov     [rsp+5A0h+var_568], rax
0x18008efc0  lea     rdx, [rsp+5A0h+var_570]
0x18008efc5  lea     rcx, [rsp+5A0h+var_560]
0x18008efca  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x18008efcf  nop
0x18008efd0  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18008efd7  mov     edx, 20h ; ' '; unsigned __int64
0x18008efdc  lea     r8d, [rdx-1Bh]; unsigned __int64
0x18008efe0  lea     rcx, [rbp+4A0h+var_500]; void *
0x18008efe4  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18008efe9  mov     r14d, 104h
0x18008efef  mov     edx, r14d; uSize
0x18008eff2  lea     rcx, [rbp+4A0h+Buffer]; lpBuffer
0x18008eff9  call    cs:__imp_GetSystemDirectoryW
0x18008efff  test    eax, eax
0x18008f001  jz      short loc_18008F07C
0x18008f003  lea     rdx, [rbp+4A0h+Buffer]
0x18008f00a  lea     rcx, [rsp+5A0h+var_548]
0x18008f00f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f014  lea     rsi, [rsp+5A0h+var_548]
0x18008f019  cmp     [rsp+5A0h+var_530], 7
0x18008f01f  cmova   rsi, [rsp+5A0h+var_548]
0x18008f025  lea     rdx, [rsp+5A0h+var_570]
0x18008f02a  lea     rcx, [rsp+5A0h+var_548]
0x18008f02f  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18008f034  mov     rbx, [rax]
0x18008f037  lea     rdi, [rsp+5A0h+var_548]
0x18008f03c  cmp     [rsp+5A0h+var_530], 7
0x18008f042  cmova   rdi, [rsp+5A0h+var_548]
0x18008f048  jmp     short loc_18008F05E
0x18008f04a  movzx   ecx, word ptr [rdi]
0x18008f04d  call    cs:__imp__o_towlower
0x18008f053  mov     [rsi], ax
0x18008f056  lea     rsi, [rsi+2]
0x18008f05a  add     rdi, 2
0x18008f05e  cmp     rdi, rbx
0x18008f061  jnz     short loc_18008F04A
0x18008f063  lea     rdx, [rsp+5A0h+var_548]
0x18008f068  mov     rcx, [rsp+5A0h+var_560]
0x18008f06d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008f072  lea     rcx, [rsp+5A0h+var_548]
0x18008f077  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f07c  xor     sil, sil
0x18008f07f  xor     edx, edx; Val
0x18008f081  mov     r8d, 208h; Size
0x18008f087  lea     rcx, [rbp+4A0h+Filename]; void *
0x18008f08b  call    memset_0
0x18008f090  mov     r8d, r14d; nSize
0x18008f093  lea     rdx, [rbp+4A0h+Filename]; lpFilename
0x18008f097  xor     ecx, ecx; hModule
0x18008f099  call    cs:__imp_GetModuleFileNameW
0x18008f09f  test    eax, eax
0x18008f0a1  jz      loc_18008F14A
0x18008f0a7  lea     rdx, [rbp+4A0h+Filename]
0x18008f0ab  lea     rcx, [rsp+5A0h+var_528]
0x18008f0b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f0b5  nop
0x18008f0b6  lea     r14, [rsp+5A0h+var_528]
0x18008f0bb  cmp     [rbp+4A0h+var_510], 7
0x18008f0c0  cmova   r14, [rsp+5A0h+var_528]
0x18008f0c6  lea     rdx, [rsp+5A0h+var_570]
0x18008f0cb  lea     rcx, [rsp+5A0h+var_528]
0x18008f0d0  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18008f0d5  mov     rbx, [rax]
0x18008f0d8  lea     rdi, [rsp+5A0h+var_528]
0x18008f0dd  cmp     [rbp+4A0h+var_510], 7
0x18008f0e2  cmova   rdi, [rsp+5A0h+var_528]
0x18008f0e8  jmp     short loc_18008F0FF
0x18008f0ea  movzx   ecx, word ptr [rdi]
0x18008f0ed  call    cs:__imp__o_towlower
0x18008f0f3  mov     [r14], ax
0x18008f0f7  lea     r14, [r14+2]
0x18008f0fb  add     rdi, 2
0x18008f0ff  cmp     rdi, rbx
0x18008f102  jnz     short loc_18008F0EA
0x18008f104  mov     rbx, [rsp+5A0h+var_560]
0x18008f109  mov     rdi, [rsp+5A0h+var_558]
0x18008f10e  jmp     short loc_18008F127
0x18008f110  mov     rdx, rbx
0x18008f113  lea     rcx, [rsp+5A0h+var_528]
0x18008f118  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18008f11d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008f121  jnz     short loc_18008F12E
0x18008f123  add     rbx, 20h ; ' '
0x18008f127  cmp     rbx, rdi
0x18008f12a  jnz     short loc_18008F110
0x18008f12c  jmp     short loc_18008F140
0x18008f12e  mov     sil, 1
0x18008f131  lea     r8, aEffectsBlocked; "Effects blocked in process"
0x18008f138  xor     edx, edx; unsigned int
0x18008f13a  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18008f13f  nop
0x18008f140  lea     rcx, [rsp+5A0h+var_528]
0x18008f145  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f14a  mov     al, [rsp+5A0h+var_580]
0x18008f14e  and     al, 0FDh
0x18008f150  add     sil, sil
0x18008f153  or      al, sil
0x18008f156  or      al, 1
0x18008f158  mov     [r15+288h], al
0x18008f15f  lea     rcx, [rsp+5A0h+var_560]
0x18008f164  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18008f169  mov     al, [r15+288h]
0x18008f170  shr     al, 1
0x18008f172  and     al, 1
0x18008f174  mov     rcx, [rbp+4A0h+var_40]
0x18008f17b  xor     rcx, rsp; StackCookie
0x18008f17e  call    __security_check_cookie
0x18008f183  add     rsp, 578h
0x18008f18a  pop     r15
0x18008f18c  pop     r14
0x18008f18e  pop     rdi
0x18008f18f  pop     rsi
0x18008f190  pop     rbx
0x18008f191  pop     rbp
0x18008f192  retn
```
