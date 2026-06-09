# NtWin32LiveSystemProvider::GetThreadContextEx(void *,void *,void *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong,bool)

- ea: `0x180024c90`
- end: `0x180024e0f`
- name: `?GetThreadContextEx@NtWin32LiveSystemProvider@@UEAAJPEAX00KPEA_K11K_N@Z`
- size: `383`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *__hidden this, void *, void *, void *, unsigned int, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180024c30`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180013790`
- `0x180024c90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024d98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024d98`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::GetThreadContextEx(
        NtWin32LiveSystemProvider *this,
        void *a2,
        void *a3,
        void *a4,
        unsigned int a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        unsigned int a9,
        bool a10)
{
  char v10; // di
  unsigned int ThreadContext; // ebp
  int v17; // eax
  __int64 v18; // [rsp+50h] [rbp-338h] BYREF
  int v19; // [rsp+60h] [rbp-328h] BYREF
  _BYTE v20[192]; // [rsp+64h] [rbp-324h] BYREF
  unsigned int v21; // [rsp+124h] [rbp-264h]

  v10 = 0;
  v18 = 0;
  if ( (*((int (__fastcall **)(void *, __int64, __int64 *, __int64, _QWORD))this + 107))(a2, 26, &v18, 8, 0) >= 0 && v18 )
  {
    v10 = 1;
  }
  else if ( a10 )
  {
    return 2147500037LL;
  }
  ThreadContext = Win32LiveSystemProvider::GetThreadContextEx(this, a2, a3, a4, a5, a6, a7, a8, a9);
  if ( v10 )
  {
    if ( a10 )
    {
      memset_0(v20, 0, 0x2C8u);
      v19 = 65599;
      if ( *(&g_NtDllCallsMdwd + 1) )
      {
        v17 = (*(&g_NtDllCallsMdwd + 1))(a3, &v19);
        if ( v17 < 0 )
        {
          if ( *((_QWORD *)this + 45) )
            (*((void (__fastcall **)(_QWORD))this + 45))((unsigned int)v17);
        }
        else
        {
          *a7 = v21;
        }
      }
    }
  }
  return ThreadContext;
}

```

## disassembly

```asm
0x180024c90  push    rbx
0x180024c92  push    rbp
0x180024c93  push    rsi
0x180024c94  push    rdi
0x180024c95  push    r12
0x180024c97  push    r13
0x180024c99  push    r14
0x180024c9b  push    r15
0x180024c9d  sub     rsp, 348h
0x180024ca4  mov     rax, cs:__security_cookie
0x180024cab  xor     rax, rsp
0x180024cae  mov     [rsp+388h+var_58], rax
0x180024cb6  mov     r13, [rsp+388h+arg_28]
0x180024cbe  xor     edi, edi
0x180024cc0  mov     r14, [rsp+388h+arg_30]
0x180024cc8  mov     rsi, rcx
0x180024ccb  mov     rbp, rdx
0x180024cce  mov     [rsp+388h+var_338], rdi
0x180024cd3  mov     r12, r9
0x180024cd6  mov     qword ptr [rsp+388h+var_368], rdi
0x180024cdb  mov     r15, r8
0x180024cde  lea     r9d, [rdi+8]
0x180024ce2  mov     rax, [rsi+358h]
0x180024ce9  lea     edx, [rdi+1Ah]
0x180024cec  lea     r8, [rsp+388h+var_338]
0x180024cf1  mov     rcx, rbp
0x180024cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cf9  mov     bl, [rsp+388h+arg_48]
0x180024d00  test    eax, eax
0x180024d02  js      loc_180024DDF
0x180024d08  cmp     [rsp+388h+var_338], rdi
0x180024d0d  jz      loc_180024DDF
0x180024d13  mov     dil, 1
0x180024d16  mov     eax, [rsp+388h+arg_40]
0x180024d1d  mov     r9, r12; void *
0x180024d20  mov     [rsp+388h+var_340], bl; bool
0x180024d24  mov     r8, r15; void *
0x180024d27  mov     [rsp+388h+var_348], eax; unsigned int
0x180024d2b  mov     rdx, rbp; void *
0x180024d2e  mov     rax, [rsp+388h+arg_38]
0x180024d36  mov     rcx, rsi; this
0x180024d39  mov     [rsp+388h+var_350], rax; unsigned __int64 *
0x180024d3e  mov     eax, [rsp+388h+arg_20]
0x180024d45  mov     [rsp+388h+var_358], r14; unsigned __int64 *
0x180024d4a  mov     [rsp+388h+var_360], r13; unsigned __int64 *
0x180024d4f  mov     [rsp+388h+var_368], eax; unsigned int
0x180024d53  call    ?GetThreadContextEx@Win32LiveSystemProvider@@UEAAJPEAX00KPEA_K11K_N@Z; Win32LiveSystemProvider::GetThreadContextEx(void *,void *,void *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong,bool)
0x180024d58  mov     ebp, eax
0x180024d5a  test    dil, dil
0x180024d5d  jz      short loc_180024DB9
0x180024d5f  test    bl, bl
0x180024d61  jz      short loc_180024DB9
0x180024d63  xor     edx, edx; Val
0x180024d65  lea     rcx, [rsp+388h+var_324]; void *
0x180024d6a  mov     r8d, 2C8h; Size
0x180024d70  call    memset_0
0x180024d75  mov     rcx, qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C+8; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180024d7c  mov     [rsp+388h+var_328], 1003Fh
0x180024d84  test    rcx, rcx
0x180024d87  jz      short loc_180024DB9
0x180024d89  mov     rax, qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C+8; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180024d90  test    rax, rax
0x180024d93  jnz     short loc_180024DEE
0x180024d95  lea     ecx, [rax+32h]; dwErrCode
0x180024d98  call    cs:__imp_SetLastError
0x180024d9e  mov     eax, 0C00000BBh
0x180024da3  mov     rdx, [rsi+168h]
0x180024daa  test    rdx, rdx
0x180024dad  jz      short loc_180024DB9
0x180024daf  mov     ecx, eax
0x180024db1  mov     rax, rdx
0x180024db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024db9  mov     eax, ebp
0x180024dbb  mov     rcx, [rsp+388h+var_58]
0x180024dc3  xor     rcx, rsp; StackCookie
0x180024dc6  call    __security_check_cookie
0x180024dcb  add     rsp, 348h
0x180024dd2  pop     r15
0x180024dd4  pop     r14
0x180024dd6  pop     r13
0x180024dd8  pop     r12
0x180024dda  pop     rdi
0x180024ddb  pop     rsi
0x180024ddc  pop     rbp
0x180024ddd  pop     rbx
0x180024dde  retn
0x180024ddf  test    bl, bl
0x180024de1  jz      loc_180024D16
0x180024de7  mov     eax, 80004005h
0x180024dec  jmp     short loc_180024DBB
0x180024dee  mov     rax, qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C+8; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180024df5  lea     rdx, [rsp+388h+var_328]
0x180024dfa  mov     rcx, r15
0x180024dfd  call    rax
0x180024dff  test    eax, eax
0x180024e01  js      short loc_180024DA3
0x180024e03  mov     eax, [rsp+388h+var_264]
0x180024e0a  mov     [r14], rax
0x180024e0d  jmp     short loc_180024DB9
```
