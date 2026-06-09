# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x18004cccc`
- end: `0x18004cd76`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800364b8`

## callees

- `0x180008900`
- `0x18004cccc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004cce1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004cce1`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18004cd63`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18004cd63`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18004cd17`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18004cd17`

## pseudocode

```c
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        __int64 a1,
        const IID *a2,
        IUnknown *a3,
        int a4)
{
  DWORD CurrentThreadId; // eax
  __int64 v9; // rax
  unsigned int AgileReference; // ebx
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 24) = a4;
  *(_DWORD *)(a1 + 40) = CurrentThreadId;
  if ( a4 == 2 )
  {
    v9 = 0;
    AgileReference = 0;
    v13 = 0;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v13);
      AgileReference = RoGetAgileReference(0, a2, a3, &v13);
      v9 = v13;
    }
    v12[0] = *(_QWORD *)(a1 + 32);
    v13 = 0;
    *(_QWORD *)(a1 + 32) = v9;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v12);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v13);
  }
  else
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(a1 + 16);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x18004cccc  push    rbx
0x18004ccce  push    rbp
0x18004cccf  push    rsi
0x18004ccd0  push    rdi
0x18004ccd1  sub     rsp, 38h
0x18004ccd5  mov     ebx, r9d
0x18004ccd8  mov     rsi, r8
0x18004ccdb  mov     rbp, rdx
0x18004ccde  mov     rdi, rcx
0x18004cce1  call    cs:__imp_GetCurrentThreadId
0x18004cce7  mov     [rdi+18h], ebx
0x18004ccea  mov     [rdi+28h], eax
0x18004cced  cmp     ebx, 2
0x18004ccf0  jnz     short loc_18004CD50
0x18004ccf2  xor     eax, eax
0x18004ccf4  xor     ebx, ebx
0x18004ccf6  mov     [rsp+58h+arg_0], rax
0x18004ccfb  test    rsi, rsi
0x18004ccfe  jz      short loc_18004CD24
0x18004cd00  lea     rcx, [rsp+58h+arg_0]
0x18004cd05  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004cd0a  lea     r9, [rsp+58h+arg_0]
0x18004cd0f  mov     r8, rsi
0x18004cd12  mov     rdx, rbp
0x18004cd15  xor     ecx, ecx
0x18004cd17  call    cs:__imp_RoGetAgileReference
0x18004cd1d  mov     ebx, eax
0x18004cd1f  mov     rax, [rsp+58h+arg_0]
0x18004cd24  mov     rcx, [rdi+20h]
0x18004cd28  mov     [rsp+58h+var_38], rcx
0x18004cd2d  lea     rcx, [rsp+58h+var_38]
0x18004cd32  mov     [rsp+58h+arg_0], 0
0x18004cd3b  mov     [rdi+20h], rax
0x18004cd3f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004cd44  lea     rcx, [rsp+58h+arg_0]
0x18004cd49  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004cd4e  jmp     short loc_18004CD6B
0x18004cd50  lea     rcx, [rdi+10h]
0x18004cd54  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004cd59  lea     r8, [rdi+10h]; ppStm
0x18004cd5d  mov     rdx, rsi; pUnk
0x18004cd60  mov     rcx, rbp; riid
0x18004cd63  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18004cd69  mov     ebx, eax
0x18004cd6b  mov     eax, ebx
0x18004cd6d  add     rsp, 38h
0x18004cd71  pop     rdi
0x18004cd72  pop     rsi
0x18004cd73  pop     rbp
0x18004cd74  pop     rbx
0x18004cd75  retn
```
