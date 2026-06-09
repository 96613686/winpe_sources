# std::sys::stdio::windows::write

- ea: `0x1800d7060`
- end: `0x1800d73fb`
- name: `std::sys::stdio::windows::write`
- size: `923`
- prototype: `__int64 __fastcall(PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d6e40`

## callees

- `0x180024ce0`
- `0x1800d6c60`
- `0x1800d6de0`
- `0x1800d7060`
- `0x1800d7440`
- `0x180316940`
- `0x180316a30`
- `0x180316ee0`
- `0x18031716c`

## import_xrefs

- `kernel32!GetLastError` at `0x1800d70a9`
- `kernel32!GetLastError` at `0x1800d70a9`
- `ntdll!RtlNtStatusToDosError` at `0x1800d71b5`
- `ntdll!RtlNtStatusToDosError` at `0x1800d71b5`
- `ntdll!NtWriteFile` at `0x1800d712d`
- `ntdll!NtWriteFile` at `0x1800d712d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d7142`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d7142`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800d7090`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800d7090`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x1800d70da`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x1800d70da`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x1800d70e4`
- `api-ms-win-core-console-l1-1-0!GetConsoleOutputCP` at `0x1800d70e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::sys::stdio::windows::write(char *Buffer, unsigned __int64 Length, unsigned __int8 *a3)
{
  HANDLE StdHandle; // r14
  __int64 result; // rax
  ULONG v8; // eax
  int v9; // eax
  __int64 v10; // rax
  unsigned __int8 v11; // al
  unsigned __int64 v12; // rsi
  __int128 v13; // kr00_16
  __int64 v14; // rdx
  char v15; // cl
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-20h] BYREF
  DWORD Mode[2]; // [rsp+70h] [rbp-10h] BYREF
  __int128 v22; // [rsp+78h] [rbp-8h]
  __int128 v23; // [rsp+88h] [rbp+8h]
  __int128 v24; // [rsp+A0h] [rbp+20h] BYREF
  _BYTE IoStatusBlock[24]; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+48h]

  v26 = -2;
  if ( !Length )
    return 0;
  StdHandle = GetStdHandle(0xFFFFFFF4);
  result = 1;
  if ( !StdHandle )
    return result;
  if ( StdHandle == (HANDLE)-1LL )
  {
    GetLastError();
    return 1;
  }
  Mode[0] = 0;
  if ( !GetConsoleMode(StdHandle, Mode) || GetConsoleOutputCP() == 65001 )
  {
    *(_OWORD *)IoStatusBlock = xmmword_1803D7E10;
    v8 = -1;
    if ( Length < 0xFFFFFFFF )
      v8 = Length;
    v9 = NtWriteFile(StdHandle, 0, 0, 0, (PIO_STATUS_BLOCK)IoStatusBlock, Buffer, v8, 0, 0);
    if ( v9 == 259 )
    {
      WaitForSingleObject(StdHandle, 0xFFFFFFFF);
      v9 = *(_DWORD *)IoStatusBlock;
      if ( *(_DWORD *)IoStatusBlock == 259 )
      {
        v20[1] = StdHandle;
        LODWORD(v24) = 0;
        BYTE4(v24) = 0;
        *(_QWORD *)Mode = &off_180343A88;
        *(_QWORD *)&v22 = 1;
        *((_QWORD *)&v22 + 1) = 8;
        v23 = 0;
        v17 = std::io::Write::write_fmt_std::sys::stdio::windows::Stderr_(&v24, Mode);
        core::ptr::drop_in_place_enum2__core::result::Result_tuple____std::io::error::Error_____(v17);
        __fastfail(7u);
      }
    }
    if ( v9 >= 0 )
      return 0;
    RtlNtStatusToDosError(v9);
    return 1;
  }
  v10 = a3[4];
  if ( !a3[4] )
  {
    core::str::converts::from_utf8(IoStatusBlock);
    if ( (IoStatusBlock[0] & 1) != 0 )
    {
      if ( !*(_QWORD *)&IoStatusBlock[8] )
      {
        v16 = (unsigned __int8)*Buffer;
        if ( Length < (unsigned __int8)byte_1803D7EFD[v16] )
        {
          *a3 = v16;
          a3[4] = 1;
          return 0;
        }
        return 1;
      }
      if ( *(_QWORD *)&IoStatusBlock[8] > Length )
        core::slice::index::slice_end_index_len_fail(*(_QWORD *)&IoStatusBlock[8], Length, &off_180343B50);
      core::str::converts::from_utf8(Mode);
      if ( Mode[0] == 1 )
      {
        v24 = v22;
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)&v24,
          (unsigned int)&qword_180343498,
          (__int64)&off_180343B68);
      }
      v13 = v22;
    }
    else
    {
      v13 = *(_OWORD *)&IoStatusBlock[8];
    }
    return std::sys::stdio::windows::write_valid_utf8_to_console(
             StdHandle,
             (const CHAR *)v13,
             *((unsigned __int64 *)&v13 + 1));
  }
  if ( (unsigned __int8)v10 >= 4u )
  {
    *(_QWORD *)Mode = &off_180343B28;
    *(_QWORD *)&v22 = 1;
    *((_QWORD *)&v22 + 1) = 8;
    v23 = 0;
    core::panicking::panic_fmt(Mode, &off_180343B80);
  }
  if ( *Buffer >= -64 )
  {
    a3[4] = 0;
    return 1;
  }
  a3[v10] = *Buffer;
  v11 = a3[4] + 1;
  a3[4] = v11;
  v12 = (unsigned __int8)byte_1803D7EFD[*a3];
  v20[0] = v12;
  if ( v11 < (unsigned __int8)v12 )
    return 0;
  if ( v11 >= 5u )
    core::slice::index::slice_end_index_len_fail(v11, 4, &off_180343B98);
  core::str::converts::from_utf8(IoStatusBlock);
  a3[4] = 0;
  if ( (IoStatusBlock[0] & 1) != 0 )
    return 1;
  v19 = *(_QWORD *)&IoStatusBlock[16];
  if ( *(_QWORD *)&IoStatusBlock[16] != v12 )
  {
    *(_QWORD *)Mode = 0;
    core::panicking::assert_failed_usize_usize_(v20, &v19, Mode, &off_180343BB0);
  }
  v15 = std::sys::stdio::windows::write_valid_utf8_to_console(StdHandle, *(const CHAR **)&IoStatusBlock[8], v12);
  result = 1;
  if ( (v15 & 1) == 0 )
  {
    v18 = v14;
    *(_QWORD *)&v24 = v12;
    if ( v12 != v14 )
    {
      *(_QWORD *)Mode = 0;
      core::panicking::assert_failed_usize_usize_(&v18, &v24, Mode, &off_180343BC8);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800d7060  push    rbp
0x1800d7061  push    r14
0x1800d7063  push    rsi
0x1800d7064  push    rdi
0x1800d7065  push    rbx
0x1800d7066  sub     rsp, 0D0h
0x1800d706d  lea     rbp, [rsp+80h]
0x1800d7075  mov     [rbp+70h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800d707d  test    rdx, rdx
0x1800d7080  jz      short loc_1800D70B4
0x1800d7082  mov     rdi, rdx
0x1800d7085  mov     rsi, rcx
0x1800d7088  mov     rbx, r8
0x1800d708b  mov     ecx, 0FFFFFFF4h; nStdHandle
0x1800d7090  call    cs:__imp_GetStdHandle
0x1800d7096  mov     r14, rax
0x1800d7099  mov     eax, 1
0x1800d709e  test    r14, r14
0x1800d70a1  jz      short loc_1800D70BD
0x1800d70a3  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800d70a7  jnz     short loc_1800D70CC
0x1800d70a9  call    cs:__imp_GetLastError
0x1800d70af  jmp     loc_1800D71BB
0x1800d70b4  xor     edx, edx
0x1800d70b6  xor     eax, eax
0x1800d70b8  jmp     loc_1800D71CA
0x1800d70bd  mov     rdx, 600000002h
0x1800d70c7  jmp     loc_1800D71CA
0x1800d70cc  mov     [rbp+70h+Mode], 0
0x1800d70d3  lea     rdx, [rbp+70h+Mode]; lpMode
0x1800d70d7  mov     rcx, r14; hConsoleHandle
0x1800d70da  call    cs:__imp_GetConsoleMode
0x1800d70e0  test    eax, eax
0x1800d70e2  jz      short loc_1800D70F1
0x1800d70e4  call    cs:__imp_GetConsoleOutputCP
0x1800d70ea  cmp     eax, 0FDE9h
0x1800d70ef  jnz     short loc_1800D7162
0x1800d70f1  movups  xmm0, cs:xmmword_1803D7E10
0x1800d70f8  movaps  xmmword ptr [rbp+70h+var_40], xmm0
0x1800d70fc  mov     eax, 0FFFFFFFFh
0x1800d7101  cmp     rdi, rax
0x1800d7104  cmovb   rax, rdi
0x1800d7108  xorps   xmm0, xmm0
0x1800d710b  movups  xmmword ptr [rsp+0F0h+ByteOffset], xmm0; ByteOffset
0x1800d7110  mov     [rsp+0F0h+Length], eax; Length
0x1800d7114  mov     [rsp+0F0h+Buffer], rsi; Buffer
0x1800d7119  lea     rax, [rbp+70h+var_40]
0x1800d711d  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x1800d7122  mov     rcx, r14; FileHandle
0x1800d7125  xor     edx, edx; Event
0x1800d7127  xor     r8d, r8d; ApcRoutine
0x1800d712a  xor     r9d, r9d; ApcContext
0x1800d712d  call    cs:__imp_NtWriteFile
0x1800d7133  cmp     eax, 103h
0x1800d7138  jnz     short loc_1800D7156
0x1800d713a  mov     rcx, r14; hHandle
0x1800d713d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800d7142  call    cs:__imp_WaitForSingleObject
0x1800d7148  mov     eax, dword ptr [rbp+70h+var_40]
0x1800d714b  cmp     eax, 103h
0x1800d7150  jz      loc_1800D73AC
0x1800d7156  test    eax, eax
0x1800d7158  js      short loc_1800D71B3
0x1800d715a  mov     rdx, [rbp+70h+var_40.Information]
0x1800d715e  xor     eax, eax
0x1800d7160  jmp     short loc_1800D71CA
0x1800d7162  movzx   eax, byte ptr [rbx+4]
0x1800d7166  test    rax, rax
0x1800d7169  jz      short loc_1800D71D8
0x1800d716b  cmp     al, 4
0x1800d716d  jnb     loc_1800D72FE
0x1800d7173  mov     rdx, rbx
0x1800d7176  movzx   ecx, byte ptr [rsi]
0x1800d7179  cmp     cl, 0C0h
0x1800d717c  jge     loc_1800D7231
0x1800d7182  mov     [rdx+rax], cl
0x1800d7185  movzx   eax, byte ptr [rdx+4]
0x1800d7189  inc     al
0x1800d718b  mov     [rdx+4], al
0x1800d718e  movzx   ecx, byte ptr [rdx]
0x1800d7191  lea     r8, byte_1803D7EFD
0x1800d7198  movzx   esi, byte ptr [rcx+r8]
0x1800d719d  mov     [rbp+70h+var_90], rsi
0x1800d71a1  cmp     al, sil
0x1800d71a4  jnb     loc_1800D7258
0x1800d71aa  mov     edx, 1
0x1800d71af  xor     eax, eax
0x1800d71b1  jmp     short loc_1800D71CA
0x1800d71b3  mov     ecx, eax; Status
0x1800d71b5  call    cs:__imp_RtlNtStatusToDosError
0x1800d71bb  mov     edx, eax
0x1800d71bd  shl     rdx, 20h
0x1800d71c1  or      rdx, 2
0x1800d71c5  mov     eax, 1
0x1800d71ca  add     rsp, 0D0h
0x1800d71d1  pop     rbx
0x1800d71d2  pop     rdi
0x1800d71d3  pop     rsi
0x1800d71d4  pop     r14
0x1800d71d6  pop     rbp
0x1800d71d7  retn
0x1800d71d8  cmp     rdi, 1000h
0x1800d71df  mov     r8d, 1000h
0x1800d71e5  cmovb   r8, rdi
0x1800d71e9  lea     rcx, [rbp+70h+var_40]
0x1800d71ed  mov     rdx, rsi
0x1800d71f0  call    core__str__converts__from_utf8
0x1800d71f5  test    byte ptr [rbp+70h+var_40], 1
0x1800d71f9  jz      short loc_1800D7243
0x1800d71fb  mov     r8, [rbp+70h+var_40.Information]
0x1800d71ff  test    r8, r8
0x1800d7202  jz      loc_1800D72DC
0x1800d7208  cmp     r8, rdi
0x1800d720b  ja      loc_1800D7347
0x1800d7211  lea     rcx, [rbp+70h+Mode]
0x1800d7215  mov     rdx, rsi
0x1800d7218  call    core__str__converts__from_utf8
0x1800d721d  cmp     [rbp+70h+Mode], 1
0x1800d7221  jz      loc_1800D735C
0x1800d7227  mov     rdx, qword ptr [rbp+70h+var_78]
0x1800d722b  mov     r8, qword ptr [rbp+70h+var_78+8]
0x1800d722f  jmp     short loc_1800D724B
0x1800d7231  mov     byte ptr [rdx+4], 0
0x1800d7235  mov     eax, 1
0x1800d723a  lea     rdx, off_180343B38; "Windows stdio in console mode does not "...
0x1800d7241  jmp     short loc_1800D71CA
0x1800d7243  mov     rdx, [rbp+70h+var_40.Information]
0x1800d7247  mov     r8, [rbp+70h+var_30]
0x1800d724b  mov     rcx, r14
0x1800d724e  call    std__sys__stdio__windows__write_valid_utf8_to_console
0x1800d7253  jmp     loc_1800D71CA
0x1800d7258  movzx   r8d, al
0x1800d725c  cmp     al, 5
0x1800d725e  jnb     loc_1800D7330
0x1800d7264  lea     rcx, [rbp+70h+var_40]
0x1800d7268  mov     rdi, rdx
0x1800d726b  call    core__str__converts__from_utf8
0x1800d7270  mov     byte ptr [rdi+4], 0
0x1800d7274  test    byte ptr [rbp+70h+var_40], 1
0x1800d7278  jnz     short loc_1800D7235
0x1800d727a  mov     rdx, [rbp+70h+var_40.Information]
0x1800d727e  mov     rax, [rbp+70h+var_30]
0x1800d7282  mov     [rbp+70h+var_98], rax
0x1800d7286  cmp     rax, rsi
0x1800d7289  jnz     loc_1800D738C
0x1800d728f  mov     rcx, r14
0x1800d7292  mov     r8, rsi
0x1800d7295  call    std__sys__stdio__windows__write_valid_utf8_to_console
0x1800d729a  mov     rcx, rax
0x1800d729d  mov     eax, 1
0x1800d72a2  test    cl, 1
0x1800d72a5  jnz     loc_1800D71CA
0x1800d72ab  mov     [rbp+70h+var_A0], rdx
0x1800d72af  mov     qword ptr [rbp+70h+var_50], rsi
0x1800d72b3  cmp     rsi, rdx
0x1800d72b6  jz      loc_1800D71AA
0x1800d72bc  mov     qword ptr [rbp+70h+Mode], 0
0x1800d72c4  lea     r9, off_180343BC8; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d72cb  lea     rcx, [rbp+70h+var_A0]
0x1800d72cf  lea     rdx, [rbp+70h+var_50]
0x1800d72d3  lea     r8, [rbp+70h+Mode]
0x1800d72d7  call    core__panicking__assert_failed_usize_usize_
0x1800d72dc  movzx   eax, byte ptr [rsi]
0x1800d72df  lea     rcx, byte_1803D7EFD
0x1800d72e6  movzx   ecx, byte ptr [rax+rcx]
0x1800d72ea  cmp     rdi, rcx
0x1800d72ed  jnb     loc_1800D7235
0x1800d72f3  mov     [rbx], al
0x1800d72f5  mov     byte ptr [rbx+4], 1
0x1800d72f9  jmp     loc_1800D71AA
0x1800d72fe  lea     rax, off_180343B28
0x1800d7305  mov     qword ptr [rbp+70h+Mode], rax
0x1800d7309  mov     qword ptr [rbp+70h+var_78], 1
0x1800d7311  mov     qword ptr [rbp+70h+var_78+8], 8
0x1800d7319  xorps   xmm0, xmm0
0x1800d731c  movups  [rbp+70h+var_68], xmm0
0x1800d7320  lea     rdx, off_180343B80; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d7327  lea     rcx, [rbp+70h+Mode]
0x1800d732b  call    core__panicking__panic_fmt
0x1800d7330  lea     rax, off_180343B98; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d7337  mov     edx, 4
0x1800d733c  mov     rcx, r8
0x1800d733f  mov     r8, rax
0x1800d7342  call    core__slice__index__slice_end_index_len_fail
0x1800d7347  lea     rax, off_180343B50; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d734e  mov     rcx, r8
0x1800d7351  mov     rdx, rdi
0x1800d7354  mov     r8, rax
0x1800d7357  call    core__slice__index__slice_end_index_len_fail
0x1800d735c  movups  xmm0, [rbp+70h+var_78]
0x1800d7360  movaps  [rbp+70h+var_50], xmm0
0x1800d7364  lea     rax, off_180343B68; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d736b  mov     [rsp+0F0h+IoStatusBlock], rax
0x1800d7370  lea     rcx, aAssertionFaile_1+1Eh; "called `Result::unwrap()` on an `Err` v"...
0x1800d7377  lea     r9, qword_180343498
0x1800d737e  lea     r8, [rbp+70h+var_50]
0x1800d7382  mov     edx, 2Bh ; '+'
0x1800d7387  call    core__result__unwrap_failed
0x1800d738c  mov     qword ptr [rbp+70h+Mode], 0
0x1800d7394  lea     r9, off_180343BB0; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d739b  lea     rcx, [rbp+70h+var_90]
0x1800d739f  lea     rdx, [rbp+70h+var_98]
0x1800d73a3  lea     r8, [rbp+70h+Mode]
0x1800d73a7  call    core__panicking__assert_failed_usize_usize_
0x1800d73ac  mov     [rbp+70h+var_88], r14
0x1800d73b0  mov     dword ptr [rbp+70h+var_50], 0
0x1800d73b7  mov     byte ptr [rbp+70h+var_50+4], 0
0x1800d73bb  lea     rax, off_180343A88; "fatal runtime error: I/O error: operati"...
0x1800d73c2  mov     qword ptr [rbp+70h+Mode], rax
0x1800d73c6  mov     qword ptr [rbp+70h+var_78], 1
0x1800d73ce  mov     qword ptr [rbp+70h+var_78+8], 8
0x1800d73d6  xorps   xmm0, xmm0
0x1800d73d9  movups  [rbp+70h+var_68], xmm0
0x1800d73dd  lea     rcx, [rbp+70h+var_50]
0x1800d73e1  lea     rdx, [rbp+70h+Mode]
0x1800d73e5  call    std__io__Write__write_fmt_std__sys__stdio__windows__Stderr_
0x1800d73ea  mov     rcx, rax
0x1800d73ed  call    core__ptr__drop_in_place_enum2$_core__result__Result_tuple$___std__io__error__Error_____
0x1800d73f2  mov     ecx, 7
0x1800d73f7  int     29h; Win8: RtlFailFast(ecx)
0x1800d73f9  ud2
```
