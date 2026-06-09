# std::panicking::rust_panic_with_hook

- ea: `0x1800d5780`
- end: `0x1800d67bf`
- name: `std::panicking::rust_panic_with_hook`
- size: `4159`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800dc980`

## callees

- `0x180022de0`
- `0x180023e40`
- `0x1800d5780`
- `0x1800d6c60`
- `0x1800d6de0`
- `0x1800d6df0`
- `0x1800d6e20`
- `0x1800d6e40`
- `0x1800d7bc0`
- `0x1800d7c20`
- `0x1800d97e0`
- `0x1800db370`
- `0x1800dc910`
- `0x180316190`
- `0x180316255`
- `0x180316940`
- `0x180316a30`
- `0x180316ae0`
- `0x180319b70`
- `0x180319c30`
- `0x180319c60`

## import_xrefs

- `kernel32!HeapFree` at `0x1800d5e10`
- `kernel32!HeapFree` at `0x1800d5ed9`
- `kernel32!HeapFree` at `0x1800d5ef1`
- `kernel32!HeapFree` at `0x1800d5f62`
- `kernel32!HeapFree` at `0x1800d6247`
- `kernel32!HeapFree` at `0x1800d625b`
- `kernel32!HeapFree` at `0x1800d65e9`
- `kernel32!HeapFree` at `0x1800d5e10`
- `kernel32!HeapFree` at `0x1800d5ed9`
- `kernel32!HeapFree` at `0x1800d5ef1`
- `kernel32!HeapFree` at `0x1800d5f62`
- `kernel32!HeapFree` at `0x1800d6247`
- `kernel32!HeapFree` at `0x1800d625b`
- `kernel32!HeapFree` at `0x1800d65e9`
- `kernel32!GetLastError` at `0x1800d60b0`
- `kernel32!GetLastError` at `0x1800d63ad`
- `kernel32!GetLastError` at `0x1800d63c3`
- `kernel32!GetLastError` at `0x1800d648b`
- `kernel32!GetLastError` at `0x1800d5fb6`
- `kernel32!GetLastError` at `0x1800d63ad`
- `kernel32!GetLastError` at `0x1800d63c3`
- `kernel32!GetLastError` at `0x1800d648b`
- `kernel32!GetProcessHeap` at `0x1800d5e02`
- `kernel32!GetProcessHeap` at `0x1800d5ec7`
- `kernel32!GetProcessHeap` at `0x1800d5edf`
- `kernel32!GetProcessHeap` at `0x1800d5f50`
- `kernel32!GetProcessHeap` at `0x1800d6235`
- `kernel32!GetProcessHeap` at `0x1800d624d`
- `kernel32!GetProcessHeap` at `0x1800d65db`
- `kernel32!GetProcessHeap` at `0x1800d5e02`
- `kernel32!GetProcessHeap` at `0x1800d5ec7`
- `kernel32!GetProcessHeap` at `0x1800d5edf`
- `kernel32!GetProcessHeap` at `0x1800d5f50`
- `kernel32!GetProcessHeap` at `0x1800d6235`
- `kernel32!GetProcessHeap` at `0x1800d624d`
- `kernel32!GetProcessHeap` at `0x1800d65db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d638b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d638b`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800d60a8`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800d5faf`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800d639e`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800d639e`

## string_xrefs

- `0x1800d5c65`: `RUST_BACKTRACElibrary\std\src\sys_common\wtf8.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall __noreturn std::panicking::rust_panic_with_hook(
        _QWORD *a1,
        __int64 a2,
        __int64 (__fastcall *a3)(),
        char a4,
        char a5)
{
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // eax
  _QWORD *v8; // r15
  _QWORD *v9; // rdx
  _QWORD *v10; // rdi
  unsigned int v11; // ebx
  __int64 (__fastcall *v12)(); // r14
  void (__fastcall *v13)(LPVOID *, __int64); // rdi
  __int64 v14; // rcx
  __int64 v15; // rdx
  char **v16; // rax
  char *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  LPVOID *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rdx
  void *v23; // rdx
  void *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned __int64 v28; // r13
  __int64 v29; // r15
  unsigned int v30; // esi
  int v31; // ecx
  int v32; // r8d
  int v33; // esi
  char v34; // dl
  __int16 v35; // r12
  void *v36; // rsi
  unsigned __int64 v37; // rax
  _WORD *v38; // rcx
  __int64 v39; // rax
  bool v40; // zf
  char **v41; // rdi
  HANDLE ProcessHeap; // rax
  signed __int8 v43; // si
  signed __int8 v44; // al
  HANDLE v45; // rax
  HANDLE v46; // rax
  HANDLE v47; // rax
  unsigned __int32 v48; // ecx
  int v49; // eax
  char v50; // al
  unsigned int v51; // eax
  signed __int32 v52; // eax
  signed __int32 v53; // eax
  int v54; // edx
  __int64 v55; // rcx
  void *v56; // rsi
  HANDLE v57; // rax
  HANDLE v58; // rax
  __int64 v59; // rax
  char v60; // al
  __int64 v61; // rax
  unsigned __int64 v62; // r8
  char *v63; // rsi
  __int64 v64; // rbx
  unsigned __int64 v65; // rdi
  WCHAR *v66; // r15
  unsigned __int64 v67; // r13
  char *v68; // r8
  DWORD EnvironmentVariableW; // eax
  unsigned __int64 v70; // r13
  unsigned __int64 v71; // rdi
  unsigned __int64 v72; // r15
  LPCWSTR v73; // rbx
  char v74; // r14
  HANDLE v75; // rax
  int is_zero_slow_path; // eax
  _QWORD *v77; // rcx
  __int64 (__fastcall *v78)(); // rax
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // rax
  __int64 v83; // rax
  LPVOID lpMem[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v85; // [rsp+40h] [rbp-40h]
  __int128 v86; // [rsp+48h] [rbp-38h]
  _QWORD v87[6]; // [rsp+430h] [rbp+3B0h] BYREF
  _QWORD v88[2]; // [rsp+460h] [rbp+3E0h] BYREF
  _QWORD v89[2]; // [rsp+470h] [rbp+3F0h] BYREF
  unsigned __int64 v90; // [rsp+480h] [rbp+400h]
  char **v91; // [rsp+488h] [rbp+408h] BYREF
  LPVOID v92; // [rsp+490h] [rbp+410h]
  __int64 v93; // [rsp+498h] [rbp+418h]
  __int128 v94; // [rsp+4A0h] [rbp+420h]
  __int64 (__fastcall *v95)(); // [rsp+4B0h] [rbp+430h]
  _QWORD *v96; // [rsp+4B8h] [rbp+438h] BYREF
  __int64 v97; // [rsp+4C0h] [rbp+440h]
  _QWORD v98[2]; // [rsp+4C8h] [rbp+448h] BYREF
  __int64 (__fastcall *v99)(); // [rsp+4D8h] [rbp+458h] BYREF
  _QWORD *v100; // [rsp+4E0h] [rbp+460h]
  __int64 (__fastcall *v101)(); // [rsp+4E8h] [rbp+468h]
  _QWORD *v102; // [rsp+4F0h] [rbp+470h] BYREF
  __int64 v103; // [rsp+4F8h] [rbp+478h]
  _QWORD *v104; // [rsp+500h] [rbp+480h]
  __int64 v105; // [rsp+508h] [rbp+488h]
  _QWORD *v106; // [rsp+510h] [rbp+490h]
  __int64 (__fastcall *v107)(); // [rsp+518h] [rbp+498h]
  __int64 v108; // [rsp+520h] [rbp+4A0h]
  __int64 v109; // [rsp+528h] [rbp+4A8h]
  __int64 v110; // [rsp+530h] [rbp+4B0h]
  _QWORD *v111; // [rsp+538h] [rbp+4B8h] BYREF
  __int64 v112; // [rsp+540h] [rbp+4C0h]
  __int64 v113; // [rsp+548h] [rbp+4C8h]
  __int64 (__fastcall *v114)(); // [rsp+550h] [rbp+4D0h] BYREF
  _QWORD *v115; // [rsp+558h] [rbp+4D8h]
  int v116; // [rsp+560h] [rbp+4E0h] BYREF
  char v117; // [rsp+564h] [rbp+4E4h]
  LPCWSTR lpName; // [rsp+568h] [rbp+4E8h]
  __int64 v119; // [rsp+570h] [rbp+4F0h]
  char v120; // [rsp+57Fh] [rbp+4FFh]
  LPVOID v121; // [rsp+580h] [rbp+500h]
  LPVOID v122; // [rsp+588h] [rbp+508h]
  __int64 v123; // [rsp+590h] [rbp+510h]

  v123 = -2;
  v120 = a4;
  v111 = a1;
  v112 = a2;
  v114 = a3;
  if ( _InterlockedIncrement64(&qword_1804B1950) <= 0 )
  {
    v77 = &v102;
    LODWORD(v102) = 0;
    BYTE4(v102) = 0;
    v91 = (char **)&v114;
    v92 = core::fmt::impl_75::fmt_core::panic::location::Location_;
    v93 = (__int64)&v111;
    lpMem[0] = &off_180343938;
    lpMem[1] = (LPVOID)3;
    *((_QWORD *)&v86 + 1) = 0;
    v78 = core::fmt::impl_73::fmt_dyn__core::fmt::Debug___;
  }
  else
  {
    v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( !*(_BYTE *)(v5 + 16) )
    {
      v6 = v5 + 8;
      ++*(_QWORD *)v6;
      v108 = v6;
      *(_BYTE *)(v6 + 8) = 1;
      v7 = dword_1804B1930;
      if ( (unsigned int)dword_1804B1930 <= 0x3FFFFFFD
        && v7 == _InterlockedCompareExchange(&dword_1804B1930, dword_1804B1930 + 1, dword_1804B1930) )
      {
LABEL_5:
        if ( qword_1804B1940 )
        {
          v10 = v111;
          v109 = v112;
          lpMem[0] = (LPVOID)(*(__int64 (__fastcall **)(_QWORD *))(v112 + 40))(v111);
          lpMem[1] = v23;
          v85 = (__int64)v114;
          LOBYTE(v86) = v120;
          BYTE1(v86) = a5;
          (*(void (__fastcall **)(__int64, LPVOID *))(qword_1804B1948 + 40))(qword_1804B1940, lpMem);
LABEL_26:
          core::ptr::drop_in_place_std::sync::poison::rwlock::RwLockReadGuard_enum2__std::panicking::Hook_____();
          *(_BYTE *)(v108 + 8) = 0;
          if ( v120 )
            std::panicking::rust_panic(v10, *(_QWORD *)(v109 + 32));
          LODWORD(v91) = 0;
          BYTE4(v91) = 0;
          lpMem[0] = &off_180343968;
          lpMem[1] = (LPVOID)1;
          v85 = 8;
          v86 = 0;
          v83 = std::io::Write::write_fmt_std::sys::stdio::windows::Stderr_(&v91, lpMem);
          core::ptr::drop_in_place_enum2__core::result::Result_tuple____std::io::error::Error_____(v83);
          __fastfail(7u);
        }
        v8 = v111;
        v109 = v112;
        v119 = (*(__int64 (__fastcall **)(_QWORD *))(v112 + 40))(v111);
        v10 = v9;
        LOBYTE(v11) = 3;
        v12 = v114;
        if ( a5 )
          goto LABEL_9;
        LOBYTE(v11) = 1;
        if ( *(_QWORD *)v108 > 1u )
          goto LABEL_9;
        LOBYTE(v11) = byte_1804B1928 - 1;
        if ( (unsigned __int8)(byte_1804B1928 - 1) < 3u )
          goto LABEL_9;
LABEL_30:
        v24 = (void *)std::sys::alloc::windows::process_heap_alloc(0, 30);
        if ( !v24 )
          alloc::alloc::handle_alloc_error(2, 30);
        v101 = v12;
        v100 = v10;
        v115 = v8;
        lpMem[0] = (LPVOID)15;
        lpMem[1] = v24;
        v85 = 0;
        v28 = 0;
        v29 = 0;
        for ( LOWORD(v30) = 0; ; LOWORD(v30) = v35 )
        {
          if ( (_WORD)v30 )
            goto LABEL_48;
          if ( v29 == 14 )
          {
            v36 = lpMem[1];
            v37 = v28;
            v38 = lpMem[1];
            if ( v28 >= 8 )
            {
              v38 = lpMem[1];
              v37 = v28;
              while ( *v38 && v38[1] && v38[2] && v38[3] && v38[4] && v38[5] && v38[6] && v38[7] )
              {
                v37 -= 8LL;
                v38 += 8;
                if ( v37 <= 7 )
                  goto LABEL_65;
              }
LABEL_68:
              v41 = &off_180343A98;
              if ( lpMem[0] )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v36);
              }
LABEL_70:
              LOBYTE(v11) = 2;
              v43 = 3;
              if ( ((unsigned __int8)v41 & 3) == 1 )
              {
                v122 = (char *)v41 - 1;
                lpName = *(LPCWSTR *)((char *)v41 - 1);
                v121 = *(char **)((char *)v41 + 7);
                if ( *(_QWORD *)v121 )
                  (*(void (__fastcall **)(LPCWSTR, __int64))v121)(lpName, v25);
                if ( *((_QWORD *)v121 + 1) )
                  sub_180022DE0(lpName, *((_QWORD *)v121 + 2));
                sub_180022DE0(v122, 8);
              }
              goto LABEL_71;
            }
LABEL_65:
            v39 = 2 * v37;
            v25 = 0;
            while ( v39 != v25 )
            {
              v40 = *(_WORD *)((char *)v38 + v25) == 0;
              v25 += 2;
              if ( v40 )
                goto LABEL_68;
            }
            v55 = (__int64)lpMem[0];
            if ( (LPVOID)v28 == lpMem[0] )
            {
              alloc::raw_vec::RawVec_u16_alloc::alloc::Global_::grow_one_u16_alloc::alloc::Global_(
                lpMem,
                &off_180343AB0);
              v55 = (__int64)lpMem[0];
              v41 = (char **)lpMem[1];
              *((_WORD *)lpMem[1] + v28) = 0;
              if ( __OFSUB__(-v55, 1) )
                goto LABEL_70;
            }
            else
            {
              *((_WORD *)lpMem[1] + v28) = 0;
              v41 = (char **)v36;
            }
            lpName = (LPCWSTR)v41;
            v110 = v55;
            v102 = 0;
            v103 = 2;
            v104 = 0;
            v62 = 512;
            v122 = 0;
            v121 = (LPVOID)2;
            v63 = 0;
            v64 = 0;
            while ( 1 )
            {
              if ( v62 >= 0x201 )
              {
                v68 = (char *)(v62 - v64);
                if ( v68 > &v63[-v64] )
                {
                  alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__7(
                    (unsigned int)&v102,
                    v64,
                    (_DWORD)v68,
                    2,
                    2);
                  v122 = v102;
                  v121 = (LPVOID)v103;
                }
                v63 = (char *)v122;
                v64 = 0xFFFFFFFFLL;
                if ( (unsigned __int64)v122 < 0xFFFFFFFF )
                  v64 = (__int64)v122;
                v104 = (_QWORD *)v64;
                v65 = v64;
                v66 = (WCHAR *)v121;
                v67 = v64;
              }
              else
              {
                v65 = 512;
                v66 = (WCHAR *)lpMem;
                v67 = v62;
              }
              SetLastError(0);
              EnvironmentVariableW = GetEnvironmentVariableW(lpName, v66, v67);
              if ( EnvironmentVariableW )
              {
                v62 = EnvironmentVariableW;
              }
              else
              {
                if ( GetLastError() )
                {
                  v72 = ((unsigned __int64)GetLastError() << 32) | 2;
                  if ( v102 )
                  {
                    v71 = 0x8000000000000000uLL;
                    v73 = lpName;
                    goto LABEL_162;
                  }
                  v73 = lpName;
LABEL_164:
                  v71 = 0x8000000000000000uLL;
                  if ( (v72 & 3) == 1 )
                  {
                    v121 = (LPVOID)(v72 - 1);
                    v113 = *(_QWORD *)(v72 - 1);
                    v122 = *(LPVOID *)(v72 + 7);
                    if ( *(_QWORD *)v122 )
                      (*(void (__fastcall **)(__int64))v122)(v113);
                    if ( *((_QWORD *)v122 + 1) )
                      sub_180022DE0(v113, *((_QWORD *)v122 + 2));
                    sub_180022DE0(v121, 8);
                    v73 = lpName;
                  }
LABEL_165:
                  if ( v110 )
                    sub_180022DE0(v73, 2);
                  if ( __OFSUB__(-(__int64)v71, 1) )
                  {
                    LOBYTE(v11) = 2;
                    v43 = 3;
                    goto LABEL_71;
                  }
                  if ( v63 == (char *)4 )
                  {
                    if ( *(_DWORD *)v72 == 1819047270 )
                    {
                      v74 = 1;
                      v43 = 2;
                      LOBYTE(v11) = 1;
                      goto LABEL_181;
                    }
                  }
                  else if ( v63 == (char *)1 && *(_BYTE *)v72 == 48 )
                  {
                    v74 = 2;
                    v43 = 3;
                    LOBYTE(v11) = 2;
LABEL_181:
                    if ( v71 )
                    {
                      v75 = GetProcessHeap();
                      HeapFree(v75, 0, (LPVOID)v72);
                      LOBYTE(v11) = v74;
                    }
LABEL_71:
                    v44 = _InterlockedCompareExchange8(&byte_1804B1928, v43, 0);
                    v8 = v115;
                    v10 = v100;
                    v12 = v101;
                    if ( v44 )
                    {
                      LOBYTE(v11) = 3;
                      if ( (unsigned __int8)v44 <= 3u )
                        v11 = 0x2010003u >> (8 * v44);
                    }
LABEL_9:
                    v99 = v12;
                    v13 = (void (__fastcall *)(LPVOID *, __int64))v10[3];
                    v13(lpMem, v119);
                    if ( _mm_movemask_epi8(
                           _mm_cmpeq_epi8(
                             _mm_load_si128((const __m128i *)lpMem),
                             (__m128i)_xmm_b98b1b7157a6417863eb502cd6cb5d6d)) == 0xFFFF )
                    {
                      v14 = 8;
                      v15 = v119;
                      v16 = (char **)v119;
                      goto LABEL_11;
                    }
                    v13(lpMem, v119);
                    if ( _mm_movemask_epi8(_mm_cmpeq_epi8(_mm_load_si128((const __m128i *)lpMem), (__m128i)_xmm)) == 0xFFFF )
                    {
                      v15 = v119;
                      v16 = (char **)(v119 + 8);
                      v14 = 16;
LABEL_11:
                      v17 = *v16;
                      v18 = *(_QWORD *)(v15 + v14);
                    }
                    else
                    {
                      v17 = "Box<dyn Any>\nthread panicked while processing panic. aborting.\naborting due to panic at thread caused non-unwinding panic. aborting.\nlibrary\\std\\src\\..\\..\\backtrace\\src\\symbolize\\mod.rs";
                      v18 = 12;
                    }
                    v98[0] = v17;
                    v98[1] = v18;
                    v116 = 0;
                    v117 = 0;
                    if ( _InterlockedCompareExchange8(&byte_1804B1929, 1, 0) )
                      std::sys::sync::mutex::futex::Mutex::lock_contended(&byte_1804B1929);
                    v115 = v8;
                    if ( 2 * qword_1804B1950 )
                    {
                      is_zero_slow_path = std::panicking::panic_count::is_zero_slow_path();
                      LOBYTE(is_zero_slow_path) = is_zero_slow_path ^ 1;
                      LODWORD(lpName) = is_zero_slow_path;
                    }
                    else
                    {
                      LODWORD(lpName) = 0;
                    }
                    v88[0] = "<unnamed>\nthread '' panicked at \nBox<dyn Any>\nthread panicked while processing panic. aborting.\naborting due to panic at thread caused non-unwinding panic. aborting.\nlibrary\\std\\src\\..\\..\\backtrace\\src\\symbolize\\mod.rs";
                    v88[1] = 9;
                    v19 = 128;
                    v20 = lpMem;
                    while ( v19 )
                    {
                      *(_DWORD *)v20 = 0;
                      v20 = (LPVOID *)((char *)v20 + 4);
                      --v19;
                    }
                    v89[0] = lpMem;
                    v89[1] = 512;
                    v90 = 0;
                    v102 = v88;
                    v12 = core::fmt::impl_75::fmt_str__;
                    v103 = (__int64)core::fmt::impl_75::fmt_str__;
                    v104 = &v99;
                    v105 = (__int64)core::fmt::impl_75::fmt_core::panic::location::Location_;
                    v8 = v98;
                    v106 = v98;
                    v87[0] = &off_180343818;
                    v87[1] = 4;
                    v87[4] = 0;
                    v107 = core::fmt::impl_75::fmt_str__;
                    v87[2] = &v102;
                    v87[3] = 3;
                    v96 = v89;
                    v97 = 0;
                    if ( (unsigned __int8)core::fmt::write(&v96, &off_1803434E8, v87) )
                    {
                      if ( !v97 )
                      {
                        v91 = &off_1803435A8;
                        v92 = (LPVOID)1;
                        v93 = 8;
                        v94 = 0;
                        core::panicking::panic_fmt(&v91, &off_1803435B8);
                      }
                      if ( (v97 & 3) == 1 )
                      {
                        v121 = (LPVOID)(v97 - 1);
                        v122 = *(LPVOID *)(v97 - 1);
                        v119 = *(_QWORD *)(v97 + 7);
                        if ( *(_QWORD *)v119 )
                          (*(void (__fastcall **)(LPVOID))v119)(v122);
                        if ( *(_QWORD *)(v119 + 8) )
                        {
                          if ( *(_QWORD *)(v119 + 16) >= 0x11u )
                            v122 = (LPVOID)*((_QWORD *)v122 - 1);
                          v45 = GetProcessHeap();
                          HeapFree(v45, 0, v122);
                        }
                        v46 = GetProcessHeap();
                        HeapFree(v46, 0, v121);
                      }
                      v91 = (char **)v88;
                      v92 = core::fmt::impl_75::fmt_str__;
                      v93 = (__int64)&v99;
                      *(_QWORD *)&v94 = core::fmt::impl_75::fmt_core::panic::location::Location_;
                      v102 = &off_180343818;
                      v103 = 4;
                      v106 = 0;
                      *((_QWORD *)&v94 + 1) = v98;
                      v95 = core::fmt::impl_75::fmt_str__;
                      v104 = &v91;
                      v105 = 3;
                      v21 = std::io::Write::write_fmt_std::sys::stdio::windows::Stderr_(&v116, &v102);
                      v10 = v115;
                      if ( (v21 & 3) == 1 )
                      {
                        v121 = (LPVOID)(v21 - 1);
                        v122 = *(LPVOID *)(v21 - 1);
                        v119 = *(_QWORD *)(v21 + 7);
                        if ( *(_QWORD *)v119 )
LABEL_119:
                          (*(void (__fastcall **)(LPVOID))v119)(v122);
LABEL_120:
                        if ( *(_QWORD *)(v119 + 8) )
                        {
                          v56 = v121;
                          if ( *(_QWORD *)(v119 + 16) >= 0x11u )
                            v122 = (LPVOID)*((_QWORD *)v122 - 1);
                          v57 = GetProcessHeap();
                          HeapFree(v57, 0, v122);
                        }
                        else
                        {
                          v56 = v121;
                        }
                        v58 = GetProcessHeap();
                        HeapFree(v58, 0, v56);
                        switch ( (char)v11 )
                        {
                          case 0:
                            goto LABEL_36;
                          case 1:
                            goto LABEL_131;
                          case 2:
                            goto LABEL_132;
                          default:
                            goto LABEL_30;
                        }
                      }
                    }
                    else
                    {
                      v10 = v115;
                      if ( (v97 & 3) == 1 )
                      {
                        v122 = (LPVOID)(v97 - 1);
                        v121 = *(LPVOID *)(v97 - 1);
                        v119 = *(_QWORD *)(v97 + 7);
                        if ( *(_QWORD *)v119 )
                          (*(void (__fastcall **)(LPVOID))v119)(v121);
                        if ( *(_QWORD *)(v119 + 8) )
                          sub_180022DE0(v121, *(_QWORD *)(v119 + 16));
                        v47 = GetProcessHeap();
                        HeapFree(v47, 0, v122);
                      }
                      if ( v90 > 0x200 )
                        core::slice::index::slice_end_index_len_fail(v90, 512, &off_180343800);
                      v26 = std::io::Write::write_all_std::sys::stdio::windows::Stderr_(&v116, lpMem);
                      if ( (v26 & 3) == 1 )
                      {
                        v121 = (LPVOID)(v26 - 1);
                        v122 = *(LPVOID *)(v26 - 1);
                        v119 = *(_QWORD *)(v26 + 7);
                        if ( *(_QWORD *)v119 )
                          goto LABEL_119;
                        goto LABEL_120;
                      }
                    }
                    switch ( (char)v11 )
                    {
                      case 0:
LABEL_36:
                        v27 = std::sys::backtrace::BacktraceLock::print(&v116, 0);
                        core::ptr::drop_in_place_enum2__core::result::Result_tuple____std::io::error::Error_____(v27);
                        goto LABEL_134;
                      case 1:
LABEL_131:
                        LOBYTE(v22) = 1;
                        v59 = std::sys::backtrace::BacktraceLock::print(&v116, v22);
                        core::ptr::drop_in_place_enum2__core::result::Result_tuple____std::io::error::Error_____(v59);
                        goto LABEL_134;
                      case 2:
LABEL_132:
                        v60 = byte_1804AFE54;
                        byte_1804AFE54 = 0;
                        if ( v60 )
                        {
                          lpMem[0] = &off_1803437F0;
                          lpMem[1] = (LPVOID)1;
                          v85 = 8;
                          v86 = 0;
                          v61 = std::io::Write::write_fmt_std::sys::stdio::windows::Stderr_(&v116, lpMem);
                          core::ptr::drop_in_place_enum2__core::result::Result_tuple____std::io::error::Error_____(v61);
                        }
LABEL_134:
                        core::ptr::drop_in_place_std::sys::backtrace::BacktraceLock_(
                          &byte_1804B1929,
                          (unsigned int)lpName);
                        goto LABEL_26;
                      default:
                        goto LABEL_30;
                    }
                  }
                  v43 = 1;
                  v74 = 0;
                  LOBYTE(v11) = 0;
                  goto LABEL_181;
                }
                v62 = 0;
              }
              if ( v62 == v67 )
              {
                if ( GetLastError() != 122 )
                  core::panicking::panic(
                    "internal error: entered unreachable coderust\\unicode_analysis\\src\\bidi_analysis.rs",
                    40,
                    &off_180343AE0);
                v70 = 2 * v67;
                if ( v70 >= 0xFFFFFFFF )
                  v70 = 0xFFFFFFFFLL;
                v62 = v70;
              }
              else if ( v62 <= v67 )
              {
                if ( v62 > v65 )
                  core::slice::index::slice_end_index_len_fail(v62, v65, &off_180343AC8);
                std::os::windows::ffi::impl_0::from_wide(&v91, v66);
                v71 = (unsigned __int64)v91;
                v72 = (unsigned __int64)v92;
                v63 = (char *)v93;
                v73 = lpName;
                if ( !v102 )
                {
LABEL_163:
                  if ( __OFSUB__(-(__int64)v71, 1) )
                    goto LABEL_164;
                  goto LABEL_165;
                }
LABEL_162:
                sub_180022DE0(v103, 2);
                goto LABEL_163;
              }
            }
          }
          LOBYTE(v25) = aRustBacktracel[v29];
          LOWORD(v30) = (unsigned __int8)v25;
          if ( (v25 & 0x80u) == 0LL )
            break;
          v31 = v25 & 0x1F;
          v32 = aRustBacktracel[v29 + 1] & 0x3F;
          if ( (unsigned __int8)v25 <= 0xDFu )
          {
            v29 += 2;
            LOWORD(v30) = v32 | ((_WORD)v31 << 6);
            goto LABEL_48;
          }
          v33 = (v32 << 6) | aRustBacktracel[v29 + 2] & 0x3F;
          if ( (unsigned __int8)v25 < 0xF0u )
          {
            v29 += 3;
            v30 = (v31 << 12) | v33;
          }
          else
          {
            v34 = aRustBacktracel[v29 + 3];
            v29 += 4;
            v25 = ((v31 & 7) << 18) | (v33 << 6) | v34 & 0x3Fu;
            v30 = v25;
          }
          if ( v30 <= 0xFFFF )
            goto LABEL_48;
          v35 = v30 & 0x3FF | 0xDC00;
          LOWORD(v30) = ((v30 + 16711680) >> 10) | 0xD800;
LABEL_49:
          if ( (LPVOID)v28 == lpMem[0] )
          {
            alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__7(
              (unsigned int)lpMem,
              v28,
              ((unsigned __int64)(17 - v29) >> 2) - (v35 == 0) + 2,
              2,
              2);
            v24 = lpMem[1];
          }
          *((_WORD *)v24 + v28++) = v30;
          v85 = v28;
        }
        ++v29;
LABEL_48:
        v35 = 0;
        goto LABEL_49;
      }
      v48 = dword_1804B1930;
      if ( dword_1804B1930 == 0x3FFFFFFF )
      {
        v49 = -99;
        do
        {
          _mm_pause();
          v48 = dword_1804B1930;
          if ( dword_1804B1930 != 0x3FFFFFFF )
            break;
          v40 = v49++ == 0;
        }
        while ( !v40 );
      }
      v50 = 0;
LABEL_91:
      if ( (v50 & 1) != 0 )
      {
        while ( 1 )
        {
          v51 = v48 & 0x3FFFFFFF;
          if ( (v48 & 0x3FFFFFFF) - 1073741822 >= 0xC0000003 && (v48 & 0x40000000) == 0
            || v48 < 0x40000000 && v51 < 0x3FFFFFFE )
          {
            v52 = _InterlockedCompareExchange(&dword_1804B1930, v48 + 1, v48);
            if ( v48 == v52 )
              goto LABEL_5;
          }
          else
          {
            if ( v51 == 1073741822 )
              goto LABEL_114;
            if ( (v48 & 0x40000000) != 0 )
              goto LABEL_107;
            v52 = _InterlockedCompareExchange(&dword_1804B1930, v48 | 0x40000000, v48);
            if ( v48 == v52 )
              goto LABEL_107;
          }
          v48 = v52;
        }
      }
      while ( 1 )
      {
        if ( (v48 & 0x3FFFFFFF) >= 0x3FFFFFFE || v48 >= 0x40000000 )
        {
          if ( (v48 & 0x3FFFFFFF) == 0x3FFFFFFE )
          {
LABEL_114:
            lpMem[0] = &off_180343C50;
            lpMem[1] = (LPVOID)1;
            v85 = 8;
            v86 = 0;
            core::panicking::panic_fmt(lpMem, &off_180343C60);
          }
          if ( (v48 & 0x40000000) != 0
            || (v53 = _InterlockedCompareExchange(&dword_1804B1930, v48 | 0x40000000, v48), v48 == v53) )
          {
LABEL_107:
            LODWORD(lpMem[0]) = v48 | 0x40000000;
            if ( !WaitOnAddress(&dword_1804B1930, lpMem, 4u, 0xFFFFFFFF) )
              GetLastError();
            v48 = dword_1804B1930;
            v50 = 1;
            if ( dword_1804B1930 == 0x3FFFFFFF )
            {
              v54 = -99;
              do
              {
                _mm_pause();
                v48 = dword_1804B1930;
                if ( dword_1804B1930 != 0x3FFFFFFF )
                  break;
                v40 = v54++ == 0;
              }
              while ( !v40 );
            }
            goto LABEL_91;
          }
        }
        else
        {
          v53 = _InterlockedCompareExchange(&dword_1804B1930, v48 + 1, v48);
          if ( v48 == v53 )
            goto LABEL_5;
        }
        v48 = v53;
      }
    }
    v79 = (*(__int64 (**)(void))(a2 + 48))();
    v81 = 1;
    if ( v79 )
      v81 = v79;
    else
      v80 = 0;
    v77 = v87;
    LODWORD(v87[0]) = 0;
    v102 = (_QWORD *)v81;
    v103 = v80;
    BYTE4(v87[0]) = 0;
    v91 = (char **)&v114;
    v92 = core::fmt::impl_75::fmt_core::panic::location::Location_;
    v93 = (__int64)&v102;
    lpMem[0] = &off_180343908;
    lpMem[1] = (LPVOID)3;
    *((_QWORD *)&v86 + 1) = 0;
    v78 = core::fmt::impl_75::fmt_str__;
  }
  *(_QWORD *)&v94 = v78;
  v85 = (__int64)&v91;
  *(_QWORD *)&v86 = 2;
  v82 = std::io::Write::write_fmt_std::sys::stdio::windows::Stderr_(v77, lpMem);
  core::ptr::drop_in_place_enum2__core::result::Result_tuple____std::io::error::Error_____(v82);
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800d5780  push    rbp
0x1800d5781  push    r15
0x1800d5783  push    r14
0x1800d5785  push    r13
0x1800d5787  push    r12
0x1800d5789  push    rsi
0x1800d578a  push    rdi
0x1800d578b  push    rbx
0x1800d578c  sub     rsp, 598h
0x1800d5793  lea     rbp, [rsp+80h]
0x1800d579b  mov     [rbp+550h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800d57a6  mov     [rbp+550h+var_51], r9b
0x1800d57ad  mov     [rbp+550h+var_98], rcx
0x1800d57b4  mov     [rbp+550h+var_90], rdx
0x1800d57bb  mov     [rbp+550h+var_80], r8
0x1800d57c2  lock inc cs:qword_1804B1950
0x1800d57ca  jle     loc_1800D6682
0x1800d57d0  mov     eax, cs:_tls_index
0x1800d57d6  mov     r8, gs:58h
0x1800d57df  mov     rax, [r8+rax*8]
0x1800d57e3  cmp     byte ptr [rax+10h], 0
0x1800d57ea  jnz     loc_1800D66DB
0x1800d57f0  lea     rax, [rax+8]
0x1800d57f7  inc     qword ptr [rax]
0x1800d57fa  mov     [rbp+550h+var_B0], rax
0x1800d5801  mov     byte ptr [rax+8], 1
0x1800d5805  mov     eax, cs:dword_1804B1930
0x1800d580b  cmp     eax, 3FFFFFFDh
0x1800d5810  ja      loc_1800D5F6D
0x1800d5816  lea     ecx, [rax+1]
0x1800d5819  lock cmpxchg cs:dword_1804B1930, ecx
0x1800d5821  jnz     loc_1800D5F6D
0x1800d5827  mov     sil, [rbp+550h+arg_20]
0x1800d582e  mov     al, cs:byte_1804B1938
0x1800d5834  cmp     cs:qword_1804B1940, 0
0x1800d583c  jnz     loc_1800D5ACD
0x1800d5842  mov     r15, [rbp+550h+var_98]
0x1800d5849  mov     rax, [rbp+550h+var_90]
0x1800d5850  mov     [rbp+550h+var_A8], rax
0x1800d5857  mov     rax, [rax+28h]
0x1800d585b  mov     rcx, r15
0x1800d585e  call    cs:__guard_dispatch_icall_fptr
0x1800d5864  mov     [rbp+550h+var_60], rax
0x1800d586b  mov     rdi, rdx
0x1800d586e  mov     bl, 3
0x1800d5870  mov     r14, [rbp+550h+var_80]
0x1800d5877  test    sil, sil
0x1800d587a  jnz     short loc_1800D589C
0x1800d587c  mov     bl, 1
0x1800d587e  mov     rax, [rbp+550h+var_B0]
0x1800d5885  cmp     qword ptr [rax], 1
0x1800d5889  ja      short loc_1800D589C
0x1800d588b  mov     bl, cs:byte_1804B1928
0x1800d5891  dec     bl; switch 3 cases
0x1800d5893  cmp     bl, 3
0x1800d5896  jnb     def_1800D5C1C; jumptable 00000001800D5C1C default case
0x1800d589c  mov     [rbp+550h+var_F8], r14
0x1800d58a3  mov     rdi, [rdi+18h]
0x1800d58a7  lea     r14, [rbp+550h+lpMem]
0x1800d58ab  mov     rcx, r14
0x1800d58ae  mov     rdx, [rbp+550h+var_60]
0x1800d58b5  mov     rax, rdi
0x1800d58b8  call    cs:__guard_dispatch_icall_fptr
0x1800d58be  movdqa  xmm0, xmmword ptr [rbp+550h+lpMem]
0x1800d58c3  pcmpeqb xmm0, cs:__xmm@b98b1b7157a6417863eb502cd6cb5d6d
0x1800d58cb  pmovmskb eax, xmm0
0x1800d58cf  cmp     eax, 0FFFFh
0x1800d58d4  jnz     loc_1800D5B5E
0x1800d58da  push    8
0x1800d58dc  pop     rcx
0x1800d58dd  mov     rdx, [rbp+550h+var_60]
0x1800d58e4  mov     rax, rdx
0x1800d58e7  mov     rax, [rax]
0x1800d58ea  mov     rcx, [rdx+rcx]
0x1800d58ee  mov     [rbp+550h+var_108], rax
0x1800d58f5  mov     [rbp+550h+var_100], rcx
0x1800d58fc  and     [rbp+550h+var_70], 0
0x1800d5903  mov     [rbp+550h+var_6C], 0
0x1800d590a  mov     cl, 1
0x1800d590c  xor     eax, eax
0x1800d590e  lock cmpxchg cs:byte_1804B1929, cl
0x1800d5916  jnz     loc_1800D65F7
0x1800d591c  mov     rax, cs:qword_1804B1950
0x1800d5923  shl     rax, 1
0x1800d5926  test    rax, rax
0x1800d5929  mov     [rbp+550h+var_78], r15
0x1800d5930  jnz     loc_1800D6608
0x1800d5936  mov     dword ptr [rbp+550h+lpName], 0
0x1800d5940  mov     al, cs:byte_1804B192A
0x1800d5946  lea     rax, aMemoryAllocati+0F1h; "<unnamed>\nthread '' panicked at \nBox<"...
0x1800d594d  lea     rsi, [rbp+550h+var_170]
0x1800d5954  mov     [rsi], rax
0x1800d5957  mov     qword ptr [rsi+8], 9
0x1800d595f  mov     ecx, 80h
0x1800d5964  xor     eax, eax
0x1800d5966  mov     rdi, r14
0x1800d5969  rep stosd
0x1800d596b  lea     rax, [rbp+550h+var_160]
0x1800d5972  mov     [rax], r14
0x1800d5975  mov     qword ptr [rax+8], 200h
0x1800d597d  and     qword ptr [rax+10h], 0
0x1800d5982  lea     rcx, [rbp+550h+var_E0]
0x1800d5989  mov     [rcx], rsi
0x1800d598c  lea     r14, core__fmt__impl$75__fmt_str$_
0x1800d5993  mov     [rcx+8], r14
0x1800d5997  lea     r12, [rbp+550h+var_F8]
0x1800d599e  mov     [rcx+10h], r12
0x1800d59a2  lea     r13, core__fmt__impl$75__fmt_core__panic__location__Location_
0x1800d59a9  mov     [rcx+18h], r13
0x1800d59ad  lea     r15, [rbp+550h+var_108]
0x1800d59b4  mov     [rcx+20h], r15
0x1800d59b8  lea     rdi, off_180343818; "\nthread '' panicked at \nBox<dyn Any>"...
0x1800d59bf  lea     r8, [rbp+550h+var_1A0]
0x1800d59c6  mov     [r8], rdi
0x1800d59c9  mov     qword ptr [r8+8], 4
0x1800d59d1  and     qword ptr [r8+20h], 0
0x1800d59d6  mov     [rcx+28h], r14
0x1800d59da  mov     [r8+10h], rcx
0x1800d59de  mov     qword ptr [r8+18h], 3
0x1800d59e6  lea     rcx, [rbp+550h+var_118]
0x1800d59ed  mov     [rcx], rax
0x1800d59f0  and     qword ptr [rcx+8], 0
0x1800d59f5  lea     rdx, off_1803434E8
0x1800d59fc  call    core__fmt__write
0x1800d5a01  mov     rcx, [rbp+550h+var_110]
0x1800d5a08  movzx   ebx, bl
0x1800d5a0b  test    al, al
0x1800d5a0d  jz      loc_1800D5BC7
0x1800d5a13  test    rcx, rcx
0x1800d5a16  jz      loc_1800D661A
0x1800d5a1c  mov     eax, ecx
0x1800d5a1e  and     eax, 3
0x1800d5a21  cmp     eax, 1
0x1800d5a24  jz      loc_1800D5E6A
0x1800d5a2a  lea     rax, [rbp+550h+var_148]
0x1800d5a31  mov     [rax], rsi
0x1800d5a34  mov     [rax+8], r14
0x1800d5a38  mov     [rax+10h], r12
0x1800d5a3c  mov     [rax+18h], r13
0x1800d5a40  lea     rdx, [rbp+550h+var_E0]
0x1800d5a47  mov     [rdx], rdi
0x1800d5a4a  mov     qword ptr [rdx+8], 4
0x1800d5a52  and     qword ptr [rdx+20h], 0
0x1800d5a57  mov     [rax+20h], r15
0x1800d5a5b  mov     [rax+28h], r14
0x1800d5a5f  mov     [rdx+10h], rax
0x1800d5a63  mov     qword ptr [rdx+18h], 3
0x1800d5a6b  lea     rcx, [rbp+550h+var_70]
0x1800d5a72  call    std__io__Write__write_fmt_std__sys__stdio__windows__Stderr_
0x1800d5a77  mov     rdi, [rbp+550h+var_78]
0x1800d5a7e  mov     ecx, eax
0x1800d5a80  and     ecx, 3
0x1800d5a83  cmp     ecx, 1
0x1800d5a86  jnz     loc_1800D5C0E
0x1800d5a8c  mov     rcx, rax
0x1800d5a8f  dec     rcx
0x1800d5a92  mov     [rbp+550h+var_50], rcx
0x1800d5a99  mov     rcx, [rax-1]
0x1800d5a9d  mov     [rbp+550h+var_48], rcx
0x1800d5aa4  mov     rax, [rax+7]
0x1800d5aa8  mov     [rbp+550h+var_60], rax
0x1800d5aaf  mov     rax, [rax]
0x1800d5ab2  test    rax, rax
0x1800d5ab5  jz      loc_1800D6193
0x1800d5abb  mov     rcx, [rbp+550h+var_48]
0x1800d5ac2  call    cs:__guard_dispatch_icall_fptr
0x1800d5ac8  jmp     loc_1800D6193
0x1800d5acd  mov     rdi, [rbp+550h+var_98]
0x1800d5ad4  mov     rax, [rbp+550h+var_90]
0x1800d5adb  mov     [rbp+550h+var_A8], rax
0x1800d5ae2  mov     rax, [rax+28h]
0x1800d5ae6  mov     rcx, rdi
0x1800d5ae9  call    cs:__guard_dispatch_icall_fptr
0x1800d5aef  lea     r8, [rbp+550h+lpMem]
0x1800d5af3  mov     [r8], rax
0x1800d5af6  mov     [r8+8], rdx
0x1800d5afa  mov     rax, [rbp+550h+var_80]
0x1800d5b01  mov     [r8+10h], rax
0x1800d5b05  mov     al, [rbp+550h+var_51]
0x1800d5b0b  mov     [r8+18h], al
0x1800d5b0f  mov     [r8+19h], sil
0x1800d5b13  mov     rcx, cs:qword_1804B1940
0x1800d5b1a  mov     rax, cs:qword_1804B1948
0x1800d5b21  mov     rax, [rax+28h]
0x1800d5b25  mov     rdx, r8
0x1800d5b28  call    cs:__guard_dispatch_icall_fptr
0x1800d5b2e  call    core__ptr__drop_in_place_std__sync__poison__rwlock__RwLockReadGuard_enum2$_std__panicking__Hook_____
0x1800d5b33  mov     rax, [rbp+550h+var_B0]
0x1800d5b3a  mov     byte ptr [rax+8], 0
0x1800d5b3e  cmp     [rbp+550h+var_51], 0
0x1800d5b45  jz      loc_1800D6776
0x1800d5b4b  mov     rax, [rbp+550h+var_A8]
0x1800d5b52  mov     rdx, [rax+20h]
0x1800d5b56  mov     rcx, rdi
0x1800d5b59  call    std__panicking__rust_panic
0x1800d5b5e  lea     rcx, [rbp+550h+lpMem]
0x1800d5b62  mov     rdx, [rbp+550h+var_60]
0x1800d5b69  mov     rax, rdi
0x1800d5b6c  call    cs:__guard_dispatch_icall_fptr
0x1800d5b72  movdqa  xmm0, xmmword ptr [rbp+550h+lpMem]
0x1800d5b77  pcmpeqb xmm0, cs:__xmm@957d6101b07cf4dabb308db8cf471cda
0x1800d5b7f  pmovmskb eax, xmm0
0x1800d5b83  cmp     eax, 0FFFFh
0x1800d5b88  jnz     loc_1800D5D71
0x1800d5b8e  mov     rdx, [rbp+550h+var_60]
0x1800d5b95  mov     rax, rdx
0x1800d5b98  add     rax, 8
0x1800d5b9c  push    10h
0x1800d5b9e  pop     rcx
0x1800d5b9f  jmp     loc_1800D58E7
0x1800d5ba4  push    1Eh; jumptable 00000001800D5C1C default case
0x1800d5ba6  pop     rdx
0x1800d5ba7  xor     ecx, ecx
0x1800d5ba9  call    std__sys__alloc__windows__process_heap_alloc
0x1800d5bae  test    rax, rax
0x1800d5bb1  jnz     loc_1800D5C39
0x1800d5bb7  push    2
0x1800d5bb9  pop     rcx
0x1800d5bba  push    1Eh
0x1800d5bbc  pop     rdx
0x1800d5bbd  call    alloc__alloc__handle_alloc_error
0x1800d5bc2  jmp     loc_1800D6680
0x1800d5bc7  mov     eax, ecx
0x1800d5bc9  and     eax, 3
0x1800d5bcc  cmp     eax, 1
0x1800d5bcf  mov     rdi, [rbp+550h+var_78]
0x1800d5bd6  jz      loc_1800D5EFC
0x1800d5bdc  mov     r8, [rbp+550h+var_150]
0x1800d5be3  cmp     r8, 200h
0x1800d5bea  ja      loc_1800D6652
0x1800d5bf0  lea     rcx, [rbp+550h+var_70]
0x1800d5bf7  lea     rdx, [rbp+550h+lpMem]
0x1800d5bfb  call    std__io__Write__write_all_std__sys__stdio__windows__Stderr_
0x1800d5c00  mov     ecx, eax
0x1800d5c02  and     ecx, 3
0x1800d5c05  cmp     ecx, 1
0x1800d5c08  jz      loc_1800D615B
0x1800d5c0e  lea     rax, jpt_1800D5C1C
0x1800d5c15  movsxd  rcx, ds:(jpt_1800D5C1C - 180407328h)[rax+rbx*4]
0x1800d5c19  add     rcx, rax
0x1800d5c1c  jmp     rcx; switch jump
0x1800d5c1e  lea     rcx, [rbp+550h+var_70]; jumptable 00000001800D5C1C case 1
0x1800d5c25  xor     edx, edx
0x1800d5c27  call    std__sys__backtrace__BacktraceLock__print
0x1800d5c2c  mov     rcx, rax
0x1800d5c2f  call    core__ptr__drop_in_place_enum2$_core__result__Result_tuple$___std__io__error__Error_____
0x1800d5c34  jmp     loc_1800D6295
0x1800d5c39  mov     [rbp+550h+var_E8], r14
0x1800d5c40  mov     [rbp+550h+var_F0], rdi
0x1800d5c47  mov     [rbp+550h+var_78], r15
0x1800d5c4e  lea     r14, [rbp+550h+lpMem]
0x1800d5c52  mov     qword ptr [r14], 0Fh
0x1800d5c59  mov     [r14+8], rax
0x1800d5c5d  and     qword ptr [r14+10h], 0
0x1800d5c62  xor     r13d, r13d
0x1800d5c65  lea     rdi, aRustBacktracel; "RUST_BACKTRACElibrary\\std\\src\\sys_co"...
0x1800d5c6c  push    11h
0x1800d5c6e  pop     rbx
0x1800d5c6f  xor     r15d, r15d
0x1800d5c72  xor     esi, esi
0x1800d5c74  test    si, si
0x1800d5c77  jnz     loc_1800D5CFF
0x1800d5c7d  cmp     r15, 0Eh
0x1800d5c81  jz      loc_1800D5D80
0x1800d5c87  mov     dl, [r15+rdi]
0x1800d5c8b  movzx   esi, dl
0x1800d5c8e  test    sil, sil
0x1800d5c91  js      short loc_1800D5C98
0x1800d5c93  inc     r15
0x1800d5c96  jmp     short loc_1800D5CFF
0x1800d5c98  mov     ecx, esi
0x1800d5c9a  and     ecx, 1Fh
0x1800d5c9d  movzx   r8d, byte ptr [r15+rdi+1]
0x1800d5ca3  and     r8d, 3Fh
0x1800d5ca7  cmp     sil, 0DFh
0x1800d5cab  jbe     short loc_1800D5CE0
0x1800d5cad  movzx   esi, byte ptr [r15+rdi+2]
0x1800d5cb3  shl     r8d, 6
0x1800d5cb7  and     esi, 3Fh
0x1800d5cba  or      esi, r8d
0x1800d5cbd  cmp     dl, 0F0h
0x1800d5cc0  jb      short loc_1800D5CEE
0x1800d5cc2  movzx   edx, byte ptr [r15+rdi+3]
0x1800d5cc8  add     r15, 4
0x1800d5ccc  and     ecx, 7
0x1800d5ccf  shl     ecx, 12h
0x1800d5cd2  shl     esi, 6
0x1800d5cd5  and     edx, 3Fh
0x1800d5cd8  or      edx, esi
0x1800d5cda  or      edx, ecx
0x1800d5cdc  mov     esi, edx
0x1800d5cde  jmp     short loc_1800D5CF7
0x1800d5ce0  add     r15, 2
0x1800d5ce4  shl     ecx, 6
0x1800d5ce7  or      ecx, r8d
0x1800d5cea  mov     esi, ecx
0x1800d5cec  jmp     short loc_1800D5CFF
0x1800d5cee  add     r15, 3
0x1800d5cf2  shl     ecx, 0Ch
0x1800d5cf5  or      esi, ecx
  ... truncated ...
```
