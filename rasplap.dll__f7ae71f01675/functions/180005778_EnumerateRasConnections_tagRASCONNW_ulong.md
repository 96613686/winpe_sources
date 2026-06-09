# EnumerateRasConnections(tagRASCONNW * *,ulong *)

- ea: `0x180005778`
- end: `0x1800058fc`
- name: `?EnumerateRasConnections@@YAKPEAPEAUtagRASCONNW@@PEAK@Z`
- size: `388`
- prototype: `unsigned int(struct tagRASCONNW **, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a60`
- `0x180005cd0`
- `0x180006144`

## callees

- `0x180005778`
- `0x18000b0ce`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800057dc`
- `KERNEL32!LocalAlloc` at `0x180005846`
- `KERNEL32!LocalAlloc` at `0x1800057dc`
- `KERNEL32!LocalAlloc` at `0x180005846`
- `KERNEL32!GetLastError` at `0x180005857`
- `KERNEL32!GetLastError` at `0x180005857`
- `KERNEL32!LocalFree` at `0x180005837`
- `KERNEL32!LocalFree` at `0x1800058d2`
- `KERNEL32!LocalFree` at `0x180005837`
- `KERNEL32!LocalFree` at `0x1800058d2`
- `RASAPI32!RasEnumConnectionsW` at `0x180005811`
- `RASAPI32!RasEnumConnectionsW` at `0x1800058a0`
- `RASAPI32!RasEnumConnectionsW` at `0x180005811`
- `RASAPI32!RasEnumConnectionsW` at `0x1800058a0`
- `rtutils!TracePrintfExA` at `0x1800057c8`
- `rtutils!TracePrintfExA` at `0x180005877`
- `rtutils!TracePrintfExA` at `0x1800058c4`
- `rtutils!TracePrintfExA` at `0x1800057c8`
- `rtutils!TracePrintfExA` at `0x180005877`
- `rtutils!TracePrintfExA` at `0x1800058c4`

## pseudocode

```c
__int64 __fastcall EnumerateRasConnections(HLOCAL *a1, unsigned int *a2)
{
  struct tagRASCONNW *v4; // rax
  struct tagRASCONNW *v5; // rbx
  DWORD v6; // eax
  DWORD v7; // ebx
  struct tagRASCONNW *v8; // rax
  struct tagRASCONNW *v9; // rbx
  DWORD LastError; // eax
  DWORD v11; // eax
  DWORD v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = 1388;
  if ( a1 && a2 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasConnections");
    *a2 = 0;
    v4 = (struct tagRASCONNW *)LocalAlloc(0x40u, 0x56Cu);
    *a1 = v4;
    v5 = v4;
    if ( v4 )
    {
      memset_0(&v4->hrasconn, 0, 0x568u);
      v5->dwSize = 1388;
      v13 = 1388;
      v6 = RasEnumConnectionsW(v5, &v13, a2);
      v7 = v6;
      if ( v6 != 603 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasConnections: RasEnumConnections failed with error: %d", v6);
        goto LABEL_12;
      }
      LocalFree(*a1);
      v8 = (struct tagRASCONNW *)LocalAlloc(0x40u, v13);
      *a1 = v8;
      v9 = v8;
      if ( v8 )
      {
        memset_0(v8, 0, v13);
        v9->dwSize = 1388;
        v11 = RasEnumConnectionsW(v9, &v13, a2);
        v7 = v11;
        if ( v11 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasConnections: RasEnumConnections failed with error: %d", v11);
          goto LABEL_17;
        }
        return v7;
      }
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "EnumerateRasConnections: LocalAlloc failed with error: %d", LastError);
LABEL_12:
    if ( v7 )
    {
LABEL_17:
      if ( *a1 )
      {
        LocalFree(*a1);
        *a1 = 0;
      }
      *a2 = 0;
      return v7;
    }
    return v7;
  }
  return 87;
}

```

## disassembly

```asm
0x180005778  push    rbx
0x18000577a  push    rsi
0x18000577b  push    rdi
0x18000577c  push    r12
0x18000577e  push    r14
0x180005780  push    r15
0x180005782  sub     rsp, 28h
0x180005786  mov     r12d, 56Ch
0x18000578c  mov     rsi, rdx
0x18000578f  mov     [rsp+58h+arg_0], r12d
0x180005794  mov     rdi, rcx
0x180005797  test    rcx, rcx
0x18000579a  jz      loc_1800058E9
0x1800057a0  test    rdx, rdx
0x1800057a3  jz      loc_1800058E9
0x1800057a9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800057af  or      r14d, 0FFFFFFFFh
0x1800057b3  mov     r15d, 0Ch
0x1800057b9  cmp     ecx, r14d
0x1800057bc  jz      short loc_1800057CE
0x1800057be  lea     r8, aEnumeraterasco_0; "EnumerateRasConnections"
0x1800057c5  mov     edx, r15d; dwFlags
0x1800057c8  call    cs:__imp_TracePrintfExA
0x1800057ce  mov     rdx, r12; uBytes
0x1800057d1  mov     dword ptr [rsi], 0
0x1800057d7  mov     ecx, 40h ; '@'; uFlags
0x1800057dc  call    cs:__imp_LocalAlloc
0x1800057e2  mov     [rdi], rax
0x1800057e5  mov     rbx, rax
0x1800057e8  test    rax, rax
0x1800057eb  jz      short loc_180005857
0x1800057ed  lea     rcx, [rax+4]; void *
0x1800057f1  xor     edx, edx; Val
0x1800057f3  mov     r8d, 568h; Size
0x1800057f9  call    memset_0
0x1800057fe  mov     [rbx], r12d
0x180005801  lea     rdx, [rsp+58h+arg_0]; LPDWORD
0x180005806  mov     r8, rsi; LPDWORD
0x180005809  mov     [rsp+58h+arg_0], r12d
0x18000580e  mov     rcx, rbx; struct tagRASCONNW *
0x180005811  call    cs:__imp_RasEnumConnectionsW
0x180005817  mov     ebx, eax
0x180005819  cmp     eax, 25Bh
0x18000581e  jz      short loc_180005834
0x180005820  mov     ecx, cs:g_dwTraceId
0x180005826  cmp     ecx, r14d
0x180005829  jz      short loc_18000587D
0x18000582b  lea     r8, aEnumeraterasco; "EnumerateRasConnections: RasEnumConnect"...
0x180005832  jmp     short loc_180005871
0x180005834  mov     rcx, [rdi]; hMem
0x180005837  call    cs:__imp_LocalFree
0x18000583d  mov     edx, [rsp+58h+arg_0]; uBytes
0x180005841  mov     ecx, 40h ; '@'; uFlags
0x180005846  call    cs:__imp_LocalAlloc
0x18000584c  mov     [rdi], rax
0x18000584f  mov     rbx, rax
0x180005852  test    rax, rax
0x180005855  jnz     short loc_180005883
0x180005857  call    cs:__imp_GetLastError
0x18000585d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005863  mov     ebx, eax
0x180005865  cmp     ecx, r14d
0x180005868  jz      short loc_18000587D
0x18000586a  lea     r8, aEnumeraterasco_1; "EnumerateRasConnections: LocalAlloc fai"...
0x180005871  mov     r9d, eax
0x180005874  mov     edx, r15d; dwFlags
0x180005877  call    cs:__imp_TracePrintfExA
0x18000587d  test    ebx, ebx
0x18000587f  jz      short loc_1800058E5
0x180005881  jmp     short loc_1800058CA
0x180005883  mov     r8d, [rsp+58h+arg_0]; Size
0x180005888  xor     edx, edx; Val
0x18000588a  mov     rcx, rbx; void *
0x18000588d  call    memset_0
0x180005892  mov     r8, rsi; LPDWORD
0x180005895  mov     [rbx], r12d
0x180005898  lea     rdx, [rsp+58h+arg_0]; LPDWORD
0x18000589d  mov     rcx, rbx; struct tagRASCONNW *
0x1800058a0  call    cs:__imp_RasEnumConnectionsW
0x1800058a6  mov     ebx, eax
0x1800058a8  test    eax, eax
0x1800058aa  jz      short loc_1800058E5
0x1800058ac  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800058b2  cmp     ecx, r14d
0x1800058b5  jz      short loc_1800058CA
0x1800058b7  mov     r9d, eax
0x1800058ba  lea     r8, aEnumeraterasco; "EnumerateRasConnections: RasEnumConnect"...
0x1800058c1  mov     edx, r15d; dwFlags
0x1800058c4  call    cs:__imp_TracePrintfExA
0x1800058ca  mov     rcx, [rdi]; hMem
0x1800058cd  test    rcx, rcx
0x1800058d0  jz      short loc_1800058DF
0x1800058d2  call    cs:__imp_LocalFree
0x1800058d8  mov     qword ptr [rdi], 0
0x1800058df  mov     dword ptr [rsi], 0
0x1800058e5  mov     eax, ebx
0x1800058e7  jmp     short loc_1800058EE
0x1800058e9  mov     eax, 57h ; 'W'
0x1800058ee  add     rsp, 28h
0x1800058f2  pop     r15
0x1800058f4  pop     r14
0x1800058f6  pop     r12
0x1800058f8  pop     rdi
0x1800058f9  pop     rsi
0x1800058fa  pop     rbx
0x1800058fb  retn
```
