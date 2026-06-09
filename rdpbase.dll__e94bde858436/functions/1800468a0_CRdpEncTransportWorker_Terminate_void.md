# CRdpEncTransportWorker::Terminate(void)

- ea: `0x1800468a0`
- end: `0x180046a7c`
- name: `?Terminate@CRdpEncTransportWorker@@UEAAJXZ`
- size: `476`
- prototype: `__int64 __fastcall(CRdpEncTransportWorker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001d8c0`

## callees

- `0x1800468a0`
- `0x180046a84`
- `0x1800721d4`
- `0x1800787d4`
- `0x180078820`
- `0x1800923f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046a69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046a69`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046906`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046918`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046918`

## string_xrefs

- `0x1800469d4`: `"SHUTDOWN_THREADPOOLIO_INFO"`

## pseudocode

```c
__int64 __fastcall CRdpEncTransportWorker::Terminate(CRdpEncTransportWorker *this)
{
  void *v1; // rsi
  _QWORD *v3; // rax
  HANDLE Thread; // rax
  HMODULE v5; // rcx
  signed int LastError; // eax
  unsigned int v8; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax

  v1 = 0;
  if ( *((_QWORD *)this + 5) )
  {
    v3 = operator new(0x10u);
    v1 = v3;
    if ( v3 )
    {
      *v3 = *((_QWORD *)this + 6);
      v3[1] = *((_QWORD *)this + 5);
      *((_QWORD *)this + 5) = 0;
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CRdpEncTransportWorker::STATIC_ShutdownThreadpoolIo, v3, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
        v1 = 0;
        *((_QWORD *)this + 6) = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_b93b18dea47034162279e05f15262601_Traceguids,
            CurrentThreadActivityIdPrefix,
            v8);
        }
        GetLastError();
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_b93b18dea47034162279e05f15262601_Traceguids,
        v10,
        (__int64)"\"SHUTDOWN_THREADPOOLIO_INFO\"");
    }
  }
  *((_DWORD *)this + 5) |= 4u;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b93b18dea47034162279e05f15262601_Traceguids, v11, 0);
  }
  if ( v1 )
    operator delete(v1);
  v5 = (HMODULE)*((_QWORD *)this + 6);
  if ( v5 )
  {
    FreeLibrary(v5);
    *((_QWORD *)this + 6) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800468a0  push    rbx
0x1800468a2  push    rsi
0x1800468a3  push    rdi
0x1800468a4  push    r14
0x1800468a6  sub     rsp, 38h
0x1800468aa  xor     esi, esi
0x1800468ac  lea     r14, WPP_GLOBAL_Control
0x1800468b3  mov     rbx, rcx
0x1800468b6  cmp     [rcx+28h], rsi
0x1800468ba  jz      short loc_180046924
0x1800468bc  lea     ecx, [rsi+10h]; Size
0x1800468bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800468c4  mov     rsi, rax
0x1800468c7  test    rax, rax
0x1800468ca  jz      loc_1800469AB
0x1800468d0  mov     rax, [rbx+30h]
0x1800468d4  lea     r8, ?STATIC_ShutdownThreadpoolIo@CRdpEncTransportWorker@@KAKPEAX@Z; lpStartAddress
0x1800468db  mov     [rsi], rax
0x1800468de  mov     r9, rsi; lpParameter
0x1800468e1  mov     rax, [rbx+28h]
0x1800468e5  xor     edx, edx; dwStackSize
0x1800468e7  mov     [rsi+8], rax
0x1800468eb  xor     ecx, ecx; lpThreadAttributes
0x1800468ed  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x1800468f6  mov     qword ptr [rbx+28h], 0
0x1800468fe  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180046906  call    cs:__imp_CreateThread
0x18004690c  test    rax, rax
0x18004690f  jz      loc_180046A04
0x180046915  mov     rcx, rax; hObject
0x180046918  call    cs:__imp_CloseHandle
0x18004691e  xor     esi, esi
0x180046920  mov     [rbx+30h], rsi
0x180046924  or      dword ptr [rbx+14h], 4
0x180046928  mov     rax, cs:WPP_GLOBAL_Control
0x18004692f  cmp     rax, r14
0x180046932  jz      short loc_180046941
0x180046934  test    dword ptr [rax+1Ch], 800h
0x18004693b  jnz     loc_180046A21
0x180046941  test    rsi, rsi
0x180046944  jnz     loc_180046A5C
0x18004694a  mov     rcx, [rbx+30h]; hLibModule
0x18004694e  test    rcx, rcx
0x180046951  jnz     loc_180046A69
0x180046957  xor     eax, eax
0x180046959  add     rsp, 38h
0x18004695d  pop     r14
0x18004695f  pop     rdi
0x180046960  pop     rsi
0x180046961  pop     rbx
0x180046962  retn
0x180046963  call    cs:__imp_GetLastError
0x180046969  mov     edi, eax
0x18004696b  test    eax, eax
0x18004696d  jle     short loc_180046978
0x18004696f  movzx   edi, ax
0x180046972  or      edi, 80070000h
0x180046978  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004697d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046984  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x18004698b  mov     edx, 14h
0x180046990  mov     [rsp+58h+dwCreationFlags], edi
0x180046994  mov     r9d, eax
0x180046997  mov     rcx, [rcx+10h]
0x18004699b  call    WPP_SF_Dd
0x1800469a0  call    cs:__imp_GetLastError
0x1800469a6  jmp     loc_180046924
0x1800469ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800469b2  cmp     rax, r14
0x1800469b5  jz      loc_180046924
0x1800469bb  test    byte ptr [rax+1Ch], 8
0x1800469bf  jz      loc_180046924
0x1800469c5  cmp     byte ptr [rax+19h], 2
0x1800469c9  jb      loc_180046924
0x1800469cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800469d4  lea     rcx, aShutdownThread; "\"SHUTDOWN_THREADPOOLIO_INFO\""
0x1800469db  mov     edx, 13h
0x1800469e0  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x1800469e5  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x1800469ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469f3  mov     r9d, eax
0x1800469f6  mov     rcx, [rcx+10h]
0x1800469fa  call    WPP_SF_Ds
0x1800469ff  jmp     loc_180046924
0x180046a04  mov     rax, cs:WPP_GLOBAL_Control
0x180046a0b  cmp     rax, r14
0x180046a0e  jz      short loc_1800469A0
0x180046a10  test    byte ptr [rax+1Ch], 8
0x180046a14  jz      short loc_1800469A0
0x180046a16  cmp     byte ptr [rax+19h], 2
0x180046a1a  jb      short loc_1800469A0
0x180046a1c  jmp     loc_180046963
0x180046a21  cmp     byte ptr [rax+19h], 4
0x180046a25  jb      loc_180046941
0x180046a2b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a37  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x180046a3e  mov     edx, 15h
0x180046a43  mov     [rsp+58h+dwCreationFlags], 0
0x180046a4b  mov     r9d, eax
0x180046a4e  mov     rcx, [rcx+10h]
0x180046a52  call    WPP_SF_Dd
0x180046a57  jmp     loc_180046941
0x180046a5c  mov     rcx, rsi; Block
0x180046a5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046a64  jmp     loc_18004694A
0x180046a69  call    cs:__imp_FreeLibrary
0x180046a6f  mov     qword ptr [rbx+30h], 0
0x180046a77  jmp     loc_180046957
```
