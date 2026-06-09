# DwCustomDialDlg

- ea: `0x180026618`
- end: `0x180026859`
- name: `DwCustomDialDlg`
- size: `577`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, __int64, __int64, int, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e360`

## callees

- `0x180026618`
- `0x18002699c`
- `0x18003c928`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800266ff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002670d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800266ff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002670d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800266f1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800266f1`
- `RASAPI32!DwGetEntryMode` at `0x180026764`
- `RASAPI32!DwGetEntryMode` at `0x180026764`
- `RASAPI32!DwGetCustomDllEntryPoint` at `0x1800266d3`
- `RASAPI32!DwGetCustomDllEntryPoint` at `0x1800266d3`
- `RASAPI32!ClosePhonebookFile` at `0x180026798`
- `RASAPI32!ClosePhonebookFile` at `0x180026798`
- `rtutils!TracePrintfExA` at `0x180026685`
- `rtutils!TracePrintfExA` at `0x18002672d`
- `rtutils!TracePrintfExA` at `0x180026839`
- `rtutils!TracePrintfExA` at `0x180026685`
- `rtutils!TracePrintfExA` at `0x18002672d`
- `rtutils!TracePrintfExA` at `0x180026839`

## pseudocode

```c
__int64 __fastcall DwCustomDialDlg(
        const WCHAR *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8)
{
  void *v11; // r12
  void *v12; // r14
  unsigned int CustomDllEntryPoint; // eax
  unsigned int v14; // ebx
  const WCHAR *v16; // rcx
  unsigned int v17; // r13d
  __int64 v18; // rax
  int v19; // eax
  _DWORD *v20; // rsi
  unsigned int v21; // eax
  int v22; // [rsp+40h] [rbp-49h] BYREF
  HMODULE hLibModule; // [rsp+48h] [rbp-41h] BYREF
  __int64 (__fastcall *v24)(HMODULE, _QWORD, const WCHAR *, const WCHAR *, __int64, __int64, __int64); // [rsp+50h] [rbp-39h] BYREF
  LPCWCH lpWideCharStr[2]; // [rsp+58h] [rbp-31h] BYREF
  __int128 v26; // [rsp+68h] [rbp-21h]
  __int128 v27; // [rsp+78h] [rbp-11h]
  __int64 v28; // [rsp+88h] [rbp-1h]
  int v29; // [rsp+D8h] [rbp+4Fh] BYREF
  __int64 v30; // [rsp+E0h] [rbp+57h]

  v30 = a3;
  hLibModule = 0;
  v29 = 0;
  v24 = 0;
  v28 = 0;
  v11 = 0;
  v22 = 0;
  v12 = 0;
  *(_OWORD *)lpWideCharStr = 0;
  v26 = 0;
  v27 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomDialDlg..");
  if ( !a2 || !*a2 )
    goto LABEL_11;
  CustomDllEntryPoint = DwInitializeCustomDlg();
  if ( CustomDllEntryPoint )
  {
LABEL_6:
    *(_DWORD *)(a4 + 28) = CustomDllEntryPoint;
LABEL_7:
    *a6 = 0;
LABEL_8:
    v14 = 0;
    goto LABEL_12;
  }
  CustomDllEntryPoint = DwGetCustomDllEntryPoint(a1, a2, &v29, &v24, &hLibModule, 0, a8);
  if ( CustomDllEntryPoint )
  {
    if ( v29 )
      goto LABEL_6;
    goto LABEL_11;
  }
  if ( !v29 )
  {
LABEL_11:
    v14 = -2147467262;
    goto LABEL_12;
  }
  CustomDllEntryPoint = DwGetEntryMode(a1, a2, lpWideCharStr, &v22);
  v14 = CustomDllEntryPoint;
  if ( CustomDllEntryPoint )
    goto LABEL_6;
  v16 = a1;
  v17 = a5 | v22;
  if ( !a1 )
    v16 = lpWideCharStr[0];
  v11 = (void *)StrDupAFromTInternal(v16);
  if ( !a1 )
    ClosePhonebookFile(lpWideCharStr);
  v18 = StrDupAFromTInternal(a2);
  v12 = (void *)v18;
  if ( !v11 || !v18 )
  {
    *(_DWORD *)(a4 + 28) = 8;
    goto LABEL_7;
  }
  v19 = v24(hLibModule, v17, a1, a2, v30, a4, a7);
  v20 = a6;
  *a6 = v19;
  if ( v19 )
  {
    v21 = ((__int64 (__fastcall *)(_QWORD, __int64, void *, void *, _QWORD))g_pRasReferenceCustomCount)(
            0,
            1,
            v11,
            v12,
            0);
    v14 = v21;
    if ( v21 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasReferenceCustomCount failed. %d", v21);
      *v20 = 0;
      *(_DWORD *)(a4 + 28) = v14;
      goto LABEL_8;
    }
  }
LABEL_12:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( v11 )
    GlobalFree(v11);
  if ( v12 )
    GlobalFree(v12);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomDialDlg done. %d", v14);
  return v14;
}

```

## disassembly

```asm
0x180026618  mov     [rsp-8+arg_0], rbx
0x18002661d  mov     [rsp-8+arg_10], r8
0x180026622  push    rbp
0x180026623  push    rsi
0x180026624  push    rdi
0x180026625  push    r12
0x180026627  push    r13
0x180026629  push    r14
0x18002662b  push    r15
0x18002662d  lea     rbp, [rsp-7]
0x180026632  sub     rsp, 90h
0x180026639  xor     r13d, r13d
0x18002663c  xorps   xmm0, xmm0
0x18002663f  xor     eax, eax
0x180026641  mov     [rbp+37h+hLibModule], r13
0x180026645  mov     r15, rcx
0x180026648  mov     [rbp+37h+arg_8], r13d
0x18002664c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180026652  mov     rdi, r9
0x180026655  mov     [rbp+37h+var_70], r13
0x180026659  mov     rsi, rdx
0x18002665c  mov     [rbp+37h+var_38], rax
0x180026660  mov     r12d, r13d
0x180026663  mov     [rbp+37h+var_80], r13d
0x180026667  mov     r14d, r13d
0x18002666a  movups  xmmword ptr [rbp+37h+lpWideCharStr], xmm0
0x18002666e  movups  [rbp+37h+var_58], xmm0
0x180026672  movups  [rbp+37h+var_48], xmm0
0x180026676  cmp     ecx, 0FFFFFFFFh
0x180026679  jz      short loc_18002668B
0x18002667b  lea     r8, aDwcustomdialdl; "DwCustomDialDlg.."
0x180026682  lea     edx, [rax+0Ch]; dwFlags
0x180026685  call    cs:__imp_TracePrintfExA
0x18002668b  test    rsi, rsi
0x18002668e  jz      short loc_1800266E3
0x180026690  cmp     r13w, [rsi]
0x180026694  jz      short loc_1800266E3
0x180026696  call    DwInitializeCustomDlg
0x18002669b  test    eax, eax
0x18002669d  jz      short loc_1800266AE
0x18002669f  mov     [rdi+1Ch], eax
0x1800266a2  mov     rax, [rbp+37h+arg_28]
0x1800266a6  mov     [rax], r13d
0x1800266a9  mov     ebx, r13d
0x1800266ac  jmp     short loc_1800266E8
0x1800266ae  mov     rax, [rbp+37h+arg_38]
0x1800266b2  lea     r9, [rbp+37h+var_70]
0x1800266b6  mov     [rsp+0C0h+var_90], rax
0x1800266bb  lea     r8, [rbp+37h+arg_8]
0x1800266bf  lea     rax, [rbp+37h+hLibModule]
0x1800266c3  mov     dword ptr [rsp+0C0h+var_98], r13d
0x1800266c8  mov     rdx, rsi
0x1800266cb  mov     [rsp+0C0h+var_A0], rax
0x1800266d0  mov     rcx, r15
0x1800266d3  call    cs:__imp_DwGetCustomDllEntryPoint
0x1800266d9  test    eax, eax
0x1800266db  jz      short loc_180026750
0x1800266dd  cmp     [rbp+37h+arg_8], r13d
0x1800266e1  jnz     short loc_18002669F
0x1800266e3  mov     ebx, 80004002h
0x1800266e8  mov     rcx, [rbp+37h+hLibModule]; hLibModule
0x1800266ec  test    rcx, rcx
0x1800266ef  jz      short loc_1800266F7
0x1800266f1  call    cs:__imp_FreeLibrary
0x1800266f7  test    r12, r12
0x1800266fa  jz      short loc_180026705
0x1800266fc  mov     rcx, r12; hMem
0x1800266ff  call    cs:__imp_GlobalFree
0x180026705  test    r14, r14
0x180026708  jz      short loc_180026713
0x18002670a  mov     rcx, r14; hMem
0x18002670d  call    cs:__imp_GlobalFree
0x180026713  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180026719  cmp     ecx, 0FFFFFFFFh
0x18002671c  jz      short loc_180026733
0x18002671e  mov     r9d, ebx
0x180026721  lea     r8, aDwcustomdialdl_0; "DwCustomDialDlg done. %d"
0x180026728  mov     edx, 0Ch; dwFlags
0x18002672d  call    cs:__imp_TracePrintfExA
0x180026733  mov     eax, ebx
0x180026735  mov     rbx, [rsp+0C0h+arg_0]
0x18002673d  add     rsp, 90h
0x180026744  pop     r15
0x180026746  pop     r14
0x180026748  pop     r13
0x18002674a  pop     r12
0x18002674c  pop     rdi
0x18002674d  pop     rsi
0x18002674e  pop     rbp
0x18002674f  retn
0x180026750  cmp     [rbp+37h+arg_8], r13d
0x180026754  jz      short loc_1800266E3
0x180026756  lea     r9, [rbp+37h+var_80]
0x18002675a  mov     rdx, rsi
0x18002675d  lea     r8, [rbp+37h+lpWideCharStr]
0x180026761  mov     rcx, r15
0x180026764  call    cs:__imp_DwGetEntryMode
0x18002676a  mov     ebx, eax
0x18002676c  test    eax, eax
0x18002676e  jnz     loc_18002669F
0x180026774  mov     r13d, [rbp+37h+var_80]
0x180026778  mov     rcx, r15
0x18002677b  or      r13d, [rbp+37h+arg_20]
0x18002677f  test    r15, r15
0x180026782  cmovz   rcx, [rbp+37h+lpWideCharStr]; lpWideCharStr
0x180026787  call    StrDupAFromTInternal
0x18002678c  mov     r12, rax
0x18002678f  test    r15, r15
0x180026792  jnz     short loc_18002679E
0x180026794  lea     rcx, [rbp+37h+lpWideCharStr]
0x180026798  call    cs:__imp_ClosePhonebookFile
0x18002679e  mov     rcx, rsi; lpWideCharStr
0x1800267a1  call    StrDupAFromTInternal
0x1800267a6  mov     r14, rax
0x1800267a9  test    r12, r12
0x1800267ac  jz      loc_18002684A
0x1800267b2  test    rax, rax
0x1800267b5  jz      loc_18002684A
0x1800267bb  mov     rcx, [rbp+37h+arg_30]
0x1800267bf  mov     r9, rsi
0x1800267c2  mov     rax, [rbp+37h+arg_10]
0x1800267c6  mov     r8, r15
0x1800267c9  mov     [rsp+0C0h+var_90], rcx
0x1800267ce  mov     edx, r13d
0x1800267d1  mov     rcx, [rbp+37h+hLibModule]
0x1800267d5  mov     [rsp+0C0h+var_98], rdi
0x1800267da  mov     [rsp+0C0h+var_A0], rax
0x1800267df  mov     rax, [rbp+37h+var_70]
0x1800267e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267e8  mov     rsi, [rbp+37h+arg_28]
0x1800267ec  xor     r13d, r13d
0x1800267ef  mov     [rsi], eax
0x1800267f1  test    eax, eax
0x1800267f3  jz      loc_1800266E8
0x1800267f9  mov     rax, cs:g_pRasReferenceCustomCount
0x180026800  lea     edx, [r13+1]
0x180026804  mov     r9, r14
0x180026807  mov     [rsp+0C0h+var_A0], r13
0x18002680c  mov     r8, r12
0x18002680f  xor     ecx, ecx
0x180026811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026816  mov     ebx, eax
0x180026818  test    eax, eax
0x18002681a  jz      loc_1800266E8
0x180026820  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180026826  cmp     ecx, 0FFFFFFFFh
0x180026829  jz      short loc_18002683F
0x18002682b  mov     r9d, eax
0x18002682e  lea     r8, aRasreferencecu; "RasReferenceCustomCount failed. %d"
0x180026835  lea     edx, [r13+0Ch]; dwFlags
0x180026839  call    cs:__imp_TracePrintfExA
0x18002683f  mov     [rsi], r13d
0x180026842  mov     [rdi+1Ch], ebx
0x180026845  jmp     loc_1800266A9
0x18002684a  xor     r13d, r13d
0x18002684d  mov     dword ptr [rdi+1Ch], 8
0x180026854  jmp     loc_1800266A2
```
