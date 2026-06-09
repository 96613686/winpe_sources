# CVolume::GetFilePath(ulong,ushort * *)

- ea: `0x18003baf0`
- end: `0x18003bcaf`
- name: `?GetFilePath@CVolume@@UEAAJKPEAPEAG@Z`
- size: `447`
- prototype: `__int64 __fastcall(CVolume *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18003baf0`
- `0x180067af2`
- `0x180067b0a`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bbb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bc81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bc81`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003bbae`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003bbae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bb82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bb82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bbcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bc6a`

## string_xrefs

- `0x18003bb19`: `CVolume::GetFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVolume::GetFilePath(CVolume *this, unsigned int a2, unsigned __int16 **a3)
{
  _DWORD *v6; // rbx
  __int16 v7; // ax
  DWORD v8; // edi
  _DWORD *v9; // rax
  signed int LastError; // eax
  bool v11; // sf
  void *v12; // rax
  void *v13; // rdi
  unsigned int v14; // ebx
  int v16; // [rsp+20h] [rbp-40h] BYREF
  __int16 v17; // [rsp+24h] [rbp-3Ch]
  __int16 v18; // [rsp+26h] [rbp-3Ah]
  HANDLE hFile; // [rsp+90h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CVolume::GetFilePath", 2921, 1);
  hFile = (HANDLE)-1LL;
  v6 = 0;
  v7 = 2929;
  if ( a3 )
  {
    v16 = 0;
    v17 = 2929;
    *a3 = 0;
    v16 = (*(__int64 (__fastcall **)(CVolume *, _QWORD, HANDLE *))(*(_QWORD *)this + 392LL))(this, a2, &hFile);
    v7 = 2933;
    if ( v16 >= 0 )
    {
      v8 = 526;
      v17 = 2933;
      while ( 1 )
      {
        v9 = CoTaskMemAlloc(v8);
        v6 = v9;
        if ( !v9 )
        {
          v16 = -2147024882;
          v18 = 2939;
          goto LABEL_18;
        }
        v16 = 0;
        v17 = 2939;
        if ( GetFileInformationByHandleEx(hFile, FileNameInfo, v9, v8) )
          goto LABEL_12;
        LastError = GetLastError();
        if ( LastError != 234 )
          break;
        v8 = *v6 + 8;
        CoTaskMemFree(v6);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v16 = LastError;
      v11 = LastError < 0;
      v7 = 2957;
      if ( !v11 )
      {
        v17 = 2957;
LABEL_12:
        v12 = CoTaskMemAlloc((unsigned int)*v6 + 2LL);
        v13 = v12;
        if ( v12 )
        {
          v16 = 0;
          v17 = 2965;
          memset_0(v12, 0, (unsigned int)*v6 + 2LL);
          memcpy_0(v13, v6 + 1, (unsigned int)*v6);
          *a3 = (unsigned __int16 *)v13;
        }
        else
        {
          v16 = -2147024882;
          v18 = 2965;
        }
        goto LABEL_18;
      }
    }
  }
  else
  {
    v16 = -2147024809;
  }
  v18 = v7;
LABEL_18:
  CoTaskMemFree(0);
  CoTaskMemFree(v6);
  v14 = v16;
  if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hFile);
    hFile = (HANDLE)-1LL;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v14;
}

```

## disassembly

```asm
0x18003baf0  mov     [rsp-18h+arg_0], rbx
0x18003baf5  mov     [rsp-18h+arg_8], rsi
0x18003bafa  push    rbp
0x18003bafb  push    rdi
0x18003bafc  push    r14
0x18003bafe  mov     rbp, rsp
0x18003bb01  sub     rsp, 60h
0x18003bb05  mov     r14, r8
0x18003bb08  mov     esi, edx
0x18003bb0a  mov     rdi, rcx
0x18003bb0d  mov     r9d, 1; unsigned __int16
0x18003bb13  mov     r8d, 0B69h; unsigned __int16
0x18003bb19  lea     rdx, aCvolumeGetfile_2; "CVolume::GetFilePath"
0x18003bb20  lea     rcx, [rbp+var_40]; this
0x18003bb24  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003bb29  nop
0x18003bb2a  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x18003bb32  xor     ebx, ebx
0x18003bb34  mov     eax, 0B71h
0x18003bb39  test    r14, r14
0x18003bb3c  jz      loc_18003BC54
0x18003bb42  mov     [rbp+var_40], ebx
0x18003bb45  mov     [rbp+var_3C], ax
0x18003bb49  mov     [r14], rbx
0x18003bb4c  mov     rax, [rdi]
0x18003bb4f  lea     r8, [rbp+hFile]
0x18003bb53  mov     edx, esi
0x18003bb55  mov     rcx, rdi
0x18003bb58  mov     rax, [rax+188h]
0x18003bb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb64  mov     [rbp+var_40], eax
0x18003bb67  test    eax, eax
0x18003bb69  mov     eax, 0B75h
0x18003bb6e  js      loc_18003BC5B
0x18003bb74  mov     edi, 20Eh
0x18003bb79  mov     [rbp+var_3C], ax
0x18003bb7d  lea     esi, [rax+6]
0x18003bb80  mov     ecx, edi; cb
0x18003bb82  call    cs:__imp_CoTaskMemAlloc
0x18003bb88  mov     rbx, rax
0x18003bb8b  test    rax, rax
0x18003bb8e  jz      loc_18003BC47
0x18003bb94  mov     [rbp+var_40], 0
0x18003bb9b  mov     [rbp+var_3C], si
0x18003bb9f  mov     r9d, edi; dwBufferSize
0x18003bba2  mov     r8, rax; lpFileInformation
0x18003bba5  mov     edx, 2; FileInformationClass
0x18003bbaa  mov     rcx, [rbp+hFile]; hFile
0x18003bbae  call    cs:__imp_GetFileInformationByHandleEx
0x18003bbb4  test    eax, eax
0x18003bbb6  jnz     short loc_18003BBF1
0x18003bbb8  call    cs:__imp_GetLastError
0x18003bbbe  cmp     eax, 0EAh
0x18003bbc3  jnz     short loc_18003BBD5
0x18003bbc5  mov     edi, [rbx]
0x18003bbc7  add     edi, 8
0x18003bbca  mov     rcx, rbx; pv
0x18003bbcd  call    cs:__imp_CoTaskMemFree
0x18003bbd3  jmp     short loc_18003BB80
0x18003bbd5  test    eax, eax
0x18003bbd7  jle     short loc_18003BBE1
0x18003bbd9  movzx   eax, ax
0x18003bbdc  or      eax, 80070000h
0x18003bbe1  mov     [rbp+var_40], eax
0x18003bbe4  test    eax, eax
0x18003bbe6  mov     eax, 0B8Dh
0x18003bbeb  js      short loc_18003BC5B
0x18003bbed  mov     [rbp+var_3C], ax
0x18003bbf1  mov     ecx, [rbx]
0x18003bbf3  add     rcx, 2; cb
0x18003bbf7  call    cs:__imp_CoTaskMemAlloc
0x18003bbfd  mov     rdi, rax
0x18003bc00  mov     ecx, 0B95h
0x18003bc05  test    rax, rax
0x18003bc08  jz      short loc_18003BC3A
0x18003bc0a  mov     [rbp+var_40], 0
0x18003bc11  mov     [rbp+var_3C], cx
0x18003bc15  mov     r8d, [rbx]
0x18003bc18  add     r8, 2; Size
0x18003bc1c  xor     edx, edx; Val
0x18003bc1e  mov     rcx, rax; void *
0x18003bc21  call    memset_0
0x18003bc26  mov     r8d, [rbx]; Size
0x18003bc29  lea     rdx, [rbx+4]; Src
0x18003bc2d  mov     rcx, rdi; void *
0x18003bc30  call    memcpy_0
0x18003bc35  mov     [r14], rdi
0x18003bc38  jmp     short loc_18003BC5F
0x18003bc3a  mov     [rbp+var_40], 8007000Eh
0x18003bc41  mov     [rbp+var_3A], cx
0x18003bc45  jmp     short loc_18003BC5F
0x18003bc47  mov     [rbp+var_40], 8007000Eh
0x18003bc4e  mov     [rbp+var_3A], si
0x18003bc52  jmp     short loc_18003BC5F
0x18003bc54  mov     [rbp+var_40], 80070057h
0x18003bc5b  mov     [rbp+var_3A], ax
0x18003bc5f  xor     ecx, ecx; pv
0x18003bc61  call    cs:__imp_CoTaskMemFree
0x18003bc67  mov     rcx, rbx; pv
0x18003bc6a  call    cs:__imp_CoTaskMemFree
0x18003bc70  mov     ebx, [rbp+var_40]
0x18003bc73  mov     rcx, [rbp+hFile]; hObject
0x18003bc77  lea     rdx, [rcx-1]
0x18003bc7b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003bc7f  ja      short loc_18003BC8F
0x18003bc81  call    cs:__imp_CloseHandle
0x18003bc87  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x18003bc8f  lea     rcx, [rbp+var_40]; this
0x18003bc93  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003bc98  mov     eax, ebx
0x18003bc9a  lea     r11, [rsp+60h+var_s0]
0x18003bc9f  mov     rbx, [r11+20h]
0x18003bca3  mov     rsi, [r11+28h]
0x18003bca7  mov     rsp, r11
0x18003bcaa  pop     r14
0x18003bcac  pop     rdi
0x18003bcad  pop     rbp
0x18003bcae  retn
```
