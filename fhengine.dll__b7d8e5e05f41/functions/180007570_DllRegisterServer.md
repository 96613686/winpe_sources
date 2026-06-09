# DllRegisterServer

- ea: `0x180007570`
- end: `0x1800075e5`
- name: `DllRegisterServer`
- size: `117`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007510`

## callees

- `0x180006934`
- `0x180007294`
- `0x180007570`
- `0x180007818`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18000757a`
- `KERNEL32!GetThreadLocale` at `0x18000757a`
- `KERNEL32!SetThreadLocale` at `0x180007587`
- `KERNEL32!SetThreadLocale` at `0x180007596`
- `KERNEL32!SetThreadLocale` at `0x180007587`
- `KERNEL32!SetThreadLocale` at `0x180007596`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebx
  HRESULT v1; // edi

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CEngineModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  if ( v1 >= 0 )
    return PrxDllRegisterServer();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids, (unsigned int)v1);
  return v1;
}

```

## disassembly

```asm
0x180007570  mov     [rsp+arg_0], rbx
0x180007575  push    rdi
0x180007576  sub     rsp, 20h
0x18000757a  call    cs:__imp_GetThreadLocale
0x180007580  mov     ecx, 800h; Locale
0x180007585  mov     ebx, eax
0x180007587  call    cs:__imp_SetThreadLocale
0x18000758d  call    ?RegisterServer@?$CAtlModuleT@VCEngineModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CEngineModule>::RegisterServer(int,_GUID const *)
0x180007592  mov     ecx, ebx; Locale
0x180007594  mov     edi, eax
0x180007596  call    cs:__imp_SetThreadLocale
0x18000759c  test    edi, edi
0x18000759e  jns     short loc_1800075D5
0x1800075a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075a7  lea     rax, WPP_GLOBAL_Control
0x1800075ae  cmp     rcx, rax
0x1800075b1  jz      short loc_1800075D1
0x1800075b3  test    byte ptr [rcx+1Ch], 2
0x1800075b7  jz      short loc_1800075D1
0x1800075b9  mov     rcx, [rcx+10h]
0x1800075bd  lea     r8, WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids
0x1800075c4  mov     edx, 0Ch
0x1800075c9  mov     r9d, edi
0x1800075cc  call    WPP_SF_d
0x1800075d1  mov     eax, edi
0x1800075d3  jmp     short loc_1800075DA
0x1800075d5  call    PrxDllRegisterServer
0x1800075da  mov     rbx, [rsp+28h+arg_0]
0x1800075df  add     rsp, 20h
0x1800075e3  pop     rdi
0x1800075e4  retn
```
