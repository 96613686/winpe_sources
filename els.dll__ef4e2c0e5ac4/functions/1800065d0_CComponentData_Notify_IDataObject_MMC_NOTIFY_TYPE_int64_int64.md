# CComponentData::Notify(IDataObject *,_MMC_NOTIFY_TYPE,__int64,__int64)

- ea: `0x1800065d0`
- end: `0x1800066d5`
- name: `?Notify@CComponentData@@UEAAJPEAUIDataObject@@W4_MMC_NOTIFY_TYPE@@_J2@Z`
- size: `261`
- prototype: `int(CComponentData *__hidden this, struct IDataObject *, enum _MMC_NOTIFY_TYPE, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800065d0`
- `0x1800078a4`
- `0x180007990`
- `0x180007ee4`
- `0x180008698`
- `0x180008be0`
- `0x180017630`
- `0x18001f638`

## pseudocode

```c
__int64 __fastcall CComponentData::Notify(
        CComponentData *this,
        struct IDataObject *a2,
        enum _MMC_NOTIFY_TYPE a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  unsigned int v5; // ebx
  int v6; // esi
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  CComponentData *v16; // rcx
  struct CDataObject *OwnDataObject; // rax

  v5 = 0;
  v6 = a4;
  v8 = a3 - 32777;
  if ( !v8 )
    return (unsigned int)CComponentData::_OnDelete((CComponentData *)((char *)this - 8), a2);
  v9 = v8 - 2;
  if ( !v9 )
  {
    if ( !a4 )
      return v5;
    return (unsigned int)CComponentData::_OnExpand((CComponentData *)((char *)this - 8), (__int64)a5, a2, 0);
  }
  v10 = v9 - 5;
  if ( !v10 )
    return v5;
  v11 = v10 - 2;
  if ( !v11 )
    return (unsigned int)CComponentData::_OnRefresh((CComponentData *)((char *)this - 8), a2);
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 10;
        if ( v15 )
        {
          if ( v15 != 2 )
            return (unsigned int)-2147418113;
        }
        else
        {
          v16 = (CComponentData *)((char *)this - 8);
          *((_QWORD *)v16 + 142) = a4;
          CComponentData::_UpdateRootDisplayName(v16);
        }
      }
    }
    else
    {
      OwnDataObject = ExtractOwnDataObject(a2);
      if ( OwnDataObject )
      {
        if ( v6 )
          CLogInfo::SetDisplayName(*((CLogInfo **)OwnDataObject + 2), a5);
        else
          LOBYTE(v5) = *((_DWORD *)OwnDataObject + 7) == 0;
      }
    }
  }
  else
  {
    CComponentData::_RemoveLogSetFromScopePane((CComponentData *)((char *)this - 8), a4);
    *((_QWORD *)this + 141) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800065d0  mov     [rsp+arg_0], rbx
0x1800065d5  mov     [rsp+arg_8], rsi
0x1800065da  push    rdi
0x1800065db  sub     rsp, 20h
0x1800065df  xor     ebx, ebx
0x1800065e1  mov     rsi, r9
0x1800065e4  mov     rdi, rcx
0x1800065e7  sub     r8d, 8009h
0x1800065ee  jz      loc_1800066B8
0x1800065f4  sub     r8d, 2
0x1800065f8  jz      loc_18000669D
0x1800065fe  sub     r8d, 5
0x180006602  jz      loc_1800066C3
0x180006608  sub     r8d, 2
0x18000660c  jz      loc_180006692
0x180006612  sub     r8d, 1
0x180006616  jz      short loc_18000667D
0x180006618  sub     r8d, 1
0x18000661c  jz      short loc_180006654
0x18000661e  sub     r8d, 1
0x180006622  jz      loc_1800066C3
0x180006628  sub     r8d, 0Ah
0x18000662c  jz      short loc_180006642
0x18000662e  cmp     r8d, 2
0x180006632  jz      loc_1800066C3
0x180006638  mov     ebx, 8000FFFFh
0x18000663d  jmp     loc_1800066C3
0x180006642  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180006646  mov     [rcx+470h], rsi
0x18000664d  call    ?_UpdateRootDisplayName@CComponentData@@AEAAXXZ; CComponentData::_UpdateRootDisplayName(void)
0x180006652  jmp     short loc_1800066C3
0x180006654  mov     rcx, rdx; struct IDataObject *
0x180006657  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x18000665c  test    rax, rax
0x18000665f  jz      short loc_1800066C3
0x180006661  test    esi, esi
0x180006663  jnz     short loc_18000666D
0x180006665  cmp     [rax+1Ch], ebx
0x180006668  setz    bl
0x18000666b  jmp     short loc_1800066C3
0x18000666d  mov     rdx, [rsp+28h+arg_20]; unsigned __int16 *
0x180006672  mov     rcx, [rax+10h]; this
0x180006676  call    ?SetDisplayName@CLogInfo@@QEAAXPEBG@Z; CLogInfo::SetDisplayName(ushort const *)
0x18000667b  jmp     short loc_1800066C3
0x18000667d  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180006681  mov     rdx, rsi; __int64
0x180006684  call    ?_RemoveLogSetFromScopePane@CComponentData@@AEAAX_J@Z; CComponentData::_RemoveLogSetFromScopePane(__int64)
0x180006689  mov     [rdi+468h], rbx
0x180006690  jmp     short loc_1800066C3
0x180006692  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180006696  call    ?_OnRefresh@CComponentData@@AEAAJPEAUIDataObject@@@Z; CComponentData::_OnRefresh(IDataObject *)
0x18000669b  jmp     short loc_1800066C1
0x18000669d  test    rsi, rsi
0x1800066a0  jz      short loc_1800066C3
0x1800066a2  mov     r8, rdx; struct IDataObject *
0x1800066a5  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800066a9  mov     rdx, [rsp+28h+arg_20]; __int64
0x1800066ae  xor     r9d, r9d; hWnd
0x1800066b1  call    ?_OnExpand@CComponentData@@AEAAJ_JPEAUIDataObject@@PEAUHWND__@@@Z; CComponentData::_OnExpand(__int64,IDataObject *,HWND__ *)
0x1800066b6  jmp     short loc_1800066C1
0x1800066b8  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800066bc  call    ?_OnDelete@CComponentData@@AEAAJPEAUIDataObject@@@Z; CComponentData::_OnDelete(IDataObject *)
0x1800066c1  mov     ebx, eax
0x1800066c3  mov     rsi, [rsp+28h+arg_8]
0x1800066c8  mov     eax, ebx
0x1800066ca  mov     rbx, [rsp+28h+arg_0]
0x1800066cf  add     rsp, 20h
0x1800066d3  pop     rdi
0x1800066d4  retn
```
