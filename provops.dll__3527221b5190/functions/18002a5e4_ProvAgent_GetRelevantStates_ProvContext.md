# ProvAgent::GetRelevantStates(ProvContext)

- ea: `0x18002a5e4`
- end: `0x18002a850`
- name: `?GetRelevantStates@ProvAgent@@SA?AV?$vector@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@V?$allocator@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@@std@@@std@@UProvContext@@@Z`
- size: `620`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000f8d0`
- `0x180010b40`

## callees

- `0x180004d68`
- `0x18001b388`
- `0x18002a340`
- `0x18002a5e4`
- `0x18002aa6c`
- `0x180033ed0`

## string_xrefs

- `0x18002a83e`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
_QWORD *__fastcall ProvAgent::GetRelevantStates(_QWORD *a1, __int64 a2)
{
  __int64 v4; // r8
  __m128i *p_si128; // rdx
  __int64 v6; // r8
  __int64 *v7; // rdx
  __int64 *v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rdx
  unsigned int v12; // eax
  __int64 v13; // [rsp+20h] [rbp-29h] BYREF
  __int64 v14; // [rsp+28h] [rbp-21h] BYREF
  __int64 v15; // [rsp+30h] [rbp-19h] BYREF
  int v16; // [rsp+38h] [rbp-11h] BYREF
  __int64 v17; // [rsp+40h] [rbp-9h] BYREF
  _QWORD *v18; // [rsp+48h] [rbp-1h]
  __int64 v19; // [rsp+50h] [rbp+7h] BYREF
  int v20; // [rsp+58h] [rbp+Fh]
  __m128i si128; // [rsp+60h] [rbp+17h] BYREF
  int v22; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v18 = a1;
  v19 = 0xB00000001LL;
  v20 = 18;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v22 = 8;
  HIDWORD(v15) = 13;
  v14 = 0xF0000000ELL;
  v16 = 6;
  v17 = 0x1000000007LL;
  v13 = 0x110000000CLL;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  LODWORD(v15) = 1;
  switch ( *(_DWORD *)(a2 + 4) )
  {
    case 1:
      ((void (__fastcall *)(_QWORD *, __int64 *, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD *))AppendPermittedStates)(
        a1,
        &v19,
        3,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18);
      ((void (__fastcall *)(_QWORD *, char *, __int64, __int64, __int64, __int64, __int64))AppendPermittedStates)(
        a1,
        (char *)&v15 + 4,
        1,
        a2,
        v13,
        v14,
        v15);
      ((void (__fastcall *)(_QWORD *, __int64 *, __int64, __int64, __int64))AppendPermittedStates)(a1, &v14, 2, a2, v13);
      if ( (unsigned __int8)IsUiccProvisioningEnabled() )
      {
LABEL_20:
        v8 = &v13;
        goto LABEL_21;
      }
      v9 = 1;
      v10 = (__int64 *)&v16;
LABEL_19:
      AppendPermittedStates(
        a1,
        v10,
        v9,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18,
        v19,
        v20,
        si128.m128i_i64[0],
        si128.m128i_i64[1],
        v22);
      goto LABEL_20;
    case 2:
      ((void (__fastcall *)(_QWORD *, __int64 *, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD *))AppendPermittedStates)(
        a1,
        &v19,
        3,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18);
      ((void (__fastcall *)(_QWORD *, __m128i *, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD *, __int64, int))AppendPermittedStates)(
        a1,
        &si128,
        5,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18,
        v19,
        v20);
      v4 = 2;
      p_si128 = (__m128i *)&v14;
      goto LABEL_10;
    case 3:
      ((void (__fastcall *)(_QWORD *, __int64 *, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD *))AppendPermittedStates)(
        a1,
        &v19,
        3,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18);
      ((void (__fastcall *)(_QWORD *, __m128i *, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD *, __int64, int))AppendPermittedStates)(
        a1,
        &si128,
        5,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18,
        v19,
        v20);
      v9 = 2;
      v10 = &v14;
      goto LABEL_19;
    case 4:
      ((void (__fastcall *)(_QWORD *, __int64 *, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD *))AppendPermittedStates)(
        a1,
        &v19,
        3,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18);
      v6 = 2;
      v7 = &v17;
      goto LABEL_11;
    case 5:
      goto LABEL_13;
    case 6:
      v4 = 3;
      p_si128 = (__m128i *)&v19;
      goto LABEL_10;
    case 7:
LABEL_13:
      ((void (__fastcall *)(_QWORD *, __int64 *, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD *))AppendPermittedStates)(
        a1,
        &v19,
        3,
        a2,
        v13,
        v14,
        v15,
        v16,
        v17,
        v18);
      break;
    case 8:
      break;
    default:
      v12 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
        (const char *)v12,
        v13);
  }
  v4 = 5;
  p_si128 = &si128;
LABEL_10:
  AppendPermittedStates(
    a1,
    p_si128,
    v4,
    a2,
    v13,
    v14,
    v15,
    v16,
    v17,
    v18,
    v19,
    v20,
    si128.m128i_i64[0],
    si128.m128i_i64[1],
    v22);
  v6 = 1;
  v7 = &v13;
LABEL_11:
  AppendPermittedStates(
    a1,
    v7,
    v6,
    a2,
    v13,
    v14,
    v15,
    v16,
    v17,
    v18,
    v19,
    v20,
    si128.m128i_i64[0],
    si128.m128i_i64[1],
    v22);
  v8 = (__int64 *)((char *)&v13 + 4);
LABEL_21:
  AppendPermittedStates(
    a1,
    v8,
    1,
    a2,
    v13,
    v14,
    v15,
    v16,
    v17,
    v18,
    v19,
    v20,
    si128.m128i_i64[0],
    si128.m128i_i64[1],
    v22);
  return a1;
}

```

## disassembly

```asm
0x18002a5e4  push    rbp
0x18002a5e6  push    rbx
0x18002a5e7  push    rsi
0x18002a5e8  push    rdi
0x18002a5e9  lea     rbp, [rsp-3Fh]
0x18002a5ee  sub     rsp, 88h
0x18002a5f5  mov     rax, cs:__security_cookie
0x18002a5fc  xor     rax, rsp
0x18002a5ff  mov     [rbp+57h+var_28], rax
0x18002a603  mov     rdi, rdx
0x18002a606  mov     rbx, rcx
0x18002a609  mov     [rbp+57h+var_58], rcx
0x18002a60d  mov     [rbp+57h+var_70], 0
0x18002a614  mov     esi, 1
0x18002a619  mov     [rbp+57h+var_50], esi
0x18002a61c  mov     [rbp+57h+var_4C], 0Bh
0x18002a623  mov     [rbp+57h+var_48], 12h
0x18002a62a  movdqa  xmm0, cs:__xmm@00000006000000090000000400000003
0x18002a632  movdqu  [rbp+57h+var_40], xmm0
0x18002a637  mov     [rbp+57h+var_30], 8
0x18002a63e  mov     [rbp+57h+var_6C], 0Dh
0x18002a645  mov     [rbp+57h+var_78], 0Eh
0x18002a64c  mov     [rbp+57h+var_74], 0Fh
0x18002a653  mov     [rbp+57h+var_68], 6
0x18002a65a  mov     [rbp+57h+var_60], 7
0x18002a661  mov     [rbp+57h+var_5C], 10h
0x18002a668  mov     [rbp+57h+var_80], 0Ch
0x18002a66f  mov     [rbp+57h+var_7C], 11h
0x18002a676  mov     qword ptr [rcx], 0
0x18002a67d  mov     qword ptr [rcx+8], 0
0x18002a685  mov     qword ptr [rcx+10h], 0
0x18002a68d  mov     [rbp+57h+var_70], esi
0x18002a690  mov     ecx, [rdx+4]
0x18002a693  sub     ecx, esi
0x18002a695  jz      loc_18002A7A9
0x18002a69b  sub     ecx, esi
0x18002a69d  jz      loc_18002A770
0x18002a6a3  sub     ecx, esi
0x18002a6a5  jz      loc_18002A737
0x18002a6ab  sub     ecx, esi
0x18002a6ad  jz      short loc_18002A716
0x18002a6af  sub     ecx, esi
0x18002a6b1  jz      short loc_18002A6FF
0x18002a6b3  sub     ecx, esi
0x18002a6b5  jz      short loc_18002A6F3
0x18002a6b7  sub     ecx, esi
0x18002a6b9  jz      short loc_18002A6FF
0x18002a6bb  cmp     ecx, esi
0x18002a6bd  jnz     loc_18002A82D
0x18002a6c3  mov     r8d, 5
0x18002a6c9  lea     rdx, [rbp+57h+var_40]
0x18002a6cd  mov     r9, rdi
0x18002a6d0  mov     rcx, rbx
0x18002a6d3  call    AppendPermittedStates
0x18002a6d8  mov     r8, rsi
0x18002a6db  lea     rdx, [rbp+57h+var_80]
0x18002a6df  mov     r9, rdi
0x18002a6e2  mov     rcx, rbx
0x18002a6e5  call    AppendPermittedStates
0x18002a6ea  lea     rdx, [rbp+57h+var_7C]
0x18002a6ee  jmp     loc_18002A804
0x18002a6f3  mov     r8d, 3
0x18002a6f9  lea     rdx, [rbp+57h+var_50]
0x18002a6fd  jmp     short loc_18002A6CD
0x18002a6ff  mov     r9, rdi
0x18002a702  mov     r8d, 3
0x18002a708  lea     rdx, [rbp+57h+var_50]
0x18002a70c  mov     rcx, rbx
0x18002a70f  call    AppendPermittedStates
0x18002a714  jmp     short loc_18002A6C3
0x18002a716  mov     r9, rdi
0x18002a719  mov     r8d, 3
0x18002a71f  lea     rdx, [rbp+57h+var_50]
0x18002a723  mov     rcx, rbx
0x18002a726  call    AppendPermittedStates
0x18002a72b  mov     r8d, 2
0x18002a731  lea     rdx, [rbp+57h+var_60]
0x18002a735  jmp     short loc_18002A6DF
0x18002a737  mov     r9, rdi
0x18002a73a  mov     r8d, 3
0x18002a740  lea     rdx, [rbp+57h+var_50]
0x18002a744  mov     rcx, rbx
0x18002a747  call    AppendPermittedStates
0x18002a74c  mov     r9, rdi
0x18002a74f  mov     r8d, 5
0x18002a755  lea     rdx, [rbp+57h+var_40]
0x18002a759  mov     rcx, rbx
0x18002a75c  call    AppendPermittedStates
0x18002a761  mov     r8d, 2
0x18002a767  lea     rdx, [rbp+57h+var_78]
0x18002a76b  jmp     loc_18002A7F5
0x18002a770  mov     r9, rdi
0x18002a773  mov     r8d, 3
0x18002a779  lea     rdx, [rbp+57h+var_50]
0x18002a77d  mov     rcx, rbx
0x18002a780  call    AppendPermittedStates
0x18002a785  mov     r9, rdi
0x18002a788  mov     r8d, 5
0x18002a78e  lea     rdx, [rbp+57h+var_40]
0x18002a792  mov     rcx, rbx
0x18002a795  call    AppendPermittedStates
0x18002a79a  mov     r8d, 2
0x18002a7a0  lea     rdx, [rbp+57h+var_78]
0x18002a7a4  jmp     loc_18002A6CD
0x18002a7a9  mov     r9, rdi
0x18002a7ac  mov     r8d, 3
0x18002a7b2  lea     rdx, [rbp+57h+var_50]
0x18002a7b6  mov     rcx, rbx
0x18002a7b9  call    AppendPermittedStates
0x18002a7be  mov     r9, rdi
0x18002a7c1  mov     r8, rsi
0x18002a7c4  lea     rdx, [rbp+57h+var_6C]
0x18002a7c8  mov     rcx, rbx
0x18002a7cb  call    AppendPermittedStates
0x18002a7d0  mov     r9, rdi
0x18002a7d3  mov     r8d, 2
0x18002a7d9  lea     rdx, [rbp+57h+var_78]
0x18002a7dd  mov     rcx, rbx
0x18002a7e0  call    AppendPermittedStates
0x18002a7e5  call    IsUiccProvisioningEnabled
0x18002a7ea  test    al, al
0x18002a7ec  jnz     short loc_18002A800
0x18002a7ee  mov     r8, rsi
0x18002a7f1  lea     rdx, [rbp+57h+var_68]
0x18002a7f5  mov     r9, rdi
0x18002a7f8  mov     rcx, rbx
0x18002a7fb  call    AppendPermittedStates
0x18002a800  lea     rdx, [rbp+57h+var_80]
0x18002a804  mov     r9, rdi
0x18002a807  mov     r8, rsi
0x18002a80a  mov     rcx, rbx
0x18002a80d  call    AppendPermittedStates
0x18002a812  mov     rax, rbx
0x18002a815  mov     rcx, [rbp+57h+var_28]
0x18002a819  xor     rcx, rsp; StackCookie
0x18002a81c  call    __security_check_cookie
0x18002a821  add     rsp, 88h
0x18002a828  pop     rdi
0x18002a829  pop     rsi
0x18002a82a  pop     rbx
0x18002a82b  pop     rbp
0x18002a82c  retn
0x18002a82d  mov     ecx, 80070057h
0x18002a832  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002a837  mov     r9d, eax; char *
0x18002a83a  mov     rcx, [rbp+5Fh]; this
0x18002a83e  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002a845  mov     edx, 120h; void *
0x18002a84a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
