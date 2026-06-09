# PortMappingProtocolExists(IWbemServices *,ushort *,ushort,uchar)

- ea: `0x18002a07c`
- end: `0x18002a1e0`
- name: `?PortMappingProtocolExists@@YAEPEAUIWbemServices@@PEAGGE@Z`
- size: `356`
- prototype: `unsigned __int8 __fastcall(struct IWbemServices *, unsigned __int16 *, unsigned __int16, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010350`
- `0x180023e20`
- `0x1800240a0`

## callees

- `0x1800056dc`
- `0x180028210`
- `0x18002a07c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002a158`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a158`

## string_xrefs

- `0x18002a0fc`: `HNet_PortMappingProtocol`
- `0x18002a0af`: `Port = %u AND IPProtocol = %u`

## pseudocode

```c
char __fastcall PortMappingProtocolExists(
        struct IWbemServices *a1,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        unsigned __int8 a4)
{
  char v6; // di
  const unsigned __int16 *v7; // rdx
  struct IWbemServicesVtbl *lpVtbl; // rax
  int v9; // ebx
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v15[264]; // [rsp+60h] [rbp-A0h] BYREF

  bstrString = 0;
  v12 = 0;
  v14 = 0;
  v6 = 0;
  v11 = 0;
  if ( !StringCchPrintfW(v15, 0x101u, L"Port = %u AND IPProtocol = %u", a3, a4)
    && !(unsigned int)BuildSelectQueryBstr(&bstrString, v7, L"HNet_PortMappingProtocol", v15) )
  {
    lpVtbl = a1->lpVtbl;
    v12 = 0;
    v9 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, BSTR, __int64, _QWORD, __int64 *))lpVtbl->ExecQuery)(
           a1,
           a2,
           bstrString,
           48,
           0,
           &v12);
    SysFreeString(bstrString);
    if ( !v9 )
    {
      v14 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v12 + 32LL))(
             v12,
             0xFFFFFFFFLL,
             1,
             &v14,
             &v11) >= 0
        && v11 == 1 )
      {
        v6 = 1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002a07c  push    rbp
0x18002a07e  push    rbx
0x18002a07f  push    rsi
0x18002a080  push    rdi
0x18002a081  lea     rbp, [rsp-188h]
0x18002a089  sub     rsp, 288h
0x18002a090  mov     rax, cs:__security_cookie
0x18002a097  xor     rax, rsp
0x18002a09a  mov     [rbp+1A0h+var_30], rax
0x18002a0a1  movzx   eax, r9b
0x18002a0a5  mov     rsi, rdx
0x18002a0a8  movzx   r9d, r8w
0x18002a0ac  mov     rbx, rcx
0x18002a0af  lea     r8, ?c_wszPortMappingProtocolQueryFormat@@3QBGB; "Port = %u AND IPProtocol = %u"
0x18002a0b6  mov     [rsp+2A0h+bstrString], 0
0x18002a0bf  mov     edx, 101h; unsigned __int64
0x18002a0c4  mov     [rsp+2A0h+var_258], 0
0x18002a0cd  lea     rcx, [rsp+2A0h+var_240]; unsigned __int16 *
0x18002a0d2  mov     [rsp+2A0h+var_248], 0
0x18002a0db  xor     dil, dil
0x18002a0de  mov     [rsp+2A0h+var_260], 0
0x18002a0e6  mov     dword ptr [rsp+2A0h+var_280], eax
0x18002a0ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a0ef  test    eax, eax
0x18002a0f1  jnz     loc_18002A1C2
0x18002a0f7  lea     r9, [rsp+2A0h+var_240]; unsigned __int16 *
0x18002a0fc  lea     r8, ?c_wszHnetPortMappingProtocol@@3QBGB; "HNet_PortMappingProtocol"
0x18002a103  lea     rcx, [rsp+2A0h+bstrString]; unsigned __int16 **
0x18002a108  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x18002a10d  test    eax, eax
0x18002a10f  jnz     loc_18002A1C2
0x18002a115  mov     rax, [rbx]
0x18002a118  lea     rcx, [rsp+2A0h+var_258]
0x18002a11d  mov     r8, [rsp+2A0h+bstrString]
0x18002a122  mov     r9d, 30h ; '0'
0x18002a128  mov     [rsp+2A0h+var_278], rcx
0x18002a12d  mov     rdx, rsi
0x18002a130  mov     rcx, rbx
0x18002a133  mov     [rsp+2A0h+var_258], 0
0x18002a13c  mov     rax, [rax+0A0h]
0x18002a143  mov     [rsp+2A0h+var_280], 0
0x18002a14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a151  mov     rcx, [rsp+2A0h+bstrString]; bstrString
0x18002a156  mov     ebx, eax
0x18002a158  call    cs:__imp_SysFreeString
0x18002a15e  test    ebx, ebx
0x18002a160  jnz     short loc_18002A1C2
0x18002a162  mov     rcx, [rsp+2A0h+var_258]
0x18002a167  lea     rdx, [rsp+2A0h+var_260]
0x18002a16c  mov     [rsp+2A0h+var_248], 0
0x18002a175  lea     r9, [rsp+2A0h+var_248]
0x18002a17a  mov     [rsp+2A0h+var_280], rdx
0x18002a17f  lea     r8d, [rbx+1]
0x18002a183  or      edx, 0FFFFFFFFh
0x18002a186  mov     rax, [rcx]
0x18002a189  mov     rax, [rax+20h]
0x18002a18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a192  test    eax, eax
0x18002a194  js      short loc_18002A1B1
0x18002a196  cmp     [rsp+2A0h+var_260], 1
0x18002a19b  jnz     short loc_18002A1B1
0x18002a19d  mov     rcx, [rsp+2A0h+var_248]
0x18002a1a2  mov     dil, 1
0x18002a1a5  mov     rax, [rcx]
0x18002a1a8  mov     rax, [rax+10h]
0x18002a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1b1  mov     rcx, [rsp+2A0h+var_258]
0x18002a1b6  mov     rdx, [rcx]
0x18002a1b9  mov     rax, [rdx+10h]
0x18002a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1c2  mov     al, dil
0x18002a1c5  mov     rcx, [rbp+1A0h+var_30]
0x18002a1cc  xor     rcx, rsp; StackCookie
0x18002a1cf  call    __security_check_cookie
0x18002a1d4  add     rsp, 288h
0x18002a1db  pop     rdi
0x18002a1dc  pop     rsi
0x18002a1dd  pop     rbx
0x18002a1de  pop     rbp
0x18002a1df  retn
```
