# NGENService::IdleGetLastInputInfo(ulong,ulong *)

- ea: `0x180007050`
- end: `0x18000712f`
- name: `?IdleGetLastInputInfo@NGENService@@YAHKPEAK@Z`
- size: `223`
- prototype: `__int64 __fastcall(NGENService *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180007130`

## callees

- `0x180007050`
- `0x180007d04`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000709b`
- `KERNEL32!LoadLibraryExW` at `0x18000709b`
- `KERNEL32!GetProcAddress` at `0x1800070b0`
- `KERNEL32!GetProcAddress` at `0x1800070b0`

## string_xrefs

- `0x180007092`: `user32.dll`

## pseudocode

```c
__int64 __fastcall NGENService::IdleGetLastInputInfo(NGENService *this, int *a2, unsigned int *a3)
{
  int v4; // edi
  int v5; // ebx
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  int v8; // edi
  int v10; // [rsp+40h] [rbp+18h] BYREF
  int v11; // [rsp+44h] [rbp+1Ch]

  v4 = (int)this;
  v5 = 0;
  if ( IsCLRGetIdleMinutesAvailable() )
  {
    while ( !qword_18006FF50 )
    {
      if ( bGetIdleMinutesProbed || !IsCLRGetIdleMinutesAvailable() )
        goto LABEL_10;
    }
    v5 = qword_18006FF50(0);
LABEL_10:
    v8 = 60000 * v5;
  }
  else
  {
    ProcAddress = (FARPROC)qword_18006FF48;
    v10 = 8;
    if ( !qword_18006FF48 )
    {
      if ( bGetLastInputInfoProbed )
        return 0;
      Library = LoadLibraryExW(L"user32.dll", 0, 0);
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "GetLastInputInfo");
        qword_18006FF48 = (__int64)ProcAddress;
      }
      else
      {
        ProcAddress = (FARPROC)qword_18006FF48;
      }
      bGetLastInputInfoProbed = 1;
      if ( !ProcAddress )
        return 0;
    }
    if ( !((unsigned int (__fastcall *)(int *))ProcAddress)(&v10) )
      return 0;
    v8 = v4 - v11;
  }
  *a2 = v8;
  return 1;
}

```

## disassembly

```asm
0x180007050  mov     [rsp+arg_0], rbx
0x180007055  mov     [rsp+arg_8], rsi
0x18000705a  push    rdi
0x18000705b  sub     rsp, 20h
0x18000705f  mov     rsi, rdx
0x180007062  mov     edi, ecx
0x180007064  call    ?IsCLRGetIdleMinutesAvailable@@YA_NXZ; IsCLRGetIdleMinutesAvailable(void)
0x180007069  xor     ebx, ebx
0x18000706b  test    al, al
0x18000706d  jnz     short loc_1800070D0
0x18000706f  mov     rax, cs:qword_18006FF48
0x180007076  mov     [rsp+28h+arg_10], 8
0x18000707e  test    rax, rax
0x180007081  jnz     short loc_180007101
0x180007083  cmp     cs:?bGetLastInputInfoProbed@@3_NA, bl; bool bGetLastInputInfoProbed
0x180007089  jnz     loc_180007110
0x18000708f  xor     r8d, r8d; dwFlags
0x180007092  lea     rcx, aUser32Dll_0; "user32.dll"
0x180007099  xor     edx, edx; hFile
0x18000709b  call    cs:__imp_LoadLibraryExW
0x1800070a1  test    rax, rax
0x1800070a4  jz      short loc_1800070EE
0x1800070a6  lea     rdx, aGetlastinputin; "GetLastInputInfo"
0x1800070ad  mov     rcx, rax; hModule
0x1800070b0  call    cs:__imp_GetProcAddress
0x1800070b6  mov     cs:qword_18006FF48, rax
0x1800070bd  jmp     short loc_1800070F5
0x1800070bf  cmp     cs:?bGetIdleMinutesProbed@@3_NA, bl; bool bGetIdleMinutesProbed
0x1800070c5  jnz     short loc_1800070E6
0x1800070c7  call    ?IsCLRGetIdleMinutesAvailable@@YA_NXZ; IsCLRGetIdleMinutesAvailable(void)
0x1800070cc  test    al, al
0x1800070ce  jz      short loc_1800070E6
0x1800070d0  mov     rax, cs:qword_18006FF50
0x1800070d7  test    rax, rax
0x1800070da  jz      short loc_1800070BF
0x1800070dc  xor     ecx, ecx
0x1800070de  call    cs:__guard_dispatch_icall_fptr
0x1800070e4  mov     ebx, eax
0x1800070e6  imul    edi, ebx, 0EA60h
0x1800070ec  jmp     short loc_180007118
0x1800070ee  mov     rax, cs:qword_18006FF48
0x1800070f5  mov     cs:?bGetLastInputInfoProbed@@3_NA, 1; bool bGetLastInputInfoProbed
0x1800070fc  test    rax, rax
0x1800070ff  jz      short loc_180007110
0x180007101  lea     rcx, [rsp+28h+arg_10]
0x180007106  call    cs:__guard_dispatch_icall_fptr
0x18000710c  test    eax, eax
0x18000710e  jnz     short loc_180007114
0x180007110  xor     eax, eax
0x180007112  jmp     short loc_18000711F
0x180007114  sub     edi, [rsp+28h+arg_14]
0x180007118  mov     [rsi], edi
0x18000711a  mov     eax, 1
0x18000711f  mov     rbx, [rsp+28h+arg_0]
0x180007124  mov     rsi, [rsp+28h+arg_8]
0x180007129  add     rsp, 20h
0x18000712d  pop     rdi
0x18000712e  retn
```
