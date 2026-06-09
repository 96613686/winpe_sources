# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001008`
- end: `0x1800010fa`
- name: `??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c76c`
- `0x18001e4fc`

## callees

- `0x180001008`
- `0x180001838`
- `0x180014130`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 v9; // rcx
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-48h]
  int v18; // [rsp+58h] [rbp-40h]
  int v19; // [rsp+5Ch] [rbp-3Ch]
  __int64 v20; // [rsp+60h] [rbp-38h]
  __int64 v21; // [rsp+68h] [rbp-30h]
  __int64 *v22; // [rsp+70h] [rbp-28h]
  int v23; // [rsp+78h] [rbp-20h]
  int v24; // [rsp+7Ch] [rbp-1Ch]

  v9 = -1;
  v10 = 2;
  v11 = *a7;
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = qword_180031880;
    v13 = 2;
  }
  v23 = v13;
  v20 = a6;
  v22 = v11;
  v24 = 0;
  v21 = 4;
  v14 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_WORD *)v14 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v14 = qword_180031880;
  }
  v17 = v14;
  v18 = v10;
  v19 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5u, &v16);
}

```

## disassembly

```asm
0x180001008  sub     rsp, 98h
0x18000100f  mov     rax, cs:__security_cookie
0x180001016  xor     rax, rsp
0x180001019  mov     [rsp+98h+var_18], rax
0x180001021  mov     rax, [rsp+98h+arg_30]
0x180001029  mov     r11, rdx
0x18000102c  mov     r10, rcx
0x18000102f  xor     r9d, r9d
0x180001032  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001036  mov     r8d, 2
0x18000103c  mov     rdx, [rax]
0x18000103f  test    rdx, rdx
0x180001042  jz      short loc_18000105A
0x180001044  mov     rax, rcx
0x180001047  inc     rax
0x18000104a  cmp     [rdx+rax*2], r9w
0x18000104f  jnz     short loc_180001047
0x180001051  lea     eax, ds:2[rax*2]
0x180001058  jmp     short loc_180001064
0x18000105a  lea     rdx, qword_180031880
0x180001061  mov     eax, r8d
0x180001064  mov     [rsp+98h+var_20], eax
0x180001068  mov     rax, [rsp+98h+arg_28]
0x180001070  mov     [rsp+98h+var_38], rax
0x180001075  mov     rax, [rsp+98h+arg_20]
0x18000107d  mov     [rsp+98h+var_28], rdx
0x180001082  mov     [rsp+98h+var_1C], r9d
0x180001087  mov     [rsp+98h+var_30], 4
0x180001090  mov     rdx, [rax]
0x180001093  test    rdx, rdx
0x180001096  jz      short loc_1800010AC
0x180001098  inc     rcx
0x18000109b  cmp     [rdx+rcx*2], r9w
0x1800010a0  jnz     short loc_180001098
0x1800010a2  lea     r8d, ds:2[rcx*2]
0x1800010aa  jmp     short loc_1800010B3
0x1800010ac  lea     rdx, qword_180031880
0x1800010b3  lea     rax, [rsp+98h+var_68]
0x1800010b8  mov     [rsp+98h+var_48], rdx
0x1800010bd  mov     [rsp+98h+var_40], r8d
0x1800010c2  mov     rdx, r11
0x1800010c5  mov     [rsp+98h+var_70], rax
0x1800010ca  xor     r8d, r8d
0x1800010cd  mov     rcx, r10
0x1800010d0  mov     [rsp+98h+var_78], 5
0x1800010d8  mov     [rsp+98h+var_3C], r9d
0x1800010dd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010e2  mov     rcx, [rsp+98h+var_18]
0x1800010ea  xor     rcx, rsp; StackCookie
0x1800010ed  call    __security_check_cookie
0x1800010f2  add     rsp, 98h
0x1800010f9  retn
```
