# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x1400010cc`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002548`

## callees

- `0x140001008`
- `0x140001310`
- `0x1400059b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 *a6,
        __int64 a7,
        const WCHAR **a8)
{
  const WCHAR *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h]
  __int64 v14; // [rsp+58h] [rbp-11h]
  __int64 v15; // [rsp+60h] [rbp-9h]
  __int64 v16; // [rsp+68h] [rbp-1h]
  __int64 v17; // [rsp+70h] [rbp+7h]
  __int64 v18; // [rsp+78h] [rbp+Fh]
  const WCHAR *v19; // [rsp+80h] [rbp+17h]
  int v20; // [rsp+88h] [rbp+1Fh]
  int v21; // [rsp+8Ch] [rbp+23h]

  v8 = *a8;
  if ( *a8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v8 = &PathName;
    v10 = 2;
  }
  v20 = v10;
  v17 = a7;
  v19 = v8;
  v21 = 0;
  v18 = 1;
  v15 = *a6;
  v16 = 16;
  v14 = 16;
  v13 = *a5;
  return tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_14000A000, a2, 0, 0, 6u, &v12);
}

```

## disassembly

```asm
0x140001008  push    rbp
0x14000100a  lea     rbp, [rsp-37h]
0x14000100f  sub     rsp, 0A0h
0x140001016  mov     rax, cs:__security_cookie
0x14000101d  xor     rax, rsp
0x140001020  mov     [rbp+37h+var_10], rax
0x140001024  mov     rax, [rbp+37h+arg_38]
0x140001028  xor     r9d, r9d
0x14000102b  mov     rcx, [rax]
0x14000102e  test    rcx, rcx
0x140001031  jz      short loc_14000104A
0x140001033  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001037  inc     rax
0x14000103a  cmp     [rcx+rax*2], r9w
0x14000103f  jnz     short loc_140001037
0x140001041  lea     eax, ds:2[rax*2]
0x140001048  jmp     short loc_140001056
0x14000104a  lea     rcx, PathName
0x140001051  mov     eax, 2
0x140001056  mov     [rbp+37h+var_18], eax
0x140001059  xor     r8d, r8d
0x14000105c  mov     rax, [rbp+37h+arg_30]
0x140001060  mov     [rbp+37h+var_30], rax
0x140001064  mov     rax, [rbp+37h+arg_28]
0x140001068  mov     [rbp+37h+var_20], rcx
0x14000106c  mov     [rbp+37h+var_14], r9d
0x140001070  mov     [rbp+37h+var_28], 1
0x140001078  mov     rcx, [rax]
0x14000107b  mov     rax, [rbp+37h+arg_20]
0x14000107f  mov     [rbp+37h+var_40], rcx
0x140001083  mov     [rbp+37h+var_38], 10h
0x14000108b  mov     [rbp+37h+var_48], 10h
0x140001093  mov     rcx, [rax]
0x140001096  lea     rax, [rbp+37h+var_70]
0x14000109a  mov     [rbp+37h+var_50], rcx
0x14000109e  lea     rcx, dword_14000A000
0x1400010a5  mov     [rsp+0A0h+var_78], rax
0x1400010aa  mov     [rsp+0A0h+var_80], 6
0x1400010b2  call    _tlgWriteTransfer_BrowserWriteTransfer
0x1400010b7  mov     rcx, [rbp+37h+var_10]
0x1400010bb  xor     rcx, rsp; StackCookie
0x1400010be  call    __security_check_cookie
0x1400010c3  add     rsp, 0A0h
0x1400010ca  pop     rbp
0x1400010cb  retn
```
