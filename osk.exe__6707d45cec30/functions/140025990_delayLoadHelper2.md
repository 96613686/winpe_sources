# __delayLoadHelper2

- ea: `0x140025990`
- end: `0x140025cc4`
- name: `__delayLoadHelper2`
- size: `820`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003206`

## callees

- `0x140002de3`
- `0x140025734`
- `0x140025934`
- `0x140025990`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140025afe`
- `KERNEL32!GetLastError` at `0x140025c2a`
- `KERNEL32!GetLastError` at `0x140025afe`
- `KERNEL32!GetLastError` at `0x140025c2a`
- `KERNEL32!LoadLibraryExA` at `0x140025af0`
- `KERNEL32!LoadLibraryExA` at `0x140025af0`
- `KERNEL32!FreeLibrary` at `0x140025ba7`
- `KERNEL32!FreeLibrary` at `0x140025ba7`
- `KERNEL32!RaiseException` at `0x140025a3f`
- `KERNEL32!RaiseException` at `0x140025b43`
- `KERNEL32!RaiseException` at `0x140025c6f`
- `KERNEL32!RaiseException` at `0x140025a3f`
- `KERNEL32!RaiseException` at `0x140025b43`
- `KERNEL32!RaiseException` at `0x140025c6f`
- `KERNEL32!HeapAlloc` at `0x140025b7c`
- `KERNEL32!HeapAlloc` at `0x140025b7c`
- `KERNEL32!GetProcAddress` at `0x140025c1c`
- `KERNEL32!GetProcAddress` at `0x140025c1c`
- `KERNEL32!GetProcessHeap` at `0x140025b6a`
- `KERNEL32!GetProcessHeap` at `0x140025b6a`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  unsigned __int64 v5; // rdx
  volatile signed __int64 *v6; // r14
  __int64 dwTimeStamp; // rcx
  char *v8; // r15
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v12; // r13
  PUnloadInfo v13; // rcx
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v16; // r14
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  struct DelayLoadInfo v22; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+48h] BYREF

  *(&v22.cb + 1) = 0;
  memset_0(&v22, 0, 0x44u);
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v5 = (unsigned __int64)&_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase.unused + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v8 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v22.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v22.cb = 72;
  v22.pidd = a1;
  v22.ppfn = a2;
  v22.dlp.fImportByName = 0;
  memset(&v22.dlp.szProcName, 0, 28);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v22;
    DloadReleaseSectionWriteAccess(dwTimeStamp, &_ImageBase, v4);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v6;
  v12 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v13 = (PUnloadInfo)(v12 + a1->rvaINT);
  v22.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase.unused + (_QWORD)v13) >= 0LL;
  if ( v22.dlp.fImportByName )
  {
    v5 = (unsigned __int64)&_ImageBase.unused + 2;
    v22.dlp.szProcName = (char *)&_ImageBase.unused + *(unsigned int *)((char *)&_ImageBase.unused + (_QWORD)v13) + 2;
  }
  else
  {
    v22.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase.unused + (_QWORD)v13);
  }
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v22), v14 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v22)) == 0 )
      {
        Library = LoadLibraryExA(v22.szDll, 0, 0);
        if ( !Library )
        {
          v22.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v22)) == 0 )
          {
            Arguments = (ULONG_PTR)&v22;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v22.pfnCur;
          }
        }
      }
      v16 = _InterlockedCompareExchange64(v6, (signed __int64)Library, 0);
      if ( v16 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v16 )
          Library = (HMODULE)v16;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v18 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v18 )
          {
            v18->pidd = a1;
            v13 = _puiHead;
            v18->puiNext = _puiHead;
            _puiHead = v18;
          }
        }
      }
      v14 = _pfnDliNotifyHook2;
    }
    v22.hmodCur = Library;
    if ( v14 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v22);
      v14 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v13 = (PUnloadInfo)*((int *)Library + 15), *(_DWORD *)((char *)Library + (_QWORD)v13) != 17744)
        || (v5 = (unsigned int)Arguments, *(_DWORD *)((char *)Library + (_QWORD)v13 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + (_QWORD)v13 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v8[v12]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v22.dlp.szProcName);
        if ( !ProcAddress )
        {
          v22.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v22)) == 0 )
          {
            Arguments = (ULONG_PTR)&v22;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess(v20, v19, v21);
            ProcAddress = v22.pfnCur;
          }
        }
        v14 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v14 )
  {
    v22.dwLastError = 0;
    v22.hmodCur = Library;
    v22.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(5, &v22);
  }
  DloadReleaseSectionWriteAccess(v13, v5, v4);
  return ProcAddress;
}

```

## disassembly

```asm
0x140025990  push    rbp
0x140025992  push    rbx
0x140025993  push    rsi
0x140025994  push    rdi
0x140025995  push    r12
0x140025997  push    r13
0x140025999  push    r14
0x14002599b  push    r15
0x14002599d  mov     rbp, rsp
0x1400259a0  sub     rsp, 78h
0x1400259a4  xor     eax, eax
0x1400259a6  mov     r12, rdx
0x1400259a9  mov     rsi, rcx
0x1400259ac  mov     [rbp+var_54], eax
0x1400259af  xor     edx, edx; Val
0x1400259b1  lea     rcx, [rbp+var_58]; void *
0x1400259b5  lea     r8d, [rax+44h]; Size
0x1400259b9  call    memset_0
0x1400259be  call    DloadAcquireSectionWriteAccess
0x1400259c3  mov     eax, [rsi+4]
0x1400259c6  lea     rdx, __ImageBase
0x1400259cd  mov     r14d, [rsi+8]
0x1400259d1  add     rax, rdx
0x1400259d4  mov     r15d, [rsi+14h]
0x1400259d8  add     r14, rdx
0x1400259db  mov     ecx, [rsi+1Ch]
0x1400259de  add     r15, rdx
0x1400259e1  mov     [rbp+lpLibFileName], rax
0x1400259e5  mov     eax, [rsi]
0x1400259e7  mov     dword ptr [rbp+Arguments], ecx
0x1400259ea  mov     [rbp+var_58], 48h ; 'H'
0x1400259f1  mov     [rbp+var_50], rsi
0x1400259f5  mov     [rbp+var_48], r12
0x1400259f9  mov     [rbp+var_38], 0
0x140025a00  mov     [rbp+lpProcName], 0
0x140025a08  mov     [rbp+var_28], 0
0x140025a10  mov     [rbp+var_20], 0
0x140025a18  mov     [rbp+var_18], 0
0x140025a1f  test    al, 1
0x140025a21  jnz     short loc_140025A4C
0x140025a23  lea     rax, [rbp+var_58]
0x140025a27  mov     [rbp+Arguments], rax
0x140025a2b  call    DloadReleaseSectionWriteAccess
0x140025a30  xor     edx, edx; dwExceptionFlags
0x140025a32  lea     r9, [rbp+Arguments]; lpArguments
0x140025a36  mov     ecx, 0C06D0057h; dwExceptionCode
0x140025a3b  lea     r8d, [rdx+1]; nNumberOfArguments
0x140025a3f  call    cs:__imp_RaiseException
0x140025a45  xor     eax, eax
0x140025a47  jmp     loc_140025CB3
0x140025a4c  mov     eax, [rsi+0Ch]
0x140025a4f  mov     rcx, r12
0x140025a52  mov     rbx, [r14]
0x140025a55  sub     rcx, rax
0x140025a58  sub     rcx, rdx
0x140025a5b  sar     rcx, 3
0x140025a5f  mov     eax, ecx
0x140025a61  mov     ecx, [rsi+10h]
0x140025a64  lea     r13, ds:0[rax*8]
0x140025a6c  xor     eax, eax
0x140025a6e  add     rcx, r13
0x140025a71  cmp     [rcx+rdx], rax
0x140025a75  setnl   al
0x140025a78  mov     [rbp+var_38], eax
0x140025a7b  test    eax, eax
0x140025a7d  jz      short loc_140025A92
0x140025a7f  mov     eax, [rcx+rdx]
0x140025a82  lea     rdx, __ImageBase.unused+2
0x140025a89  add     rax, rdx
0x140025a8c  mov     [rbp+lpProcName], rax
0x140025a90  jmp     short loc_140025A99
0x140025a92  movzx   eax, word ptr [rcx+rdx]
0x140025a96  mov     dword ptr [rbp+lpProcName], eax
0x140025a99  mov     rax, cs:__pfnDliNotifyHook2
0x140025aa0  xor     edi, edi
0x140025aa2  test    rax, rax
0x140025aa5  jz      short loc_140025AC5
0x140025aa7  lea     rdx, [rbp+var_58]
0x140025aab  xor     ecx, ecx
0x140025aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025ab2  mov     rdi, rax
0x140025ab5  test    rax, rax
0x140025ab8  mov     rax, cs:__pfnDliNotifyHook2
0x140025abf  jnz     loc_140025C89
0x140025ac5  test    rbx, rbx
0x140025ac8  jnz     loc_140025BBB
0x140025ace  test    rax, rax
0x140025ad1  jz      short loc_140025AE7
0x140025ad3  lea     rdx, [rbp+var_58]
0x140025ad7  lea     ecx, [rbx+1]
0x140025ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025adf  mov     rbx, rax
0x140025ae2  test    rax, rax
0x140025ae5  jnz     short loc_140025B52
0x140025ae7  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x140025aeb  xor     r8d, r8d; dwFlags
0x140025aee  xor     edx, edx; hFile
0x140025af0  call    cs:__imp_LoadLibraryExA
0x140025af6  mov     rbx, rax
0x140025af9  test    rax, rax
0x140025afc  jnz     short loc_140025B52
0x140025afe  call    cs:__imp_GetLastError
0x140025b04  mov     [rbp+var_18], eax
0x140025b07  mov     rax, cs:__pfnDefaultDliFailureHook2
0x140025b0e  test    rax, rax
0x140025b11  jz      short loc_140025B27
0x140025b13  lea     rdx, [rbp+var_58]
0x140025b17  lea     ecx, [rbx+3]
0x140025b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025b1f  mov     rbx, rax
0x140025b22  test    rax, rax
0x140025b25  jnz     short loc_140025B52
0x140025b27  lea     rax, [rbp+var_58]
0x140025b2b  mov     [rbp+Arguments], rax
0x140025b2f  call    DloadReleaseSectionWriteAccess
0x140025b34  xor     edx, edx; dwExceptionFlags
0x140025b36  lea     r9, [rbp+Arguments]; lpArguments
0x140025b3a  mov     ecx, 0C06D007Eh; dwExceptionCode
0x140025b3f  lea     r8d, [rdx+1]; nNumberOfArguments
0x140025b43  call    cs:__imp_RaiseException
0x140025b49  mov     rax, [rbp+var_20]
0x140025b4d  jmp     loc_140025CB3
0x140025b52  xor     eax, eax
0x140025b54  lock cmpxchg [r14], rbx
0x140025b59  mov     r14, rax
0x140025b5c  jnz     short loc_140025B9E
0x140025b5e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140025b62  jz      short loc_140025BB4
0x140025b64  cmp     dword ptr [rsi+18h], 0
0x140025b68  jz      short loc_140025BB4
0x140025b6a  call    cs:__imp_GetProcessHeap
0x140025b70  mov     edx, 8; dwFlags
0x140025b75  mov     rcx, rax; hHeap
0x140025b78  lea     r8d, [rdx+8]; dwBytes
0x140025b7c  call    cs:__imp_HeapAlloc
0x140025b82  test    rax, rax
0x140025b85  jz      short loc_140025BB4
0x140025b87  mov     [rax+8], rsi
0x140025b8b  mov     rcx, cs:__puiHead
0x140025b92  mov     [rax], rcx
0x140025b95  mov     cs:__puiHead, rax
0x140025b9c  jmp     short loc_140025BB4
0x140025b9e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140025ba2  jz      short loc_140025BAD
0x140025ba4  mov     rcx, rbx; hLibModule
0x140025ba7  call    cs:__imp_FreeLibrary
0x140025bad  cmp     rbx, r14
0x140025bb0  cmovnz  rbx, r14
0x140025bb4  mov     rax, cs:__pfnDliNotifyHook2
0x140025bbb  mov     [rbp+var_28], rbx
0x140025bbf  test    rax, rax
0x140025bc2  jz      short loc_140025BDC
0x140025bc4  lea     rdx, [rbp+var_58]
0x140025bc8  mov     ecx, 2
0x140025bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025bd2  mov     rdi, rax
0x140025bd5  mov     rax, cs:__pfnDliNotifyHook2
0x140025bdc  test    rdi, rdi
0x140025bdf  jnz     loc_140025C85
0x140025be5  cmp     [rsi+14h], edi
0x140025be8  jz      short loc_140025C15
0x140025bea  cmp     [rsi+1Ch], edi
0x140025bed  jz      short loc_140025C15
0x140025bef  movsxd  rcx, dword ptr [rbx+3Ch]
0x140025bf3  cmp     dword ptr [rcx+rbx], 4550h
0x140025bfa  jnz     short loc_140025C15
0x140025bfc  mov     edx, dword ptr [rbp+Arguments]
0x140025bff  cmp     [rcx+rbx+8], edx
0x140025c03  jnz     short loc_140025C15
0x140025c05  cmp     rbx, [rcx+rbx+30h]
0x140025c0a  jnz     short loc_140025C15
0x140025c0c  mov     rdi, [r15+r13]
0x140025c10  test    rdi, rdi
0x140025c13  jnz     short loc_140025C85
0x140025c15  mov     rdx, [rbp+lpProcName]; lpProcName
0x140025c19  mov     rcx, rbx; hModule
0x140025c1c  call    cs:__imp_GetProcAddress
0x140025c22  mov     rdi, rax
0x140025c25  test    rax, rax
0x140025c28  jnz     short loc_140025C7E
0x140025c2a  call    cs:__imp_GetLastError
0x140025c30  mov     [rbp+var_18], eax
0x140025c33  mov     rax, cs:__pfnDefaultDliFailureHook2
0x140025c3a  test    rax, rax
0x140025c3d  jz      short loc_140025C53
0x140025c3f  lea     rdx, [rbp+var_58]
0x140025c43  lea     ecx, [rdi+4]
0x140025c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025c4b  mov     rdi, rax
0x140025c4e  test    rax, rax
0x140025c51  jnz     short loc_140025C7E
0x140025c53  lea     rax, [rbp+var_58]
0x140025c57  mov     [rbp+Arguments], rax
0x140025c5b  call    DloadReleaseSectionWriteAccess
0x140025c60  xor     edx, edx; dwExceptionFlags
0x140025c62  lea     r9, [rbp+Arguments]; lpArguments
0x140025c66  mov     ecx, 0C06D007Fh; dwExceptionCode
0x140025c6b  lea     r8d, [rdx+1]; nNumberOfArguments
0x140025c6f  call    cs:__imp_RaiseException
0x140025c75  call    DloadAcquireSectionWriteAccess
0x140025c7a  mov     rdi, [rbp+var_20]
0x140025c7e  mov     rax, cs:__pfnDliNotifyHook2
0x140025c85  mov     [r12], rdi
0x140025c89  test    rax, rax
0x140025c8c  jz      short loc_140025CAB
0x140025c8e  lea     rdx, [rbp+var_58]
0x140025c92  mov     [rbp+var_18], 0
0x140025c99  mov     ecx, 5
0x140025c9e  mov     [rbp+var_28], rbx
0x140025ca2  mov     [rbp+var_20], rdi
0x140025ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025cab  call    DloadReleaseSectionWriteAccess
0x140025cb0  mov     rax, rdi
0x140025cb3  add     rsp, 78h
0x140025cb7  pop     r15
0x140025cb9  pop     r14
0x140025cbb  pop     r13
0x140025cbd  pop     r12
0x140025cbf  pop     rdi
0x140025cc0  pop     rsi
0x140025cc1  pop     rbx
0x140025cc2  pop     rbp
0x140025cc3  retn
```
