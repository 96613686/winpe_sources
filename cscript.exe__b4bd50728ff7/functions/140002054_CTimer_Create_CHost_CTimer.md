# CTimer::Create(CHost *,CTimer * *)

- ea: `0x140002054`
- end: `0x14000216d`
- name: `?Create@CTimer@@SAJPEAVCHost@@PEAPEAV1@@Z`
- size: `281`
- prototype: `__int64 __fastcall(struct CHost *, struct CTimer **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400014b0`

## callees

- `0x140002054`
- `0x1400026d0`
- `0x140009c70`
- `0x14000d984`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400020ad`
- `KERNEL32!GetCurrentThreadId` at `0x1400020ad`
- `KERNEL32!CloseHandle` at `0x14000212d`
- `KERNEL32!CloseHandle` at `0x14000212d`
- `KERNEL32!GetLastError` at `0x1400020d3`
- `KERNEL32!GetLastError` at `0x1400020d3`
- `KERNEL32!CreateThread` at `0x140002111`
- `KERNEL32!CreateThread` at `0x140002111`
- `KERNEL32!CreateEventA` at `0x1400020c4`
- `KERNEL32!CreateEventA` at `0x1400020c4`

## pseudocode

```c
__int64 __fastcall CTimer::Create(struct CHost *a1, struct CTimer **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  HANDLE EventA; // rax
  signed int LastError; // eax
  unsigned int v8; // edx
  signed int v9; // ebx
  HANDLE Thread; // rax
  int v11; // edx
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  bool v14; // sf

  v4 = operator new(0x38u);
  v5 = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  v4[4] = 0;
  *v4 = 0;
  v4[6] = 0;
  v4[1] = 0;
  v4[2] = 0;
  *((_DWORD *)v4 + 6) = 0;
  *((_DWORD *)v4 + 11) = GetCurrentThreadId();
  v5[2] = a1;
  EventA = CreateEventA(0, 0, 0, 0);
  v5[6] = EventA;
  if ( EventA && (Thread = CreateThread(0, 0, CTimer::ThreadCallback, v5, 0, (LPDWORD)v5 + 10), (v5[4] = Thread) != 0) )
  {
    PumpWaitForSingleObject((void *)v5[6], v11, v12, v13);
    CloseHandle((HANDLE)v5[6]);
    v9 = *((_DWORD *)v5 + 6);
    v5[6] = 0;
    v14 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v14 = v9 < 0;
    }
    if ( !v14 )
    {
      *a2 = (struct CTimer *)v5;
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  CTimer::`scalar deleting destructor'((CTimer *)v5, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140002054  mov     [rsp+arg_0], rbx
0x140002059  mov     [rsp+arg_8], rsi
0x14000205e  push    rdi
0x14000205f  sub     rsp, 30h
0x140002063  mov     rbx, rcx
0x140002066  mov     rsi, rdx
0x140002069  mov     ecx, 38h ; '8'; Size
0x14000206e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002073  mov     rdi, rax
0x140002076  test    rax, rax
0x140002079  jz      loc_140002156
0x14000207f  mov     qword ptr [rax+20h], 0
0x140002087  mov     qword ptr [rax], 0
0x14000208e  mov     qword ptr [rax+30h], 0
0x140002096  mov     qword ptr [rax+8], 0
0x14000209e  mov     qword ptr [rax+10h], 0
0x1400020a6  mov     dword ptr [rax+18h], 0
0x1400020ad  call    cs:__imp_GetCurrentThreadId
0x1400020b3  mov     [rdi+2Ch], eax
0x1400020b6  xor     r9d, r9d; lpName
0x1400020b9  xor     r8d, r8d; bInitialState
0x1400020bc  mov     [rdi+10h], rbx
0x1400020c0  xor     edx, edx; bManualReset
0x1400020c2  xor     ecx, ecx; lpEventAttributes
0x1400020c4  call    cs:__imp_CreateEventA
0x1400020ca  mov     [rdi+30h], rax
0x1400020ce  test    rax, rax
0x1400020d1  jnz     short loc_1400020F2
0x1400020d3  call    cs:__imp_GetLastError
0x1400020d9  mov     ebx, eax
0x1400020db  test    eax, eax
0x1400020dd  jle     short loc_1400020E8
0x1400020df  movzx   ebx, ax
0x1400020e2  or      ebx, 80070000h
0x1400020e8  mov     rcx, rdi; this
0x1400020eb  call    ??_GCTimer@@QEAAPEAXI@Z; CTimer::`scalar deleting destructor'(uint)
0x1400020f0  jmp     short loc_14000215B
0x1400020f2  lea     rax, [rdi+28h]
0x1400020f6  mov     r9, rdi; lpParameter
0x1400020f9  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1400020fe  lea     r8, ?ThreadCallback@CTimer@@KAKPEAX@Z; lpStartAddress
0x140002105  xor     edx, edx; dwStackSize
0x140002107  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14000210f  xor     ecx, ecx; lpThreadAttributes
0x140002111  call    cs:__imp_CreateThread
0x140002117  mov     [rdi+20h], rax
0x14000211b  test    rax, rax
0x14000211e  jz      short loc_1400020D3
0x140002120  mov     rcx, [rdi+30h]; void *
0x140002124  call    ?PumpWaitForSingleObject@@YAKPEAXHKK@Z; PumpWaitForSingleObject(void *,int,ulong,ulong)
0x140002129  mov     rcx, [rdi+30h]; hObject
0x14000212d  call    cs:__imp_CloseHandle
0x140002133  mov     ebx, [rdi+18h]
0x140002136  mov     qword ptr [rdi+30h], 0
0x14000213e  test    ebx, ebx
0x140002140  jle     short loc_14000214D
0x140002142  movzx   ebx, bx
0x140002145  or      ebx, 80070000h
0x14000214b  test    ebx, ebx
0x14000214d  js      short loc_1400020E8
0x14000214f  mov     [rsi], rdi
0x140002152  xor     ebx, ebx
0x140002154  jmp     short loc_14000215B
0x140002156  mov     ebx, 8007000Eh
0x14000215b  mov     rsi, [rsp+38h+arg_8]
0x140002160  mov     eax, ebx
0x140002162  mov     rbx, [rsp+38h+arg_0]
0x140002167  add     rsp, 30h
0x14000216b  pop     rdi
0x14000216c  retn
```
