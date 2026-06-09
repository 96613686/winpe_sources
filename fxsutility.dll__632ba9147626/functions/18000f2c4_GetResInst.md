# GetResInst

- ea: `0x18000f2c4`
- end: `0x18000f3dd`
- name: `GetResInst`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000edb0`

## callees

- `0x180005eac`
- `0x18000d6bc`
- `0x18000f2c4`
- `0x18000f3e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f34c`
- `KERNEL32!GetLastError` at `0x18000f3a2`
- `KERNEL32!GetLastError` at `0x18000f34c`
- `KERNEL32!GetLastError` at `0x18000f3a2`
- `KERNEL32!LoadLibraryW` at `0x18000f378`
- `KERNEL32!LoadLibraryW` at `0x18000f378`

## string_xrefs

- `0x18000f334`: `FXSRESM.DLL`

## pseudocode

```c
HMODULE __fastcall GetResInst(__int64 a1, HMODULE a2)
{
  void *v3; // rcx
  HMODULE result; // rax
  char LastError; // al
  char v6; // al

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids);
  }
  result = (HMODULE)qword_18001EE48;
  if ( !qword_18001EE48 )
  {
    result = LoadLibraryFromLocalFolder((__int64)v3, a2);
    qword_18001EE48 = (__int64)result;
    if ( !result )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
      qword_18001EE48 = (__int64)result;
      if ( !result
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids,
          (unsigned int)L"FXSRESM.DLL",
          v6);
        return (HMODULE)qword_18001EE48;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f2c4  mov     [rsp+arg_0], rbx
0x18000f2c9  push    rsi
0x18000f2ca  sub     rsp, 30h
0x18000f2ce  mov     rbx, rdx
0x18000f2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2d8  lea     rsi, WPP_GLOBAL_Control
0x18000f2df  cmp     rcx, rsi
0x18000f2e2  jz      short loc_18000F305
0x18000f2e4  test    byte ptr [rcx+1Ch], 2
0x18000f2e8  jz      short loc_18000F305
0x18000f2ea  cmp     byte ptr [rcx+19h], 5
0x18000f2ee  jb      short loc_18000F305
0x18000f2f0  mov     rcx, [rcx+10h]
0x18000f2f4  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x18000f2fb  mov     edx, 0Ah
0x18000f300  call    WPP_SF_
0x18000f305  mov     rax, cs:qword_18001EE48
0x18000f30c  test    rax, rax
0x18000f30f  jnz     loc_18000F3D2
0x18000f315  mov     rdx, rbx
0x18000f318  call    LoadLibraryFromLocalFolder
0x18000f31d  mov     cs:qword_18001EE48, rax
0x18000f324  test    rax, rax
0x18000f327  jnz     loc_18000F3D2
0x18000f32d  mov     rax, cs:WPP_GLOBAL_Control
0x18000f334  lea     rbx, aFxsresmDll; "FXSRESM.DLL"
0x18000f33b  cmp     rax, rsi
0x18000f33e  jz      short loc_18000F375
0x18000f340  test    byte ptr [rax+1Ch], 2
0x18000f344  jz      short loc_18000F375
0x18000f346  cmp     byte ptr [rax+19h], 2
0x18000f34a  jb      short loc_18000F375
0x18000f34c  call    cs:__imp_GetLastError
0x18000f352  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f359  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x18000f360  mov     edx, 0Bh
0x18000f365  mov     [rsp+38h+var_18], eax
0x18000f369  mov     r9, rbx
0x18000f36c  mov     rcx, [rcx+10h]
0x18000f370  call    WPP_SF_Sd
0x18000f375  mov     rcx, rbx; lpLibFileName
0x18000f378  call    cs:__imp_LoadLibraryW
0x18000f37e  mov     cs:qword_18001EE48, rax
0x18000f385  test    rax, rax
0x18000f388  jnz     short loc_18000F3D2
0x18000f38a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f391  cmp     rcx, rsi
0x18000f394  jz      short loc_18000F3D2
0x18000f396  test    byte ptr [rcx+1Ch], 2
0x18000f39a  jz      short loc_18000F3D2
0x18000f39c  cmp     byte ptr [rcx+19h], 2
0x18000f3a0  jb      short loc_18000F3D2
0x18000f3a2  call    cs:__imp_GetLastError
0x18000f3a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3af  lea     r8, WPP_ad5ad008bb663493a5c9d51c6a6dd328_Traceguids
0x18000f3b6  mov     edx, 0Ch
0x18000f3bb  mov     [rsp+38h+var_18], eax
0x18000f3bf  mov     r9, rbx
0x18000f3c2  mov     rcx, [rcx+10h]
0x18000f3c6  call    WPP_SF_Sd
0x18000f3cb  mov     rax, cs:qword_18001EE48
0x18000f3d2  mov     rbx, [rsp+38h+arg_0]
0x18000f3d7  add     rsp, 30h
0x18000f3db  pop     rsi
0x18000f3dc  retn
```
