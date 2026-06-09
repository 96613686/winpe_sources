# CopyOnWriteBitmap::CreateHICON(HICON__ * *)

- ea: `0x18006e820`
- end: `0x18006ead9`
- name: `?CreateHICON@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHICON__@@@Z`
- size: `697`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18006e768`

## callees

- `0x180011330`
- `0x1800116c8`
- `0x18001f950`
- `0x18006e820`
- `0x18006f328`
- `0x1800e5044`
- `0x1800e9380`
- `0x180175010`

## import_xrefs

- `USER32!CreateIconIndirect` at `0x18006eac0`
- `USER32!CreateIconIndirect` at `0x18006eac0`
- `USER32!GetDC` at `0x18006ea14`
- `USER32!GetDC` at `0x18006ea14`
- `USER32!ReleaseDC` at `0x18006ea97`
- `USER32!ReleaseDC` at `0x18006ea97`
- `GDI32!SetDIBits` at `0x18006ea82`
- `GDI32!SetDIBits` at `0x18006ea82`
- `GDI32!SetBkMode` at `0x18006ea55`
- `GDI32!SetBkMode` at `0x18006ea55`
- `GDI32!SetBkColor` at `0x18006ea41`
- `GDI32!SetBkColor` at `0x18006ea41`
- `GDI32!SetTextColor` at `0x18006ea2d`
- `GDI32!SetTextColor` at `0x18006ea2d`
- `GDI32!CreateBitmap` at `0x18006e8c1`
- `GDI32!CreateBitmap` at `0x18006e8c1`
- `GDI32!DeleteObject` at `0x18006e8f3`
- `GDI32!DeleteObject` at `0x18006e927`
- `GDI32!DeleteObject` at `0x18006e8f3`
- `GDI32!DeleteObject` at `0x18006e927`

## pseudocode

```c
void __fastcall __noreturn CopyOnWriteBitmap::CreateHICON(__int64 a1, __int64 a2)
{
  ICONINFO piconinfo; // [rsp+60h] [rbp-39h] BYREF
  __int64 v3; // [rsp+80h] [rbp-19h]

  v3 = a2;
  *(_OWORD *)&piconinfo.hbmMask = 0;
  CopyOnWriteBitmap::CreateHBITMAP(a1, &piconinfo.hbmColor, 0);
}

```

## disassembly

```asm
0x18006e820  mov     [rsp-8+arg_10], rbx
0x18006e825  push    rbp
0x18006e826  push    rsi
0x18006e827  push    rdi
0x18006e828  push    r12
0x18006e82a  push    r13
0x18006e82c  push    r14
0x18006e82e  push    r15
0x18006e830  lea     rbp, [rsp-27h]
0x18006e835  sub     rsp, 0C0h
0x18006e83c  mov     rax, cs:__security_cookie
0x18006e843  xor     rax, rsp
0x18006e846  mov     [rbp+57h+var_38], rax
0x18006e84a  xorps   xmm0, xmm0
0x18006e84d  mov     [rbp+57h+var_70], rdx
0x18006e851  mov     r12, rdx
0x18006e854  mov     edi, 1
0x18006e859  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x18006e85d  xor     r8d, r8d
0x18006e860  mov     [rbp+57h+piconinfo.fIcon], edi
0x18006e863  lea     rdx, [rbp+57h+piconinfo.hbmColor]
0x18006e867  mov     rsi, rcx
0x18006e86a  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x18006e86e  call    ?CreateHBITMAP@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHBITMAP__@@K@Z; CopyOnWriteBitmap::CreateHBITMAP(HBITMAP__ * *,ulong)
0x18006e873  xor     r13d, r13d
0x18006e876  mov     ebx, eax
0x18006e878  test    eax, eax
0x18006e87a  jnz     loc_18006E933
0x18006e880  xorps   xmm0, xmm0
0x18006e883  lea     rax, [rbp+57h+nWidth]
0x18006e887  mov     r9d, 26200Ah
0x18006e88d  mov     [rsp+0F0h+lpBits], rax
0x18006e892  mov     r8d, edi
0x18006e895  xor     edx, edx
0x18006e897  mov     rcx, rsi
0x18006e89a  movups  xmmword ptr [rbp+57h+nWidth], xmm0
0x18006e89e  movups  [rbp+57h+var_A0], xmm0
0x18006e8a2  call    ?LockBits@CopyOnWriteBitmap@@AEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; CopyOnWriteBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x18006e8a7  mov     ebx, eax
0x18006e8a9  test    eax, eax
0x18006e8ab  jnz     short loc_18006E923
0x18006e8ad  mov     edx, [rbp+57h+nWidth+4]; nHeight
0x18006e8b0  lea     ebx, [rdi+6]
0x18006e8b3  mov     ecx, [rbp+57h+nWidth]; nWidth
0x18006e8b6  mov     r9d, edi; nBitCount
0x18006e8b9  mov     r8d, edi; nPlanes
0x18006e8bc  mov     [rsp+0F0h+lpBits], r13; lpBits
0x18006e8c1  call    cs:__imp_CreateBitmap
0x18006e8c8  nop     dword ptr [rax+rax+00h]
0x18006e8cd  mov     [rbp+57h+piconinfo.hbmMask], rax
0x18006e8d1  test    rax, rax
0x18006e8d4  jz      short loc_18006E8FF
0x18006e8d6  mov     ecx, [rbp+57h+nWidth]
0x18006e8d9  mov     edx, 0FFFFFFFFh
0x18006e8de  mov     eax, [rbp+57h+nWidth+4]
0x18006e8e1  imul    rcx, rax
0x18006e8e5  cmp     rcx, rdx
0x18006e8e8  jbe     short loc_18006E95D
0x18006e8ea  mov     ebx, 3
0x18006e8ef  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x18006e8f3  call    cs:__imp_DeleteObject
0x18006e8fa  nop     dword ptr [rax+rax+00h]
0x18006e8ff  mov     rcx, [rsi+58h]
0x18006e903  test    rcx, rcx
0x18006e906  jz      short loc_18006E923
0x18006e908  mov     rax, [rcx]
0x18006e90b  lea     rdx, [rbp+57h+nWidth]
0x18006e90f  mov     rax, [rax+30h]
0x18006e913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e918  dec     dword ptr [rsi+3Ch]
0x18006e91b  test    eax, eax
0x18006e91d  js      loc_18006EAB0
0x18006e923  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x18006e927  call    cs:__imp_DeleteObject
0x18006e92e  nop     dword ptr [rax+rax+00h]
0x18006e933  mov     eax, ebx
0x18006e935  mov     rcx, [rbp+57h+var_38]
0x18006e939  xor     rcx, rsp; StackCookie
0x18006e93c  call    __security_check_cookie
0x18006e941  mov     rbx, [rsp+0F0h+arg_10]
0x18006e949  add     rsp, 0C0h
0x18006e950  pop     r15
0x18006e952  pop     r14
0x18006e954  pop     r13
0x18006e956  pop     r12
0x18006e958  pop     rdi
0x18006e959  pop     rsi
0x18006e95a  pop     rbp
0x18006e95b  retn
0x18006e95d  mov     eax, ecx
0x18006e95f  shl     rax, 2
0x18006e963  cmp     rax, rdx
0x18006e966  ja      short loc_18006E8EA
0x18006e968  mov     ecx, eax
0x18006e96a  xor     edx, edx
0x18006e96c  call    GpMallocEx
0x18006e971  mov     r14, rax
0x18006e974  test    rax, rax
0x18006e977  jz      loc_18006E8EA
0x18006e97d  mov     edx, [rbp+57h+nWidth]
0x18006e980  mov     r10d, r13d
0x18006e983  mov     ecx, [rbp+57h+nWidth+4]
0x18006e986  mov     r8, qword ptr [rbp+57h+var_A0]
0x18006e98a  lea     r15d, ds:0[rdx*4]
0x18006e992  test    ecx, ecx
0x18006e994  jz      short loc_18006E9EF
0x18006e996  mov     r9, rax
0x18006e999  mov     r12d, edi
0x18006e99c  mov     r11, r8
0x18006e99f  mov     edi, r13d
0x18006e9a2  test    edx, edx
0x18006e9a4  jz      short loc_18006E9D6
0x18006e9a6  mov     rcx, r9
0x18006e9a9  sub     rcx, r8
0x18006e9ac  mov     eax, [r11]
0x18006e9af  mov     edx, 0FF000000h
0x18006e9b4  and     eax, edx
0x18006e9b6  sub     eax, edx
0x18006e9b8  neg     eax
0x18006e9ba  sbb     eax, eax
0x18006e9bc  add     edi, r12d
0x18006e9bf  and     eax, 0FFFFFFh
0x18006e9c4  mov     [rcx+r11], eax
0x18006e9c8  lea     r11, [r11+4]
0x18006e9cc  mov     edx, [rbp+57h+nWidth]
0x18006e9cf  cmp     edi, edx
0x18006e9d1  jb      short loc_18006E9AC
0x18006e9d3  mov     ecx, [rbp+57h+nWidth+4]
0x18006e9d6  movsxd  rax, [rbp+57h+nWidth+8]
0x18006e9da  add     r10d, r12d
0x18006e9dd  add     r8, rax
0x18006e9e0  movsxd  rax, r15d
0x18006e9e3  add     r9, rax
0x18006e9e6  cmp     r10d, ecx
0x18006e9e9  jb      short loc_18006E99C
0x18006e9eb  mov     r12, [rbp+57h+var_70]
0x18006e9ef  neg     ecx
0x18006e9f1  mov     qword ptr [rbp+57h+bmi.bmiHeader.biClrImportant], r13
0x18006e9f5  mov     [rbp+57h+bmi.bmiHeader.biHeight], ecx
0x18006e9f8  xorps   xmm0, xmm0
0x18006e9fb  xor     ecx, ecx; hWnd
0x18006e9fd  mov     [rbp+57h+bmi.bmiHeader.biSize], 28h ; '('
0x18006ea04  movdqu  xmmword ptr [rbp+57h+bmi.bmiHeader.biSizeImage], xmm0
0x18006ea09  mov     [rbp+57h+bmi.bmiHeader.biWidth], edx
0x18006ea0c  mov     qword ptr [rbp+57h+bmi.bmiHeader.biPlanes], 200001h
0x18006ea14  call    cs:__imp_GetDC
0x18006ea1b  nop     dword ptr [rax+rax+00h]
0x18006ea20  mov     rdi, rax
0x18006ea23  test    rax, rax
0x18006ea26  jz      short loc_18006EAA3
0x18006ea28  xor     edx, edx; color
0x18006ea2a  mov     rcx, rax; hdc
0x18006ea2d  call    cs:__imp_SetTextColor
0x18006ea34  nop     dword ptr [rax+rax+00h]
0x18006ea39  mov     edx, 0FFFFFFh; color
0x18006ea3e  mov     rcx, rdi; hdc
0x18006ea41  call    cs:__imp_SetBkColor
0x18006ea48  nop     dword ptr [rax+rax+00h]
0x18006ea4d  mov     edx, 2; mode
0x18006ea52  mov     rcx, rdi; hdc
0x18006ea55  call    cs:__imp_SetBkMode
0x18006ea5c  nop     dword ptr [rax+rax+00h]
0x18006ea61  mov     r9d, [rbp+57h+nWidth+4]; cLines
0x18006ea65  lea     rax, [rbp+57h+bmi]
0x18006ea69  mov     rdx, [rbp+57h+piconinfo.hbmMask]; hbm
0x18006ea6d  xor     r8d, r8d; start
0x18006ea70  mov     [rsp+0F0h+ColorUse], r13d; ColorUse
0x18006ea75  mov     rcx, rdi; hdc
0x18006ea78  mov     [rsp+0F0h+lpbmi], rax; lpbmi
0x18006ea7d  mov     [rsp+0F0h+lpBits], r14; lpBits
0x18006ea82  call    cs:__imp_SetDIBits
0x18006ea89  nop     dword ptr [rax+rax+00h]
0x18006ea8e  test    eax, eax
0x18006ea90  jnz     short loc_18006EABC
0x18006ea92  mov     rdx, rdi; hDC
0x18006ea95  xor     ecx, ecx; hWnd
0x18006ea97  call    cs:__imp_ReleaseDC
0x18006ea9e  nop     dword ptr [rax+rax+00h]
0x18006eaa3  mov     rcx, r14
0x18006eaa6  call    GpFree
0x18006eaab  jmp     loc_18006E8EF
0x18006eab0  mov     ecx, eax
0x18006eab2  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x18006eab7  jmp     loc_18006E923
0x18006eabc  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x18006eac0  call    cs:__imp_CreateIconIndirect
0x18006eac7  nop     dword ptr [rax+rax+00h]
0x18006eacc  test    rax, rax
0x18006eacf  mov     [r12], rax
0x18006ead3  cmovnz  ebx, r13d
0x18006ead7  jmp     short loc_18006EA92
```
