# CreateTemporarySessionFile(void)

- ea: `0x140040b14`
- end: `0x140040d4a`
- name: `?CreateTemporarySessionFile@@YAJXZ`
- size: `566`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000859c`

## callees

- `0x140006fe0`
- `0x14000706c`
- `0x140020420`
- `0x140040a40`
- `0x140040b14`
- `0x1400418a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140040c91`
- `KERNEL32!GetLastError` at `0x140040c91`
- `KERNEL32!HeapAlloc` at `0x140040b4d`
- `KERNEL32!HeapAlloc` at `0x140040b8d`
- `KERNEL32!HeapAlloc` at `0x140040b4d`
- `KERNEL32!HeapAlloc` at `0x140040b8d`
- `KERNEL32!HeapFree` at `0x140040d06`
- `KERNEL32!HeapFree` at `0x140040d2b`
- `KERNEL32!HeapFree` at `0x140040d06`
- `KERNEL32!HeapFree` at `0x140040d2b`
- `KERNEL32!GetProcessHeap` at `0x140040b34`
- `KERNEL32!GetProcessHeap` at `0x140040b79`
- `KERNEL32!GetProcessHeap` at `0x140040cf2`
- `KERNEL32!GetProcessHeap` at `0x140040d17`
- `KERNEL32!GetProcessHeap` at `0x140040b34`
- `KERNEL32!GetProcessHeap` at `0x140040b79`
- `KERNEL32!GetProcessHeap` at `0x140040cf2`
- `KERNEL32!GetProcessHeap` at `0x140040d17`
- `KERNEL32!CreateFileW` at `0x140040c69`
- `KERNEL32!CreateFileW` at `0x140040c69`
- `KERNEL32!LocalFree` at `0x140040cd8`
- `KERNEL32!LocalFree` at `0x140040cd8`

## string_xrefs

- `0x140040cb6`: `CreateTemporarySessionFile`

## pseudocode

```c
__int64 CreateTemporarySessionFile(void)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v1; // rsi
  unsigned __int16 *v2; // rdi
  unsigned int v3; // ebx
  HANDLE v4; // rax
  int v5; // eax
  int v6; // eax
  unsigned __int64 v7; // r11
  int v8; // eax
  int v9; // eax
  char *v10; // rax
  signed int LastError; // eax
  HANDLE v12; // rax
  HANDLE v13; // rax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-28h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  ProcessHeap = GetProcessHeap();
  v1 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( v1 )
  {
    v4 = GetProcessHeap();
    v2 = (unsigned __int16 *)HeapAlloc(v4, 0, 0x208u);
    if ( v2 )
    {
      v5 = NewSessionTemporaryPath(v1);
      v3 = v5;
      if ( v5 >= 0 )
      {
        v6 = StringCchCopyW(v2, 0x104u, v1);
        v3 = v6;
        if ( v6 >= 0 )
        {
          v8 = StringCchCatW(v1, v7, L"inuse");
          v3 = v8;
          if ( v8 >= 0 )
          {
            v9 = CreateSecurityDescriptor(&SecurityAttributes);
            v3 = v9;
            if ( v9 >= 0 )
            {
              v10 = (char *)CreateFileW(v1, 0xC0000000, 0, &SecurityAttributes, 1u, 1u, 0);
              if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
              {
                LastError = GetLastError();
                v3 = LastError;
                if ( LastError > 0 )
                  v3 = (unsigned __int16)LastError | 0x80070000;
                SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateTemporarySessionFile", 422, v3);
              }
              else
              {
                g_TempDirectoryPath = v2;
                v2 = 0;
                g_FileHandle = v10;
              }
            }
            else
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateTemporarySessionFile", 409, v9);
            }
          }
          else
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateTemporarySessionFile", 406, v8);
          }
        }
        else
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateTemporarySessionFile", 403, v6);
        }
      }
      else
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateTemporarySessionFile", 400, v5);
      }
    }
    else
    {
      v3 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateTemporarySessionFile", 394, -2147024882);
    }
  }
  else
  {
    v2 = 0;
    v3 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateTemporarySessionFile", 393, -2147024882);
  }
  if ( SecurityAttributes.lpSecurityDescriptor )
  {
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
    SecurityAttributes.lpSecurityDescriptor = 0;
  }
  if ( v1 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v1);
  }
  if ( v2 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x140040b14  mov     rax, rsp
0x140040b17  mov     [rax+8], rbx
0x140040b1b  mov     [rax+10h], rsi
0x140040b1f  push    rdi
0x140040b20  sub     rsp, 60h
0x140040b24  xorps   xmm0, xmm0
0x140040b27  mov     qword ptr [rax-28h], 0
0x140040b2f  movdqu  xmmword ptr [rax-20h], xmm0
0x140040b34  call    cs:__imp_GetProcessHeap
0x140040b3b  nop     dword ptr [rax+rax+00h]
0x140040b40  mov     ebx, 208h
0x140040b45  xor     edx, edx; dwFlags
0x140040b47  mov     rcx, rax; hHeap
0x140040b4a  mov     r8d, ebx; dwBytes
0x140040b4d  call    cs:__imp_HeapAlloc
0x140040b54  nop     dword ptr [rax+rax+00h]
0x140040b59  mov     rsi, rax
0x140040b5c  test    rax, rax
0x140040b5f  jnz     short loc_140040B79
0x140040b61  mov     eax, 8007000Eh
0x140040b66  xor     edi, edi
0x140040b68  mov     ebx, eax
0x140040b6a  mov     [rsp+68h+dwCreationDisposition], eax
0x140040b6e  mov     r9d, 189h
0x140040b74  jmp     loc_140040CB6
0x140040b79  call    cs:__imp_GetProcessHeap
0x140040b80  nop     dword ptr [rax+rax+00h]
0x140040b85  mov     r8, rbx; dwBytes
0x140040b88  xor     edx, edx; dwFlags
0x140040b8a  mov     rcx, rax; hHeap
0x140040b8d  call    cs:__imp_HeapAlloc
0x140040b94  nop     dword ptr [rax+rax+00h]
0x140040b99  mov     rdi, rax
0x140040b9c  test    rax, rax
0x140040b9f  jnz     short loc_140040BB7
0x140040ba1  mov     eax, 8007000Eh
0x140040ba6  mov     r9d, 18Ah
0x140040bac  mov     ebx, eax
0x140040bae  mov     [rsp+68h+dwCreationDisposition], eax
0x140040bb2  jmp     loc_140040CB6
0x140040bb7  mov     rcx, rsi; lpSrc
0x140040bba  call    ?NewSessionTemporaryPath@@YAJPEAG_K@Z; NewSessionTemporaryPath(ushort *,unsigned __int64)
0x140040bbf  mov     ebx, eax
0x140040bc1  test    eax, eax
0x140040bc3  jns     short loc_140040BD4
0x140040bc5  mov     [rsp+68h+dwCreationDisposition], eax
0x140040bc9  mov     r9d, 190h
0x140040bcf  jmp     loc_140040CB6
0x140040bd4  mov     r11d, 104h
0x140040bda  mov     r8, rsi; unsigned __int16 *
0x140040bdd  mov     edx, r11d; unsigned __int64
0x140040be0  mov     rcx, rdi; unsigned __int16 *
0x140040be3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140040be8  mov     ebx, eax
0x140040bea  test    eax, eax
0x140040bec  jns     short loc_140040BFD
0x140040bee  mov     [rsp+68h+dwCreationDisposition], eax
0x140040bf2  mov     r9d, 193h
0x140040bf8  jmp     loc_140040CB6
0x140040bfd  lea     r8, aInuse; "inuse"
0x140040c04  mov     rdx, r11; unsigned __int64
0x140040c07  mov     rcx, rsi; unsigned __int16 *
0x140040c0a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140040c0f  mov     ebx, eax
0x140040c11  test    eax, eax
0x140040c13  jns     short loc_140040C24
0x140040c15  mov     [rsp+68h+dwCreationDisposition], eax
0x140040c19  mov     r9d, 196h
0x140040c1f  jmp     loc_140040CB6
0x140040c24  lea     rcx, [rsp+68h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x140040c29  call    ?CreateSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z; CreateSecurityDescriptor(_SECURITY_ATTRIBUTES *)
0x140040c2e  mov     ebx, eax
0x140040c30  test    eax, eax
0x140040c32  jns     short loc_140040C40
0x140040c34  mov     [rsp+68h+dwCreationDisposition], eax
0x140040c38  mov     r9d, 199h
0x140040c3e  jmp     short loc_140040CB6
0x140040c40  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x140040c49  lea     r9, [rsp+68h+SecurityAttributes]; lpSecurityAttributes
0x140040c4e  mov     [rsp+68h+dwFlagsAndAttributes], 1; dwFlagsAndAttributes
0x140040c56  xor     r8d, r8d; dwShareMode
0x140040c59  mov     edx, 0C0000000h; dwDesiredAccess
0x140040c5e  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x140040c66  mov     rcx, rsi; lpFileName
0x140040c69  call    cs:__imp_CreateFileW
0x140040c70  nop     dword ptr [rax+rax+00h]
0x140040c75  lea     rcx, [rax-1]
0x140040c79  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140040c7d  ja      short loc_140040C91
0x140040c7f  mov     cs:?g_TempDirectoryPath@@3PEAGEA, rdi; ushort * g_TempDirectoryPath
0x140040c86  xor     edi, edi
0x140040c88  mov     cs:?g_FileHandle@@3PEAXEA, rax; void * g_FileHandle
0x140040c8f  jmp     short loc_140040CCE
0x140040c91  call    cs:__imp_GetLastError
0x140040c98  nop     dword ptr [rax+rax+00h]
0x140040c9d  mov     ebx, eax
0x140040c9f  test    eax, eax
0x140040ca1  jle     short loc_140040CAC
0x140040ca3  movzx   ebx, ax
0x140040ca6  or      ebx, 80070000h
0x140040cac  mov     [rsp+68h+dwCreationDisposition], ebx
0x140040cb0  mov     r9d, 1A6h
0x140040cb6  lea     r8, aCreatetemporar; "CreateTemporarySessionFile"
0x140040cbd  mov     ecx, 1; Level
0x140040cc2  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140040cc9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040cce  mov     rcx, [rsp+68h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x140040cd3  test    rcx, rcx
0x140040cd6  jz      short loc_140040CED
0x140040cd8  call    cs:__imp_LocalFree
0x140040cdf  nop     dword ptr [rax+rax+00h]
0x140040ce4  mov     [rsp+68h+SecurityAttributes.lpSecurityDescriptor], 0
0x140040ced  test    rsi, rsi
0x140040cf0  jz      short loc_140040D12
0x140040cf2  call    cs:__imp_GetProcessHeap
0x140040cf9  nop     dword ptr [rax+rax+00h]
0x140040cfe  mov     r8, rsi; lpMem
0x140040d01  xor     edx, edx; dwFlags
0x140040d03  mov     rcx, rax; hHeap
0x140040d06  call    cs:__imp_HeapFree
0x140040d0d  nop     dword ptr [rax+rax+00h]
0x140040d12  test    rdi, rdi
0x140040d15  jz      short loc_140040D37
0x140040d17  call    cs:__imp_GetProcessHeap
0x140040d1e  nop     dword ptr [rax+rax+00h]
0x140040d23  mov     r8, rdi; lpMem
0x140040d26  xor     edx, edx; dwFlags
0x140040d28  mov     rcx, rax; hHeap
0x140040d2b  call    cs:__imp_HeapFree
0x140040d32  nop     dword ptr [rax+rax+00h]
0x140040d37  mov     rsi, [rsp+68h+arg_8]
0x140040d3c  mov     eax, ebx
0x140040d3e  mov     rbx, [rsp+68h+arg_0]
0x140040d43  add     rsp, 60h
0x140040d47  pop     rdi
0x140040d48  retn
```
