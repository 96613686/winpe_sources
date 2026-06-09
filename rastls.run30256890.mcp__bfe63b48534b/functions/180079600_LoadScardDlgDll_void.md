# LoadScardDlgDll(void)

- ea: `0x180079600`
- end: `0x1800796c0`
- name: `?LoadScardDlgDll@@YAKXZ`
- size: `192`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800782b0`

## callees

- `0x180005010`
- `0x180079600`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079666`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007967e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007967e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007961c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007961c`

## string_xrefs

- `0x180079615`: `scarddlg.dll`

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
0x180079600  push    rbx
0x180079602  sub     rsp, 20h
0x180079606  xor     ebx, ebx
0x180079608  cmp     cs:?g_hInstanceScardDlg@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstanceScardDlg
0x18007960f  jnz     loc_1800796B7
0x180079615  lea     rcx, aScarddlgDll; "scarddlg.dll"
0x18007961c  call    cs:__imp_LoadLibraryW
0x180079623  nop     dword ptr [rax+rax+00h]
0x180079628  mov     cs:?g_hInstanceScardDlg@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstanceScardDlg
0x18007962f  test    rax, rax
0x180079632  jnz     short loc_18007965C
0x180079634  call    cs:__imp_GetLastError
0x18007963b  nop     dword ptr [rax+rax+00h]
0x180079640  mov     ebx, eax
0x180079642  mov     rcx, cs:WPP_GLOBAL_Control
0x180079649  lea     rax, WPP_GLOBAL_Control
0x180079650  cmp     rcx, rax
0x180079653  jz      short loc_1800796B7
0x180079655  mov     edx, 0Ah
0x18007965a  jmp     short loc_1800796A4
0x18007965c  lea     rdx, aScarduidlgsele; "SCardUIDlgSelectCardW"
0x180079663  mov     rcx, rax; hModule
0x180079666  call    cs:__imp_GetProcAddress
0x18007966d  nop     dword ptr [rax+rax+00h]
0x180079672  mov     cs:?g_fnDlgSelectCard@@3P6AJPEAUOPENCARDNAME_EXW@@@ZEA, rax; long (*g_fnDlgSelectCard)(OPENCARDNAME_EXW *)
0x180079679  test    rax, rax
0x18007967c  jnz     short loc_1800796B7
0x18007967e  call    cs:__imp_GetLastError
0x180079685  nop     dword ptr [rax+rax+00h]
0x18007968a  mov     ebx, eax
0x18007968c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079693  lea     rax, WPP_GLOBAL_Control
0x18007969a  cmp     rcx, rax
0x18007969d  jz      short loc_1800796B7
0x18007969f  mov     edx, 0Bh
0x1800796a4  mov     rcx, [rcx+10h]
0x1800796a8  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800796af  mov     r9d, ebx
0x1800796b2  call    WPP_SF_d
0x1800796b7  mov     eax, ebx
0x1800796b9  add     rsp, 20h
0x1800796bd  pop     rbx
0x1800796be  retn
```
