# LoadParserDll

- ea: `0x180012024`
- end: `0x1800122b3`
- name: `LoadParserDll`
- size: `655`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180005704`
- `0x180014bb0`

## callees

- `0x180012024`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001223b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001227c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001223b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001227c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001209b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001210d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001209b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001210d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012065`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800120d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180012065`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800120d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012197`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800121aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800121bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012197`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800121aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800121bd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800121cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012249`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001225a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800121cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012249`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001225a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180012178`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180012178`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800120ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180012129`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800120ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180012129`

## string_xrefs

- `0x180012053`: `ParseDllPath`
- `0x1800120bd`: `ParseDllPath`

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
          if ( qword_18004CA58 && !strcmp(v4, (const char *)qword_18004CA58) )
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
              if ( qword_18004CA58 )
                HeapFree(hHeap, 0, qword_18004CA58);
              qword_18004CA58 = v4;
              v4 = 0;
              qword_18004CAB8 = (__int64)v10;
              qword_18004CAB0 = (__int64)ProcAddress;
              qword_18004CAC0 = (__int64)v11;
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
    if ( qword_18004CA58 )
      result = HeapFree(hHeap, 0, qword_18004CA58);
    qword_18004CA58 = 0;
    qword_18004CAB0 = 0;
    qword_18004CAB8 = 0;
    qword_18004CAC0 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180012024  mov     [rsp-38h+arg_0], rbx
0x180012029  push    rbp
0x18001202a  push    rsi
0x18001202b  push    rdi
0x18001202c  push    r12
0x18001202e  push    r13
0x180012030  push    r14
0x180012032  push    r15
0x180012034  mov     rbp, rsp
0x180012037  sub     rsp, 30h
0x18001203b  xor     r12d, r12d
0x18001203e  lea     rax, [rbp+cbData]
0x180012042  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180012047  lea     r9, [rbp+Type]; lpType
0x18001204b  xor     r8d, r8d; lpReserved
0x18001204e  mov     [rsp+30h+lpData], r12; lpData
0x180012053  lea     rdx, aParsedllpath; "ParseDllPath"
0x18001205a  mov     [rbp+Type], r12d
0x18001205e  mov     r15, rcx
0x180012061  mov     [rbp+cbData], r12d
0x180012065  call    cs:__imp_RegQueryValueExA
0x18001206b  test    eax, eax
0x18001206d  jnz     loc_180012253
0x180012073  mov     eax, [rbp+Type]
0x180012076  lea     esi, [r12+1]
0x18001207b  dec     eax
0x18001207d  cmp     eax, esi
0x18001207f  ja      loc_180012253
0x180012085  mov     r8d, [rbp+cbData]
0x180012089  lea     r13d, [r12+8]
0x18001208e  mov     rcx, cs:hHeap; hHeap
0x180012095  inc     r8d; dwBytes
0x180012098  mov     edx, r13d; dwFlags
0x18001209b  call    cs:__imp_HeapAlloc
0x1800120a1  mov     r14, rax
0x1800120a4  test    rax, rax
0x1800120a7  jz      loc_180012253
0x1800120ad  lea     rax, [rbp+cbData]
0x1800120b1  xor     r8d, r8d; lpReserved
0x1800120b4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800120b9  lea     r9, [rbp+Type]; lpType
0x1800120bd  lea     rdx, aParsedllpath; "ParseDllPath"
0x1800120c4  mov     [rsp+30h+lpData], r14; lpData
0x1800120c9  mov     rcx, r15; hKey
0x1800120cc  mov     ebx, r12d
0x1800120cf  mov     edi, r12d
0x1800120d2  call    cs:__imp_RegQueryValueExA
0x1800120d8  test    eax, eax
0x1800120da  jnz     loc_180012218
0x1800120e0  mov     eax, [rbp+cbData]
0x1800120e3  xor     r8d, r8d; nSize
0x1800120e6  xor     edx, edx; lpDst
0x1800120e8  mov     rcx, r14; lpSrc
0x1800120eb  mov     [rax+r14], r12b
0x1800120ef  call    cs:__imp_ExpandEnvironmentStringsA
0x1800120f5  mov     [rbp+cbData], eax
0x1800120f8  test    eax, eax
0x1800120fa  jz      loc_180012218
0x180012100  mov     rcx, cs:hHeap; hHeap
0x180012107  mov     edx, r13d; dwFlags
0x18001210a  mov     r8d, eax; dwBytes
0x18001210d  call    cs:__imp_HeapAlloc
0x180012113  mov     rbx, rax
0x180012116  test    rax, rax
0x180012119  jz      loc_180012218
0x18001211f  mov     r8d, [rbp+cbData]; nSize
0x180012123  mov     rdx, rax; lpDst
0x180012126  mov     rcx, r14; lpSrc
0x180012129  call    cs:__imp_ExpandEnvironmentStringsA
0x18001212f  mov     [rbp+cbData], eax
0x180012132  test    eax, eax
0x180012134  jz      loc_180012218
0x18001213a  mov     rcx, cs:qword_18004CA58
0x180012141  test    rcx, rcx
0x180012144  jz      short loc_18001216D
0x180012146  mov     rax, rbx
0x180012149  sub     rcx, rbx
0x18001214c  movzx   edx, byte ptr [rax]
0x18001214f  movzx   r8d, byte ptr [rax+rcx]
0x180012154  sub     edx, r8d
0x180012157  jnz     short loc_180012161
0x180012159  add     rax, rsi
0x18001215c  test    r8d, r8d
0x18001215f  jnz     short loc_18001214C
0x180012161  test    edx, edx
0x180012163  jnz     short loc_18001216D
0x180012165  mov     esi, r12d
0x180012168  jmp     loc_180012218
0x18001216d  xor     edx, edx; hFile
0x18001216f  mov     r8d, 1000h; dwFlags
0x180012175  mov     rcx, rbx; lpLibFileName
0x180012178  call    cs:__imp_LoadLibraryExA
0x18001217e  mov     rdi, rax
0x180012181  test    rax, rax
0x180012184  jz      loc_180012218
0x18001218a  lea     rdx, aPacketfrompeer; "PacketFromPeer"
0x180012191  mov     rcx, rax; hModule
0x180012194  mov     esi, r12d
0x180012197  call    cs:__imp_GetProcAddress
0x18001219d  lea     rdx, aPackettopeer; "PacketToPeer"
0x1800121a4  mov     rcx, rdi; hModule
0x1800121a7  mov     r15, rax
0x1800121aa  call    cs:__imp_GetProcAddress
0x1800121b0  lea     rdx, aPacketfree; "PacketFree"
0x1800121b7  mov     rcx, rdi; hModule
0x1800121ba  mov     r12, rax
0x1800121bd  call    cs:__imp_GetProcAddress
0x1800121c3  mov     rcx, cs:hLibModule; hLibModule
0x1800121ca  mov     r13, rax
0x1800121cd  call    cs:__imp_FreeLibrary
0x1800121d3  mov     r8, cs:qword_18004CA58; lpMem
0x1800121da  mov     cs:hLibModule, rdi
0x1800121e1  xor     edi, edi
0x1800121e3  test    r8, r8
0x1800121e6  jz      short loc_1800121F7
0x1800121e8  mov     rcx, cs:hHeap; hHeap
0x1800121ef  xor     edx, edx; dwFlags
0x1800121f1  call    cs:__imp_HeapFree
0x1800121f7  mov     cs:qword_18004CA58, rbx
0x1800121fe  xor     ebx, ebx
0x180012200  mov     cs:qword_18004CAB8, r12
0x180012207  xor     r12d, r12d
0x18001220a  mov     cs:qword_18004CAB0, r15
0x180012211  mov     cs:qword_18004CAC0, r13
0x180012218  mov     rcx, cs:hHeap; hHeap
0x18001221f  mov     r8, r14; lpMem
0x180012222  xor     edx, edx; dwFlags
0x180012224  call    cs:__imp_HeapFree
0x18001222a  test    rbx, rbx
0x18001222d  jz      short loc_180012241
0x18001222f  mov     rcx, cs:hHeap; hHeap
0x180012236  mov     r8, rbx; lpMem
0x180012239  xor     edx, edx; dwFlags
0x18001223b  call    cs:__imp_HeapFree
0x180012241  test    rdi, rdi
0x180012244  jz      short loc_18001224F
0x180012246  mov     rcx, rdi; hLibModule
0x180012249  call    cs:__imp_FreeLibrary
0x18001224f  test    esi, esi
0x180012251  jz      short loc_18001229E
0x180012253  mov     rcx, cs:hLibModule; hLibModule
0x18001225a  call    cs:__imp_FreeLibrary
0x180012260  mov     r8, cs:qword_18004CA58; lpMem
0x180012267  mov     cs:hLibModule, r12
0x18001226e  test    r8, r8
0x180012271  jz      short loc_180012282
0x180012273  mov     rcx, cs:hHeap; hHeap
0x18001227a  xor     edx, edx; dwFlags
0x18001227c  call    cs:__imp_HeapFree
0x180012282  mov     cs:qword_18004CA58, r12
0x180012289  mov     cs:qword_18004CAB0, r12
0x180012290  mov     cs:qword_18004CAB8, r12
0x180012297  mov     cs:qword_18004CAC0, r12
0x18001229e  mov     rbx, [rsp+30h+arg_0]
0x1800122a3  add     rsp, 30h
0x1800122a7  pop     r15
0x1800122a9  pop     r14
0x1800122ab  pop     r13
0x1800122ad  pop     r12
0x1800122af  pop     rdi
0x1800122b0  pop     rsi
0x1800122b1  pop     rbp
0x1800122b2  retn
```
