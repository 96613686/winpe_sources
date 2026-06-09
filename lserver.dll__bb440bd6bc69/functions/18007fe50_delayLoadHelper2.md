# __delayLoadHelper2

- ea: `0x18007fe50`
- end: `0x180080197`
- name: `__delayLoadHelper2`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800030c6`

## callees

- `0x18007fb14`
- `0x18007fd8c`
- `0x18007fdec`
- `0x18007fe50`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18007ff00`
- `KERNEL32!RaiseException` at `0x180080009`
- `KERNEL32!RaiseException` at `0x18008012e`
- `KERNEL32!RaiseException` at `0x18007ff00`
- `KERNEL32!RaiseException` at `0x180080009`
- `KERNEL32!RaiseException` at `0x18008012e`
- `KERNEL32!LoadLibraryExA` at `0x18007ffaa`
- `KERNEL32!LoadLibraryExA` at `0x18007ffaa`
- `KERNEL32!FreeLibrary` at `0x180080049`
- `KERNEL32!FreeLibrary` at `0x180080049`
- `KERNEL32!GetLastError` at `0x18007ffbe`
- `KERNEL32!GetLastError` at `0x1800800e3`
- `KERNEL32!GetLastError` at `0x18007ffbe`
- `KERNEL32!GetLastError` at `0x1800800e3`
- `KERNEL32!GetProcAddress` at `0x1800800cf`
- `KERNEL32!GetProcAddress` at `0x1800800cf`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(_DWORD *a1, char *a2)
{
  const CHAR *v4; // rax
  volatile signed __int64 *v5; // r15
  char *v6; // rcx
  __int64 v7; // r13
  __int16 *v8; // rdx
  char *v9; // r13
  __int64 v10; // r8
  HMODULE Library; // rbx
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64, _DWORD *); // r8
  FARPROC ProcAddress; // rdi
  __int64 v18; // rax
  __int64 v19; // r8
  signed __int64 v20; // r15
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  _DWORD v27[2]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD *v28; // [rsp+28h] [rbp-48h]
  char *v29; // [rsp+30h] [rbp-40h]
  LPCSTR lpLibFileName; // [rsp+38h] [rbp-38h]
  BOOL v31; // [rsp+40h] [rbp-30h]
  int v32; // [rsp+44h] [rbp-2Ch]
  LPCSTR lpProcName; // [rsp+48h] [rbp-28h]
  HMODULE v34; // [rsp+50h] [rbp-20h]
  INT_PTR (__stdcall *v35)(); // [rsp+58h] [rbp-18h]
  DWORD LastError; // [rsp+60h] [rbp-10h]
  ULONG_PTR Arguments; // [rsp+A0h] [rbp+30h] BYREF

  v32 = 0;
  v27[1] = 0;
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v4 = (char *)&_ImageBase + (unsigned int)a1[1];
  v5 = (volatile signed __int64 *)((char *)&_ImageBase + (unsigned int)a1[2]);
  v6 = (char *)&_ImageBase + (unsigned int)a1[3];
  v7 = (unsigned int)a1[5];
  v8 = (__int16 *)((char *)&_ImageBase + (unsigned int)a1[4]);
  v31 = 0;
  v9 = (char *)&_ImageBase + v7;
  lpProcName = 0;
  v34 = 0;
  v35 = 0;
  LastError = 0;
  v10 = (unsigned int)a1[7];
  lpLibFileName = v4;
  LODWORD(v4) = *a1;
  LODWORD(Arguments) = v10;
  v27[0] = 72;
  v28 = a1;
  v29 = a2;
  if ( ((unsigned __int8)v4 & 1) == 0 )
  {
    Arguments = (ULONG_PTR)v27;
    DloadReleaseSectionWriteAccess(v6, v8, v10);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v5;
  v13 = (a2 - v6) >> 3;
  v14 = (unsigned int)v13;
  v31 = *(_QWORD *)&v8[4 * (unsigned int)v13] >= 0LL;
  if ( v31 )
  {
    v15 = *(unsigned int *)&v8[4 * (unsigned int)v13];
    v8 = &word_180000002;
    lpProcName = (char *)&word_180000002 + v15;
  }
  else
  {
    LODWORD(lpProcName) = (unsigned __int16)v8[4 * (unsigned int)v13];
  }
  v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
  ProcAddress = 0;
  if ( !_pfnDefaultDliFailureHook2
    || (v18 = _pfnDefaultDliFailureHook2(0, v27),
        v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2,
        (ProcAddress = (FARPROC)v18) == 0) )
  {
    if ( !Library )
    {
      if ( !v16 || (Library = (HMODULE)v16(1, v27)) == 0 )
      {
        Library = LoadLibraryExA(lpLibFileName, 0, 0);
        if ( !Library )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, v27)) == 0 )
          {
            Arguments = (ULONG_PTR)v27;
            DloadReleaseSectionWriteAccess(v14, v8, v19);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v35;
          }
        }
      }
      v20 = _InterlockedCompareExchange64(v5, (signed __int64)Library, 0);
      if ( v20 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v20 )
          Library = (HMODULE)v20;
      }
      else if ( Library != (HMODULE)-1LL && a1[6] )
      {
        NewUnloadInfo(a1);
      }
      v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
    }
    v34 = Library;
    if ( v16 )
    {
      v21 = v16(2, v27);
      v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
      ProcAddress = (FARPROC)v21;
    }
    if ( !ProcAddress )
    {
      if ( !a1[5]
        || !a1[7]
        || (v22 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v22) != 17744)
        || (v14 = (unsigned int)Arguments, *(_DWORD *)((char *)Library + v22 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + v22 + 48)
        || (ProcAddress = *(FARPROC *)&v9[8 * (unsigned int)v13]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, lpProcName);
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(4, v27)) == 0 )
          {
            Arguments = (ULONG_PTR)v27;
            DloadReleaseSectionWriteAccess(v14, v8, v23);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess(v25, v24, v26);
            ProcAddress = v35;
          }
        }
        v16 = (__int64 (__fastcall *)(__int64, _DWORD *))_pfnDefaultDliFailureHook2;
      }
    }
    *(_QWORD *)a2 = ProcAddress;
  }
  if ( v16 )
  {
    LastError = 0;
    v34 = Library;
    v35 = ProcAddress;
    v16(5, v27);
  }
  DloadReleaseSectionWriteAccess(v14, v8, v16);
  return ProcAddress;
}

```

## disassembly

```asm
0x18007fe50  mov     [rsp-28h+arg_8], rbx
0x18007fe55  mov     [rsp-28h+arg_10], rsi
0x18007fe5a  mov     [rsp-28h+arg_18], rdi
0x18007fe5f  push    rbp
0x18007fe60  push    r12
0x18007fe62  push    r13
0x18007fe64  push    r14
0x18007fe66  push    r15
0x18007fe68  mov     rbp, rsp
0x18007fe6b  sub     rsp, 70h
0x18007fe6f  xor     eax, eax
0x18007fe71  mov     r12, rdx
0x18007fe74  and     [rbp+var_2C], eax
0x18007fe77  mov     rsi, rcx
0x18007fe7a  mov     [rbp+var_4C], eax
0x18007fe7d  and     [rbp+var_4C], eax
0x18007fe80  call    DloadAcquireSectionWriteAccess
0x18007fe85  mov     eax, [rsi+4]
0x18007fe88  lea     r8, __ImageBase
0x18007fe8f  mov     r15d, [rsi+8]
0x18007fe93  add     rax, r8
0x18007fe96  mov     ecx, [rsi+0Ch]
0x18007fe99  add     r15, r8
0x18007fe9c  mov     edx, [rsi+10h]
0x18007fe9f  add     rcx, r8
0x18007fea2  mov     r13d, [rsi+14h]
0x18007fea6  add     rdx, r8
0x18007fea9  and     [rbp+var_30], 0
0x18007fead  add     r13, r8
0x18007feb0  and     [rbp+lpProcName], 0
0x18007feb5  and     [rbp+var_20], 0
0x18007feba  and     [rbp+var_18], 0
0x18007febf  and     [rbp+var_10], 0
0x18007fec3  mov     r8d, [rsi+1Ch]
0x18007fec7  mov     [rbp+lpLibFileName], rax
0x18007fecb  mov     eax, [rsi]
0x18007fecd  mov     dword ptr [rbp+Arguments], r8d
0x18007fed1  mov     [rbp+var_50], 48h ; 'H'
0x18007fed8  mov     [rbp+var_48], rsi
0x18007fedc  mov     [rbp+var_40], r12
0x18007fee0  test    al, 1
0x18007fee2  jnz     short loc_18007FF13
0x18007fee4  lea     rax, [rbp+var_50]
0x18007fee8  mov     [rbp+Arguments], rax
0x18007feec  call    DloadReleaseSectionWriteAccess
0x18007fef1  xor     edx, edx; dwExceptionFlags
0x18007fef3  lea     r9, [rbp+Arguments]; lpArguments
0x18007fef7  mov     ecx, 0C06D0057h; dwExceptionCode
0x18007fefc  lea     r8d, [rdx+1]; nNumberOfArguments
0x18007ff00  call    cs:__imp_RaiseException
0x18007ff07  nop     dword ptr [rax+rax+00h]
0x18007ff0c  xor     eax, eax
0x18007ff0e  jmp     loc_180080178
0x18007ff13  mov     rbx, [r15]
0x18007ff16  xor     eax, eax
0x18007ff18  mov     r14, r12
0x18007ff1b  sub     r14, rcx
0x18007ff1e  sar     r14, 3
0x18007ff22  mov     ecx, r14d
0x18007ff25  cmp     [rdx+rcx*8], rax
0x18007ff29  setnl   al
0x18007ff2c  mov     [rbp+var_30], eax
0x18007ff2f  test    eax, eax
0x18007ff31  jz      short loc_18007FF46
0x18007ff33  mov     eax, [rdx+rcx*8]
0x18007ff36  lea     rdx, word_180000002
0x18007ff3d  add     rax, rdx
0x18007ff40  mov     [rbp+lpProcName], rax
0x18007ff44  jmp     short loc_18007FF4D
0x18007ff46  movzx   eax, word ptr [rdx+rcx*8]
0x18007ff4a  mov     dword ptr [rbp+lpProcName], eax
0x18007ff4d  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18007ff54  xor     edi, edi
0x18007ff56  test    r8, r8
0x18007ff59  jz      short loc_18007FF7C
0x18007ff5b  lea     rdx, [rbp+var_50]
0x18007ff5f  xor     ecx, ecx
0x18007ff61  mov     rax, r8
0x18007ff64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ff69  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18007ff70  mov     rdi, rax
0x18007ff73  test    rax, rax
0x18007ff76  jnz     loc_18008014E
0x18007ff7c  test    rbx, rbx
0x18007ff7f  jnz     loc_180080063
0x18007ff85  test    r8, r8
0x18007ff88  jz      short loc_18007FFA1
0x18007ff8a  lea     rdx, [rbp+var_50]
0x18007ff8e  mov     rax, r8
0x18007ff91  lea     ecx, [rbx+1]
0x18007ff94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ff99  mov     rbx, rax
0x18007ff9c  test    rax, rax
0x18007ff9f  jnz     short loc_18008001E
0x18007ffa1  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18007ffa5  xor     r8d, r8d; dwFlags
0x18007ffa8  xor     edx, edx; hFile
0x18007ffaa  call    cs:__imp_LoadLibraryExA
0x18007ffb1  nop     dword ptr [rax+rax+00h]
0x18007ffb6  mov     rbx, rax
0x18007ffb9  test    rax, rax
0x18007ffbc  jnz     short loc_18008001E
0x18007ffbe  call    cs:__imp_GetLastError
0x18007ffc5  nop     dword ptr [rax+rax+00h]
0x18007ffca  mov     [rbp+var_10], eax
0x18007ffcd  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18007ffd4  test    rax, rax
0x18007ffd7  jz      short loc_18007FFED
0x18007ffd9  lea     rdx, [rbp+var_50]
0x18007ffdd  lea     ecx, [rbx+3]
0x18007ffe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ffe5  mov     rbx, rax
0x18007ffe8  test    rax, rax
0x18007ffeb  jnz     short loc_18008001E
0x18007ffed  lea     rax, [rbp+var_50]
0x18007fff1  mov     [rbp+Arguments], rax
0x18007fff5  call    DloadReleaseSectionWriteAccess
0x18007fffa  xor     edx, edx; dwExceptionFlags
0x18007fffc  lea     r9, [rbp+Arguments]; lpArguments
0x180080000  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180080005  lea     r8d, [rdx+1]; nNumberOfArguments
0x180080009  call    cs:__imp_RaiseException
0x180080010  nop     dword ptr [rax+rax+00h]
0x180080015  mov     rax, [rbp+var_18]
0x180080019  jmp     loc_180080178
0x18008001e  xor     eax, eax
0x180080020  lock cmpxchg [r15], rbx
0x180080025  mov     r15, rax
0x180080028  jnz     short loc_180080040
0x18008002a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18008002e  jz      short loc_18008005C
0x180080030  cmp     dword ptr [rsi+18h], 0
0x180080034  jz      short loc_18008005C
0x180080036  mov     rcx, rsi
0x180080039  call    NewUnloadInfo
0x18008003e  jmp     short loc_18008005C
0x180080040  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180080044  jz      short loc_180080055
0x180080046  mov     rcx, rbx; hLibModule
0x180080049  call    cs:__imp_FreeLibrary
0x180080050  nop     dword ptr [rax+rax+00h]
0x180080055  cmp     rbx, r15
0x180080058  cmovnz  rbx, r15
0x18008005c  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180080063  mov     [rbp+var_20], rbx
0x180080067  test    r8, r8
0x18008006a  jz      short loc_180080087
0x18008006c  lea     rdx, [rbp+var_50]
0x180080070  mov     ecx, 2
0x180080075  mov     rax, r8
0x180080078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008007d  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180080084  mov     rdi, rax
0x180080087  test    rdi, rdi
0x18008008a  jnz     loc_18008014A
0x180080090  cmp     [rsi+14h], edi
0x180080093  jz      short loc_1800800C8
0x180080095  cmp     [rsi+1Ch], edi
0x180080098  jz      short loc_1800800C8
0x18008009a  movsxd  rax, dword ptr [rbx+3Ch]
0x18008009e  cmp     dword ptr [rax+rbx], 4550h
0x1800800a5  jnz     short loc_1800800C8
0x1800800a7  mov     ecx, dword ptr [rbp+Arguments]
0x1800800aa  cmp     [rax+rbx+8], ecx
0x1800800ae  jnz     short loc_1800800C8
0x1800800b0  cmp     rbx, [rax+rbx+30h]
0x1800800b5  jnz     short loc_1800800C8
0x1800800b7  mov     eax, r14d
0x1800800ba  mov     rdi, [r13+rax*8+0]
0x1800800bf  test    rdi, rdi
0x1800800c2  jnz     loc_18008014A
0x1800800c8  mov     rdx, [rbp+lpProcName]; lpProcName
0x1800800cc  mov     rcx, rbx; hModule
0x1800800cf  call    cs:__imp_GetProcAddress
0x1800800d6  nop     dword ptr [rax+rax+00h]
0x1800800db  mov     rdi, rax
0x1800800de  test    rax, rax
0x1800800e1  jnz     short loc_180080143
0x1800800e3  call    cs:__imp_GetLastError
0x1800800ea  nop     dword ptr [rax+rax+00h]
0x1800800ef  mov     [rbp+var_10], eax
0x1800800f2  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800800f9  test    rax, rax
0x1800800fc  jz      short loc_180080112
0x1800800fe  lea     rdx, [rbp+var_50]
0x180080102  lea     ecx, [rdi+4]
0x180080105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008010a  mov     rdi, rax
0x18008010d  test    rax, rax
0x180080110  jnz     short loc_180080143
0x180080112  lea     rax, [rbp+var_50]
0x180080116  mov     [rbp+Arguments], rax
0x18008011a  call    DloadReleaseSectionWriteAccess
0x18008011f  xor     edx, edx; dwExceptionFlags
0x180080121  lea     r9, [rbp+Arguments]; lpArguments
0x180080125  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18008012a  lea     r8d, [rdx+1]; nNumberOfArguments
0x18008012e  call    cs:__imp_RaiseException
0x180080135  nop     dword ptr [rax+rax+00h]
0x18008013a  call    DloadAcquireSectionWriteAccess
0x18008013f  mov     rdi, [rbp+var_18]
0x180080143  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18008014a  mov     [r12], rdi
0x18008014e  test    r8, r8
0x180080151  jz      short loc_180080170
0x180080153  and     [rbp+var_10], 0
0x180080157  lea     rdx, [rbp+var_50]
0x18008015b  mov     ecx, 5
0x180080160  mov     [rbp+var_20], rbx
0x180080164  mov     rax, r8
0x180080167  mov     [rbp+var_18], rdi
0x18008016b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080170  call    DloadReleaseSectionWriteAccess
0x180080175  mov     rax, rdi
0x180080178  lea     r11, [rsp+70h+var_s0]
0x18008017d  mov     rbx, [r11+38h]
0x180080181  mov     rsi, [r11+40h]
0x180080185  mov     rdi, [r11+48h]
0x180080189  mov     rsp, r11
0x18008018c  pop     r15
0x18008018e  pop     r14
0x180080190  pop     r13
0x180080192  pop     r12
0x180080194  pop     rbp
0x180080195  retn
```
