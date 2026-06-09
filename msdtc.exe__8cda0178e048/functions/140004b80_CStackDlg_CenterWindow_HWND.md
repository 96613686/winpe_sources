# CStackDlg::CenterWindow(HWND__ *)

- ea: `0x140004b80`
- end: `0x140004cf4`
- name: `?CenterWindow@CStackDlg@@SAHPEAUHWND__@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005050`

## callees

- `0x140004b80`
- `0x140006f10`
- `0x140008010`

## pseudocode

```c
__int64 __fastcall CStackDlg::CenterWindow(HWND a1)
{
  __int64 v2; // rbx
  __int128 v4; // [rsp+40h] [rbp-40h] BYREF
  __int128 v5; // [rsp+50h] [rbp-30h] BYREF
  __int128 v6; // [rsp+60h] [rbp-20h] BYREF

  v2 = (*(__int64 (**)(void))(qword_1400107C8 + 32))();
  v6 = 0;
  (*(void (__fastcall **)(HWND, __int128 *))(qword_1400107C8 + 40))(a1, &v6);
  v4 = 0;
  v5 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(qword_1400107C8 + 48))(v2, &v4);
  (*(void (__fastcall **)(__int64, __int128 *))(qword_1400107C8 + 48))(v2, &v5);
  (*(void (__fastcall **)(__int64, __int64, __int128 *, __int64))(qword_1400107C8 + 56))(v2, v2, &v5, 2);
  return (*(__int64 (__fastcall **)(HWND, _QWORD))(qword_1400107C8 + 64))(a1, 0);
}

```

## disassembly

```asm
0x140004b80  mov     [rsp-8+arg_8], rbx
0x140004b85  mov     [rsp-8+arg_10], rdi
0x140004b8a  push    rbp
0x140004b8b  mov     rbp, rsp
0x140004b8e  sub     rsp, 80h
0x140004b95  mov     rax, cs:__security_cookie
0x140004b9c  xor     rax, rsp
0x140004b9f  mov     [rbp+var_10], rax
0x140004ba3  mov     rax, cs:qword_1400107C8
0x140004baa  mov     rdi, rcx
0x140004bad  mov     rax, [rax+20h]
0x140004bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bb6  mov     rcx, cs:qword_1400107C8
0x140004bbd  lea     rdx, [rbp+var_20]
0x140004bc1  xorps   xmm0, xmm0
0x140004bc4  mov     rbx, rax
0x140004bc7  movups  [rbp+var_20], xmm0
0x140004bcb  mov     rax, [rcx+28h]
0x140004bcf  mov     rcx, rdi
0x140004bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bd7  mov     rcx, cs:qword_1400107C8
0x140004bde  lea     rdx, [rbp+var_40]
0x140004be2  xorps   xmm0, xmm0
0x140004be5  xorps   xmm1, xmm1
0x140004be8  movups  [rbp+var_40], xmm0
0x140004bec  movups  [rbp+var_30], xmm1
0x140004bf0  mov     rax, [rcx+30h]
0x140004bf4  mov     rcx, rbx
0x140004bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bfc  mov     rax, cs:qword_1400107C8
0x140004c03  lea     rdx, [rbp+var_30]
0x140004c07  mov     rcx, rbx
0x140004c0a  mov     rax, [rax+30h]
0x140004c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c13  mov     rax, cs:qword_1400107C8
0x140004c1a  lea     r8, [rbp+var_30]
0x140004c1e  mov     r9d, 2
0x140004c24  mov     rdx, rbx
0x140004c27  mov     rcx, rbx
0x140004c2a  mov     rax, [rax+38h]
0x140004c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c33  mov     eax, dword ptr [rbp+var_30+8]
0x140004c36  add     eax, dword ptr [rbp+var_30]
0x140004c39  mov     r9d, dword ptr [rbp+var_20+8]
0x140004c3d  cdq
0x140004c3e  sub     r9d, dword ptr [rbp+var_20]
0x140004c42  sub     eax, edx
0x140004c44  mov     r11d, dword ptr [rbp+var_20+0Ch]
0x140004c48  sub     r11d, dword ptr [rbp+var_20+4]
0x140004c4c  mov     r8d, dword ptr [rbp+var_40]
0x140004c50  sar     eax, 1
0x140004c52  mov     r10d, eax
0x140004c55  mov     eax, r9d
0x140004c58  cdq
0x140004c59  sub     eax, edx
0x140004c5b  sar     eax, 1
0x140004c5d  sub     r10d, eax
0x140004c60  mov     eax, dword ptr [rbp+var_30+0Ch]
0x140004c63  add     eax, dword ptr [rbp+var_30+4]
0x140004c66  cdq
0x140004c67  sub     eax, edx
0x140004c69  sar     eax, 1
0x140004c6b  mov     ecx, eax
0x140004c6d  mov     eax, r11d
0x140004c70  cdq
0x140004c71  sub     eax, edx
0x140004c73  sar     eax, 1
0x140004c75  sub     ecx, eax
0x140004c77  cmp     r10d, r8d
0x140004c7a  jl      short loc_140004C8F
0x140004c7c  lea     eax, [r10+r9]
0x140004c80  mov     r8d, r10d
0x140004c83  cmp     eax, dword ptr [rbp+var_40+8]
0x140004c86  jle     short loc_140004C8F
0x140004c88  mov     r8d, dword ptr [rbp+var_40+8]
0x140004c8c  sub     r8d, r9d
0x140004c8f  mov     r9d, dword ptr [rbp+var_40+4]
0x140004c93  cmp     ecx, r9d
0x140004c96  jl      short loc_140004CAB
0x140004c98  lea     eax, [rcx+r11]
0x140004c9c  mov     r9d, ecx
0x140004c9f  cmp     eax, dword ptr [rbp+var_40+0Ch]
0x140004ca2  jle     short loc_140004CAB
0x140004ca4  mov     r9d, dword ptr [rbp+var_40+0Ch]
0x140004ca8  sub     r9d, r11d
0x140004cab  mov     rax, cs:qword_1400107C8
0x140004cb2  or      ecx, 0FFFFFFFFh
0x140004cb5  mov     [rsp+80h+var_50], 1
0x140004cbd  xor     edx, edx
0x140004cbf  mov     [rsp+80h+var_58], ecx
0x140004cc3  mov     [rsp+80h+var_60], ecx
0x140004cc7  mov     rcx, rdi
0x140004cca  mov     rax, [rax+40h]
0x140004cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004cd3  mov     rcx, [rbp+var_10]
0x140004cd7  xor     rcx, rsp; StackCookie
0x140004cda  call    __security_check_cookie
0x140004cdf  lea     r11, [rsp+80h+var_s0]
0x140004ce7  mov     rbx, [r11+18h]
0x140004ceb  mov     rdi, [r11+20h]
0x140004cef  mov     rsp, r11
0x140004cf2  pop     rbp
0x140004cf3  retn
```
