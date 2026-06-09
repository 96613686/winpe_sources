# common_stat<_stat64>(wchar_t const * const,_stat64 * const)

- ea: `0x140130d68`
- end: `0x140130f05`
- name: `??$common_stat@U_stat64@@@@YAHQEB_WQEAU_stat64@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140130a1c`

## callees

- `0x14011d198`
- `0x1401302f8`
- `0x14013031c`
- `0x140130a24`
- `0x140130b60`
- `0x140130bc0`
- `0x140130d68`
- `0x140130f08`
- `0x1401427ac`
- `0x140147c5c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140130e2f`
- `KERNEL32!CloseHandle` at `0x140130e37`
- `KERNEL32!CloseHandle` at `0x140130e2f`
- `KERNEL32!CloseHandle` at `0x140130e37`
- `KERNEL32!CreateFileW` at `0x140130de8`
- `KERNEL32!CreateFileW` at `0x140130de8`

## pseudocode

```c
__int64 __fastcall common_stat<_stat64>(wchar_t *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  HANDLE FileW; // rbx
  unsigned __int16 v11; // ax
  int v12; // eax
  __int64 v13; // rax
  int v14; // [rsp+98h] [rbp+10h] BYREF

  if ( !a2 || (*(_OWORD *)a2 = 0, *(_OWORD *)(a2 + 16) = 0, *(_OWORD *)(a2 + 32) = 0, *(_QWORD *)(a2 + 48) = 0, !a1) )
  {
    *(_DWORD *)sub_1401302F8(a1, a2, a3, a4) = 0;
    *(_DWORD *)sub_14011D198(v7, v6, v8) = 22;
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  FileW = CreateFileW(a1, 0x80u, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( is_usable_drive_or_unc_root(a1) )
    {
      v11 = convert_to_stat_mode(16, a1);
      v14 = 0;
      *(_WORD *)(a2 + 6) = v11;
      *(_WORD *)(a2 + 8) = 1;
      if ( get_drive_number_from_path(a1, &v14) )
      {
        v12 = v14 - 1;
        *(_DWORD *)(a2 + 16) = v14 - 1;
        *(_DWORD *)a2 = v12;
        v13 = sub_140147C5C(1980, 1, 1, 0, 0, 0, -1);
        *(_QWORD *)(a2 + 40) = v13;
        *(_QWORD *)(a2 + 32) = v13;
        *(_QWORD *)(a2 + 48) = v13;
        return 0;
      }
    }
    else
    {
      sub_14013031C(2);
    }
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_OWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    return 0xFFFFFFFFLL;
  }
  if ( !(unsigned __int8)common_stat_handle_file_opened<_stat64>(a1) )
  {
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_OWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    CloseHandle(FileW);
    return 0xFFFFFFFFLL;
  }
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x140130d68  mov     [rsp+arg_0], rbx
0x140130d6d  mov     [rsp+arg_10], rsi
0x140130d72  push    rdi
0x140130d73  sub     rsp, 80h
0x140130d7a  mov     rdi, rdx
0x140130d7d  mov     rsi, rcx
0x140130d80  test    rdx, rdx
0x140130d83  jnz     short loc_140130DA2
0x140130d85  call    sub_1401302F8
0x140130d8a  and     dword ptr [rax], 0
0x140130d8d  call    sub_14011D198
0x140130d92  mov     dword ptr [rax], 16h
0x140130d98  call    _invalid_parameter_noinfo
0x140130d9d  jmp     loc_140130E75
0x140130da2  xorps   xmm0, xmm0
0x140130da5  xor     eax, eax
0x140130da7  mov     [rsp+88h+var_18], rax
0x140130dac  movups  xmmword ptr [rdx], xmm0
0x140130daf  movups  xmmword ptr [rdx+10h], xmm0
0x140130db3  movups  xmmword ptr [rdx+20h], xmm0
0x140130db7  movsd   xmm0, [rsp+88h+var_18]
0x140130dbd  movsd   qword ptr [rdx+30h], xmm0
0x140130dc2  test    rsi, rsi
0x140130dc5  jz      short loc_140130D85
0x140130dc7  and     [rsp+88h+var_58], rax
0x140130dcc  lea     r8d, [rax+7]; dwShareMode
0x140130dd0  mov     [rsp+88h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140130dd8  xor     r9d, r9d; lpSecurityAttributes
0x140130ddb  mov     edx, 80h; dwDesiredAccess
0x140130de0  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x140130de8  call    cs:CreateFileW
0x140130dee  mov     rbx, rax
0x140130df1  mov     rcx, rsi; Path
0x140130df4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140130df8  jz      short loc_140130E42
0x140130dfa  mov     r9, rdi
0x140130dfd  mov     r8, rax
0x140130e00  or      edx, 0FFFFFFFFh
0x140130e03  call    ??$common_stat_handle_file_opened@U_stat64@@@@YA_NQEB_WHQEAXAEAU_stat64@@@Z
0x140130e08  mov     rcx, rbx; hObject
0x140130e0b  test    al, al
0x140130e0d  jnz     short loc_140130E37
0x140130e0f  xorps   xmm0, xmm0
0x140130e12  xor     eax, eax
0x140130e14  movups  xmmword ptr [rdi], xmm0
0x140130e17  mov     [rsp+88h+var_18], rax
0x140130e1c  movups  xmmword ptr [rdi+10h], xmm0
0x140130e20  movups  xmmword ptr [rdi+20h], xmm0
0x140130e24  movsd   xmm0, [rsp+88h+var_18]
0x140130e2a  movsd   qword ptr [rdi+30h], xmm0
0x140130e2f  call    cs:__imp_CloseHandle
0x140130e35  jmp     short loc_140130E75
0x140130e37  call    cs:__imp_CloseHandle
0x140130e3d  jmp     loc_140130EFE
0x140130e42  call    ?is_usable_drive_or_unc_root@@YA_NQEB_W@Z
0x140130e47  test    al, al
0x140130e49  jnz     short loc_140130E8D
0x140130e4b  mov     ecx, 2
0x140130e50  call    sub_14013031C
0x140130e55  xorps   xmm0, xmm0
0x140130e58  xor     eax, eax
0x140130e5a  movups  xmmword ptr [rdi], xmm0
0x140130e5d  mov     [rsp+88h+var_18], rax
0x140130e62  movups  xmmword ptr [rdi+10h], xmm0
0x140130e66  movups  xmmword ptr [rdi+20h], xmm0
0x140130e6a  movsd   xmm0, [rsp+88h+var_18]
0x140130e70  movsd   qword ptr [rdi+30h], xmm0
0x140130e75  or      eax, 0FFFFFFFFh
0x140130e78  lea     r11, [rsp+88h+var_8]
0x140130e80  mov     rbx, [r11+10h]
0x140130e84  mov     rsi, [r11+20h]
0x140130e88  mov     rsp, r11
0x140130e8b  pop     rdi
0x140130e8c  retn
0x140130e8d  mov     rdx, rsi; wchar_t *
0x140130e90  mov     ecx, 10h; int
0x140130e95  call    ?convert_to_stat_mode@@YAGHQEB_W@Z
0x140130e9a  and     [rsp+88h+arg_8], 0
0x140130ea2  lea     rdx, [rsp+88h+arg_8]; int *
0x140130eaa  mov     ebx, 1
0x140130eaf  mov     [rdi+6], ax
0x140130eb3  mov     rcx, rsi; wchar_t *
0x140130eb6  mov     [rdi+8], bx
0x140130eba  call    ?get_drive_number_from_path@@YA_NQEB_WAEAH@Z
0x140130ebf  test    al, al
0x140130ec1  jz      short loc_140130E55
0x140130ec3  or      dword ptr [rsp+88h+var_58], 0FFFFFFFFh
0x140130ec8  xor     r9d, r9d
0x140130ecb  mov     eax, [rsp+88h+arg_8]
0x140130ed2  mov     r8d, ebx
0x140130ed5  and     [rsp+88h+dwFlagsAndAttributes], 0
0x140130eda  dec     eax
0x140130edc  and     [rsp+88h+dwCreationDisposition], 0
0x140130ee1  mov     edx, ebx
0x140130ee3  mov     ecx, 7BCh
0x140130ee8  mov     [rdi+10h], eax
0x140130eeb  mov     [rdi], eax
0x140130eed  call    sub_140147C5C
0x140130ef2  mov     [rdi+28h], rax
0x140130ef6  mov     [rdi+20h], rax
0x140130efa  mov     [rdi+30h], rax
0x140130efe  xor     eax, eax
0x140130f00  jmp     loc_140130E78
```
