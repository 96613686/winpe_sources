# CReFsVolume::_GetHandleToFile(CReFsFile *,void * *)

- ea: `0x18002e944`
- end: `0x18002eb1d`
- name: `?_GetHandleToFile@CReFsVolume@@AEAAJPEAVCReFsFile@@PEAPEAX@Z`
- size: `473`
- prototype: `__int64 __fastcall(CReFsVolume *this, LPCWSTR *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18001f468`
- `0x180063280`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180010bc0`
- `0x18002e944`
- `0x180038c3c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e9e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e9e5`
- `ntdll!RtlGetLastNtStatus` at `0x18002e9f2`
- `ntdll!RtlGetLastNtStatus` at `0x18002e9f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eafb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eafb`

## pseudocode

```c
__int64 __fastcall CReFsVolume::_GetHandleToFile(CReFsVolume *this, LPCWSTR *a2, void **a3)
{
  __int64 FileW; // rbx
  __int16 v6; // ax
  unsigned int v7; // edi
  NTSTATUS LastNtStatus; // eax
  unsigned int v10; // [rsp+40h] [rbp-19h] BYREF
  __int16 v11; // [rsp+44h] [rbp-15h]
  __int16 v12; // [rsp+46h] [rbp-13h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CReFsVolume::_GetHandleToFile", 56, 1);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9a6ec28d2db13e7eb6dd4d7fe202a1ff_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9a6ec28d2db13e7eb6dd4d7fe202a1ff_Traceguids);
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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9a6ec28d2db13e7eb6dd4d7fe202a1ff_Traceguids, a2[2]);
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
0x18002e944  mov     [rsp-8+arg_0], rcx
0x18002e949  push    rbp
0x18002e94a  push    rbx
0x18002e94b  push    rsi
0x18002e94c  push    rdi
0x18002e94d  push    r14
0x18002e94f  push    r15
0x18002e951  lea     rbp, [rsp-2Fh]
0x18002e956  sub     rsp, 88h
0x18002e95d  mov     rdi, r8
0x18002e960  mov     rsi, rdx
0x18002e963  mov     r9d, 1; unsigned __int16
0x18002e969  lea     r8d, [r9+37h]; unsigned __int16
0x18002e96d  lea     rdx, aCrefsvolumeGet_8; "CReFsVolume::_GetHandleToFile"
0x18002e974  lea     rcx, [rbp+57h+var_70]; this
0x18002e978  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002e97d  nop
0x18002e97e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002e982  mov     rbx, r15
0x18002e985  lea     eax, [r15+3Dh]
0x18002e989  test    rsi, rsi
0x18002e98c  jnz     short loc_18002E99F
0x18002e98e  mov     edi, 80070057h
0x18002e993  mov     [rbp+57h+var_70], edi
0x18002e996  mov     [rbp+57h+var_6A], ax
0x18002e99a  jmp     loc_18002EAEE
0x18002e99f  mov     [rbp+57h+var_6C], ax
0x18002e9a3  mov     eax, 3Dh ; '='
0x18002e9a8  test    rdi, rdi
0x18002e9ab  jz      short loc_18002E98E
0x18002e9ad  mov     [rbp+57h+var_70], 0
0x18002e9b4  mov     [rbp+57h+var_6C], ax
0x18002e9b8  mov     [rdi], r15
0x18002e9bb  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18002e9c4  mov     r14d, 2000000h
0x18002e9ca  mov     [rsp+0B0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18002e9cf  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002e9d7  xor     r9d, r9d; lpSecurityAttributes
0x18002e9da  lea     edx, [rax+43h]; dwDesiredAccess
0x18002e9dd  lea     r8d, [rax-3Ch]; dwShareMode
0x18002e9e1  mov     rcx, [rsi+10h]; lpFileName
0x18002e9e5  call    cs:__imp_CreateFileW
0x18002e9eb  mov     rbx, rax
0x18002e9ee  mov     [rbp+57h+arg_0], rax
0x18002e9f2  call    cs:__imp_RtlGetLastNtStatus
0x18002e9f8  lea     rcx, [rbx+1]
0x18002e9fc  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18002ea03  jnz     loc_18002EAE5
0x18002ea09  cmp     eax, 0C000000Eh
0x18002ea0e  jz      loc_18002EAA8
0x18002ea14  cmp     eax, 0C000026Eh
0x18002ea19  jz      loc_18002EAA8
0x18002ea1f  cmp     eax, 0C0000032h
0x18002ea24  jnz     short loc_18002EA63
0x18002ea26  lea     rax, WPP_GLOBAL_Control
0x18002ea2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea34  cmp     rcx, rax
0x18002ea37  jz      short loc_18002EA54
0x18002ea39  test    [rcx+1Ch], r14d
0x18002ea3d  jz      short loc_18002EA54
0x18002ea3f  mov     edx, 0Bh
0x18002ea44  lea     r8, WPP_9a6ec28d2db13e7eb6dd4d7fe202a1ff_Traceguids
0x18002ea4b  mov     rcx, [rcx+10h]
0x18002ea4f  call    WPP_SF_
0x18002ea54  mov     edi, 8900001Dh
0x18002ea59  mov     eax, 58h ; 'X'
0x18002ea5e  jmp     loc_18002E993
0x18002ea63  test    eax, eax
0x18002ea65  jns     short loc_18002EAE5
0x18002ea67  lea     rax, WPP_GLOBAL_Control
0x18002ea6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea75  cmp     rcx, rax
0x18002ea78  jz      short loc_18002EA99
0x18002ea7a  test    [rcx+1Ch], r14d
0x18002ea7e  jz      short loc_18002EA99
0x18002ea80  mov     edx, 0Ch
0x18002ea85  mov     r9, [rsi+10h]
0x18002ea89  lea     r8, WPP_9a6ec28d2db13e7eb6dd4d7fe202a1ff_Traceguids
0x18002ea90  mov     rcx, [rcx+10h]
0x18002ea94  call    WPP_SF_S
0x18002ea99  mov     edi, 8900001Eh
0x18002ea9e  mov     eax, 5Dh ; ']'
0x18002eaa3  jmp     loc_18002E993
0x18002eaa8  lea     rax, WPP_GLOBAL_Control
0x18002eaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eab6  cmp     rcx, rax
0x18002eab9  jz      short loc_18002EAD6
0x18002eabb  test    [rcx+1Ch], r14d
0x18002eabf  jz      short loc_18002EAD6
0x18002eac1  mov     edx, 0Ah
0x18002eac6  lea     r8, WPP_9a6ec28d2db13e7eb6dd4d7fe202a1ff_Traceguids
0x18002eacd  mov     rcx, [rcx+10h]
0x18002ead1  call    WPP_SF_
0x18002ead6  mov     edi, 89000011h
0x18002eadb  mov     eax, 53h ; 'S'
0x18002eae0  jmp     loc_18002E993
0x18002eae5  mov     [rdi], rbx
0x18002eae8  mov     rbx, r15
0x18002eaeb  mov     edi, [rbp+57h+var_70]
0x18002eaee  lea     rdx, [rbx-1]
0x18002eaf2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002eaf6  ja      short loc_18002EB02
0x18002eaf8  mov     rcx, rbx; hObject
0x18002eafb  call    cs:__imp_CloseHandle
0x18002eb01  nop
0x18002eb02  lea     rcx, [rbp+57h+var_70]; this
0x18002eb06  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002eb0b  mov     eax, edi
0x18002eb0d  add     rsp, 88h
0x18002eb14  pop     r15
0x18002eb16  pop     r14
0x18002eb18  pop     rdi
0x18002eb19  pop     rsi
0x18002eb1a  pop     rbx
0x18002eb1b  pop     rbp
0x18002eb1c  retn
```
