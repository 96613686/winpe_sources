# FwIcfSubNetsCopy

- ea: `0x18002abe0`
- end: `0x18002ac6a`
- name: `FwIcfSubNetsCopy`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a770`

## callees

- `0x1800047e0`
- `0x180014840`
- `0x18002abe0`

## string_xrefs

- `0x18002ac2a`: `FwIcfSubNetsCopy`
- `0x18002ac38`: `FwIcfSubNetsCopy`

## pseudocode

```c
__int64 __fastcall FwIcfSubNetsCopy(__int64 a1, _OWORD *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  v4 = FwArrayCopy(
         8u,
         (__int64 (__fastcall *)(unsigned __int64, unsigned __int64))FwIcfIpV4SubNetCopy,
         (void (__fastcall *)(char *))wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         (unsigned int *)(a1 + 8),
         &v7);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *a2 = *(_OWORD *)a1;
    *(_OWORD *)((char *)a2 + 8) = v7;
  }
  else
  {
    FwReportReturnError("FwIcfSubNetsCopy", (unsigned int)v4);
    return (unsigned int)FwReportReturnError("FwIcfSubNetsCopy", v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002abe0  mov     rax, rsp
0x18002abe3  mov     [rax+8], rbx
0x18002abe7  mov     [rax+10h], rsi
0x18002abeb  push    rdi
0x18002abec  sub     rsp, 40h
0x18002abf0  xorps   xmm0, xmm0
0x18002abf3  mov     rdi, rdx
0x18002abf6  mov     rsi, rcx
0x18002abf9  lea     r9, [rcx+8]
0x18002abfd  mov     ecx, 8
0x18002ac02  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18002ac09  movups  xmmword ptr [rax-18h], xmm0
0x18002ac0d  lea     rax, [rax-18h]
0x18002ac11  lea     rdx, FwIcfIpV4SubNetCopy
0x18002ac18  mov     [rsp+48h+var_28], rax
0x18002ac1d  call    FwArrayCopy
0x18002ac22  mov     ebx, eax
0x18002ac24  test    eax, eax
0x18002ac26  jns     short loc_18002AC48
0x18002ac28  mov     edx, eax
0x18002ac2a  lea     rcx, aFwicfsubnetsco_0; "FwIcfSubNetsCopy"
0x18002ac31  call    FwReportReturnError
0x18002ac36  mov     edx, ebx
0x18002ac38  lea     rcx, aFwicfsubnetsco_0; "FwIcfSubNetsCopy"
0x18002ac3f  call    FwReportReturnError
0x18002ac44  mov     ebx, eax
0x18002ac46  jmp     short loc_18002AC58
0x18002ac48  movups  xmm0, xmmword ptr [rsi]
0x18002ac4b  movups  xmmword ptr [rdi], xmm0
0x18002ac4e  movups  xmm0, [rsp+48h+var_18]
0x18002ac53  movdqu  xmmword ptr [rdi+8], xmm0
0x18002ac58  mov     rsi, [rsp+48h+arg_8]
0x18002ac5d  mov     eax, ebx
0x18002ac5f  mov     rbx, [rsp+48h+arg_0]
0x18002ac64  add     rsp, 40h
0x18002ac68  pop     rdi
0x18002ac69  retn
```
