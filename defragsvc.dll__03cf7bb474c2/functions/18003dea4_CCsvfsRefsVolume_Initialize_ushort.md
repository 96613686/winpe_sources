# CCsvfsRefsVolume::_Initialize(ushort *)

- ea: `0x18003dea4`
- end: `0x18003e076`
- name: `?_Initialize@CCsvfsRefsVolume@@AEAAJPEAG@Z`
- size: `466`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180037c90`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001913c`
- `0x18001a630`
- `0x18003dea4`
- `0x18006495c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003df53`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003df53`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003dfe0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003dfe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df6a`

## pseudocode

```c
__int64 __fastcall CCsvfsRefsVolume::_Initialize(LPCWSTR *this, unsigned __int16 *a2)
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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CCsvfsRefsVolume::_Initialize", 374, 1);
  InBuffer = 0;
  BytesReturned = 0;
  v4 = 379;
  if ( a2 )
  {
    v16 = 0;
    v17 = 379;
    LastFailureAsHRESULT = CBsString::Set((CBsString *)(this + 6), a2);
    v16 = LastFailureAsHRESULT;
    v4 = 382;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v17 = 382;
      FileW = (WCHAR *)CreateFileW(this[6], 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
      v10 = (WCHAR *)this[5];
      if ( (unsigned __int64)v10 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v10);
      this[5] = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v16 = 0;
        v17 = 393;
        InBuffer = 0;
        if ( DeviceIoControl(FileW, 0x902BCu, &InBuffer, 4u, 0, 0, &BytesReturned, 0) )
        {
          v16 = 0;
          v17 = 410;
          LastFailureAsHRESULT = (*((__int64 (__fastcall **)(LPCWSTR *, char *))*this + 6))(this, (char *)this + 392);
          v16 = LastFailureAsHRESULT;
          v4 = 413;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v17 = 413;
            LastFailureAsHRESULT = CVolume::_DiscoverTiers((CVolume *)this);
            v16 = LastFailureAsHRESULT;
            v4 = 415;
            if ( LastFailureAsHRESULT >= 0 )
            {
              v17 = 415;
              goto LABEL_14;
            }
          }
        }
        else
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12, v11, v13, v14);
          v16 = LastFailureAsHRESULT;
          v4 = 410;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10, v6, v8, v9);
        v16 = LastFailureAsHRESULT;
        v4 = 393;
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
  }
  v18 = v4;
LABEL_14:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003dea4  mov     [rsp-18h+arg_0], rbx
0x18003dea9  push    rbp
0x18003deaa  push    rsi
0x18003deab  push    rdi
0x18003deac  mov     rbp, rsp
0x18003deaf  sub     rsp, 80h
0x18003deb6  mov     rbx, rdx
0x18003deb9  mov     rdi, rcx
0x18003debc  mov     r9d, 1; unsigned __int16
0x18003dec2  mov     r8d, 176h; unsigned __int16
0x18003dec8  lea     rdx, aCcsvfsrefsvolu_2; "CCsvfsRefsVolume::_Initialize"
0x18003decf  lea     rcx, [rbp+var_40]; this
0x18003ded3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003ded8  nop
0x18003ded9  mov     [rbp+InBuffer], 0
0x18003dee0  mov     [rbp+BytesReturned], 0
0x18003dee7  mov     eax, 17Bh
0x18003deec  test    rbx, rbx
0x18003deef  jnz     short loc_18003DF02
0x18003def1  mov     ebx, 80070057h
0x18003def6  mov     [rbp+var_40], ebx
0x18003def9  mov     [rbp+var_3A], ax
0x18003defd  jmp     loc_18003E058
0x18003df02  mov     [rbp+var_40], 0
0x18003df09  mov     [rbp+var_3C], ax
0x18003df0d  mov     rdx, rbx; unsigned __int16 *
0x18003df10  lea     rcx, [rdi+30h]; this
0x18003df14  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003df19  mov     ebx, eax
0x18003df1b  mov     [rbp+var_40], eax
0x18003df1e  test    eax, eax
0x18003df20  mov     eax, 17Eh
0x18003df25  js      short loc_18003DEF9
0x18003df27  mov     [rbp+var_3C], ax
0x18003df2b  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18003df34  mov     [rsp+80h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18003df3c  mov     r8d, 3; dwShareMode
0x18003df42  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003df47  xor     r9d, r9d; lpSecurityAttributes
0x18003df4a  mov     edx, 0C0000000h; dwDesiredAccess
0x18003df4f  mov     rcx, [rdi+30h]; lpFileName
0x18003df53  call    cs:__imp_CreateFileW
0x18003df59  mov     rbx, rax
0x18003df5c  mov     rcx, [rdi+28h]; hObject
0x18003df60  lea     rax, [rcx-1]
0x18003df64  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003df68  ja      short loc_18003DF70
0x18003df6a  call    cs:__imp_CloseHandle
0x18003df70  mov     [rdi+28h], rbx
0x18003df74  lea     rax, [rbx+1]
0x18003df78  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003df7e  jnz     short loc_18003DF94
0x18003df80  call    GetLastFailureAsHRESULT
0x18003df85  mov     ebx, eax
0x18003df87  mov     [rbp+var_40], eax
0x18003df8a  mov     eax, 189h
0x18003df8f  jmp     loc_18003DEF9
0x18003df94  mov     [rbp+var_40], 0
0x18003df9b  mov     eax, 189h
0x18003dfa0  mov     [rbp+var_3C], ax
0x18003dfa4  mov     [rbp+InBuffer], 0
0x18003dfab  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18003dfb4  lea     rax, [rbp+BytesReturned]
0x18003dfb8  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x18003dfbd  mov     [rsp+80h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18003dfc5  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOutBuffer
0x18003dfce  mov     r9d, 4; nInBufferSize
0x18003dfd4  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18003dfd8  mov     edx, 902BCh; dwIoControlCode
0x18003dfdd  mov     rcx, rbx; hDevice
0x18003dfe0  call    cs:__imp_DeviceIoControl
0x18003dfe6  test    eax, eax
0x18003dfe8  jnz     short loc_18003DFFE
0x18003dfea  call    GetLastFailureAsHRESULT
0x18003dfef  mov     ebx, eax
0x18003dff1  mov     [rbp+var_40], eax
0x18003dff4  mov     eax, 19Ah
0x18003dff9  jmp     loc_18003DEF9
0x18003dffe  mov     [rbp+var_40], 0
0x18003e005  mov     eax, 19Ah
0x18003e00a  mov     [rbp+var_3C], ax
0x18003e00e  mov     rax, [rdi]
0x18003e011  lea     rdx, [rdi+188h]
0x18003e018  mov     rcx, rdi
0x18003e01b  mov     rax, [rax+30h]
0x18003e01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e024  mov     ebx, eax
0x18003e026  mov     [rbp+var_40], eax
0x18003e029  test    eax, eax
0x18003e02b  mov     eax, 19Dh
0x18003e030  js      loc_18003DEF9
0x18003e036  mov     [rbp+var_3C], ax
0x18003e03a  mov     rcx, rdi; this
0x18003e03d  call    ?_DiscoverTiers@CVolume@@IEAAJXZ; CVolume::_DiscoverTiers(void)
0x18003e042  mov     ebx, eax
0x18003e044  mov     [rbp+var_40], eax
0x18003e047  test    eax, eax
0x18003e049  mov     eax, 19Fh
0x18003e04e  js      loc_18003DEF9
0x18003e054  mov     [rbp+var_3C], ax
0x18003e058  lea     rcx, [rbp+var_40]; this
0x18003e05c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003e061  mov     eax, ebx
0x18003e063  mov     rbx, [rsp+80h+arg_0]
0x18003e06b  add     rsp, 80h
0x18003e072  pop     rdi
0x18003e073  pop     rsi
0x18003e074  pop     rbp
0x18003e075  retn
```
