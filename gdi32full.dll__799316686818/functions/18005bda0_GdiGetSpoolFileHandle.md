# GdiGetSpoolFileHandle

- ea: `0x18005bda0`
- end: `0x18005bf8f`
- name: `GdiGetSpoolFileHandle`
- size: `495`
- prototype: `HANDLE __stdcall(LPWSTR pwszPrinterName, LPDEVMODEW pDevmode, LPWSTR pwszDocName)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180094b70`

## callees

- `0x18005bda0`
- `0x18005bf98`
- `0x18007ba24`
- `0x1800a3514`
- `0x1800a5010`

## import_xrefs

- `GDI32!DeleteDC` at `0x18005bf48`
- `GDI32!DeleteDC` at `0x18005bf48`
- `GDI32!CreateDCW` at `0x18005be75`
- `GDI32!CreateDCW` at `0x18005be75`
- `GDI32!fpClosePrinter` at `0x18005bf4e`
- `ntdll!RtlFreeHeap` at `0x18005bf78`
- `ntdll!RtlFreeHeap` at `0x18005bf78`
- `ntdll!RtlAllocateHeap` at `0x18005bdff`
- `ntdll!RtlAllocateHeap` at `0x18005bea4`
- `ntdll!RtlAllocateHeap` at `0x18005bdff`
- `ntdll!RtlAllocateHeap` at `0x18005bea4`
- `ntdll!RtlDecodePointer` at `0x18005be3b`
- `ntdll!RtlDecodePointer` at `0x18005bf58`
- `ntdll!RtlDecodePointer` at `0x18005be3b`
- `ntdll!RtlDecodePointer` at `0x18005bf58`

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
0x18005bda0  push    rbx
0x18005bda2  push    rbp
0x18005bda3  push    rsi
0x18005bda4  push    rdi
0x18005bda5  push    r12
0x18005bda7  push    r14
0x18005bda9  push    r15
0x18005bdab  sub     rsp, 20h
0x18005bdaf  cmp     cs:ghSpooler, 0
0x18005bdb7  mov     r12, r8
0x18005bdba  mov     rdi, rdx
0x18005bdbd  mov     r15, rcx
0x18005bdc0  jnz     short loc_18005BDCF
0x18005bdc2  call    bLoadSpooler
0x18005bdc7  test    eax, eax
0x18005bdc9  jz      loc_18005BF7E
0x18005bdcf  lea     rsi, [rdi+46h]
0x18005bdd3  lea     rbp, [rdi+44h]
0x18005bdd7  test    rdi, rdi
0x18005bdda  jz      short loc_18005BDE9
0x18005bddc  movzx   r8d, word ptr [rbp+0]
0x18005bde1  movzx   eax, word ptr [rsi]
0x18005bde4  add     r8, rax
0x18005bde7  jmp     short loc_18005BDEC
0x18005bde9  xor     r8d, r8d
0x18005bdec  mov     rcx, gs:60h
0x18005bdf5  add     r8, 68h ; 'h'; Size
0x18005bdf9  xor     edx, edx; Flags
0x18005bdfb  mov     rcx, [rcx+30h]; HeapHandle
0x18005bdff  call    cs:__imp_RtlAllocateHeap
0x18005be05  mov     rbx, rax
0x18005be08  test    rax, rax
0x18005be0b  jz      loc_18005BF7E
0x18005be11  test    rdi, rdi
0x18005be14  jz      short loc_18005BE23
0x18005be16  movzx   r8d, word ptr [rbp+0]
0x18005be1b  movzx   ecx, word ptr [rsi]
0x18005be1e  add     r8, rcx
0x18005be21  jmp     short loc_18005BE26
0x18005be23  xor     r8d, r8d
0x18005be26  add     r8, 68h ; 'h'; Size
0x18005be2a  xor     edx, edx; Val
0x18005be2c  mov     rcx, rbx; void *
0x18005be2f  call    memset_0
0x18005be34  mov     rcx, cs:fpOpenPrinterW; Pointer
0x18005be3b  call    cs:__imp_RtlDecodePointer
0x18005be41  lea     r14, [rbx+10h]
0x18005be45  xor     r8d, r8d
0x18005be48  mov     rdx, r14
0x18005be4b  mov     rcx, r12
0x18005be4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be53  test    eax, eax
0x18005be55  jz      loc_18005BF66
0x18005be5b  cmp     qword ptr [r14], 0
0x18005be5f  jz      loc_18005BF66
0x18005be65  lea     rcx, Default; pwszDriver
0x18005be6c  mov     r9, rdi; pdm
0x18005be6f  mov     r8, rcx; pszPort
0x18005be72  mov     rdx, r15; pwszDevice
0x18005be75  call    cs:__imp_CreateDCW
0x18005be7b  mov     [rbx+8], rax
0x18005be7f  test    rax, rax
0x18005be82  jz      loc_18005BF4E
0x18005be88  mov     dword ptr [rbx+38h], 14h
0x18005be8f  xor     edx, edx; Flags
0x18005be91  mov     rcx, gs:60h
0x18005be9a  mov     r8d, 320h; Size
0x18005bea0  mov     rcx, [rcx+30h]; HeapHandle
0x18005bea4  call    cs:__imp_RtlAllocateHeap
0x18005beaa  mov     [rbx+30h], rax
0x18005beae  test    rax, rax
0x18005beb1  jz      loc_18005BF44
0x18005beb7  mov     dword ptr [rbx], 53504854h
0x18005bebd  test    rdi, rdi
0x18005bec0  jz      short loc_18005BEDF
0x18005bec2  lea     rcx, [rbx+68h]; void *
0x18005bec6  mov     rdx, rdi; Src
0x18005bec9  mov     [rbx+18h], rcx
0x18005becd  movzx   r8d, word ptr [rbp+0]
0x18005bed2  movzx   eax, word ptr [rsi]
0x18005bed5  add     r8, rax; Size
0x18005bed8  call    memcpy_0
0x18005bedd  jmp     short loc_18005BEE7
0x18005bedf  mov     qword ptr [rbx+18h], 0
0x18005bee7  mov     rax, [rbx+18h]
0x18005beeb  xor     edx, edx; Val
0x18005beed  mov     rcx, [rbx+30h]; void *
0x18005bef1  mov     [rbx+20h], rax
0x18005bef5  mov     eax, [rbx+38h]
0x18005bef8  mov     dword ptr [rbx+28h], 0
0x18005beff  mov     qword ptr [rbx+58h], 0
0x18005bf07  lea     r8, [rax+rax*4]
0x18005bf0b  shl     r8, 3; Size
0x18005bf0f  call    memset_0
0x18005bf14  mov     rax, [rbx+20h]
0x18005bf18  mov     ecx, 1
0x18005bf1d  mov     dword ptr [rbx+60h], 3
0x18005bf24  test    rax, rax
0x18005bf27  jz      short loc_18005BF3C
0x18005bf29  test    dword ptr [rax+48h], 800h
0x18005bf30  jz      short loc_18005BF3C
0x18005bf32  cmp     word ptr [rax+5Ch], 2
0x18005bf37  jnz     short loc_18005BF3C
0x18005bf39  mov     [rbx+60h], ecx
0x18005bf3c  mov     [rbx+64h], ecx
0x18005bf3f  mov     rax, rbx
0x18005bf42  jmp     short loc_18005BF80
0x18005bf44  mov     rcx, [rbx+8]; hdc
0x18005bf48  call    cs:__imp_DeleteDC
0x18005bf4e  mov     rcx, cs:__imp_fpClosePrinter
0x18005bf55  mov     rcx, [rcx]; Pointer
0x18005bf58  call    cs:__imp_RtlDecodePointer
0x18005bf5e  mov     rcx, [r14]
0x18005bf61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf66  mov     rcx, gs:60h
0x18005bf6f  mov     r8, rbx; P
0x18005bf72  xor     edx, edx; Flags
0x18005bf74  mov     rcx, [rcx+30h]; HeapHandle
0x18005bf78  call    cs:__imp_RtlFreeHeap
0x18005bf7e  xor     eax, eax
0x18005bf80  add     rsp, 20h
0x18005bf84  pop     r15
0x18005bf86  pop     r14
0x18005bf88  pop     r12
0x18005bf8a  pop     rdi
0x18005bf8b  pop     rsi
0x18005bf8c  pop     rbp
0x18005bf8d  pop     rbx
0x18005bf8e  retn
```
