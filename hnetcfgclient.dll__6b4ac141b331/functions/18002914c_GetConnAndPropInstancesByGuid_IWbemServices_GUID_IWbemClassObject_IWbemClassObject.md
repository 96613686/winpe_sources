# GetConnAndPropInstancesByGuid(IWbemServices *,_GUID *,IWbemClassObject * *,IWbemClassObject * *)

- ea: `0x18002914c`
- end: `0x1800291d6`
- name: `?GetConnAndPropInstancesByGuid@@YAJPEAUIWbemServices@@PEAU_GUID@@PEAPEAUIWbemClassObject@@2@Z`
- size: `138`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct _GUID *, struct IWbemClassObject **, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180014760`
- `0x180014bc0`

## callees

- `0x18002914c`
- `0x1800291dc`
- `0x1800298f4`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002916a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002916a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800291bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800291bc`

## pseudocode

```c
__int64 __fastcall GetConnAndPropInstancesByGuid(
        struct IWbemServices *a1,
        struct _GUID *a2,
        struct IWbemClassObject **a3,
        struct IWbemClassObject **a4)
{
  unsigned __int16 *v8; // rax
  OLECHAR *v9; // rsi
  int ConnectionInstanceByGuid; // ebx

  v8 = SysAllocString(L"WQL");
  v9 = v8;
  if ( v8 )
  {
    ConnectionInstanceByGuid = GetConnectionInstanceByGuid(a1, v8, a2, a3);
    if ( ConnectionInstanceByGuid >= 0 )
    {
      ConnectionInstanceByGuid = GetPropInstanceFromConnInstance(a1, *a3, a4);
      if ( ConnectionInstanceByGuid < 0 )
      {
        ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
        *a3 = 0;
      }
    }
    SysFreeString(v9);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)ConnectionInstanceByGuid;
}

```

## disassembly

```asm
0x18002914c  push    rbx
0x18002914e  push    rbp
0x18002914f  push    rsi
0x180029150  push    rdi
0x180029151  push    r14
0x180029153  sub     rsp, 20h
0x180029157  mov     rbp, rcx
0x18002915a  mov     r14, r9
0x18002915d  lea     rcx, ?c_wszWQL@@3QBGB; "WQL"
0x180029164  mov     rdi, r8
0x180029167  mov     rbx, rdx
0x18002916a  call    cs:__imp_SysAllocString
0x180029170  mov     rsi, rax
0x180029173  test    rax, rax
0x180029176  jz      short loc_1800291C4
0x180029178  mov     r9, rdi; struct IWbemClassObject **
0x18002917b  mov     r8, rbx; struct _GUID *
0x18002917e  mov     rdx, rax; unsigned __int16 *
0x180029181  mov     rcx, rbp; struct IWbemServices *
0x180029184  call    ?GetConnectionInstanceByGuid@@YAJPEAUIWbemServices@@PEAGPEAU_GUID@@PEAPEAUIWbemClassObject@@@Z; GetConnectionInstanceByGuid(IWbemServices *,ushort *,_GUID *,IWbemClassObject * *)
0x180029189  mov     ebx, eax
0x18002918b  test    eax, eax
0x18002918d  js      short loc_1800291B9
0x18002918f  mov     rdx, [rdi]; struct IWbemClassObject *
0x180029192  mov     r8, r14; struct IWbemClassObject **
0x180029195  mov     rcx, rbp; struct IWbemServices *
0x180029198  call    ?GetPropInstanceFromConnInstance@@YAJPEAUIWbemServices@@PEAUIWbemClassObject@@PEAPEAU2@@Z; GetPropInstanceFromConnInstance(IWbemServices *,IWbemClassObject *,IWbemClassObject * *)
0x18002919d  mov     ebx, eax
0x18002919f  test    eax, eax
0x1800291a1  jns     short loc_1800291B9
0x1800291a3  mov     rcx, [rdi]
0x1800291a6  mov     rdx, [rcx]
0x1800291a9  mov     rax, [rdx+10h]
0x1800291ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291b2  mov     qword ptr [rdi], 0
0x1800291b9  mov     rcx, rsi; bstrString
0x1800291bc  call    cs:__imp_SysFreeString
0x1800291c2  jmp     short loc_1800291C9
0x1800291c4  mov     ebx, 8007000Eh
0x1800291c9  mov     eax, ebx
0x1800291cb  add     rsp, 20h
0x1800291cf  pop     r14
0x1800291d1  pop     rdi
0x1800291d2  pop     rsi
0x1800291d3  pop     rbp
0x1800291d4  pop     rbx
0x1800291d5  retn
```
