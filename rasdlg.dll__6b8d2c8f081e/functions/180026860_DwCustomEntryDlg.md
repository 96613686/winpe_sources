# DwCustomEntryDlg

- ea: `0x180026860`
- end: `0x180026993`
- name: `DwCustomEntryDlg`
- size: `307`
- prototype: `__int64 __fastcall(__int64, _WORD *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800149b4`

## callees

- `0x180026860`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002695e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002695e`
- `RASAPI32!DwGetEntryMode` at `0x180026923`
- `RASAPI32!DwGetEntryMode` at `0x180026923`
- `RASAPI32!DwGetCustomDllEntryPoint` at `0x1800268ef`
- `RASAPI32!DwGetCustomDllEntryPoint` at `0x1800268ef`
- `rtutils!TracePrintfExA` at `0x1800268b1`
- `rtutils!TracePrintfExA` at `0x18002697e`
- `rtutils!TracePrintfExA` at `0x1800268b1`
- `rtutils!TracePrintfExA` at `0x18002697e`

## pseudocode

```c
__int64 __fastcall DwCustomEntryDlg(__int64 a1, _WORD *a2, __int64 a3, _DWORD *a4)
{
  unsigned int CustomDllEntryPoint; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+40h] [rbp-28h] BYREF
  HMODULE hLibModule; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+50h] [rbp-18h] BYREF
  int v14; // [rsp+A8h] [rbp+40h] BYREF

  hLibModule = 0;
  v14 = 0;
  v13[0] = 0;
  v11 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomEntryDlg..");
  if ( !a2 || !*a2 )
    goto LABEL_11;
  CustomDllEntryPoint = DwGetCustomDllEntryPoint(a1, a2, &v14, v13, &hLibModule, 1, 0);
  if ( CustomDllEntryPoint )
  {
    if ( v14 )
    {
LABEL_7:
      *(_DWORD *)(a3 + 540) = CustomDllEntryPoint;
      v9 = 0;
      *a4 = 0;
      goto LABEL_12;
    }
    goto LABEL_11;
  }
  if ( !v14 )
  {
LABEL_11:
    v9 = -2147467262;
    goto LABEL_12;
  }
  CustomDllEntryPoint = DwGetEntryMode(a1, a2, 0, &v11);
  v9 = CustomDllEntryPoint;
  if ( CustomDllEntryPoint )
    goto LABEL_7;
  *a4 = ((__int64 (__fastcall *)(HMODULE, __int64, _WORD *, __int64, int))v13[0])(hLibModule, a1, a2, a3, v11);
LABEL_12:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwCustomEntryDlg done. %d", v9);
  return v9;
}

```

## disassembly

```asm
0x180026860  push    rbp
0x180026862  push    rbx
0x180026863  push    rsi
0x180026864  push    rdi
0x180026865  push    r14
0x180026867  push    r15
0x180026869  mov     rbp, rsp
0x18002686c  sub     rsp, 68h
0x180026870  mov     r15, rcx
0x180026873  mov     [rbp+hLibModule], 0
0x18002687b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180026881  mov     rsi, r9
0x180026884  mov     [rbp+arg_8], 0
0x18002688b  mov     r14, r8
0x18002688e  mov     [rbp+var_18], 0
0x180026896  mov     rdi, rdx
0x180026899  mov     [rbp+var_28], 0
0x1800268a0  cmp     ecx, 0FFFFFFFFh
0x1800268a3  jz      short loc_1800268B7
0x1800268a5  lea     r8, aDwcustomentryd; "DwCustomEntryDlg.."
0x1800268ac  mov     edx, 0Ch; dwFlags
0x1800268b1  call    cs:__imp_TracePrintfExA
0x1800268b7  test    rdi, rdi
0x1800268ba  jz      loc_180026950
0x1800268c0  xor     eax, eax
0x1800268c2  cmp     ax, [rdi]
0x1800268c5  jz      loc_180026950
0x1800268cb  mov     [rsp+68h+var_38], rax
0x1800268d0  lea     r9, [rbp+var_18]
0x1800268d4  lea     rax, [rbp+hLibModule]
0x1800268d8  mov     [rsp+68h+var_40], 1
0x1800268e0  lea     r8, [rbp+arg_8]
0x1800268e4  mov     [rsp+68h+var_48], rax
0x1800268e9  mov     rdx, rdi
0x1800268ec  mov     rcx, r15
0x1800268ef  call    cs:__imp_DwGetCustomDllEntryPoint
0x1800268f5  test    eax, eax
0x1800268f7  jz      short loc_180026910
0x1800268f9  cmp     [rbp+arg_8], 0
0x1800268fd  jz      short loc_180026950
0x1800268ff  mov     [r14+21Ch], eax
0x180026906  xor     ebx, ebx
0x180026908  mov     dword ptr [rsi], 0
0x18002690e  jmp     short loc_180026955
0x180026910  cmp     [rbp+arg_8], 0
0x180026914  jz      short loc_180026950
0x180026916  lea     r9, [rbp+var_28]
0x18002691a  xor     r8d, r8d
0x18002691d  mov     rdx, rdi
0x180026920  mov     rcx, r15
0x180026923  call    cs:__imp_DwGetEntryMode
0x180026929  mov     ebx, eax
0x18002692b  test    eax, eax
0x18002692d  jnz     short loc_1800268FF
0x18002692f  mov     ecx, [rbp+var_28]
0x180026932  mov     r9, r14
0x180026935  mov     rax, [rbp+var_18]
0x180026939  mov     r8, rdi
0x18002693c  mov     dword ptr [rsp+68h+var_48], ecx
0x180026940  mov     rdx, r15
0x180026943  mov     rcx, [rbp+hLibModule]
0x180026947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002694c  mov     [rsi], eax
0x18002694e  jmp     short loc_180026955
0x180026950  mov     ebx, 80004002h
0x180026955  mov     rcx, [rbp+hLibModule]; hLibModule
0x180026959  test    rcx, rcx
0x18002695c  jz      short loc_180026964
0x18002695e  call    cs:__imp_FreeLibrary
0x180026964  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002696a  cmp     ecx, 0FFFFFFFFh
0x18002696d  jz      short loc_180026984
0x18002696f  mov     r9d, ebx
0x180026972  lea     r8, aDwcustomentryd_0; "DwCustomEntryDlg done. %d"
0x180026979  mov     edx, 0Ch; dwFlags
0x18002697e  call    cs:__imp_TracePrintfExA
0x180026984  mov     eax, ebx
0x180026986  add     rsp, 68h
0x18002698a  pop     r15
0x18002698c  pop     r14
0x18002698e  pop     rdi
0x18002698f  pop     rsi
0x180026990  pop     rbx
0x180026991  pop     rbp
0x180026992  retn
```
