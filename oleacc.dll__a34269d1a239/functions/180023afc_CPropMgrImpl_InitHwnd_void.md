# CPropMgrImpl::InitHwnd(void)

- ea: `0x180023afc`
- end: `0x180023c20`
- name: `?InitHwnd@CPropMgrImpl@@QEAAHXZ`
- size: `292`
- prototype: `__int64 __fastcall(CPropMgrImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001102c`

## callees

- `0x18001e4c0`
- `0x18001f024`
- `0x180023afc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023b24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023b24`
- `USER32!DefWindowProcW` at `0x180023b4b`
- `USER32!RegisterClassW` at `0x180023b95`
- `USER32!RegisterClassW` at `0x180023b95`
- `USER32!CreateWindowExW` at `0x180023be7`
- `USER32!CreateWindowExW` at `0x180023be7`

## pseudocode

```c
_BOOL8 __fastcall CPropMgrImpl::InitHwnd(CPropMgrImpl *this)
{
  DWORD CurrentProcessId; // eax
  HWND Window; // rax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-49h] BYREF
  wchar_t Buffer[32]; // [rsp+B0h] [rbp+7h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  if ( swprintf_s(Buffer, 0x20u, L"MSAA_DA_%lx", CurrentProcessId) == -1 )
    return 0;
  WndClass.lpfnWndProc = DefWindowProcW;
  WndClass.hInstance = hInstance;
  *(_QWORD *)&WndClass.style = 0;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  *(_OWORD *)&WndClass.hIcon = 0;
  *(__m128i *)&WndClass.hbrBackground = _mm_load_si128((const __m128i *)&_xmm);
  WndClass.lpszClassName = L"MSAA_DA_Class";
  RegisterClassW(&WndClass);
  Window = CreateWindowExW(0, L"MSAA_DA_Class", Buffer, 0, 0, 0, 128, 128, HWND_MESSAGE, 0, hInstance, this);
  *((_QWORD *)this + 2) = Window;
  return Window != 0;
}

```

## disassembly

```asm
0x180023afc  mov     [rsp-8+arg_8], rbx
0x180023b01  mov     [rsp-8+arg_10], rdi
0x180023b06  push    rbp
0x180023b07  lea     rbp, [rsp-57h]
0x180023b0c  sub     rsp, 100h
0x180023b13  mov     rax, cs:__security_cookie
0x180023b1a  xor     rax, rsp
0x180023b1d  mov     [rbp+57h+var_10], rax
0x180023b21  mov     rbx, rcx
0x180023b24  call    cs:__imp_GetCurrentProcessId
0x180023b2a  lea     r8, aMsaaDaLx; "MSAA_DA_%lx"
0x180023b31  mov     edx, 20h ; ' '; BufferCount
0x180023b36  mov     r9d, eax
0x180023b39  lea     rcx, [rbp+57h+Buffer]; Buffer
0x180023b3d  call    swprintf_s
0x180023b42  cmp     eax, 0FFFFFFFFh
0x180023b45  jz      loc_180023BFD
0x180023b4b  mov     rax, cs:__imp_DefWindowProcW
0x180023b52  lea     rdi, ClassName; "MSAA_DA_Class"
0x180023b59  movdqa  xmm1, cs:__xmm@00000000000000000000000000000006
0x180023b61  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x180023b65  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x180023b69  xorps   xmm0, xmm0
0x180023b6c  mov     rax, cs:hInstance
0x180023b73  mov     [rbp+57h+WndClass.hInstance], rax
0x180023b77  mov     qword ptr [rbp+57h+WndClass.style], 0
0x180023b7f  mov     qword ptr [rbp+57h+WndClass.cbClsExtra], 0
0x180023b87  movdqa  xmmword ptr [rbp+57h+WndClass.hIcon], xmm0
0x180023b8c  movdqa  xmmword ptr [rbp+57h+WndClass.hbrBackground], xmm1
0x180023b91  mov     [rbp+57h+WndClass.lpszClassName], rdi
0x180023b95  call    cs:__imp_RegisterClassW
0x180023b9b  mov     rax, cs:hInstance
0x180023ba2  lea     r8, [rbp+57h+Buffer]; lpWindowName
0x180023ba6  mov     [rsp+100h+lpParam], rbx; lpParam
0x180023bab  xor     r9d, r9d; dwStyle
0x180023bae  mov     [rsp+100h+hInstance], rax; hInstance
0x180023bb3  mov     rdx, rdi; lpClassName
0x180023bb6  mov     [rsp+100h+hMenu], 0; hMenu
0x180023bbf  mov     eax, 80h
0x180023bc4  mov     [rsp+100h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x180023bcd  xor     ecx, ecx; dwExStyle
0x180023bcf  mov     [rsp+100h+nHeight], eax; nHeight
0x180023bd3  mov     [rsp+100h+nWidth], eax; nWidth
0x180023bd7  mov     [rsp+100h+Y], 0; Y
0x180023bdf  mov     [rsp+100h+X], 0; X
0x180023be7  call    cs:__imp_CreateWindowExW
0x180023bed  xor     ecx, ecx
0x180023bef  mov     [rbx+10h], rax
0x180023bf3  test    rax, rax
0x180023bf6  setnz   cl
0x180023bf9  mov     eax, ecx
0x180023bfb  jmp     short loc_180023BFF
0x180023bfd  xor     eax, eax
0x180023bff  mov     rcx, [rbp+57h+var_10]
0x180023c03  xor     rcx, rsp; StackCookie
0x180023c06  call    __security_check_cookie
0x180023c0b  lea     r11, [rsp+100h+var_s0]
0x180023c13  mov     rbx, [r11+18h]
0x180023c17  mov     rdi, [r11+20h]
0x180023c1b  mov     rsp, r11
0x180023c1e  pop     rbp
0x180023c1f  retn
```
