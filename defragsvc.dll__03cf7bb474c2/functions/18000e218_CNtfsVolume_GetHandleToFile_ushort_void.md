# CNtfsVolume::_GetHandleToFile(ushort *,void * *)

- ea: `0x18000e218`
- end: `0x18000e3f7`
- name: `?_GetHandleToFile@CNtfsVolume@@AEAAJPEAGPEAPEAX@Z`
- size: `479`
- prototype: `__int64 __fastcall(CNtfsVolume *this, unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000cf94`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000e218`
- `0x180038c3c`
- `0x18004e2f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e2e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e2e1`
- `ntdll!RtlGetLastNtStatus` at `0x18000e2ee`
- `ntdll!RtlGetLastNtStatus` at `0x18000e2ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e364`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::_GetHandleToFile(CNtfsVolume *this, unsigned __int16 *a2, void **a3)
{
  __int64 FileW; // rbx
  __int16 v6; // ax
  unsigned int v7; // edi
  NTSTATUS LastNtStatus; // eax
  int v10; // r8d
  unsigned int v11; // [rsp+40h] [rbp-19h] BYREF
  __int16 v12; // [rsp+44h] [rbp-15h]
  __int16 v13; // [rsp+46h] [rbp-13h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "CNtfsVolume::_GetHandleToFile", 692, 1);
  FileW = -1;
  v6 = 696;
  if ( !a2 || (v12 = 696, v6 = 697, !a3) )
  {
    v7 = -2147024809;
LABEL_3:
    v11 = v7;
    v13 = v6;
    goto LABEL_4;
  }
  v11 = 0;
  v12 = 697;
  *a3 = (void *)-1LL;
  FileW = (__int64)CreateFileW(a2, 0x80u, 1u, 0, 3u, 0x2000000u, 0);
  LastNtStatus = RtlGetLastNtStatus();
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( LastNtStatus == -1073741810 || LastNtStatus == -1073741202 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids);
      }
      v7 = -1996488687;
      v6 = 719;
      goto LABEL_3;
    }
    if ( LastNtStatus == -1073741774 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids);
      }
      v7 = -1996488675;
      v6 = 724;
      goto LABEL_3;
    }
    if ( LastNtStatus < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastNtStatus, v10, (_DWORD)a2, LastNtStatus);
      }
      v7 = -1996488674;
      v6 = 729;
      goto LABEL_3;
    }
  }
  *a3 = (void *)FileW;
  FileW = -1;
  v7 = v11;
LABEL_4:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return v7;
}

```

## disassembly

```asm
0x18000e218  mov     [rsp-8+arg_0], rcx
0x18000e21d  push    rbp
0x18000e21e  push    rbx
0x18000e21f  push    rsi
0x18000e220  push    rdi
0x18000e221  push    r14
0x18000e223  push    r15
0x18000e225  lea     rbp, [rsp-2Fh]
0x18000e22a  sub     rsp, 88h
0x18000e231  mov     rdi, r8
0x18000e234  mov     rsi, rdx
0x18000e237  mov     r9d, 1; unsigned __int16
0x18000e23d  mov     r8d, 2B4h; unsigned __int16
0x18000e243  lea     rdx, aCntfsvolumeGet_10; "CNtfsVolume::_GetHandleToFile"
0x18000e24a  lea     rcx, [rbp+57h+var_70]; this
0x18000e24e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e253  nop
0x18000e254  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000e258  mov     rbx, r15
0x18000e25b  mov     eax, 2B8h
0x18000e260  test    rsi, rsi
0x18000e263  jnz     short loc_18000E29A
0x18000e265  mov     edi, 80070057h
0x18000e26a  mov     [rbp+57h+var_70], edi
0x18000e26d  mov     [rbp+57h+var_6A], ax
0x18000e271  lea     rdx, [rbx-1]
0x18000e275  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000e279  jbe     loc_18000E361
0x18000e27f  lea     rcx, [rbp+57h+var_70]; this
0x18000e283  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e288  mov     eax, edi
0x18000e28a  add     rsp, 88h
0x18000e291  pop     r15
0x18000e293  pop     r14
0x18000e295  pop     rdi
0x18000e296  pop     rsi
0x18000e297  pop     rbx
0x18000e298  pop     rbp
0x18000e299  retn
0x18000e29a  mov     [rbp+57h+var_6C], ax
0x18000e29e  mov     eax, 2B9h
0x18000e2a3  test    rdi, rdi
0x18000e2a6  jz      short loc_18000E265
0x18000e2a8  mov     [rbp+57h+var_70], 0
0x18000e2af  mov     [rbp+57h+var_6C], ax
0x18000e2b3  mov     [rdi], r15
0x18000e2b6  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18000e2bf  mov     r14d, 2000000h
0x18000e2c5  mov     [rsp+0B0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18000e2ca  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e2d2  xor     r9d, r9d; lpSecurityAttributes
0x18000e2d5  mov     edx, 80h; dwDesiredAccess
0x18000e2da  lea     r8d, [r9+1]; dwShareMode
0x18000e2de  mov     rcx, rsi; lpFileName
0x18000e2e1  call    cs:__imp_CreateFileW
0x18000e2e7  mov     rbx, rax
0x18000e2ea  mov     [rbp+57h+arg_0], rax
0x18000e2ee  call    cs:__imp_RtlGetLastNtStatus
0x18000e2f4  mov     edx, eax
0x18000e2f6  lea     rcx, [rbx+1]
0x18000e2fa  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000e301  jnz     loc_18000E3E8
0x18000e307  cmp     eax, 0C000000Eh
0x18000e30c  jz      loc_18000E3AB
0x18000e312  cmp     eax, 0C000026Eh
0x18000e317  jz      loc_18000E3AB
0x18000e31d  cmp     eax, 0C0000032h
0x18000e322  jnz     short loc_18000E36F
0x18000e324  lea     rax, WPP_GLOBAL_Control
0x18000e32b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e332  cmp     rcx, rax
0x18000e335  jz      short loc_18000E352
0x18000e337  test    [rcx+1Ch], r14d
0x18000e33b  jz      short loc_18000E352
0x18000e33d  mov     edx, 16h
0x18000e342  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000e349  mov     rcx, [rcx+10h]
0x18000e34d  call    WPP_SF_
0x18000e352  mov     edi, 8900001Dh
0x18000e357  mov     eax, 2D4h
0x18000e35c  jmp     loc_18000E26A
0x18000e361  mov     rcx, rbx; hObject
0x18000e364  call    cs:__imp_CloseHandle
0x18000e36a  jmp     loc_18000E27F
0x18000e36f  test    edx, edx
0x18000e371  jns     short loc_18000E3E8
0x18000e373  lea     rax, WPP_GLOBAL_Control
0x18000e37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e381  cmp     rcx, rax
0x18000e384  jz      short loc_18000E39C
0x18000e386  test    [rcx+1Ch], r14d
0x18000e38a  jz      short loc_18000E39C
0x18000e38c  mov     [rsp+0B0h+dwCreationDisposition], edx
0x18000e390  mov     r9, rsi
0x18000e393  mov     rcx, [rcx+10h]
0x18000e397  call    WPP_SF_Sd
0x18000e39c  mov     edi, 8900001Eh
0x18000e3a1  mov     eax, 2D9h
0x18000e3a6  jmp     loc_18000E26A
0x18000e3ab  lea     rax, WPP_GLOBAL_Control
0x18000e3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3b9  cmp     rcx, rax
0x18000e3bc  jz      short loc_18000E3D9
0x18000e3be  test    [rcx+1Ch], r14d
0x18000e3c2  jz      short loc_18000E3D9
0x18000e3c4  mov     edx, 15h
0x18000e3c9  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000e3d0  mov     rcx, [rcx+10h]
0x18000e3d4  call    WPP_SF_
0x18000e3d9  mov     edi, 89000011h
0x18000e3de  mov     eax, 2CFh
0x18000e3e3  jmp     loc_18000E26A
0x18000e3e8  mov     [rdi], rbx
0x18000e3eb  mov     rbx, r15
0x18000e3ee  mov     edi, [rbp+57h+var_70]
0x18000e3f1  jmp     loc_18000E271
```
