# ImportRegistry

- ea: `0x14000998c`
- end: `0x140009ade`
- name: `ImportRegistry`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1400030b8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140001fec`
- `0x140002234`
- `0x140002b70`
- `0x140002f30`
- `0x14000998c`
- `0x140009d40`
- `0x14000ae58`
- `0x14000cd10`
- `0x14000da24`
- `0x14000dbe8`
- `0x14000dc24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009aa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009aa0`

## pseudocode

```c
__int64 __fastcall ImportRegistry(unsigned int a1, __int64 a2)
{
  FILE *v4; // rax
  unsigned int v5; // ebx
  __int64 ResString; // rax
  FILE *v8; // rax
  FILE *v9; // rax
  _DWORD v10[4]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v11[4]; // [rsp+30h] [rbp-B8h] BYREF
  int v12; // [rsp+34h] [rbp-B4h]
  LPCWSTR lpFileName; // [rsp+90h] [rbp-58h]
  unsigned int v14; // [rsp+BCh] [rbp-2Ch]

  v12 = 0;
  memset_0(v11, 0, 0x94u);
  v10[0] = 0;
  if ( a1 && a2 )
  {
    InitGlobalData(10, v11);
    if ( (unsigned int)ParseImportCmdLine(a1, a2, v11, v10) )
    {
      v5 = 1;
      if ( v10[0] == 1 )
      {
        Usage(10);
        v5 = 0;
      }
      else
      {
        ImportRegFileWorker(lpFileName, v14);
        if ( g_FileErrorStringID )
        {
          ResString = GetResString((unsigned int)g_FileErrorStringID);
          SetReason(ResString);
        }
        else
        {
          SaveErrorMessage(0);
          v5 = 0;
        }
        v8 = o___acrt_iob_func_0(2u);
        ShowLastErrorEx(v8);
      }
    }
    else
    {
      v4 = o___acrt_iob_func_0(2u);
      ShowLastErrorEx(v4);
      v5 = 1;
    }
    FreeGlobalData(v11);
    return v5;
  }
  else
  {
    SetLastError(0x57u);
    v9 = o___acrt_iob_func_0(2u);
    ShowLastError(v9);
    return 1;
  }
}

```

## disassembly

```asm
0x14000998c  mov     [rsp+arg_10], rbx
0x140009991  push    rdi
0x140009992  sub     rsp, 0E0h
0x140009999  mov     rax, cs:__security_cookie
0x1400099a0  xor     rax, rsp
0x1400099a3  mov     [rsp+0E8h+var_18], rax
0x1400099ab  mov     rbx, rdx
0x1400099ae  mov     edi, ecx
0x1400099b0  xor     eax, eax
0x1400099b2  lea     rcx, [rsp+0E8h+var_B8]; void *
0x1400099b7  xor     edx, edx; Val
0x1400099b9  mov     [rsp+0E8h+var_B4], eax
0x1400099bd  mov     r8d, 94h; Size
0x1400099c3  call    memset_0
0x1400099c8  mov     [rsp+0E8h+var_C8], 0
0x1400099d0  test    edi, edi
0x1400099d2  jz      loc_140009A9B
0x1400099d8  test    rbx, rbx
0x1400099db  jz      loc_140009A9B
0x1400099e1  lea     rdx, [rsp+0E8h+var_B8]
0x1400099e6  mov     ecx, 0Ah
0x1400099eb  call    InitGlobalData
0x1400099f0  lea     r9, [rsp+0E8h+var_C8]
0x1400099f5  mov     rdx, rbx
0x1400099f8  lea     r8, [rsp+0E8h+var_B8]
0x1400099fd  mov     ecx, edi
0x1400099ff  call    ParseImportCmdLine
0x140009a04  test    eax, eax
0x140009a06  jnz     short loc_140009A24
0x140009a08  lea     ecx, [rax+2]; Ix
0x140009a0b  call    _o___acrt_iob_func_0
0x140009a10  mov     rcx, rax
0x140009a13  mov     edx, 20000h
0x140009a18  call    ShowLastErrorEx
0x140009a1d  mov     ebx, 1
0x140009a22  jmp     short loc_140009A39
0x140009a24  mov     ebx, 1
0x140009a29  cmp     [rsp+0E8h+var_C8], ebx
0x140009a2d  jnz     short loc_140009A47
0x140009a2f  lea     ecx, [rbx+9]
0x140009a32  call    Usage
0x140009a37  xor     ebx, ebx
0x140009a39  lea     rcx, [rsp+0E8h+var_B8]
0x140009a3e  call    FreeGlobalData
0x140009a43  mov     eax, ebx
0x140009a45  jmp     short loc_140009ABD
0x140009a47  mov     edx, [rsp+0E8h+var_2C]
0x140009a4e  mov     rcx, [rsp+0E8h+lpFileName]; lpFileName
0x140009a56  call    ImportRegFileWorker
0x140009a5b  mov     ecx, cs:g_FileErrorStringID
0x140009a61  test    ecx, ecx
0x140009a63  jnz     short loc_140009A73
0x140009a65  call    SaveErrorMessage
0x140009a6a  xor     ebx, ebx
0x140009a6c  mov     edi, 20000h
0x140009a71  jmp     short loc_140009A85
0x140009a73  call    GetResString
0x140009a78  mov     rcx, rax
0x140009a7b  call    SetReason
0x140009a80  mov     edi, 20001h
0x140009a85  mov     ecx, 2; Ix
0x140009a8a  call    _o___acrt_iob_func_0
0x140009a8f  mov     rcx, rax
0x140009a92  mov     edx, edi
0x140009a94  call    ShowLastErrorEx
0x140009a99  jmp     short loc_140009A39
0x140009a9b  mov     ecx, 57h ; 'W'; dwErrCode
0x140009aa0  call    cs:__imp_SetLastError
0x140009aa6  mov     ecx, 2; Ix
0x140009aab  call    _o___acrt_iob_func_0
0x140009ab0  mov     rcx, rax
0x140009ab3  call    ShowLastError
0x140009ab8  mov     eax, 1
0x140009abd  mov     rcx, [rsp+0E8h+var_18]
0x140009ac5  xor     rcx, rsp; StackCookie
0x140009ac8  call    __security_check_cookie
0x140009acd  mov     rbx, [rsp+0E8h+arg_10]
0x140009ad5  add     rsp, 0E0h
0x140009adc  pop     rdi
0x140009add  retn
```
