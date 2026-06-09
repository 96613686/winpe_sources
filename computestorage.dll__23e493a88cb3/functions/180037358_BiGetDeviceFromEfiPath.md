# BiGetDeviceFromEfiPath

- ea: `0x180037358`
- end: `0x180037554`
- name: `BiGetDeviceFromEfiPath`
- size: `508`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180036540`

## callees

- `0x1800032b8`
- `0x180003bb5`
- `0x180034254`
- `0x180037358`
- `0x180037e68`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800374ea`
- `ntdll!RtlFreeHeap` at `0x18003750d`
- `ntdll!RtlFreeHeap` at `0x180037530`
- `ntdll!RtlFreeHeap` at `0x1800374ea`
- `ntdll!RtlFreeHeap` at `0x18003750d`
- `ntdll!RtlFreeHeap` at `0x180037530`
- `ntdll!RtlAllocateHeap` at `0x1800373ed`
- `ntdll!RtlAllocateHeap` at `0x18003746e`
- `ntdll!RtlAllocateHeap` at `0x1800373ed`
- `ntdll!RtlAllocateHeap` at `0x18003746e`

## string_xrefs

- `0x1800374c2`: `BiGetDeviceFromEfiPath failed: %x`

## pseudocode

```c
__int64 __fastcall BiGetDeviceFromEfiPath(char *Src, _QWORD *a2, _DWORD *a3)
{
  char *v3; // rdi
  char v4; // al
  _DWORD *v5; // r14
  char *v8; // rsi
  unsigned int v9; // ebx
  char *i; // rbx
  size_t v11; // rbx
  char *Heap; // rax
  int v13; // eax
  unsigned int v14; // ebp
  _DWORD *v15; // rax
  _QWORD *v16; // rax
  PVOID P; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp+10h]

  v19 = a2;
  v3 = 0;
  v4 = *Src & 0x7F;
  v5 = 0;
  P = 0;
  if ( v4 == 127 )
  {
    v8 = 0;
    v9 = -1073741766;
  }
  else
  {
    for ( i = &Src[*((unsigned __int16 *)Src + 1)];
          (*i & 0x7F) != 0x7F && (*i != 4 || i[1] != 4);
          i += *((unsigned __int16 *)i + 1) )
    {
      ;
    }
    v11 = (unsigned int)((_DWORD)i - (_DWORD)Src);
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v11 + 16));
    v8 = Heap;
    if ( Heap )
    {
      *(_DWORD *)Heap = 1;
      *((_DWORD *)Heap + 1) = v11 + 16;
      *((_DWORD *)Heap + 2) = 4;
      memcpy_0(Heap + 12, Src, v11);
      *(_DWORD *)&v8[v11 + 12] = 327551;
      v13 = BiTranslateFilePath((__int64)v8, 3u, &P);
      v3 = (char *)P;
      v9 = v13;
      if ( v13 < 0 )
      {
        if ( v13 == -1073741811 )
          goto LABEL_16;
        goto LABEL_14;
      }
      v14 = *((_DWORD *)P + 1) - 12;
      v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14 + 20);
      v5 = v15;
      if ( v15 )
      {
        memset_0(v15, 0, v14 + 20);
        *v5 = 2;
        memcpy_0(v5 + 5, v3 + 12, v14);
        v16 = v19;
        *a3 = v14 + 20;
        *v16 = v5;
        goto LABEL_16;
      }
    }
    v9 = -1073741670;
  }
LABEL_14:
  BiLogMessage(4, L"BiGetDeviceFromEfiPath failed: %x", v9);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
LABEL_16:
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return v9;
}

```

## disassembly

```asm
0x180037358  mov     [rsp+arg_10], rbx
0x18003735d  mov     [rsp+arg_8], rdx
0x180037362  push    rbp
0x180037363  push    rsi
0x180037364  push    rdi
0x180037365  push    r12
0x180037367  push    r13
0x180037369  push    r14
0x18003736b  push    r15
0x18003736d  sub     rsp, 20h
0x180037371  mov     al, [rcx]
0x180037373  mov     r12b, 7Fh
0x180037376  xor     edi, edi
0x180037378  and     al, r12b
0x18003737b  xor     r14d, r14d
0x18003737e  mov     [rsp+58h+P], rdi
0x180037383  mov     r13, r8
0x180037386  mov     r15, rcx
0x180037389  cmp     al, r12b
0x18003738c  jnz     short loc_18003739A
0x18003738e  xor     esi, esi
0x180037390  mov     ebx, 0C000003Ah
0x180037395  jmp     loc_1800374BF
0x18003739a  movzx   ebx, byte ptr [rcx+3]
0x18003739e  movzx   eax, byte ptr [rcx+2]
0x1800373a2  shl     rbx, 8
0x1800373a6  or      rbx, rax
0x1800373a9  add     rbx, r15
0x1800373ac  mov     al, [rbx]
0x1800373ae  and     al, r12b
0x1800373b1  cmp     al, r12b
0x1800373b4  jz      short loc_1800373D5
0x1800373b6  cmp     byte ptr [rbx], 4
0x1800373b9  jnz     short loc_1800373C1
0x1800373bb  cmp     byte ptr [rbx+1], 4
0x1800373bf  jz      short loc_1800373D5
0x1800373c1  movzx   ecx, byte ptr [rbx+3]
0x1800373c5  movzx   eax, byte ptr [rbx+2]
0x1800373c9  shl     rcx, 8
0x1800373cd  or      rcx, rax
0x1800373d0  add     rbx, rcx
0x1800373d3  jmp     short loc_1800373AC
0x1800373d5  mov     rcx, gs:60h
0x1800373de  sub     ebx, r15d
0x1800373e1  xor     edx, edx; Flags
0x1800373e3  mov     rcx, [rcx+30h]; HeapHandle
0x1800373e7  lea     ebp, [rbx+10h]
0x1800373ea  mov     r8d, ebp; Size
0x1800373ed  call    cs:__imp_RtlAllocateHeap
0x1800373f4  nop     dword ptr [rax+rax+00h]
0x1800373f9  mov     rsi, rax
0x1800373fc  test    rax, rax
0x1800373ff  jnz     short loc_18003740B
0x180037401  mov     ebx, 0C000009Ah
0x180037406  jmp     loc_1800374BF
0x18003740b  lea     rcx, [rax+0Ch]; void *
0x18003740f  mov     dword ptr [rax], 1
0x180037415  mov     r8, rbx; Size
0x180037418  mov     [rax+4], ebp
0x18003741b  mov     rdx, r15; Src
0x18003741e  mov     dword ptr [rax+8], 4
0x180037425  call    memcpy_0
0x18003742a  lea     r8, [rsp+58h+P]
0x18003742f  mov     dword ptr [rbx+rsi+0Ch], 4FF7Fh
0x180037437  mov     edx, 3
0x18003743c  mov     rcx, rsi
0x18003743f  call    BiTranslateFilePath
0x180037444  mov     rdi, [rsp+58h+P]
0x180037449  mov     ebx, eax
0x18003744b  test    eax, eax
0x18003744d  js      short loc_1800374B8
0x18003744f  mov     ebp, [rdi+4]
0x180037452  xor     edx, edx; Flags
0x180037454  mov     rcx, gs:60h
0x18003745d  add     ebp, 0FFFFFFF4h
0x180037460  mov     rcx, [rcx+30h]; HeapHandle
0x180037464  lea     r15d, [rbp+14h]
0x180037468  mov     r8d, r15d; Size
0x18003746b  mov     r12d, r15d
0x18003746e  call    cs:__imp_RtlAllocateHeap
0x180037475  nop     dword ptr [rax+rax+00h]
0x18003747a  mov     r14, rax
0x18003747d  test    rax, rax
0x180037480  jz      loc_180037401
0x180037486  mov     r8d, r12d; Size
0x180037489  xor     edx, edx; Val
0x18003748b  mov     rcx, rax; void *
0x18003748e  call    memset_0
0x180037493  mov     r8d, ebp; Size
0x180037496  lea     rdx, [rdi+0Ch]; Src
0x18003749a  lea     rcx, [r14+14h]; void *
0x18003749e  mov     dword ptr [r14], 2
0x1800374a5  call    memcpy_0
0x1800374aa  mov     rax, [rsp+58h+arg_8]
0x1800374af  mov     [r13+0], r15d
0x1800374b3  mov     [rax], r14
0x1800374b6  jmp     short loc_1800374F6
0x1800374b8  cmp     eax, 0C000000Dh
0x1800374bd  jz      short loc_1800374F6
0x1800374bf  mov     r8d, ebx
0x1800374c2  lea     rdx, aBigetdevicefro; "BiGetDeviceFromEfiPath failed: %x"
0x1800374c9  mov     ecx, 4
0x1800374ce  call    BiLogMessage
0x1800374d3  test    r14, r14
0x1800374d6  jz      short loc_1800374F6
0x1800374d8  mov     rcx, gs:60h
0x1800374e1  mov     r8, r14; P
0x1800374e4  xor     edx, edx; Flags
0x1800374e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800374ea  call    cs:__imp_RtlFreeHeap
0x1800374f1  nop     dword ptr [rax+rax+00h]
0x1800374f6  test    rdi, rdi
0x1800374f9  jz      short loc_180037519
0x1800374fb  mov     rcx, gs:60h
0x180037504  mov     r8, rdi; P
0x180037507  xor     edx, edx; Flags
0x180037509  mov     rcx, [rcx+30h]; HeapHandle
0x18003750d  call    cs:__imp_RtlFreeHeap
0x180037514  nop     dword ptr [rax+rax+00h]
0x180037519  test    rsi, rsi
0x18003751c  jz      short loc_18003753C
0x18003751e  mov     rcx, gs:60h
0x180037527  mov     r8, rsi; P
0x18003752a  xor     edx, edx; Flags
0x18003752c  mov     rcx, [rcx+30h]; HeapHandle
0x180037530  call    cs:__imp_RtlFreeHeap
0x180037537  nop     dword ptr [rax+rax+00h]
0x18003753c  mov     eax, ebx
0x18003753e  mov     rbx, [rsp+58h+arg_10]
0x180037543  add     rsp, 20h
0x180037547  pop     r15
0x180037549  pop     r14
0x18003754b  pop     r13
0x18003754d  pop     r12
0x18003754f  pop     rdi
0x180037550  pop     rsi
0x180037551  pop     rbp
0x180037552  retn
```
