# IsElevatedProcess(void)

- ea: `0x180024480`
- end: `0x180024521`
- name: `?IsElevatedProcess@@YAHXZ`
- size: `161`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023d98`
- `0x180064f64`
- `0x180065f64`
- `0x180072fa0`

## callees

- `0x180024480`
- `0x180024b80`
- `0x180024bb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800244b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800244b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800244c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800244c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024504`

## pseudocode

```c
__int64 IsElevatedProcess(void)
{
  HANDLE CurrentProcess; // rax
  int v2; // [rsp+30h] [rbp+8h] BYREF
  int v3; // [rsp+38h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  TokenHandle = 0;
  if ( !dword_180299FF4 )
  {
    if ( (unsigned int)IsMICLowProcess(0) )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        if ( (int)LUAGetSplitToken(TokenHandle, &v2, &v3) >= 0 )
        {
          dword_180299FF4 = 1;
          dword_180299FF8 = v2 != 0;
        }
        CloseHandle(TokenHandle);
      }
    }
    else
    {
      dword_180299FF4 = 1;
    }
  }
  return (unsigned int)dword_180299FF8;
}

```

## disassembly

```asm
0x180024480  sub     rsp, 28h
0x180024484  cmp     cs:dword_180299FF4, 0
0x18002448b  mov     [rsp+28h+arg_0], 0
0x180024493  mov     [rsp+28h+arg_8], 0
0x18002449b  mov     [rsp+28h+TokenHandle], 0
0x1800244a4  jnz     short loc_18002450A
0x1800244a6  xor     ecx, ecx; void *
0x1800244a8  call    ?IsMICLowProcess@@YAJPEAX@Z; IsMICLowProcess(void *)
0x1800244ad  test    eax, eax
0x1800244af  jz      short loc_180024515
0x1800244b1  call    cs:__imp_GetCurrentProcess
0x1800244b7  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800244bc  mov     edx, 8; DesiredAccess
0x1800244c1  mov     rcx, rax; ProcessHandle
0x1800244c4  call    cs:__imp_OpenProcessToken
0x1800244ca  test    eax, eax
0x1800244cc  jz      short loc_18002450A
0x1800244ce  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800244d3  lea     r8, [rsp+28h+arg_8]; int *
0x1800244d8  lea     rdx, [rsp+28h+arg_0]; int *
0x1800244dd  call    ?LUAGetSplitToken@@YAJPEAXPEAH1@Z; LUAGetSplitToken(void *,int *,int *)
0x1800244e2  test    eax, eax
0x1800244e4  js      short loc_1800244FF
0x1800244e6  xor     eax, eax
0x1800244e8  mov     cs:dword_180299FF4, 1
0x1800244f2  cmp     [rsp+28h+arg_0], eax
0x1800244f6  setnz   al
0x1800244f9  mov     cs:dword_180299FF8, eax
0x1800244ff  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180024504  call    cs:__imp_CloseHandle
0x18002450a  mov     eax, cs:dword_180299FF8
0x180024510  add     rsp, 28h
0x180024514  retn
0x180024515  mov     cs:dword_180299FF4, 1
0x18002451f  jmp     short loc_18002450A
```
