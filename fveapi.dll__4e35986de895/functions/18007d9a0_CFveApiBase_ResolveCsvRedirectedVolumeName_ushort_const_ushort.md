# CFveApiBase::ResolveCsvRedirectedVolumeName(ushort const *,ushort * *)

- ea: `0x18007d9a0`
- end: `0x18007dbc2`
- name: `?ResolveCsvRedirectedVolumeName@CFveApiBase@@SAJPEBGPEAPEAG@Z`
- size: `546`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a650`

## callees

- `0x180005410`
- `0x180007ae0`
- `0x180009b20`
- `0x18000ba30`
- `0x18000ca50`
- `0x180042998`
- `0x18007d9a0`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18007da07`
- `ntdll!RtlSetThreadErrorMode` at `0x18007db8f`
- `ntdll!RtlSetThreadErrorMode` at `0x180123d1d`
- `ntdll!RtlSetThreadErrorMode` at `0x18007da07`
- `ntdll!RtlSetThreadErrorMode` at `0x18007db8f`
- `ntdll!RtlSetThreadErrorMode` at `0x180123d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007db61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123cdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007db61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123cdf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007da5e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007da5e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007dabb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007dabb`

## pseudocode

```c
__int64 __fastcall CFveApiBase::ResolveCsvRedirectedVolumeName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 FileW; // rsi
  unsigned __int16 *v5; // rdi
  int LastHresultError; // ebx
  unsigned __int16 *v7; // rax
  LPCWSTR lpFileName; // [rsp+48h] [rbp-880h] BYREF
  unsigned __int16 *v10; // [rsp+50h] [rbp-878h]
  __int64 v11; // [rsp+58h] [rbp-870h]
  ULONG OldMode; // [rsp+60h] [rbp-868h] BYREF
  DWORD BytesReturned[3]; // [rsp+64h] [rbp-864h] BYREF
  _DWORD OutBuffer[7]; // [rsp+70h] [rbp-858h] BYREF
  unsigned __int16 v15; // [rsp+8Ch] [rbp-83Ch]
  unsigned __int16 v16[1033]; // [rsp+8Eh] [rbp-83Ah] BYREF

  FileW = -1;
  v11 = -1;
  OldMode = 0;
  memset_0(OutBuffer, 0, 0x830u);
  lpFileName = 0;
  v5 = 0;
  v10 = 0;
  BytesReturned[0] = 0;
  RtlSetThreadErrorMode(0x10u, &OldMode);
  if ( a1 && a2 )
  {
    LastHresultError = CFveApiBase::VolumeNameToVolumeGuidName(a1, (unsigned __int16 **)&lpFileName);
    if ( LastHresultError >= 0 )
    {
      FileW = (__int64)CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
      v11 = FileW;
      if ( FileW == -1 || !DeviceIoControl((HANDLE)FileW, 0x7780004u, 0, 0, OutBuffer, 0x830u, BytesReturned, 0) )
      {
        LastHresultError = GetLastHresultError();
      }
      else if ( OutBuffer[0] == 3 )
      {
        v7 = (unsigned __int16 *)CFveApiBase::FastAlloc(0x20Au);
        v5 = v7;
        v10 = v7;
        if ( v7 )
        {
          LastHresultError = StringCchCopyNW(v7, 0x105u, v16, (unsigned __int64)v15 >> 1);
          if ( LastHresultError >= 0 )
          {
            LastHresultError = CFveApiBase::ResolveVolumeName(v5, 0, a2);
            if ( LastHresultError >= 0 )
            {
              *a2 = v5;
              v5 = 0;
              v10 = 0;
            }
          }
        }
        else
        {
          LastHresultError = -2147024882;
        }
      }
      else
      {
        LastHresultError = 1;
        *a2 = 0;
      }
    }
  }
  else
  {
    LastHresultError = -2147024809;
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( lpFileName )
    CFveApiBase::FastFree((void *)lpFileName);
  if ( v5 )
    CFveApiBase::FastFree(v5);
  RtlSetThreadErrorMode(OldMode, 0);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18007d9a0  mov     [rsp+arg_10], rbx
0x18007d9a5  push    rsi
0x18007d9a6  push    rdi
0x18007d9a7  push    r14
0x18007d9a9  sub     rsp, 8B0h
0x18007d9b0  mov     rax, cs:__security_cookie
0x18007d9b7  xor     rax, rsp
0x18007d9ba  mov     [rsp+8C8h+var_28], rax
0x18007d9c2  mov     r14, rdx
0x18007d9c5  mov     rbx, rcx
0x18007d9c8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007d9cc  mov     [rsp+8C8h+var_870], rsi
0x18007d9d1  mov     [rsp+8C8h+OldMode], 0
0x18007d9d9  xor     edx, edx; Val
0x18007d9db  mov     r8d, 830h; Size
0x18007d9e1  lea     rcx, [rsp+8C8h+OutBuffer]; void *
0x18007d9e6  call    memset_0
0x18007d9eb  mov     [rsp+8C8h+lpFileName], 0
0x18007d9f4  xor     edi, edi
0x18007d9f6  mov     [rsp+8C8h+var_878], rdi
0x18007d9fb  mov     [rsp+8C8h+BytesReturned], edi
0x18007d9ff  lea     rdx, [rsp+8C8h+OldMode]; OldMode
0x18007da04  lea     ecx, [rsi+11h]; NewMode
0x18007da07  call    cs:__imp_RtlSetThreadErrorMode
0x18007da0e  nop     dword ptr [rax+rax+00h]
0x18007da13  nop
0x18007da14  test    rbx, rbx
0x18007da17  jz      loc_18007DB4F
0x18007da1d  test    r14, r14
0x18007da20  jz      loc_18007DB4F
0x18007da26  lea     rdx, [rsp+8C8h+lpFileName]; unsigned __int16 **
0x18007da2b  mov     rcx, rbx; unsigned __int16 *
0x18007da2e  call    ?VolumeNameToVolumeGuidName@CFveApiBase@@SAJPEBGPEAPEAG@Z; CFveApiBase::VolumeNameToVolumeGuidName(ushort const *,ushort * *)
0x18007da33  mov     ebx, eax
0x18007da35  mov     [rsp+8C8h+var_888], eax
0x18007da39  test    eax, eax
0x18007da3b  js      loc_18007DB58
0x18007da41  mov     [rsp+8C8h+hTemplateFile], rdi; hTemplateFile
0x18007da46  mov     [rsp+8C8h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18007da4a  lea     ebx, [rsi+4]
0x18007da4d  mov     [rsp+8C8h+dwCreationDisposition], ebx; dwCreationDisposition
0x18007da51  xor     r9d, r9d; lpSecurityAttributes
0x18007da54  mov     r8d, ebx; dwShareMode
0x18007da57  xor     edx, edx; dwDesiredAccess
0x18007da59  mov     rcx, [rsp+8C8h+lpFileName]; lpFileName
0x18007da5e  call    cs:__imp_CreateFileW
0x18007da65  nop     dword ptr [rax+rax+00h]
0x18007da6a  mov     rsi, rax
0x18007da6d  mov     [rsp+8C8h+var_870], rax
0x18007da72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007da76  jnz     short loc_18007DA88
0x18007da78  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18007da7d  mov     ebx, eax
0x18007da7f  mov     [rsp+8C8h+var_888], eax
0x18007da83  jmp     loc_18007DB58
0x18007da88  mov     [rsp+8C8h+lpOverlapped], 0; lpOverlapped
0x18007da91  lea     rax, [rsp+8C8h+BytesReturned]
0x18007da96  mov     [rsp+8C8h+hTemplateFile], rax; lpBytesReturned
0x18007da9b  mov     [rsp+8C8h+dwFlagsAndAttributes], 830h; nOutBufferSize
0x18007daa3  lea     rax, [rsp+8C8h+OutBuffer]
0x18007daa8  mov     qword ptr [rsp+8C8h+dwCreationDisposition], rax; lpOutBuffer
0x18007daad  xor     r9d, r9d; nInBufferSize
0x18007dab0  xor     r8d, r8d; lpInBuffer
0x18007dab3  mov     edx, 7780004h; dwIoControlCode
0x18007dab8  mov     rcx, rsi; hDevice
0x18007dabb  call    cs:__imp_DeviceIoControl
0x18007dac2  nop     dword ptr [rax+rax+00h]
0x18007dac7  test    eax, eax
0x18007dac9  jz      short loc_18007DA78
0x18007dacb  cmp     [rsp+8C8h+OutBuffer], ebx
0x18007dacf  jz      short loc_18007DAE3
0x18007dad1  mov     ebx, 1
0x18007dad6  mov     [rsp+8C8h+var_888], ebx
0x18007dada  mov     qword ptr [r14], 0
0x18007dae1  jmp     short loc_18007DB58
0x18007dae3  mov     ecx, 20Ah; unsigned __int64
0x18007dae8  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x18007daed  mov     rdi, rax
0x18007daf0  mov     [rsp+8C8h+var_878], rax
0x18007daf5  test    rax, rax
0x18007daf8  jnz     short loc_18007DB01
0x18007dafa  mov     ebx, 8007000Eh
0x18007daff  jmp     short loc_18007DB54
0x18007db01  movzx   r9d, [rsp+8C8h+var_83C]
0x18007db0a  shr     r9, 1; unsigned __int64
0x18007db0d  lea     r8, [rsp+8C8h+var_83A]; unsigned __int16 *
0x18007db15  mov     edx, 105h; unsigned __int64
0x18007db1a  mov     rcx, rdi; unsigned __int16 *
0x18007db1d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18007db22  mov     ebx, eax
0x18007db24  mov     [rsp+8C8h+var_888], eax
0x18007db28  test    eax, eax
0x18007db2a  js      short loc_18007DB58
0x18007db2c  mov     r8, r14; unsigned __int16 **
0x18007db2f  xor     edx, edx; unsigned int
0x18007db31  mov     rcx, rdi; unsigned __int16 *
0x18007db34  call    ?ResolveVolumeName@CFveApiBase@@SAJPEBGKPEAPEAG@Z; CFveApiBase::ResolveVolumeName(ushort const *,ulong,ushort * *)
0x18007db39  mov     ebx, eax
0x18007db3b  mov     [rsp+8C8h+var_888], eax
0x18007db3f  test    eax, eax
0x18007db41  js      short loc_18007DB58
0x18007db43  mov     [r14], rdi
0x18007db46  xor     edi, edi
0x18007db48  mov     [rsp+8C8h+var_878], rdi
0x18007db4d  jmp     short loc_18007DB58
0x18007db4f  mov     ebx, 80070057h
0x18007db54  mov     [rsp+8C8h+var_888], ebx
0x18007db58  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007db5c  jz      short loc_18007DB6D
0x18007db5e  mov     rcx, rsi; hObject
0x18007db61  call    cs:__imp_CloseHandle
0x18007db68  nop     dword ptr [rax+rax+00h]
0x18007db6d  mov     rcx, [rsp+8C8h+lpFileName]; lpMem
0x18007db72  test    rcx, rcx
0x18007db75  jz      short loc_18007DB7C
0x18007db77  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007db7c  test    rdi, rdi
0x18007db7f  jz      short loc_18007DB89
0x18007db81  mov     rcx, rdi; lpMem
0x18007db84  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007db89  xor     edx, edx; OldMode
0x18007db8b  mov     ecx, [rsp+8C8h+OldMode]; NewMode
0x18007db8f  call    cs:__imp_RtlSetThreadErrorMode
0x18007db96  nop     dword ptr [rax+rax+00h]
0x18007db9b  mov     eax, ebx
0x18007db9d  mov     rcx, [rsp+8C8h+var_28]
0x18007dba5  xor     rcx, rsp; StackCookie
0x18007dba8  call    __security_check_cookie
0x18007dbad  mov     rbx, [rsp+8C8h+arg_10]
0x18007dbb5  add     rsp, 8B0h
0x18007dbbc  pop     r14
0x18007dbbe  pop     rdi
0x18007dbbf  pop     rsi
0x18007dbc0  retn
0x180123ccc  push    rbp
0x180123cce  sub     rsp, 40h
0x180123cd2  mov     rbp, rdx
0x180123cd5  mov     rcx, [rbp+58h]; hObject
0x180123cd9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180123cdd  jz      short loc_180123CF3
0x180123cdf  call    cs:__imp_CloseHandle
0x180123ce6  nop     dword ptr [rax+rax+00h]
0x180123ceb  mov     qword ptr [rbp+58h], 0FFFFFFFFFFFFFFFFh
0x180123cf3  mov     rcx, [rbp+48h]; lpMem
0x180123cf7  test    rcx, rcx
0x180123cfa  jz      short loc_180123D02
0x180123cfc  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180123d01  nop
0x180123d02  mov     rcx, [rbp+50h]; lpMem
0x180123d06  test    rcx, rcx
0x180123d09  jz      short loc_180123D18
0x180123d0b  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180123d10  mov     qword ptr [rbp+50h], 0
0x180123d18  xor     edx, edx; OldMode
0x180123d1a  mov     ecx, [rbp+60h]; NewMode
0x180123d1d  call    cs:__imp_RtlSetThreadErrorMode
0x180123d24  nop     dword ptr [rax+rax+00h]
0x180123d29  nop
0x180123d2a  add     rsp, 40h
0x180123d2e  pop     rbp
0x180123d2f  retn
```
