# WFDDiscoverOidCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)

- ea: `0x140054af0`
- end: `0x140054be0`
- name: `?WFDDiscoverOidCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z`
- size: `240`
- prototype: `void __fastcall(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400546c0`
- `0x140054af0`
- `0x14009a3d0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054b43`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054b72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054b43`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054b72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054b54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054b83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054b54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054b83`

## pseudocode

```c
void __fastcall WFDDiscoverOidCompletion(struct _ADAPT *a1, struct DOT11_NDIS_REQUEST *a2)
{
  int ndisStatus; // ebx
  char *pvContext1; // rcx
  ULONG *v6; // rcx
  int v7; // r9d
  _BYTE v8[24]; // [rsp+20h] [rbp-28h] BYREF

  ndisStatus = a2->ndisStatus;
  memset(v8, 0, sizeof(v8));
  pvContext1 = (char *)a2->pvContext1;
  if ( pvContext1 )
  {
    v6 = (ULONG *)(pvContext1 - 16);
    if ( *(_QWORD *)v6 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, v6);
    else
      ExFreePoolWithTag(v6, v6[2]);
  }
  if ( a2[-1].pCompletion )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)a2[-1].pCompletion, &a2[-1].pCompletion);
  else
    ExFreePoolWithTag(&a2[-1].pCompletion, (ULONG)a2[-1].pVElan);
  if ( ndisStatus )
  {
    if ( ndisStatus != 1076035585 )
    {
      *(_DWORD *)v8 = 1573248;
      *(_DWORD *)&v8[4] = ndisStatus;
      *(_OWORD *)&v8[8] = 0;
      WFDDiscoverCompletion(a1, (struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *)v8, 0x18u, v7);
    }
  }
}

```

## disassembly

```asm
0x140054af0  mov     [rsp+arg_10], rbx
0x140054af5  mov     [rsp+arg_18], rsi
0x140054afa  push    rdi
0x140054afb  sub     rsp, 40h
0x140054aff  mov     rax, cs:__security_cookie
0x140054b06  xor     rax, rsp
0x140054b09  mov     [rsp+48h+var_10], rax
0x140054b0e  mov     ebx, [rdx]
0x140054b10  xor     eax, eax
0x140054b12  xorps   xmm0, xmm0
0x140054b15  mov     [rsp+48h+var_18], rax
0x140054b1a  movups  [rsp+48h+var_28], xmm0
0x140054b1f  mov     rsi, rcx
0x140054b22  mov     rdi, rdx
0x140054b25  mov     rcx, [rdx+110h]
0x140054b2c  test    rcx, rcx
0x140054b2f  jz      short loc_140054B60
0x140054b31  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140054b35  mov     rax, [rcx]
0x140054b38  test    rax, rax
0x140054b3b  jz      short loc_140054B51
0x140054b3d  mov     rdx, rcx; Entry
0x140054b40  mov     rcx, rax; Lookaside
0x140054b43  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054b4a  nop     dword ptr [rax+rax+00h]
0x140054b4f  jmp     short loc_140054B60
0x140054b51  mov     edx, [rcx+8]; Tag
0x140054b54  call    cs:__imp_ExFreePoolWithTag
0x140054b5b  nop     dword ptr [rax+rax+00h]
0x140054b60  lea     rcx, [rdi-10h]; P
0x140054b64  mov     rax, [rcx]
0x140054b67  test    rax, rax
0x140054b6a  jz      short loc_140054B80
0x140054b6c  mov     rdx, rcx; Entry
0x140054b6f  mov     rcx, rax; Lookaside
0x140054b72  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054b79  nop     dword ptr [rax+rax+00h]
0x140054b7e  jmp     short loc_140054B8F
0x140054b80  mov     edx, [rcx+8]; Tag
0x140054b83  call    cs:__imp_ExFreePoolWithTag
0x140054b8a  nop     dword ptr [rax+rax+00h]
0x140054b8f  test    ebx, ebx
0x140054b91  jz      short loc_140054BC2
0x140054b93  cmp     ebx, 40230001h
0x140054b99  jz      short loc_140054BC2
0x140054b9b  xorps   xmm0, xmm0
0x140054b9e  mov     dword ptr [rsp+48h+var_28], 180180h
0x140054ba6  mov     r8d, 18h; unsigned int
0x140054bac  mov     dword ptr [rsp+48h+var_28+4], ebx
0x140054bb0  lea     rdx, [rsp+48h+var_28]; struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *
0x140054bb5  mov     rcx, rsi; struct _ADAPT *
0x140054bb8  movups  [rsp+48h+var_28+8], xmm0
0x140054bbd  call    ?WFDDiscoverCompletion@@YAXPEAU_ADAPT@@PEAU_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS@@KH@Z; WFDDiscoverCompletion(_ADAPT *,_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *,ulong,int)
0x140054bc2  mov     rcx, [rsp+48h+var_10]
0x140054bc7  xor     rcx, rsp; StackCookie
0x140054bca  call    __security_check_cookie
0x140054bcf  mov     rbx, [rsp+48h+arg_10]
0x140054bd4  mov     rsi, [rsp+48h+arg_18]
0x140054bd9  add     rsp, 40h
0x140054bdd  pop     rdi
0x140054bde  retn
```
