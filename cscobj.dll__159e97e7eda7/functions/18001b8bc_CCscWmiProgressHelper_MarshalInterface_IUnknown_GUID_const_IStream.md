# CCscWmiProgressHelper::_MarshalInterface(IUnknown *,_GUID const &,IStream * *)

- ea: `0x18001b8bc`
- end: `0x18001ba4b`
- name: `?_MarshalInterface@CCscWmiProgressHelper@@AEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAUIStream@@@Z`
- size: `399`
- prototype: `int(CCscWmiProgressHelper *__hidden this, struct IUnknown *, const struct _GUID *, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ba54`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x18001b8bc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001b929`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001b929`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001b95b`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001b95b`

## pseudocode

```c
__int64 __fastcall CCscWmiProgressHelper::_MarshalInterface(
        CCscWmiProgressHelper *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IStream **a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  HRESULT v9; // eax
  LPSTREAM v10; // rcx
  __int64 v11; // rcx
  LPSTREAM ppstm; // [rsp+50h] [rbp+8h] BYREF
  __int64 v14; // [rsp+68h] [rbp+20h]

  ppstm = this;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  *a4 = 0;
  ppstm = 0;
  v7 = CreateStreamOnHGlobal(0, 1, &ppstm);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = CoMarshalInterface(ppstm, a3, a2, 3u, 0, 1u);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          13,
          WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
          (unsigned int)v9);
    }
    else
    {
      v14 = 0;
      (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
      v10 = ppstm;
      *a4 = ppstm;
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v10 + 8LL))(v10);
    }
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_14;
  }
  v11 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      14,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)v7);
LABEL_14:
    v11 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_DWORD *)(v11 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v11 + 16), 15, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001b8bc  mov     [rsp+arg_8], rbx
0x18001b8c1  mov     [rsp+arg_10], rbp
0x18001b8c6  mov     [rsp+ppstm], rcx
0x18001b8cb  push    rsi
0x18001b8cc  push    rdi
0x18001b8cd  push    r15
0x18001b8cf  sub     rsp, 30h
0x18001b8d3  mov     rdi, r9
0x18001b8d6  mov     rsi, r8
0x18001b8d9  mov     rbp, rdx
0x18001b8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8e3  lea     r15, WPP_GLOBAL_Control
0x18001b8ea  cmp     rcx, r15
0x18001b8ed  jz      short loc_18001B90D
0x18001b8ef  test    dword ptr [rcx+1Ch], 4000000h
0x18001b8f6  jz      short loc_18001B90D
0x18001b8f8  mov     rcx, [rcx+10h]
0x18001b8fc  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b903  mov     edx, 0Ch
0x18001b908  call    WPP_SF_
0x18001b90d  lea     r8, [rsp+48h+ppstm]; ppstm
0x18001b912  mov     qword ptr [rdi], 0
0x18001b919  mov     edx, 1; fDeleteOnRelease
0x18001b91e  mov     [rsp+48h+ppstm], 0
0x18001b927  xor     ecx, ecx; hGlobal
0x18001b929  call    cs:__imp_CreateStreamOnHGlobal
0x18001b92f  mov     ebx, eax
0x18001b931  test    eax, eax
0x18001b933  js      loc_18001B9DF
0x18001b939  mov     rcx, [rsp+48h+ppstm]; pStm
0x18001b93e  mov     r9d, 3; dwDestContext
0x18001b944  mov     [rsp+48h+mshlflags], 1; mshlflags
0x18001b94c  mov     r8, rbp; pUnk
0x18001b94f  mov     rdx, rsi; riid
0x18001b952  mov     [rsp+48h+pvDestContext], 0; pvDestContext
0x18001b95b  call    cs:__imp_CoMarshalInterface
0x18001b961  mov     ebx, eax
0x18001b963  test    eax, eax
0x18001b965  js      short loc_18001B9A2
0x18001b967  mov     rcx, [rsp+48h+ppstm]
0x18001b96c  xor     r9d, r9d
0x18001b96f  mov     [rsp+48h+arg_18], 0
0x18001b978  xor     r8d, r8d
0x18001b97b  mov     rdx, [rsp+48h+arg_18]
0x18001b980  mov     rax, [rcx]
0x18001b983  mov     rax, [rax+28h]
0x18001b987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b98c  mov     rcx, [rsp+48h+ppstm]
0x18001b991  mov     [rdi], rcx
0x18001b994  mov     rax, [rcx]
0x18001b997  mov     rax, [rax+8]
0x18001b99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9a0  jmp     short loc_18001B9CC
0x18001b9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9a9  cmp     rcx, r15
0x18001b9ac  jz      short loc_18001B9CC
0x18001b9ae  test    byte ptr [rcx+1Ch], 2
0x18001b9b2  jz      short loc_18001B9CC
0x18001b9b4  mov     rcx, [rcx+10h]
0x18001b9b8  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b9bf  mov     edx, 0Dh
0x18001b9c4  mov     r9d, eax
0x18001b9c7  call    WPP_SF_d
0x18001b9cc  mov     rcx, [rsp+48h+ppstm]
0x18001b9d1  mov     rax, [rcx]
0x18001b9d4  mov     rax, [rax+10h]
0x18001b9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9dd  jmp     short loc_18001BA09
0x18001b9df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9e6  cmp     rcx, r15
0x18001b9e9  jz      short loc_18001BA36
0x18001b9eb  test    byte ptr [rcx+1Ch], 2
0x18001b9ef  jz      short loc_18001BA10
0x18001b9f1  mov     rcx, [rcx+10h]
0x18001b9f5  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b9fc  mov     edx, 0Eh
0x18001ba01  mov     r9d, eax
0x18001ba04  call    WPP_SF_d
0x18001ba09  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba10  cmp     rcx, r15
0x18001ba13  jz      short loc_18001BA36
0x18001ba15  test    dword ptr [rcx+1Ch], 4000000h
0x18001ba1c  jz      short loc_18001BA36
0x18001ba1e  mov     rcx, [rcx+10h]
0x18001ba22  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001ba29  mov     edx, 0Fh
0x18001ba2e  mov     r9d, ebx
0x18001ba31  call    WPP_SF_d
0x18001ba36  mov     rbp, [rsp+48h+arg_10]
0x18001ba3b  mov     eax, ebx
0x18001ba3d  mov     rbx, [rsp+48h+arg_8]
0x18001ba42  add     rsp, 30h
0x18001ba46  pop     r15
0x18001ba48  pop     rdi
0x18001ba49  pop     rsi
0x18001ba4a  retn
```
