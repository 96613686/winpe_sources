# CActiveXInstallBroker::STARegisterDllFile2(ushort *,ushort *,int,int)

- ea: `0x140005e98`
- end: `0x140005ff5`
- name: `?STARegisterDllFile2@CActiveXInstallBroker@@AEAAJPEAG0HH@Z`
- size: `349`
- prototype: `int(CActiveXInstallBroker *__hidden this, unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005108`

## callees

- `0x140003978`
- `0x1400039bc`
- `0x140005e98`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140005f93`
- `KERNEL32!CloseHandle` at `0x140005f93`
- `KERNEL32!CreateThread` at `0x140005f34`
- `KERNEL32!CreateThread` at `0x140005f34`
- `KERNEL32!GetExitCodeThread` at `0x140005f84`
- `KERNEL32!GetExitCodeThread` at `0x140005f84`
- `KERNEL32!GetLastError` at `0x140005f5e`
- `KERNEL32!GetLastError` at `0x140005fa1`
- `KERNEL32!GetLastError` at `0x140005f5e`
- `KERNEL32!GetLastError` at `0x140005fa1`
- `KERNEL32!WaitForSingleObject` at `0x140005f4e`
- `KERNEL32!WaitForSingleObject` at `0x140005f4e`
- `OLEAUT32!__imp_SysAllocString` at `0x140005ed0`
- `OLEAUT32!__imp_SysAllocString` at `0x140005eec`
- `OLEAUT32!__imp_SysAllocString` at `0x140005ed0`
- `OLEAUT32!__imp_SysAllocString` at `0x140005eec`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fc1`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fd1`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fc1`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fd1`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::STARegisterDllFile2(
        OLECHAR *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        int a5)
{
  BSTR *v9; // rbx
  BSTR v10; // rax
  BSTR v11; // rax
  HANDLE Thread; // rax
  void *v13; // rdi
  int LastError; // eax
  int v15; // eax
  DWORD ExitCode[14]; // [rsp+30h] [rbp-38h] BYREF

  ExitCode[0] = -2147024882;
  v9 = (BSTR *)operator new(0x20u);
  if ( v9 )
  {
    v10 = SysAllocString(a2);
    v9[1] = v10;
    if ( v10 )
    {
      v11 = SysAllocString(a3);
      v9[2] = v11;
      if ( v11 )
      {
        *((_DWORD *)v9 + 7) = a5;
        *v9 = this;
        *((_DWORD *)v9 + 6) = a4;
        Thread = CreateThread(0, 0, CActiveXInstallBroker::RegisterDllFile2ThreadProc, v9, 0, 0);
        v13 = Thread;
        if ( Thread )
        {
          if ( WaitForSingleObject(Thread, 0xFFFFFFFF) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            ExitCode[0] = LastError;
          }
          else
          {
            GetExitCodeThread(v13, ExitCode);
          }
          CloseHandle(v13);
        }
        else
        {
          v15 = GetLastError();
          if ( v15 > 0 )
            v15 = (unsigned __int16)v15 | 0x80070000;
          ExitCode[0] = v15;
        }
        SysFreeString(v9[2]);
      }
      SysFreeString(v9[1]);
    }
    operator delete(v9);
  }
  return ExitCode[0];
}

```

## disassembly

```asm
0x140005e98  push    rbx
0x140005e9a  push    rbp
0x140005e9b  push    rsi
0x140005e9c  push    rdi
0x140005e9d  push    r14
0x140005e9f  sub     rsp, 40h
0x140005ea3  mov     r14, rcx
0x140005ea6  mov     [rsp+68h+ExitCode], 8007000Eh
0x140005eae  mov     ecx, 20h ; ' '; dwBytes
0x140005eb3  mov     ebp, r9d
0x140005eb6  mov     rsi, r8
0x140005eb9  mov     rdi, rdx
0x140005ebc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005ec1  mov     rbx, rax
0x140005ec4  test    rax, rax
0x140005ec7  jz      loc_140005FE5
0x140005ecd  mov     rcx, rdi; psz
0x140005ed0  call    cs:__imp_SysAllocString
0x140005ed7  nop     dword ptr [rax+rax+00h]
0x140005edc  mov     [rbx+8], rax
0x140005ee0  test    rax, rax
0x140005ee3  jz      loc_140005FDD
0x140005ee9  mov     rcx, rsi; psz
0x140005eec  call    cs:__imp_SysAllocString
0x140005ef3  nop     dword ptr [rax+rax+00h]
0x140005ef8  mov     [rbx+10h], rax
0x140005efc  test    rax, rax
0x140005eff  jz      loc_140005FCD
0x140005f05  mov     eax, [rsp+68h+arg_20]
0x140005f0c  lea     r8, ?RegisterDllFile2ThreadProc@CActiveXInstallBroker@@CAKPEAX@Z; lpStartAddress
0x140005f13  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x140005f1c  mov     r9, rbx; lpParameter
0x140005f1f  xor     edx, edx; dwStackSize
0x140005f21  mov     [rbx+1Ch], eax
0x140005f24  xor     ecx, ecx; lpThreadAttributes
0x140005f26  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x140005f2e  mov     [rbx], r14
0x140005f31  mov     [rbx+18h], ebp
0x140005f34  call    cs:__imp_CreateThread
0x140005f3b  nop     dword ptr [rax+rax+00h]
0x140005f40  mov     rdi, rax
0x140005f43  test    rax, rax
0x140005f46  jz      short loc_140005FA1
0x140005f48  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005f4b  mov     rcx, rax; hHandle
0x140005f4e  call    cs:__imp_WaitForSingleObject
0x140005f55  nop     dword ptr [rax+rax+00h]
0x140005f5a  test    eax, eax
0x140005f5c  jz      short loc_140005F7C
0x140005f5e  call    cs:__imp_GetLastError
0x140005f65  nop     dword ptr [rax+rax+00h]
0x140005f6a  test    eax, eax
0x140005f6c  jle     short loc_140005F76
0x140005f6e  movzx   eax, ax
0x140005f71  or      eax, 80070000h
0x140005f76  mov     [rsp+68h+ExitCode], eax
0x140005f7a  jmp     short loc_140005F90
0x140005f7c  lea     rdx, [rsp+68h+ExitCode]; lpExitCode
0x140005f81  mov     rcx, rdi; hThread
0x140005f84  call    cs:__imp_GetExitCodeThread
0x140005f8b  nop     dword ptr [rax+rax+00h]
0x140005f90  mov     rcx, rdi; hObject
0x140005f93  call    cs:__imp_CloseHandle
0x140005f9a  nop     dword ptr [rax+rax+00h]
0x140005f9f  jmp     short loc_140005FBD
0x140005fa1  call    cs:__imp_GetLastError
0x140005fa8  nop     dword ptr [rax+rax+00h]
0x140005fad  test    eax, eax
0x140005faf  jle     short loc_140005FB9
0x140005fb1  movzx   eax, ax
0x140005fb4  or      eax, 80070000h
0x140005fb9  mov     [rsp+68h+ExitCode], eax
0x140005fbd  mov     rcx, [rbx+10h]; bstrString
0x140005fc1  call    cs:__imp_SysFreeString
0x140005fc8  nop     dword ptr [rax+rax+00h]
0x140005fcd  mov     rcx, [rbx+8]; bstrString
0x140005fd1  call    cs:__imp_SysFreeString
0x140005fd8  nop     dword ptr [rax+rax+00h]
0x140005fdd  mov     rcx, rbx; lpMem
0x140005fe0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140005fe5  mov     eax, [rsp+68h+ExitCode]
0x140005fe9  add     rsp, 40h
0x140005fed  pop     r14
0x140005fef  pop     rdi
0x140005ff0  pop     rsi
0x140005ff1  pop     rbp
0x140005ff2  pop     rbx
0x140005ff3  retn
```
