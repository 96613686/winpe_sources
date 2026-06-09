# Enumerator::GetIndex<IValueMapItem>(tagVARIANT,long (IValueMapItem::*)(ushort * *),ulong *)

- ea: `0x1800339b4`
- end: `0x180033df3`
- name: `??$GetIndex@UIValueMapItem@@@Enumerator@@IEAAJUtagVARIANT@@P8IValueMapItem@@EAAJPEAPEAG@ZPEAK@Z`
- size: `1087`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800335d8`
- `0x18011bfe4`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x1800339b4`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180033d64`
- `msvcrt!_wcsicmp` at `0x180033d64`
- `OLEAUT32!__imp_VariantChangeType` at `0x180033bfd`
- `OLEAUT32!__imp_VariantChangeType` at `0x180033bfd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180033b2c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180033b2c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180033da2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180033da2`

## pseudocode

```c
__int64 __fastcall Enumerator::GetIndex<IValueMapItem>(
        __int64 a1,
        VARIANTARG *a2,
        __int64 (__fastcall *a3)(__int64, wchar_t **),
        unsigned int *a4)
{
  int vt; // ecx
  unsigned int *v6; // r12
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  SAFEARRAY *v15; // rcx
  int v16; // ebx
  __int64 v17; // rax
  HRESULT *v18; // r9
  HRESULT *v19; // rcx
  unsigned int i; // edi
  HRESULT v21; // eax
  __int64 v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rcx
  HRESULT v27; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v28; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v32[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v33[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v34[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  v28 = a4;
  String1 = 0;
  vt = a2->vt;
  v6 = a4;
  ppvData = 0;
  v31 = 0;
  v9 = vt - 2;
  if ( !v9 )
    goto LABEL_8;
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_8;
  v11 = v10 - 5;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( !v12 )
      goto LABEL_8;
    v13 = v12 - 7;
    if ( !v13 )
      goto LABEL_8;
    v14 = v13 - 1;
    if ( !v14 || (unsigned int)(v14 - 1) <= 1 )
      goto LABEL_8;
LABEL_11:
    v16 = -2147024809;
    LODWORD(v28) = -2147024809;
    v27 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_62;
    }
    PlaiWhoAmI(v32, 0x4000000000000800uLL);
    v17 = -1;
    do
      ++v17;
    while ( v32[v17] );
    v18 = (HRESULT *)&v28;
    v19 = &v27;
    goto LABEL_17;
  }
  if ( !a3 )
    goto LABEL_11;
LABEL_8:
  v15 = *(SAFEARRAY **)(a1 + 64);
  if ( !v15 )
  {
    v16 = -2147023728;
    goto LABEL_62;
  }
  i = *(_DWORD *)(a1 + 76);
  v21 = SafeArrayAccessData(v15, &ppvData);
  v16 = v21;
  if ( v21 < 0 )
  {
    LODWORD(v28) = 0;
    v27 = v21;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v33, 0x4000000000000800uLL);
      v22 = -1;
      do
        ++v22;
      while ( v33[v22] );
LABEL_24:
      v18 = &v27;
      v19 = (HRESULT *)&v28;
LABEL_17:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v18, 4, byte_180147320, 1, v19, 4);
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  if ( a2->vt != 2 && a2->vt != 3 )
  {
    if ( a2->vt == 8 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 76); ++i )
      {
        if ( *((_WORD *)ppvData + 12 * i) == 9 )
        {
          if ( v31 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            v31 = 0;
          }
          v25 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)ppvData + 3 * i + 1);
          v16 = (**v25)(v25, &GUID_03837533_098b_11d8_9414_505054503030, &v31);
          if ( v16 >= 0 )
          {
            PlaiFreeString(String1);
            String1 = 0;
            v16 = a3(v31, &String1);
            if ( v16 >= 0 && String1 && *String1 && !_wcsicmp(String1, a2->bstrVal) )
              break;
          }
        }
      }
      v6 = v28;
      goto LABEL_57;
    }
    if ( a2->vt == 9 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 76); ++i )
      {
        if ( *((_WORD *)ppvData + 12 * i) == 9 && a2->llVal == *((_QWORD *)ppvData + 3 * i + 1) )
          break;
      }
      goto LABEL_57;
    }
    if ( a2->vt != 16 && a2->vt != 17 && (unsigned int)a2->vt - 18 > 1 )
    {
LABEL_57:
      if ( i < *(_DWORD *)(a1 + 76) )
        *v6 = i;
      else
        v16 = -2147023728;
      goto LABEL_60;
    }
  }
  v23 = VariantChangeType(a2, a2, 0, 0x13u);
  v16 = v23;
  if ( v23 >= 0 )
  {
    i = a2->cyVal.Lo;
    goto LABEL_57;
  }
  LODWORD(v28) = 0;
  v27 = v23;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v34, 0x4000000000000800uLL);
    v24 = -1;
    do
      ++v24;
    while ( v34[v24] );
    goto LABEL_24;
  }
LABEL_60:
  if ( ppvData )
  {
    SafeArrayUnaccessData(*(SAFEARRAY **)(a1 + 64));
    ppvData = 0;
  }
LABEL_62:
  PlaiFreeString(String1);
  String1 = 0;
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800339b4  push    rbp
0x1800339b6  push    rbx
0x1800339b7  push    rsi
0x1800339b8  push    rdi
0x1800339b9  push    r12
0x1800339bb  push    r13
0x1800339bd  push    r14
0x1800339bf  push    r15
0x1800339c1  lea     rbp, [rsp-138h]
0x1800339c9  sub     rsp, 238h
0x1800339d0  mov     rax, cs:__security_cookie
0x1800339d7  xor     rax, rsp
0x1800339da  mov     [rbp+170h+var_50], rax
0x1800339e1  xor     r15d, r15d
0x1800339e4  mov     [rsp+270h+var_1F8], r9
0x1800339e9  mov     rsi, rcx
0x1800339ec  mov     [rbp+170h+String1], r15
0x1800339f0  movzx   ecx, word ptr [rdx]
0x1800339f3  mov     r12, r9
0x1800339f6  mov     [rbp+170h+ppvData], r15
0x1800339fa  mov     r13, r8
0x1800339fd  mov     [rbp+170h+var_1E0], r15
0x180033a01  mov     r14, rdx
0x180033a04  sub     ecx, 2
0x180033a07  jz      short loc_180033A2C
0x180033a09  sub     ecx, 1
0x180033a0c  jz      short loc_180033A2C
0x180033a0e  sub     ecx, 5
0x180033a11  jz      short loc_180033A43
0x180033a13  sub     ecx, 1
0x180033a16  jz      short loc_180033A2C
0x180033a18  sub     ecx, 7
0x180033a1b  jz      short loc_180033A2C
0x180033a1d  sub     ecx, 1
0x180033a20  jz      short loc_180033A2C
0x180033a22  sub     ecx, 1
0x180033a25  jz      short loc_180033A2C
0x180033a27  cmp     ecx, 1
0x180033a2a  jnz     short loc_180033A48
0x180033a2c  mov     rcx, [rsi+40h]; psa
0x180033a30  test    rcx, rcx
0x180033a33  jnz     loc_180033B25
0x180033a39  mov     ebx, 80070490h
0x180033a3e  jmp     loc_180033DAC
0x180033a43  test    r13, r13
0x180033a46  jnz     short loc_180033A2C
0x180033a48  cmp     dword ptr cs:xmmword_180169738, r15d
0x180033a4f  mov     ebx, 80070057h
0x180033a54  mov     dword ptr [rsp+270h+var_1F8], ebx
0x180033a58  mov     [rsp+270h+var_200], r15d
0x180033a5d  jz      loc_180033DAC
0x180033a63  mov     rdx, 4000000000000800h; unsigned __int64
0x180033a6d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180033a74  jz      loc_180033DAC
0x180033a7a  mov     rax, cs:qword_180169748
0x180033a81  and     rax, rdx
0x180033a84  cmp     cs:qword_180169748, rax
0x180033a8b  jnz     loc_180033DAC
0x180033a91  lea     rcx, [rbp+170h+var_1D0]; unsigned __int16 *
0x180033a95  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180033a9a  lea     rcx, [rbp+170h+var_1D0]
0x180033a9e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033aa2  inc     rax
0x180033aa5  cmp     [rcx+rax*2], r15w
0x180033aaa  jnz     short loc_180033AA2
0x180033aac  lea     ecx, [rax+rax]
0x180033aaf  add     rcx, 2
0x180033ab3  lea     rax, [rbp+170h+var_1D0]
0x180033ab7  mov     [rsp+270h+var_210], rcx
0x180033abc  lea     r9, [rsp+270h+var_1F8]
0x180033ac1  lea     rcx, [rsp+270h+var_200]
0x180033ac6  mov     [rsp+270h+var_218], rax
0x180033acb  lea     rdx, PLA_EVENT_ERROR
0x180033ad2  mov     [rsp+270h+var_220], 15h
0x180033adb  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180033ae2  mov     [rsp+270h+var_228], rax
0x180033ae7  mov     eax, 4
0x180033aec  mov     [rsp+270h+var_230], rax
0x180033af1  mov     [rsp+270h+var_238], rcx
0x180033af6  lea     rcx, byte_180147320
0x180033afd  mov     [rsp+270h+var_240], 1
0x180033b06  mov     [rsp+270h+var_248], rcx
0x180033b0b  lea     r8d, [rax+1]
0x180033b0f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180033b16  mov     [rsp+270h+var_250], rax
0x180033b1b  call    EventingWriteEvent
0x180033b20  jmp     loc_180033D93
0x180033b25  mov     edi, [rsi+4Ch]
0x180033b28  lea     rdx, [rbp+170h+ppvData]; ppvData
0x180033b2c  call    cs:__imp_SafeArrayAccessData
0x180033b32  mov     ebx, eax
0x180033b34  test    eax, eax
0x180033b36  jns     short loc_180033BB6
0x180033b38  cmp     dword ptr cs:xmmword_180169738, r15d
0x180033b3f  mov     dword ptr [rsp+270h+var_1F8], r15d
0x180033b44  mov     [rsp+270h+var_200], eax
0x180033b48  jz      loc_180033D93
0x180033b4e  mov     rdx, 4000000000000800h; unsigned __int64
0x180033b58  test    qword ptr cs:xmmword_180169738+8, rdx
0x180033b5f  jz      loc_180033D93
0x180033b65  mov     rax, cs:qword_180169748
0x180033b6c  and     rax, rdx
0x180033b6f  cmp     cs:qword_180169748, rax
0x180033b76  jnz     loc_180033D93
0x180033b7c  lea     rcx, [rbp+170h+var_150]; unsigned __int16 *
0x180033b80  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180033b85  lea     rcx, [rbp+170h+var_150]
0x180033b89  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033b8d  inc     rax
0x180033b90  cmp     [rcx+rax*2], r15w
0x180033b95  jnz     short loc_180033B8D
0x180033b97  lea     ecx, [rax+rax]
0x180033b9a  lea     rax, [rbp+170h+var_150]
0x180033b9e  add     rcx, 2
0x180033ba2  lea     r9, [rsp+270h+var_200]
0x180033ba7  mov     [rsp+270h+var_210], rcx
0x180033bac  lea     rcx, [rsp+270h+var_1F8]
0x180033bb1  jmp     loc_180033AC6
0x180033bb6  movzx   ecx, word ptr [r14]
0x180033bba  sub     ecx, 2
0x180033bbd  jz      short loc_180033BEE
0x180033bbf  sub     ecx, 1
0x180033bc2  jz      short loc_180033BEE
0x180033bc4  sub     ecx, 5
0x180033bc7  jz      loc_180033CC0
0x180033bcd  sub     ecx, 1
0x180033bd0  jz      loc_180033C81
0x180033bd6  sub     ecx, 7
0x180033bd9  jz      short loc_180033BEE
0x180033bdb  sub     ecx, 1
0x180033bde  jz      short loc_180033BEE
0x180033be0  sub     ecx, 1
0x180033be3  jz      short loc_180033BEE
0x180033be5  cmp     ecx, 1
0x180033be8  jnz     loc_180033D80
0x180033bee  mov     r9d, 13h; vt
0x180033bf4  xor     r8d, r8d; wFlags
0x180033bf7  mov     rdx, r14; pvarSrc
0x180033bfa  mov     rcx, r14; pvargDest
0x180033bfd  call    cs:__imp_VariantChangeType
0x180033c03  mov     ebx, eax
0x180033c05  test    eax, eax
0x180033c07  jns     loc_180033D75
0x180033c0d  cmp     dword ptr cs:xmmword_180169738, r15d
0x180033c14  mov     dword ptr [rsp+270h+var_1F8], r15d
0x180033c19  mov     [rsp+270h+var_200], eax
0x180033c1d  jz      loc_180033D93
0x180033c23  mov     rdx, 4000000000000800h; unsigned __int64
0x180033c2d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180033c34  jz      loc_180033D93
0x180033c3a  mov     rax, cs:qword_180169748
0x180033c41  and     rax, rdx
0x180033c44  cmp     cs:qword_180169748, rax
0x180033c4b  jnz     loc_180033D93
0x180033c51  lea     rcx, [rbp+170h+var_D0]; unsigned __int16 *
0x180033c58  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180033c5d  lea     rcx, [rbp+170h+var_D0]
0x180033c64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033c68  inc     rax
0x180033c6b  cmp     [rcx+rax*2], r15w
0x180033c70  jnz     short loc_180033C68
0x180033c72  lea     ecx, [rax+rax]
0x180033c75  lea     rax, [rbp+170h+var_D0]
0x180033c7c  jmp     loc_180033B9E
0x180033c81  mov     edi, r15d
0x180033c84  cmp     [rsi+4Ch], r15d
0x180033c88  jbe     loc_180033D80
0x180033c8e  mov     r15d, 9
0x180033c94  mov     rcx, [rbp+170h+ppvData]
0x180033c98  mov     eax, edi
0x180033c9a  lea     rax, [rax+rax*2]
0x180033c9e  cmp     r15w, [rcx+rax*8]
0x180033ca3  jnz     short loc_180033CB4
0x180033ca5  mov     rax, [rcx+rax*8+8]
0x180033caa  cmp     [r14+8], rax
0x180033cae  jz      loc_180033D80
0x180033cb4  inc     edi
0x180033cb6  cmp     edi, [rsi+4Ch]
0x180033cb9  jb      short loc_180033C94
0x180033cbb  jmp     loc_180033D80
0x180033cc0  mov     edi, r15d
0x180033cc3  mov     r15d, 9
0x180033cc9  cmp     edi, [rsi+4Ch]
0x180033ccc  jnb     loc_180033D7B
0x180033cd2  mov     eax, edi
0x180033cd4  lea     r12, [rax+rax*2]
0x180033cd8  mov     rax, [rbp+170h+ppvData]
0x180033cdc  cmp     r15w, [rax+r12*8]
0x180033ce1  jnz     loc_180033D6E
0x180033ce7  mov     rcx, [rbp+170h+var_1E0]
0x180033ceb  test    rcx, rcx
0x180033cee  jz      short loc_180033D04
0x180033cf0  mov     rax, [rcx]
0x180033cf3  mov     rax, [rax+10h]
0x180033cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cfc  mov     [rbp+170h+var_1E0], 0
0x180033d04  mov     rax, [rbp+170h+ppvData]
0x180033d08  lea     r8, [rbp+170h+var_1E0]
0x180033d0c  lea     rdx, _GUID_03837533_098b_11d8_9414_505054503030
0x180033d13  mov     rcx, [rax+r12*8+8]
0x180033d18  mov     rax, [rcx]
0x180033d1b  mov     rax, [rax]
0x180033d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d23  mov     ebx, eax
0x180033d25  test    eax, eax
0x180033d27  js      short loc_180033D6E
0x180033d29  mov     rcx, [rbp+170h+String1]; bstrString
0x180033d2d  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180033d32  mov     rcx, [rbp+170h+var_1E0]
0x180033d36  lea     rdx, [rbp+170h+String1]
0x180033d3a  mov     rax, r13
0x180033d3d  mov     [rbp+170h+String1], 0
0x180033d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d4a  mov     ebx, eax
0x180033d4c  test    eax, eax
0x180033d4e  js      short loc_180033D6E
0x180033d50  mov     rcx, [rbp+170h+String1]; String1
0x180033d54  test    rcx, rcx
0x180033d57  jz      short loc_180033D6E
0x180033d59  xor     eax, eax
0x180033d5b  cmp     ax, [rcx]
0x180033d5e  jz      short loc_180033D6E
0x180033d60  mov     rdx, [r14+8]; String2
0x180033d64  call    cs:__imp__wcsicmp
0x180033d6a  test    eax, eax
0x180033d6c  jz      short loc_180033D7B
0x180033d6e  inc     edi
0x180033d70  jmp     loc_180033CC9
0x180033d75  mov     edi, [r14+8]
0x180033d79  jmp     short loc_180033D80
0x180033d7b  mov     r12, [rsp+270h+var_1F8]
0x180033d80  xor     r15d, r15d
0x180033d83  cmp     edi, [rsi+4Ch]
0x180033d86  jb      short loc_180033D8F
0x180033d88  mov     ebx, 80070490h
0x180033d8d  jmp     short loc_180033D93
0x180033d8f  mov     [r12], edi
0x180033d93  mov     ecx, 40h ; '@'
0x180033d98  cmp     [rbp+170h+ppvData], r15
0x180033d9c  jz      short loc_180033DAC
0x180033d9e  mov     rcx, [rcx+rsi]; psa
0x180033da2  call    cs:__imp_SafeArrayUnaccessData
0x180033da8  mov     [rbp+170h+ppvData], r15
0x180033dac  mov     rcx, [rbp+170h+String1]; bstrString
0x180033db0  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180033db5  mov     rcx, [rbp+170h+var_1E0]
0x180033db9  mov     [rbp+170h+String1], r15
0x180033dbd  test    rcx, rcx
0x180033dc0  jz      short loc_180033DCE
0x180033dc2  mov     rax, [rcx]
0x180033dc5  mov     rax, [rax+10h]
0x180033dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dce  mov     eax, ebx
0x180033dd0  mov     rcx, [rbp+170h+var_50]
0x180033dd7  xor     rcx, rsp; StackCookie
0x180033dda  call    __security_check_cookie
0x180033ddf  add     rsp, 238h
0x180033de6  pop     r15
0x180033de8  pop     r14
0x180033dea  pop     r13
0x180033dec  pop     r12
0x180033dee  pop     rdi
0x180033def  pop     rsi
0x180033df0  pop     rbx
0x180033df1  pop     rbp
0x180033df2  retn
```
