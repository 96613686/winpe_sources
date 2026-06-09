# FwIcfAuthorizedAppsCopy

- ea: `0x18002a900`
- end: `0x18002a992`
- name: `FwIcfAuthorizedAppsCopy`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800047e0`
- `0x180014840`
- `0x18002a900`

## string_xrefs

- `0x18002a949`: `FwIcfAuthorizedAppsCopy`
- `0x18002a957`: `FwIcfAuthorizedAppsCopy`

## pseudocode

```c
__int64 __fastcall FwIcfAuthorizedAppsCopy(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int128 v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  v4 = FwArrayCopy(
         0x70u,
         (__int64 (__fastcall *)(unsigned __int64, unsigned __int64))FwIcfAuthorizedAppCopy,
         (void (__fastcall *)(char *))FwIcfAuthorizedAppDestroy,
         (unsigned int *)a1,
         &v8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *((_QWORD *)&v8 + 1);
    *(_OWORD *)a2 = *(_OWORD *)a1;
    *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a2 + 8) = v6;
  }
  else
  {
    FwReportReturnError("FwIcfAuthorizedAppsCopy", (unsigned int)v4);
    return (unsigned int)FwReportReturnError("FwIcfAuthorizedAppsCopy", v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002a900  mov     rax, rsp
0x18002a903  mov     [rax+8], rbx
0x18002a907  mov     [rax+10h], rsi
0x18002a90b  push    rdi
0x18002a90c  sub     rsp, 40h
0x18002a910  xorps   xmm0, xmm0
0x18002a913  mov     rdi, rdx
0x18002a916  mov     rsi, rcx
0x18002a919  mov     r9, rcx
0x18002a91c  mov     ecx, 70h ; 'p'
0x18002a921  lea     r8, FwIcfAuthorizedAppDestroy
0x18002a928  movups  xmmword ptr [rax-18h], xmm0
0x18002a92c  lea     rax, [rax-18h]
0x18002a930  lea     rdx, FwIcfAuthorizedAppCopy
0x18002a937  mov     [rsp+48h+var_28], rax
0x18002a93c  call    FwArrayCopy
0x18002a941  mov     ebx, eax
0x18002a943  test    eax, eax
0x18002a945  jns     short loc_18002A967
0x18002a947  mov     edx, eax
0x18002a949  lea     rcx, aFwicfauthorize_2; "FwIcfAuthorizedAppsCopy"
0x18002a950  call    FwReportReturnError
0x18002a955  mov     edx, ebx
0x18002a957  lea     rcx, aFwicfauthorize_2; "FwIcfAuthorizedAppsCopy"
0x18002a95e  call    FwReportReturnError
0x18002a963  mov     ebx, eax
0x18002a965  jmp     short loc_18002A980
0x18002a967  movups  xmm0, xmmword ptr [rsi]
0x18002a96a  mov     rax, [rsp+48h+var_10]
0x18002a96f  movups  xmmword ptr [rdi], xmm0
0x18002a972  movsd   xmm1, qword ptr [rsi+10h]
0x18002a977  movsd   qword ptr [rdi+10h], xmm1
0x18002a97c  mov     [rdi+8], rax
0x18002a980  mov     rsi, [rsp+48h+arg_8]
0x18002a985  mov     eax, ebx
0x18002a987  mov     rbx, [rsp+48h+arg_0]
0x18002a98c  add     rsp, 40h
0x18002a990  pop     rdi
0x18002a991  retn
```
