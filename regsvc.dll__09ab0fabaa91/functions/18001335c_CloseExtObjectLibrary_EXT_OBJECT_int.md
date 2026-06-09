# CloseExtObjectLibrary(EXT_OBJECT *,int)

- ea: `0x18001335c`
- end: `0x180013517`
- name: `?CloseExtObjectLibrary@@YAKPEAUEXT_OBJECT@@H@Z`
- size: `443`
- prototype: `__int64 __fastcall(struct EXT_OBJECT *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180004f00`
- `0x18000a2a4`
- `0x18000e1a8`

## callees

- `0x18000ab64`
- `0x18000be10`
- `0x1800119b4`
- `0x1800119fc`
- `0x180011ad4`
- `0x18001335c`
- `0x180014648`
- `0x18001f010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180013409`
- `ntdll!RtlDllShutdownInProgress` at `0x180013409`
- `RPCRT4!NdrClientCall3` at `0x180013430`
- `RPCRT4!NdrClientCall3` at `0x180013430`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800134c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800134c7`

## pseudocode

```c
__int64 __fastcall CloseExtObjectLibrary(struct EXT_OBJECT *a1, int a2)
{
  HMODULE *v4; // rsi
  void (*v5)(void); // rax

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
      *((_QWORD *)a1 + 49));
  if ( ((dwThreadAndLibraryTimeout + 1) & 0xFFFFFFFE) != 0 || a2 )
  {
    v4 = (HMODULE *)((char *)a1 + 88);
    if ( *((_QWORD *)a1 + 11)
      && (GetTimeAsLongLong() - dwThreadAndLibraryTimeout > *((_QWORD *)a1 + 50) || a2)
      && (a2 || (*((_BYTE *)a1 + 380) & 4) == 0) )
    {
      if ( !RtlDllShutdownInProgress() )
      {
        if ( *((_BYTE *)a1 + 80) )
        {
          *((_BYTE *)a1 + 80) = 0;
          NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&PerfHost_ProxyInfo, 2u, 0, (char *)a1 + 88);
        }
        else
        {
          v5 = (void (*)(void))*((_QWORD *)a1 + 8);
          if ( v5 )
            v5();
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
              *((_QWORD *)a1 + 49));
          FreeLibrary(*v4);
        }
      }
      *v4 = 0;
      *((_QWORD *)a1 + 2) = 0;
      *((_QWORD *)a1 + 5) = 0;
      *((_QWORD *)a1 + 8) = 0;
      _InterlockedIncrement((volatile signed __int32 *)a1 + 114);
      *((_QWORD *)a1 + 50) = 0;
    }
    PerfpDeleteErrorLogs((struct ERROR_LOG *)((char *)a1 + 488));
  }
  return 0;
}

```

## disassembly

```asm
0x18001335c  mov     [rsp+arg_8], rbx
0x180013361  mov     [rsp+arg_0], rcx
0x180013366  push    rsi
0x180013367  push    r14
0x180013369  push    r15
0x18001336b  sub     rsp, 30h
0x18001336f  mov     r14d, edx
0x180013372  mov     rbx, rcx
0x180013375  mov     rcx, cs:WPP_GLOBAL_Control
0x18001337c  test    byte ptr [rcx+1Ch], 10h
0x180013380  jz      short loc_1800133A4
0x180013382  cmp     byte ptr [rcx+19h], 4
0x180013386  jb      short loc_1800133A4
0x180013388  mov     edx, 0Ah
0x18001338d  mov     r9, [rbx+188h]
0x180013394  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18001339b  mov     rcx, [rcx+10h]
0x18001339f  call    WPP_SF_S
0x1800133a4  mov     eax, cs:?dwThreadAndLibraryTimeout@@3KA; ulong dwThreadAndLibraryTimeout
0x1800133aa  inc     eax
0x1800133ac  test    eax, 0FFFFFFFEh
0x1800133b1  jnz     short loc_1800133BC
0x1800133b3  test    r14d, r14d
0x1800133b6  jz      loc_180013506
0x1800133bc  lea     rsi, [rbx+58h]
0x1800133c0  mov     [rsp+48h+arg_10], rsi
0x1800133c5  cmp     qword ptr [rsi], 0
0x1800133c9  jz      loc_1800134FA
0x1800133cf  call    ?GetTimeAsLongLong@@YA_JXZ; GetTimeAsLongLong(void)
0x1800133d4  lea     r15, [rbx+190h]
0x1800133db  mov     [rsp+48h+arg_18], r15
0x1800133e0  mov     ecx, cs:?dwThreadAndLibraryTimeout@@3KA; ulong dwThreadAndLibraryTimeout
0x1800133e6  sub     rax, rcx
0x1800133e9  cmp     rax, [r15]
0x1800133ec  jg      short loc_1800133F7
0x1800133ee  test    r14d, r14d
0x1800133f1  jz      loc_1800134FA
0x1800133f7  test    r14d, r14d
0x1800133fa  jnz     short loc_180013409
0x1800133fc  test    byte ptr [rbx+17Ch], 4
0x180013403  jnz     loc_1800134FA
0x180013409  call    cs:__imp_RtlDllShutdownInProgress
0x18001340f  test    al, al
0x180013411  jnz     loc_1800134CD
0x180013417  cmp     [rbx+50h], al
0x18001341a  jz      short loc_18001343B
0x18001341c  mov     [rbx+50h], al
0x18001341f  mov     r9, rsi
0x180013422  xor     r8d, r8d; pReturnValue
0x180013425  lea     edx, [r8+2]; nProcNum
0x180013429  lea     rcx, ?PerfHost_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180013430  call    cs:__imp_NdrClientCall3
0x180013436  jmp     loc_1800134CD
0x18001343b  mov     rax, [rbx+40h]
0x18001343f  test    rax, rax
0x180013442  jz      short loc_180013449
0x180013444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013449  mov     rcx, cs:WPP_GLOBAL_Control
0x180013450  jmp     short loc_18001349C
0x180013452  mov     ebx, eax
0x180013454  mov     ecx, eax; unsigned int
0x180013456  call    ?PerfpExceptionHandler@@YAXK@Z; PerfpExceptionHandler(ulong)
0x18001345b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013462  test    byte ptr [rcx+1Ch], 10h
0x180013466  jz      short loc_18001348D
0x180013468  cmp     byte ptr [rcx+19h], 2
0x18001346c  jb      short loc_18001348D
0x18001346e  mov     [rsp+48h+var_28], ebx
0x180013472  mov     rbx, [rsp+48h+arg_0]
0x180013477  mov     r9, [rbx+48h]
0x18001347b  mov     rcx, [rcx+10h]
0x18001347f  call    WPP_SF_sd
0x180013484  mov     rcx, cs:WPP_GLOBAL_Control
0x18001348b  jmp     short loc_180013492
0x18001348d  mov     rbx, [rsp+48h+arg_0]
0x180013492  mov     rsi, [rsp+48h+arg_10]
0x180013497  mov     r15, [rsp+48h+arg_18]
0x18001349c  test    byte ptr [rcx+1Ch], 10h
0x1800134a0  jz      short loc_1800134C4
0x1800134a2  cmp     byte ptr [rcx+19h], 4
0x1800134a6  jb      short loc_1800134C4
0x1800134a8  mov     edx, 0Ch
0x1800134ad  mov     r9, [rbx+188h]
0x1800134b4  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x1800134bb  mov     rcx, [rcx+10h]
0x1800134bf  call    WPP_SF_S
0x1800134c4  mov     rcx, [rsi]; hLibModule
0x1800134c7  call    cs:__imp_FreeLibrary
0x1800134cd  mov     qword ptr [rsi], 0
0x1800134d4  mov     qword ptr [rbx+10h], 0
0x1800134dc  mov     qword ptr [rbx+28h], 0
0x1800134e4  mov     qword ptr [rbx+40h], 0
0x1800134ec  lock inc dword ptr [rbx+1C8h]
0x1800134f3  mov     qword ptr [r15], 0
0x1800134fa  lea     rcx, [rbx+1E8h]; struct ERROR_LOG *
0x180013501  call    ?PerfpDeleteErrorLogs@@YAXPEAUERROR_LOG@@@Z; PerfpDeleteErrorLogs(ERROR_LOG *)
0x180013506  xor     eax, eax
0x180013508  mov     rbx, [rsp+48h+arg_8]
0x18001350d  add     rsp, 30h
0x180013511  pop     r15
0x180013513  pop     r14
0x180013515  pop     rsi
0x180013516  retn
0x18001e659  push    rbp
0x18001e65b  sub     rsp, 30h
0x18001e65f  mov     rbp, rdx
0x18001e662  mov     rdx, rcx; struct _EXCEPTION_POINTERS *
0x18001e665  mov     rcx, [rcx]
0x18001e668  mov     ecx, [rcx]; unsigned int
0x18001e66a  mov     r9d, 3F3h; unsigned int
0x18001e670  mov     r8, [rbp+50h]; struct EXT_OBJECT *
0x18001e674  call    ?PerfpExceptionFilter@@YAKKPEBU_EXCEPTION_POINTERS@@PEAUEXT_OBJECT@@K@Z; PerfpExceptionFilter(ulong,_EXCEPTION_POINTERS const *,EXT_OBJECT *,ulong)
0x18001e679  nop
0x18001e67a  add     rsp, 30h
0x18001e67e  pop     rbp
0x18001e67f  retn
```
