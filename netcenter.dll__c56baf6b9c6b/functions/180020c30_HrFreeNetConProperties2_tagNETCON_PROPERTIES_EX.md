# HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)

- ea: `0x180020c30`
- end: `0x180020c77`
- name: `?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct tagNETCON_PROPERTIES_EX *pv)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fde8`
- `0x180020e2c`

## callees

- `0x180020c30`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180020c42`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c56`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c60`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c42`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c56`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020c69`

## pseudocode

```c
__int64 __fastcall HrFreeNetConProperties2(BSTR *pv)
{
  if ( pv )
  {
    SysFreeString(pv[3]);
    SysFreeString(pv[4]);
    SysFreeString(pv[11]);
    SysFreeString(pv[12]);
    CoTaskMemFree(pv);
  }
  return 0;
}

```

## disassembly

```asm
0x180020c30  push    rbx
0x180020c32  sub     rsp, 20h
0x180020c36  mov     rbx, rcx
0x180020c39  test    rcx, rcx
0x180020c3c  jz      short loc_180020C6F
0x180020c3e  mov     rcx, [rcx+18h]; bstrString
0x180020c42  call    cs:__imp_SysFreeString
0x180020c48  mov     rcx, [rbx+20h]; bstrString
0x180020c4c  call    cs:__imp_SysFreeString
0x180020c52  mov     rcx, [rbx+58h]; bstrString
0x180020c56  call    cs:__imp_SysFreeString
0x180020c5c  mov     rcx, [rbx+60h]; bstrString
0x180020c60  call    cs:__imp_SysFreeString
0x180020c66  mov     rcx, rbx; pv
0x180020c69  call    cs:__imp_CoTaskMemFree
0x180020c6f  xor     eax, eax
0x180020c71  add     rsp, 20h
0x180020c75  pop     rbx
0x180020c76  retn
```
