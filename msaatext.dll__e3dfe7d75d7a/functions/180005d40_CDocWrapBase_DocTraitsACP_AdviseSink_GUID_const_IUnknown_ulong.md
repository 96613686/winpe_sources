# CDocWrapBase<DocTraitsACP>::AdviseSink(_GUID const &,IUnknown *,ulong)

- ea: `0x180005d40`
- end: `0x180005f88`
- name: `?AdviseSink@?$CDocWrapBase@VDocTraitsACP@@@@UEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `584`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800026d0`
- `0x180005d40`
- `0x1800071ac`
- `0x180014010`

## string_xrefs

- `0x180005f1e`: `UpdateMask() on empty sink`

## pseudocode

```c
__int64 __fastcall CDocWrapBase<DocTraitsACP>::AdviseSink(
        __int64 a1,
        _QWORD *a2,
        __int64 (__fastcall ***a3)(__int64, GUID *, __int64 *),
        int a4)
{
  __int64 (__fastcall **v8)(__int64, GUID *, __int64 *); // rax
  unsigned int updated; // ebp
  __int64 v10; // rdi
  __int128 v11; // xmm0
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // esi
  int v16; // [rsp+20h] [rbp-58h]
  __int64 v17; // [rsp+80h] [rbp+8h] BYREF

  if ( !*(_QWORD *)(a1 + 152) )
    InternalTrace(L"windows\\oleacc\\msaatext\\docwrap.cpp", 0x435u, 8u, 0, v16, 0, (wchar_t *)L"m_pMgr");
  if ( !a3 )
    return 2147942487LL;
  if ( (*a2 != *(_QWORD *)&GUID_22d44c94_a419_4542_a272_ae26093ececf.Data1
     || a2[1] != *(_QWORD *)GUID_22d44c94_a419_4542_a272_ae26093ececf.Data4)
    && (*a2 != *(_QWORD *)&GUID_aa80e901_2021_11d2_93e0_0060b067b86e.Data1
     || a2[1] != *(_QWORD *)GUID_aa80e901_2021_11d2_93e0_0060b067b86e.Data4)
    && (*a2 != *(_QWORD *)&GUID_2bdf9464_41e2_43e3_950c_a6865ba25cd4.Data1
     || a2[1] != *(_QWORD *)GUID_2bdf9464_41e2_43e3_950c_a6865ba25cd4.Data4) )
  {
    return 2147500034LL;
  }
  if ( (a4 & 0xFFFFFFE0) != 0 )
    return 2147942487LL;
  v8 = *a3;
  v17 = 0;
  updated = (*v8)((__int64)a3, &IID_IUnknown, &v17);
  if ( !updated )
  {
    v10 = v17;
    if ( v17 )
    {
      if ( !*(_QWORD *)(a1 + 112) )
      {
        *(_QWORD *)(a1 + 112) = a3;
        ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*a3)[1])(a3);
        v11 = *(_OWORD *)a2;
        *(_DWORD *)(a1 + 136) = a4;
        *(_QWORD *)(a1 + 144) = v10;
        *(_OWORD *)(a1 + 120) = v11;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        updated = CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription(*(_QWORD *)(a1 + 152));
        if ( updated )
        {
          v12 = *(_QWORD *)(a1 + 112);
          if ( v12 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            v13 = *(_QWORD *)(a1 + 144);
            *(_QWORD *)(a1 + 112) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            *(_QWORD *)(a1 + 144) = 0;
            *(_DWORD *)(a1 + 136) = 0;
          }
        }
LABEL_24:
        v10 = v17;
        goto LABEL_25;
      }
      if ( v17 == *(_QWORD *)(a1 + 144) )
      {
        v14 = *(_DWORD *)(a1 + 136);
        *(_DWORD *)(a1 + 136) = a4;
        if ( *(_QWORD *)(a1 + 152) )
        {
          updated = ((__int64 (*)(void))CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription)();
          if ( updated )
          {
            if ( !*(_QWORD *)(a1 + 112) )
              InternalTrace(
                L"windows\\oleacc\\msaatext\\docwrap.cpp",
                0x31Fu,
                8u,
                0,
                v16,
                0,
                (wchar_t *)L"UpdateMask() on empty sink");
            *(_DWORD *)(a1 + 136) = v14;
          }
          goto LABEL_24;
        }
      }
      else
      {
        updated = -2147220991;
      }
LABEL_25:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return updated;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180005d40  push    rbx
0x180005d42  push    rbp
0x180005d43  push    rsi
0x180005d44  push    rdi
0x180005d45  push    r14
0x180005d47  push    r15
0x180005d49  sub     rsp, 48h
0x180005d4d  cmp     qword ptr [rcx+98h], 0
0x180005d55  mov     r15d, r9d
0x180005d58  mov     r14, r8
0x180005d5b  mov     rsi, rdx
0x180005d5e  mov     rbx, rcx
0x180005d61  jnz     short loc_180005D8F
0x180005d63  xor     r9d, r9d
0x180005d66  lea     rax, aMPmgr; "m_pMgr"
0x180005d6d  mov     [rsp+78h+var_48], rax; __int64
0x180005d72  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180005d79  mov     edx, 435h; Value
0x180005d7e  mov     [rsp+78h+var_50], 0; int
0x180005d86  lea     r8d, [r9+8]
0x180005d8a  call    InternalTrace
0x180005d8f  test    r14, r14
0x180005d92  jz      loc_180005F76
0x180005d98  mov     rax, [rsi]
0x180005d9b  cmp     rax, qword ptr cs:_GUID_22d44c94_a419_4542_a272_ae26093ececf.Data1
0x180005da2  jnz     short loc_180005DB1
0x180005da4  mov     rax, [rsi+8]
0x180005da8  cmp     rax, qword ptr cs:_GUID_22d44c94_a419_4542_a272_ae26093ececf.Data4
0x180005daf  jz      short loc_180005DEB
0x180005db1  mov     rax, [rsi]
0x180005db4  cmp     rax, qword ptr cs:_GUID_aa80e901_2021_11d2_93e0_0060b067b86e.Data1
0x180005dbb  jnz     short loc_180005DCA
0x180005dbd  mov     rax, [rsi+8]
0x180005dc1  cmp     rax, qword ptr cs:_GUID_aa80e901_2021_11d2_93e0_0060b067b86e.Data4
0x180005dc8  jz      short loc_180005DEB
0x180005dca  mov     rax, [rsi]
0x180005dcd  cmp     rax, qword ptr cs:_GUID_2bdf9464_41e2_43e3_950c_a6865ba25cd4.Data1
0x180005dd4  jnz     loc_180005F6F
0x180005dda  mov     rax, [rsi+8]
0x180005dde  cmp     rax, qword ptr cs:_GUID_2bdf9464_41e2_43e3_950c_a6865ba25cd4.Data4
0x180005de5  jnz     loc_180005F6F
0x180005deb  test    r15d, 0FFFFFFE0h
0x180005df2  jnz     loc_180005F76
0x180005df8  mov     rax, [r14]
0x180005dfb  lea     r8, [rsp+78h+arg_0]
0x180005e03  lea     rdx, IID_IUnknown
0x180005e0a  mov     [rsp+78h+arg_0], 0
0x180005e16  mov     rcx, r14
0x180005e19  mov     rax, [rax]
0x180005e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e21  mov     ebp, eax
0x180005e23  test    eax, eax
0x180005e25  jnz     loc_180005F68
0x180005e2b  mov     rdi, [rsp+78h+arg_0]
0x180005e33  test    rdi, rdi
0x180005e36  jz      loc_180005F68
0x180005e3c  cmp     qword ptr [rbx+70h], 0
0x180005e41  jnz     loc_180005EE0
0x180005e47  mov     [rbx+70h], r14
0x180005e4b  mov     rcx, r14
0x180005e4e  mov     rax, [r14]
0x180005e51  mov     rax, [rax+8]
0x180005e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5a  movups  xmm0, xmmword ptr [rsi]
0x180005e5d  mov     [rbx+88h], r15d
0x180005e64  mov     rcx, rdi
0x180005e67  mov     [rbx+90h], rdi
0x180005e6e  movdqu  xmmword ptr [rbx+78h], xmm0
0x180005e73  mov     rax, [rdi]
0x180005e76  mov     rax, [rax+8]
0x180005e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7f  mov     rcx, [rbx+98h]
0x180005e86  call    ?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsACP@@@@QEAAJXZ; CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription(void)
0x180005e8b  mov     ebp, eax
0x180005e8d  test    eax, eax
0x180005e8f  jz      loc_180005F4D
0x180005e95  mov     rcx, [rbx+70h]
0x180005e99  test    rcx, rcx
0x180005e9c  jz      loc_180005F4D
0x180005ea2  mov     rax, [rcx]
0x180005ea5  mov     rax, [rax+10h]
0x180005ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eae  mov     rcx, [rbx+90h]
0x180005eb5  mov     qword ptr [rbx+70h], 0
0x180005ebd  mov     rax, [rcx]
0x180005ec0  mov     rax, [rax+10h]
0x180005ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec9  mov     qword ptr [rbx+90h], 0
0x180005ed4  mov     dword ptr [rbx+88h], 0
0x180005ede  jmp     short loc_180005F4D
0x180005ee0  cmp     rdi, [rbx+90h]
0x180005ee7  jz      short loc_180005EF0
0x180005ee9  mov     ebp, 80040201h
0x180005eee  jmp     short loc_180005F55
0x180005ef0  mov     esi, [rbx+88h]
0x180005ef6  mov     [rbx+88h], r15d
0x180005efd  mov     rcx, [rbx+98h]
0x180005f04  test    rcx, rcx
0x180005f07  jz      short loc_180005F55
0x180005f09  call    ?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsACP@@@@QEAAJXZ; CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription(void)
0x180005f0e  mov     ebp, eax
0x180005f10  test    eax, eax
0x180005f12  jz      short loc_180005F4D
0x180005f14  cmp     qword ptr [rbx+70h], 0
0x180005f19  jnz     short loc_180005F47
0x180005f1b  xor     r9d, r9d
0x180005f1e  lea     rax, aUpdatemaskOnEm; "UpdateMask() on empty sink"
0x180005f25  mov     [rsp+78h+var_48], rax; __int64
0x180005f2a  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180005f31  mov     edx, 31Fh; Value
0x180005f36  mov     [rsp+78h+var_50], 0; int
0x180005f3e  lea     r8d, [r9+8]
0x180005f42  call    InternalTrace
0x180005f47  mov     [rbx+88h], esi
0x180005f4d  mov     rdi, [rsp+78h+arg_0]
0x180005f55  mov     rax, [rdi]
0x180005f58  mov     rcx, rdi
0x180005f5b  mov     rax, [rax+10h]
0x180005f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f64  mov     eax, ebp
0x180005f66  jmp     short loc_180005F7B
0x180005f68  mov     eax, 80004005h
0x180005f6d  jmp     short loc_180005F7B
0x180005f6f  mov     eax, 80004002h
0x180005f74  jmp     short loc_180005F7B
0x180005f76  mov     eax, 80070057h
0x180005f7b  add     rsp, 48h
0x180005f7f  pop     r15
0x180005f81  pop     r14
0x180005f83  pop     rdi
0x180005f84  pop     rsi
0x180005f85  pop     rbp
0x180005f86  pop     rbx
0x180005f87  retn
```
