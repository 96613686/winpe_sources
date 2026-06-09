# GetConfiguredInfo

- ea: `0x1800109cc`
- end: `0x180010cf4`
- name: `GetConfiguredInfo`
- size: `808`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fad4`
- `0x180013308`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000b9ac`
- `0x18000ba40`
- `0x1800109cc`
- `0x180011064`
- `0x18002a138`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall GetConfiguredInfo(__int64 a1, int a2, __int64 a3, _DWORD *a4)
{
  unsigned int v7; // esi
  _DWORD *v8; // r12
  _DWORD *v9; // r13
  _DWORD *PointerToCPCB; // rax
  _DWORD *v11; // r10
  _DWORD *v12; // rbx
  char *v13; // r9
  __int64 v14; // r8
  int v15; // eax
  unsigned int v16; // ebp
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // r9d
  const wchar_t *v21; // rdx
  __int64 result; // rax
  char pszDest[32]; // [rsp+30h] [rbp-868h] BYREF
  int v25; // [rsp+50h] [rbp-848h] BYREF
  _BYTE v26[2044]; // [rsp+54h] [rbp-844h] BYREF

  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  *(_DWORD *)a3 = 0;
  v7 = 1;
  v8 = (_DWORD *)(a3 + 4);
  *(_DWORD *)(a3 + 60) = 720;
  v9 = (_DWORD *)(a3 + 136);
  *(_DWORD *)(a3 + 4) = 720;
  *(_DWORD *)(a3 + 136) = 720;
  while ( 1 )
  {
    if ( v7 >= (unsigned int)PppConfigInfo )
    {
      if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
        StringCchCopyA(pszDest, 0x11u, (STRSAFE_LPCSTR)(*(_QWORD *)(a1 + 8) + 1284LL));
      *a4 = 1;
      return 0;
    }
    PointerToCPCB = (_DWORD *)GetPointerToCPCB(a1, v7);
    v12 = PointerToCPCB;
    if ( !PointerToCPCB[11] )
    {
      v20 = PointerToCPCB[10];
      if ( v20 )
      {
        switch ( *((_DWORD *)CpTable + 44 * v7) )
        {
          case 0x8021:
            *v8 = v20;
            break;
          case 0x8057:
            *v11 = v20;
            break;
          case 0x80FD:
            *v9 = v20;
            break;
        }
      }
      goto LABEL_35;
    }
    if ( PointerToCPCB[14] == 1 )
      return 0;
    v13 = (char *)CpTable;
    v14 = 176LL * v7;
    if ( *(_DWORD *)((char *)CpTable + v14) == 32801 )
      break;
    if ( *(_DWORD *)((char *)CpTable + v14) == 32855 )
    {
      v18 = PointerToCPCB[10];
      *v11 = v18;
      if ( !v18 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))&v13[v14 + 136])(*((_QWORD *)v12 + 2), v11);
        if ( v16 )
        {
          if ( (byte_18004CF34 & 1) == 0 )
            goto LABEL_40;
          v21 = L"IPv6CP GetNegotiatedInfo returned %d";
          goto LABEL_38;
        }
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 136LL) = *(_QWORD *)(a3 + 72);
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 144LL) = *(_QWORD *)(a3 + 80);
      }
    }
    else if ( *(_DWORD *)((char *)CpTable + v14) == 33021 )
    {
      v15 = PointerToCPCB[10];
      *v9 = v15;
      if ( !v15 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))&v13[v14 + 136])(*((_QWORD *)v12 + 2), a3 + 136);
        if ( v16 )
          goto LABEL_40;
        v17 = (unsigned __int16)*(_DWORD *)(a1 + 60);
        if ( v17 != 9 && v17 != 14 )
        {
          switch ( *(_DWORD *)(a3 + 144) & 0xF0 )
          {
            case 16:
            case 32:
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x800u;
              break;
            case 64:
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x2000u;
              break;
            case 128:
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x1000u;
              break;
          }
        }
      }
    }
LABEL_35:
    ++v7;
  }
  v19 = PointerToCPCB[10];
  *v8 = v19;
  if ( v19 )
    goto LABEL_35;
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))&v13[v14 + 136])(*((_QWORD *)v12 + 2), a3 + 4);
  if ( !v16 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 120LL) = *(_DWORD *)(a3 + 36);
    if ( *(_DWORD *)(a3 + 8) && *(_DWORD *)(a3 + 12) != v16 )
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x400u;
    goto LABEL_35;
  }
  if ( (byte_18004CF34 & 1) == 0 )
    goto LABEL_40;
  v21 = L"IPCP GetNegotiatedInfo returned %d";
LABEL_38:
  LOWORD(v25) = 0;
  FormatRRASErrorString(&v25, v21, v16);
  if ( (byte_18004CF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
      (const wchar_t *)&v25);
LABEL_40:
  v12[10] = v16;
  v12[14] = 1;
  FsmClose(a1, v7);
  result = 0;
  if ( v7 == a2 )
    return v16;
  return result;
}

```

## disassembly

```asm
0x1800109cc  mov     [rsp+arg_8], rbx
0x1800109d1  push    rbp
0x1800109d2  push    rsi
0x1800109d3  push    rdi
0x1800109d4  push    r12
0x1800109d6  push    r13
0x1800109d8  push    r14
0x1800109da  push    r15
0x1800109dc  sub     rsp, 860h
0x1800109e3  mov     rax, cs:__security_cookie
0x1800109ea  xor     rax, rsp
0x1800109ed  mov     [rsp+898h+var_48], rax
0x1800109f5  mov     r14, r8
0x1800109f8  mov     [rsp+898h+var_870], r9
0x1800109fd  mov     r15d, edx
0x180010a00  mov     rdi, rcx
0x180010a03  xor     eax, eax
0x180010a05  lea     rcx, [rsp+898h+var_844]; void *
0x180010a0a  xor     edx, edx; Val
0x180010a0c  mov     [rsp+898h+var_848], eax
0x180010a10  mov     r8d, 7FCh; Size
0x180010a16  call    memset_0
0x180010a1b  mov     eax, 2D0h
0x180010a20  mov     dword ptr [r14], 0
0x180010a27  lea     r10, [r14+3Ch]
0x180010a2b  mov     esi, 1
0x180010a30  lea     r12, [r14+4]
0x180010a34  mov     [r10], eax
0x180010a37  lea     r13, [r14+88h]
0x180010a3e  mov     [r12], eax
0x180010a42  mov     [r13+0], eax
0x180010a46  cmp     esi, dword ptr cs:PppConfigInfo
0x180010a4c  jnb     loc_180010C9C
0x180010a52  mov     edx, esi
0x180010a54  mov     rcx, rdi
0x180010a57  call    GetPointerToCPCB
0x180010a5c  mov     rbx, rax
0x180010a5f  cmp     dword ptr [rax+2Ch], 0
0x180010a63  jz      loc_180010BDC
0x180010a69  cmp     dword ptr [rax+38h], 1
0x180010a6d  jz      loc_180010CC7
0x180010a73  mov     r9, cs:CpTable
0x180010a7a  mov     ecx, esi
0x180010a7c  imul    r8, rcx, 0B0h
0x180010a83  mov     eax, [r8+r9]
0x180010a87  sub     eax, 8021h
0x180010a8c  jz      loc_180010B89
0x180010a92  sub     eax, 36h ; '6'
0x180010a95  jz      loc_180010B3D
0x180010a9b  cmp     eax, 0A6h
0x180010aa0  jnz     loc_180010C20
0x180010aa6  mov     eax, [rbx+28h]
0x180010aa9  mov     [r13+0], eax
0x180010aad  test    eax, eax
0x180010aaf  jnz     loc_180010C20
0x180010ab5  mov     rcx, [rbx+10h]
0x180010ab9  mov     rdx, r13
0x180010abc  mov     rax, [r8+r9+88h]
0x180010ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac9  mov     ebp, eax
0x180010acb  test    eax, eax
0x180010acd  jnz     loc_180010C6C
0x180010ad3  mov     eax, [rdi+3Ch]
0x180010ad6  movzx   eax, ax
0x180010ad9  cmp     eax, 9
0x180010adc  jz      loc_180010BD6
0x180010ae2  cmp     eax, 0Eh
0x180010ae5  jz      loc_180010BD6
0x180010aeb  mov     eax, [r14+90h]
0x180010af2  and     eax, 0F0h
0x180010af7  sub     eax, 10h
0x180010afa  jz      short loc_180010B2F
0x180010afc  sub     eax, 10h
0x180010aff  jz      short loc_180010B2F
0x180010b01  sub     eax, 20h ; ' '
0x180010b04  jz      short loc_180010B21
0x180010b06  lea     r10, [r14+3Ch]
0x180010b0a  cmp     eax, 40h ; '@'
0x180010b0d  jnz     loc_180010C20
0x180010b13  mov     rax, [rdi+8]
0x180010b17  bts     dword ptr [rax+34h], 0Ch
0x180010b1c  jmp     loc_180010C20
0x180010b21  mov     rax, [rdi+8]
0x180010b25  bts     dword ptr [rax+34h], 0Dh
0x180010b2a  jmp     loc_180010BD6
0x180010b2f  mov     rax, [rdi+8]
0x180010b33  bts     dword ptr [rax+34h], 0Bh
0x180010b38  jmp     loc_180010BD6
0x180010b3d  mov     eax, [rbx+28h]
0x180010b40  mov     [r10], eax
0x180010b43  test    eax, eax
0x180010b45  jnz     loc_180010C20
0x180010b4b  mov     rcx, [rbx+10h]
0x180010b4f  mov     rdx, r10
0x180010b52  mov     rax, [r8+r9+88h]
0x180010b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b5f  mov     ebp, eax
0x180010b61  test    eax, eax
0x180010b63  jnz     loc_180010C27
0x180010b69  mov     rcx, [rdi+8]
0x180010b6d  mov     rax, [r14+48h]
0x180010b71  mov     [rcx+88h], rax
0x180010b78  mov     rcx, [rdi+8]
0x180010b7c  mov     rax, [r14+50h]
0x180010b80  mov     [rcx+90h], rax
0x180010b87  jmp     short loc_180010BD6
0x180010b89  mov     eax, [rbx+28h]
0x180010b8c  mov     [r12], eax
0x180010b90  test    eax, eax
0x180010b92  jnz     loc_180010C20
0x180010b98  mov     rcx, [rbx+10h]
0x180010b9c  mov     rdx, r12
0x180010b9f  mov     rax, [r8+r9+88h]
0x180010ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bac  mov     ebp, eax
0x180010bae  test    eax, eax
0x180010bb0  jnz     loc_180010C8A
0x180010bb6  mov     rcx, [rdi+8]
0x180010bba  mov     eax, [r14+24h]
0x180010bbe  mov     [rcx+78h], eax
0x180010bc1  cmp     [r14+8], ebp
0x180010bc5  jz      short loc_180010BD6
0x180010bc7  cmp     [r14+0Ch], ebp
0x180010bcb  jz      short loc_180010BD6
0x180010bcd  mov     rax, [rdi+8]
0x180010bd1  bts     dword ptr [rax+34h], 0Ah
0x180010bd6  lea     r10, [r14+3Ch]
0x180010bda  jmp     short loc_180010C20
0x180010bdc  mov     r9d, [rax+28h]
0x180010be0  test    r9d, r9d
0x180010be3  jz      short loc_180010C20
0x180010be5  mov     rcx, cs:CpTable
0x180010bec  mov     eax, esi
0x180010bee  imul    rdx, rax, 0B0h
0x180010bf5  mov     r8d, [rdx+rcx]
0x180010bf9  sub     r8d, 8021h
0x180010c00  jz      short loc_180010C1C
0x180010c02  sub     r8d, 36h ; '6'
0x180010c06  jz      short loc_180010C17
0x180010c08  cmp     r8d, 0A6h
0x180010c0f  jnz     short loc_180010C20
0x180010c11  mov     [r13+0], r9d
0x180010c15  jmp     short loc_180010C20
0x180010c17  mov     [r10], r9d
0x180010c1a  jmp     short loc_180010C20
0x180010c1c  mov     [r12], r9d
0x180010c20  inc     esi
0x180010c22  jmp     loc_180010A46
0x180010c27  test    cs:byte_18004CF34, 1
0x180010c2e  jz      short loc_180010C6C
0x180010c30  lea     rdx, aIpv6cpGetnegot; "IPv6CP GetNegotiatedInfo returned %d"
0x180010c37  xor     eax, eax
0x180010c39  lea     rcx, [rsp+898h+var_848]
0x180010c3e  mov     r8d, ebp
0x180010c41  mov     word ptr [rsp+898h+var_848], ax
0x180010c46  call    FormatRRASErrorString
0x180010c4b  test    cs:byte_18004CF34, 1
0x180010c52  jz      short loc_180010C6C
0x180010c54  lea     r8, [rsp+898h+var_848]
0x180010c59  lea     rdx, RasPppTraceInfo
0x180010c60  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010c67  call    McTemplateU0z_EventWriteTransfer
0x180010c6c  mov     edx, esi
0x180010c6e  mov     [rbx+28h], ebp
0x180010c71  mov     rcx, rdi
0x180010c74  mov     dword ptr [rbx+38h], 1
0x180010c7b  call    FsmClose
0x180010c80  xor     eax, eax
0x180010c82  cmp     esi, r15d
0x180010c85  cmovz   eax, ebp
0x180010c88  jmp     short loc_180010CC9
0x180010c8a  test    cs:byte_18004CF34, 1
0x180010c91  jz      short loc_180010C6C
0x180010c93  lea     rdx, aIpcpGetnegotia; "IPCP GetNegotiatedInfo returned %d"
0x180010c9a  jmp     short loc_180010C37
0x180010c9c  test    byte ptr [rdi+38h], 4
0x180010ca0  jz      short loc_180010CBC
0x180010ca2  mov     r8, [rdi+8]
0x180010ca6  lea     rcx, [rsp+898h+pszDest]; pszDest
0x180010cab  add     r8, 504h; pszSrc
0x180010cb2  mov     edx, 11h; cchDest
0x180010cb7  call    StringCchCopyA
0x180010cbc  mov     rax, [rsp+898h+var_870]
0x180010cc1  mov     dword ptr [rax], 1
0x180010cc7  xor     eax, eax
0x180010cc9  mov     rcx, [rsp+898h+var_48]
0x180010cd1  xor     rcx, rsp; StackCookie
0x180010cd4  call    __security_check_cookie
0x180010cd9  mov     rbx, [rsp+898h+arg_8]
0x180010ce1  add     rsp, 860h
0x180010ce8  pop     r15
0x180010cea  pop     r14
0x180010cec  pop     r13
0x180010cee  pop     r12
0x180010cf0  pop     rdi
0x180010cf1  pop     rsi
0x180010cf2  pop     rbp
0x180010cf3  retn
```
