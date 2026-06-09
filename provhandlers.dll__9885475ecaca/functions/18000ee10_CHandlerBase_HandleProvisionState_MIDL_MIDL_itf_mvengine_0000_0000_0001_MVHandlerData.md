# CHandlerBase::HandleProvisionState(__MIDL___MIDL_itf_mvengine_0000_0000_0001,_MVHandlerData *)

- ea: `0x18000ee10`
- end: `0x18000ee7c`
- name: `?HandleProvisionState@CHandlerBase@@UEAAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@PEAU_MVHandlerData@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, int, _OWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800143f0`
- `0x180018490`
- `0x180030600`

## callees

- `0x1800076a4`
- `0x18000ee10`

## string_xrefs

- `0x18000ee1e`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000ee4d`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
__int64 __fastcall CHandlerBase::HandleProvisionState(__int64 a1, int a2, _OWORD *a3)
{
  __int64 result; // rax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    if ( a2 <= 18 )
    {
      *(_DWORD *)(a1 + 24) = a2;
      result = 0;
      *(_DWORD *)(a1 + 28) = -1;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
        (const char *)0x80070057LL,
        v4);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80004003LL,
      v4);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ee10  sub     rsp, 28h
0x18000ee14  test    r8, r8
0x18000ee17  jnz     short loc_18000EE3C
0x18000ee19  mov     rcx, [rsp+28h]; this
0x18000ee1e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ee25  mov     r9d, 80004003h; char *
0x18000ee2b  mov     edx, 2Dh ; '-'; void *
0x18000ee30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee35  mov     eax, 80004003h
0x18000ee3a  jmp     short loc_18000EE77
0x18000ee3c  xorps   xmm0, xmm0
0x18000ee3f  movups  xmmword ptr [r8], xmm0
0x18000ee43  cmp     edx, 12h
0x18000ee46  jle     short loc_18000EE6B
0x18000ee48  mov     rcx, [rsp+28h]; this
0x18000ee4d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ee54  mov     r9d, 80070057h; char *
0x18000ee5a  mov     edx, 30h ; '0'; void *
0x18000ee5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee64  mov     eax, 80070057h
0x18000ee69  jmp     short loc_18000EE77
0x18000ee6b  mov     [rcx+18h], edx
0x18000ee6e  xor     eax, eax
0x18000ee70  mov     dword ptr [rcx+1Ch], 0FFFFFFFFh
0x18000ee77  add     rsp, 28h
0x18000ee7b  retn
```
