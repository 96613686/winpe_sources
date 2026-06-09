# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)

- ea: `0x180001624`
- end: `0x1800016d2`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperArray@$00@@4@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000df40`
- `0x180010710`

## callees

- `0x1800011cc`
- `0x180002270`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        __int64 *a7)
{
  _BYTE v8[32]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v9; // [rsp+50h] [rbp-21h]
  __int64 v10; // [rsp+58h] [rbp-19h]
  __int64 *v11; // [rsp+60h] [rbp-11h]
  __int64 v12; // [rsp+68h] [rbp-9h]
  __int64 v13; // [rsp+70h] [rbp-1h]
  int v14; // [rsp+78h] [rbp+7h]
  int v15; // [rsp+7Ch] [rbp+Bh]
  __int64 *v16; // [rsp+80h] [rbp+Fh]
  __int64 v17; // [rsp+88h] [rbp+17h]
  __int64 v18; // [rsp+90h] [rbp+1Fh]
  int v19; // [rsp+98h] [rbp+27h]
  int v20; // [rsp+9Ch] [rbp+2Bh]

  v17 = 2;
  v20 = 0;
  v12 = 2;
  v15 = 0;
  v18 = *a7;
  v19 = *((unsigned __int16 *)a7 + 4);
  v16 = a7 + 1;
  v10 = 4;
  v13 = *a6;
  v14 = *((unsigned __int16 *)a6 + 4);
  v9 = a5;
  v11 = a6 + 1;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, a2, 0, 0, 7, v8);
}

```

## disassembly

```asm
0x180001624  push    rbp
0x180001626  lea     rbp, [rsp-3Fh]
0x18000162b  sub     rsp, 0B0h
0x180001632  mov     rax, cs:__security_cookie
0x180001639  xor     rax, rsp
0x18000163c  mov     [rbp+3Fh+var_10], rax
0x180001640  mov     rax, [rbp+3Fh+arg_30]
0x180001644  xor     r9d, r9d
0x180001647  xor     r8d, r8d
0x18000164a  mov     [rbp+3Fh+var_28], 2
0x180001652  mov     [rbp+3Fh+var_14], r9d
0x180001656  mov     [rbp+3Fh+var_48], 2
0x18000165e  lea     rcx, [rax+8]
0x180001662  mov     [rbp+3Fh+var_34], r9d
0x180001666  mov     rax, [rax]
0x180001669  mov     [rbp+3Fh+var_20], rax
0x18000166d  movzx   eax, word ptr [rcx]
0x180001670  mov     [rbp+3Fh+var_18], eax
0x180001673  mov     rax, [rbp+3Fh+arg_28]
0x180001677  mov     [rbp+3Fh+var_30], rcx
0x18000167b  mov     [rbp+3Fh+var_58], 4
0x180001683  lea     rcx, [rax+8]
0x180001687  mov     rax, [rax]
0x18000168a  mov     [rbp+3Fh+var_40], rax
0x18000168e  movzx   eax, word ptr [rcx]
0x180001691  mov     [rbp+3Fh+var_38], eax
0x180001694  mov     rax, [rbp+3Fh+arg_20]
0x180001698  mov     [rbp+3Fh+var_60], rax
0x18000169c  lea     rax, [rbp+3Fh+var_80]
0x1800016a0  mov     [rbp+3Fh+var_50], rcx
0x1800016a4  lea     rcx, dword_18001E048
0x1800016ab  mov     [rsp+0B0h+var_88], rax
0x1800016b0  mov     [rsp+0B0h+var_90], 7
0x1800016b8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800016bd  mov     rcx, [rbp+3Fh+var_10]
0x1800016c1  xor     rcx, rsp; StackCookie
0x1800016c4  call    __security_check_cookie
0x1800016c9  add     rsp, 0B0h
0x1800016d0  pop     rbp
0x1800016d1  retn
```
