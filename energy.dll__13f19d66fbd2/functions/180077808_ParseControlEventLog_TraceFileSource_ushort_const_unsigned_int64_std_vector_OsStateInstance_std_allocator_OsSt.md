# ParseControlEventLog(TraceFileSource,ushort const *,unsigned __int64,std::vector<OsStateInstance *,std::allocator<OsStateInstance *>> &)

- ea: `0x180077808`
- end: `0x1800778c2`
- name: `?ParseControlEventLog@@YAJW4TraceFileSource@@PEBG_KAEAV?$vector@PEAVOsStateInstance@@V?$allocator@PEAVOsStateInstance@@@std@@@std@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800778f0`

## callees

- `0x180008740`
- `0x180041c5c`
- `0x180045d70`
- `0x18004ca90`
- `0x18005956c`
- `0x180077808`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18007786d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18007786d`

## pseudocode

```c
HRESULT __fastcall ParseControlEventLog(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  HRESULT result; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( (_DWORD)a1 == 1 )
    return 0;
  if ( (_DWORD)a1 )
  {
    if ( (_DWORD)a1 != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3);
      return -2147024809;
    }
    result = StringCchCopyW(pszPath, (unsigned __int64)a2, a2);
  }
  else
  {
    result = GetSleepStudyTraceDirectory(pszPath);
  }
  if ( result >= 0 )
  {
    result = PathCchAppend(pszPath, 0x104u, L"SleepStudyControlTraceSession.etl");
    if ( result >= 0 )
    {
      result = ControlEventLogParser::Parse(pszPath);
      if ( !result )
        return 0;
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180077808  mov     [rsp+arg_0], rbx
0x18007780d  push    rdi
0x18007780e  sub     rsp, 240h
0x180077815  mov     rax, cs:__security_cookie
0x18007781c  xor     rax, rsp
0x18007781f  mov     [rsp+248h+var_18], rax
0x180077827  mov     rdi, r9
0x18007782a  mov     rbx, r8
0x18007782d  cmp     ecx, 1
0x180077830  jnz     short loc_180077836
0x180077832  xor     eax, eax
0x180077834  jmp     short loc_1800778A1
0x180077836  test    ecx, ecx
0x180077838  jnz     short loc_180077846
0x18007783a  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x18007783f  call    GetSleepStudyTraceDirectory
0x180077844  jmp     short loc_180077858
0x180077846  cmp     ecx, 2
0x180077849  jnz     short loc_180077897
0x18007784b  mov     r8, rdx; unsigned __int16 *
0x18007784e  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180077853  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180077858  test    eax, eax
0x18007785a  js      short loc_1800778A1
0x18007785c  lea     r8, aSleepstudycont; "SleepStudyControlTraceSession.etl"
0x180077863  mov     edx, 104h; cchPath
0x180077868  lea     rcx, [rsp+248h+pszPath]; pszPath
0x18007786d  call    cs:__imp_PathCchAppend
0x180077873  test    eax, eax
0x180077875  js      short loc_1800778A1
0x180077877  mov     r8, rdi
0x18007787a  lea     rcx, [rsp+248h+pszPath]; lpFileName
0x18007787f  mov     rdx, rbx
0x180077882  call    ?Parse@ControlEventLogParser@@SAKPEBG_KAEAV?$vector@PEAVOsStateInstance@@V?$allocator@PEAVOsStateInstance@@@std@@@std@@@Z; ControlEventLogParser::Parse(ushort const *,unsigned __int64,std::vector<OsStateInstance *> &)
0x180077887  test    eax, eax
0x180077889  jz      short loc_180077832
0x18007788b  jle     short loc_1800778A1
0x18007788d  movzx   eax, ax
0x180077890  or      eax, 80070000h
0x180077895  jmp     short loc_1800778A1
0x180077897  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007789c  mov     eax, 80070057h
0x1800778a1  mov     rcx, [rsp+248h+var_18]
0x1800778a9  xor     rcx, rsp; StackCookie
0x1800778ac  call    __security_check_cookie
0x1800778b1  mov     rbx, [rsp+248h+arg_0]
0x1800778b9  add     rsp, 240h
0x1800778c0  pop     rdi
0x1800778c1  retn
```
