# GetProcessAppContainerNumber(ulong,ulong *)

- ea: `0x1800623c0`
- end: `0x180062479`
- name: `?GetProcessAppContainerNumber@@YAJKPEAK@Z`
- size: `185`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180025024`
- `0x1800623c0`
- `0x180062480`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800623d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800623d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062466`

## pseudocode

```c
__int64 __fastcall GetProcessAppContainerNumber(DWORD a1, unsigned int *a2)
{
  __int64 v4; // rcx
  int ProcessToken; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v7; // rcx
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  if ( !a1 || a1 == GetCurrentProcessId() )
  {
    if ( byte_180299E8C )
    {
      ProcessToken = 0;
      *a2 = dword_180299E88;
    }
    else
    {
      hObject = 0;
      CurrentProcessId = GetCurrentProcessId();
      ProcessToken = GetProcessToken(v7, CurrentProcessId, &hObject);
      if ( ProcessToken >= 0 )
      {
        ProcessToken = GetTokenAppContainerNumber(hObject, a2);
        if ( ProcessToken >= 0 )
        {
          dword_180299E88 = *a2;
          byte_180299E8C = 1;
        }
        goto LABEL_10;
      }
    }
  }
  else
  {
    hObject = 0;
    ProcessToken = GetProcessToken(v4, a1, &hObject);
    if ( ProcessToken >= 0 )
    {
      ProcessToken = GetTokenAppContainerNumber(hObject, a2);
LABEL_10:
      CloseHandle(hObject);
    }
  }
  return (unsigned int)ProcessToken;
}

```

## disassembly

```asm
0x1800623c0  mov     [rsp+arg_0], rbx
0x1800623c5  push    rdi
0x1800623c6  sub     rsp, 20h
0x1800623ca  mov     rdi, rdx
0x1800623cd  mov     ebx, ecx
0x1800623cf  test    ecx, ecx
0x1800623d1  jz      short loc_180062409
0x1800623d3  call    cs:__imp_GetCurrentProcessId
0x1800623d9  cmp     ebx, eax
0x1800623db  jz      short loc_180062409
0x1800623dd  lea     r8, [rsp+28h+hObject]; void **
0x1800623e2  mov     [rsp+28h+hObject], 0
0x1800623eb  mov     edx, ebx; unsigned int
0x1800623ed  call    ?GetProcessToken@@YAJKKPEAPEAX@Z; GetProcessToken(ulong,ulong,void * *)
0x1800623f2  mov     ebx, eax
0x1800623f4  test    eax, eax
0x1800623f6  js      short loc_18006246C
0x1800623f8  mov     rcx, [rsp+28h+hObject]; void *
0x1800623fd  mov     rdx, rdi; unsigned int *
0x180062400  call    ?GetTokenAppContainerNumber@@YAJPEAXPEAK@Z; GetTokenAppContainerNumber(void *,ulong *)
0x180062405  mov     ebx, eax
0x180062407  jmp     short loc_180062461
0x180062409  cmp     cs:byte_180299E8C, 0
0x180062410  jz      short loc_18006241E
0x180062412  mov     eax, cs:dword_180299E88
0x180062418  xor     ebx, ebx
0x18006241a  mov     [rdi], eax
0x18006241c  jmp     short loc_18006246C
0x18006241e  mov     [rsp+28h+hObject], 0
0x180062427  call    cs:__imp_GetCurrentProcessId
0x18006242d  mov     edx, eax; unsigned int
0x18006242f  lea     r8, [rsp+28h+hObject]; void **
0x180062434  call    ?GetProcessToken@@YAJKKPEAPEAX@Z; GetProcessToken(ulong,ulong,void * *)
0x180062439  mov     ebx, eax
0x18006243b  test    eax, eax
0x18006243d  js      short loc_18006246C
0x18006243f  mov     rcx, [rsp+28h+hObject]; void *
0x180062444  mov     rdx, rdi; unsigned int *
0x180062447  call    ?GetTokenAppContainerNumber@@YAJPEAXPEAK@Z; GetTokenAppContainerNumber(void *,ulong *)
0x18006244c  mov     ebx, eax
0x18006244e  test    eax, eax
0x180062450  js      short loc_180062461
0x180062452  mov     eax, [rdi]
0x180062454  mov     cs:dword_180299E88, eax
0x18006245a  mov     cs:byte_180299E8C, 1
0x180062461  mov     rcx, [rsp+28h+hObject]; hObject
0x180062466  call    cs:__imp_CloseHandle
0x18006246c  mov     eax, ebx
0x18006246e  mov     rbx, [rsp+28h+arg_0]
0x180062473  add     rsp, 20h
0x180062477  pop     rdi
0x180062478  retn
```
