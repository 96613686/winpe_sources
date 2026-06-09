# DfsAddStandaloneRoot(ushort const *,ushort const *,ushort const *,uchar)

- ea: `0x140010924`
- end: `0x140010b23`
- name: `?DfsAddStandaloneRoot@@YAKPEBG00E@Z`
- size: `511`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140003f60`

## callees

- `0x140005b28`
- `0x14000abc4`
- `0x1400102a8`
- `0x140010924`
- `0x140012748`
- `0x140012808`
- `0x140012f74`
- `0x140014434`
- `0x1400144ac`
- `0x140018ae0`
- `0x140021e40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010aa0`
- `CLUSAPI!CloseCluster` at `0x140010a29`
- `CLUSAPI!CloseCluster` at `0x140010a29`
- `CLUSAPI!OpenCluster` at `0x1400109f4`
- `CLUSAPI!OpenCluster` at `0x1400109f4`

## pseudocode

```c
__int64 __fastcall DfsAddStandaloneRoot(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 a4)
{
  unsigned int *v8; // r10
  unsigned int IsCluster; // ebx
  struct _HCLUSTER *v10; // rax
  struct _HCLUSTER *v11; // rbp
  DfsRegistryStore *v12; // rbp
  struct DfsRegistryStore *v14; // [rsp+30h] [rbp-38h] BYREF
  int v15; // [rsp+70h] [rbp+8h] BYREF

  v14 = 0;
  LOBYTE(v15) = 0;
  v8 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x40) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)pWppControl + 2), 22, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids, a2);
    v8 = pWppControl;
  }
  if ( !a1 || !*a1 || !a2 || !*a2 )
  {
    IsCluster = 87;
    goto LABEL_23;
  }
  a1 = (unsigned __int16 *)DfsSkipLeadingPathSep(a1);
  IsCluster = DfsNodeIsCluster(a1, (unsigned __int8 *)&v15);
  if ( !IsCluster )
  {
    if ( !(_BYTE)v15 )
      goto LABEL_16;
    v10 = OpenCluster(a1);
    v11 = v10;
    if ( v10 )
    {
      v15 = 0;
      IsCluster = DfsIsResourceExists(v10, a1, a2, &v15);
      CloseCluster(v11);
      if ( !IsCluster )
      {
        if ( v15 || (IsCluster = DfsCreateClusterResource(a1, a2), IsCluster == 5047) )
        {
LABEL_16:
          IsCluster = DfsGetRegistryStore(&v14);
          if ( !IsCluster )
          {
            v12 = v14;
            IsCluster = DfsStore::CheckSKULimit(v14);
            if ( !IsCluster )
              IsCluster = DfsRegistryStore::CreateStandaloneRoot(v12, a1, a2, a3, a4);
            DfsGeneric::ReleaseReference(v12);
          }
        }
      }
    }
    else
    {
      IsCluster = GetLastError();
    }
  }
  v8 = pWppControl;
LABEL_23:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v8
    && (((1 << (IsCluster != 0 ? 11 : 31)) | 0x40) & v8[7]) != 0
    && *((_BYTE *)v8 + 25) >= 2u )
  {
    WPP_SF_DSS(*((_QWORD *)v8 + 2), 23, (_DWORD)a3, IsCluster, (__int64)a1, (__int64)a2);
  }
  return IsCluster;
}

```

## disassembly

```asm
0x140010924  mov     rax, rsp
0x140010927  mov     [rax+10h], rbx
0x14001092b  mov     [rax+18h], rbp
0x14001092f  mov     [rax+20h], rsi
0x140010933  push    rdi
0x140010934  push    r12
0x140010936  push    r13
0x140010938  push    r14
0x14001093a  push    r15
0x14001093c  sub     rsp, 40h
0x140010940  xor     r13d, r13d
0x140010943  mov     r15b, r9b
0x140010946  mov     [rax-38h], r13
0x14001094a  mov     r12, r8
0x14001094d  mov     [rax+8], r13b
0x140010951  mov     rsi, rdx
0x140010954  mov     rdi, rcx
0x140010957  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001095e  lea     rax, WPP_GLOBAL_Control
0x140010965  cmp     cs:WPP_GLOBAL_Control, rax
0x14001096c  lea     r14d, [r13+40h]
0x140010970  jz      short loc_1400109A2
0x140010972  test    r10, r10
0x140010975  jz      short loc_1400109A2
0x140010977  test    [r10+1Ch], r14b
0x14001097b  jz      short loc_1400109A2
0x14001097d  cmp     byte ptr [r10+19h], 2
0x140010982  jb      short loc_1400109A2
0x140010984  mov     rcx, [r10+10h]
0x140010988  lea     edx, [r13+16h]
0x14001098c  mov     r9, rsi
0x14001098f  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140010996  call    WPP_SF_S
0x14001099b  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400109a2  test    rdi, rdi
0x1400109a5  jz      loc_140010AB0
0x1400109ab  cmp     [rdi], r13w
0x1400109af  jz      loc_140010AB0
0x1400109b5  test    rsi, rsi
0x1400109b8  jz      loc_140010AB0
0x1400109be  cmp     [rsi], r13w
0x1400109c2  jz      loc_140010AB0
0x1400109c8  mov     rcx, rdi; unsigned __int16 *
0x1400109cb  call    ?DfsSkipLeadingPathSep@@YAPEBGPEBG@Z; DfsSkipLeadingPathSep(ushort const *)
0x1400109d0  mov     rcx, rax; unsigned __int16 *
0x1400109d3  lea     rdx, [rsp+68h+arg_0]; unsigned __int8 *
0x1400109d8  mov     rdi, rax
0x1400109db  call    ?DfsNodeIsCluster@@YAKPEBGPEAE@Z; DfsNodeIsCluster(ushort const *,uchar *)
0x1400109e0  mov     ebx, eax
0x1400109e2  test    eax, eax
0x1400109e4  jnz     loc_140010A97
0x1400109ea  cmp     byte ptr [rsp+68h+arg_0], r13b
0x1400109ef  jz      short loc_140010A54
0x1400109f1  mov     rcx, rdi; lpszClusterName
0x1400109f4  call    cs:__imp_OpenCluster
0x1400109fb  nop     dword ptr [rax+rax+00h]
0x140010a00  mov     rbp, rax
0x140010a03  test    rax, rax
0x140010a06  jz      loc_140010AA0
0x140010a0c  lea     r9, [rsp+68h+arg_0]; int *
0x140010a11  mov     [rsp+68h+arg_0], r13d
0x140010a16  mov     r8, rsi; unsigned __int16 *
0x140010a19  mov     rdx, rdi; unsigned __int16 *
0x140010a1c  mov     rcx, rax; struct _HCLUSTER *
0x140010a1f  call    ?DfsIsResourceExists@@YAKPEAU_HCLUSTER@@PEBG1PEAH@Z; DfsIsResourceExists(_HCLUSTER *,ushort const *,ushort const *,int *)
0x140010a24  mov     rcx, rbp; hCluster
0x140010a27  mov     ebx, eax
0x140010a29  call    cs:__imp_CloseCluster
0x140010a30  nop     dword ptr [rax+rax+00h]
0x140010a35  test    ebx, ebx
0x140010a37  jnz     short loc_140010A97
0x140010a39  cmp     [rsp+68h+arg_0], r13d
0x140010a3e  jnz     short loc_140010A54
0x140010a40  mov     rdx, rsi; unsigned __int16 *
0x140010a43  mov     rcx, rdi; unsigned __int16 *
0x140010a46  call    ?DfsCreateClusterResource@@YAKPEBG0@Z; DfsCreateClusterResource(ushort const *,ushort const *)
0x140010a4b  mov     ebx, eax
0x140010a4d  cmp     eax, 13B7h
0x140010a52  jnz     short loc_140010A97
0x140010a54  lea     rcx, [rsp+68h+var_38]; struct DfsRegistryStore **
0x140010a59  call    ?DfsGetRegistryStore@@YAKPEAPEAVDfsRegistryStore@@@Z; DfsGetRegistryStore(DfsRegistryStore * *)
0x140010a5e  mov     ebx, eax
0x140010a60  test    eax, eax
0x140010a62  jnz     short loc_140010A97
0x140010a64  mov     rbp, [rsp+68h+var_38]
0x140010a69  mov     rcx, rbp; this
0x140010a6c  call    ?CheckSKULimit@DfsStore@@QEAAKXZ; DfsStore::CheckSKULimit(void)
0x140010a71  mov     ebx, eax
0x140010a73  test    eax, eax
0x140010a75  jnz     short loc_140010A8F
0x140010a77  mov     r9, r12; unsigned __int16 *
0x140010a7a  mov     [rsp+68h+var_48], r15b; unsigned __int8
0x140010a7f  mov     r8, rsi; unsigned __int16 *
0x140010a82  mov     rdx, rdi; unsigned __int16 *
0x140010a85  mov     rcx, rbp; this
0x140010a88  call    ?CreateStandaloneRoot@DfsRegistryStore@@QEAAKPEBG00E@Z; DfsRegistryStore::CreateStandaloneRoot(ushort const *,ushort const *,ushort const *,uchar)
0x140010a8d  mov     ebx, eax
0x140010a8f  mov     rcx, rbp; this
0x140010a92  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x140010a97  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140010a9e  jmp     short loc_140010AB5
0x140010aa0  call    cs:__imp_GetLastError
0x140010aa7  nop     dword ptr [rax+rax+00h]
0x140010aac  mov     ebx, eax
0x140010aae  jmp     short loc_140010A97
0x140010ab0  mov     ebx, 57h ; 'W'
0x140010ab5  lea     rax, WPP_GLOBAL_Control
0x140010abc  cmp     cs:WPP_GLOBAL_Control, rax
0x140010ac3  jz      short loc_140010B02
0x140010ac5  test    r10, r10
0x140010ac8  jz      short loc_140010B02
0x140010aca  mov     eax, ebx
0x140010acc  neg     eax
0x140010ace  sbb     ecx, ecx
0x140010ad0  and     ecx, 0FFFFFFECh
0x140010ad3  add     ecx, 1Fh
0x140010ad6  bts     r14d, ecx
0x140010ada  test    [r10+1Ch], r14d
0x140010ade  jz      short loc_140010B02
0x140010ae0  cmp     byte ptr [r10+19h], 2
0x140010ae5  jb      short loc_140010B02
0x140010ae7  mov     rcx, [r10+10h]
0x140010aeb  mov     edx, 17h
0x140010af0  mov     [rsp+68h+var_40], rsi
0x140010af5  mov     r9d, ebx
0x140010af8  mov     qword ptr [rsp+68h+var_48], rdi
0x140010afd  call    WPP_SF_DSS
0x140010b02  lea     r11, [rsp+68h+var_28]
0x140010b07  mov     eax, ebx
0x140010b09  mov     rbx, [r11+38h]
0x140010b0d  mov     rbp, [r11+40h]
0x140010b11  mov     rsi, [r11+48h]
0x140010b15  mov     rsp, r11
0x140010b18  pop     r15
0x140010b1a  pop     r14
0x140010b1c  pop     r13
0x140010b1e  pop     r12
0x140010b20  pop     rdi
0x140010b21  retn
```
