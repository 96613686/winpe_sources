# LoadParserDll

- ea: `0x18001264c`
- end: `0x180012942`
- name: `LoadParserDll`
- size: `758`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180005908`
- `0x1800152d0`

## callees

- `0x18001264c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001285b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012894`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800128b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012904`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001285b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012894`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800128b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800126c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001274d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800126c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001274d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001268d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012706`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001268d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012706`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800127e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012802`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001281b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800127e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012802`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001281b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012831`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800128c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800128dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012831`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800128c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800128dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800127c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800127c4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180012729`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001276f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180012729`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001276f`

## string_xrefs

- `0x18001267b`: `ParseDllPath`
- `0x1800126f1`: `ParseDllPath`

## pseudocode

```c
BOOL __fastcall LoadParserDll(HKEY hKey)
{
  int v2; // esi
  CHAR *lpData; // r14
  CHAR *v4; // rbx
  HMODULE v5; // rdi
  DWORD v6; // eax
  CHAR *v7; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // r15
  FARPROC v10; // r12
  FARPROC v11; // r13
  BOOL result; // eax
  DWORD cbData; // [rsp+78h] [rbp+48h] BYREF
  DWORD Type; // [rsp+80h] [rbp+50h] BYREF

  Type = 0;
  cbData = 0;
  if ( RegQueryValueExA(hKey, "ParseDllPath", 0, &Type, 0, &cbData) )
    goto LABEL_20;
  v2 = 1;
  if ( Type - 1 > 1 )
    goto LABEL_20;
  lpData = (CHAR *)HeapAlloc(hHeap, 8u, cbData + 1);
  if ( !lpData )
    goto LABEL_20;
  v4 = 0;
  v5 = 0;
  if ( !RegQueryValueExA(hKey, "ParseDllPath", 0, &Type, (LPBYTE)lpData, &cbData) )
  {
    lpData[cbData] = 0;
    v6 = ExpandEnvironmentStringsA(lpData, 0, 0);
    cbData = v6;
    if ( v6 )
    {
      v7 = (CHAR *)HeapAlloc(hHeap, 8u, v6);
      v4 = v7;
      if ( v7 )
      {
        cbData = ExpandEnvironmentStringsA(lpData, v7, cbData);
        if ( cbData )
        {
          if ( qword_18004DA58 && !strcmp(v4, (const char *)qword_18004DA58) )
          {
            v2 = 0;
          }
          else
          {
            Library = LoadLibraryExA(v4, 0, 0x1000u);
            v5 = Library;
            if ( Library )
            {
              v2 = 0;
              ProcAddress = GetProcAddress(Library, "PacketFromPeer");
              v10 = GetProcAddress(v5, "PacketToPeer");
              v11 = GetProcAddress(v5, "PacketFree");
              FreeLibrary(hLibModule);
              hLibModule = v5;
              v5 = 0;
              if ( qword_18004DA58 )
                HeapFree(hHeap, 0, qword_18004DA58);
              qword_18004DA58 = v4;
              v4 = 0;
              qword_18004DAB8 = (__int64)v10;
              qword_18004DAB0 = (__int64)ProcAddress;
              qword_18004DAC0 = (__int64)v11;
            }
          }
        }
      }
    }
  }
  result = HeapFree(hHeap, 0, lpData);
  if ( v4 )
    result = HeapFree(hHeap, 0, v4);
  if ( v5 )
    result = FreeLibrary(v5);
  if ( v2 )
  {
LABEL_20:
    result = FreeLibrary(hLibModule);
    hLibModule = 0;
    if ( qword_18004DA58 )
      result = HeapFree(hHeap, 0, qword_18004DA58);
    qword_18004DA58 = 0;
    qword_18004DAB0 = 0;
    qword_18004DAB8 = 0;
    qword_18004DAC0 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001264c  mov     [rsp-38h+arg_0], rbx
0x180012651  push    rbp
0x180012652  push    rsi
0x180012653  push    rdi
0x180012654  push    r12
0x180012656  push    r13
0x180012658  push    r14
0x18001265a  push    r15
0x18001265c  mov     rbp, rsp
0x18001265f  sub     rsp, 30h
0x180012663  xor     r12d, r12d
0x180012666  lea     rax, [rbp+cbData]
0x18001266a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001266f  lea     r9, [rbp+Type]; lpType
0x180012673  xor     r8d, r8d; lpReserved
0x180012676  mov     [rsp+30h+lpData], r12; lpData
0x18001267b  lea     rdx, aParsedllpath; "ParseDllPath"
0x180012682  mov     [rbp+Type], r12d
0x180012686  mov     r15, rcx
0x180012689  mov     [rbp+cbData], r12d
0x18001268d  call    cs:__imp_RegQueryValueExA
0x180012694  nop     dword ptr [rax+rax+00h]
0x180012699  test    eax, eax
0x18001269b  jnz     loc_1800128D5
0x1800126a1  mov     eax, [rbp+Type]
0x1800126a4  lea     esi, [r12+1]
0x1800126a9  dec     eax
0x1800126ab  cmp     eax, esi
0x1800126ad  ja      loc_1800128D5
0x1800126b3  mov     r8d, [rbp+cbData]
0x1800126b7  lea     r13d, [r12+8]
0x1800126bc  mov     rcx, cs:hHeap; hHeap
0x1800126c3  inc     r8d; dwBytes
0x1800126c6  mov     edx, r13d; dwFlags
0x1800126c9  call    cs:__imp_HeapAlloc
0x1800126d0  nop     dword ptr [rax+rax+00h]
0x1800126d5  mov     r14, rax
0x1800126d8  test    rax, rax
0x1800126db  jz      loc_1800128D5
0x1800126e1  lea     rax, [rbp+cbData]
0x1800126e5  xor     r8d, r8d; lpReserved
0x1800126e8  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800126ed  lea     r9, [rbp+Type]; lpType
0x1800126f1  lea     rdx, aParsedllpath; "ParseDllPath"
0x1800126f8  mov     [rsp+30h+lpData], r14; lpData
0x1800126fd  mov     rcx, r15; hKey
0x180012700  mov     ebx, r12d
0x180012703  mov     edi, r12d
0x180012706  call    cs:__imp_RegQueryValueExA
0x18001270d  nop     dword ptr [rax+rax+00h]
0x180012712  test    eax, eax
0x180012714  jnz     loc_180012888
0x18001271a  mov     eax, [rbp+cbData]
0x18001271d  xor     r8d, r8d; nSize
0x180012720  xor     edx, edx; lpDst
0x180012722  mov     rcx, r14; lpSrc
0x180012725  mov     [rax+r14], r12b
0x180012729  call    cs:__imp_ExpandEnvironmentStringsA
0x180012730  nop     dword ptr [rax+rax+00h]
0x180012735  mov     [rbp+cbData], eax
0x180012738  test    eax, eax
0x18001273a  jz      loc_180012888
0x180012740  mov     rcx, cs:hHeap; hHeap
0x180012747  mov     edx, r13d; dwFlags
0x18001274a  mov     r8d, eax; dwBytes
0x18001274d  call    cs:__imp_HeapAlloc
0x180012754  nop     dword ptr [rax+rax+00h]
0x180012759  mov     rbx, rax
0x18001275c  test    rax, rax
0x18001275f  jz      loc_180012888
0x180012765  mov     r8d, [rbp+cbData]; nSize
0x180012769  mov     rdx, rax; lpDst
0x18001276c  mov     rcx, r14; lpSrc
0x18001276f  call    cs:__imp_ExpandEnvironmentStringsA
0x180012776  nop     dword ptr [rax+rax+00h]
0x18001277b  mov     [rbp+cbData], eax
0x18001277e  test    eax, eax
0x180012780  jz      loc_180012888
0x180012786  mov     rcx, cs:qword_18004DA58
0x18001278d  test    rcx, rcx
0x180012790  jz      short loc_1800127B9
0x180012792  mov     rax, rbx
0x180012795  sub     rcx, rbx
0x180012798  movzx   edx, byte ptr [rax]
0x18001279b  movzx   r8d, byte ptr [rax+rcx]
0x1800127a0  sub     edx, r8d
0x1800127a3  jnz     short loc_1800127AD
0x1800127a5  add     rax, rsi
0x1800127a8  test    r8d, r8d
0x1800127ab  jnz     short loc_180012798
0x1800127ad  test    edx, edx
0x1800127af  jnz     short loc_1800127B9
0x1800127b1  mov     esi, r12d
0x1800127b4  jmp     loc_180012888
0x1800127b9  xor     edx, edx; hFile
0x1800127bb  mov     r8d, 1000h; dwFlags
0x1800127c1  mov     rcx, rbx; lpLibFileName
0x1800127c4  call    cs:__imp_LoadLibraryExA
0x1800127cb  nop     dword ptr [rax+rax+00h]
0x1800127d0  mov     rdi, rax
0x1800127d3  test    rax, rax
0x1800127d6  jz      loc_180012888
0x1800127dc  lea     rdx, aPacketfrompeer; "PacketFromPeer"
0x1800127e3  mov     rcx, rax; hModule
0x1800127e6  mov     esi, r12d
0x1800127e9  call    cs:__imp_GetProcAddress
0x1800127f0  nop     dword ptr [rax+rax+00h]
0x1800127f5  lea     rdx, aPackettopeer; "PacketToPeer"
0x1800127fc  mov     rcx, rdi; hModule
0x1800127ff  mov     r15, rax
0x180012802  call    cs:__imp_GetProcAddress
0x180012809  nop     dword ptr [rax+rax+00h]
0x18001280e  lea     rdx, aPacketfree; "PacketFree"
0x180012815  mov     rcx, rdi; hModule
0x180012818  mov     r12, rax
0x18001281b  call    cs:__imp_GetProcAddress
0x180012822  nop     dword ptr [rax+rax+00h]
0x180012827  mov     rcx, cs:hLibModule; hLibModule
0x18001282e  mov     r13, rax
0x180012831  call    cs:__imp_FreeLibrary
0x180012838  nop     dword ptr [rax+rax+00h]
0x18001283d  mov     r8, cs:qword_18004DA58; lpMem
0x180012844  mov     cs:hLibModule, rdi
0x18001284b  xor     edi, edi
0x18001284d  test    r8, r8
0x180012850  jz      short loc_180012867
0x180012852  mov     rcx, cs:hHeap; hHeap
0x180012859  xor     edx, edx; dwFlags
0x18001285b  call    cs:__imp_HeapFree
0x180012862  nop     dword ptr [rax+rax+00h]
0x180012867  mov     cs:qword_18004DA58, rbx
0x18001286e  xor     ebx, ebx
0x180012870  mov     cs:qword_18004DAB8, r12
0x180012877  xor     r12d, r12d
0x18001287a  mov     cs:qword_18004DAB0, r15
0x180012881  mov     cs:qword_18004DAC0, r13
0x180012888  mov     rcx, cs:hHeap; hHeap
0x18001288f  mov     r8, r14; lpMem
0x180012892  xor     edx, edx; dwFlags
0x180012894  call    cs:__imp_HeapFree
0x18001289b  nop     dword ptr [rax+rax+00h]
0x1800128a0  test    rbx, rbx
0x1800128a3  jz      short loc_1800128BD
0x1800128a5  mov     rcx, cs:hHeap; hHeap
0x1800128ac  mov     r8, rbx; lpMem
0x1800128af  xor     edx, edx; dwFlags
0x1800128b1  call    cs:__imp_HeapFree
0x1800128b8  nop     dword ptr [rax+rax+00h]
0x1800128bd  test    rdi, rdi
0x1800128c0  jz      short loc_1800128D1
0x1800128c2  mov     rcx, rdi; hLibModule
0x1800128c5  call    cs:__imp_FreeLibrary
0x1800128cc  nop     dword ptr [rax+rax+00h]
0x1800128d1  test    esi, esi
0x1800128d3  jz      short loc_18001292C
0x1800128d5  mov     rcx, cs:hLibModule; hLibModule
0x1800128dc  call    cs:__imp_FreeLibrary
0x1800128e3  nop     dword ptr [rax+rax+00h]
0x1800128e8  mov     r8, cs:qword_18004DA58; lpMem
0x1800128ef  mov     cs:hLibModule, r12
0x1800128f6  test    r8, r8
0x1800128f9  jz      short loc_180012910
0x1800128fb  mov     rcx, cs:hHeap; hHeap
0x180012902  xor     edx, edx; dwFlags
0x180012904  call    cs:__imp_HeapFree
0x18001290b  nop     dword ptr [rax+rax+00h]
0x180012910  mov     cs:qword_18004DA58, r12
0x180012917  mov     cs:qword_18004DAB0, r12
0x18001291e  mov     cs:qword_18004DAB8, r12
0x180012925  mov     cs:qword_18004DAC0, r12
0x18001292c  mov     rbx, [rsp+30h+arg_0]
0x180012931  add     rsp, 30h
0x180012935  pop     r15
0x180012937  pop     r14
0x180012939  pop     r13
0x18001293b  pop     r12
0x18001293d  pop     rdi
0x18001293e  pop     rsi
0x18001293f  pop     rbp
0x180012940  retn
```
