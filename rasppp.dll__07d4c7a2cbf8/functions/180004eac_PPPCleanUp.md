# PPPCleanUp

- ea: `0x180004eac`
- end: `0x18000518d`
- name: `PPPCleanUp`
- size: `737`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008320`
- `0x180017950`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180004eac`
- `0x1800181d4`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180005099`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180005099`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005039`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005039`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005051`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050ab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000500e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800050bd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000500e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800050bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005075`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005075`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005087`

## string_xrefs

- `0x180004f98`: `RasCpInit(FALSE) for protocol 0x%x returned error %d`

## pseudocode

```c
void *PPPCleanUp()
{
  unsigned int v0; // esi
  unsigned int i; // ebx
  __int64 v2; // rdi
  unsigned int v3; // eax
  _QWORD *v4; // r8
  unsigned int v5; // ebx
  HMODULE v6; // rcx
  void *result; // rax
  int v8; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v9[2044]; // [rsp+24h] [rbp-814h] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( lpMem )
  {
    v0 = PppConfigInfo + HIDWORD(PppConfigInfo);
    for ( i = 0; i < v0; ++i )
    {
      v2 = 176LL * i;
      if ( (*((_BYTE *)CpTable + v2 + 168) & 1) != 0 )
      {
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v8) = 0;
          FormatRRASErrorString(&v8, L"RasCpInit(%x, FALSE)", *(unsigned int *)((char *)CpTable + v2));
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v8);
        }
        v3 = (*(__int64 (__fastcall **)(_QWORD))((char *)CpTable + v2 + 24))(0);
        if ( v3 && byte_18004CF33 < 0 )
        {
          LOWORD(v8) = 0;
          FormatRRASErrorString(
            &v8,
            L"RasCpInit(FALSE) for protocol 0x%x returned error %d",
            *(unsigned int *)((char *)CpTable + v2),
            v3);
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v8);
        }
        *(_DWORD *)((char *)CpTable + v2 + 168) &= 0xFFFFFFFC;
      }
    }
    v4 = lpMem;
    v5 = 0;
    if ( *((_QWORD *)lpMem + 3) != -1 )
    {
      do
      {
        v6 = (HMODULE)v4[4 * v5 + 3];
        if ( v6 )
        {
          FreeLibrary(v6);
          v4 = lpMem;
        }
        ++v5;
      }
      while ( v4[4 * v5 + 3] != -1 );
    }
    if ( v4 )
      HeapFree(hHeap, 0, v4);
    lpMem = 0;
  }
  DeleteCriticalSection(&CriticalSection);
  if ( *(&TimerQ + 1) )
    CloseHandle(*(&TimerQ + 1));
  if ( hEvent )
    CloseHandle(hEvent);
  if ( qword_18004CA40 )
    CloseHandle(qword_18004CA40);
  if ( hHeap )
    HeapDestroy(hHeap);
  if ( hKey )
    RegCloseKey(hKey);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( qword_18004CA58 )
    HeapFree(hHeap, 0, qword_18004CA58);
  qword_18004CA58 = 0;
  qword_18004CAB0 = 0;
  qword_18004CAB8 = 0;
  qword_18004CAC0 = 0;
  hLogHandle = 0;
  RasPppUnRegisterEtw();
  qword_18004C970 = 0;
  *(_OWORD *)&PcbTable = 0;
  memset_0(&WorkItemQ, 0, 0x40u);
  result = memset_0(&PppConfigInfo, 0, 0x550u);
  CpTable = 0;
  *(_OWORD *)&TimerQ = 0;
  return result;
}

```

## disassembly

```asm
0x180004eac  mov     [rsp+arg_0], rbx
0x180004eb1  mov     [rsp+arg_8], rsi
0x180004eb6  push    rdi
0x180004eb7  sub     rsp, 830h
0x180004ebe  mov     rax, cs:__security_cookie
0x180004ec5  xor     rax, rsp
0x180004ec8  mov     [rsp+838h+var_18], rax
0x180004ed0  xor     eax, eax
0x180004ed2  lea     rcx, [rsp+838h+var_814]; void *
0x180004ed7  xor     edx, edx; Val
0x180004ed9  mov     [rsp+838h+var_818], eax
0x180004edd  mov     r8d, 7FCh; Size
0x180004ee3  call    memset_0
0x180004ee8  cmp     cs:lpMem, 0
0x180004ef0  jz      loc_18000504A
0x180004ef6  mov     esi, dword ptr cs:PppConfigInfo+4
0x180004efc  add     esi, dword ptr cs:PppConfigInfo
0x180004f02  xor     ebx, ebx
0x180004f04  cmp     ebx, esi
0x180004f06  jnb     loc_180004FEE
0x180004f0c  mov     r8, cs:CpTable
0x180004f13  mov     eax, ebx
0x180004f15  imul    rdi, rax, 0B0h
0x180004f1c  test    byte ptr [rdi+r8+0A8h], 1
0x180004f25  jz      loc_180004FE7
0x180004f2b  test    cs:byte_18004CF34, 1
0x180004f32  jz      short loc_180004F71
0x180004f34  xor     eax, eax
0x180004f36  lea     rdx, aRascpinitXFals; "RasCpInit(%x, FALSE)"
0x180004f3d  mov     word ptr [rsp+838h+var_818], ax
0x180004f42  lea     rcx, [rsp+838h+var_818]
0x180004f47  mov     r8d, [rdi+r8]
0x180004f4b  call    FormatRRASErrorString
0x180004f50  test    cs:byte_18004CF34, 1
0x180004f57  jz      short loc_180004F71
0x180004f59  lea     r8, [rsp+838h+var_818]
0x180004f5e  lea     rdx, RasPppTraceInfo
0x180004f65  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004f6c  call    McTemplateU0z_EventWriteTransfer
0x180004f71  mov     rax, cs:CpTable
0x180004f78  xor     ecx, ecx
0x180004f7a  mov     rax, [rdi+rax+18h]
0x180004f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f84  test    eax, eax
0x180004f86  jz      short loc_180004FD8
0x180004f88  cmp     cs:byte_18004CF33, 0
0x180004f8f  jge     short loc_180004FD8
0x180004f91  mov     r8, cs:CpTable
0x180004f98  lea     rdx, aRascpinitFalse; "RasCpInit(FALSE) for protocol 0x%x retu"...
0x180004f9f  xor     ecx, ecx
0x180004fa1  mov     r9d, eax
0x180004fa4  mov     word ptr [rsp+838h+var_818], cx
0x180004fa9  lea     rcx, [rsp+838h+var_818]
0x180004fae  mov     r8d, [rdi+r8]
0x180004fb2  call    FormatRRASErrorString
0x180004fb7  cmp     cs:byte_18004CF33, 0
0x180004fbe  jge     short loc_180004FD8
0x180004fc0  lea     r8, [rsp+838h+var_818]
0x180004fc5  lea     rdx, RasPppTraceError
0x180004fcc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004fd3  call    McTemplateU0z_EventWriteTransfer
0x180004fd8  mov     rax, cs:CpTable
0x180004fdf  and     dword ptr [rdi+rax+0A8h], 0FFFFFFFCh
0x180004fe7  inc     ebx
0x180004fe9  jmp     loc_180004F04
0x180004fee  mov     r8, cs:lpMem
0x180004ff5  xor     ebx, ebx
0x180004ff7  cmp     qword ptr [r8+18h], 0FFFFFFFFFFFFFFFFh
0x180004ffc  jz      short loc_18000502B
0x180004ffe  mov     eax, ebx
0x180005000  shl     rax, 5
0x180005004  mov     rcx, [rax+r8+18h]; hLibModule
0x180005009  test    rcx, rcx
0x18000500c  jz      short loc_18000501B
0x18000500e  call    cs:__imp_FreeLibrary
0x180005014  mov     r8, cs:lpMem; lpMem
0x18000501b  inc     ebx
0x18000501d  mov     eax, ebx
0x18000501f  shl     rax, 5
0x180005023  cmp     qword ptr [rax+r8+18h], 0FFFFFFFFFFFFFFFFh
0x180005029  jnz     short loc_180004FFE
0x18000502b  test    r8, r8
0x18000502e  jz      short loc_18000503F
0x180005030  mov     rcx, cs:hHeap; hHeap
0x180005037  xor     edx, edx; dwFlags
0x180005039  call    cs:__imp_HeapFree
0x18000503f  mov     cs:lpMem, 0
0x18000504a  lea     rcx, CriticalSection; lpCriticalSection
0x180005051  call    cs:__imp_DeleteCriticalSection
0x180005057  mov     rcx, qword ptr cs:TimerQ+8; hObject
0x18000505e  test    rcx, rcx
0x180005061  jz      short loc_180005069
0x180005063  call    cs:__imp_CloseHandle
0x180005069  mov     rcx, cs:hEvent; hObject
0x180005070  test    rcx, rcx
0x180005073  jz      short loc_18000507B
0x180005075  call    cs:__imp_CloseHandle
0x18000507b  mov     rcx, cs:qword_18004CA40; hObject
0x180005082  test    rcx, rcx
0x180005085  jz      short loc_18000508D
0x180005087  call    cs:__imp_CloseHandle
0x18000508d  mov     rcx, cs:hHeap; hHeap
0x180005094  test    rcx, rcx
0x180005097  jz      short loc_18000509F
0x180005099  call    cs:__imp_HeapDestroy
0x18000509f  mov     rcx, cs:hKey; hKey
0x1800050a6  test    rcx, rcx
0x1800050a9  jz      short loc_1800050B1
0x1800050ab  call    cs:__imp_RegCloseKey
0x1800050b1  mov     rcx, cs:hLibModule; hLibModule
0x1800050b8  test    rcx, rcx
0x1800050bb  jz      short loc_1800050C3
0x1800050bd  call    cs:__imp_FreeLibrary
0x1800050c3  mov     r8, cs:qword_18004CA58; lpMem
0x1800050ca  test    r8, r8
0x1800050cd  jz      short loc_1800050DE
0x1800050cf  mov     rcx, cs:hHeap; hHeap
0x1800050d6  xor     edx, edx; dwFlags
0x1800050d8  call    cs:__imp_HeapFree
0x1800050de  mov     cs:qword_18004CA58, 0
0x1800050e9  mov     cs:qword_18004CAB0, 0
0x1800050f4  mov     cs:qword_18004CAB8, 0
0x1800050ff  mov     cs:qword_18004CAC0, 0
0x18000510a  mov     cs:hLogHandle, 0
0x180005115  call    RasPppUnRegisterEtw
0x18000511a  xor     eax, eax
0x18000511c  lea     rcx, WorkItemQ; void *
0x180005123  xorps   xmm0, xmm0
0x180005126  mov     cs:qword_18004C970, rax
0x18000512d  xor     edx, edx; Val
0x18000512f  movups  cs:PcbTable, xmm0
0x180005136  lea     r8d, [rax+40h]; Size
0x18000513a  call    memset_0
0x18000513f  xor     edx, edx; Val
0x180005141  lea     rcx, PppConfigInfo; void *
0x180005148  mov     r8d, 550h; Size
0x18000514e  call    memset_0
0x180005153  xorps   xmm0, xmm0
0x180005156  mov     cs:CpTable, 0
0x180005161  movups  cs:TimerQ, xmm0
0x180005168  mov     rcx, [rsp+838h+var_18]
0x180005170  xor     rcx, rsp; StackCookie
0x180005173  call    __security_check_cookie
0x180005178  lea     r11, [rsp+838h+var_8]
0x180005180  mov     rbx, [r11+10h]
0x180005184  mov     rsi, [r11+18h]
0x180005188  mov     rsp, r11
0x18000518b  pop     rdi
0x18000518c  retn
```
