# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x18003ae5c`
- end: `0x18003b056`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x1800026d0`
- `0x18003ab98`
- `0x18003ae5c`
- `0x18003b6dc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003af53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003af53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003af70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003af70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b01c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b01c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003afbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003afbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003afd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003afd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b008`

## string_xrefs

- `0x18003af4c`: `kernelbase.dll`
- `0x18003af66`: `TestCreate`

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
0x18003ae5c  mov     [rsp-8+arg_10], rbx
0x18003ae61  push    rbp
0x18003ae62  push    rsi
0x18003ae63  push    rdi
0x18003ae64  push    r12
0x18003ae66  push    r13
0x18003ae68  push    r14
0x18003ae6a  push    r15
0x18003ae6c  lea     rbp, [rsp-790h]
0x18003ae74  sub     rsp, 890h
0x18003ae7b  mov     rax, cs:__security_cookie
0x18003ae82  xor     rax, rsp
0x18003ae85  mov     [rbp+7C0h+var_40], rax
0x18003ae8c  mov     r13, rdx
0x18003ae8f  mov     rdi, rcx
0x18003ae92  lea     r14, [rcx+0C0h]
0x18003ae99  mov     rcx, r14; lpCriticalSection
0x18003ae9c  call    cs:__imp_EnterCriticalSection
0x18003aea3  nop     dword ptr [rax+rax+00h]
0x18003aea8  mov     [rsp+8C0h+pv], 0
0x18003aeb1  mov     [rsp+8C0h+var_868], 0
0x18003aeb6  lea     rax, [rsp+8C0h+var_867]
0x18003aebb  mov     [rbp+7C0h+var_60], rax
0x18003aec2  lea     rax, [rbp+7C0h+var_67]
0x18003aec9  mov     [rbp+7C0h+var_50], rax
0x18003aed0  mov     [rsp+8C0h+var_867], 80408040h
0x18003aed8  mov     [rsp+8C0h+var_863], 0
0x18003aedd  lea     rax, [rsp+8C0h+var_862]
0x18003aee2  mov     [rbp+7C0h+var_58], rax
0x18003aee9  test    dword ptr [rdi+40h], 800h
0x18003aef0  jz      short loc_18003AEFF
0x18003aef2  test    dword ptr [rdi+14h], 8000h
0x18003aef9  jnz     short loc_18003AEFF
0x18003aefb  mov     al, 1
0x18003aefd  jmp     short loc_18003AF01
0x18003aeff  xor     al, al
0x18003af01  lea     r15, [rdi+90h]
0x18003af08  test    al, al
0x18003af0a  jz      short loc_18003AF24
0x18003af0c  mov     r8d, 1
0x18003af12  lea     rdx, [rsp+8C0h+pv]
0x18003af17  mov     rcx, rdi
0x18003af1a  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18003af1f  mov     rsi, rax
0x18003af22  jmp     short loc_18003AF26
0x18003af24  xor     esi, esi
0x18003af26  mov     ebx, [rdi+14h]
0x18003af29  mov     r12b, [rdi+20h]
0x18003af2d  mov     eax, [rdi+10h]
0x18003af30  mov     [rsp+8C0h+var_880], eax
0x18003af34  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18003af3b  test    rax, rax
0x18003af3e  jnz     short loc_18003AF95
0x18003af40  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18003af47  test    rax, rax
0x18003af4a  jnz     short loc_18003AF66
0x18003af4c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003af53  call    cs:__imp_GetModuleHandleW
0x18003af5a  nop     dword ptr [rax+rax+00h]
0x18003af5f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18003af66  lea     rdx, aTestcreate; "TestCreate"
0x18003af6d  mov     rcx, rax; hModule
0x18003af70  call    cs:__imp_GetProcAddress
0x18003af77  nop     dword ptr [rax+rax+00h]
0x18003af7c  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18003af83  test    rax, rax
0x18003af86  jnz     short loc_18003AF95
0x18003af88  xorps   xmm0, xmm0
0x18003af8b  movdqu  xmmword ptr [r15], xmm0
0x18003af90  xor     r12d, r12d
0x18003af93  jmp     short loc_18003AFB3
0x18003af95  mov     [rsp+8C0h+var_898], r15
0x18003af9a  mov     [rsp+8C0h+var_8A0], rsi
0x18003af9f  mov     r9d, ebx
0x18003afa2  mov     r8b, r12b
0x18003afa5  xor     edx, edx
0x18003afa7  mov     ecx, [rsp+8C0h+var_880]
0x18003afab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afb0  mov     r12, rax
0x18003afb3  mov     rsi, [rdi+0F0h]
0x18003afba  test    rsi, rsi
0x18003afbd  jz      short loc_18003AFE3
0x18003afbf  call    cs:__imp_GetLastError
0x18003afc6  nop     dword ptr [rax+rax+00h]
0x18003afcb  mov     ebx, eax
0x18003afcd  mov     rcx, rsi
0x18003afd0  call    TestClose
0x18003afd5  mov     ecx, ebx; dwErrCode
0x18003afd7  call    cs:__imp_SetLastError
0x18003afde  nop     dword ptr [rax+rax+00h]
0x18003afe3  mov     [rdi+0F0h], r12
0x18003afea  mov     dword ptr [rdi+0B8h], 1
0x18003aff4  movups  xmm0, xmmword ptr [r15]
0x18003aff8  movdqu  xmmword ptr [r13+0], xmm0
0x18003affe  mov     rcx, [rsp+8C0h+pv]; pv
0x18003b003  test    rcx, rcx
0x18003b006  jz      short loc_18003B014
0x18003b008  call    cs:__imp_CoTaskMemFree
0x18003b00f  nop     dword ptr [rax+rax+00h]
0x18003b014  test    r14, r14
0x18003b017  jz      short loc_18003B028
0x18003b019  mov     rcx, r14; lpCriticalSection
0x18003b01c  call    cs:__imp_LeaveCriticalSection
0x18003b023  nop     dword ptr [rax+rax+00h]
0x18003b028  mov     rax, r13
0x18003b02b  mov     rcx, [rbp+7C0h+var_40]
0x18003b032  xor     rcx, rsp; StackCookie
0x18003b035  call    __security_check_cookie
0x18003b03a  mov     rbx, [rsp+8C0h+arg_10]
0x18003b042  add     rsp, 890h
0x18003b049  pop     r15
0x18003b04b  pop     r14
0x18003b04d  pop     r13
0x18003b04f  pop     r12
0x18003b051  pop     rdi
0x18003b052  pop     rsi
0x18003b053  pop     rbp
0x18003b054  retn
```
