# CFatVolume::_GetHandleToFile(CFatFile *,void * *)

- ea: `0x180014c68`
- end: `0x180014e41`
- name: `?_GetHandleToFile@CFatVolume@@AEAAJPEAVCFatFile@@PEAPEAX@Z`
- size: `473`
- prototype: `__int64 __fastcall(CFatVolume *this, LPCWSTR *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1800164ac`
- `0x180062910`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180010bc0`
- `0x180014c68`
- `0x180038c3c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014d09`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014d09`
- `ntdll!RtlGetLastNtStatus` at `0x180014d16`
- `ntdll!RtlGetLastNtStatus` at `0x180014d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e1f`

## pseudocode

```c
__int64 __fastcall CFatVolume::_GetHandleToFile(CFatVolume *this, LPCWSTR *a2, void **a3)
{
  __int64 FileW; // rbx
  __int16 v6; // ax
  unsigned int v7; // edi
  NTSTATUS LastNtStatus; // eax
  unsigned int v10; // [rsp+40h] [rbp-19h] BYREF
  __int16 v11; // [rsp+44h] [rbp-15h]
  __int16 v12; // [rsp+46h] [rbp-13h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CFatVolume::_GetHandleToFile", 56, 1);
  FileW = -1;
  v6 = 60;
  if ( !a2 || (v11 = 60, v6 = 61, !a3) )
  {
    v7 = -2147024809;
LABEL_3:
    v10 = v7;
    v12 = v6;
    goto LABEL_23;
  }
  v10 = 0;
  v11 = 61;
  *a3 = (void *)-1LL;
  FileW = (__int64)CreateFileW(a2[2], 0x80u, 1u, 0, 3u, 0x2000000u, 0);
  LastNtStatus = RtlGetLastNtStatus();
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( LastNtStatus == -1073741810 || LastNtStatus == -1073741202 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fe9b456ef50c386f386845b0fbdbb50f_Traceguids);
      }
      v7 = -1996488687;
      v6 = 83;
      goto LABEL_3;
    }
    if ( LastNtStatus == -1073741774 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fe9b456ef50c386f386845b0fbdbb50f_Traceguids);
      }
      v7 = -1996488675;
      v6 = 88;
      goto LABEL_3;
    }
    if ( LastNtStatus < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fe9b456ef50c386f386845b0fbdbb50f_Traceguids, a2[2]);
      }
      v7 = -1996488674;
      v6 = 93;
      goto LABEL_3;
    }
  }
  *a3 = (void *)FileW;
  FileW = -1;
  v7 = v10;
LABEL_23:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v7;
}

```

## disassembly

```asm
0x180014c68  mov     [rsp-8+arg_0], rcx
0x180014c6d  push    rbp
0x180014c6e  push    rbx
0x180014c6f  push    rsi
0x180014c70  push    rdi
0x180014c71  push    r14
0x180014c73  push    r15
0x180014c75  lea     rbp, [rsp-2Fh]
0x180014c7a  sub     rsp, 88h
0x180014c81  mov     rdi, r8
0x180014c84  mov     rsi, rdx
0x180014c87  mov     r9d, 1; unsigned __int16
0x180014c8d  lea     r8d, [r9+37h]; unsigned __int16
0x180014c91  lea     rdx, aCfatvolumeGeth; "CFatVolume::_GetHandleToFile"
0x180014c98  lea     rcx, [rbp+57h+var_70]; this
0x180014c9c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014ca1  nop
0x180014ca2  or      r15, 0FFFFFFFFFFFFFFFFh
0x180014ca6  mov     rbx, r15
0x180014ca9  lea     eax, [r15+3Dh]
0x180014cad  test    rsi, rsi
0x180014cb0  jnz     short loc_180014CC3
0x180014cb2  mov     edi, 80070057h
0x180014cb7  mov     [rbp+57h+var_70], edi
0x180014cba  mov     [rbp+57h+var_6A], ax
0x180014cbe  jmp     loc_180014E12
0x180014cc3  mov     [rbp+57h+var_6C], ax
0x180014cc7  mov     eax, 3Dh ; '='
0x180014ccc  test    rdi, rdi
0x180014ccf  jz      short loc_180014CB2
0x180014cd1  mov     [rbp+57h+var_70], 0
0x180014cd8  mov     [rbp+57h+var_6C], ax
0x180014cdc  mov     [rdi], r15
0x180014cdf  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x180014ce8  mov     r14d, 2000000h
0x180014cee  mov     [rsp+0B0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180014cf3  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180014cfb  xor     r9d, r9d; lpSecurityAttributes
0x180014cfe  lea     edx, [rax+43h]; dwDesiredAccess
0x180014d01  lea     r8d, [rax-3Ch]; dwShareMode
0x180014d05  mov     rcx, [rsi+10h]; lpFileName
0x180014d09  call    cs:__imp_CreateFileW
0x180014d0f  mov     rbx, rax
0x180014d12  mov     [rbp+57h+arg_0], rax
0x180014d16  call    cs:__imp_RtlGetLastNtStatus
0x180014d1c  lea     rcx, [rbx+1]
0x180014d20  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180014d27  jnz     loc_180014E09
0x180014d2d  cmp     eax, 0C000000Eh
0x180014d32  jz      loc_180014DCC
0x180014d38  cmp     eax, 0C000026Eh
0x180014d3d  jz      loc_180014DCC
0x180014d43  cmp     eax, 0C0000032h
0x180014d48  jnz     short loc_180014D87
0x180014d4a  lea     rax, WPP_GLOBAL_Control
0x180014d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d58  cmp     rcx, rax
0x180014d5b  jz      short loc_180014D78
0x180014d5d  test    [rcx+1Ch], r14d
0x180014d61  jz      short loc_180014D78
0x180014d63  mov     edx, 0Bh
0x180014d68  lea     r8, WPP_fe9b456ef50c386f386845b0fbdbb50f_Traceguids
0x180014d6f  mov     rcx, [rcx+10h]
0x180014d73  call    WPP_SF_
0x180014d78  mov     edi, 8900001Dh
0x180014d7d  mov     eax, 58h ; 'X'
0x180014d82  jmp     loc_180014CB7
0x180014d87  test    eax, eax
0x180014d89  jns     short loc_180014E09
0x180014d8b  lea     rax, WPP_GLOBAL_Control
0x180014d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d99  cmp     rcx, rax
0x180014d9c  jz      short loc_180014DBD
0x180014d9e  test    [rcx+1Ch], r14d
0x180014da2  jz      short loc_180014DBD
0x180014da4  mov     edx, 0Ch
0x180014da9  mov     r9, [rsi+10h]
0x180014dad  lea     r8, WPP_fe9b456ef50c386f386845b0fbdbb50f_Traceguids
0x180014db4  mov     rcx, [rcx+10h]
0x180014db8  call    WPP_SF_S
0x180014dbd  mov     edi, 8900001Eh
0x180014dc2  mov     eax, 5Dh ; ']'
0x180014dc7  jmp     loc_180014CB7
0x180014dcc  lea     rax, WPP_GLOBAL_Control
0x180014dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dda  cmp     rcx, rax
0x180014ddd  jz      short loc_180014DFA
0x180014ddf  test    [rcx+1Ch], r14d
0x180014de3  jz      short loc_180014DFA
0x180014de5  mov     edx, 0Ah
0x180014dea  lea     r8, WPP_fe9b456ef50c386f386845b0fbdbb50f_Traceguids
0x180014df1  mov     rcx, [rcx+10h]
0x180014df5  call    WPP_SF_
0x180014dfa  mov     edi, 89000011h
0x180014dff  mov     eax, 53h ; 'S'
0x180014e04  jmp     loc_180014CB7
0x180014e09  mov     [rdi], rbx
0x180014e0c  mov     rbx, r15
0x180014e0f  mov     edi, [rbp+57h+var_70]
0x180014e12  lea     rdx, [rbx-1]
0x180014e16  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180014e1a  ja      short loc_180014E26
0x180014e1c  mov     rcx, rbx; hObject
0x180014e1f  call    cs:__imp_CloseHandle
0x180014e25  nop
0x180014e26  lea     rcx, [rbp+57h+var_70]; this
0x180014e2a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180014e2f  mov     eax, edi
0x180014e31  add     rsp, 88h
0x180014e38  pop     r15
0x180014e3a  pop     r14
0x180014e3c  pop     rdi
0x180014e3d  pop     rsi
0x180014e3e  pop     rbx
0x180014e3f  pop     rbp
0x180014e40  retn
```
