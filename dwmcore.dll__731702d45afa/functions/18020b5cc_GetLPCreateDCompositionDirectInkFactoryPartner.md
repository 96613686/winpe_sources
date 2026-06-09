# GetLPCreateDCompositionDirectInkFactoryPartner

- ea: `0x18020b5cc`
- end: `0x18020b6a8`
- name: `GetLPCreateDCompositionDirectInkFactoryPartner`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18020b53c`

## callees

- `0x180050270`
- `0x18020b5cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18020b649`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18020b649`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18020b5f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18020b5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020b60d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020b60d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18020b602`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18020b602`

## string_xrefs

- `0x18020b5fb`: `Windows.UI.Input.Inking.dll`
- `0x18020b63f`: `CreateDCompositionDirectInkFactoryPartner`

## pseudocode

```c
__int64 __fastcall GetLPCreateDCompositionDirectInkFactoryPartner(FARPROC *a1)
{
  signed int v1; // ebx
  FARPROC ProcAddress; // rax
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  unsigned int v7; // [rsp+20h] [rbp-18h]

  v1 = dword_1803BF088;
  if ( dword_1803BF088 < 0 )
  {
    v7 = 24;
LABEL_13:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v1, v7, 0);
    goto LABEL_14;
  }
  ProcAddress = (FARPROC)qword_1803BF080;
  if ( qword_1803BF080 )
    goto LABEL_11;
  SetLastError(0);
  LibraryW = LoadLibraryW(L"Windows.UI.Input.Inking.dll");
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v7 = 29;
    if ( v1 >= 0 )
      v1 = -2003304445;
    goto LABEL_13;
  }
  ProcAddress = GetProcAddress(LibraryW, "CreateDCompositionDirectInkFactoryPartner");
  qword_1803BF080 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_11:
    *a1 = ProcAddress;
  }
  else
  {
    v1 = -2147467261;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147467261, 0x23u, 0);
  }
LABEL_14:
  dword_1803BF088 = v1;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18020b5cc  mov     [rsp+arg_0], rbx
0x18020b5d1  push    rdi
0x18020b5d2  sub     rsp, 30h
0x18020b5d6  mov     ebx, cs:dword_1803BF088
0x18020b5dc  mov     rdi, rcx
0x18020b5df  test    ebx, ebx
0x18020b5e1  js      loc_18020B674
0x18020b5e7  mov     rax, cs:qword_1803BF080
0x18020b5ee  test    rax, rax
0x18020b5f1  jnz     short loc_18020B66F
0x18020b5f3  xor     ecx, ecx; dwErrCode
0x18020b5f5  call    cs:__imp_SetLastError
0x18020b5fb  lea     rcx, aWindowsUiInput; "Windows.UI.Input.Inking.dll"
0x18020b602  call    cs:__imp_LoadLibraryW
0x18020b608  test    rax, rax
0x18020b60b  jnz     short loc_18020B63F
0x18020b60d  call    cs:__imp_GetLastError
0x18020b613  mov     ebx, eax
0x18020b615  test    eax, eax
0x18020b617  jle     short loc_18020B622
0x18020b619  movzx   ebx, ax
0x18020b61c  or      ebx, 80070000h
0x18020b622  test    ebx, ebx
0x18020b624  mov     [rsp+38h+var_10], 0
0x18020b62d  mov     eax, 88980003h
0x18020b632  mov     [rsp+38h+var_18], 1Dh
0x18020b63a  cmovns  ebx, eax
0x18020b63d  jmp     short loc_18020B685
0x18020b63f  lea     rdx, aCreatedcomposi; "CreateDCompositionDirectInkFactoryPartn"...
0x18020b646  mov     rcx, rax; hModule
0x18020b649  call    cs:__imp_GetProcAddress
0x18020b64f  mov     cs:qword_1803BF080, rax
0x18020b656  test    rax, rax
0x18020b659  jnz     short loc_18020B66F
0x18020b65b  mov     [rsp+38h+var_10], rax
0x18020b660  mov     ebx, 80004003h
0x18020b665  mov     [rsp+38h+var_18], 23h ; '#'
0x18020b66d  jmp     short loc_18020B685
0x18020b66f  mov     [rdi], rax
0x18020b672  jmp     short loc_18020B695
0x18020b674  mov     [rsp+38h+var_10], 0; void *
0x18020b67d  mov     [rsp+38h+var_18], 18h; unsigned int
0x18020b685  xor     edx, edx; int *
0x18020b687  mov     r9d, ebx; int
0x18020b68a  xor     r8d, r8d; unsigned int
0x18020b68d  lea     ecx, [rdx+14h]; unsigned int
0x18020b690  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18020b695  mov     cs:dword_1803BF088, ebx
0x18020b69b  mov     eax, ebx
0x18020b69d  mov     rbx, [rsp+38h+arg_0]
0x18020b6a2  add     rsp, 30h
0x18020b6a6  pop     rdi
0x18020b6a7  retn
```
