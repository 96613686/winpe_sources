# CRdpEncTransportWorker::Terminate(void)

- ea: `0x140080230`
- end: `0x1400803df`
- name: `?Terminate@CRdpEncTransportWorker@@UEAAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(CRdpEncTransportWorker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14007b3f0`

## callees

- `0x140003b08`
- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x140080230`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1400802ed`
- `KERNEL32!CreateThread` at `0x1400802ed`
- `KERNEL32!FreeLibrary` at `0x1400803c5`
- `KERNEL32!FreeLibrary` at `0x1400803c5`
- `KERNEL32!CloseHandle` at `0x140080358`
- `KERNEL32!CloseHandle` at `0x140080358`
- `KERNEL32!GetLastError` at `0x140080310`
- `KERNEL32!GetLastError` at `0x14008034d`
- `KERNEL32!GetLastError` at `0x140080310`
- `KERNEL32!GetLastError` at `0x14008034d`

## string_xrefs

- `0x140080289`: `"SHUTDOWN_THREADPOOLIO_INFO"`

## pseudocode

```c
__int64 __fastcall CRdpEncTransportWorker::Terminate(CRdpEncTransportWorker *this)
{
  void *v1; // rsi
  _QWORD *v3; // rax
  unsigned int v4; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v7; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  HMODULE v10; // rcx

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
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_b93b18dea47034162279e05f15262601_Traceguids,
            CurrentThreadActivityIdPrefix,
            v7);
        }
        GetLastError();
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_b93b18dea47034162279e05f15262601_Traceguids,
        v4,
        (__int64)"\"SHUTDOWN_THREADPOOLIO_INFO\"");
    }
  }
  *((_DWORD *)this + 5) |= 4u;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b93b18dea47034162279e05f15262601_Traceguids, v9, 0);
  }
  if ( v1 )
    operator delete(v1);
  v10 = (HMODULE)*((_QWORD *)this + 6);
  if ( v10 )
  {
    FreeLibrary(v10);
    *((_QWORD *)this + 6) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140080230  push    rbx
0x140080232  push    rsi
0x140080233  push    rdi
0x140080234  push    r14
0x140080236  sub     rsp, 38h
0x14008023a  xor     esi, esi
0x14008023c  lea     r14, WPP_GLOBAL_Control
0x140080243  mov     rbx, rcx
0x140080246  cmp     [rcx+28h], rsi
0x14008024a  jz      loc_140080364
0x140080250  lea     ecx, [rsi+10h]; Size
0x140080253  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140080258  mov     rsi, rax
0x14008025b  test    rax, rax
0x14008025e  jnz     short loc_1400802B7
0x140080260  mov     rax, cs:WPP_GLOBAL_Control
0x140080267  cmp     rax, r14
0x14008026a  jz      loc_140080364
0x140080270  test    byte ptr [rax+1Ch], 8
0x140080274  jz      loc_140080364
0x14008027a  cmp     byte ptr [rax+19h], 2
0x14008027e  jb      loc_140080364
0x140080284  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140080289  lea     rcx, aShutdownThread; "\"SHUTDOWN_THREADPOOLIO_INFO\""
0x140080290  mov     r9d, eax
0x140080293  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x140080298  lea     edx, [rsi+13h]
0x14008029b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400802a2  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x1400802a9  mov     rcx, [rcx+10h]
0x1400802ad  call    WPP_SF_Ds
0x1400802b2  jmp     loc_140080364
0x1400802b7  mov     rax, [rbx+30h]
0x1400802bb  lea     r8, ?STATIC_ShutdownThreadpoolIo@CRdpEncTransportWorker@@KAKPEAX@Z; lpStartAddress
0x1400802c2  mov     [rsi], rax
0x1400802c5  mov     r9, rsi; lpParameter
0x1400802c8  mov     rax, [rbx+28h]
0x1400802cc  xor     edx, edx; dwStackSize
0x1400802ce  mov     [rsi+8], rax
0x1400802d2  xor     ecx, ecx; lpThreadAttributes
0x1400802d4  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x1400802dd  mov     qword ptr [rbx+28h], 0
0x1400802e5  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1400802ed  call    cs:__imp_CreateThread
0x1400802f3  test    rax, rax
0x1400802f6  jnz     short loc_140080355
0x1400802f8  mov     rax, cs:WPP_GLOBAL_Control
0x1400802ff  cmp     rax, r14
0x140080302  jz      short loc_14008034D
0x140080304  test    byte ptr [rax+1Ch], 8
0x140080308  jz      short loc_14008034D
0x14008030a  cmp     byte ptr [rax+19h], 2
0x14008030e  jb      short loc_14008034D
0x140080310  call    cs:__imp_GetLastError
0x140080316  mov     edi, eax
0x140080318  test    eax, eax
0x14008031a  jle     short loc_140080325
0x14008031c  movzx   edi, ax
0x14008031f  or      edi, 80070000h
0x140080325  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14008032a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080331  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x140080338  mov     edx, 14h
0x14008033d  mov     [rsp+58h+dwCreationFlags], edi
0x140080341  mov     r9d, eax
0x140080344  mov     rcx, [rcx+10h]
0x140080348  call    WPP_SF_Dd
0x14008034d  call    cs:__imp_GetLastError
0x140080353  jmp     short loc_140080364
0x140080355  mov     rcx, rax; hObject
0x140080358  call    cs:__imp_CloseHandle
0x14008035e  xor     esi, esi
0x140080360  mov     [rbx+30h], rsi
0x140080364  or      dword ptr [rbx+14h], 4
0x140080368  mov     rax, cs:WPP_GLOBAL_Control
0x14008036f  cmp     rax, r14
0x140080372  jz      short loc_1400803AF
0x140080374  test    dword ptr [rax+1Ch], 800h
0x14008037b  jz      short loc_1400803AF
0x14008037d  cmp     byte ptr [rax+19h], 4
0x140080381  jb      short loc_1400803AF
0x140080383  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140080388  mov     rcx, cs:WPP_GLOBAL_Control
0x14008038f  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x140080396  mov     edx, 15h
0x14008039b  mov     [rsp+58h+dwCreationFlags], 0
0x1400803a3  mov     r9d, eax
0x1400803a6  mov     rcx, [rcx+10h]
0x1400803aa  call    WPP_SF_Dd
0x1400803af  test    rsi, rsi
0x1400803b2  jz      short loc_1400803BC
0x1400803b4  mov     rcx, rsi; Block
0x1400803b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400803bc  mov     rcx, [rbx+30h]; hLibModule
0x1400803c0  test    rcx, rcx
0x1400803c3  jz      short loc_1400803D3
0x1400803c5  call    cs:__imp_FreeLibrary
0x1400803cb  mov     qword ptr [rbx+30h], 0
0x1400803d3  xor     eax, eax
0x1400803d5  add     rsp, 38h
0x1400803d9  pop     r14
0x1400803db  pop     rdi
0x1400803dc  pop     rsi
0x1400803dd  pop     rbx
0x1400803de  retn
```
