# CHandlerBase::DoesOwnAnyKeys(_MVProvisionData *,int *)

- ea: `0x18000eb00`
- end: `0x18000eb7f`
- name: `?DoesOwnAnyKeys@CHandlerBase@@UEAAJPEAU_MVProvisionData@@PEAH@Z`
- size: `127`
- prototype: `__int64 __fastcall(CHandlerBase *this, struct _MVProvisionData *, int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000eb00`
- `0x180037aa8`

## string_xrefs

- `0x18000eb0e`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000eb36`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000eb5e`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
__int64 __fastcall CHandlerBase::DoesOwnAnyKeys(CHandlerBase *this, struct _MVProvisionData *a2, int *a3, __int64 a4)
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
        (void *)0x9D,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
        (const char *)0x80004001LL,
        v5);
      return 2147500033LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x99,
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
      (void *)0x98,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80070057LL,
      v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000eb00  sub     rsp, 28h
0x18000eb04  test    rdx, rdx
0x18000eb07  jnz     short loc_18000EB2C
0x18000eb09  mov     rcx, [rsp+28h]; this
0x18000eb0e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000eb15  mov     r9d, 80070057h; char *
0x18000eb1b  mov     edx, 98h; void *
0x18000eb20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb25  mov     eax, 80070057h
0x18000eb2a  jmp     short loc_18000EB7A
0x18000eb2c  test    r8, r8
0x18000eb2f  jnz     short loc_18000EB54
0x18000eb31  mov     rcx, [rsp+28h]; this
0x18000eb36  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000eb3d  mov     r9d, 80004003h; char *
0x18000eb43  mov     edx, 99h; void *
0x18000eb48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb4d  mov     eax, 80004003h
0x18000eb52  jmp     short loc_18000EB7A
0x18000eb54  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000eb59  mov     rcx, [rsp+28h]; this
0x18000eb5e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000eb65  mov     r9d, 80004001h; char *
0x18000eb6b  mov     edx, 9Dh; void *
0x18000eb70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb75  mov     eax, 80004001h
0x18000eb7a  add     rsp, 28h
0x18000eb7e  retn
```
