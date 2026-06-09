# ApplicationProtocolExists(IWbemServices *,ushort *,ushort,uchar)

- ea: `0x180027ca4`
- end: `0x180027e08`
- name: `?ApplicationProtocolExists@@YAEPEAUIWbemServices@@PEAGGE@Z`
- size: `356`
- prototype: `char __fastcall(struct IWbemServices *, unsigned __int16 *, unsigned __int16, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ddf0`
- `0x180023270`
- `0x1800233e0`

## callees

- `0x1800056dc`
- `0x180027ca4`
- `0x180028210`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180027d80`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d80`

## string_xrefs

- `0x180027d24`: `HNet_ApplicationProtocol`
- `0x180027cd7`: `OutgoingPort = %u AND OutgoingIPProtocol = %u`

## pseudocode

```c
char __fastcall ApplicationProtocolExists(
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
  if ( !StringCchPrintfW(v15, 0x101u, L"OutgoingPort = %u AND OutgoingIPProtocol = %u", a3, a4)
    && !(unsigned int)BuildSelectQueryBstr(&bstrString, v7, L"HNet_ApplicationProtocol", v15) )
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
0x180027ca4  push    rbp
0x180027ca6  push    rbx
0x180027ca7  push    rsi
0x180027ca8  push    rdi
0x180027ca9  lea     rbp, [rsp-188h]
0x180027cb1  sub     rsp, 288h
0x180027cb8  mov     rax, cs:__security_cookie
0x180027cbf  xor     rax, rsp
0x180027cc2  mov     [rbp+1A0h+var_30], rax
0x180027cc9  movzx   eax, r9b
0x180027ccd  mov     rsi, rdx
0x180027cd0  movzx   r9d, r8w
0x180027cd4  mov     rbx, rcx
0x180027cd7  lea     r8, ?c_wszApplicationProtocolQueryFormat@@3QBGB; "OutgoingPort = %u AND OutgoingIPProtoco"...
0x180027cde  mov     [rsp+2A0h+bstrString], 0
0x180027ce7  mov     edx, 101h; unsigned __int64
0x180027cec  mov     [rsp+2A0h+var_258], 0
0x180027cf5  lea     rcx, [rsp+2A0h+var_240]; unsigned __int16 *
0x180027cfa  mov     [rsp+2A0h+var_248], 0
0x180027d03  xor     dil, dil
0x180027d06  mov     [rsp+2A0h+var_260], 0
0x180027d0e  mov     dword ptr [rsp+2A0h+var_280], eax
0x180027d12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027d17  test    eax, eax
0x180027d19  jnz     loc_180027DEA
0x180027d1f  lea     r9, [rsp+2A0h+var_240]; unsigned __int16 *
0x180027d24  lea     r8, ?c_wszHnetApplicationProtocol@@3QBGB; "HNet_ApplicationProtocol"
0x180027d2b  lea     rcx, [rsp+2A0h+bstrString]; unsigned __int16 **
0x180027d30  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x180027d35  test    eax, eax
0x180027d37  jnz     loc_180027DEA
0x180027d3d  mov     rax, [rbx]
0x180027d40  lea     rcx, [rsp+2A0h+var_258]
0x180027d45  mov     r8, [rsp+2A0h+bstrString]
0x180027d4a  mov     r9d, 30h ; '0'
0x180027d50  mov     [rsp+2A0h+var_278], rcx
0x180027d55  mov     rdx, rsi
0x180027d58  mov     rcx, rbx
0x180027d5b  mov     [rsp+2A0h+var_258], 0
0x180027d64  mov     rax, [rax+0A0h]
0x180027d6b  mov     [rsp+2A0h+var_280], 0
0x180027d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d79  mov     rcx, [rsp+2A0h+bstrString]; bstrString
0x180027d7e  mov     ebx, eax
0x180027d80  call    cs:__imp_SysFreeString
0x180027d86  test    ebx, ebx
0x180027d88  jnz     short loc_180027DEA
0x180027d8a  mov     rcx, [rsp+2A0h+var_258]
0x180027d8f  lea     rdx, [rsp+2A0h+var_260]
0x180027d94  mov     [rsp+2A0h+var_248], 0
0x180027d9d  lea     r9, [rsp+2A0h+var_248]
0x180027da2  mov     [rsp+2A0h+var_280], rdx
0x180027da7  lea     r8d, [rbx+1]
0x180027dab  or      edx, 0FFFFFFFFh
0x180027dae  mov     rax, [rcx]
0x180027db1  mov     rax, [rax+20h]
0x180027db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dba  test    eax, eax
0x180027dbc  js      short loc_180027DD9
0x180027dbe  cmp     [rsp+2A0h+var_260], 1
0x180027dc3  jnz     short loc_180027DD9
0x180027dc5  mov     rcx, [rsp+2A0h+var_248]
0x180027dca  mov     dil, 1
0x180027dcd  mov     rax, [rcx]
0x180027dd0  mov     rax, [rax+10h]
0x180027dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dd9  mov     rcx, [rsp+2A0h+var_258]
0x180027dde  mov     rdx, [rcx]
0x180027de1  mov     rax, [rdx+10h]
0x180027de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dea  mov     al, dil
0x180027ded  mov     rcx, [rbp+1A0h+var_30]
0x180027df4  xor     rcx, rsp; StackCookie
0x180027df7  call    __security_check_cookie
0x180027dfc  add     rsp, 288h
0x180027e03  pop     rdi
0x180027e04  pop     rsi
0x180027e05  pop     rbx
0x180027e06  pop     rbp
0x180027e07  retn
```
