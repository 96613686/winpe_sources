# GetImageListGrayScale(HBITMAP__ *,int)

- ea: `0x1800637f0`
- end: `0x1800639fc`
- name: `?GetImageListGrayScale@@YAPEAUHBITMAP__@@PEAU1@H@Z`
- size: `524`
- prototype: `HBITMAP __fastcall(HBITMAP h, UINT cLines)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180063a70`

## callees

- `0x1800637f0`
- `0x1800cca00`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180063890`
- `GDI32!CreateCompatibleDC` at `0x180063890`
- `GDI32!SelectObject` at `0x1800639ab`
- `GDI32!SelectObject` at `0x1800639ab`
- `GDI32!DeleteDC` at `0x1800639bd`
- `GDI32!DeleteDC` at `0x1800639bd`
- `GDI32!GetDIBits` at `0x1800638ca`
- `GDI32!GetDIBits` at `0x180063908`
- `GDI32!GetDIBits` at `0x1800638ca`
- `GDI32!GetDIBits` at `0x180063908`
- `GDI32!SetDIBits` at `0x18006399f`
- `GDI32!SetDIBits` at `0x18006399f`
- `GDI32!GetObjectA` at `0x180063834`
- `GDI32!GetObjectA` at `0x180063834`
- `KERNEL32!LocalFree` at `0x1800639b4`
- `KERNEL32!LocalFree` at `0x1800639b4`
- `KERNEL32!LocalAlloc` at `0x1800638d7`
- `KERNEL32!LocalAlloc` at `0x1800638d7`
- `USER32!GetDC` at `0x180063884`
- `USER32!GetDC` at `0x180063884`
- `USER32!ReleaseDC` at `0x1800639c8`
- `USER32!ReleaseDC` at `0x1800639c8`

## pseudocode

```c
HBITMAP __fastcall GetImageListGrayScale(HBITMAP h, UINT cLines)
{
  HDC DC; // r14
  HDC CompatibleDC; // rax
  HDC v6; // rbx
  unsigned __int8 *lpvBits; // rsi
  unsigned __int8 *v8; // r10
  _BYTE *v9; // r9
  DWORD v10; // r11d
  DWORD v11; // r12d
  int v12; // r8d
  int v13; // ecx
  unsigned __int8 *v14; // r10
  _BYTE *v15; // rax
  unsigned int v16; // edx
  __int128 pv; // [rsp+40h] [rbp-39h] BYREF
  __int128 v19; // [rsp+50h] [rbp-29h]
  struct tagBITMAPINFO bmi; // [rsp+60h] [rbp-19h] BYREF

  pv = 0;
  v19 = 0;
  if ( !GetObjectA(h, 32, &pv) || (WORD1(v19) & 0xFFF8u) < 0x18 )
    return 0;
  *(_QWORD *)&bmi.bmiHeader.biWidth = *(_QWORD *)((char *)&pv + 4);
  memset(&bmi.bmiHeader.biSizeImage, 0, 24);
  bmi.bmiHeader.biSize = 40;
  *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  v6 = CompatibleDC;
  if ( DC )
  {
    if ( CompatibleDC )
    {
      GetDIBits(CompatibleDC, h, 0, cLines, 0, &bmi, 0);
      lpvBits = (unsigned __int8 *)LocalAlloc(0x40u, bmi.bmiHeader.biSizeImage);
      if ( lpvBits )
      {
        GetDIBits(v6, h, 0, cLines, lpvBits, &bmi, 0);
        v8 = lpvBits;
        v9 = lpvBits;
        v10 = 0;
        v11 = bmi.bmiHeader.biSizeImage / (WORD1(v19) >> 3);
        if ( v11 )
        {
          do
          {
            v12 = *v8;
            v13 = v8[1];
            v14 = v8 + 2;
            v15 = v9 + 2;
            v16 = (v12 + v13 + (unsigned int)*v14) / 3;
            *v9 = v16;
            v9[1] = v16;
            v9[2] = v16;
            if ( WORD1(v19) == 32 )
              ++v14;
            else
              v15 = v9 + 1;
            ++v10;
            v9 = v15 + 2;
            v8 = v14 + 1;
          }
          while ( v10 < v11 );
        }
        SetDIBits(v6, h, 0, cLines, lpvBits, &bmi, 0);
        SelectObject(v6, h);
        LocalFree(lpvBits);
      }
    }
  }
  DeleteDC(v6);
  ReleaseDC(0, DC);
  return h;
}

```

## disassembly

```asm
0x1800637f0  mov     [rsp-8+arg_10], rbx
0x1800637f5  push    rbp
0x1800637f6  push    rsi
0x1800637f7  push    rdi
0x1800637f8  push    r12
0x1800637fa  push    r13
0x1800637fc  push    r14
0x1800637fe  push    r15
0x180063800  lea     rbp, [rsp-27h]
0x180063805  sub     rsp, 0A0h
0x18006380c  mov     rax, cs:__security_cookie
0x180063813  xor     rax, rsp
0x180063816  mov     [rbp+57h+var_40], rax
0x18006381a  xorps   xmm0, xmm0
0x18006381d  lea     r8, [rbp+57h+pv]; pv
0x180063821  mov     r15d, edx
0x180063824  mov     rdi, rcx
0x180063827  mov     edx, 20h ; ' '; c
0x18006382c  movups  [rbp+57h+pv], xmm0
0x180063830  movups  [rbp+57h+var_80], xmm0
0x180063834  call    cs:__imp_GetObjectA
0x18006383a  xor     r13d, r13d
0x18006383d  test    eax, eax
0x18006383f  jz      loc_1800639D3
0x180063845  movzx   eax, word ptr [rbp+57h+var_80+2]
0x180063849  mov     ecx, 0FFF8h
0x18006384e  and     ax, cx
0x180063851  cmp     ax, 18h
0x180063855  jb      loc_1800639D3
0x18006385b  mov     eax, dword ptr [rbp+57h+pv+4]
0x18006385e  xorps   xmm0, xmm0
0x180063861  mov     [rbp+57h+bmi.bmiHeader.biWidth], eax
0x180063864  xor     ecx, ecx; hWnd
0x180063866  mov     eax, dword ptr [rbp+57h+pv+8]
0x180063869  mov     [rbp+57h+bmi.bmiHeader.biHeight], eax
0x18006386c  movdqu  xmmword ptr [rbp+57h+bmi.bmiHeader.biSizeImage], xmm0
0x180063871  mov     qword ptr [rbp+57h+bmi.bmiHeader.biClrImportant], r13
0x180063875  mov     [rbp+57h+bmi.bmiHeader.biSize], 28h ; '('
0x18006387c  mov     qword ptr [rbp+57h+bmi.bmiHeader.biPlanes], 200001h
0x180063884  call    cs:__imp_GetDC
0x18006388a  mov     rcx, rax; hdc
0x18006388d  mov     r14, rax
0x180063890  call    cs:__imp_CreateCompatibleDC
0x180063896  mov     rbx, rax
0x180063899  test    r14, r14
0x18006389c  jz      loc_1800639BA
0x1800638a2  test    rax, rax
0x1800638a5  jz      loc_1800639BA
0x1800638ab  lea     rax, [rbp+57h+bmi]
0x1800638af  mov     [rsp+0D0h+usage], r13d; usage
0x1800638b4  mov     [rsp+0D0h+lpbmi], rax; lpbmi
0x1800638b9  mov     r9d, r15d; cLines
0x1800638bc  xor     r8d, r8d; start
0x1800638bf  mov     [rsp+0D0h+lpvBits], r13; lpvBits
0x1800638c4  mov     rdx, rdi; hbm
0x1800638c7  mov     rcx, rbx; hdc
0x1800638ca  call    cs:__imp_GetDIBits
0x1800638d0  mov     edx, [rbp+57h+bmi.bmiHeader.biSizeImage]; uBytes
0x1800638d3  lea     ecx, [r13+40h]; uFlags
0x1800638d7  call    cs:__imp_LocalAlloc
0x1800638dd  mov     rsi, rax
0x1800638e0  test    rax, rax
0x1800638e3  jz      loc_1800639BA
0x1800638e9  lea     rax, [rbp+57h+bmi]
0x1800638ed  mov     [rsp+0D0h+usage], r13d; usage
0x1800638f2  mov     [rsp+0D0h+lpbmi], rax; lpbmi
0x1800638f7  mov     r9d, r15d; cLines
0x1800638fa  xor     r8d, r8d; start
0x1800638fd  mov     [rsp+0D0h+lpvBits], rsi; lpvBits
0x180063902  mov     rdx, rdi; hbm
0x180063905  mov     rcx, rbx; hdc
0x180063908  call    cs:__imp_GetDIBits
0x18006390e  movzx   ecx, word ptr [rbp+57h+var_80+2]
0x180063912  xor     edx, edx
0x180063914  mov     eax, [rbp+57h+bmi.bmiHeader.biSizeImage]
0x180063917  mov     r10, rsi
0x18006391a  shr     ecx, 3
0x18006391d  mov     r9, rsi
0x180063920  div     ecx
0x180063922  mov     r11d, r13d
0x180063925  mov     r12d, eax
0x180063928  test    eax, eax
0x18006392a  jz      short loc_180063980
0x18006392c  mov     r13d, 20h ; ' '
0x180063932  movzx   r8d, byte ptr [r10]
0x180063936  mov     eax, 0AAAAAAABh
0x18006393b  movzx   ecx, byte ptr [r10+1]
0x180063940  add     r10, 2
0x180063944  movzx   edx, byte ptr [r10]
0x180063948  add     edx, ecx
0x18006394a  add     edx, r8d
0x18006394d  mul     edx
0x18006394f  lea     rax, [r9+2]
0x180063953  shr     edx, 1
0x180063955  mov     [r9], dl
0x180063958  mov     [r9+1], dl
0x18006395c  mov     [rax], dl
0x18006395e  cmp     word ptr [rbp+57h+var_80+2], r13w
0x180063963  jnz     short loc_18006396A
0x180063965  inc     r10
0x180063968  jmp     short loc_18006396E
0x18006396a  lea     rax, [r9+1]
0x18006396e  inc     r11d
0x180063971  lea     r9, [rax+2]
0x180063975  inc     r10
0x180063978  cmp     r11d, r12d
0x18006397b  jb      short loc_180063932
0x18006397d  xor     r13d, r13d
0x180063980  lea     rax, [rbp+57h+bmi]
0x180063984  mov     [rsp+0D0h+usage], r13d; ColorUse
0x180063989  mov     [rsp+0D0h+lpbmi], rax; lpbmi
0x18006398e  mov     r9d, r15d; cLines
0x180063991  xor     r8d, r8d; start
0x180063994  mov     [rsp+0D0h+lpvBits], rsi; lpBits
0x180063999  mov     rdx, rdi; hbm
0x18006399c  mov     rcx, rbx; hdc
0x18006399f  call    cs:__imp_SetDIBits
0x1800639a5  mov     rdx, rdi; h
0x1800639a8  mov     rcx, rbx; hdc
0x1800639ab  call    cs:__imp_SelectObject
0x1800639b1  mov     rcx, rsi; hMem
0x1800639b4  call    cs:__imp_LocalFree
0x1800639ba  mov     rcx, rbx; hdc
0x1800639bd  call    cs:__imp_DeleteDC
0x1800639c3  mov     rdx, r14; hDC
0x1800639c6  xor     ecx, ecx; hWnd
0x1800639c8  call    cs:__imp_ReleaseDC
0x1800639ce  mov     rax, rdi
0x1800639d1  jmp     short loc_1800639D5
0x1800639d3  xor     eax, eax
0x1800639d5  mov     rcx, [rbp+57h+var_40]
0x1800639d9  xor     rcx, rsp; StackCookie
0x1800639dc  call    __security_check_cookie
0x1800639e1  mov     rbx, [rsp+0D0h+arg_10]
0x1800639e9  add     rsp, 0A0h
0x1800639f0  pop     r15
0x1800639f2  pop     r14
0x1800639f4  pop     r13
0x1800639f6  pop     r12
0x1800639f8  pop     rdi
0x1800639f9  pop     rsi
0x1800639fa  pop     rbp
0x1800639fb  retn
```
