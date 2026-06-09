# CopyOnWriteBitmap::CreateHBITMAP(HBITMAP__ * *,ulong)

- ea: `0x18006f328`
- end: `0x18006f6af`
- name: `?CreateHBITMAP@CopyOnWriteBitmap@@AEAA?AW4Status@@PEAPEAUHBITMAP__@@K@Z`
- size: `903`
- prototype: `void __fastcall __noreturn(LONG *, HBITMAP *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006e820`
- `0x18006f2c8`

## callees

- `0x18000e6d0`
- `0x18002031c`
- `0x18006f260`
- `0x18006f328`
- `0x18006f7c4`
- `0x180070dd4`
- `0x1800e9380`

## import_xrefs

- `GDI32!PatBlt` at `0x18006f507`
- `GDI32!PatBlt` at `0x18006f507`
- `GDI32!CreateBrushIndirect` at `0x18006f4b0`
- `GDI32!CreateBrushIndirect` at `0x18006f4b0`
- `GDI32!CreateDIBSection` at `0x18006f3e1`
- `GDI32!CreateDIBSection` at `0x18006f3e1`
- `GDI32!DeleteDC` at `0x18006f651`
- `GDI32!DeleteDC` at `0x18006f651`
- `GDI32!SelectObject` at `0x18006f45c`
- `GDI32!SelectObject` at `0x18006f4ce`
- `GDI32!SelectObject` at `0x18006f62b`
- `GDI32!SelectObject` at `0x18006f642`
- `GDI32!SelectObject` at `0x18006f45c`
- `GDI32!SelectObject` at `0x18006f4ce`
- `GDI32!SelectObject` at `0x18006f62b`
- `GDI32!SelectObject` at `0x18006f642`
- `GDI32!CreateCompatibleDC` at `0x18006f376`
- `GDI32!CreateCompatibleDC` at `0x18006f376`
- `GDI32!DeleteObject` at `0x18006f414`
- `GDI32!DeleteObject` at `0x18006f69e`
- `GDI32!DeleteObject` at `0x18006f414`
- `GDI32!DeleteObject` at `0x18006f69e`

## pseudocode

```c
void __fastcall __noreturn CopyOnWriteBitmap::CreateHBITMAP(LONG *a1, HBITMAP *a2, int a3)
{
  void *v4; // rbx
  HBRUSH v5; // r12
  HGDIOBJ v6; // r13
  GpGraphics *v7; // r14
  HDC CompatibleDC; // rsi
  HBITMAP v9; // rax
  HBITMAP v10; // r15
  HBRUSH v11; // rax
  struct GpGraphics *v12; // rax
  signed __int32 v13; // eax
  int v14; // ebx
  int v15; // eax
  float v16; // xmm1_4
  unsigned int v17; // edx
  HANDLE hSection; // [rsp+20h] [rbp-E0h]
  HGDIOBJ v20; // [rsp+38h] [rbp-C8h]
  _DWORD v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  signed __int32 v22; // [rsp+50h] [rbp-B0h] BYREF
  volatile signed __int32 *v23; // [rsp+58h] [rbp-A8h]
  void *ppvBits; // [rsp+60h] [rbp-A0h] BYREF
  HBITMAP *v25; // [rsp+68h] [rbp-98h]
  LOGBRUSH plbrush; // [rsp+70h] [rbp-90h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[1504]; // [rsp+B0h] [rbp-50h] BYREF

  v25 = a2;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    memset(&pbmi, 0, sizeof(pbmi));
    pbmi.bmiHeader.biWidth = a1[41];
    pbmi.bmiHeader.biHeight = a1[42];
    ppvBits = 0;
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v9 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
    v10 = v9;
    if ( v9 )
    {
      v20 = SelectObject(CompatibleDC, v9);
      v4 = v20;
      if ( v20 )
      {
        plbrush = 0;
        plbrush.lbStyle = 0;
        BYTE2(plbrush.lbColor) = a3;
        LOBYTE(plbrush.lbColor) = BYTE2(a3);
        BYTE1(plbrush.lbColor) = BYTE1(a3);
        v11 = CreateBrushIndirect(&plbrush);
        v5 = v11;
        if ( v11 )
        {
          v6 = SelectObject(CompatibleDC, v11);
          if ( v6 )
          {
            PatBlt(CompatibleDC, 0, 0, a1[41], a1[42], 0xF00021u);
            v12 = GpGraphics::GetFromHdc(CompatibleDC, 0);
            v7 = v12;
            if ( v12 )
            {
              if ( v12 == (struct GpGraphics *)-16LL )
              {
                v13 = 0;
                v23 = &v22;
              }
              else
              {
                v23 = (volatile signed __int32 *)((char *)v12 + 16);
                v13 = _InterlockedIncrement((volatile signed __int32 *)v12 + 4);
              }
              v22 = v13;
              if ( !v13 )
              {
                v14 = _mm_getcsr();
                if ( (v14 & 0xFF80) != 0x3F80 )
                  _mm_setcsr(0x3F80u);
                v15 = a1[42];
                v21[0] = 0;
                v21[1] = 0;
                v16 = (float)a1[41];
                *(float *)&v21[3] = (float)v15;
                *(float *)&v21[2] = v16;
                GpBitmap::GpBitmap((GpBitmap *)v28, (const struct CopyOnWriteBitmap *)a1);
                LODWORD(hSection) = 2;
                if ( !(unsigned int)GpGraphics::DrawImage(v7, v28, v21, v21, hSection, 0) )
                {
                  *v25 = v10;
                  v10 = 0;
                }
                GpBitmap::~GpBitmap((GpBitmap *)v28);
                if ( (v14 & 0xFF80) != 0x3F80 )
                  _mm_setcsr(v14 & 0xFFFFFFC0);
                v4 = v20;
              }
              _InterlockedDecrement(v23);
            }
          }
        }
      }
    }
    if ( v4 )
      SelectObject(CompatibleDC, v4);
    if ( v6 )
      SelectObject(CompatibleDC, v6);
    DeleteDC(CompatibleDC);
    if ( v10 )
      DeleteObject(v10);
    if ( v5 )
      DeleteObject(v5);
    if ( v7 )
      GpGraphics::`scalar deleting destructor'(v7, v17);
  }
}

```

## disassembly

```asm
0x18006f328  mov     [rsp-8+arg_18], rbx
0x18006f32d  push    rbp
0x18006f32e  push    rsi
0x18006f32f  push    rdi
0x18006f330  push    r12
0x18006f332  push    r13
0x18006f334  push    r14
0x18006f336  push    r15
0x18006f338  lea     rbp, [rsp-5A0h]
0x18006f340  sub     rsp, 6A0h
0x18006f347  mov     rax, cs:__security_cookie
0x18006f34e  xor     rax, rsp
0x18006f351  mov     [rbp+5D0h+var_40], rax
0x18006f358  xor     r15d, r15d
0x18006f35b  mov     [rsp+6D0h+var_6A0], r8d
0x18006f360  mov     rdi, rcx
0x18006f363  mov     [rsp+6D0h+var_668], rdx
0x18006f368  xor     ecx, ecx; hdc
0x18006f36a  mov     ebx, r15d
0x18006f36d  mov     r12d, r15d
0x18006f370  mov     r13d, r15d
0x18006f373  mov     r14d, r15d
0x18006f376  call    cs:__imp_CreateCompatibleDC
0x18006f37d  nop     dword ptr [rax+rax+00h]
0x18006f382  mov     rsi, rax
0x18006f385  test    rax, rax
0x18006f388  jz      loc_18006F691
0x18006f38e  xor     eax, eax
0x18006f390  mov     [rsp+6D0h+offset], r15d; offset
0x18006f395  xorps   xmm0, xmm0
0x18006f398  mov     qword ptr [rbp+5D0h+pbmi.bmiHeader.biClrUsed], rax
0x18006f39c  movups  xmmword ptr [rbp+5D0h+pbmi.bmiHeader.biSize], xmm0
0x18006f3a0  mov     dword ptr [rbp+5D0h+pbmi.bmiColors.rgbBlue], eax
0x18006f3a3  lea     r9, [rsp+6D0h+ppvBits]; ppvBits
0x18006f3a8  mov     eax, [rdi+0A4h]
0x18006f3ae  lea     rdx, [rbp+5D0h+pbmi]; pbmi
0x18006f3b2  mov     [rbp+5D0h+pbmi.bmiHeader.biWidth], eax
0x18006f3b5  xor     r8d, r8d; usage
0x18006f3b8  mov     eax, [rdi+0A8h]
0x18006f3be  mov     rcx, rsi; hdc
0x18006f3c1  movups  xmmword ptr [rbp+5D0h+pbmi.bmiHeader.biCompression], xmm0
0x18006f3c5  mov     [rbp+5D0h+pbmi.bmiHeader.biHeight], eax
0x18006f3c8  mov     [rsp+6D0h+ppvBits], r15
0x18006f3cd  mov     [rbp+5D0h+pbmi.bmiHeader.biSize], 28h ; '('
0x18006f3d4  mov     qword ptr [rbp+5D0h+pbmi.bmiHeader.biPlanes], 200001h
0x18006f3dc  mov     [rsp+6D0h+hSection], r15; hSection
0x18006f3e1  call    cs:__imp_CreateDIBSection
0x18006f3e8  nop     dword ptr [rax+rax+00h]
0x18006f3ed  mov     r15, rax
0x18006f3f0  test    rax, rax
0x18006f3f3  jnz     short loc_18006F456
0x18006f3f5  mov     edi, 7
0x18006f3fa  test    rsi, rsi
0x18006f3fd  jnz     loc_18006F620
0x18006f403  test    r15, r15
0x18006f406  jnz     loc_18006F69B
0x18006f40c  test    r12, r12
0x18006f40f  jz      short loc_18006F420
0x18006f411  mov     rcx, r12; ho
0x18006f414  call    cs:__imp_DeleteObject
0x18006f41b  nop     dword ptr [rax+rax+00h]
0x18006f420  test    r14, r14
0x18006f423  jnz     loc_18006F662
0x18006f429  mov     eax, edi
0x18006f42b  mov     rcx, [rbp+5D0h+var_40]
0x18006f432  xor     rcx, rsp; StackCookie
0x18006f435  call    __security_check_cookie
0x18006f43a  mov     rbx, [rsp+6D0h+arg_18]
0x18006f442  add     rsp, 6A0h
0x18006f449  pop     r15
0x18006f44b  pop     r14
0x18006f44d  pop     r13
0x18006f44f  pop     r12
0x18006f451  pop     rdi
0x18006f452  pop     rsi
0x18006f453  pop     rbp
0x18006f454  retn
0x18006f456  mov     rdx, r15; h
0x18006f459  mov     rcx, rsi; hdc
0x18006f45c  call    cs:__imp_SelectObject
0x18006f463  nop     dword ptr [rax+rax+00h]
0x18006f468  mov     [rsp+6D0h+var_698], rax
0x18006f46d  mov     rbx, rax
0x18006f470  test    rax, rax
0x18006f473  jz      short loc_18006F3F5
0x18006f475  mov     r8d, [rsp+6D0h+var_6A0]
0x18006f47a  xorps   xmm0, xmm0
0x18006f47d  movups  xmmword ptr [rsp+6D0h+plbrush.lbStyle], xmm0
0x18006f482  and     [rsp+6D0h+plbrush.lbStyle], r12d
0x18006f487  mov     eax, r8d
0x18006f48a  shr     eax, 8
0x18006f48d  movzx   edx, al
0x18006f490  mov     eax, r8d
0x18006f493  shr     eax, 10h
0x18006f496  movzx   ecx, al
0x18006f499  shl     edx, 8
0x18006f49c  or      edx, ecx
0x18006f49e  movzx   eax, r8b
0x18006f4a2  shl     eax, 10h
0x18006f4a5  lea     rcx, [rsp+6D0h+plbrush]; plbrush
0x18006f4aa  or      edx, eax
0x18006f4ac  mov     [rsp+6D0h+plbrush.lbColor], edx
0x18006f4b0  call    cs:__imp_CreateBrushIndirect
0x18006f4b7  nop     dword ptr [rax+rax+00h]
0x18006f4bc  mov     r12, rax
0x18006f4bf  test    rax, rax
0x18006f4c2  jz      loc_18006F3F5
0x18006f4c8  mov     rdx, rax; h
0x18006f4cb  mov     rcx, rsi; hdc
0x18006f4ce  call    cs:__imp_SelectObject
0x18006f4d5  nop     dword ptr [rax+rax+00h]
0x18006f4da  mov     r13, rax
0x18006f4dd  test    rax, rax
0x18006f4e0  jz      loc_18006F3F5
0x18006f4e6  mov     eax, [rdi+0A8h]
0x18006f4ec  xor     r8d, r8d; y
0x18006f4ef  mov     r9d, [rdi+0A4h]; w
0x18006f4f6  xor     edx, edx; x
0x18006f4f8  mov     [rsp+6D0h+offset], 0F00021h; rop
0x18006f500  mov     rcx, rsi; hdc
0x18006f503  mov     dword ptr [rsp+6D0h+hSection], eax; h
0x18006f507  call    cs:__imp_PatBlt
0x18006f50e  nop     dword ptr [rax+rax+00h]
0x18006f513  xor     edx, edx; void *
0x18006f515  mov     rcx, rsi; hdc
0x18006f518  call    ?GetFromHdc@GpGraphics@@SAPEAV1@PEAUHDC__@@PEAX@Z
0x18006f51d  mov     r14, rax
0x18006f520  test    rax, rax
0x18006f523  jz      loc_18006F687
0x18006f529  lea     rcx, [rax+10h]
0x18006f52d  test    rcx, rcx
0x18006f530  jz      loc_18006F676
0x18006f536  mov     [rsp+6D0h+var_678], rcx
0x18006f53b  mov     eax, 1
0x18006f540  lock xadd [rcx], eax
0x18006f544  inc     eax
0x18006f546  mov     [rsp+6D0h+var_680], eax
0x18006f54a  test    eax, eax
0x18006f54c  jnz     loc_18006F66F
0x18006f552  mov     edx, 0FF80h
0x18006f557  mov     ecx, 3F80h
0x18006f55c  stmxcsr [rsp+6D0h+var_6A0]
0x18006f561  mov     ebx, [rsp+6D0h+var_6A0]
0x18006f565  mov     eax, ebx
0x18006f567  and     eax, edx
0x18006f569  cmp     eax, ecx
0x18006f56b  jz      short loc_18006F576
0x18006f56d  mov     [rsp+6D0h+var_6A0], ecx
0x18006f571  ldmxcsr [rsp+6D0h+var_6A0]
0x18006f576  mov     eax, [rdi+0A8h]
0x18006f57c  lea     rcx, [rbp+5D0h+var_620]; this
0x18006f580  and     [rsp+6D0h+var_690], 0
0x18006f585  xorps   xmm2, xmm2
0x18006f588  and     [rsp+6D0h+var_68C], 0
0x18006f58d  xorps   xmm1, xmm1
0x18006f590  mov     rdx, rdi; struct CopyOnWriteBitmap *
0x18006f593  cvtsi2ss xmm2, rax
0x18006f598  mov     eax, [rdi+0A4h]
0x18006f59e  cvtsi2ss xmm1, rax
0x18006f5a3  movss   [rsp+6D0h+var_684], xmm2
0x18006f5a9  movss   [rsp+6D0h+var_688], xmm1
0x18006f5af  call    ??0GpBitmap@@AEAA@PEBVCopyOnWriteBitmap@@@Z
0x18006f5b4  and     qword ptr [rsp+6D0h+offset], 0
0x18006f5ba  lea     r9, [rsp+6D0h+var_690]
0x18006f5bf  lea     r8, [rsp+6D0h+var_690]
0x18006f5c4  mov     dword ptr [rsp+6D0h+hSection], 2
0x18006f5cc  lea     rdx, [rbp+5D0h+var_620]
0x18006f5d0  mov     rcx, r14
0x18006f5d3  call    ?DrawImage@GpGraphics@@QEAA?AW4Status@@PEAVGpImage@@AEBVRectF@@1W4Unit@@PEBVGpImageAttributes@@@Z
0x18006f5d8  mov     edi, eax
0x18006f5da  test    eax, eax
0x18006f5dc  jnz     short loc_18006F5E9
0x18006f5de  mov     rax, [rsp+6D0h+var_668]
0x18006f5e3  mov     [rax], r15
0x18006f5e6  xor     r15d, r15d
0x18006f5e9  lea     rcx, [rbp+5D0h+var_620]; this
0x18006f5ed  call    ??1GpBitmap@@EEAA@XZ
0x18006f5f2  mov     ecx, ebx
0x18006f5f4  and     ecx, 0FF80h
0x18006f5fa  cmp     ecx, 3F80h
0x18006f600  jz      short loc_18006F60E
0x18006f602  and     ebx, 0FFFFFFC0h
0x18006f605  mov     [rsp+6D0h+var_6A0], ebx
0x18006f609  ldmxcsr [rsp+6D0h+var_6A0]
0x18006f60e  mov     rbx, [rsp+6D0h+var_698]
0x18006f613  mov     rax, [rsp+6D0h+var_678]
0x18006f618  lock dec dword ptr [rax]
0x18006f61b  jmp     loc_18006F3FA
0x18006f620  test    rbx, rbx
0x18006f623  jz      short loc_18006F637
0x18006f625  mov     rdx, rbx; h
0x18006f628  mov     rcx, rsi; hdc
0x18006f62b  call    cs:__imp_SelectObject
0x18006f632  nop     dword ptr [rax+rax+00h]
0x18006f637  test    r13, r13
0x18006f63a  jz      short loc_18006F64E
0x18006f63c  mov     rdx, r13; h
0x18006f63f  mov     rcx, rsi; hdc
0x18006f642  call    cs:__imp_SelectObject
0x18006f649  nop     dword ptr [rax+rax+00h]
0x18006f64e  mov     rcx, rsi; hdc
0x18006f651  call    cs:__imp_DeleteDC
0x18006f658  nop     dword ptr [rax+rax+00h]
0x18006f65d  jmp     loc_18006F403
0x18006f662  mov     rcx, r14; this
0x18006f665  call    ??_GGpGraphics@@QEAAPEAXI@Z
0x18006f66a  jmp     loc_18006F429
0x18006f66f  mov     edi, 4
0x18006f674  jmp     short loc_18006F613
0x18006f676  lea     rcx, [rsp+6D0h+var_680]
0x18006f67b  xor     eax, eax
0x18006f67d  mov     [rsp+6D0h+var_678], rcx
0x18006f682  jmp     loc_18006F546
0x18006f687  mov     edi, 3
0x18006f68c  jmp     loc_18006F3FA
0x18006f691  mov     edi, 7
0x18006f696  jmp     loc_18006F429
0x18006f69b  mov     rcx, r15; ho
0x18006f69e  call    cs:__imp_DeleteObject
0x18006f6a5  nop     dword ptr [rax+rax+00h]
0x18006f6aa  jmp     loc_18006F40C
```
