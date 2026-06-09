# UpdatePropertiesWithNetcon2(IHNetConnection *,tagHNET_CONN_PROPERTIES *)

- ea: `0x18002ab30`
- end: `0x18002ac54`
- name: `?UpdatePropertiesWithNetcon2@@YAJPEAUIHNetConnection@@PEAUtagHNET_CONN_PROPERTIES@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct IHNetConnection *, struct tagHNET_CONN_PROPERTIES *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180015200`
- `0x1800203b0`
- `0x180020930`
- `0x180026300`

## callees

- `0x1800067e8`
- `0x18002ab30`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002abee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002abfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac0c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac1b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002abee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002abfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac0c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac24`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpdatePropertiesWithNetcon2(struct IHNetConnection *a1, struct tagHNET_CONN_PROPERTIES *a2)
{
  _QWORD *v3; // rbx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 && a1 )
  {
    v10 = 0;
    v9 = 0;
    if ( (*(int (__fastcall **)(struct IHNetConnection *, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a1 + 24LL))(
           a1,
           &v10) < 0
      || (**v10)(v10, &IID_INetConnection2, &v9) < 0
      || (pv = 0, (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v9 + 24LL))(v9, &pv) < 0) )
    {
LABEL_20:
      ATL::CComPtrBase<IHNetBridgedConnection>::~CComPtrBase<IHNetBridgedConnection>(&v9);
      ATL::CComPtrBase<IHNetBridgedConnection>::~CComPtrBase<IHNetBridgedConnection>((__int64 *)&v10);
      return 0;
    }
    v3 = pv;
    if ( *((_DWORD *)pv + 12) == 7 )
    {
      *((_WORD *)a2 + 4) = 0;
    }
    else if ( (*((_DWORD *)pv + 13) & 0x70000) == 0 )
    {
      goto LABEL_10;
    }
    *((_BYTE *)a2 + 6) = 0;
LABEL_10:
    if ( v3 )
    {
      v4 = (OLECHAR *)v3[3];
      if ( v4 )
        SysFreeString(v4);
      v5 = (OLECHAR *)v3[4];
      if ( v5 )
        SysFreeString(v5);
      v6 = (OLECHAR *)v3[11];
      if ( v6 )
        SysFreeString(v6);
      v7 = (OLECHAR *)v3[12];
      if ( v7 )
        SysFreeString(v7);
      CoTaskMemFree(v3);
    }
    goto LABEL_20;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002ab30  mov     r11, rsp
0x18002ab33  mov     [r11+8], rbx
0x18002ab37  push    rdi
0x18002ab38  sub     rsp, 20h
0x18002ab3c  mov     rdi, rdx
0x18002ab3f  test    rdx, rdx
0x18002ab42  jz      loc_18002AC44
0x18002ab48  test    rcx, rcx
0x18002ab4b  jz      loc_18002AC44
0x18002ab51  mov     qword ptr [r11+18h], 0
0x18002ab59  mov     qword ptr [r11+10h], 0
0x18002ab61  mov     rax, [rcx]
0x18002ab64  lea     rdx, [r11+18h]
0x18002ab68  mov     rax, [rax+18h]
0x18002ab6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab71  test    eax, eax
0x18002ab73  js      loc_18002AC2B
0x18002ab79  mov     rcx, [rsp+28h+arg_10]
0x18002ab7e  mov     rax, [rcx]
0x18002ab81  lea     r8, [rsp+28h+arg_8]
0x18002ab86  lea     rdx, IID_INetConnection2
0x18002ab8d  mov     rax, [rax]
0x18002ab90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab95  test    eax, eax
0x18002ab97  js      loc_18002AC2B
0x18002ab9d  mov     [rsp+28h+pv], 0
0x18002aba6  mov     rcx, [rsp+28h+arg_8]
0x18002abab  mov     rax, [rcx]
0x18002abae  lea     rdx, [rsp+28h+pv]
0x18002abb3  mov     rax, [rax+18h]
0x18002abb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abbc  test    eax, eax
0x18002abbe  js      short loc_18002AC2B
0x18002abc0  mov     rbx, [rsp+28h+pv]
0x18002abc5  cmp     dword ptr [rbx+30h], 7
0x18002abc9  jnz     short loc_18002ABD3
0x18002abcb  mov     word ptr [rdi+8], 0
0x18002abd1  jmp     short loc_18002ABDC
0x18002abd3  test    dword ptr [rbx+34h], 70000h
0x18002abda  jz      short loc_18002ABE0
0x18002abdc  mov     byte ptr [rdi+6], 0
0x18002abe0  test    rbx, rbx
0x18002abe3  jz      short loc_18002AC2B
0x18002abe5  mov     rcx, [rbx+18h]; bstrString
0x18002abe9  test    rcx, rcx
0x18002abec  jz      short loc_18002ABF4
0x18002abee  call    cs:__imp_SysFreeString
0x18002abf4  mov     rcx, [rbx+20h]; bstrString
0x18002abf8  test    rcx, rcx
0x18002abfb  jz      short loc_18002AC03
0x18002abfd  call    cs:__imp_SysFreeString
0x18002ac03  mov     rcx, [rbx+58h]; bstrString
0x18002ac07  test    rcx, rcx
0x18002ac0a  jz      short loc_18002AC12
0x18002ac0c  call    cs:__imp_SysFreeString
0x18002ac12  mov     rcx, [rbx+60h]; bstrString
0x18002ac16  test    rcx, rcx
0x18002ac19  jz      short loc_18002AC21
0x18002ac1b  call    cs:__imp_SysFreeString
0x18002ac21  mov     rcx, rbx; pv
0x18002ac24  call    cs:__imp_CoTaskMemFree
0x18002ac2a  nop
0x18002ac2b  lea     rcx, [rsp+28h+arg_8]
0x18002ac30  call    ??1?$CComPtrBase@UIHNetBridgedConnection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IHNetBridgedConnection>::~CComPtrBase<IHNetBridgedConnection>(void)
0x18002ac35  nop
0x18002ac36  lea     rcx, [rsp+28h+arg_10]
0x18002ac3b  call    ??1?$CComPtrBase@UIHNetBridgedConnection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IHNetBridgedConnection>::~CComPtrBase<IHNetBridgedConnection>(void)
0x18002ac40  xor     eax, eax
0x18002ac42  jmp     short loc_18002AC49
0x18002ac44  mov     eax, 80070057h
0x18002ac49  mov     rbx, [rsp+28h+arg_0]
0x18002ac4e  add     rsp, 20h
0x18002ac52  pop     rdi
0x18002ac53  retn
```
