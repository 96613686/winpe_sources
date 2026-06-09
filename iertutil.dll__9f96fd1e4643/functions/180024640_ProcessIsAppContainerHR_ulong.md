# ProcessIsAppContainerHR(ulong)

- ea: `0x180024640`
- end: `0x1800246e1`
- name: `?ProcessIsAppContainerHR@@YAJK@Z`
- size: `161`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022fd0`
- `0x180023d98`
- `0x180024960`

## callees

- `0x180024640`
- `0x180025024`
- `0x180025180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002465e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800246ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002465e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800246ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024698`

## pseudocode

```c
__int64 __fastcall ProcessIsAppContainerHR(DWORD a1)
{
  DWORD CurrentProcessId; // eax
  __int64 v3; // rcx
  int ProcessToken; // ebx
  int IsAppContainerHR; // eax
  __int64 v7; // rcx
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  if ( a1 && a1 != GetCurrentProcessId() )
  {
    hObject = 0;
    ProcessToken = GetProcessToken(v7, a1, &hObject);
    if ( ProcessToken < 0 )
      return (unsigned int)ProcessToken;
    ProcessToken = TokenIsAppContainerHR(hObject);
    goto LABEL_6;
  }
  if ( byte_180299FFE )
    return (unsigned int)dword_18029AC50;
  hObject = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessToken = GetProcessToken(v3, CurrentProcessId, &hObject);
  if ( ProcessToken >= 0 )
  {
    IsAppContainerHR = TokenIsAppContainerHR(hObject);
    ProcessToken = IsAppContainerHR;
    if ( IsAppContainerHR >= 0 )
    {
      dword_18029AC50 = IsAppContainerHR;
      byte_180299FFE = 1;
    }
LABEL_6:
    CloseHandle(hObject);
  }
  return (unsigned int)ProcessToken;
}

```

## disassembly

```asm
0x180024640  push    rbx
0x180024642  sub     rsp, 20h
0x180024646  mov     ebx, ecx
0x180024648  test    ecx, ecx
0x18002464a  jnz     short loc_1800246AE
0x18002464c  cmp     cs:byte_180299FFE, 0
0x180024653  jnz     short loc_1800246A6
0x180024655  mov     [rsp+28h+hObject], 0
0x18002465e  call    cs:__imp_GetCurrentProcessId
0x180024664  mov     edx, eax; unsigned int
0x180024666  lea     r8, [rsp+28h+hObject]; void **
0x18002466b  call    ?GetProcessToken@@YAJKKPEAPEAX@Z; GetProcessToken(ulong,ulong,void * *)
0x180024670  mov     ebx, eax
0x180024672  test    eax, eax
0x180024674  js      short loc_18002469E
0x180024676  mov     rcx, [rsp+28h+hObject]; TokenHandle
0x18002467b  call    ?TokenIsAppContainerHR@@YAJPEAX@Z; TokenIsAppContainerHR(void *)
0x180024680  mov     ebx, eax
0x180024682  test    eax, eax
0x180024684  js      short loc_180024693
0x180024686  mov     cs:dword_18029AC50, eax
0x18002468c  mov     cs:byte_180299FFE, 1
0x180024693  mov     rcx, [rsp+28h+hObject]; hObject
0x180024698  call    cs:__imp_CloseHandle
0x18002469e  mov     eax, ebx
0x1800246a0  add     rsp, 20h
0x1800246a4  pop     rbx
0x1800246a5  retn
0x1800246a6  mov     ebx, cs:dword_18029AC50
0x1800246ac  jmp     short loc_18002469E
0x1800246ae  call    cs:__imp_GetCurrentProcessId
0x1800246b4  cmp     ebx, eax
0x1800246b6  jz      short loc_18002464C
0x1800246b8  lea     r8, [rsp+28h+hObject]; void **
0x1800246bd  mov     [rsp+28h+hObject], 0
0x1800246c6  mov     edx, ebx; unsigned int
0x1800246c8  call    ?GetProcessToken@@YAJKKPEAPEAX@Z; GetProcessToken(ulong,ulong,void * *)
0x1800246cd  mov     ebx, eax
0x1800246cf  test    eax, eax
0x1800246d1  js      short loc_18002469E
0x1800246d3  mov     rcx, [rsp+28h+hObject]; TokenHandle
0x1800246d8  call    ?TokenIsAppContainerHR@@YAJPEAX@Z; TokenIsAppContainerHR(void *)
0x1800246dd  mov     ebx, eax
0x1800246df  jmp     short loc_180024693
```
