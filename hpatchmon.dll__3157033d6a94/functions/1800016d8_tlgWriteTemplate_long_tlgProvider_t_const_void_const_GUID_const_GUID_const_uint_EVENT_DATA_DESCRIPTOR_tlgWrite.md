# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)

- ea: `0x1800016d8`
- end: `0x1800017cc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperArray@$00@@U2@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperArray@$00@@4AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `244`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64 *, __int64 *, __int64, __int64 *)`
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
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        __int64 *a8,
        __int64 a9,
        __int64 *a10)
{
  _BYTE v11[32]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v12; // [rsp+50h] [rbp-79h]
  __int64 v13; // [rsp+58h] [rbp-71h]
  __int64 v14; // [rsp+60h] [rbp-69h]
  __int64 v15; // [rsp+68h] [rbp-61h]
  __int64 *v16; // [rsp+70h] [rbp-59h]
  __int64 v17; // [rsp+78h] [rbp-51h]
  __int64 v18; // [rsp+80h] [rbp-49h]
  int v19; // [rsp+88h] [rbp-41h]
  int v20; // [rsp+8Ch] [rbp-3Dh]
  __int64 *v21; // [rsp+90h] [rbp-39h]
  __int64 v22; // [rsp+98h] [rbp-31h]
  __int64 v23; // [rsp+A0h] [rbp-29h]
  int v24; // [rsp+A8h] [rbp-21h]
  int v25; // [rsp+ACh] [rbp-1Dh]
  __int64 v26; // [rsp+B0h] [rbp-19h]
  __int64 v27; // [rsp+B8h] [rbp-11h]
  __int64 *v28; // [rsp+C0h] [rbp-9h]
  __int64 v29; // [rsp+C8h] [rbp-1h]
  __int64 v30; // [rsp+D0h] [rbp+7h]
  int v31; // [rsp+D8h] [rbp+Fh]
  int v32; // [rsp+DCh] [rbp+13h]

  v29 = 2;
  v32 = 0;
  v27 = 4;
  v22 = 2;
  v30 = *a10;
  v31 = *((unsigned __int16 *)a10 + 4);
  v26 = a9;
  v28 = a10 + 1;
  v25 = 0;
  v17 = 2;
  v20 = 0;
  v23 = *a8;
  v24 = *((unsigned __int16 *)a8 + 4);
  v21 = a8 + 1;
  v15 = 8;
  v13 = 8;
  v18 = *a7;
  v19 = *((unsigned __int16 *)a7 + 4);
  v14 = a6;
  v12 = a5;
  v16 = a7 + 1;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001E080, a2, 0, 0, 11, v11);
}

```

## disassembly

```asm
0x1800016d8  push    rbp
0x1800016da  lea     rbp, [rsp-27h]
0x1800016df  sub     rsp, 0F0h
0x1800016e6  mov     rax, cs:__security_cookie
0x1800016ed  xor     rax, rsp
0x1800016f0  mov     [rbp+27h+var_10], rax
0x1800016f4  mov     rax, [rbp+27h+arg_48]
0x1800016f8  xor     r9d, r9d
0x1800016fb  xor     r8d, r8d
0x1800016fe  mov     [rbp+27h+var_28], 2
0x180001706  mov     [rbp+27h+var_14], r9d
0x18000170a  mov     [rbp+27h+var_38], 4
0x180001712  lea     rcx, [rax+8]
0x180001716  mov     [rbp+27h+var_58], 2
0x18000171e  mov     rax, [rax]
0x180001721  mov     [rbp+27h+var_20], rax
0x180001725  movzx   eax, word ptr [rcx]
0x180001728  mov     [rbp+27h+var_18], eax
0x18000172b  mov     rax, [rbp+27h+arg_40]
0x18000172f  mov     [rbp+27h+var_40], rax
0x180001733  mov     rax, [rbp+27h+arg_38]
0x180001737  mov     [rbp+27h+var_30], rcx
0x18000173b  mov     [rbp+27h+var_44], r9d
0x18000173f  mov     [rbp+27h+var_78], 2
0x180001747  lea     rcx, [rax+8]
0x18000174b  mov     [rbp+27h+var_64], r9d
0x18000174f  mov     rax, [rax]
0x180001752  mov     [rbp+27h+var_50], rax
0x180001756  movzx   eax, word ptr [rcx]
0x180001759  mov     [rbp+27h+var_48], eax
0x18000175c  mov     rax, [rbp+27h+arg_30]
0x180001760  mov     [rbp+27h+var_60], rcx
0x180001764  mov     [rbp+27h+var_88], 8
0x18000176c  mov     [rbp+27h+var_98], 8
0x180001774  lea     rcx, [rax+8]
0x180001778  mov     rax, [rax]
0x18000177b  mov     [rbp+27h+var_70], rax
0x18000177f  movzx   eax, word ptr [rcx]
0x180001782  mov     [rbp+27h+var_68], eax
0x180001785  mov     rax, [rbp+27h+arg_28]
0x180001789  mov     [rbp+27h+var_90], rax
0x18000178d  mov     rax, [rbp+27h+arg_20]
0x180001791  mov     [rbp+27h+var_A0], rax
0x180001795  lea     rax, [rsp+0F0h+var_C0]
0x18000179a  mov     [rbp+27h+var_80], rcx
0x18000179e  lea     rcx, dword_18001E080
0x1800017a5  mov     [rsp+0F0h+var_C8], rax
0x1800017aa  mov     [rsp+0F0h+var_D0], 0Bh
0x1800017b2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800017b7  mov     rcx, [rbp+27h+var_10]
0x1800017bb  xor     rcx, rsp; StackCookie
0x1800017be  call    __security_check_cookie
0x1800017c3  add     rsp, 0F0h
0x1800017ca  pop     rbp
0x1800017cb  retn
```
