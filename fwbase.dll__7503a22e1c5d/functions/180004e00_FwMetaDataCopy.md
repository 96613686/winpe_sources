# FwMetaDataCopy

- ea: `0x180004e00`
- end: `0x180004f22`
- name: `FwMetaDataCopy`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003890`
- `0x180004870`
- `0x180004e00`
- `0x18000ccd4`
- `0x18002f674`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e11`

## pseudocode

```c
__int64 __fastcall FwMetaDataCopy(__int64 a1, _QWORD *a2)
{
  HANDLE ProcessHeap; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rdi
  unsigned int v7; // ecx
  __int64 v8; // rbp
  void *v9; // rax
  unsigned int v10; // ebx
  __int64 v12; // r9
  _QWORD *v13; // rcx
  __int64 v14; // rdx

  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x18u);
  if ( !v6 )
  {
    v12 = 2147942414LL;
    v10 = -2147024882;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v14 = 42;
    goto LABEL_17;
  }
  v7 = *(_DWORD *)(a1 + 8);
  if ( v7 )
  {
    v5 = 0xFFFFFFFF % v7;
    if ( 0xFFFFFFFF / v7 < 4 )
    {
      v10 = -2147024362;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_8;
      v14 = 43;
      v12 = 2147942934LL;
      goto LABEL_17;
    }
  }
  v8 = 4 * v7;
  v9 = (void *)FwAlloc(v8, v5);
  v6[2] = v9;
  if ( !v9 )
  {
    v12 = 2147942414LL;
    v10 = -2147024882;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v14 = 44;
LABEL_17:
    WPP_SF_d(v13[2], v14, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, v12);
LABEL_8:
    FwMetaDataFree(v6);
    return v10;
  }
  v10 = 0;
  memcpy_0(v9, *(const void **)(a1 + 16), (unsigned int)v8);
  *((_DWORD *)v6 + 2) = *(_DWORD *)(a1 + 8);
  *v6 = *(_QWORD *)a1;
  *a2 = v6;
  return v10;
}

```

## disassembly

```asm
0x180004e00  push    rbx
0x180004e02  push    rbp
0x180004e03  push    rsi
0x180004e04  push    rdi
0x180004e05  push    r14
0x180004e07  sub     rsp, 20h
0x180004e0b  mov     r14, rdx
0x180004e0e  mov     rsi, rcx
0x180004e11  call    cs:__imp_GetProcessHeap
0x180004e17  mov     edx, 8; dwFlags
0x180004e1c  mov     rcx, rax; hHeap
0x180004e1f  lea     r8d, [rdx+10h]; dwBytes
0x180004e23  call    cs:__imp_HeapAlloc
0x180004e29  mov     rdi, rax
0x180004e2c  test    rax, rax
0x180004e2f  jz      short loc_180004E8E
0x180004e31  mov     ecx, [rsi+8]
0x180004e34  test    ecx, ecx
0x180004e36  jz      short loc_180004E44
0x180004e38  xor     edx, edx
0x180004e3a  or      eax, 0FFFFFFFFh
0x180004e3d  div     ecx
0x180004e3f  cmp     eax, 4
0x180004e42  jb      short loc_180004EC1
0x180004e44  lea     eax, ds:0[rcx*4]
0x180004e4b  mov     ecx, eax
0x180004e4d  mov     ebp, eax
0x180004e4f  call    FwAlloc
0x180004e54  mov     [rdi+10h], rax
0x180004e58  test    rax, rax
0x180004e5b  jz      loc_180004EE9
0x180004e61  mov     rdx, [rsi+10h]; Src
0x180004e65  xor     ebx, ebx
0x180004e67  mov     r8d, ebp; Size
0x180004e6a  mov     rcx, rax; void *
0x180004e6d  call    memcpy_0
0x180004e72  mov     ecx, [rsi+8]
0x180004e75  mov     [rdi+8], ecx
0x180004e78  mov     rcx, [rsi]
0x180004e7b  mov     [rdi], rcx
0x180004e7e  mov     [r14], rdi
0x180004e81  mov     eax, ebx
0x180004e83  add     rsp, 20h
0x180004e87  pop     r14
0x180004e89  pop     rdi
0x180004e8a  pop     rsi
0x180004e8b  pop     rbp
0x180004e8c  pop     rbx
0x180004e8d  retn
0x180004e8e  mov     r9d, 8007000Eh
0x180004e94  mov     ebx, r9d
0x180004e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e9e  lea     rax, WPP_GLOBAL_Control
0x180004ea5  cmp     rcx, rax
0x180004ea8  jnz     short loc_180004EB4
0x180004eaa  mov     rcx, rdi
0x180004ead  call    FwMetaDataFree
0x180004eb2  jmp     short loc_180004E81
0x180004eb4  test    byte ptr [rcx+1Ch], 1
0x180004eb8  jz      short loc_180004EAA
0x180004eba  mov     edx, 2Ah ; '*'
0x180004ebf  jmp     short loc_180004F10
0x180004ec1  mov     ebx, 80070216h
0x180004ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ecd  lea     rax, WPP_GLOBAL_Control
0x180004ed4  cmp     rcx, rax
0x180004ed7  jz      short loc_180004EAA
0x180004ed9  test    byte ptr [rcx+1Ch], 1
0x180004edd  jz      short loc_180004EAA
0x180004edf  mov     edx, 2Bh ; '+'
0x180004ee4  mov     r9d, ebx
0x180004ee7  jmp     short loc_180004F10
0x180004ee9  mov     r9d, 8007000Eh
0x180004eef  mov     ebx, r9d
0x180004ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ef9  lea     rax, WPP_GLOBAL_Control
0x180004f00  cmp     rcx, rax
0x180004f03  jz      short loc_180004EAA
0x180004f05  test    byte ptr [rcx+1Ch], 1
0x180004f09  jz      short loc_180004EAA
0x180004f0b  mov     edx, 2Ch ; ','
0x180004f10  mov     rcx, [rcx+10h]
0x180004f14  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x180004f1b  call    WPP_SF_d
0x180004f20  jmp     short loc_180004EAA
```
