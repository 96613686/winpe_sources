# GdiGetSpoolFileHandle

- ea: `0x180060600`
- end: `0x18006081a`
- name: `GdiGetSpoolFileHandle`
- size: `538`
- prototype: `HANDLE __stdcall(LPWSTR pwszPrinterName, LPDEVMODEW pDevmode, LPWSTR pwszDocName)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18009a9e0`

## callees

- `0x180060600`
- `0x180060820`
- `0x180080604`
- `0x1800a68d4`
- `0x1800a8010`

## import_xrefs

- `GDI32!DeleteDC` at `0x1800607c0`
- `GDI32!DeleteDC` at `0x1800607c0`
- `GDI32!CreateDCW` at `0x1800606e1`
- `GDI32!CreateDCW` at `0x1800606e1`
- `GDI32!fpClosePrinter` at `0x1800607cc`
- `ntdll!RtlFreeHeap` at `0x1800607fc`
- `ntdll!RtlFreeHeap` at `0x1800607fc`
- `ntdll!RtlAllocateHeap` at `0x18006065f`
- `ntdll!RtlAllocateHeap` at `0x180060716`
- `ntdll!RtlAllocateHeap` at `0x18006065f`
- `ntdll!RtlAllocateHeap` at `0x180060716`
- `ntdll!RtlDecodePointer` at `0x1800606a1`
- `ntdll!RtlDecodePointer` at `0x1800607d6`
- `ntdll!RtlDecodePointer` at `0x1800606a1`
- `ntdll!RtlDecodePointer` at `0x1800607d6`

## pseudocode

```c
HANDLE __stdcall GdiGetSpoolFileHandle(LPWSTR pwszPrinterName, LPDEVMODEW pDevmode, LPWSTR pwszDocName)
{
  WORD *p_dmDriverExtra; // rsi
  WORD *p_dmSize; // rbp
  unsigned __int64 v8; // r8
  _DWORD *Heap; // rax
  _DWORD *v10; // rbx
  unsigned __int64 v11; // r8
  PVOID v12; // rax
  _QWORD *v13; // r14
  HDC DCW; // rax
  PVOID v15; // rax
  void *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  void (__fastcall *v20)(_QWORD); // rax

  if ( !ghSpooler && !(unsigned int)bLoadSpooler() )
    return 0;
  p_dmDriverExtra = &pDevmode->dmDriverExtra;
  p_dmSize = &pDevmode->dmSize;
  v8 = pDevmode ? *p_dmDriverExtra + (unsigned __int64)*p_dmSize : 0LL;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8 + 104);
  v10 = Heap;
  if ( !Heap )
    return 0;
  if ( pDevmode )
    v11 = *p_dmDriverExtra + (unsigned __int64)*p_dmSize;
  else
    v11 = 0;
  memset_0(Heap, 0, v11 + 104);
  v12 = RtlDecodePointer(fpOpenPrinterW);
  v13 = v10 + 4;
  if ( !((unsigned int (__fastcall *)(LPWSTR, _DWORD *, _QWORD))v12)(pwszDocName, v10 + 4, 0) || !*v13 )
  {
LABEL_24:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    return 0;
  }
  DCW = CreateDCW(&Default, pwszPrinterName, &Default, pDevmode);
  *((_QWORD *)v10 + 1) = DCW;
  if ( !DCW )
  {
LABEL_23:
    v20 = (void (__fastcall *)(_QWORD))RtlDecodePointer(fpClosePrinter);
    v20(*v13);
    goto LABEL_24;
  }
  v10[14] = 20;
  v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x320u);
  *((_QWORD *)v10 + 6) = v15;
  if ( !v15 )
  {
    DeleteDC(*((HDC *)v10 + 1));
    goto LABEL_23;
  }
  *v10 = 1397770324;
  if ( pDevmode )
  {
    *((_QWORD *)v10 + 3) = v10 + 26;
    memcpy_0(v10 + 26, pDevmode, *p_dmDriverExtra + (unsigned __int64)*p_dmSize);
  }
  else
  {
    *((_QWORD *)v10 + 3) = 0;
  }
  v16 = (void *)*((_QWORD *)v10 + 6);
  *((_QWORD *)v10 + 4) = *((_QWORD *)v10 + 3);
  v17 = (unsigned int)v10[14];
  v10[10] = 0;
  *((_QWORD *)v10 + 11) = 0;
  memset_0(v16, 0, 40 * v17);
  v18 = *((_QWORD *)v10 + 4);
  v10[24] = 3;
  if ( v18 && (*(_DWORD *)(v18 + 72) & 0x800) != 0 && *(_WORD *)(v18 + 92) == 2 )
    v10[24] = 1;
  v10[25] = 1;
  return v10;
}

```

## disassembly

```asm
0x180060600  push    rbx
0x180060602  push    rbp
0x180060603  push    rsi
0x180060604  push    rdi
0x180060605  push    r12
0x180060607  push    r14
0x180060609  push    r15
0x18006060b  sub     rsp, 20h
0x18006060f  cmp     cs:ghSpooler, 0
0x180060617  mov     r12, r8
0x18006061a  mov     rdi, rdx
0x18006061d  mov     r15, rcx
0x180060620  jnz     short loc_18006062F
0x180060622  call    bLoadSpooler
0x180060627  test    eax, eax
0x180060629  jz      loc_180060808
0x18006062f  lea     rsi, [rdi+46h]
0x180060633  lea     rbp, [rdi+44h]
0x180060637  test    rdi, rdi
0x18006063a  jz      short loc_180060649
0x18006063c  movzx   r8d, word ptr [rbp+0]
0x180060641  movzx   eax, word ptr [rsi]
0x180060644  add     r8, rax
0x180060647  jmp     short loc_18006064C
0x180060649  xor     r8d, r8d
0x18006064c  mov     rcx, gs:60h
0x180060655  add     r8, 68h ; 'h'; Size
0x180060659  xor     edx, edx; Flags
0x18006065b  mov     rcx, [rcx+30h]; HeapHandle
0x18006065f  call    cs:__imp_RtlAllocateHeap
0x180060666  nop     dword ptr [rax+rax+00h]
0x18006066b  mov     rbx, rax
0x18006066e  test    rax, rax
0x180060671  jz      loc_180060808
0x180060677  test    rdi, rdi
0x18006067a  jz      short loc_180060689
0x18006067c  movzx   r8d, word ptr [rbp+0]
0x180060681  movzx   ecx, word ptr [rsi]
0x180060684  add     r8, rcx
0x180060687  jmp     short loc_18006068C
0x180060689  xor     r8d, r8d
0x18006068c  add     r8, 68h ; 'h'; Size
0x180060690  xor     edx, edx; Val
0x180060692  mov     rcx, rbx; void *
0x180060695  call    memset_0
0x18006069a  mov     rcx, cs:fpOpenPrinterW; Pointer
0x1800606a1  call    cs:__imp_RtlDecodePointer
0x1800606a8  nop     dword ptr [rax+rax+00h]
0x1800606ad  lea     r14, [rbx+10h]
0x1800606b1  xor     r8d, r8d
0x1800606b4  mov     rdx, r14
0x1800606b7  mov     rcx, r12
0x1800606ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606bf  test    eax, eax
0x1800606c1  jz      loc_1800607EA
0x1800606c7  cmp     qword ptr [r14], 0
0x1800606cb  jz      loc_1800607EA
0x1800606d1  lea     rcx, Default; pwszDriver
0x1800606d8  mov     r9, rdi; pdm
0x1800606db  mov     r8, rcx; pszPort
0x1800606de  mov     rdx, r15; pwszDevice
0x1800606e1  call    cs:__imp_CreateDCW
0x1800606e8  nop     dword ptr [rax+rax+00h]
0x1800606ed  mov     [rbx+8], rax
0x1800606f1  test    rax, rax
0x1800606f4  jz      loc_1800607CC
0x1800606fa  mov     dword ptr [rbx+38h], 14h
0x180060701  xor     edx, edx; Flags
0x180060703  mov     rcx, gs:60h
0x18006070c  mov     r8d, 320h; Size
0x180060712  mov     rcx, [rcx+30h]; HeapHandle
0x180060716  call    cs:__imp_RtlAllocateHeap
0x18006071d  nop     dword ptr [rax+rax+00h]
0x180060722  mov     [rbx+30h], rax
0x180060726  test    rax, rax
0x180060729  jz      loc_1800607BC
0x18006072f  mov     dword ptr [rbx], 53504854h
0x180060735  test    rdi, rdi
0x180060738  jz      short loc_180060757
0x18006073a  lea     rcx, [rbx+68h]; void *
0x18006073e  mov     rdx, rdi; Src
0x180060741  mov     [rbx+18h], rcx
0x180060745  movzx   r8d, word ptr [rbp+0]
0x18006074a  movzx   eax, word ptr [rsi]
0x18006074d  add     r8, rax; Size
0x180060750  call    memcpy_0
0x180060755  jmp     short loc_18006075F
0x180060757  mov     qword ptr [rbx+18h], 0
0x18006075f  mov     rax, [rbx+18h]
0x180060763  xor     edx, edx; Val
0x180060765  mov     rcx, [rbx+30h]; void *
0x180060769  mov     [rbx+20h], rax
0x18006076d  mov     eax, [rbx+38h]
0x180060770  mov     dword ptr [rbx+28h], 0
0x180060777  mov     qword ptr [rbx+58h], 0
0x18006077f  lea     r8, [rax+rax*4]
0x180060783  shl     r8, 3; Size
0x180060787  call    memset_0
0x18006078c  mov     rax, [rbx+20h]
0x180060790  mov     ecx, 1
0x180060795  mov     dword ptr [rbx+60h], 3
0x18006079c  test    rax, rax
0x18006079f  jz      short loc_1800607B4
0x1800607a1  test    dword ptr [rax+48h], 800h
0x1800607a8  jz      short loc_1800607B4
0x1800607aa  cmp     word ptr [rax+5Ch], 2
0x1800607af  jnz     short loc_1800607B4
0x1800607b1  mov     [rbx+60h], ecx
0x1800607b4  mov     [rbx+64h], ecx
0x1800607b7  mov     rax, rbx
0x1800607ba  jmp     short loc_18006080A
0x1800607bc  mov     rcx, [rbx+8]; hdc
0x1800607c0  call    cs:__imp_DeleteDC
0x1800607c7  nop     dword ptr [rax+rax+00h]
0x1800607cc  mov     rcx, cs:__imp_fpClosePrinter
0x1800607d3  mov     rcx, [rcx]; Pointer
0x1800607d6  call    cs:__imp_RtlDecodePointer
0x1800607dd  nop     dword ptr [rax+rax+00h]
0x1800607e2  mov     rcx, [r14]
0x1800607e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607ea  mov     rcx, gs:60h
0x1800607f3  mov     r8, rbx; P
0x1800607f6  xor     edx, edx; Flags
0x1800607f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800607fc  call    cs:__imp_RtlFreeHeap
0x180060803  nop     dword ptr [rax+rax+00h]
0x180060808  xor     eax, eax
0x18006080a  add     rsp, 20h
0x18006080e  pop     r15
0x180060810  pop     r14
0x180060812  pop     r12
0x180060814  pop     rdi
0x180060815  pop     rsi
0x180060816  pop     rbp
0x180060817  pop     rbx
0x180060818  retn
```
