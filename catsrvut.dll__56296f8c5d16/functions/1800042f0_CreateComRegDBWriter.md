# CreateComRegDBWriter

- ea: `0x1800042f0`
- end: `0x18000445c`
- name: `CreateComRegDBWriter`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800042f0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004315`
- `VSSAPI!CreateWriter` at `0x18000437e`
- `VSSAPI!CreateWriter` at `0x18000437e`

## string_xrefs

- `0x180004391`: `COM+ REGDB Writer`

## pseudocode

```c
__int64 CreateComRegDBWriter()
{
  _QWORD *v1; // rax
  _QWORD *v2; // rsi
  int Writer; // edi
  __int64 v4; // rcx
  __int64 (__fastcall *v5)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, _BYTE); // rax
  __int128 v6; // [rsp+70h] [rbp-28h] BYREF

  if ( CComRegDBWriter::sm_pWriter )
    return 0;
  v1 = CoTaskMemAlloc(0x18u);
  if ( v1 )
  {
    v2 = v1 + 1;
    *v1 = &CComRegDBWriter::`vftable';
    v1[1] = 0;
    *((_DWORD *)v1 + 4) = 0;
    CComRegDBWriter::sm_pWriter = (struct CComRegDBWriter *)v1;
    if ( !v1[1] )
    {
      Writer = CreateWriter(v1, v1 + 1);
      if ( Writer < 0 )
        return (unsigned int)Writer;
      v4 = *v2;
      v5 = *(__int64 (__fastcall **)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, _BYTE))(*(_QWORD *)*v2 + 24LL);
      v6 = xmmword_180060BE8;
      Writer = v5(v4, &v6, L"COM+ REGDB Writer", 0, 0, 0, 1, 3, 1, 60000, 1, 0);
      if ( Writer < 0 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
        *v2 = 0;
        return (unsigned int)Writer;
      }
      if ( *v2 )
        return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 32LL))(*v2, 0, 6);
    }
    return (unsigned int)-2147467259;
  }
  CComRegDBWriter::sm_pWriter = 0;
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800042f0  push    rbx
0x1800042f2  sub     rsp, 90h
0x1800042f9  cmp     cs:?sm_pWriter@CComRegDBWriter@@0PEAV1@EA, 0; CComRegDBWriter * CComRegDBWriter::sm_pWriter
0x180004301  jz      short loc_180004310
0x180004303  xor     ebx, ebx
0x180004305  mov     eax, ebx
0x180004307  add     rsp, 90h
0x18000430e  pop     rbx
0x18000430f  retn
0x180004310  mov     ecx, 18h; cb
0x180004315  call    cs:__imp_CoTaskMemAlloc
0x18000431b  xor     ebx, ebx
0x18000431d  mov     [rsp+98h+arg_0], rax
0x180004325  test    rax, rax
0x180004328  jz      loc_180004447
0x18000432e  mov     [rsp+98h+arg_8], rsi
0x180004336  lea     rcx, ??_7CComRegDBWriter@@6B@; const CComRegDBWriter::`vftable'
0x18000433d  lea     rsi, [rax+8]
0x180004341  mov     [rax], rcx
0x180004344  mov     [rax+8], rbx
0x180004348  mov     [rax+10h], ebx
0x18000434b  mov     [rsp+98h+arg_10], rdi
0x180004353  mov     cs:?sm_pWriter@CComRegDBWriter@@0PEAV1@EA, rax; CComRegDBWriter * CComRegDBWriter::sm_pWriter
0x18000435a  movaps  [rsp+98h+var_18], xmm6
0x180004362  cmp     [rsi], rbx
0x180004365  jz      short loc_180004371
0x180004367  mov     edi, 80004005h
0x18000436c  jmp     loc_180004424
0x180004371  movups  xmm6, cs:xmmword_180060BE8
0x180004378  mov     rdx, rsi
0x18000437b  mov     rcx, rax
0x18000437e  call    cs:__imp_CreateWriter
0x180004384  mov     edi, eax
0x180004386  test    eax, eax
0x180004388  js      loc_180004424
0x18000438e  mov     rcx, [rsi]
0x180004391  lea     r8, aComRegdbWriter; "COM+ REGDB Writer"
0x180004398  mov     [rsp+98h+var_40], bl
0x18000439c  lea     rdx, [rsp+98h+var_28]
0x1800043a1  mov     [rsp+98h+var_48], 1
0x1800043a9  xor     r9d, r9d
0x1800043ac  mov     [rsp+98h+var_50], 0EA60h
0x1800043b4  mov     rax, [rcx]
0x1800043b7  mov     [rsp+98h+var_58], 1
0x1800043bf  mov     [rsp+98h+var_60], 3
0x1800043c7  mov     [rsp+98h+var_68], 1
0x1800043cf  mov     rax, [rax+18h]
0x1800043d3  mov     [rsp+98h+var_70], ebx
0x1800043d7  movdqa  [rsp+98h+var_28], xmm6
0x1800043dd  mov     [rsp+98h+var_78], ebx
0x1800043e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e6  mov     edi, eax
0x1800043e8  test    eax, eax
0x1800043ea  jns     short loc_1800043FE
0x1800043ec  mov     rcx, [rsi]
0x1800043ef  mov     rax, [rcx]
0x1800043f2  mov     rax, [rax+10h]
0x1800043f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fb  mov     [rsi], rbx
0x1800043fe  test    edi, edi
0x180004400  js      short loc_180004424
0x180004402  mov     rcx, [rsi]
0x180004405  test    rcx, rcx
0x180004408  jz      loc_180004367
0x18000440e  mov     rax, [rcx]
0x180004411  xor     edx, edx
0x180004413  mov     r8d, 6
0x180004419  mov     rax, [rax+20h]
0x18000441d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004422  mov     edi, eax
0x180004424  movaps  xmm6, [rsp+98h+var_18]
0x18000442c  mov     eax, edi
0x18000442e  mov     rdi, [rsp+98h+arg_10]
0x180004436  mov     rsi, [rsp+98h+arg_8]
0x18000443e  add     rsp, 90h
0x180004445  pop     rbx
0x180004446  retn
0x180004447  mov     cs:?sm_pWriter@CComRegDBWriter@@0PEAV1@EA, rbx; CComRegDBWriter * CComRegDBWriter::sm_pWriter
0x18000444e  mov     eax, 8007000Eh
0x180004453  add     rsp, 90h
0x18000445a  pop     rbx
0x18000445b  retn
```
