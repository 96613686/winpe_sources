# CorGetSvc

- ea: `0x18002cdbc`
- end: `0x18002ce89`
- name: `CorGetSvc`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007480`
- `0x18002cf5c`

## callees

- `0x180002710`
- `0x180008710`
- `0x180009af4`
- `0x18002cdbc`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002ce56`
- `KERNEL32!GetProcAddress` at `0x18002ce56`

## string_xrefs

- `0x18002ce34`: `mscorsvc.dll`

## pseudocode

```c
__int64 __fastcall CorGetSvc(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // r8
  FARPROC ProcAddress; // rax
  wchar_t *v6[2]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v7; // [rsp+30h] [rbp-49h]
  __int128 v8; // [rsp+40h] [rbp-39h]
  __int64 v9; // [rsp+50h] [rbp-29h]
  int v10; // [rsp+58h] [rbp-21h]
  __int64 v11; // [rsp+5Ch] [rbp-1Dh]
  __int64 v12; // [rsp+64h] [rbp-15h]
  __int64 v13; // [rsp+70h] [rbp-9h]
  int v14; // [rsp+78h] [rbp-1h]
  __int64 v15; // [rsp+80h] [rbp+7h]
  __int64 v16; // [rsp+88h] [rbp+Fh]
  __int64 v17; // [rsp+90h] [rbp+17h]
  int v18; // [rsp+98h] [rbp+1Fh]
  __int64 v19; // [rsp+A0h] [rbp+27h]
  HMODULE hModule; // [rsp+E8h] [rbp+6Fh] BYREF

  v19 = -1;
  v9 = 0;
  *(_OWORD *)v6 = 0;
  v8 = 0;
  v7 = 0;
  v14 = 1;
  v10 = 1;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  hModule = 0;
  v2 = RuntimeRequest::ComputeVersionString((const unsigned __int16 **)v6, 0);
  if ( v2 >= 0 )
  {
    v2 = LoadLibraryShim_0((wchar_t *)L"mscorsvc.dll", v6[0], v3, &hModule);
    if ( v2 >= 0 )
    {
      if ( hModule && (ProcAddress = GetProcAddress(hModule, "CorGetSvc")) != 0 )
        v2 = ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
      else
        v2 = -2147467259;
    }
  }
  RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002cdbc  push    rbp
0x18002cdbe  push    rbx
0x18002cdbf  push    rsi
0x18002cdc0  push    rdi
0x18002cdc1  lea     rbp, [rsp-3Fh]
0x18002cdc6  sub     rsp, 0B8h
0x18002cdcd  xor     esi, esi
0x18002cdcf  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFFh
0x18002cdd7  xorps   xmm0, xmm0
0x18002cdda  mov     [rbp+57h+var_80], rsi
0x18002cdde  mov     rdi, rcx
0x18002cde1  movdqa  xmmword ptr [rbp+57h+var_B0], xmm0
0x18002cde6  xorps   xmm1, xmm1
0x18002cde9  movdqa  [rbp+57h+var_90], xmm0
0x18002cdee  lea     eax, [rsi+1]
0x18002cdf1  movdqa  [rbp+57h+var_A0], xmm1
0x18002cdf6  xor     edx, edx; int
0x18002cdf8  mov     [rbp+57h+var_58], eax
0x18002cdfb  lea     rcx, [rbp+57h+var_B0]; this
0x18002cdff  mov     [rbp+57h+var_78], eax
0x18002ce02  mov     [rbp+57h+var_74], rsi
0x18002ce06  mov     [rbp+57h+var_6C], rsi
0x18002ce0a  mov     [rbp+57h+var_60], rsi
0x18002ce0e  mov     [rbp+57h+var_50], rsi
0x18002ce12  mov     [rbp+57h+var_48], rsi
0x18002ce16  mov     [rbp+57h+var_40], rsi
0x18002ce1a  mov     [rbp+57h+var_38], esi
0x18002ce1d  mov     [rbp+57h+hModule], rsi
0x18002ce21  call    ?ComputeVersionString@RuntimeRequest@@QEAAJH@Z; RuntimeRequest::ComputeVersionString(int)
0x18002ce26  mov     ebx, eax
0x18002ce28  test    eax, eax
0x18002ce2a  js      short loc_18002CE72
0x18002ce2c  mov     rdx, [rbp+57h+var_B0]; wchar_t *
0x18002ce30  lea     r9, [rbp+57h+hModule]
0x18002ce34  lea     rcx, aMscorsvcDll; "mscorsvc.dll"
0x18002ce3b  call    LoadLibraryShim_0
0x18002ce40  mov     ebx, eax
0x18002ce42  test    eax, eax
0x18002ce44  js      short loc_18002CE72
0x18002ce46  mov     rcx, [rbp+57h+hModule]; hModule
0x18002ce4a  test    rcx, rcx
0x18002ce4d  jz      short loc_18002CE6D
0x18002ce4f  lea     rdx, aCorgetsvc_0; "CorGetSvc"
0x18002ce56  call    cs:__imp_GetProcAddress
0x18002ce5c  test    rax, rax
0x18002ce5f  jz      short loc_18002CE6D
0x18002ce61  mov     rcx, rdi
0x18002ce64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce69  mov     ebx, eax
0x18002ce6b  jmp     short loc_18002CE72
0x18002ce6d  mov     ebx, 80004005h
0x18002ce72  lea     rcx, [rbp+57h+var_B0]; this
0x18002ce76  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002ce7b  mov     eax, ebx
0x18002ce7d  add     rsp, 0B8h
0x18002ce84  pop     rdi
0x18002ce85  pop     rsi
0x18002ce86  pop     rbx
0x18002ce87  pop     rbp
0x18002ce88  retn
```
