# CRedbookWriterEvent::Update(IDispatch *,IDispatch *)

- ea: `0x180014d60`
- end: `0x180014f44`
- name: `?Update@CRedbookWriterEvent@@UEAAXPEAUIDispatch@@0@Z`
- size: `484`
- prototype: `void __fastcall(CRedbookWriterEvent *__hidden this, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180007bac`
- `0x180010a40`
- `0x180014d60`
- `0x180014f4c`
- `0x180019010`

## pseudocode

```c
void __fastcall CRedbookWriterEvent::Update(CMyUpdateList **this, struct IDispatch *a2, struct IDispatch *a3)
{
  struct IDispatchVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IDispatch *, const IID *const, void **); // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  _QWORD *v8; // rcx
  int v9; // eax
  int v10; // edx
  CMyUpdateList *v11; // rcx
  int v12; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+44h] [rbp-1Ch] BYREF
  int v14; // [rsp+48h] [rbp-18h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+20h] BYREF
  int v17; // [rsp+88h] [rbp+28h] BYREF

  lpVtbl = a3->lpVtbl;
  v17 = 0;
  v13 = 0;
  v12 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( ((int (__fastcall *)(struct IDispatch *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_27354140_7f64_5b0f_8f00_5d77afbe261e,
         &v15) >= 0
    && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 120LL))(v15, &v16) >= 0
    && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 56LL))(v15, &v17) >= 0
    && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 72LL))(v15, &v13) >= 0
    && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 80LL))(v15, &v12) >= 0
    && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 64LL))(v15, &v14) >= 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 7), v6, v7, v16, v17, v14, v13, v12);
      v8 = WPP_GLOBAL_Control;
    }
    switch ( v16 )
    {
      case 1u:
        if ( v8 != &WPP_GLOBAL_Control && ((unsigned __int8)v16 & *((_BYTE *)v8 + 68)) != 0 )
          WPP_SF_(v8[7], v16 + 10, &WPP_dac12a0582233e9479e987ada37a8a6e_Traceguids);
        CMyUpdateList::SetDataBurnAddProgress(this[14], 1u);
        break;
      case 3u:
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 68) & 1) != 0 )
          WPP_SF_(v8[7], v16 + 9, &WPP_dac12a0582233e9479e987ada37a8a6e_Traceguids);
        break;
      case 2u:
        v9 = v17;
        if ( *((_DWORD *)this + 30) >= v17 )
          v9 = *((_DWORD *)this + 30);
        else
          *((_DWORD *)this + 30) = v17;
        v10 = v12;
        v11 = this[14];
        *((_DWORD *)this + 31) = v12;
        CMyUpdateList::SetDataBurnAddProgress(v11, v10 - v9);
        *((_DWORD *)this + 30) = *((_DWORD *)this + 31);
        break;
    }
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
}

```

## disassembly

```asm
0x180014d60  mov     [rsp-8+arg_0], rbx
0x180014d65  mov     [rsp-8+arg_8], r14
0x180014d6a  push    rbp
0x180014d6b  mov     rbp, rsp
0x180014d6e  sub     rsp, 60h
0x180014d72  mov     rax, [r8]
0x180014d75  lea     rdx, _GUID_27354140_7f64_5b0f_8f00_5d77afbe261e
0x180014d7c  mov     r9, r8
0x180014d7f  mov     [rbp+arg_18], 0
0x180014d86  mov     rbx, rcx
0x180014d89  mov     [rbp+var_1C], 0
0x180014d90  lea     r8, [rbp+var_10]
0x180014d94  mov     [rbp+var_20], 0
0x180014d9b  mov     rax, [rax]
0x180014d9e  mov     rcx, r9
0x180014da1  mov     [rbp+var_18], 0
0x180014da8  mov     [rbp+var_10], 0
0x180014db0  mov     [rbp+arg_10], 0
0x180014db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dbc  test    eax, eax
0x180014dbe  js      loc_180014F1F
0x180014dc4  mov     rcx, [rbp+var_10]
0x180014dc8  lea     rdx, [rbp+arg_10]
0x180014dcc  mov     rax, [rcx]
0x180014dcf  mov     rax, [rax+78h]
0x180014dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dd8  test    eax, eax
0x180014dda  js      loc_180014F1F
0x180014de0  mov     rcx, [rbp+var_10]
0x180014de4  lea     rdx, [rbp+arg_18]
0x180014de8  mov     rax, [rcx]
0x180014deb  mov     rax, [rax+38h]
0x180014def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014df4  test    eax, eax
0x180014df6  js      loc_180014F1F
0x180014dfc  mov     rcx, [rbp+var_10]
0x180014e00  lea     rdx, [rbp+var_1C]
0x180014e04  mov     rax, [rcx]
0x180014e07  mov     rax, [rax+48h]
0x180014e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e10  test    eax, eax
0x180014e12  js      loc_180014F1F
0x180014e18  mov     rcx, [rbp+var_10]
0x180014e1c  lea     rdx, [rbp+var_20]
0x180014e20  mov     rax, [rcx]
0x180014e23  mov     rax, [rax+50h]
0x180014e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e2c  test    eax, eax
0x180014e2e  js      loc_180014F1F
0x180014e34  mov     rcx, [rbp+var_10]
0x180014e38  lea     rdx, [rbp+var_18]
0x180014e3c  mov     rax, [rcx]
0x180014e3f  mov     rax, [rax+40h]
0x180014e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e48  test    eax, eax
0x180014e4a  js      loc_180014F1F
0x180014e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e57  lea     r14, WPP_GLOBAL_Control
0x180014e5e  cmp     rcx, r14
0x180014e61  jz      short loc_180014E99
0x180014e63  test    byte ptr [rcx+44h], 1
0x180014e67  jz      short loc_180014E99
0x180014e69  mov     eax, [rbp+var_20]
0x180014e6c  mov     r9d, [rbp+arg_10]
0x180014e70  mov     rcx, [rcx+38h]
0x180014e74  mov     [rsp+60h+var_28], eax
0x180014e78  mov     eax, [rbp+var_1C]
0x180014e7b  mov     [rsp+60h+var_30], eax
0x180014e7f  mov     eax, [rbp+var_18]
0x180014e82  mov     [rsp+60h+var_38], eax
0x180014e86  mov     eax, [rbp+arg_18]
0x180014e89  mov     [rsp+60h+var_40], eax
0x180014e8d  call    WPP_SF_DDDDD
0x180014e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e99  mov     eax, [rbp+arg_10]
0x180014e9c  cmp     eax, 1
0x180014e9f  jnz     short loc_180014ECE
0x180014ea1  cmp     rcx, r14
0x180014ea4  jz      short loc_180014EBE
0x180014ea6  test    [rcx+44h], al
0x180014ea9  jz      short loc_180014EBE
0x180014eab  mov     rcx, [rcx+38h]
0x180014eaf  lea     edx, [rax+0Ah]
0x180014eb2  lea     r8, WPP_dac12a0582233e9479e987ada37a8a6e_Traceguids
0x180014eb9  call    WPP_SF_
0x180014ebe  mov     rcx, [rbx+70h]; this
0x180014ec2  mov     edx, 1; unsigned int
0x180014ec7  call    ?SetDataBurnAddProgress@CMyUpdateList@@QEAAEK@Z; CMyUpdateList::SetDataBurnAddProgress(ulong)
0x180014ecc  jmp     short loc_180014F1F
0x180014ece  cmp     eax, 3
0x180014ed1  jnz     short loc_180014EF3
0x180014ed3  cmp     rcx, r14
0x180014ed6  jz      short loc_180014F1F
0x180014ed8  test    byte ptr [rcx+44h], 1
0x180014edc  jz      short loc_180014F1F
0x180014ede  mov     rcx, [rcx+38h]
0x180014ee2  lea     edx, [rax+9]
0x180014ee5  lea     r8, WPP_dac12a0582233e9479e987ada37a8a6e_Traceguids
0x180014eec  call    WPP_SF_
0x180014ef1  jmp     short loc_180014F1F
0x180014ef3  cmp     eax, 2
0x180014ef6  jnz     short loc_180014F1F
0x180014ef8  mov     eax, [rbp+arg_18]
0x180014efb  cmp     [rbx+78h], eax
0x180014efe  jge     short loc_180014F05
0x180014f00  mov     [rbx+78h], eax
0x180014f03  jmp     short loc_180014F08
0x180014f05  mov     eax, [rbx+78h]
0x180014f08  mov     edx, [rbp+var_20]
0x180014f0b  mov     rcx, [rbx+70h]; this
0x180014f0f  mov     [rbx+7Ch], edx
0x180014f12  sub     edx, eax; unsigned int
0x180014f14  call    ?SetDataBurnAddProgress@CMyUpdateList@@QEAAEK@Z; CMyUpdateList::SetDataBurnAddProgress(ulong)
0x180014f19  mov     eax, [rbx+7Ch]
0x180014f1c  mov     [rbx+78h], eax
0x180014f1f  mov     rcx, [rbp+var_10]
0x180014f23  test    rcx, rcx
0x180014f26  jz      short loc_180014F34
0x180014f28  mov     rax, [rcx]
0x180014f2b  mov     rax, [rax+10h]
0x180014f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f34  mov     rbx, [rsp+60h+arg_0]
0x180014f39  mov     r14, [rsp+60h+arg_8]
0x180014f3e  add     rsp, 60h
0x180014f42  pop     rbp
0x180014f43  retn
```
