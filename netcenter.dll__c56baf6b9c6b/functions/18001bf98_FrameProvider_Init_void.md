# FrameProvider::Init(void)

- ea: `0x18001bf98`
- end: `0x18001c028`
- name: `?Init@FrameProvider@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015500`

## callees

- `0x18001bf98`
- `0x18001d4cc`
- `0x18001d5cc`
- `0x18001de78`
- `0x18001dfa8`

## import_xrefs

- `DUI70!UnInitProcessPriv` at `0x18001bfe0`
- `DUI70!UnInitProcessPriv` at `0x18001bfe0`
- `DUI70!InitThread` at `0x18001bfcd`
- `DUI70!InitThread` at `0x18001bfcd`
- `DUI70!InitProcessPriv` at `0x18001bfbc`
- `DUI70!InitProcessPriv` at `0x18001bfbc`

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
0x18001bf98  mov     [rsp+arg_0], rbx
0x18001bf9d  push    rdi
0x18001bf9e  sub     rsp, 30h
0x18001bfa2  mov     r9b, 1
0x18001bfa5  mov     [rsp+38h+var_18], 1
0x18001bfaa  mov     rdi, rcx
0x18001bfad  lea     rdx, __ImageBase
0x18001bfb4  mov     r8b, r9b
0x18001bfb7  mov     ecx, 0Eh
0x18001bfbc  call    cs:__imp_InitProcessPriv
0x18001bfc2  mov     ebx, eax
0x18001bfc4  test    eax, eax
0x18001bfc6  js      short loc_18001BFE6
0x18001bfc8  mov     ecx, 2
0x18001bfcd  call    cs:__imp_InitThread
0x18001bfd3  mov     ebx, eax
0x18001bfd5  test    eax, eax
0x18001bfd7  jns     short loc_18001BFE6
0x18001bfd9  lea     rcx, __ImageBase
0x18001bfe0  call    cs:__imp_UnInitProcessPriv
0x18001bfe6  mov     [rdi+268h], ebx
0x18001bfec  test    ebx, ebx
0x18001bfee  js      short loc_18001C01B
0x18001bff0  mov     ebx, 80004005h
0x18001bff5  call    ?Register@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18001bffa  test    eax, eax
0x18001bffc  js      short loc_18001C01B
0x18001bffe  call    ?Register@CElementWithSite@@SAJXZ; CElementWithSite::Register(void)
0x18001c003  test    eax, eax
0x18001c005  js      short loc_18001C01B
0x18001c007  call    ?Register@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18001c00c  test    eax, eax
0x18001c00e  js      short loc_18001C01B
0x18001c010  call    ?Register@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18001c015  test    eax, eax
0x18001c017  js      short loc_18001C01B
0x18001c019  xor     ebx, ebx
0x18001c01b  mov     eax, ebx
0x18001c01d  mov     rbx, [rsp+38h+arg_0]
0x18001c022  add     rsp, 30h
0x18001c026  pop     rdi
0x18001c027  retn
```
