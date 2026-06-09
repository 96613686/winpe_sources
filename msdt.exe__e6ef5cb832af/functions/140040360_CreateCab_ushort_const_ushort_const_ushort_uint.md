# CreateCab(ushort const *,ushort const *,ushort * *,uint)

- ea: `0x140040360`
- end: `0x1400404ed`
- name: `?CreateCab@@YAJPEBG0PEAPEAGI@Z`
- size: `397`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14003ceb0`

## callees

- `0x140020420`
- `0x140040360`
- `0x14006051c`
- `0x140061354`
- `0x1400616d4`
- `0x140061b14`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400403a3`
- `KERNEL32!HeapAlloc` at `0x1400403a3`
- `KERNEL32!HeapFree` at `0x1400404be`
- `KERNEL32!HeapFree` at `0x1400404be`
- `KERNEL32!GetProcessHeap` at `0x14004038c`
- `KERNEL32!GetProcessHeap` at `0x1400404aa`
- `KERNEL32!GetProcessHeap` at `0x14004038c`
- `KERNEL32!GetProcessHeap` at `0x1400404aa`
- `KERNEL32!GetFullPathNameW` at `0x14004041f`
- `KERNEL32!GetFullPathNameW` at `0x14004041f`

## string_xrefs

- `0x1400403c0`: `CreateCab`
- `0x140040497`: `CreateCab`

## pseudocode

```c
__int64 __fastcall CreateCab(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int a4)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // r14
  unsigned int v10; // ebx
  int CabContext; // eax
  int v12; // r9d
  __int64 i; // rsi
  HFCI *v14; // r8
  HANDLE v15; // rax
  struct _DIAG_CAB_CONTEXT *lpMem; // [rsp+30h] [rbp-48h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-40h] BYREF

  lpMem = 0;
  FilePart = 0;
  ProcessHeap = GetProcessHeap();
  v9 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v9 )
  {
    v10 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateCab", 103, -2147024882);
    return v10;
  }
  CabContext = DiagCreateCabContext(a1, a2, (ERF **)&lpMem);
  v10 = CabContext;
  if ( CabContext >= 0 )
  {
    for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
    {
      if ( GetFullPathNameW(a3[i], 0x104u, v9, &FilePart) - 1 > 0x103 || FilePart <= v9 )
      {
        v10 = -2147319786;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateCab", 119, -2147319786);
        goto LABEL_16;
      }
      v14 = (HFCI *)lpMem;
      *(FilePart - 1) = 0;
      CabContext = DiagAddFileToCab(v9, FilePart, v14);
      v10 = CabContext;
      if ( CabContext < 0 )
      {
        v12 = 129;
        goto LABEL_15;
      }
    }
    CabContext = DiagFlushCab(lpMem);
    v10 = CabContext;
    if ( CabContext >= 0 )
      goto LABEL_16;
    v12 = 133;
  }
  else
  {
    v12 = 109;
  }
LABEL_15:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateCab", v12, CabContext);
LABEL_16:
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v9);
  if ( lpMem )
    DiagDestroyCabContext(lpMem);
  return v10;
}

```

## disassembly

```asm
0x140040360  push    rbx
0x140040362  push    rsi
0x140040363  push    rdi
0x140040364  push    r12
0x140040366  push    r14
0x140040368  push    r15
0x14004036a  sub     rsp, 48h
0x14004036e  mov     r15d, r9d
0x140040371  mov     [rsp+78h+lpMem], 0
0x14004037a  mov     r12, r8
0x14004037d  mov     [rsp+78h+FilePart], 0
0x140040386  mov     rbx, rdx
0x140040389  mov     rdi, rcx
0x14004038c  call    cs:__imp_GetProcessHeap
0x140040393  nop     dword ptr [rax+rax+00h]
0x140040398  xor     edx, edx; dwFlags
0x14004039a  mov     r8d, 208h; dwBytes
0x1400403a0  mov     rcx, rax; hHeap
0x1400403a3  call    cs:__imp_HeapAlloc
0x1400403aa  nop     dword ptr [rax+rax+00h]
0x1400403af  mov     r14, rax
0x1400403b2  test    rax, rax
0x1400403b5  jnz     short loc_1400403DF
0x1400403b7  mov     ebx, 8007000Eh
0x1400403bc  lea     r9d, [rax+67h]
0x1400403c0  lea     r8, aCreatecab; "CreateCab"
0x1400403c7  mov     [rsp+78h+var_58], ebx
0x1400403cb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400403d2  lea     ecx, [rax+1]; Level
0x1400403d5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400403da  jmp     loc_1400404DC
0x1400403df  lea     r8, [rsp+78h+lpMem]; struct _DIAG_CAB_CONTEXT **
0x1400403e4  mov     rdx, rbx; unsigned __int16 *
0x1400403e7  mov     rcx, rdi; unsigned __int16 *
0x1400403ea  call    ?DiagCreateCabContext@@YAJPEBG0PEAPEAU_DIAG_CAB_CONTEXT@@@Z; DiagCreateCabContext(ushort const *,ushort const *,_DIAG_CAB_CONTEXT * *)
0x1400403ef  mov     ebx, eax
0x1400403f1  test    eax, eax
0x1400403f3  jns     short loc_140040404
0x1400403f5  mov     r9d, 6Dh ; 'm'
0x1400403fb  lea     ecx, [r9-6Ch]
0x1400403ff  jmp     loc_140040493
0x140040404  xor     esi, esi
0x140040406  lea     edi, [rsi+1]
0x140040409  cmp     esi, r15d
0x14004040c  jnb     short loc_14004047B
0x14004040e  mov     rcx, [r12+rsi*8]; lpFileName
0x140040412  lea     r9, [rsp+78h+FilePart]; lpFilePart
0x140040417  mov     r8, r14; lpBuffer
0x14004041a  mov     edx, 104h; nBufferLength
0x14004041f  call    cs:__imp_GetFullPathNameW
0x140040426  nop     dword ptr [rax+rax+00h]
0x14004042b  dec     eax
0x14004042d  cmp     eax, 103h
0x140040432  ja      short loc_140040468
0x140040434  mov     rcx, [rsp+78h+FilePart]
0x140040439  cmp     rcx, r14
0x14004043c  jbe     short loc_140040468
0x14004043e  mov     r8, [rsp+78h+lpMem]; struct _DIAG_CAB_CONTEXT *
0x140040443  xor     eax, eax
0x140040445  mov     [rcx-2], ax
0x140040449  mov     rcx, r14; unsigned __int16 *
0x14004044c  mov     rdx, [rsp+78h+FilePart]; unsigned __int16 *
0x140040451  call    ?DiagAddFileToCab@@YAJPEBG0PEAU_DIAG_CAB_CONTEXT@@@Z; DiagAddFileToCab(ushort const *,ushort const *,_DIAG_CAB_CONTEXT *)
0x140040456  mov     ebx, eax
0x140040458  test    eax, eax
0x14004045a  js      short loc_140040460
0x14004045c  add     esi, edi
0x14004045e  jmp     short loc_140040409
0x140040460  mov     r9d, 81h
0x140040466  jmp     short loc_140040491
0x140040468  mov     ebx, 80028016h
0x14004046d  mov     r9d, 77h ; 'w'
0x140040473  mov     [rsp+78h+var_58], ebx
0x140040477  mov     ecx, edi
0x140040479  jmp     short loc_140040497
0x14004047b  mov     rcx, [rsp+78h+lpMem]; struct _DIAG_CAB_CONTEXT *
0x140040480  call    ?DiagFlushCab@@YAJPEAU_DIAG_CAB_CONTEXT@@@Z; DiagFlushCab(_DIAG_CAB_CONTEXT *)
0x140040485  mov     ebx, eax
0x140040487  test    eax, eax
0x140040489  jns     short loc_1400404AA
0x14004048b  mov     r9d, 85h
0x140040491  mov     ecx, edi; Level
0x140040493  mov     [rsp+78h+var_58], eax
0x140040497  lea     r8, aCreatecab; "CreateCab"
0x14004049e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400404a5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400404aa  call    cs:__imp_GetProcessHeap
0x1400404b1  nop     dword ptr [rax+rax+00h]
0x1400404b6  mov     r8, r14; lpMem
0x1400404b9  xor     edx, edx; dwFlags
0x1400404bb  mov     rcx, rax; hHeap
0x1400404be  call    cs:__imp_HeapFree
0x1400404c5  nop     dword ptr [rax+rax+00h]
0x1400404ca  cmp     [rsp+78h+lpMem], 0
0x1400404d0  jz      short loc_1400404DC
0x1400404d2  mov     rcx, [rsp+78h+lpMem]; lpMem
0x1400404d7  call    ?DiagDestroyCabContext@@YAJPEAU_DIAG_CAB_CONTEXT@@@Z; DiagDestroyCabContext(_DIAG_CAB_CONTEXT *)
0x1400404dc  mov     eax, ebx
0x1400404de  add     rsp, 48h
0x1400404e2  pop     r15
0x1400404e4  pop     r14
0x1400404e6  pop     r12
0x1400404e8  pop     rdi
0x1400404e9  pop     rsi
0x1400404ea  pop     rbx
0x1400404eb  retn
```
