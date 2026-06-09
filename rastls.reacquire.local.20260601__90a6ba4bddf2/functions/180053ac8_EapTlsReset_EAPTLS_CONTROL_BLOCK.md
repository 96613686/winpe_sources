# EapTlsReset(_EAPTLS_CONTROL_BLOCK *)

- ea: `0x180053ac8`
- end: `0x180053c59`
- name: `?EapTlsReset@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z`
- size: `401`
- prototype: `unsigned int __fastcall(struct _EAPTLS_CONTROL_BLOCK *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180052198`
- `0x180053c60`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180018f50`
- `0x18001e0c0`
- `0x180029550`
- `0x1800508d4`
- `0x180053ac8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053bd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053bfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053bd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053bfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c24`
- `SspiCli!DeleteSecurityContext` at `0x180053b5e`
- `SspiCli!DeleteSecurityContext` at `0x180053b5e`

## pseudocode

```c
__int64 __fastcall EapTlsReset(struct _EAPTLS_CONTROL_BLOCK *a1)
{
  int v2; // edi
  unsigned int v3; // eax
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  *(_DWORD *)a1 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, g_szEapTlsState);
  v2 = *((_DWORD *)a1 + 1);
  *((_DWORD *)a1 + 1) = v2 & 0x75D87;
  if ( *((_QWORD *)a1 + 74) )
    *((_QWORD *)a1 + 74) = 0;
  if ( *((_BYTE *)a1 + 849) )
  {
    if ( (v2 & 0x40) == 0 )
    {
      v3 = DeleteSecurityContext((PCtxtHandle)((char *)a1 + 648));
      if ( v3 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v3);
      *(_OWORD *)((char *)a1 + 648) = 0;
    }
  }
  else
  {
    EapTlsReset_DeleteSecurityContextModern(a1);
  }
  if ( (v2 & 0x20) == 0 )
    *(_OWORD *)((char *)a1 + 616) = 0;
  *((_DWORD *)a1 + 1) |= 0x60u;
  v4 = (void *)*((_QWORD *)a1 + 67);
  if ( v4 )
  {
    RasAuthAttributeDestroy(v4);
    *((_QWORD *)a1 + 67) = 0;
  }
  LocalFree(*((HLOCAL *)a1 + 84));
  v5 = (void *)*((_QWORD *)a1 + 87);
  *((_QWORD *)a1 + 84) = 0;
  *((_QWORD *)a1 + 85) = 0;
  *((_DWORD *)a1 + 172) = 0;
  LocalFree(v5);
  v6 = (void *)*((_QWORD *)a1 + 93);
  *((_QWORD *)a1 + 87) = 0;
  *((_QWORD *)a1 + 88) = 0;
  *((_QWORD *)a1 + 89) = 0;
  LocalFree(v6);
  *((_QWORD *)a1 + 93) = 0;
  *((_DWORD *)a1 + 181) = 0;
  result = EapGetCredentials(a1);
  if ( !(_DWORD)result )
    *((_DWORD *)a1 + 1) &= ~0x20u;
  return result;
}

```

## disassembly

```asm
0x180053ac8  push    rbx
0x180053aca  push    rbp
0x180053acb  push    rsi
0x180053acc  push    rdi
0x180053acd  push    r14
0x180053acf  sub     rsp, 20h
0x180053ad3  mov     rbx, rcx
0x180053ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180053add  lea     r14, WPP_GLOBAL_Control
0x180053ae4  cmp     rcx, r14
0x180053ae7  jz      short loc_180053AFE
0x180053ae9  mov     rcx, [rcx+10h]
0x180053aed  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180053af4  mov     edx, 3Dh ; '='
0x180053af9  call    WPP_SF_
0x180053afe  xor     ebp, ebp
0x180053b00  mov     [rbx], ebp
0x180053b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b09  cmp     rcx, r14
0x180053b0c  jz      short loc_180053B28
0x180053b0e  mov     r9, cs:?g_szEapTlsState@@3PAPEADA; char * near * g_szEapTlsState
0x180053b15  lea     edx, [rbp+3Eh]
0x180053b18  mov     rcx, [rcx+10h]
0x180053b1c  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180053b23  call    WPP_SF_s
0x180053b28  mov     edi, [rbx+4]
0x180053b2b  mov     eax, edi
0x180053b2d  and     eax, 75D87h
0x180053b32  mov     [rbx+4], eax
0x180053b35  cmp     [rbx+250h], rbp
0x180053b3c  jz      short loc_180053B45
0x180053b3e  mov     [rbx+250h], rbp
0x180053b45  cmp     [rbx+351h], bpl
0x180053b4c  jz      short loc_180053B9A
0x180053b4e  test    dil, 40h
0x180053b52  jnz     short loc_180053BA2
0x180053b54  lea     rsi, [rbx+288h]
0x180053b5b  mov     rcx, rsi; phContext
0x180053b5e  call    cs:__imp_DeleteSecurityContext
0x180053b65  nop     dword ptr [rax+rax+00h]
0x180053b6a  test    eax, eax
0x180053b6c  jz      short loc_180053B92
0x180053b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b75  cmp     rcx, r14
0x180053b78  jz      short loc_180053B92
0x180053b7a  mov     rcx, [rcx+10h]
0x180053b7e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180053b85  mov     edx, 3Ch ; '<'
0x180053b8a  mov     r9d, eax
0x180053b8d  call    WPP_SF_d
0x180053b92  xorps   xmm0, xmm0
0x180053b95  movups  xmmword ptr [rsi], xmm0
0x180053b98  jmp     short loc_180053BA2
0x180053b9a  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180053b9d  call    ?EapTlsReset_DeleteSecurityContextModern@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; EapTlsReset_DeleteSecurityContextModern(_EAPTLS_CONTROL_BLOCK *)
0x180053ba2  test    dil, 20h
0x180053ba6  jnz     short loc_180053BB2
0x180053ba8  xorps   xmm0, xmm0
0x180053bab  movups  xmmword ptr [rbx+268h], xmm0
0x180053bb2  or      dword ptr [rbx+4], 60h
0x180053bb6  mov     rcx, [rbx+218h]; hMem
0x180053bbd  test    rcx, rcx
0x180053bc0  jz      short loc_180053BCE
0x180053bc2  call    RasAuthAttributeDestroy
0x180053bc7  mov     [rbx+218h], rbp
0x180053bce  mov     rcx, [rbx+2A0h]; hMem
0x180053bd5  call    cs:__imp_LocalFree
0x180053bdc  nop     dword ptr [rax+rax+00h]
0x180053be1  mov     rcx, [rbx+2B8h]; hMem
0x180053be8  mov     [rbx+2A0h], rbp
0x180053bef  mov     [rbx+2A8h], rbp
0x180053bf6  mov     [rbx+2B0h], ebp
0x180053bfc  call    cs:__imp_LocalFree
0x180053c03  nop     dword ptr [rax+rax+00h]
0x180053c08  mov     rcx, [rbx+2E8h]; hMem
0x180053c0f  mov     [rbx+2B8h], rbp
0x180053c16  mov     [rbx+2C0h], rbp
0x180053c1d  mov     [rbx+2C8h], rbp
0x180053c24  call    cs:__imp_LocalFree
0x180053c2b  nop     dword ptr [rax+rax+00h]
0x180053c30  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180053c33  mov     [rbx+2E8h], rbp
0x180053c3a  mov     [rbx+2D4h], ebp
0x180053c40  call    ?EapGetCredentials@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@@Z; EapGetCredentials(_EAPTLS_CONTROL_BLOCK *)
0x180053c45  test    eax, eax
0x180053c47  jnz     short loc_180053C4D
0x180053c49  and     dword ptr [rbx+4], 0FFFFFFDFh
0x180053c4d  add     rsp, 20h
0x180053c51  pop     r14
0x180053c53  pop     rdi
0x180053c54  pop     rsi
0x180053c55  pop     rbp
0x180053c56  pop     rbx
0x180053c57  retn
```
