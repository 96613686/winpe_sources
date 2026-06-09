# CHandlerBase::GetContextPath(ushort * *,ulong const *)

- ea: `0x18000eca0`
- end: `0x18000ece9`
- name: `?GetContextPath@CHandlerBase@@UEAAJPEAPEAGPEBK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CHandlerBase *this, unsigned __int16 **, const unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000eca0`
- `0x180037aa8`

## string_xrefs

- `0x18000ecd2`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHandlerBase::GetContextPath(
        CHandlerBase *this,
        unsigned __int16 **a2,
        const unsigned int *a3,
        __int64 a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
    v5 = 87;
    v4 = -2147467263;
  }
  else
  {
    v4 = -2147467261;
    v5 = 82;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
    (const char *)v4,
    v7);
  return v4;
}

```

## disassembly

```asm
0x18000eca0  push    rbx; int
0x18000eca2  sub     rsp, 20h
0x18000eca6  test    rdx, rdx
0x18000eca9  jnz     short loc_18000ECB7
0x18000ecab  mov     ebx, 80004003h
0x18000ecb0  mov     edx, 52h ; 'R'
0x18000ecb5  jmp     short loc_18000ECCD
0x18000ecb7  mov     qword ptr [rdx], 0
0x18000ecbe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ecc3  mov     edx, 57h ; 'W'; void *
0x18000ecc8  mov     ebx, 80004001h
0x18000eccd  mov     rcx, [rsp+28h]; this
0x18000ecd2  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ecd9  mov     r9d, ebx; char *
0x18000ecdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ece1  mov     eax, ebx
0x18000ece3  add     rsp, 20h
0x18000ece7  pop     rbx
0x18000ece8  retn
```
