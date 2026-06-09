# PPPCleanUp

- ea: `0x180005054`
- end: `0x180005372`
- name: `PPPCleanUp`
- size: `798`
- prototype: `void *()`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008630`
- `0x180018160`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180005054`
- `0x180018a54`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180005265`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180005265`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005205`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005205`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000527d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000527d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800051b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005295`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800051b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000521d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005235`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000524d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000521d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005235`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000524d`

## string_xrefs

- `0x180005140`: `RasCpInit(FALSE) for protocol 0x%x returned error %d`

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
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v8) = 0;
          FormatRRASErrorString((wchar_t *)&v8, L"RasCpInit(%x, FALSE)", *(unsigned int *)((char *)CpTable + v2));
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v8);
        }
        v3 = (*(__int64 (__fastcall **)(_QWORD))((char *)CpTable + v2 + 24))(0);
        if ( v3 && byte_18004DF33 < 0 )
        {
          LOWORD(v8) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v8,
            L"RasCpInit(FALSE) for protocol 0x%x returned error %d",
            *(unsigned int *)((char *)CpTable + v2),
            v3);
          if ( byte_18004DF33 < 0 )
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
  if ( qword_18004DA40 )
    CloseHandle(qword_18004DA40);
  if ( hHeap )
    HeapDestroy(hHeap);
  if ( hKey )
    RegCloseKey(hKey);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( qword_18004DA58 )
    HeapFree(hHeap, 0, qword_18004DA58);
  qword_18004DA58 = 0;
  qword_18004DAB0 = 0;
  qword_18004DAB8 = 0;
  qword_18004DAC0 = 0;
  hLogHandle = 0;
  RasPppUnRegisterEtw();
  qword_18004D970 = 0;
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
0x180005054  mov     [rsp+arg_0], rbx
0x180005059  mov     [rsp+arg_8], rsi
0x18000505e  push    rdi
0x18000505f  sub     rsp, 830h
0x180005066  mov     rax, cs:__security_cookie
0x18000506d  xor     rax, rsp
0x180005070  mov     [rsp+838h+var_18], rax
0x180005078  xor     eax, eax
0x18000507a  lea     rcx, [rsp+838h+var_814]; void *
0x18000507f  xor     edx, edx; Val
0x180005081  mov     [rsp+838h+var_818], eax
0x180005085  mov     r8d, 7FCh; Size
0x18000508b  call    memset_0
0x180005090  cmp     cs:lpMem, 0
0x180005098  jz      loc_1800051FE
0x18000509e  mov     esi, dword ptr cs:PppConfigInfo+4
0x1800050a4  add     esi, dword ptr cs:PppConfigInfo
0x1800050aa  xor     ebx, ebx
0x1800050ac  cmp     ebx, esi
0x1800050ae  jnb     loc_180005196
0x1800050b4  mov     r8, cs:CpTable
0x1800050bb  mov     eax, ebx
0x1800050bd  imul    rdi, rax, 0B0h
0x1800050c4  test    byte ptr [rdi+r8+0A8h], 1
0x1800050cd  jz      loc_18000518F
0x1800050d3  test    cs:byte_18004DF34, 1
0x1800050da  jz      short loc_180005119
0x1800050dc  xor     eax, eax
0x1800050de  lea     rdx, aRascpinitXFals; "RasCpInit(%x, FALSE)"
0x1800050e5  mov     word ptr [rsp+838h+var_818], ax
0x1800050ea  lea     rcx, [rsp+838h+var_818]
0x1800050ef  mov     r8d, [rdi+r8]
0x1800050f3  call    FormatRRASErrorString
0x1800050f8  test    cs:byte_18004DF34, 1
0x1800050ff  jz      short loc_180005119
0x180005101  lea     r8, [rsp+838h+var_818]
0x180005106  lea     rdx, RasPppTraceInfo
0x18000510d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005114  call    McTemplateU0z_EventWriteTransfer
0x180005119  mov     rax, cs:CpTable
0x180005120  xor     ecx, ecx
0x180005122  mov     rax, [rdi+rax+18h]
0x180005127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000512c  test    eax, eax
0x18000512e  jz      short loc_180005180
0x180005130  cmp     cs:byte_18004DF33, 0
0x180005137  jge     short loc_180005180
0x180005139  mov     r8, cs:CpTable
0x180005140  lea     rdx, aRascpinitFalse; "RasCpInit(FALSE) for protocol 0x%x retu"...
0x180005147  xor     ecx, ecx
0x180005149  mov     r9d, eax
0x18000514c  mov     word ptr [rsp+838h+var_818], cx
0x180005151  lea     rcx, [rsp+838h+var_818]
0x180005156  mov     r8d, [rdi+r8]
0x18000515a  call    FormatRRASErrorString
0x18000515f  cmp     cs:byte_18004DF33, 0
0x180005166  jge     short loc_180005180
0x180005168  lea     r8, [rsp+838h+var_818]
0x18000516d  lea     rdx, RasPppTraceError
0x180005174  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000517b  call    McTemplateU0z_EventWriteTransfer
0x180005180  mov     rax, cs:CpTable
0x180005187  and     dword ptr [rdi+rax+0A8h], 0FFFFFFFCh
0x18000518f  inc     ebx
0x180005191  jmp     loc_1800050AC
0x180005196  mov     r8, cs:lpMem
0x18000519d  xor     ebx, ebx
0x18000519f  cmp     qword ptr [r8+18h], 0FFFFFFFFFFFFFFFFh
0x1800051a4  jz      short loc_1800051D9
0x1800051a6  mov     eax, ebx
0x1800051a8  shl     rax, 5
0x1800051ac  mov     rcx, [rax+r8+18h]; hLibModule
0x1800051b1  test    rcx, rcx
0x1800051b4  jz      short loc_1800051C9
0x1800051b6  call    cs:__imp_FreeLibrary
0x1800051bd  nop     dword ptr [rax+rax+00h]
0x1800051c2  mov     r8, cs:lpMem; lpMem
0x1800051c9  inc     ebx
0x1800051cb  mov     eax, ebx
0x1800051cd  shl     rax, 5
0x1800051d1  cmp     qword ptr [rax+r8+18h], 0FFFFFFFFFFFFFFFFh
0x1800051d7  jnz     short loc_1800051A6
0x1800051d9  test    r8, r8
0x1800051dc  jz      short loc_1800051F3
0x1800051de  mov     rcx, cs:hHeap; hHeap
0x1800051e5  xor     edx, edx; dwFlags
0x1800051e7  call    cs:__imp_HeapFree
0x1800051ee  nop     dword ptr [rax+rax+00h]
0x1800051f3  mov     cs:lpMem, 0
0x1800051fe  lea     rcx, CriticalSection; lpCriticalSection
0x180005205  call    cs:__imp_DeleteCriticalSection
0x18000520c  nop     dword ptr [rax+rax+00h]
0x180005211  mov     rcx, qword ptr cs:TimerQ+8; hObject
0x180005218  test    rcx, rcx
0x18000521b  jz      short loc_180005229
0x18000521d  call    cs:__imp_CloseHandle
0x180005224  nop     dword ptr [rax+rax+00h]
0x180005229  mov     rcx, cs:hEvent; hObject
0x180005230  test    rcx, rcx
0x180005233  jz      short loc_180005241
0x180005235  call    cs:__imp_CloseHandle
0x18000523c  nop     dword ptr [rax+rax+00h]
0x180005241  mov     rcx, cs:qword_18004DA40; hObject
0x180005248  test    rcx, rcx
0x18000524b  jz      short loc_180005259
0x18000524d  call    cs:__imp_CloseHandle
0x180005254  nop     dword ptr [rax+rax+00h]
0x180005259  mov     rcx, cs:hHeap; hHeap
0x180005260  test    rcx, rcx
0x180005263  jz      short loc_180005271
0x180005265  call    cs:__imp_HeapDestroy
0x18000526c  nop     dword ptr [rax+rax+00h]
0x180005271  mov     rcx, cs:hKey; hKey
0x180005278  test    rcx, rcx
0x18000527b  jz      short loc_180005289
0x18000527d  call    cs:__imp_RegCloseKey
0x180005284  nop     dword ptr [rax+rax+00h]
0x180005289  mov     rcx, cs:hLibModule; hLibModule
0x180005290  test    rcx, rcx
0x180005293  jz      short loc_1800052A1
0x180005295  call    cs:__imp_FreeLibrary
0x18000529c  nop     dword ptr [rax+rax+00h]
0x1800052a1  mov     r8, cs:qword_18004DA58; lpMem
0x1800052a8  test    r8, r8
0x1800052ab  jz      short loc_1800052C2
0x1800052ad  mov     rcx, cs:hHeap; hHeap
0x1800052b4  xor     edx, edx; dwFlags
0x1800052b6  call    cs:__imp_HeapFree
0x1800052bd  nop     dword ptr [rax+rax+00h]
0x1800052c2  mov     cs:qword_18004DA58, 0
0x1800052cd  mov     cs:qword_18004DAB0, 0
0x1800052d8  mov     cs:qword_18004DAB8, 0
0x1800052e3  mov     cs:qword_18004DAC0, 0
0x1800052ee  mov     cs:hLogHandle, 0
0x1800052f9  call    RasPppUnRegisterEtw
0x1800052fe  xor     eax, eax
0x180005300  lea     rcx, WorkItemQ; void *
0x180005307  xorps   xmm0, xmm0
0x18000530a  mov     cs:qword_18004D970, rax
0x180005311  xor     edx, edx; Val
0x180005313  movups  cs:PcbTable, xmm0
0x18000531a  lea     r8d, [rax+40h]; Size
0x18000531e  call    memset_0
0x180005323  xor     edx, edx; Val
0x180005325  lea     rcx, PppConfigInfo; void *
0x18000532c  mov     r8d, 550h; Size
0x180005332  call    memset_0
0x180005337  xorps   xmm0, xmm0
0x18000533a  mov     cs:CpTable, 0
0x180005345  movups  cs:TimerQ, xmm0
0x18000534c  mov     rcx, [rsp+838h+var_18]
0x180005354  xor     rcx, rsp; StackCookie
0x180005357  call    __security_check_cookie
0x18000535c  lea     r11, [rsp+838h+var_8]
0x180005364  mov     rbx, [r11+10h]
0x180005368  mov     rsi, [r11+18h]
0x18000536c  mov     rsp, r11
0x18000536f  pop     rdi
0x180005370  retn
```
