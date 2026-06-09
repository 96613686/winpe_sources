# ObtainIELowUtilSyncObjects(bool,ulong,void * *,void * *,void * *,void * *,void * *,void * *)

- ea: `0x18004ba44`
- end: `0x18004bdc1`
- name: `?ObtainIELowUtilSyncObjects@@YAJ_NKPEAPEAX11111@Z`
- size: `893`
- prototype: `__int64 __fastcall(bool, unsigned int, void **, void **, void **, void **, void **, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18004b188`
- `0x18004b370`

## callees

- `0x18004ba44`
- `0x1800857c8`
- `0x18057a4bc`
- `0x180591f80`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x18004bd6e`
- `KERNEL32!UnmapViewOfFile` at `0x18004bd6e`
- `KERNEL32!CreateMutexW` at `0x18004bb31`
- `KERNEL32!CreateMutexW` at `0x18004bb31`
- `KERNEL32!OpenMutexW` at `0x18004bb6d`
- `KERNEL32!OpenMutexW` at `0x18004bb6d`
- `KERNEL32!CreateFileMappingW` at `0x18004bbef`
- `KERNEL32!CreateFileMappingW` at `0x18004bbef`
- `KERNEL32!MapViewOfFile` at `0x18004bcb3`
- `KERNEL32!MapViewOfFile` at `0x18004bcb3`
- `KERNEL32!OpenFileMappingW` at `0x18004bc57`
- `KERNEL32!OpenFileMappingW` at `0x18004bc57`
- `KERNEL32!CloseHandle` at `0x18004bd08`
- `KERNEL32!CloseHandle` at `0x18004bd21`
- `KERNEL32!CloseHandle` at `0x18004bd3b`
- `KERNEL32!CloseHandle` at `0x18004bd54`
- `KERNEL32!CloseHandle` at `0x18004bd87`
- `KERNEL32!CloseHandle` at `0x18004bd08`
- `KERNEL32!CloseHandle` at `0x18004bd21`
- `KERNEL32!CloseHandle` at `0x18004bd3b`
- `KERNEL32!CloseHandle` at `0x18004bd54`
- `KERNEL32!CloseHandle` at `0x18004bd87`
- `KERNEL32!GetLastError` at `0x18004bb81`
- `KERNEL32!GetLastError` at `0x18004bc08`
- `KERNEL32!GetLastError` at `0x18004bc36`
- `KERNEL32!GetLastError` at `0x18004bc6c`
- `KERNEL32!GetLastError` at `0x18004bccc`
- `KERNEL32!GetLastError` at `0x18004bb81`
- `KERNEL32!GetLastError` at `0x18004bc08`
- `KERNEL32!GetLastError` at `0x18004bc36`
- `KERNEL32!GetLastError` at `0x18004bc6c`
- `KERNEL32!GetLastError` at `0x18004bccc`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004bb53`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004bc26`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004bb53`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x18004bc26`

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
0x18004ba44  mov     [rsp+arg_0], rbx
0x18004ba49  push    rbp
0x18004ba4a  push    rsi
0x18004ba4b  push    rdi
0x18004ba4c  push    r12
0x18004ba4e  push    r13
0x18004ba50  push    r14
0x18004ba52  push    r15
0x18004ba54  sub     rsp, 260h
0x18004ba5b  mov     rax, cs:__security_cookie
0x18004ba62  xor     rax, rsp
0x18004ba65  mov     [rsp+298h+var_48], rax
0x18004ba6d  mov     r13, [rsp+298h+arg_20]
0x18004ba75  xor     ebx, ebx
0x18004ba77  mov     r14, [rsp+298h+arg_28]
0x18004ba7f  mov     rax, r8
0x18004ba82  mov     rdi, [rsp+298h+arg_30]
0x18004ba8a  mov     r15, r9
0x18004ba8d  mov     r12, [rsp+298h+arg_38]
0x18004ba95  mov     ebp, edx
0x18004ba97  mov     [rsp+298h+var_268], rax
0x18004ba9c  mov     sil, cl
0x18004ba9f  test    r8, r8
0x18004baa2  jz      short loc_18004BAB9
0x18004baa4  mov     r9, rax
0x18004baa7  xor     r8d, r8d
0x18004baaa  call    ?_CreateIELowEvent@@YAJ_NKW4_ISOUTILOBJTYPE@@PEAPEAX@Z; _CreateIELowEvent(bool,ulong,_ISOUTILOBJTYPE,void * *)
0x18004baaf  mov     ebx, eax
0x18004bab1  test    eax, eax
0x18004bab3  js      loc_18004BCFB
0x18004bab9  test    r15, r15
0x18004babc  jz      short loc_18004BADB
0x18004babe  mov     r9, r15
0x18004bac1  mov     r8d, 1
0x18004bac7  mov     edx, ebp
0x18004bac9  mov     cl, sil
0x18004bacc  call    ?_CreateIELowEvent@@YAJ_NKW4_ISOUTILOBJTYPE@@PEAPEAX@Z; _CreateIELowEvent(bool,ulong,_ISOUTILOBJTYPE,void * *)
0x18004bad1  mov     ebx, eax
0x18004bad3  test    eax, eax
0x18004bad5  js      loc_18004BCEF
0x18004badb  test    r13, r13
0x18004bade  jz      short loc_18004BAFD
0x18004bae0  mov     r9, r13
0x18004bae3  mov     r8d, 2
0x18004bae9  mov     edx, ebp
0x18004baeb  mov     cl, sil
0x18004baee  call    ?_CreateIELowEvent@@YAJ_NKW4_ISOUTILOBJTYPE@@PEAPEAX@Z; _CreateIELowEvent(bool,ulong,_ISOUTILOBJTYPE,void * *)
0x18004baf3  mov     ebx, eax
0x18004baf5  test    eax, eax
0x18004baf7  js      loc_18004BCEF
0x18004bafd  test    r14, r14
0x18004bb00  jz      loc_18004BBA4
0x18004bb06  mov     r9d, ebp
0x18004bb09  lea     rcx, [rsp+298h+Name]
0x18004bb0e  mov     r8d, 3
0x18004bb14  call    ?GetLowUtilBrokerObjectName@@YAJPEAGKW4_ISOUTILOBJTYPE@@K@Z; GetLowUtilBrokerObjectName(ushort *,ulong,_ISOUTILOBJTYPE,ulong)
0x18004bb19  mov     ebx, eax
0x18004bb1b  test    eax, eax
0x18004bb1d  js      loc_18004BCEF
0x18004bb23  xor     edx, edx; bInheritHandle
0x18004bb25  lea     r8, [rsp+298h+Name]; lpName
0x18004bb2a  test    sil, sil
0x18004bb2d  jz      short loc_18004BB68
0x18004bb2f  xor     ecx, ecx; lpMutexAttributes
0x18004bb31  call    cs:__imp_CreateMutexW
0x18004bb38  nop     dword ptr [rax+rax+00h]
0x18004bb3d  mov     [r14], rax
0x18004bb40  test    rax, rax
0x18004bb43  jz      short loc_18004BB66
0x18004bb45  mov     edx, 114Fh
0x18004bb4a  mov     r8d, 100001h
0x18004bb50  mov     rcx, rax
0x18004bb53  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18004bb5a  nop     dword ptr [rax+rax+00h]
0x18004bb5f  mov     ebx, eax
0x18004bb61  mov     rax, [r14]
0x18004bb64  jmp     short loc_18004BB7C
0x18004bb66  jmp     short loc_18004BB7C
0x18004bb68  mov     ecx, 100001h; dwDesiredAccess
0x18004bb6d  call    cs:__imp_OpenMutexW
0x18004bb74  nop     dword ptr [rax+rax+00h]
0x18004bb79  mov     [r14], rax
0x18004bb7c  test    rax, rax
0x18004bb7f  jnz     short loc_18004BB9C
0x18004bb81  call    cs:__imp_GetLastError
0x18004bb88  nop     dword ptr [rax+rax+00h]
0x18004bb8d  mov     ebx, eax
0x18004bb8f  test    eax, eax
0x18004bb91  jle     short loc_18004BB9C
0x18004bb93  movzx   ebx, ax
0x18004bb96  or      ebx, 80070000h
0x18004bb9c  test    ebx, ebx
0x18004bb9e  js      loc_18004BCEF
0x18004bba4  test    rdi, rdi
0x18004bba7  jz      loc_18004BD93
0x18004bbad  mov     r9d, ebp
0x18004bbb0  lea     rcx, [rsp+298h+Name]
0x18004bbb5  mov     ebp, 4
0x18004bbba  mov     r8d, ebp
0x18004bbbd  call    ?GetLowUtilBrokerObjectName@@YAJPEAGKW4_ISOUTILOBJTYPE@@K@Z; GetLowUtilBrokerObjectName(ushort *,ulong,_ISOUTILOBJTYPE,ulong)
0x18004bbc2  mov     ebx, eax
0x18004bbc4  test    eax, eax
0x18004bbc6  js      loc_18004BCEF
0x18004bbcc  test    sil, sil
0x18004bbcf  jz      short loc_18004BC4D
0x18004bbd1  lea     rax, [rsp+298h+Name]
0x18004bbd6  xor     r9d, r9d; dwMaximumSizeHigh
0x18004bbd9  mov     [rsp+298h+lpName], rax; lpName
0x18004bbde  mov     r8d, ebp; flProtect
0x18004bbe1  xor     edx, edx; lpFileMappingAttributes
0x18004bbe3  mov     [rsp+298h+dwMaximumSizeLow], 0B05Ch; dwMaximumSizeLow
0x18004bbeb  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004bbef  call    cs:__imp_CreateFileMappingW
0x18004bbf6  nop     dword ptr [rax+rax+00h]
0x18004bbfb  mov     [rdi], rax
0x18004bbfe  mov     esi, 0B7h
0x18004bc03  test    rax, rax
0x18004bc06  jz      short loc_18004BC36
0x18004bc08  call    cs:__imp_GetLastError
0x18004bc0f  nop     dword ptr [rax+rax+00h]
0x18004bc14  cmp     eax, esi
0x18004bc16  jz      short loc_18004BC36
0x18004bc18  mov     rcx, [rdi]
0x18004bc1b  mov     edx, 2114Fh
0x18004bc20  mov     r8d, 0C0000002h
0x18004bc26  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18004bc2d  nop     dword ptr [rax+rax+00h]
0x18004bc32  mov     ebx, eax
0x18004bc34  jmp     short loc_18004BC66
0x18004bc36  call    cs:__imp_GetLastError
0x18004bc3d  nop     dword ptr [rax+rax+00h]
0x18004bc42  cmp     eax, esi
0x18004bc44  jnz     short loc_18004BC66
0x18004bc46  mov     ebx, 8000FFFFh
0x18004bc4b  jmp     short loc_18004BC66
0x18004bc4d  xor     edx, edx; bInheritHandle
0x18004bc4f  lea     r8, [rsp+298h+Name]; lpName
0x18004bc54  lea     ecx, [rdx+6]; dwDesiredAccess
0x18004bc57  call    cs:__imp_OpenFileMappingW
0x18004bc5e  nop     dword ptr [rax+rax+00h]
0x18004bc63  mov     [rdi], rax
0x18004bc66  cmp     qword ptr [rdi], 0
0x18004bc6a  jnz     short loc_18004BC87
0x18004bc6c  call    cs:__imp_GetLastError
0x18004bc73  nop     dword ptr [rax+rax+00h]
0x18004bc78  mov     ebx, eax
0x18004bc7a  test    eax, eax
0x18004bc7c  jle     short loc_18004BC87
0x18004bc7e  movzx   ebx, ax
0x18004bc81  or      ebx, 80070000h
0x18004bc87  test    ebx, ebx
0x18004bc89  js      short loc_18004BCEF
0x18004bc8b  mov     rcx, [rdi]; hFileMappingObject
0x18004bc8e  test    rcx, rcx
0x18004bc91  jz      loc_18004BD93
0x18004bc97  test    r12, r12
0x18004bc9a  jz      loc_18004BD93
0x18004bca0  xor     r9d, r9d; dwFileOffsetLow
0x18004bca3  mov     qword ptr [rsp+298h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18004bcac  xor     r8d, r8d; dwFileOffsetHigh
0x18004bcaf  lea     edx, [r9+2]; dwDesiredAccess
0x18004bcb3  call    cs:__imp_MapViewOfFile
0x18004bcba  nop     dword ptr [rax+rax+00h]
0x18004bcbf  mov     [r12], rax
0x18004bcc3  test    rax, rax
0x18004bcc6  jnz     loc_18004BD93
0x18004bccc  call    cs:__imp_GetLastError
0x18004bcd3  nop     dword ptr [rax+rax+00h]
0x18004bcd8  mov     ebx, eax
0x18004bcda  test    eax, eax
0x18004bcdc  jle     short loc_18004BCE7
0x18004bcde  movzx   ebx, ax
0x18004bce1  or      ebx, 80070000h
0x18004bce7  test    ebx, ebx
0x18004bce9  jns     loc_18004BD93
0x18004bcef  mov     rcx, [rsp+298h+var_268]
0x18004bcf4  test    rcx, rcx
0x18004bcf7  jnz     short loc_18004BD00
0x18004bcf9  jmp     short loc_18004BD14
0x18004bcfb  mov     rcx, [rsp+298h+var_268]
0x18004bd00  mov     rcx, [rcx]; hObject
0x18004bd03  test    rcx, rcx
0x18004bd06  jz      short loc_18004BD14
0x18004bd08  call    cs:__imp_CloseHandle
0x18004bd0f  nop     dword ptr [rax+rax+00h]
0x18004bd14  test    r15, r15
0x18004bd17  jz      short loc_18004BD2D
0x18004bd19  mov     rcx, [r15]; hObject
0x18004bd1c  test    rcx, rcx
0x18004bd1f  jz      short loc_18004BD2D
0x18004bd21  call    cs:__imp_CloseHandle
0x18004bd28  nop     dword ptr [rax+rax+00h]
0x18004bd2d  test    r13, r13
0x18004bd30  jz      short loc_18004BD47
0x18004bd32  mov     rcx, [r13+0]; hObject
0x18004bd36  test    rcx, rcx
0x18004bd39  jz      short loc_18004BD47
0x18004bd3b  call    cs:__imp_CloseHandle
0x18004bd42  nop     dword ptr [rax+rax+00h]
0x18004bd47  test    r14, r14
0x18004bd4a  jz      short loc_18004BD60
0x18004bd4c  mov     rcx, [r14]; hObject
0x18004bd4f  test    rcx, rcx
0x18004bd52  jz      short loc_18004BD60
0x18004bd54  call    cs:__imp_CloseHandle
0x18004bd5b  nop     dword ptr [rax+rax+00h]
0x18004bd60  test    r12, r12
0x18004bd63  jz      short loc_18004BD7A
0x18004bd65  mov     rcx, [r12]; lpBaseAddress
0x18004bd69  test    rcx, rcx
0x18004bd6c  jz      short loc_18004BD7A
0x18004bd6e  call    cs:__imp_UnmapViewOfFile
0x18004bd75  nop     dword ptr [rax+rax+00h]
0x18004bd7a  test    rdi, rdi
0x18004bd7d  jz      short loc_18004BD93
0x18004bd7f  mov     rcx, [rdi]; hObject
0x18004bd82  test    rcx, rcx
0x18004bd85  jz      short loc_18004BD93
0x18004bd87  call    cs:__imp_CloseHandle
0x18004bd8e  nop     dword ptr [rax+rax+00h]
0x18004bd93  mov     eax, ebx
0x18004bd95  mov     rcx, [rsp+298h+var_48]
0x18004bd9d  xor     rcx, rsp; StackCookie
0x18004bda0  call    __security_check_cookie
0x18004bda5  mov     rbx, [rsp+298h+arg_0]
0x18004bdad  add     rsp, 260h
0x18004bdb4  pop     r15
0x18004bdb6  pop     r14
0x18004bdb8  pop     r13
0x18004bdba  pop     r12
0x18004bdbc  pop     rdi
0x18004bdbd  pop     rsi
0x18004bdbe  pop     rbp
0x18004bdbf  retn
```
