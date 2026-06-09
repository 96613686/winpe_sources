# GpDevice::GpDevice(HDC__ *)

- ea: `0x18009d2dc`
- end: `0x18009d4a7`
- name: `??0GpDevice@@QEAA@PEAUHDC__@@@Z`
- size: `459`
- prototype: `GpDevice *__fastcall(GpDevice *__hidden this, HDC hdc)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007a18`
- `0x18009e77c`

## callees

- `0x18009d2dc`
- `0x18009d4b0`
- `0x18009d574`
- `0x18009d5e0`
- `0x18009e37c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d3e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d40d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d3e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d40d`
- `GDI32!CreateCompatibleDC` at `0x18009d37b`
- `GDI32!CreateCompatibleDC` at `0x18009d37b`
- `GDI32!GetDeviceCaps` at `0x18009d38d`
- `GDI32!GetDeviceCaps` at `0x18009d3af`
- `GDI32!GetDeviceCaps` at `0x18009d3c3`
- `GDI32!GetDeviceCaps` at `0x18009d46d`
- `GDI32!GetDeviceCaps` at `0x18009d38d`
- `GDI32!GetDeviceCaps` at `0x18009d3af`
- `GDI32!GetDeviceCaps` at `0x18009d3c3`
- `GDI32!GetDeviceCaps` at `0x18009d46d`

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
    || (GpDevice::PaletteChangeNotification((HDC *)this), *((_QWORD *)this + 197)) )
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
0x18009d2dc  mov     [rsp+arg_0], rcx
0x18009d2e1  push    rbx
0x18009d2e2  push    rsi
0x18009d2e3  push    rdi
0x18009d2e4  push    r14
0x18009d2e6  sub     rsp, 28h
0x18009d2ea  mov     rsi, rdx
0x18009d2ed  mov     rbx, rcx
0x18009d2f0  lea     rax, ??_7GpDevice@@6B@; const GpDevice::`vftable'
0x18009d2f7  mov     [rcx], rax
0x18009d2fa  add     rcx, 58h ; 'X'; this
0x18009d2fe  call    ??0EpScanEngine@@QEAA@XZ; EpScanEngine::EpScanEngine(void)
0x18009d303  lea     rcx, [rbx+630h]; this
0x18009d30a  xor     r14d, r14d
0x18009d30d  mov     [rcx+28h], r14d
0x18009d311  mov     [rbx+5D0h], r14
0x18009d318  mov     [rbx+5E8h], r14
0x18009d31f  mov     [rbx+28h], r14
0x18009d323  call    ?Initialize@GpSemaphore@@QEAAXXZ; GpSemaphore::Initialize(void)
0x18009d328  jmp     short loc_18009D33B
0x18009d32a  mov     rbx, [rsp+48h+arg_0]
0x18009d32f  mov     dword ptr [rbx+8], 4C494146h
0x18009d336  jmp     loc_18009D44B
0x18009d33b  mov     [rbx+5E0h], rsi
0x18009d342  mov     [rbx+0Ch], r14d
0x18009d346  mov     [rbx+10h], r14
0x18009d34a  mov     [rbx+20h], r14
0x18009d34e  mov     [rbx+5D8h], r14
0x18009d355  mov     [rbx+600h], r14
0x18009d35c  mov     [rbx+608h], r14
0x18009d363  mov     [rbx+610h], r14
0x18009d36a  mov     [rbx+618h], r14
0x18009d371  mov     [rbx+628h], r14
0x18009d378  mov     rcx, rsi; hdc
0x18009d37b  call    cs:__imp_CreateCompatibleDC
0x18009d381  mov     [rbx+18h], rax
0x18009d385  mov     edx, 2; index
0x18009d38a  mov     rcx, rsi; hdc
0x18009d38d  call    cs:__imp_GetDeviceCaps
0x18009d393  mov     edi, 1
0x18009d398  cmp     eax, edi
0x18009d39a  jz      loc_18009D465
0x18009d3a0  mov     [rbx+5F0h], r14
0x18009d3a7  mov     edx, 8; index
0x18009d3ac  mov     rcx, rsi; hdc
0x18009d3af  call    cs:__imp_GetDeviceCaps
0x18009d3b5  mov     [rbx+5F8h], eax
0x18009d3bb  mov     edx, 0Ah; index
0x18009d3c0  mov     rcx, rsi; hdc
0x18009d3c3  call    cs:__imp_GetDeviceCaps
0x18009d3c9  mov     [rbx+5FCh], eax
0x18009d3cf  mov     esi, 5B8h
0x18009d3d4  mov     r8d, esi; dwBytes
0x18009d3d7  xor     edx, edx; dwFlags
0x18009d3d9  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18009d3e0  call    cs:__imp_HeapAlloc
0x18009d3e6  test    rax, rax
0x18009d3e9  jz      loc_18009D49A
0x18009d3ef  mov     rdx, rbx; struct GpDevice *
0x18009d3f2  mov     rcx, rax; this
0x18009d3f5  call    ??0EpScanGdiDci@@QEAA@PEAVGpDevice@@@Z; EpScanGdiDci::EpScanGdiDci(GpDevice *)
0x18009d3fa  mov     [rbx+5D8h], rax
0x18009d401  mov     r8, rsi; dwBytes
0x18009d404  xor     edx, edx; dwFlags
0x18009d406  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18009d40d  call    cs:__imp_HeapAlloc
0x18009d413  test    rax, rax
0x18009d416  jz      loc_18009D4A2
0x18009d41c  mov     rdx, rbx; struct GpDevice *
0x18009d41f  mov     rcx, rax; this
0x18009d422  call    ??0EpScanGdiDci@@QEAA@PEAVGpDevice@@@Z; EpScanGdiDci::EpScanGdiDci(GpDevice *)
0x18009d427  mov     [rbx+5D0h], rax
0x18009d42e  cmp     [rbx+5D8h], r14
0x18009d435  jnz     short loc_18009D458
0x18009d437  mov     edi, r14d
0x18009d43a  neg     edi
0x18009d43c  sbb     eax, eax
0x18009d43e  and     eax, 2A1C02EBh
0x18009d443  add     eax, 4C494146h
0x18009d448  mov     [rbx+8], eax
0x18009d44b  mov     rax, rbx
0x18009d44e  add     rsp, 28h
0x18009d452  pop     r14
0x18009d454  pop     rdi
0x18009d455  pop     rsi
0x18009d456  pop     rbx
0x18009d457  retn
0x18009d458  test    rax, rax
0x18009d45b  jz      short loc_18009D437
0x18009d45d  cmp     [rbx+18h], r14
0x18009d461  jnz     short loc_18009D43A
0x18009d463  jmp     short loc_18009D437
0x18009d465  mov     edx, 0Ch; index
0x18009d46a  mov     rcx, rsi; hdc
0x18009d46d  call    cs:__imp_GetDeviceCaps
0x18009d473  cmp     eax, 8
0x18009d476  jg      loc_18009D3A0
0x18009d47c  mov     rcx, rbx; this
0x18009d47f  call    ?PaletteChangeNotification@GpDevice@@QEAAXXZ; GpDevice::PaletteChangeNotification(void)
0x18009d484  cmp     [rbx+628h], r14
0x18009d48b  jnz     loc_18009D3A0
0x18009d491  mov     dword ptr [rbx+8], 4C494146h
0x18009d498  jmp     short loc_18009D44B
0x18009d49a  mov     rax, r14
0x18009d49d  jmp     loc_18009D3FA
0x18009d4a2  mov     rax, r14
0x18009d4a5  jmp     short loc_18009D427
0x180168548  push    rbp
0x18016854a  sub     rsp, 20h
0x18016854e  mov     rbp, rdx
0x180168551  mov     rax, [rcx]
0x180168554  xor     ecx, ecx
0x180168556  cmp     dword ptr [rax], 0C0000017h
0x18016855c  setz    cl
0x18016855f  mov     eax, ecx
0x180168561  add     rsp, 20h
0x180168565  pop     rbp
0x180168566  retn
```
