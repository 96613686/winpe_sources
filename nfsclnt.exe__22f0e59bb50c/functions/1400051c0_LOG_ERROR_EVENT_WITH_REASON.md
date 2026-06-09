# LOG_ERROR_EVENT_WITH_REASON

- ea: `0x1400051c0`
- end: `0x1400053d9`
- name: `LOG_ERROR_EVENT_WITH_REASON`
- size: `537`
- prototype: `void __fastcall(const EVENT_DESCRIPTOR *, __int64, __int64, int, DWORD dwMessageId)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140005134`
- `0x140005180`

## callees

- `0x140002bd8`
- `0x1400051c0`
- `0x14001830e`
- `0x140018350`
- `0x1400183e0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140005385`
- `ADVAPI32!EventWrite` at `0x140005385`
- `KERNEL32!LocalFree` at `0x14000533d`
- `KERNEL32!LocalFree` at `0x14000533d`
- `KERNEL32!FormatMessageW` at `0x14000528b`
- `KERNEL32!FormatMessageW` at `0x14000528b`
- `msvcrt!_snwprintf_s` at `0x1400052c2`
- `msvcrt!_snwprintf_s` at `0x1400052df`
- `msvcrt!_snwprintf_s` at `0x140005310`
- `msvcrt!_snwprintf_s` at `0x140005332`
- `msvcrt!_snwprintf_s` at `0x1400052c2`
- `msvcrt!_snwprintf_s` at `0x1400052df`
- `msvcrt!_snwprintf_s` at `0x140005310`
- `msvcrt!_snwprintf_s` at `0x140005332`

## pseudocode

```c
void __fastcall LOG_ERROR_EVENT_WITH_REASON(
        const EVENT_DESCRIPTOR *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        DWORD dwMessageId)
{
  __int64 v9; // rax
  __int64 nSize; // [rsp+28h] [rbp-D8h]
  va_list *Arguments; // [rsp+30h] [rbp-D0h]
  WCHAR Buffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v14[2048]; // [rsp+70h] [rbp-90h] BYREF

  if ( *(int *)&g_dwLoggingLevel >= 0 && g_hEventProviderHandle )
  {
    *(_QWORD *)Buffer = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_befea35b910b3d8fcaee8503f00af8a3_Traceguids);
    memset_0(v14, 0, sizeof(v14));
    if ( FormatMessageW(0x1100u, 0, dwMessageId, 0x400u, Buffer, 0, 0) )
    {
      if ( a2 )
      {
        LODWORD(nSize) = a4;
        _snwprintf_s(v14, 0x800u, 0x7FFu, L"[%s:%u] %s : %u: %s", a3, nSize, a2, dwMessageId, *(_QWORD *)Buffer);
      }
      else
      {
        LODWORD(Arguments) = dwMessageId;
        LODWORD(nSize) = a4;
        _snwprintf_s(v14, 0x800u, 0x7FFu, L"[%s:%u] : %u: %s", a3, nSize, Arguments, *(_QWORD *)Buffer);
      }
      LocalFree(*(HLOCAL *)Buffer);
    }
    else if ( a2 )
    {
      LODWORD(nSize) = a4;
      _snwprintf_s(v14, 0x800u, 0x7FFu, L"[%s:%u] %s : %u", a3, nSize, a2, dwMessageId);
    }
    else
    {
      LODWORD(Arguments) = dwMessageId;
      LODWORD(nSize) = a4;
      _snwprintf_s(v14, 0x800u, 0x7FFu, L"[%s:%u] %u", a3, nSize, Arguments);
    }
    v9 = -1;
    do
      ++v9;
    while ( v14[v9] );
    UserData.Reserved = 0;
    UserData.Ptr = (ULONGLONG)v14;
    UserData.Size = 2 * v9 + 2;
    if ( EventWrite(g_hEventProviderHandle, a1, 1u, &UserData)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_befea35b910b3d8fcaee8503f00af8a3_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x1400051c0  push    rbp
0x1400051c2  push    rbx
0x1400051c3  push    rsi
0x1400051c4  push    rdi
0x1400051c5  push    r12
0x1400051c7  push    r13
0x1400051c9  push    r14
0x1400051cb  push    r15
0x1400051cd  lea     rbp, [rsp-0F88h]
0x1400051d5  mov     eax, 1088h
0x1400051da  call    _alloca_probe
0x1400051df  sub     rsp, rax
0x1400051e2  mov     rax, cs:__security_cookie
0x1400051e9  xor     rax, rsp
0x1400051ec  mov     [rbp+0FC0h+var_50], rax
0x1400051f3  xor     r12d, r12d
0x1400051f6  mov     r14d, r9d
0x1400051f9  cmp     cs:g_dwLoggingLevel, r12d
0x140005200  mov     rsi, r8
0x140005203  mov     rbx, rdx
0x140005206  mov     r15, rcx
0x140005209  jl      loc_1400053B6
0x14000520f  cmp     cs:g_hEventProviderHandle, r12
0x140005216  jz      loc_1400053B6
0x14000521c  mov     qword ptr [rsp+10C0h+Buffer], r12
0x140005221  mov     rcx, cs:WPP_GLOBAL_Control
0x140005228  lea     r13, WPP_GLOBAL_Control
0x14000522f  cmp     rcx, r13
0x140005232  jz      short loc_14000524F
0x140005234  test    byte ptr [rcx+1Ch], 8
0x140005238  jz      short loc_14000524F
0x14000523a  mov     rcx, [rcx+10h]
0x14000523e  lea     edx, [r12+14h]
0x140005243  lea     r8, WPP_befea35b910b3d8fcaee8503f00af8a3_Traceguids
0x14000524a  call    WPP_SF_
0x14000524f  xor     edx, edx; Val
0x140005251  lea     rcx, [rsp+10C0h+var_1050]; void *
0x140005256  mov     r8d, 1000h; Size
0x14000525c  call    memset_0
0x140005261  mov     edi, [rbp+0FC0h+dwMessageId]
0x140005267  lea     rax, [rsp+10C0h+Buffer]
0x14000526c  mov     [rsp+10C0h+Arguments], r12; Arguments
0x140005271  mov     r9d, 400h; dwLanguageId
0x140005277  mov     dword ptr [rsp+10C0h+nSize], r12d; nSize
0x14000527c  mov     r8d, edi; dwMessageId
0x14000527f  xor     edx, edx; lpSource
0x140005281  mov     [rsp+10C0h+lpBuffer], rax; lpBuffer
0x140005286  mov     ecx, 1100h; dwFlags
0x14000528b  call    cs:__imp_FormatMessageW
0x140005291  mov     edx, 800h; BufferCount
0x140005296  lea     rcx, [rsp+10C0h+var_1050]; Buffer
0x14000529b  lea     r8d, [rdx-1]; MaxCount
0x14000529f  test    eax, eax
0x1400052a1  jnz     short loc_1400052E7
0x1400052a3  test    rbx, rbx
0x1400052a6  jz      short loc_1400052CA
0x1400052a8  mov     dword ptr [rsp+10C0h+var_1088], edi
0x1400052ac  lea     r9, aSUSU; "[%s:%u] %s : %u"
0x1400052b3  mov     [rsp+10C0h+Arguments], rbx
0x1400052b8  mov     dword ptr [rsp+10C0h+nSize], r14d
0x1400052bd  mov     [rsp+10C0h+lpBuffer], rsi
0x1400052c2  call    cs:__imp__snwprintf_s
0x1400052c8  jmp     short loc_140005343
0x1400052ca  mov     dword ptr [rsp+10C0h+Arguments], edi
0x1400052ce  lea     r9, aSUU; "[%s:%u] %u"
0x1400052d5  mov     dword ptr [rsp+10C0h+nSize], r14d
0x1400052da  mov     [rsp+10C0h+lpBuffer], rsi
0x1400052df  call    cs:__imp__snwprintf_s
0x1400052e5  jmp     short loc_140005343
0x1400052e7  mov     rax, qword ptr [rsp+10C0h+Buffer]
0x1400052ec  test    rbx, rbx
0x1400052ef  jz      short loc_140005318
0x1400052f1  mov     [rsp+10C0h+var_1080], rax
0x1400052f6  lea     r9, aSUSUS; "[%s:%u] %s : %u: %s"
0x1400052fd  mov     dword ptr [rsp+10C0h+var_1088], edi
0x140005301  mov     [rsp+10C0h+Arguments], rbx
0x140005306  mov     dword ptr [rsp+10C0h+nSize], r14d
0x14000530b  mov     [rsp+10C0h+lpBuffer], rsi
0x140005310  call    cs:__imp__snwprintf_s
0x140005316  jmp     short loc_140005338
0x140005318  mov     [rsp+10C0h+var_1088], rax
0x14000531d  lea     r9, aSUUS; "[%s:%u] : %u: %s"
0x140005324  mov     dword ptr [rsp+10C0h+Arguments], edi
0x140005328  mov     dword ptr [rsp+10C0h+nSize], r14d
0x14000532d  mov     [rsp+10C0h+lpBuffer], rsi
0x140005332  call    cs:__imp__snwprintf_s
0x140005338  mov     rcx, qword ptr [rsp+10C0h+Buffer]; hMem
0x14000533d  call    cs:__imp_LocalFree
0x140005343  lea     rcx, [rsp+10C0h+var_1050]
0x140005348  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000534c  inc     rax
0x14000534f  cmp     [rcx+rax*2], r12w
0x140005354  jnz     short loc_14000534C
0x140005356  lea     rcx, [rsp+10C0h+var_1050]
0x14000535b  mov     dword ptr [rsp+10C0h+UserData.0Ch], r12d
0x140005360  mov     [rsp+10C0h+UserData.Ptr], rcx
0x140005365  lea     eax, ds:2[rax*2]
0x14000536c  mov     rcx, cs:g_hEventProviderHandle; RegHandle
0x140005373  lea     r9, [rsp+10C0h+UserData]; UserData
0x140005378  mov     r8d, 1; UserDataCount
0x14000537e  mov     [rsp+10C0h+UserData.Size], eax
0x140005382  mov     rdx, r15; EventDescriptor
0x140005385  call    cs:__imp_EventWrite
0x14000538b  test    eax, eax
0x14000538d  jz      short loc_1400053B6
0x14000538f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005396  cmp     rcx, r13
0x140005399  jz      short loc_1400053B6
0x14000539b  test    byte ptr [rcx+1Ch], 8
0x14000539f  jz      short loc_1400053B6
0x1400053a1  mov     rcx, [rcx+10h]
0x1400053a5  lea     r8, WPP_befea35b910b3d8fcaee8503f00af8a3_Traceguids
0x1400053ac  mov     edx, 15h
0x1400053b1  call    WPP_SF_
0x1400053b6  mov     rcx, [rbp+0FC0h+var_50]
0x1400053bd  xor     rcx, rsp; StackCookie
0x1400053c0  call    __security_check_cookie
0x1400053c5  add     rsp, 1088h
0x1400053cc  pop     r15
0x1400053ce  pop     r14
0x1400053d0  pop     r13
0x1400053d2  pop     r12
0x1400053d4  pop     rdi
0x1400053d5  pop     rsi
0x1400053d6  pop     rbx
0x1400053d7  pop     rbp
0x1400053d8  retn
```
