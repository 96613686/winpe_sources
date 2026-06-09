# Pku2uAllocateContext(int,_PKU2U_SECONDARY_CREDENTIAL *,_UNICODE_STRING *,ulong,_PKU2U_CONTEXT * *)

- ea: `0x18000b6c0`
- end: `0x18000bcc9`
- name: `?Pku2uAllocateContext@@YAJHPEAU_PKU2U_SECONDARY_CREDENTIAL@@PEAU_UNICODE_STRING@@KPEAPEAU_PKU2U_CONTEXT@@@Z`
- size: `1545`
- prototype: `int(int, struct _PKU2U_SECONDARY_CREDENTIAL *, struct _UNICODE_STRING *, unsigned int, struct _PKU2U_CONTEXT **)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f40`
- `0x180009070`

## callees

- `0x180005300`
- `0x18000a340`
- `0x18000b6c0`
- `0x180011410`
- `0x1800139e0`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x18002adb0`
- `0x18002b158`
- `0x18002b220`
- `0x18002b2f4`
- `0x18002b744`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b89d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b8b5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b8d0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b89d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b8b5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000b8d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcab`
- `ntdll!RtlInitUnicodeString` at `0x18000b7d7`
- `ntdll!RtlInitUnicodeString` at `0x18000b8f0`
- `ntdll!RtlInitUnicodeString` at `0x18000b7d7`
- `ntdll!RtlInitUnicodeString` at `0x18000b8f0`
- `SspiCli!CredUnmarshalTargetInfo` at `0x18000b757`
- `SspiCli!CredUnmarshalTargetInfo` at `0x18000b757`
- `LSASRV!LsaIIsLocalHost` at `0x18000b8fb`
- `LSASRV!LsaIIsLocalHost` at `0x18000b922`
- `LSASRV!LsaIIsLocalHost` at `0x18000b8fb`
- `LSASRV!LsaIIsLocalHost` at `0x18000b922`

## string_xrefs

- `0x18000b9e2`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uAllocateContext(
        int a1,
        struct _PKU2U_SECONDARY_CREDENTIAL *a2,
        struct _UNICODE_STRING *a3,
        int a4,
        struct _PKU2U_CONTEXT **a5)
{
  struct _KERB_INTERNAL_NAME *v5; // rsi
  PWSTR v11; // rcx
  unsigned int MaximumLength; // eax
  int Length; // r8d
  int v14; // eax
  int v15; // ebx
  PVOID *v16; // r10
  const WCHAR *v17; // rdx
  struct _UNICODE_STRING *p_DestinationString; // rbp
  int v19; // eax
  const wchar_t *Buffer; // rcx
  wchar_t *v21; // rax
  wchar_t *v22; // rbx
  wchar_t *v23; // rax
  wchar_t *v24; // rsi
  wchar_t *v25; // rax
  wchar_t *v26; // rdi
  int v27; // eax
  __int16 v28; // ax
  int v29; // edx
  int v30; // r8d
  int v31; // ecx
  int v32; // edx
  int v33; // ecx
  int v34; // ecx
  int v35; // edx
  int v36; // ecx
  int v37; // ebx
  _DWORD *v38; // rcx
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r9
  __int64 v42; // rdi
  void *v43; // rax
  int v44; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING v46; // [rsp+38h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-40h] BYREF
  struct _KERB_INTERNAL_NAME *v48; // [rsp+A0h] [rbp+18h] BYREF

  v5 = 0;
  v48 = 0;
  DestinationString = 0;
  if ( a1 && (!a3 || !a3->Length) )
    return 2148074243LL;
  hMem = 0;
  if ( !a3
    || (v11 = a3->Buffer) == 0
    || (MaximumLength = a3->MaximumLength,
        Length = a3->Length,
        (unsigned __int16)Length >= (unsigned __int16)MaximumLength)
    || (int)(MaximumLength - Length) < 12 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
    if ( hMem && (v17 = *(const WCHAR **)hMem) != 0 && *v17 )
    {
      RtlInitUnicodeString(&DestinationString, v17);
      p_DestinationString = &DestinationString;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      p_DestinationString = a3;
      if ( !a3 )
        goto LABEL_48;
    }
    if ( p_DestinationString->Length )
    {
      v19 = Pku2uProcessTargetNames(p_DestinationString, &v48);
      v15 = v19;
      if ( v19 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19);
        v5 = v48;
        goto LABEL_107;
      }
      if ( *((_DWORD *)a2 + 8) == 1 && !Pku2uGlobalSupportLocalHost )
      {
        Buffer = p_DestinationString->Buffer;
        v46 = 0;
        v21 = wcschr(Buffer, 0x2Fu);
        if ( v21 )
        {
          v22 = v21 + 1;
          v23 = wcschr(v21 + 1, 0x2Fu);
          v24 = v23;
          if ( v23 )
            *v23 = 0;
          v25 = wcschr(v22, 0x3Au);
          v26 = v25;
          if ( v25 )
            *v25 = 0;
          if ( v24 )
          {
            RtlInitUnicodeString(&v46, v22);
            v27 = LsaIIsLocalHost(&v46);
            *v24 = 47;
          }
          else
          {
            v28 = LOWORD(p_DestinationString->Buffer) - (_WORD)v22;
            v46.Buffer = v22;
            v46.Length = p_DestinationString->Length + v28;
            v46.MaximumLength = v46.Length;
            v27 = LsaIIsLocalHost(&v46);
          }
          if ( v26 )
            *v26 = 58;
          if ( v27 )
          {
            v5 = v48;
            v15 = -2146893053;
            goto LABEL_107;
          }
        }
      }
      v5 = v48;
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_48:
    if ( a1 )
    {
      v29 = a4 & 2 | 0x10008;
      if ( (a4 & 8) == 0 )
        v29 = a4 & 2;
      v30 = v29 | 0x10004;
      if ( (a4 & 4) == 0 )
        v30 = v29;
      v31 = v30 | 0x10000;
      if ( (a4 & 0x10000) == 0 )
        v31 = v30;
      v32 = v31 | 0x1001C;
      if ( (a4 & 0x10) == 0 )
        v32 = v31;
      v33 = v32 | 0x200;
      if ( (a4 & 0x200) == 0 )
        v33 = v32;
      v34 = v33 | 0x4000;
      if ( (a4 & 0x400) != 0 )
      {
        if ( (a4 & 0x800) != 0 )
        {
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
            WPP_SF_sd(
              (unsigned int)v16[2],
              13,
              (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
              (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
              240);
          v15 = -2146893054;
          goto LABEL_107;
        }
        v34 |= 0x400u;
      }
      v35 = v34 | 0x800;
      if ( (a4 & 0x800) == 0 )
        v35 = v34;
      v36 = v35 | 0x20000;
      if ( (a4 & 0x20000) == 0 )
        v36 = v35;
      v37 = v36 | 0x1000200;
      if ( (a4 & 0x1000000) == 0 )
        v37 = v36;
      v38 = (_DWORD *)*((_QWORD *)a2 + 3);
      v39 = v38[13];
      if ( (v39 & 2) == 0 )
      {
        v15 = -2146893054;
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
        {
          v40 = 14;
          v41 = v39;
LABEL_76:
          WPP_SF_d(v16[2], v40, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v41);
          goto LABEL_107;
        }
        goto LABEL_107;
      }
      if ( (v39 & 0x10) != 0 && *((_DWORD *)a2 + 8) )
      {
        v15 = -2146893042;
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
          WPP_SF_(v16[2], 15, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
        goto LABEL_107;
      }
      if ( *((_DWORD *)a2 + 8) == 1 && v38[6] == 997 && !v38[7] )
      {
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
          WPP_SF_(v16[2], 16, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
        v15 = -2146893042;
        goto LABEL_107;
      }
    }
    else
    {
      v37 = 0;
      v41 = *(unsigned int *)(*((_QWORD *)a2 + 3) + 52LL);
      if ( (v41 & 1) == 0 )
      {
        v15 = -2146893054;
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
        {
          v40 = 17;
          goto LABEL_76;
        }
LABEL_107:
        if ( v5 )
        {
          if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
            (*(void (__fastcall **)(struct _KERB_INTERNAL_NAME *))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL))(v5);
          else
            (*(void (__fastcall **)(struct _KERB_INTERNAL_NAME *))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL))(v5);
        }
        goto LABEL_111;
      }
    }
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
    {
      v42 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(400);
    }
    else
    {
      v43 = (void *)(**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(400);
      v42 = (__int64)v43;
      if ( v43 )
      {
        memset_0(v43, 0, 0x190u);
        goto LABEL_99;
      }
    }
    if ( !v42 )
    {
      v15 = -1073741801;
      goto LABEL_107;
    }
LABEL_99:
    *(_DWORD *)(v42 + 56) = a1;
    *(_QWORD *)(v42 + 80) = v5;
    *(_DWORD *)(v42 + 68) = 0;
    v5 = 0;
    *(_DWORD *)(v42 + 8) = 1;
    *(_QWORD *)v42 = 0x5458544155554B50LL;
    *(_DWORD *)(v42 + 60) = a4;
    *(_DWORD *)(v42 + 64) = v37;
    Pku2uReferenceSecondaryCredential(a2);
    *(_QWORD *)(v42 + 16) = a2;
    *(_DWORD *)(v42 + 68) = 0;
    *(union _LARGE_INTEGER *)(v42 + 48) = Pku2uGlobalWillNeverTime;
    *(_QWORD *)(v42 + 312) = v42 + 304;
    *(_QWORD *)(v42 + 304) = v42 + 304;
    v15 = KerbDuplicateStringEx((struct _UNICODE_STRING *)(v42 + 88), p_DestinationString, 1u, 0);
    if ( v15 >= 0 )
    {
      v15 = KerbDuplicateStringEx((struct _UNICODE_STRING *)(v42 + 104), a3, 0, 1u);
      if ( v15 >= 0 )
      {
        *(_DWORD *)(v42 + 392) = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
        {
          v44 = 2;
          if ( !*(_DWORD *)(v42 + 56) )
            v44 = 4;
          *(_DWORD *)(v42 + 40) = v44;
        }
        v15 = 0;
        *a5 = (struct _PKU2U_CONTEXT *)v42;
        goto LABEL_111;
      }
    }
    Pku2uFreeContext((struct _PKU2U_CONTEXT *)v42);
    goto LABEL_107;
  }
  v14 = CredUnmarshalTargetInfo(v11, MaximumLength, &hMem, 0);
  if ( v14 < 0 )
  {
    v15 = 0;
    if ( v14 != -1073741811 )
      v15 = v14;
    goto LABEL_16;
  }
  v15 = v14;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_ZS(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_QWORD *)hMem);
LABEL_16:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 >= 0 )
    goto LABEL_20;
LABEL_111:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000b6c0  mov     [rsp+arg_18], rbx
0x18000b6c5  push    rsi
0x18000b6c6  push    r12
0x18000b6c8  push    r13
0x18000b6ca  push    r14
0x18000b6cc  push    r15
0x18000b6ce  sub     rsp, 60h
0x18000b6d2  xor     esi, esi
0x18000b6d4  xorps   xmm0, xmm0
0x18000b6d7  mov     [rsp+88h+arg_10], rsi
0x18000b6df  mov     r13d, r9d
0x18000b6e2  mov     r14, r8
0x18000b6e5  mov     r15, rdx
0x18000b6e8  mov     r12d, ecx
0x18000b6eb  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18000b6f0  test    ecx, ecx
0x18000b6f2  jz      short loc_18000B709
0x18000b6f4  test    r8, r8
0x18000b6f7  jz      short loc_18000B6FF
0x18000b6f9  cmp     [r8], si
0x18000b6fd  jnz     short loc_18000B709
0x18000b6ff  mov     eax, 80090303h
0x18000b704  jmp     loc_18000BCB3
0x18000b709  mov     [rsp+88h+arg_8], rdi
0x18000b711  lea     rdi, WPP_GLOBAL_Control
0x18000b718  mov     [rsp+88h+hMem], rsi
0x18000b71d  test    r14, r14
0x18000b720  jz      loc_18000B7AC
0x18000b726  mov     rcx, [r8+8]
0x18000b72a  test    rcx, rcx
0x18000b72d  jz      short loc_18000B7AC
0x18000b72f  movzx   eax, word ptr [r8+2]
0x18000b734  movzx   r8d, word ptr [r8]
0x18000b738  cmp     r8w, ax
0x18000b73c  jnb     short loc_18000B7AC
0x18000b73e  mov     edx, eax
0x18000b740  mov     eax, r8d
0x18000b743  mov     r8d, edx
0x18000b746  sub     r8d, eax
0x18000b749  cmp     r8d, 0Ch
0x18000b74d  jl      short loc_18000B7AC
0x18000b74f  xor     r9d, r9d
0x18000b752  lea     r8, [rsp+88h+hMem]
0x18000b757  call    cs:__imp_CredUnmarshalTargetInfo
0x18000b75d  test    eax, eax
0x18000b75f  jns     short loc_18000B76D
0x18000b761  xor     ebx, ebx
0x18000b763  cmp     eax, 0C000000Dh
0x18000b768  cmovnz  ebx, eax
0x18000b76b  jmp     short loc_18000B79B
0x18000b76d  mov     ebx, eax
0x18000b76f  mov     r10, cs:WPP_GLOBAL_Control
0x18000b776  cmp     r10, rdi
0x18000b779  jz      short loc_18000B7A2
0x18000b77b  test    byte ptr [r10+1Ch], 2
0x18000b780  jz      short loc_18000B7A2
0x18000b782  mov     rax, [rsp+88h+hMem]
0x18000b787  mov     r9, r14
0x18000b78a  mov     rcx, [r10+10h]; LoggerHandle
0x18000b78e  mov     rdx, [rax]
0x18000b791  mov     qword ptr [rsp+88h+var_68], rdx; __int64
0x18000b796  call    WPP_SF_ZS
0x18000b79b  mov     r10, cs:WPP_GLOBAL_Control
0x18000b7a2  test    ebx, ebx
0x18000b7a4  js      loc_18000BC99
0x18000b7aa  jmp     short loc_18000B7B3
0x18000b7ac  mov     r10, cs:WPP_GLOBAL_Control
0x18000b7b3  mov     rcx, [rsp+88h+hMem]
0x18000b7b8  mov     [rsp+88h+arg_0], rbp
0x18000b7c0  test    rcx, rcx
0x18000b7c3  jz      short loc_18000B818
0x18000b7c5  mov     rdx, [rcx]; SourceString
0x18000b7c8  test    rdx, rdx
0x18000b7cb  jz      short loc_18000B818
0x18000b7cd  cmp     [rdx], si
0x18000b7d0  jz      short loc_18000B818
0x18000b7d2  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18000b7d7  call    cs:__imp_RtlInitUnicodeString
0x18000b7dd  lea     rbp, [rsp+88h+DestinationString]
0x18000b7e2  mov     r10, cs:WPP_GLOBAL_Control
0x18000b7e9  cmp     r10, rdi
0x18000b7ec  jz      short loc_18000B824
0x18000b7ee  test    byte ptr [r10+1Ch], 2
0x18000b7f3  jz      short loc_18000B824
0x18000b7f5  mov     rcx, [r10+10h]; LoggerHandle
0x18000b7f9  lea     r9, [rsp+88h+DestinationString]
0x18000b7fe  mov     edx, 0Bh
0x18000b803  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18000b80a  call    WPP_SF_Z
0x18000b80f  mov     r10, cs:WPP_GLOBAL_Control
0x18000b816  jmp     short loc_18000B824
0x18000b818  mov     rbp, r14
0x18000b81b  test    r14, r14
0x18000b81e  jz      loc_18000B95E
0x18000b824  cmp     [rbp+0], si
0x18000b828  jz      loc_18000B95E
0x18000b82e  lea     rdx, [rsp+88h+arg_10]; struct _KERB_INTERNAL_NAME **
0x18000b836  mov     rcx, rbp; struct _UNICODE_STRING *
0x18000b839  call    ?Pku2uProcessTargetNames@@YAJPEAU_UNICODE_STRING@@PEAPEAU_KERB_INTERNAL_NAME@@@Z; Pku2uProcessTargetNames(_UNICODE_STRING *,_KERB_INTERNAL_NAME * *)
0x18000b83e  mov     ebx, eax
0x18000b840  test    eax, eax
0x18000b842  jns     short loc_18000B873
0x18000b844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b84b  cmp     rcx, rdi
0x18000b84e  jz      short loc_18000B866
0x18000b850  test    byte ptr [rcx+1Ch], 2
0x18000b854  jz      short loc_18000B866
0x18000b856  mov     rcx, [rcx+10h]; LoggerHandle
0x18000b85a  mov     r9, rbp
0x18000b85d  mov     dword ptr [rsp+88h+var_68], eax; char
0x18000b861  call    WPP_SF_ZD
0x18000b866  mov     rsi, [rsp+88h+arg_10]
0x18000b86e  jmp     loc_18000BC59
0x18000b873  cmp     dword ptr [r15+20h], 1
0x18000b878  jnz     loc_18000B94F
0x18000b87e  cmp     cs:?Pku2uGlobalSupportLocalHost@@3KA, esi; ulong Pku2uGlobalSupportLocalHost
0x18000b884  jnz     loc_18000B94F
0x18000b88a  mov     rcx, [rbp+8]; Str
0x18000b88e  xorps   xmm0, xmm0
0x18000b891  mov     esi, 2Fh ; '/'
0x18000b896  mov     edx, esi; Ch
0x18000b898  movups  xmmword ptr [rsp+88h+var_50.Length], xmm0
0x18000b89d  call    cs:__imp_wcschr
0x18000b8a3  test    rax, rax
0x18000b8a6  jz      loc_18000B94F
0x18000b8ac  lea     rbx, [rax+2]
0x18000b8b0  mov     edx, esi; Ch
0x18000b8b2  mov     rcx, rbx; Str
0x18000b8b5  call    cs:__imp_wcschr
0x18000b8bb  mov     rsi, rax
0x18000b8be  test    rax, rax
0x18000b8c1  jz      short loc_18000B8C8
0x18000b8c3  xor     ecx, ecx
0x18000b8c5  mov     [rax], cx
0x18000b8c8  mov     edx, 3Ah ; ':'; Ch
0x18000b8cd  mov     rcx, rbx; Str
0x18000b8d0  call    cs:__imp_wcschr
0x18000b8d6  mov     rdi, rax
0x18000b8d9  test    rax, rax
0x18000b8dc  jz      short loc_18000B8E3
0x18000b8de  xor     ecx, ecx
0x18000b8e0  mov     [rax], cx
0x18000b8e3  lea     rcx, [rsp+88h+var_50]; DestinationString
0x18000b8e8  test    rsi, rsi
0x18000b8eb  jz      short loc_18000B908
0x18000b8ed  mov     rdx, rbx; SourceString
0x18000b8f0  call    cs:__imp_RtlInitUnicodeString
0x18000b8f6  lea     rcx, [rsp+88h+var_50]
0x18000b8fb  call    cs:__imp_LsaIIsLocalHost
0x18000b901  mov     word ptr [rsi], 2Fh ; '/'
0x18000b906  jmp     short loc_18000B928
0x18000b908  movzx   eax, word ptr [rbp+8]
0x18000b90c  sub     ax, bx
0x18000b90f  mov     [rsp+88h+var_50.Buffer], rbx
0x18000b914  add     ax, [rbp+0]
0x18000b918  mov     [rsp+88h+var_50.Length], ax
0x18000b91d  mov     [rsp+88h+var_50.MaximumLength], ax
0x18000b922  call    cs:__imp_LsaIIsLocalHost
0x18000b928  test    rdi, rdi
0x18000b92b  jz      short loc_18000B932
0x18000b92d  mov     word ptr [rdi], 3Ah ; ':'
0x18000b932  test    eax, eax
0x18000b934  jz      short loc_18000B948
0x18000b936  mov     rsi, [rsp+88h+arg_10]
0x18000b93e  mov     ebx, 80090303h
0x18000b943  jmp     loc_18000BC59
0x18000b948  lea     rdi, WPP_GLOBAL_Control
0x18000b94f  mov     rsi, [rsp+88h+arg_10]
0x18000b957  mov     r10, cs:WPP_GLOBAL_Control
0x18000b95e  test    r12d, r12d
0x18000b961  jz      loc_18000BAF9
0x18000b967  mov     ecx, r13d
0x18000b96a  mov     eax, r13d
0x18000b96d  and     ecx, 2
0x18000b970  mov     edx, ecx
0x18000b972  or      edx, 10008h
0x18000b978  test    r13b, 8
0x18000b97c  cmovz   edx, ecx
0x18000b97f  mov     r8d, edx
0x18000b982  or      r8d, 10004h
0x18000b989  test    r13b, 4
0x18000b98d  cmovz   r8d, edx
0x18000b991  mov     ecx, r8d
0x18000b994  bts     ecx, 10h
0x18000b998  bt      r13d, 10h
0x18000b99d  cmovnb  ecx, r8d
0x18000b9a1  mov     edx, ecx
0x18000b9a3  or      edx, 1001Ch
0x18000b9a9  test    r13b, 10h
0x18000b9ad  cmovz   edx, ecx
0x18000b9b0  mov     ecx, edx
0x18000b9b2  bts     ecx, 9
0x18000b9b6  bt      r13d, 9
0x18000b9bb  cmovnb  ecx, edx
0x18000b9be  and     eax, 800h
0x18000b9c3  bts     ecx, 0Eh
0x18000b9c7  bt      r13d, 0Ah
0x18000b9cc  jnb     short loc_18000BA10
0x18000b9ce  test    eax, eax
0x18000b9d0  jz      short loc_18000BA0C
0x18000b9d2  cmp     r10, rdi
0x18000b9d5  jz      short loc_18000BA02
0x18000b9d7  test    byte ptr [r10+1Ch], 1
0x18000b9dc  jz      short loc_18000BA02
0x18000b9de  mov     rcx, [r10+10h]
0x18000b9e2  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\protocols\\pku2u"...
0x18000b9e9  mov     edx, 0Dh
0x18000b9ee  mov     dword ptr [rsp+88h+var_68], 0F0h
0x18000b9f6  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18000b9fd  call    WPP_SF_sd
0x18000ba02  mov     ebx, 80090302h
0x18000ba07  jmp     loc_18000BC59
0x18000ba0c  bts     ecx, 0Ah
0x18000ba10  mov     edx, ecx
0x18000ba12  bts     edx, 0Bh
0x18000ba16  test    eax, eax
0x18000ba18  cmovz   edx, ecx
0x18000ba1b  mov     ecx, edx
0x18000ba1d  bts     ecx, 11h
0x18000ba21  bt      r13d, 11h
0x18000ba26  cmovnb  ecx, edx
0x18000ba29  mov     ebx, ecx
0x18000ba2b  or      ebx, 1000200h
0x18000ba31  bt      r13d, 18h
0x18000ba36  cmovnb  ebx, ecx
0x18000ba39  mov     rcx, [r15+18h]
0x18000ba3d  mov     eax, [rcx+34h]
0x18000ba40  test    al, 2
0x18000ba42  jnz     short loc_18000BA7A
0x18000ba44  mov     ebx, 80090302h
0x18000ba49  cmp     r10, rdi
0x18000ba4c  jz      loc_18000BC59
0x18000ba52  test    byte ptr [r10+1Ch], 1
0x18000ba57  jz      loc_18000BC59
0x18000ba5d  mov     edx, 0Eh
0x18000ba62  mov     r9d, eax
0x18000ba65  mov     rcx, [r10+10h]
0x18000ba69  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18000ba70  call    WPP_SF_d
0x18000ba75  jmp     loc_18000BC59
0x18000ba7a  test    al, 10h
0x18000ba7c  jz      short loc_18000BAB8
0x18000ba7e  cmp     dword ptr [r15+20h], 0
0x18000ba83  jz      short loc_18000BAB8
0x18000ba85  mov     ebx, 8009030Eh
0x18000ba8a  cmp     r10, rdi
0x18000ba8d  jz      loc_18000BC59
0x18000ba93  test    byte ptr [r10+1Ch], 1
0x18000ba98  jz      loc_18000BC59
0x18000ba9e  mov     rcx, [r10+10h]
0x18000baa2  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18000baa9  mov     edx, 0Fh
0x18000baae  call    WPP_SF_
0x18000bab3  jmp     loc_18000BC59
0x18000bab8  cmp     dword ptr [r15+20h], 1
0x18000babd  jnz     short loc_18000BB2C
0x18000babf  cmp     dword ptr [rcx+18h], 3E5h
0x18000bac6  jnz     short loc_18000BB2C
0x18000bac8  cmp     dword ptr [rcx+1Ch], 0
0x18000bacc  jnz     short loc_18000BB2C
0x18000bace  cmp     r10, rdi
0x18000bad1  jz      short loc_18000BAEF
0x18000bad3  test    byte ptr [r10+1Ch], 1
0x18000bad8  jz      short loc_18000BAEF
0x18000bada  mov     rcx, [r10+10h]
0x18000bade  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18000bae5  mov     edx, 10h
0x18000baea  call    WPP_SF_
0x18000baef  mov     ebx, 8009030Eh
0x18000baf4  jmp     loc_18000BC59
0x18000baf9  mov     rax, [r15+18h]
0x18000bafd  xor     ebx, ebx
0x18000baff  mov     r9d, [rax+34h]
0x18000bb03  test    r9b, 1
0x18000bb07  jnz     short loc_18000BB2C
0x18000bb09  mov     ebx, 80090302h
0x18000bb0e  cmp     r10, rdi
0x18000bb11  jz      loc_18000BC59
0x18000bb17  test    byte ptr [r10+1Ch], 1
0x18000bb1c  jz      loc_18000BC59
0x18000bb22  mov     edx, 11h
0x18000bb27  jmp     loc_18000BA65
0x18000bb2c  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000bb33  cmp     dword ptr [rax+0D0h], 1
0x18000bb3a  jnz     short loc_18000BB66
0x18000bb3c  mov     rax, [rax+0F0h]
0x18000bb43  mov     ecx, 190h
0x18000bb48  mov     rax, [rax+180h]
0x18000bb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb54  mov     rdi, rax
0x18000bb57  test    rdi, rdi
0x18000bb5a  jnz     short loc_18000BB92
0x18000bb5c  mov     ebx, 0C0000017h
0x18000bb61  jmp     loc_18000BC59
0x18000bb66  mov     rax, [rax+0F8h]
0x18000bb6d  mov     ecx, 190h
0x18000bb72  mov     rax, [rax]
0x18000bb75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb7a  mov     rdi, rax
0x18000bb7d  test    rax, rax
  ... truncated ...
```
