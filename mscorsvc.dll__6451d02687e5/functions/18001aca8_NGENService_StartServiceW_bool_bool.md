# NGENService::StartServiceW(bool,bool)

- ea: `0x18001aca8`
- end: `0x18001ada3`
- name: `?StartServiceW@NGENService@@YAJ_N0@Z`
- size: `251`
- prototype: `__int64 __fastcall(NGENService *__hidden this, bool, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18001b038`
- `0x18001bf08`

## callees

- `0x180007914`
- `0x18001a690`
- `0x18001aca8`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001ad0e`
- `KERNEL32!LoadLibraryExW` at `0x18001ad0e`
- `KERNEL32!GetLastError` at `0x18001ad5b`
- `KERNEL32!GetLastError` at `0x18001ad5b`
- `KERNEL32!GetProcAddress` at `0x18001ad23`
- `KERNEL32!GetProcAddress` at `0x18001ad23`

## string_xrefs

- `0x18001ad05`: `advapi32.dll`
- `0x18001ad19`: `StartServiceW`

## pseudocode

```c
__int64 __fastcall NGENService::StartServiceW(NGENService *this, struct SC_HANDLE__ **a2)
{
  char v2; // bp
  char v3; // si
  signed int v4; // ebx
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  struct SC_HANDLE__ *v10; // [rsp+40h] [rbp+18h] BYREF
  const wchar_t *v11; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  v2 = (char)this;
  v3 = (char)a2;
  v4 = NGENService::OpenNGENService((NGENService *)&v10, a2);
  if ( v4 >= 0 )
  {
    v5 = 0;
    if ( v3 )
    {
      v5 = 1;
      v11 = L"-startpaused";
    }
    ProcAddress = (FARPROC)qword_18006FF38;
    if ( (qword_18006FF38
       || !bStartServiceProbed
       && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
         ? (ProcAddress = (FARPROC)qword_18006FF38)
         : (FARPROC)(ProcAddress = GetProcAddress(Library, "StartServiceW"), qword_18006FF38 = (__int64)ProcAddress),
           bStartServiceProbed = 1,
           ProcAddress))
      && ((unsigned int (__fastcall *)(struct SC_HANDLE__ *, _QWORD, const wchar_t **))ProcAddress)(v10, v5, &v11)
      || (LastError = GetLastError(), v2) && LastError == 1056 )
    {
      v4 = 0;
    }
    else
    {
      v4 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v4 = LastError;
    }
  }
  if ( v10 )
    CLRCloseServiceHandle(v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001aca8  mov     rax, rsp
0x18001acab  mov     [rax+8], rbx
0x18001acaf  mov     [rax+10h], rbp
0x18001acb3  push    rsi
0x18001acb4  sub     rsp, 20h
0x18001acb8  and     qword ptr [rax+18h], 0
0x18001acbd  mov     bpl, cl
0x18001acc0  lea     rcx, [rax+18h]; this
0x18001acc4  mov     sil, dl
0x18001acc7  call    ?OpenNGENService@NGENService@@YAJPEAPEAUSC_HANDLE__@@@Z; NGENService::OpenNGENService(SC_HANDLE__ * *)
0x18001accc  mov     ebx, eax
0x18001acce  test    eax, eax
0x18001acd0  js      loc_18001AD7F
0x18001acd6  xor     ebx, ebx
0x18001acd8  test    sil, sil
0x18001acdb  jz      short loc_18001ACEE
0x18001acdd  lea     rax, aStartpaused; "-startpaused"
0x18001ace4  mov     ebx, 1
0x18001ace9  mov     [rsp+28h+arg_18], rax
0x18001acee  mov     rax, cs:qword_18006FF38
0x18001acf5  test    rax, rax
0x18001acf8  jnz     short loc_18001AD45
0x18001acfa  cmp     cs:?bStartServiceProbed@@3_NA, al; bool bStartServiceProbed
0x18001ad00  jnz     short loc_18001AD5B
0x18001ad02  xor     r8d, r8d; dwFlags
0x18001ad05  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18001ad0c  xor     edx, edx; hFile
0x18001ad0e  call    cs:__imp_LoadLibraryExW
0x18001ad14  test    rax, rax
0x18001ad17  jz      short loc_18001AD32
0x18001ad19  lea     rdx, aStartservicew; "StartServiceW"
0x18001ad20  mov     rcx, rax; hModule
0x18001ad23  call    cs:__imp_GetProcAddress
0x18001ad29  mov     cs:qword_18006FF38, rax
0x18001ad30  jmp     short loc_18001AD39
0x18001ad32  mov     rax, cs:qword_18006FF38
0x18001ad39  mov     cs:?bStartServiceProbed@@3_NA, 1; bool bStartServiceProbed
0x18001ad40  test    rax, rax
0x18001ad43  jz      short loc_18001AD5B
0x18001ad45  mov     rcx, [rsp+28h+arg_10]
0x18001ad4a  lea     r8, [rsp+28h+arg_18]
0x18001ad4f  mov     edx, ebx
0x18001ad51  call    cs:__guard_dispatch_icall_fptr
0x18001ad57  test    eax, eax
0x18001ad59  jnz     short loc_18001AD7D
0x18001ad5b  call    cs:__imp_GetLastError
0x18001ad61  test    bpl, bpl
0x18001ad64  jz      short loc_18001AD6D
0x18001ad66  cmp     eax, 420h
0x18001ad6b  jz      short loc_18001AD7D
0x18001ad6d  movzx   ebx, ax
0x18001ad70  or      ebx, 80070000h
0x18001ad76  test    eax, eax
0x18001ad78  cmovle  ebx, eax
0x18001ad7b  jmp     short loc_18001AD7F
0x18001ad7d  xor     ebx, ebx
0x18001ad7f  cmp     [rsp+28h+arg_10], 0
0x18001ad85  jz      short loc_18001AD91
0x18001ad87  mov     rcx, [rsp+28h+arg_10]; struct SC_HANDLE__ *
0x18001ad8c  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001ad91  mov     rbp, [rsp+28h+arg_8]
0x18001ad96  mov     eax, ebx
0x18001ad98  mov     rbx, [rsp+28h+arg_0]
0x18001ad9d  add     rsp, 20h
0x18001ada1  pop     rsi
0x18001ada2  retn
```
