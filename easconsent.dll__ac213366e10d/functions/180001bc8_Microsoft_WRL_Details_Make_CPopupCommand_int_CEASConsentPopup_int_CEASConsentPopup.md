# Microsoft::WRL::Details::Make<CPopupCommand,int,CEASConsentPopup *>(int &&,CEASConsentPopup * &&)

- ea: `0x180001bc8`
- end: `0x180001c7e`
- name: `??$Make@VCPopupCommand@@HPEAVCEASConsentPopup@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPopupCommand@@@12@$$QEAH$$QEAPEAVCEASConsentPopup@@@Z`
- size: `182`
- prototype: `_QWORD *__fastcall(_QWORD *, int *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800026f8`

## callees

- `0x180001548`
- `0x180001bc8`
- `0x180004010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<CPopupCommand,int,CEASConsentPopup *>(
        _QWORD *a1,
        int *a2,
        __int64 *a3)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  __int64 v8; // r8
  int v9; // ebp
  struct Microsoft::WRL::Details::ModuleBase *v10; // rcx
  __int64 v11; // rsi

  *a1 = 0;
  v6 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v8 = *a3;
    v9 = *a2;
    v10 = Microsoft::WRL::Details::ModuleBase::module_;
    v6[3] = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vftable';
    v11 = (v8 + 8) & -(__int64)(v8 != 0);
    if ( v10 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v10 + 8LL))(v10);
    v7[4] = v9;
    *(_QWORD *)v7 = &CPopupCommand::`vftable';
    *((_QWORD *)v7 + 3) = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v7;
  }
  return a1;
}

```

## disassembly

```asm
0x180001bc8  push    rbx
0x180001bca  push    rbp
0x180001bcb  push    rsi
0x180001bcc  push    rdi
0x180001bcd  sub     rsp, 28h
0x180001bd1  mov     rbp, rdx
0x180001bd4  mov     qword ptr [rcx], 0
0x180001bdb  mov     rdi, rcx
0x180001bde  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001be5  mov     ecx, 20h ; ' '; unsigned __int64
0x180001bea  mov     rsi, r8
0x180001bed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001bf2  mov     rbx, rax
0x180001bf5  test    rax, rax
0x180001bf8  jz      short loc_180001C72
0x180001bfa  mov     r8, [rsi]
0x180001bfd  mov     ebp, [rbp+0]
0x180001c00  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001c07  mov     dword ptr [rax+0Ch], 1
0x180001c0e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommand@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vftable'
0x180001c15  lea     r9, [r8+8]
0x180001c19  mov     [rbx], rax
0x180001c1c  neg     r8
0x180001c1f  sbb     rsi, rsi
0x180001c22  and     rsi, r9
0x180001c25  test    rcx, rcx
0x180001c28  jz      short loc_180001C36
0x180001c2a  mov     rax, [rcx]
0x180001c2d  mov     rax, [rax+8]
0x180001c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c36  mov     [rbx+10h], ebp
0x180001c39  lea     rax, ??_7CPopupCommand@@6B@; const CPopupCommand::`vftable'
0x180001c40  mov     [rbx], rax
0x180001c43  mov     [rbx+18h], rsi
0x180001c47  test    rsi, rsi
0x180001c4a  jz      short loc_180001C5B
0x180001c4c  mov     rax, [rsi]
0x180001c4f  mov     rcx, rsi
0x180001c52  mov     rax, [rax+8]
0x180001c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c5b  mov     rcx, [rdi]
0x180001c5e  test    rcx, rcx
0x180001c61  jz      short loc_180001C6F
0x180001c63  mov     rax, [rcx]
0x180001c66  mov     rax, [rax+10h]
0x180001c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6f  mov     [rdi], rbx
0x180001c72  mov     rax, rdi
0x180001c75  add     rsp, 28h
0x180001c79  pop     rdi
0x180001c7a  pop     rsi
0x180001c7b  pop     rbp
0x180001c7c  pop     rbx
0x180001c7d  retn
```
