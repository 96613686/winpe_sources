# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800012dc`
- end: `0x1800013a3`
- name: `??$Write@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010430`

## callees

- `0x18000123c`
- `0x1800012dc`
- `0x180007740`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  unsigned __int16 *v10; // rax
  int v11; // ecx
  _BYTE v13[32]; // [rsp+30h] [rbp-31h] BYREF
  _DWORD *v14; // [rsp+50h] [rbp-11h]
  __int64 v15; // [rsp+58h] [rbp-9h]
  __int64 v16; // [rsp+60h] [rbp-1h]
  _DWORD v17[2]; // [rsp+68h] [rbp+7h] BYREF
  __int64 v18; // [rsp+70h] [rbp+Fh]
  __int64 v19; // [rsp+78h] [rbp+17h]
  __int64 *v20; // [rsp+80h] [rbp+1Fh]
  int v21; // [rsp+88h] [rbp+27h]
  int v22; // [rsp+8Ch] [rbp+2Bh]

  v7 = *a7;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &qword_180023510;
    v9 = 2;
  }
  v21 = v9;
  v18 = a6;
  v14 = v17;
  v20 = v7;
  v15 = 2;
  v22 = 0;
  v10 = *a5;
  v19 = 4;
  v11 = *v10;
  v16 = *((_QWORD *)v10 + 1);
  v17[0] = v11;
  v17[1] = 0;
  return tlgWriteTransfer_EtwEventWriteTransfer((__int64)&dword_18002B048, a2, 0, 0, 6, (__int64)v13);
}

```

## disassembly

```asm
0x1800012dc  push    rbp
0x1800012de  lea     rbp, [rsp-3Fh]
0x1800012e3  sub     rsp, 0A0h
0x1800012ea  mov     rax, cs:__security_cookie
0x1800012f1  xor     rax, rsp
0x1800012f4  mov     [rbp+3Fh+var_10], rax
0x1800012f8  mov     rax, [rbp+3Fh+arg_30]
0x1800012fc  xor     r8d, r8d
0x1800012ff  mov     r9d, 2
0x180001305  mov     rcx, [rax]
0x180001308  test    rcx, rcx
0x18000130b  jz      short loc_180001324
0x18000130d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001311  inc     rax
0x180001314  cmp     [rcx+rax*2], r8w
0x180001319  jnz     short loc_180001311
0x18000131b  lea     eax, ds:2[rax*2]
0x180001322  jmp     short loc_18000132E
0x180001324  lea     rcx, qword_180023510
0x18000132b  mov     eax, r9d
0x18000132e  mov     [rbp+3Fh+var_18], eax
0x180001331  mov     rax, [rbp+3Fh+arg_28]
0x180001335  mov     [rbp+3Fh+var_30], rax
0x180001339  lea     rax, [rbp+3Fh+var_38]
0x18000133d  mov     [rbp+3Fh+var_50], rax
0x180001341  mov     rax, [rbp+3Fh+arg_20]
0x180001345  mov     [rbp+3Fh+var_20], rcx
0x180001349  mov     [rbp+3Fh+var_48], r9
0x18000134d  xor     r9d, r9d
0x180001350  mov     [rbp+3Fh+var_14], r8d
0x180001354  mov     rax, [rax]
0x180001357  mov     [rbp+3Fh+var_28], 4
0x18000135f  movzx   ecx, word ptr [rax]
0x180001362  mov     rax, [rax+8]
0x180001366  mov     [rbp+3Fh+var_40], rax
0x18000136a  lea     rax, [rbp+3Fh+var_70]
0x18000136e  mov     [rbp+3Fh+var_38], ecx
0x180001371  lea     rcx, dword_18002B048
0x180001378  mov     [rsp+0A0h+var_78], rax
0x18000137d  mov     [rsp+0A0h+var_80], 6
0x180001385  mov     [rbp+3Fh+var_34], r8d
0x180001389  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000138e  mov     rcx, [rbp+3Fh+var_10]
0x180001392  xor     rcx, rsp; StackCookie
0x180001395  call    __security_check_cookie
0x18000139a  add     rsp, 0A0h
0x1800013a1  pop     rbp
0x1800013a2  retn
```
