# CFveApiBase::VerifyBindDataVolumeDpapi(bool *,_GUID *)

- ea: `0x18007682c`
- end: `0x180076b16`
- name: `?VerifyBindDataVolumeDpapi@CFveApiBase@@QEAAJPEA_NPEAU_GUID@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, bool *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f154`

## callees

- `0x18001b260`
- `0x18001c470`
- `0x18001de20`
- `0x1800301c8`
- `0x1800600c0`
- `0x18007682c`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180076a67`
- `msvcrt!_wcsicmp` at `0x180076a67`
- `msvcrt!??3@YAXPEAX@Z` at `0x180076ace`
- `msvcrt!??3@YAXPEAX@Z` at `0x180122e00`
- `msvcrt!??3@YAXPEAX@Z` at `0x180076ace`
- `msvcrt!??3@YAXPEAX@Z` at `0x180122e00`
- `ntdll!RtlFreeUnicodeString` at `0x180076a8e`
- `ntdll!RtlFreeUnicodeString` at `0x180076aa7`
- `ntdll!RtlFreeUnicodeString` at `0x180076a8e`
- `ntdll!RtlFreeUnicodeString` at `0x180076aa7`
- `ntdll!RtlStringFromGUID` at `0x180076a43`
- `ntdll!RtlStringFromGUID` at `0x180076a43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076ae4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180122e15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076ae4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180122e15`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180076a04`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180076a04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007699c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007699c`

## pseudocode

```c
__int64 __fastcall CFveApiBase::VerifyBindDataVolumeDpapi(CFveApiBase *this, bool *a2, struct _GUID *a3)
{
  unsigned int v5; // ebx
  struct _GUID *v6; // r12
  unsigned int v7; // r15d
  unsigned int v8; // edi
  DWORD v9; // esi
  NTSTATUS Count; // eax
  unsigned __int64 v11; // rax
  struct _GUID *v12; // rax
  __int64 v13; // rcx
  LSTATUS v14; // eax
  bool v15; // cc
  unsigned int i; // edi
  unsigned int v18; // [rsp+40h] [rbp-2A8h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-2A4h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-2A0h]
  __int64 v21; // [rsp+50h] [rbp-298h] BYREF
  struct _GUID *v22; // [rsp+58h] [rbp-290h]
  DWORD v23; // [rsp+60h] [rbp-288h]
  struct _GUID *v24; // [rsp+68h] [rbp-280h]
  HKEY hKey; // [rsp+70h] [rbp-278h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+78h] [rbp-270h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-260h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-258h] BYREF

  v24 = a3;
  GuidString = 0;
  memset_0(Name, 0, 0x208u);
  v5 = 0;
  v6 = 0;
  v22 = 0;
  v7 = 0;
  v18 = 0;
  v21 = 0;
  v8 = 0;
  v19 = 0;
  v9 = 0;
  cchName = 0;
  hKey = 0;
  *a2 = 0;
  Count = FveDatasetGetCount(*((_QWORD *)this + 146), 2, 8, &v18);
  if ( Count < 0 )
  {
LABEL_2:
    v5 = Count | 0x10000000;
    goto LABEL_25;
  }
  v11 = 16LL * v18;
  if ( !is_mul_ok(v18, 0x10u) )
    v11 = -1;
  v6 = (struct _GUID *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v6;
  if ( !v6 )
  {
    v5 = -2147024882;
    goto LABEL_25;
  }
  while ( (int)FveDatasetGetNext(*((_QWORD *)this + 146), 2, 8, v8, (__int64)&v19) >= 0 )
  {
    v8 = v19;
    if ( (int)FveDatasetGetDatum(*((_QWORD *)this + 146), v19, &v21) >= 0 )
    {
      v12 = &v6[v7++];
      v20 = v7;
      v13 = v21;
      *v12 = *(struct _GUID *)(v21 + 8);
      FveDatumFree(v13);
    }
  }
  v18 = v7;
  v14 = RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\FveAutoUnlock",
          0,
          0x2000000u,
          &hKey);
  if ( v14 == 2 )
    goto LABEL_15;
  v15 = v14 <= 0;
  if ( !v14 )
  {
    while ( 1 )
    {
      cchName = 260;
      v14 = RegEnumKeyExW(hKey, v9, Name, &cchName, 0, 0, 0, 0);
      if ( v14 == 259 )
        break;
      v15 = v14 <= 0;
      if ( v14 )
        goto LABEL_12;
      for ( i = 0; ; ++i )
      {
        v20 = i;
        if ( i >= v7 )
          break;
        Count = RtlStringFromGUID(&v6[i], &GuidString);
        if ( Count < 0 )
          goto LABEL_2;
        if ( !_wcsicmp(Name, GuidString.Buffer) )
        {
          *v24 = v6[i];
          *a2 = 1;
          RtlFreeUnicodeString(&GuidString);
          break;
        }
        RtlFreeUnicodeString(&GuidString);
      }
      v23 = ++v9;
      if ( *a2 )
        goto LABEL_25;
    }
LABEL_15:
    v5 = 0;
    goto LABEL_25;
  }
LABEL_12:
  if ( v15 )
    v5 = v14;
  else
    v5 = (unsigned __int16)v14 | 0x80070000;
LABEL_25:
  operator delete(v6);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18007682c  push    rbx
0x18007682e  push    rsi
0x18007682f  push    rdi
0x180076830  push    r12
0x180076832  push    r13
0x180076834  push    r14
0x180076836  push    r15
0x180076838  sub     rsp, 2B0h
0x18007683f  mov     rax, cs:__security_cookie
0x180076846  xor     rax, rsp
0x180076849  mov     [rsp+2E8h+var_48], rax
0x180076851  mov     [rsp+2E8h+var_280], r8
0x180076856  mov     r13, rdx
0x180076859  mov     r14, rcx
0x18007685c  xorps   xmm0, xmm0
0x18007685f  movups  xmmword ptr [rsp+2E8h+GuidString.Length], xmm0
0x180076864  xor     edx, edx; Val
0x180076866  mov     r8d, 208h; Size
0x18007686c  lea     rcx, [rsp+2E8h+Name]; void *
0x180076874  call    memset_0
0x180076879  xor     eax, eax
0x18007687b  mov     ebx, eax
0x18007687d  mov     r12d, eax
0x180076880  mov     [rsp+2E8h+var_290], rax
0x180076885  mov     r15d, eax
0x180076888  mov     [rsp+2E8h+var_2A8], eax
0x18007688c  mov     [rsp+2E8h+var_298], rax
0x180076891  mov     edi, eax
0x180076893  mov     [rsp+2E8h+var_2A4], eax
0x180076897  mov     esi, eax
0x180076899  mov     [rsp+2E8h+cchName], eax
0x1800768a0  mov     [rsp+2E8h+hKey], rax
0x1800768a5  mov     [r13+0], al
0x1800768a9  lea     edx, [rax+2]
0x1800768ac  lea     r8d, [rax+8]
0x1800768b0  lea     r9, [rsp+2E8h+var_2A8]
0x1800768b5  mov     rcx, [r14+490h]
0x1800768bc  call    FveDatasetGetCount
0x1800768c1  test    eax, eax
0x1800768c3  jns     short loc_1800768D0
0x1800768c5  mov     ebx, eax
0x1800768c7  bts     ebx, 1Ch
0x1800768cb  jmp     loc_180076ACB
0x1800768d0  mov     ecx, [rsp+2E8h+var_2A8]
0x1800768d4  mov     eax, 10h
0x1800768d9  mul     rcx
0x1800768dc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800768e3  cmovb   rax, rcx
0x1800768e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800768ee  mov     rcx, rax; unsigned __int64
0x1800768f1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800768f6  mov     r12, rax
0x1800768f9  mov     [rsp+2E8h+var_290], rax
0x1800768fe  test    rax, rax
0x180076901  jnz     short loc_18007690D
0x180076903  mov     ebx, 8007000Eh
0x180076908  jmp     loc_180076ACB
0x18007690d  mov     edx, 2
0x180076912  lea     r8d, [rdx+6]
0x180076916  lea     rax, [rsp+2E8h+var_2A4]
0x18007691b  mov     [rsp+2E8h+phkResult], rax
0x180076920  mov     r9d, edi
0x180076923  mov     rcx, [r14+490h]
0x18007692a  call    FveDatasetGetNext
0x18007692f  test    eax, eax
0x180076931  js      short loc_180076976
0x180076933  lea     r8, [rsp+2E8h+var_298]
0x180076938  mov     edi, [rsp+2E8h+var_2A4]
0x18007693c  mov     edx, edi
0x18007693e  mov     rcx, [r14+490h]
0x180076945  call    FveDatasetGetDatum
0x18007694a  test    eax, eax
0x18007694c  jns     short loc_180076950
0x18007694e  jmp     short loc_18007690D
0x180076950  mov     eax, r15d
0x180076953  shl     rax, 4
0x180076957  add     rax, r12
0x18007695a  inc     r15d
0x18007695d  mov     [rsp+2E8h+var_2A0], r15d
0x180076962  mov     rcx, [rsp+2E8h+var_298]
0x180076967  movups  xmm0, xmmword ptr [rcx+8]
0x18007696b  movdqu  xmmword ptr [rax], xmm0
0x18007696f  call    FveDatumFree
0x180076974  jmp     short loc_18007694E
0x180076976  mov     [rsp+2E8h+var_2A8], r15d
0x18007697b  lea     rax, [rsp+2E8h+hKey]
0x180076980  mov     [rsp+2E8h+phkResult], rax; phkResult
0x180076985  mov     r9d, 2000000h; samDesired
0x18007698b  xor     r8d, r8d; ulOptions
0x18007698e  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180076995  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007699c  call    cs:__imp_RegOpenKeyExW
0x1800769a3  nop     dword ptr [rax+rax+00h]
0x1800769a8  cmp     eax, 2
0x1800769ab  jz      short loc_180076A17
0x1800769ad  test    eax, eax
0x1800769af  jz      short loc_1800769BE
0x1800769b1  jg      loc_180076A9C
0x1800769b7  mov     ebx, eax
0x1800769b9  jmp     loc_180076ACB
0x1800769be  mov     [rsp+2E8h+cchName], 104h
0x1800769c9  mov     [rsp+2E8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800769d2  mov     [rsp+2E8h+lpcchClass], 0; lpcchClass
0x1800769db  mov     [rsp+2E8h+lpClass], 0; lpClass
0x1800769e4  mov     [rsp+2E8h+phkResult], 0; lpReserved
0x1800769ed  lea     r9, [rsp+2E8h+cchName]; lpcchName
0x1800769f5  lea     r8, [rsp+2E8h+Name]; lpName
0x1800769fd  mov     edx, esi; dwIndex
0x1800769ff  mov     rcx, [rsp+2E8h+hKey]; hKey
0x180076a04  call    cs:__imp_RegEnumKeyExW
0x180076a0b  nop     dword ptr [rax+rax+00h]
0x180076a10  cmp     eax, 103h
0x180076a15  jnz     short loc_180076A1E
0x180076a17  xor     ebx, ebx
0x180076a19  jmp     loc_180076ACB
0x180076a1e  test    eax, eax
0x180076a20  jnz     short loc_1800769B1
0x180076a22  xor     edi, edi
0x180076a24  mov     [rsp+2E8h+var_2A0], edi
0x180076a28  cmp     edi, r15d
0x180076a2b  jnb     loc_180076ABA
0x180076a31  mov     r14d, edi
0x180076a34  shl     r14, 4
0x180076a38  add     r14, r12
0x180076a3b  lea     rdx, [rsp+2E8h+GuidString]; GuidString
0x180076a40  mov     rcx, r14; Guid
0x180076a43  call    cs:__imp_RtlStringFromGUID
0x180076a4a  nop     dword ptr [rax+rax+00h]
0x180076a4f  test    eax, eax
0x180076a51  js      loc_1800768C5
0x180076a57  mov     rdx, [rsp+2E8h+GuidString.Buffer]; String2
0x180076a5f  lea     rcx, [rsp+2E8h+Name]; String1
0x180076a67  call    cs:__imp__wcsicmp
0x180076a6e  nop     dword ptr [rax+rax+00h]
0x180076a73  lea     rcx, [rsp+2E8h+GuidString]; UnicodeString
0x180076a78  test    eax, eax
0x180076a7a  jnz     short loc_180076AA7
0x180076a7c  movups  xmm0, xmmword ptr [r14]
0x180076a80  mov     rax, [rsp+2E8h+var_280]
0x180076a85  movdqu  xmmword ptr [rax], xmm0
0x180076a89  mov     byte ptr [r13+0], 1
0x180076a8e  call    cs:__imp_RtlFreeUnicodeString
0x180076a95  nop     dword ptr [rax+rax+00h]
0x180076a9a  jmp     short loc_180076ABA
0x180076a9c  movzx   ebx, ax
0x180076a9f  or      ebx, 80070000h
0x180076aa5  jmp     short loc_180076ACB
0x180076aa7  call    cs:__imp_RtlFreeUnicodeString
0x180076aae  nop     dword ptr [rax+rax+00h]
0x180076ab3  inc     edi
0x180076ab5  jmp     loc_180076A24
0x180076aba  inc     esi
0x180076abc  mov     [rsp+2E8h+var_288], esi
0x180076ac0  cmp     byte ptr [r13+0], 0
0x180076ac5  jz      loc_1800769BE
0x180076acb  mov     rcx, r12
0x180076ace  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180076ad5  nop     dword ptr [rax+rax+00h]
0x180076ada  mov     rcx, [rsp+2E8h+hKey]; hKey
0x180076adf  test    rcx, rcx
0x180076ae2  jz      short loc_180076AF0
0x180076ae4  call    cs:__imp_RegCloseKey
0x180076aeb  nop     dword ptr [rax+rax+00h]
0x180076af0  mov     eax, ebx
0x180076af2  mov     rcx, [rsp+2E8h+var_48]
0x180076afa  xor     rcx, rsp; StackCookie
0x180076afd  call    __security_check_cookie
0x180076b02  add     rsp, 2B0h
0x180076b09  pop     r15
0x180076b0b  pop     r14
0x180076b0d  pop     r13
0x180076b0f  pop     r12
0x180076b11  pop     rdi
0x180076b12  pop     rsi
0x180076b13  pop     rbx
0x180076b14  retn
0x180122df3  push    rbp
0x180122df5  sub     rsp, 40h
0x180122df9  mov     rbp, rdx
0x180122dfc  mov     rcx, [rbp+58h]
0x180122e00  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180122e07  nop     dword ptr [rax+rax+00h]
0x180122e0c  mov     rcx, [rbp+70h]; hKey
0x180122e10  test    rcx, rcx
0x180122e13  jz      short loc_180122E22
0x180122e15  call    cs:__imp_RegCloseKey
0x180122e1c  nop     dword ptr [rax+rax+00h]
0x180122e21  nop
0x180122e22  add     rsp, 40h
0x180122e26  pop     rbp
0x180122e27  retn
```
