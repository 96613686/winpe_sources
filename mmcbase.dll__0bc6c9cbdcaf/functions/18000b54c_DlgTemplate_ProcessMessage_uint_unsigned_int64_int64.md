# DlgTemplate::ProcessMessage(uint,unsigned __int64,__int64)

- ea: `0x18000b54c`
- end: `0x18000b68b`
- name: `?ProcessMessage@DlgTemplate@@AEAA_JI_K_J@Z`
- size: `319`
- prototype: `__int64 __fastcall(DlgTemplate *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b400`

## callees

- `0x18000b290`
- `0x18000b54c`
- `0x18001d010`

## import_xrefs

- `USER32!EnumChildWindows` at `0x18000b5b3`
- `USER32!EnumChildWindows` at `0x18000b5b3`
- `USER32!EndDialog` at `0x18000b66b`
- `USER32!EndDialog` at `0x18000b66b`

## pseudocode

```c
__int64 __fastcall DlgTemplate::ProcessMessage(DlgTemplate *this, HWND a2, unsigned __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  unsigned int v8; // edi
  unsigned __int16 v9; // r14
  unsigned __int64 v10; // rsi
  __int64 v11; // r13
  void (__fastcall *v12)(DlgTemplate *, _QWORD, _QWORD, __int64, int *); // rax
  __int64 (__fastcall *v13)(DlgTemplate *, _QWORD, unsigned __int64, __int64); // rax
  int v15; // [rsp+88h] [rbp+10h] BYREF

  v4 = *((_QWORD *)this + 2);
  v8 = (unsigned int)a2;
  if ( (_DWORD)a2 == 273 )
  {
    v9 = a3;
    v10 = a3 >> 16;
    v11 = a4;
  }
  else
  {
    LOWORD(v10) = 0;
    v9 = 0;
    v11 = 0;
    if ( (_DWORD)a2 == 272 )
    {
      DlgTemplate::CenterWindow(this, a2);
    }
    else if ( (_DWORD)a2 == 21 )
    {
      EnumChildWindows(*((HWND *)this + 1), SendSysColorChangeEnumProc, 0);
    }
  }
  while ( v4 && *(_BYTE *)v4 )
  {
    if ( v8 == *(_DWORD *)(v4 + 4) )
    {
      if ( v8 == 273 )
      {
        v12 = *(void (__fastcall **)(DlgTemplate *, _QWORD, _QWORD, __int64, int *))(v4 + 24);
        if ( v12 )
        {
          if ( v9 == *(_WORD *)(v4 + 10) && (_WORD)v10 == *(_WORD *)(v4 + 8) )
          {
            v15 = 0;
            v12(this, (unsigned __int16)v10, v9, v11, &v15);
            if ( v15 == 1 )
              return 1;
          }
        }
      }
      else
      {
        v13 = *(__int64 (__fastcall **)(DlgTemplate *, _QWORD, unsigned __int64, __int64))(v4 + 16);
        if ( v13 )
          return v13(this, v8, a3, a4);
      }
    }
    v4 += 32;
  }
  if ( (_WORD)v10 || (unsigned __int16)(v9 - 1) > 1u )
    return 0;
  EndDialog(*((HWND *)this + 1), v9);
  return 1;
}

```

## disassembly

```asm
0x18000b54c  push    rbx
0x18000b54e  push    rbp
0x18000b54f  push    rsi
0x18000b550  push    rdi
0x18000b551  push    r12
0x18000b553  push    r13
0x18000b555  push    r14
0x18000b557  push    r15
0x18000b559  sub     rsp, 38h
0x18000b55d  mov     rbx, [rcx+10h]
0x18000b561  mov     rbp, rcx
0x18000b564  xor     ecx, ecx
0x18000b566  mov     r12, r9
0x18000b569  mov     r15, r8
0x18000b56c  mov     edi, edx
0x18000b56e  cmp     edx, 111h
0x18000b574  jnz     short loc_18000B586
0x18000b576  mov     rsi, r8
0x18000b579  movzx   r14d, r15w
0x18000b57d  shr     rsi, 10h
0x18000b581  mov     r13, r9
0x18000b584  jmp     short loc_18000B5BB
0x18000b586  mov     esi, ecx
0x18000b588  mov     r14d, ecx
0x18000b58b  mov     r13, rcx
0x18000b58e  cmp     edi, 110h
0x18000b594  jnz     short loc_18000B5A0
0x18000b596  mov     rcx, rbp; this
0x18000b599  call    ?CenterWindow@DlgTemplate@@AEAAHPEAUHWND__@@@Z; DlgTemplate::CenterWindow(HWND__ *)
0x18000b59e  jmp     short loc_18000B5B9
0x18000b5a0  cmp     edi, 15h
0x18000b5a3  jnz     short loc_18000B5BB
0x18000b5a5  mov     rcx, [rbp+8]; hWndParent
0x18000b5a9  lea     rdx, ?SendSysColorChangeEnumProc@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x18000b5b0  xor     r8d, r8d; lParam
0x18000b5b3  call    cs:__imp_EnumChildWindows
0x18000b5b9  xor     ecx, ecx
0x18000b5bb  mov     edx, 1
0x18000b5c0  test    rbx, rbx
0x18000b5c3  jz      loc_18000B652
0x18000b5c9  cmp     [rbx], cl
0x18000b5cb  jz      loc_18000B652
0x18000b5d1  cmp     edi, [rbx+4]
0x18000b5d4  jnz     short loc_18000B635
0x18000b5d6  cmp     edi, 111h
0x18000b5dc  jnz     short loc_18000B62C
0x18000b5de  mov     rax, [rbx+18h]
0x18000b5e2  test    rax, rax
0x18000b5e5  jz      short loc_18000B635
0x18000b5e7  cmp     r14w, [rbx+0Ah]
0x18000b5ec  jnz     short loc_18000B635
0x18000b5ee  cmp     si, [rbx+8]
0x18000b5f2  jnz     short loc_18000B635
0x18000b5f4  mov     [rsp+78h+arg_8], ecx
0x18000b5fb  mov     r9, r13
0x18000b5fe  lea     rcx, [rsp+78h+arg_8]
0x18000b606  movzx   r8d, r14w
0x18000b60a  mov     [rsp+78h+var_58], rcx
0x18000b60f  movzx   edx, si
0x18000b612  mov     rcx, rbp
0x18000b615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b61a  mov     edx, 1
0x18000b61f  cmp     [rsp+78h+arg_8], edx
0x18000b626  jz      short loc_18000B63B
0x18000b628  xor     ecx, ecx
0x18000b62a  jmp     short loc_18000B635
0x18000b62c  mov     rax, [rbx+10h]
0x18000b630  test    rax, rax
0x18000b633  jnz     short loc_18000B640
0x18000b635  add     rbx, 20h ; ' '
0x18000b639  jmp     short loc_18000B5C0
0x18000b63b  mov     rax, rdx
0x18000b63e  jmp     short loc_18000B67A
0x18000b640  mov     r9, r12
0x18000b643  mov     r8, r15
0x18000b646  mov     edx, edi
0x18000b648  mov     rcx, rbp
0x18000b64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b650  jmp     short loc_18000B67A
0x18000b652  test    si, si
0x18000b655  jnz     short loc_18000B678
0x18000b657  movzx   eax, r14w
0x18000b65b  sub     ax, dx
0x18000b65e  cmp     ax, dx
0x18000b661  ja      short loc_18000B678
0x18000b663  mov     rcx, [rbp+8]; hDlg
0x18000b667  movzx   edx, r14w; nResult
0x18000b66b  call    cs:__imp_EndDialog
0x18000b671  mov     eax, 1
0x18000b676  jmp     short loc_18000B67A
0x18000b678  xor     eax, eax
0x18000b67a  add     rsp, 38h
0x18000b67e  pop     r15
0x18000b680  pop     r14
0x18000b682  pop     r13
0x18000b684  pop     r12
0x18000b686  pop     rdi
0x18000b687  pop     rsi
0x18000b688  pop     rbp
0x18000b689  pop     rbx
0x18000b68a  retn
```
