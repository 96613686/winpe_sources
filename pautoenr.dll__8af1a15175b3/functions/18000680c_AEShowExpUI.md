# AEShowExpUI

- ea: `0x18000680c`
- end: `0x18000696e`
- name: `AEShowExpUI`
- size: `354`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006974`

## callees

- `0x18000680c`
- `0x18000765c`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000684b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006933`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000684b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006933`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006955`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006955`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006831`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006877`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006831`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006877`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006860`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006860`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006947`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006947`
- `USER32!GetDesktopWindow` at `0x180006903`
- `USER32!GetDesktopWindow` at `0x180006903`

## pseudocode

```c
__int64 __fastcall AEShowExpUI(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  WCHAR *v9; // rbx
  HMODULE Library; // rsi
  UINT SystemDirectoryW; // eax
  UINT v12; // edi
  unsigned int v13; // edi
  WCHAR *v14; // rax
  UINT v15; // eax
  __int64 v16; // rdx
  FARPROC ProcAddress; // rbp
  HWND DesktopWindow; // rax
  signed int v19; // eax

  v9 = 0;
  Library = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v12 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    goto LABEL_14;
  if ( SystemDirectoryW <= 0x104 )
  {
    v14 = (WCHAR *)LocalAlloc(0, 2LL * (SystemDirectoryW + 12));
    v9 = v14;
    if ( v14 )
    {
      v15 = GetSystemDirectoryW(v14, v12);
      v16 = v15;
      if ( v15 )
      {
        if ( v15 >= v12 )
        {
          SetLastError(0xDu);
          v13 = 0;
LABEL_15:
          LocalFree(v9);
          goto LABEL_16;
        }
        v13 = 1;
        if ( v9[v15 - 1] != 92 )
        {
          v9[v15] = 92;
          v16 = v15 + 1;
        }
        *(_OWORD *)&v9[v16] = xmmword_18000B368;
        *(_QWORD *)&v9[v16 + 8] = 0x6C006C0064LL;
        Library = (HMODULE)IsolationAwareLoadLibraryExW(v9);
        LocalFree(v9);
        v9 = 0;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "CryptUIViewExpiringCerts");
          if ( ProcAddress )
          {
            DesktopWindow = GetDesktopWindow();
            v19 = ((__int64 (__fastcall *)(HWND, __int64, __int64, __int64, __int64, int))ProcAddress)(
                    DesktopWindow,
                    a1,
                    a2,
                    a3,
                    a4,
                    a5);
            if ( v19 >= 0 )
              goto LABEL_17;
            SetLastError(v19);
            v13 = 0;
LABEL_16:
            if ( !Library )
              return v13;
LABEL_17:
            FreeLibrary(Library);
            return v13;
          }
        }
      }
    }
LABEL_14:
    v13 = 0;
    if ( !v9 )
      goto LABEL_16;
    goto LABEL_15;
  }
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x18000680c  push    rbx
0x18000680e  push    rbp
0x18000680f  push    rsi
0x180006810  push    rdi
0x180006811  push    r12
0x180006813  push    r13
0x180006815  push    r14
0x180006817  push    r15
0x180006819  sub     rsp, 48h
0x18000681d  mov     r12, rdx
0x180006820  mov     r13, rcx
0x180006823  xor     edx, edx; uSize
0x180006825  xor     ecx, ecx; lpBuffer
0x180006827  mov     r14, r9
0x18000682a  mov     r15, r8
0x18000682d  xor     ebx, ebx
0x18000682f  xor     esi, esi
0x180006831  call    cs:__imp_GetSystemDirectoryW
0x180006837  mov     edi, eax
0x180006839  test    eax, eax
0x18000683b  jz      loc_18000693D
0x180006841  cmp     eax, 104h
0x180006846  jbe     short loc_180006858
0x180006848  lea     ecx, [rbx+0Dh]; dwErrCode
0x18000684b  call    cs:__imp_SetLastError
0x180006851  xor     edi, edi
0x180006853  jmp     loc_18000695B
0x180006858  lea     edx, [rax+0Ch]
0x18000685b  xor     ecx, ecx; uFlags
0x18000685d  add     rdx, rdx; uBytes
0x180006860  call    cs:__imp_LocalAlloc
0x180006866  mov     rbx, rax
0x180006869  test    rax, rax
0x18000686c  jz      loc_18000693D
0x180006872  mov     edx, edi; uSize
0x180006874  mov     rcx, rax; lpBuffer
0x180006877  call    cs:__imp_GetSystemDirectoryW
0x18000687d  mov     edx, eax
0x18000687f  test    eax, eax
0x180006881  jz      loc_18000693D
0x180006887  cmp     edx, edi
0x180006889  jb      short loc_18000689D
0x18000688b  mov     ecx, 0Dh; dwErrCode
0x180006890  call    cs:__imp_SetLastError
0x180006896  xor     edi, edi
0x180006898  jmp     loc_180006944
0x18000689d  mov     edi, 1
0x1800068a2  lea     eax, [rdx-1]
0x1800068a5  lea     r8d, [rdi+5Bh]
0x1800068a9  cmp     [rbx+rax*2], r8w
0x1800068ae  jz      short loc_1800068B7
0x1800068b0  mov     [rbx+rdx*2], r8w
0x1800068b5  add     edx, edi
0x1800068b7  movups  xmm0, cs:xmmword_18000B368
0x1800068be  mov     rcx, rbx; lpLibFileName
0x1800068c1  movups  xmmword ptr [rbx+rdx*2], xmm0
0x1800068c5  movsd   xmm1, cs:qword_18000B378
0x1800068cd  movsd   qword ptr [rbx+rdx*2+10h], xmm1
0x1800068d3  call    IsolationAwareLoadLibraryExW
0x1800068d8  mov     rcx, rbx; hMem
0x1800068db  mov     rsi, rax
0x1800068de  call    cs:__imp_LocalFree
0x1800068e4  xor     ebx, ebx
0x1800068e6  test    rsi, rsi
0x1800068e9  jz      short loc_18000693D
0x1800068eb  lea     rdx, ProcName; "CryptUIViewExpiringCerts"
0x1800068f2  mov     rcx, rsi; hModule
0x1800068f5  call    cs:__imp_GetProcAddress
0x1800068fb  mov     rbp, rax
0x1800068fe  test    rax, rax
0x180006901  jz      short loc_18000693D
0x180006903  call    cs:__imp_GetDesktopWindow
0x180006909  mov     edx, [rsp+88h+arg_20]
0x180006910  mov     r9, r15
0x180006913  mov     [rsp+88h+var_60], edx
0x180006917  mov     rcx, rax
0x18000691a  mov     rdx, r13
0x18000691d  mov     [rsp+88h+var_68], r14
0x180006922  mov     rax, rbp
0x180006925  mov     r8, r12
0x180006928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000692d  test    eax, eax
0x18000692f  jns     short loc_180006952
0x180006931  mov     ecx, eax; dwErrCode
0x180006933  call    cs:__imp_SetLastError
0x180006939  xor     edi, edi
0x18000693b  jmp     short loc_18000694D
0x18000693d  xor     edi, edi
0x18000693f  test    rbx, rbx
0x180006942  jz      short loc_18000694D
0x180006944  mov     rcx, rbx; hMem
0x180006947  call    cs:__imp_LocalFree
0x18000694d  test    rsi, rsi
0x180006950  jz      short loc_18000695B
0x180006952  mov     rcx, rsi; hLibModule
0x180006955  call    cs:__imp_FreeLibrary
0x18000695b  mov     eax, edi
0x18000695d  add     rsp, 48h
0x180006961  pop     r15
0x180006963  pop     r14
0x180006965  pop     r13
0x180006967  pop     r12
0x180006969  pop     rdi
0x18000696a  pop     rsi
0x18000696b  pop     rbp
0x18000696c  pop     rbx
0x18000696d  retn
```
