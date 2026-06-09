# CHandlerBase::GetKeySetId(ulong,ushort * *)

- ea: `0x18000ecf0`
- end: `0x18000ed38`
- name: `?GetKeySetId@CHandlerBase@@UEAAJKPEAPEAG@Z`
- size: `72`
- prototype: `__int64 __fastcall(CHandlerBase *this, __int64, unsigned __int16 **, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000ecf0`
- `0x180037aa8`

## string_xrefs

- `0x18000ed21`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHandlerBase::GetKeySetId(CHandlerBase *this, __int64 a2, unsigned __int16 **a3, __int64 a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
    v5 = 111;
    v4 = -2147467263;
  }
  else
  {
    v4 = -2147467261;
    v5 = 106;
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
0x18000ecf0  push    rbx; int
0x18000ecf2  sub     rsp, 20h
0x18000ecf6  test    r8, r8
0x18000ecf9  jnz     short loc_18000ED06
0x18000ecfb  mov     ebx, 80004003h
0x18000ed00  lea     edx, [r8+6Ah]
0x18000ed04  jmp     short loc_18000ED1C
0x18000ed06  mov     qword ptr [r8], 0
0x18000ed0d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ed12  mov     edx, 6Fh ; 'o'; void *
0x18000ed17  mov     ebx, 80004001h
0x18000ed1c  mov     rcx, [rsp+28h]; this
0x18000ed21  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000ed28  mov     r9d, ebx; char *
0x18000ed2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed30  mov     eax, ebx
0x18000ed32  add     rsp, 20h
0x18000ed36  pop     rbx
0x18000ed37  retn
```
