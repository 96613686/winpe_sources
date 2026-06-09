# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x18000134c`
- end: `0x1800013d7`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `139`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b81c`
- `0x18000bce8`
- `0x18000be6c`

## callees

- `0x180001090`
- `0x18000134c`
- `0x18000ccc0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &qword_180010000;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x18000134c  sub     rsp, 78h
0x180001350  mov     rax, cs:__security_cookie
0x180001357  xor     rax, rsp
0x18000135a  mov     [rsp+78h+var_18], rax
0x18000135f  mov     rax, [rsp+78h+arg_20]
0x180001367  xor     r8d, r8d
0x18000136a  mov     rcx, [rax]
0x18000136d  test    rcx, rcx
0x180001370  jz      short loc_180001389
0x180001372  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001376  inc     rax
0x180001379  cmp     [rcx+rax*2], r8w
0x18000137e  jnz     short loc_180001376
0x180001380  lea     eax, ds:2[rax*2]
0x180001387  jmp     short loc_180001395
0x180001389  lea     rcx, qword_180010000
0x180001390  mov     eax, 2
0x180001395  mov     [rsp+78h+var_20], eax
0x180001399  xor     r9d, r9d
0x18000139c  lea     rax, [rsp+78h+var_48]
0x1800013a1  mov     [rsp+78h+var_28], rcx
0x1800013a6  mov     [rsp+78h+var_50], rax
0x1800013ab  lea     rcx, dword_180014230
0x1800013b2  mov     [rsp+78h+var_58], 3
0x1800013ba  mov     [rsp+78h+var_1C], r8d
0x1800013bf  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013c4  mov     rcx, [rsp+78h+var_18]
0x1800013c9  xor     rcx, rsp; StackCookie
0x1800013cc  call    __security_check_cookie
0x1800013d1  add     rsp, 78h
0x1800013d5  retn
```
