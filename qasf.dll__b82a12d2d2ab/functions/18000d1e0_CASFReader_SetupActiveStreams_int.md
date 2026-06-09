# CASFReader::SetupActiveStreams(int)

- ea: `0x18000d1e0`
- end: `0x18000d3e6`
- name: `?SetupActiveStreams@CASFReader@@AEAAJH@Z`
- size: `518`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180008764`
- `0x18000d3ec`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001460`
- `0x18000d1e0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::SetupActiveStreams(CASFReader *this, int a2)
{
  int v4; // ebx
  unsigned int v6; // edi
  void (*v7)(void); // rax
  _WORD *v8; // rbx
  _DWORD *v9; // r14
  __int64 v10; // rdx
  __int64 i; // r8
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-20h] BYREF

  v15 = 0;
  v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 43))(
         *((_QWORD *)this + 43),
         &IID_IWMProfile,
         &v15);
  if ( v4 < 0 )
  {
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)v4;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 64LL))(v15, &v14);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( !v15 )
      return v6;
    v7 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
LABEL_28:
    v7();
    return v6;
  }
  if ( v14 )
  {
    v8 = operator new[](saturated_mul(v14, 2u));
    if ( v8 )
    {
      v9 = operator new[](saturated_mul(v14, 4u));
      if ( v9 )
      {
        v10 = *((_QWORD *)this + 35);
        for ( i = 0; (unsigned int)i < v14; v10 = *(_QWORD *)(v10 + 8) )
        {
          if ( !v10 )
            break;
          v12 = *(_QWORD *)(v10 + 16);
          v13 = a2 ? *(_DWORD *)(v12 + 308) : *(_QWORD *)(v12 + 48) != 0 ? 2 : 0;
          v9[i] = v13;
          v8[i] = *(_WORD *)(*((_QWORD *)this + 50) + 2 * i);
          i = (unsigned int)(i + 1);
        }
        if ( !*((_DWORD *)this + 112) )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 44) + 48LL))(*((_QWORD *)this + 44), 1);
          v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, _DWORD *))(**((_QWORD **)this + 44) + 64LL))(
                 *((_QWORD *)this + 44),
                 (unsigned __int16)v14,
                 v8,
                 v9);
        }
        operator delete(v9);
        operator delete(v8);
        if ( !v15 )
          return v6;
        v7 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
        goto LABEL_28;
      }
      operator delete(v8);
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    return 2147942414LL;
  }
  else
  {
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18000d1e0  push    rbp
0x18000d1e2  push    rbx
0x18000d1e3  push    rsi
0x18000d1e4  push    rdi
0x18000d1e5  push    r14
0x18000d1e7  push    r15
0x18000d1e9  mov     rbp, rsp
0x18000d1ec  sub     rsp, 58h
0x18000d1f0  mov     rax, cs:__security_cookie
0x18000d1f7  xor     rax, rsp
0x18000d1fa  mov     [rbp+var_18], rax
0x18000d1fe  mov     rsi, rcx
0x18000d201  mov     [rbp+var_20], 0
0x18000d209  mov     rcx, [rcx+158h]
0x18000d210  lea     r8, [rbp+var_20]
0x18000d214  mov     r15d, edx
0x18000d217  lea     rdx, IID_IWMProfile
0x18000d21e  mov     rax, [rcx]
0x18000d221  mov     rax, [rax]
0x18000d224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d229  mov     rcx, [rbp+var_20]
0x18000d22d  mov     ebx, eax
0x18000d22f  test    eax, eax
0x18000d231  jns     short loc_18000D24B
0x18000d233  test    rcx, rcx
0x18000d236  jz      short loc_18000D244
0x18000d238  mov     rdx, [rcx]
0x18000d23b  mov     rax, [rdx+10h]
0x18000d23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d244  mov     eax, ebx
0x18000d246  jmp     loc_18000D3CD
0x18000d24b  mov     [rbp+var_28], 0
0x18000d252  lea     rdx, [rbp+var_28]
0x18000d256  mov     rax, [rcx]
0x18000d259  mov     rax, [rax+40h]
0x18000d25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d262  mov     edi, eax
0x18000d264  test    eax, eax
0x18000d266  jns     short loc_18000D281
0x18000d268  mov     rcx, [rbp+var_20]
0x18000d26c  test    rcx, rcx
0x18000d26f  jz      loc_18000D3CB
0x18000d275  mov     rdx, [rcx]
0x18000d278  mov     rax, [rdx+10h]
0x18000d27c  jmp     loc_18000D3C6
0x18000d281  mov     eax, [rbp+var_28]
0x18000d284  test    eax, eax
0x18000d286  jnz     short loc_18000D2A7
0x18000d288  mov     rcx, [rbp+var_20]
0x18000d28c  test    rcx, rcx
0x18000d28f  jz      short loc_18000D29D
0x18000d291  mov     rax, [rcx]
0x18000d294  mov     rax, [rax+10h]
0x18000d298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d29d  mov     eax, 80004005h
0x18000d2a2  jmp     loc_18000D3CD
0x18000d2a7  mov     rcx, rax
0x18000d2aa  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000d2b1  mov     eax, 2
0x18000d2b6  mul     rcx
0x18000d2b9  cmovb   rax, r14
0x18000d2bd  mov     rcx, rax; unsigned __int64
0x18000d2c0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d2c5  mov     rbx, rax
0x18000d2c8  test    rax, rax
0x18000d2cb  jz      short loc_18000D2F3
0x18000d2cd  mov     ecx, [rbp+var_28]
0x18000d2d0  lea     eax, [r14+5]
0x18000d2d4  mul     rcx
0x18000d2d7  cmovb   rax, r14
0x18000d2db  mov     rcx, rax; unsigned __int64
0x18000d2de  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d2e3  mov     r14, rax
0x18000d2e6  test    rax, rax
0x18000d2e9  jnz     short loc_18000D312
0x18000d2eb  mov     rcx, rbx; void *
0x18000d2ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d2f3  mov     rcx, [rbp+var_20]
0x18000d2f7  test    rcx, rcx
0x18000d2fa  jz      short loc_18000D308
0x18000d2fc  mov     rax, [rcx]
0x18000d2ff  mov     rax, [rax+10h]
0x18000d303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d308  mov     eax, 8007000Eh
0x18000d30d  jmp     loc_18000D3CD
0x18000d312  mov     rdx, [rsi+118h]
0x18000d319  xor     r8d, r8d
0x18000d31c  cmp     [rbp+var_28], r8d
0x18000d320  jbe     short loc_18000D366
0x18000d322  test    rdx, rdx
0x18000d325  jz      short loc_18000D366
0x18000d327  mov     rax, [rdx+10h]
0x18000d32b  test    r15d, r15d
0x18000d32e  jz      short loc_18000D338
0x18000d330  mov     eax, [rax+134h]
0x18000d336  jmp     short loc_18000D344
0x18000d338  mov     rax, [rax+30h]
0x18000d33c  neg     rax
0x18000d33f  sbb     eax, eax
0x18000d341  and     eax, 2
0x18000d344  mov     [r14+r8*4], eax
0x18000d348  mov     rax, [rsi+190h]
0x18000d34f  movzx   ecx, word ptr [rax+r8*2]
0x18000d354  mov     [rbx+r8*2], cx
0x18000d359  inc     r8d
0x18000d35c  mov     rdx, [rdx+8]
0x18000d360  cmp     r8d, [rbp+var_28]
0x18000d364  jb      short loc_18000D322
0x18000d366  cmp     dword ptr [rsi+1C0h], 0
0x18000d36d  jnz     short loc_18000D3A6
0x18000d36f  mov     rcx, [rsi+160h]
0x18000d376  mov     edx, 1
0x18000d37b  mov     rax, [rcx]
0x18000d37e  mov     rax, [rax+30h]
0x18000d382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d387  mov     rcx, [rsi+160h]
0x18000d38e  mov     r9, r14
0x18000d391  movzx   edx, word ptr [rbp+var_28]
0x18000d395  mov     r8, rbx
0x18000d398  mov     rax, [rcx]
0x18000d39b  mov     rax, [rax+40h]
0x18000d39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a4  mov     edi, eax
0x18000d3a6  mov     rcx, r14; void *
0x18000d3a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d3ae  mov     rcx, rbx; void *
0x18000d3b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d3b6  mov     rcx, [rbp+var_20]
0x18000d3ba  test    rcx, rcx
0x18000d3bd  jz      short loc_18000D3CB
0x18000d3bf  mov     rax, [rcx]
0x18000d3c2  mov     rax, [rax+10h]
0x18000d3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3cb  mov     eax, edi
0x18000d3cd  mov     rcx, [rbp+var_18]
0x18000d3d1  xor     rcx, rsp; StackCookie
0x18000d3d4  call    __security_check_cookie
0x18000d3d9  add     rsp, 58h
0x18000d3dd  pop     r15
0x18000d3df  pop     r14
0x18000d3e1  pop     rdi
0x18000d3e2  pop     rsi
0x18000d3e3  pop     rbx
0x18000d3e4  pop     rbp
0x18000d3e5  retn
```
