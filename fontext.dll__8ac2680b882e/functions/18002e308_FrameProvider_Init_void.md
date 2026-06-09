# FrameProvider::Init(void)

- ea: `0x18002e308`
- end: `0x18002e398`
- name: `?Init@FrameProvider@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800209d0`

## callees

- `0x18002e308`
- `0x18002f3fc`
- `0x18002f4fc`
- `0x180030390`
- `0x1800304c0`

## import_xrefs

- `DUI70!InitProcessPriv` at `0x18002e32c`
- `DUI70!InitProcessPriv` at `0x18002e32c`
- `DUI70!UnInitProcessPriv` at `0x18002e350`
- `DUI70!UnInitProcessPriv` at `0x18002e350`
- `DUI70!InitThread` at `0x18002e33d`
- `DUI70!InitThread` at `0x18002e33d`

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
0x18002e308  mov     [rsp+arg_0], rbx
0x18002e30d  push    rdi
0x18002e30e  sub     rsp, 30h
0x18002e312  mov     r9b, 1
0x18002e315  mov     [rsp+38h+var_18], 1
0x18002e31a  mov     rdi, rcx
0x18002e31d  lea     rdx, __ImageBase
0x18002e324  mov     r8b, r9b
0x18002e327  mov     ecx, 0Eh
0x18002e32c  call    cs:__imp_InitProcessPriv
0x18002e332  mov     ebx, eax
0x18002e334  test    eax, eax
0x18002e336  js      short loc_18002E356
0x18002e338  mov     ecx, 2
0x18002e33d  call    cs:__imp_InitThread
0x18002e343  mov     ebx, eax
0x18002e345  test    eax, eax
0x18002e347  jns     short loc_18002E356
0x18002e349  lea     rcx, __ImageBase
0x18002e350  call    cs:__imp_UnInitProcessPriv
0x18002e356  mov     [rdi+268h], ebx
0x18002e35c  test    ebx, ebx
0x18002e35e  js      short loc_18002E38B
0x18002e360  mov     ebx, 80004005h
0x18002e365  call    ?Register@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002e36a  test    eax, eax
0x18002e36c  js      short loc_18002E38B
0x18002e36e  call    ?Register@CElementWithSite@@SAJXZ; CElementWithSite::Register(void)
0x18002e373  test    eax, eax
0x18002e375  js      short loc_18002E38B
0x18002e377  call    ?Register@?$ClassInfo@VCFrameModule@@VCElementWithSite@@V?$StandardCreator@VCFrameModule@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFrameModule,CElementWithSite,DirectUI::StandardCreator<CFrameModule>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002e37c  test    eax, eax
0x18002e37e  js      short loc_18002E38B
0x18002e380  call    ?Register@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18002e385  test    eax, eax
0x18002e387  js      short loc_18002E38B
0x18002e389  xor     ebx, ebx
0x18002e38b  mov     eax, ebx
0x18002e38d  mov     rbx, [rsp+38h+arg_0]
0x18002e392  add     rsp, 30h
0x18002e396  pop     rdi
0x18002e397  retn
```
