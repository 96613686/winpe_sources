# DllGetCommitSig(ILockBytes *,ulong *)

- ea: `0x180036734`
- end: `0x1800367e2`
- name: `?DllGetCommitSig@@YAJPEAUILockBytes@@PEAK@Z`
- size: `174`
- prototype: `__int64 __fastcall(struct ILockBytes *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000745c`
- `0x18001cd84`
- `0x1800362a4`

## callees

- `0x18000cdd8`
- `0x180036734`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003674e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003674e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367cc`

## pseudocode

```c
__int64 __fastcall DllGetCommitSig(struct ILockBytes *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  CMSFHeader *v5; // rsi
  int v6; // ebx
  struct ILockBytesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *ReadAt)(ILockBytes *, ULARGE_INTEGER, void *, ULONG, ULONG *); // rax
  int v10; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h]

  v4 = 516;
  while ( 1 )
  {
    v5 = (CMSFHeader *)CoTaskMemAlloc(v4);
    if ( v5 )
      break;
    v4 >>= 1;
    if ( v4 < 0x204 )
    {
      v6 = -2147287032;
      goto LABEL_10;
    }
  }
  lpVtbl = a1->lpVtbl;
  v11 = 0;
  ReadAt = lpVtbl->ReadAt;
  v10 = 0;
  v6 = ((__int64 (__fastcall *)(struct ILockBytes *, _QWORD, CMSFHeader *, _QWORD, int *))ReadAt)(a1, 0, v5, v4, &v10);
  if ( v6 >= 0 )
  {
    if ( v10 == v4 )
    {
      v6 = CMSFHeader::Validate(v5);
      if ( v6 >= 0 )
        *a2 = *((_DWORD *)v5 + 13);
    }
    else
    {
      v6 = -2147286787;
    }
  }
LABEL_10:
  CoTaskMemFree(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180036734  mov     [rsp+arg_0], rbx
0x180036739  push    rsi
0x18003673a  push    rdi
0x18003673b  push    r14
0x18003673d  sub     rsp, 30h
0x180036741  mov     r14, rdx
0x180036744  mov     rbx, rcx
0x180036747  mov     edi, 204h
0x18003674c  mov     ecx, edi; cb
0x18003674e  call    cs:__imp_CoTaskMemAlloc
0x180036754  mov     rsi, rax
0x180036757  test    rax, rax
0x18003675a  jnz     short loc_18003676D
0x18003675c  shr     edi, 1
0x18003675e  cmp     edi, 204h
0x180036764  jnb     short loc_18003674C
0x180036766  mov     ebx, 80030008h
0x18003676b  jmp     short loc_1800367C9
0x18003676d  mov     rax, [rbx]
0x180036770  lea     rcx, [rsp+48h+arg_10]
0x180036775  mov     [rsp+48h+var_28], rcx
0x18003677a  mov     r9d, edi
0x18003677d  mov     [rsp+48h+arg_18], 0
0x180036786  mov     r8, rsi
0x180036789  mov     rdx, [rsp+48h+arg_18]
0x18003678e  mov     rcx, rbx
0x180036791  mov     rax, [rax+18h]
0x180036795  mov     [rsp+48h+arg_10], 0
0x18003679d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367a2  mov     ebx, eax
0x1800367a4  test    eax, eax
0x1800367a6  js      short loc_1800367C9
0x1800367a8  cmp     [rsp+48h+arg_10], edi
0x1800367ac  jz      short loc_1800367B5
0x1800367ae  mov     ebx, 800300FDh
0x1800367b3  jmp     short loc_1800367C9
0x1800367b5  mov     rcx, rsi; this
0x1800367b8  call    ?Validate@CMSFHeader@@QEBAJXZ; CMSFHeader::Validate(void)
0x1800367bd  mov     ebx, eax
0x1800367bf  test    eax, eax
0x1800367c1  js      short loc_1800367C9
0x1800367c3  mov     eax, [rsi+34h]
0x1800367c6  mov     [r14], eax
0x1800367c9  mov     rcx, rsi; pv
0x1800367cc  call    cs:__imp_CoTaskMemFree
0x1800367d2  mov     eax, ebx
0x1800367d4  mov     rbx, [rsp+48h+arg_0]
0x1800367d9  add     rsp, 30h
0x1800367dd  pop     r14
0x1800367df  pop     rdi
0x1800367e0  pop     rsi
0x1800367e1  retn
```
