# CPackage::_IconRefresh(void)

- ea: `0x18000a624`
- end: `0x18000a6e6`
- name: `?_IconRefresh@CPackage@@IEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(HICON **this)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000642c`
- `0x180008ec0`
- `0x180009144`

## callees

- `0x18000a624`
- `0x18000afb4`
- `0x18000b7a0`
- `0x18000b94c`
- `0x18000cbf0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CPackage::_IconRefresh(HICON **this)
{
  CPackage *v2; // rcx
  HICON *v3; // rcx
  HICON *v4; // rcx
  unsigned __int16 v6[264]; // [rsp+30h] [rbp-228h] BYREF

  CPackage::_GetCurrentIcon((CPackage *)this, this[12]);
  CPackage::_CreateSaferIconTitle((CPackage *)this, (CPackage *)v6, (const WCHAR *)this[12], 0);
  CPackage::_IconCalcSize(v2, (struct tagRECT *)((char *)this[12] + 1052), v6);
  v3 = this[20];
  if ( v3 )
    (*((void (__fastcall **)(HICON *, unsigned __int64, _QWORD, _QWORD))*v3 + 6))(
      v3,
      (unsigned __int64)(this + 4) & -(__int64)(this != 0),
      0,
      0);
  v4 = this[25];
  if ( v4 )
    (*((void (__fastcall **)(HICON *, __int64))*v4 + 4))(v4, 4);
  *((_DWORD *)this + 38) = 1;
  return 0;
}

```

## disassembly

```asm
0x18000a624  push    rbx
0x18000a626  sub     rsp, 250h
0x18000a62d  mov     rax, cs:__security_cookie
0x18000a634  xor     rax, rsp
0x18000a637  mov     [rsp+258h+var_18], rax
0x18000a63f  mov     rdx, [rcx+60h]; struct _IC *
0x18000a643  mov     rbx, rcx
0x18000a646  call    ?_GetCurrentIcon@CPackage@@IEAAXPEAU_IC@@@Z; CPackage::_GetCurrentIcon(_IC *)
0x18000a64b  mov     r8, [rbx+60h]; struct _IC *
0x18000a64f  lea     rdx, [rsp+258h+var_228]; unsigned __int16 *
0x18000a654  xor     r9d, r9d; struct tagRECT *
0x18000a657  mov     rcx, rbx; this
0x18000a65a  call    ?_CreateSaferIconTitle@CPackage@@IEAAXPEAGPEAU_IC@@PEBUtagRECT@@@Z; CPackage::_CreateSaferIconTitle(ushort *,_IC *,tagRECT const *)
0x18000a65f  mov     rdx, [rbx+60h]
0x18000a663  lea     r8, [rsp+258h+var_228]; unsigned __int16 *
0x18000a668  add     rdx, 41Ch; struct tagRECT *
0x18000a66f  call    ?_IconCalcSize@CPackage@@IEAAHPEAUtagRECT@@PEBG@Z; CPackage::_IconCalcSize(tagRECT *,ushort const *)
0x18000a674  mov     rcx, [rbx+0A0h]
0x18000a67b  test    rcx, rcx
0x18000a67e  jz      short loc_18000A6A2
0x18000a680  mov     r9, [rcx]
0x18000a683  lea     r8, [rbx+20h]
0x18000a687  mov     rax, rbx
0x18000a68a  neg     rax
0x18000a68d  mov     rax, [r9+30h]
0x18000a691  sbb     rdx, rdx
0x18000a694  and     rdx, r8
0x18000a697  xor     r9d, r9d
0x18000a69a  xor     r8d, r8d
0x18000a69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6a2  mov     rcx, [rbx+0C8h]
0x18000a6a9  test    rcx, rcx
0x18000a6ac  jz      short loc_18000A6C1
0x18000a6ae  mov     rax, [rcx]
0x18000a6b1  xor     r8d, r8d
0x18000a6b4  mov     rax, [rax+20h]
0x18000a6b8  lea     edx, [r8+4]
0x18000a6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c1  mov     dword ptr [rbx+98h], 1
0x18000a6cb  xor     eax, eax
0x18000a6cd  mov     rcx, [rsp+258h+var_18]
0x18000a6d5  xor     rcx, rsp; StackCookie
0x18000a6d8  call    __security_check_cookie
0x18000a6dd  add     rsp, 250h
0x18000a6e4  pop     rbx
0x18000a6e5  retn
```
