# CCsvfsNtfsVolume::_Initialize(ushort *)

- ea: `0x18003cef0`
- end: `0x18003d0a0`
- name: `?_Initialize@CCsvfsNtfsVolume@@EEAAJPEAG@Z`
- size: `432`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001913c`
- `0x18001a630`
- `0x18003cef0`
- `0x18006495c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cf9f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cf9f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003d02c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003d02c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cfb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cfb6`

## pseudocode

```c
__int64 __fastcall CCsvfsNtfsVolume::_Initialize(LPCWSTR *this, unsigned __int16 *a2)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v6; // rdx
  WCHAR *FileW; // rbx
  __int64 v8; // r8
  __int64 v9; // r9
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v16; // [rsp+40h] [rbp-40h] BYREF
  __int16 v17; // [rsp+44h] [rbp-3Ch]
  __int16 v18; // [rsp+46h] [rbp-3Ah]
  int InBuffer; // [rsp+A8h] [rbp+28h] BYREF
  DWORD BytesReturned; // [rsp+B0h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CCsvfsNtfsVolume::_Initialize", 201, 1);
  InBuffer = 0;
  BytesReturned = 0;
  v4 = 206;
  if ( a2 )
  {
    v16 = 0;
    v17 = 206;
    LastFailureAsHRESULT = CBsString::Set((CBsString *)(this + 6), a2);
    v16 = LastFailureAsHRESULT;
    v4 = 209;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v17 = 209;
      FileW = (WCHAR *)CreateFileW(this[6], 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
      v10 = (WCHAR *)this[5];
      if ( (unsigned __int64)v10 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v10);
      this[5] = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v16 = 0;
        v17 = 220;
        InBuffer = 0;
        if ( DeviceIoControl(FileW, 0x902BCu, &InBuffer, 4u, 0, 0, &BytesReturned, 0) )
        {
          v16 = 0;
          v17 = 237;
          *((_DWORD *)this + 104) = 61440;
          LastFailureAsHRESULT = CVolume::_DiscoverTiers((CVolume *)this);
          v16 = LastFailureAsHRESULT;
          v4 = 241;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v17 = 241;
            goto LABEL_13;
          }
        }
        else
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12, v11, v13, v14);
          v16 = LastFailureAsHRESULT;
          v4 = 237;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10, v6, v8, v9);
        v16 = LastFailureAsHRESULT;
        v4 = 220;
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
  }
  v18 = v4;
LABEL_13:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003cef0  mov     [rsp-18h+arg_0], rbx
0x18003cef5  push    rbp
0x18003cef6  push    rsi
0x18003cef7  push    rdi
0x18003cef8  mov     rbp, rsp
0x18003cefb  sub     rsp, 80h
0x18003cf02  mov     rbx, rdx
0x18003cf05  mov     rdi, rcx
0x18003cf08  mov     r9d, 1; unsigned __int16
0x18003cf0e  mov     r8d, 0C9h; unsigned __int16
0x18003cf14  lea     rdx, aCcsvfsntfsvolu_2; "CCsvfsNtfsVolume::_Initialize"
0x18003cf1b  lea     rcx, [rbp+var_40]; this
0x18003cf1f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003cf24  nop
0x18003cf25  mov     [rbp+InBuffer], 0
0x18003cf2c  mov     [rbp+BytesReturned], 0
0x18003cf33  mov     eax, 0CEh
0x18003cf38  test    rbx, rbx
0x18003cf3b  jnz     short loc_18003CF4E
0x18003cf3d  mov     ebx, 80070057h
0x18003cf42  mov     [rbp+var_40], ebx
0x18003cf45  mov     [rbp+var_3A], ax
0x18003cf49  jmp     loc_18003D082
0x18003cf4e  mov     [rbp+var_40], 0
0x18003cf55  mov     [rbp+var_3C], ax
0x18003cf59  mov     rdx, rbx; unsigned __int16 *
0x18003cf5c  lea     rcx, [rdi+30h]; this
0x18003cf60  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003cf65  mov     ebx, eax
0x18003cf67  mov     [rbp+var_40], eax
0x18003cf6a  test    eax, eax
0x18003cf6c  mov     eax, 0D1h
0x18003cf71  js      short loc_18003CF45
0x18003cf73  mov     [rbp+var_3C], ax
0x18003cf77  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18003cf80  mov     [rsp+80h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18003cf88  mov     r8d, 3; dwShareMode
0x18003cf8e  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003cf93  xor     r9d, r9d; lpSecurityAttributes
0x18003cf96  mov     edx, 0C0000000h; dwDesiredAccess
0x18003cf9b  mov     rcx, [rdi+30h]; lpFileName
0x18003cf9f  call    cs:__imp_CreateFileW
0x18003cfa5  mov     rbx, rax
0x18003cfa8  mov     rcx, [rdi+28h]; hObject
0x18003cfac  lea     rax, [rcx-1]
0x18003cfb0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003cfb4  ja      short loc_18003CFBC
0x18003cfb6  call    cs:__imp_CloseHandle
0x18003cfbc  mov     [rdi+28h], rbx
0x18003cfc0  lea     rax, [rbx+1]
0x18003cfc4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003cfca  jnz     short loc_18003CFE0
0x18003cfcc  call    GetLastFailureAsHRESULT
0x18003cfd1  mov     ebx, eax
0x18003cfd3  mov     [rbp+var_40], eax
0x18003cfd6  mov     eax, 0DCh
0x18003cfdb  jmp     loc_18003CF45
0x18003cfe0  mov     [rbp+var_40], 0
0x18003cfe7  mov     eax, 0DCh
0x18003cfec  mov     [rbp+var_3C], ax
0x18003cff0  mov     [rbp+InBuffer], 0
0x18003cff7  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18003d000  lea     rax, [rbp+BytesReturned]
0x18003d004  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x18003d009  mov     [rsp+80h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18003d011  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOutBuffer
0x18003d01a  mov     r9d, 4; nInBufferSize
0x18003d020  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18003d024  mov     edx, 902BCh; dwIoControlCode
0x18003d029  mov     rcx, rbx; hDevice
0x18003d02c  call    cs:__imp_DeviceIoControl
0x18003d032  test    eax, eax
0x18003d034  jnz     short loc_18003D04A
0x18003d036  call    GetLastFailureAsHRESULT
0x18003d03b  mov     ebx, eax
0x18003d03d  mov     [rbp+var_40], eax
0x18003d040  mov     eax, 0EDh
0x18003d045  jmp     loc_18003CF45
0x18003d04a  mov     [rbp+var_40], 0
0x18003d051  mov     eax, 0EDh
0x18003d056  mov     [rbp+var_3C], ax
0x18003d05a  mov     dword ptr [rdi+1A0h], 0F000h
0x18003d064  mov     rcx, rdi; this
0x18003d067  call    ?_DiscoverTiers@CVolume@@IEAAJXZ; CVolume::_DiscoverTiers(void)
0x18003d06c  mov     ebx, eax
0x18003d06e  mov     [rbp+var_40], eax
0x18003d071  test    eax, eax
0x18003d073  mov     eax, 0F1h
0x18003d078  js      loc_18003CF45
0x18003d07e  mov     [rbp+var_3C], ax
0x18003d082  lea     rcx, [rbp+var_40]; this
0x18003d086  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003d08b  mov     eax, ebx
0x18003d08d  mov     rbx, [rsp+80h+arg_0]
0x18003d095  add     rsp, 80h
0x18003d09c  pop     rdi
0x18003d09d  pop     rsi
0x18003d09e  pop     rbp
0x18003d09f  retn
```
