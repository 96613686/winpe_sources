# CHandlerBase::DoesOwnKey(IMVKey *,int *)

- ea: `0x18000eb90`
- end: `0x18000ec0f`
- name: `?DoesOwnKey@CHandlerBase@@UEAAJPEAUIMVKey@@PEAH@Z`
- size: `127`
- prototype: `__int64 __fastcall(CHandlerBase *this, struct IMVKey *, int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000eb90`
- `0x180037aa8`

## string_xrefs

- `0x18000eb9e`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000ebc6`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000ebee`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
__int64 __fastcall CHandlerBase::DoesOwnKey(CHandlerBase *this, struct IMVKey *a2, int *a3, __int64 a4)
{
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    if ( a3 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
        (const char *)0x80004001LL,
        v5);
      return 2147500033LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
        (const char *)0x80004003LL,
        v5);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80070057LL,
      v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000eb90  sub     rsp, 28h
0x18000eb94  test    rdx, rdx
0x18000eb97  jnz     short loc_18000EBBC
0x18000eb99  mov     rcx, [rsp+28h]; this
0x18000eb9e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000eba5  mov     r9d, 80070057h; char *
0x18000ebab  mov     edx, 0A5h; void *
0x18000ebb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebb5  mov     eax, 80070057h
0x18000ebba  jmp     short loc_18000EC0A
0x18000ebbc  test    r8, r8
0x18000ebbf  jnz     short loc_18000EBE4
0x18000ebc1  mov     rcx, [rsp+28h]; this
0x18000ebc6  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ebcd  mov     r9d, 80004003h; char *
0x18000ebd3  mov     edx, 0A6h; void *
0x18000ebd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebdd  mov     eax, 80004003h
0x18000ebe2  jmp     short loc_18000EC0A
0x18000ebe4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ebe9  mov     rcx, [rsp+28h]; this
0x18000ebee  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ebf5  mov     r9d, 80004001h; char *
0x18000ebfb  mov     edx, 0AAh; void *
0x18000ec00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec05  mov     eax, 80004001h
0x18000ec0a  add     rsp, 28h
0x18000ec0e  retn
```
