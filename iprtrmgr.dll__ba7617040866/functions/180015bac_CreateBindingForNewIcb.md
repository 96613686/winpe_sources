# CreateBindingForNewIcb

- ea: `0x180015bac`
- end: `0x180015e53`
- name: `CreateBindingForNewIcb`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015e5c`

## callees

- `0x180011790`
- `0x180015bac`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180015d29`
- `ntdll!RtlAcquireResourceExclusive` at `0x180015d29`
- `ntdll!RtlReleaseResource` at `0x180015d8e`
- `ntdll!RtlReleaseResource` at `0x180015d8e`
- `KERNEL32!HeapFree` at `0x180015c75`
- `KERNEL32!HeapFree` at `0x180015c75`
- `KERNEL32!HeapAlloc` at `0x180015c3d`
- `KERNEL32!HeapAlloc` at `0x180015c5b`
- `KERNEL32!HeapAlloc` at `0x180015daf`
- `KERNEL32!HeapAlloc` at `0x180015c3d`
- `KERNEL32!HeapAlloc` at `0x180015c5b`
- `KERNEL32!HeapAlloc` at `0x180015daf`

## string_xrefs

- `0x180015dd1`: `CreateBindingFornewIcb: Allocated for binding for interface %ws of type %d at %X `

## pseudocode

```c
__int64 __fastcall CreateBindingForNewIcb(__int64 a1)
{
  unsigned int v2; // eax
  int v3; // ecx
  int v4; // r14d
  _QWORD *v5; // rbx
  _DWORD *v6; // rcx
  __int64 *v8; // rcx
  __int64 v9; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  __int64 v12; // r9
  __int64 v13; // r8
  __int128 *v14; // r9
  __int128 v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+44h] [rbp-BCh]
  __int128 v18; // [rsp+54h] [rbp-ACh]
  int v19; // [rsp+64h] [rbp-9Ch]
  int v20; // [rsp+70h] [rbp-90h] BYREF
  char v21[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v16 = 0;
  v19 = 0;
  v2 = *(_DWORD *)(a1 + 144);
  v17 = 0;
  v18 = 0;
  v15 = 0;
  if ( v2 <= 7 && (v3 = 166, _bittest(&v3, v2)) )
  {
    v4 = *(_DWORD *)(a1 + 516);
    v5 = HeapAlloc(IPRouterHeap, 8u, 0x84u);
    if ( !v5 )
      return 8;
    v6 = HeapAlloc(IPRouterHeap, 8u, 0x1Cu);
    if ( !v6 )
    {
      HeapFree(IPRouterHeap, 0, v5);
      return 8;
    }
    v5[5] = a1;
    *((_DWORD *)v5 + 6) = *(_DWORD *)(a1 + 16);
    v5[4] = *(_QWORD *)(a1 + 160);
    *((_DWORD *)v5 + 25) = *(_DWORD *)(a1 + 88);
    *((_DWORD *)v5 + 4) = *(_DWORD *)(a1 + 512);
    *((_DWORD *)v5 + 14) = *(_DWORD *)(a1 + 704);
    *(_OWORD *)((char *)v5 + 60) = *(_OWORD *)(a1 + 688);
    if ( v4 )
    {
      *((_DWORD *)v5 + 19) = 0;
      v5[13] = 0;
    }
    *((_DWORD *)v5 + 32) = 0;
    *((_DWORD *)v5 + 23) = *(_DWORD *)(a1 + 524);
    *((_DWORD *)v5 + 24) = *(_DWORD *)(a1 + 528);
    *((_DWORD *)v5 + 12) = *(_DWORD *)(a1 + 144);
    v6[6] = 0;
    *((_DWORD *)v5 + 5) = v4;
    *(_QWORD *)(a1 + 712) = v6;
    RtlAcquireResourceExclusive(&stru_18008C500, 1u);
    v8 = &g_leBindingTable[2 * (*(_DWORD *)(a1 + 16) % 0x39u)];
    v9 = *v8;
    if ( *(__int64 **)(*v8 + 8) != v8 )
      __fastfail(3u);
    ++g_ulNumBindings;
    v5[1] = v8;
    *v5 = v9;
    *(_QWORD *)(v9 + 8) = v5;
    *v8 = (__int64)v5;
    g_LastUpdateTable[0] = 0;
    RtlReleaseResource(&stru_18008C500);
  }
  else if ( !v2 )
  {
    v10 = HeapAlloc(IPRouterHeap, 8u, 0x1Cu);
    v11 = v10;
    if ( !v10 )
      return 8;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v12 = *(unsigned int *)(a1 + 516);
      v13 = *(_QWORD *)(a1 + 72);
      LOWORD(v20) = 0;
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v20,
        L"CreateBindingFornewIcb: Allocated for binding for interface %ws of type %d at %X ",
        v13,
        v12,
        v10);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v14 = &v15;
        if ( a1 != -688 )
          LODWORD(v14) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v20,
          (_DWORD)v14,
          *(_QWORD *)(a1 + 72),
          (__int64)&v16);
      }
    }
    v11[6] = 0;
    *(_QWORD *)(a1 + 712) = v11;
  }
  return 0;
}

```

## disassembly

```asm
0x180015bac  push    rbp
0x180015bae  push    rbx
0x180015baf  push    rdi
0x180015bb0  push    r14
0x180015bb2  lea     rbp, [rsp-788h]
0x180015bba  sub     rsp, 888h
0x180015bc1  mov     rax, cs:__security_cookie
0x180015bc8  xor     rax, rsp
0x180015bcb  mov     [rbp+7A0h+var_30], rax
0x180015bd2  mov     rdi, rcx
0x180015bd5  xor     eax, eax
0x180015bd7  lea     rcx, [rsp+8A0h+var_82C]; void *
0x180015bdc  mov     [rsp+8A0h+var_830], eax
0x180015be0  xor     edx, edx; Val
0x180015be2  mov     r8d, 7FCh; Size
0x180015be8  call    memset_0
0x180015bed  xor     eax, eax
0x180015bef  xorps   xmm0, xmm0
0x180015bf2  mov     [rsp+8A0h+var_860], eax
0x180015bf6  mov     [rsp+8A0h+var_83C], eax
0x180015bfa  mov     eax, [rdi+90h]
0x180015c00  movups  [rsp+8A0h+var_85C], xmm0
0x180015c05  movups  [rsp+8A0h+var_84C], xmm0
0x180015c0a  movups  [rsp+8A0h+var_870], xmm0
0x180015c0f  cmp     eax, 7
0x180015c12  ja      loc_180015D99
0x180015c18  mov     ecx, 0A6h
0x180015c1d  bt      ecx, eax
0x180015c20  jnb     loc_180015D99
0x180015c26  mov     r14d, [rdi+204h]
0x180015c2d  lea     r8d, [rcx-22h]; dwBytes
0x180015c31  mov     rcx, cs:IPRouterHeap; hHeap
0x180015c38  mov     edx, 8; dwFlags
0x180015c3d  call    cs:__imp_HeapAlloc
0x180015c43  mov     rbx, rax
0x180015c46  test    rax, rax
0x180015c49  jz      short loc_180015C7B
0x180015c4b  mov     rcx, cs:IPRouterHeap; hHeap
0x180015c52  mov     edx, 8; dwFlags
0x180015c57  lea     r8d, [rdx+14h]; dwBytes
0x180015c5b  call    cs:__imp_HeapAlloc
0x180015c61  mov     rcx, rax
0x180015c64  test    rax, rax
0x180015c67  jnz     short loc_180015C9C
0x180015c69  mov     rcx, cs:IPRouterHeap; hHeap
0x180015c70  mov     r8, rbx; lpMem
0x180015c73  xor     edx, edx; dwFlags
0x180015c75  call    cs:__imp_HeapFree
0x180015c7b  mov     eax, 8
0x180015c80  mov     rcx, [rbp+7A0h+var_30]
0x180015c87  xor     rcx, rsp; StackCookie
0x180015c8a  call    __security_check_cookie
0x180015c8f  add     rsp, 888h
0x180015c96  pop     r14
0x180015c98  pop     rdi
0x180015c99  pop     rbx
0x180015c9a  pop     rbp
0x180015c9b  retn
0x180015c9c  mov     [rbx+28h], rdi
0x180015ca0  mov     eax, [rdi+10h]
0x180015ca3  mov     [rbx+18h], eax
0x180015ca6  mov     rax, [rdi+0A0h]
0x180015cad  mov     [rbx+20h], rax
0x180015cb1  mov     eax, [rdi+58h]
0x180015cb4  mov     [rbx+64h], eax
0x180015cb7  mov     eax, [rdi+200h]
0x180015cbd  mov     [rbx+10h], eax
0x180015cc0  mov     eax, [rdi+2C0h]
0x180015cc6  mov     [rbx+38h], eax
0x180015cc9  movups  xmm0, xmmword ptr [rdi+2B0h]
0x180015cd0  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x180015cd5  test    r14d, r14d
0x180015cd8  jz      short loc_180015CE9
0x180015cda  mov     dword ptr [rbx+4Ch], 0
0x180015ce1  mov     qword ptr [rbx+68h], 0
0x180015ce9  mov     dword ptr [rbx+80h], 0
0x180015cf3  mov     dl, 1; Wait
0x180015cf5  mov     eax, [rdi+20Ch]
0x180015cfb  mov     [rbx+5Ch], eax
0x180015cfe  mov     eax, [rdi+210h]
0x180015d04  mov     [rbx+60h], eax
0x180015d07  mov     eax, [rdi+90h]
0x180015d0d  mov     [rbx+30h], eax
0x180015d10  mov     dword ptr [rcx+18h], 0
0x180015d17  mov     [rbx+14h], r14d
0x180015d1b  mov     [rdi+2C8h], rcx
0x180015d22  lea     rcx, stru_18008C500; Resource
0x180015d29  call    cs:__imp_RtlAcquireResourceExclusive
0x180015d2f  mov     ecx, [rdi+10h]
0x180015d32  mov     eax, 1F7047DDh
0x180015d37  mul     ecx
0x180015d39  mov     eax, ecx
0x180015d3b  sub     eax, edx
0x180015d3d  shr     eax, 1
0x180015d3f  add     eax, edx
0x180015d41  shr     eax, 5
0x180015d44  imul    eax, 39h ; '9'
0x180015d47  sub     ecx, eax
0x180015d49  mov     eax, ecx
0x180015d4b  lea     rcx, g_leBindingTable
0x180015d52  shl     rax, 4
0x180015d56  add     rcx, rax
0x180015d59  mov     rax, [rcx]
0x180015d5c  cmp     [rax+8], rcx
0x180015d60  jz      short loc_180015D69
0x180015d62  mov     ecx, 3
0x180015d67  int     29h; Win8: RtlFailFast(ecx)
0x180015d69  inc     cs:g_ulNumBindings
0x180015d6f  mov     [rbx+8], rcx
0x180015d73  mov     [rbx], rax
0x180015d76  mov     [rax+8], rbx
0x180015d7a  mov     [rcx], rbx
0x180015d7d  lea     rcx, stru_18008C500; Resource
0x180015d84  mov     cs:g_LastUpdateTable, 0
0x180015d8e  call    cs:__imp_RtlReleaseResource
0x180015d94  jmp     loc_180015E4C
0x180015d99  test    eax, eax
0x180015d9b  jnz     loc_180015E4C
0x180015da1  mov     rcx, cs:IPRouterHeap; hHeap
0x180015da8  lea     edx, [rax+8]; dwFlags
0x180015dab  lea     r8d, [rax+1Ch]; dwBytes
0x180015daf  call    cs:__imp_HeapAlloc
0x180015db5  mov     rbx, rax
0x180015db8  test    rax, rax
0x180015dbb  jz      loc_180015C7B
0x180015dc1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180015dc8  jge     short loc_180015E3E
0x180015dca  mov     r9d, [rdi+204h]
0x180015dd1  lea     rdx, aCreatebindingf; "CreateBindingFornewIcb: Allocated for b"...
0x180015dd8  mov     r8, [rdi+48h]
0x180015ddc  xor     ecx, ecx
0x180015dde  mov     word ptr [rsp+8A0h+var_830], cx
0x180015de3  mov     word ptr [rsp+8A0h+var_860], cx
0x180015de8  lea     rcx, [rsp+8A0h+var_830]
0x180015ded  mov     [rsp+8A0h+var_880], rax
0x180015df2  call    FormatRRASErrorString
0x180015df7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180015dfe  jge     short loc_180015E3E
0x180015e00  lea     rax, [rdi+2B0h]
0x180015e07  test    rax, rax
0x180015e0a  lea     r9, [rsp+8A0h+var_870]
0x180015e0f  lea     r8, [rsp+8A0h+var_830]
0x180015e14  cmovnz  r9, rax
0x180015e18  lea     rdx, RasRtrmgrParamTraceInfo
0x180015e1f  lea     rax, [rsp+8A0h+var_860]
0x180015e24  mov     [rsp+8A0h+var_878], rax
0x180015e29  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015e30  mov     rax, [rdi+48h]
0x180015e34  mov     [rsp+8A0h+var_880], rax
0x180015e39  call    McTemplateU0zjzz_EventWriteTransfer
0x180015e3e  mov     dword ptr [rbx+18h], 0
0x180015e45  mov     [rdi+2C8h], rbx
0x180015e4c  xor     eax, eax
0x180015e4e  jmp     loc_180015C80
```
