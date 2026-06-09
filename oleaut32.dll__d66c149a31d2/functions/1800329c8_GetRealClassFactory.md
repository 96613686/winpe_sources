# GetRealClassFactory

- ea: `0x1800329c8`
- end: `0x180032a27`
- name: `GetRealClassFactory`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032948`

## callees

- `0x1800329c8`
- `0x18004a530`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180032a05`
- `RPCRT4!NdrDllGetClassObject` at `0x180032a05`

## pseudocode

```c
HRESULT __fastcall GetRealClassFactory(int a1, void **a2)
{
  struct IPSFactoryBuffer *v4; // rax

  if ( a1 )
  {
    *a2 = 0;
    return NdrDllGetClassObject(
             &IID_IProvideClassInfo,
             &IID_IPSFactoryBuffer,
             a2,
             (const ProxyFileInfo **)&aProxyFileList,
             &IID_IProvideClassInfo,
             &gPFactory);
  }
  else
  {
    v4 = COleAutomationPSFactory::Create();
    *a2 = v4;
    return v4 == 0 ? 0x8007000E : 0;
  }
}

```

## disassembly

```asm
0x1800329c8  push    rbx
0x1800329ca  sub     rsp, 30h
0x1800329ce  mov     rbx, rdx
0x1800329d1  test    ecx, ecx
0x1800329d3  jz      short loc_180032A11
0x1800329d5  lea     rax, gPFactory
0x1800329dc  mov     qword ptr [rdx], 0
0x1800329e3  lea     rcx, IID_IProvideClassInfo; rclsid
0x1800329ea  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800329ef  mov     r8, rdx; ppv
0x1800329f2  mov     [rsp+38h+pclsid], rcx; pclsid
0x1800329f7  lea     r9, aProxyFileList; pProxyFileList
0x1800329fe  lea     rdx, IID_IPSFactoryBuffer; riid
0x180032a05  call    cs:__imp_NdrDllGetClassObject
0x180032a0b  add     rsp, 30h
0x180032a0f  pop     rbx
0x180032a10  retn
0x180032a11  call    ?Create@COleAutomationPSFactory@@SAPEAUIPSFactoryBuffer@@XZ; COleAutomationPSFactory::Create(void)
0x180032a16  mov     [rbx], rax
0x180032a19  neg     rax
0x180032a1c  sbb     eax, eax
0x180032a1e  not     eax
0x180032a20  and     eax, 8007000Eh
0x180032a25  jmp     short loc_180032A0B
```
