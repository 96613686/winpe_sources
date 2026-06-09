# CWizardExtension::Initialize(void)

- ea: `0x180037ca4`
- end: `0x180037cf1`
- name: `?Initialize@CWizardExtension@@QEAAJXZ`
- size: `77`
- prototype: `__int64 __fastcall(CWizardExtension *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180037e10`
- `0x180037ec0`
- `0x180037f90`
- `0x180038050`
- `0x1800380f0`
- `0x1800381b0`
- `0x180038270`

## callees

- `0x18000a2ac`
- `0x180037ca4`
- `0x180037cf8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037cde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037cde`

## pseudocode

```c
__int64 __fastcall CWizardExtension::Initialize(CWizardExtension *this)
{
  int ExtensionPoint; // ebx
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  hMem = 0;
  ExtensionPoint = CWizardExtension::_ReadExtensionPoint(this, (BYTE **)&hMem);
  if ( ExtensionPoint >= 0 )
    ExtensionPoint = CCryptUiExtension::Initialize(this, (const unsigned __int16 *)hMem);
  LocalFree(hMem);
  return (unsigned int)ExtensionPoint;
}

```

## disassembly

```asm
0x180037ca4  mov     [rsp+arg_0], rbx
0x180037ca9  push    rdi
0x180037caa  sub     rsp, 20h
0x180037cae  lea     rdx, [rsp+28h+hMem]; unsigned __int16 **
0x180037cb3  mov     [rsp+28h+hMem], 0
0x180037cbc  mov     rdi, rcx
0x180037cbf  call    ?_ReadExtensionPoint@CWizardExtension@@AEAAJPEAPEAG@Z; CWizardExtension::_ReadExtensionPoint(ushort * *)
0x180037cc4  mov     ebx, eax
0x180037cc6  test    eax, eax
0x180037cc8  js      short loc_180037CD9
0x180037cca  mov     rdx, [rsp+28h+hMem]; unsigned __int16 *
0x180037ccf  mov     rcx, rdi; this
0x180037cd2  call    ?Initialize@CCryptUiExtension@@IEAAJPEBG@Z; CCryptUiExtension::Initialize(ushort const *)
0x180037cd7  mov     ebx, eax
0x180037cd9  mov     rcx, [rsp+28h+hMem]; hMem
0x180037cde  call    cs:__imp_LocalFree
0x180037ce4  mov     eax, ebx
0x180037ce6  mov     rbx, [rsp+28h+arg_0]
0x180037ceb  add     rsp, 20h
0x180037cef  pop     rdi
0x180037cf0  retn
```
