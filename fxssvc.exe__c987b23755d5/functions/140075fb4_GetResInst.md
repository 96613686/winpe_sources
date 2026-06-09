# GetResInst

- ea: `0x140075fb4`
- end: `0x1400760c3`
- name: `GetResInst`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140024994`
- `0x14002b058`

## callees

- `0x140004b30`
- `0x140004df0`
- `0x140075fb4`
- `0x1400760cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007602b`
- `KERNEL32!GetLastError` at `0x140076089`
- `KERNEL32!GetLastError` at `0x14007602b`
- `KERNEL32!GetLastError` at `0x140076089`
- `KERNEL32!LoadLibraryW` at `0x14007605f`
- `KERNEL32!LoadLibraryW` at `0x14007605f`

## string_xrefs

- `0x140076038`: `FXSRESM.DLL`
- `0x140076058`: `FXSRESM.DLL`
- `0x140076096`: `FXSRESM.DLL`

## pseudocode

```c
HMODULE GetResInst()
{
  HMODULE result; // rax
  char LastError; // al
  char v2; // al

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids);
  }
  result = hLibModule;
  if ( !hLibModule )
  {
    result = LoadLibraryFromLocalFolder();
    hLibModule = result;
    if ( !result )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
          (unsigned int)L"FXSRESM.DLL",
          LastError);
      }
      result = LoadLibraryW(L"FXSRESM.DLL");
      hLibModule = result;
      if ( !result
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v2 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
          (unsigned int)L"FXSRESM.DLL",
          v2);
        return hLibModule;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140075fb4  push    rdi
0x140075fb6  sub     rsp, 30h
0x140075fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140075fc1  lea     rdi, WPP_GLOBAL_Control
0x140075fc8  cmp     rcx, rdi
0x140075fcb  jz      short loc_140075FEE
0x140075fcd  test    byte ptr [rcx+1Ch], 2
0x140075fd1  jz      short loc_140075FEE
0x140075fd3  cmp     byte ptr [rcx+19h], 5
0x140075fd7  jb      short loc_140075FEE
0x140075fd9  mov     rcx, [rcx+10h]
0x140075fdd  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x140075fe4  mov     edx, 0Ah
0x140075fe9  call    WPP_SF_
0x140075fee  mov     rax, cs:hLibModule
0x140075ff5  test    rax, rax
0x140075ff8  jnz     loc_1400760BD
0x140075ffe  call    LoadLibraryFromLocalFolder
0x140076003  mov     cs:hLibModule, rax
0x14007600a  test    rax, rax
0x14007600d  jnz     loc_1400760BD
0x140076013  mov     rax, cs:WPP_GLOBAL_Control
0x14007601a  cmp     rax, rdi
0x14007601d  jz      short loc_140076058
0x14007601f  test    byte ptr [rax+1Ch], 2
0x140076023  jz      short loc_140076058
0x140076025  cmp     byte ptr [rax+19h], 2
0x140076029  jb      short loc_140076058
0x14007602b  call    cs:__imp_GetLastError
0x140076031  mov     rcx, cs:WPP_GLOBAL_Control
0x140076038  lea     r9, aFxsresmDll; "FXSRESM.DLL"
0x14007603f  mov     edx, 0Bh
0x140076044  mov     [rsp+38h+var_18], eax
0x140076048  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x14007604f  mov     rcx, [rcx+10h]
0x140076053  call    WPP_SF_Sd
0x140076058  lea     rcx, aFxsresmDll; "FXSRESM.DLL"
0x14007605f  call    cs:__imp_LoadLibraryW
0x140076065  mov     cs:hLibModule, rax
0x14007606c  test    rax, rax
0x14007606f  jnz     short loc_1400760BD
0x140076071  mov     rcx, cs:WPP_GLOBAL_Control
0x140076078  cmp     rcx, rdi
0x14007607b  jz      short loc_1400760BD
0x14007607d  test    byte ptr [rcx+1Ch], 2
0x140076081  jz      short loc_1400760BD
0x140076083  cmp     byte ptr [rcx+19h], 2
0x140076087  jb      short loc_1400760BD
0x140076089  call    cs:__imp_GetLastError
0x14007608f  mov     rcx, cs:WPP_GLOBAL_Control
0x140076096  lea     r9, aFxsresmDll; "FXSRESM.DLL"
0x14007609d  mov     edx, 0Ch
0x1400760a2  mov     [rsp+38h+var_18], eax
0x1400760a6  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x1400760ad  mov     rcx, [rcx+10h]
0x1400760b1  call    WPP_SF_Sd
0x1400760b6  mov     rax, cs:hLibModule
0x1400760bd  add     rsp, 30h
0x1400760c1  pop     rdi
0x1400760c2  retn
```
