# FwpQueueReresolveRequest

- ea: `0x18003901c`
- end: `0x18003922d`
- name: `FwpQueueReresolveRequest`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180038ec4`

## callees

- `0x1800034e0`
- `0x180005fc8`
- `0x180006230`
- `0x180007e38`
- `0x18000d7a8`
- `0x180011984`
- `0x180012bd0`
- `0x18003901c`
- `0x180039234`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800390b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800390b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800391e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800391e3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800391a2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800391a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800390fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800391cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800390fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800391cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039165`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039165`

## string_xrefs

- `0x1800390a9`: `fwpuclnt.dll`

## pseudocode

```c
__int64 __fastcall FwpQueueReresolveRequest(void **a1, PSID *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 LastError; // r8
  const char *v7; // rdx
  HMODULE phModule; // [rsp+38h] [rbp-30h] BYREF

  phModule = 0;
  v4 = WfpMemAlloc(0x28u, 8u);
  if ( !v4 )
  {
    v4 = WfpStringCopy(*a1);
    if ( !v4 )
    {
      v4 = FwpSidCopy(*a2, (_QWORD *)0x18);
      if ( !v4 )
      {
        if ( !GetModuleHandleExA(0, "fwpuclnt.dll", &phModule) )
        {
          LastError = GetLastError();
          v7 = "GetModuleHandleA";
LABEL_6:
          v4 = WfpReportSysErrorAsWinError(v5, v7, LastError);
          goto LABEL_19;
        }
        WfpCriticalSectionEnterBusyWait(&gNameCacheState);
        if ( byte_18007C401 )
        {
          LeaveCriticalSection(&gNameCacheState);
          LastError = 641;
          v7 = "FwpQueueReresolveRequest";
          goto LABEL_6;
        }
        if ( *(__int64 **)(qword_18007C430 + 8) != &qword_18007C430 )
          __fastfail(3u);
        MEMORY[0] = qword_18007C430;
        MEMORY[8] = &qword_18007C430;
        *(_QWORD *)(qword_18007C430 + 8) = 0;
        qword_18007C430 = 0;
        if ( !hObject || (_BYTE)word_18007C402 )
        {
          if ( (_BYTE)word_18007C402 )
          {
            if ( hObject )
              CloseHandle(hObject);
            hObject = 0;
            LOBYTE(word_18007C402) = 0;
          }
          hObject = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)FwpWorkerThread, 0, 0, 0);
          hLibModule = phModule;
          phModule = 0;
        }
        LeaveCriticalSection(&gNameCacheState);
      }
    }
  }
LABEL_19:
  if ( phModule )
    FreeLibrary(phModule);
  if ( v4 )
  {
    FwpDestroyWorkEntry(0);
    WfpReportError(v4, "FwpQueueReresolveRequest");
  }
  return v4;
}

```

## disassembly

```asm
0x18003901c  mov     r11, rsp
0x18003901f  mov     [r11+18h], rbx
0x180039023  push    rsi
0x180039024  push    rdi
0x180039025  push    r14
0x180039027  sub     rsp, 50h
0x18003902b  mov     rax, cs:__security_cookie
0x180039032  xor     rax, rsp
0x180039035  mov     [rsp+68h+var_28], rax
0x18003903a  mov     r14, rdx
0x18003903d  mov     qword ptr [r11-38h], 0
0x180039045  mov     edx, 8; dwFlags
0x18003904a  mov     qword ptr [r11-30h], 0
0x180039052  mov     rsi, rcx
0x180039055  lea     r8, [r11-38h]
0x180039059  lea     ecx, [rdx+20h]; dwBytes
0x18003905c  call    WfpMemAlloc
0x180039061  mov     rdi, [rsp+68h+var_38]
0x180039066  mov     rbx, rax
0x180039069  test    rax, rax
0x18003906c  jnz     loc_1800391D9
0x180039072  mov     rcx, [rsi]; Src
0x180039075  lea     r8, [rdi+10h]
0x180039079  call    WfpStringCopy
0x18003907e  mov     rbx, rax
0x180039081  test    rax, rax
0x180039084  jnz     loc_1800391D9
0x18003908a  mov     rcx, [r14]; pSourceSid
0x18003908d  lea     rdx, [rdi+18h]
0x180039091  call    FwpSidCopy
0x180039096  mov     rbx, rax
0x180039099  test    rax, rax
0x18003909c  jnz     loc_1800391D9
0x1800390a2  lea     r8, [rsp+68h+phModule]; phModule
0x1800390a7  xor     ecx, ecx; dwFlags
0x1800390a9  lea     rdx, aFwpuclntDll_0; "fwpuclnt.dll"
0x1800390b0  call    cs:__imp_GetModuleHandleExA
0x1800390b7  nop     dword ptr [rax+rax+00h]
0x1800390bc  test    eax, eax
0x1800390be  jnz     short loc_1800390E3
0x1800390c0  call    cs:__imp_GetLastError
0x1800390c7  nop     dword ptr [rax+rax+00h]
0x1800390cc  mov     r8d, eax
0x1800390cf  lea     rdx, aGetmodulehandl_0; "GetModuleHandleA"
0x1800390d6  call    WfpReportSysErrorAsWinError
0x1800390db  mov     rbx, rax
0x1800390de  jmp     loc_1800391D9
0x1800390e3  lea     rsi, gNameCacheState
0x1800390ea  mov     rcx, rsi
0x1800390ed  call    WfpCriticalSectionEnterBusyWait
0x1800390f2  cmp     cs:byte_18007C401, 0
0x1800390f9  jz      short loc_180039119
0x1800390fb  mov     rcx, rsi; lpCriticalSection
0x1800390fe  call    cs:__imp_LeaveCriticalSection
0x180039105  nop     dword ptr [rax+rax+00h]
0x18003910a  mov     r8d, 281h
0x180039110  lea     rdx, aFwpqueuerereso; "FwpQueueReresolveRequest"
0x180039117  jmp     short loc_1800390D6
0x180039119  mov     rax, cs:qword_18007C430
0x180039120  lea     rcx, qword_18007C430
0x180039127  cmp     [rax+8], rcx
0x18003912b  jz      short loc_180039134
0x18003912d  mov     ecx, 3
0x180039132  int     29h; Win8: RtlFailFast(ecx)
0x180039134  mov     [rdi], rax
0x180039137  mov     [rdi+8], rcx
0x18003913b  mov     [rax+8], rdi
0x18003913f  mov     rcx, cs:hObject; hObject
0x180039146  mov     al, byte ptr cs:word_18007C402
0x18003914c  mov     cs:qword_18007C430, rdi
0x180039153  test    rcx, rcx
0x180039156  jz      short loc_18003915C
0x180039158  test    al, al
0x18003915a  jz      short loc_1800391CA
0x18003915c  test    al, al
0x18003915e  jz      short loc_180039183
0x180039160  test    rcx, rcx
0x180039163  jz      short loc_180039171
0x180039165  call    cs:__imp_CloseHandle
0x18003916c  nop     dword ptr [rax+rax+00h]
0x180039171  mov     cs:hObject, 0
0x18003917c  mov     byte ptr cs:word_18007C402, 0
0x180039183  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18003918c  lea     r8, FwpWorkerThread; lpStartAddress
0x180039193  xor     r9d, r9d; lpParameter
0x180039196  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18003919e  xor     edx, edx; dwStackSize
0x1800391a0  xor     ecx, ecx; lpThreadAttributes
0x1800391a2  call    cs:__imp_CreateThread
0x1800391a9  nop     dword ptr [rax+rax+00h]
0x1800391ae  mov     cs:hObject, rax
0x1800391b5  mov     rax, [rsp+68h+phModule]
0x1800391ba  mov     cs:hLibModule, rax
0x1800391c1  mov     [rsp+68h+phModule], 0
0x1800391ca  mov     rcx, rsi; lpCriticalSection
0x1800391cd  call    cs:__imp_LeaveCriticalSection
0x1800391d4  nop     dword ptr [rax+rax+00h]
0x1800391d9  mov     rcx, [rsp+68h+phModule]; hLibModule
0x1800391de  test    rcx, rcx
0x1800391e1  jz      short loc_1800391EF
0x1800391e3  call    cs:__imp_FreeLibrary
0x1800391ea  nop     dword ptr [rax+rax+00h]
0x1800391ef  test    rbx, rbx
0x1800391f2  jz      short loc_18003920B
0x1800391f4  mov     rcx, rdi
0x1800391f7  call    FwpDestroyWorkEntry
0x1800391fc  lea     rdx, aFwpqueuerereso; "FwpQueueReresolveRequest"
0x180039203  mov     rcx, rbx
0x180039206  call    WfpReportError
0x18003920b  mov     rax, rbx
0x18003920e  mov     rcx, [rsp+68h+var_28]
0x180039213  xor     rcx, rsp; StackCookie
0x180039216  call    __security_check_cookie
0x18003921b  mov     rbx, [rsp+68h+arg_10]
0x180039223  add     rsp, 50h
0x180039227  pop     r14
0x180039229  pop     rdi
0x18003922a  pop     rsi
0x18003922b  retn
```
