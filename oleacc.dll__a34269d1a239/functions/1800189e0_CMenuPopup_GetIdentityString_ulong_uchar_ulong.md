# CMenuPopup::GetIdentityString(ulong,uchar * *,ulong *)

- ea: `0x1800189e0`
- end: `0x180018aee`
- name: `?GetIdentityString@CMenuPopup@@UEAAJKPEAPEAEPEAK@Z`
- size: `270`
- prototype: `__int64 __fastcall(CMenuPopup *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800189e0`
- `0x18001e4c0`
- `0x18001efc4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018a25`
- `USER32!GetWindowThreadProcessId` at `0x180018a81`
- `USER32!GetWindowThreadProcessId` at `0x180018a81`

## pseudocode

```c
__int64 __fastcall CMenuPopup::GetIdentityString(CMenuPopup *this, int a2, unsigned __int8 **a3, unsigned int *a4)
{
  _DWORD *v8; // rbx
  DWORD v9; // ecx
  __int64 result; // rax
  int v11; // eax
  DWORD dwProcessId[4]; // [rsp+20h] [rbp-88h] BYREF
  struct tagGUITHREADINFO v13; // [rsp+30h] [rbp-78h] BYREF

  *a3 = 0;
  *a4 = 0;
  v8 = CoTaskMemAlloc(0x10u);
  if ( !v8 )
    return 2147942414LL;
  memset_0(&v13, 0, sizeof(v13));
  if ( !lpfnGuiThreadInfo || (v13.cbSize = 72, !lpfnGuiThreadInfo(0, &v13)) )
  {
    CoTaskMemFree(v8);
    return 2147500037LL;
  }
  dwProcessId[0] = 0;
  GetWindowThreadProcessId(v13.hwndActive, dwProcessId);
  v9 = dwProcessId[0];
  if ( !dwProcessId[0] )
    return 2147500037LL;
  v11 = *((_DWORD *)this + 24);
  *v8 = -2147483646;
  v8[1] = v9;
  v8[2] = v11;
  result = 0;
  v8[3] = a2;
  *a3 = (unsigned __int8 *)v8;
  *a4 = 16;
  return result;
}

```

## disassembly

```asm
0x1800189e0  mov     [rsp+arg_0], rbx
0x1800189e5  mov     [rsp+arg_8], rbp
0x1800189ea  push    rsi
0x1800189eb  push    rdi
0x1800189ec  push    r14
0x1800189ee  sub     rsp, 90h
0x1800189f5  mov     rax, cs:__security_cookie
0x1800189fc  xor     rax, rsp
0x1800189ff  mov     [rsp+0A8h+var_28], rax
0x180018a07  mov     r14, rcx
0x180018a0a  mov     qword ptr [r8], 0
0x180018a11  mov     ecx, 10h; cb
0x180018a16  mov     dword ptr [r9], 0
0x180018a1d  mov     rsi, r9
0x180018a20  mov     rdi, r8
0x180018a23  mov     ebp, edx
0x180018a25  call    cs:__imp_CoTaskMemAlloc
0x180018a2b  mov     rbx, rax
0x180018a2e  test    rax, rax
0x180018a31  jz      loc_180018ADC
0x180018a37  xor     edx, edx; Val
0x180018a39  lea     rcx, [rsp+0A8h+var_78]; void *
0x180018a3e  lea     r8d, [rdx+48h]; Size
0x180018a42  call    memset_0
0x180018a47  mov     rax, cs:?lpfnGuiThreadInfo@@3P6AHKPEAUtagGUITHREADINFO@@@ZEA; int (*lpfnGuiThreadInfo)(ulong,tagGUITHREADINFO *)
0x180018a4e  test    rax, rax
0x180018a51  jz      loc_180018AE3
0x180018a57  lea     rdx, [rsp+0A8h+var_78]
0x180018a5c  mov     [rsp+0A8h+var_78], 48h ; 'H'
0x180018a64  xor     ecx, ecx
0x180018a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a6b  test    eax, eax
0x180018a6d  jz      short loc_180018AE3
0x180018a6f  mov     rcx, [rsp+0A8h+hWnd]; hWnd
0x180018a74  lea     rdx, [rsp+0A8h+dwProcessId]; lpdwProcessId
0x180018a79  mov     [rsp+0A8h+dwProcessId], 0
0x180018a81  call    cs:__imp_GetWindowThreadProcessId
0x180018a87  mov     ecx, [rsp+0A8h+dwProcessId]
0x180018a8b  test    ecx, ecx
0x180018a8d  jnz     short loc_180018ABC
0x180018a8f  mov     eax, 80004005h
0x180018a94  mov     rcx, [rsp+0A8h+var_28]
0x180018a9c  xor     rcx, rsp; StackCookie
0x180018a9f  call    __security_check_cookie
0x180018aa4  lea     r11, [rsp+0A8h+var_18]
0x180018aac  mov     rbx, [r11+20h]
0x180018ab0  mov     rbp, [r11+28h]
0x180018ab4  mov     rsp, r11
0x180018ab7  pop     r14
0x180018ab9  pop     rdi
0x180018aba  pop     rsi
0x180018abb  retn
0x180018abc  mov     eax, [r14+60h]
0x180018ac0  mov     dword ptr [rbx], 80000002h
0x180018ac6  mov     [rbx+4], ecx
0x180018ac9  mov     [rbx+8], eax
0x180018acc  xor     eax, eax
0x180018ace  mov     [rbx+0Ch], ebp
0x180018ad1  mov     [rdi], rbx
0x180018ad4  mov     dword ptr [rsi], 10h
0x180018ada  jmp     short loc_180018A94
0x180018adc  mov     eax, 8007000Eh
0x180018ae1  jmp     short loc_180018A94
0x180018ae3  mov     rcx, rbx; pv
0x180018ae6  call    cs:__imp_CoTaskMemFree
0x180018aec  jmp     short loc_180018A8F
```
