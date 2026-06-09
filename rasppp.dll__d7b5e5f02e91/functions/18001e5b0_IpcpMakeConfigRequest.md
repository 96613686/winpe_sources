# IpcpMakeConfigRequest

- ea: `0x18001e5b0`
- end: `0x18001e81e`
- name: `IpcpMakeConfigRequest`
- size: `622`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001e5b0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18001e609`: `IPCP: IpcpMakeConfigRequest`
- `0x18001e7b0`: `IPCP: ConfigRequest...`
- `0x18001e7d6`: `Dumping Bytes ConfigRequest`

## pseudocode

```c
__int64 __fastcall IpcpMakeConfigRequest(__int64 a1, _BYTE *a2)
{
  __int64 v4; // rdx
  unsigned __int16 v6; // si
  _BYTE *v7; // rdi
  __int16 v8; // cx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v15[2044]; // [rsp+34h] [rbp-824h] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v4 = *((_QWORD *)&xmmword_18004D860 + 1);
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: IpcpMakeConfigRequest");
    v4 = *((_QWORD *)&xmmword_18004D860 + 1);
  }
  if ( *(_DWORD *)(a1 + 1260) )
  {
    if ( (_QWORD)xmmword_18004D860 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString((wchar_t *)&v14, L"IPCP: Deferred IpcpBegin error=%d");
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, xmmword_18004D860, &v14);
    }
    return *(unsigned int *)(a1 + 1260);
  }
  else
  {
    v6 = 4;
    v7 = a2 + 4;
    if ( ++*(_DWORD *)(a1 + 92) >= (unsigned int)DwMaxMSOptionCfgCnt )
    {
      if ( v4 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          v4,
          L"IPCP: Tossing MS options (request timeouts)");
        v4 = *((_QWORD *)&xmmword_18004D860 + 1);
      }
      *(_DWORD *)(a1 + 56) = 1;
      *(_DWORD *)(a1 + 40) = 1;
      *(_DWORD *)(a1 + 44) = 1;
      *(_DWORD *)(a1 + 48) = 1;
      *(_DWORD *)(a1 + 52) = 1;
    }
    if ( !*(_DWORD *)(a1 + 32) )
    {
      *(_WORD *)v7 = 1538;
      v6 = 10;
      v8 = *(_WORD *)(a1 + 176);
      a2[7] = v8;
      a2[6] = HIBYTE(v8);
      a2[8] = *(_BYTE *)(a1 + 178);
      a2[9] = *(_BYTE *)(a1 + 179);
      v7 = a2 + 10;
    }
    if ( !*(_DWORD *)(a1 + 36) && !*(_DWORD *)(a1 + 60) )
    {
      v9 = *(_DWORD *)(a1 + 144);
      v6 += 6;
      *(_WORD *)v7 = 1539;
      *(_DWORD *)(v7 + 2) = v9;
      v7 += 6;
    }
    if ( !*(_DWORD *)a1 )
    {
      if ( !*(_DWORD *)(a1 + 40) )
      {
        v10 = *(_DWORD *)(a1 + 104);
        v6 += 6;
        *(_WORD *)v7 = 1665;
        *(_DWORD *)(v7 + 2) = v10;
        v7 += 6;
      }
      if ( !*(_DWORD *)(a1 + 44) )
      {
        v11 = *(_DWORD *)(a1 + 96);
        v6 += 6;
        *(_WORD *)v7 = 1666;
        *(_DWORD *)(v7 + 2) = v11;
        v7 += 6;
      }
      if ( !*(_DWORD *)(a1 + 48) )
      {
        v12 = *(_DWORD *)(a1 + 108);
        v6 += 6;
        *(_WORD *)v7 = 1667;
        *(_DWORD *)(v7 + 2) = v12;
        v7 += 6;
      }
      if ( !*(_DWORD *)(a1 + 52) )
      {
        v13 = *(_DWORD *)(a1 + 100);
        v6 += 6;
        *(_WORD *)v7 = 1668;
        *(_DWORD *)(v7 + 2) = v13;
      }
    }
    *a2 = 1;
    a2[2] = HIBYTE(v6);
    a2[3] = v6;
    if ( v4 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v4,
        L"IPCP: ConfigRequest...");
    if ( qword_18004D880 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, _BYTE *))gRasIpcpByteTemplateFunc)(
        gRasIpcpEtwContext,
        qword_18004D880,
        L"Dumping Bytes ConfigRequest",
        v6,
        a2);
    return 0;
  }
}

```

## disassembly

```asm
0x18001e5b0  mov     [rsp+arg_10], rbx
0x18001e5b5  mov     [rsp+arg_18], rsi
0x18001e5ba  push    rdi
0x18001e5bb  push    r14
0x18001e5bd  push    r15
0x18001e5bf  sub     rsp, 840h
0x18001e5c6  mov     rax, cs:__security_cookie
0x18001e5cd  xor     rax, rsp
0x18001e5d0  mov     [rsp+858h+var_28], rax
0x18001e5d8  mov     r14, rdx
0x18001e5db  mov     rbx, rcx
0x18001e5de  xor     eax, eax
0x18001e5e0  lea     rcx, [rsp+858h+var_824]; void *
0x18001e5e5  xor     edx, edx; Val
0x18001e5e7  mov     [rsp+858h+var_828], eax
0x18001e5eb  mov     r8d, 7FCh; Size
0x18001e5f1  call    memset_0
0x18001e5f6  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001e5fd  test    rdx, rdx
0x18001e600  jz      short loc_18001E623
0x18001e602  mov     rcx, cs:gRasIpcpEtwContext
0x18001e609  lea     r8, aIpcpIpcpmakeco_0; "IPCP: IpcpMakeConfigRequest"
0x18001e610  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e61c  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001e623  mov     r8d, [rbx+4ECh]
0x18001e62a  test    r8d, r8d
0x18001e62d  jz      short loc_18001E67B
0x18001e62f  cmp     qword ptr cs:xmmword_18004D860, 0
0x18001e637  jz      short loc_18001E670
0x18001e639  xor     eax, eax
0x18001e63b  lea     rdx, aIpcpDeferredIp; "IPCP: Deferred IpcpBegin error=%d"
0x18001e642  lea     rcx, [rsp+858h+var_828]
0x18001e647  mov     word ptr [rsp+858h+var_828], ax
0x18001e64c  call    FormatRRASErrorString
0x18001e651  mov     rdx, qword ptr cs:xmmword_18004D860
0x18001e658  lea     r8, [rsp+858h+var_828]
0x18001e65d  mov     rcx, cs:gRasIpcpEtwContext
0x18001e664  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e670  mov     eax, [rbx+4ECh]
0x18001e676  jmp     loc_18001E7F4
0x18001e67b  mov     esi, 4
0x18001e680  lea     rdi, [r14+4]
0x18001e684  lea     r15d, [rsi-3]
0x18001e688  add     [rbx+5Ch], r15d
0x18001e68c  mov     eax, [rbx+5Ch]
0x18001e68f  cmp     eax, cs:DwMaxMSOptionCfgCnt
0x18001e695  jb      short loc_18001E6D1
0x18001e697  test    rdx, rdx
0x18001e69a  jz      short loc_18001E6BD
0x18001e69c  mov     rcx, cs:gRasIpcpEtwContext
0x18001e6a3  lea     r8, aIpcpTossingMsO; "IPCP: Tossing MS options (request timeo"...
0x18001e6aa  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6b6  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001e6bd  mov     [rbx+38h], r15d
0x18001e6c1  mov     [rbx+28h], r15d
0x18001e6c5  mov     [rbx+2Ch], r15d
0x18001e6c9  mov     [rbx+30h], r15d
0x18001e6cd  mov     [rbx+34h], r15d
0x18001e6d1  cmp     dword ptr [rbx+20h], 0
0x18001e6d5  mov     r8d, 6
0x18001e6db  jnz     short loc_18001E70F
0x18001e6dd  mov     word ptr [rdi], 602h
0x18001e6e2  lea     esi, [r8+4]
0x18001e6e6  movzx   ecx, word ptr [rbx+0B0h]
0x18001e6ed  mov     [rdi+3], cl
0x18001e6f0  movzx   eax, cx
0x18001e6f3  shr     ax, 8
0x18001e6f7  mov     [rdi+2], al
0x18001e6fa  mov     al, [rbx+0B2h]
0x18001e700  mov     [rdi+4], al
0x18001e703  mov     al, [rbx+0B3h]
0x18001e709  mov     [rdi+5], al
0x18001e70c  add     rdi, r8
0x18001e70f  cmp     dword ptr [rbx+24h], 0
0x18001e713  jnz     short loc_18001E730
0x18001e715  cmp     dword ptr [rbx+3Ch], 0
0x18001e719  jnz     short loc_18001E730
0x18001e71b  mov     eax, [rbx+90h]
0x18001e721  add     si, r8w
0x18001e725  mov     word ptr [rdi], 603h
0x18001e72a  mov     [rdi+2], eax
0x18001e72d  add     rdi, r8
0x18001e730  cmp     dword ptr [rbx], 0
0x18001e733  jnz     short loc_18001E792
0x18001e735  cmp     dword ptr [rbx+28h], 0
0x18001e739  jnz     short loc_18001E74D
0x18001e73b  mov     eax, [rbx+68h]
0x18001e73e  add     si, r8w
0x18001e742  mov     word ptr [rdi], 681h
0x18001e747  mov     [rdi+2], eax
0x18001e74a  add     rdi, r8
0x18001e74d  cmp     dword ptr [rbx+2Ch], 0
0x18001e751  jnz     short loc_18001E765
0x18001e753  mov     eax, [rbx+60h]
0x18001e756  add     si, r8w
0x18001e75a  mov     word ptr [rdi], 682h
0x18001e75f  mov     [rdi+2], eax
0x18001e762  add     rdi, r8
0x18001e765  cmp     dword ptr [rbx+30h], 0
0x18001e769  jnz     short loc_18001E77D
0x18001e76b  mov     eax, [rbx+6Ch]
0x18001e76e  add     si, r8w
0x18001e772  mov     word ptr [rdi], 683h
0x18001e777  mov     [rdi+2], eax
0x18001e77a  add     rdi, r8
0x18001e77d  cmp     dword ptr [rbx+34h], 0
0x18001e781  jnz     short loc_18001E792
0x18001e783  mov     eax, [rbx+64h]
0x18001e786  add     si, r8w
0x18001e78a  mov     word ptr [rdi], 684h
0x18001e78f  mov     [rdi+2], eax
0x18001e792  mov     [r14], r15b
0x18001e795  movzx   eax, si
0x18001e798  shr     ax, 8
0x18001e79c  mov     [r14+2], al
0x18001e7a0  mov     [r14+3], sil
0x18001e7a4  test    rdx, rdx
0x18001e7a7  jz      short loc_18001E7C3
0x18001e7a9  mov     rcx, cs:gRasIpcpEtwContext
0x18001e7b0  lea     r8, aIpcpConfigrequ; "IPCP: ConfigRequest..."
0x18001e7b7  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7c3  mov     rdx, cs:qword_18004D880
0x18001e7ca  test    rdx, rdx
0x18001e7cd  jz      short loc_18001E7F2
0x18001e7cf  mov     rcx, cs:gRasIpcpEtwContext
0x18001e7d6  lea     r8, aDumpingBytesCo; "Dumping Bytes ConfigRequest"
0x18001e7dd  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001e7e4  movzx   r9d, si
0x18001e7e8  mov     [rsp+858h+var_838], r14
0x18001e7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7f2  xor     eax, eax
0x18001e7f4  mov     rcx, [rsp+858h+var_28]
0x18001e7fc  xor     rcx, rsp; StackCookie
0x18001e7ff  call    __security_check_cookie
0x18001e804  lea     r11, [rsp+858h+var_18]
0x18001e80c  mov     rbx, [r11+30h]
0x18001e810  mov     rsi, [r11+38h]
0x18001e814  mov     rsp, r11
0x18001e817  pop     r15
0x18001e819  pop     r14
0x18001e81b  pop     rdi
0x18001e81c  retn
```
