# ATL::AtlAdvise(IUnknown *,IUnknown *,_GUID const &,ulong *)

- ea: `0x18000b4b0`
- end: `0x18000b56f`
- name: `?AtlAdvise@ATL@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z`
- size: `191`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IUnknown *, const struct _GUID *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce60`
- `0x18000d830`
- `0x1800165b4`

## callees

- `0x18000b4b0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::AtlAdvise(struct IUnknown *a1, struct IUnknown *a2, const struct _GUID *a3, unsigned int *a4)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int v9; // ebx
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 )
    return 2147942487LL;
  lpVtbl = a1->lpVtbl;
  v10[0] = 0;
  v11 = 0;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))lpVtbl->QueryInterface)(
         a1,
         &GUID_b196b284_bab4_101a_b69c_00aa00341d07,
         v10);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, __int64 *))(*(_QWORD *)v10[0] + 32LL))(
           v10[0],
           a3,
           &v11);
    if ( v9 >= 0 )
      v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, unsigned int *))(*(_QWORD *)v11 + 40LL))(v11, a2, a4);
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v10[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10[0] + 16LL))(v10[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b4b0  push    rbx
0x18000b4b2  push    rbp
0x18000b4b3  push    rsi
0x18000b4b4  push    rdi
0x18000b4b5  sub     rsp, 38h
0x18000b4b9  mov     rsi, r9
0x18000b4bc  mov     rdi, r8
0x18000b4bf  mov     rbp, rdx
0x18000b4c2  test    rcx, rcx
0x18000b4c5  jnz     short loc_18000B4D1
0x18000b4c7  mov     eax, 80070057h
0x18000b4cc  jmp     loc_18000B566
0x18000b4d1  mov     rax, [rcx]
0x18000b4d4  lea     r8, [rsp+58h+var_38]
0x18000b4d9  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x18000b4e0  mov     [rsp+58h+var_38], 0
0x18000b4e9  mov     [rsp+58h+arg_0], 0
0x18000b4f2  mov     rax, [rax]
0x18000b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4fa  mov     ebx, eax
0x18000b4fc  test    eax, eax
0x18000b4fe  js      short loc_18000B538
0x18000b500  mov     rcx, [rsp+58h+var_38]
0x18000b505  lea     r8, [rsp+58h+arg_0]
0x18000b50a  mov     rdx, rdi
0x18000b50d  mov     rax, [rcx]
0x18000b510  mov     rax, [rax+20h]
0x18000b514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b519  mov     ebx, eax
0x18000b51b  test    eax, eax
0x18000b51d  js      short loc_18000B538
0x18000b51f  mov     rcx, [rsp+58h+arg_0]
0x18000b524  mov     r8, rsi
0x18000b527  mov     rdx, rbp
0x18000b52a  mov     rax, [rcx]
0x18000b52d  mov     rax, [rax+28h]
0x18000b531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b536  mov     ebx, eax
0x18000b538  mov     rcx, [rsp+58h+arg_0]
0x18000b53d  test    rcx, rcx
0x18000b540  jz      short loc_18000B54E
0x18000b542  mov     rax, [rcx]
0x18000b545  mov     rax, [rax+10h]
0x18000b549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54e  mov     rcx, [rsp+58h+var_38]
0x18000b553  test    rcx, rcx
0x18000b556  jz      short loc_18000B564
0x18000b558  mov     rax, [rcx]
0x18000b55b  mov     rax, [rax+10h]
0x18000b55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b564  mov     eax, ebx
0x18000b566  add     rsp, 38h
0x18000b56a  pop     rdi
0x18000b56b  pop     rsi
0x18000b56c  pop     rbp
0x18000b56d  pop     rbx
0x18000b56e  retn
```
