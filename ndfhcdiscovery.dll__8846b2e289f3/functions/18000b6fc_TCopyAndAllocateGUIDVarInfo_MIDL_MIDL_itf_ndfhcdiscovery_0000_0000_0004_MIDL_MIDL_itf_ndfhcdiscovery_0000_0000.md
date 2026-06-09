# TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)

- ea: `0x18000b6fc`
- end: `0x18000b79a`
- name: `??$TCopyAndAllocateGUIDVarInfo@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@@@YAJPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEBUGUIDVarInfo@@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bb4c`

## callees

- `0x18000b6fc`
- `0x18001065c`
- `0x180010684`
- `0x180010a6c`
- `0x180011fcc`

## pseudocode

```c
int __fastcall TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(
        unsigned __int16 **a1,
        __int64 a2)
{
  const unsigned __int16 *v2; // r8
  int result; // eax
  unsigned __int16 *v6; // rbx
  unsigned __int64 v7; // rcx
  int v8; // eax
  void *v9; // rdx
  const unsigned __int16 *v10; // r8
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v13; // [rsp+40h] [rbp+8h] BYREF

  v2 = (const unsigned __int16 *)(a2 + 48);
  *(_OWORD *)a1 = *(_OWORD *)a2;
  if ( *(_QWORD *)(a2 + 72) >= 8u )
    v2 = *(const unsigned __int16 **)v2;
  result = ResourceStringLoader::LoadStringWithAlloc((ResourceStringLoader *)a1, a1 + 3, v2);
  if ( result >= 0 )
  {
    v6 = (unsigned __int16 *)(a2 + 16);
    if ( *(_QWORD *)(a2 + 40) >= 8u )
      v6 = *(unsigned __int16 **)v6;
    v7 = *(_QWORD *)(a2 + 32);
    v13 = 0;
    if ( v7 < 0xFFFFFFFF )
      ++v7;
    v8 = ULongLongToULong(v7, &v13);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v9, (unsigned int)v10, (const char *)(unsigned int)v8, v11);
    return UtilAssembleStringsWithAlloc(a1 + 2, v13, v10, v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000b6fc  mov     [rsp+arg_8], rbx
0x18000b701  mov     [rsp+arg_10], rsi
0x18000b706  push    rdi
0x18000b707  sub     rsp, 30h
0x18000b70b  movups  xmm0, xmmword ptr [rdx]
0x18000b70e  lea     r8, [rdx+30h]
0x18000b712  mov     rdi, rdx
0x18000b715  mov     rsi, rcx
0x18000b718  movdqu  xmmword ptr [rcx], xmm0
0x18000b71c  cmp     qword ptr [r8+18h], 8
0x18000b721  jb      short loc_18000B726
0x18000b723  mov     r8, [r8]; unsigned __int16 *
0x18000b726  lea     rdx, [rcx+18h]; unsigned __int16 **
0x18000b72a  call    ?LoadStringWithAlloc@ResourceStringLoader@@QEAAJPEAPEAGPEBG@Z; ResourceStringLoader::LoadStringWithAlloc(ushort * *,ushort const *)
0x18000b72f  test    eax, eax
0x18000b731  js      short loc_18000B77B
0x18000b733  lea     rbx, [rdi+10h]
0x18000b737  cmp     qword ptr [rbx+18h], 8
0x18000b73c  jb      short loc_18000B741
0x18000b73e  mov     rbx, [rbx]
0x18000b741  mov     rcx, [rdi+20h]
0x18000b745  mov     edx, 0FFFFFFFFh
0x18000b74a  cmp     rcx, rdx
0x18000b74d  mov     [rsp+38h+arg_0], 0
0x18000b755  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x18000b75a  lea     rax, [rcx+1]
0x18000b75e  cmovb   rcx, rax; unsigned __int64
0x18000b762  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000b767  test    eax, eax
0x18000b769  js      short loc_18000B78C
0x18000b76b  mov     edx, [rsp+38h+arg_0]; unsigned int
0x18000b76f  lea     rcx, [rsi+10h]; unsigned __int16 **
0x18000b773  mov     r9, rbx; unsigned __int16 *
0x18000b776  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000b77b  mov     rbx, [rsp+38h+arg_8]
0x18000b780  mov     rsi, [rsp+38h+arg_10]
0x18000b785  add     rsp, 30h
0x18000b789  pop     rdi
0x18000b78a  retn
0x18000b78c  mov     rcx, [rsp+38h]; this
0x18000b791  mov     r9d, eax; char *
0x18000b794  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
