# CDfMutex::Init(CGlobalContext *,int)

- ea: `0x18001fbb4`
- end: `0x18001fcff`
- name: `?Init@CDfMutex@@QEAAJPEAVCGlobalContext@@H@Z`
- size: `331`
- prototype: `__int64 __fastcall(CDfMutex *__hidden this, struct CGlobalContext *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020178`
- `0x18003b588`
- `0x1800405dc`
- `0x18004ca84`

## callees

- `0x18001fbb4`
- `0x18001fd08`
- `0x180020044`
- `0x180042800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcde`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001fcb4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001fcb4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fc41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fcf7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fc41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fcf7`

## pseudocode

```c
__int64 __fastcall CDfMutex::Init(CDfMutex *this, struct CGlobalContext *a2, int a3)
{
  int v6; // ebx
  HANDLE v7; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  _BYTE v11[440]; // [rsp+30h] [rbp-238h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+1E8h] [rbp-80h] BYREF
  WCHAR Name[32]; // [rsp+200h] [rbp-68h] BYREF

  if ( !a2 )
    return (unsigned int)-2147287031;
  v6 = StringCchPrintfW(Name, 0x20u, L"OleDfRoot%X%08lX", *((unsigned int *)a2 + 15), *((_DWORD *)a2 + 14));
  if ( v6 >= 0 )
  {
    if ( a3 )
    {
      v6 = CSharedMemoryMarshalingSecurityDescriptor::Init((CSharedMemoryMarshalingSecurityDescriptor *)v11, 0x1F0003u);
      if ( v6 < 0 )
        return (unsigned int)v6;
      v7 = CreateEventW(&EventAttributes, 0, 0, Name);
      *((_QWORD *)this + 1) = v7;
      if ( v7 || GetLastError() != 5 )
        goto LABEL_6;
      EventW = CreateEventW(0, 0, 0, 0);
    }
    else
    {
      EventW = OpenEventW(0x100002u, 0, Name);
    }
    *((_QWORD *)this + 1) = EventW;
LABEL_6:
    if ( *((_QWORD *)this + 1) )
    {
      *(_QWORD *)this = (char *)a2 + 64;
      if ( a3 )
      {
        *((_DWORD *)a2 + 16) = -1;
        *(_DWORD *)(*(_QWORD *)this + 4LL) = 0;
        *(_DWORD *)(*(_QWORD *)this + 8LL) = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001fbb4  mov     r11, rsp
0x18001fbb7  mov     [r11+18h], rbx
0x18001fbbb  push    rbp
0x18001fbbc  push    rsi
0x18001fbbd  push    rdi
0x18001fbbe  sub     rsp, 250h
0x18001fbc5  mov     rax, cs:__security_cookie
0x18001fbcc  xor     rax, rsp
0x18001fbcf  mov     [rsp+268h+var_28], rax
0x18001fbd7  mov     ebp, r8d
0x18001fbda  mov     rsi, rdx
0x18001fbdd  mov     rdi, rcx
0x18001fbe0  test    rdx, rdx
0x18001fbe3  jz      loc_18001FCD7
0x18001fbe9  mov     eax, [rdx+38h]
0x18001fbec  lea     r8, aOledfrootX08lx; "OleDfRoot%X%08lX"
0x18001fbf3  mov     r9d, [rdx+3Ch]
0x18001fbf7  lea     rcx, [r11-68h]; unsigned __int16 *
0x18001fbfb  mov     edx, 20h ; ' '; unsigned __int64
0x18001fc00  mov     [rsp+268h+var_248], eax
0x18001fc04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fc09  mov     ebx, eax
0x18001fc0b  test    eax, eax
0x18001fc0d  js      short loc_18001FC80
0x18001fc0f  test    ebp, ebp
0x18001fc11  jz      loc_18001FCA5
0x18001fc17  mov     edx, 1F0003h; AccessMask
0x18001fc1c  lea     rcx, [rsp+268h+var_238]; this
0x18001fc21  call    ?Init@CSharedMemoryMarshalingSecurityDescriptor@@QEAAJK@Z; CSharedMemoryMarshalingSecurityDescriptor::Init(ulong)
0x18001fc26  mov     ebx, eax
0x18001fc28  test    eax, eax
0x18001fc2a  js      short loc_18001FC80
0x18001fc2c  lea     r9, [rsp+268h+Name]; lpName
0x18001fc34  xor     r8d, r8d; bInitialState
0x18001fc37  xor     edx, edx; bManualReset
0x18001fc39  lea     rcx, [rsp+268h+EventAttributes]; lpEventAttributes
0x18001fc41  call    cs:__imp_CreateEventW
0x18001fc47  mov     [rdi+8], rax
0x18001fc4b  test    rax, rax
0x18001fc4e  jz      loc_18001FCDE
0x18001fc54  cmp     qword ptr [rdi+8], 0
0x18001fc59  jz      short loc_18001FCC0
0x18001fc5b  lea     rax, [rsi+40h]
0x18001fc5f  mov     [rdi], rax
0x18001fc62  test    ebp, ebp
0x18001fc64  jz      short loc_18001FC80
0x18001fc66  mov     dword ptr [rax], 0FFFFFFFFh
0x18001fc6c  mov     rax, [rdi]
0x18001fc6f  mov     dword ptr [rax+4], 0
0x18001fc76  mov     rax, [rdi]
0x18001fc79  mov     dword ptr [rax+8], 0
0x18001fc80  mov     eax, ebx
0x18001fc82  mov     rcx, [rsp+268h+var_28]
0x18001fc8a  xor     rcx, rsp; StackCookie
0x18001fc8d  call    __security_check_cookie
0x18001fc92  mov     rbx, [rsp+268h+arg_10]
0x18001fc9a  add     rsp, 250h
0x18001fca1  pop     rdi
0x18001fca2  pop     rsi
0x18001fca3  pop     rbp
0x18001fca4  retn
0x18001fca5  lea     r8, [rsp+268h+Name]; lpName
0x18001fcad  xor     edx, edx; bInheritHandle
0x18001fcaf  mov     ecx, 100002h; dwDesiredAccess
0x18001fcb4  call    cs:__imp_OpenEventW
0x18001fcba  mov     [rdi+8], rax
0x18001fcbe  jmp     short loc_18001FC54
0x18001fcc0  call    cs:__imp_GetLastError
0x18001fcc6  mov     ebx, eax
0x18001fcc8  test    eax, eax
0x18001fcca  jle     short loc_18001FC80
0x18001fccc  movzx   ebx, ax
0x18001fccf  or      ebx, 80070000h
0x18001fcd5  jmp     short loc_18001FC80
0x18001fcd7  mov     ebx, 80030009h
0x18001fcdc  jmp     short loc_18001FC80
0x18001fcde  call    cs:__imp_GetLastError
0x18001fce4  cmp     eax, 5
0x18001fce7  jnz     loc_18001FC54
0x18001fced  xor     r9d, r9d; lpName
0x18001fcf0  xor     r8d, r8d; bInitialState
0x18001fcf3  xor     edx, edx; bManualReset
0x18001fcf5  xor     ecx, ecx; lpEventAttributes
0x18001fcf7  call    cs:__imp_CreateEventW
0x18001fcfd  jmp     short loc_18001FCBA
```
