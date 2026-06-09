# WanAllocateECP

- ea: `0x140024a80`
- end: `0x140024d5f`
- name: `WanAllocateECP`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14002aa40`

## callees

- `0x14000a290`
- `0x14000a2c0`
- `0x140016700`
- `0x140024728`
- `0x1400247c4`
- `0x140024a80`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024cc9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024d03`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024cc9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024d03`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024ae9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024bea`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024ae9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024bea`

## pseudocode

```c
__int64 __fastcall WanAllocateECP(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  char v4; // r14
  PDEVICE_OBJECT v8; // rcx
  _QWORD *v9; // rax
  int v10; // eax
  unsigned int CryptoMSChapV2; // eax
  unsigned int v13; // edi
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  char *v15; // rax
  int v16; // edx
  __int64 v17; // r8
  __int64 v18; // r9
  void *v19; // rdx
  void *v20; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v21; // rcx

  v4 = a4;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids);
  }
  if ( (a2[14] & 0xF0) == 0 )
    goto LABEL_37;
  if ( *(_QWORD *)(a3 + 40) )
  {
LABEL_9:
    *(_DWORD *)a3 |= (a2[26] >> 1) & 1;
    v10 = a2[15];
    switch ( v10 )
    {
      case 1:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids);
        }
        return 3221225659LL;
      case 2:
        LOBYTE(a4) = v4;
        CryptoMSChapV2 = AllocateCryptoMSChapV2(v8, a2, a3, a4);
        break;
      case 3:
        CryptoMSChapV2 = AllocateCryptoEap(v8, a2, a3);
        break;
      default:
        v13 = -1073741823;
        goto LABEL_43;
    }
    v13 = CryptoMSChapV2;
    if ( !v4 && !*(_QWORD *)(a3 + 56) )
    {
      v14 = &CachedKeyListLong;
      if ( (a2[14] & 0x40) == 0 )
        v14 = &CachedKeyList;
      v15 = (char *)ExAllocateFromNPagedLookasideList(v14);
      *(_QWORD *)(a3 + 56) = v15;
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids);
        }
        v13 = -1073741670;
        goto LABEL_43;
      }
      v16 = glCachedKeyCount;
      v17 = (unsigned int)glCachedKeyCount;
      v18 = *(unsigned int *)(a3 + 36) + 2LL;
      *(_QWORD *)(a3 + 64) = v15;
      *(_QWORD *)(a3 + 72) = &v15[v18 * (unsigned int)(v16 - 1)];
      memset(v15, 255, v18 * v17);
    }
    if ( !v13 )
    {
      *(_DWORD *)(a1 + 16) |= 4u;
LABEL_37:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids);
      }
      return 0;
    }
LABEL_43:
    v19 = *(void **)(a3 + 40);
    if ( v19 )
    {
      ExFreeToNPagedLookasideList(&EncryptCtxList, v19);
      *(_QWORD *)(a3 + 48) = 0;
      *(_QWORD *)(a3 + 40) = 0;
    }
    v20 = *(void **)(a3 + 56);
    if ( v20 )
    {
      v21 = &CachedKeyListLong;
      if ( (a2[14] & 0x40) == 0 )
        v21 = &CachedKeyList;
      ExFreeToNPagedLookasideList(v21, v20);
      *(_QWORD *)(a3 + 56) = 0;
      *(_QWORD *)(a3 + 72) = 0;
      *(_QWORD *)(a3 + 64) = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids, v13);
    }
    return v13;
  }
  v9 = ExAllocateFromNPagedLookasideList(&EncryptCtxList);
  if ( v9 )
  {
    v8 = 0;
    *(_OWORD *)v9 = 0;
    v9[2] = 0;
    *(_QWORD *)(a3 + 40) = v9;
    *(_QWORD *)(a3 + 48) = (unsigned __int64)(v9 + 2) & 0xFFFFFFFFFFFFFFF8uLL;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140024a80  push    rbx
0x140024a82  push    rbp
0x140024a83  push    rsi
0x140024a84  push    rdi
0x140024a85  push    r12
0x140024a87  push    r13
0x140024a89  push    r14
0x140024a8b  sub     rsp, 20h
0x140024a8f  mov     r14b, r9b
0x140024a92  mov     rbx, r8
0x140024a95  mov     rsi, rdx
0x140024a98  mov     rbp, rcx
0x140024a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024aa2  lea     r13, WPP_GLOBAL_Control
0x140024aa9  cmp     rcx, r13
0x140024aac  jz      short loc_140024AD0
0x140024aae  bt      dword ptr [rcx+2Ch], 9
0x140024ab3  jnb     short loc_140024AD0
0x140024ab5  cmp     byte ptr [rcx+29h], 5
0x140024ab9  jb      short loc_140024AD0
0x140024abb  mov     rcx, [rcx+18h]
0x140024abf  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024ac6  mov     edx, 0Ah
0x140024acb  call    WPP_SF_
0x140024ad0  mov     eax, [rsi+38h]
0x140024ad3  test    al, 0F0h
0x140024ad5  jz      loc_140024C74
0x140024adb  cmp     qword ptr [rbx+28h], 0
0x140024ae0  jnz     short loc_140024B16
0x140024ae2  lea     rcx, EncryptCtxList; Lookaside
0x140024ae9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140024af0  nop     dword ptr [rax+rax+00h]
0x140024af5  test    rax, rax
0x140024af8  jz      short loc_140024B5E
0x140024afa  xor     ecx, ecx
0x140024afc  xorps   xmm0, xmm0
0x140024aff  movups  xmmword ptr [rax], xmm0
0x140024b02  mov     [rax+10h], rcx
0x140024b06  mov     [rbx+28h], rax
0x140024b0a  add     rax, 10h
0x140024b0e  and     rax, 0FFFFFFFFFFFFFFF8h
0x140024b12  mov     [rbx+30h], rax
0x140024b16  mov     eax, [rsi+68h]
0x140024b19  shr     eax, 1
0x140024b1b  and     eax, 1
0x140024b1e  or      [rbx], eax
0x140024b20  mov     eax, [rsi+3Ch]
0x140024b23  cmp     eax, 1
0x140024b26  jnz     short loc_140024B96
0x140024b28  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b2f  cmp     rcx, r13
0x140024b32  jz      short loc_140024B54
0x140024b34  bt      dword ptr [rcx+2Ch], 9
0x140024b39  jnb     short loc_140024B54
0x140024b3b  cmp     byte ptr [rcx+29h], 3
0x140024b3f  jb      short loc_140024B54
0x140024b41  mov     rcx, [rcx+18h]
0x140024b45  lea     edx, [rax+0Bh]
0x140024b48  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024b4f  call    WPP_SF_
0x140024b54  mov     eax, 0C00000BBh
0x140024b59  jmp     loc_140024CA4
0x140024b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b65  cmp     rcx, r13
0x140024b68  jz      short loc_140024B8C
0x140024b6a  bt      dword ptr [rcx+2Ch], 9
0x140024b6f  jnb     short loc_140024B8C
0x140024b71  cmp     byte ptr [rcx+29h], 3
0x140024b75  jb      short loc_140024B8C
0x140024b77  mov     rcx, [rcx+18h]
0x140024b7b  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024b82  mov     edx, 0Bh
0x140024b87  call    WPP_SF_
0x140024b8c  mov     eax, 0C000009Ah
0x140024b91  jmp     loc_140024CA4
0x140024b96  cmp     eax, 2
0x140024b99  jnz     short loc_140024BAB
0x140024b9b  mov     r9b, r14b
0x140024b9e  mov     r8, rbx
0x140024ba1  mov     rdx, rsi
0x140024ba4  call    AllocateCryptoMSChapV2
0x140024ba9  jmp     short loc_140024BBF
0x140024bab  cmp     eax, 3
0x140024bae  jnz     loc_140024CB4
0x140024bb4  mov     r8, rbx
0x140024bb7  mov     rdx, rsi
0x140024bba  call    AllocateCryptoEap
0x140024bbf  mov     edi, eax
0x140024bc1  test    r14b, r14b
0x140024bc4  jnz     loc_140024C6C
0x140024bca  cmp     qword ptr [rbx+38h], 0
0x140024bcf  jnz     loc_140024C6C
0x140024bd5  mov     eax, [rsi+38h]
0x140024bd8  lea     rcx, CachedKeyListLong
0x140024bdf  test    al, 40h
0x140024be1  jnz     short loc_140024BEA
0x140024be3  lea     rcx, CachedKeyList; Lookaside
0x140024bea  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140024bf1  nop     dword ptr [rax+rax+00h]
0x140024bf6  mov     [rbx+38h], rax
0x140024bfa  mov     r10, rax
0x140024bfd  test    rax, rax
0x140024c00  jnz     short loc_140024C38
0x140024c02  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c09  cmp     rcx, r13
0x140024c0c  jz      short loc_140024C2E
0x140024c0e  bt      dword ptr [rcx+2Ch], 9
0x140024c13  jnb     short loc_140024C2E
0x140024c15  cmp     byte ptr [rcx+29h], 3
0x140024c19  jb      short loc_140024C2E
0x140024c1b  mov     rcx, [rcx+18h]
0x140024c1f  lea     edx, [rax+0Dh]
0x140024c22  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024c29  call    WPP_SF_
0x140024c2e  mov     edi, 0C000009Ah
0x140024c33  jmp     loc_140024CB9
0x140024c38  mov     edx, cs:glCachedKeyCount
0x140024c3e  mov     r9d, [rbx+24h]
0x140024c42  mov     r8d, edx
0x140024c45  add     r9, 2
0x140024c49  mov     [rbx+40h], r10
0x140024c4d  imul    r8, r9; Size
0x140024c51  lea     ecx, [rdx-1]
0x140024c54  mov     edx, 0FFh; Val
0x140024c59  imul    rcx, r9
0x140024c5d  add     rcx, r10
0x140024c60  mov     [rbx+48h], rcx
0x140024c64  mov     rcx, r10; void *
0x140024c67  call    memset
0x140024c6c  test    edi, edi
0x140024c6e  jnz     short loc_140024CB9
0x140024c70  or      dword ptr [rbp+10h], 4
0x140024c74  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c7b  cmp     rcx, r13
0x140024c7e  jz      short loc_140024CA2
0x140024c80  bt      dword ptr [rcx+2Ch], 9
0x140024c85  jnb     short loc_140024CA2
0x140024c87  cmp     byte ptr [rcx+29h], 5
0x140024c8b  jb      short loc_140024CA2
0x140024c8d  mov     rcx, [rcx+18h]
0x140024c91  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024c98  mov     edx, 0Fh
0x140024c9d  call    WPP_SF_
0x140024ca2  xor     eax, eax
0x140024ca4  add     rsp, 20h
0x140024ca8  pop     r14
0x140024caa  pop     r13
0x140024cac  pop     r12
0x140024cae  pop     rdi
0x140024caf  pop     rsi
0x140024cb0  pop     rbp
0x140024cb1  pop     rbx
0x140024cb2  retn
0x140024cb4  mov     edi, 0C0000001h
0x140024cb9  mov     rdx, [rbx+28h]; Entry
0x140024cbd  test    rdx, rdx
0x140024cc0  jz      short loc_140024CE5
0x140024cc2  lea     rcx, EncryptCtxList; Lookaside
0x140024cc9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024cd0  nop     dword ptr [rax+rax+00h]
0x140024cd5  mov     qword ptr [rbx+30h], 0
0x140024cdd  mov     qword ptr [rbx+28h], 0
0x140024ce5  mov     rdx, [rbx+38h]; Entry
0x140024ce9  test    rdx, rdx
0x140024cec  jz      short loc_140024D27
0x140024cee  mov     eax, [rsi+38h]
0x140024cf1  lea     rcx, CachedKeyListLong
0x140024cf8  test    al, 40h
0x140024cfa  jnz     short loc_140024D03
0x140024cfc  lea     rcx, CachedKeyList; Lookaside
0x140024d03  call    cs:__imp_ExFreeToNPagedLookasideList
0x140024d0a  nop     dword ptr [rax+rax+00h]
0x140024d0f  mov     qword ptr [rbx+38h], 0
0x140024d17  mov     qword ptr [rbx+48h], 0
0x140024d1f  mov     qword ptr [rbx+40h], 0
0x140024d27  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d2e  cmp     rcx, r13
0x140024d31  jz      short loc_140024D58
0x140024d33  bt      dword ptr [rcx+2Ch], 9
0x140024d38  jnb     short loc_140024D58
0x140024d3a  cmp     byte ptr [rcx+29h], 3
0x140024d3e  jb      short loc_140024D58
0x140024d40  mov     rcx, [rcx+18h]
0x140024d44  lea     r8, WPP_e3dccf6fd86a38f3a431f6838d605fbf_Traceguids
0x140024d4b  mov     edx, 0Eh
0x140024d50  mov     r9d, edi
0x140024d53  call    WPP_SF_d
0x140024d58  mov     eax, edi
0x140024d5a  jmp     loc_140024CA4
```
