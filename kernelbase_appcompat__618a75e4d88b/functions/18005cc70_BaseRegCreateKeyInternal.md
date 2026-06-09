# BaseRegCreateKeyInternal

- ea: `0x18005cc70`
- end: `0x18005d3fd`
- name: `BaseRegCreateKeyInternal`
- size: `1933`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCUNICODE_STRING Source@<rdx>, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e440`
- `0x18005d410`

## callees

- `0x18005cc70`
- `0x18005f8a0`
- `0x1800602e0`
- `0x180060700`
- `0x180060db0`
- `0x180061a20`
- `0x1800bce60`
- `0x1800bd3b0`
- `0x180114974`
- `0x1801369c9`
- `0x180139854`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005cf22`
- `ntdll!RtlNtStatusToDosError` at `0x18005cf22`
- `ntdll!RtlCopyUnicodeString` at `0x18019ae7d`
- `ntdll!RtlCopyUnicodeString` at `0x18019b07b`
- `ntdll!RtlCopyUnicodeString` at `0x18019ae7d`
- `ntdll!RtlCopyUnicodeString` at `0x18019b07b`
- `ntdll!NtClose` at `0x18005d118`
- `ntdll!NtClose` at `0x18005d1d4`
- `ntdll!NtClose` at `0x18005d328`
- `ntdll!NtClose` at `0x18005d388`
- `ntdll!NtClose` at `0x18005d3db`
- `ntdll!NtClose` at `0x18005d118`
- `ntdll!NtClose` at `0x18005d1d4`
- `ntdll!NtClose` at `0x18005d328`
- `ntdll!NtClose` at `0x18005d388`
- `ntdll!NtClose` at `0x18005d3db`
- `ntdll!NtQueryKey` at `0x18005d316`
- `ntdll!NtQueryKey` at `0x18005d316`
- `ntdll!RtlFreeHeap` at `0x18005cf11`
- `ntdll!RtlFreeHeap` at `0x18005cf7e`
- `ntdll!RtlFreeHeap` at `0x18005d2c4`
- `ntdll!RtlFreeHeap` at `0x18005d35c`
- `ntdll!RtlFreeHeap` at `0x18005d3b3`
- `ntdll!RtlFreeHeap` at `0x18019af07`
- `ntdll!RtlFreeHeap` at `0x18019af47`
- `ntdll!RtlFreeHeap` at `0x18019b10c`
- `ntdll!RtlFreeHeap` at `0x18019b156`
- `ntdll!RtlFreeHeap` at `0x18005cf11`
- `ntdll!RtlFreeHeap` at `0x18005cf7e`
- `ntdll!RtlFreeHeap` at `0x18005d2c4`
- `ntdll!RtlFreeHeap` at `0x18005d35c`
- `ntdll!RtlFreeHeap` at `0x18005d3b3`
- `ntdll!RtlFreeHeap` at `0x18019af07`
- `ntdll!RtlFreeHeap` at `0x18019af47`
- `ntdll!RtlFreeHeap` at `0x18019b10c`
- `ntdll!RtlFreeHeap` at `0x18019b156`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18005d0a2`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18005d0a2`
- `ntdll!RtlAllocateHeap` at `0x18005d205`
- `ntdll!RtlAllocateHeap` at `0x18019ad94`
- `ntdll!RtlAllocateHeap` at `0x18019ae18`
- `ntdll!RtlAllocateHeap` at `0x18019af8a`
- `ntdll!RtlAllocateHeap` at `0x18019b011`
- `ntdll!RtlAllocateHeap` at `0x18005d205`
- `ntdll!RtlAllocateHeap` at `0x18019ad94`
- `ntdll!RtlAllocateHeap` at `0x18019ae18`
- `ntdll!RtlAllocateHeap` at `0x18019af8a`
- `ntdll!RtlAllocateHeap` at `0x18019b011`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvCreateRegEntry` at `0x18005d0e3`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvCreateRegEntry` at `0x18005d0e3`

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
0x18005cc70  push    rbp
0x18005cc72  push    rbx
0x18005cc73  push    rsi
0x18005cc74  push    rdi
0x18005cc75  push    r12
0x18005cc77  push    r13
0x18005cc79  push    r14
0x18005cc7b  push    r15
0x18005cc7d  lea     rbp, [rsp-228h]
0x18005cc85  sub     rsp, 328h
0x18005cc8c  movaps  [rsp+360h+var_50], xmm6
0x18005cc94  mov     rax, cs:__security_cookie
0x18005cc9b  xor     rax, rsp
0x18005cc9e  mov     [rbp+260h+var_60], rax
0x18005cca5  mov     rax, [rbp+260h+arg_48]
0x18005ccac  xorps   xmm0, xmm0
0x18005ccaf  mov     r13, [rbp+260h+arg_28]
0x18005ccb6  xor     esi, esi
0x18005ccb8  mov     r12, [rbp+260h+arg_38]
0x18005ccbf  mov     r15, r8
0x18005ccc2  mov     [rbp+260h+var_2C8], rax
0x18005ccc6  mov     rbx, rdx
0x18005ccc9  mov     rax, [rbp+260h+arg_40]
0x18005ccd0  mov     r14, rcx
0x18005ccd3  mov     [rbp+260h+var_248], rax
0x18005ccd7  xor     edx, edx; Val
0x18005ccd9  xor     eax, eax
0x18005ccdb  mov     [rsp+360h+Handle], rcx
0x18005cce0  movups  [rbp+260h+var_230], xmm0
0x18005cce4  mov     r8d, 180h; Size
0x18005ccea  mov     [rbp+260h+var_1F0], rax
0x18005ccee  lea     rcx, [rbp+260h+var_1E0]; void *
0x18005ccf5  mov     [rbp+260h+P], rax
0x18005ccf9  mov     edi, r9d
0x18005ccfc  mov     [rsp+360h+var_2E8], r9d
0x18005cd01  movups  [rbp+260h+var_240], xmm0
0x18005cd05  mov     [rbp+260h+var_2A0], rsi
0x18005cd09  movups  [rbp+260h+var_230+0Ch], xmm0
0x18005cd0d  mov     [rbp+260h+var_2D0], esi
0x18005cd10  movups  [rbp+260h+KeyInformation], xmm0
0x18005cd14  mov     [rbp+260h+var_290], esi
0x18005cd17  movups  [rbp+260h+var_200], xmm0
0x18005cd1b  movups  [rbp+260h+var_2C0], xmm0
0x18005cd1f  call    memset_0
0x18005cd24  movzx   eax, word ptr [rbx]
0x18005cd27  mov     [rbp+260h+var_2A0+8], rsi
0x18005cd2b  mov     [rsp+360h+var_2F0], rsi
0x18005cd30  movups  xmm6, xmmword ptr [rbx]
0x18005cd33  cmp     eax, 2
0x18005cd36  jb      loc_18005CF5A
0x18005cd3c  mov     rcx, [rbx+8]
0x18005cd40  test    rcx, rcx
0x18005cd43  jz      loc_18005CF5A
0x18005cd49  test    al, 1
0x18005cd4b  jnz     loc_18005CF5A
0x18005cd51  shr     rax, 1
0x18005cd54  cmp     [rcx+rax*2-2], si
0x18005cd59  jnz     loc_18005CF5A
0x18005cd5f  test    r12, r12
0x18005cd62  jz      loc_18005CF5A
0x18005cd68  test    r15, r15
0x18005cd6b  jz      loc_18005CF5A
0x18005cd71  movzx   eax, word ptr [r15]
0x18005cd75  test    al, 1
0x18005cd77  jnz     loc_18005CF5A
0x18005cd7d  test    ax, ax
0x18005cd80  jnz     loc_18005D13C
0x18005cd86  mov     [r12], rsi
0x18005cd8a  mov     eax, 0FFFEh
0x18005cd8f  add     [rbx], ax
0x18005cd92  mov     rax, [rbx+8]
0x18005cd96  cmp     word ptr [rax], 5Ch ; '\'
0x18005cd9a  jz      loc_18005D2DA
0x18005cda0  mov     eax, 1
0x18005cda5  mov     [rsp+360h+var_304], eax
0x18005cda9  mov     [rsp+360h+var_2E4], eax
0x18005cdad  movzx   eax, word ptr [r15]
0x18005cdb1  test    ax, ax
0x18005cdb4  jz      short loc_18005CDBE
0x18005cdb6  sub     ax, 2
0x18005cdba  mov     [r15], ax
0x18005cdbe  mov     eax, 40h ; '@'
0x18005cdc3  mov     [rbp+260h+var_2CC], eax
0x18005cdc6  test    r13, r13
0x18005cdc9  jnz     loc_18005D0F4
0x18005cdcf  test    dil, 8
0x18005cdd3  jnz     loc_18005D2E4
0x18005cdd9  test    r14b, 2
0x18005cddd  jnz     loc_18005D14B
0x18005cde3  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005cdea  jnz     loc_18005D274
0x18005cdf0  xorps   xmm0, xmm0
0x18005cdf3  mov     [rsp+360h+var_2F0], r14
0x18005cdf8  xor     eax, eax
0x18005cdfa  mov     [rsp+360h+Handle], rbx
0x18005cdff  movups  [rbp+260h+var_2C0], xmm0
0x18005ce03  mov     [rbp+260h+P], rax
0x18005ce07  mov     rsi, r14
0x18005ce0a  mov     r8, rbx
0x18005ce0d  mov     eax, 1
0x18005ce12  mov     edi, 0C0000034h
0x18005ce17  test    eax, eax
0x18005ce19  jz      loc_18005CEA9
0x18005ce1f  test    r13, r13
0x18005ce22  jnz     loc_18005D08E
0x18005ce28  mov     eax, [rbp+260h+var_2CC]
0x18005ce2b  xor     ecx, ecx
0x18005ce2d  mov     dword ptr [rbp+260h+var_240], 30h ; '0'
0x18005ce34  mov     qword ptr [rbp+260h+var_240+8], rsi
0x18005ce38  mov     dword ptr [rbp+260h+var_230+8], eax
0x18005ce3b  mov     qword ptr [rbp+260h+var_230], r8
0x18005ce3f  test    r13, r13
0x18005ce42  jnz     loc_18005D108
0x18005ce48  mov     [rbp+260h+var_220], rcx
0x18005ce4c  mov     rax, [rbp+260h+var_2C8]
0x18005ce50  lea     r8, [rbp+260h+var_240]
0x18005ce54  mov     edx, [rbp+260h+arg_20]
0x18005ce5a  mov     [rbp+260h+var_218], rcx
0x18005ce5e  test    rax, rax
0x18005ce61  jnz     loc_18005D129
0x18005ce67  lea     rax, [rbp+260h+var_2D0]
0x18005ce6b  mov     [rsp+360h+var_328], rax
0x18005ce70  mov     [rsp+360h+var_330], rcx
0x18005ce75  mov     eax, [rsp+360h+var_2E8]
0x18005ce79  mov     rcx, r12
0x18005ce7c  mov     dword ptr [rsp+360h+var_338], eax
0x18005ce80  mov     [rsp+360h+ResultLength], r15
0x18005ce85  call    Wow64NtCreateKey
0x18005ce8a  mov     edi, eax
0x18005ce8c  cmp     eax, 40000016h
0x18005ce91  jz      loc_18005D2FA
0x18005ce97  test    eax, eax
0x18005ce99  js      short loc_18005CEA5
0x18005ce9b  cmp     [rbp+260h+var_2D0], 1
0x18005ce9f  jz      loc_18005D0C0
0x18005cea5  mov     eax, [rsp+360h+var_304]
0x18005cea9  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005ceb0  jnz     loc_18005CF8F
0x18005ceb6  test    edi, edi
0x18005ceb8  js      loc_18005CFE6
0x18005cebe  mov     rcx, [rbp+260h+var_248]
0x18005cec2  test    rcx, rcx
0x18005cec5  jz      short loc_18005CECC
0x18005cec7  mov     eax, [rbp+260h+var_2D0]
0x18005ceca  mov     [rcx], eax
0x18005cecc  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005ced3  jnz     loc_18005D02F
0x18005ced9  test    edi, edi
0x18005cedb  js      short loc_18005CEE3
0x18005cedd  test    byte ptr [rbp+260h+var_2C0], 4
0x18005cee1  jnz     short loc_18005CF61
0x18005cee3  test    rsi, rsi
0x18005cee6  jz      short loc_18005CEF1
0x18005cee8  cmp     rsi, r14
0x18005ceeb  jnz     loc_18005D115
0x18005cef1  cmp     [rbp+260h+var_2A0+8], 0
0x18005cef6  jnz     short loc_18005CF6B
0x18005cef8  test    byte ptr [rbp+260h+var_2C0], 20h
0x18005cefc  jz      short loc_18005CF1D
0x18005cefe  mov     rcx, gs:60h
0x18005cf07  xor     edx, edx; Flags
0x18005cf09  mov     r8, [rbp+260h+P]; P
0x18005cf0d  mov     rcx, [rcx+30h]; HeapHandle
0x18005cf11  call    cs:__imp_RtlFreeHeap
0x18005cf18  nop     dword ptr [rax+rax+00h]
0x18005cf1d  mov     ecx, edi; Status
0x18005cf1f  movups  xmmword ptr [rbx], xmm6
0x18005cf22  call    cs:__imp_RtlNtStatusToDosError
0x18005cf29  nop     dword ptr [rax+rax+00h]
0x18005cf2e  mov     rcx, [rbp+260h+var_60]
0x18005cf35  xor     rcx, rsp; StackCookie
0x18005cf38  call    __security_check_cookie
0x18005cf3d  movaps  xmm6, [rsp+360h+var_50]
0x18005cf45  add     rsp, 328h
0x18005cf4c  pop     r15
0x18005cf4e  pop     r14
0x18005cf50  pop     r13
0x18005cf52  pop     r12
0x18005cf54  pop     rdi
0x18005cf55  pop     rsi
0x18005cf56  pop     rbx
0x18005cf57  pop     rbp
0x18005cf58  retn
0x18005cf5a  mov     edi, 0C000000Dh
0x18005cf5f  jmp     short loc_18005CEF8
0x18005cf61  or      qword ptr [r12], 2
0x18005cf66  jmp     loc_18005CEE3
0x18005cf6b  mov     rcx, gs:60h
0x18005cf74  xor     edx, edx; Flags
0x18005cf76  mov     r8, [rbp+260h+var_2A0+8]; P
0x18005cf7a  mov     rcx, [rcx+30h]; HeapHandle
0x18005cf7e  call    cs:__imp_RtlFreeHeap
0x18005cf85  nop     dword ptr [rax+rax+00h]
0x18005cf8a  jmp     loc_18005CEF8
0x18005cf8f  test    eax, eax
0x18005cf91  jz      loc_18005CEB6
0x18005cf97  cmp     edi, 0C0000022h
0x18005cf9d  jnz     loc_18005CEB6
0x18005cfa3  test    byte ptr [rbp+260h+var_2C0], 4
0x18005cfa7  jz      short loc_18005CFE6
0x18005cfa9  cmp     [rsp+360h+var_2E4], 0
0x18005cfae  jz      short loc_18005CFE6
0x18005cfb0  cmp     [rbp+260h+var_2A0+8], 0
0x18005cfb5  jnz     loc_18005D349
0x18005cfbb  xor     ecx, ecx
0x18005cfbd  test    byte ptr [rbp+260h+var_2C0], 4
0x18005cfc1  mov     edi, 0C0000022h
0x18005cfc6  mov     qword ptr [rbp+260h+SourceString.Length], rcx
0x18005cfca  mov     [rbp+260h+SourceString.Buffer], rcx
0x18005cfce  jnz     loc_18005D377
0x18005cfd4  mov     r8, [rsp+360h+Handle]
0x18005cfd9  test    edi, edi
0x18005cfdb  jns     loc_18005CE12
0x18005cfe1  jmp     loc_18005CEE3
0x18005cfe6  mov     rax, [rbp+260h+var_2C8]
0x18005cfea  mov     r8, r15
0x18005cfed  mov     r9d, [rsp+360h+var_2E8]
0x18005cff2  mov     rcx, rsi
0x18005cff5  mov     rdx, [rsp+360h+Handle]
0x18005cffa  mov     [rsp+360h+var_318], rax
0x18005cfff  mov     eax, [rbp+260h+var_2CC]
0x18005d002  mov     [rsp+360h+var_320], eax
0x18005d006  mov     rax, [rbp+260h+var_248]
0x18005d00a  mov     [rsp+360h+var_328], rax
0x18005d00f  mov     eax, [rbp+260h+arg_20]
0x18005d015  mov     [rsp+360h+var_330], r12
0x18005d01a  mov     [rsp+360h+var_338], r13
0x18005d01f  mov     dword ptr [rsp+360h+ResultLength], eax
0x18005d023  call    BaseRegCreateMultipartKey
0x18005d028  mov     edi, eax
0x18005d02a  jmp     loc_18005CECC
0x18005d02f  cmp     edi, 0C0000022h
0x18005d035  jnz     loc_18005CED9
0x18005d03b  test    byte ptr [rbp+260h+var_2C0], 4
0x18005d03f  jz      loc_18005CEE3
0x18005d045  cmp     [rsp+360h+var_2E4], 0
0x18005d04a  jz      loc_18005CEE3
0x18005d050  cmp     [rbp+260h+var_2A0+8], 0
0x18005d055  jnz     loc_18005D3A0
0x18005d05b  xor     ecx, ecx
0x18005d05d  test    byte ptr [rbp+260h+var_2C0], 4
0x18005d061  mov     edi, 0C0000022h
0x18005d066  mov     [rsp+360h+var_300], rcx
0x18005d06b  mov     [rsp+360h+var_300+8], rcx
0x18005d070  jnz     loc_18005D3CA
0x18005d076  mov     r8, [rsp+360h+Handle]
0x18005d07b  mov     [rsp+360h+var_304], ecx
0x18005d07f  mov     eax, ecx
0x18005d081  test    edi, edi
0x18005d083  jns     loc_18005CE12
0x18005d089  jmp     loc_18005CEE3
0x18005d08e  mov     rcx, [r13+8]; SecurityDescriptorInput
0x18005d092  test    rcx, rcx
0x18005d095  jz      loc_18005CE28
0x18005d09b  mov     edx, [r13+10h]; SecurityDescriptorLength
0x18005d09f  xor     r8d, r8d; RequiredInformation
0x18005d0a2  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18005d0a9  nop     dword ptr [rax+rax+00h]
0x18005d0ae  test    al, al
0x18005d0b0  jz      loc_18005D3F3
0x18005d0b6  mov     r8, [rsp+360h+Handle]
0x18005d0bb  jmp     loc_18005CE28
0x18005d0c0  call    IsTermsrvDeleteKeyPresent
0x18005d0c5  test    al, al
0x18005d0c7  jz      loc_18005CEA5
0x18005d0cd  mov     eax, [rsp+360h+var_2E8]
0x18005d0d1  lea     rdx, [rbp+260h+var_240]
0x18005d0d5  mov     rcx, [r12]
0x18005d0d9  mov     r9, r15
0x18005d0dc  xor     r8d, r8d
0x18005d0df  mov     dword ptr [rsp+360h+ResultLength], eax
0x18005d0e3  call    cs:__imp_TermsrvCreateRegEntry
0x18005d0ea  nop     dword ptr [rax+rax+00h]
0x18005d0ef  jmp     loc_18005CEA5
0x18005d0f4  cmp     [r13+18h], sil
0x18005d0f8  mov     ecx, 42h ; 'B'
0x18005d0fd  cmovnz  eax, ecx
0x18005d100  mov     [rbp+260h+var_2CC], eax
0x18005d103  jmp     loc_18005CDCF
0x18005d108  mov     rax, [r13+8]
0x18005d10c  mov     [rbp+260h+var_220], rax
0x18005d110  jmp     loc_18005CE4C
0x18005d115  mov     rcx, rsi; Handle
0x18005d118  call    cs:__imp_NtClose
0x18005d11f  nop     dword ptr [rax+rax+00h]
0x18005d124  jmp     loc_18005CEF1
0x18005d129  lea     rcx, [rbp+260h+var_2D0]
0x18005d12d  mov     [rsp+360h+var_328], rcx
0x18005d132  mov     [rsp+360h+var_330], rax
0x18005d137  jmp     loc_18005CE75
0x18005d13c  cmp     [r15+8], rsi
0x18005d140  jnz     loc_18005CD86
0x18005d146  jmp     loc_18005CF5A
0x18005d14b  and     dword ptr [rbp+260h+var_2C0], 0FFFFFFDFh
0x18005d14f  lea     rax, [rbp+260h+var_1E0]
0x18005d156  lea     r8, [rbp+260h+var_2C0]
0x18005d15a  mov     [rbp+260h+P], rax
0x18005d15e  mov     rdx, rbx; Source
0x18005d161  mov     dword ptr [rbp+260h+var_2C0+0Ch], 180h
0x18005d168  mov     rcx, r14; KeyHandle
  ... truncated ...
```
