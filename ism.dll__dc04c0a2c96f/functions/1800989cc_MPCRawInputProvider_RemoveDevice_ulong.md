# MPCRawInputProvider::RemoveDevice(ulong)

- ea: `0x1800989cc`
- end: `0x180098a65`
- name: `?RemoveDevice@MPCRawInputProvider@@QEAAJK@Z`
- size: `153`
- prototype: `__int64 __fastcall(MPCRawInputProvider *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801168fc`

## callees

- `0x1800989cc`
- `0x1800996c8`
- `0x1800b9d88`
- `0x1801159ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800989e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800989e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098a0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098a0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098a4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098a4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MPCRawInputProvider::RemoveDevice(MPCRawInputProvider *this, unsigned int a2)
{
  int v4; // ebx
  unsigned int *v5; // rdx
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = a2;
  v4 = *((_DWORD *)this + 22);
  if ( GetCurrentThreadId() == v4 && *((_BYTE *)this + 80) )
  {
    MPCRawInputProvider::RemoveDeviceImpl(this, a2);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v5 = (unsigned int *)*((_QWORD *)this + 21);
    if ( v5 == *((unsigned int **)this + 22) )
    {
      std::vector<Windows::UI::Color>::_Emplace_reallocate<Windows::UI::Color const &>((char *)this + 160, v5, &v7);
    }
    else
    {
      *v5 = a2;
      *((_QWORD *)this + 21) += 4LL;
    }
    wil::details::SetEvent(*((wil::details **)this + 9), v5);
    if ( this != (MPCRawInputProvider *)-96LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  }
  return 0;
}

```

## disassembly

```asm
0x1800989cc  mov     [rsp+arg_10], rbx
0x1800989d1  mov     [rsp+arg_18], rsi
0x1800989d6  mov     [rsp+arg_8], edx
0x1800989da  push    rdi
0x1800989db  sub     rsp, 20h
0x1800989df  mov     esi, edx
0x1800989e1  mov     rdi, rcx
0x1800989e4  mov     ebx, [rcx+58h]
0x1800989e7  call    cs:__imp_GetCurrentThreadId
0x1800989ed  cmp     eax, ebx
0x1800989ef  jnz     short loc_180098A05
0x1800989f1  mov     al, [rdi+50h]
0x1800989f4  nop
0x1800989f5  test    al, al
0x1800989f7  jz      short loc_180098A05
0x1800989f9  mov     edx, esi; unsigned int
0x1800989fb  mov     rcx, rdi; this
0x1800989fe  call    ?RemoveDeviceImpl@MPCRawInputProvider@@AEAAXK@Z; MPCRawInputProvider::RemoveDeviceImpl(ulong)
0x180098a03  jmp     short loc_180098A53
0x180098a05  lea     rbx, [rdi+60h]
0x180098a09  mov     rcx, rbx; lpCriticalSection
0x180098a0c  call    cs:__imp_EnterCriticalSection
0x180098a12  mov     [rsp+28h+arg_0], rbx
0x180098a17  lea     rcx, [rdi+0A0h]
0x180098a1e  mov     rdx, [rcx+8]
0x180098a22  cmp     rdx, [rcx+10h]
0x180098a26  jz      short loc_180098A31
0x180098a28  mov     [rdx], esi
0x180098a2a  add     qword ptr [rcx+8], 4
0x180098a2f  jmp     short loc_180098A3B
0x180098a31  lea     r8, [rsp+28h+arg_8]
0x180098a36  call    ??$_Emplace_reallocate@AEBUColor@UI@Windows@@@?$vector@UColor@UI@Windows@@V?$allocator@UColor@UI@Windows@@@std@@@std@@AEAAPEAUColor@UI@Windows@@QEAU234@AEBU234@@Z; std::vector<Windows::UI::Color>::_Emplace_reallocate<Windows::UI::Color const &>(Windows::UI::Color * const,Windows::UI::Color const &)
0x180098a3b  mov     rcx, [rdi+48h]; this
0x180098a3f  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180098a44  nop
0x180098a45  test    rbx, rbx
0x180098a48  jz      short loc_180098A53
0x180098a4a  mov     rcx, rbx; lpCriticalSection
0x180098a4d  call    cs:__imp_LeaveCriticalSection
0x180098a53  xor     eax, eax
0x180098a55  mov     rbx, [rsp+28h+arg_10]
0x180098a5a  mov     rsi, [rsp+28h+arg_18]
0x180098a5f  add     rsp, 20h
0x180098a63  pop     rdi
0x180098a64  retn
```
