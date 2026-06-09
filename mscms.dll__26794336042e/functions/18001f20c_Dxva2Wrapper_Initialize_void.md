# Dxva2Wrapper::Initialize(void)

- ea: `0x18001f20c`
- end: `0x18001f339`
- name: `?Initialize@Dxva2Wrapper@@AEAAJXZ`
- size: `301`
- prototype: `__int64 __fastcall(Dxva2Wrapper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001f194`

## callees

- `0x18001f20c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f224`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f224`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f258`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f272`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f28c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f300`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f31e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f258`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f272`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f28c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f300`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f233`

## string_xrefs

- `0x18001f217`: `Dxva2.dll`
- `0x18001f2db`: `SetMonitorColorTemperature`

## pseudocode

```c
signed int __fastcall Dxva2Wrapper::Initialize(Dxva2Wrapper *this)
{
  HMODULE Library; // rax
  signed int result; // eax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax

  Library = LoadLibraryExW(L"Dxva2.dll", 0, 0x800u);
  *((_QWORD *)this + 1) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetNumberOfPhysicalMonitorsFromHMONITOR");
    *((_QWORD *)this + 2) = ProcAddress;
    if ( ProcAddress )
    {
      v5 = GetProcAddress(*((HMODULE *)this + 1), "GetPhysicalMonitorsFromHMONITOR");
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        v6 = GetProcAddress(*((HMODULE *)this + 1), "DestroyPhysicalMonitors");
        *((_QWORD *)this + 4) = v6;
        if ( v6 )
        {
          v7 = GetProcAddress(*((HMODULE *)this + 1), "SetMonitorBrightness");
          *((_QWORD *)this + 5) = v7;
          if ( v7 )
          {
            v8 = GetProcAddress(*((HMODULE *)this + 1), "SetMonitorContrast");
            *((_QWORD *)this + 6) = v8;
            if ( v8 )
            {
              v9 = GetProcAddress(*((HMODULE *)this + 1), "SetMonitorColorTemperature");
              *((_QWORD *)this + 7) = v9;
              if ( v9 )
              {
                v10 = GetProcAddress(*((HMODULE *)this + 1), "SetVCPFeature");
                *((_QWORD *)this + 8) = v10;
                if ( v10 )
                {
                  v11 = GetProcAddress(*((HMODULE *)this + 1), "GetVCPFeatureAndVCPFeatureReply");
                  *((_QWORD *)this + 9) = v11;
                  if ( v11 )
                    return 0;
                }
              }
            }
          }
        }
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001f20c  push    rbx
0x18001f20e  sub     rsp, 20h
0x18001f212  mov     rbx, rcx
0x18001f215  xor     edx, edx; hFile
0x18001f217  lea     rcx, aDxva2Dll; "Dxva2.dll"
0x18001f21e  mov     r8d, 800h; dwFlags
0x18001f224  call    cs:__imp_LoadLibraryExW
0x18001f22a  mov     [rbx+8], rax
0x18001f22e  test    rax, rax
0x18001f231  jnz     short loc_18001F24E
0x18001f233  call    cs:__imp_GetLastError
0x18001f239  test    eax, eax
0x18001f23b  jle     loc_18001F333
0x18001f241  movzx   eax, ax
0x18001f244  or      eax, 80070000h
0x18001f249  jmp     loc_18001F333
0x18001f24e  lea     rdx, aGetnumberofphy; "GetNumberOfPhysicalMonitorsFromHMONITOR"
0x18001f255  mov     rcx, rax; hModule
0x18001f258  call    cs:__imp_GetProcAddress
0x18001f25e  mov     [rbx+10h], rax
0x18001f262  test    rax, rax
0x18001f265  jz      short loc_18001F233
0x18001f267  mov     rcx, [rbx+8]; hModule
0x18001f26b  lea     rdx, aGetphysicalmon; "GetPhysicalMonitorsFromHMONITOR"
0x18001f272  call    cs:__imp_GetProcAddress
0x18001f278  mov     [rbx+18h], rax
0x18001f27c  test    rax, rax
0x18001f27f  jz      short loc_18001F233
0x18001f281  mov     rcx, [rbx+8]; hModule
0x18001f285  lea     rdx, aDestroyphysica; "DestroyPhysicalMonitors"
0x18001f28c  call    cs:__imp_GetProcAddress
0x18001f292  mov     [rbx+20h], rax
0x18001f296  test    rax, rax
0x18001f299  jz      short loc_18001F233
0x18001f29b  mov     rcx, [rbx+8]; hModule
0x18001f29f  lea     rdx, aSetmonitorbrig; "SetMonitorBrightness"
0x18001f2a6  call    cs:__imp_GetProcAddress
0x18001f2ac  mov     [rbx+28h], rax
0x18001f2b0  test    rax, rax
0x18001f2b3  jz      loc_18001F233
0x18001f2b9  mov     rcx, [rbx+8]; hModule
0x18001f2bd  lea     rdx, aSetmonitorcont; "SetMonitorContrast"
0x18001f2c4  call    cs:__imp_GetProcAddress
0x18001f2ca  mov     [rbx+30h], rax
0x18001f2ce  test    rax, rax
0x18001f2d1  jz      loc_18001F233
0x18001f2d7  mov     rcx, [rbx+8]; hModule
0x18001f2db  lea     rdx, aSetmonitorcolo; "SetMonitorColorTemperature"
0x18001f2e2  call    cs:__imp_GetProcAddress
0x18001f2e8  mov     [rbx+38h], rax
0x18001f2ec  test    rax, rax
0x18001f2ef  jz      loc_18001F233
0x18001f2f5  mov     rcx, [rbx+8]; hModule
0x18001f2f9  lea     rdx, aSetvcpfeature; "SetVCPFeature"
0x18001f300  call    cs:__imp_GetProcAddress
0x18001f306  mov     [rbx+40h], rax
0x18001f30a  test    rax, rax
0x18001f30d  jz      loc_18001F233
0x18001f313  mov     rcx, [rbx+8]; hModule
0x18001f317  lea     rdx, aGetvcpfeaturea; "GetVCPFeatureAndVCPFeatureReply"
0x18001f31e  call    cs:__imp_GetProcAddress
0x18001f324  mov     [rbx+48h], rax
0x18001f328  test    rax, rax
0x18001f32b  jz      loc_18001F233
0x18001f331  xor     eax, eax
0x18001f333  add     rsp, 20h
0x18001f337  pop     rbx
0x18001f338  retn
```
