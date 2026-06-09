# GpDevice::GpDevice(HDC__ *)

- ea: `0x180086668`
- end: `0x180086861`
- name: `??0GpDevice@@QEAA@PEAUHDC__@@@Z`
- size: `505`
- prototype: `GpDevice *__fastcall(GpDevice *__hidden this, HDC hdc)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006651c`
- `0x1800cc950`

## callees

- `0x180084d04`
- `0x180086668`
- `0x180086868`
- `0x18008692c`
- `0x180086998`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180086784`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800867b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180086784`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800867b7`
- `GDI32!CreateCompatibleDC` at `0x180086707`
- `GDI32!CreateCompatibleDC` at `0x180086707`
- `GDI32!GetDeviceCaps` at `0x18008671f`
- `GDI32!GetDeviceCaps` at `0x180086747`
- `GDI32!GetDeviceCaps` at `0x180086761`
- `GDI32!GetDeviceCaps` at `0x18008681e`
- `GDI32!GetDeviceCaps` at `0x18008671f`
- `GDI32!GetDeviceCaps` at `0x180086747`
- `GDI32!GetDeviceCaps` at `0x180086761`
- `GDI32!GetDeviceCaps` at `0x18008681e`

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
0x180086668  mov     [rsp+arg_0], rcx
0x18008666d  push    rbx
0x18008666e  push    rsi
0x18008666f  push    rdi
0x180086670  push    r14
0x180086672  sub     rsp, 28h
0x180086676  mov     rsi, rdx
0x180086679  mov     rbx, rcx
0x18008667c  lea     rax, ??_7GpDevice@@6B@; const GpDevice::`vftable'
0x180086683  mov     [rcx], rax
0x180086686  add     rcx, 58h ; 'X'; this
0x18008668a  call    ??0EpScanEngine@@QEAA@XZ; EpScanEngine::EpScanEngine(void)
0x18008668f  lea     rcx, [rbx+630h]; this
0x180086696  xor     r14d, r14d
0x180086699  mov     [rcx+28h], r14d
0x18008669d  mov     [rbx+5D0h], r14
0x1800866a4  mov     [rbx+5E8h], r14
0x1800866ab  mov     [rbx+28h], r14
0x1800866af  call    ?Initialize@GpSemaphore@@QEAAXXZ; GpSemaphore::Initialize(void)
0x1800866b4  jmp     short loc_1800866C7
0x1800866b6  mov     rbx, [rsp+48h+arg_0]
0x1800866bb  mov     dword ptr [rbx+8], 4C494146h
0x1800866c2  jmp     loc_1800867FB
0x1800866c7  mov     [rbx+5E0h], rsi
0x1800866ce  mov     [rbx+0Ch], r14d
0x1800866d2  mov     [rbx+10h], r14
0x1800866d6  mov     [rbx+20h], r14
0x1800866da  mov     [rbx+5D8h], r14
0x1800866e1  mov     [rbx+600h], r14
0x1800866e8  mov     [rbx+608h], r14
0x1800866ef  mov     [rbx+610h], r14
0x1800866f6  mov     [rbx+618h], r14
0x1800866fd  mov     [rbx+628h], r14
0x180086704  mov     rcx, rsi; hdc
0x180086707  call    cs:__imp_CreateCompatibleDC
0x18008670e  nop     dword ptr [rax+rax+00h]
0x180086713  mov     [rbx+18h], rax
0x180086717  mov     edx, 2; index
0x18008671c  mov     rcx, rsi; hdc
0x18008671f  call    cs:__imp_GetDeviceCaps
0x180086726  nop     dword ptr [rax+rax+00h]
0x18008672b  mov     edi, 1
0x180086730  cmp     eax, edi
0x180086732  jz      loc_180086816
0x180086738  mov     [rbx+5F0h], r14
0x18008673f  mov     edx, 8; index
0x180086744  mov     rcx, rsi; hdc
0x180086747  call    cs:__imp_GetDeviceCaps
0x18008674e  nop     dword ptr [rax+rax+00h]
0x180086753  mov     [rbx+5F8h], eax
0x180086759  mov     edx, 0Ah; index
0x18008675e  mov     rcx, rsi; hdc
0x180086761  call    cs:__imp_GetDeviceCaps
0x180086768  nop     dword ptr [rax+rax+00h]
0x18008676d  mov     [rbx+5FCh], eax
0x180086773  mov     esi, 5B8h
0x180086778  mov     r8d, esi; dwBytes
0x18008677b  xor     edx, edx; dwFlags
0x18008677d  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180086784  call    cs:__imp_HeapAlloc
0x18008678b  nop     dword ptr [rax+rax+00h]
0x180086790  test    rax, rax
0x180086793  jz      loc_180086851
0x180086799  mov     rdx, rbx; struct GpDevice *
0x18008679c  mov     rcx, rax; this
0x18008679f  call    ??0EpScanGdiDci@@QEAA@PEAVGpDevice@@@Z; EpScanGdiDci::EpScanGdiDci(GpDevice *)
0x1800867a4  mov     [rbx+5D8h], rax
0x1800867ab  mov     r8, rsi; dwBytes
0x1800867ae  xor     edx, edx; dwFlags
0x1800867b0  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800867b7  call    cs:__imp_HeapAlloc
0x1800867be  nop     dword ptr [rax+rax+00h]
0x1800867c3  test    rax, rax
0x1800867c6  jz      loc_180086859
0x1800867cc  mov     rdx, rbx; struct GpDevice *
0x1800867cf  mov     rcx, rax; this
0x1800867d2  call    ??0EpScanGdiDci@@QEAA@PEAVGpDevice@@@Z; EpScanGdiDci::EpScanGdiDci(GpDevice *)
0x1800867d7  mov     [rbx+5D0h], rax
0x1800867de  cmp     [rbx+5D8h], r14
0x1800867e5  jnz     short loc_180086809
0x1800867e7  mov     edi, r14d
0x1800867ea  neg     edi
0x1800867ec  sbb     eax, eax
0x1800867ee  and     eax, 2A1C02EBh
0x1800867f3  add     eax, 4C494146h
0x1800867f8  mov     [rbx+8], eax
0x1800867fb  mov     rax, rbx
0x1800867fe  add     rsp, 28h
0x180086802  pop     r14
0x180086804  pop     rdi
0x180086805  pop     rsi
0x180086806  pop     rbx
0x180086807  retn
0x180086809  test    rax, rax
0x18008680c  jz      short loc_1800867E7
0x18008680e  cmp     [rbx+18h], r14
0x180086812  jnz     short loc_1800867EA
0x180086814  jmp     short loc_1800867E7
0x180086816  mov     edx, 0Ch; index
0x18008681b  mov     rcx, rsi; hdc
0x18008681e  call    cs:__imp_GetDeviceCaps
0x180086825  nop     dword ptr [rax+rax+00h]
0x18008682a  cmp     eax, 8
0x18008682d  jg      loc_180086738
0x180086833  mov     rcx, rbx; this
0x180086836  call    ?PaletteChangeNotification@GpDevice@@QEAAXXZ; GpDevice::PaletteChangeNotification(void)
0x18008683b  cmp     [rbx+628h], r14
0x180086842  jnz     loc_180086738
0x180086848  mov     dword ptr [rbx+8], 4C494146h
0x18008684f  jmp     short loc_1800867FB
0x180086851  mov     rax, r14
0x180086854  jmp     loc_1800867A4
0x180086859  mov     rax, r14
0x18008685c  jmp     loc_1800867D7
0x1801714d2  push    rbp
0x1801714d4  sub     rsp, 20h
0x1801714d8  mov     rbp, rdx
0x1801714db  mov     rax, [rcx]
0x1801714de  xor     ecx, ecx
0x1801714e0  cmp     dword ptr [rax], 0C0000017h
0x1801714e6  setz    cl
0x1801714e9  mov     eax, ecx
0x1801714eb  add     rsp, 20h
0x1801714ef  pop     rbp
0x1801714f0  retn
```
