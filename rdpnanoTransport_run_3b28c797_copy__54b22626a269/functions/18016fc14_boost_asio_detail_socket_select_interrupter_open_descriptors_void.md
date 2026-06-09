# boost::asio::detail::socket_select_interrupter::open_descriptors(void)

- ea: `0x18016fc14`
- end: `0x18017014a`
- name: `?open_descriptors@socket_select_interrupter@detail@asio@boost@@AEAAXXZ`
- size: `1334`
- prototype: `void __fastcall(boost::asio::detail::socket_select_interrupter *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x180164258`
- `0x18016d500`

## callees

- `0x18016a3cc`
- `0x18016aba8`
- `0x18016b440`
- `0x18016bbdc`
- `0x18016dbe4`
- `0x18016e61c`
- `0x18016ef1c`
- `0x18016f0e8`
- `0x18016fc14`
- `0x180171c20`
- `0x1801722a0`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18016fd14`
- `WS2_32!__imp_htonl` at `0x18016fdb5`
- `WS2_32!__imp_htonl` at `0x18016fdc5`
- `WS2_32!__imp_htonl` at `0x18016fd14`
- `WS2_32!__imp_htonl` at `0x18016fdb5`
- `WS2_32!__imp_htonl` at `0x18016fdc5`

## string_xrefs

- `0x18016fc85`: `void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)`
- `0x18016fed2`: `void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)`
- `0x18016ff34`: `void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)`
- `0x18016ffca`: `void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)`
- `0x18016fc7e`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\boost/asio/detail/impl/socket_select_interrupter.ipp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall boost::asio::detail::socket_select_interrupter::open_descriptors(
        boost::asio::detail::socket_select_interrupter *this)
{
  void *v2; // rbx
  const struct boost::source_location *v3; // r9
  const struct boost::source_location *v4; // r9
  const struct boost::source_location *v5; // r9
  struct boost::system::error_code *v6; // r9
  const struct boost::source_location *v7; // r9
  boost::asio::detail::socket_ops *v8; // rax
  const struct boost::source_location *v9; // r9
  boost::asio::detail::socket_ops *v10; // rdi
  const struct boost::source_location *v11; // r9
  void *v12; // rsi
  const struct boost::source_location *v13; // r9
  const struct boost::source_location *v14; // r9
  const struct boost::source_location *v15; // r9
  unsigned __int8 *v16; // r8
  struct boost::system::error_code *v17; // [rsp+20h] [rbp-59h]
  struct boost::system::error_code *v18; // [rsp+20h] [rbp-59h]
  struct boost::system::error_code *v19; // [rsp+20h] [rbp-59h]
  struct boost::system::error_code *v20; // [rsp+20h] [rbp-59h]
  struct boost::system::error_code *v21; // [rsp+20h] [rbp-59h]
  struct boost::system::error_code *v22; // [rsp+20h] [rbp-59h]
  struct boost::system::error_code *v23; // [rsp+20h] [rbp-59h]
  struct boost::system::error_code *v24; // [rsp+28h] [rbp-51h]
  struct boost::system::error_code *v25; // [rsp+28h] [rbp-51h]
  struct boost::system::error_code *v26; // [rsp+38h] [rbp-41h]
  struct boost::system::error_code *v27; // [rsp+38h] [rbp-41h]
  struct boost::system::error_code *v28; // [rsp+38h] [rbp-41h]
  unsigned __int64 v29; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v30[4]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v31; // [rsp+58h] [rbp-21h]
  void *v32[3]; // [rsp+60h] [rbp-19h] BYREF
  bool v33[16]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v34; // [rsp+88h] [rbp+Fh]
  char optval[4]; // [rsp+90h] [rbp+17h] BYREF
  int v36; // [rsp+94h] [rbp+1Bh] BYREF
  _WORD v37[2]; // [rsp+98h] [rbp+1Fh] BYREF
  u_long v38; // [rsp+9Ch] [rbp+23h]
  __int64 v39; // [rsp+A0h] [rbp+27h]

  *(_OWORD *)v30 = 0;
  v31 = 0;
  v2 = (void *)boost::asio::detail::socket_ops::socket((boost::asio::detail::socket_ops *)2, 1, 6, (int)v30, v17);
  v32[1] = v2;
  if ( v2 == (void *)-1LL )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A00000032LL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v3);
  }
  *(_DWORD *)optval = 1;
  LOBYTE(v29) = 0;
  boost::asio::detail::socket_ops::setsockopt(
    (boost::asio::detail::socket_ops *)v2,
    (unsigned __int64)&v29,
    (unsigned __int8 *)0xFFFF,
    4,
    optval,
    (const void *)4,
    (unsigned __int64)v30,
    v26);
  v32[0] = (void *)16;
  v39 = 0;
  v37[0] = 2;
  v38 = htonl(0x7F000001u);
  v37[1] = 0;
  if ( (unsigned int)boost::asio::detail::socket_ops::bind(
                       (boost::asio::detail::socket_ops *)v2,
                       (unsigned __int64)v37,
                       (const void *)0x10,
                       (unsigned __int64)v30,
                       v18) == -1 )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A00000042LL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v4);
  }
  if ( (unsigned int)boost::asio::detail::socket_ops::getsockname(
                       (boost::asio::detail::socket_ops *)v2,
                       (unsigned __int64)v37,
                       v32,
                       (unsigned __int64 *)v30,
                       v19) == -1 )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A00000046LL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v5);
  }
  if ( v38 == htonl(0) )
    v38 = htonl(0x7F000001u);
  if ( (unsigned int)boost::asio::detail::socket_ops::listen(
                       (boost::asio::detail::socket_ops *)v2,
                       0x7FFFFFFFu,
                       (int)v30,
                       v6) == -1 )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A00000050LL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v7);
  }
  v8 = (boost::asio::detail::socket_ops *)boost::asio::detail::socket_ops::socket(
                                            (boost::asio::detail::socket_ops *)2,
                                            1,
                                            6,
                                            (int)v30,
                                            v20);
  v10 = v8;
  v32[2] = v8;
  if ( v8 == (boost::asio::detail::socket_ops *)-1LL )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A00000055LL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v9);
  }
  if ( (unsigned int)boost::asio::detail::socket_ops::connect(
                       v8,
                       (unsigned __int64)v37,
                       v32[0],
                       (unsigned __int64)v30,
                       v21) == -1 )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A00000059LL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v11);
  }
  v12 = (void *)boost::asio::detail::socket_ops::accept(
                  (boost::asio::detail::socket_ops *)v2,
                  0,
                  0,
                  (unsigned __int64 *)v30,
                  v22);
  v32[0] = v12;
  if ( v12 == (void *)-1LL )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A0000005DLL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v13);
  }
  v36 = 1;
  LOBYTE(v29) = 0;
  if ( (unsigned int)boost::asio::detail::socket_ops::ioctl(
                       v10,
                       (unsigned __int64)&v29,
                       (unsigned __int8 *)0x8004667ELL,
                       (int)&v36,
                       v30,
                       v24) )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A00000063LL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v14);
  }
  *(_DWORD *)optval = 1;
  boost::asio::detail::socket_ops::setsockopt(
    v10,
    (unsigned __int64)&v29,
    (unsigned __int8 *)6,
    1,
    optval,
    (const void *)4,
    (unsigned __int64)v30,
    v27);
  v36 = 1;
  LOBYTE(v29) = 0;
  if ( (unsigned int)boost::asio::detail::socket_ops::ioctl(
                       (boost::asio::detail::socket_ops *)v12,
                       (unsigned __int64)&v29,
                       (unsigned __int8 *)0x8004667ELL,
                       (int)&v36,
                       v30,
                       v25) )
  {
    *(_QWORD *)v33 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/sock"
                     "et_select_interrupter.ipp";
    *(_QWORD *)&v33[8] = "void __cdecl boost::asio::detail::socket_select_interrupter::open_descriptors(void)";
    v34 = 0x1A0000006DLL;
    if ( (v31 & 1) != 0 && (v31 != 1 || v30[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v30,
        (const struct boost::system::error_code *)"socket_select_interrupter",
        (const char *)v33,
        v15);
  }
  *(_DWORD *)optval = 1;
  boost::asio::detail::socket_ops::setsockopt(
    (boost::asio::detail::socket_ops *)v12,
    (unsigned __int64)&v29,
    (unsigned __int8 *)6,
    1,
    optval,
    (const void *)4,
    (unsigned __int64)v30,
    v28);
  *(_QWORD *)this = v12;
  *((_QWORD *)this + 1) = v10;
  if ( v2 != (void *)-1LL )
  {
    *(_OWORD *)v33 = 0;
    v34 = 0;
    LOBYTE(v29) = 0;
    LOBYTE(v16) = 1;
    boost::asio::detail::socket_ops::close(
      (boost::asio::detail::socket_ops *)v2,
      (unsigned __int64)&v29,
      v16,
      (bool)v33,
      v23);
  }
}

```

## disassembly

```asm
0x18016fc14  mov     rax, rsp
0x18016fc17  mov     [rax+10h], rbx
0x18016fc1b  mov     [rax+18h], rsi
0x18016fc1f  mov     [rax+20h], rdi
0x18016fc23  push    rbp
0x18016fc24  push    r12
0x18016fc26  push    r13
0x18016fc28  push    r14
0x18016fc2a  push    r15
0x18016fc2c  lea     rbp, [rax-5Fh]
0x18016fc30  mov     eax, 0B0h
0x18016fc35  call    _alloca_probe
0x18016fc3a  sub     rsp, rax
0x18016fc3d  mov     rax, cs:__security_cookie
0x18016fc44  xor     rax, rsp
0x18016fc47  mov     [rbp+57h+var_28], rax
0x18016fc4b  mov     r14, rcx
0x18016fc4e  xorps   xmm0, xmm0
0x18016fc51  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18016fc55  xor     r12d, r12d
0x18016fc58  mov     [rbp+57h+var_78], r12
0x18016fc5c  lea     r9, [rbp+57h+var_88]; int
0x18016fc60  lea     r8d, [r12+6]; int
0x18016fc65  lea     r15d, [r12+1]
0x18016fc6a  mov     edx, r15d; int
0x18016fc6d  lea     ecx, [r12+2]; this
0x18016fc72  call    ?socket@socket_ops@detail@asio@boost@@YA_KHHHAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::socket(int,int,int,boost::system::error_code &)
0x18016fc77  mov     rbx, rax
0x18016fc7a  mov     [rbp+57h+var_68], rax
0x18016fc7e  lea     r13, aCW1SExternalsV_7; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18016fc85  lea     rsi, aVoidCdeclBoost_51; "void __cdecl boost::asio::detail::socke"...
0x18016fc8c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016fc90  jnz     short loc_18016FCC2
0x18016fc92  mov     qword ptr [rbp+57h+var_58], r13
0x18016fc96  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18016fc9a  mov     dword ptr [rbp+57h+var_48], 32h ; '2'
0x18016fca1  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016fca8  test    byte ptr [rbp+57h+var_78], r15b
0x18016fcac  jz      short loc_18016FCC2
0x18016fcae  cmp     [rbp+57h+var_78], r15
0x18016fcb2  jnz     loc_1801700A2
0x18016fcb8  cmp     [rbp+57h+var_88], r12d
0x18016fcbc  jnz     loc_1801700A2
0x18016fcc2  mov     dword ptr [rbp+57h+optval], r15d
0x18016fcc6  mov     byte ptr [rbp+57h+var_90], r12b
0x18016fcca  lea     rax, [rbp+57h+var_88]
0x18016fcce  mov     [rsp+0D0h+var_A0], rax; unsigned __int64
0x18016fcd3  mov     ecx, 4
0x18016fcd8  mov     [rsp+0D0h+var_A8], rcx; struct boost::system::error_code *
0x18016fcdd  lea     rax, [rbp+57h+optval]
0x18016fce1  mov     [rsp+0D0h+var_B0], rax; struct boost::system::error_code *
0x18016fce6  mov     r9d, ecx; int
0x18016fce9  mov     r8d, 0FFFFh; unsigned __int8 *
0x18016fcef  lea     rdx, [rbp+57h+var_90]; unsigned __int64
0x18016fcf3  mov     rcx, rbx; this
0x18016fcf6  call    ?setsockopt@socket_ops@detail@asio@boost@@YAH_KAEAEHHPEBX0AEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::setsockopt(unsigned __int64,uchar &,int,int,void const *,unsigned __int64,boost::system::error_code &)
0x18016fcfb  mov     edi, 10h
0x18016fd00  mov     [rbp+57h+var_70], rdi
0x18016fd04  mov     [rbp+57h+var_30], r12
0x18016fd08  lea     eax, [rdi-0Eh]
0x18016fd0b  mov     word ptr [rbp+57h+var_38], ax
0x18016fd0f  mov     ecx, 7F000001h; hostlong
0x18016fd14  call    cs:__imp_htonl
0x18016fd1a  mov     dword ptr [rbp+57h+var_38+4], eax
0x18016fd1d  mov     word ptr [rbp+57h+var_38+2], r12w
0x18016fd22  lea     r9, [rbp+57h+var_88]; unsigned __int64
0x18016fd26  mov     r8d, edi; void *
0x18016fd29  lea     rdx, [rbp+57h+var_38]; unsigned __int64
0x18016fd2d  mov     rcx, rbx; this
0x18016fd30  call    ?bind@socket_ops@detail@asio@boost@@YAH_KPEBX0AEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::bind(unsigned __int64,void const *,unsigned __int64,boost::system::error_code &)
0x18016fd35  cmp     eax, 0FFFFFFFFh
0x18016fd38  jnz     short loc_18016FD6A
0x18016fd3a  mov     qword ptr [rbp+57h+var_58], r13
0x18016fd3e  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18016fd42  mov     dword ptr [rbp+57h+var_48], 42h ; 'B'
0x18016fd49  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016fd50  test    byte ptr [rbp+57h+var_78], r15b
0x18016fd54  jz      short loc_18016FD6A
0x18016fd56  cmp     [rbp+57h+var_78], r15
0x18016fd5a  jnz     loc_1801700B7
0x18016fd60  cmp     [rbp+57h+var_88], r12d
0x18016fd64  jnz     loc_1801700B7
0x18016fd6a  lea     r9, [rbp+57h+var_88]; unsigned __int64 *
0x18016fd6e  lea     r8, [rbp+57h+var_70]; void *
0x18016fd72  lea     rdx, [rbp+57h+var_38]; unsigned __int64
0x18016fd76  mov     rcx, rbx; this
0x18016fd79  call    ?getsockname@socket_ops@detail@asio@boost@@YAH_KPEAXPEA_KAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::getsockname(unsigned __int64,void *,unsigned __int64 *,boost::system::error_code &)
0x18016fd7e  cmp     eax, 0FFFFFFFFh
0x18016fd81  jnz     short loc_18016FDB3
0x18016fd83  mov     qword ptr [rbp+57h+var_58], r13
0x18016fd87  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18016fd8b  mov     dword ptr [rbp+57h+var_48], 46h ; 'F'
0x18016fd92  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016fd99  test    byte ptr [rbp+57h+var_78], r15b
0x18016fd9d  jz      short loc_18016FDB3
0x18016fd9f  cmp     [rbp+57h+var_78], r15
0x18016fda3  jnz     loc_1801700CC
0x18016fda9  cmp     [rbp+57h+var_88], r12d
0x18016fdad  jnz     loc_1801700CC
0x18016fdb3  xor     ecx, ecx; hostlong
0x18016fdb5  call    cs:__imp_htonl
0x18016fdbb  cmp     dword ptr [rbp+57h+var_38+4], eax
0x18016fdbe  jnz     short loc_18016FDCE
0x18016fdc0  mov     ecx, 7F000001h; hostlong
0x18016fdc5  call    cs:__imp_htonl
0x18016fdcb  mov     dword ptr [rbp+57h+var_38+4], eax
0x18016fdce  lea     r8, [rbp+57h+var_88]; int
0x18016fdd2  mov     edx, 7FFFFFFFh; unsigned __int64
0x18016fdd7  mov     rcx, rbx; this
0x18016fdda  call    ?listen@socket_ops@detail@asio@boost@@YAH_KHAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::listen(unsigned __int64,int,boost::system::error_code &)
0x18016fddf  cmp     eax, 0FFFFFFFFh
0x18016fde2  jnz     short loc_18016FE14
0x18016fde4  mov     qword ptr [rbp+57h+var_58], r13
0x18016fde8  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18016fdec  mov     dword ptr [rbp+57h+var_48], 50h ; 'P'
0x18016fdf3  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016fdfa  test    byte ptr [rbp+57h+var_78], r15b
0x18016fdfe  jz      short loc_18016FE14
0x18016fe00  cmp     [rbp+57h+var_78], r15
0x18016fe04  jnz     loc_1801700E1
0x18016fe0a  cmp     [rbp+57h+var_88], r12d
0x18016fe0e  jnz     loc_1801700E1
0x18016fe14  lea     r9, [rbp+57h+var_88]; int
0x18016fe18  mov     r8d, 6; int
0x18016fe1e  mov     edx, r15d; int
0x18016fe21  lea     ecx, [r8-4]; this
0x18016fe25  call    ?socket@socket_ops@detail@asio@boost@@YA_KHHHAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::socket(int,int,int,boost::system::error_code &)
0x18016fe2a  mov     rdi, rax
0x18016fe2d  mov     [rbp+57h+var_60], rax
0x18016fe31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016fe35  jnz     short loc_18016FE67
0x18016fe37  mov     qword ptr [rbp+57h+var_58], r13
0x18016fe3b  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18016fe3f  mov     dword ptr [rbp+57h+var_48], 55h ; 'U'
0x18016fe46  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016fe4d  test    byte ptr [rbp+57h+var_78], r15b
0x18016fe51  jz      short loc_18016FE67
0x18016fe53  cmp     [rbp+57h+var_78], r15
0x18016fe57  jnz     loc_1801700F6
0x18016fe5d  cmp     [rbp+57h+var_88], r12d
0x18016fe61  jnz     loc_1801700F6
0x18016fe67  lea     r9, [rbp+57h+var_88]; unsigned __int64
0x18016fe6b  mov     r8, [rbp+57h+var_70]; void *
0x18016fe6f  lea     rdx, [rbp+57h+var_38]; unsigned __int64
0x18016fe73  mov     rcx, rdi; this
0x18016fe76  call    ?connect@socket_ops@detail@asio@boost@@YAH_KPEBX0AEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::connect(unsigned __int64,void const *,unsigned __int64,boost::system::error_code &)
0x18016fe7b  cmp     eax, 0FFFFFFFFh
0x18016fe7e  jnz     short loc_18016FEB0
0x18016fe80  mov     qword ptr [rbp+57h+var_58], r13
0x18016fe84  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18016fe88  mov     dword ptr [rbp+57h+var_48], 59h ; 'Y'
0x18016fe8f  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016fe96  test    byte ptr [rbp+57h+var_78], r15b
0x18016fe9a  jz      short loc_18016FEB0
0x18016fe9c  cmp     [rbp+57h+var_78], r15
0x18016fea0  jnz     loc_18017010B
0x18016fea6  cmp     [rbp+57h+var_88], r12d
0x18016feaa  jnz     loc_18017010B
0x18016feb0  lea     r9, [rbp+57h+var_88]; unsigned __int64 *
0x18016feb4  xor     r8d, r8d; void *
0x18016feb7  xor     edx, edx; unsigned __int64
0x18016feb9  mov     rcx, rbx; this
0x18016febc  call    ?accept@socket_ops@detail@asio@boost@@YA_K_KPEAXPEA_KAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::accept(unsigned __int64,void *,unsigned __int64 *,boost::system::error_code &)
0x18016fec1  mov     rsi, rax
0x18016fec4  mov     [rbp+57h+var_70], rax
0x18016fec8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016fecc  jnz     short loc_18016FF05
0x18016fece  mov     qword ptr [rbp+57h+var_58], r13
0x18016fed2  lea     rax, aVoidCdeclBoost_51; "void __cdecl boost::asio::detail::socke"...
0x18016fed9  mov     qword ptr [rbp+57h+var_58+8], rax
0x18016fedd  mov     dword ptr [rbp+57h+var_48], 5Dh ; ']'
0x18016fee4  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016feeb  test    byte ptr [rbp+57h+var_78], r15b
0x18016feef  jz      short loc_18016FF05
0x18016fef1  cmp     [rbp+57h+var_78], r15
0x18016fef5  jnz     loc_180170120
0x18016fefb  cmp     [rbp+57h+var_88], r12d
0x18016feff  jnz     loc_180170120
0x18016ff05  mov     [rbp+57h+var_3C], r15d
0x18016ff09  mov     byte ptr [rbp+57h+var_90], r12b
0x18016ff0d  lea     rax, [rbp+57h+var_88]
0x18016ff11  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x18016ff16  lea     r9, [rbp+57h+var_3C]; int
0x18016ff1a  mov     r8d, 8004667Eh; unsigned __int8 *
0x18016ff20  lea     rdx, [rbp+57h+var_90]; unsigned __int64
0x18016ff24  mov     rcx, rdi; this
0x18016ff27  call    ?ioctl@socket_ops@detail@asio@boost@@YAH_KAEAEHPEAKAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::ioctl(unsigned __int64,uchar &,int,ulong *,boost::system::error_code &)
0x18016ff2c  test    eax, eax
0x18016ff2e  jz      short loc_18016FF67
0x18016ff30  mov     qword ptr [rbp+57h+var_58], r13
0x18016ff34  lea     rax, aVoidCdeclBoost_51; "void __cdecl boost::asio::detail::socke"...
0x18016ff3b  mov     qword ptr [rbp+57h+var_58+8], rax
0x18016ff3f  mov     dword ptr [rbp+57h+var_48], 63h ; 'c'
0x18016ff46  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016ff4d  test    byte ptr [rbp+57h+var_78], r15b
0x18016ff51  jz      short loc_18016FF67
0x18016ff53  cmp     [rbp+57h+var_78], r15
0x18016ff57  jnz     loc_180170135
0x18016ff5d  cmp     [rbp+57h+var_88], r12d
0x18016ff61  jnz     loc_180170135
0x18016ff67  mov     dword ptr [rbp+57h+optval], r15d
0x18016ff6b  lea     rax, [rbp+57h+var_88]
0x18016ff6f  mov     [rsp+0D0h+var_A0], rax; unsigned __int64
0x18016ff74  mov     [rsp+0D0h+var_A8], 4; struct boost::system::error_code *
0x18016ff7d  lea     rax, [rbp+57h+optval]
0x18016ff81  mov     [rsp+0D0h+var_B0], rax; optval
0x18016ff86  mov     r9d, r15d; int
0x18016ff89  mov     r8d, 6; unsigned __int8 *
0x18016ff8f  lea     rdx, [rbp+57h+var_90]; unsigned __int64
0x18016ff93  mov     rcx, rdi; this
0x18016ff96  call    ?setsockopt@socket_ops@detail@asio@boost@@YAH_KAEAEHHPEBX0AEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::setsockopt(unsigned __int64,uchar &,int,int,void const *,unsigned __int64,boost::system::error_code &)
0x18016ff9b  mov     [rbp+57h+var_3C], r15d
0x18016ff9f  mov     byte ptr [rbp+57h+var_90], r12b
0x18016ffa3  lea     rax, [rbp+57h+var_88]
0x18016ffa7  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x18016ffac  lea     r9, [rbp+57h+var_3C]; int
0x18016ffb0  mov     r8d, 8004667Eh; unsigned __int8 *
0x18016ffb6  lea     rdx, [rbp+57h+var_90]; unsigned __int64
0x18016ffba  mov     rcx, rsi; this
0x18016ffbd  call    ?ioctl@socket_ops@detail@asio@boost@@YAH_KAEAEHPEAKAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::ioctl(unsigned __int64,uchar &,int,ulong *,boost::system::error_code &)
0x18016ffc2  test    eax, eax
0x18016ffc4  jz      short loc_18016FFFD
0x18016ffc6  mov     qword ptr [rbp+57h+var_58], r13
0x18016ffca  lea     rax, aVoidCdeclBoost_51; "void __cdecl boost::asio::detail::socke"...
0x18016ffd1  mov     qword ptr [rbp+57h+var_58+8], rax
0x18016ffd5  mov     dword ptr [rbp+57h+var_48], 6Dh ; 'm'
0x18016ffdc  mov     dword ptr [rbp+57h+var_48+4], 1Ah
0x18016ffe3  test    byte ptr [rbp+57h+var_78], r15b
0x18016ffe7  jz      short loc_18016FFFD
0x18016ffe9  cmp     [rbp+57h+var_78], r15
0x18016ffed  jnz     loc_18017008D
0x18016fff3  cmp     [rbp+57h+var_88], r12d
0x18016fff7  jnz     loc_18017008D
0x18016fffd  mov     dword ptr [rbp+57h+optval], r15d
0x180170001  lea     rax, [rbp+57h+var_88]
0x180170005  mov     [rsp+0D0h+var_A0], rax; unsigned __int64
0x18017000a  mov     [rsp+0D0h+var_A8], 4; void *
0x180170013  lea     rax, [rbp+57h+optval]
0x180170017  mov     [rsp+0D0h+var_B0], rax; struct boost::system::error_code *
0x18017001c  mov     r9d, r15d; int
0x18017001f  mov     r8d, 6; unsigned __int8 *
0x180170025  lea     rdx, [rbp+57h+var_90]; unsigned __int64
0x180170029  mov     rcx, rsi; this
0x18017002c  call    ?setsockopt@socket_ops@detail@asio@boost@@YAH_KAEAEHHPEBX0AEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::setsockopt(unsigned __int64,uchar &,int,int,void const *,unsigned __int64,boost::system::error_code &)
0x180170031  mov     [r14], rsi
0x180170034  mov     [r14+8], rdi
0x180170038  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18017003c  jz      short loc_180170060
0x18017003e  xorps   xmm0, xmm0
0x180170041  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180170045  mov     [rbp+57h+var_48], r12
0x180170049  mov     byte ptr [rbp+57h+var_90], r12b
0x18017004d  lea     r9, [rbp+57h+var_58]; bool
0x180170051  mov     r8b, r15b; unsigned __int8 *
0x180170054  lea     rdx, [rbp+57h+var_90]; unsigned __int64
0x180170058  mov     rcx, rbx; this
0x18017005b  call    ?close@socket_ops@detail@asio@boost@@YAH_KAEAE_NAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::close(unsigned __int64,uchar &,bool,boost::system::error_code &)
0x180170060  mov     rcx, [rbp+57h+var_28]
0x180170064  xor     rcx, rsp; StackCookie
0x180170067  call    __security_check_cookie
0x18017006c  lea     r11, [rsp+0D0h+var_20]
0x180170074  mov     rbx, [r11+38h]
0x180170078  mov     rsi, [r11+40h]
0x18017007c  mov     rdi, [r11+48h]
0x180170080  mov     rsp, r11
0x180170083  pop     r15
0x180170085  pop     r14
0x180170087  pop     r13
0x180170089  pop     r12
0x18017008b  pop     rbp
0x18017008c  retn
0x18017008d  lea     r8, [rbp+57h+var_58]; char *
0x180170091  lea     rdx, aSocketSelectIn; "socket_select_interrupter"
0x180170098  lea     rcx, [rbp+57h+var_88]; this
0x18017009c  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x1801700a2  lea     r8, [rbp+57h+var_58]; char *
0x1801700a6  lea     rdx, aSocketSelectIn; "socket_select_interrupter"
0x1801700ad  lea     rcx, [rbp+57h+var_88]; this
0x1801700b1  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x1801700b7  lea     r8, [rbp+57h+var_58]; char *
0x1801700bb  lea     rdx, aSocketSelectIn; "socket_select_interrupter"
0x1801700c2  lea     rcx, [rbp+57h+var_88]; this
0x1801700c6  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x1801700cc  lea     r8, [rbp+57h+var_58]; char *
0x1801700d0  lea     rdx, aSocketSelectIn; "socket_select_interrupter"
0x1801700d7  lea     rcx, [rbp+57h+var_88]; this
0x1801700db  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x1801700e1  lea     r8, [rbp+57h+var_58]; char *
0x1801700e5  lea     rdx, aSocketSelectIn; "socket_select_interrupter"
0x1801700ec  lea     rcx, [rbp+57h+var_88]; this
0x1801700f0  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x1801700f6  lea     r8, [rbp+57h+var_58]; char *
0x1801700fa  lea     rdx, aSocketSelectIn; "socket_select_interrupter"
0x180170101  lea     rcx, [rbp+57h+var_88]; this
0x180170105  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x18017010b  lea     r8, [rbp+57h+var_58]; char *
0x18017010f  lea     rdx, aSocketSelectIn; "socket_select_interrupter"
0x180170116  lea     rcx, [rbp+57h+var_88]; this
0x18017011a  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x180170120  lea     r8, [rbp+57h+var_58]; char *
  ... truncated ...
```
