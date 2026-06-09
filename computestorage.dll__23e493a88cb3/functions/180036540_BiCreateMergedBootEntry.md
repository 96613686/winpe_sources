# BiCreateMergedBootEntry

- ea: `0x180036540`
- end: `0x1800368e9`
- name: `BiCreateMergedBootEntry`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180038034`

## callees

- `0x1800032b8`
- `0x180003bb5`
- `0x180034254`
- `0x180036540`
- `0x180037358`
- `0x18003755c`
- `0x180037e68`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180036857`
- `ntdll!RtlFreeHeap` at `0x18003687b`
- `ntdll!RtlFreeHeap` at `0x18003689f`
- `ntdll!RtlFreeHeap` at `0x1800368c2`
- `ntdll!RtlFreeHeap` at `0x180036857`
- `ntdll!RtlFreeHeap` at `0x18003687b`
- `ntdll!RtlFreeHeap` at `0x18003689f`
- `ntdll!RtlFreeHeap` at `0x1800368c2`
- `ntdll!RtlAllocateHeap` at `0x18003668b`
- `ntdll!RtlAllocateHeap` at `0x18003677a`
- `ntdll!RtlAllocateHeap` at `0x18003668b`
- `ntdll!RtlAllocateHeap` at `0x18003677a`

## string_xrefs

- `0x18003682b`: `BiCreateMergedBootEntry failed %x`

## pseudocode

```c
__int64 __fastcall BiCreateMergedBootEntry(_DWORD *a1, _WORD *a2, _DWORD *a3, _WORD *a4, _QWORD *a5)
{
  __int64 v5; // r13
  _WORD *v6; // rax
  _WORD *v7; // rbx
  _DWORD *v9; // rdi
  _WORD *v10; // r14
  char *v11; // r15
  int DeviceFromEfiPath; // ebx
  char *v13; // r12
  int FilePathFromEfiPath; // eax
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // ebx
  char *Heap; // rax
  __int64 v21; // rbx
  size_t v22; // r8
  int v23; // eax
  unsigned int v24; // edx
  unsigned int v25; // r13d
  int v26; // r8d
  _DWORD *v27; // rax
  _DWORD *v28; // r12
  __int64 v29; // rcx
  int v30; // eax
  char v32; // [rsp+20h] [rbp-30h]
  size_t Size; // [rsp+24h] [rbp-2Ch] BYREF
  _DWORD *v34; // [rsp+30h] [rbp-20h] BYREF
  void *Src; // [rsp+38h] [rbp-18h] BYREF
  PVOID P; // [rsp+40h] [rbp-10h]
  char v38; // [rsp+A0h] [rbp+50h]

  v5 = -1;
  v6 = a4;
  Size = 0;
  v7 = a2;
  P = 0;
  v34 = 0;
  v9 = 0;
  v38 = 0;
  v10 = 0;
  Src = 0;
  v11 = 0;
  v32 = 0;
  if ( !a3 )
  {
    v9 = (_DWORD *)((char *)a1 + (unsigned int)a1[5]);
    if ( !a4 )
      goto LABEL_23;
    v34 = (_DWORD *)((char *)a1 + (unsigned int)a1[5]);
    DeviceFromEfiPath = BiGetDeviceFromEfiPath(v9 + 3);
    if ( DeviceFromEfiPath < 0 )
      goto LABEL_32;
    v6 = a4;
    v13 = (char *)P + 20;
    goto LABEL_12;
  }
  if ( *a3 != 5 )
  {
    if ( *a3 != 2 )
    {
      DeviceFromEfiPath = -1073741811;
      goto LABEL_32;
    }
    v13 = (char *)(a3 + 5);
    if ( !a4 )
    {
      v9 = (_DWORD *)((char *)a1 + (unsigned int)a1[5]);
      v34 = v9;
      FilePathFromEfiPath = BiGetFilePathFromEfiPath(v9 + 3, &Src, &Size);
      v10 = Src;
      DeviceFromEfiPath = FilePathFromEfiPath;
      if ( FilePathFromEfiPath < 0 )
        goto LABEL_32;
      v32 = 1;
      goto LABEL_13;
    }
LABEL_12:
    v10 = v6;
LABEL_13:
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v13[2 * v15] );
    v16 = 2 * v15 + 2;
    v17 = -1;
    HIDWORD(Size) = v16;
    do
      ++v17;
    while ( v10[v17] );
    LODWORD(Size) = 2 * v17 + 2;
    v18 = v16 + Size;
    if ( v16 + (unsigned int)Size < v16 || (v19 = v18 + 12, v18 + 12 < v18) )
    {
      DeviceFromEfiPath = -1073741675;
      goto LABEL_32;
    }
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
    v11 = Heap;
    if ( !Heap )
    {
LABEL_20:
      DeviceFromEfiPath = -1073741670;
      goto LABEL_32;
    }
    *((_DWORD *)Heap + 1) = v19;
    v21 = HIDWORD(Size);
    v22 = HIDWORD(Size);
    *(_DWORD *)Heap = 1;
    *((_DWORD *)Heap + 2) = 3;
    memcpy_0(Heap + 12, v13, v22);
    memcpy_0(&v11[v21 + 12], v10, (unsigned int)Size);
    v23 = BiTranslateFilePath((__int64)v11, 4u, &v34);
    v9 = v34;
    DeviceFromEfiPath = v23;
    if ( v23 < 0 )
      goto LABEL_32;
    v7 = a2;
    v38 = 1;
LABEL_23:
    if ( !v7 )
      v7 = (_WORD *)((char *)a1 + (unsigned int)a1[4]);
    do
      ++v5;
    while ( v7[v5] );
    v24 = a1[6];
    v25 = 2 * v5 + 2;
    if ( v24 + v25 < v24 || (v26 = v9[1], v24 + v25 + v26 + 36 < v24 + v25) )
    {
      DeviceFromEfiPath = -1073741675;
      goto LABEL_32;
    }
    LODWORD(v34) = (v24 + 31) & 0xFFFFFFFC;
    LODWORD(Size) = (v25 + (_DWORD)v34 + 3) & 0xFFFFFFFC;
    HIDWORD(Size) = v26 + Size;
    Src = (void *)(unsigned int)(v26 + Size);
    v27 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Src);
    v28 = v27;
    if ( v27 )
    {
      memset_0(v27, 0, (size_t)Src);
      v29 = (unsigned int)v34;
      v28[1] = HIDWORD(Size);
      *v28 = 1;
      v28[2] = a1[2];
      v28[3] = a1[3];
      v30 = Size;
      v28[4] = v29;
      v28[5] = v30;
      v28[6] = a1[6];
      memcpy_0((char *)v28 + v29, v7, v25);
      memcpy_0((char *)v28 + (unsigned int)Size, v9, (unsigned int)v9[1]);
      memcpy_0(v28 + 7, a1 + 7, (unsigned int)a1[6]);
      *a5 = v28;
      DeviceFromEfiPath = 0;
      goto LABEL_33;
    }
    goto LABEL_20;
  }
  DeviceFromEfiPath = -1073741810;
LABEL_32:
  BiLogMessage(4, L"BiCreateMergedBootEntry failed %x", (unsigned int)DeviceFromEfiPath);
LABEL_33:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v38 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( v32 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  return (unsigned int)DeviceFromEfiPath;
}

```

## disassembly

```asm
0x180036540  mov     [rsp-38h+arg_0], rbx
0x180036545  mov     [rsp-38h+arg_18], r9
0x18003654a  mov     [rsp-38h+arg_8], rdx
0x18003654f  push    rbp
0x180036550  push    rsi
0x180036551  push    rdi
0x180036552  push    r12
0x180036554  push    r13
0x180036556  push    r14
0x180036558  push    r15
0x18003655a  mov     rbp, rsp
0x18003655d  sub     rsp, 50h
0x180036561  xor     r12d, r12d
0x180036564  or      r13, 0FFFFFFFFFFFFFFFFh
0x180036568  mov     dword ptr [rbp+Size+4], r12d
0x18003656c  mov     rax, r9
0x18003656f  mov     dword ptr [rbp+Size], r12d
0x180036573  mov     rbx, rdx
0x180036576  mov     [rbp+P], r12
0x18003657a  mov     rsi, rcx
0x18003657d  mov     [rbp+var_20], r12
0x180036581  mov     edi, r12d
0x180036584  mov     [rbp+arg_10], r12b
0x180036588  mov     r14d, r12d
0x18003658b  mov     [rbp+Src], r12
0x18003658f  mov     r15d, r12d
0x180036592  mov     [rbp+var_30], r12b
0x180036596  test    r8, r8
0x180036599  jz      short loc_1800365F7
0x18003659b  cmp     dword ptr [r8], 5
0x18003659f  jnz     short loc_1800365AB
0x1800365a1  mov     ebx, 0C000000Eh
0x1800365a6  jmp     loc_180036828
0x1800365ab  cmp     dword ptr [r8], 2
0x1800365af  jz      short loc_1800365BB
0x1800365b1  mov     ebx, 0C000000Dh
0x1800365b6  jmp     loc_180036828
0x1800365bb  xor     edx, edx
0x1800365bd  lea     r12, [r8+14h]
0x1800365c1  test    rax, rax
0x1800365c4  jnz     short loc_180036633
0x1800365c6  mov     edi, [rcx+14h]
0x1800365c9  lea     r8, [rbp+Size]
0x1800365cd  add     rdi, rsi
0x1800365d0  lea     rdx, [rbp+Src]
0x1800365d4  mov     [rbp+var_20], rdi
0x1800365d8  lea     rcx, [rdi+0Ch]
0x1800365dc  call    BiGetFilePathFromEfiPath
0x1800365e1  mov     r14, [rbp+Src]
0x1800365e5  xor     edx, edx
0x1800365e7  mov     ebx, eax
0x1800365e9  test    eax, eax
0x1800365eb  js      loc_180036825
0x1800365f1  mov     [rbp+var_30], 1
0x1800365f5  jmp     short loc_180036636
0x1800365f7  mov     edi, [rcx+14h]
0x1800365fa  add     rdi, rsi
0x1800365fd  test    rax, rax
0x180036600  jz      loc_180036708
0x180036606  lea     rcx, [rdi+0Ch]; Src
0x18003660a  mov     [rbp+var_20], rdi
0x18003660e  lea     r8, [rbp+Size+4]
0x180036612  lea     rdx, [rbp+P]
0x180036616  call    BiGetDeviceFromEfiPath
0x18003661b  mov     ebx, eax
0x18003661d  test    eax, eax
0x18003661f  js      loc_180036828
0x180036625  mov     r12, [rbp+P]
0x180036629  mov     rax, [rbp+arg_18]
0x18003662d  add     r12, 14h
0x180036631  xor     edx, edx
0x180036633  mov     r14, rax
0x180036636  mov     rax, r13
0x180036639  inc     rax
0x18003663c  cmp     [r12+rax*2], dx
0x180036641  jnz     short loc_180036639
0x180036643  lea     ecx, ds:2[rax*2]
0x18003664a  mov     rax, r13
0x18003664d  mov     dword ptr [rbp+Size+4], ecx
0x180036650  inc     rax
0x180036653  cmp     [r14+rax*2], dx
0x180036658  jnz     short loc_180036650
0x18003665a  lea     eax, ds:2[rax*2]
0x180036661  mov     dword ptr [rbp+Size], eax
0x180036664  add     eax, ecx
0x180036666  cmp     eax, ecx
0x180036668  jb      loc_180036820
0x18003666e  lea     ebx, [rax+0Ch]
0x180036671  cmp     ebx, eax
0x180036673  jb      loc_180036820
0x180036679  mov     rcx, gs:60h
0x180036682  xor     edx, edx; Flags
0x180036684  mov     r8d, ebx; Size
0x180036687  mov     rcx, [rcx+30h]; HeapHandle
0x18003668b  call    cs:__imp_RtlAllocateHeap
0x180036692  nop     dword ptr [rax+rax+00h]
0x180036697  mov     r15, rax
0x18003669a  test    rax, rax
0x18003669d  jnz     short loc_1800366A9
0x18003669f  mov     ebx, 0C000009Ah
0x1800366a4  jmp     loc_180036825
0x1800366a9  mov     [rax+4], ebx
0x1800366ac  lea     rcx, [rax+0Ch]; void *
0x1800366b0  mov     ebx, dword ptr [rbp+Size+4]
0x1800366b3  mov     rdx, r12; Src
0x1800366b6  mov     r8d, ebx; Size
0x1800366b9  mov     dword ptr [rax], 1
0x1800366bf  mov     dword ptr [rax+8], 3
0x1800366c6  call    memcpy_0
0x1800366cb  mov     r8d, dword ptr [rbp+Size]; Size
0x1800366cf  lea     rcx, [rbx+0Ch]
0x1800366d3  add     rcx, r15; void *
0x1800366d6  mov     rdx, r14; Src
0x1800366d9  call    memcpy_0
0x1800366de  lea     r8, [rbp+var_20]
0x1800366e2  mov     edx, 4
0x1800366e7  mov     rcx, r15
0x1800366ea  call    BiTranslateFilePath
0x1800366ef  mov     rdi, [rbp+var_20]
0x1800366f3  xor     r12d, r12d
0x1800366f6  mov     ebx, eax
0x1800366f8  test    eax, eax
0x1800366fa  js      loc_180036828
0x180036700  mov     rbx, [rbp+arg_8]
0x180036704  mov     [rbp+arg_10], 1
0x180036708  test    rbx, rbx
0x18003670b  jnz     short loc_180036713
0x18003670d  mov     ebx, [rsi+10h]
0x180036710  add     rbx, rsi
0x180036713  inc     r13
0x180036716  cmp     [rbx+r13*2], r12w
0x18003671b  jnz     short loc_180036713
0x18003671d  mov     edx, [rsi+18h]
0x180036720  lea     r13d, ds:2[r13*2]
0x180036728  lea     ecx, [rdx+r13]
0x18003672c  cmp     ecx, edx
0x18003672e  jb      loc_180036819
0x180036734  mov     r8d, [rdi+4]
0x180036738  lea     eax, [r8+24h]
0x18003673c  add     eax, ecx
0x18003673e  cmp     eax, ecx
0x180036740  jb      loc_180036819
0x180036746  lea     eax, [rdx+1Fh]
0x180036749  mov     ecx, 0FFFFFFFCh
0x18003674e  and     eax, ecx
0x180036750  xor     edx, edx; Flags
0x180036752  mov     dword ptr [rbp+var_20], eax
0x180036755  add     eax, 3
0x180036758  add     eax, r13d
0x18003675b  and     eax, ecx
0x18003675d  mov     rcx, gs:60h
0x180036766  mov     dword ptr [rbp+Size], eax
0x180036769  add     eax, r8d
0x18003676c  mov     r8d, eax; Size
0x18003676f  mov     dword ptr [rbp+Size+4], eax
0x180036772  mov     [rbp+Src], rax
0x180036776  mov     rcx, [rcx+30h]; HeapHandle
0x18003677a  call    cs:__imp_RtlAllocateHeap
0x180036781  nop     dword ptr [rax+rax+00h]
0x180036786  mov     r12, rax
0x180036789  test    rax, rax
0x18003678c  jz      loc_18003669F
0x180036792  mov     r8, [rbp+Src]; Size
0x180036796  xor     edx, edx; Val
0x180036798  mov     rcx, rax; void *
0x18003679b  call    memset_0
0x1800367a0  mov     eax, dword ptr [rbp+Size+4]
0x1800367a3  mov     rdx, rbx; Src
0x1800367a6  mov     ecx, dword ptr [rbp+var_20]
0x1800367a9  mov     [r12+4], eax
0x1800367ae  mov     dword ptr [r12], 1
0x1800367b6  mov     eax, [rsi+8]
0x1800367b9  mov     [r12+8], eax
0x1800367be  mov     eax, [rsi+0Ch]
0x1800367c1  mov     [r12+0Ch], eax
0x1800367c6  mov     eax, dword ptr [rbp+Size]
0x1800367c9  mov     [r12+10h], ecx
0x1800367ce  add     rcx, r12; void *
0x1800367d1  mov     [r12+14h], eax
0x1800367d6  mov     eax, [rsi+18h]
0x1800367d9  mov     r8d, r13d; Size
0x1800367dc  mov     [r12+18h], eax
0x1800367e1  call    memcpy_0
0x1800367e6  mov     ecx, dword ptr [rbp+Size]
0x1800367e9  mov     rdx, rdi; Src
0x1800367ec  mov     r8d, [rdi+4]; Size
0x1800367f0  add     rcx, r12; void *
0x1800367f3  call    memcpy_0
0x1800367f8  mov     r8d, [rsi+18h]; Size
0x1800367fc  lea     rdx, [rsi+1Ch]; Src
0x180036800  lea     rcx, [r12+1Ch]; void *
0x180036805  call    memcpy_0
0x18003680a  mov     rax, [rbp+arg_20]
0x18003680e  mov     [rax], r12
0x180036811  xor     r12d, r12d
0x180036814  mov     ebx, r12d
0x180036817  jmp     short loc_18003683C
0x180036819  mov     ebx, 0C0000095h
0x18003681e  jmp     short loc_180036828
0x180036820  mov     ebx, 0C0000095h
0x180036825  xor     r12d, r12d
0x180036828  mov     r8d, ebx
0x18003682b  lea     rdx, aBicreatemerged; "BiCreateMergedBootEntry failed %x"
0x180036832  mov     ecx, 4
0x180036837  call    BiLogMessage
0x18003683c  mov     rax, [rbp+P]
0x180036840  test    rax, rax
0x180036843  jz      short loc_180036863
0x180036845  mov     rcx, gs:60h
0x18003684e  mov     r8, rax; P
0x180036851  xor     edx, edx; Flags
0x180036853  mov     rcx, [rcx+30h]; HeapHandle
0x180036857  call    cs:__imp_RtlFreeHeap
0x18003685e  nop     dword ptr [rax+rax+00h]
0x180036863  cmp     [rbp+arg_10], r12b
0x180036867  jz      short loc_180036887
0x180036869  mov     rcx, gs:60h
0x180036872  mov     r8, rdi; P
0x180036875  xor     edx, edx; Flags
0x180036877  mov     rcx, [rcx+30h]; HeapHandle
0x18003687b  call    cs:__imp_RtlFreeHeap
0x180036882  nop     dword ptr [rax+rax+00h]
0x180036887  cmp     [rbp+var_30], r12b
0x18003688b  jz      short loc_1800368AB
0x18003688d  mov     rcx, gs:60h
0x180036896  mov     r8, r14; P
0x180036899  xor     edx, edx; Flags
0x18003689b  mov     rcx, [rcx+30h]; HeapHandle
0x18003689f  call    cs:__imp_RtlFreeHeap
0x1800368a6  nop     dword ptr [rax+rax+00h]
0x1800368ab  test    r15, r15
0x1800368ae  jz      short loc_1800368CE
0x1800368b0  mov     rcx, gs:60h
0x1800368b9  mov     r8, r15; P
0x1800368bc  xor     edx, edx; Flags
0x1800368be  mov     rcx, [rcx+30h]; HeapHandle
0x1800368c2  call    cs:__imp_RtlFreeHeap
0x1800368c9  nop     dword ptr [rax+rax+00h]
0x1800368ce  mov     eax, ebx
0x1800368d0  mov     rbx, [rsp+50h+arg_0]
0x1800368d8  add     rsp, 50h
0x1800368dc  pop     r15
0x1800368de  pop     r14
0x1800368e0  pop     r13
0x1800368e2  pop     r12
0x1800368e4  pop     rdi
0x1800368e5  pop     rsi
0x1800368e6  pop     rbp
0x1800368e7  retn
```
