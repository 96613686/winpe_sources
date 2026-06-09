# Enumerator::GetIndex<IFolderAction>(tagVARIANT,long (IFolderAction::*)(ushort * *),ulong *)

- ea: `0x1801237d8`
- end: `0x180123c29`
- name: `??$GetIndex@UIFolderAction@@@Enumerator@@IEAAJUtagVARIANT@@P8IFolderAction@@EAAJPEAPEAG@ZPEAK@Z`
- size: `1105`
- prototype: `__int64 __fastcall(__int64, VARIANTARG *, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180067960`
- `0x180123c30`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x1801237d8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180123b98`
- `msvcrt!_wcsicmp` at `0x180123b98`
- `OLEAUT32!__imp_VariantChangeType` at `0x180123a33`
- `OLEAUT32!__imp_VariantChangeType` at `0x180123a33`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180123962`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180123962`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180123bd1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180123bd1`

## pseudocode

```c
__int64 __fastcall Enumerator::GetIndex<IFolderAction>(__int64 a1, VARIANTARG *a2, __int64 a3, unsigned int *a4)
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
          if ( (**v24)(v24, &GUID_03837543_098b_11d8_9414_505054503030, &v30) >= 0 )
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
0x1801237d8  mov     [rsp-8+arg_10], rbx
0x1801237dd  push    rbp
0x1801237de  push    rsi
0x1801237df  push    rdi
0x1801237e0  push    r12
0x1801237e2  push    r13
0x1801237e4  push    r14
0x1801237e6  push    r15
0x1801237e8  lea     rbp, [rsp-130h]
0x1801237f0  sub     rsp, 230h
0x1801237f7  mov     rax, cs:__security_cookie
0x1801237fe  xor     rax, rsp
0x180123801  mov     [rbp+160h+var_40], rax
0x180123808  xor     r12d, r12d
0x18012380b  mov     rdi, rcx
0x18012380e  movzx   ecx, word ptr [rdx]
0x180123811  mov     r13, r9
0x180123814  mov     [rbp+160h+String1], r12
0x180123818  mov     r14, rdx
0x18012381b  mov     [rbp+160h+ppvData], r12
0x18012381f  mov     [rbp+160h+var_1D0], r12
0x180123823  lea     r15d, [r12+5]
0x180123828  sub     ecx, 2
0x18012382b  jz      loc_180123948
0x180123831  sub     ecx, 1
0x180123834  jz      loc_180123948
0x18012383a  sub     ecx, r15d
0x18012383d  jz      short loc_18012386C
0x18012383f  sub     ecx, 1
0x180123842  jz      loc_180123948
0x180123848  sub     ecx, 7
0x18012384b  jz      loc_180123948
0x180123851  sub     ecx, 1
0x180123854  jz      loc_180123948
0x18012385a  sub     ecx, 1
0x18012385d  jz      loc_180123948
0x180123863  cmp     ecx, 1
0x180123866  jz      loc_180123948
0x18012386c  cmp     dword ptr cs:xmmword_180169738, r12d
0x180123873  mov     ebx, 80070057h
0x180123878  mov     [rsp+260h+var_1E8], ebx
0x18012387c  mov     [rsp+260h+var_1F0], r12d
0x180123881  jz      loc_180123BDB
0x180123887  mov     rdx, 4000000000000800h; unsigned __int64
0x180123891  test    qword ptr cs:xmmword_180169738+8, rdx
0x180123898  jz      loc_180123BDB
0x18012389e  mov     rax, cs:qword_180169748
0x1801238a5  and     rax, rdx
0x1801238a8  cmp     cs:qword_180169748, rax
0x1801238af  jnz     loc_180123BDB
0x1801238b5  lea     rcx, [rbp+160h+var_1C0]; unsigned __int16 *
0x1801238b9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801238be  lea     rcx, [rbp+160h+var_1C0]
0x1801238c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801238c6  inc     rax
0x1801238c9  cmp     [rcx+rax*2], r12w
0x1801238ce  jnz     short loc_1801238C6
0x1801238d0  lea     ecx, [rax+rax]
0x1801238d3  add     rcx, 2
0x1801238d7  lea     rax, [rbp+160h+var_1C0]
0x1801238db  mov     [rsp+260h+var_200], rcx
0x1801238e0  lea     r9, [rsp+260h+var_1E8]
0x1801238e5  lea     rcx, [rsp+260h+var_1F0]
0x1801238ea  mov     [rsp+260h+var_208], rax
0x1801238ef  lea     rdx, PLA_EVENT_ERROR
0x1801238f6  mov     [rsp+260h+var_210], 15h
0x1801238ff  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180123906  mov     [rsp+260h+var_218], rax
0x18012390b  mov     r8d, r15d
0x18012390e  mov     eax, 4
0x180123913  mov     [rsp+260h+var_220], rax
0x180123918  mov     [rsp+260h+var_228], rcx
0x18012391d  lea     rcx, qword_180147320
0x180123924  mov     [rsp+260h+var_230], 1
0x18012392d  mov     [rsp+260h+var_238], rcx
0x180123932  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180123939  mov     [rsp+260h+var_240], rax
0x18012393e  call    EventingWriteEvent
0x180123943  jmp     loc_180123BC2
0x180123948  mov     rcx, [rdi+40h]; psa
0x18012394c  test    rcx, rcx
0x18012394f  jnz     short loc_18012395B
0x180123951  mov     ebx, 80070490h
0x180123956  jmp     loc_180123BDB
0x18012395b  mov     esi, [rdi+4Ch]
0x18012395e  lea     rdx, [rbp+160h+ppvData]; ppvData
0x180123962  call    cs:__imp_SafeArrayAccessData
0x180123968  mov     ebx, eax
0x18012396a  test    eax, eax
0x18012396c  jns     short loc_1801239EC
0x18012396e  cmp     dword ptr cs:xmmword_180169738, r12d
0x180123975  mov     [rsp+260h+var_1E8], r12d
0x18012397a  mov     [rsp+260h+var_1F0], eax
0x18012397e  jz      loc_180123BC2
0x180123984  mov     rdx, 4000000000000800h; unsigned __int64
0x18012398e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180123995  jz      loc_180123BC2
0x18012399b  mov     rax, cs:qword_180169748
0x1801239a2  and     rax, rdx
0x1801239a5  cmp     cs:qword_180169748, rax
0x1801239ac  jnz     loc_180123BC2
0x1801239b2  lea     rcx, [rbp+160h+var_140]; unsigned __int16 *
0x1801239b6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801239bb  lea     rcx, [rbp+160h+var_140]
0x1801239bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801239c3  inc     rax
0x1801239c6  cmp     [rcx+rax*2], r12w
0x1801239cb  jnz     short loc_1801239C3
0x1801239cd  lea     ecx, [rax+rax]
0x1801239d0  lea     rax, [rbp+160h+var_140]
0x1801239d4  add     rcx, 2
0x1801239d8  lea     r9, [rsp+260h+var_1F0]
0x1801239dd  mov     [rsp+260h+var_200], rcx
0x1801239e2  lea     rcx, [rsp+260h+var_1E8]
0x1801239e7  jmp     loc_1801238EA
0x1801239ec  movzx   ecx, word ptr [r14]
0x1801239f0  sub     ecx, 2
0x1801239f3  jz      short loc_180123A24
0x1801239f5  sub     ecx, 1
0x1801239f8  jz      short loc_180123A24
0x1801239fa  sub     ecx, r15d
0x1801239fd  jz      loc_180123AF6
0x180123a03  sub     ecx, 1
0x180123a06  jz      loc_180123AB7
0x180123a0c  sub     ecx, 7
0x180123a0f  jz      short loc_180123A24
0x180123a11  sub     ecx, 1
0x180123a14  jz      short loc_180123A24
0x180123a16  sub     ecx, 1
0x180123a19  jz      short loc_180123A24
0x180123a1b  cmp     ecx, 1
0x180123a1e  jnz     loc_180123BB2
0x180123a24  mov     r9d, 13h; vt
0x180123a2a  xor     r8d, r8d; wFlags
0x180123a2d  mov     rdx, r14; pvarSrc
0x180123a30  mov     rcx, r14; pvargDest
0x180123a33  call    cs:__imp_VariantChangeType
0x180123a39  mov     ebx, eax
0x180123a3b  test    eax, eax
0x180123a3d  jns     loc_180123BAE
0x180123a43  cmp     dword ptr cs:xmmword_180169738, r12d
0x180123a4a  mov     [rsp+260h+var_1E8], r12d
0x180123a4f  mov     [rsp+260h+var_1F0], eax
0x180123a53  jz      loc_180123BC2
0x180123a59  mov     rdx, 4000000000000800h; unsigned __int64
0x180123a63  test    qword ptr cs:xmmword_180169738+8, rdx
0x180123a6a  jz      loc_180123BC2
0x180123a70  mov     rax, cs:qword_180169748
0x180123a77  and     rax, rdx
0x180123a7a  cmp     cs:qword_180169748, rax
0x180123a81  jnz     loc_180123BC2
0x180123a87  lea     rcx, [rbp+160h+var_C0]; unsigned __int16 *
0x180123a8e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180123a93  lea     rcx, [rbp+160h+var_C0]
0x180123a9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180123a9e  inc     rax
0x180123aa1  cmp     [rcx+rax*2], r12w
0x180123aa6  jnz     short loc_180123A9E
0x180123aa8  lea     ecx, [rax+rax]
0x180123aab  lea     rax, [rbp+160h+var_C0]
0x180123ab2  jmp     loc_1801239D4
0x180123ab7  mov     esi, r12d
0x180123aba  cmp     [rdi+4Ch], r12d
0x180123abe  jbe     loc_180123BB2
0x180123ac4  mov     r15d, 9
0x180123aca  mov     rcx, [rbp+160h+ppvData]
0x180123ace  mov     eax, esi
0x180123ad0  lea     rax, [rax+rax*2]
0x180123ad4  cmp     r15w, [rcx+rax*8]
0x180123ad9  jnz     short loc_180123AEA
0x180123adb  mov     rax, [rcx+rax*8+8]
0x180123ae0  cmp     [r14+8], rax
0x180123ae4  jz      loc_180123BB2
0x180123aea  inc     esi
0x180123aec  cmp     esi, [rdi+4Ch]
0x180123aef  jb      short loc_180123ACA
0x180123af1  jmp     loc_180123BB2
0x180123af6  mov     esi, r12d
0x180123af9  mov     r15d, 9
0x180123aff  cmp     esi, [rdi+4Ch]
0x180123b02  jnb     loc_180123BB7
0x180123b08  mov     eax, esi
0x180123b0a  lea     r12, [rax+rax*2]
0x180123b0e  mov     rax, [rbp+160h+ppvData]
0x180123b12  cmp     r15w, [rax+r12*8]
0x180123b17  jnz     loc_180123BA4
0x180123b1d  mov     rcx, [rbp+160h+var_1D0]
0x180123b21  test    rcx, rcx
0x180123b24  jz      short loc_180123B3A
0x180123b26  mov     rax, [rcx]
0x180123b29  mov     rax, [rax+10h]
0x180123b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123b32  mov     [rbp+160h+var_1D0], 0
0x180123b3a  mov     rax, [rbp+160h+ppvData]
0x180123b3e  lea     r8, [rbp+160h+var_1D0]
0x180123b42  lea     rdx, _GUID_03837543_098b_11d8_9414_505054503030
0x180123b49  mov     rcx, [rax+r12*8+8]
0x180123b4e  mov     rax, [rcx]
0x180123b51  mov     rax, [rax]
0x180123b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123b59  xor     r12d, r12d
0x180123b5c  mov     ebx, eax
0x180123b5e  test    eax, eax
0x180123b60  js      short loc_180123BA7
0x180123b62  mov     rcx, [rbp+160h+String1]; bstrString
0x180123b66  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180123b6b  mov     rcx, [rbp+160h+var_1D0]
0x180123b6f  lea     rdx, [rbp+160h+String1]
0x180123b73  mov     eax, r12d
0x180123b76  mov     [rbp+160h+String1], r12
0x180123b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123b7f  mov     ebx, eax
0x180123b81  test    eax, eax
0x180123b83  js      short loc_180123BA7
0x180123b85  mov     rcx, [rbp+160h+String1]; String1
0x180123b89  test    rcx, rcx
0x180123b8c  jz      short loc_180123BA7
0x180123b8e  cmp     r12w, [rcx]
0x180123b92  jz      short loc_180123BA7
0x180123b94  mov     rdx, [r14+8]; String2
0x180123b98  call    cs:__imp__wcsicmp
0x180123b9e  test    eax, eax
0x180123ba0  jz      short loc_180123BB2
0x180123ba2  jmp     short loc_180123BA7
0x180123ba4  xor     r12d, r12d
0x180123ba7  inc     esi
0x180123ba9  jmp     loc_180123AFF
0x180123bae  mov     esi, [r14+8]
0x180123bb2  cmp     esi, [rdi+4Ch]
0x180123bb5  jb      short loc_180123BBE
0x180123bb7  mov     ebx, 80070490h
0x180123bbc  jmp     short loc_180123BC2
0x180123bbe  mov     [r13+0], esi
0x180123bc2  mov     ecx, 40h ; '@'
0x180123bc7  cmp     [rbp+160h+ppvData], r12
0x180123bcb  jz      short loc_180123BDB
0x180123bcd  mov     rcx, [rcx+rdi]; psa
0x180123bd1  call    cs:__imp_SafeArrayUnaccessData
0x180123bd7  mov     [rbp+160h+ppvData], r12
0x180123bdb  mov     rcx, [rbp+160h+String1]; bstrString
0x180123bdf  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180123be4  mov     rcx, [rbp+160h+var_1D0]
0x180123be8  mov     [rbp+160h+String1], r12
0x180123bec  test    rcx, rcx
0x180123bef  jz      short loc_180123BFD
0x180123bf1  mov     rax, [rcx]
0x180123bf4  mov     rax, [rax+10h]
0x180123bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123bfd  mov     eax, ebx
0x180123bff  mov     rcx, [rbp+160h+var_40]
0x180123c06  xor     rcx, rsp; StackCookie
0x180123c09  call    __security_check_cookie
0x180123c0e  mov     rbx, [rsp+260h+arg_10]
0x180123c16  add     rsp, 230h
0x180123c1d  pop     r15
0x180123c1f  pop     r14
0x180123c21  pop     r13
0x180123c23  pop     r12
0x180123c25  pop     rdi
0x180123c26  pop     rsi
0x180123c27  pop     rbp
0x180123c28  retn
```
