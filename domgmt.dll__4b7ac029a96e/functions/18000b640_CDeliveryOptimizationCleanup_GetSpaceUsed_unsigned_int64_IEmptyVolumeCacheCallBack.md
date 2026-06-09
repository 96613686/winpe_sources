# CDeliveryOptimizationCleanup::GetSpaceUsed(unsigned __int64 *,IEmptyVolumeCacheCallBack *)

- ea: `0x18000b640`
- end: `0x18000b6ba`
- name: `?GetSpaceUsed@CDeliveryOptimizationCleanup@@UEAAJPEA_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(CDeliveryOptimizationCleanup *__hidden this, unsigned __int64 *, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005964`
- `0x18000b640`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CDeliveryOptimizationCleanup::GetSpaceUsed(
        CDeliveryOptimizationCleanup *this,
        unsigned __int64 *a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a2 )
  {
    v5 = 33;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\cleanup.cpp",
      (const char *)0x80004003LL,
      v7);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v5 = 34;
    goto LABEL_3;
  }
  *a2 = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2));
  return ((__int64 (__fastcall *)(struct IEmptyVolumeCacheCallBack *, _QWORD, __int64))a3->lpVtbl->ScanProgress)(
           a3,
           *a2,
           1);
}

```

## disassembly

```asm
0x18000b640  mov     [rsp+arg_0], rbx
0x18000b645  push    rdi
0x18000b646  sub     rsp, 30h
0x18000b64a  mov     rdi, r8
0x18000b64d  mov     rbx, rdx
0x18000b650  test    rdx, rdx
0x18000b653  jnz     short loc_18000B675
0x18000b655  lea     edx, [rbx+21h]; void *
0x18000b658  mov     rcx, [rsp+38h]; this
0x18000b65d  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\deliveryoptimization"...
0x18000b664  mov     ebx, 80004003h
0x18000b669  mov     r9d, ebx; char *
0x18000b66c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b671  mov     eax, ebx
0x18000b673  jmp     short loc_18000B6AF
0x18000b675  test    rdi, rdi
0x18000b678  jnz     short loc_18000B67F
0x18000b67a  lea     edx, [rdi+22h]
0x18000b67d  jmp     short loc_18000B658
0x18000b67f  mov     qword ptr [rdx], 0
0x18000b686  mov     rcx, [rcx+10h]
0x18000b68a  mov     rax, [rcx]
0x18000b68d  mov     rax, [rax+20h]
0x18000b691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b696  mov     rax, [rdi]
0x18000b699  xor     r9d, r9d
0x18000b69c  mov     rdx, [rbx]
0x18000b69f  mov     rcx, rdi
0x18000b6a2  mov     rax, [rax+18h]
0x18000b6a6  lea     r8d, [r9+1]
0x18000b6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6af  mov     rbx, [rsp+38h+arg_0]
0x18000b6b4  add     rsp, 30h
0x18000b6b8  pop     rdi
0x18000b6b9  retn
```
