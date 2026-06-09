# CSSMappedStream::SetSize(ulong,uchar,void * *,long *)

- ea: `0x1800379c0`
- end: `0x180037a7c`
- name: `?SetSize@CSSMappedStream@@UEAAXKEPEAPEAXPEAJ@Z`
- size: `188`
- prototype: `void(CSSMappedStream *__hidden this, unsigned int, unsigned __int8, void **, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800379c0`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a51`

## pseudocode

```c
void __fastcall CSSMappedStream::SetSize(CSSMappedStream *this, unsigned int a2, char a3, void **a4, int *a5)
{
  SIZE_T v6; // rbx
  int v8; // eax
  void *v9; // rbp
  unsigned int v10; // eax

  v6 = a2;
  *a5 = 0;
  if ( a2 - 1 > 0x1FFFFF )
  {
    *a5 = -2147418113;
    return;
  }
  if ( a3 && a2 > *((_DWORD *)this + 9) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 48LL))(*((_QWORD *)this + 2), a2);
    *a5 = v8;
    if ( v8 < 0 )
      return;
    *((_DWORD *)this + 9) = v6;
  }
  if ( (_DWORD)v6 != *((_DWORD *)this + 8) )
  {
    v9 = CoTaskMemAlloc(v6);
    if ( !v9 )
    {
      *a5 = -2147024882;
      return;
    }
    v10 = *((_DWORD *)this + 8);
    if ( (unsigned int)v6 < v10 )
      v10 = v6;
    memcpy_0(v9, *((const void **)this + 3), v10);
    CoTaskMemFree(*((LPVOID *)this + 3));
    *((_QWORD *)this + 3) = v9;
    *a4 = v9;
  }
  *((_DWORD *)this + 8) = v6;
}

```

## disassembly

```asm
0x1800379c0  push    rbx
0x1800379c2  push    rbp
0x1800379c3  push    rsi
0x1800379c4  push    rdi
0x1800379c5  push    r14
0x1800379c7  sub     rsp, 20h
0x1800379cb  mov     rsi, [rsp+48h+arg_20]
0x1800379d0  mov     r14, r9
0x1800379d3  mov     ebx, edx
0x1800379d5  mov     rdi, rcx
0x1800379d8  mov     dword ptr [rsi], 0
0x1800379de  lea     eax, [rbx-1]
0x1800379e1  cmp     eax, 1FFFFFh
0x1800379e6  ja      loc_180037A6C
0x1800379ec  test    r8b, r8b
0x1800379ef  jz      short loc_180037A20
0x1800379f1  cmp     ebx, [rcx+24h]
0x1800379f4  jbe     short loc_180037A20
0x1800379f6  mov     rcx, [rcx+10h]
0x1800379fa  mov     dword ptr [rsp+48h+arg_20+4], 0
0x180037a02  mov     dword ptr [rsp+48h+arg_20], ebx
0x180037a06  mov     rdx, [rsp+48h+arg_20]
0x180037a0b  mov     rax, [rcx]
0x180037a0e  mov     rax, [rax+30h]
0x180037a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a17  mov     [rsi], eax
0x180037a19  test    eax, eax
0x180037a1b  js      short loc_180037A61
0x180037a1d  mov     [rdi+24h], ebx
0x180037a20  cmp     ebx, [rdi+20h]
0x180037a23  jz      short loc_180037A5E
0x180037a25  mov     rcx, rbx; cb
0x180037a28  call    cs:__imp_CoTaskMemAlloc
0x180037a2e  mov     rbp, rax
0x180037a31  test    rax, rax
0x180037a34  jz      short loc_180037A74
0x180037a36  mov     eax, [rdi+20h]
0x180037a39  mov     rcx, rbp; void *
0x180037a3c  mov     rdx, [rdi+18h]; Src
0x180037a40  cmp     ebx, eax
0x180037a42  cmovb   eax, ebx
0x180037a45  mov     r8d, eax; Size
0x180037a48  call    memcpy_0
0x180037a4d  mov     rcx, [rdi+18h]; pv
0x180037a51  call    cs:__imp_CoTaskMemFree
0x180037a57  mov     [rdi+18h], rbp
0x180037a5b  mov     [r14], rbp
0x180037a5e  mov     [rdi+20h], ebx
0x180037a61  add     rsp, 20h
0x180037a65  pop     r14
0x180037a67  pop     rdi
0x180037a68  pop     rsi
0x180037a69  pop     rbp
0x180037a6a  pop     rbx
0x180037a6b  retn
0x180037a6c  mov     dword ptr [rsi], 8000FFFFh
0x180037a72  jmp     short loc_180037A61
0x180037a74  mov     dword ptr [rsi], 8007000Eh
0x180037a7a  jmp     short loc_180037A61
```
