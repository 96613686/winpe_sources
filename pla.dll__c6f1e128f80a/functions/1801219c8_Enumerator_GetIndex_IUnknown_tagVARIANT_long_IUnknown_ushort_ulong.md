# Enumerator::GetIndex<IUnknown>(tagVARIANT,long (IUnknown::*)(ushort * *),ulong *)

- ea: `0x1801219c8`
- end: `0x180121e19`
- name: `??$GetIndex@UIUnknown@@@Enumerator@@IEAAJUtagVARIANT@@P8IUnknown@@EAAJPEAPEAG@ZPEAK@Z`
- size: `1105`
- prototype: `__int64 __fastcall(__int64, VARIANTARG *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180121e20`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x1801219c8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180121d88`
- `msvcrt!_wcsicmp` at `0x180121d88`
- `OLEAUT32!__imp_VariantChangeType` at `0x180121c23`
- `OLEAUT32!__imp_VariantChangeType` at `0x180121c23`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180121b52`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180121b52`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180121dc1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180121dc1`

## pseudocode

```c
__int64 __fastcall Enumerator::GetIndex<IUnknown>(__int64 a1, VARIANTARG *a2, __int64 a3, unsigned int *a4)
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
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        v16,
        4,
        qword_180147320,
        1,
        v17,
        4,
        "Enumerator::GetIndex",
        21);
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
          if ( (**v24)(v24, &GUID_00000000_0000_0000_c000_000000000046, &v30) >= 0 )
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
0x1801219c8  mov     [rsp-8+arg_10], rbx
0x1801219cd  push    rbp
0x1801219ce  push    rsi
0x1801219cf  push    rdi
0x1801219d0  push    r12
0x1801219d2  push    r13
0x1801219d4  push    r14
0x1801219d6  push    r15
0x1801219d8  lea     rbp, [rsp-130h]
0x1801219e0  sub     rsp, 230h
0x1801219e7  mov     rax, cs:__security_cookie
0x1801219ee  xor     rax, rsp
0x1801219f1  mov     [rbp+160h+var_40], rax
0x1801219f8  xor     r12d, r12d
0x1801219fb  mov     rdi, rcx
0x1801219fe  movzx   ecx, word ptr [rdx]
0x180121a01  mov     r13, r9
0x180121a04  mov     [rbp+160h+String1], r12
0x180121a08  mov     r14, rdx
0x180121a0b  mov     [rbp+160h+ppvData], r12
0x180121a0f  mov     [rbp+160h+var_1D0], r12
0x180121a13  lea     r15d, [r12+5]
0x180121a18  sub     ecx, 2
0x180121a1b  jz      loc_180121B38
0x180121a21  sub     ecx, 1
0x180121a24  jz      loc_180121B38
0x180121a2a  sub     ecx, r15d
0x180121a2d  jz      short loc_180121A5C
0x180121a2f  sub     ecx, 1
0x180121a32  jz      loc_180121B38
0x180121a38  sub     ecx, 7
0x180121a3b  jz      loc_180121B38
0x180121a41  sub     ecx, 1
0x180121a44  jz      loc_180121B38
0x180121a4a  sub     ecx, 1
0x180121a4d  jz      loc_180121B38
0x180121a53  cmp     ecx, 1
0x180121a56  jz      loc_180121B38
0x180121a5c  cmp     dword ptr cs:xmmword_180169738, r12d
0x180121a63  mov     ebx, 80070057h
0x180121a68  mov     [rsp+260h+var_1E8], ebx
0x180121a6c  mov     [rsp+260h+var_1F0], r12d
0x180121a71  jz      loc_180121DCB
0x180121a77  mov     rdx, 4000000000000800h; unsigned __int64
0x180121a81  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121a88  jz      loc_180121DCB
0x180121a8e  mov     rax, cs:qword_180169748
0x180121a95  and     rax, rdx
0x180121a98  cmp     cs:qword_180169748, rax
0x180121a9f  jnz     loc_180121DCB
0x180121aa5  lea     rcx, [rbp+160h+var_1C0]; unsigned __int16 *
0x180121aa9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180121aae  lea     rcx, [rbp+160h+var_1C0]
0x180121ab2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180121ab6  inc     rax
0x180121ab9  cmp     [rcx+rax*2], r12w
0x180121abe  jnz     short loc_180121AB6
0x180121ac0  lea     ecx, [rax+rax]
0x180121ac3  add     rcx, 2
0x180121ac7  lea     rax, [rbp+160h+var_1C0]
0x180121acb  mov     [rsp+260h+var_200], rcx
0x180121ad0  lea     r9, [rsp+260h+var_1E8]
0x180121ad5  lea     rcx, [rsp+260h+var_1F0]
0x180121ada  mov     [rsp+260h+var_208], rax
0x180121adf  lea     rdx, PLA_EVENT_ERROR
0x180121ae6  mov     [rsp+260h+var_210], 15h
0x180121aef  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180121af6  mov     [rsp+260h+var_218], rax
0x180121afb  mov     r8d, r15d
0x180121afe  mov     eax, 4
0x180121b03  mov     [rsp+260h+var_220], rax
0x180121b08  mov     [rsp+260h+var_228], rcx
0x180121b0d  lea     rcx, qword_180147320
0x180121b14  mov     [rsp+260h+var_230], 1
0x180121b1d  mov     [rsp+260h+var_238], rcx
0x180121b22  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180121b29  mov     [rsp+260h+var_240], rax
0x180121b2e  call    EventingWriteEvent
0x180121b33  jmp     loc_180121DB2
0x180121b38  mov     rcx, [rdi+40h]; psa
0x180121b3c  test    rcx, rcx
0x180121b3f  jnz     short loc_180121B4B
0x180121b41  mov     ebx, 80070490h
0x180121b46  jmp     loc_180121DCB
0x180121b4b  mov     esi, [rdi+4Ch]
0x180121b4e  lea     rdx, [rbp+160h+ppvData]; ppvData
0x180121b52  call    cs:__imp_SafeArrayAccessData
0x180121b58  mov     ebx, eax
0x180121b5a  test    eax, eax
0x180121b5c  jns     short loc_180121BDC
0x180121b5e  cmp     dword ptr cs:xmmword_180169738, r12d
0x180121b65  mov     [rsp+260h+var_1E8], r12d
0x180121b6a  mov     [rsp+260h+var_1F0], eax
0x180121b6e  jz      loc_180121DB2
0x180121b74  mov     rdx, 4000000000000800h; unsigned __int64
0x180121b7e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121b85  jz      loc_180121DB2
0x180121b8b  mov     rax, cs:qword_180169748
0x180121b92  and     rax, rdx
0x180121b95  cmp     cs:qword_180169748, rax
0x180121b9c  jnz     loc_180121DB2
0x180121ba2  lea     rcx, [rbp+160h+var_140]; unsigned __int16 *
0x180121ba6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180121bab  lea     rcx, [rbp+160h+var_140]
0x180121baf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180121bb3  inc     rax
0x180121bb6  cmp     [rcx+rax*2], r12w
0x180121bbb  jnz     short loc_180121BB3
0x180121bbd  lea     ecx, [rax+rax]
0x180121bc0  lea     rax, [rbp+160h+var_140]
0x180121bc4  add     rcx, 2
0x180121bc8  lea     r9, [rsp+260h+var_1F0]
0x180121bcd  mov     [rsp+260h+var_200], rcx
0x180121bd2  lea     rcx, [rsp+260h+var_1E8]
0x180121bd7  jmp     loc_180121ADA
0x180121bdc  movzx   ecx, word ptr [r14]
0x180121be0  sub     ecx, 2
0x180121be3  jz      short loc_180121C14
0x180121be5  sub     ecx, 1
0x180121be8  jz      short loc_180121C14
0x180121bea  sub     ecx, r15d
0x180121bed  jz      loc_180121CE6
0x180121bf3  sub     ecx, 1
0x180121bf6  jz      loc_180121CA7
0x180121bfc  sub     ecx, 7
0x180121bff  jz      short loc_180121C14
0x180121c01  sub     ecx, 1
0x180121c04  jz      short loc_180121C14
0x180121c06  sub     ecx, 1
0x180121c09  jz      short loc_180121C14
0x180121c0b  cmp     ecx, 1
0x180121c0e  jnz     loc_180121DA2
0x180121c14  mov     r9d, 13h; vt
0x180121c1a  xor     r8d, r8d; wFlags
0x180121c1d  mov     rdx, r14; pvarSrc
0x180121c20  mov     rcx, r14; pvargDest
0x180121c23  call    cs:__imp_VariantChangeType
0x180121c29  mov     ebx, eax
0x180121c2b  test    eax, eax
0x180121c2d  jns     loc_180121D9E
0x180121c33  cmp     dword ptr cs:xmmword_180169738, r12d
0x180121c3a  mov     [rsp+260h+var_1E8], r12d
0x180121c3f  mov     [rsp+260h+var_1F0], eax
0x180121c43  jz      loc_180121DB2
0x180121c49  mov     rdx, 4000000000000800h; unsigned __int64
0x180121c53  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121c5a  jz      loc_180121DB2
0x180121c60  mov     rax, cs:qword_180169748
0x180121c67  and     rax, rdx
0x180121c6a  cmp     cs:qword_180169748, rax
0x180121c71  jnz     loc_180121DB2
0x180121c77  lea     rcx, [rbp+160h+var_C0]; unsigned __int16 *
0x180121c7e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180121c83  lea     rcx, [rbp+160h+var_C0]
0x180121c8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180121c8e  inc     rax
0x180121c91  cmp     [rcx+rax*2], r12w
0x180121c96  jnz     short loc_180121C8E
0x180121c98  lea     ecx, [rax+rax]
0x180121c9b  lea     rax, [rbp+160h+var_C0]
0x180121ca2  jmp     loc_180121BC4
0x180121ca7  mov     esi, r12d
0x180121caa  cmp     [rdi+4Ch], r12d
0x180121cae  jbe     loc_180121DA2
0x180121cb4  mov     r15d, 9
0x180121cba  mov     rcx, [rbp+160h+ppvData]
0x180121cbe  mov     eax, esi
0x180121cc0  lea     rax, [rax+rax*2]
0x180121cc4  cmp     r15w, [rcx+rax*8]
0x180121cc9  jnz     short loc_180121CDA
0x180121ccb  mov     rax, [rcx+rax*8+8]
0x180121cd0  cmp     [r14+8], rax
0x180121cd4  jz      loc_180121DA2
0x180121cda  inc     esi
0x180121cdc  cmp     esi, [rdi+4Ch]
0x180121cdf  jb      short loc_180121CBA
0x180121ce1  jmp     loc_180121DA2
0x180121ce6  mov     esi, r12d
0x180121ce9  mov     r15d, 9
0x180121cef  cmp     esi, [rdi+4Ch]
0x180121cf2  jnb     loc_180121DA7
0x180121cf8  mov     eax, esi
0x180121cfa  lea     r12, [rax+rax*2]
0x180121cfe  mov     rax, [rbp+160h+ppvData]
0x180121d02  cmp     r15w, [rax+r12*8]
0x180121d07  jnz     loc_180121D94
0x180121d0d  mov     rcx, [rbp+160h+var_1D0]
0x180121d11  test    rcx, rcx
0x180121d14  jz      short loc_180121D2A
0x180121d16  mov     rax, [rcx]
0x180121d19  mov     rax, [rax+10h]
0x180121d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121d22  mov     [rbp+160h+var_1D0], 0
0x180121d2a  mov     rax, [rbp+160h+ppvData]
0x180121d2e  lea     r8, [rbp+160h+var_1D0]
0x180121d32  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180121d39  mov     rcx, [rax+r12*8+8]
0x180121d3e  mov     rax, [rcx]
0x180121d41  mov     rax, [rax]
0x180121d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121d49  xor     r12d, r12d
0x180121d4c  mov     ebx, eax
0x180121d4e  test    eax, eax
0x180121d50  js      short loc_180121D97
0x180121d52  mov     rcx, [rbp+160h+String1]; bstrString
0x180121d56  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180121d5b  mov     rcx, [rbp+160h+var_1D0]
0x180121d5f  lea     rdx, [rbp+160h+String1]
0x180121d63  mov     eax, r12d
0x180121d66  mov     [rbp+160h+String1], r12
0x180121d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121d6f  mov     ebx, eax
0x180121d71  test    eax, eax
0x180121d73  js      short loc_180121D97
0x180121d75  mov     rcx, [rbp+160h+String1]; String1
0x180121d79  test    rcx, rcx
0x180121d7c  jz      short loc_180121D97
0x180121d7e  cmp     r12w, [rcx]
0x180121d82  jz      short loc_180121D97
0x180121d84  mov     rdx, [r14+8]; String2
0x180121d88  call    cs:__imp__wcsicmp
0x180121d8e  test    eax, eax
0x180121d90  jz      short loc_180121DA2
0x180121d92  jmp     short loc_180121D97
0x180121d94  xor     r12d, r12d
0x180121d97  inc     esi
0x180121d99  jmp     loc_180121CEF
0x180121d9e  mov     esi, [r14+8]
0x180121da2  cmp     esi, [rdi+4Ch]
0x180121da5  jb      short loc_180121DAE
0x180121da7  mov     ebx, 80070490h
0x180121dac  jmp     short loc_180121DB2
0x180121dae  mov     [r13+0], esi
0x180121db2  mov     ecx, 40h ; '@'
0x180121db7  cmp     [rbp+160h+ppvData], r12
0x180121dbb  jz      short loc_180121DCB
0x180121dbd  mov     rcx, [rcx+rdi]; psa
0x180121dc1  call    cs:__imp_SafeArrayUnaccessData
0x180121dc7  mov     [rbp+160h+ppvData], r12
0x180121dcb  mov     rcx, [rbp+160h+String1]; bstrString
0x180121dcf  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180121dd4  mov     rcx, [rbp+160h+var_1D0]
0x180121dd8  mov     [rbp+160h+String1], r12
0x180121ddc  test    rcx, rcx
0x180121ddf  jz      short loc_180121DED
0x180121de1  mov     rax, [rcx]
0x180121de4  mov     rax, [rax+10h]
0x180121de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121ded  mov     eax, ebx
0x180121def  mov     rcx, [rbp+160h+var_40]
0x180121df6  xor     rcx, rsp; StackCookie
0x180121df9  call    __security_check_cookie
0x180121dfe  mov     rbx, [rsp+260h+arg_10]
0x180121e06  add     rsp, 230h
0x180121e0d  pop     r15
0x180121e0f  pop     r14
0x180121e11  pop     r13
0x180121e13  pop     r12
0x180121e15  pop     rdi
0x180121e16  pop     rsi
0x180121e17  pop     rbp
0x180121e18  retn
```
