# LoadScardDlgDll(void)

- ea: `0x1800743b0`
- end: `0x180074457`
- name: `?LoadScardDlgDll@@YAKXZ`
- size: `167`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800731d4`

## callees

- `0x180004bd0`
- `0x1800743b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007440a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007440a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800743de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007441c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800743de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007441c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800743cc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800743cc`

## string_xrefs

- `0x1800743c5`: `scarddlg.dll`

## pseudocode

```c
__int64 LoadScardDlgDll(void)
{
  DWORD LastError; // ebx
  HMODULE LibraryW; // rax
  struct _EAPTLS_CONTROL_BLOCK *v2; // rcx
  __int64 v3; // rdx

  LastError = 0;
  if ( !g_hInstanceScardDlg )
  {
    LibraryW = LoadLibraryW(L"scarddlg.dll");
    g_hInstanceScardDlg = LibraryW;
    if ( LibraryW )
    {
      g_fnDlgSelectCard = (int (*)(struct OPENCARDNAME_EXW *))GetProcAddress(LibraryW, "SCardUIDlgSelectCardW");
      if ( !g_fnDlgSelectCard )
      {
        LastError = GetLastError();
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v3 = 11;
          goto LABEL_8;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v3 = 10;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v2 + 2), v3, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, LastError);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800743b0  push    rbx
0x1800743b2  sub     rsp, 20h
0x1800743b6  xor     ebx, ebx
0x1800743b8  cmp     cs:?g_hInstanceScardDlg@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstanceScardDlg
0x1800743bf  jnz     loc_18007444F
0x1800743c5  lea     rcx, aScarddlgDll; "scarddlg.dll"
0x1800743cc  call    cs:__imp_LoadLibraryW
0x1800743d2  mov     cs:?g_hInstanceScardDlg@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstanceScardDlg
0x1800743d9  test    rax, rax
0x1800743dc  jnz     short loc_180074400
0x1800743de  call    cs:__imp_GetLastError
0x1800743e4  mov     ebx, eax
0x1800743e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743ed  lea     rax, WPP_GLOBAL_Control
0x1800743f4  cmp     rcx, rax
0x1800743f7  jz      short loc_18007444F
0x1800743f9  mov     edx, 0Ah
0x1800743fe  jmp     short loc_18007443C
0x180074400  lea     rdx, aScarduidlgsele; "SCardUIDlgSelectCardW"
0x180074407  mov     rcx, rax; hModule
0x18007440a  call    cs:__imp_GetProcAddress
0x180074410  mov     cs:?g_fnDlgSelectCard@@3P6AJPEAUOPENCARDNAME_EXW@@@ZEA, rax; long (*g_fnDlgSelectCard)(OPENCARDNAME_EXW *)
0x180074417  test    rax, rax
0x18007441a  jnz     short loc_18007444F
0x18007441c  call    cs:__imp_GetLastError
0x180074422  mov     ebx, eax
0x180074424  mov     rcx, cs:WPP_GLOBAL_Control
0x18007442b  lea     rax, WPP_GLOBAL_Control
0x180074432  cmp     rcx, rax
0x180074435  jz      short loc_18007444F
0x180074437  mov     edx, 0Bh
0x18007443c  mov     rcx, [rcx+10h]
0x180074440  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180074447  mov     r9d, ebx
0x18007444a  call    WPP_SF_d
0x18007444f  mov     eax, ebx
0x180074451  add     rsp, 20h
0x180074455  pop     rbx
0x180074456  retn
```
