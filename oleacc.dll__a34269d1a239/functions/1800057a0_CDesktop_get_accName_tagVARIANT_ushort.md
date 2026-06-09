# CDesktop::get_accName(tagVARIANT,ushort * *)

- ea: `0x1800057a0`
- end: `0x180005901`
- name: `?get_accName@CDesktop@@UEAAJUtagVARIANT@@PEAPEAG@Z`
- size: `353`
- prototype: `int(CDesktop *__hidden this, struct tagVARIANT *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800057a0`
- `0x180006288`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005891`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005891`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005862`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005862`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800057cf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000587e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000587e`

## pseudocode

```c
__int64 __fastcall CDesktop::get_accName(CDesktop *this, struct tagVARIANT *a2, unsigned __int16 **a3)
{
  volatile signed __int32 *v4; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  unsigned int String; // esi
  HANDLE EventW; // rax
  unsigned __int16 *v10; // rax

  *a3 = 0;
  if ( !(*(unsigned int (__fastcall **)(CDesktop *, struct tagVARIANT *))(*(_QWORD *)this + 240LL))(this, a2) )
    return 2147942487LL;
  v4 = (volatile signed __int32 *)LocalAlloc(0x40u, 0x28u);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
    goto LABEL_4;
  }
  *((_DWORD *)v4 + 2) = 1;
  v6 = (__int64)(v4 + 2);
  *(_QWORD *)v4 = &off_18004BF30;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = 0;
  *((_DWORD *)v4 + 8) = 0;
  _InterlockedAdd(v4 + 2, 1u);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v5 + 3) = EventW;
  if ( !EventW || !QueueUserWorkItem((LPTHREAD_START_ROUTINE)GetCurrentDesktopNameWorker, (PVOID)v5, 0) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(HLOCAL, __int64))v5)((HLOCAL)v5, 1);
    goto LABEL_4;
  }
  if ( WaitForSingleObject(*((HANDLE *)v5 + 3), 0x1F4u) || *((int *)v5 + 8) < 0 )
  {
LABEL_4:
    String = HrCreateString(0x126u, a3);
    if ( v5 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(HLOCAL, __int64))v5)((HLOCAL)v5, 1);
    }
    return String;
  }
  v10 = (unsigned __int16 *)*((_QWORD *)v5 + 2);
  *((_QWORD *)v5 + 2) = 0;
  *a3 = v10;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(HLOCAL, __int64))v5)((HLOCAL)v5, 1);
  return 0;
}

```

## disassembly

```asm
0x1800057a0  push    rbx
0x1800057a2  push    rsi
0x1800057a3  push    rdi
0x1800057a4  push    r15
0x1800057a6  sub     rsp, 28h
0x1800057aa  mov     qword ptr [r8], 0
0x1800057b1  mov     rsi, r8
0x1800057b4  mov     rax, [rcx]
0x1800057b7  mov     rax, [rax+0F0h]
0x1800057be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c3  test    eax, eax
0x1800057c5  jz      short loc_18000581B
0x1800057c7  mov     edx, 28h ; '('; uBytes
0x1800057cc  lea     ecx, [rdx+18h]; uFlags
0x1800057cf  call    cs:__imp_LocalAlloc
0x1800057d5  mov     rbx, rax
0x1800057d8  mov     r15d, 1
0x1800057de  test    rax, rax
0x1800057e1  jnz     short loc_18000582A
0x1800057e3  lea     edi, [rax+8]
0x1800057e6  mov     rdx, rsi; unsigned __int16 **
0x1800057e9  mov     ecx, 126h; uID
0x1800057ee  call    ?HrCreateString@@YAJHPEAPEAG@Z
0x1800057f3  mov     esi, eax
0x1800057f5  test    rbx, rbx
0x1800057f8  jz      short loc_180005817
0x1800057fa  or      edx, 0FFFFFFFFh
0x1800057fd  lock xadd [rdi], edx
0x180005801  cmp     edx, r15d
0x180005804  jnz     short loc_180005817
0x180005806  mov     rdx, [rbx]
0x180005809  mov     rcx, rbx
0x18000580c  mov     rax, [rdx]
0x18000580f  mov     edx, r15d
0x180005812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005817  mov     eax, esi
0x180005819  jmp     short loc_180005820
0x18000581b  mov     eax, 80070057h
0x180005820  add     rsp, 28h
0x180005824  pop     r15
0x180005826  pop     rdi
0x180005827  pop     rsi
0x180005828  pop     rbx
0x180005829  retn
0x18000582a  mov     [rax+8], r15d
0x18000582e  lea     rdi, [rbx+8]
0x180005832  lea     rax, off_18004BF30
0x180005839  mov     [rbx], rax
0x18000583c  mov     qword ptr [rbx+10h], 0
0x180005844  mov     qword ptr [rbx+18h], 0
0x18000584c  mov     dword ptr [rbx+20h], 0
0x180005853  lock add [rdi], r15d
0x180005857  xor     r9d, r9d; lpName
0x18000585a  xor     r8d, r8d; bInitialState
0x18000585d  mov     edx, r15d; bManualReset
0x180005860  xor     ecx, ecx; lpEventAttributes
0x180005862  call    cs:__imp_CreateEventW
0x180005868  mov     [rbx+18h], rax
0x18000586c  test    rax, rax
0x18000586f  jz      short loc_1800058DB
0x180005871  xor     r8d, r8d; Flags
0x180005874  lea     rcx, ?GetCurrentDesktopNameWorker@@YAKPEAX@Z; Function
0x18000587b  mov     rdx, rbx; Context
0x18000587e  call    cs:__imp_QueueUserWorkItem
0x180005884  test    eax, eax
0x180005886  jz      short loc_1800058DB
0x180005888  mov     rcx, [rbx+18h]; hHandle
0x18000588c  mov     edx, 1F4h; dwMilliseconds
0x180005891  call    cs:__imp_WaitForSingleObject
0x180005897  test    eax, eax
0x180005899  jnz     loc_1800057E6
0x18000589f  cmp     [rbx+20h], eax
0x1800058a2  jl      loc_1800057E6
0x1800058a8  mov     rax, [rbx+10h]
0x1800058ac  mov     qword ptr [rbx+10h], 0
0x1800058b4  mov     [rsi], rax
0x1800058b7  or      eax, 0FFFFFFFFh
0x1800058ba  lock xadd [rdi], eax
0x1800058be  cmp     eax, r15d
0x1800058c1  jnz     short loc_1800058D4
0x1800058c3  mov     rax, [rbx]
0x1800058c6  mov     edx, r15d
0x1800058c9  mov     rcx, rbx
0x1800058cc  mov     rax, [rax]
0x1800058cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d4  xor     eax, eax
0x1800058d6  jmp     loc_180005820
0x1800058db  or      eax, 0FFFFFFFFh
0x1800058de  lock xadd [rdi], eax
0x1800058e2  cmp     eax, r15d
0x1800058e5  jnz     loc_1800057E6
0x1800058eb  mov     rax, [rbx]
0x1800058ee  mov     edx, r15d
0x1800058f1  mov     rcx, rbx
0x1800058f4  mov     rax, [rax]
0x1800058f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058fc  jmp     loc_1800057E6
```
