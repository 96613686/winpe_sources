# CDeliveryOptimizationCleanup::Purge(unsigned __int64,IEmptyVolumeCacheCallBack *)

- ea: `0x18000b830`
- end: `0x18000b8ab`
- name: `?Purge@CDeliveryOptimizationCleanup@@UEAAJ_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `123`
- prototype: `__int64 __fastcall(CDeliveryOptimizationCleanup *this, __int64, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005964`
- `0x18000b830`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CDeliveryOptimizationCleanup::Purge(
        CDeliveryOptimizationCleanup *this,
        __int64 a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a3 )
  {
    if ( a2 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 40LL))(*((_QWORD *)this + 2));
    return ((__int64 (__fastcall *)(struct IEmptyVolumeCacheCallBack *, __int64, _QWORD, __int64, _QWORD))a3->lpVtbl->PurgeProgress)(
             a3,
             a2,
             0,
             1,
             0);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\cleanup.cpp",
      (const char *)0x80004003LL,
      v6);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000b830  mov     [rsp+arg_0], rbx
0x18000b835  push    rdi
0x18000b836  sub     rsp, 30h
0x18000b83a  mov     rbx, r8
0x18000b83d  mov     rdi, rdx
0x18000b840  test    r8, r8
0x18000b843  jnz     short loc_18000B867
0x18000b845  mov     rcx, [rsp+38h]; this
0x18000b84a  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\deliveryoptimization"...
0x18000b851  mov     ebx, 80004003h
0x18000b856  mov     edx, 2Bh ; '+'; void *
0x18000b85b  mov     r9d, ebx; char *
0x18000b85e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b863  mov     eax, ebx
0x18000b865  jmp     short loc_18000B8A0
0x18000b867  test    rdi, rdi
0x18000b86a  jz      short loc_18000B87C
0x18000b86c  mov     rcx, [rcx+10h]
0x18000b870  mov     rax, [rcx]
0x18000b873  mov     rax, [rax+28h]
0x18000b877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b87c  mov     rax, [rbx]
0x18000b87f  mov     r9d, 1
0x18000b885  xor     r8d, r8d
0x18000b888  mov     qword ptr [rsp+38h+var_18], 0
0x18000b891  mov     rdx, rdi
0x18000b894  mov     rcx, rbx
0x18000b897  mov     rax, [rax+20h]
0x18000b89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a0  mov     rbx, [rsp+38h+arg_0]
0x18000b8a5  add     rsp, 30h
0x18000b8a9  pop     rdi
0x18000b8aa  retn
```
