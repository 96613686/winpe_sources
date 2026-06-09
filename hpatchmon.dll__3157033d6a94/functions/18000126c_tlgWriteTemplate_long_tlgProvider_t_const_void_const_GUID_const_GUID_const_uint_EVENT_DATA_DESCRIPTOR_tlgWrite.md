# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000126c`
- end: `0x180001324`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@D@@3@Z`
- size: `184`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009a80`

## callees

- `0x1800011cc`
- `0x18000126c`
- `0x180002270`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8)
{
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _BYTE v12[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h]
  __int64 v14; // [rsp+58h] [rbp-11h]
  __int64 v15; // [rsp+60h] [rbp-9h]
  __int64 v16; // [rsp+68h] [rbp-1h]
  const unsigned __int16 *v17; // [rsp+70h] [rbp+7h]
  int v18; // [rsp+78h] [rbp+Fh]
  int v19; // [rsp+7Ch] [rbp+13h]
  __int64 v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  v20 = a8;
  v21 = 4;
  v8 = *a7;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v8 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v8 = &byte_180016B57;
    v10 = 1;
  }
  v18 = v10;
  v15 = a6;
  v13 = a5;
  v17 = v8;
  v19 = 0;
  v16 = 4;
  v14 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, a2, 0, 0, 6, v12);
}

```

## disassembly

```asm
0x18000126c  push    rbp
0x18000126e  lea     rbp, [rsp-37h]
0x180001273  sub     rsp, 0A0h
0x18000127a  mov     rax, cs:__security_cookie
0x180001281  xor     rax, rsp
0x180001284  mov     [rbp+37h+var_10], rax
0x180001288  mov     rax, [rbp+37h+arg_38]
0x18000128c  xor     r8d, r8d
0x18000128f  mov     [rbp+37h+var_20], rax
0x180001293  mov     rax, [rbp+37h+arg_30]
0x180001297  mov     [rbp+37h+var_18], 4
0x18000129f  mov     rcx, [rax]
0x1800012a2  test    rcx, rcx
0x1800012a5  jz      short loc_1800012B8
0x1800012a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800012ab  inc     rax
0x1800012ae  cmp     [rcx+rax], r8b
0x1800012b2  jnz     short loc_1800012AB
0x1800012b4  inc     eax
0x1800012b6  jmp     short loc_1800012C4
0x1800012b8  lea     rcx, byte_180016B57
0x1800012bf  mov     eax, 1
0x1800012c4  mov     [rbp+37h+var_28], eax
0x1800012c7  xor     r9d, r9d
0x1800012ca  mov     rax, [rbp+37h+arg_28]
0x1800012ce  mov     [rbp+37h+var_40], rax
0x1800012d2  mov     rax, [rbp+37h+arg_20]
0x1800012d6  mov     [rbp+37h+var_50], rax
0x1800012da  lea     rax, [rbp+37h+var_70]
0x1800012de  mov     [rbp+37h+var_30], rcx
0x1800012e2  lea     rcx, dword_18001E048
0x1800012e9  mov     [rsp+0A0h+var_78], rax
0x1800012ee  mov     [rsp+0A0h+var_80], 6
0x1800012f6  mov     [rbp+37h+var_24], r8d
0x1800012fa  mov     [rbp+37h+var_38], 4
0x180001302  mov     [rbp+37h+var_48], 4
0x18000130a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000130f  mov     rcx, [rbp+37h+var_10]
0x180001313  xor     rcx, rsp; StackCookie
0x180001316  call    __security_check_cookie
0x18000131b  add     rsp, 0A0h
0x180001322  pop     rbp
0x180001323  retn
```
