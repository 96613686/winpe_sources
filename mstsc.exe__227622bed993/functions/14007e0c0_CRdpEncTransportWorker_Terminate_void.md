# CRdpEncTransportWorker::Terminate(void)

- ea: `0x14007e0c0`
- end: `0x14007e26f`
- name: `?Terminate@CRdpEncTransportWorker@@UEAAJXZ`
- size: `431`
- prototype: `__int64 __fastcall(CRdpEncTransportWorker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140079280`

## callees

- `0x140003b08`
- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14007e0c0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14007e17d`
- `KERNEL32!CreateThread` at `0x14007e17d`
- `KERNEL32!FreeLibrary` at `0x14007e255`
- `KERNEL32!FreeLibrary` at `0x14007e255`
- `KERNEL32!CloseHandle` at `0x14007e1e8`
- `KERNEL32!CloseHandle` at `0x14007e1e8`
- `KERNEL32!GetLastError` at `0x14007e1a0`
- `KERNEL32!GetLastError` at `0x14007e1dd`
- `KERNEL32!GetLastError` at `0x14007e1a0`
- `KERNEL32!GetLastError` at `0x14007e1dd`

## string_xrefs

- `0x14007e119`: `"SHUTDOWN_THREADPOOLIO_INFO"`

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
0x14007e0c0  push    rbx
0x14007e0c2  push    rsi
0x14007e0c3  push    rdi
0x14007e0c4  push    r14
0x14007e0c6  sub     rsp, 38h
0x14007e0ca  xor     esi, esi
0x14007e0cc  lea     r14, WPP_GLOBAL_Control
0x14007e0d3  mov     rbx, rcx
0x14007e0d6  cmp     [rcx+28h], rsi
0x14007e0da  jz      loc_14007E1F4
0x14007e0e0  lea     ecx, [rsi+10h]; Size
0x14007e0e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007e0e8  mov     rsi, rax
0x14007e0eb  test    rax, rax
0x14007e0ee  jnz     short loc_14007E147
0x14007e0f0  mov     rax, cs:WPP_GLOBAL_Control
0x14007e0f7  cmp     rax, r14
0x14007e0fa  jz      loc_14007E1F4
0x14007e100  test    byte ptr [rax+1Ch], 8
0x14007e104  jz      loc_14007E1F4
0x14007e10a  cmp     byte ptr [rax+19h], 2
0x14007e10e  jb      loc_14007E1F4
0x14007e114  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007e119  lea     rcx, aShutdownThread; "\"SHUTDOWN_THREADPOOLIO_INFO\""
0x14007e120  mov     r9d, eax
0x14007e123  mov     qword ptr [rsp+58h+dwCreationFlags], rcx
0x14007e128  lea     edx, [rsi+13h]
0x14007e12b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e132  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x14007e139  mov     rcx, [rcx+10h]
0x14007e13d  call    WPP_SF_Ds
0x14007e142  jmp     loc_14007E1F4
0x14007e147  mov     rax, [rbx+30h]
0x14007e14b  lea     r8, ?STATIC_ShutdownThreadpoolIo@CRdpEncTransportWorker@@KAKPEAX@Z; lpStartAddress
0x14007e152  mov     [rsi], rax
0x14007e155  mov     r9, rsi; lpParameter
0x14007e158  mov     rax, [rbx+28h]
0x14007e15c  xor     edx, edx; dwStackSize
0x14007e15e  mov     [rsi+8], rax
0x14007e162  xor     ecx, ecx; lpThreadAttributes
0x14007e164  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x14007e16d  mov     qword ptr [rbx+28h], 0
0x14007e175  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14007e17d  call    cs:__imp_CreateThread
0x14007e183  test    rax, rax
0x14007e186  jnz     short loc_14007E1E5
0x14007e188  mov     rax, cs:WPP_GLOBAL_Control
0x14007e18f  cmp     rax, r14
0x14007e192  jz      short loc_14007E1DD
0x14007e194  test    byte ptr [rax+1Ch], 8
0x14007e198  jz      short loc_14007E1DD
0x14007e19a  cmp     byte ptr [rax+19h], 2
0x14007e19e  jb      short loc_14007E1DD
0x14007e1a0  call    cs:__imp_GetLastError
0x14007e1a6  mov     edi, eax
0x14007e1a8  test    eax, eax
0x14007e1aa  jle     short loc_14007E1B5
0x14007e1ac  movzx   edi, ax
0x14007e1af  or      edi, 80070000h
0x14007e1b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007e1ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e1c1  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x14007e1c8  mov     edx, 14h
0x14007e1cd  mov     [rsp+58h+dwCreationFlags], edi
0x14007e1d1  mov     r9d, eax
0x14007e1d4  mov     rcx, [rcx+10h]
0x14007e1d8  call    WPP_SF_Dd
0x14007e1dd  call    cs:__imp_GetLastError
0x14007e1e3  jmp     short loc_14007E1F4
0x14007e1e5  mov     rcx, rax; hObject
0x14007e1e8  call    cs:__imp_CloseHandle
0x14007e1ee  xor     esi, esi
0x14007e1f0  mov     [rbx+30h], rsi
0x14007e1f4  or      dword ptr [rbx+14h], 4
0x14007e1f8  mov     rax, cs:WPP_GLOBAL_Control
0x14007e1ff  cmp     rax, r14
0x14007e202  jz      short loc_14007E23F
0x14007e204  test    dword ptr [rax+1Ch], 800h
0x14007e20b  jz      short loc_14007E23F
0x14007e20d  cmp     byte ptr [rax+19h], 4
0x14007e211  jb      short loc_14007E23F
0x14007e213  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007e218  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e21f  lea     r8, WPP_b93b18dea47034162279e05f15262601_Traceguids
0x14007e226  mov     edx, 15h
0x14007e22b  mov     [rsp+58h+dwCreationFlags], 0
0x14007e233  mov     r9d, eax
0x14007e236  mov     rcx, [rcx+10h]
0x14007e23a  call    WPP_SF_Dd
0x14007e23f  test    rsi, rsi
0x14007e242  jz      short loc_14007E24C
0x14007e244  mov     rcx, rsi; Block
0x14007e247  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007e24c  mov     rcx, [rbx+30h]; hLibModule
0x14007e250  test    rcx, rcx
0x14007e253  jz      short loc_14007E263
0x14007e255  call    cs:__imp_FreeLibrary
0x14007e25b  mov     qword ptr [rbx+30h], 0
0x14007e263  xor     eax, eax
0x14007e265  add     rsp, 38h
0x14007e269  pop     r14
0x14007e26b  pop     rdi
0x14007e26c  pop     rsi
0x14007e26d  pop     rbx
0x14007e26e  retn
```
