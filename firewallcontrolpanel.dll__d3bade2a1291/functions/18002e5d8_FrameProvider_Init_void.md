# FrameProvider::Init(void)

- ea: `0x18002e5d8`
- end: `0x18002e668`
- name: `?Init@FrameProvider@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010c00`

## callees

- `0x18002e5d8`
- `0x18002f81c`
- `0x18002f91c`
- `0x1800307d8`
- `0x180030908`

## import_xrefs

- `DUI70!UnInitProcessPriv` at `0x18002e620`
- `DUI70!UnInitProcessPriv` at `0x18002e620`
- `DUI70!InitThread` at `0x18002e60d`
- `DUI70!InitThread` at `0x18002e60d`
- `DUI70!InitProcessPriv` at `0x18002e5fc`
- `DUI70!InitProcessPriv` at `0x18002e5fc`

## pseudocode

```c
__int64 __fastcall FrameProvider::Init(FrameProvider *this, __int64 a2, __int64 a3)
{
  int inited; // ebx

  LOBYTE(a3) = 1;
  inited = InitProcessPriv(14, &_ImageBase, a3);
  if ( inited >= 0 )
  {
    inited = InitThread(2);
    if ( inited < 0 )
      UnInitProcessPriv(&_ImageBase);
  }
  *((_DWORD *)this + 154) = inited;
  if ( inited >= 0 )
  {
    inited = -2147467259;
    if ( (int)DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register() >= 0
      && (int)CElementWithSite::Register() >= 0
      && (int)DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register() >= 0
      && (int)DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register() >= 0 )
    {
      return 0;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002e5d8  mov     [rsp+arg_0], rbx
0x18002e5dd  push    rdi
0x18002e5de  sub     rsp, 30h
0x18002e5e2  mov     r9b, 1
0x18002e5e5  mov     [rsp+38h+var_18], 1
0x18002e5ea  mov     rdi, rcx
0x18002e5ed  lea     rdx, __ImageBase
0x18002e5f4  mov     r8b, r9b
0x18002e5f7  mov     ecx, 0Eh
0x18002e5fc  call    cs:__imp_InitProcessPriv
0x18002e602  mov     ebx, eax
0x18002e604  test    eax, eax
0x18002e606  js      short loc_18002E626
0x18002e608  mov     ecx, 2
0x18002e60d  call    cs:__imp_InitThread
0x18002e613  mov     ebx, eax
0x18002e615  test    eax, eax
0x18002e617  jns     short loc_18002E626
0x18002e619  lea     rcx, __ImageBase
0x18002e620  call    cs:__imp_UnInitProcessPriv
0x18002e626  mov     [rdi+268h], ebx
0x18002e62c  test    ebx, ebx
0x18002e62e  js      short loc_18002E65B
0x18002e630  mov     ebx, 80004005h
0x18002e635  call    ?Register@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002e63a  test    eax, eax
0x18002e63c  js      short loc_18002E65B
0x18002e63e  call    ?Register@CElementWithSite@@SAJXZ; CElementWithSite::Register(void)
0x18002e643  test    eax, eax
0x18002e645  js      short loc_18002E65B
0x18002e647  call    ?Register@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002e64c  test    eax, eax
0x18002e64e  js      short loc_18002E65B
0x18002e650  call    ?Register@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002e655  test    eax, eax
0x18002e657  js      short loc_18002E65B
0x18002e659  xor     ebx, ebx
0x18002e65b  mov     eax, ebx
0x18002e65d  mov     rbx, [rsp+38h+arg_0]
0x18002e662  add     rsp, 30h
0x18002e666  pop     rdi
0x18002e667  retn
```
