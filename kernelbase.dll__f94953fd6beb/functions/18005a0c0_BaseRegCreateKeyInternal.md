# BaseRegCreateKeyInternal

- ea: `0x18005a0c0`
- end: `0x18005a7ec`
- name: `BaseRegCreateKeyInternal`
- size: `1836`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCUNICODE_STRING Source@<rdx>, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005a800`
- `0x180097d80`

## callees

- `0x18005a0c0`
- `0x18005cb00`
- `0x18005d320`
- `0x18005d6f0`
- `0x18005dd30`
- `0x18005ee30`
- `0x1800b2490`
- `0x1800b2990`
- `0x18010b9f4`
- `0x18012d119`
- `0x18012ffa4`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005a36c`
- `ntdll!RtlNtStatusToDosError` at `0x18005a36c`
- `ntdll!RtlCopyUnicodeString` at `0x18018fd41`
- `ntdll!RtlCopyUnicodeString` at `0x18018ff21`
- `ntdll!RtlCopyUnicodeString` at `0x18018fd41`
- `ntdll!RtlCopyUnicodeString` at `0x18018ff21`
- `ntdll!NtClose` at `0x18005a543`
- `ntdll!NtClose` at `0x18005a5f9`
- `ntdll!NtClose` at `0x18005a735`
- `ntdll!NtClose` at `0x18005a789`
- `ntdll!NtClose` at `0x18005a7d0`
- `ntdll!NtClose` at `0x18005a543`
- `ntdll!NtClose` at `0x18005a5f9`
- `ntdll!NtClose` at `0x18005a735`
- `ntdll!NtClose` at `0x18005a789`
- `ntdll!NtClose` at `0x18005a7d0`
- `ntdll!NtQueryKey` at `0x18005a729`
- `ntdll!NtQueryKey` at `0x18005a729`
- `ntdll!RtlFreeHeap` at `0x18005a361`
- `ntdll!RtlFreeHeap` at `0x18005a3be`
- `ntdll!RtlFreeHeap` at `0x18005a6dd`
- `ntdll!RtlFreeHeap` at `0x18005a763`
- `ntdll!RtlFreeHeap` at `0x18005a7ae`
- `ntdll!RtlFreeHeap` at `0x18018fdc5`
- `ntdll!RtlFreeHeap` at `0x18018fdff`
- `ntdll!RtlFreeHeap` at `0x18018ffac`
- `ntdll!RtlFreeHeap` at `0x18018fff0`
- `ntdll!RtlFreeHeap` at `0x18005a361`
- `ntdll!RtlFreeHeap` at `0x18005a3be`
- `ntdll!RtlFreeHeap` at `0x18005a6dd`
- `ntdll!RtlFreeHeap` at `0x18005a763`
- `ntdll!RtlFreeHeap` at `0x18005a7ae`
- `ntdll!RtlFreeHeap` at `0x18018fdc5`
- `ntdll!RtlFreeHeap` at `0x18018fdff`
- `ntdll!RtlFreeHeap` at `0x18018ffac`
- `ntdll!RtlFreeHeap` at `0x18018fff0`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18005a4d9`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18005a4d9`
- `ntdll!RtlAllocateHeap` at `0x18005a624`
- `ntdll!RtlAllocateHeap` at `0x18018fc64`
- `ntdll!RtlAllocateHeap` at `0x18018fce2`
- `ntdll!RtlAllocateHeap` at `0x18018fe3c`
- `ntdll!RtlAllocateHeap` at `0x18018febd`
- `ntdll!RtlAllocateHeap` at `0x18005a624`
- `ntdll!RtlAllocateHeap` at `0x18018fc64`
- `ntdll!RtlAllocateHeap` at `0x18018fce2`
- `ntdll!RtlAllocateHeap` at `0x18018fe3c`
- `ntdll!RtlAllocateHeap` at `0x18018febd`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvCreateRegEntry` at `0x18005a514`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvCreateRegEntry` at `0x18005a514`

## pseudocode

```c
ULONG __fastcall BaseRegCreateKeyInternal(
        HANDLE KeyHandle,
        UNICODE_STRING *Source,
        struct _UNICODE_STRING *a3,
        ULONG a4,
        ACCESS_MASK a5,
        __int64 a6,
        int a7,
        HANDLE *a8,
        _DWORD *a9,
        void *a10)
{
  HANDLE v10; // rsi
  HANDLE v13; // r14
  char v14; // di
  int v15; // r9d
  unsigned __int64 Length; // rax
  UNICODE_STRING v17; // xmm6
  PWSTR Buffer; // rcx
  int v19; // eax
  struct _UNICODE_STRING *v20; // r8
  int v21; // eax
  int KeySemantics; // edi
  int v23; // eax
  void *v25; // rcx
  int v26; // eax
  unsigned int v27; // edi
  int v28; // eax
  unsigned __int16 v29; // ax
  PVOID Heap; // rax
  __int16 v31; // si
  unsigned __int64 v32; // rdi
  __int64 v33; // rcx
  SIZE_T v34; // r8
  PVOID v35; // rax
  __int16 v36; // si
  unsigned __int64 v37; // rdi
  __int64 v38; // rcx
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+58h] [rbp-A8h] BYREF
  int v41; // [rsp+5Ch] [rbp-A4h]
  PVOID v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v43; // [rsp+70h] [rbp-90h] BYREF
  ULONG v44; // [rsp+78h] [rbp-88h]
  int v45; // [rsp+7Ch] [rbp-84h]
  UNICODE_STRING SourceString; // [rsp+80h] [rbp-80h] BYREF
  ULONG v47; // [rsp+90h] [rbp-70h] BYREF
  int v48; // [rsp+94h] [rbp-6Ch]
  void *v49; // [rsp+98h] [rbp-68h]
  __int128 v50; // [rsp+A0h] [rbp-60h] BYREF
  PVOID P; // [rsp+B0h] [rbp-50h]
  PVOID v52[2]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v54; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v55[48]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD *v56; // [rsp+118h] [rbp+18h]
  _BYTE v57[48]; // [rsp+120h] [rbp+20h] BYREF
  __int128 KeyInformation; // [rsp+150h] [rbp+50h] BYREF
  __int128 v59; // [rsp+160h] [rbp+60h]
  __int64 v60; // [rsp+170h] [rbp+70h]
  _BYTE v61[384]; // [rsp+180h] [rbp+80h] BYREF

  v10 = 0;
  v49 = a10;
  v13 = KeyHandle;
  v56 = a9;
  Handle = KeyHandle;
  v60 = 0;
  P = 0;
  v14 = a4;
  v44 = a4;
  memset(v57, 0, 44);
  v52[0] = 0;
  v47 = 0;
  KeyInformation = 0;
  ResultLength = 0;
  v59 = 0;
  v50 = 0;
  memset_0(v61, 0, sizeof(v61));
  Length = Source->Length;
  v52[1] = 0;
  v43 = 0;
  v17 = *Source;
  if ( (unsigned int)Length < 2
    || (Buffer = Source->Buffer) == 0
    || (Length & 1) != 0
    || Buffer[(Length >> 1) - 1]
    || !a8
    || !a3
    || (a3->Length & 1) != 0
    || a3->Length && !a3->Buffer )
  {
    KeySemantics = -1073741811;
    goto LABEL_42;
  }
  *a8 = 0;
  Source->Length -= 2;
  if ( *Source->Buffer == 92 )
  {
    KeySemantics = -1073741767;
    goto LABEL_42;
  }
  v41 = 1;
  v45 = 1;
  if ( a3->Length )
    a3->Length -= 2;
  v19 = 64;
  v48 = 64;
  if ( a6 )
  {
    if ( *(_BYTE *)(a6 + 24) )
      v19 = 66;
    v48 = v19;
  }
  if ( (v14 & 8) != 0 )
    v48 = v19 | 0x100;
  if ( ((unsigned __int8)v13 & 2) != 0
    || (g_RegKrnGlobalState & 2) != 0 && (v28 = ExtractClassKey(&Handle, Source, v49), v13 = Handle, v28) )
  {
    LODWORD(v50) = v50 & 0xFFFFFFDF;
    P = v61;
    HIDWORD(v50) = 384;
    KeySemantics = BaseRegGetKeySemantics(v13, Source);
    if ( KeySemantics < 0 )
      goto LABEL_40;
    Handle = 0;
    *(_OWORD *)v42 = 0;
    v26 = BaseRegOpenClassKeyFromLocation((__int64)&v50, v13, (__int64)Source, 0x2000000, 2, v44, &Handle, v49);
    KeySemantics = v26;
    if ( v26 < 0 )
    {
      if ( v26 != -1073741772 )
        goto LABEL_37;
      v27 = 1;
      v40 = 1;
    }
    else
    {
      v27 = 0;
      v40 = 0;
      NtClose(Handle);
    }
    WORD1(v42[0]) = *(_WORD *)P + 362;
    v42[1] = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, WORD1(v42[0]));
    if ( !v42[1] )
    {
LABEL_92:
      KeySemantics = -1073741801;
      goto LABEL_37;
    }
    KeySemantics = BaseRegOpenClassKeyRoot(&v50, &v43, v42, v27, v49);
    if ( KeySemantics < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v42[1]);
      v10 = v43;
      goto LABEL_37;
    }
    if ( !v40 )
      v45 = 0;
    v20 = (struct _UNICODE_STRING *)v52;
    v10 = v43;
    v52[0] = v42[0];
    v52[1] = (PVOID)_mm_srli_si128(*(__m128i *)v42, 8).m128i_u64[0];
    Handle = v52;
  }
  else
  {
    v43 = v13;
    Handle = Source;
    v50 = 0;
    P = 0;
    v10 = v13;
    v20 = Source;
  }
  v21 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      KeySemantics = -1073741772;
      if ( v21 )
      {
        if ( a6 )
        {
          v25 = *(void **)(a6 + 8);
          if ( v25 )
          {
            if ( !RtlValidRelativeSecurityDescriptor(v25, *(_DWORD *)(a6 + 16), 0) )
            {
              KeySemantics = -1073741811;
              goto LABEL_37;
            }
            v20 = (struct _UNICODE_STRING *)Handle;
          }
        }
        *(_DWORD *)v57 = 48;
        *(_QWORD *)&v57[8] = v10;
        *(_DWORD *)&v57[24] = v48;
        *(_QWORD *)&v57[16] = v20;
        if ( a6 )
          *(_QWORD *)&v57[32] = *(_QWORD *)(a6 + 8);
        else
          *(_QWORD *)&v57[32] = 0;
        *(_QWORD *)&v57[40] = 0;
        if ( v49 )
          v23 = Wow64NtCreateKey(a8, a5, (__int128 *)v57, v15, a3, v44, (__int64)v49, &v47);
        else
          v23 = Wow64NtCreateKey(a8, a5, (__int128 *)v57, v15, a3, v44, 0, &v47);
        KeySemantics = v23;
        if ( v23 == 1073741846 )
        {
          KeySemantics = NtQueryKey(*a8, KeyCachedInformation, &KeyInformation, 0x28u, &ResultLength);
          NtClose(*a8);
          if ( KeySemantics >= 0 )
          {
            *a8 = (HANDLE)SDWORD1(v59);
            goto LABEL_27;
          }
        }
        else if ( v23 >= 0 )
        {
LABEL_27:
          if ( v47 == 1 && (unsigned __int8)IsTermsrvDeleteKeyPresent() )
            TermsrvCreateRegEntry(*a8, v57, 0, a3, v44);
        }
        v21 = v41;
      }
      if ( (g_RegKrnGlobalState & 2) == 0 || !v21 || KeySemantics != -1073741790 )
        break;
      if ( (v50 & 4) == 0 || !v45 )
      {
LABEL_56:
        KeySemantics = BaseRegCreateMultipartKey(
                         (_DWORD)v10,
                         (_DWORD)Handle,
                         (_DWORD)a3,
                         v44,
                         a5,
                         a6,
                         (__int64)a8,
                         (__int64)v56,
                         v48,
                         (__int64)v49);
        goto LABEL_33;
      }
      if ( v52[1] )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v52[1]);
        v21 = v41;
        v52[1] = 0;
      }
      KeySemantics = -1073741790;
      *(_QWORD *)&SourceString.Length = 0;
      SourceString.Buffer = 0;
      if ( (v50 & 4) == 0 )
        goto LABEL_53;
      LOWORD(v40) = 0;
      if ( v10 )
      {
        NtClose(v10);
        v10 = 0;
        v43 = 0;
      }
      SourceString.MaximumLength = *(_WORD *)P + 362;
      SourceString.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, SourceString.MaximumLength);
      if ( !SourceString.Buffer )
        goto LABEL_92;
      v45 = 0;
      KeySemantics = BaseRegTranslateToUserClassKey(&v50, &SourceString, &v40);
      if ( KeySemantics < 0 )
        goto LABEL_109;
      v54 = 0;
      v29 = SourceString.MaximumLength - v40 + 2;
      *((_WORD *)Handle + 1) = v29;
      memset(v55, 0, 44);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
      v20 = (struct _UNICODE_STRING *)Handle;
      *((_QWORD *)Handle + 1) = Heap;
      if ( Heap )
      {
        v31 = v40;
        *((_QWORD *)&v54 + 1) = SourceString.Buffer;
        LOWORD(v54) = v40;
        v32 = 2 * (((unsigned __int64)(unsigned __int16)v40 + 2) >> 1);
        SourceString.Buffer = (PWSTR)((char *)SourceString.Buffer + v32);
        SourceString.Length += -2 - v40;
        SourceString.MaximumLength += -2 - v40;
        RtlCopyUnicodeString(v20, &SourceString);
        SourceString.Length += v31 + 2;
        SourceString.Buffer = (PWSTR)((char *)SourceString.Buffer - v32);
        *(_DWORD *)v55 = 48;
        SourceString.MaximumLength += v31 + 2;
        v33 = (__int64)v49;
        *(_DWORD *)&v55[24] = 64;
        *(_QWORD *)&v55[8] = 0;
        *(_QWORD *)&v55[16] = &v54;
        if ( !v49 )
          v33 = 0;
        *(_OWORD *)&v55[32] = 0;
        KeySemantics = Wow64NtOpenKey((unsigned int)&v43, 0x2000000, (unsigned int)v55, 0, v33);
        if ( KeySemantics >= 0 )
        {
          v10 = v43;
LABEL_109:
          v20 = (struct _UNICODE_STRING *)Handle;
          goto LABEL_110;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)Handle + 1));
        v20 = (struct _UNICODE_STRING *)Handle;
        *((_QWORD *)Handle + 1) = 0;
        v10 = v43;
      }
      else
      {
        KeySemantics = -1073741801;
      }
LABEL_110:
      if ( !SourceString.Buffer )
      {
        v21 = v41;
        goto LABEL_54;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SourceString.Buffer);
      v21 = v41;
LABEL_53:
      v20 = (struct _UNICODE_STRING *)Handle;
LABEL_54:
      if ( KeySemantics < 0 )
        goto LABEL_37;
    }
    if ( KeySemantics < 0 )
      goto LABEL_56;
    if ( v56 )
      *v56 = v47;
LABEL_33:
    if ( (g_RegKrnGlobalState & 2) == 0 || KeySemantics != -1073741790 )
      break;
    if ( (v50 & 4) == 0 || !v45 )
      goto LABEL_37;
    if ( v52[1] )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v52[1]);
      v52[1] = 0;
    }
    KeySemantics = -1073741790;
    v42[0] = 0;
    v42[1] = 0;
    if ( (v50 & 4) == 0 )
      goto LABEL_63;
    LOWORD(v40) = 0;
    if ( v10 )
    {
      NtClose(v10);
      v10 = 0;
      v43 = 0;
    }
    WORD1(v42[0]) = *(_WORD *)P + 362;
    v42[1] = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, WORD1(v42[0]));
    if ( !v42[1] )
      goto LABEL_92;
    v45 = 0;
    KeySemantics = BaseRegTranslateToUserClassKey(&v50, v42, &v40);
    if ( KeySemantics < 0 )
      goto LABEL_122;
    v34 = (unsigned __int16)(WORD1(v42[0]) - v40 + 2);
    v54 = 0;
    *(_OWORD *)&v55[16] = 0;
    *((_WORD *)Handle + 1) = v34;
    *(_OWORD *)v55 = 0;
    *(_OWORD *)&v55[28] = 0;
    v35 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v34);
    v20 = (struct _UNICODE_STRING *)Handle;
    *((_QWORD *)Handle + 1) = v35;
    if ( v35 )
    {
      v36 = v40;
      *((PVOID *)&v54 + 1) = v42[1];
      LOWORD(v54) = v40;
      v37 = 2 * (((unsigned __int64)(unsigned __int16)v40 + 2) >> 1);
      v42[1] = (char *)v42[1] + v37;
      LOWORD(v42[0]) += -2 - v40;
      WORD1(v42[0]) += -2 - v40;
      RtlCopyUnicodeString(v20, (PCUNICODE_STRING)v42);
      LOWORD(v42[0]) += v36 + 2;
      v42[1] = (char *)v42[1] - v37;
      v38 = (__int64)v49;
      *(_QWORD *)&v55[16] = &v54;
      *(_DWORD *)v55 = 48;
      *(_QWORD *)&v55[8] = 0;
      WORD1(v42[0]) += v36 + 2;
      *(_DWORD *)&v55[24] = 64;
      if ( !v49 )
        v38 = 0;
      *(_OWORD *)&v55[32] = 0;
      KeySemantics = Wow64NtOpenKey((unsigned int)&v43, 0x2000000, (unsigned int)v55, 0, v38);
      if ( KeySemantics >= 0 )
      {
        v10 = v43;
LABEL_122:
        v20 = (struct _UNICODE_STRING *)Handle;
        goto LABEL_123;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)Handle + 1));
      v20 = (struct _UNICODE_STRING *)Handle;
      v10 = v43;
      *((_QWORD *)Handle + 1) = 0;
    }
    else
    {
      KeySemantics = -1073741801;
    }
LABEL_123:
    if ( !v42[1] )
      goto LABEL_64;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v42[1]);
LABEL_63:
    v20 = (struct _UNICODE_STRING *)Handle;
LABEL_64:
    v41 = 0;
    v21 = 0;
    if ( KeySemantics < 0 )
      goto LABEL_37;
  }
  if ( KeySemantics >= 0 && (v50 & 4) != 0 )
    *a8 = (HANDLE)((unsigned __int64)*a8 | 2);
LABEL_37:
  if ( v10 && v10 != v13 )
    NtClose(v10);
LABEL_40:
  if ( v52[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v52[1]);
LABEL_42:
  if ( (v50 & 0x20) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  *Source = v17;
  return RtlNtStatusToDosError(KeySemantics);
}

```

## disassembly

```asm
0x18005a0c0  push    rbp
0x18005a0c2  push    rbx
0x18005a0c3  push    rsi
0x18005a0c4  push    rdi
0x18005a0c5  push    r12
0x18005a0c7  push    r13
0x18005a0c9  push    r14
0x18005a0cb  push    r15
0x18005a0cd  lea     rbp, [rsp-228h]
0x18005a0d5  sub     rsp, 328h
0x18005a0dc  movaps  [rsp+360h+var_50], xmm6
0x18005a0e4  mov     rax, cs:__security_cookie
0x18005a0eb  xor     rax, rsp
0x18005a0ee  mov     [rbp+260h+var_60], rax
0x18005a0f5  mov     rax, [rbp+260h+arg_48]
0x18005a0fc  xorps   xmm0, xmm0
0x18005a0ff  mov     r13, [rbp+260h+arg_28]
0x18005a106  xor     esi, esi
0x18005a108  mov     r12, [rbp+260h+arg_38]
0x18005a10f  mov     r15, r8
0x18005a112  mov     [rbp+260h+var_2C8], rax
0x18005a116  mov     rbx, rdx
0x18005a119  mov     rax, [rbp+260h+arg_40]
0x18005a120  mov     r14, rcx
0x18005a123  mov     [rbp+260h+var_248], rax
0x18005a127  xor     edx, edx; Val
0x18005a129  xor     eax, eax
0x18005a12b  mov     [rsp+360h+Handle], rcx
0x18005a130  movups  [rbp+260h+var_230], xmm0
0x18005a134  mov     r8d, 180h; Size
0x18005a13a  mov     [rbp+260h+var_1F0], rax
0x18005a13e  lea     rcx, [rbp+260h+var_1E0]; void *
0x18005a145  mov     [rbp+260h+P], rax
0x18005a149  mov     edi, r9d
0x18005a14c  mov     [rsp+360h+var_2E8], r9d
0x18005a151  movups  [rbp+260h+var_240], xmm0
0x18005a155  mov     [rbp+260h+var_2A0], rsi
0x18005a159  movups  [rbp+260h+var_230+0Ch], xmm0
0x18005a15d  mov     [rbp+260h+var_2D0], esi
0x18005a160  movups  [rbp+260h+KeyInformation], xmm0
0x18005a164  mov     [rbp+260h+var_290], esi
0x18005a167  movups  [rbp+260h+var_200], xmm0
0x18005a16b  movups  [rbp+260h+var_2C0], xmm0
0x18005a16f  call    memset_0
0x18005a174  movzx   eax, word ptr [rbx]
0x18005a177  mov     [rbp+260h+var_2A0+8], rsi
0x18005a17b  mov     [rsp+360h+var_2F0], rsi
0x18005a180  movups  xmm6, xmmword ptr [rbx]
0x18005a183  cmp     eax, 2
0x18005a186  jb      loc_18005A39D
0x18005a18c  mov     rcx, [rbx+8]
0x18005a190  test    rcx, rcx
0x18005a193  jz      loc_18005A39D
0x18005a199  test    al, 1
0x18005a19b  jnz     loc_18005A39D
0x18005a1a1  shr     rax, 1
0x18005a1a4  cmp     [rcx+rax*2-2], si
0x18005a1a9  jnz     loc_18005A39D
0x18005a1af  test    r12, r12
0x18005a1b2  jz      loc_18005A39D
0x18005a1b8  test    r15, r15
0x18005a1bb  jz      loc_18005A39D
0x18005a1c1  movzx   eax, word ptr [r15]
0x18005a1c5  test    al, 1
0x18005a1c7  jnz     loc_18005A39D
0x18005a1cd  test    ax, ax
0x18005a1d0  jnz     loc_18005A561
0x18005a1d6  mov     [r12], rsi
0x18005a1da  mov     eax, 0FFFEh
0x18005a1df  add     [rbx], ax
0x18005a1e2  mov     rax, [rbx+8]
0x18005a1e6  cmp     word ptr [rax], 5Ch ; '\'
0x18005a1ea  jz      loc_18005A6ED
0x18005a1f0  mov     eax, 1
0x18005a1f5  mov     [rsp+360h+var_304], eax
0x18005a1f9  mov     [rsp+360h+var_2E4], eax
0x18005a1fd  movzx   eax, word ptr [r15]
0x18005a201  test    ax, ax
0x18005a204  jz      short loc_18005A20E
0x18005a206  sub     ax, 2
0x18005a20a  mov     [r15], ax
0x18005a20e  mov     eax, 40h ; '@'
0x18005a213  mov     [rbp+260h+var_2CC], eax
0x18005a216  test    r13, r13
0x18005a219  jnz     loc_18005A51F
0x18005a21f  test    dil, 8
0x18005a223  jnz     loc_18005A6F7
0x18005a229  test    r14b, 2
0x18005a22d  jnz     loc_18005A570
0x18005a233  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005a23a  jnz     loc_18005A68D
0x18005a240  xorps   xmm0, xmm0
0x18005a243  mov     [rsp+360h+var_2F0], r14
0x18005a248  xor     eax, eax
0x18005a24a  mov     [rsp+360h+Handle], rbx
0x18005a24f  movups  [rbp+260h+var_2C0], xmm0
0x18005a253  mov     [rbp+260h+P], rax
0x18005a257  mov     rsi, r14
0x18005a25a  mov     r8, rbx
0x18005a25d  mov     eax, 1
0x18005a262  mov     edi, 0C0000034h
0x18005a267  test    eax, eax
0x18005a269  jz      loc_18005A2F9
0x18005a26f  test    r13, r13
0x18005a272  jnz     loc_18005A4C5
0x18005a278  mov     eax, [rbp+260h+var_2CC]
0x18005a27b  xor     ecx, ecx
0x18005a27d  mov     dword ptr [rbp+260h+var_240], 30h ; '0'
0x18005a284  mov     qword ptr [rbp+260h+var_240+8], rsi
0x18005a288  mov     dword ptr [rbp+260h+var_230+8], eax
0x18005a28b  mov     qword ptr [rbp+260h+var_230], r8
0x18005a28f  test    r13, r13
0x18005a292  jnz     loc_18005A533
0x18005a298  mov     [rbp+260h+var_220], rcx
0x18005a29c  mov     rax, [rbp+260h+var_2C8]
0x18005a2a0  lea     r8, [rbp+260h+var_240]
0x18005a2a4  mov     edx, [rbp+260h+arg_20]
0x18005a2aa  mov     [rbp+260h+var_218], rcx
0x18005a2ae  test    rax, rax
0x18005a2b1  jnz     loc_18005A54E
0x18005a2b7  lea     rax, [rbp+260h+var_2D0]
0x18005a2bb  mov     [rsp+360h+var_328], rax
0x18005a2c0  mov     [rsp+360h+var_330], rcx
0x18005a2c5  mov     eax, [rsp+360h+var_2E8]
0x18005a2c9  mov     rcx, r12
0x18005a2cc  mov     dword ptr [rsp+360h+var_338], eax
0x18005a2d0  mov     [rsp+360h+ResultLength], r15
0x18005a2d5  call    Wow64NtCreateKey
0x18005a2da  mov     edi, eax
0x18005a2dc  cmp     eax, 40000016h
0x18005a2e1  jz      loc_18005A70D
0x18005a2e7  test    eax, eax
0x18005a2e9  js      short loc_18005A2F5
0x18005a2eb  cmp     [rbp+260h+var_2D0], 1
0x18005a2ef  jz      loc_18005A4F1
0x18005a2f5  mov     eax, [rsp+360h+var_304]
0x18005a2f9  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005a300  jnz     loc_18005A3C6
0x18005a306  test    edi, edi
0x18005a308  js      loc_18005A41D
0x18005a30e  mov     rcx, [rbp+260h+var_248]
0x18005a312  test    rcx, rcx
0x18005a315  jz      short loc_18005A31C
0x18005a317  mov     eax, [rbp+260h+var_2D0]
0x18005a31a  mov     [rcx], eax
0x18005a31c  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005a323  jnz     loc_18005A466
0x18005a329  test    edi, edi
0x18005a32b  js      short loc_18005A333
0x18005a32d  test    byte ptr [rbp+260h+var_2C0], 4
0x18005a331  jnz     short loc_18005A3A4
0x18005a333  test    rsi, rsi
0x18005a336  jz      short loc_18005A341
0x18005a338  cmp     rsi, r14
0x18005a33b  jnz     loc_18005A540
0x18005a341  cmp     [rbp+260h+var_2A0+8], 0
0x18005a346  jnz     short loc_18005A3AB
0x18005a348  test    byte ptr [rbp+260h+var_2C0], 20h
0x18005a34c  jz      short loc_18005A367
0x18005a34e  mov     rcx, gs:60h
0x18005a357  xor     edx, edx; Flags
0x18005a359  mov     r8, [rbp+260h+P]; P
0x18005a35d  mov     rcx, [rcx+30h]; HeapHandle
0x18005a361  call    cs:__imp_RtlFreeHeap
0x18005a367  mov     ecx, edi; Status
0x18005a369  movups  xmmword ptr [rbx], xmm6
0x18005a36c  call    cs:__imp_RtlNtStatusToDosError
0x18005a372  mov     rcx, [rbp+260h+var_60]
0x18005a379  xor     rcx, rsp; StackCookie
0x18005a37c  call    __security_check_cookie
0x18005a381  movaps  xmm6, [rsp+360h+var_50]
0x18005a389  add     rsp, 328h
0x18005a390  pop     r15
0x18005a392  pop     r14
0x18005a394  pop     r13
0x18005a396  pop     r12
0x18005a398  pop     rdi
0x18005a399  pop     rsi
0x18005a39a  pop     rbx
0x18005a39b  pop     rbp
0x18005a39c  retn
0x18005a39d  mov     edi, 0C000000Dh
0x18005a3a2  jmp     short loc_18005A348
0x18005a3a4  or      qword ptr [r12], 2
0x18005a3a9  jmp     short loc_18005A333
0x18005a3ab  mov     rcx, gs:60h
0x18005a3b4  xor     edx, edx; Flags
0x18005a3b6  mov     r8, [rbp+260h+var_2A0+8]; P
0x18005a3ba  mov     rcx, [rcx+30h]; HeapHandle
0x18005a3be  call    cs:__imp_RtlFreeHeap
0x18005a3c4  jmp     short loc_18005A348
0x18005a3c6  test    eax, eax
0x18005a3c8  jz      loc_18005A306
0x18005a3ce  cmp     edi, 0C0000022h
0x18005a3d4  jnz     loc_18005A306
0x18005a3da  test    byte ptr [rbp+260h+var_2C0], 4
0x18005a3de  jz      short loc_18005A41D
0x18005a3e0  cmp     [rsp+360h+var_2E4], 0
0x18005a3e5  jz      short loc_18005A41D
0x18005a3e7  cmp     [rbp+260h+var_2A0+8], 0
0x18005a3ec  jnz     loc_18005A750
0x18005a3f2  xor     ecx, ecx
0x18005a3f4  test    byte ptr [rbp+260h+var_2C0], 4
0x18005a3f8  mov     edi, 0C0000022h
0x18005a3fd  mov     qword ptr [rbp+260h+SourceString.Length], rcx
0x18005a401  mov     [rbp+260h+SourceString.Buffer], rcx
0x18005a405  jnz     loc_18005A778
0x18005a40b  mov     r8, [rsp+360h+Handle]
0x18005a410  test    edi, edi
0x18005a412  jns     loc_18005A262
0x18005a418  jmp     loc_18005A333
0x18005a41d  mov     rax, [rbp+260h+var_2C8]
0x18005a421  mov     r8, r15
0x18005a424  mov     r9d, [rsp+360h+var_2E8]
0x18005a429  mov     rcx, rsi
0x18005a42c  mov     rdx, [rsp+360h+Handle]
0x18005a431  mov     [rsp+360h+var_318], rax
0x18005a436  mov     eax, [rbp+260h+var_2CC]
0x18005a439  mov     [rsp+360h+var_320], eax
0x18005a43d  mov     rax, [rbp+260h+var_248]
0x18005a441  mov     [rsp+360h+var_328], rax
0x18005a446  mov     eax, [rbp+260h+arg_20]
0x18005a44c  mov     [rsp+360h+var_330], r12
0x18005a451  mov     [rsp+360h+var_338], r13
0x18005a456  mov     dword ptr [rsp+360h+ResultLength], eax
0x18005a45a  call    BaseRegCreateMultipartKey
0x18005a45f  mov     edi, eax
0x18005a461  jmp     loc_18005A31C
0x18005a466  cmp     edi, 0C0000022h
0x18005a46c  jnz     loc_18005A329
0x18005a472  test    byte ptr [rbp+260h+var_2C0], 4
0x18005a476  jz      loc_18005A333
0x18005a47c  cmp     [rsp+360h+var_2E4], 0
0x18005a481  jz      loc_18005A333
0x18005a487  cmp     [rbp+260h+var_2A0+8], 0
0x18005a48c  jnz     loc_18005A79B
0x18005a492  xor     ecx, ecx
0x18005a494  test    byte ptr [rbp+260h+var_2C0], 4
0x18005a498  mov     edi, 0C0000022h
0x18005a49d  mov     [rsp+360h+var_300], rcx
0x18005a4a2  mov     [rsp+360h+var_300+8], rcx
0x18005a4a7  jnz     loc_18005A7BF
0x18005a4ad  mov     r8, [rsp+360h+Handle]
0x18005a4b2  mov     [rsp+360h+var_304], ecx
0x18005a4b6  mov     eax, ecx
0x18005a4b8  test    edi, edi
0x18005a4ba  jns     loc_18005A262
0x18005a4c0  jmp     loc_18005A333
0x18005a4c5  mov     rcx, [r13+8]; SecurityDescriptorInput
0x18005a4c9  test    rcx, rcx
0x18005a4cc  jz      loc_18005A278
0x18005a4d2  mov     edx, [r13+10h]; SecurityDescriptorLength
0x18005a4d6  xor     r8d, r8d; RequiredInformation
0x18005a4d9  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18005a4df  test    al, al
0x18005a4e1  jz      loc_18005A7E2
0x18005a4e7  mov     r8, [rsp+360h+Handle]
0x18005a4ec  jmp     loc_18005A278
0x18005a4f1  call    IsTermsrvDeleteKeyPresent
0x18005a4f6  test    al, al
0x18005a4f8  jz      loc_18005A2F5
0x18005a4fe  mov     eax, [rsp+360h+var_2E8]
0x18005a502  lea     rdx, [rbp+260h+var_240]
0x18005a506  mov     rcx, [r12]
0x18005a50a  mov     r9, r15
0x18005a50d  xor     r8d, r8d
0x18005a510  mov     dword ptr [rsp+360h+ResultLength], eax
0x18005a514  call    cs:__imp_TermsrvCreateRegEntry
0x18005a51a  jmp     loc_18005A2F5
0x18005a51f  cmp     [r13+18h], sil
0x18005a523  mov     ecx, 42h ; 'B'
0x18005a528  cmovnz  eax, ecx
0x18005a52b  mov     [rbp+260h+var_2CC], eax
0x18005a52e  jmp     loc_18005A21F
0x18005a533  mov     rax, [r13+8]
0x18005a537  mov     [rbp+260h+var_220], rax
0x18005a53b  jmp     loc_18005A29C
0x18005a540  mov     rcx, rsi; Handle
0x18005a543  call    cs:__imp_NtClose
0x18005a549  jmp     loc_18005A341
0x18005a54e  lea     rcx, [rbp+260h+var_2D0]
0x18005a552  mov     [rsp+360h+var_328], rcx
0x18005a557  mov     [rsp+360h+var_330], rax
0x18005a55c  jmp     loc_18005A2C5
0x18005a561  cmp     [r15+8], rsi
0x18005a565  jnz     loc_18005A1D6
0x18005a56b  jmp     loc_18005A39D
0x18005a570  and     dword ptr [rbp+260h+var_2C0], 0FFFFFFDFh
0x18005a574  lea     rax, [rbp+260h+var_1E0]
0x18005a57b  lea     r8, [rbp+260h+var_2C0]
0x18005a57f  mov     [rbp+260h+P], rax
0x18005a583  mov     rdx, rbx; Source
0x18005a586  mov     dword ptr [rbp+260h+var_2C0+0Ch], 180h
0x18005a58d  mov     rcx, r14; KeyHandle
0x18005a590  call    BaseRegGetKeySemantics
0x18005a595  mov     edi, eax
0x18005a597  test    eax, eax
0x18005a599  js      loc_18005A341
0x18005a59f  mov     rax, [rbp+260h+var_2C8]
0x18005a5a3  lea     rcx, [rbp+260h+var_2C0]
  ... truncated ...
```
