# ATL::CAccessorBase::FreeType(ushort,uchar *,IRowset *)

- ea: `0x180008ef0`
- end: `0x180008ff6`
- name: `?FreeType@CAccessorBase@ATL@@SAXGPEAEPEAUIRowset@@@Z`
- size: `262`
- prototype: `void __fastcall(__int16, VARIANTARG *, struct IRowset *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008db4`

## callees

- `0x180008ef0`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008fcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008fcc`
- `OLEAUT32!__imp_VariantClear` at `0x180008fab`
- `OLEAUT32!__imp_VariantClear` at `0x180008fab`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180008f1f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180008f1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fe4`

## pseudocode

```c
void __fastcall ATL::CAccessorBase::FreeType(__int16 a1, VARIANTARG *a2, struct IRowset *a3)
{
  struct IRowset *v3; // r9
  __int64 v6; // rcx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v3 = a3;
    if ( (a1 & 0x2000) != 0 )
    {
      if ( !*(_QWORD *)&a2->vt )
        goto LABEL_22;
      SafeArrayDestroy(*(SAFEARRAY **)&a2->vt);
    }
    else if ( a1 == 8 )
    {
      SysFreeString(*(BSTR *)&a2->vt);
    }
    else
    {
      if ( a1 != 9 )
      {
        if ( a1 == 12 )
        {
          VariantClear(a2);
          goto LABEL_22;
        }
        if ( a1 != 13 )
        {
          if ( a1 == 136 )
          {
            v6 = 0;
            v7 = 0;
            if ( a3 )
            {
              ((void (__fastcall *)(struct IRowset *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
                a3,
                &GUID_0c733a93_2a1c_11ce_ade5_00aa0044773d,
                &v7);
              v6 = v7;
            }
            if ( v6 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, struct IRowset *))(*(_QWORD *)v6 + 32LL))(
                v6,
                *(_QWORD *)&a2->vt,
                0,
                v3);
              v6 = v7;
            }
            if ( v6 )
              (*(void (__fastcall **)(__int64, VARIANTARG *, struct IRowset *, struct IRowset *))(*(_QWORD *)v6 + 16LL))(
                v6,
                a2,
                a3,
                v3);
          }
          goto LABEL_22;
        }
      }
      if ( !*(_QWORD *)&a2->vt )
      {
LABEL_22:
        if ( (a1 & 0x1000) != 0 )
          CoTaskMemFree(a2->bstrVal);
        return;
      }
      (*(void (__fastcall **)(_QWORD, VARIANTARG *, struct IRowset *, struct IRowset *))(**(_QWORD **)&a2->vt + 16LL))(
        *(_QWORD *)&a2->vt,
        a2,
        a3,
        a3);
    }
    *(_QWORD *)&a2->vt = 0;
    goto LABEL_22;
  }
}

```

## disassembly

```asm
0x180008ef0  test    rdx, rdx
0x180008ef3  jz      locret_180008FF5
0x180008ef9  mov     [rsp+arg_0], rbx
0x180008efe  push    rdi
0x180008eff  sub     rsp, 20h
0x180008f03  mov     r9, r8
0x180008f06  mov     rbx, rdx
0x180008f09  movzx   edi, cx
0x180008f0c  bt      di, 0Dh
0x180008f11  jnb     short loc_180008F2A
0x180008f13  mov     rcx, [rdx]; psa
0x180008f16  test    rcx, rcx
0x180008f19  jz      loc_180008FD9
0x180008f1f  call    cs:__imp_SafeArrayDestroy
0x180008f25  jmp     loc_180008FD2
0x180008f2a  mov     ecx, edi
0x180008f2c  sub     ecx, 8
0x180008f2f  jz      loc_180008FC9
0x180008f35  sub     ecx, 1
0x180008f38  jz      short loc_180008FB3
0x180008f3a  sub     ecx, 3
0x180008f3d  jz      short loc_180008FA8
0x180008f3f  sub     ecx, 1
0x180008f42  jz      short loc_180008FB3
0x180008f44  cmp     ecx, 7Bh ; '{'
0x180008f47  jnz     loc_180008FD9
0x180008f4d  xor     ecx, ecx
0x180008f4f  mov     [rsp+28h+arg_8], rcx
0x180008f54  test    r9, r9
0x180008f57  jz      short loc_180008F78
0x180008f59  mov     rax, [r8]
0x180008f5c  lea     r8, [rsp+28h+arg_8]
0x180008f61  lea     rdx, _GUID_0c733a93_2a1c_11ce_ade5_00aa0044773d
0x180008f68  mov     rcx, r9
0x180008f6b  mov     rax, [rax]
0x180008f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f73  mov     rcx, [rsp+28h+arg_8]
0x180008f78  test    rcx, rcx
0x180008f7b  jz      short loc_180008F94
0x180008f7d  mov     rax, [rcx]
0x180008f80  xor     r8d, r8d
0x180008f83  mov     rdx, [rbx]
0x180008f86  mov     rax, [rax+20h]
0x180008f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f8f  mov     rcx, [rsp+28h+arg_8]
0x180008f94  test    rcx, rcx
0x180008f97  jz      short loc_180008FA6
0x180008f99  mov     rax, [rcx]
0x180008f9c  mov     rax, [rax+10h]
0x180008fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fa5  nop
0x180008fa6  jmp     short loc_180008FD9
0x180008fa8  mov     rcx, rbx; pvarg
0x180008fab  call    cs:__imp_VariantClear
0x180008fb1  jmp     short loc_180008FD9
0x180008fb3  mov     rcx, [rdx]
0x180008fb6  test    rcx, rcx
0x180008fb9  jz      short loc_180008FD9
0x180008fbb  mov     rax, [rcx]
0x180008fbe  mov     rax, [rax+10h]
0x180008fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc7  jmp     short loc_180008FD2
0x180008fc9  mov     rcx, [rdx]; bstrString
0x180008fcc  call    cs:__imp_SysFreeString
0x180008fd2  mov     qword ptr [rbx], 0
0x180008fd9  bt      di, 0Ch
0x180008fde  jnb     short loc_180008FEB
0x180008fe0  mov     rcx, [rbx+8]; pv
0x180008fe4  call    cs:__imp_CoTaskMemFree
0x180008fea  nop
0x180008feb  mov     rbx, [rsp+28h+arg_0]
0x180008ff0  add     rsp, 20h
0x180008ff4  pop     rdi
0x180008ff5  retn
```
