# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)

- ea: `0x18000993c`
- end: `0x180009ab1`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `373`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180009774`
- `0x18000986c`

## callees

- `0x1800012e8`
- `0x180001ba0`
- `0x180007504`
- `0x180008a68`
- `0x180008d88`
- `0x180008f94`
- `0x18000993c`
- `0x18000a960`

## string_xrefs

- `0x18000996b`: `uusbrain.dll`

## pseudocode

```c
std::filesystem::path *__fastcall uus::Utility::FindFileInSubFolder(
        std::filesystem::path *this,
        struct std::filesystem::path *a2)
{
  const WCHAR *v4; // rcx
  int stats; // eax
  const struct std::filesystem::path *v6; // r9
  int v7; // edx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  bool v15; // al
  char v17[16]; // [rsp+30h] [rbp-19h] BYREF
  __int128 v18; // [rsp+40h] [rbp-9h]
  LPCWSTR lpFileName[4]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp+27h] BYREF

  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v20);
  std::filesystem::operator/(lpFileName, a2, (std::filesystem *)v20);
  std::wstring::~wstring(v20);
  *(_OWORD *)v17 = 0;
  v18 = 0;
  v4 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v4 = lpFileName[0];
  stats = _std_fs_get_stats(v4);
  v7 = stats;
  if ( stats )
  {
    v9 = stats - 2;
    v8 = 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 50;
        if ( v11 )
        {
          v12 = v11 - 11;
          if ( v12 )
          {
            v13 = v12 - 59;
            if ( v13 )
            {
              v14 = v13 - 38;
              if ( v14 )
              {
                if ( v14 != 106 )
                  v8 = 0;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    if ( (v18 & 0x400) == 0 )
      goto LABEL_9;
    if ( DWORD1(v18) == -1610612724 )
    {
      v8 = 4;
      goto LABEL_19;
    }
    if ( DWORD1(v18) == -1610612733 )
      v8 = 10;
    else
LABEL_9:
      v8 = (unsigned __int128)(v18 & 0x10 | 0x20) >> 4;
  }
LABEL_19:
  *(_DWORD *)v17 = v7;
  *(_QWORD *)&v17[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( (_DWORD)v8 )
  {
    v15 = (_DWORD)v8 != 1;
  }
  else
  {
    v15 = 0;
    if ( v7 )
      std::filesystem::_Throw_fs_error((std::filesystem *)v8, v17, (const struct std::error_code *)lpFileName, v6);
  }
  if ( v15 )
  {
    std::filesystem::path::path(this, (const struct std::filesystem::path *)lpFileName);
    *((_BYTE *)this + 32) = 1;
  }
  else
  {
    *((_BYTE *)this + 32) = 0;
  }
  std::wstring::~wstring(lpFileName);
  return this;
}

```

## disassembly

```asm
0x18000993c  mov     [rsp-8+arg_10], rbx
0x180009941  mov     [rsp-8+arg_18], rdi
0x180009946  push    rbp
0x180009947  lea     rbp, [rsp-57h]
0x18000994c  sub     rsp, 0A0h
0x180009953  mov     rax, cs:__security_cookie
0x18000995a  xor     rax, rsp
0x18000995d  mov     [rbp+57h+var_10], rax
0x180009961  mov     rbx, rdx
0x180009964  mov     rdi, rcx
0x180009967  mov     qword ptr [rbp+57h+var_70], rcx
0x18000996b  lea     rax, aUusbrainDll; "uusbrain.dll"
0x180009972  mov     qword ptr [rbp+57h+var_70], rax
0x180009976  mov     qword ptr [rbp+57h+var_70+8], 0Ch
0x18000997e  lea     rdx, [rbp+57h+var_70]
0x180009982  lea     rcx, [rbp+57h+var_30]; void *
0x180009986  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18000998b  nop
0x18000998c  lea     r8, [rbp+57h+var_30]; this
0x180009990  mov     rdx, rbx; struct std::filesystem::path *
0x180009993  lea     rcx, [rbp+57h+lpFileName]; Src
0x180009997  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000999c  nop
0x18000999d  lea     rcx, [rbp+57h+var_30]
0x1800099a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800099a6  xorps   xmm0, xmm0
0x1800099a9  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800099ad  movups  [rbp+57h+var_60], xmm0
0x1800099b1  lea     rcx, [rbp+57h+lpFileName]
0x1800099b5  cmp     [rbp+57h+var_38], 7
0x1800099ba  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1800099bf  or      r9d, 0FFFFFFFFh
0x1800099c3  mov     r8d, 3
0x1800099c9  lea     rdx, [rbp+57h+var_70]
0x1800099cd  call    __std_fs_get_stats
0x1800099d2  mov     edx, eax
0x1800099d4  test    eax, eax
0x1800099d6  jnz     short loc_180009A0A
0x1800099d8  mov     ecx, dword ptr [rbp+57h+var_60]
0x1800099db  bt      ecx, 0Ah
0x1800099df  jnb     short loc_1800099FF
0x1800099e1  cmp     dword ptr [rbp+57h+var_60+4], 0A000000Ch
0x1800099e8  jnz     short loc_1800099EF
0x1800099ea  lea     ecx, [rax+4]
0x1800099ed  jmp     short loc_180009A36
0x1800099ef  cmp     dword ptr [rbp+57h+var_60+4], 0A0000003h
0x1800099f6  jnz     short loc_1800099FF
0x1800099f8  mov     ecx, 0Ah
0x1800099fd  jmp     short loc_180009A36
0x1800099ff  and     ecx, 10h
0x180009a02  or      ecx, 20h
0x180009a05  shr     ecx, 4
0x180009a08  jmp     short loc_180009A36
0x180009a0a  sub     eax, 2
0x180009a0d  jz      short loc_180009A31
0x180009a0f  sub     eax, 1
0x180009a12  jz      short loc_180009A31
0x180009a14  sub     eax, 32h ; '2'
0x180009a17  jz      short loc_180009A31
0x180009a19  sub     eax, 0Bh
0x180009a1c  jz      short loc_180009A31
0x180009a1e  sub     eax, 3Bh ; ';'
0x180009a21  jz      short loc_180009A31
0x180009a23  sub     eax, 26h ; '&'
0x180009a26  jz      short loc_180009A31
0x180009a28  cmp     eax, 6Ah ; 'j'
0x180009a2b  jz      short loc_180009A31
0x180009a2d  xor     ecx, ecx
0x180009a2f  jmp     short loc_180009A36
0x180009a31  mov     ecx, 1; this
0x180009a36  mov     dword ptr [rbp+57h+var_70], edx
0x180009a39  mov     eax, dword ptr [rbp+57h+var_70+4]
0x180009a3c  mov     dword ptr [rbp+57h+var_70+4], eax
0x180009a3f  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180009a46  mov     qword ptr [rbp+57h+var_70+8], rax
0x180009a4a  test    ecx, ecx
0x180009a4c  jz      short loc_180009A6A
0x180009a4e  cmp     ecx, 1
0x180009a51  setnz   al
0x180009a54  test    al, al
0x180009a56  jz      short loc_180009A72
0x180009a58  lea     rdx, [rbp+57h+lpFileName]; struct std::filesystem::path *
0x180009a5c  mov     rcx, rdi; this
0x180009a5f  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180009a64  mov     byte ptr [rdi+20h], 1
0x180009a68  jmp     short loc_180009A76
0x180009a6a  xor     al, al
0x180009a6c  test    edx, edx
0x180009a6e  jnz     short loc_180009AA3
0x180009a70  jmp     short loc_180009A54
0x180009a72  mov     byte ptr [rdi+20h], 0
0x180009a76  lea     rcx, [rbp+57h+lpFileName]
0x180009a7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009a7f  mov     rax, rdi
0x180009a82  mov     rcx, [rbp+57h+var_10]
0x180009a86  xor     rcx, rsp; StackCookie
0x180009a89  call    __security_check_cookie
0x180009a8e  lea     r11, [rsp+0A0h+var_s0]
0x180009a96  mov     rbx, [r11+20h]
0x180009a9a  mov     rdi, [r11+28h]
0x180009a9e  mov     rsp, r11
0x180009aa1  pop     rbp
0x180009aa2  retn
0x180009aa3  lea     r8, [rbp+57h+lpFileName]; struct std::error_code *
0x180009aa7  lea     rdx, [rbp+57h+var_70]; char *
0x180009aab  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
