# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x14003e260`
- end: `0x14003e45a`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140039cfc`
- `0x140048db0`

## callees

- `0x140003450`
- `0x14000d7ec`
- `0x140025a50`
- `0x14003e260`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e374`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e374`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14003e357`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14003e357`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003e2a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003e2a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003e420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003e420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e3c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e3db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e3db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e40c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e40c`

## string_xrefs

- `0x14003e350`: `kernelbase.dll`
- `0x14003e36a`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  __int64 v5; // r8
  bool v6; // al
  _OWORD *v7; // r15
  __int64 v8; // rsi
  unsigned int v9; // ebx
  char v10; // r12
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r12
  __int64 v14; // rsi
  DWORD LastError; // ebx
  unsigned int v17; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+59h] [rbp-A7h] BYREF
  char v21; // [rsp+5Dh] [rbp-A3h]
  char v22; // [rsp+5Eh] [rbp-A2h] BYREF
  char v23; // [rsp+859h] [rbp+759h] BYREF
  int *v24; // [rsp+860h] [rbp+760h]
  char *v25; // [rsp+868h] [rbp+768h]
  char *v26; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v19 = 0;
  v24 = &v20;
  v26 = &v23;
  v20 = -2143256512;
  v21 = 0;
  v25 = &v22;
  v6 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (_OWORD *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v17 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_13;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_13:
    LOBYTE(v5) = v10;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v17,
            0,
            v5,
            v9,
            v8,
            a1 + 144);
  }
  else
  {
    *v7 = 0;
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 240);
  if ( v14 )
  {
    LastError = GetLastError();
    TestClose(v14);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 240) = v13;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v7;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x14003e260  mov     [rsp-8+arg_10], rbx
0x14003e265  push    rbp
0x14003e266  push    rsi
0x14003e267  push    rdi
0x14003e268  push    r12
0x14003e26a  push    r13
0x14003e26c  push    r14
0x14003e26e  push    r15
0x14003e270  lea     rbp, [rsp-790h]
0x14003e278  sub     rsp, 890h
0x14003e27f  mov     rax, cs:__security_cookie
0x14003e286  xor     rax, rsp
0x14003e289  mov     [rbp+7C0h+var_40], rax
0x14003e290  mov     r13, rdx
0x14003e293  mov     rdi, rcx
0x14003e296  lea     r14, [rcx+0C0h]
0x14003e29d  mov     rcx, r14; lpCriticalSection
0x14003e2a0  call    cs:__imp_EnterCriticalSection
0x14003e2a7  nop     dword ptr [rax+rax+00h]
0x14003e2ac  mov     [rsp+8C0h+pv], 0
0x14003e2b5  mov     [rsp+8C0h+var_868], 0
0x14003e2ba  lea     rax, [rsp+8C0h+var_867]
0x14003e2bf  mov     [rbp+7C0h+var_60], rax
0x14003e2c6  lea     rax, [rbp+7C0h+var_67]
0x14003e2cd  mov     [rbp+7C0h+var_50], rax
0x14003e2d4  mov     [rsp+8C0h+var_867], 80408040h
0x14003e2dc  mov     [rsp+8C0h+var_863], 0
0x14003e2e1  lea     rax, [rsp+8C0h+var_862]
0x14003e2e6  mov     [rbp+7C0h+var_58], rax
0x14003e2ed  test    dword ptr [rdi+40h], 800h
0x14003e2f4  jz      short loc_14003E303
0x14003e2f6  test    dword ptr [rdi+14h], 8000h
0x14003e2fd  jnz     short loc_14003E303
0x14003e2ff  mov     al, 1
0x14003e301  jmp     short loc_14003E305
0x14003e303  xor     al, al
0x14003e305  lea     r15, [rdi+90h]
0x14003e30c  test    al, al
0x14003e30e  jz      short loc_14003E328
0x14003e310  mov     r8d, 1
0x14003e316  lea     rdx, [rsp+8C0h+pv]
0x14003e31b  mov     rcx, rdi
0x14003e31e  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14003e323  mov     rsi, rax
0x14003e326  jmp     short loc_14003E32A
0x14003e328  xor     esi, esi
0x14003e32a  mov     ebx, [rdi+14h]
0x14003e32d  mov     r12b, [rdi+20h]
0x14003e331  mov     eax, [rdi+10h]
0x14003e334  mov     [rsp+8C0h+var_880], eax
0x14003e338  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14003e33f  test    rax, rax
0x14003e342  jnz     short loc_14003E399
0x14003e344  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14003e34b  test    rax, rax
0x14003e34e  jnz     short loc_14003E36A
0x14003e350  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14003e357  call    cs:__imp_GetModuleHandleW
0x14003e35e  nop     dword ptr [rax+rax+00h]
0x14003e363  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14003e36a  lea     rdx, aTestcreate; "TestCreate"
0x14003e371  mov     rcx, rax; hModule
0x14003e374  call    cs:__imp_GetProcAddress
0x14003e37b  nop     dword ptr [rax+rax+00h]
0x14003e380  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14003e387  test    rax, rax
0x14003e38a  jnz     short loc_14003E399
0x14003e38c  xorps   xmm0, xmm0
0x14003e38f  movdqu  xmmword ptr [r15], xmm0
0x14003e394  xor     r12d, r12d
0x14003e397  jmp     short loc_14003E3B7
0x14003e399  mov     [rsp+8C0h+var_898], r15
0x14003e39e  mov     [rsp+8C0h+var_8A0], rsi
0x14003e3a3  mov     r9d, ebx
0x14003e3a6  mov     r8b, r12b
0x14003e3a9  xor     edx, edx
0x14003e3ab  mov     ecx, [rsp+8C0h+var_880]
0x14003e3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e3b4  mov     r12, rax
0x14003e3b7  mov     rsi, [rdi+0F0h]
0x14003e3be  test    rsi, rsi
0x14003e3c1  jz      short loc_14003E3E7
0x14003e3c3  call    cs:__imp_GetLastError
0x14003e3ca  nop     dword ptr [rax+rax+00h]
0x14003e3cf  mov     ebx, eax
0x14003e3d1  mov     rcx, rsi
0x14003e3d4  call    TestClose
0x14003e3d9  mov     ecx, ebx; dwErrCode
0x14003e3db  call    cs:__imp_SetLastError
0x14003e3e2  nop     dword ptr [rax+rax+00h]
0x14003e3e7  mov     [rdi+0F0h], r12
0x14003e3ee  mov     dword ptr [rdi+0B8h], 1
0x14003e3f8  movups  xmm0, xmmword ptr [r15]
0x14003e3fc  movdqu  xmmword ptr [r13+0], xmm0
0x14003e402  mov     rcx, [rsp+8C0h+pv]; pv
0x14003e407  test    rcx, rcx
0x14003e40a  jz      short loc_14003E418
0x14003e40c  call    cs:__imp_CoTaskMemFree
0x14003e413  nop     dword ptr [rax+rax+00h]
0x14003e418  test    r14, r14
0x14003e41b  jz      short loc_14003E42C
0x14003e41d  mov     rcx, r14; lpCriticalSection
0x14003e420  call    cs:__imp_LeaveCriticalSection
0x14003e427  nop     dword ptr [rax+rax+00h]
0x14003e42c  mov     rax, r13
0x14003e42f  mov     rcx, [rbp+7C0h+var_40]
0x14003e436  xor     rcx, rsp; StackCookie
0x14003e439  call    __security_check_cookie
0x14003e43e  mov     rbx, [rsp+8C0h+arg_10]
0x14003e446  add     rsp, 890h
0x14003e44d  pop     r15
0x14003e44f  pop     r14
0x14003e451  pop     r13
0x14003e453  pop     r12
0x14003e455  pop     rdi
0x14003e456  pop     rsi
0x14003e457  pop     rbp
0x14003e458  retn
```
