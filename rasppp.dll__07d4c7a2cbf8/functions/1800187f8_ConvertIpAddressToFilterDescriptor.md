# ConvertIpAddressToFilterDescriptor

- ea: `0x1800187f8`
- end: `0x1800189d1`
- name: `ConvertIpAddressToFilterDescriptor`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a7c0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800187f8`
- `0x18002a138`
- `0x18002c328`
- `0x18002c594`
- `0x18002c604`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018989`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018992`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018989`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018992`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001884f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001884f`

## string_xrefs

- `0x18001890d`: `MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d`

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
    if ( gIsProtocolCommonTracingEnabled && *((_QWORD *)&xmmword_18004C8E0 + 1) )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"MprInfoCreate failed  in ConvertIpAddressToFilterDescriptor and returned %d", v12);
      ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
        gProtocolCommonEtwContext,
        *((_QWORD *)&xmmword_18004C8E0 + 1),
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
0x1800187f8  mov     [rsp-8+arg_10], rbx
0x1800187fd  mov     [rsp-8+arg_18], rsi
0x180018802  push    rbp
0x180018803  push    rdi
0x180018804  push    r14
0x180018806  lea     rbp, [rsp-750h]
0x18001880e  sub     rsp, 850h
0x180018815  mov     rax, cs:__security_cookie
0x18001881c  xor     rax, rsp
0x18001881f  mov     [rbp+760h+var_20], rax
0x180018826  lea     esi, [rdx-1]
0x180018829  mov     [rsp+860h+lpNewHeader], 0
0x180018832  mov     ebx, edx
0x180018834  mov     eax, esi
0x180018836  imul    rdx, rax, 1Ch
0x18001883a  mov     r14, rcx
0x18001883d  mov     [rsp+860h+var_828], 0
0x180018846  add     rdx, 28h ; '('; uBytes
0x18001884a  mov     ecx, 40h ; '@'; uFlags
0x18001884f  call    cs:__imp_LocalAlloc
0x180018855  xor     edx, edx; Val
0x180018857  lea     rcx, [rsp+860h+var_81C]; void *
0x18001885c  mov     rdi, rax
0x18001885f  mov     r8d, 7FCh; Size
0x180018865  xor     eax, eax
0x180018867  mov     [rsp+860h+var_820], eax
0x18001886b  call    memset_0
0x180018870  xor     r11d, r11d
0x180018873  test    ebx, ebx
0x180018875  jz      short loc_1800188D0
0x180018877  xor     r10d, r10d
0x18001887a  mov     rcx, [r14]; dwVersion
0x18001887d  lea     eax, ds:0[r11*4]
0x180018885  imul    r9, r10, 1Ch
0x180018889  mov     r8d, eax
0x18001888c  inc     r11d
0x18001888f  movzx   edx, byte ptr [rax+rcx+4]
0x180018894  inc     r10
0x180018897  movzx   eax, byte ptr [rax+rcx+2]
0x18001889c  shl     edx, 10h
0x18001889f  or      edx, eax
0x1800188a1  movzx   eax, byte ptr [r8+rcx+3]
0x1800188a7  shl     edx, 8
0x1800188aa  shl     eax, 10h
0x1800188ad  or      edx, eax
0x1800188af  movzx   eax, byte ptr [r8+rcx+1]
0x1800188b5  or      dword ptr [r9+rdi+20h], 11h
0x1800188bb  or      edx, eax
0x1800188bd  mov     [r9+rdi+14h], edx
0x1800188c2  mov     dword ptr [r9+rdi+18h], 0FFFFFFFFh
0x1800188cb  cmp     r11d, ebx
0x1800188ce  jb      short loc_18001887A
0x1800188d0  lea     rdx, [rsp+860h+lpNewHeader]; lplpNewHeader
0x1800188d5  mov     dword ptr [rdi+8], 1
0x1800188dc  mov     dword ptr [rdi], 1
0x1800188e2  mov     [rdi+4], ebx
0x1800188e5  call    MprInfoCreate
0x1800188ea  mov     ebx, eax
0x1800188ec  test    eax, eax
0x1800188ee  jz      short loc_180018947
0x1800188f0  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x1800188f7  jz      loc_1800189A8
0x1800188fd  cmp     qword ptr cs:xmmword_18004C8E0+8, 0
0x180018905  jz      loc_1800189A8
0x18001890b  xor     ecx, ecx
0x18001890d  lea     rdx, aMprinfocreateF; "MprInfoCreate failed  in ConvertIpAddre"...
0x180018914  mov     word ptr [rsp+860h+var_820], cx
0x180018919  mov     r8d, eax
0x18001891c  lea     rcx, [rsp+860h+var_820]
0x180018921  call    FormatRRASErrorString
0x180018926  mov     rdx, qword ptr cs:xmmword_18004C8E0+8
0x18001892d  lea     r8, [rsp+860h+var_820]
0x180018932  mov     rcx, cs:gProtocolCommonEtwContext
0x180018939  mov     rax, cs:gProtocolCommonTemplateFunc
0x180018940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018945  jmp     short loc_1800189A8
0x180018947  imul    r8d, esi, 1Ch
0x18001894b  lea     rax, [rsp+860h+var_828]
0x180018950  mov     rsi, [rsp+860h+lpNewHeader]
0x180018955  mov     edx, 0FFFF0001h; dwInfoType
0x18001895a  mov     [rsp+860h+lplpNewHeader], rax; lplpNewHeader
0x18001895f  mov     r9d, 1; dwItemCount
0x180018965  mov     rcx, rsi; lpHeader
0x180018968  mov     [rsp+860h+lpItemData], rdi; lpItemData
0x18001896d  add     r8d, 28h ; '('; dwItemSize
0x180018971  call    MprInfoBlockAdd
0x180018976  mov     ebx, eax
0x180018978  test    eax, eax
0x18001897a  jz      short loc_180018986
0x18001897c  mov     rcx, rsi; lpHeader
0x18001897f  call    MprInfoDelete
0x180018984  jmp     short loc_1800189A8
0x180018986  mov     rcx, [r14]; hMem
0x180018989  call    cs:__imp_LocalFree
0x18001898f  mov     rcx, rdi; hMem
0x180018992  call    cs:__imp_LocalFree
0x180018998  mov     rcx, rsi; lpHeader
0x18001899b  call    MprInfoDelete
0x1800189a0  mov     rax, [rsp+860h+var_828]
0x1800189a5  mov     [r14], rax
0x1800189a8  mov     eax, ebx
0x1800189aa  mov     rcx, [rbp+760h+var_20]
0x1800189b1  xor     rcx, rsp; StackCookie
0x1800189b4  call    __security_check_cookie
0x1800189b9  lea     r11, [rsp+860h+var_10]
0x1800189c1  mov     rbx, [r11+30h]
0x1800189c5  mov     rsi, [r11+38h]
0x1800189c9  mov     rsp, r11
0x1800189cc  pop     r14
0x1800189ce  pop     rdi
0x1800189cf  pop     rbp
0x1800189d0  retn
```
