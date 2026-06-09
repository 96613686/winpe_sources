# Enumerator::GetIndex<ISchedule>(tagVARIANT,long (ISchedule::*)(ushort * *),ulong *)

- ea: `0x180122938`
- end: `0x180122d89`
- name: `??$GetIndex@UISchedule@@@Enumerator@@IEAAJUtagVARIANT@@P8ISchedule@@EAAJPEAPEAG@ZPEAK@Z`
- size: `1105`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ebb70`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x180122938`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180122cf8`
- `msvcrt!_wcsicmp` at `0x180122cf8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180122b93`
- `OLEAUT32!__imp_VariantChangeType` at `0x180122b93`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180122ac2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180122ac2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180122d31`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180122d31`

## pseudocode

```c
__int64 __fastcall Enumerator::GetIndex<ISchedule>(__int64 a1, VARIANTARG *a2, __int64 a3, unsigned int *a4)
{
  int vt; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ebx
  __int64 v15; // rax
  int *v16; // r9
  int *v17; // rcx
  SAFEARRAY *v18; // rcx
  unsigned int i; // esi
  HRESULT v20; // eax
  __int64 v21; // rax
  HRESULT v22; // eax
  __int64 v23; // rax
  int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rcx
  HRESULT v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v31[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v32[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v33[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  vt = a2->vt;
  String1 = 0;
  ppvData = 0;
  v30 = 0;
  v8 = vt - 2;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 5;
      if ( !v10 || (v11 = v10 - 1) != 0 && (v12 = v11 - 7) != 0 && (v13 = v12 - 1) != 0 && (unsigned int)(v13 - 1) >= 2 )
      {
        v14 = -2147024809;
        v27 = -2147024809;
        v26 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_60;
        }
        PlaiWhoAmI(v31, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v31[v15] );
        v16 = &v27;
        v17 = &v26;
        goto LABEL_14;
      }
    }
  }
  v18 = *(SAFEARRAY **)(a1 + 64);
  if ( !v18 )
  {
    v14 = -2147023728;
    goto LABEL_60;
  }
  i = *(_DWORD *)(a1 + 76);
  v20 = SafeArrayAccessData(v18, &ppvData);
  v14 = v20;
  if ( v20 < 0 )
  {
    v27 = 0;
    v26 = v20;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v32, 0x4000000000000800uLL);
      v21 = -1;
      do
        ++v21;
      while ( v32[v21] );
LABEL_23:
      v16 = &v26;
      v17 = &v27;
LABEL_14:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v16, 4, byte_180147320, 1, v17, 4);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  if ( a2->vt != 2 && a2->vt != 3 )
  {
    if ( a2->vt == 8 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 76); ++i )
      {
        if ( *((_WORD *)ppvData + 12 * i) == 9 )
        {
          if ( v30 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            v30 = 0;
          }
          v24 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)ppvData + 3 * i + 1);
          if ( (**v24)(v24, &GUID_0383753a_098b_11d8_9414_505054503030, &v30) >= 0 )
          {
            PlaiFreeString(String1);
            String1 = 0;
            v14 = MEMORY[0](v30, &String1);
            if ( v14 >= 0 && String1 && *String1 && !_wcsicmp(String1, a2->bstrVal) )
              goto LABEL_55;
          }
        }
      }
      goto LABEL_56;
    }
    if ( a2->vt == 9 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 76); ++i )
      {
        if ( *((_WORD *)ppvData + 12 * i) == 9 && a2->llVal == *((_QWORD *)ppvData + 3 * i + 1) )
          break;
      }
    }
    else if ( a2->vt == 16 || a2->vt == 17 || (unsigned int)a2->vt - 18 <= 1 )
    {
      goto LABEL_31;
    }
LABEL_55:
    if ( i < *(_DWORD *)(a1 + 76) )
    {
      *a4 = i;
      goto LABEL_58;
    }
LABEL_56:
    v14 = -2147023728;
    goto LABEL_58;
  }
LABEL_31:
  v22 = VariantChangeType(a2, a2, 0, 0x13u);
  v14 = v22;
  if ( v22 >= 0 )
  {
    i = a2->cyVal.Lo;
    goto LABEL_55;
  }
  v27 = 0;
  v26 = v22;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v33, 0x4000000000000800uLL);
    v23 = -1;
    do
      ++v23;
    while ( v33[v23] );
    goto LABEL_23;
  }
LABEL_58:
  if ( ppvData )
  {
    SafeArrayUnaccessData(*(SAFEARRAY **)(a1 + 64));
    ppvData = 0;
  }
LABEL_60:
  PlaiFreeString(String1);
  String1 = 0;
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180122938  mov     [rsp-8+arg_10], rbx
0x18012293d  push    rbp
0x18012293e  push    rsi
0x18012293f  push    rdi
0x180122940  push    r12
0x180122942  push    r13
0x180122944  push    r14
0x180122946  push    r15
0x180122948  lea     rbp, [rsp-130h]
0x180122950  sub     rsp, 230h
0x180122957  mov     rax, cs:__security_cookie
0x18012295e  xor     rax, rsp
0x180122961  mov     [rbp+160h+var_40], rax
0x180122968  xor     r12d, r12d
0x18012296b  mov     rdi, rcx
0x18012296e  movzx   ecx, word ptr [rdx]
0x180122971  mov     r13, r9
0x180122974  mov     [rbp+160h+String1], r12
0x180122978  mov     r14, rdx
0x18012297b  mov     [rbp+160h+ppvData], r12
0x18012297f  mov     [rbp+160h+var_1D0], r12
0x180122983  lea     r15d, [r12+5]
0x180122988  sub     ecx, 2
0x18012298b  jz      loc_180122AA8
0x180122991  sub     ecx, 1
0x180122994  jz      loc_180122AA8
0x18012299a  sub     ecx, r15d
0x18012299d  jz      short loc_1801229CC
0x18012299f  sub     ecx, 1
0x1801229a2  jz      loc_180122AA8
0x1801229a8  sub     ecx, 7
0x1801229ab  jz      loc_180122AA8
0x1801229b1  sub     ecx, 1
0x1801229b4  jz      loc_180122AA8
0x1801229ba  sub     ecx, 1
0x1801229bd  jz      loc_180122AA8
0x1801229c3  cmp     ecx, 1
0x1801229c6  jz      loc_180122AA8
0x1801229cc  cmp     dword ptr cs:xmmword_180169738, r12d
0x1801229d3  mov     ebx, 80070057h
0x1801229d8  mov     [rsp+260h+var_1E8], ebx
0x1801229dc  mov     [rsp+260h+var_1F0], r12d
0x1801229e1  jz      loc_180122D3B
0x1801229e7  mov     rdx, 4000000000000800h; unsigned __int64
0x1801229f1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801229f8  jz      loc_180122D3B
0x1801229fe  mov     rax, cs:qword_180169748
0x180122a05  and     rax, rdx
0x180122a08  cmp     cs:qword_180169748, rax
0x180122a0f  jnz     loc_180122D3B
0x180122a15  lea     rcx, [rbp+160h+var_1C0]; unsigned __int16 *
0x180122a19  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180122a1e  lea     rcx, [rbp+160h+var_1C0]
0x180122a22  or      rax, 0FFFFFFFFFFFFFFFFh
0x180122a26  inc     rax
0x180122a29  cmp     [rcx+rax*2], r12w
0x180122a2e  jnz     short loc_180122A26
0x180122a30  lea     ecx, [rax+rax]
0x180122a33  add     rcx, 2
0x180122a37  lea     rax, [rbp+160h+var_1C0]
0x180122a3b  mov     [rsp+260h+var_200], rcx
0x180122a40  lea     r9, [rsp+260h+var_1E8]
0x180122a45  lea     rcx, [rsp+260h+var_1F0]
0x180122a4a  mov     [rsp+260h+var_208], rax
0x180122a4f  lea     rdx, PLA_EVENT_ERROR
0x180122a56  mov     [rsp+260h+var_210], 15h
0x180122a5f  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180122a66  mov     [rsp+260h+var_218], rax
0x180122a6b  mov     r8d, r15d
0x180122a6e  mov     eax, 4
0x180122a73  mov     [rsp+260h+var_220], rax
0x180122a78  mov     [rsp+260h+var_228], rcx
0x180122a7d  lea     rcx, byte_180147320
0x180122a84  mov     [rsp+260h+var_230], 1
0x180122a8d  mov     [rsp+260h+var_238], rcx
0x180122a92  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180122a99  mov     [rsp+260h+var_240], rax
0x180122a9e  call    EventingWriteEvent
0x180122aa3  jmp     loc_180122D22
0x180122aa8  mov     rcx, [rdi+40h]; psa
0x180122aac  test    rcx, rcx
0x180122aaf  jnz     short loc_180122ABB
0x180122ab1  mov     ebx, 80070490h
0x180122ab6  jmp     loc_180122D3B
0x180122abb  mov     esi, [rdi+4Ch]
0x180122abe  lea     rdx, [rbp+160h+ppvData]; ppvData
0x180122ac2  call    cs:__imp_SafeArrayAccessData
0x180122ac8  mov     ebx, eax
0x180122aca  test    eax, eax
0x180122acc  jns     short loc_180122B4C
0x180122ace  cmp     dword ptr cs:xmmword_180169738, r12d
0x180122ad5  mov     [rsp+260h+var_1E8], r12d
0x180122ada  mov     [rsp+260h+var_1F0], eax
0x180122ade  jz      loc_180122D22
0x180122ae4  mov     rdx, 4000000000000800h; unsigned __int64
0x180122aee  test    qword ptr cs:xmmword_180169738+8, rdx
0x180122af5  jz      loc_180122D22
0x180122afb  mov     rax, cs:qword_180169748
0x180122b02  and     rax, rdx
0x180122b05  cmp     cs:qword_180169748, rax
0x180122b0c  jnz     loc_180122D22
0x180122b12  lea     rcx, [rbp+160h+var_140]; unsigned __int16 *
0x180122b16  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180122b1b  lea     rcx, [rbp+160h+var_140]
0x180122b1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180122b23  inc     rax
0x180122b26  cmp     [rcx+rax*2], r12w
0x180122b2b  jnz     short loc_180122B23
0x180122b2d  lea     ecx, [rax+rax]
0x180122b30  lea     rax, [rbp+160h+var_140]
0x180122b34  add     rcx, 2
0x180122b38  lea     r9, [rsp+260h+var_1F0]
0x180122b3d  mov     [rsp+260h+var_200], rcx
0x180122b42  lea     rcx, [rsp+260h+var_1E8]
0x180122b47  jmp     loc_180122A4A
0x180122b4c  movzx   ecx, word ptr [r14]
0x180122b50  sub     ecx, 2
0x180122b53  jz      short loc_180122B84
0x180122b55  sub     ecx, 1
0x180122b58  jz      short loc_180122B84
0x180122b5a  sub     ecx, r15d
0x180122b5d  jz      loc_180122C56
0x180122b63  sub     ecx, 1
0x180122b66  jz      loc_180122C17
0x180122b6c  sub     ecx, 7
0x180122b6f  jz      short loc_180122B84
0x180122b71  sub     ecx, 1
0x180122b74  jz      short loc_180122B84
0x180122b76  sub     ecx, 1
0x180122b79  jz      short loc_180122B84
0x180122b7b  cmp     ecx, 1
0x180122b7e  jnz     loc_180122D12
0x180122b84  mov     r9d, 13h; vt
0x180122b8a  xor     r8d, r8d; wFlags
0x180122b8d  mov     rdx, r14; pvarSrc
0x180122b90  mov     rcx, r14; pvargDest
0x180122b93  call    cs:__imp_VariantChangeType
0x180122b99  mov     ebx, eax
0x180122b9b  test    eax, eax
0x180122b9d  jns     loc_180122D0E
0x180122ba3  cmp     dword ptr cs:xmmword_180169738, r12d
0x180122baa  mov     [rsp+260h+var_1E8], r12d
0x180122baf  mov     [rsp+260h+var_1F0], eax
0x180122bb3  jz      loc_180122D22
0x180122bb9  mov     rdx, 4000000000000800h; unsigned __int64
0x180122bc3  test    qword ptr cs:xmmword_180169738+8, rdx
0x180122bca  jz      loc_180122D22
0x180122bd0  mov     rax, cs:qword_180169748
0x180122bd7  and     rax, rdx
0x180122bda  cmp     cs:qword_180169748, rax
0x180122be1  jnz     loc_180122D22
0x180122be7  lea     rcx, [rbp+160h+var_C0]; unsigned __int16 *
0x180122bee  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180122bf3  lea     rcx, [rbp+160h+var_C0]
0x180122bfa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180122bfe  inc     rax
0x180122c01  cmp     [rcx+rax*2], r12w
0x180122c06  jnz     short loc_180122BFE
0x180122c08  lea     ecx, [rax+rax]
0x180122c0b  lea     rax, [rbp+160h+var_C0]
0x180122c12  jmp     loc_180122B34
0x180122c17  mov     esi, r12d
0x180122c1a  cmp     [rdi+4Ch], r12d
0x180122c1e  jbe     loc_180122D12
0x180122c24  mov     r15d, 9
0x180122c2a  mov     rcx, [rbp+160h+ppvData]
0x180122c2e  mov     eax, esi
0x180122c30  lea     rax, [rax+rax*2]
0x180122c34  cmp     r15w, [rcx+rax*8]
0x180122c39  jnz     short loc_180122C4A
0x180122c3b  mov     rax, [rcx+rax*8+8]
0x180122c40  cmp     [r14+8], rax
0x180122c44  jz      loc_180122D12
0x180122c4a  inc     esi
0x180122c4c  cmp     esi, [rdi+4Ch]
0x180122c4f  jb      short loc_180122C2A
0x180122c51  jmp     loc_180122D12
0x180122c56  mov     esi, r12d
0x180122c59  mov     r15d, 9
0x180122c5f  cmp     esi, [rdi+4Ch]
0x180122c62  jnb     loc_180122D17
0x180122c68  mov     eax, esi
0x180122c6a  lea     r12, [rax+rax*2]
0x180122c6e  mov     rax, [rbp+160h+ppvData]
0x180122c72  cmp     r15w, [rax+r12*8]
0x180122c77  jnz     loc_180122D04
0x180122c7d  mov     rcx, [rbp+160h+var_1D0]
0x180122c81  test    rcx, rcx
0x180122c84  jz      short loc_180122C9A
0x180122c86  mov     rax, [rcx]
0x180122c89  mov     rax, [rax+10h]
0x180122c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122c92  mov     [rbp+160h+var_1D0], 0
0x180122c9a  mov     rax, [rbp+160h+ppvData]
0x180122c9e  lea     r8, [rbp+160h+var_1D0]
0x180122ca2  lea     rdx, _GUID_0383753a_098b_11d8_9414_505054503030
0x180122ca9  mov     rcx, [rax+r12*8+8]
0x180122cae  mov     rax, [rcx]
0x180122cb1  mov     rax, [rax]
0x180122cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122cb9  xor     r12d, r12d
0x180122cbc  mov     ebx, eax
0x180122cbe  test    eax, eax
0x180122cc0  js      short loc_180122D07
0x180122cc2  mov     rcx, [rbp+160h+String1]; bstrString
0x180122cc6  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180122ccb  mov     rcx, [rbp+160h+var_1D0]
0x180122ccf  lea     rdx, [rbp+160h+String1]
0x180122cd3  mov     eax, r12d
0x180122cd6  mov     [rbp+160h+String1], r12
0x180122cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122cdf  mov     ebx, eax
0x180122ce1  test    eax, eax
0x180122ce3  js      short loc_180122D07
0x180122ce5  mov     rcx, [rbp+160h+String1]; String1
0x180122ce9  test    rcx, rcx
0x180122cec  jz      short loc_180122D07
0x180122cee  cmp     r12w, [rcx]
0x180122cf2  jz      short loc_180122D07
0x180122cf4  mov     rdx, [r14+8]; String2
0x180122cf8  call    cs:__imp__wcsicmp
0x180122cfe  test    eax, eax
0x180122d00  jz      short loc_180122D12
0x180122d02  jmp     short loc_180122D07
0x180122d04  xor     r12d, r12d
0x180122d07  inc     esi
0x180122d09  jmp     loc_180122C5F
0x180122d0e  mov     esi, [r14+8]
0x180122d12  cmp     esi, [rdi+4Ch]
0x180122d15  jb      short loc_180122D1E
0x180122d17  mov     ebx, 80070490h
0x180122d1c  jmp     short loc_180122D22
0x180122d1e  mov     [r13+0], esi
0x180122d22  mov     ecx, 40h ; '@'
0x180122d27  cmp     [rbp+160h+ppvData], r12
0x180122d2b  jz      short loc_180122D3B
0x180122d2d  mov     rcx, [rcx+rdi]; psa
0x180122d31  call    cs:__imp_SafeArrayUnaccessData
0x180122d37  mov     [rbp+160h+ppvData], r12
0x180122d3b  mov     rcx, [rbp+160h+String1]; bstrString
0x180122d3f  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180122d44  mov     rcx, [rbp+160h+var_1D0]
0x180122d48  mov     [rbp+160h+String1], r12
0x180122d4c  test    rcx, rcx
0x180122d4f  jz      short loc_180122D5D
0x180122d51  mov     rax, [rcx]
0x180122d54  mov     rax, [rax+10h]
0x180122d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122d5d  mov     eax, ebx
0x180122d5f  mov     rcx, [rbp+160h+var_40]
0x180122d66  xor     rcx, rsp; StackCookie
0x180122d69  call    __security_check_cookie
0x180122d6e  mov     rbx, [rsp+260h+arg_10]
0x180122d76  add     rsp, 230h
0x180122d7d  pop     r15
0x180122d7f  pop     r14
0x180122d81  pop     r13
0x180122d83  pop     r12
0x180122d85  pop     rdi
0x180122d86  pop     rsi
0x180122d87  pop     rbp
0x180122d88  retn
```
