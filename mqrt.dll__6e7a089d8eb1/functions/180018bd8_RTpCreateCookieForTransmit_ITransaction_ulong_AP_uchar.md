# RTpCreateCookieForTransmit(ITransaction *,ulong &,AP<uchar> &)

- ea: `0x180018bd8`
- end: `0x180018f46`
- name: `?RTpCreateCookieForTransmit@@YAJPEAUITransaction@@AEAKAEAV?$AP@E@@@Z`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018f4c`

## callees

- `0x180013c74`
- `0x180018bd8`
- `0x180021010`
- `0x180026010`

## import_xrefs

- `mqsec!XactGetDTC` at `0x180018c02`
- `mqsec!XactGetDTC` at `0x180018c02`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RTpCreateCookieForTransmit(__int64 a1, __int64 a2, _QWORD *a3)
{
  int DTC; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  void *v12; // r8
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  struct IUnknown *v16; // [rsp+38h] [rbp-18h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v18; // [rsp+88h] [rbp+38h] BYREF

  v16 = 0;
  DTC = XactGetDTC(&v16);
  v7 = DTC;
  if ( DTC >= 0 )
  {
    v17 = 0;
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v16->lpVtbl->QueryInterface)(
           v16,
           &GUID_59313e00_b36c_11cf_a539_00aa006887c3,
           &v17);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v15 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v15);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 24LL))(v15, a1);
        v7 = v10;
        if ( v10 >= 0 )
        {
          LODWORD(v18) = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v15 + 32LL))(v15, &v18);
          v7 = v11;
          if ( v11 >= 0 )
          {
            v12 = MmAllocate((unsigned int)v18);
            *a3 = v12;
            if ( v12 )
            {
              v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *, __int64))(*(_QWORD *)v15 + 40LL))(
                      v15,
                      (unsigned int)v18,
                      v12,
                      a2);
              v7 = v13;
              if ( v13 >= 0 )
              {
                if ( v15 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                if ( v17 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              }
              else
              {
                LogMsgHR(v13, (wchar_t *)L"rt/XactRT", 0x3B9u);
                if ( v15 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                if ( v17 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              }
              if ( v16 )
                ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
            }
            else
            {
              v7 = -1072824281;
              LogMsgHR(-1072824281, (wchar_t *)L"rt/XactRT", 0x3B8u);
              if ( v15 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              if ( v17 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              if ( v16 )
                ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
            }
          }
          else
          {
            LogMsgHR(v11, (wchar_t *)L"rt/XactRT", 0x3B7u);
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            if ( v16 )
              ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
          }
        }
        else
        {
          LogMsgHR(v10, (wchar_t *)L"rt/XactRT", 0x3B5u);
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          if ( v16 )
            ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
        }
      }
      else
      {
        LogMsgHR(v9, (wchar_t *)L"rt/XactRT", 0x3B4u);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        if ( v16 )
          ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
      }
    }
    else
    {
      LogMsgHR(v8, (wchar_t *)L"rt/XactRT", 0x3B3u);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v16 )
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
    }
  }
  else
  {
    LogMsgHR(DTC, (wchar_t *)L"rt/XactRT", 0x3B2u);
    if ( v16 )
      ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
  }
  return v7;
}

```

## disassembly

```asm
0x180018bd8  mov     [rsp-18h+arg_0], rbx
0x180018bdd  mov     [rsp-18h+arg_8], rsi
0x180018be2  push    rbp
0x180018be3  push    rdi
0x180018be4  push    r14
0x180018be6  mov     rbp, rsp
0x180018be9  sub     rsp, 50h
0x180018bed  mov     rdi, r8
0x180018bf0  mov     r14, rdx
0x180018bf3  mov     rsi, rcx
0x180018bf6  mov     [rbp+var_18], 0
0x180018bfe  lea     rcx, [rbp+var_18]
0x180018c02  call    cs:__imp_?XactGetDTC@@YAJPEAPEAUIUnknown@@@Z; XactGetDTC(IUnknown * *)
0x180018c08  mov     ebx, eax
0x180018c0a  test    eax, eax
0x180018c0c  jns     short loc_180018C3E
0x180018c0e  mov     r8d, 3B2h; unsigned __int16
0x180018c14  lea     rdx, aRtXactrt; "rt/XactRT"
0x180018c1b  mov     ecx, eax; int
0x180018c1d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018c22  nop
0x180018c23  mov     rcx, [rbp+var_18]
0x180018c27  test    rcx, rcx
0x180018c2a  jz      short loc_180018C39
0x180018c2c  mov     rax, [rcx]
0x180018c2f  mov     rax, [rax+10h]
0x180018c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c38  nop
0x180018c39  jmp     loc_180018F31
0x180018c3e  mov     [rbp+var_10], 0
0x180018c46  mov     rcx, [rbp+var_18]
0x180018c4a  mov     rax, [rcx]
0x180018c4d  lea     r8, [rbp+var_10]
0x180018c51  lea     rdx, _GUID_59313e00_b36c_11cf_a539_00aa006887c3
0x180018c58  mov     rax, [rax]
0x180018c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c60  mov     ebx, eax
0x180018c62  test    eax, eax
0x180018c64  jns     short loc_180018CAC
0x180018c66  mov     r8d, 3B3h; unsigned __int16
0x180018c6c  lea     rdx, aRtXactrt; "rt/XactRT"
0x180018c73  mov     ecx, eax; int
0x180018c75  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018c7a  nop
0x180018c7b  mov     rcx, [rbp+var_10]
0x180018c7f  test    rcx, rcx
0x180018c82  jz      short loc_180018C91
0x180018c84  mov     rax, [rcx]
0x180018c87  mov     rax, [rax+10h]
0x180018c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c90  nop
0x180018c91  mov     rcx, [rbp+var_18]
0x180018c95  test    rcx, rcx
0x180018c98  jz      short loc_180018CA7
0x180018c9a  mov     rax, [rcx]
0x180018c9d  mov     rax, [rax+10h]
0x180018ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ca6  nop
0x180018ca7  jmp     loc_180018F31
0x180018cac  mov     [rbp+var_20], 0
0x180018cb4  mov     rcx, [rbp+var_10]
0x180018cb8  mov     rax, [rcx]
0x180018cbb  lea     rdx, [rbp+var_20]
0x180018cbf  mov     rax, [rax+18h]
0x180018cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cc8  mov     ebx, eax
0x180018cca  test    eax, eax
0x180018ccc  jns     short loc_180018D2A
0x180018cce  mov     r8d, 3B4h; unsigned __int16
0x180018cd4  lea     rdx, aRtXactrt; "rt/XactRT"
0x180018cdb  mov     ecx, eax; int
0x180018cdd  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018ce2  nop
0x180018ce3  mov     rcx, [rbp+var_20]
0x180018ce7  test    rcx, rcx
0x180018cea  jz      short loc_180018CF9
0x180018cec  mov     rax, [rcx]
0x180018cef  mov     rax, [rax+10h]
0x180018cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cf8  nop
0x180018cf9  mov     rcx, [rbp+var_10]
0x180018cfd  test    rcx, rcx
0x180018d00  jz      short loc_180018D0F
0x180018d02  mov     rax, [rcx]
0x180018d05  mov     rax, [rax+10h]
0x180018d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d0e  nop
0x180018d0f  mov     rcx, [rbp+var_18]
0x180018d13  test    rcx, rcx
0x180018d16  jz      short loc_180018D25
0x180018d18  mov     rax, [rcx]
0x180018d1b  mov     rax, [rax+10h]
0x180018d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d24  nop
0x180018d25  jmp     loc_180018F31
0x180018d2a  mov     rcx, [rbp+var_20]
0x180018d2e  mov     rax, [rcx]
0x180018d31  mov     rdx, rsi
0x180018d34  mov     rax, [rax+18h]
0x180018d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d3d  mov     ebx, eax
0x180018d3f  test    eax, eax
0x180018d41  jns     short loc_180018D9F
0x180018d43  mov     r8d, 3B5h; unsigned __int16
0x180018d49  lea     rdx, aRtXactrt; "rt/XactRT"
0x180018d50  mov     ecx, eax; int
0x180018d52  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018d57  nop
0x180018d58  mov     rcx, [rbp+var_20]
0x180018d5c  test    rcx, rcx
0x180018d5f  jz      short loc_180018D6E
0x180018d61  mov     rax, [rcx]
0x180018d64  mov     rax, [rax+10h]
0x180018d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d6d  nop
0x180018d6e  mov     rcx, [rbp+var_10]
0x180018d72  test    rcx, rcx
0x180018d75  jz      short loc_180018D84
0x180018d77  mov     rax, [rcx]
0x180018d7a  mov     rax, [rax+10h]
0x180018d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d83  nop
0x180018d84  mov     rcx, [rbp+var_18]
0x180018d88  test    rcx, rcx
0x180018d8b  jz      short loc_180018D9A
0x180018d8d  mov     rax, [rcx]
0x180018d90  mov     rax, [rax+10h]
0x180018d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d99  nop
0x180018d9a  jmp     loc_180018F31
0x180018d9f  mov     dword ptr [rbp+arg_18], 0
0x180018da6  mov     rcx, [rbp+var_20]
0x180018daa  mov     rax, [rcx]
0x180018dad  lea     rdx, [rbp+arg_18]
0x180018db1  mov     rax, [rax+20h]
0x180018db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dba  mov     ebx, eax
0x180018dbc  test    eax, eax
0x180018dbe  jns     short loc_180018E1C
0x180018dc0  mov     r8d, 3B7h; unsigned __int16
0x180018dc6  lea     rdx, aRtXactrt; "rt/XactRT"
0x180018dcd  mov     ecx, eax; int
0x180018dcf  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018dd4  nop
0x180018dd5  mov     rcx, [rbp+var_20]
0x180018dd9  test    rcx, rcx
0x180018ddc  jz      short loc_180018DEB
0x180018dde  mov     rax, [rcx]
0x180018de1  mov     rax, [rax+10h]
0x180018de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dea  nop
0x180018deb  mov     rcx, [rbp+var_10]
0x180018def  test    rcx, rcx
0x180018df2  jz      short loc_180018E01
0x180018df4  mov     rax, [rcx]
0x180018df7  mov     rax, [rax+10h]
0x180018dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e00  nop
0x180018e01  mov     rcx, [rbp+var_18]
0x180018e05  test    rcx, rcx
0x180018e08  jz      short loc_180018E17
0x180018e0a  mov     rax, [rcx]
0x180018e0d  mov     rax, [rax+10h]
0x180018e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e16  nop
0x180018e17  jmp     loc_180018F31
0x180018e1c  mov     ecx, dword ptr [rbp+arg_18]; unsigned __int64
0x180018e1f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180018e24  mov     r8, rax
0x180018e27  mov     [rdi], rax
0x180018e2a  test    rax, rax
0x180018e2d  jnz     short loc_180018E90
0x180018e2f  mov     r8d, 3B8h; unsigned __int16
0x180018e35  lea     rdx, aRtXactrt; "rt/XactRT"
0x180018e3c  mov     ebx, 0C00E0027h
0x180018e41  mov     ecx, ebx; int
0x180018e43  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018e48  nop
0x180018e49  mov     rcx, [rbp+var_20]
0x180018e4d  test    rcx, rcx
0x180018e50  jz      short loc_180018E5F
0x180018e52  mov     rax, [rcx]
0x180018e55  mov     rax, [rax+10h]
0x180018e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e5e  nop
0x180018e5f  mov     rcx, [rbp+var_10]
0x180018e63  test    rcx, rcx
0x180018e66  jz      short loc_180018E75
0x180018e68  mov     rax, [rcx]
0x180018e6b  mov     rax, [rax+10h]
0x180018e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e74  nop
0x180018e75  mov     rcx, [rbp+var_18]
0x180018e79  test    rcx, rcx
0x180018e7c  jz      short loc_180018E8B
0x180018e7e  mov     rdx, [rcx]
0x180018e81  mov     rax, [rdx+10h]
0x180018e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e8a  nop
0x180018e8b  jmp     loc_180018F31
0x180018e90  mov     rcx, [rbp+var_20]
0x180018e94  mov     rax, [rcx]
0x180018e97  mov     r9, r14
0x180018e9a  mov     edx, dword ptr [rbp+arg_18]
0x180018e9d  mov     rax, [rax+28h]
0x180018ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ea6  mov     ebx, eax
0x180018ea8  test    eax, eax
0x180018eaa  jns     short loc_180018EEF
0x180018eac  mov     r8d, 3B9h; unsigned __int16
0x180018eb2  lea     rdx, aRtXactrt; "rt/XactRT"
0x180018eb9  mov     ecx, eax; int
0x180018ebb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018ec0  nop
0x180018ec1  mov     rcx, [rbp+var_20]
0x180018ec5  test    rcx, rcx
0x180018ec8  jz      short loc_180018ED7
0x180018eca  mov     rax, [rcx]
0x180018ecd  mov     rax, [rax+10h]
0x180018ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ed6  nop
0x180018ed7  mov     rcx, [rbp+var_10]
0x180018edb  test    rcx, rcx
0x180018ede  jz      short loc_180018EED
0x180018ee0  mov     rax, [rcx]
0x180018ee3  mov     rax, [rax+10h]
0x180018ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eec  nop
0x180018eed  jmp     short loc_180018F1B
0x180018eef  mov     rcx, [rbp+var_20]
0x180018ef3  test    rcx, rcx
0x180018ef6  jz      short loc_180018F05
0x180018ef8  mov     rax, [rcx]
0x180018efb  mov     rax, [rax+10h]
0x180018eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f04  nop
0x180018f05  mov     rcx, [rbp+var_10]
0x180018f09  test    rcx, rcx
0x180018f0c  jz      short loc_180018F1B
0x180018f0e  mov     rax, [rcx]
0x180018f11  mov     rax, [rax+10h]
0x180018f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f1a  nop
0x180018f1b  mov     rcx, [rbp+var_18]
0x180018f1f  test    rcx, rcx
0x180018f22  jz      short loc_180018F31
0x180018f24  mov     rax, [rcx]
0x180018f27  mov     rax, [rax+10h]
0x180018f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f30  nop
0x180018f31  mov     eax, ebx
0x180018f33  mov     rbx, [rsp+50h+arg_0]
0x180018f38  mov     rsi, [rsp+50h+arg_8]
0x180018f3d  add     rsp, 50h
0x180018f41  pop     r14
0x180018f43  pop     rdi
0x180018f44  pop     rbp
0x180018f45  retn
```
