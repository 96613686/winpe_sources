# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001b14`
- end: `0x180001b9f`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `139`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180011e80`
- `0x1800133d8`
- `0x180027d6c`
- `0x1800287dc`
- `0x180031afc`
- `0x1800320a8`
- `0x1800322c0`
- `0x180034150`
- `0x180034440`
- `0x180034dd0`

## callees

- `0x180001a70`
- `0x180001b14`
- `0x1800358a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5)
{
  const WCHAR *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  const WCHAR *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &Name;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800495B0, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x180001b14  sub     rsp, 78h
0x180001b18  mov     rax, cs:__security_cookie
0x180001b1f  xor     rax, rsp
0x180001b22  mov     [rsp+78h+var_18], rax
0x180001b27  mov     rax, [rsp+78h+arg_20]
0x180001b2f  xor     r8d, r8d
0x180001b32  mov     rcx, [rax]
0x180001b35  test    rcx, rcx
0x180001b38  jz      short loc_180001B51
0x180001b3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001b3e  inc     rax
0x180001b41  cmp     [rcx+rax*2], r8w
0x180001b46  jnz     short loc_180001B3E
0x180001b48  lea     eax, ds:2[rax*2]
0x180001b4f  jmp     short loc_180001B5D
0x180001b51  lea     rcx, Name
0x180001b58  mov     eax, 2
0x180001b5d  mov     [rsp+78h+var_20], eax
0x180001b61  xor     r9d, r9d
0x180001b64  lea     rax, [rsp+78h+var_48]
0x180001b69  mov     [rsp+78h+var_28], rcx
0x180001b6e  mov     [rsp+78h+var_50], rax
0x180001b73  lea     rcx, dword_1800495B0
0x180001b7a  mov     [rsp+78h+var_58], 3
0x180001b82  mov     [rsp+78h+var_1C], r8d
0x180001b87  call    _tlgWriteTransfer_EventWriteTransfer
0x180001b8c  mov     rcx, [rsp+78h+var_18]
0x180001b91  xor     rcx, rsp; StackCookie
0x180001b94  call    __security_check_cookie
0x180001b99  add     rsp, 78h
0x180001b9d  retn
```
