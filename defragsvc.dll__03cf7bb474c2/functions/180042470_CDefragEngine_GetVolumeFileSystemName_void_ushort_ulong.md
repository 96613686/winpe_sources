# CDefragEngine::_GetVolumeFileSystemName(void *,ushort *,ulong)

- ea: `0x180042470`
- end: `0x180042593`
- name: `?_GetVolumeFileSystemName@CDefragEngine@@AEAAJPEAXPEAGK@Z`
- size: `291`
- prototype: `__int64 __fastcall(CDefragEngine *this, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013824`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180042470`
- `0x180067af2`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x180042520`
- `ntdll!NtQueryVolumeInformationFile` at `0x180042520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800424e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800424e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042573`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefragEngine::_GetVolumeFileSystemName(CDefragEngine *this, void *a2, unsigned __int16 *a3)
{
  unsigned int *v5; // rbx
  __int16 v6; // ax
  NTSTATUS v7; // eax
  bool v8; // sf
  int v9; // eax
  unsigned int v10; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-19h] BYREF
  int v13; // [rsp+40h] [rbp-9h] BYREF
  __int16 v14; // [rsp+44h] [rbp-5h]
  __int16 v15; // [rsp+46h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "CDefragEngine::_GetVolumeFileSystemName", 2551, 1);
  v5 = 0;
  IoStatusBlock = 0;
  v6 = 2557;
  if ( a2 && (v14 = 2557, v6 = 2558, a3) )
  {
    v13 = 0;
    v14 = 2558;
    v5 = (unsigned int *)CoTaskMemAlloc(0x24u);
    v6 = 2562;
    if ( v5 )
    {
      v13 = 0;
      v14 = 2562;
      v7 = NtQueryVolumeInformationFile(a2, &IoStatusBlock, v5, 0x24u, FileFsAttributeInformation);
      if ( v7 < 0 )
      {
        v9 = v7 | 0x10000000;
        v8 = v9 < 0;
        v13 = v9;
        v6 = 2575;
        if ( v8 )
          goto LABEL_3;
        v14 = 2575;
      }
      if ( v5[2] < 0x14 )
      {
        memcpy_0(a3, v5 + 3, v5[2]);
        a3[(unsigned __int64)v5[2] >> 1] = 0;
        goto LABEL_13;
      }
      v13 = -2147024872;
      v6 = 2580;
    }
    else
    {
      v13 = -2147024882;
    }
  }
  else
  {
    v13 = -2147024809;
  }
LABEL_3:
  v15 = v6;
LABEL_13:
  CoTaskMemFree(v5);
  v10 = v13;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return v10;
}

```

## disassembly

```asm
0x180042470  push    rbp
0x180042472  push    rbx
0x180042473  push    rsi
0x180042474  push    rdi
0x180042475  lea     rbp, [rsp-3Fh]
0x18004247a  sub     rsp, 88h
0x180042481  mov     rdi, r8
0x180042484  mov     rsi, rdx
0x180042487  mov     r9d, 1; unsigned __int16
0x18004248d  mov     r8d, 9F7h; unsigned __int16
0x180042493  lea     rdx, aCdefragengineG_7; "CDefragEngine::_GetVolumeFileSystemName"
0x18004249a  lea     rcx, [rbp+57h+var_60]; this
0x18004249e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800424a3  nop
0x1800424a4  xor     ebx, ebx
0x1800424a6  xorps   xmm0, xmm0
0x1800424a9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800424ad  mov     eax, 9FDh
0x1800424b2  test    rsi, rsi
0x1800424b5  jnz     short loc_1800424C7
0x1800424b7  mov     [rbp+57h+var_60], 80070057h
0x1800424be  mov     [rbp+57h+var_5A], ax
0x1800424c2  jmp     loc_180042570
0x1800424c7  mov     [rbp+57h+var_5C], ax
0x1800424cb  mov     eax, 9FEh
0x1800424d0  test    rdi, rdi
0x1800424d3  jz      short loc_1800424B7
0x1800424d5  mov     [rbp+57h+var_60], ebx
0x1800424d8  mov     [rbp+57h+var_5C], ax
0x1800424dc  mov     ecx, 24h ; '$'; cb
0x1800424e1  call    cs:__imp_CoTaskMemAlloc
0x1800424e7  mov     rbx, rax
0x1800424ea  test    rax, rax
0x1800424ed  mov     eax, 0A02h
0x1800424f2  jnz     short loc_1800424FD
0x1800424f4  mov     [rbp+57h+var_60], 8007000Eh
0x1800424fb  jmp     short loc_1800424BE
0x1800424fd  mov     [rbp+57h+var_60], 0
0x180042504  mov     [rbp+57h+var_5C], ax
0x180042508  mov     [rsp+0A0h+FsInformationClass], 5; FsInformationClass
0x180042510  mov     r9d, 24h ; '$'; Length
0x180042516  mov     r8, rbx; FsInformation
0x180042519  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18004251d  mov     rcx, rsi; FileHandle
0x180042520  call    cs:__imp_NtQueryVolumeInformationFile
0x180042526  test    eax, eax
0x180042528  jns     short loc_18004253D
0x18004252a  or      eax, 10000000h
0x18004252f  mov     [rbp+57h+var_60], eax
0x180042532  mov     eax, 0A0Fh
0x180042537  jl      short loc_1800424BE
0x180042539  mov     [rbp+57h+var_5C], ax
0x18004253d  cmp     dword ptr [rbx+8], 14h
0x180042541  jb      short loc_180042554
0x180042543  mov     [rbp+57h+var_60], 80070018h
0x18004254a  mov     eax, 0A14h
0x18004254f  jmp     loc_1800424BE
0x180042554  mov     r8d, [rbx+8]; Size
0x180042558  lea     rdx, [rbx+0Ch]; Src
0x18004255c  mov     rcx, rdi; void *
0x18004255f  call    memcpy_0
0x180042564  mov     ecx, [rbx+8]
0x180042567  shr     rcx, 1
0x18004256a  xor     eax, eax
0x18004256c  mov     [rdi+rcx*2], ax
0x180042570  mov     rcx, rbx; pv
0x180042573  call    cs:__imp_CoTaskMemFree
0x180042579  mov     ebx, [rbp+57h+var_60]
0x18004257c  lea     rcx, [rbp+57h+var_60]; this
0x180042580  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180042585  mov     eax, ebx
0x180042587  add     rsp, 88h
0x18004258e  pop     rdi
0x18004258f  pop     rsi
0x180042590  pop     rbx
0x180042591  pop     rbp
0x180042592  retn
```
