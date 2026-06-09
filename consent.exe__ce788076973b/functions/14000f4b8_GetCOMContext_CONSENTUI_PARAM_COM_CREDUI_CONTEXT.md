# GetCOMContext(_CONSENTUI_PARAM_COM *,_CREDUI_CONTEXT *)

- ea: `0x14000f4b8`
- end: `0x14000f581`
- name: `?GetCOMContext@@YAXPEAU_CONSENTUI_PARAM_COM@@PEAU_CREDUI_CONTEXT@@@Z`
- size: `201`
- prototype: `void __fastcall(struct _CONSENTUI_PARAM_COM *, struct _CREDUI_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003040`

## callees

- `0x14000f4b8`
- `0x140010ad3`
- `0x140019338`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f521`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000f501`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000f501`
- `SHLWAPI!SHStrDupW` at `0x14000f514`
- `SHLWAPI!SHStrDupW` at `0x14000f538`
- `SHLWAPI!SHStrDupW` at `0x14000f514`
- `SHLWAPI!SHStrDupW` at `0x14000f538`

## pseudocode

```c
void __fastcall GetCOMContext(struct _CONSENTUI_PARAM_COM *a1, struct _CREDUI_CONTEXT *a2)
{
  OLECHAR sz[40]; // [rsp+20h] [rbp-68h] BYREF

  memset_0(sz, 0, 0x4Eu);
  if ( StringFromGUID2((const GUID *const)((char *)a1 + 232), sz, 39) >= 0 )
    SHStrDupW(sz, (LPWSTR *)a2 + 4);
  CoTaskMemFree(*((LPVOID *)a2 + 2));
  *((_QWORD *)a2 + 2) = 0;
  SHStrDupW(*((LPCWSTR *)a1 + 25), (LPWSTR *)a2 + 2);
  if ( (unsigned int)(*(_DWORD *)a2 - 2) <= 1 )
    *((_QWORD *)a2 + 1) = LoadIconFromResourceString(*((unsigned __int16 **)a1 + 27));
  *((_DWORD *)a2 + 15) = 2;
}

```

## disassembly

```asm
0x14000f4b8  mov     [rsp+arg_10], rbx
0x14000f4bd  mov     [rsp+arg_18], rsi
0x14000f4c2  push    rdi
0x14000f4c3  sub     rsp, 80h
0x14000f4ca  mov     rax, cs:__security_cookie
0x14000f4d1  xor     rax, rsp
0x14000f4d4  mov     [rsp+88h+var_18], rax
0x14000f4d9  mov     rdi, rdx
0x14000f4dc  mov     rsi, rcx
0x14000f4df  xor     edx, edx; Val
0x14000f4e1  lea     rcx, [rsp+88h+sz]; void *
0x14000f4e6  lea     r8d, [rdx+4Eh]; Size
0x14000f4ea  call    memset_0
0x14000f4ef  lea     rcx, [rsi+0E8h]; rguid
0x14000f4f6  mov     r8d, 27h ; '''; cchMax
0x14000f4fc  lea     rdx, [rsp+88h+sz]; lpsz
0x14000f501  call    cs:__imp_StringFromGUID2
0x14000f507  test    eax, eax
0x14000f509  js      short loc_14000F51A
0x14000f50b  lea     rdx, [rdi+20h]; ppwsz
0x14000f50f  lea     rcx, [rsp+88h+sz]; psz
0x14000f514  call    cs:__imp_SHStrDupW
0x14000f51a  lea     rbx, [rdi+10h]
0x14000f51e  mov     rcx, [rbx]; pv
0x14000f521  call    cs:__imp_CoTaskMemFree
0x14000f527  mov     qword ptr [rbx], 0
0x14000f52e  mov     rdx, rbx; ppwsz
0x14000f531  mov     rcx, [rsi+0C8h]; psz
0x14000f538  call    cs:__imp_SHStrDupW
0x14000f53e  mov     eax, [rdi]
0x14000f540  sub     eax, 2
0x14000f543  cmp     eax, 1
0x14000f546  ja      short loc_14000F558
0x14000f548  mov     rcx, [rsi+0D8h]; unsigned __int16 *
0x14000f54f  call    ?LoadIconFromResourceString@@YAPEAUHICON__@@PEAG@Z; LoadIconFromResourceString(ushort *)
0x14000f554  mov     [rdi+8], rax
0x14000f558  mov     dword ptr [rdi+3Ch], 2
0x14000f55f  mov     rcx, [rsp+88h+var_18]
0x14000f564  xor     rcx, rsp; StackCookie
0x14000f567  call    __security_check_cookie
0x14000f56c  lea     r11, [rsp+88h+var_8]
0x14000f574  mov     rbx, [r11+20h]
0x14000f578  mov     rsi, [r11+28h]
0x14000f57c  mov     rsp, r11
0x14000f57f  pop     rdi
0x14000f580  retn
```
