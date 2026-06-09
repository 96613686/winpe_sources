# CHandlerBase::GetValue(ushort const *,ulong *,uchar *,ulong const *)

- ea: `0x18000ed40`
- end: `0x18000edbc`
- name: `?GetValue@CHandlerBase@@UEAAJPEBGPEAKPEAEPEBK@Z`
- size: `124`
- prototype: `__int64 __fastcall(CHandlerBase *this, const unsigned __int16 *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000ed40`
- `0x180037aa8`
- `0x18003b96a`

## string_xrefs

- `0x18000ed53`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000ed9b`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
__int64 __fastcall CHandlerBase::GetValue(
        CHandlerBase *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 v4; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    v4 = 136;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80004003LL,
      v10);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v4 = 137;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v4 = 138;
    goto LABEL_3;
  }
  memset_0(a4, 0, *a3);
  MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6, v8, v9);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
    (const char *)0x80004001LL,
    v10);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000ed40  sub     rsp, 28h
0x18000ed44  test    rdx, rdx
0x18000ed47  jnz     short loc_18000ED6C
0x18000ed49  mov     edx, 88h; void *
0x18000ed4e  mov     rcx, [rsp+28h]; this
0x18000ed53  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ed5a  mov     r9d, 80004003h; char *
0x18000ed60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed65  mov     eax, 80004003h
0x18000ed6a  jmp     short loc_18000EDB7
0x18000ed6c  test    r8, r8
0x18000ed6f  jnz     short loc_18000ED78
0x18000ed71  mov     edx, 89h
0x18000ed76  jmp     short loc_18000ED4E
0x18000ed78  test    r9, r9
0x18000ed7b  jnz     short loc_18000ED84
0x18000ed7d  mov     edx, 8Ah
0x18000ed82  jmp     short loc_18000ED4E
0x18000ed84  mov     r8d, [r8]; Size
0x18000ed87  xor     edx, edx; Val
0x18000ed89  mov     rcx, r9; void *
0x18000ed8c  call    memset_0
0x18000ed91  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ed96  mov     rcx, [rsp+28h]; this
0x18000ed9b  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000eda2  mov     r9d, 80004001h; char *
0x18000eda8  mov     edx, 90h; void *
0x18000edad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000edb2  mov     eax, 80004001h
0x18000edb7  add     rsp, 28h
0x18000edbb  retn
```
