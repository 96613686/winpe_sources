# XMLScrSite::CheckRuntimeSettings(void)

- ea: `0x1400113b0`
- end: `0x1400114b7`
- name: `?CheckRuntimeSettings@XMLScrSite@@UEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400113b0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140011419`
- `OLEAUT32!__imp_SysAllocString` at `0x140011419`

## pseudocode

```c
__int64 __fastcall XMLScrSite::CheckRuntimeSettings(XMLScrSite *this)
{
  __int64 v1; // rax
  int v3; // ebx
  BSTR v4; // rax
  __int16 v6; // [rsp+40h] [rbp+20h] BYREF
  __int64 v7; // [rsp+48h] [rbp+28h] BYREF
  __int64 v8; // [rsp+50h] [rbp+30h] BYREF

  v1 = *((_QWORD *)this + 2);
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v1 + 624) + 128LL))(*(_QWORD *)(v1 + 624), &v7);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 88LL))(v7, &v8);
    if ( v3 >= 0 )
    {
      v4 = SysAllocString(L"?");
      v3 = (*(__int64 (__fastcall **)(__int64, BSTR, __int16 *))(*(_QWORD *)v8 + 80LL))(v8, v4, &v6);
      if ( v3 >= 0 )
      {
        if ( v6 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 104LL))(v7);
          if ( v3 >= 0 )
          {
            v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 624LL) + 104LL))(
                   *(_QWORD *)(*((_QWORD *)this + 2) + 624LL),
                   0);
            if ( v3 >= 0 )
              v3 = 1;
          }
        }
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400113b0  mov     [rsp-18h+arg_18], rbx
0x1400113b5  push    rbp
0x1400113b6  push    rsi
0x1400113b7  push    rdi
0x1400113b8  mov     rbp, rsp
0x1400113bb  sub     rsp, 20h
0x1400113bf  mov     rax, [rcx+10h]
0x1400113c3  lea     rdx, [rbp+arg_8]
0x1400113c7  xor     esi, esi
0x1400113c9  mov     rdi, rcx
0x1400113cc  mov     [rbp+arg_0], si
0x1400113d0  mov     [rbp+arg_8], rsi
0x1400113d4  mov     [rbp+arg_10], rsi
0x1400113d8  mov     rcx, [rax+270h]
0x1400113df  mov     rax, [rcx]
0x1400113e2  mov     rax, [rax+80h]
0x1400113e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113ee  mov     ebx, eax
0x1400113f0  test    eax, eax
0x1400113f2  js      loc_14001147E
0x1400113f8  mov     rcx, [rbp+arg_8]
0x1400113fc  lea     rdx, [rbp+arg_10]
0x140011400  mov     rax, [rcx]
0x140011403  mov     rax, [rax+58h]
0x140011407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001140c  mov     ebx, eax
0x14001140e  test    eax, eax
0x140011410  js      short loc_14001147E
0x140011412  lea     rcx, asc_14001A1A4; "?"
0x140011419  call    cs:__imp_SysAllocString
0x14001141f  mov     rcx, [rbp+arg_10]
0x140011423  lea     r8, [rbp+arg_0]
0x140011427  mov     r9, rax
0x14001142a  mov     rdx, [rcx]
0x14001142d  mov     rax, [rdx+50h]
0x140011431  mov     rdx, r9
0x140011434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011439  mov     ebx, eax
0x14001143b  test    eax, eax
0x14001143d  js      short loc_14001147E
0x14001143f  cmp     [rbp+arg_0], si
0x140011443  jz      short loc_14001147E
0x140011445  mov     rcx, [rbp+arg_8]
0x140011449  mov     rax, [rcx]
0x14001144c  mov     rax, [rax+68h]
0x140011450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011455  mov     ebx, eax
0x140011457  test    eax, eax
0x140011459  js      short loc_14001147E
0x14001145b  mov     rax, [rdi+10h]
0x14001145f  xor     edx, edx
0x140011461  mov     rcx, [rax+270h]
0x140011468  mov     rax, [rcx]
0x14001146b  mov     rax, [rax+68h]
0x14001146f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011474  mov     ebx, eax
0x140011476  lea     eax, [rsi+1]
0x140011479  test    ebx, ebx
0x14001147b  cmovns  ebx, eax
0x14001147e  mov     rcx, [rbp+arg_8]
0x140011482  test    rcx, rcx
0x140011485  jz      short loc_140011493
0x140011487  mov     rax, [rcx]
0x14001148a  mov     rax, [rax+10h]
0x14001148e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011493  mov     rcx, [rbp+arg_10]
0x140011497  test    rcx, rcx
0x14001149a  jz      short loc_1400114A8
0x14001149c  mov     rax, [rcx]
0x14001149f  mov     rax, [rax+10h]
0x1400114a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114a8  mov     eax, ebx
0x1400114aa  mov     rbx, [rsp+20h+arg_18]
0x1400114af  add     rsp, 20h
0x1400114b3  pop     rdi
0x1400114b4  pop     rsi
0x1400114b5  pop     rbp
0x1400114b6  retn
```
