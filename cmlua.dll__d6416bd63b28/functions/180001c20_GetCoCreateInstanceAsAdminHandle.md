# _GetCoCreateInstanceAsAdminHandle

- ea: `0x180001c20`
- end: `0x180001d2d`
- name: `_GetCoCreateInstanceAsAdminHandle`
- size: `269`
- prototype: `__int64 __fastcall(HWND hWnd, LPCWSTR lpCaption, GUID *rguid, IID *riid, void **ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001b90`
- `0x180001c20`
- `0x180001e40`
- `0x1800054b0`

## import_xrefs

- `ole32!CoGetObject` at `0x180001cea`
- `ole32!CoGetObject` at `0x180001cea`
- `ole32!StringFromGUID2` at `0x180001c83`
- `ole32!StringFromGUID2` at `0x180001c83`

## pseudocode

```c
__int64 __fastcall GetCoCreateInstanceAsAdminHandle(HWND hWnd, LPCWSTR lpCaption, GUID *rguid, IID *riid, void **ppv)
{
  HRESULT Object; // ebx
  BIND_OPTS pBindOptions[3]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[304]; // [rsp+C0h] [rbp-40h] BYREF

  *ppv = 0;
  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( !StringFromGUID2(rguid, sz, 50) )
  {
    Object = -2147024882;
LABEL_6:
    ThrowErrorBox(hWnd, lpCaption);
    return (unsigned int)Object;
  }
  Object = StringCchPrintfW(
             pszName,
             0x12Cu,
             L"Elevation:Administrator!new:%s",
             sz,
             *(_QWORD *)&pBindOptions[0].cbStruct,
             *(_QWORD *)&pBindOptions[0].grfMode,
             *(_OWORD *)&pBindOptions[1],
             *(_OWORD *)&pBindOptions[2]);
  if ( Object < 0
    || (pBindOptions[0].cbStruct = 48,
        *(_QWORD *)&pBindOptions[2].grfMode = hWnd,
        pBindOptions[1].grfFlags = 4,
        *(_OWORD *)&pBindOptions[0].grfFlags = 0,
        *(_OWORD *)&pBindOptions[1].grfMode = 0,
        Object = CoGetObject(pszName, pBindOptions, riid, ppv),
        Object < 0) )
  {
    if ( Object != -2147023673 )
      goto LABEL_6;
  }
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180001c20  push    rbp
0x180001c22  push    rbx
0x180001c23  push    rsi
0x180001c24  push    rdi
0x180001c25  push    r14
0x180001c27  push    r15
0x180001c29  lea     rbp, [rsp-238h]
0x180001c31  sub     rsp, 338h
0x180001c38  mov     rax, cs:__security_cookie
0x180001c3f  xor     rax, rsp
0x180001c42  mov     [rbp+260h+var_40], rax
0x180001c49  mov     r14, [rbp+260h+ppv]
0x180001c50  xorps   xmm0, xmm0
0x180001c53  mov     rax, r8
0x180001c56  mov     rsi, rdx
0x180001c59  mov     rdi, rcx
0x180001c5c  lea     rdx, [rsp+360h+sz]; lpsz
0x180001c61  mov     r8d, 32h ; '2'; cchMax
0x180001c67  mov     rcx, rax; rguid
0x180001c6a  mov     qword ptr [r14], 0
0x180001c71  mov     r15, r9
0x180001c74  movups  xmmword ptr [rsp+360h+pBindOptions.cbStruct], xmm0
0x180001c79  movups  [rsp+360h+var_330], xmm0
0x180001c7e  movups  [rsp+360h+var_320], xmm0
0x180001c83  call    cs:__imp_StringFromGUID2
0x180001c89  test    eax, eax
0x180001c8b  jnz     short loc_180001C94
0x180001c8d  mov     ebx, 8007000Eh
0x180001c92  jmp     short loc_180001CFE
0x180001c94  lea     r9, [rsp+360h+sz]
0x180001c99  mov     edx, 12Ch; unsigned __int64
0x180001c9e  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180001ca5  lea     rcx, [rbp+260h+pszName]; unsigned __int16 *
0x180001ca9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001cae  mov     ebx, eax
0x180001cb0  test    eax, eax
0x180001cb2  js      short loc_180001CF6
0x180001cb4  xorps   xmm0, xmm0
0x180001cb7  mov     [rsp+360h+pBindOptions.cbStruct], 30h ; '0'
0x180001cbf  xorps   xmm1, xmm1
0x180001cc2  mov     qword ptr [rsp+360h+var_320+8], rdi
0x180001cc7  mov     r9, r14; ppv
0x180001cca  mov     dword ptr [rsp+360h+var_330+4], 4
0x180001cd2  mov     r8, r15; riid
0x180001cd5  lea     rdx, [rsp+360h+pBindOptions]; pBindOptions
0x180001cda  lea     rcx, [rbp+260h+pszName]; pszName
0x180001cde  movdqu  xmmword ptr [rsp+360h+pBindOptions.grfFlags], xmm0
0x180001ce4  movdqu  [rsp+360h+var_330+8], xmm1
0x180001cea  call    cs:__imp_CoGetObject
0x180001cf0  mov     ebx, eax
0x180001cf2  test    eax, eax
0x180001cf4  jns     short loc_180001D0C
0x180001cf6  cmp     ebx, 800704C7h
0x180001cfc  jz      short loc_180001D0C
0x180001cfe  mov     r8d, ebx
0x180001d01  mov     rdx, rsi; lpCaption
0x180001d04  mov     rcx, rdi; hWnd
0x180001d07  call    _ThrowErrorBox
0x180001d0c  mov     eax, ebx
0x180001d0e  mov     rcx, [rbp+260h+var_40]
0x180001d15  xor     rcx, rsp; StackCookie
0x180001d18  call    __security_check_cookie
0x180001d1d  add     rsp, 338h
0x180001d24  pop     r15
0x180001d26  pop     r14
0x180001d28  pop     rdi
0x180001d29  pop     rsi
0x180001d2a  pop     rbx
0x180001d2b  pop     rbp
0x180001d2c  retn
```
