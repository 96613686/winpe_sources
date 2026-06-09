# CreateHistoryFile(void)

- ea: `0x140043024`
- end: `0x140043314`
- name: `?CreateHistoryFile@@YAJXZ`
- size: `752`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140043a14`

## callees

- `0x1400070b0`
- `0x140020220`
- `0x140020420`
- `0x1400210f0`
- `0x140043024`
- `0x140043698`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004324d`
- `KERNEL32!GetLastError` at `0x14004324d`
- `KERNEL32!HeapAlloc` at `0x140043075`
- `KERNEL32!HeapAlloc` at `0x1400431c2`
- `KERNEL32!HeapAlloc` at `0x140043075`
- `KERNEL32!HeapAlloc` at `0x1400431c2`
- `KERNEL32!HeapFree` at `0x1400432cb`
- `KERNEL32!HeapFree` at `0x1400432f0`
- `KERNEL32!HeapFree` at `0x1400432cb`
- `KERNEL32!HeapFree` at `0x1400432f0`
- `KERNEL32!GetProcessHeap` at `0x14004305e`
- `KERNEL32!GetProcessHeap` at `0x1400431ab`
- `KERNEL32!GetProcessHeap` at `0x1400432b7`
- `KERNEL32!GetProcessHeap` at `0x1400432dc`
- `KERNEL32!GetProcessHeap` at `0x14004305e`
- `KERNEL32!GetProcessHeap` at `0x1400431ab`
- `KERNEL32!GetProcessHeap` at `0x1400432b7`
- `KERNEL32!GetProcessHeap` at `0x1400432dc`
- `KERNEL32!CopyFileW` at `0x140043239`
- `KERNEL32!CopyFileW` at `0x140043239`
- `OLEAUT32!__imp_VariantInit` at `0x140043052`
- `OLEAUT32!__imp_VariantInit` at `0x140043052`
- `OLEAUT32!__imp_VariantClear` at `0x140043292`
- `OLEAUT32!__imp_VariantClear` at `0x140043292`

## string_xrefs

- `0x140043108`: `results.xml`
- `0x1400430bf`: `CreateHistoryFile`
- `0x140043276`: `CreateHistoryFile`

## pseudocode

```c
__int64 CreateHistoryFile(void)
{
  struct IXMLDOMDocument2 *v0; // rdi
  unsigned __int16 *v1; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // r14
  signed int v4; // ebx
  int v5; // eax
  int HistoryXml; // eax
  int v7; // eax
  int v8; // eax
  HRESULT (__stdcall *save)(IXMLDOMDocument2 *, VARIANT); // rax
  int v10; // eax
  HANDLE v11; // rax
  int v12; // eax
  signed int LastError; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v18; // [rsp+50h] [rbp-20h] BYREF
  struct IXMLDOMDocument2 *v19; // [rsp+90h] [rbp+20h] BYREF

  v0 = 0;
  v19 = 0;
  v1 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( v3 )
  {
    v5 = DwzXmlCreate((OLECHAR *)L"<DiagnosticResults />", (LPVOID *)&v19);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v0 = v19;
      HistoryXml = LoadHistoryXml(v19);
      v4 = HistoryXml;
      if ( HistoryXml >= 0 )
      {
        v7 = StringCchPrintfW(v3, 0x104u, L"%s\\%s", g_HistoryDirectory, L"results.xml");
        v4 = v7;
        if ( v7 >= 0 )
        {
          v8 = AssignVariantString(&pvarg, v3);
          v4 = v8;
          if ( v8 >= 0 )
          {
            save = v0->lpVtbl->save;
            v18 = pvarg;
            v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))save)(v0, &v18);
            v4 = v10;
            if ( v10 >= 0 )
            {
              if ( *((_DWORD *)Config + 3) )
              {
                v11 = GetProcessHeap();
                v1 = (unsigned __int16 *)HeapAlloc(v11, 0, 0x208u);
                if ( v1 )
                {
                  v12 = StringCchPrintfW(v1, 0x104u, L"%s\\%s", g_HistoryDirectory, L"results.cab");
                  v4 = v12;
                  if ( v12 >= 0 )
                  {
                    if ( CopyFileW(*((LPCWSTR *)Config + 18), v1, 0) )
                    {
                      v4 = 0;
                    }
                    else
                    {
                      LastError = GetLastError();
                      v4 = LastError;
                      if ( LastError > 0 )
                        v4 = (unsigned __int16)LastError | 0x80070000;
                      if ( v4 < 0 )
                        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 398, v4);
                    }
                  }
                  else
                  {
                    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 395, v12);
                  }
                }
                else
                {
                  v4 = -2147024882;
                  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 387, -2147024882);
                }
              }
            }
            else
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 381, v10);
            }
          }
          else
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 375, v8);
          }
        }
        else
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 372, v7);
        }
      }
      else
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 364, HistoryXml);
      }
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 358, v5);
      v0 = v19;
    }
  }
  else
  {
    v4 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateHistoryFile", 355, -2147024882);
  }
  VariantClear(&pvarg);
  if ( v0 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v0->lpVtbl->Release)(v0);
  if ( v3 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v3);
  }
  if ( v1 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v1);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140043024  mov     [rsp-18h+arg_8], rbx
0x140043029  mov     [rsp-18h+arg_10], rsi
0x14004302e  push    rbp
0x14004302f  push    rdi
0x140043030  push    r14
0x140043032  mov     rbp, rsp
0x140043035  sub     rsp, 70h
0x140043039  xorps   xmm0, xmm0
0x14004303c  lea     rcx, [rbp+pvarg]; pvarg
0x140043040  xor     eax, eax
0x140043042  xor     edi, edi
0x140043044  mov     [rbp+arg_0], rdi
0x140043048  xor     esi, esi
0x14004304a  movups  xmmword ptr [rbp+pvarg], xmm0
0x14004304e  mov     qword ptr [rbp+pvarg+10h], rax
0x140043052  call    cs:__imp_VariantInit
0x140043059  nop     dword ptr [rax+rax+00h]
0x14004305e  call    cs:__imp_GetProcessHeap
0x140043065  nop     dword ptr [rax+rax+00h]
0x14004306a  xor     edx, edx; dwFlags
0x14004306c  mov     r8d, 208h; dwBytes
0x140043072  mov     rcx, rax; hHeap
0x140043075  call    cs:__imp_HeapAlloc
0x14004307c  nop     dword ptr [rax+rax+00h]
0x140043081  mov     r14, rax
0x140043084  test    rax, rax
0x140043087  jnz     short loc_14004309F
0x140043089  mov     eax, 8007000Eh
0x14004308e  mov     r9d, 163h
0x140043094  mov     ebx, eax
0x140043096  mov     dword ptr [rsp+70h+var_50], eax
0x14004309a  jmp     loc_140043276
0x14004309f  lea     rdx, [rbp+arg_0]; struct IXMLDOMDocument2 **
0x1400430a3  lea     rcx, aDiagnosticresu; "<DiagnosticResults />"
0x1400430aa  call    ?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1400430af  mov     ebx, eax
0x1400430b1  test    eax, eax
0x1400430b3  jns     short loc_1400430E0
0x1400430b5  mov     r9d, 166h
0x1400430bb  mov     dword ptr [rsp+70h+var_50], eax
0x1400430bf  lea     r8, aCreatehistoryf; "CreateHistoryFile"
0x1400430c6  mov     ecx, 1; Level
0x1400430cb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400430d2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400430d7  mov     rdi, [rbp+arg_0]
0x1400430db  jmp     loc_14004328E
0x1400430e0  mov     rdi, [rbp+arg_0]
0x1400430e4  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x1400430e7  call    ?LoadHistoryXml@@YAJPEAUIXMLDOMDocument2@@@Z; LoadHistoryXml(IXMLDOMDocument2 *)
0x1400430ec  mov     ebx, eax
0x1400430ee  test    eax, eax
0x1400430f0  jns     short loc_140043101
0x1400430f2  mov     dword ptr [rsp+70h+var_50], eax
0x1400430f6  mov     r9d, 16Ch
0x1400430fc  jmp     loc_140043276
0x140043101  mov     r9, cs:?g_HistoryDirectory@@3PEAGEA; ushort * g_HistoryDirectory
0x140043108  lea     rax, aResultsXml; "results.xml"
0x14004310f  lea     r8, aSS_1; "%s\\%s"
0x140043116  mov     [rsp+70h+var_50], rax
0x14004311b  mov     edx, 104h; unsigned __int64
0x140043120  mov     rcx, r14; unsigned __int16 *
0x140043123  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140043128  mov     ebx, eax
0x14004312a  test    eax, eax
0x14004312c  jns     short loc_14004313D
0x14004312e  mov     dword ptr [rsp+70h+var_50], eax
0x140043132  mov     r9d, 174h
0x140043138  jmp     loc_140043276
0x14004313d  mov     rdx, r14; unsigned __int16 *
0x140043140  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x140043144  call    ?AssignVariantString@@YAJPEAUtagVARIANT@@PEBG@Z; AssignVariantString(tagVARIANT *,ushort const *)
0x140043149  mov     ebx, eax
0x14004314b  test    eax, eax
0x14004314d  jns     short loc_14004315E
0x14004314f  mov     dword ptr [rsp+70h+var_50], eax
0x140043153  mov     r9d, 177h
0x140043159  jmp     loc_140043276
0x14004315e  mov     rax, [rdi]
0x140043161  lea     rdx, [rbp+var_20]
0x140043165  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140043169  mov     rcx, rdi
0x14004316c  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140043171  mov     rax, [rax+210h]
0x140043178  movaps  [rbp+var_20], xmm0
0x14004317c  movsd   [rbp+var_10], xmm1
0x140043181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043186  mov     ebx, eax
0x140043188  test    eax, eax
0x14004318a  jns     short loc_14004319B
0x14004318c  mov     dword ptr [rsp+70h+var_50], eax
0x140043190  mov     r9d, 17Dh
0x140043196  jmp     loc_140043276
0x14004319b  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400431a2  cmp     [rax+0Ch], esi
0x1400431a5  jz      loc_14004328E
0x1400431ab  call    cs:__imp_GetProcessHeap
0x1400431b2  nop     dword ptr [rax+rax+00h]
0x1400431b7  xor     edx, edx; dwFlags
0x1400431b9  mov     r8d, 208h; dwBytes
0x1400431bf  mov     rcx, rax; hHeap
0x1400431c2  call    cs:__imp_HeapAlloc
0x1400431c9  nop     dword ptr [rax+rax+00h]
0x1400431ce  mov     rsi, rax
0x1400431d1  test    rax, rax
0x1400431d4  jnz     short loc_1400431EC
0x1400431d6  mov     eax, 8007000Eh
0x1400431db  mov     r9d, 183h
0x1400431e1  mov     ebx, eax
0x1400431e3  mov     dword ptr [rsp+70h+var_50], eax
0x1400431e7  jmp     loc_140043276
0x1400431ec  mov     r9, cs:?g_HistoryDirectory@@3PEAGEA; ushort * g_HistoryDirectory
0x1400431f3  lea     rax, aResultsCab; "results.cab"
0x1400431fa  lea     r8, aSS_1; "%s\\%s"
0x140043201  mov     [rsp+70h+var_50], rax
0x140043206  mov     edx, 104h; unsigned __int64
0x14004320b  mov     rcx, rsi; unsigned __int16 *
0x14004320e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140043213  mov     ebx, eax
0x140043215  test    eax, eax
0x140043217  jns     short loc_140043225
0x140043219  mov     dword ptr [rsp+70h+var_50], eax
0x14004321d  mov     r9d, 18Bh
0x140043223  jmp     short loc_140043276
0x140043225  mov     rcx, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14004322c  xor     r8d, r8d; bFailIfExists
0x14004322f  mov     rdx, rsi; lpNewFileName
0x140043232  mov     rcx, [rcx+90h]; lpExistingFileName
0x140043239  call    cs:__imp_CopyFileW
0x140043240  nop     dword ptr [rax+rax+00h]
0x140043245  test    eax, eax
0x140043247  jz      short loc_14004324D
0x140043249  xor     ebx, ebx
0x14004324b  jmp     short loc_14004328E
0x14004324d  call    cs:__imp_GetLastError
0x140043254  nop     dword ptr [rax+rax+00h]
0x140043259  mov     ebx, eax
0x14004325b  test    eax, eax
0x14004325d  jle     short loc_140043268
0x14004325f  movzx   ebx, ax
0x140043262  or      ebx, 80070000h
0x140043268  test    ebx, ebx
0x14004326a  jns     short loc_14004328E
0x14004326c  mov     dword ptr [rsp+70h+var_50], ebx
0x140043270  mov     r9d, 18Eh
0x140043276  lea     r8, aCreatehistoryf; "CreateHistoryFile"
0x14004327d  mov     ecx, 1; Level
0x140043282  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140043289  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004328e  lea     rcx, [rbp+pvarg]; pvarg
0x140043292  call    cs:__imp_VariantClear
0x140043299  nop     dword ptr [rax+rax+00h]
0x14004329e  test    rdi, rdi
0x1400432a1  jz      short loc_1400432B2
0x1400432a3  mov     rax, [rdi]
0x1400432a6  mov     rcx, rdi
0x1400432a9  mov     rax, [rax+10h]
0x1400432ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400432b2  test    r14, r14
0x1400432b5  jz      short loc_1400432D7
0x1400432b7  call    cs:__imp_GetProcessHeap
0x1400432be  nop     dword ptr [rax+rax+00h]
0x1400432c3  mov     r8, r14; lpMem
0x1400432c6  xor     edx, edx; dwFlags
0x1400432c8  mov     rcx, rax; hHeap
0x1400432cb  call    cs:__imp_HeapFree
0x1400432d2  nop     dword ptr [rax+rax+00h]
0x1400432d7  test    rsi, rsi
0x1400432da  jz      short loc_1400432FC
0x1400432dc  call    cs:__imp_GetProcessHeap
0x1400432e3  nop     dword ptr [rax+rax+00h]
0x1400432e8  mov     r8, rsi; lpMem
0x1400432eb  xor     edx, edx; dwFlags
0x1400432ed  mov     rcx, rax; hHeap
0x1400432f0  call    cs:__imp_HeapFree
0x1400432f7  nop     dword ptr [rax+rax+00h]
0x1400432fc  lea     r11, [rsp+70h+var_s0]
0x140043301  mov     eax, ebx
0x140043303  mov     rbx, [r11+28h]
0x140043307  mov     rsi, [r11+30h]
0x14004330b  mov     rsp, r11
0x14004330e  pop     r14
0x140043310  pop     rdi
0x140043311  pop     rbp
0x140043312  retn
```
