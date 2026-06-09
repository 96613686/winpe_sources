# LOSSY_QUEUE::Initialize(ulong)

- ea: `0x18000a934`
- end: `0x18000aacc`
- name: `?Initialize@LOSSY_QUEUE@@QEAAJK@Z`
- size: `408`
- prototype: `__int64 __fastcall(LOSSY_QUEUE *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008424`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000a934`
- `0x18000ac52`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a955`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a977`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a955`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a977`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a992`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a992`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aa77`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aa77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a99c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a99c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa9c`

## pseudocode

```c
__int64 __fastcall LOSSY_QUEUE::Initialize(LOSSY_QUEUE *this)
{
  unsigned int *v1; // rdi
  int v2; // r14d
  int v3; // ebp
  HANDLE EventW; // rax
  int v5; // esi
  HANDLE v6; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  void *v9; // rax
  void *v10; // rax
  void *v11; // rax
  void *v12; // rcx
  void *v13; // rcx

  v1 = (unsigned int *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue;
  v2 = 0;
  v3 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v1 + 9) = EventW;
  if ( EventW )
  {
    v5 = 1;
    v6 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v1 + 10) = v6;
    if ( v6 )
    {
      v2 = 1;
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v1 + 8), 0xFA0u) )
      {
        *v1 = 100;
        v3 = 1;
        v9 = operator new(0x320u);
        *((_QWORD *)v1 + 1) = v9;
        if ( v9 )
        {
          memset_0(v9, 0, 8LL * *v1);
          v10 = operator new(saturated_mul(*v1, 8u));
          *((_QWORD *)v1 + 2) = v10;
          if ( v10 )
          {
            memset_0(v10, 0, 8LL * *v1);
            v11 = operator new(saturated_mul(*v1, 4u));
            *((_QWORD *)v1 + 3) = v11;
            if ( v11 )
            {
              v8 = 0;
              memset_0(v11, 0, 4LL * *v1);
              return v8;
            }
          }
        }
        v8 = -2147024888;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v5 = 0;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
LABEL_13:
    v12 = (void *)*((_QWORD *)v1 + 1);
    if ( v12 )
    {
      operator delete(v12);
      *((_QWORD *)v1 + 1) = 0;
    }
    v13 = (void *)*((_QWORD *)v1 + 2);
    if ( v13 )
    {
      operator delete(v13);
      *((_QWORD *)v1 + 2) = 0;
    }
    if ( v3 )
      DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
    if ( v5 )
    {
      CloseHandle(*((HANDLE *)v1 + 9));
      *((_QWORD *)v1 + 9) = 0;
    }
    if ( v2 )
    {
      CloseHandle(*((HANDLE *)v1 + 10));
      *((_QWORD *)v1 + 10) = 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000a934  push    rbx
0x18000a936  push    rbp
0x18000a937  push    rsi
0x18000a938  push    rdi
0x18000a939  push    r14
0x18000a93b  sub     rsp, 20h
0x18000a93f  mov     rdi, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x18000a946  xor     r9d, r9d; lpName
0x18000a949  xor     r8d, r8d; bInitialState
0x18000a94c  xor     edx, edx; bManualReset
0x18000a94e  xor     ecx, ecx; lpEventAttributes
0x18000a950  xor     r14d, r14d
0x18000a953  xor     ebp, ebp
0x18000a955  call    cs:__imp_CreateEventW
0x18000a95b  mov     [rdi+48h], rax
0x18000a95f  test    rax, rax
0x18000a962  jnz     short loc_18000A968
0x18000a964  xor     esi, esi
0x18000a966  jmp     short loc_18000A99C
0x18000a968  mov     esi, 1
0x18000a96d  xor     r9d, r9d; lpName
0x18000a970  mov     edx, esi; bManualReset
0x18000a972  xor     r8d, r8d; bInitialState
0x18000a975  xor     ecx, ecx; lpEventAttributes
0x18000a977  call    cs:__imp_CreateEventW
0x18000a97d  mov     [rdi+50h], rax
0x18000a981  test    rax, rax
0x18000a984  jz      short loc_18000A99C
0x18000a986  lea     rcx, [rdi+20h]; lpCriticalSection
0x18000a98a  mov     edx, 0FA0h; dwSpinCount
0x18000a98f  mov     r14d, esi
0x18000a992  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000a998  test    eax, eax
0x18000a99a  jnz     short loc_18000A9BE
0x18000a99c  call    cs:__imp_GetLastError
0x18000a9a2  mov     ebx, eax
0x18000a9a4  test    eax, eax
0x18000a9a6  jle     short loc_18000A9B1
0x18000a9a8  movzx   ebx, ax
0x18000a9ab  or      ebx, 80070000h
0x18000a9b1  test    ebx, ebx
0x18000a9b3  jns     loc_18000AABF
0x18000a9b9  jmp     loc_18000AA43
0x18000a9be  mov     ecx, 320h; Size
0x18000a9c3  mov     dword ptr [rdi], 64h ; 'd'
0x18000a9c9  mov     ebp, esi
0x18000a9cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a9d0  mov     [rdi+8], rax
0x18000a9d4  test    rax, rax
0x18000a9d7  jz      short loc_18000AA3E
0x18000a9d9  mov     r8d, [rdi]
0x18000a9dc  xor     edx, edx; Val
0x18000a9de  shl     r8, 3; Size
0x18000a9e2  mov     rcx, rax; void *
0x18000a9e5  call    memset_0
0x18000a9ea  mov     ecx, [rdi]
0x18000a9ec  mov     eax, 8
0x18000a9f1  mul     rcx
0x18000a9f4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a9fb  cmovb   rax, rbx
0x18000a9ff  mov     rcx, rax; Size
0x18000aa02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa07  mov     [rdi+10h], rax
0x18000aa0b  test    rax, rax
0x18000aa0e  jz      short loc_18000AA3E
0x18000aa10  mov     r8d, [rdi]
0x18000aa13  xor     edx, edx; Val
0x18000aa15  shl     r8, 3; Size
0x18000aa19  mov     rcx, rax; void *
0x18000aa1c  call    memset_0
0x18000aa21  mov     ecx, [rdi]
0x18000aa23  lea     eax, [rbx+5]
0x18000aa26  mul     rcx
0x18000aa29  cmovb   rax, rbx
0x18000aa2d  mov     rcx, rax; Size
0x18000aa30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa35  mov     [rdi+18h], rax
0x18000aa39  test    rax, rax
0x18000aa3c  jnz     short loc_18000AAAC
0x18000aa3e  mov     ebx, 80070008h
0x18000aa43  mov     rcx, [rdi+8]; Block
0x18000aa47  test    rcx, rcx
0x18000aa4a  jz      short loc_18000AA59
0x18000aa4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa51  mov     qword ptr [rdi+8], 0
0x18000aa59  mov     rcx, [rdi+10h]; Block
0x18000aa5d  test    rcx, rcx
0x18000aa60  jz      short loc_18000AA6F
0x18000aa62  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa67  mov     qword ptr [rdi+10h], 0
0x18000aa6f  test    ebp, ebp
0x18000aa71  jz      short loc_18000AA7D
0x18000aa73  lea     rcx, [rdi+20h]; lpCriticalSection
0x18000aa77  call    cs:__imp_DeleteCriticalSection
0x18000aa7d  test    esi, esi
0x18000aa7f  jz      short loc_18000AA93
0x18000aa81  mov     rcx, [rdi+48h]; hObject
0x18000aa85  call    cs:__imp_CloseHandle
0x18000aa8b  mov     qword ptr [rdi+48h], 0
0x18000aa93  test    r14d, r14d
0x18000aa96  jz      short loc_18000AABF
0x18000aa98  mov     rcx, [rdi+50h]; hObject
0x18000aa9c  call    cs:__imp_CloseHandle
0x18000aaa2  mov     qword ptr [rdi+50h], 0
0x18000aaaa  jmp     short loc_18000AABF
0x18000aaac  mov     r8d, [rdi]
0x18000aaaf  xor     ebx, ebx
0x18000aab1  shl     r8, 2; Size
0x18000aab5  xor     edx, edx; Val
0x18000aab7  mov     rcx, rax; void *
0x18000aaba  call    memset_0
0x18000aabf  mov     eax, ebx
0x18000aac1  add     rsp, 20h
0x18000aac5  pop     r14
0x18000aac7  pop     rdi
0x18000aac8  pop     rsi
0x18000aac9  pop     rbp
0x18000aaca  pop     rbx
0x18000aacb  retn
```
