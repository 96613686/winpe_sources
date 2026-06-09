# ProcessDeviceDirectoriesToRemove

- ea: `0x18000829c`
- end: `0x1800083a4`
- name: `ProcessDeviceDirectoriesToRemove`
- size: `264`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180007dec`

## callees

- `0x180007c00`
- `0x180007f48`
- `0x180007fbc`
- `0x18000829c`
- `0x180008628`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008300`
- `KERNEL32!GetLastError` at `0x18000836d`
- `KERNEL32!GetLastError` at `0x180008300`
- `KERNEL32!GetLastError` at `0x18000836d`
- `SETUPAPI!pSetupFree` at `0x18000838a`
- `SETUPAPI!pSetupFree` at `0x18000838a`
- `SETUPAPI!pSetupStringTableDestroy` at `0x180008393`
- `SETUPAPI!pSetupStringTableDestroy` at `0x180008393`
- `SETUPAPI!pSetupStringTableInitialize` at `0x1800082f2`
- `SETUPAPI!pSetupStringTableInitialize` at `0x1800082f2`

## pseudocode

```c
__int64 __fastcall ProcessDeviceDirectoriesToRemove(__int64 a1)
{
  unsigned int valid; // ebx
  __int64 v3; // rax
  __int64 v4; // rsi
  const WCHAR *RedirectedFilePath; // rax
  const WCHAR *v6; // rbp
  int v8; // [rsp+60h] [rbp+8h] BYREF

  v8 = 0;
  if ( a1 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64, const char *))(a1 + 40))(
      *(_QWORD *)(a1 + 48),
      3,
      1,
      "Processing device directories");
    if ( (unsigned int)PnpCleanFilesNotifyCallback(a1) )
    {
      v3 = pSetupStringTableInitialize();
      v4 = v3;
      if ( v3 )
      {
        valid = PopulateValidDeviceDirectories(a1, v3, &v8);
        if ( !valid )
        {
          (*(void (**)(_QWORD, __int64, __int64, const char *, ...))(a1 + 40))(
            *(_QWORD *)(a1 + 48),
            4,
            1,
            "Found %d potential valid directories",
            v8);
          (*(void (__fastcall **)(_QWORD, __int64, __int64, const char *))(a1 + 40))(
            *(_QWORD *)(a1 + 48),
            4,
            1,
            "Cleaning unused device directories");
          RedirectedFilePath = (const WCHAR *)pUtilGetRedirectedFilePath();
          v6 = RedirectedFilePath;
          if ( RedirectedFilePath )
          {
            valid = CleanDeviceDirectories(a1, RedirectedFilePath, v4);
            pSetupFree(v6);
          }
          else
          {
            valid = GetLastError();
          }
        }
        pSetupStringTableDestroy(v4);
      }
      else
      {
        return GetLastError();
      }
    }
    else
    {
      return 1223;
    }
  }
  else
  {
    return 87;
  }
  return valid;
}

```

## disassembly

```asm
0x18000829c  push    rbx
0x18000829e  push    rbp
0x18000829f  push    rsi
0x1800082a0  push    rdi
0x1800082a1  sub     rsp, 38h
0x1800082a5  mov     [rsp+58h+arg_0], 0
0x1800082ad  mov     rdi, rcx
0x1800082b0  test    rcx, rcx
0x1800082b3  jnz     short loc_1800082BD
0x1800082b5  lea     ebx, [rcx+57h]
0x1800082b8  jmp     loc_180008399
0x1800082bd  mov     rcx, [rcx+30h]
0x1800082c1  lea     r9, aProcessingDevi_1; "Processing device directories"
0x1800082c8  mov     rax, [rdi+28h]
0x1800082cc  mov     ebp, 1
0x1800082d1  mov     r8d, ebp
0x1800082d4  lea     edx, [rbp+2]
0x1800082d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082dc  mov     rcx, rdi
0x1800082df  call    PnpCleanFilesNotifyCallback
0x1800082e4  test    eax, eax
0x1800082e6  jnz     short loc_1800082F2
0x1800082e8  mov     ebx, 4C7h
0x1800082ed  jmp     loc_180008399
0x1800082f2  call    cs:__imp_pSetupStringTableInitialize
0x1800082f8  mov     rsi, rax
0x1800082fb  test    rax, rax
0x1800082fe  jnz     short loc_18000830D
0x180008300  call    cs:__imp_GetLastError
0x180008306  mov     ebx, eax
0x180008308  jmp     loc_180008399
0x18000830d  lea     r8, [rsp+58h+arg_0]
0x180008312  mov     rdx, rsi
0x180008315  mov     rcx, rdi
0x180008318  call    PopulateValidDeviceDirectories
0x18000831d  mov     ebx, eax
0x18000831f  test    eax, eax
0x180008321  jnz     short loc_180008390
0x180008323  mov     ecx, [rsp+58h+arg_0]
0x180008327  lea     ebx, [rax+4]
0x18000832a  mov     rax, [rdi+28h]
0x18000832e  lea     r9, aFoundDPotentia; "Found %d potential valid directories"
0x180008335  mov     [rsp+58h+var_38], ecx
0x180008339  mov     edx, ebx
0x18000833b  mov     rcx, [rdi+30h]
0x18000833f  mov     r8d, ebp
0x180008342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008347  mov     rcx, [rdi+30h]
0x18000834b  lea     r9, aCleaningUnused; "Cleaning unused device directories"
0x180008352  mov     rax, [rdi+28h]
0x180008356  mov     r8d, ebp
0x180008359  mov     edx, ebx
0x18000835b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008360  call    pUtilGetRedirectedFilePath
0x180008365  mov     rbp, rax
0x180008368  test    rax, rax
0x18000836b  jnz     short loc_180008377
0x18000836d  call    cs:__imp_GetLastError
0x180008373  mov     ebx, eax
0x180008375  jmp     short loc_180008390
0x180008377  mov     r8, rsi
0x18000837a  mov     rdx, rbp
0x18000837d  mov     rcx, rdi
0x180008380  call    CleanDeviceDirectories
0x180008385  mov     ebx, eax
0x180008387  mov     rcx, rbp
0x18000838a  call    cs:__imp_pSetupFree
0x180008390  mov     rcx, rsi
0x180008393  call    cs:__imp_pSetupStringTableDestroy
0x180008399  mov     eax, ebx
0x18000839b  add     rsp, 38h
0x18000839f  pop     rdi
0x1800083a0  pop     rsi
0x1800083a1  pop     rbp
0x1800083a2  pop     rbx
0x1800083a3  retn
```
