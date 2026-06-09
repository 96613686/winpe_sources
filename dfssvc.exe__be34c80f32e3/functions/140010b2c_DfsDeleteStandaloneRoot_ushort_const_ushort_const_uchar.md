# DfsDeleteStandaloneRoot(ushort const *,ushort const *,uchar)

- ea: `0x140010b2c`
- end: `0x140010d56`
- name: `?DfsDeleteStandaloneRoot@@YAKPEBG0E@Z`
- size: `554`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140005590`

## callees

- `0x140005b28`
- `0x14000abc4`
- `0x140010b2c`
- `0x140012748`
- `0x140012808`
- `0x140014434`
- `0x1400144ac`
- `0x1400144f4`
- `0x140018ae0`
- `0x140022598`
- `0x1400591e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010c91`
- `CLUSAPI!CloseCluster` at `0x140010c64`
- `CLUSAPI!CloseCluster` at `0x140010c64`
- `CLUSAPI!OpenCluster` at `0x140010c33`
- `CLUSAPI!OpenCluster` at `0x140010c33`

## pseudocode

```c
__int64 __fastcall DfsDeleteStandaloneRoot(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int8 a3)
{
  const WCHAR *v6; // rdi
  char IsScopedServerName; // r15
  unsigned int IsCluster; // ebx
  struct _HCLUSTER *v9; // rax
  struct _HCLUSTER *v10; // rbp
  int v12; // r8d
  int v14; // [rsp+70h] [rbp+8h] BYREF
  struct DfsRegistryStore *v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = 0;
  LOBYTE(v14) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x40) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)pWppControl + 2), 24, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids, a2);
  }
  if ( !a1 || !*a1 || !a2 || !*a2 )
    return 87;
  v6 = DfsSkipLeadingPathSep(a1);
  IsScopedServerName = DfsIsScopedServerName(v6);
  if ( IsScopedServerName
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)pWppControl + 2), 25, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids, v6);
  }
  IsCluster = DfsNodeIsCluster(v6, (unsigned __int8 *)&v14);
  if ( !IsCluster )
  {
    if ( !(_BYTE)v14 )
    {
LABEL_24:
      IsCluster = DfsGetRegistryStore(&v15);
      if ( !IsCluster )
      {
        IsCluster = DfsRegistryStore::DeleteStandaloneRoot(
                      v15,
                      (unsigned __int64)v6 & -(__int64)(IsScopedServerName != 0),
                      a2,
                      IsScopedServerName,
                      a3);
        DfsGeneric::ReleaseReference(v15);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (((1 << (IsCluster != 0 ? 11 : 31)) | 0x40) & pWppControl[7]) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_DSS(*((_QWORD *)pWppControl + 2), 26, v12, IsCluster, (__int64)v6, (__int64)a2);
      }
      return IsCluster;
    }
    v9 = OpenCluster(v6);
    v10 = v9;
    if ( !v9 )
      return GetLastError();
    v14 = 0;
    IsCluster = DfsIsResourceExists(v9, v6, a2, &v14);
    CloseCluster(v10);
    if ( !IsCluster )
    {
      if ( v14 )
        return (unsigned int)DfsRemoveClusterResource(v6, a2);
      goto LABEL_24;
    }
  }
  return IsCluster;
}

```

## disassembly

```asm
0x140010b2c  mov     rax, rsp
0x140010b2f  mov     [rax+10h], rbx
0x140010b33  push    rbp
0x140010b34  push    rsi
0x140010b35  push    rdi
0x140010b36  push    r12
0x140010b38  push    r13
0x140010b3a  push    r14
0x140010b3c  push    r15
0x140010b3e  sub     rsp, 30h
0x140010b42  xor     r13d, r13d
0x140010b45  mov     r12b, r8b
0x140010b48  mov     [rax+20h], r13
0x140010b4c  mov     rsi, rdx
0x140010b4f  mov     [rax+8], r13b
0x140010b53  mov     rbx, rcx
0x140010b56  lea     rbp, WPP_GLOBAL_Control
0x140010b5d  cmp     cs:WPP_GLOBAL_Control, rbp
0x140010b64  lea     r14d, [r13+40h]
0x140010b68  jz      short loc_140010B99
0x140010b6a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140010b71  test    rcx, rcx
0x140010b74  jz      short loc_140010B99
0x140010b76  test    [rcx+1Ch], r14b
0x140010b7a  jz      short loc_140010B99
0x140010b7c  cmp     byte ptr [rcx+19h], 2
0x140010b80  jb      short loc_140010B99
0x140010b82  mov     rcx, [rcx+10h]
0x140010b86  lea     edx, [r13+18h]
0x140010b8a  mov     r9, rsi
0x140010b8d  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140010b94  call    WPP_SF_S
0x140010b99  test    rbx, rbx
0x140010b9c  jz      loc_140010D39
0x140010ba2  cmp     [rbx], r13w
0x140010ba6  jz      loc_140010D39
0x140010bac  test    rsi, rsi
0x140010baf  jz      loc_140010D39
0x140010bb5  cmp     [rsi], r13w
0x140010bb9  jz      loc_140010D39
0x140010bbf  mov     rcx, rbx; unsigned __int16 *
0x140010bc2  call    ?DfsSkipLeadingPathSep@@YAPEBGPEBG@Z; DfsSkipLeadingPathSep(ushort const *)
0x140010bc7  mov     rcx, rax; SourceString
0x140010bca  mov     rdi, rax
0x140010bcd  call    ?DfsIsScopedServerName@@YAEPEBG@Z; DfsIsScopedServerName(ushort const *)
0x140010bd2  mov     r15b, al
0x140010bd5  test    al, al
0x140010bd7  jz      short loc_140010C12
0x140010bd9  cmp     cs:WPP_GLOBAL_Control, rbp
0x140010be0  jz      short loc_140010C12
0x140010be2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140010be9  test    rcx, rcx
0x140010bec  jz      short loc_140010C12
0x140010bee  test    byte ptr [rcx+1Ch], 20h
0x140010bf2  jz      short loc_140010C12
0x140010bf4  cmp     byte ptr [rcx+19h], 3
0x140010bf8  jb      short loc_140010C12
0x140010bfa  mov     rcx, [rcx+10h]
0x140010bfe  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140010c05  mov     edx, 19h
0x140010c0a  mov     r9, rdi
0x140010c0d  call    WPP_SF_S
0x140010c12  lea     rdx, [rsp+68h+arg_0]; unsigned __int8 *
0x140010c17  mov     rcx, rdi; unsigned __int16 *
0x140010c1a  call    ?DfsNodeIsCluster@@YAKPEBGPEAE@Z; DfsNodeIsCluster(ushort const *,uchar *)
0x140010c1f  mov     ebx, eax
0x140010c21  test    eax, eax
0x140010c23  jnz     loc_140010D3E
0x140010c29  cmp     byte ptr [rsp+68h+arg_0], r13b
0x140010c2e  jz      short loc_140010CA6
0x140010c30  mov     rcx, rdi; lpszClusterName
0x140010c33  call    cs:__imp_OpenCluster
0x140010c3a  nop     dword ptr [rax+rax+00h]
0x140010c3f  mov     rbp, rax
0x140010c42  test    rax, rax
0x140010c45  jz      short loc_140010C91
0x140010c47  lea     r9, [rsp+68h+arg_0]; int *
0x140010c4c  mov     [rsp+68h+arg_0], r13d
0x140010c51  mov     r8, rsi; unsigned __int16 *
0x140010c54  mov     rdx, rdi; unsigned __int16 *
0x140010c57  mov     rcx, rax; struct _HCLUSTER *
0x140010c5a  call    ?DfsIsResourceExists@@YAKPEAU_HCLUSTER@@PEBG1PEAH@Z; DfsIsResourceExists(_HCLUSTER *,ushort const *,ushort const *,int *)
0x140010c5f  mov     rcx, rbp; hCluster
0x140010c62  mov     ebx, eax
0x140010c64  call    cs:__imp_CloseCluster
0x140010c6b  nop     dword ptr [rax+rax+00h]
0x140010c70  test    ebx, ebx
0x140010c72  jnz     loc_140010D3E
0x140010c78  cmp     [rsp+68h+arg_0], r13d
0x140010c7d  jz      short loc_140010C9F
0x140010c7f  mov     rdx, rsi; unsigned __int16 *
0x140010c82  mov     rcx, rdi; unsigned __int16 *
0x140010c85  call    ?DfsRemoveClusterResource@@YAKPEBG0@Z; DfsRemoveClusterResource(ushort const *,ushort const *)
0x140010c8a  mov     ebx, eax
0x140010c8c  jmp     loc_140010D3E
0x140010c91  call    cs:__imp_GetLastError
0x140010c98  nop     dword ptr [rax+rax+00h]
0x140010c9d  jmp     short loc_140010C8A
0x140010c9f  lea     rbp, WPP_GLOBAL_Control
0x140010ca6  lea     rcx, [rsp+68h+arg_18]; struct DfsRegistryStore **
0x140010cae  call    ?DfsGetRegistryStore@@YAKPEAPEAVDfsRegistryStore@@@Z; DfsGetRegistryStore(DfsRegistryStore * *)
0x140010cb3  mov     ebx, eax
0x140010cb5  test    eax, eax
0x140010cb7  jnz     short loc_140010CEB
0x140010cb9  mov     rcx, [rsp+68h+arg_18]; this
0x140010cc1  mov     al, r15b
0x140010cc4  neg     al
0x140010cc6  mov     [rsp+68h+var_48], r12b; unsigned __int8
0x140010ccb  mov     r9b, r15b; unsigned __int8
0x140010cce  mov     r8, rsi; unsigned __int16 *
0x140010cd1  sbb     rdx, rdx
0x140010cd4  and     rdx, rdi; unsigned __int16 *
0x140010cd7  call    ?DeleteStandaloneRoot@DfsRegistryStore@@QEAAKPEBG0EE@Z; DfsRegistryStore::DeleteStandaloneRoot(ushort const *,ushort const *,uchar,uchar)
0x140010cdc  mov     rcx, [rsp+68h+arg_18]; this
0x140010ce4  mov     ebx, eax
0x140010ce6  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x140010ceb  cmp     cs:WPP_GLOBAL_Control, rbp
0x140010cf2  jz      short loc_140010D3E
0x140010cf4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140010cfb  test    rcx, rcx
0x140010cfe  jz      short loc_140010D3E
0x140010d00  mov     eax, ebx
0x140010d02  neg     eax
0x140010d04  sbb     edx, edx
0x140010d06  and     edx, 0FFFFFFECh
0x140010d09  add     edx, 1Fh
0x140010d0c  bts     r14d, edx
0x140010d10  test    [rcx+1Ch], r14d
0x140010d14  jz      short loc_140010D3E
0x140010d16  cmp     byte ptr [rcx+19h], 2
0x140010d1a  jb      short loc_140010D3E
0x140010d1c  mov     rcx, [rcx+10h]
0x140010d20  mov     edx, 1Ah
0x140010d25  mov     [rsp+68h+var_40], rsi
0x140010d2a  mov     r9d, ebx
0x140010d2d  mov     qword ptr [rsp+68h+var_48], rdi
0x140010d32  call    WPP_SF_DSS
0x140010d37  jmp     short loc_140010D3E
0x140010d39  mov     ebx, 57h ; 'W'
0x140010d3e  mov     eax, ebx
0x140010d40  mov     rbx, [rsp+68h+arg_8]
0x140010d45  add     rsp, 30h
0x140010d49  pop     r15
0x140010d4b  pop     r14
0x140010d4d  pop     r13
0x140010d4f  pop     r12
0x140010d51  pop     rdi
0x140010d52  pop     rsi
0x140010d53  pop     rbp
0x140010d54  retn
```
