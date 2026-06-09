# FrameProvider::Init(void)

- ea: `0x180016c48`
- end: `0x180016cd8`
- name: `?Init@FrameProvider@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f7d0`

## callees

- `0x180016c48`
- `0x18001774c`
- `0x18001784c`
- `0x1800180f0`
- `0x180018220`

## import_xrefs

- `DUI70!InitProcessPriv` at `0x180016c6c`
- `DUI70!InitProcessPriv` at `0x180016c6c`
- `DUI70!UnInitProcessPriv` at `0x180016c90`
- `DUI70!UnInitProcessPriv` at `0x180016c90`
- `DUI70!InitThread` at `0x180016c7d`
- `DUI70!InitThread` at `0x180016c7d`

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
0x180016c48  mov     [rsp+arg_0], rbx
0x180016c4d  push    rdi
0x180016c4e  sub     rsp, 30h
0x180016c52  mov     r9b, 1
0x180016c55  mov     [rsp+38h+var_18], 1
0x180016c5a  mov     rdi, rcx
0x180016c5d  lea     rdx, __ImageBase
0x180016c64  mov     r8b, r9b
0x180016c67  mov     ecx, 0Eh
0x180016c6c  call    cs:__imp_InitProcessPriv
0x180016c72  mov     ebx, eax
0x180016c74  test    eax, eax
0x180016c76  js      short loc_180016C96
0x180016c78  mov     ecx, 2
0x180016c7d  call    cs:__imp_InitThread
0x180016c83  mov     ebx, eax
0x180016c85  test    eax, eax
0x180016c87  jns     short loc_180016C96
0x180016c89  lea     rcx, __ImageBase
0x180016c90  call    cs:__imp_UnInitProcessPriv
0x180016c96  mov     [rdi+268h], ebx
0x180016c9c  test    ebx, ebx
0x180016c9e  js      short loc_180016CCB
0x180016ca0  mov     ebx, 80004005h
0x180016ca5  call    ?Register@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x180016caa  test    eax, eax
0x180016cac  js      short loc_180016CCB
0x180016cae  call    ?Register@CElementWithSite@@SAJXZ; CElementWithSite::Register(void)
0x180016cb3  test    eax, eax
0x180016cb5  js      short loc_180016CCB
0x180016cb7  call    ?Register@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x180016cbc  test    eax, eax
0x180016cbe  js      short loc_180016CCB
0x180016cc0  call    ?Register@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x180016cc5  test    eax, eax
0x180016cc7  js      short loc_180016CCB
0x180016cc9  xor     ebx, ebx
0x180016ccb  mov     eax, ebx
0x180016ccd  mov     rbx, [rsp+38h+arg_0]
0x180016cd2  add     rsp, 30h
0x180016cd6  pop     rdi
0x180016cd7  retn
```
