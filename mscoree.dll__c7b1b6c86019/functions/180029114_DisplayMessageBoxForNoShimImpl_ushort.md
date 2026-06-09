# DisplayMessageBoxForNoShimImpl(ushort *)

- ea: `0x180029114`
- end: `0x18002920a`
- name: `?DisplayMessageBoxForNoShimImpl@@YAXPEAG@Z`
- size: `246`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800071c0`
- `0x180028a60`

## callees

- `0x180029114`
- `0x18002a3b8`
- `0x18002a570`
- `0x18002b19c`
- `0x18003e758`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `USER32!LoadStringW` at `0x18002918a`
- `USER32!LoadStringW` at `0x1800291ac`
- `USER32!LoadStringW` at `0x18002918a`
- `USER32!LoadStringW` at `0x1800291ac`

## string_xrefs

- `0x1800291bb`: `mscoreei.dll`

## pseudocode

```c
void __fastcall DisplayMessageBoxForNoShimImpl(unsigned __int16 *a1)
{
  HINSTANCE ResourceInst; // rax
  HINSTANCE v2; // rax
  unsigned int ShimMBRTLStyle; // eax
  WCHAR v4[256]; // [rsp+40h] [rbp-618h] BYREF
  WCHAR Buffer[512]; // [rsp+240h] [rbp-418h] BYREF

  if ( !(unsigned int)NoGuiFromShim() )
  {
    memset_thunk_772440563353939046(Buffer, 0, 0x400u);
    memset_thunk_772440563353939046(v4, 0, 0x200u);
    if ( GetResourceInst() )
    {
      ResourceInst = GetResourceInst();
      if ( LoadStringW(ResourceInst, 3u, Buffer, 512) > 0 )
      {
        v2 = GetResourceInst();
        if ( LoadStringW(v2, 2u, v4, 256) > 0 )
        {
          ShimMBRTLStyle = GetShimMBRTLStyle();
          UtilMessageBoxNonLocalized(0, Buffer, v4, ShimMBRTLStyle | 0x10, 0, 1, g_wszShimImplDllPath);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180029114  sub     rsp, 658h
0x18002911b  mov     rax, cs:__security_cookie
0x180029122  xor     rax, rsp
0x180029125  mov     [rsp+658h+var_18], rax
0x18002912d  call    ?NoGuiFromShim@@YAHXZ; NoGuiFromShim(void)
0x180029132  test    eax, eax
0x180029134  jnz     loc_1800291F2
0x18002913a  xor     edx, edx; Val
0x18002913c  lea     rcx, [rsp+658h+Buffer]; void *
0x180029144  mov     r8d, 400h; Size
0x18002914a  call    memset$thunk$772440563353939046
0x18002914f  xor     edx, edx; Val
0x180029151  lea     rcx, [rsp+658h+var_618]; void *
0x180029156  mov     r8d, 200h; Size
0x18002915c  call    memset$thunk$772440563353939046
0x180029161  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029166  test    rax, rax
0x180029169  jz      loc_1800291F2
0x18002916f  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029174  mov     rcx, rax; hInstance
0x180029177  lea     r8, [rsp+658h+Buffer]; lpBuffer
0x18002917f  mov     r9d, 200h; cchBufferMax
0x180029185  mov     edx, 3; uID
0x18002918a  call    cs:__imp_LoadStringW
0x180029190  test    eax, eax
0x180029192  jle     short loc_1800291F2
0x180029194  call    ?GetResourceInst@@YAPEAUHINSTANCE__@@XZ; GetResourceInst(void)
0x180029199  mov     rcx, rax; hInstance
0x18002919c  lea     r8, [rsp+658h+var_618]; lpBuffer
0x1800291a1  mov     r9d, 100h; cchBufferMax
0x1800291a7  mov     edx, 2; uID
0x1800291ac  call    cs:__imp_LoadStringW
0x1800291b2  test    eax, eax
0x1800291b4  jle     short loc_1800291F2
0x1800291b6  call    ?GetShimMBRTLStyle@@YAIXZ; GetShimMBRTLStyle(void)
0x1800291bb  lea     rcx, ?g_wszShimImplDllPath@@3PAGA; "mscoreei.dll"
0x1800291c2  or      eax, 10h
0x1800291c5  mov     [rsp+658h+var_628], rcx
0x1800291ca  lea     r8, [rsp+658h+var_618]; unsigned __int16 *
0x1800291cf  mov     [rsp+658h+var_630], 1; int
0x1800291d7  lea     rdx, [rsp+658h+Buffer]; unsigned __int16 *
0x1800291df  xor     ecx, ecx; HWND
0x1800291e1  mov     qword ptr [rsp+658h+var_638], 0; int
0x1800291ea  mov     r9d, eax; unsigned int
0x1800291ed  call    ?UtilMessageBoxNonLocalized@@YAHPEAUHWND__@@PEBG1IHHZZ; UtilMessageBoxNonLocalized(HWND__ *,ushort const *,ushort const *,uint,int,int,...)
0x1800291f2  mov     rcx, [rsp+658h+var_18]
0x1800291fa  xor     rcx, rsp; StackCookie
0x1800291fd  call    __security_check_cookie
0x180029202  add     rsp, 658h
0x180029209  retn
```
