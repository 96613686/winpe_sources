# CFullPropSpec::SetProperty(wchar_t const *)

- ea: `0x180005aa4`
- end: `0x180005b19`
- name: `?SetProperty@CFullPropSpec@@QEAAHPEB_W@Z`
- size: `117`
- prototype: `int(CFullPropSpec *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800057b8`
- `0x18002172c`

## callees

- `0x180005aa4`
- `0x180023388`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005ad5`

## pseudocode

```c
__int64 __fastcall CFullPropSpec::SetProperty(CFullPropSpec *this, const wchar_t *a2)
{
  __int64 v4; // rax
  SIZE_T v5; // rsi
  void *v6; // rax
  void *v8; // rcx

  if ( !*((_DWORD *)this + 4) )
  {
    v8 = (void *)*((_QWORD *)this + 3);
    if ( v8 )
      CoTaskMemFree(v8);
  }
  *((_DWORD *)this + 4) = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 2 * v4 + 2;
  v6 = CoTaskMemAlloc(v5);
  *((_QWORD *)this + 3) = v6;
  if ( v6 )
  {
    memcpy_0(v6, a2, v5);
    return 1;
  }
  else
  {
    *((_QWORD *)this + 3) = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180005aa4  push    rbx
0x180005aa6  push    rbp
0x180005aa7  push    rsi
0x180005aa8  push    rdi
0x180005aa9  sub     rsp, 28h
0x180005aad  xor     ebp, ebp
0x180005aaf  mov     rdi, rdx
0x180005ab2  mov     rbx, rcx
0x180005ab5  cmp     [rcx+10h], ebp
0x180005ab8  jz      short loc_180005B08
0x180005aba  mov     [rbx+10h], ebp
0x180005abd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ac1  inc     rax
0x180005ac4  cmp     [rdi+rax*2], bp
0x180005ac8  jnz     short loc_180005AC1
0x180005aca  lea     rsi, ds:2[rax*2]
0x180005ad2  mov     rcx, rsi; cb
0x180005ad5  call    cs:__imp_CoTaskMemAlloc
0x180005adb  mov     [rbx+18h], rax
0x180005adf  test    rax, rax
0x180005ae2  jz      short loc_180005B00
0x180005ae4  mov     r8, rsi; Size
0x180005ae7  mov     rdx, rdi; Src
0x180005aea  mov     rcx, rax; void *
0x180005aed  call    memcpy_0
0x180005af2  mov     eax, 1
0x180005af7  add     rsp, 28h
0x180005afb  pop     rdi
0x180005afc  pop     rsi
0x180005afd  pop     rbp
0x180005afe  pop     rbx
0x180005aff  retn
0x180005b00  mov     [rbx+18h], rbp
0x180005b04  xor     eax, eax
0x180005b06  jmp     short loc_180005AF7
0x180005b08  mov     rcx, [rcx+18h]; pv
0x180005b0c  test    rcx, rcx
0x180005b0f  jz      short loc_180005ABA
0x180005b11  call    cs:__imp_CoTaskMemFree
0x180005b17  jmp     short loc_180005ABA
```
