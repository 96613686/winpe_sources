# ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)

- ea: `0x18004b624`
- end: `0x18004b934`
- name: `?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z`
- size: `784`
- prototype: `__int64 __fastcall(bool, unsigned int, void **, void **, void **, void **, void **, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18004ae14`
- `0x18004aff0`

## callees

- `0x18004b624`
- `0x18007f2d8`
- `0x180537e64`
- `0x18054e310`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x18004b8ee`
- `KERNEL32!UnmapViewOfFile` at `0x18004b8ee`
- `KERNEL32!CreateMutexW` at `0x18004b711`
- `KERNEL32!CreateMutexW` at `0x18004b711`
- `KERNEL32!OpenMutexW` at `0x18004b741`
- `KERNEL32!OpenMutexW` at `0x18004b741`
- `KERNEL32!CreateFileMappingW` at `0x18004b7b7`
- `KERNEL32!CreateFileMappingW` at `0x18004b7b7`
- `KERNEL32!MapViewOfFile` at `0x18004b857`
- `KERNEL32!MapViewOfFile` at `0x18004b857`
- `KERNEL32!OpenFileMappingW` at `0x18004b807`
- `KERNEL32!OpenFileMappingW` at `0x18004b807`
- `KERNEL32!CloseHandle` at `0x18004b8a0`
- `KERNEL32!CloseHandle` at `0x18004b8b3`
- `KERNEL32!CloseHandle` at `0x18004b8c7`
- `KERNEL32!CloseHandle` at `0x18004b8da`
- `KERNEL32!CloseHandle` at `0x18004b901`
- `KERNEL32!CloseHandle` at `0x18004b8a0`
- `KERNEL32!CloseHandle` at `0x18004b8b3`
- `KERNEL32!CloseHandle` at `0x18004b8c7`
- `KERNEL32!CloseHandle` at `0x18004b8da`
- `KERNEL32!CloseHandle` at `0x18004b901`
- `KERNEL32!GetLastError` at `0x18004b74f`
- `KERNEL32!GetLastError` at `0x18004b7ca`
- `KERNEL32!GetLastError` at `0x18004b7ec`
- `KERNEL32!GetLastError` at `0x18004b816`
- `KERNEL32!GetLastError` at `0x18004b86a`
- `KERNEL32!GetLastError` at `0x18004b74f`
- `KERNEL32!GetLastError` at `0x18004b7ca`
- `KERNEL32!GetLastError` at `0x18004b7ec`
- `KERNEL32!GetLastError` at `0x18004b816`
- `KERNEL32!GetLastError` at `0x18004b86a`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004b72d`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004b7e2`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004b72d`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004b7e2`

## pseudocode

```c
__int64 __fastcall ObtainIELowUtilSyncObjects(
        __int64 a1,
        __int64 a2,
        void **a3,
        void **a4,
        void **a5,
        void **a6,
        void **a7,
        void **a8)
{
  signed int IELowEvent; // ebx
  unsigned int v10; // ebp
  char v11; // si
  HANDLE MutexW; // rax
  signed int LastError; // eax
  HANDLE FileMappingW; // rax
  signed int v15; // eax
  void *v16; // rax
  signed int v17; // eax
  void **v18; // rcx
  void *v19; // rcx
  WCHAR Name[264]; // [rsp+40h] [rbp-258h] BYREF

  IELowEvent = 0;
  v10 = a2;
  v11 = a1;
  if ( a3 )
  {
    IELowEvent = _CreateIELowEvent(a1, a2, 0, a3);
    if ( IELowEvent < 0 )
    {
      v18 = a3;
      goto LABEL_40;
    }
  }
  if ( a4 )
  {
    LOBYTE(a1) = v11;
    IELowEvent = _CreateIELowEvent(a1, v10, 1, a4);
    if ( IELowEvent < 0 )
      goto LABEL_37;
  }
  if ( a5 )
  {
    LOBYTE(a1) = v11;
    IELowEvent = _CreateIELowEvent(a1, v10, 2, a5);
    if ( IELowEvent < 0 )
      goto LABEL_37;
  }
  if ( a6 )
  {
    IELowEvent = GetLowUtilBrokerObjectName(Name, a2, 3, v10);
    if ( IELowEvent < 0 )
      goto LABEL_37;
    if ( v11 )
    {
      MutexW = CreateMutexW(0, 0, Name);
      *a6 = MutexW;
      if ( MutexW )
      {
        IELowEvent = SetWindowsHandleAccess(MutexW, 0x114Fu, 0x100001u);
        MutexW = *a6;
      }
    }
    else
    {
      MutexW = OpenMutexW(0x100001u, 0, Name);
      *a6 = MutexW;
    }
    if ( !MutexW )
    {
      LastError = GetLastError();
      IELowEvent = LastError;
      if ( LastError > 0 )
        IELowEvent = (unsigned __int16)LastError | 0x80070000;
    }
    if ( IELowEvent < 0 )
      goto LABEL_37;
  }
  if ( a7 )
  {
    IELowEvent = GetLowUtilBrokerObjectName(Name, a2, 4, v10);
    if ( IELowEvent < 0 )
      goto LABEL_37;
    if ( v11 )
    {
      FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0xB05Cu, Name);
      *a7 = FileMappingW;
      if ( !FileMappingW || GetLastError() == 183 )
      {
        if ( GetLastError() == 183 )
          IELowEvent = -2147418113;
      }
      else
      {
        IELowEvent = SetWindowsHandleAccess(*a7, 0x2114Fu, 0xC0000002);
      }
    }
    else
    {
      *a7 = OpenFileMappingW(6u, 0, Name);
    }
    if ( !*a7 )
    {
      v15 = GetLastError();
      IELowEvent = v15;
      if ( v15 > 0 )
        IELowEvent = (unsigned __int16)v15 | 0x80070000;
    }
    if ( IELowEvent < 0 )
      goto LABEL_37;
    if ( *a7 )
    {
      if ( a8 )
      {
        v16 = MapViewOfFile(*a7, 2u, 0, 0, 0);
        *a8 = v16;
        if ( !v16 )
        {
          v17 = GetLastError();
          IELowEvent = v17;
          if ( v17 > 0 )
            IELowEvent = (unsigned __int16)v17 | 0x80070000;
          if ( IELowEvent < 0 )
          {
LABEL_37:
            v18 = a3;
            if ( !a3 )
            {
LABEL_42:
              if ( a4 && *a4 )
                CloseHandle(*a4);
              if ( a5 && *a5 )
                CloseHandle(*a5);
              if ( a6 && *a6 )
                CloseHandle(*a6);
              if ( a8 && *a8 )
                UnmapViewOfFile(*a8);
              if ( a7 && *a7 )
                CloseHandle(*a7);
              return (unsigned int)IELowEvent;
            }
LABEL_40:
            v19 = *v18;
            if ( v19 )
              CloseHandle(v19);
            goto LABEL_42;
          }
        }
      }
    }
  }
  return (unsigned int)IELowEvent;
}

```

## disassembly

```asm
0x18004b624  mov     [rsp+arg_0], rbx
0x18004b629  push    rbp
0x18004b62a  push    rsi
0x18004b62b  push    rdi
0x18004b62c  push    r12
0x18004b62e  push    r13
0x18004b630  push    r14
0x18004b632  push    r15
0x18004b634  sub     rsp, 260h
0x18004b63b  mov     rax, cs:__security_cookie
0x18004b642  xor     rax, rsp
0x18004b645  mov     [rsp+298h+var_48], rax
0x18004b64d  mov     r13, [rsp+298h+arg_20]
0x18004b655  xor     ebx, ebx
0x18004b657  mov     r14, [rsp+298h+arg_28]
0x18004b65f  mov     rax, r8
0x18004b662  mov     rdi, [rsp+298h+arg_30]
0x18004b66a  mov     r15, r9
0x18004b66d  mov     r12, [rsp+298h+arg_38]
0x18004b675  mov     ebp, edx
0x18004b677  mov     [rsp+298h+var_268], rax
0x18004b67c  mov     sil, cl
0x18004b67f  test    r8, r8
0x18004b682  jz      short loc_18004B699
0x18004b684  mov     r9, rax
0x18004b687  xor     r8d, r8d
0x18004b68a  call    ?_CreateIELowEvent@@YAJ_NKW4_ISOUTILOBJTYPE@@PEAPEAX@Z; _CreateIELowEvent(bool,ulong,_ISOUTILOBJTYPE,void * *)
0x18004b68f  mov     ebx, eax
0x18004b691  test    eax, eax
0x18004b693  js      loc_18004B893
0x18004b699  test    r15, r15
0x18004b69c  jz      short loc_18004B6BB
0x18004b69e  mov     r9, r15
0x18004b6a1  mov     r8d, 1
0x18004b6a7  mov     edx, ebp
0x18004b6a9  mov     cl, sil
0x18004b6ac  call    ?_CreateIELowEvent@@YAJ_NKW4_ISOUTILOBJTYPE@@PEAPEAX@Z; _CreateIELowEvent(bool,ulong,_ISOUTILOBJTYPE,void * *)
0x18004b6b1  mov     ebx, eax
0x18004b6b3  test    eax, eax
0x18004b6b5  js      loc_18004B887
0x18004b6bb  test    r13, r13
0x18004b6be  jz      short loc_18004B6DD
0x18004b6c0  mov     r9, r13
0x18004b6c3  mov     r8d, 2
0x18004b6c9  mov     edx, ebp
0x18004b6cb  mov     cl, sil
0x18004b6ce  call    ?_CreateIELowEvent@@YAJ_NKW4_ISOUTILOBJTYPE@@PEAPEAX@Z; _CreateIELowEvent(bool,ulong,_ISOUTILOBJTYPE,void * *)
0x18004b6d3  mov     ebx, eax
0x18004b6d5  test    eax, eax
0x18004b6d7  js      loc_18004B887
0x18004b6dd  test    r14, r14
0x18004b6e0  jz      loc_18004B76C
0x18004b6e6  mov     r9d, ebp
0x18004b6e9  lea     rcx, [rsp+298h+Name]
0x18004b6ee  mov     r8d, 3
0x18004b6f4  call    ?GetLowUtilBrokerObjectName@@YAJPEAGKW4_ISOUTILOBJTYPE@@K@Z; GetLowUtilBrokerObjectName(ushort *,ulong,_ISOUTILOBJTYPE,ulong)
0x18004b6f9  mov     ebx, eax
0x18004b6fb  test    eax, eax
0x18004b6fd  js      loc_18004B887
0x18004b703  xor     edx, edx; bInheritHandle
0x18004b705  lea     r8, [rsp+298h+Name]; lpName
0x18004b70a  test    sil, sil
0x18004b70d  jz      short loc_18004B73C
0x18004b70f  xor     ecx, ecx; lpMutexAttributes
0x18004b711  call    cs:__imp_CreateMutexW
0x18004b717  mov     [r14], rax
0x18004b71a  test    rax, rax
0x18004b71d  jz      short loc_18004B73A
0x18004b71f  mov     edx, 114Fh
0x18004b724  mov     r8d, 100001h
0x18004b72a  mov     rcx, rax
0x18004b72d  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18004b733  mov     ebx, eax
0x18004b735  mov     rax, [r14]
0x18004b738  jmp     short loc_18004B74A
0x18004b73a  jmp     short loc_18004B74A
0x18004b73c  mov     ecx, 100001h; dwDesiredAccess
0x18004b741  call    cs:__imp_OpenMutexW
0x18004b747  mov     [r14], rax
0x18004b74a  test    rax, rax
0x18004b74d  jnz     short loc_18004B764
0x18004b74f  call    cs:__imp_GetLastError
0x18004b755  mov     ebx, eax
0x18004b757  test    eax, eax
0x18004b759  jle     short loc_18004B764
0x18004b75b  movzx   ebx, ax
0x18004b75e  or      ebx, 80070000h
0x18004b764  test    ebx, ebx
0x18004b766  js      loc_18004B887
0x18004b76c  test    rdi, rdi
0x18004b76f  jz      loc_18004B907
0x18004b775  mov     r9d, ebp
0x18004b778  lea     rcx, [rsp+298h+Name]
0x18004b77d  mov     ebp, 4
0x18004b782  mov     r8d, ebp
0x18004b785  call    ?GetLowUtilBrokerObjectName@@YAJPEAGKW4_ISOUTILOBJTYPE@@K@Z; GetLowUtilBrokerObjectName(ushort *,ulong,_ISOUTILOBJTYPE,ulong)
0x18004b78a  mov     ebx, eax
0x18004b78c  test    eax, eax
0x18004b78e  js      loc_18004B887
0x18004b794  test    sil, sil
0x18004b797  jz      short loc_18004B7FD
0x18004b799  lea     rax, [rsp+298h+Name]
0x18004b79e  xor     r9d, r9d; dwMaximumSizeHigh
0x18004b7a1  mov     [rsp+298h+lpName], rax; lpName
0x18004b7a6  mov     r8d, ebp; flProtect
0x18004b7a9  xor     edx, edx; lpFileMappingAttributes
0x18004b7ab  mov     [rsp+298h+dwMaximumSizeLow], 0B05Ch; dwMaximumSizeLow
0x18004b7b3  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004b7b7  call    cs:__imp_CreateFileMappingW
0x18004b7bd  mov     [rdi], rax
0x18004b7c0  mov     esi, 0B7h
0x18004b7c5  test    rax, rax
0x18004b7c8  jz      short loc_18004B7EC
0x18004b7ca  call    cs:__imp_GetLastError
0x18004b7d0  cmp     eax, esi
0x18004b7d2  jz      short loc_18004B7EC
0x18004b7d4  mov     rcx, [rdi]
0x18004b7d7  mov     edx, 2114Fh
0x18004b7dc  mov     r8d, 0C0000002h
0x18004b7e2  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18004b7e8  mov     ebx, eax
0x18004b7ea  jmp     short loc_18004B810
0x18004b7ec  call    cs:__imp_GetLastError
0x18004b7f2  cmp     eax, esi
0x18004b7f4  jnz     short loc_18004B810
0x18004b7f6  mov     ebx, 8000FFFFh
0x18004b7fb  jmp     short loc_18004B810
0x18004b7fd  xor     edx, edx; bInheritHandle
0x18004b7ff  lea     r8, [rsp+298h+Name]; lpName
0x18004b804  lea     ecx, [rdx+6]; dwDesiredAccess
0x18004b807  call    cs:__imp_OpenFileMappingW
0x18004b80d  mov     [rdi], rax
0x18004b810  cmp     qword ptr [rdi], 0
0x18004b814  jnz     short loc_18004B82B
0x18004b816  call    cs:__imp_GetLastError
0x18004b81c  mov     ebx, eax
0x18004b81e  test    eax, eax
0x18004b820  jle     short loc_18004B82B
0x18004b822  movzx   ebx, ax
0x18004b825  or      ebx, 80070000h
0x18004b82b  test    ebx, ebx
0x18004b82d  js      short loc_18004B887
0x18004b82f  mov     rcx, [rdi]; hFileMappingObject
0x18004b832  test    rcx, rcx
0x18004b835  jz      loc_18004B907
0x18004b83b  test    r12, r12
0x18004b83e  jz      loc_18004B907
0x18004b844  xor     r9d, r9d; dwFileOffsetLow
0x18004b847  mov     qword ptr [rsp+298h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18004b850  xor     r8d, r8d; dwFileOffsetHigh
0x18004b853  lea     edx, [r9+2]; dwDesiredAccess
0x18004b857  call    cs:__imp_MapViewOfFile
0x18004b85d  mov     [r12], rax
0x18004b861  test    rax, rax
0x18004b864  jnz     loc_18004B907
0x18004b86a  call    cs:__imp_GetLastError
0x18004b870  mov     ebx, eax
0x18004b872  test    eax, eax
0x18004b874  jle     short loc_18004B87F
0x18004b876  movzx   ebx, ax
0x18004b879  or      ebx, 80070000h
0x18004b87f  test    ebx, ebx
0x18004b881  jns     loc_18004B907
0x18004b887  mov     rcx, [rsp+298h+var_268]
0x18004b88c  test    rcx, rcx
0x18004b88f  jnz     short loc_18004B898
0x18004b891  jmp     short loc_18004B8A6
0x18004b893  mov     rcx, [rsp+298h+var_268]
0x18004b898  mov     rcx, [rcx]; hObject
0x18004b89b  test    rcx, rcx
0x18004b89e  jz      short loc_18004B8A6
0x18004b8a0  call    cs:__imp_CloseHandle
0x18004b8a6  test    r15, r15
0x18004b8a9  jz      short loc_18004B8B9
0x18004b8ab  mov     rcx, [r15]; hObject
0x18004b8ae  test    rcx, rcx
0x18004b8b1  jz      short loc_18004B8B9
0x18004b8b3  call    cs:__imp_CloseHandle
0x18004b8b9  test    r13, r13
0x18004b8bc  jz      short loc_18004B8CD
0x18004b8be  mov     rcx, [r13+0]; hObject
0x18004b8c2  test    rcx, rcx
0x18004b8c5  jz      short loc_18004B8CD
0x18004b8c7  call    cs:__imp_CloseHandle
0x18004b8cd  test    r14, r14
0x18004b8d0  jz      short loc_18004B8E0
0x18004b8d2  mov     rcx, [r14]; hObject
0x18004b8d5  test    rcx, rcx
0x18004b8d8  jz      short loc_18004B8E0
0x18004b8da  call    cs:__imp_CloseHandle
0x18004b8e0  test    r12, r12
0x18004b8e3  jz      short loc_18004B8F4
0x18004b8e5  mov     rcx, [r12]; lpBaseAddress
0x18004b8e9  test    rcx, rcx
0x18004b8ec  jz      short loc_18004B8F4
0x18004b8ee  call    cs:__imp_UnmapViewOfFile
0x18004b8f4  test    rdi, rdi
0x18004b8f7  jz      short loc_18004B907
0x18004b8f9  mov     rcx, [rdi]; hObject
0x18004b8fc  test    rcx, rcx
0x18004b8ff  jz      short loc_18004B907
0x18004b901  call    cs:__imp_CloseHandle
0x18004b907  mov     eax, ebx
0x18004b909  mov     rcx, [rsp+298h+var_48]
0x18004b911  xor     rcx, rsp; StackCookie
0x18004b914  call    __security_check_cookie
0x18004b919  mov     rbx, [rsp+298h+arg_0]
0x18004b921  add     rsp, 260h
0x18004b928  pop     r15
0x18004b92a  pop     r14
0x18004b92c  pop     r13
0x18004b92e  pop     r12
0x18004b930  pop     rdi
0x18004b931  pop     rsi
0x18004b932  pop     rbp
0x18004b933  retn
```
