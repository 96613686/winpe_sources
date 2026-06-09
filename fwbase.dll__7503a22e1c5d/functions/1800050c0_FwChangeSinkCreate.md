# FwChangeSinkCreate

- ea: `0x1800050c0`
- end: `0x180005349`
- name: `FwChangeSinkCreate`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x1800050c0`
- `0x1800053c0`
- `0x180006000`
- `0x180006f50`
- `0x18001e1d0`
- `0x18001eb54`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800051e4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800051e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005209`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005209`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800051f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800051f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800051b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800051b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051a5`

## string_xrefs

- `0x1800050ee`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Epoch`
- `0x180005159`: `SharedAccessEpoch`
- `0x180005270`: `FwChangeSinkCreate`
- `0x180005302`: `FwChangeSinkCreate`
- `0x18000531c`: `FwChangeSinkCreate`
- `0x180005332`: `FwChangeSinkCreate`
- `0x1800051d1`: `SharedAccessEpoch2`
- `0x1800051f2`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall FwChangeSinkCreate(__int64 a1, int a2, __int64 *a3)
{
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rax
  __int64 v8; // rdi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v14; // rsi
  unsigned int v15; // eax
  __int64 v16; // rdx
  _OWORD v17[5]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[26]; // [rsp+90h] [rbp-70h]
  _BYTE v19[422]; // [rsp+AAh] [rbp-56h] BYREF
  _OWORD v20[2]; // [rsp+250h] [rbp+150h] BYREF
  int v21; // [rsp+270h] [rbp+170h]
  _BYTE v22[492]; // [rsp+274h] [rbp+174h] BYREF

  v17[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Epoch";
  v17[2] = *(_OWORD *)L"ntrolSet\\Services\\SharedAccess\\Epoch";
  v17[1] = *(_OWORD *)L"urrentControlSet\\Services\\SharedAccess\\Epoch";
  v17[4] = *(_OWORD *)L"s\\SharedAccess\\Epoch";
  v5 = a2;
  v17[3] = *(_OWORD *)L"\\Services\\SharedAccess\\Epoch";
  *(_OWORD *)v18 = *(_OWORD *)L"Access\\Epoch";
  *(_OWORD *)&v18[10] = *(_OWORD *)L"s\\Epoch";
  memset_0(v19, 0, 0x19Eu);
  v20[0] = *(_OWORD *)L"SharedAccessEpoch";
  v20[1] = *(_OWORD *)L"cessEpoch";
  v21 = *(_DWORD *)L"h";
  memset_0(v22, 0, 0x1E4u);
  *a3 = 0;
  if ( (unsigned int)v5 > 1 )
  {
    v8 = 0;
LABEL_13:
    v16 = 2147942487LL;
    v12 = -2147024809;
LABEL_14:
    FwReportReturnError("FwChangeSinkCreate", v16);
    goto LABEL_15;
  }
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  v8 = (__int64)v7;
  if ( !v7 )
  {
    v12 = FwReportErrorAsWinError("FwChangeSinkCreate", "FwAlloc", 8);
    if ( (v12 & 0x80000000) == 0 )
      return v12;
LABEL_15:
    FwChangeSinkDestroy(v8);
    return (unsigned int)FwReportReturnError("FwChangeSinkCreate", v12);
  }
  *v7 = a1;
  if ( (_DWORD)v5 == 1 && (unsigned int)_o_wcscpy_s(v20, 260, L"SharedAccessEpoch2") )
    goto LABEL_13;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetPersistedStateLocation");
  if ( ProcAddress )
  {
    v14 = ((unsigned int (__fastcall *)(_OWORD *, _QWORD, wchar_t *, _QWORD, _OWORD *, int, _QWORD))ProcAddress)(
            v20,
            0,
            off_180031228[v5],
            0,
            v17,
            520,
            0);
    if ( (int)FwNtStatusToHResult(v14) < 0 )
    {
      v12 = 0;
      v15 = FwNtStatusToHResult((unsigned int)v14);
      FwReportReturnError("FwChangeSinkCreate", v15);
      return v12;
    }
  }
  v11 = FwRegNotifyCreate(-2147483646, v17, 0, 4, 50, (__int64)FwChangeSinkOnChange, v8, (_QWORD *)(v8 + 8));
  v12 = v11;
  if ( v11 < 0 )
  {
    v16 = (unsigned int)v11;
    goto LABEL_14;
  }
  *a3 = v8;
  return v12;
}

```

## disassembly

```asm
0x1800050c0  mov     [rsp-8+arg_0], rbx
0x1800050c5  mov     [rsp-8+arg_18], rsi
0x1800050ca  push    rbp
0x1800050cb  push    rdi
0x1800050cc  push    r14
0x1800050ce  lea     rbp, [rsp-370h]
0x1800050d6  sub     rsp, 470h
0x1800050dd  mov     rax, cs:__security_cookie
0x1800050e4  xor     rax, rsp
0x1800050e7  mov     [rbp+380h+var_20], rax
0x1800050ee  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800050f5  mov     r14, r8
0x1800050f8  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\SharedAcces"...
0x1800050ff  mov     rsi, rcx
0x180005102  movaps  [rsp+480h+var_440], xmm0
0x180005107  lea     rcx, [rbp+380h+var_3D6]; void *
0x18000510b  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\SharedAccess\\Epoch"
0x180005112  mov     r8d, 19Eh; Size
0x180005118  movaps  [rsp+480h+var_420], xmm0
0x18000511d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\SharedAccess\\Epoch"
0x180005124  movaps  [rsp+480h+var_430], xmm1
0x180005129  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\SharedAccess\\Epoch"
0x180005130  movaps  [rbp+380h+var_400], xmm0
0x180005134  movups  xmm0, xmmword ptr cs:aSystemCurrentc+5Ah; "s\\Epoch"
0x18000513b  movsxd  rbx, edx
0x18000513e  xor     edx, edx; Val
0x180005140  movaps  [rsp+480h+var_410], xmm1
0x180005145  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+50h; "Access\\Epoch"
0x18000514c  movaps  xmmword ptr [rbp+380h+var_3F0], xmm1
0x180005150  movups  xmmword ptr [rbp+380h+var_3F0+0Ah], xmm0
0x180005154  call    memset_0
0x180005159  movups  xmm0, xmmword ptr cs:aSharedaccessep_0; "SharedAccessEpoch"
0x180005160  mov     eax, dword ptr cs:aSharedaccessep_0+20h; "h"
0x180005166  xor     edx, edx; Val
0x180005168  movups  xmm1, xmmword ptr cs:aSharedaccessep_0+10h; "cessEpoch"
0x18000516f  mov     r8d, 1E4h; Size
0x180005175  lea     rcx, [rbp+380h+var_20C]; void *
0x18000517c  movaps  [rbp+380h+var_230], xmm0
0x180005183  movaps  [rbp+380h+var_220], xmm1
0x18000518a  mov     [rbp+380h+var_210], eax
0x180005190  call    memset_0
0x180005195  mov     qword ptr [r14], 0
0x18000519c  cmp     ebx, 1
0x18000519f  ja      loc_180005313
0x1800051a5  call    cs:__imp_GetProcessHeap
0x1800051ab  mov     edx, 8; dwFlags
0x1800051b0  mov     rcx, rax; hHeap
0x1800051b3  lea     r8d, [rdx+8]; dwBytes
0x1800051b7  call    cs:__imp_HeapAlloc
0x1800051bd  mov     rdi, rax
0x1800051c0  test    rax, rax
0x1800051c3  jz      loc_180005263
0x1800051c9  mov     [rax], rsi
0x1800051cc  cmp     ebx, 1
0x1800051cf  jnz     short loc_1800051F2
0x1800051d1  lea     r8, aSharedaccessep; "SharedAccessEpoch2"
0x1800051d8  mov     edx, 104h
0x1800051dd  lea     rcx, [rbp+380h+var_230]
0x1800051e4  call    cs:__imp__o_wcscpy_s
0x1800051ea  test    eax, eax
0x1800051ec  jnz     loc_180005315
0x1800051f2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800051f9  call    cs:__imp_GetModuleHandleW
0x1800051ff  mov     rcx, rax; hModule
0x180005202  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180005209  call    cs:__imp_GetProcAddress
0x18000520f  test    rax, rax
0x180005212  jnz     loc_1800052AF
0x180005218  lea     rax, [rdi+8]
0x18000521c  mov     r9d, 4
0x180005222  mov     [rsp+480h+var_448], rax
0x180005227  lea     rdx, [rsp+480h+var_440]
0x18000522c  lea     rax, ?FwChangeSinkOnChange@@YAXPEAUFW_CHANGE_SINK_@@J@Z; FwChangeSinkOnChange(FW_CHANGE_SINK_ *,long)
0x180005233  mov     [rsp+480h+var_450], rdi
0x180005238  mov     [rsp+480h+var_458], rax
0x18000523d  xor     r8d, r8d
0x180005240  mov     rcx, 0FFFFFFFF80000002h
0x180005247  mov     dword ptr [rsp+480h+var_460], 32h ; '2'
0x18000524f  call    FwRegNotifyCreate
0x180005254  mov     ebx, eax
0x180005256  test    eax, eax
0x180005258  js      loc_180005345
0x18000525e  mov     [r14], rdi
0x180005261  jmp     short loc_180005286
0x180005263  mov     r8d, 8
0x180005269  lea     rdx, aFwalloc_0; "FwAlloc"
0x180005270  lea     rcx, aFwchangesinkcr_0; "FwChangeSinkCreate"
0x180005277  call    FwReportErrorAsWinError
0x18000527c  mov     ebx, eax
0x18000527e  test    eax, eax
0x180005280  js      loc_180005328
0x180005286  mov     eax, ebx
0x180005288  mov     rcx, [rbp+380h+var_20]
0x18000528f  xor     rcx, rsp; StackCookie
0x180005292  call    __security_check_cookie
0x180005297  lea     r11, [rsp+480h+var_10]
0x18000529f  mov     rbx, [r11+20h]
0x1800052a3  mov     rsi, [r11+38h]
0x1800052a7  mov     rsp, r11
0x1800052aa  pop     r14
0x1800052ac  pop     rdi
0x1800052ad  pop     rbp
0x1800052ae  retn
0x1800052af  lea     rdx, off_180031228; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800052b6  mov     [rsp+480h+var_450], 0
0x1800052bf  mov     r8, [rdx+rbx*8]
0x1800052c3  lea     rcx, [rsp+480h+var_440]
0x1800052c8  mov     dword ptr [rsp+480h+var_458], 208h
0x1800052d0  xor     edx, edx
0x1800052d2  mov     [rsp+480h+var_460], rcx
0x1800052d7  xor     r9d, r9d
0x1800052da  lea     rcx, [rbp+380h+var_230]
0x1800052e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e6  mov     ecx, eax
0x1800052e8  mov     esi, eax
0x1800052ea  call    FwNtStatusToHResult
0x1800052ef  test    eax, eax
0x1800052f1  jns     loc_180005218
0x1800052f7  mov     ecx, esi
0x1800052f9  xor     ebx, ebx
0x1800052fb  call    FwNtStatusToHResult
0x180005300  mov     edx, eax
0x180005302  lea     rcx, aFwchangesinkcr_0; "FwChangeSinkCreate"
0x180005309  call    FwReportReturnError
0x18000530e  jmp     loc_180005286
0x180005313  xor     edi, edi
0x180005315  mov     edx, 80070057h
0x18000531a  mov     ebx, edx
0x18000531c  lea     rcx, aFwchangesinkcr_0; "FwChangeSinkCreate"
0x180005323  call    FwReportReturnError
0x180005328  mov     rcx, rdi
0x18000532b  call    FwChangeSinkDestroy
0x180005330  mov     edx, ebx
0x180005332  lea     rcx, aFwchangesinkcr_0; "FwChangeSinkCreate"
0x180005339  call    FwReportReturnError
0x18000533e  mov     ebx, eax
0x180005340  jmp     loc_180005286
0x180005345  mov     edx, eax
0x180005347  jmp     short loc_18000531C
```
