# HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)

- ea: `0x1800157f0`
- end: `0x18001585d`
- name: `?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct tagNETCON_PROPERTIES_EX *pv)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800154c8`
- `0x18002a9e0`
- `0x18002c0d4`
- `0x18002ebf8`
- `0x18004094c`
- `0x18004a730`
- `0x18005ac00`
- `0x180061524`

## callees

- `0x1800157f0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015843`
- `ole32!CoTaskMemFree` at `0x180015843`
- `OLEAUT32!__imp_SysFreeString` at `0x18001580d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001581c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001582b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001583a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001580d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001581c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001582b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001583a`

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
0x1800157f0  mov     [rsp+arg_0], rbx
0x1800157f5  push    rdi
0x1800157f6  sub     rsp, 20h
0x1800157fa  mov     rbx, rcx
0x1800157fd  test    rcx, rcx
0x180015800  jz      short loc_18001584B
0x180015802  mov     rcx, [rcx+18h]; bstrString
0x180015806  xor     edi, edi
0x180015808  test    rcx, rcx
0x18001580b  jz      short loc_180015813
0x18001580d  call    cs:__imp_SysFreeString
0x180015813  mov     rcx, [rbx+20h]; bstrString
0x180015817  test    rcx, rcx
0x18001581a  jz      short loc_180015822
0x18001581c  call    cs:__imp_SysFreeString
0x180015822  mov     rcx, [rbx+58h]; bstrString
0x180015826  test    rcx, rcx
0x180015829  jz      short loc_180015831
0x18001582b  call    cs:__imp_SysFreeString
0x180015831  mov     rcx, [rbx+60h]; bstrString
0x180015835  test    rcx, rcx
0x180015838  jz      short loc_180015840
0x18001583a  call    cs:__imp_SysFreeString
0x180015840  mov     rcx, rbx; pv
0x180015843  call    cs:__imp_CoTaskMemFree
0x180015849  jmp     short loc_180015850
0x18001584b  mov     edi, 1
0x180015850  mov     rbx, [rsp+28h+arg_0]
0x180015855  mov     eax, edi
0x180015857  add     rsp, 20h
0x18001585b  pop     rdi
0x18001585c  retn
```
