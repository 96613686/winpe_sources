# PmConstructDeviceLocationDefault(_DEVICE_EXTENSION *)

- ea: `0x140024844`
- end: `0x140024ab7`
- name: `?PmConstructDeviceLocationDefault@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14002366c`

## callees

- `0x140004504`
- `0x140004800`
- `0x1400060e0`
- `0x140010f20`
- `0x140011440`
- `0x140024844`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140024a81`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024a81`
- `ntoskrnl!ExAllocatePool2` at `0x140024a4a`
- `ntoskrnl!ExAllocatePool2` at `0x140024a4a`

## pseudocode

```c
__int64 __fastcall PmConstructDeviceLocationDefault(struct _DEVICE_EXTENSION *a1)
{
  size_t v2; // rdx
  size_t v3; // rdx
  size_t v4; // rdx
  size_t v5; // rdx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // rax
  size_t v14; // rsi
  wchar_t *Pool2; // rax
  unsigned int v16; // edi
  PCWSTR v17; // r10
  wchar_t pszDest[128]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszSrc[128]; // [rsp+130h] [rbp+30h] BYREF

  memset(pszDest, 0, sizeof(pszDest));
  memset(pszSrc, 0, sizeof(pszSrc));
  if ( *((_DWORD *)a1 + 103) == -1 )
    RtlStringCbPrintfW(pszDest, 0x100u, L"Integrated");
  else
    RtlStringCbPrintfW(pszDest, 0x100u, L"PCI Slot %u");
  RtlStringCbCatW(pszSrc, v2, pszDest);
  if ( *((_DWORD *)a1 + 108) != -1 && *((_DWORD *)a1 + 109) != -1 && *((_DWORD *)a1 + 110) != -1 )
  {
    RtlStringCbPrintfW(pszDest, 0x100u, L" : Bus %u : Device %u : Function %u");
    RtlStringCbCatW(pszSrc, v3, pszDest);
  }
  RtlStringCbPrintfW(pszDest, 0x100u, L" : Adapter %u", *((unsigned int *)a1 + 104));
  RtlStringCbCatW(pszSrc, v4, pszDest);
  v6 = *(_DWORD *)(*((_QWORD *)a1 + 29) + 28LL);
  if ( v6 > 6 )
  {
    v10 = v6 - 7;
    if ( !v10 )
      goto LABEL_21;
    v11 = v10 - 1;
    if ( !v11 )
      goto LABEL_14;
    v12 = v11 - 2;
    if ( !v12 )
      goto LABEL_14;
    if ( v12 == 1 )
    {
LABEL_21:
      RtlStringCbPrintfW(pszDest, 0x100u, L" : Port %u", *((unsigned int *)a1 + 105));
      goto LABEL_22;
    }
LABEL_20:
    pszDest[0] = 0;
    goto LABEL_22;
  }
  if ( v6 != 6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( !v8 || (v9 = v8 - 1) == 0 )
      {
        RtlStringCbPrintfW(
          pszDest,
          0x100u,
          L" : Channel %u : Device %u",
          *((unsigned int *)a1 + 106),
          *((_DWORD *)a1 + 107));
        goto LABEL_22;
      }
      if ( (unsigned int)(v9 - 1) > 1 )
        goto LABEL_20;
    }
  }
LABEL_14:
  RtlStringCbPrintfW(
    pszDest,
    0x100u,
    L" : Port %u : Target %u : LUN %u",
    *((unsigned int *)a1 + 105),
    *((_DWORD *)a1 + 106),
    *((_DWORD *)a1 + 107));
LABEL_22:
  RtlStringCbCatW(pszSrc, v5, pszDest);
  v13 = -1;
  do
    ++v13;
  while ( pszSrc[v13] );
  v14 = (unsigned int)(2 * v13 + 2);
  Pool2 = (wchar_t *)ExAllocatePool2(66, v14, 1112108368);
  if ( Pool2 )
  {
    v16 = 0;
    RtlStringCbCopyW(Pool2, v14, pszSrc);
    RtlInitUnicodeString((PUNICODE_STRING)a1 + 28, v17);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v16;
}

```

## disassembly

```asm
0x140024844  mov     [rsp-8+arg_8], rbx
0x140024849  mov     [rsp-8+arg_10], rsi
0x14002484e  push    rbp
0x14002484f  push    rdi
0x140024850  push    r14
0x140024852  lea     rbp, [rsp-140h]
0x14002485a  sub     rsp, 240h
0x140024861  mov     rax, cs:__security_cookie
0x140024868  xor     rax, rsp
0x14002486b  mov     [rbp+150h+var_20], rax
0x140024872  mov     rbx, rcx
0x140024875  mov     edi, 0FEh
0x14002487a  xor     r14d, r14d
0x14002487d  lea     rcx, [rsp+250h+var_21E]; void *
0x140024882  mov     r8d, edi; Size
0x140024885  mov     [rsp+250h+pszDest], r14w
0x14002488b  xor     edx, edx; Val
0x14002488d  call    memset
0x140024892  mov     r8d, edi; Size
0x140024895  mov     [rbp+150h+pszSrc], r14w
0x14002489a  xor     edx, edx; Val
0x14002489c  lea     rcx, [rbp+150h+var_11E]; void *
0x1400248a0  call    memset
0x1400248a5  mov     r9d, [rbx+19Ch]
0x1400248ac  lea     rcx, [rsp+250h+pszDest]; pszDest
0x1400248b1  or      esi, 0FFFFFFFFh
0x1400248b4  mov     edi, 100h
0x1400248b9  mov     edx, edi; cbDest
0x1400248bb  cmp     r9d, esi
0x1400248be  jz      short loc_1400248CE
0x1400248c0  lea     r8, aPciSlotU; "PCI Slot %u"
0x1400248c7  call    RtlStringCbPrintfW
0x1400248cc  jmp     short loc_1400248DA
0x1400248ce  lea     r8, aIntegrated; "Integrated"
0x1400248d5  call    RtlStringCbPrintfW
0x1400248da  lea     r8, [rsp+250h+pszDest]; pszSrc
0x1400248df  lea     rcx, [rbp+150h+pszSrc]; pszDest
0x1400248e3  call    RtlStringCbCatW
0x1400248e8  mov     r9d, [rbx+1B0h]
0x1400248ef  cmp     r9d, esi
0x1400248f2  jz      short loc_140024932
0x1400248f4  mov     eax, [rbx+1B4h]
0x1400248fa  cmp     eax, esi
0x1400248fc  jz      short loc_140024932
0x1400248fe  mov     ecx, [rbx+1B8h]
0x140024904  cmp     ecx, esi
0x140024906  jz      short loc_140024932
0x140024908  mov     [rsp+250h+var_228], ecx
0x14002490c  lea     r8, aBusUDeviceUFun; " : Bus %u : Device %u : Function %u"
0x140024913  lea     rcx, [rsp+250h+pszDest]; pszDest
0x140024918  mov     [rsp+250h+var_230], eax
0x14002491c  mov     rdx, rdi; cbDest
0x14002491f  call    RtlStringCbPrintfW
0x140024924  lea     r8, [rsp+250h+pszDest]; pszSrc
0x140024929  lea     rcx, [rbp+150h+pszSrc]; pszDest
0x14002492d  call    RtlStringCbCatW
0x140024932  mov     r9d, [rbx+1A0h]
0x140024939  lea     r8, aAdapterU; " : Adapter %u"
0x140024940  mov     rdx, rdi; cbDest
0x140024943  lea     rcx, [rsp+250h+pszDest]; pszDest
0x140024948  call    RtlStringCbPrintfW
0x14002494d  lea     r8, [rsp+250h+pszDest]; pszSrc
0x140024952  lea     rcx, [rbp+150h+pszSrc]; pszDest
0x140024956  call    RtlStringCbCatW
0x14002495b  mov     rax, [rbx+0E8h]
0x140024962  mov     ecx, [rax+1Ch]
0x140024965  cmp     ecx, 6
0x140024968  jg      short loc_1400249DD
0x14002496a  jz      short loc_140024985
0x14002496c  sub     ecx, 1
0x14002496f  jz      short loc_140024985
0x140024971  sub     ecx, 1
0x140024974  jz      short loc_1400249B6
0x140024976  sub     ecx, 1
0x140024979  jz      short loc_1400249B6
0x14002497b  sub     ecx, 1
0x14002497e  jz      short loc_140024985
0x140024980  cmp     ecx, 1
0x140024983  jnz     short loc_1400249F1
0x140024985  mov     eax, [rbx+1ACh]
0x14002498b  lea     r8, aPortUTargetULu; " : Port %u : Target %u : LUN %u"
0x140024992  mov     r9d, [rbx+1A4h]
0x140024999  lea     rcx, [rsp+250h+pszDest]; pszDest
0x14002499e  mov     [rsp+250h+var_228], eax
0x1400249a2  mov     rdx, rdi; cbDest
0x1400249a5  mov     eax, [rbx+1A8h]
0x1400249ab  mov     [rsp+250h+var_230], eax
0x1400249af  call    RtlStringCbPrintfW
0x1400249b4  jmp     short loc_140024A14
0x1400249b6  mov     eax, [rbx+1ACh]
0x1400249bc  lea     r8, aChannelUDevice; " : Channel %u : Device %u"
0x1400249c3  mov     r9d, [rbx+1A8h]
0x1400249ca  lea     rcx, [rsp+250h+pszDest]; pszDest
0x1400249cf  mov     rdx, rdi; cbDest
0x1400249d2  mov     [rsp+250h+var_230], eax
0x1400249d6  call    RtlStringCbPrintfW
0x1400249db  jmp     short loc_140024A14
0x1400249dd  sub     ecx, 7
0x1400249e0  jz      short loc_1400249F9
0x1400249e2  sub     ecx, 1
0x1400249e5  jz      short loc_140024985
0x1400249e7  sub     ecx, 2
0x1400249ea  jz      short loc_140024985
0x1400249ec  cmp     ecx, 1
0x1400249ef  jz      short loc_1400249F9
0x1400249f1  mov     [rsp+250h+pszDest], r14w
0x1400249f7  jmp     short loc_140024A14
0x1400249f9  mov     r9d, [rbx+1A4h]
0x140024a00  lea     r8, aPortU; " : Port %u"
0x140024a07  mov     rdx, rdi; cbDest
0x140024a0a  lea     rcx, [rsp+250h+pszDest]; pszDest
0x140024a0f  call    RtlStringCbPrintfW
0x140024a14  lea     r8, [rsp+250h+pszDest]; pszSrc
0x140024a19  lea     rcx, [rbp+150h+pszSrc]; pszDest
0x140024a1d  call    RtlStringCbCatW
0x140024a22  lea     rcx, [rbp+150h+pszSrc]
0x140024a26  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024a2a  inc     rax
0x140024a2d  cmp     [rcx+rax*2], r14w
0x140024a32  jnz     short loc_140024A2A
0x140024a34  lea     eax, ds:2[rax*2]
0x140024a3b  mov     r8d, 42496D50h
0x140024a41  mov     edx, eax
0x140024a43  mov     ecx, 42h ; 'B'
0x140024a48  mov     esi, eax
0x140024a4a  call    cs:__imp_ExAllocatePool2
0x140024a51  nop     dword ptr [rax+rax+00h]
0x140024a56  mov     r10, rax
0x140024a59  test    rax, rax
0x140024a5c  jnz     short loc_140024A65
0x140024a5e  mov     edi, 0C000009Ah
0x140024a63  jmp     short loc_140024A8D
0x140024a65  lea     r8, [rbp+150h+pszSrc]; pszSrc
0x140024a69  mov     rdx, rsi; cbDest
0x140024a6c  mov     rcx, r10; pszDest
0x140024a6f  mov     edi, r14d
0x140024a72  call    RtlStringCbCopyW
0x140024a77  lea     rcx, [rbx+1C0h]; DestinationString
0x140024a7e  mov     rdx, r10; SourceString
0x140024a81  call    cs:__imp_RtlInitUnicodeString
0x140024a88  nop     dword ptr [rax+rax+00h]
0x140024a8d  mov     eax, edi
0x140024a8f  mov     rcx, [rbp+150h+var_20]
0x140024a96  xor     rcx, rsp; StackCookie
0x140024a99  call    __security_check_cookie
0x140024a9e  lea     r11, [rsp+250h+var_10]
0x140024aa6  mov     rbx, [r11+28h]
0x140024aaa  mov     rsi, [r11+30h]
0x140024aae  mov     rsp, r11
0x140024ab1  pop     r14
0x140024ab3  pop     rdi
0x140024ab4  pop     rbp
0x140024ab5  retn
```
