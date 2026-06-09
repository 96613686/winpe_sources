# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001254`
- end: `0x180001346`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094a0`

## callees

- `0x180001090`
- `0x180001254`
- `0x18000ccc0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  __int64 *v19; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+68h] [rbp-30h]
  int v21; // [rsp+6Ch] [rbp-2Ch]
  __int64 v22; // [rsp+70h] [rbp-28h]
  __int64 v23; // [rsp+78h] [rbp-20h]

  v22 = a7;
  v8 = -1;
  v23 = 4;
  v9 = 2;
  v10 = *a6;
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_180010000;
    v12 = 2;
  }
  v20 = v12;
  v19 = v10;
  v21 = 0;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_WORD *)v13 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &qword_180010000;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, a2, 0, 0, 5u, &v15);
}

```

## disassembly

```asm
0x180001254  sub     rsp, 98h
0x18000125b  mov     rax, cs:__security_cookie
0x180001262  xor     rax, rsp
0x180001265  mov     [rsp+98h+var_18], rax
0x18000126d  mov     rax, [rsp+98h+arg_30]
0x180001275  xor     r9d, r9d
0x180001278  mov     [rsp+98h+var_28], rax
0x18000127d  mov     r10, rdx
0x180001280  mov     rax, [rsp+98h+arg_28]
0x180001288  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000128c  mov     [rsp+98h+var_20], 4
0x180001295  lea     r8d, [r9+2]
0x180001299  mov     rdx, [rax]
0x18000129c  test    rdx, rdx
0x18000129f  jz      short loc_1800012B7
0x1800012a1  mov     rax, rcx
0x1800012a4  inc     rax
0x1800012a7  cmp     [rdx+rax*2], r9w
0x1800012ac  jnz     short loc_1800012A4
0x1800012ae  lea     eax, ds:2[rax*2]
0x1800012b5  jmp     short loc_1800012C1
0x1800012b7  lea     rdx, qword_180010000
0x1800012be  mov     eax, r8d
0x1800012c1  mov     [rsp+98h+var_30], eax
0x1800012c5  mov     rax, [rsp+98h+arg_20]
0x1800012cd  mov     [rsp+98h+var_38], rdx
0x1800012d2  mov     [rsp+98h+var_2C], r9d
0x1800012d7  mov     rdx, [rax]
0x1800012da  test    rdx, rdx
0x1800012dd  jz      short loc_1800012F3
0x1800012df  inc     rcx
0x1800012e2  cmp     [rdx+rcx*2], r9w
0x1800012e7  jnz     short loc_1800012DF
0x1800012e9  lea     r8d, ds:2[rcx*2]
0x1800012f1  jmp     short loc_1800012FA
0x1800012f3  lea     rdx, qword_180010000
0x1800012fa  lea     rax, [rsp+98h+var_68]
0x1800012ff  mov     [rsp+98h+var_48], rdx
0x180001304  mov     [rsp+98h+var_40], r8d
0x180001309  lea     rcx, dword_180014230
0x180001310  mov     [rsp+98h+var_70], rax
0x180001315  xor     r8d, r8d
0x180001318  mov     rdx, r10
0x18000131b  mov     [rsp+98h+var_78], 5
0x180001323  mov     [rsp+98h+var_3C], r9d
0x180001328  call    _tlgWriteTransfer_EventWriteTransfer
0x18000132d  mov     rcx, [rsp+98h+var_18]
0x180001335  xor     rcx, rsp; StackCookie
0x180001338  call    __security_check_cookie
0x18000133d  add     rsp, 98h
0x180001344  retn
```
