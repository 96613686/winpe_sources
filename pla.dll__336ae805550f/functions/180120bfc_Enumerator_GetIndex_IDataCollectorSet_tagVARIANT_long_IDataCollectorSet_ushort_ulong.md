# Enumerator::GetIndex<IDataCollectorSet>(tagVARIANT,long (IDataCollectorSet::*)(ushort * *),ulong *)

- ea: `0x180120bfc`
- end: `0x18012104e`
- name: `??$GetIndex@UIDataCollectorSet@@@Enumerator@@IEAAJUtagVARIANT@@P8IDataCollectorSet@@EAAJPEAPEAG@ZPEAK@Z`
- size: `1106`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180121054`
- `0x180121408`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x180120bfc`
- `0x1801218f8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180120fbd`
- `msvcrt!_wcsicmp` at `0x180120fbd`
- `OLEAUT32!__imp_VariantChangeType` at `0x180120e5b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180120e5b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180120d8a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180120d8a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180120ff6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180120ff6`

## pseudocode

```c
__int64 __fastcall Enumerator::GetIndex<IDataCollectorSet>(__int64 a1, VARIANTARG *a2, __int64 a3, unsigned int *a4)
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
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 7;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( (unsigned int)(v13 - 1) >= 2 )
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
        }
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
          if ( (**v24)(v24, &GUID_03837520_098b_11d8_9414_505054503030, &v30) >= 0 )
          {
            PlaiFreeString(String1);
            String1 = 0;
            v14 =  IDataCollectorSet::`vcall'{160,{flat}}(v30, &String1);
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
0x180120bfc  mov     [rsp-8+arg_10], rbx
0x180120c01  push    rbp
0x180120c02  push    rsi
0x180120c03  push    rdi
0x180120c04  push    r12
0x180120c06  push    r13
0x180120c08  push    r14
0x180120c0a  push    r15
0x180120c0c  lea     rbp, [rsp-130h]
0x180120c14  sub     rsp, 230h
0x180120c1b  mov     rax, cs:__security_cookie
0x180120c22  xor     rax, rsp
0x180120c25  mov     [rbp+160h+var_40], rax
0x180120c2c  xor     r12d, r12d
0x180120c2f  mov     rdi, rcx
0x180120c32  movzx   ecx, word ptr [rdx]
0x180120c35  mov     r13, r9
0x180120c38  mov     [rbp+160h+String1], r12
0x180120c3c  mov     r14, rdx
0x180120c3f  mov     [rbp+160h+ppvData], r12
0x180120c43  mov     [rbp+160h+var_1D0], r12
0x180120c47  lea     r15d, [r12+5]
0x180120c4c  sub     ecx, 2
0x180120c4f  jz      loc_180120D70
0x180120c55  sub     ecx, 1
0x180120c58  jz      loc_180120D70
0x180120c5e  sub     ecx, r15d
0x180120c61  jz      loc_180120D70
0x180120c67  sub     ecx, 1
0x180120c6a  jz      loc_180120D70
0x180120c70  sub     ecx, 7
0x180120c73  jz      loc_180120D70
0x180120c79  sub     ecx, 1
0x180120c7c  jz      loc_180120D70
0x180120c82  sub     ecx, 1
0x180120c85  jz      loc_180120D70
0x180120c8b  cmp     ecx, 1
0x180120c8e  jz      loc_180120D70
0x180120c94  cmp     dword ptr cs:xmmword_180169738, r12d
0x180120c9b  mov     ebx, 80070057h
0x180120ca0  mov     [rsp+260h+var_1E8], ebx
0x180120ca4  mov     [rsp+260h+var_1F0], r12d
0x180120ca9  jz      loc_180121000
0x180120caf  mov     rdx, 4000000000000800h; unsigned __int64
0x180120cb9  test    qword ptr cs:xmmword_180169738+8, rdx
0x180120cc0  jz      loc_180121000
0x180120cc6  mov     rax, cs:qword_180169748
0x180120ccd  and     rax, rdx
0x180120cd0  cmp     cs:qword_180169748, rax
0x180120cd7  jnz     loc_180121000
0x180120cdd  lea     rcx, [rbp+160h+var_1C0]; unsigned __int16 *
0x180120ce1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180120ce6  lea     rcx, [rbp+160h+var_1C0]
0x180120cea  or      rax, 0FFFFFFFFFFFFFFFFh
0x180120cee  inc     rax
0x180120cf1  cmp     [rcx+rax*2], r12w
0x180120cf6  jnz     short loc_180120CEE
0x180120cf8  lea     ecx, [rax+rax]
0x180120cfb  add     rcx, 2
0x180120cff  lea     rax, [rbp+160h+var_1C0]
0x180120d03  mov     [rsp+260h+var_200], rcx
0x180120d08  lea     r9, [rsp+260h+var_1E8]
0x180120d0d  lea     rcx, [rsp+260h+var_1F0]
0x180120d12  mov     [rsp+260h+var_208], rax
0x180120d17  lea     rdx, PLA_EVENT_ERROR
0x180120d1e  mov     [rsp+260h+var_210], 15h
0x180120d27  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180120d2e  mov     [rsp+260h+var_218], rax
0x180120d33  mov     r8d, r15d
0x180120d36  mov     eax, 4
0x180120d3b  mov     [rsp+260h+var_220], rax
0x180120d40  mov     [rsp+260h+var_228], rcx
0x180120d45  lea     rcx, byte_180147320
0x180120d4c  mov     [rsp+260h+var_230], 1
0x180120d55  mov     [rsp+260h+var_238], rcx
0x180120d5a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180120d61  mov     [rsp+260h+var_240], rax
0x180120d66  call    EventingWriteEvent
0x180120d6b  jmp     loc_180120FE7
0x180120d70  mov     rcx, [rdi+40h]; psa
0x180120d74  test    rcx, rcx
0x180120d77  jnz     short loc_180120D83
0x180120d79  mov     ebx, 80070490h
0x180120d7e  jmp     loc_180121000
0x180120d83  mov     esi, [rdi+4Ch]
0x180120d86  lea     rdx, [rbp+160h+ppvData]; ppvData
0x180120d8a  call    cs:__imp_SafeArrayAccessData
0x180120d90  mov     ebx, eax
0x180120d92  test    eax, eax
0x180120d94  jns     short loc_180120E14
0x180120d96  cmp     dword ptr cs:xmmword_180169738, r12d
0x180120d9d  mov     [rsp+260h+var_1E8], r12d
0x180120da2  mov     [rsp+260h+var_1F0], eax
0x180120da6  jz      loc_180120FE7
0x180120dac  mov     rdx, 4000000000000800h; unsigned __int64
0x180120db6  test    qword ptr cs:xmmword_180169738+8, rdx
0x180120dbd  jz      loc_180120FE7
0x180120dc3  mov     rax, cs:qword_180169748
0x180120dca  and     rax, rdx
0x180120dcd  cmp     cs:qword_180169748, rax
0x180120dd4  jnz     loc_180120FE7
0x180120dda  lea     rcx, [rbp+160h+var_140]; unsigned __int16 *
0x180120dde  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180120de3  lea     rcx, [rbp+160h+var_140]
0x180120de7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180120deb  inc     rax
0x180120dee  cmp     [rcx+rax*2], r12w
0x180120df3  jnz     short loc_180120DEB
0x180120df5  lea     ecx, [rax+rax]
0x180120df8  lea     rax, [rbp+160h+var_140]
0x180120dfc  add     rcx, 2
0x180120e00  lea     r9, [rsp+260h+var_1F0]
0x180120e05  mov     [rsp+260h+var_200], rcx
0x180120e0a  lea     rcx, [rsp+260h+var_1E8]
0x180120e0f  jmp     loc_180120D12
0x180120e14  movzx   ecx, word ptr [r14]
0x180120e18  sub     ecx, 2
0x180120e1b  jz      short loc_180120E4C
0x180120e1d  sub     ecx, 1
0x180120e20  jz      short loc_180120E4C
0x180120e22  sub     ecx, r15d
0x180120e25  jz      loc_180120F1E
0x180120e2b  sub     ecx, 1
0x180120e2e  jz      loc_180120EDF
0x180120e34  sub     ecx, 7
0x180120e37  jz      short loc_180120E4C
0x180120e39  sub     ecx, 1
0x180120e3c  jz      short loc_180120E4C
0x180120e3e  sub     ecx, 1
0x180120e41  jz      short loc_180120E4C
0x180120e43  cmp     ecx, 1
0x180120e46  jnz     loc_180120FD7
0x180120e4c  mov     r9d, 13h; vt
0x180120e52  xor     r8d, r8d; wFlags
0x180120e55  mov     rdx, r14; pvarSrc
0x180120e58  mov     rcx, r14; pvargDest
0x180120e5b  call    cs:__imp_VariantChangeType
0x180120e61  mov     ebx, eax
0x180120e63  test    eax, eax
0x180120e65  jns     loc_180120FD3
0x180120e6b  cmp     dword ptr cs:xmmword_180169738, r12d
0x180120e72  mov     [rsp+260h+var_1E8], r12d
0x180120e77  mov     [rsp+260h+var_1F0], eax
0x180120e7b  jz      loc_180120FE7
0x180120e81  mov     rdx, 4000000000000800h; unsigned __int64
0x180120e8b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180120e92  jz      loc_180120FE7
0x180120e98  mov     rax, cs:qword_180169748
0x180120e9f  and     rax, rdx
0x180120ea2  cmp     cs:qword_180169748, rax
0x180120ea9  jnz     loc_180120FE7
0x180120eaf  lea     rcx, [rbp+160h+var_C0]; unsigned __int16 *
0x180120eb6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180120ebb  lea     rcx, [rbp+160h+var_C0]
0x180120ec2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180120ec6  inc     rax
0x180120ec9  cmp     [rcx+rax*2], r12w
0x180120ece  jnz     short loc_180120EC6
0x180120ed0  lea     ecx, [rax+rax]
0x180120ed3  lea     rax, [rbp+160h+var_C0]
0x180120eda  jmp     loc_180120DFC
0x180120edf  mov     esi, r12d
0x180120ee2  cmp     [rdi+4Ch], r12d
0x180120ee6  jbe     loc_180120FD7
0x180120eec  mov     r15d, 9
0x180120ef2  mov     rcx, [rbp+160h+ppvData]
0x180120ef6  mov     eax, esi
0x180120ef8  lea     rax, [rax+rax*2]
0x180120efc  cmp     r15w, [rcx+rax*8]
0x180120f01  jnz     short loc_180120F12
0x180120f03  mov     rax, [rcx+rax*8+8]
0x180120f08  cmp     [r14+8], rax
0x180120f0c  jz      loc_180120FD7
0x180120f12  inc     esi
0x180120f14  cmp     esi, [rdi+4Ch]
0x180120f17  jb      short loc_180120EF2
0x180120f19  jmp     loc_180120FD7
0x180120f1e  mov     esi, r12d
0x180120f21  mov     r15d, 9
0x180120f27  cmp     esi, [rdi+4Ch]
0x180120f2a  jnb     loc_180120FDC
0x180120f30  mov     eax, esi
0x180120f32  lea     r12, [rax+rax*2]
0x180120f36  mov     rax, [rbp+160h+ppvData]
0x180120f3a  cmp     r15w, [rax+r12*8]
0x180120f3f  jnz     loc_180120FC9
0x180120f45  mov     rcx, [rbp+160h+var_1D0]
0x180120f49  test    rcx, rcx
0x180120f4c  jz      short loc_180120F62
0x180120f4e  mov     rax, [rcx]
0x180120f51  mov     rax, [rax+10h]
0x180120f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f5a  mov     [rbp+160h+var_1D0], 0
0x180120f62  mov     rax, [rbp+160h+ppvData]
0x180120f66  lea     r8, [rbp+160h+var_1D0]
0x180120f6a  lea     rdx, _GUID_03837520_098b_11d8_9414_505054503030
0x180120f71  mov     rcx, [rax+r12*8+8]
0x180120f76  mov     rax, [rcx]
0x180120f79  mov     rax, [rax]
0x180120f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f81  xor     r12d, r12d
0x180120f84  mov     ebx, eax
0x180120f86  test    eax, eax
0x180120f88  js      short loc_180120FCC
0x180120f8a  mov     rcx, [rbp+160h+String1]; bstrString
0x180120f8e  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180120f93  mov     rcx, [rbp+160h+var_1D0]
0x180120f97  lea     rdx, [rbp+160h+String1]
0x180120f9b  mov     [rbp+160h+String1], r12
0x180120f9f  call    ??_9IDataCollectorSet@@$BKA@AA; [thunk]: IDataCollectorSet::`vcall'{160,{flat}}
0x180120fa4  mov     ebx, eax
0x180120fa6  test    eax, eax
0x180120fa8  js      short loc_180120FCC
0x180120faa  mov     rcx, [rbp+160h+String1]; String1
0x180120fae  test    rcx, rcx
0x180120fb1  jz      short loc_180120FCC
0x180120fb3  cmp     r12w, [rcx]
0x180120fb7  jz      short loc_180120FCC
0x180120fb9  mov     rdx, [r14+8]; String2
0x180120fbd  call    cs:__imp__wcsicmp
0x180120fc3  test    eax, eax
0x180120fc5  jz      short loc_180120FD7
0x180120fc7  jmp     short loc_180120FCC
0x180120fc9  xor     r12d, r12d
0x180120fcc  inc     esi
0x180120fce  jmp     loc_180120F27
0x180120fd3  mov     esi, [r14+8]
0x180120fd7  cmp     esi, [rdi+4Ch]
0x180120fda  jb      short loc_180120FE3
0x180120fdc  mov     ebx, 80070490h
0x180120fe1  jmp     short loc_180120FE7
0x180120fe3  mov     [r13+0], esi
0x180120fe7  mov     ecx, 40h ; '@'
0x180120fec  cmp     [rbp+160h+ppvData], r12
0x180120ff0  jz      short loc_180121000
0x180120ff2  mov     rcx, [rcx+rdi]; psa
0x180120ff6  call    cs:__imp_SafeArrayUnaccessData
0x180120ffc  mov     [rbp+160h+ppvData], r12
0x180121000  mov     rcx, [rbp+160h+String1]; bstrString
0x180121004  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180121009  mov     rcx, [rbp+160h+var_1D0]
0x18012100d  mov     [rbp+160h+String1], r12
0x180121011  test    rcx, rcx
0x180121014  jz      short loc_180121022
0x180121016  mov     rax, [rcx]
0x180121019  mov     rax, [rax+10h]
0x18012101d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121022  mov     eax, ebx
0x180121024  mov     rcx, [rbp+160h+var_40]
0x18012102b  xor     rcx, rsp; StackCookie
0x18012102e  call    __security_check_cookie
0x180121033  mov     rbx, [rsp+260h+arg_10]
0x18012103b  add     rsp, 230h
0x180121042  pop     r15
0x180121044  pop     r14
0x180121046  pop     r13
0x180121048  pop     r12
0x18012104a  pop     rdi
0x18012104b  pop     rsi
0x18012104c  pop     rbp
0x18012104d  retn
```
