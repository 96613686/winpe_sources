# ConvertIpAddressToFilterDescriptor

- ea: `0x180019098`
- end: `0x180019284`
- name: `ConvertIpAddressToFilterDescriptor`
- size: `492`
- prototype: `__int64 __fastcall(HLOCAL *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b198`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180019098`
- `0x18002b0dc`
- `0x18002d414`
- `0x18002d68c`
- `0x18002d708`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001922f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001923e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001922f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001923e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800190ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800190ef`

## string_xrefs

- `0x1800191b3`: `MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d`

## pseudocode

```c
__int64 __fastcall ConvertIpAddressToFilterDescriptor(HLOCAL *a1, unsigned int a2)
{
  unsigned int v2; // esi
  BYTE *lpItemData; // rdi
  HLOCAL v6; // rcx
  unsigned int v7; // r11d
  __int64 v8; // r10
  __int64 v9; // rax
  __int64 v10; // r9
  int v11; // edx
  DWORD v12; // eax
  DWORD v13; // ebx
  int v14; // r8d
  void *v15; // rsi
  LPVOID lpNewHeader; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lplpNewHeader; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  char v20[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v2 = a2 - 1;
  lpNewHeader = 0;
  lplpNewHeader = 0;
  lpItemData = (BYTE *)LocalAlloc(0x40u, 28LL * (a2 - 1) + 40);
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v7 = 0;
  if ( a2 )
  {
    v8 = 0;
    do
    {
      v6 = *a1;
      v9 = 4 * v7;
      v10 = 28 * v8;
      ++v7;
      ++v8;
      v11 = (*((unsigned __int8 *)*a1 + v9 + 3) << 16)
          | ((*((unsigned __int8 *)*a1 + v9 + 2) | (*((unsigned __int8 *)*a1 + v9 + 4) << 16)) << 8);
      LODWORD(v9) = *((unsigned __int8 *)*a1 + v9 + 1);
      *(_DWORD *)&lpItemData[v10 + 32] |= 0x11u;
      *(_DWORD *)&lpItemData[v10 + 20] = v9 | v11;
      *(_DWORD *)&lpItemData[v10 + 24] = -1;
    }
    while ( v7 < a2 );
  }
  *((_DWORD *)lpItemData + 2) = 1;
  *(_DWORD *)lpItemData = 1;
  *((_DWORD *)lpItemData + 1) = a2;
  v12 = MprInfoCreate((DWORD)v6, &lpNewHeader);
  v13 = v12;
  if ( v12 )
  {
    if ( gIsProtocolCommonTracingEnabled && *((_QWORD *)&xmmword_18004D8E0 + 1) )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v19,
        L"MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d",
        v12);
      ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
        gProtocolCommonEtwContext,
        *((_QWORD *)&xmmword_18004D8E0 + 1),
        &v19);
    }
  }
  else
  {
    v14 = 28 * v2;
    v15 = lpNewHeader;
    v13 = MprInfoBlockAdd(lpNewHeader, 0xFFFF0001, v14 + 40, 1u, lpItemData, &lplpNewHeader);
    if ( v13 )
    {
      MprInfoDelete(v15);
    }
    else
    {
      LocalFree(*a1);
      LocalFree(lpItemData);
      MprInfoDelete(v15);
      *a1 = lplpNewHeader;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180019098  mov     [rsp-8+arg_10], rbx
0x18001909d  mov     [rsp-8+arg_18], rsi
0x1800190a2  push    rbp
0x1800190a3  push    rdi
0x1800190a4  push    r14
0x1800190a6  lea     rbp, [rsp-750h]
0x1800190ae  sub     rsp, 850h
0x1800190b5  mov     rax, cs:__security_cookie
0x1800190bc  xor     rax, rsp
0x1800190bf  mov     [rbp+760h+var_20], rax
0x1800190c6  lea     esi, [rdx-1]
0x1800190c9  mov     [rsp+860h+lpNewHeader], 0
0x1800190d2  mov     ebx, edx
0x1800190d4  mov     eax, esi
0x1800190d6  imul    rdx, rax, 1Ch
0x1800190da  mov     r14, rcx
0x1800190dd  mov     [rsp+860h+var_828], 0
0x1800190e6  add     rdx, 28h ; '('; uBytes
0x1800190ea  mov     ecx, 40h ; '@'; uFlags
0x1800190ef  call    cs:__imp_LocalAlloc
0x1800190f6  nop     dword ptr [rax+rax+00h]
0x1800190fb  xor     edx, edx; Val
0x1800190fd  lea     rcx, [rsp+860h+var_81C]; void *
0x180019102  mov     rdi, rax
0x180019105  mov     r8d, 7FCh; Size
0x18001910b  xor     eax, eax
0x18001910d  mov     [rsp+860h+var_820], eax
0x180019111  call    memset_0
0x180019116  xor     r11d, r11d
0x180019119  test    ebx, ebx
0x18001911b  jz      short loc_180019176
0x18001911d  xor     r10d, r10d
0x180019120  mov     rcx, [r14]; dwVersion
0x180019123  lea     eax, ds:0[r11*4]
0x18001912b  imul    r9, r10, 1Ch
0x18001912f  mov     r8d, eax
0x180019132  inc     r11d
0x180019135  movzx   edx, byte ptr [rax+rcx+4]
0x18001913a  inc     r10
0x18001913d  movzx   eax, byte ptr [rax+rcx+2]
0x180019142  shl     edx, 10h
0x180019145  or      edx, eax
0x180019147  movzx   eax, byte ptr [r8+rcx+3]
0x18001914d  shl     edx, 8
0x180019150  shl     eax, 10h
0x180019153  or      edx, eax
0x180019155  movzx   eax, byte ptr [r8+rcx+1]
0x18001915b  or      dword ptr [r9+rdi+20h], 11h
0x180019161  or      edx, eax
0x180019163  mov     [r9+rdi+14h], edx
0x180019168  mov     dword ptr [r9+rdi+18h], 0FFFFFFFFh
0x180019171  cmp     r11d, ebx
0x180019174  jb      short loc_180019120
0x180019176  lea     rdx, [rsp+860h+lpNewHeader]; lplpNewHeader
0x18001917b  mov     dword ptr [rdi+8], 1
0x180019182  mov     dword ptr [rdi], 1
0x180019188  mov     [rdi+4], ebx
0x18001918b  call    MprInfoCreate
0x180019190  mov     ebx, eax
0x180019192  test    eax, eax
0x180019194  jz      short loc_1800191ED
0x180019196  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x18001919d  jz      loc_18001925A
0x1800191a3  cmp     qword ptr cs:xmmword_18004D8E0+8, 0
0x1800191ab  jz      loc_18001925A
0x1800191b1  xor     ecx, ecx
0x1800191b3  lea     rdx, aMprinfocreateF; "MprInfoCreate failed  in ConvertIpAddre"...
0x1800191ba  mov     word ptr [rsp+860h+var_820], cx
0x1800191bf  mov     r8d, eax
0x1800191c2  lea     rcx, [rsp+860h+var_820]
0x1800191c7  call    FormatRRASErrorString
0x1800191cc  mov     rdx, qword ptr cs:xmmword_18004D8E0+8
0x1800191d3  lea     r8, [rsp+860h+var_820]
0x1800191d8  mov     rcx, cs:gProtocolCommonEtwContext
0x1800191df  mov     rax, cs:gProtocolCommonTemplateFunc
0x1800191e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191eb  jmp     short loc_18001925A
0x1800191ed  imul    r8d, esi, 1Ch
0x1800191f1  lea     rax, [rsp+860h+var_828]
0x1800191f6  mov     rsi, [rsp+860h+lpNewHeader]
0x1800191fb  mov     edx, 0FFFF0001h; dwInfoType
0x180019200  mov     [rsp+860h+lplpNewHeader], rax; lplpNewHeader
0x180019205  mov     r9d, 1; dwItemCount
0x18001920b  mov     rcx, rsi; lpHeader
0x18001920e  mov     [rsp+860h+lpItemData], rdi; lpItemData
0x180019213  add     r8d, 28h ; '('; dwItemSize
0x180019217  call    MprInfoBlockAdd
0x18001921c  mov     ebx, eax
0x18001921e  test    eax, eax
0x180019220  jz      short loc_18001922C
0x180019222  mov     rcx, rsi; lpHeader
0x180019225  call    MprInfoDelete
0x18001922a  jmp     short loc_18001925A
0x18001922c  mov     rcx, [r14]; hMem
0x18001922f  call    cs:__imp_LocalFree
0x180019236  nop     dword ptr [rax+rax+00h]
0x18001923b  mov     rcx, rdi; hMem
0x18001923e  call    cs:__imp_LocalFree
0x180019245  nop     dword ptr [rax+rax+00h]
0x18001924a  mov     rcx, rsi; lpHeader
0x18001924d  call    MprInfoDelete
0x180019252  mov     rax, [rsp+860h+var_828]
0x180019257  mov     [r14], rax
0x18001925a  mov     eax, ebx
0x18001925c  mov     rcx, [rbp+760h+var_20]
0x180019263  xor     rcx, rsp; StackCookie
0x180019266  call    __security_check_cookie
0x18001926b  lea     r11, [rsp+860h+var_10]
0x180019273  mov     rbx, [r11+30h]
0x180019277  mov     rsi, [r11+38h]
0x18001927b  mov     rsp, r11
0x18001927e  pop     r14
0x180019280  pop     rdi
0x180019281  pop     rbp
0x180019282  retn
```
