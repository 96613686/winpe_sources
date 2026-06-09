# ConnectObject_2

- ea: `0x140011f90`
- end: `0x14001204a`
- name: `ConnectObject_2`
- size: `186`
- prototype: `__int64 __fastcall(struct IDispatch *)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140011c00`
- `0x140011d54`
- `0x140011e50`

## callees

- `0x140009c70`
- `0x14000dcf8`
- `0x14000de10`
- `0x140011f90`
- `0x1400126d4`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ConnectObject_2(struct IDispatch *a1, __int64 a2, unsigned __int16 *a3)
{
  CConnectionSink *v6; // rax
  CConnectionSink *v7; // rbx
  int SourceFromClass; // eax
  struct ITypeInfo *v9; // rsi
  int v10; // edi
  struct ITypeInfo *v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  v6 = (CConnectionSink *)operator new(0x50u);
  if ( v6 && (v7 = CConnectionSink::CConnectionSink(v6)) != 0 )
  {
    SourceFromClass = GetSourceFromClass(a2, &v12);
    v9 = v12;
    v10 = SourceFromClass;
    if ( SourceFromClass >= 0 )
    {
      v10 = CConnectionSink::Connect(v7, a1, v12, a3);
      if ( v10 >= 0 )
      {
        v7 = 0;
        v10 = 0;
      }
    }
    if ( v9 )
      ((void (__fastcall *)(struct ITypeInfo *))v9->lpVtbl->Release)(v9);
    if ( v7 )
      (*(void (__fastcall **)(CConnectionSink *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140011f90  mov     [rsp+arg_0], rbx
0x140011f95  mov     [rsp+arg_8], rbp
0x140011f9a  push    rsi
0x140011f9b  push    rdi
0x140011f9c  push    r14
0x140011f9e  sub     rsp, 20h
0x140011fa2  mov     r14, rcx
0x140011fa5  mov     [rsp+38h+arg_18], 0
0x140011fae  mov     ecx, 50h ; 'P'; Size
0x140011fb3  mov     rbp, r8
0x140011fb6  mov     rdi, rdx
0x140011fb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011fbe  test    rax, rax
0x140011fc1  jz      short loc_140012030
0x140011fc3  mov     rcx, rax; this
0x140011fc6  call    ??0CConnectionSink@@QEAA@XZ; CConnectionSink::CConnectionSink(void)
0x140011fcb  mov     rbx, rax
0x140011fce  test    rax, rax
0x140011fd1  jz      short loc_140012030
0x140011fd3  lea     rdx, [rsp+38h+arg_18]
0x140011fd8  mov     rcx, rdi
0x140011fdb  call    GetSourceFromClass
0x140011fe0  mov     rsi, [rsp+38h+arg_18]
0x140011fe5  mov     edi, eax
0x140011fe7  test    eax, eax
0x140011fe9  js      short loc_140012006
0x140011feb  mov     r9, rbp; unsigned __int16 *
0x140011fee  mov     r8, rsi; struct ITypeInfo *
0x140011ff1  mov     rdx, r14; struct IDispatch *
0x140011ff4  mov     rcx, rbx; this
0x140011ff7  call    ?Connect@CConnectionSink@@QEAAJPEAUIDispatch@@PEAUITypeInfo@@PEAG@Z; CConnectionSink::Connect(IDispatch *,ITypeInfo *,ushort *)
0x140011ffc  mov     edi, eax
0x140011ffe  test    eax, eax
0x140012000  js      short loc_140012006
0x140012002  xor     ebx, ebx
0x140012004  xor     edi, edi
0x140012006  test    rsi, rsi
0x140012009  jz      short loc_14001201A
0x14001200b  mov     rax, [rsi]
0x14001200e  mov     rcx, rsi
0x140012011  mov     rax, [rax+10h]
0x140012015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001201a  test    rbx, rbx
0x14001201d  jz      short loc_140012035
0x14001201f  mov     rax, [rbx]
0x140012022  mov     rcx, rbx
0x140012025  mov     rax, [rax+10h]
0x140012029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001202e  jmp     short loc_140012035
0x140012030  mov     edi, 8007000Eh
0x140012035  mov     rbx, [rsp+38h+arg_0]
0x14001203a  mov     eax, edi
0x14001203c  mov     rbp, [rsp+38h+arg_8]
0x140012041  add     rsp, 20h
0x140012045  pop     r14
0x140012047  pop     rdi
0x140012048  pop     rsi
0x140012049  retn
```
