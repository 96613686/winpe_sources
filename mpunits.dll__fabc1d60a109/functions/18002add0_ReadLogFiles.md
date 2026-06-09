# ReadLogFiles

- ea: `0x18002add0`
- end: `0x18002b209`
- name: `ReadLogFiles`
- size: `1081`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006e64`
- `0x1800077a0`
- `0x180007800`
- `0x180007ad0`
- `0x180007c80`
- `0x18000ab88`
- `0x18000abb8`
- `0x18000ae98`
- `0x18000af38`
- `0x18000b5bc`
- `0x180026940`
- `0x1800290f4`
- `0x1800291a8`
- `0x18002add0`
- `0x180043cd8`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!_close` at `0x18002aff2`
- `msvcrt!_close` at `0x18002b03f`
- `msvcrt!_close` at `0x18002b1b9`
- `msvcrt!_close` at `0x18002aff2`
- `msvcrt!_close` at `0x18002b03f`
- `msvcrt!_close` at `0x18002b1b9`
- `msvcrt!free` at `0x18002aef0`
- `msvcrt!free` at `0x18002af07`
- `msvcrt!free` at `0x18002aef0`
- `msvcrt!free` at `0x18002af07`
- `msvcrt!wcscpy_s` at `0x18002ae6f`
- `msvcrt!wcscpy_s` at `0x18002aeac`
- `msvcrt!wcscpy_s` at `0x18002ae6f`
- `msvcrt!wcscpy_s` at `0x18002aeac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002b15b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002b15b`

## string_xrefs

- `0x18002b14f`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall ReadLogFiles(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // r12
  unsigned int v3; // esi
  __int64 i; // r15
  errno_t v5; // r13d
  __int64 v6; // rax
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  char v11; // al
  __int64 v12; // rbx
  int v13; // ecx
  const wchar_t *v14; // rdx
  int v15; // ecx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  const wchar_t *v21; // rbx
  HMODULE ModuleHandleA; // rax
  int v23; // ecx
  char v24[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  void *v27; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR v29; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+70h] [rbp-90h] BYREF

  v1 = a1 + 152;
  v26 = 0;
  v27 = 0;
  v2 = EnableErrorDetails();
  v3 = ((__int64 (__fastcall *)(void **))ExecutionContext_ImpersonateIdentity)(&v27);
  if ( !v3 )
  {
    for ( i = *(_QWORD *)(*(_QWORD *)(v1 + 152) + 16LL); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
      {
        v15 = *(_DWORD *)(v1 + 4);
        if ( v15 != -1 )
        {
          _close(v15);
          *(_DWORD *)(v1 + 4) = -1;
          trace_BinLogWriter_ClosedLogFile();
        }
        RevertErrorDetails(v2);
        ((void (__fastcall *)(_QWORD))ObserverProtocol_PostCompleted)(*(_QWORD *)(v1 + 112));
        return ExecutionContext_RevertIdentity(v27);
      }
      v5 = wcscpy_s(Destination, 0x104u, *(const wchar_t **)(*(_QWORD *)(v1 + 152) + 8LL));
      if ( v5 )
      {
        trace_BinLogReader_FailedToCreateFileName();
        v21 = *(const wchar_t **)(*(_QWORD *)(v1 + 152) + 8LL);
        goto LABEL_42;
      }
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 152) + 8LL) + 2 * v6) );
      v5 = wcscpy_s(&Destination[v6], 260 - v6, *(const wchar_t **)i);
      if ( v5 )
      {
        trace_BinLogReader_FailedToCreateFileName();
        v21 = *(const wchar_t **)i;
LABEL_42:
        EventDescriptor = 0;
        ModuleHandleA = GetModuleHandleA("mpunits.dll");
        *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2007, v21);
        LOBYTE(EventDescriptor.Keyword) = 1;
        MI_ReportErrorDetails_ForCustomError(v5, (int)L"ERRNO", 0, 0);
        goto LABEL_43;
      }
      v3 = BinaryLogReader_Core_OpenFile(v1, Destination);
      if ( v3 )
      {
        RevertErrorDetails(v2);
        goto LABEL_43;
      }
      v7 = (*(_BYTE *)v1 & 1) == 0;
      v24[0] = 1;
      if ( v7 && *(_QWORD *)(v1 + 32) )
      {
        ((void (*)(void))HashMap_Destroy)();
        free(*(void **)(v1 + 32));
        v8 = *(_QWORD *)(v1 + 80);
        *(_QWORD *)(v1 + 32) = 0;
        HashMap_Destroy(v8);
        free(*(void **)(v1 + 80));
        *(_QWORD *)(v1 + 80) = 0;
      }
      v26 = 0;
      v3 = BinaryLogReader_Core_ValidateHeader(v1);
      if ( !v3 )
      {
        v25 = 0;
        v3 = BinaryLogReader_Core_ReadInstance(v1, &v25, v24);
        if ( v3 )
        {
          if ( v24[0] )
            goto LABEL_24;
LABEL_23:
          *(_DWORD *)&v29.Id = 208;
          *(_DWORD *)&v29.Level = 4;
          v29.Keyword = 1;
          Etw_Trace0(&v29, v9, v10);
          goto LABEL_24;
        }
        v11 = v24[0];
        if ( !v24[0] )
          goto LABEL_23;
        while ( v11 )
        {
          if ( *(_BYTE *)(v1 + 136) )
          {
            if ( v25 && *(_QWORD *)v25 )
              (*(void (**)(void))(*(_QWORD *)v25 + 16LL))();
            goto LABEL_37;
          }
          v12 = v25;
          MI_ObserverProtocol_PostNextBoxOrInstance(*(_QWORD *)(v1 + 112), v25);
          if ( v12 && *(_QWORD *)v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v25 = 0;
          v3 = BinaryLogReader_Core_ReadInstance(v1, &v25, v24);
          if ( v3 )
            break;
          v11 = v24[0];
        }
      }
LABEL_24:
      if ( v3 == 23 )
      {
LABEL_37:
        RevertErrorDetails(v2);
        *(_DWORD *)&EventDescriptor.Id = 211;
        *(_DWORD *)&EventDescriptor.Level = 4;
        EventDescriptor.Keyword = 1;
        Etw_Trace0(&EventDescriptor, v17, v18);
        return ExecutionContext_RevertIdentity(v27);
      }
      if ( v3 )
      {
        RevertErrorDetails(v2);
        *(_DWORD *)&EventDescriptor.Id = 212;
        *(_DWORD *)&EventDescriptor.Level = 4;
        EventDescriptor.Keyword = 1;
        Etw_Trace0(&EventDescriptor, v19, v20);
        goto LABEL_43;
      }
      v13 = *(_DWORD *)(v1 + 4);
      if ( v13 != -1 )
      {
        _close(v13);
        *(_DWORD *)(v1 + 4) = -1;
        trace_BinLogWriter_ClosedLogFile();
      }
      v14 = *(const wchar_t **)i;
      *(_DWORD *)&EventDescriptor.Id = 10202;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 1;
      Etw_Trace1_LPCWSTR(&EventDescriptor, (ULONGLONG)v14);
    }
  }
  CatchErrorDetails(v2, &v26);
LABEL_43:
  *(_BYTE *)(v1 + 136) = 1;
  v23 = *(_DWORD *)(v1 + 4);
  if ( v23 != -1 )
  {
    _close(v23);
    *(_DWORD *)(v1 + 4) = -1;
    trace_BinLogWriter_ClosedLogFile();
  }
  ((void (__fastcall *)(_QWORD, _QWORD, __int64))ObserverProtocol_PostError)(*(_QWORD *)(v1 + 112), v3, v26);
  if ( v26 && *(_QWORD *)v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return ExecutionContext_RevertIdentity(v27);
}

```

## disassembly

```asm
0x18002add0  mov     [rsp-8+arg_8], rbx
0x18002add5  mov     [rsp-8+arg_10], rsi
0x18002adda  push    rbp
0x18002addb  push    rdi
0x18002addc  push    r12
0x18002adde  push    r13
0x18002ade0  push    r15
0x18002ade2  lea     rbp, [rsp-190h]
0x18002adea  sub     rsp, 290h
0x18002adf1  mov     rax, cs:__security_cookie
0x18002adf8  xor     rax, rsp
0x18002adfb  mov     [rbp+1B0h+var_30], rax
0x18002ae02  xor     ebx, ebx
0x18002ae04  lea     rdi, [rcx+98h]
0x18002ae0b  mov     [rsp+2B0h+var_270], rbx
0x18002ae10  mov     [rsp+2B0h+var_268], rbx
0x18002ae15  call    EnableErrorDetails
0x18002ae1a  mov     rcx, cs:off_180047C30
0x18002ae21  mov     r12, rax
0x18002ae24  mov     rax, [rcx+50h]
0x18002ae28  lea     rcx, [rsp+2B0h+var_268]
0x18002ae2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae32  mov     esi, eax
0x18002ae34  test    eax, eax
0x18002ae36  jz      short loc_18002AE4A
0x18002ae38  lea     rdx, [rsp+2B0h+var_270]
0x18002ae3d  mov     rcx, r12
0x18002ae40  call    CatchErrorDetails
0x18002ae45  jmp     loc_18002B1AA
0x18002ae4a  mov     rax, [rdi+98h]
0x18002ae51  mov     r15, [rax+10h]
0x18002ae55  jmp     loc_18002B02E
0x18002ae5a  mov     r8, [rdi+98h]
0x18002ae61  lea     rcx, [rsp+2B0h+Destination]; Destination
0x18002ae66  mov     edx, 104h; SizeInWords
0x18002ae6b  mov     r8, [r8+8]; Source
0x18002ae6f  call    cs:__imp_wcscpy_s
0x18002ae75  mov     r13d, eax
0x18002ae78  test    eax, eax
0x18002ae7a  jnz     loc_18002B13C
0x18002ae80  mov     rax, [rdi+98h]
0x18002ae87  mov     rcx, [rax+8]
0x18002ae8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ae8f  inc     rax
0x18002ae92  cmp     [rcx+rax*2], bx
0x18002ae96  jnz     short loc_18002AE8F
0x18002ae98  mov     r8, [r15]; Source
0x18002ae9b  lea     rcx, [rsp+2B0h+Destination]
0x18002aea0  mov     edx, 104h
0x18002aea5  lea     rcx, [rcx+rax*2]; Destination
0x18002aea9  sub     rdx, rax; SizeInWords
0x18002aeac  call    cs:__imp_wcscpy_s
0x18002aeb2  mov     r13d, eax
0x18002aeb5  test    eax, eax
0x18002aeb7  jnz     loc_18002B132
0x18002aebd  lea     rdx, [rsp+2B0h+Destination]
0x18002aec2  mov     rcx, rdi
0x18002aec5  call    BinaryLogReader_Core_OpenFile
0x18002aeca  mov     esi, eax
0x18002aecc  test    eax, eax
0x18002aece  jnz     loc_18002B128
0x18002aed4  test    byte ptr [rdi], 1
0x18002aed7  mov     [rsp+2B0h+var_280], 1
0x18002aedc  jnz     short loc_18002AF11
0x18002aede  mov     rcx, [rdi+20h]
0x18002aee2  test    rcx, rcx
0x18002aee5  jz      short loc_18002AF11
0x18002aee7  call    HashMap_Destroy
0x18002aeec  mov     rcx, [rdi+20h]; Block
0x18002aef0  call    cs:__imp_free
0x18002aef6  mov     rcx, [rdi+50h]
0x18002aefa  mov     [rdi+20h], rbx
0x18002aefe  call    HashMap_Destroy
0x18002af03  mov     rcx, [rdi+50h]; Block
0x18002af07  call    cs:__imp_free
0x18002af0d  mov     [rdi+50h], rbx
0x18002af11  mov     rcx, rdi
0x18002af14  mov     [rsp+2B0h+var_270], rbx
0x18002af19  call    BinaryLogReader_Core_ValidateHeader
0x18002af1e  mov     esi, eax
0x18002af20  test    eax, eax
0x18002af22  jnz     loc_18002AFD9
0x18002af28  lea     r8, [rsp+2B0h+var_280]
0x18002af2d  mov     [rsp+2B0h+var_278], rbx
0x18002af32  lea     rdx, [rsp+2B0h+var_278]
0x18002af37  mov     rcx, rdi
0x18002af3a  call    BinaryLogReader_Core_ReadInstance
0x18002af3f  mov     esi, eax
0x18002af41  test    eax, eax
0x18002af43  jnz     short loc_18002AFB0
0x18002af45  mov     al, [rsp+2B0h+var_280]
0x18002af49  test    al, al
0x18002af4b  jz      short loc_18002AFB6
0x18002af4d  test    al, al
0x18002af4f  jz      loc_18002AFD9
0x18002af55  cmp     [rdi+88h], bl
0x18002af5b  jnz     loc_18002B0AD
0x18002af61  mov     rbx, [rsp+2B0h+var_278]
0x18002af66  mov     rcx, [rdi+70h]
0x18002af6a  mov     rdx, rbx
0x18002af6d  call    MI_ObserverProtocol_PostNextBoxOrInstance
0x18002af72  test    rbx, rbx
0x18002af75  jz      short loc_18002AF8B
0x18002af77  mov     rax, [rbx]
0x18002af7a  test    rax, rax
0x18002af7d  jz      short loc_18002AF8B
0x18002af7f  mov     rax, [rax+10h]
0x18002af83  mov     rcx, rbx
0x18002af86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af8b  xor     ebx, ebx
0x18002af8d  lea     r8, [rsp+2B0h+var_280]
0x18002af92  lea     rdx, [rsp+2B0h+var_278]
0x18002af97  mov     [rsp+2B0h+var_278], rbx
0x18002af9c  mov     rcx, rdi
0x18002af9f  call    BinaryLogReader_Core_ReadInstance
0x18002afa4  mov     esi, eax
0x18002afa6  test    eax, eax
0x18002afa8  jnz     short loc_18002AFD9
0x18002afaa  mov     al, [rsp+2B0h+var_280]
0x18002afae  jmp     short loc_18002AF4D
0x18002afb0  cmp     [rsp+2B0h+var_280], bl
0x18002afb4  jnz     short loc_18002AFD9
0x18002afb6  lea     rcx, [rsp+2B0h+var_250]
0x18002afbb  mov     [rsp+2B0h+var_250], 0D0h
0x18002afc3  mov     [rsp+2B0h+var_24C], 4
0x18002afcb  mov     [rsp+2B0h+var_248], 1
0x18002afd4  call    Etw_Trace0
0x18002afd9  cmp     esi, 17h
0x18002afdc  jz      loc_18002B0C8
0x18002afe2  test    esi, esi
0x18002afe4  jnz     loc_18002B0F8
0x18002afea  mov     ecx, [rdi+4]; FileHandle
0x18002afed  cmp     ecx, 0FFFFFFFFh
0x18002aff0  jz      short loc_18002B004
0x18002aff2  call    cs:__imp__close
0x18002aff8  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x18002afff  call    trace_BinLogWriter_ClosedLogFile
0x18002b004  mov     rdx, [r15]
0x18002b007  lea     rcx, [rsp+2B0h+EventDescriptor]; EventDescriptor
0x18002b00c  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 27DAh
0x18002b014  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], 4
0x18002b01c  mov     [rsp+2B0h+EventDescriptor.Keyword], 1
0x18002b025  call    Etw_Trace1_LPCWSTR
0x18002b02a  mov     r15, [r15+8]
0x18002b02e  test    r15, r15
0x18002b031  jnz     loc_18002AE5A
0x18002b037  mov     ecx, [rdi+4]; FileHandle
0x18002b03a  cmp     ecx, 0FFFFFFFFh
0x18002b03d  jz      short loc_18002B051
0x18002b03f  call    cs:__imp__close
0x18002b045  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x18002b04c  call    trace_BinLogWriter_ClosedLogFile
0x18002b051  mov     rcx, r12
0x18002b054  call    RevertErrorDetails
0x18002b059  mov     rax, cs:off_180047BB0
0x18002b060  mov     rcx, [rdi+70h]
0x18002b064  mov     rax, [rax+30h]
0x18002b068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b06d  mov     rax, cs:off_180047C30
0x18002b074  mov     rcx, [rsp+2B0h+var_268]
0x18002b079  mov     rax, [rax+58h]
0x18002b07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b082  mov     rcx, [rbp+1B0h+var_30]
0x18002b089  xor     rcx, rsp; StackCookie
0x18002b08c  call    __security_check_cookie
0x18002b091  lea     r11, [rsp+2B0h+var_20]
0x18002b099  mov     rbx, [r11+38h]
0x18002b09d  mov     rsi, [r11+40h]
0x18002b0a1  mov     rsp, r11
0x18002b0a4  pop     r15
0x18002b0a6  pop     r13
0x18002b0a8  pop     r12
0x18002b0aa  pop     rdi
0x18002b0ab  pop     rbp
0x18002b0ac  retn
0x18002b0ad  mov     rcx, [rsp+2B0h+var_278]
0x18002b0b2  test    rcx, rcx
0x18002b0b5  jz      short loc_18002B0C8
0x18002b0b7  mov     rax, [rcx]
0x18002b0ba  test    rax, rax
0x18002b0bd  jz      short loc_18002B0C8
0x18002b0bf  mov     rax, [rax+10h]
0x18002b0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0c8  mov     rcx, r12
0x18002b0cb  call    RevertErrorDetails
0x18002b0d0  lea     rcx, [rsp+2B0h+EventDescriptor]
0x18002b0d5  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0D3h
0x18002b0dd  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], 4
0x18002b0e5  mov     [rsp+2B0h+EventDescriptor.Keyword], 1
0x18002b0ee  call    Etw_Trace0
0x18002b0f3  jmp     loc_18002B06D
0x18002b0f8  mov     rcx, r12
0x18002b0fb  call    RevertErrorDetails
0x18002b100  lea     rcx, [rsp+2B0h+EventDescriptor]
0x18002b105  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0D4h
0x18002b10d  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], 4
0x18002b115  mov     [rsp+2B0h+EventDescriptor.Keyword], 1
0x18002b11e  call    Etw_Trace0
0x18002b123  jmp     loc_18002B1AA
0x18002b128  mov     rcx, r12
0x18002b12b  call    RevertErrorDetails
0x18002b130  jmp     short loc_18002B1AA
0x18002b132  call    trace_BinLogReader_FailedToCreateFileName
0x18002b137  mov     rbx, [r15]
0x18002b13a  jmp     short loc_18002B14C
0x18002b13c  call    trace_BinLogReader_FailedToCreateFileName
0x18002b141  mov     rax, [rdi+98h]
0x18002b148  mov     rbx, [rax+8]
0x18002b14c  xorps   xmm0, xmm0
0x18002b14f  lea     rcx, ModuleName; "mpunits.dll"
0x18002b156  movups  xmmword ptr [rsp+2B0h+EventDescriptor.Id], xmm0
0x18002b15b  call    cs:__imp_GetModuleHandleA
0x18002b161  mov     r8, rbx
0x18002b164  mov     edx, 7D7h
0x18002b169  mov     rcx, rax
0x18002b16c  call    _Intlstr_FormatString_FormatMessage
0x18002b171  xor     ebx, ebx
0x18002b173  mov     qword ptr [rsp+2B0h+EventDescriptor.Id], rax
0x18002b178  mov     byte ptr [rsp+2B0h+EventDescriptor.Keyword], 1
0x18002b17d  lea     r9, [rsp+2B0h+EventDescriptor]
0x18002b182  movaps  xmm0, xmmword ptr [rsp+2B0h+EventDescriptor.Id]
0x18002b187  lea     rdx, aErrno; "ERRNO"
0x18002b18e  mov     [rsp+2B0h+var_288], rbx; __int64
0x18002b193  mov     ecx, r13d; int
0x18002b196  lea     r8d, [rbx+5]
0x18002b19a  mov     [rsp+2B0h+var_290], rbx; __int64
0x18002b19f  movdqa  xmmword ptr [rsp+2B0h+EventDescriptor.Id], xmm0
0x18002b1a5  call    MI_ReportErrorDetails_ForCustomError
0x18002b1aa  mov     byte ptr [rdi+88h], 1
0x18002b1b1  mov     ecx, [rdi+4]; FileHandle
0x18002b1b4  cmp     ecx, 0FFFFFFFFh
0x18002b1b7  jz      short loc_18002B1CB
0x18002b1b9  call    cs:__imp__close
0x18002b1bf  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x18002b1c6  call    trace_BinLogWriter_ClosedLogFile
0x18002b1cb  mov     rax, cs:off_180047BB0
0x18002b1d2  mov     edx, esi
0x18002b1d4  mov     r8, [rsp+2B0h+var_270]
0x18002b1d9  mov     rcx, [rdi+70h]
0x18002b1dd  mov     rax, [rax+50h]
0x18002b1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1e6  mov     rcx, [rsp+2B0h+var_270]
0x18002b1eb  test    rcx, rcx
0x18002b1ee  jz      loc_18002B06D
0x18002b1f4  mov     rax, [rcx]
0x18002b1f7  test    rax, rax
0x18002b1fa  jz      loc_18002B06D
0x18002b200  mov     rax, [rax+10h]
0x18002b204  jmp     loc_18002B068
```
