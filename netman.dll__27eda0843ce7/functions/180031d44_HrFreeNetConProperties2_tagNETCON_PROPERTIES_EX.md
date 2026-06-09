# HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)

- ea: `0x180031d44`
- end: `0x180031db1`
- name: `?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct tagNETCON_PROPERTIES_EX *pv)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f920`
- `0x180023080`
- `0x180025020`
- `0x180030884`

## callees

- `0x180031d44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d97`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d61`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d70`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d61`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d70`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180031d8e`

## pseudocode

```c
__int64 __fastcall HrFreeNetConProperties2(struct tagNETCON_PROPERTIES_EX *pv)
{
  OLECHAR *v2; // rcx
  unsigned int v3; // edi
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx

  if ( pv )
  {
    v2 = (OLECHAR *)*((_QWORD *)pv + 3);
    v3 = 0;
    if ( v2 )
      SysFreeString(v2);
    v4 = (OLECHAR *)*((_QWORD *)pv + 4);
    if ( v4 )
      SysFreeString(v4);
    v5 = (OLECHAR *)*((_QWORD *)pv + 11);
    if ( v5 )
      SysFreeString(v5);
    v6 = (OLECHAR *)*((_QWORD *)pv + 12);
    if ( v6 )
      SysFreeString(v6);
    CoTaskMemFree(pv);
  }
  else
  {
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180031d44  mov     [rsp+arg_0], rbx
0x180031d49  push    rdi
0x180031d4a  sub     rsp, 20h
0x180031d4e  mov     rbx, rcx
0x180031d51  test    rcx, rcx
0x180031d54  jz      short loc_180031D9F
0x180031d56  mov     rcx, [rcx+18h]; bstrString
0x180031d5a  xor     edi, edi
0x180031d5c  test    rcx, rcx
0x180031d5f  jz      short loc_180031D67
0x180031d61  call    cs:__imp_SysFreeString
0x180031d67  mov     rcx, [rbx+20h]; bstrString
0x180031d6b  test    rcx, rcx
0x180031d6e  jz      short loc_180031D76
0x180031d70  call    cs:__imp_SysFreeString
0x180031d76  mov     rcx, [rbx+58h]; bstrString
0x180031d7a  test    rcx, rcx
0x180031d7d  jz      short loc_180031D85
0x180031d7f  call    cs:__imp_SysFreeString
0x180031d85  mov     rcx, [rbx+60h]; bstrString
0x180031d89  test    rcx, rcx
0x180031d8c  jz      short loc_180031D94
0x180031d8e  call    cs:__imp_SysFreeString
0x180031d94  mov     rcx, rbx; pv
0x180031d97  call    cs:__imp_CoTaskMemFree
0x180031d9d  jmp     short loc_180031DA4
0x180031d9f  mov     edi, 1
0x180031da4  mov     rbx, [rsp+28h+arg_0]
0x180031da9  mov     eax, edi
0x180031dab  add     rsp, 20h
0x180031daf  pop     rdi
0x180031db0  retn
```
