# CWriter::Initialize(ushort const *,CWriterGlobalHelper *,void *)

- ea: `0x18002a818`
- end: `0x18002a992`
- name: `?Initialize@CWriter@@QEAAJPEBGPEAVCWriterGlobalHelper@@PEAX@Z`
- size: `378`
- prototype: `int(CWriter *__hidden this, const unsigned __int16 *, struct CWriterGlobalHelper *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180023e00`

## callees

- `0x180002af0`
- `0x18002a6f0`
- `0x18002a818`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002a882`
- `msvcrt!wcscpy_s` at `0x18002a882`
- `ole32!CoTaskMemAlloc` at `0x18002a861`
- `ole32!CoTaskMemAlloc` at `0x18002a861`

## pseudocode

```c
__int64 __fastcall CWriter::Initialize(
        CWriter *this,
        const unsigned __int16 *a2,
        struct CWriterGlobalHelper *a3,
        void *a4)
{
  __int64 v6; // rax
  rsize_t v7; // rsi
  wchar_t *v8; // rax
  int GlobalHelper; // ebx
  __int64 v10; // rcx
  void *v12; // [rsp+80h] [rbp+18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h] BYREF

  v12 = 0;
  v13 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + 1;
  v8 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v6 + 1, 2u));
  *(_QWORD *)this = v8;
  if ( v8 )
  {
    wcscpy_s(v8, v7, a2);
    *((_QWORD *)this + 8199) = 0;
    *((_QWORD *)this + 8200) = 0;
    *((_DWORD *)this + 4) = 0;
    GlobalHelper = GetGlobalHelper(v10, (struct CWriterGlobalHelper **)this + 8200);
    if ( GlobalHelper >= 0 )
    {
      *((_DWORD *)this + 3) = 1;
      GlobalHelper = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v12);
      if ( GlobalHelper >= 0 )
      {
        GlobalHelper = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v12)(
                         v12,
                         &IID_IAdvancedTableDispenser,
                         &v13);
        if ( GlobalHelper >= 0 )
          GlobalHelper = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, _QWORD, int, int, char *))(*(_QWORD *)v13 + 32LL))(
                           v13,
                           L"METABASE",
                           L"MBProperty",
                           0,
                           0,
                           0,
                           3,
                           2,
                           (char *)this + 65608);
      }
    }
  }
  else
  {
    GlobalHelper = -2147024882;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)GlobalHelper;
}

```

## disassembly

```asm
0x18002a818  mov     rax, rsp
0x18002a81b  mov     [rax+8], rbx
0x18002a81f  mov     [rax+20h], r9
0x18002a823  mov     [rax+18h], r8
0x18002a827  push    rbp
0x18002a828  push    rsi
0x18002a829  push    rdi
0x18002a82a  sub     rsp, 50h
0x18002a82e  xor     ebp, ebp
0x18002a830  mov     rdi, rcx
0x18002a833  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002a837  mov     [rax+18h], rbp
0x18002a83b  mov     [rax+20h], rbp
0x18002a83f  mov     rbx, rdx
0x18002a842  mov     rax, rcx
0x18002a845  inc     rax
0x18002a848  cmp     [rdx+rax*2], bp
0x18002a84c  jnz     short loc_18002A845
0x18002a84e  lea     rsi, [rax+1]
0x18002a852  mov     eax, 2
0x18002a857  mul     rsi
0x18002a85a  cmovb   rax, rcx
0x18002a85e  mov     rcx, rax; cb
0x18002a861  call    cs:__imp_CoTaskMemAlloc
0x18002a867  mov     [rdi], rax
0x18002a86a  test    rax, rax
0x18002a86d  jnz     short loc_18002A879
0x18002a86f  mov     ebx, 8007000Eh
0x18002a874  jmp     loc_18002A949
0x18002a879  mov     r8, rbx; Source
0x18002a87c  mov     rdx, rsi; SizeInWords
0x18002a87f  mov     rcx, rax; Destination
0x18002a882  call    cs:__imp_wcscpy_s
0x18002a888  lea     rdx, [rdi+10040h]; struct CWriterGlobalHelper **
0x18002a88f  mov     [rdi+10038h], rbp
0x18002a896  mov     [rdx], rbp
0x18002a899  mov     [rdi+10h], ebp
0x18002a89c  call    ?GetGlobalHelper@@YAJHPEAPEAVCWriterGlobalHelper@@@Z; GetGlobalHelper(int,CWriterGlobalHelper * *)
0x18002a8a1  mov     ebx, eax
0x18002a8a3  test    eax, eax
0x18002a8a5  js      loc_18002A949
0x18002a8ab  mov     ecx, 1
0x18002a8b0  lea     r9, aIis; "IIS"
0x18002a8b7  lea     r8, [rsp+68h+arg_10]
0x18002a8bf  mov     [rdi+0Ch], ecx
0x18002a8c2  lea     rdx, IID_ISimpleTableDispenser2
0x18002a8c9  call    DllGetSimpleObjectByIDEx
0x18002a8ce  mov     ebx, eax
0x18002a8d0  test    eax, eax
0x18002a8d2  js      short loc_18002A949
0x18002a8d4  mov     rcx, [rsp+68h+arg_10]
0x18002a8dc  lea     r8, [rsp+68h+arg_18]
0x18002a8e4  lea     rdx, IID_IAdvancedTableDispenser
0x18002a8eb  mov     rax, [rcx]
0x18002a8ee  mov     rax, [rax]
0x18002a8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8f6  mov     ebx, eax
0x18002a8f8  test    eax, eax
0x18002a8fa  js      short loc_18002A949
0x18002a8fc  mov     rcx, [rsp+68h+arg_18]
0x18002a904  lea     rdx, [rdi+10048h]
0x18002a90b  mov     [rsp+68h+var_28], rdx
0x18002a910  lea     r8, aMbproperty; "MBProperty"
0x18002a917  mov     [rsp+68h+var_30], 2
0x18002a91f  lea     rdx, aMetabase; "METABASE"
0x18002a926  mov     [rsp+68h+var_38], 3
0x18002a92e  xor     r9d, r9d
0x18002a931  mov     rax, [rcx]
0x18002a934  mov     [rsp+68h+var_40], rbp
0x18002a939  mov     [rsp+68h+var_48], rbp
0x18002a93e  mov     rax, [rax+20h]
0x18002a942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a947  mov     ebx, eax
0x18002a949  mov     rcx, [rsp+68h+arg_18]
0x18002a951  test    rcx, rcx
0x18002a954  jz      short loc_18002A96A
0x18002a956  mov     rax, [rcx]
0x18002a959  mov     rax, [rax+10h]
0x18002a95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a962  mov     [rsp+68h+arg_18], rbp
0x18002a96a  mov     rcx, [rsp+68h+arg_10]
0x18002a972  test    rcx, rcx
0x18002a975  jz      short loc_18002A983
0x18002a977  mov     rax, [rcx]
0x18002a97a  mov     rax, [rax+10h]
0x18002a97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a983  mov     eax, ebx
0x18002a985  mov     rbx, [rsp+68h+arg_0]
0x18002a98a  add     rsp, 50h
0x18002a98e  pop     rdi
0x18002a98f  pop     rsi
0x18002a990  pop     rbp
0x18002a991  retn
```
