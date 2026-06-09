# CreateColorBitmap

- ea: `0x1800852a0`
- end: `0x180085388`
- name: `CreateColorBitmap`
- size: `232`
- prototype: `__int64 __fastcall(int cx, int cy)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005058c`
- `0x18005506c`
- `0x18005ffa0`
- `0x18006e230`
- `0x18007b070`
- `0x18007b364`
- `0x18007ff98`
- `0x180081170`
- `0x180082eac`
- `0x180083ed0`

## callees

- `0x1800115f0`
- `0x1800852a0`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180085344`
- `GDI32!CreateDIBSection` at `0x180085344`
- `GDI32!CreateCompatibleBitmap` at `0x180085354`
- `GDI32!CreateCompatibleBitmap` at `0x180085354`
- `GDI32!GetDeviceCaps` at `0x1800852d2`
- `GDI32!GetDeviceCaps` at `0x1800852d2`
- `USER32!GetDC` at `0x1800852c1`
- `USER32!GetDC` at `0x1800852c1`
- `USER32!ReleaseDC` at `0x180085362`
- `USER32!ReleaseDC` at `0x180085362`
- `USER32!GetSystemMetrics` at `0x1800852e3`
- `USER32!GetSystemMetrics` at `0x1800852f5`
- `USER32!GetSystemMetrics` at `0x1800852e3`
- `USER32!GetSystemMetrics` at `0x1800852f5`

## pseudocode

```c
HBITMAP __fastcall CreateColorBitmap(int cx, int cy)
{
  HDC DC; // rbx
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v6; // rdi
  void *ppvBits; // [rsp+30h] [rbp-58h] BYREF
  BITMAPINFO pbmi; // [rsp+38h] [rbp-50h] BYREF

  DC = GetDC(0);
  if ( (GetDeviceCaps(DC, 38) & 0x100) != 0 || GetSystemMetrics(80) <= 1 || GetSystemMetrics(81) )
  {
    CompatibleBitmap = CreateCompatibleBitmap(DC, cx, cy);
  }
  else
  {
    ppvBits = 0;
    memset(&pbmi.bmiHeader.biCompression, 0, 28);
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biWidth = cx;
    pbmi.bmiHeader.biHeight = cy;
    *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    CompatibleBitmap = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
  }
  v6 = CompatibleBitmap;
  ReleaseDC(0, DC);
  return v6;
}

```

## disassembly

```asm
0x1800852a0  mov     [rsp+arg_10], rbx
0x1800852a5  push    rbp
0x1800852a6  push    rsi
0x1800852a7  push    rdi
0x1800852a8  sub     rsp, 70h
0x1800852ac  mov     rax, cs:__security_cookie
0x1800852b3  xor     rax, rsp
0x1800852b6  mov     [rsp+88h+var_20], rax
0x1800852bb  mov     edi, ecx
0x1800852bd  mov     esi, edx
0x1800852bf  xor     ecx, ecx; hWnd
0x1800852c1  call    cs:__imp_GetDC
0x1800852c7  mov     rcx, rax; hdc
0x1800852ca  mov     edx, 26h ; '&'; index
0x1800852cf  mov     rbx, rax
0x1800852d2  call    cs:__imp_GetDeviceCaps
0x1800852d8  bt      eax, 8
0x1800852dc  jb      short loc_18008534C
0x1800852de  mov     ecx, 50h ; 'P'; nIndex
0x1800852e3  call    cs:__imp_GetSystemMetrics
0x1800852e9  mov     ebp, 1
0x1800852ee  cmp     eax, ebp
0x1800852f0  jle     short loc_18008534C
0x1800852f2  lea     ecx, [rbp+50h]; nIndex
0x1800852f5  call    cs:__imp_GetSystemMetrics
0x1800852fb  xor     ecx, ecx
0x1800852fd  test    eax, eax
0x1800852ff  jnz     short loc_18008534C
0x180085301  xorps   xmm0, xmm0
0x180085304  mov     [rsp+88h+offset], ecx; offset
0x180085308  mov     [rsp+88h+hSection], rcx; hSection
0x18008530d  lea     r9, [rsp+88h+ppvBits]; ppvBits
0x180085312  mov     [rsp+88h+ppvBits], rcx
0x180085317  lea     rdx, [rsp+88h+pbmi]; pbmi
0x18008531c  movups  xmmword ptr [rsp+88h+pbmi.bmiHeader.biCompression], xmm0
0x180085321  mov     rcx, rbx; hdc
0x180085324  mov     [rsp+88h+pbmi.bmiHeader.biSize], 28h ; '('
0x18008532c  xor     r8d, r8d; usage
0x18008532f  mov     [rsp+88h+pbmi.bmiHeader.biWidth], edi
0x180085333  movups  xmmword ptr [rsp+88h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x180085338  mov     [rsp+88h+pbmi.bmiHeader.biHeight], esi
0x18008533c  mov     dword ptr [rsp+88h+pbmi.bmiHeader.biPlanes], 200001h
0x180085344  call    cs:__imp_CreateDIBSection
0x18008534a  jmp     short loc_18008535A
0x18008534c  mov     r8d, esi; cy
0x18008534f  mov     edx, edi; cx
0x180085351  mov     rcx, rbx; hdc
0x180085354  call    cs:__imp_CreateCompatibleBitmap
0x18008535a  mov     rdx, rbx; hDC
0x18008535d  xor     ecx, ecx; hWnd
0x18008535f  mov     rdi, rax
0x180085362  call    cs:__imp_ReleaseDC
0x180085368  mov     rax, rdi
0x18008536b  mov     rcx, [rsp+88h+var_20]
0x180085370  xor     rcx, rsp; StackCookie
0x180085373  call    __security_check_cookie
0x180085378  mov     rbx, [rsp+88h+arg_10]
0x180085380  add     rsp, 70h
0x180085384  pop     rdi
0x180085385  pop     rsi
0x180085386  pop     rbp
0x180085387  retn
```
