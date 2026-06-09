# StartDiagnosis

- ea: `0x180039c3c`
- end: `0x180039d1c`
- name: `StartDiagnosis`
- size: `224`
- prototype: `__int64 __fastcall(__int128 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cb00`

## callees

- `0x180039c3c`
- `0x18004d110`

## import_xrefs

- `USER32!GetDesktopWindow` at `0x180039cd8`
- `USER32!GetDesktopWindow` at `0x180039cd8`
- `NDFAPI!NdfExecuteDiagnosis` at `0x180039ce6`
- `NDFAPI!NdfExecuteDiagnosis` at `0x180039ce6`
- `NDFAPI!NdfCreateIncident` at `0x180039ccc`
- `NDFAPI!NdfCreateIncident` at `0x180039ccc`
- `NDFAPI!NdfCloseIncident` at `0x180039cf3`
- `NDFAPI!NdfCloseIncident` at `0x180039cf3`

## pseudocode

```c
__int64 __fastcall StartDiagnosis(__int128 *a1, int a2)
{
  __int128 v2; // xmm0
  HRESULT v3; // eax
  unsigned __int16 v4; // bx
  HWND DesktopWindow; // rax
  NDFHANDLE handle; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v9; // [rsp+C0h] [rbp-40h]
  int v10; // [rsp+C8h] [rbp-38h]
  __int128 v11; // [rsp+D0h] [rbp-30h]
  const wchar_t *v12; // [rsp+150h] [rbp+50h]
  int v13; // [rsp+158h] [rbp+58h]
  int v14; // [rsp+160h] [rbp+60h]

  v2 = *a1;
  v14 = a2;
  attributes.pwszName = L"HelperClassName";
  handle = 0;
  v9 = L"ConnectionGuid";
  attributes.type = AT_STRING;
  v12 = L"ErrorCode";
  attributes.Int64 = (LONGLONG)L"CRasDiagHelper";
  v10 = 11;
  v11 = v2;
  v13 = 7;
  v3 = NdfCreateIncident(L"CRasDiagHelper", 3u, &attributes, &handle);
  v4 = v3;
  if ( v3 >= 0 )
  {
    DesktopWindow = GetDesktopWindow();
    v4 = NdfExecuteDiagnosis(handle, DesktopWindow);
    NdfCloseIncident(handle);
  }
  return v4;
}

```

## disassembly

```asm
0x180039c3c  mov     [rsp-8+arg_0], rbx
0x180039c41  push    rbp
0x180039c42  lea     rbp, [rsp-0F0h]
0x180039c4a  sub     rsp, 1F0h
0x180039c51  mov     rax, cs:__security_cookie
0x180039c58  xor     rax, rsp
0x180039c5b  mov     [rbp+0F0h+var_10], rax
0x180039c62  movaps  xmm0, xmmword ptr [rcx]
0x180039c65  lea     r10, helperClassName; "CRasDiagHelper"
0x180039c6c  lea     rax, aHelperclassnam; "HelperClassName"
0x180039c73  mov     [rbp+0F0h+var_90], edx
0x180039c76  mov     [rsp+1F0h+attributes.pwszName], rax
0x180039c7b  lea     r9, [rsp+1F0h+handle]; handle
0x180039c80  lea     rax, aConnectionguid; "ConnectionGuid"
0x180039c87  mov     [rsp+1F0h+handle], 0
0x180039c90  mov     [rbp+0F0h+var_130], rax
0x180039c94  lea     r8, [rsp+1F0h+attributes]; attributes
0x180039c99  lea     rax, aErrorcode; "ErrorCode"
0x180039ca0  mov     [rsp+1F0h+attributes.type], 0Ah
0x180039ca8  mov     edx, 3; celt
0x180039cad  mov     [rbp+0F0h+var_A0], rax
0x180039cb1  mov     rcx, r10; helperClassName
0x180039cb4  mov     qword ptr [rsp+1F0h+attributes.10h], r10
0x180039cb9  mov     [rbp+0F0h+var_128], 0Bh
0x180039cc0  movdqu  [rbp+0F0h+var_120], xmm0
0x180039cc5  mov     [rbp+0F0h+var_98], 7
0x180039ccc  call    cs:__imp_NdfCreateIncident
0x180039cd2  mov     ebx, eax
0x180039cd4  test    eax, eax
0x180039cd6  js      short loc_180039CF9
0x180039cd8  call    cs:__imp_GetDesktopWindow
0x180039cde  mov     rcx, [rsp+1F0h+handle]; handle
0x180039ce3  mov     rdx, rax; hwnd
0x180039ce6  call    cs:__imp_NdfExecuteDiagnosis
0x180039cec  mov     rcx, [rsp+1F0h+handle]; handle
0x180039cf1  mov     ebx, eax
0x180039cf3  call    cs:__imp_NdfCloseIncident
0x180039cf9  movzx   eax, bx
0x180039cfc  mov     rcx, [rbp+0F0h+var_10]
0x180039d03  xor     rcx, rsp; StackCookie
0x180039d06  call    __security_check_cookie
0x180039d0b  mov     rbx, [rsp+1F0h+arg_0]
0x180039d13  add     rsp, 1F0h
0x180039d1a  pop     rbp
0x180039d1b  retn
```
