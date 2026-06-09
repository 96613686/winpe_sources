# MarshalIUnknownIntoBlob(tagBLOB &,IUnknown *,ulong,ulong)

- ea: `0x180013cb8`
- end: `0x180013e2b`
- name: `?MarshalIUnknownIntoBlob@@YAJAEAUtagBLOB@@PEAUIUnknown@@KK@Z`
- size: `371`
- prototype: `int(struct tagBLOB *, struct IUnknown *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800130a0`
- `0x1800140c0`

## callees

- `0x180013cb8`
- `0x1800434c6`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180013cf8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180013cf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d91`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180013e23`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180044356`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180013e23`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180044356`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180013d2c`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180013d2c`

## pseudocode

```c
HRESULT __fastcall MarshalIUnknownIntoBlob(struct tagBLOB *a1, struct IUnknown *a2)
{
  HRESULT result; // eax
  HRESULT v5; // ebx
  BYTE *v6; // rdx
  __int64 v7; // r8
  void (*v8)(void); // rax
  LPSTREAM ppstm; // [rsp+30h] [rbp-78h] BYREF
  HRESULT v10; // [rsp+38h] [rbp-70h]
  int v11; // [rsp+3Ch] [rbp-6Ch] BYREF
  _BYTE v12[16]; // [rsp+40h] [rbp-68h] BYREF
  ULONG cb; // [rsp+50h] [rbp-58h]
  int cb_4; // [rsp+54h] [rbp-54h]

  *a1 = 0;
  ppstm = 0;
  result = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( result >= 0 )
  {
    v5 = CoMarshalInterface(ppstm, &IID_IUnknown, a2, 1u, 0, 0);
    v10 = v5;
    if ( v5 < 0 )
    {
      v8 = *(void (**)(void))(*(_QWORD *)ppstm + 16LL);
LABEL_12:
      v8();
      return v5;
    }
    (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
    memset_0(v12, 0, 0x50u);
    (*(void (__fastcall **)(LPSTREAM, _BYTE *, __int64))(*(_QWORD *)ppstm + 96LL))(ppstm, v12, 1);
    if ( cb_4 )
    {
      v5 = -2147024774;
    }
    else
    {
      v6 = (BYTE *)CoTaskMemAlloc(cb);
      a1->pBlobData = v6;
      if ( v6 )
      {
        v7 = cb;
        a1->cbSize = cb;
        v11 = 0;
        (*(void (__fastcall **)(LPSTREAM, BYTE *, __int64, int *))(*(_QWORD *)ppstm + 24LL))(ppstm, v6, v7, &v11);
LABEL_9:
        if ( v5 < 0 )
          CoReleaseMarshalData(ppstm);
        v8 = *(void (**)(void))(*(_QWORD *)ppstm + 16LL);
        goto LABEL_12;
      }
      v5 = -2147024882;
    }
    v10 = v5;
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x180013cb8  mov     [rsp+arg_10], rbx
0x180013cbd  push    rdi
0x180013cbe  sub     rsp, 0A0h
0x180013cc5  mov     rax, cs:__security_cookie
0x180013ccc  xor     rax, rsp
0x180013ccf  mov     [rsp+0A8h+var_18], rax
0x180013cd7  mov     rbx, rdx
0x180013cda  mov     rdi, rcx
0x180013cdd  xorps   xmm0, xmm0
0x180013ce0  movups  xmmword ptr [rcx], xmm0
0x180013ce3  mov     [rsp+0A8h+ppstm], 0
0x180013cec  lea     r8, [rsp+0A8h+ppstm]; ppstm
0x180013cf1  mov     edx, 1; fDeleteOnRelease
0x180013cf6  xor     ecx, ecx; hGlobal
0x180013cf8  call    cs:__imp_CreateStreamOnHGlobal
0x180013cfe  test    eax, eax
0x180013d00  js      loc_180013DF4
0x180013d06  mov     [rsp+0A8h+mshlflags], 0; mshlflags
0x180013d0e  mov     [rsp+0A8h+pvDestContext], 0; pvDestContext
0x180013d17  mov     r9d, 1; dwDestContext
0x180013d1d  mov     r8, rbx; pUnk
0x180013d20  lea     rdx, IID_IUnknown; riid
0x180013d27  mov     rcx, [rsp+0A8h+ppstm]; pStm
0x180013d2c  call    cs:__imp_CoMarshalInterface
0x180013d32  mov     ebx, eax
0x180013d34  mov     [rsp+0A8h+var_70], eax
0x180013d38  mov     rcx, [rsp+0A8h+ppstm]
0x180013d3d  test    eax, eax
0x180013d3f  js      loc_180013E15
0x180013d45  xor     edx, edx
0x180013d47  mov     rax, [rcx]
0x180013d4a  xor     r9d, r9d
0x180013d4d  xor     r8d, r8d
0x180013d50  mov     rax, [rax+28h]
0x180013d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d59  nop
0x180013d5a  xor     edx, edx; Val
0x180013d5c  lea     r8d, [rdx+50h]; Size
0x180013d60  lea     rcx, [rsp+0A8h+var_68]; void *
0x180013d65  call    memset_0
0x180013d6a  mov     rcx, [rsp+0A8h+ppstm]
0x180013d6f  mov     rax, [rcx]
0x180013d72  mov     r8d, 1
0x180013d78  lea     rdx, [rsp+0A8h+var_68]
0x180013d7d  mov     rax, [rax+60h]
0x180013d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d86  cmp     dword ptr [rsp+0A8h+cb+4], 0
0x180013d8b  jnz     short loc_180013DCB
0x180013d8d  mov     ecx, dword ptr [rsp+0A8h+cb]; cb
0x180013d91  call    cs:__imp_CoTaskMemAlloc
0x180013d97  mov     rdx, rax
0x180013d9a  mov     [rdi+8], rax
0x180013d9e  test    rax, rax
0x180013da1  jz      short loc_180013DD6
0x180013da3  mov     r8d, dword ptr [rsp+0A8h+cb]
0x180013da8  mov     [rdi], r8d
0x180013dab  mov     [rsp+0A8h+var_6C], 0
0x180013db3  mov     rcx, [rsp+0A8h+ppstm]
0x180013db8  mov     rax, [rcx]
0x180013dbb  lea     r9, [rsp+0A8h+var_6C]
0x180013dc0  mov     rax, [rax+18h]
0x180013dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc9  jmp     short loc_180013DDD
0x180013dcb  mov     ebx, 8007007Ah
0x180013dd0  mov     [rsp+0A8h+var_70], ebx
0x180013dd4  jmp     short loc_180013DDD
0x180013dd6  mov     ebx, 8007000Eh
0x180013ddb  jmp     short loc_180013DD0
0x180013ddd  test    ebx, ebx
0x180013ddf  js      short loc_180013E1E
0x180013de1  mov     rcx, [rsp+0A8h+ppstm]
0x180013de6  mov     rax, [rcx]
0x180013de9  mov     rax, [rax+10h]
0x180013ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013df2  mov     eax, ebx
0x180013df4  mov     rcx, [rsp+0A8h+var_18]
0x180013dfc  xor     rcx, rsp; StackCookie
0x180013dff  call    __security_check_cookie
0x180013e04  mov     rbx, [rsp+0A8h+arg_10]
0x180013e0c  add     rsp, 0A0h
0x180013e13  pop     rdi
0x180013e14  retn
0x180013e15  mov     rdx, [rcx]
0x180013e18  mov     rax, [rdx+10h]
0x180013e1c  jmp     short loc_180013DED
0x180013e1e  mov     rcx, [rsp+0A8h+ppstm]; pStm
0x180013e23  call    cs:__imp_CoReleaseMarshalData
0x180013e29  jmp     short loc_180013DE1
0x180044343  push    rbp
0x180044345  sub     rsp, 30h
0x180044349  mov     rbp, rdx
0x18004434c  cmp     dword ptr [rbp+38h], 0
0x180044350  jge     short loc_18004435D
0x180044352  mov     rcx, [rbp+30h]; pStm
0x180044356  call    cs:__imp_CoReleaseMarshalData
0x18004435c  nop
0x18004435d  mov     rcx, [rbp+30h]
0x180044361  mov     rax, [rcx]
0x180044364  mov     rax, [rax+10h]
0x180044368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004436d  nop
0x18004436e  add     rsp, 30h
0x180044372  pop     rbp
0x180044373  retn
```
