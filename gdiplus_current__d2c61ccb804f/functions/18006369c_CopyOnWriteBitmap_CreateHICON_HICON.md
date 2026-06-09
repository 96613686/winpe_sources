# CopyOnWriteBitmap::CreateHICON(HICON__ * *)

- ea: `0x18006369c`
- end: `0x18006395c`
- name: `?CreateHICON@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHICON__@@@Z`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800dd0c0`

## callees

- `0x180010bd0`
- `0x180017190`
- `0x180017a3c`
- `0x18006369c`
- `0x180063964`
- `0x180063cd8`
- `0x180105d40`
- `0x180172010`

## import_xrefs

- `USER32!CreateIconIndirect` at `0x18006392e`
- `USER32!CreateIconIndirect` at `0x18006392e`
- `USER32!GetDC` at `0x18006389c`
- `USER32!GetDC` at `0x18006389c`
- `USER32!ReleaseDC` at `0x18006394b`
- `USER32!ReleaseDC` at `0x18006394b`
- `GDI32!SetDIBits` at `0x18006391a`
- `GDI32!SetDIBits` at `0x18006391a`
- `GDI32!SetBkMode` at `0x1800638ea`
- `GDI32!SetBkMode` at `0x1800638ea`
- `GDI32!SetBkColor` at `0x1800638d6`
- `GDI32!SetBkColor` at `0x1800638d6`
- `GDI32!SetTextColor` at `0x1800638c2`
- `GDI32!SetTextColor` at `0x1800638c2`
- `GDI32!CreateBitmap` at `0x18006373e`
- `GDI32!CreateBitmap` at `0x18006373e`
- `GDI32!DeleteObject` at `0x180063770`
- `GDI32!DeleteObject` at `0x1800637a7`
- `GDI32!DeleteObject` at `0x180063770`
- `GDI32!DeleteObject` at `0x1800637a7`

## pseudocode

```c
void __fastcall __noreturn CopyOnWriteBitmap::CreateHICON(LONG *a1, __int64 a2)
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
0x18006369c  mov     [rsp-8+arg_10], rbx
0x1800636a1  push    rbp
0x1800636a2  push    rsi
0x1800636a3  push    rdi
0x1800636a4  push    r12
0x1800636a6  push    r13
0x1800636a8  push    r14
0x1800636aa  push    r15
0x1800636ac  lea     rbp, [rsp-27h]
0x1800636b1  sub     rsp, 0C0h
0x1800636b8  mov     rax, cs:__security_cookie
0x1800636bf  xor     rax, rsp
0x1800636c2  mov     [rbp+57h+var_38], rax
0x1800636c6  xorps   xmm0, xmm0
0x1800636c9  mov     [rbp+57h+var_70], rdx
0x1800636cd  mov     r13, rdx
0x1800636d0  mov     edi, 1
0x1800636d5  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x1800636d9  xor     r8d, r8d
0x1800636dc  mov     [rbp+57h+piconinfo.fIcon], edi
0x1800636df  lea     rdx, [rbp+57h+piconinfo.hbmColor]
0x1800636e3  mov     rsi, rcx
0x1800636e6  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x1800636ea  call    ?CreateHBITMAP@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHBITMAP__@@K@Z; CopyOnWriteBitmap::CreateHBITMAP(HBITMAP__ * *,ulong)
0x1800636ef  mov     ebx, eax
0x1800636f1  test    eax, eax
0x1800636f3  jnz     loc_1800637B3
0x1800636f9  xorps   xmm0, xmm0
0x1800636fc  lea     rax, [rbp+57h+nWidth]
0x180063700  mov     r9d, 26200Ah
0x180063706  mov     [rsp+0F0h+lpBits], rax
0x18006370b  mov     r8d, edi
0x18006370e  xor     edx, edx
0x180063710  mov     rcx, rsi
0x180063713  movups  xmmword ptr [rbp+57h+nWidth], xmm0
0x180063717  movups  [rbp+57h+var_A0], xmm0
0x18006371b  call    ?LockBits@CopyOnWriteBitmap@@AEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; CopyOnWriteBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x180063720  mov     ebx, eax
0x180063722  test    eax, eax
0x180063724  jnz     short loc_1800637A3
0x180063726  mov     edx, [rbp+57h+nWidth+4]; nHeight
0x180063729  lea     ebx, [rdi+6]
0x18006372c  mov     ecx, [rbp+57h+nWidth]; nWidth
0x18006372f  mov     r9d, edi; nBitCount
0x180063732  mov     r8d, edi; nPlanes
0x180063735  mov     [rsp+0F0h+lpBits], 0; lpBits
0x18006373e  call    cs:__imp_CreateBitmap
0x180063745  nop     dword ptr [rax+rax+00h]
0x18006374a  mov     [rbp+57h+piconinfo.hbmMask], rax
0x18006374e  test    rax, rax
0x180063751  jz      short loc_18006377C
0x180063753  mov     ecx, [rbp+57h+nWidth]
0x180063756  mov     edx, 0FFFFFFFFh
0x18006375b  mov     eax, [rbp+57h+nWidth+4]
0x18006375e  imul    rcx, rax
0x180063762  cmp     rcx, rdx
0x180063765  jbe     short loc_1800637DD
0x180063767  mov     ebx, 3
0x18006376c  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x180063770  call    cs:__imp_DeleteObject
0x180063777  nop     dword ptr [rax+rax+00h]
0x18006377c  mov     rcx, [rsi+58h]
0x180063780  test    rcx, rcx
0x180063783  jz      short loc_1800637A3
0x180063785  mov     rax, [rcx]
0x180063788  lea     rdx, [rbp+57h+nWidth]
0x18006378c  mov     rax, [rax+30h]
0x180063790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063795  dec     dword ptr [rsi+3Ch]
0x180063798  test    eax, eax
0x18006379a  jns     short loc_1800637A3
0x18006379c  mov     ecx, eax
0x18006379e  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x1800637a3  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x1800637a7  call    cs:__imp_DeleteObject
0x1800637ae  nop     dword ptr [rax+rax+00h]
0x1800637b3  mov     eax, ebx
0x1800637b5  mov     rcx, [rbp+57h+var_38]
0x1800637b9  xor     rcx, rsp; StackCookie
0x1800637bc  call    __security_check_cookie
0x1800637c1  mov     rbx, [rsp+0F0h+arg_10]
0x1800637c9  add     rsp, 0C0h
0x1800637d0  pop     r15
0x1800637d2  pop     r14
0x1800637d4  pop     r13
0x1800637d6  pop     r12
0x1800637d8  pop     rdi
0x1800637d9  pop     rsi
0x1800637da  pop     rbp
0x1800637db  retn
0x1800637dd  mov     eax, ecx
0x1800637df  shl     rax, 2
0x1800637e3  cmp     rax, rdx
0x1800637e6  ja      loc_180063767
0x1800637ec  mov     ecx, eax
0x1800637ee  xor     edx, edx
0x1800637f0  call    GpMallocEx
0x1800637f5  mov     r14, rax
0x1800637f8  test    rax, rax
0x1800637fb  jz      loc_180063767
0x180063801  mov     edx, [rbp+57h+nWidth]
0x180063804  mov     ecx, [rbp+57h+nWidth+4]
0x180063807  lea     r12d, ds:0[rdx*4]
0x18006380f  test    ecx, ecx
0x180063811  jz      short loc_180063873
0x180063813  mov     r8, qword ptr [rbp+57h+var_A0]
0x180063817  xor     r10d, r10d
0x18006381a  mov     r9, rax
0x18006381d  mov     r13d, edi
0x180063820  xor     r15d, r15d
0x180063823  mov     r11, r8
0x180063826  mov     rdi, r9
0x180063829  test    edx, edx
0x18006382b  jz      short loc_18006385A
0x18006382d  mov     ecx, 0FF000000h
0x180063832  mov     eax, [r11]
0x180063835  lea     r11, [r11+4]
0x180063839  and     eax, ecx
0x18006383b  sub     eax, ecx
0x18006383d  neg     eax
0x18006383f  sbb     eax, eax
0x180063841  add     r15d, r13d
0x180063844  and     eax, 0FFFFFFh
0x180063849  mov     [rdi], eax
0x18006384b  lea     rdi, [rdi+4]
0x18006384f  mov     edx, [rbp+57h+nWidth]
0x180063852  cmp     r15d, edx
0x180063855  jb      short loc_180063832
0x180063857  mov     ecx, [rbp+57h+nWidth+4]
0x18006385a  movsxd  rax, [rbp+57h+nWidth+8]
0x18006385e  add     r10d, r13d
0x180063861  add     r8, rax
0x180063864  movsxd  rax, r12d
0x180063867  add     r9, rax
0x18006386a  cmp     r10d, ecx
0x18006386d  jb      short loc_180063820
0x18006386f  mov     r13, [rbp+57h+var_70]
0x180063873  neg     ecx
0x180063875  mov     qword ptr [rbp+57h+bmi.bmiHeader.biClrImportant], 0
0x18006387d  mov     [rbp+57h+bmi.bmiHeader.biHeight], ecx
0x180063880  xorps   xmm0, xmm0
0x180063883  xor     ecx, ecx; hWnd
0x180063885  mov     [rbp+57h+bmi.bmiHeader.biSize], 28h ; '('
0x18006388c  movdqu  xmmword ptr [rbp+57h+bmi.bmiHeader.biSizeImage], xmm0
0x180063891  mov     [rbp+57h+bmi.bmiHeader.biWidth], edx
0x180063894  mov     qword ptr [rbp+57h+bmi.bmiHeader.biPlanes], 200001h
0x18006389c  call    cs:__imp_GetDC
0x1800638a3  nop     dword ptr [rax+rax+00h]
0x1800638a8  mov     rdi, rax
0x1800638ab  test    rax, rax
0x1800638ae  jnz     short loc_1800638BD
0x1800638b0  mov     rcx, r14
0x1800638b3  call    GpFree
0x1800638b8  jmp     loc_18006376C
0x1800638bd  xor     edx, edx; color
0x1800638bf  mov     rcx, rdi; hdc
0x1800638c2  call    cs:__imp_SetTextColor
0x1800638c9  nop     dword ptr [rax+rax+00h]
0x1800638ce  mov     edx, 0FFFFFFh; color
0x1800638d3  mov     rcx, rdi; hdc
0x1800638d6  call    cs:__imp_SetBkColor
0x1800638dd  nop     dword ptr [rax+rax+00h]
0x1800638e2  mov     edx, 2; mode
0x1800638e7  mov     rcx, rdi; hdc
0x1800638ea  call    cs:__imp_SetBkMode
0x1800638f1  nop     dword ptr [rax+rax+00h]
0x1800638f6  mov     r9d, [rbp+57h+nWidth+4]; cLines
0x1800638fa  lea     rax, [rbp+57h+bmi]
0x1800638fe  mov     rdx, [rbp+57h+piconinfo.hbmMask]; hbm
0x180063902  xor     r8d, r8d; start
0x180063905  mov     [rsp+0F0h+ColorUse], 0; ColorUse
0x18006390d  mov     rcx, rdi; hdc
0x180063910  mov     [rsp+0F0h+lpbmi], rax; lpbmi
0x180063915  mov     [rsp+0F0h+lpBits], r14; lpBits
0x18006391a  call    cs:__imp_SetDIBits
0x180063921  nop     dword ptr [rax+rax+00h]
0x180063926  test    eax, eax
0x180063928  jz      short loc_180063946
0x18006392a  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x18006392e  call    cs:__imp_CreateIconIndirect
0x180063935  nop     dword ptr [rax+rax+00h]
0x18006393a  xor     ecx, ecx
0x18006393c  mov     [r13+0], rax
0x180063940  test    rax, rax
0x180063943  cmovnz  ebx, ecx
0x180063946  mov     rdx, rdi; hDC
0x180063949  xor     ecx, ecx; hWnd
0x18006394b  call    cs:__imp_ReleaseDC
0x180063952  nop     dword ptr [rax+rax+00h]
0x180063957  jmp     loc_1800638B0
```
