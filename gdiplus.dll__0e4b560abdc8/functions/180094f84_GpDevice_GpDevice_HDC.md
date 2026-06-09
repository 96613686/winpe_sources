# GpDevice::GpDevice(HDC__ *)

- ea: `0x180094f84`
- end: `0x180095194`
- name: `??0GpDevice@@QEAA@PEAUHDC__@@@Z`
- size: `528`
- prototype: `GpDevice *__fastcall(GpDevice *__hidden this, HDC hdc)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006ecbc`
- `0x1800e2458`

## callees

- `0x180094f84`
- `0x18009519c`
- `0x180095208`
- `0x180095238`
- `0x180095318`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800950ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800950de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800950ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800950de`
- `GDI32!CreateCompatibleDC` at `0x18009502e`
- `GDI32!CreateCompatibleDC` at `0x18009502e`
- `GDI32!GetDeviceCaps` at `0x180095046`
- `GDI32!GetDeviceCaps` at `0x18009506e`
- `GDI32!GetDeviceCaps` at `0x180095088`
- `GDI32!GetDeviceCaps` at `0x180095151`
- `GDI32!GetDeviceCaps` at `0x180095046`
- `GDI32!GetDeviceCaps` at `0x18009506e`
- `GDI32!GetDeviceCaps` at `0x180095088`
- `GDI32!GetDeviceCaps` at `0x180095151`

## pseudocode

```c
GpDevice *__fastcall GpDevice::GpDevice(GpDevice *this, HDC hdc)
{
  int v4; // edi
  EpScanGdiDci *v5; // rax
  EpScanGdiDci *v6; // rax
  EpScanGdiDci *v7; // rax
  EpScanGdiDci *v8; // rax

  *(_QWORD *)this = &GpDevice::`vftable';
  EpScanEngine::EpScanEngine((GpDevice *)((char *)this + 88));
  *((_DWORD *)this + 406) = 0;
  *((_QWORD *)this + 186) = 0;
  *((_QWORD *)this + 189) = 0;
  *((_QWORD *)this + 5) = 0;
  GpSemaphore::Initialize((GpDevice *)((char *)this + 1584));
  *((_QWORD *)this + 188) = hdc;
  *((_DWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 187) = 0;
  *((_QWORD *)this + 192) = 0;
  *((_QWORD *)this + 193) = 0;
  *((_QWORD *)this + 194) = 0;
  *((_QWORD *)this + 195) = 0;
  *((_QWORD *)this + 197) = 0;
  *((_QWORD *)this + 3) = CreateCompatibleDC(hdc);
  v4 = 1;
  if ( GetDeviceCaps(hdc, 2) != 1
    || GetDeviceCaps(hdc, 12) > 8
    || (GpDevice::PaletteChangeNotification(this), *((_QWORD *)this + 197)) )
  {
    *((_QWORD *)this + 190) = 0;
    *((_DWORD *)this + 382) = GetDeviceCaps(hdc, 8);
    *((_DWORD *)this + 383) = GetDeviceCaps(hdc, 10);
    v5 = (EpScanGdiDci *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x5B8u);
    if ( v5 )
      v6 = EpScanGdiDci::EpScanGdiDci(v5, this);
    else
      v6 = 0;
    *((_QWORD *)this + 187) = v6;
    v7 = (EpScanGdiDci *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x5B8u);
    if ( v7 )
      v8 = EpScanGdiDci::EpScanGdiDci(v7, this);
    else
      v8 = 0;
    *((_QWORD *)this + 186) = v8;
    if ( !*((_QWORD *)this + 187) || !v8 || !*((_QWORD *)this + 3) )
      v4 = 0;
    *((_DWORD *)this + 2) = v4 != 0 ? 1986348081 : 1279869254;
  }
  else
  {
    *((_DWORD *)this + 2) = 1279869254;
  }
  return this;
}

```

## disassembly

```asm
0x180094f84  mov     rax, rsp
0x180094f87  mov     [rax+10h], rbx
0x180094f8b  mov     [rax+18h], rsi
0x180094f8f  mov     [rax+20h], rdi
0x180094f93  mov     [rax+8], rcx
0x180094f97  push    r14
0x180094f99  sub     rsp, 20h
0x180094f9d  mov     rsi, rdx
0x180094fa0  mov     rbx, rcx
0x180094fa3  lea     rax, ??_7GpDevice@@6B@; const GpDevice::`vftable'
0x180094faa  mov     [rcx], rax
0x180094fad  add     rcx, 58h ; 'X'; this
0x180094fb1  call    ??0EpScanEngine@@QEAA@XZ; EpScanEngine::EpScanEngine(void)
0x180094fb6  lea     rcx, [rbx+630h]; this
0x180094fbd  xor     r14d, r14d
0x180094fc0  mov     [rcx+28h], r14d
0x180094fc4  mov     [rbx+5D0h], r14
0x180094fcb  mov     [rbx+5E8h], r14
0x180094fd2  mov     [rbx+28h], r14
0x180094fd6  call    ?Initialize@GpSemaphore@@QEAAXXZ; GpSemaphore::Initialize(void)
0x180094fdb  jmp     short loc_180094FEE
0x180094fdd  mov     rbx, [rsp+28h+arg_0]
0x180094fe2  mov     dword ptr [rbx+8], 4C494146h
0x180094fe9  jmp     loc_18009512A
0x180094fee  mov     [rbx+5E0h], rsi
0x180094ff5  mov     [rbx+0Ch], r14d
0x180094ff9  mov     [rbx+10h], r14
0x180094ffd  mov     [rbx+20h], r14
0x180095001  mov     [rbx+5D8h], r14
0x180095008  mov     [rbx+600h], r14
0x18009500f  mov     [rbx+608h], r14
0x180095016  mov     [rbx+610h], r14
0x18009501d  mov     [rbx+618h], r14
0x180095024  mov     [rbx+628h], r14
0x18009502b  mov     rcx, rsi; hdc
0x18009502e  call    cs:__imp_CreateCompatibleDC
0x180095035  nop     dword ptr [rax+rax+00h]
0x18009503a  mov     [rbx+18h], rax
0x18009503e  mov     edx, 2; index
0x180095043  mov     rcx, rsi; hdc
0x180095046  call    cs:__imp_GetDeviceCaps
0x18009504d  nop     dword ptr [rax+rax+00h]
0x180095052  mov     edi, 1
0x180095057  cmp     eax, edi
0x180095059  jz      loc_180095149
0x18009505f  mov     [rbx+5F0h], r14
0x180095066  mov     edx, 8; index
0x18009506b  mov     rcx, rsi; hdc
0x18009506e  call    cs:__imp_GetDeviceCaps
0x180095075  nop     dword ptr [rax+rax+00h]
0x18009507a  mov     [rbx+5F8h], eax
0x180095080  mov     edx, 0Ah; index
0x180095085  mov     rcx, rsi; hdc
0x180095088  call    cs:__imp_GetDeviceCaps
0x18009508f  nop     dword ptr [rax+rax+00h]
0x180095094  mov     [rbx+5FCh], eax
0x18009509a  mov     esi, 5B8h
0x18009509f  mov     r8d, esi; dwBytes
0x1800950a2  xor     edx, edx; dwFlags
0x1800950a4  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800950ab  call    cs:__imp_HeapAlloc
0x1800950b2  nop     dword ptr [rax+rax+00h]
0x1800950b7  test    rax, rax
0x1800950ba  jz      loc_180095184
0x1800950c0  mov     rdx, rbx; struct GpDevice *
0x1800950c3  mov     rcx, rax; this
0x1800950c6  call    ??0EpScanGdiDci@@QEAA@PEAVGpDevice@@@Z; EpScanGdiDci::EpScanGdiDci(GpDevice *)
0x1800950cb  mov     [rbx+5D8h], rax
0x1800950d2  mov     r8, rsi; dwBytes
0x1800950d5  xor     edx, edx; dwFlags
0x1800950d7  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800950de  call    cs:__imp_HeapAlloc
0x1800950e5  nop     dword ptr [rax+rax+00h]
0x1800950ea  test    rax, rax
0x1800950ed  jz      loc_18009518C
0x1800950f3  mov     rdx, rbx; struct GpDevice *
0x1800950f6  mov     rcx, rax; this
0x1800950f9  call    ??0EpScanGdiDci@@QEAA@PEAVGpDevice@@@Z; EpScanGdiDci::EpScanGdiDci(GpDevice *)
0x1800950fe  mov     [rbx+5D0h], rax
0x180095105  cmp     [rbx+5D8h], r14
0x18009510c  jz      short loc_180095144
0x18009510e  test    rax, rax
0x180095111  jz      short loc_180095144
0x180095113  cmp     [rbx+18h], r14
0x180095117  jz      short loc_180095144
0x180095119  neg     edi
0x18009511b  sbb     eax, eax
0x18009511d  and     eax, 2A1C02EBh
0x180095122  add     eax, 4C494146h
0x180095127  mov     [rbx+8], eax
0x18009512a  mov     rax, rbx
0x18009512d  mov     rbx, [rsp+28h+arg_8]
0x180095132  mov     rsi, [rsp+28h+arg_10]
0x180095137  mov     rdi, [rsp+28h+arg_18]
0x18009513c  add     rsp, 20h
0x180095140  pop     r14
0x180095142  retn
0x180095144  mov     edi, r14d
0x180095147  jmp     short loc_180095119
0x180095149  mov     edx, 0Ch; index
0x18009514e  mov     rcx, rsi; hdc
0x180095151  call    cs:__imp_GetDeviceCaps
0x180095158  nop     dword ptr [rax+rax+00h]
0x18009515d  cmp     eax, 8
0x180095160  jg      loc_18009505F
0x180095166  mov     rcx, rbx; this
0x180095169  call    ?PaletteChangeNotification@GpDevice@@QEAAXXZ; GpDevice::PaletteChangeNotification(void)
0x18009516e  cmp     [rbx+628h], r14
0x180095175  jnz     loc_18009505F
0x18009517b  mov     dword ptr [rbx+8], 4C494146h
0x180095182  jmp     short loc_18009512A
0x180095184  mov     rax, r14
0x180095187  jmp     loc_1800950CB
0x18009518c  mov     rax, r14
0x18009518f  jmp     loc_1800950FE
0x180174172  push    rbp
0x180174174  sub     rsp, 20h
0x180174178  mov     rbp, rdx
0x18017417b  mov     rax, [rcx]
0x18017417e  xor     ecx, ecx
0x180174180  cmp     dword ptr [rax], 0C0000017h
0x180174186  setz    cl
0x180174189  mov     eax, ecx
0x18017418b  add     rsp, 20h
0x18017418f  pop     rbp
0x180174190  retn
```
