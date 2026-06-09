# CHandlerBase::GetContextIds(ushort * * *,ulong *,ulong const *)

- ea: `0x18000ec20`
- end: `0x18000ec90`
- name: `?GetContextIds@CHandlerBase@@UEAAJPEAPEAPEAGPEAKPEBK@Z`
- size: `112`
- prototype: `__int64 __fastcall(CHandlerBase *__hidden this, unsigned __int16 ***, unsigned int *, const unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000ec20`
- `0x180037aa8`

## string_xrefs

- `0x18000ec33`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000ec6f`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
__int64 __fastcall CHandlerBase::GetContextIds(
        CHandlerBase *this,
        unsigned __int16 ***a2,
        unsigned int *a3,
        const unsigned int *a4)
{
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    v4 = 93;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80004003LL,
      v6);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v4 = 94;
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x64,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
    (const char *)0x80004001LL,
    v6);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000ec20  sub     rsp, 28h
0x18000ec24  test    rdx, rdx
0x18000ec27  jnz     short loc_18000EC4C
0x18000ec29  mov     edx, 5Dh ; ']'; void *
0x18000ec2e  mov     rcx, [rsp+28h]; this
0x18000ec33  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ec3a  mov     r9d, 80004003h; char *
0x18000ec40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec45  mov     eax, 80004003h
0x18000ec4a  jmp     short loc_18000EC8B
0x18000ec4c  test    r8, r8
0x18000ec4f  jnz     short loc_18000EC57
0x18000ec51  lea     edx, [r8+5Eh]
0x18000ec55  jmp     short loc_18000EC2E
0x18000ec57  mov     qword ptr [rdx], 0
0x18000ec5e  mov     dword ptr [r8], 0
0x18000ec65  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ec6a  mov     rcx, [rsp+28h]; this
0x18000ec6f  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ec76  mov     r9d, 80004001h; char *
0x18000ec7c  mov     edx, 64h ; 'd'; void *
0x18000ec81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec86  mov     eax, 80004001h
0x18000ec8b  add     rsp, 28h
0x18000ec8f  retn
```
