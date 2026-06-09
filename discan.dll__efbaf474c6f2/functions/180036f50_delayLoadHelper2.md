# __delayLoadHelper2

- ea: `0x180036f50`
- end: `0x180037284`
- name: `__delayLoadHelper2`
- size: `820`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002abf`

## callees

- `0x180036cf0`
- `0x180036ef0`
- `0x180036f50`
- `0x1800375ee`
- `0x180039010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x1800370b0`
- `KERNEL32!LoadLibraryExA` at `0x1800370b0`
- `KERNEL32!HeapAlloc` at `0x18003713c`
- `KERNEL32!HeapAlloc` at `0x18003713c`
- `KERNEL32!GetProcessHeap` at `0x18003712a`
- `KERNEL32!GetProcessHeap` at `0x18003712a`
- `KERNEL32!FreeLibrary` at `0x180037167`
- `KERNEL32!FreeLibrary` at `0x180037167`
- `KERNEL32!GetLastError` at `0x1800370be`
- `KERNEL32!GetLastError` at `0x1800371ea`
- `KERNEL32!GetLastError` at `0x1800370be`
- `KERNEL32!GetLastError` at `0x1800371ea`
- `KERNEL32!RaiseException` at `0x180036fff`
- `KERNEL32!RaiseException` at `0x180037103`
- `KERNEL32!RaiseException` at `0x18003722f`
- `KERNEL32!RaiseException` at `0x180036fff`
- `KERNEL32!RaiseException` at `0x180037103`
- `KERNEL32!RaiseException` at `0x18003722f`
- `KERNEL32!GetProcAddress` at `0x1800371dc`
- `KERNEL32!GetProcAddress` at `0x1800371dc`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  __int16 *v5; // rdx
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
  v5 = &_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
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
  v22.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + (_QWORD)v13) >= 0LL;
  if ( v22.dlp.fImportByName )
  {
    v5 = &word_180000002;
    v22.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + (_QWORD)v13);
  }
  else
  {
    v22.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + (_QWORD)v13);
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
        || (v5 = (__int16 *)(unsigned int)Arguments, *(_DWORD *)((char *)Library + (_QWORD)v13 + 8) != (_DWORD)Arguments)
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
0x180036f50  push    rbp
0x180036f52  push    rbx
0x180036f53  push    rsi
0x180036f54  push    rdi
0x180036f55  push    r12
0x180036f57  push    r13
0x180036f59  push    r14
0x180036f5b  push    r15
0x180036f5d  mov     rbp, rsp
0x180036f60  sub     rsp, 78h
0x180036f64  xor     eax, eax
0x180036f66  mov     r12, rdx
0x180036f69  mov     rsi, rcx
0x180036f6c  mov     [rbp+var_54], eax
0x180036f6f  xor     edx, edx; Val
0x180036f71  lea     rcx, [rbp+var_58]; void *
0x180036f75  lea     r8d, [rax+44h]; Size
0x180036f79  call    memset_0
0x180036f7e  call    DloadAcquireSectionWriteAccess
0x180036f83  mov     eax, [rsi+4]
0x180036f86  lea     rdx, __ImageBase
0x180036f8d  mov     r14d, [rsi+8]
0x180036f91  add     rax, rdx
0x180036f94  mov     r15d, [rsi+14h]
0x180036f98  add     r14, rdx
0x180036f9b  mov     ecx, [rsi+1Ch]
0x180036f9e  add     r15, rdx
0x180036fa1  mov     [rbp+lpLibFileName], rax
0x180036fa5  mov     eax, [rsi]
0x180036fa7  mov     dword ptr [rbp+Arguments], ecx
0x180036faa  mov     [rbp+var_58], 48h ; 'H'
0x180036fb1  mov     [rbp+var_50], rsi
0x180036fb5  mov     [rbp+var_48], r12
0x180036fb9  mov     [rbp+var_38], 0
0x180036fc0  mov     [rbp+lpProcName], 0
0x180036fc8  mov     [rbp+var_28], 0
0x180036fd0  mov     [rbp+var_20], 0
0x180036fd8  mov     [rbp+var_18], 0
0x180036fdf  test    al, 1
0x180036fe1  jnz     short loc_18003700C
0x180036fe3  lea     rax, [rbp+var_58]
0x180036fe7  mov     [rbp+Arguments], rax
0x180036feb  call    DloadReleaseSectionWriteAccess
0x180036ff0  xor     edx, edx; dwExceptionFlags
0x180036ff2  lea     r9, [rbp+Arguments]; lpArguments
0x180036ff6  mov     ecx, 0C06D0057h; dwExceptionCode
0x180036ffb  lea     r8d, [rdx+1]; nNumberOfArguments
0x180036fff  call    cs:__imp_RaiseException
0x180037005  xor     eax, eax
0x180037007  jmp     loc_180037273
0x18003700c  mov     eax, [rsi+0Ch]
0x18003700f  mov     rcx, r12
0x180037012  mov     rbx, [r14]
0x180037015  sub     rcx, rax
0x180037018  sub     rcx, rdx
0x18003701b  sar     rcx, 3
0x18003701f  mov     eax, ecx
0x180037021  mov     ecx, [rsi+10h]
0x180037024  lea     r13, ds:0[rax*8]
0x18003702c  xor     eax, eax
0x18003702e  add     rcx, r13
0x180037031  cmp     [rcx+rdx], rax
0x180037035  setnl   al
0x180037038  mov     [rbp+var_38], eax
0x18003703b  test    eax, eax
0x18003703d  jz      short loc_180037052
0x18003703f  mov     eax, [rcx+rdx]
0x180037042  lea     rdx, word_180000002
0x180037049  add     rax, rdx
0x18003704c  mov     [rbp+lpProcName], rax
0x180037050  jmp     short loc_180037059
0x180037052  movzx   eax, word ptr [rcx+rdx]
0x180037056  mov     dword ptr [rbp+lpProcName], eax
0x180037059  mov     rax, cs:__pfnDliNotifyHook2
0x180037060  xor     edi, edi
0x180037062  test    rax, rax
0x180037065  jz      short loc_180037085
0x180037067  lea     rdx, [rbp+var_58]
0x18003706b  xor     ecx, ecx
0x18003706d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037072  mov     rdi, rax
0x180037075  test    rax, rax
0x180037078  mov     rax, cs:__pfnDliNotifyHook2
0x18003707f  jnz     loc_180037249
0x180037085  test    rbx, rbx
0x180037088  jnz     loc_18003717B
0x18003708e  test    rax, rax
0x180037091  jz      short loc_1800370A7
0x180037093  lea     rdx, [rbp+var_58]
0x180037097  lea     ecx, [rbx+1]
0x18003709a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003709f  mov     rbx, rax
0x1800370a2  test    rax, rax
0x1800370a5  jnz     short loc_180037112
0x1800370a7  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800370ab  xor     r8d, r8d; dwFlags
0x1800370ae  xor     edx, edx; hFile
0x1800370b0  call    cs:__imp_LoadLibraryExA
0x1800370b6  mov     rbx, rax
0x1800370b9  test    rax, rax
0x1800370bc  jnz     short loc_180037112
0x1800370be  call    cs:__imp_GetLastError
0x1800370c4  mov     [rbp+var_18], eax
0x1800370c7  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800370ce  test    rax, rax
0x1800370d1  jz      short loc_1800370E7
0x1800370d3  lea     rdx, [rbp+var_58]
0x1800370d7  lea     ecx, [rbx+3]
0x1800370da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370df  mov     rbx, rax
0x1800370e2  test    rax, rax
0x1800370e5  jnz     short loc_180037112
0x1800370e7  lea     rax, [rbp+var_58]
0x1800370eb  mov     [rbp+Arguments], rax
0x1800370ef  call    DloadReleaseSectionWriteAccess
0x1800370f4  xor     edx, edx; dwExceptionFlags
0x1800370f6  lea     r9, [rbp+Arguments]; lpArguments
0x1800370fa  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800370ff  lea     r8d, [rdx+1]; nNumberOfArguments
0x180037103  call    cs:__imp_RaiseException
0x180037109  mov     rax, [rbp+var_20]
0x18003710d  jmp     loc_180037273
0x180037112  xor     eax, eax
0x180037114  lock cmpxchg [r14], rbx
0x180037119  mov     r14, rax
0x18003711c  jnz     short loc_18003715E
0x18003711e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180037122  jz      short loc_180037174
0x180037124  cmp     dword ptr [rsi+18h], 0
0x180037128  jz      short loc_180037174
0x18003712a  call    cs:__imp_GetProcessHeap
0x180037130  mov     edx, 8; dwFlags
0x180037135  mov     rcx, rax; hHeap
0x180037138  lea     r8d, [rdx+8]; dwBytes
0x18003713c  call    cs:__imp_HeapAlloc
0x180037142  test    rax, rax
0x180037145  jz      short loc_180037174
0x180037147  mov     [rax+8], rsi
0x18003714b  mov     rcx, cs:__puiHead
0x180037152  mov     [rax], rcx
0x180037155  mov     cs:__puiHead, rax
0x18003715c  jmp     short loc_180037174
0x18003715e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180037162  jz      short loc_18003716D
0x180037164  mov     rcx, rbx; hLibModule
0x180037167  call    cs:__imp_FreeLibrary
0x18003716d  cmp     rbx, r14
0x180037170  cmovnz  rbx, r14
0x180037174  mov     rax, cs:__pfnDliNotifyHook2
0x18003717b  mov     [rbp+var_28], rbx
0x18003717f  test    rax, rax
0x180037182  jz      short loc_18003719C
0x180037184  lea     rdx, [rbp+var_58]
0x180037188  mov     ecx, 2
0x18003718d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037192  mov     rdi, rax
0x180037195  mov     rax, cs:__pfnDliNotifyHook2
0x18003719c  test    rdi, rdi
0x18003719f  jnz     loc_180037245
0x1800371a5  cmp     [rsi+14h], edi
0x1800371a8  jz      short loc_1800371D5
0x1800371aa  cmp     [rsi+1Ch], edi
0x1800371ad  jz      short loc_1800371D5
0x1800371af  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800371b3  cmp     dword ptr [rcx+rbx], 4550h
0x1800371ba  jnz     short loc_1800371D5
0x1800371bc  mov     edx, dword ptr [rbp+Arguments]
0x1800371bf  cmp     [rcx+rbx+8], edx
0x1800371c3  jnz     short loc_1800371D5
0x1800371c5  cmp     rbx, [rcx+rbx+30h]
0x1800371ca  jnz     short loc_1800371D5
0x1800371cc  mov     rdi, [r15+r13]
0x1800371d0  test    rdi, rdi
0x1800371d3  jnz     short loc_180037245
0x1800371d5  mov     rdx, [rbp+lpProcName]; lpProcName
0x1800371d9  mov     rcx, rbx; hModule
0x1800371dc  call    cs:__imp_GetProcAddress
0x1800371e2  mov     rdi, rax
0x1800371e5  test    rax, rax
0x1800371e8  jnz     short loc_18003723E
0x1800371ea  call    cs:__imp_GetLastError
0x1800371f0  mov     [rbp+var_18], eax
0x1800371f3  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800371fa  test    rax, rax
0x1800371fd  jz      short loc_180037213
0x1800371ff  lea     rdx, [rbp+var_58]
0x180037203  lea     ecx, [rdi+4]
0x180037206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003720b  mov     rdi, rax
0x18003720e  test    rax, rax
0x180037211  jnz     short loc_18003723E
0x180037213  lea     rax, [rbp+var_58]
0x180037217  mov     [rbp+Arguments], rax
0x18003721b  call    DloadReleaseSectionWriteAccess
0x180037220  xor     edx, edx; dwExceptionFlags
0x180037222  lea     r9, [rbp+Arguments]; lpArguments
0x180037226  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18003722b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18003722f  call    cs:__imp_RaiseException
0x180037235  call    DloadAcquireSectionWriteAccess
0x18003723a  mov     rdi, [rbp+var_20]
0x18003723e  mov     rax, cs:__pfnDliNotifyHook2
0x180037245  mov     [r12], rdi
0x180037249  test    rax, rax
0x18003724c  jz      short loc_18003726B
0x18003724e  lea     rdx, [rbp+var_58]
0x180037252  mov     [rbp+var_18], 0
0x180037259  mov     ecx, 5
0x18003725e  mov     [rbp+var_28], rbx
0x180037262  mov     [rbp+var_20], rdi
0x180037266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003726b  call    DloadReleaseSectionWriteAccess
0x180037270  mov     rax, rdi
0x180037273  add     rsp, 78h
0x180037277  pop     r15
0x180037279  pop     r14
0x18003727b  pop     r13
0x18003727d  pop     r12
0x18003727f  pop     rdi
0x180037280  pop     rsi
0x180037281  pop     rbx
0x180037282  pop     rbp
0x180037283  retn
```
