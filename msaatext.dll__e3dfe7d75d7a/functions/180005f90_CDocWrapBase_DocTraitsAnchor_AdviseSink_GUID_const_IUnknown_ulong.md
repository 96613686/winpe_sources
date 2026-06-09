# CDocWrapBase<DocTraitsAnchor>::AdviseSink(_GUID const &,IUnknown *,ulong)

- ea: `0x180005f90`
- end: `0x1800061d8`
- name: `?AdviseSink@?$CDocWrapBase@VDocTraitsAnchor@@@@UEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `584`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800026d0`
- `0x180005f90`
- `0x1800074c8`
- `0x180014010`

## string_xrefs

- `0x18000616e`: `UpdateMask() on empty sink`

## pseudocode

```c
__int64 __fastcall CDocWrapBase<DocTraitsAnchor>::AdviseSink(
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
  if ( (*a2 != *(_QWORD *)&GUID_aa80e905_2021_11d2_93e0_0060b067b86e.Data1
     || a2[1] != *(_QWORD *)GUID_aa80e905_2021_11d2_93e0_0060b067b86e.Data4)
    && (*a2 != *(_QWORD *)&GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e.Data1
     || a2[1] != *(_QWORD *)GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e.Data4)
    && (*a2 != *(_QWORD *)&GUID_25642426_028d_4474_977b_111bb114fe3e.Data1
     || a2[1] != *(_QWORD *)GUID_25642426_028d_4474_977b_111bb114fe3e.Data4) )
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
        updated = CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription(*(_QWORD *)(a1 + 152));
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
          updated = ((__int64 (*)(void))CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription)();
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
0x180005f90  push    rbx
0x180005f92  push    rbp
0x180005f93  push    rsi
0x180005f94  push    rdi
0x180005f95  push    r14
0x180005f97  push    r15
0x180005f99  sub     rsp, 48h
0x180005f9d  cmp     qword ptr [rcx+98h], 0
0x180005fa5  mov     r15d, r9d
0x180005fa8  mov     r14, r8
0x180005fab  mov     rsi, rdx
0x180005fae  mov     rbx, rcx
0x180005fb1  jnz     short loc_180005FDF
0x180005fb3  xor     r9d, r9d
0x180005fb6  lea     rax, aMPmgr; "m_pMgr"
0x180005fbd  mov     [rsp+78h+var_48], rax; __int64
0x180005fc2  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180005fc9  mov     edx, 435h; Value
0x180005fce  mov     [rsp+78h+var_50], 0; int
0x180005fd6  lea     r8d, [r9+8]
0x180005fda  call    InternalTrace
0x180005fdf  test    r14, r14
0x180005fe2  jz      loc_1800061C6
0x180005fe8  mov     rax, [rsi]
0x180005feb  cmp     rax, qword ptr cs:_GUID_aa80e905_2021_11d2_93e0_0060b067b86e.Data1
0x180005ff2  jnz     short loc_180006001
0x180005ff4  mov     rax, [rsi+8]
0x180005ff8  cmp     rax, qword ptr cs:_GUID_aa80e905_2021_11d2_93e0_0060b067b86e.Data4
0x180005fff  jz      short loc_18000603B
0x180006001  mov     rax, [rsi]
0x180006004  cmp     rax, qword ptr cs:_GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e.Data1
0x18000600b  jnz     short loc_18000601A
0x18000600d  mov     rax, [rsi+8]
0x180006011  cmp     rax, qword ptr cs:_GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e.Data4
0x180006018  jz      short loc_18000603B
0x18000601a  mov     rax, [rsi]
0x18000601d  cmp     rax, qword ptr cs:_GUID_25642426_028d_4474_977b_111bb114fe3e.Data1
0x180006024  jnz     loc_1800061BF
0x18000602a  mov     rax, [rsi+8]
0x18000602e  cmp     rax, qword ptr cs:_GUID_25642426_028d_4474_977b_111bb114fe3e.Data4
0x180006035  jnz     loc_1800061BF
0x18000603b  test    r15d, 0FFFFFFE0h
0x180006042  jnz     loc_1800061C6
0x180006048  mov     rax, [r14]
0x18000604b  lea     r8, [rsp+78h+arg_0]
0x180006053  lea     rdx, IID_IUnknown
0x18000605a  mov     [rsp+78h+arg_0], 0
0x180006066  mov     rcx, r14
0x180006069  mov     rax, [rax]
0x18000606c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006071  mov     ebp, eax
0x180006073  test    eax, eax
0x180006075  jnz     loc_1800061B8
0x18000607b  mov     rdi, [rsp+78h+arg_0]
0x180006083  test    rdi, rdi
0x180006086  jz      loc_1800061B8
0x18000608c  cmp     qword ptr [rbx+70h], 0
0x180006091  jnz     loc_180006130
0x180006097  mov     [rbx+70h], r14
0x18000609b  mov     rcx, r14
0x18000609e  mov     rax, [r14]
0x1800060a1  mov     rax, [rax+8]
0x1800060a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060aa  movups  xmm0, xmmword ptr [rsi]
0x1800060ad  mov     [rbx+88h], r15d
0x1800060b4  mov     rcx, rdi
0x1800060b7  mov     [rbx+90h], rdi
0x1800060be  movdqu  xmmword ptr [rbx+78h], xmm0
0x1800060c3  mov     rax, [rdi]
0x1800060c6  mov     rax, [rax+8]
0x1800060ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060cf  mov     rcx, [rbx+98h]
0x1800060d6  call    ?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsAnchor@@@@QEAAJXZ; CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription(void)
0x1800060db  mov     ebp, eax
0x1800060dd  test    eax, eax
0x1800060df  jz      loc_18000619D
0x1800060e5  mov     rcx, [rbx+70h]
0x1800060e9  test    rcx, rcx
0x1800060ec  jz      loc_18000619D
0x1800060f2  mov     rax, [rcx]
0x1800060f5  mov     rax, [rax+10h]
0x1800060f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060fe  mov     rcx, [rbx+90h]
0x180006105  mov     qword ptr [rbx+70h], 0
0x18000610d  mov     rax, [rcx]
0x180006110  mov     rax, [rax+10h]
0x180006114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006119  mov     qword ptr [rbx+90h], 0
0x180006124  mov     dword ptr [rbx+88h], 0
0x18000612e  jmp     short loc_18000619D
0x180006130  cmp     rdi, [rbx+90h]
0x180006137  jz      short loc_180006140
0x180006139  mov     ebp, 80040201h
0x18000613e  jmp     short loc_1800061A5
0x180006140  mov     esi, [rbx+88h]
0x180006146  mov     [rbx+88h], r15d
0x18000614d  mov     rcx, [rbx+98h]
0x180006154  test    rcx, rcx
0x180006157  jz      short loc_1800061A5
0x180006159  call    ?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsAnchor@@@@QEAAJXZ; CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription(void)
0x18000615e  mov     ebp, eax
0x180006160  test    eax, eax
0x180006162  jz      short loc_18000619D
0x180006164  cmp     qword ptr [rbx+70h], 0
0x180006169  jnz     short loc_180006197
0x18000616b  xor     r9d, r9d
0x18000616e  lea     rax, aUpdatemaskOnEm; "UpdateMask() on empty sink"
0x180006175  mov     [rsp+78h+var_48], rax; __int64
0x18000617a  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180006181  mov     edx, 31Fh; Value
0x180006186  mov     [rsp+78h+var_50], 0; int
0x18000618e  lea     r8d, [r9+8]
0x180006192  call    InternalTrace
0x180006197  mov     [rbx+88h], esi
0x18000619d  mov     rdi, [rsp+78h+arg_0]
0x1800061a5  mov     rax, [rdi]
0x1800061a8  mov     rcx, rdi
0x1800061ab  mov     rax, [rax+10h]
0x1800061af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b4  mov     eax, ebp
0x1800061b6  jmp     short loc_1800061CB
0x1800061b8  mov     eax, 80004005h
0x1800061bd  jmp     short loc_1800061CB
0x1800061bf  mov     eax, 80004002h
0x1800061c4  jmp     short loc_1800061CB
0x1800061c6  mov     eax, 80070057h
0x1800061cb  add     rsp, 48h
0x1800061cf  pop     r15
0x1800061d1  pop     r14
0x1800061d3  pop     rdi
0x1800061d4  pop     rsi
0x1800061d5  pop     rbp
0x1800061d6  pop     rbx
0x1800061d7  retn
```
