# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x18000888c`
- end: `0x180008936`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c5c`

## callees

- `0x180005904`
- `0x18000888c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088a1`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180008923`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180008923`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800088d7`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800088d7`

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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      AgileReference = RoGetAgileReference(0, a2, a3, &v13);
      v9 = v13;
    }
    v12[0] = *(_QWORD *)(a1 + 32);
    v13 = 0;
    *(_QWORD *)(a1 + 32) = v9;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 16);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x18000888c  push    rbx
0x18000888e  push    rbp
0x18000888f  push    rsi
0x180008890  push    rdi
0x180008891  sub     rsp, 38h
0x180008895  mov     ebx, r9d
0x180008898  mov     rsi, r8
0x18000889b  mov     rbp, rdx
0x18000889e  mov     rdi, rcx
0x1800088a1  call    cs:__imp_GetCurrentThreadId
0x1800088a7  mov     [rdi+18h], ebx
0x1800088aa  mov     [rdi+28h], eax
0x1800088ad  cmp     ebx, 2
0x1800088b0  jnz     short loc_180008910
0x1800088b2  xor     eax, eax
0x1800088b4  xor     ebx, ebx
0x1800088b6  mov     [rsp+58h+arg_0], rax
0x1800088bb  test    rsi, rsi
0x1800088be  jz      short loc_1800088E4
0x1800088c0  lea     rcx, [rsp+58h+arg_0]
0x1800088c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800088ca  lea     r9, [rsp+58h+arg_0]
0x1800088cf  mov     r8, rsi
0x1800088d2  mov     rdx, rbp
0x1800088d5  xor     ecx, ecx
0x1800088d7  call    cs:__imp_RoGetAgileReference
0x1800088dd  mov     ebx, eax
0x1800088df  mov     rax, [rsp+58h+arg_0]
0x1800088e4  mov     rcx, [rdi+20h]
0x1800088e8  mov     [rsp+58h+var_38], rcx
0x1800088ed  lea     rcx, [rsp+58h+var_38]
0x1800088f2  mov     [rsp+58h+arg_0], 0
0x1800088fb  mov     [rdi+20h], rax
0x1800088ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008904  lea     rcx, [rsp+58h+arg_0]
0x180008909  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000890e  jmp     short loc_18000892B
0x180008910  lea     rcx, [rdi+10h]
0x180008914  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008919  lea     r8, [rdi+10h]; ppStm
0x18000891d  mov     rdx, rsi; pUnk
0x180008920  mov     rcx, rbp; riid
0x180008923  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180008929  mov     ebx, eax
0x18000892b  mov     eax, ebx
0x18000892d  add     rsp, 38h
0x180008931  pop     rdi
0x180008932  pop     rsi
0x180008933  pop     rbp
0x180008934  pop     rbx
0x180008935  retn
```
