# CheckUseWow6432Node(ulong,bool *)

- ea: `0x180037714`
- end: `0x18003784b`
- name: `?CheckUseWow6432Node@@YAJKPEA_N@Z`
- size: `311`
- prototype: `__int64 __fastcall(__int16, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003784c`

## callees

- `0x180030530`
- `0x1800374f0`
- `0x180037714`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800377fe`
- `ADVAPI32!RegCloseKey` at `0x1800377fe`
- `ADVAPI32!RegOpenKeyExW` at `0x1800377dc`
- `ADVAPI32!RegOpenKeyExW` at `0x1800377dc`
- `ucrtbase_clr0400!wcscpy_s` at `0x180037795`
- `ucrtbase_clr0400!wcscpy_s` at `0x180037795`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CheckUseWow6432Node(__int16 a1, bool *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rbx
  unsigned __int64 v6; // rbx
  unsigned __int128 v7; // rax
  wchar_t *v8; // rax
  unsigned __int16 *v9; // rbp
  char v10; // al
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  v4 = 0;
  if ( !byte_180070798 )
  {
    v5 = -1;
    do
      ++v5;
    while ( qword_180070038[v5] );
    v6 = v5 + 43;
    v7 = v6 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v6, 2u) )
      *(_QWORD *)&v7 = -1;
    v8 = (wchar_t *)operator new(v7, *((const struct NoThrow **)&v7 + 1));
    v9 = v8;
    if ( !v8 )
      return 8;
    wcscpy_s(v8, v6, qword_180070038);
    StringCchCatW(v9, v6, L"Wow6432Node\\");
    StringCchCatW(v9, v6, L"Microsoft\\.NETFramework\\Policy");
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey);
    byte_18007079A = v4 == 0;
    if ( v4 == 2 )
      v4 = 0;
    if ( hKey )
      RegCloseKey(hKey);
    byte_180070798 = 1;
  }
  v10 = byte_18007079A;
  if ( !v4 )
  {
    *a2 = 0;
    if ( v10 )
    {
      if ( (a1 & 0x100) == 0 )
        *a2 = (a1 & 0x200) != 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180037714  mov     [rsp+arg_0], rbx
0x180037719  mov     [rsp+arg_8], rbp
0x18003771e  mov     [rsp+arg_18], rsi
0x180037723  push    rdi
0x180037724  push    r14
0x180037726  push    r15
0x180037728  sub     rsp, 30h
0x18003772c  xor     r14d, r14d
0x18003772f  mov     rdi, rdx
0x180037732  cmp     cs:byte_180070798, r14b
0x180037739  mov     esi, ecx
0x18003773b  mov     ebx, r14d
0x18003773e  lea     r15d, [r14+1]
0x180037742  jnz     loc_18003780B
0x180037748  mov     rax, cs:qword_180070038
0x18003774f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180037753  mov     rbx, rcx
0x180037756  inc     rbx
0x180037759  cmp     [rax+rbx*2], r14w
0x18003775e  jnz     short loc_180037756
0x180037760  add     rbx, 2Bh ; '+'
0x180037764  mov     eax, 2
0x180037769  mul     rbx
0x18003776c  cmovo   rax, rcx
0x180037770  mov     rcx, rax; dwBytes
0x180037773  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180037778  mov     rbp, rax
0x18003777b  test    rax, rax
0x18003777e  jnz     short loc_180037788
0x180037780  lea     ebx, [rax+8]
0x180037783  jmp     loc_180037830
0x180037788  mov     r8, cs:qword_180070038; Source
0x18003778f  mov     rdx, rbx; SizeInWords
0x180037792  mov     rcx, rbp; Destination
0x180037795  call    cs:__imp_wcscpy_s
0x18003779b  lea     r8, aWow6432node; "Wow6432Node\\"
0x1800377a2  mov     rdx, rbx; unsigned __int64
0x1800377a5  mov     rcx, rbp; unsigned __int16 *
0x1800377a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377ad  lea     r8, aMicrosoftNetfr; "Microsoft\\.NETFramework\\Policy"
0x1800377b4  mov     rdx, rbx; unsigned __int64
0x1800377b7  mov     rcx, rbp; unsigned __int16 *
0x1800377ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377bf  lea     rax, [rsp+48h+hKey]
0x1800377c4  mov     r9d, 20019h; samDesired
0x1800377ca  xor     r8d, r8d; ulOptions
0x1800377cd  mov     [rsp+48h+phkResult], rax; phkResult
0x1800377d2  mov     rdx, rbp; lpSubKey
0x1800377d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800377dc  call    cs:__imp_RegOpenKeyExW
0x1800377e2  mov     rcx, [rsp+48h+hKey]; hKey
0x1800377e7  test    eax, eax
0x1800377e9  mov     ebx, eax
0x1800377eb  setz    cs:byte_18007079A
0x1800377f2  cmp     eax, 2
0x1800377f5  cmovz   ebx, r14d
0x1800377f9  test    rcx, rcx
0x1800377fc  jz      short loc_180037804
0x1800377fe  call    cs:__imp_RegCloseKey
0x180037804  mov     cs:byte_180070798, r15b
0x18003780b  mov     al, cs:byte_18007079A
0x180037811  test    ebx, ebx
0x180037813  jnz     short loc_180037830
0x180037815  mov     [rdi], r14b
0x180037818  test    al, al
0x18003781a  jz      short loc_180037830
0x18003781c  bt      esi, 8
0x180037820  jb      short loc_180037830
0x180037822  bt      esi, 9
0x180037826  movzx   ecx, r14b
0x18003782a  cmovb   ecx, r15d
0x18003782e  mov     [rdi], cl
0x180037830  mov     rbp, [rsp+48h+arg_8]
0x180037835  mov     eax, ebx
0x180037837  mov     rbx, [rsp+48h+arg_0]
0x18003783c  mov     rsi, [rsp+48h+arg_18]
0x180037841  add     rsp, 30h
0x180037845  pop     r15
0x180037847  pop     r14
0x180037849  pop     rdi
0x18003784a  retn
```
