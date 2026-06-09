# SNI_Spn::SpnInit(void)

- ea: `0x100439fac`
- end: `0x10043a2cd`
- name: `?SpnInit@SNI_Spn@@SAKXZ`
- size: `801`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1004394a8`

## callees

- `0x100417768`
- `0x100439a88`
- `0x100439fac`
- `0x100545d84`
- `0x100546aa8`
- `0x100548140`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10043a262`
- `KERNEL32!GetLastError` at `0x10043a262`
- `KERNEL32!GetProcAddress` at `0x10043a05b`
- `KERNEL32!GetProcAddress` at `0x10043a078`
- `KERNEL32!GetProcAddress` at `0x10043a095`
- `KERNEL32!GetProcAddress` at `0x10043a0b2`
- `KERNEL32!GetProcAddress` at `0x10043a0cf`
- `KERNEL32!GetProcAddress` at `0x10043a0ec`
- `KERNEL32!GetProcAddress` at `0x10043a109`
- `KERNEL32!GetProcAddress` at `0x10043a142`
- `KERNEL32!GetProcAddress` at `0x10043a15f`
- `KERNEL32!GetProcAddress` at `0x10043a198`
- `KERNEL32!GetProcAddress` at `0x10043a1b5`
- `KERNEL32!GetProcAddress` at `0x10043a05b`
- `KERNEL32!GetProcAddress` at `0x10043a078`
- `KERNEL32!GetProcAddress` at `0x10043a095`
- `KERNEL32!GetProcAddress` at `0x10043a0b2`
- `KERNEL32!GetProcAddress` at `0x10043a0cf`
- `KERNEL32!GetProcAddress` at `0x10043a0ec`
- `KERNEL32!GetProcAddress` at `0x10043a109`
- `KERNEL32!GetProcAddress` at `0x10043a142`
- `KERNEL32!GetProcAddress` at `0x10043a15f`
- `KERNEL32!GetProcAddress` at `0x10043a198`
- `KERNEL32!GetProcAddress` at `0x10043a1b5`

## string_xrefs

- `0x10043a172`: `secur32.dll`
- `0x10043a026`: `ntdsapi.dll`
- `0x10043a11c`: `netapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SNI_Spn::SpnInit(void)
{
  DWORD v0; // ebx
  HINSTANCE v1; // rdi
  HINSTANCE v2; // rax
  HINSTANCE v3; // rsi
  HINSTANCE v4; // rax
  HINSTANCE v5; // r14
  DWORD LastError; // edi
  __int128 v8; // [rsp+50h] [rbp-29h] BYREF
  __int128 v9; // [rsp+60h] [rbp-19h]
  __int128 v10; // [rsp+70h] [rbp-9h]
  __int128 v11; // [rsp+80h] [rbp+7h]
  __int128 v12; // [rsp+90h] [rbp+17h]
  FARPROC ProcAddress; // [rsp+A0h] [rbp+27h]
  HINSTANCE v14; // [rsp+E0h] [rbp+67h] BYREF
  HINSTANCE v15; // [rsp+E8h] [rbp+6Fh] BYREF
  HINSTANCE v16; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v17; // [rsp+F8h] [rbp+7Fh] BYREF

  v17 = -1;
  v0 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7E08[0] && bidID != -1 )
    off_1005D39F0(bidID);
  v1 = SNILoadSystemLibA("ntdsapi.dll");
  v16 = v1;
  memset_0(&v8, 0, 0x58u);
  if ( !v1 )
    goto LABEL_24;
  *(_QWORD *)&v8 = GetProcAddress(v1, DsFunctionNames);
  if ( !(_QWORD)v8 )
    goto LABEL_24;
  *((_QWORD *)&v8 + 1) = GetProcAddress(v1, lpProcName);
  if ( !*((_QWORD *)&v8 + 1) )
    goto LABEL_24;
  *(_QWORD *)&v9 = GetProcAddress(v1, off_1005CF550);
  if ( !(_QWORD)v9 )
    goto LABEL_24;
  *((_QWORD *)&v9 + 1) = GetProcAddress(v1, off_1005CF558);
  if ( !*((_QWORD *)&v9 + 1) )
    goto LABEL_24;
  *(_QWORD *)&v10 = GetProcAddress(v1, off_1005CF560);
  if ( !(_QWORD)v10 )
    goto LABEL_24;
  *((_QWORD *)&v10 + 1) = GetProcAddress(v1, off_1005CF568);
  if ( !*((_QWORD *)&v10 + 1) )
    goto LABEL_24;
  *(_QWORD *)&v11 = GetProcAddress(v1, off_1005CF570);
  if ( !(_QWORD)v11 )
    goto LABEL_24;
  v2 = SNILoadSystemLibA("netapi32.dll");
  v3 = v2;
  v15 = v2;
  if ( !v2 )
    goto LABEL_24;
  *((_QWORD *)&v11 + 1) = GetProcAddress(v2, off_1005CF578);
  if ( *((_QWORD *)&v11 + 1)
    && (*(_QWORD *)&v12 = GetProcAddress(v3, "NetApiBufferFree"), (_QWORD)v12)
    && (v4 = SNILoadSystemLibA("secur32.dll"), v5 = v4, (v14 = v4) != 0)
    && (*((_QWORD *)&v12 + 1) = GetProcAddress(v4, off_1005CF580)) != 0
    && (ProcAddress = GetProcAddress(v5, off_1005CF588)) != 0 )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 )
    {
      if ( off_1005E5C50[0] )
        bidTraceW(0, 160768, off_1005E5C50[0], 0);
      v5 = v14;
      v3 = v15;
      v1 = v16;
    }
    gDsFunc = v8;
    xmmword_1005D8ED0 = v9;
    xmmword_1005D8EE0 = v10;
    xmmword_1005D8EF0 = v11;
    xmmword_1005D8F00 = v12;
    qword_1005D8F10 = (__int64)ProcAddress;
    ghSpnLib = v1;
    ghNetApiLib = v3;
    ghSecur = v5;
  }
  else
  {
LABEL_24:
    LastError = GetLastError();
    SNI_Spn::DoSpnTerminate(&v16, &v15, &v14, (struct _DsFunctionTable *)&v8);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5C58[0] )
      bidTraceW(0, 177152, off_1005E5C58[0], LastError);
    v0 = LastError;
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v17);
  return v0;
}

```

## disassembly

```asm
0x100439fac  push    rbp
0x100439fae  push    rbx
0x100439faf  push    rsi
0x100439fb0  push    rdi
0x100439fb1  push    r14
0x100439fb3  lea     rbp, [rsp-37h]
0x100439fb8  sub     rsp, 0B0h
0x100439fbf  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x100439fc7  or      [rbp+57h+arg_18], 0FFFFFFFFFFFFFFFFh
0x100439fcc  mov     eax, cs:_bidGblFlags
0x100439fd2  mov     ecx, 20004h
0x100439fd7  and     eax, ecx
0x100439fd9  xor     ebx, ebx
0x100439fdb  cmp     eax, ecx
0x100439fdd  jnz     short loc_10043A026
0x100439fdf  mov     rax, cs:off_1005E7E08; "<SNI_Spn::SpnInit|API|SNI> \n"
0x100439fe6  test    rax, rax
0x100439fe9  jz      short loc_10043A026
0x100439feb  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100439ff3  jz      short loc_10043A026
0x100439ff5  mov     r10, cs:off_1005D39F0
0x100439ffc  mov     [rsp+0D0h+var_A8], rbx
0x10043a001  mov     rax, cs:off_1005E7E08; "<SNI_Spn::SpnInit|API|SNI> \n"
0x10043a008  mov     [rsp+0D0h+var_B0], rax
0x10043a00d  lea     r9, [rbp+57h+arg_18]
0x10043a011  xor     r8d, r8d
0x10043a014  xor     edx, edx
0x10043a016  mov     rcx, cs:_bidID
0x10043a01d  mov     rax, r10
0x10043a020  call    cs:__guard_dispatch_icall_fptr
0x10043a026  lea     rcx, aNtdsapiDll; "ntdsapi.dll"
0x10043a02d  call    SNILoadSystemLibA
0x10043a032  mov     rdi, rax
0x10043a035  mov     [rbp+57h+arg_10], rax
0x10043a039  xor     edx, edx; Val
0x10043a03b  lea     r8d, [rdx+58h]; Size
0x10043a03f  lea     rcx, [rbp+57h+var_80]; void *
0x10043a043  call    memset_0
0x10043a048  test    rdi, rdi
0x10043a04b  jz      loc_10043A262
0x10043a051  mov     rdx, cs:?DsFunctionNames@@3PAPEBDA; lpProcName
0x10043a058  mov     rcx, rdi; hModule
0x10043a05b  call    cs:__imp_GetProcAddress
0x10043a061  mov     qword ptr [rbp+57h+var_80], rax
0x10043a065  test    rax, rax
0x10043a068  jz      loc_10043A262
0x10043a06e  mov     rdx, cs:lpProcName; lpProcName
0x10043a075  mov     rcx, rdi; hModule
0x10043a078  call    cs:__imp_GetProcAddress
0x10043a07e  mov     qword ptr [rbp+57h+var_80+8], rax
0x10043a082  test    rax, rax
0x10043a085  jz      loc_10043A262
0x10043a08b  mov     rdx, cs:off_1005CF550; lpProcName
0x10043a092  mov     rcx, rdi; hModule
0x10043a095  call    cs:__imp_GetProcAddress
0x10043a09b  mov     qword ptr [rbp+57h+var_70], rax
0x10043a09f  test    rax, rax
0x10043a0a2  jz      loc_10043A262
0x10043a0a8  mov     rdx, cs:off_1005CF558; lpProcName
0x10043a0af  mov     rcx, rdi; hModule
0x10043a0b2  call    cs:__imp_GetProcAddress
0x10043a0b8  mov     qword ptr [rbp+57h+var_70+8], rax
0x10043a0bc  test    rax, rax
0x10043a0bf  jz      loc_10043A262
0x10043a0c5  mov     rdx, cs:off_1005CF560; lpProcName
0x10043a0cc  mov     rcx, rdi; hModule
0x10043a0cf  call    cs:__imp_GetProcAddress
0x10043a0d5  mov     qword ptr [rbp+57h+var_60], rax
0x10043a0d9  test    rax, rax
0x10043a0dc  jz      loc_10043A262
0x10043a0e2  mov     rdx, cs:off_1005CF568; lpProcName
0x10043a0e9  mov     rcx, rdi; hModule
0x10043a0ec  call    cs:__imp_GetProcAddress
0x10043a0f2  mov     qword ptr [rbp+57h+var_60+8], rax
0x10043a0f6  test    rax, rax
0x10043a0f9  jz      loc_10043A262
0x10043a0ff  mov     rdx, cs:off_1005CF570; lpProcName
0x10043a106  mov     rcx, rdi; hModule
0x10043a109  call    cs:__imp_GetProcAddress
0x10043a10f  mov     qword ptr [rbp+57h+var_50], rax
0x10043a113  test    rax, rax
0x10043a116  jz      loc_10043A262
0x10043a11c  lea     rcx, aNetapi32Dll_0; "netapi32.dll"
0x10043a123  call    SNILoadSystemLibA
0x10043a128  mov     rsi, rax
0x10043a12b  mov     [rbp+57h+arg_8], rax
0x10043a12f  test    rax, rax
0x10043a132  jz      loc_10043A262
0x10043a138  mov     rdx, cs:off_1005CF578; lpProcName
0x10043a13f  mov     rcx, rax; hModule
0x10043a142  call    cs:__imp_GetProcAddress
0x10043a148  mov     qword ptr [rbp+57h+var_50+8], rax
0x10043a14c  test    rax, rax
0x10043a14f  jz      loc_10043A262
0x10043a155  lea     rdx, aNetapibufferfr; "NetApiBufferFree"
0x10043a15c  mov     rcx, rsi; hModule
0x10043a15f  call    cs:__imp_GetProcAddress
0x10043a165  mov     qword ptr [rbp+57h+var_40], rax
0x10043a169  test    rax, rax
0x10043a16c  jz      loc_10043A262
0x10043a172  lea     rcx, aSecur32Dll_0; "secur32.dll"
0x10043a179  call    SNILoadSystemLibA
0x10043a17e  mov     r14, rax
0x10043a181  mov     [rbp+57h+arg_0], rax
0x10043a185  test    rax, rax
0x10043a188  jz      loc_10043A262
0x10043a18e  mov     rdx, cs:off_1005CF580; lpProcName
0x10043a195  mov     rcx, rax; hModule
0x10043a198  call    cs:__imp_GetProcAddress
0x10043a19e  mov     qword ptr [rbp+57h+var_40+8], rax
0x10043a1a2  test    rax, rax
0x10043a1a5  jz      loc_10043A262
0x10043a1ab  mov     rdx, cs:off_1005CF588; lpProcName
0x10043a1b2  mov     rcx, r14; hModule
0x10043a1b5  call    cs:__imp_GetProcAddress
0x10043a1bb  mov     [rbp+57h+var_30], rax
0x10043a1bf  test    rax, rax
0x10043a1c2  jz      loc_10043A262
0x10043a1c8  mov     eax, cs:_bidGblFlags
0x10043a1ce  mov     ecx, 20002h
0x10043a1d3  and     eax, ecx
0x10043a1d5  cmp     eax, ecx
0x10043a1d7  jnz     short loc_10043A207
0x10043a1d9  mov     rax, cs:off_1005E5C50; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x10043a1e0  test    rax, rax
0x10043a1e3  jz      short loc_10043A1FB
0x10043a1e5  xor     r9d, r9d
0x10043a1e8  mov     r8, cs:off_1005E5C50; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x10043a1ef  mov     edx, 27400h
0x10043a1f4  xor     ecx, ecx
0x10043a1f6  call    _bidTraceW
0x10043a1fb  mov     r14, [rbp+57h+arg_0]
0x10043a1ff  mov     rsi, [rbp+57h+arg_8]
0x10043a203  mov     rdi, [rbp+57h+arg_10]
0x10043a207  movaps  xmm0, [rbp+57h+var_80]
0x10043a20b  movaps  cs:?gDsFunc@@3U_DsFunctionTable@@A, xmm0; _DsFunctionTable gDsFunc
0x10043a212  movaps  xmm1, [rbp+57h+var_70]
0x10043a216  movaps  cs:xmmword_1005D8ED0, xmm1
0x10043a21d  movaps  xmm0, [rbp+57h+var_60]
0x10043a221  movaps  cs:xmmword_1005D8EE0, xmm0
0x10043a228  movaps  xmm1, [rbp+57h+var_50]
0x10043a22c  movaps  cs:xmmword_1005D8EF0, xmm1
0x10043a233  movaps  xmm0, [rbp+57h+var_40]
0x10043a237  movaps  cs:xmmword_1005D8F00, xmm0
0x10043a23e  movsd   xmm1, [rbp+57h+var_30]
0x10043a243  movsd   cs:qword_1005D8F10, xmm1
0x10043a24b  mov     cs:?ghSpnLib@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * ghSpnLib
0x10043a252  mov     cs:?ghNetApiLib@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * ghNetApiLib
0x10043a259  mov     cs:?ghSecur@@3PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * ghSecur
0x10043a260  jmp     short loc_10043A2B4
0x10043a262  call    cs:__imp_GetLastError
0x10043a268  mov     edi, eax
0x10043a26a  lea     r9, [rbp+57h+var_80]; struct _DsFunctionTable *
0x10043a26e  lea     r8, [rbp+57h+arg_0]; HINSTANCE *
0x10043a272  lea     rdx, [rbp+57h+arg_8]; HINSTANCE *
0x10043a276  lea     rcx, [rbp+57h+arg_10]; HINSTANCE *
0x10043a27a  call    ?DoSpnTerminate@SNI_Spn@@CAXPEAPEAUHINSTANCE__@@00PEAU_DsFunctionTable@@@Z; SNI_Spn::DoSpnTerminate(HINSTANCE__ * *,HINSTANCE__ * *,HINSTANCE__ * *,_DsFunctionTable *)
0x10043a27f  mov     eax, cs:_bidGblFlags
0x10043a285  mov     ecx, 20002h
0x10043a28a  and     eax, ecx
0x10043a28c  cmp     eax, ecx
0x10043a28e  jnz     short loc_10043A2B2
0x10043a290  mov     rax, cs:off_1005E5C58; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x10043a297  test    rax, rax
0x10043a29a  jz      short loc_10043A2B2
0x10043a29c  mov     r9d, edi
0x10043a29f  mov     r8, cs:off_1005E5C58; "<SNI_Spn::SpnInit|RET|SNI> %d{WINERR}\n"
0x10043a2a6  mov     edx, 2B400h
0x10043a2ab  xor     ecx, ecx
0x10043a2ad  call    _bidTraceW
0x10043a2b2  mov     ebx, edi
0x10043a2b4  lea     rcx, [rbp+57h+arg_18]; this
0x10043a2b8  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10043a2bd  mov     eax, ebx
0x10043a2bf  add     rsp, 0B0h
0x10043a2c6  pop     r14
0x10043a2c8  pop     rdi
0x10043a2c9  pop     rsi
0x10043a2ca  pop     rbx
0x10043a2cb  pop     rbp
0x10043a2cc  retn
```
