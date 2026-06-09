# FontSubsettingTelemetry::CreateFontPackage::~CreateFontPackage(void)

- ea: `0x180003b1c`
- end: `0x180003b41`
- name: `??1CreateFontPackage@FontSubsettingTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(FontSubsettingTelemetry::CreateFontPackage *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a70`

## callees

- `0x1800037d4`
- `0x180003f30`

## pseudocode

```c
void __fastcall FontSubsettingTelemetry::CreateFontPackage::~CreateFontPackage(
        FontSubsettingTelemetry::CreateFontPackage *this)
{
  *(_QWORD *)this = &FontSubsettingTelemetry::CreateFontPackage::`vftable';
  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180003b1c  push    rbx
0x180003b1e  sub     rsp, 20h
0x180003b22  lea     rax, ??_7CreateFontPackage@FontSubsettingTelemetry@@6B@; const FontSubsettingTelemetry::CreateFontPackage::`vftable'
0x180003b29  mov     rbx, rcx
0x180003b2c  mov     [rcx], rax
0x180003b2f  call    ?Destroy@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180003b34  mov     rcx, rbx
0x180003b37  add     rsp, 20h
0x180003b3b  pop     rbx
0x180003b3c  jmp     ??1?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
