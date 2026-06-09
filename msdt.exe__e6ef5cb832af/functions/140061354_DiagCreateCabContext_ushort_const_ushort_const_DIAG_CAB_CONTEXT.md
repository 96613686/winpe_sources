# DiagCreateCabContext(ushort const *,ushort const *,_DIAG_CAB_CONTEXT * *)

- ea: `0x140061354`
- end: `0x140061625`
- name: `?DiagCreateCabContext@@YAJPEBG0PEAPEAU_DIAG_CAB_CONTEXT@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, ERF **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140040360`
- `0x1400404f4`

## callees

- `0x1400039b1`
- `0x1400070b0`
- `0x140061354`
- `0x1400616d4`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400614bc`
- `KERNEL32!GetLastError` at `0x1400614d0`
- `KERNEL32!GetLastError` at `0x1400614bc`
- `KERNEL32!GetLastError` at `0x1400614d0`
- `KERNEL32!HeapAlloc` at `0x1400613c4`
- `KERNEL32!HeapAlloc` at `0x140061437`
- `KERNEL32!HeapAlloc` at `0x1400613c4`
- `KERNEL32!HeapAlloc` at `0x140061437`
- `KERNEL32!HeapFree` at `0x1400615ec`
- `KERNEL32!HeapFree` at `0x1400615ec`
- `KERNEL32!GetProcessHeap` at `0x1400613ac`
- `KERNEL32!GetProcessHeap` at `0x140061420`
- `KERNEL32!GetProcessHeap` at `0x1400615d8`
- `KERNEL32!GetProcessHeap` at `0x1400613ac`
- `KERNEL32!GetProcessHeap` at `0x140061420`
- `KERNEL32!GetProcessHeap` at `0x1400615d8`
- `KERNEL32!WideCharToMultiByte` at `0x1400614ac`
- `KERNEL32!WideCharToMultiByte` at `0x140061525`
- `KERNEL32!WideCharToMultiByte` at `0x1400614ac`
- `KERNEL32!WideCharToMultiByte` at `0x140061525`
- `msvcrt!time` at `0x140061391`
- `msvcrt!time` at `0x140061391`
- `msvcrt!rand` at `0x140061401`
- `msvcrt!rand` at `0x140061401`
- `msvcrt!srand` at `0x1400613a0`
- `msvcrt!srand` at `0x1400613a0`
- `Cabinet!__imp_FCICreate` at `0x1400615b0`
- `Cabinet!__imp_FCICreate` at `0x1400615b0`

## pseudocode

```c
__int64 __fastcall DiagCreateCabContext(const unsigned __int16 *a1, const unsigned __int16 *a2, ERF **a3)
{
  unsigned int v6; // eax
  HANDLE ProcessHeap; // rax
  ERF *pv; // rdi
  signed int v9; // ebx
  HANDLE v10; // rax
  unsigned __int16 *v11; // rax
  WCHAR *v12; // rsi
  signed int LastError; // eax
  HFCI v14; // rax
  HANDLE v15; // rax
  CCAB lpMultiByteStr; // [rsp+70h] [rbp-368h] BYREF

  memset_0(&lpMultiByteStr, 0, sizeof(lpMultiByteStr));
  v6 = time(0);
  srand(v6);
  ProcessHeap = GetProcessHeap();
  pv = (ERF *)HeapAlloc(ProcessHeap, 8u, 0x30u);
  if ( pv )
  {
    memset_0(&lpMultiByteStr.cbReserveCFHeader, 0, 0x31Cu);
    lpMultiByteStr.cb = 0x7FFFFFFF;
    lpMultiByteStr.cbFolderThresh = 0x7FFFFFFF;
    lpMultiByteStr.setID = rand();
    lpMultiByteStr.iDisk = 1;
    v10 = GetProcessHeap();
    v11 = (unsigned __int16 *)HeapAlloc(v10, 0, 0x208u);
    v12 = v11;
    if ( !v11 )
    {
      v9 = -2147024882;
      goto LABEL_16;
    }
    v9 = StringCchPrintfW(v11, 0x104u, L"%s\\", a1);
    if ( v9 >= 0 )
    {
      if ( WideCharToMultiByte(0xFDE9u, 0, v12, -1, lpMultiByteStr.szCabPath, 256, 0, 0)
        && WideCharToMultiByte(0xFDE9u, 0, a2, -1, lpMultiByteStr.szCab, 256, 0, 0) )
      {
        v14 = FCICreate(
                pv,
                NoRootCausesElevatePage::ShowFeedbackQuestion,
                DiagCabAlloc,
                DiagCabFree,
                (PFNFCIOPEN)DiagCabOpenFile,
                DiagCabReadFile,
                (PFNFCIWRITE)DiagCabWriteFile,
                DiagCabCloseFile,
                DiagCabSeekFile,
                DiagCabDeleteFile,
                (PFNFCIGETTEMPFILE)DiagCabGetTempFileName,
                &lpMultiByteStr,
                pv);
        *(_QWORD *)&pv[1].erfType = v14;
        if ( !v14 )
        {
          v9 = -2144337645;
          goto LABEL_15;
        }
        pv[3].erfType = 50;
        *a3 = pv;
        goto LABEL_14;
      }
      if ( !GetLastError() )
      {
LABEL_14:
        v9 = 0;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_15:
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v12);
    if ( v9 >= 0 )
      return (unsigned int)v9;
LABEL_16:
    DiagDestroyCabContext((struct _DIAG_CAB_CONTEXT *)pv);
    return (unsigned int)v9;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x140061354  push    rbx
0x140061356  push    rbp
0x140061357  push    rsi
0x140061358  push    rdi
0x140061359  push    r14
0x14006135b  sub     rsp, 3B0h
0x140061362  mov     rax, cs:__security_cookie
0x140061369  xor     rax, rsp
0x14006136c  mov     [rsp+3D8h+var_38], rax
0x140061374  mov     r14, r8
0x140061377  mov     rbp, rdx
0x14006137a  mov     rbx, rcx
0x14006137d  xor     edx, edx; Val
0x14006137f  mov     r8d, 324h; Size
0x140061385  lea     rcx, [rsp+3D8h+var_368]; void *
0x14006138a  call    memset_0
0x14006138f  xor     ecx, ecx; Time
0x140061391  call    cs:__imp_time
0x140061398  nop     dword ptr [rax+rax+00h]
0x14006139d  mov     rcx, rax; Seed
0x1400613a0  call    cs:__imp_srand
0x1400613a7  nop     dword ptr [rax+rax+00h]
0x1400613ac  call    cs:__imp_GetProcessHeap
0x1400613b3  nop     dword ptr [rax+rax+00h]
0x1400613b8  mov     edx, 8; dwFlags
0x1400613bd  mov     rcx, rax; hHeap
0x1400613c0  lea     r8d, [rdx+28h]; dwBytes
0x1400613c4  call    cs:__imp_HeapAlloc
0x1400613cb  nop     dword ptr [rax+rax+00h]
0x1400613d0  mov     rdi, rax
0x1400613d3  test    rax, rax
0x1400613d6  jnz     short loc_1400613E2
0x1400613d8  mov     ebx, 8007000Eh
0x1400613dd  jmp     loc_140061604
0x1400613e2  xor     edx, edx; Val
0x1400613e4  lea     rcx, [rsp+3D8h+var_368.cbReserveCFHeader]; void *
0x1400613e9  mov     r8d, 31Ch; Size
0x1400613ef  call    memset_0
0x1400613f4  mov     eax, 7FFFFFFFh
0x1400613f9  mov     [rsp+3D8h+var_368.cb], eax
0x1400613fd  mov     [rsp+3D8h+var_368.cbFolderThresh], eax
0x140061401  call    cs:__imp_rand
0x140061408  nop     dword ptr [rax+rax+00h]
0x14006140d  mov     [rsp+3D8h+var_368.setID], ax
0x140061415  mov     [rsp+3D8h+var_368.iDisk], 1
0x140061420  call    cs:__imp_GetProcessHeap
0x140061427  nop     dword ptr [rax+rax+00h]
0x14006142c  xor     edx, edx; dwFlags
0x14006142e  mov     r8d, 208h; dwBytes
0x140061434  mov     rcx, rax; hHeap
0x140061437  call    cs:__imp_HeapAlloc
0x14006143e  nop     dword ptr [rax+rax+00h]
0x140061443  mov     rsi, rax
0x140061446  test    rax, rax
0x140061449  jnz     short loc_140061455
0x14006144b  mov     ebx, 8007000Eh
0x140061450  jmp     loc_1400615FC
0x140061455  mov     r9, rbx
0x140061458  lea     r8, aS_1; "%s\\"
0x14006145f  mov     edx, 104h; unsigned __int64
0x140061464  mov     rcx, rsi; unsigned __int16 *
0x140061467  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14006146c  mov     ebx, eax
0x14006146e  test    eax, eax
0x140061470  js      loc_1400615D8
0x140061476  mov     [rsp+3D8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x14006147f  lea     rax, [rsp+3D8h+var_368.szCabPath]
0x140061487  mov     [rsp+3D8h+lpDefaultChar], 0; lpDefaultChar
0x140061490  mov     ebx, 100h
0x140061495  mov     [rsp+3D8h+cbMultiByte], ebx; cbMultiByte
0x140061499  or      r9d, 0FFFFFFFFh; cchWideChar
0x14006149d  mov     r8, rsi; lpWideCharStr
0x1400614a0  mov     [rsp+3D8h+lpMultiByteStr], rax; lpMultiByteStr
0x1400614a5  xor     edx, edx; dwFlags
0x1400614a7  mov     ecx, 0FDE9h; CodePage
0x1400614ac  call    cs:__imp_WideCharToMultiByte
0x1400614b3  nop     dword ptr [rax+rax+00h]
0x1400614b8  test    eax, eax
0x1400614ba  jnz     short loc_1400614F4
0x1400614bc  call    cs:__imp_GetLastError
0x1400614c3  nop     dword ptr [rax+rax+00h]
0x1400614c8  test    eax, eax
0x1400614ca  jz      loc_1400615D6
0x1400614d0  call    cs:__imp_GetLastError
0x1400614d7  nop     dword ptr [rax+rax+00h]
0x1400614dc  mov     ebx, eax
0x1400614de  test    eax, eax
0x1400614e0  jle     loc_1400615D8
0x1400614e6  movzx   ebx, ax
0x1400614e9  or      ebx, 80070000h
0x1400614ef  jmp     loc_1400615D8
0x1400614f4  mov     [rsp+3D8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400614fd  lea     rax, [rsp+3D8h+var_368.szCab]
0x140061505  mov     [rsp+3D8h+lpDefaultChar], 0; lpDefaultChar
0x14006150e  or      r9d, 0FFFFFFFFh; cchWideChar
0x140061512  mov     [rsp+3D8h+cbMultiByte], ebx; cbMultiByte
0x140061516  mov     r8, rbp; lpWideCharStr
0x140061519  xor     edx, edx; dwFlags
0x14006151b  mov     [rsp+3D8h+lpMultiByteStr], rax; lpMultiByteStr
0x140061520  mov     ecx, 0FDE9h; CodePage
0x140061525  call    cs:__imp_WideCharToMultiByte
0x14006152c  nop     dword ptr [rax+rax+00h]
0x140061531  test    eax, eax
0x140061533  jz      short loc_1400614BC
0x140061535  mov     [rsp+3D8h+pv], rdi; pv
0x14006153a  lea     rax, [rsp+3D8h+var_368]
0x14006153f  mov     [rsp+3D8h+pccab], rax; pccab
0x140061544  lea     r9, ?DiagCabFree@@YAXPEAX@Z; pfnf
0x14006154b  lea     rax, ?DiagCabGetTempFileName@@YAHPEADHPEAX@Z; DiagCabGetTempFileName(char *,int,void *)
0x140061552  mov     rcx, rdi; perf
0x140061555  mov     [rsp+3D8h+pfnfcigtf], rax; pfnfcigtf
0x14006155a  lea     r8, ?DiagCabAlloc@@YAPEAXK@Z; pfna
0x140061561  lea     rax, ?DiagCabDeleteFile@@YAHPEADPEAHPEAX@Z; DiagCabDeleteFile(char *,int *,void *)
0x140061568  mov     [rsp+3D8h+pfndelete], rax; pfndelete
0x14006156d  lea     rdx, ?ShowFeedbackQuestion@NoRootCausesElevatePage@@MEAAHXZ; pfnfcifp
0x140061574  lea     rax, ?DiagCabSeekFile@@YAJ_JJHPEAHPEAX@Z; DiagCabSeekFile(__int64,long,int,int *,void *)
0x14006157b  mov     [rsp+3D8h+pfnseek], rax; pfnseek
0x140061580  lea     rax, ?DiagCabCloseFile@@YAH_JPEAHPEAX@Z; DiagCabCloseFile(__int64,int *,void *)
0x140061587  mov     [rsp+3D8h+lpUsedDefaultChar], rax; pfnclose
0x14006158c  lea     rax, ?DiagCabWriteFile@@YAI_JPEAXIPEAH1@Z; DiagCabWriteFile(__int64,void *,uint,int *,void *)
0x140061593  mov     [rsp+3D8h+lpDefaultChar], rax; pfnwrite
0x140061598  lea     rax, ?DiagCabReadFile@@YAI_JPEAXIPEAH1@Z; DiagCabReadFile(__int64,void *,uint,int *,void *)
0x14006159f  mov     qword ptr [rsp+3D8h+cbMultiByte], rax; pfnread
0x1400615a4  lea     rax, ?DiagCabOpenFile@@YA_JPEADHHPEAHPEAX@Z; DiagCabOpenFile(char *,int,int,int *,void *)
0x1400615ab  mov     [rsp+3D8h+lpMultiByteStr], rax; pfnopen
0x1400615b0  call    cs:__imp_FCICreate
0x1400615b7  nop     dword ptr [rax+rax+00h]
0x1400615bc  mov     [rdi+10h], rax
0x1400615c0  test    rax, rax
0x1400615c3  jnz     short loc_1400615CC
0x1400615c5  mov     ebx, 80300113h
0x1400615ca  jmp     short loc_1400615D8
0x1400615cc  mov     dword ptr [rdi+28h], 32h ; '2'
0x1400615d3  mov     [r14], rdi
0x1400615d6  xor     ebx, ebx
0x1400615d8  call    cs:__imp_GetProcessHeap
0x1400615df  nop     dword ptr [rax+rax+00h]
0x1400615e4  mov     r8, rsi; lpMem
0x1400615e7  xor     edx, edx; dwFlags
0x1400615e9  mov     rcx, rax; hHeap
0x1400615ec  call    cs:__imp_HeapFree
0x1400615f3  nop     dword ptr [rax+rax+00h]
0x1400615f8  test    ebx, ebx
0x1400615fa  jns     short loc_140061604
0x1400615fc  mov     rcx, rdi; lpMem
0x1400615ff  call    ?DiagDestroyCabContext@@YAJPEAU_DIAG_CAB_CONTEXT@@@Z; DiagDestroyCabContext(_DIAG_CAB_CONTEXT *)
0x140061604  mov     eax, ebx
0x140061606  mov     rcx, [rsp+3D8h+var_38]
0x14006160e  xor     rcx, rsp; StackCookie
0x140061611  call    __security_check_cookie
0x140061616  add     rsp, 3B0h
0x14006161d  pop     r14
0x14006161f  pop     rdi
0x140061620  pop     rsi
0x140061621  pop     rbp
0x140061622  pop     rbx
0x140061623  retn
```
