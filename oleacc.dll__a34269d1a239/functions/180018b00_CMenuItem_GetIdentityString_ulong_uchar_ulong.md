# CMenuItem::GetIdentityString(ulong,uchar * *,ulong *)

- ea: `0x180018b00`
- end: `0x180018c11`
- name: `?GetIdentityString@CMenuItem@@UEAAJKPEAPEAEPEAK@Z`
- size: `273`
- prototype: `__int64 __fastcall(CMenuItem *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180018b00`
- `0x18001e4c0`
- `0x18001efc4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018bfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018bfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018b44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018b44`
- `USER32!GetWindowThreadProcessId` at `0x180018ba0`
- `USER32!GetWindowThreadProcessId` at `0x180018ba0`

## pseudocode

```c
__int64 __fastcall CMenuItem::GetIdentityString(CMenuItem *this, int a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned __int8 *v7; // rbx
  DWORD v8; // edx
  int v9; // eax
  int v10; // ecx
  __int64 result; // rax
  DWORD dwProcessId[4]; // [rsp+20h] [rbp-88h] BYREF
  struct tagGUITHREADINFO v13; // [rsp+30h] [rbp-78h] BYREF

  *a3 = 0;
  *a4 = 0;
  if ( a2 )
    return 2147942487LL;
  v7 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
  if ( !v7 )
    return 2147942414LL;
  memset_0(&v13, 0, sizeof(v13));
  if ( lpfnGuiThreadInfo
    && (v13.cbSize = 72, lpfnGuiThreadInfo(0, &v13))
    && (dwProcessId[0] = 0, GetWindowThreadProcessId(v13.hwndActive, dwProcessId), (v8 = dwProcessId[0]) != 0) )
  {
    v9 = *((_DWORD *)this + 24);
    v10 = *((_DWORD *)this + 29);
    *(_DWORD *)v7 = -2147483646;
    *((_DWORD *)v7 + 1) = v8;
    *((_DWORD *)v7 + 2) = v9;
    result = 0;
    *((_DWORD *)v7 + 3) = v10;
    *a3 = v7;
    *a4 = 16;
  }
  else
  {
    CoTaskMemFree(v7);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180018b00  mov     [rsp+arg_0], rbx
0x180018b05  push    rsi
0x180018b06  push    rdi
0x180018b07  push    r14
0x180018b09  sub     rsp, 90h
0x180018b10  mov     rax, cs:__security_cookie
0x180018b17  xor     rax, rsp
0x180018b1a  mov     [rsp+0A8h+var_28], rax
0x180018b22  mov     qword ptr [r8], 0
0x180018b29  mov     r14, r9
0x180018b2c  mov     dword ptr [r9], 0
0x180018b33  mov     rsi, r8
0x180018b36  mov     rdi, rcx
0x180018b39  test    edx, edx
0x180018b3b  jnz     loc_180018BF3
0x180018b41  lea     ecx, [rdx+10h]; cb
0x180018b44  call    cs:__imp_CoTaskMemAlloc
0x180018b4a  mov     rbx, rax
0x180018b4d  test    rax, rax
0x180018b50  jz      loc_180018C0A
0x180018b56  xor     edx, edx; Val
0x180018b58  lea     rcx, [rsp+0A8h+var_78]; void *
0x180018b5d  lea     r8d, [rdx+48h]; Size
0x180018b61  call    memset_0
0x180018b66  mov     rax, cs:?lpfnGuiThreadInfo@@3P6AHKPEAUtagGUITHREADINFO@@@ZEA; int (*lpfnGuiThreadInfo)(ulong,tagGUITHREADINFO *)
0x180018b6d  test    rax, rax
0x180018b70  jz      loc_180018BFA
0x180018b76  lea     rdx, [rsp+0A8h+var_78]
0x180018b7b  mov     [rsp+0A8h+var_78], 48h ; 'H'
0x180018b83  xor     ecx, ecx
0x180018b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b8a  test    eax, eax
0x180018b8c  jz      short loc_180018BFA
0x180018b8e  mov     rcx, [rsp+0A8h+hWnd]; hWnd
0x180018b93  lea     rdx, [rsp+0A8h+dwProcessId]; lpdwProcessId
0x180018b98  mov     [rsp+0A8h+dwProcessId], 0
0x180018ba0  call    cs:__imp_GetWindowThreadProcessId
0x180018ba6  mov     edx, [rsp+0A8h+dwProcessId]
0x180018baa  test    edx, edx
0x180018bac  jz      short loc_180018BFA
0x180018bae  mov     eax, [rdi+60h]
0x180018bb1  mov     ecx, [rdi+74h]
0x180018bb4  mov     dword ptr [rbx], 80000002h
0x180018bba  mov     [rbx+4], edx
0x180018bbd  mov     [rbx+8], eax
0x180018bc0  xor     eax, eax
0x180018bc2  mov     [rbx+0Ch], ecx
0x180018bc5  mov     [rsi], rbx
0x180018bc8  mov     dword ptr [r14], 10h
0x180018bcf  mov     rcx, [rsp+0A8h+var_28]
0x180018bd7  xor     rcx, rsp; StackCookie
0x180018bda  call    __security_check_cookie
0x180018bdf  mov     rbx, [rsp+0A8h+arg_0]
0x180018be7  add     rsp, 90h
0x180018bee  pop     r14
0x180018bf0  pop     rdi
0x180018bf1  pop     rsi
0x180018bf2  retn
0x180018bf3  mov     eax, 80070057h
0x180018bf8  jmp     short loc_180018BCF
0x180018bfa  mov     rcx, rbx; pv
0x180018bfd  call    cs:__imp_CoTaskMemFree
0x180018c03  mov     eax, 80004005h
0x180018c08  jmp     short loc_180018BCF
0x180018c0a  mov     eax, 8007000Eh
0x180018c0f  jmp     short loc_180018BCF
```
