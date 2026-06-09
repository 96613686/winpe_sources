# ImportRegistry

- ea: `0x140009f80`
- end: `0x14000a0d9`
- name: `ImportRegistry`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1400031f4`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002004`
- `0x1400022dc`
- `0x140002ce4`
- `0x140003068`
- `0x140009f80`
- `0x14000a358`
- `0x14000b54c`
- `0x14000d65c`
- `0x14000e560`
- `0x14000e75c`
- `0x14000e798`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a094`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a094`

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
0x140009f80  mov     [rsp+arg_10], rbx
0x140009f85  push    rdi
0x140009f86  sub     rsp, 0E0h
0x140009f8d  mov     rax, cs:__security_cookie
0x140009f94  xor     rax, rsp
0x140009f97  mov     [rsp+0E8h+var_18], rax
0x140009f9f  mov     rbx, rdx
0x140009fa2  mov     edi, ecx
0x140009fa4  xor     eax, eax
0x140009fa6  lea     rcx, [rsp+0E8h+var_B8]; void *
0x140009fab  xor     edx, edx; Val
0x140009fad  mov     [rsp+0E8h+var_B4], eax
0x140009fb1  mov     r8d, 94h; Size
0x140009fb7  call    memset_0
0x140009fbc  mov     [rsp+0E8h+var_C8], 0
0x140009fc4  test    edi, edi
0x140009fc6  jz      loc_14000A08F
0x140009fcc  test    rbx, rbx
0x140009fcf  jz      loc_14000A08F
0x140009fd5  lea     rdx, [rsp+0E8h+var_B8]
0x140009fda  mov     ecx, 0Ah
0x140009fdf  call    InitGlobalData
0x140009fe4  lea     r9, [rsp+0E8h+var_C8]
0x140009fe9  mov     rdx, rbx
0x140009fec  lea     r8, [rsp+0E8h+var_B8]
0x140009ff1  mov     ecx, edi
0x140009ff3  call    ParseImportCmdLine
0x140009ff8  test    eax, eax
0x140009ffa  jnz     short loc_14000A018
0x140009ffc  lea     ecx, [rax+2]; Ix
0x140009fff  call    _o___acrt_iob_func_0
0x14000a004  mov     rcx, rax
0x14000a007  mov     edx, 20000h
0x14000a00c  call    ShowLastErrorEx
0x14000a011  mov     ebx, 1
0x14000a016  jmp     short loc_14000A02D
0x14000a018  mov     ebx, 1
0x14000a01d  cmp     [rsp+0E8h+var_C8], ebx
0x14000a021  jnz     short loc_14000A03B
0x14000a023  lea     ecx, [rbx+9]
0x14000a026  call    Usage
0x14000a02b  xor     ebx, ebx
0x14000a02d  lea     rcx, [rsp+0E8h+var_B8]
0x14000a032  call    FreeGlobalData
0x14000a037  mov     eax, ebx
0x14000a039  jmp     short loc_14000A0B7
0x14000a03b  mov     edx, [rsp+0E8h+var_2C]
0x14000a042  mov     rcx, [rsp+0E8h+lpFileName]; lpFileName
0x14000a04a  call    ImportRegFileWorker
0x14000a04f  mov     ecx, cs:g_FileErrorStringID
0x14000a055  test    ecx, ecx
0x14000a057  jnz     short loc_14000A067
0x14000a059  call    SaveErrorMessage
0x14000a05e  xor     ebx, ebx
0x14000a060  mov     edi, 20000h
0x14000a065  jmp     short loc_14000A079
0x14000a067  call    GetResString
0x14000a06c  mov     rcx, rax
0x14000a06f  call    SetReason
0x14000a074  mov     edi, 20001h
0x14000a079  mov     ecx, 2; Ix
0x14000a07e  call    _o___acrt_iob_func_0
0x14000a083  mov     rcx, rax
0x14000a086  mov     edx, edi
0x14000a088  call    ShowLastErrorEx
0x14000a08d  jmp     short loc_14000A02D
0x14000a08f  mov     ecx, 57h ; 'W'; dwErrCode
0x14000a094  call    cs:__imp_SetLastError
0x14000a09b  nop     dword ptr [rax+rax+00h]
0x14000a0a0  mov     ecx, 2; Ix
0x14000a0a5  call    _o___acrt_iob_func_0
0x14000a0aa  mov     rcx, rax
0x14000a0ad  call    ShowLastError
0x14000a0b2  mov     eax, 1
0x14000a0b7  mov     rcx, [rsp+0E8h+var_18]
0x14000a0bf  xor     rcx, rsp; StackCookie
0x14000a0c2  call    __security_check_cookie
0x14000a0c7  mov     rbx, [rsp+0E8h+arg_10]
0x14000a0cf  add     rsp, 0E0h
0x14000a0d6  pop     rdi
0x14000a0d7  retn
```
