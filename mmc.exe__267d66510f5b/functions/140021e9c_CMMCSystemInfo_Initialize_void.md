# CMMCSystemInfo::Initialize(void)

- ea: `0x140021e9c`
- end: `0x1400220d7`
- name: `?Initialize@CMMCSystemInfo@@SAXXZ`
- size: `571`
- prototype: `void(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140021afc`
- `0x140058088`
- `0x1400653fc`
- `0x1400658f4`
- `0x1400664ac`
- `0x14006d780`

## callees

- `0x140021e9c`
- `0x1400598b4`
- `0x14006623c`
- `0x140066264`
- `0x1400f3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140021f1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140021f1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140021f78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002201b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140021f78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002201b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140021fc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140021fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002206b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002206b`
- `SHELL32!SHGetFolderPathW` at `0x140021eda`
- `SHELL32!SHGetFolderPathW` at `0x140021eda`

## string_xrefs

- `0x140021f14`: `kernel32.dll`
- `0x140022011`: `GetSystemWow64DirectoryW`

## pseudocode

```c
void CMMCSystemInfo::Initialize(void)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  signed int LastError; // eax
  __int64 v3; // rcx
  __int64 v4; // rdx
  FARPROC ProcAddress; // rdi
  HANDLE CurrentProcess; // rax
  FARPROC v7; // rax
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // [rsp+60h] [rbp+8h] BYREF

  if ( !CMMCSystemInfo::s_fInitialized )
  {
    CMMCSystemInfo::s_szSysWow64Path = 0;
    CMMCSystemInfo::s_szSystem32Path = 0;
    SHGetFolderPathW(0, 37, 0, 0, &CMMCSystemInfo::s_szSystem32Path);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
      WPP_SF_S(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_a5e2870eceae33db85684ba111189499_Traceguids,
        &CMMCSystemInfo::s_szSystem32Path);
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    v1 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "IsWow64Process");
      if ( ProcAddress )
      {
        v11 = 0;
        CurrentProcess = GetCurrentProcess();
        if ( ((unsigned int (__fastcall *)(HANDLE, int *))ProcAddress)(CurrentProcess, &v11) )
        {
          v7 = GetProcAddress(v1, "GetSystemWow64DirectoryW");
          if ( v7 )
          {
            v8 = ((__int64 (__fastcall *)(wchar_t *, __int64))v7)(&CMMCSystemInfo::s_szSysWow64Path, 512);
            if ( GetLastError() == 120 )
            {
              v9 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
                return;
              v10 = 15;
            }
            else
            {
              CMMCSystemInfo::s_fIsWoWCapableSystem = 1;
              CMMCSystemInfo::s_fIsWoWProcess = v11 != 0;
              if ( (unsigned int)(v8 - 1) <= 0x1FF )
                return;
              v9 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
                return;
              v10 = 16;
            }
            WPP_SF_(*(_QWORD *)(v9 + 16), v10, WPP_a5e2870eceae33db85684ba111189499_Traceguids);
            return;
          }
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v3 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v4 = 14;
            goto LABEL_11;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v3 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v4 = 13;
            goto LABEL_11;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v3 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v4 = 12;
          goto LABEL_11;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v4 = 11;
LABEL_11:
        WPP_SF_d(*(_QWORD *)(v3 + 16), v4, WPP_a5e2870eceae33db85684ba111189499_Traceguids, (unsigned int)LastError);
      }
    }
  }
}

```

## disassembly

```asm
0x140021e9c  push    rbx
0x140021e9e  push    rbp
0x140021e9f  push    rdi
0x140021ea0  push    r14
0x140021ea2  sub     rsp, 38h
0x140021ea6  cmp     cs:?s_fInitialized@CMMCSystemInfo@@0_NA, 0; bool CMMCSystemInfo::s_fInitialized
0x140021ead  jnz     loc_1400220CD
0x140021eb3  xor     eax, eax
0x140021eb5  lea     rbx, ?s_szSystem32Path@CMMCSystemInfo@@0PAGA; ushort near * CMMCSystemInfo::s_szSystem32Path
0x140021ebc  xor     r9d, r9d; dwFlags
0x140021ebf  mov     cs:?s_szSysWow64Path@CMMCSystemInfo@@0PAGA, ax; ushort near * CMMCSystemInfo::s_szSysWow64Path
0x140021ec6  xor     r8d, r8d; hToken
0x140021ec9  mov     cs:?s_szSystem32Path@CMMCSystemInfo@@0PAGA, ax; ushort near * CMMCSystemInfo::s_szSystem32Path
0x140021ed0  xor     ecx, ecx; hwnd
0x140021ed2  mov     [rsp+58h+pszPath], rbx; pszPath
0x140021ed7  lea     edx, [rax+25h]; csidl
0x140021eda  call    cs:__imp_SHGetFolderPathW
0x140021ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ee7  lea     rbp, WPP_GLOBAL_Control
0x140021eee  lea     r14, WPP_a5e2870eceae33db85684ba111189499_Traceguids
0x140021ef5  cmp     rcx, rbp
0x140021ef8  jz      short loc_140021F14
0x140021efa  cmp     byte ptr [rcx+19h], 4
0x140021efe  jb      short loc_140021F14
0x140021f00  mov     rcx, [rcx+10h]
0x140021f04  mov     edx, 0Ah
0x140021f09  mov     r9, rbx
0x140021f0c  mov     r8, r14
0x140021f0f  call    WPP_SF_S
0x140021f14  lea     rcx, aKernel32Dll_1; "kernel32.dll"
0x140021f1b  call    cs:__imp_GetModuleHandleW
0x140021f21  mov     rbx, rax
0x140021f24  test    rax, rax
0x140021f27  jnz     short loc_140021F6E
0x140021f29  call    cs:__imp_GetLastError
0x140021f2f  test    eax, eax
0x140021f31  jle     short loc_140021F3B
0x140021f33  movzx   eax, ax
0x140021f36  or      eax, 80070000h
0x140021f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f42  cmp     rcx, rbp
0x140021f45  jz      loc_1400220CD
0x140021f4b  cmp     byte ptr [rcx+19h], 2
0x140021f4f  jb      loc_1400220CD
0x140021f55  mov     edx, 0Bh
0x140021f5a  mov     rcx, [rcx+10h]
0x140021f5e  mov     r9d, eax
0x140021f61  mov     r8, r14
0x140021f64  call    WPP_SF_d
0x140021f69  jmp     loc_1400220CD
0x140021f6e  lea     rdx, aIswow64process; "IsWow64Process"
0x140021f75  mov     rcx, rbx; hModule
0x140021f78  call    cs:__imp_GetProcAddress
0x140021f7e  mov     rdi, rax
0x140021f81  test    rax, rax
0x140021f84  jnz     short loc_140021FB9
0x140021f86  call    cs:__imp_GetLastError
0x140021f8c  test    eax, eax
0x140021f8e  jle     short loc_140021F98
0x140021f90  movzx   eax, ax
0x140021f93  or      eax, 80070000h
0x140021f98  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f9f  cmp     rcx, rbp
0x140021fa2  jz      loc_1400220CD
0x140021fa8  cmp     byte ptr [rcx+19h], 2
0x140021fac  jb      loc_1400220CD
0x140021fb2  mov     edx, 0Ch
0x140021fb7  jmp     short loc_140021F5A
0x140021fb9  mov     [rsp+58h+arg_0], 0
0x140021fc1  call    cs:__imp_GetCurrentProcess
0x140021fc7  mov     rcx, rax
0x140021fca  lea     rdx, [rsp+58h+arg_0]
0x140021fcf  mov     rax, rdi
0x140021fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021fd7  test    eax, eax
0x140021fd9  jnz     short loc_140022011
0x140021fdb  call    cs:__imp_GetLastError
0x140021fe1  test    eax, eax
0x140021fe3  jle     short loc_140021FED
0x140021fe5  movzx   eax, ax
0x140021fe8  or      eax, 80070000h
0x140021fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ff4  cmp     rcx, rbp
0x140021ff7  jz      loc_1400220CD
0x140021ffd  cmp     byte ptr [rcx+19h], 2
0x140022001  jb      loc_1400220CD
0x140022007  mov     edx, 0Dh
0x14002200c  jmp     loc_140021F5A
0x140022011  lea     rdx, aGetsystemwow64; "GetSystemWow64DirectoryW"
0x140022018  mov     rcx, rbx; hModule
0x14002201b  call    cs:__imp_GetProcAddress
0x140022021  test    rax, rax
0x140022024  jnz     short loc_140022058
0x140022026  call    cs:__imp_GetLastError
0x14002202c  test    eax, eax
0x14002202e  jle     short loc_140022038
0x140022030  movzx   eax, ax
0x140022033  or      eax, 80070000h
0x140022038  mov     rcx, cs:WPP_GLOBAL_Control
0x14002203f  cmp     rcx, rbp
0x140022042  jz      loc_1400220CD
0x140022048  cmp     byte ptr [rcx+19h], 2
0x14002204c  jb      short loc_1400220CD
0x14002204e  mov     edx, 0Eh
0x140022053  jmp     loc_140021F5A
0x140022058  mov     edx, 200h
0x14002205d  lea     rcx, ?s_szSysWow64Path@CMMCSystemInfo@@0PAGA; ushort near * CMMCSystemInfo::s_szSysWow64Path
0x140022064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022069  mov     ebx, eax
0x14002206b  call    cs:__imp_GetLastError
0x140022071  cmp     eax, 78h ; 'x'
0x140022074  jnz     short loc_14002208D
0x140022076  mov     rcx, cs:WPP_GLOBAL_Control
0x14002207d  cmp     rcx, rbp
0x140022080  jz      short loc_1400220CD
0x140022082  cmp     byte ptr [rcx+19h], 2
0x140022086  jb      short loc_1400220CD
0x140022088  lea     edx, [rax-69h]
0x14002208b  jmp     short loc_1400220C1
0x14002208d  cmp     [rsp+58h+arg_0], 0
0x140022092  lea     eax, [rbx-1]
0x140022095  mov     cs:?s_fIsWoWCapableSystem@CMMCSystemInfo@@0_NA, 1; bool CMMCSystemInfo::s_fIsWoWCapableSystem
0x14002209c  setnz   cs:?s_fIsWoWProcess@CMMCSystemInfo@@0_NA; bool CMMCSystemInfo::s_fIsWoWProcess
0x1400220a3  cmp     eax, 1FFh
0x1400220a8  jbe     short loc_1400220CD
0x1400220aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220b1  cmp     rcx, rbp
0x1400220b4  jz      short loc_1400220CD
0x1400220b6  cmp     byte ptr [rcx+19h], 2
0x1400220ba  jb      short loc_1400220CD
0x1400220bc  mov     edx, 10h
0x1400220c1  mov     rcx, [rcx+10h]
0x1400220c5  mov     r8, r14
0x1400220c8  call    WPP_SF_
0x1400220cd  add     rsp, 38h
0x1400220d1  pop     r14
0x1400220d3  pop     rdi
0x1400220d4  pop     rbp
0x1400220d5  pop     rbx
0x1400220d6  retn
```
