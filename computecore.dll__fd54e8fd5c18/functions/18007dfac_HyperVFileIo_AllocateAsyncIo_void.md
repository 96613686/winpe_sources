# HyperVFileIo::AllocateAsyncIo(void)

- ea: `0x18007dfac`
- end: `0x18007e069`
- name: `?AllocateAsyncIo@HyperVFileIo@@AEAAPEAVHyperVAsyncIo@@XZ`
- size: `189`
- prototype: `struct HyperVAsyncIo *__fastcall(HyperVFileIo *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180080590`
- `0x180081090`
- `0x1800819c0`

## callees

- `0x1800067e4`
- `0x18007dfac`
- `0x18008226c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e027`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e05b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e05b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18007dfbd`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18007dfbd`

## pseudocode

```c
struct _SLIST_ENTRY *__fastcall HyperVFileIo::AllocateAsyncIo(union _SLIST_HEADER *this)
{
  PSLIST_ENTRY v2; // rax
  struct _SLIST_ENTRY *v3; // rbx
  HANDLE EventW; // rax
  DWORD LastError; // eax

  v2 = InterlockedPopEntrySList(this + 6);
  if ( !v2 || (v3 = v2 - 6, v2 == (PSLIST_ENTRY)96) )
  {
    v3 = (struct _SLIST_ENTRY *)operator new(0x70u);
    v3->Next = (struct _SLIST_ENTRY *)&HyperVAsyncIo::`vftable';
    v3[4].Next = 0;
    v3[5].Next = 0;
    *((_QWORD *)&v3->Next + 1) = this;
    v3[3].Next = 0;
    *((_QWORD *)&v3[3].Next + 1) = 0;
    *((_BYTE *)&v3[4].Next + 8) = 0;
    v3[1] = 0;
    v3[2] = 0;
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)&v3[2].Next + 1) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      HvsThrowWin32Error(LastError);
    }
    v3[6].Next = 0;
    v3->Next = (struct _SLIST_ENTRY *)&HvsInterlockedSList<HyperVAsyncIo>::Element::`vftable';
  }
  _InterlockedIncrement64((volatile signed __int64 *)&this[7]);
  return v3;
}

```

## disassembly

```asm
0x18007dfac  mov     [rsp+arg_0], rbx
0x18007dfb1  push    rdi
0x18007dfb2  sub     rsp, 20h
0x18007dfb6  mov     rdi, rcx
0x18007dfb9  add     rcx, 60h ; '`'; ListHead
0x18007dfbd  call    cs:__imp_InterlockedPopEntrySList
0x18007dfc3  test    rax, rax
0x18007dfc6  jz      short loc_18007DFD1
0x18007dfc8  lea     rbx, [rax-60h]
0x18007dfcc  test    rbx, rbx
0x18007dfcf  jnz     short loc_18007E048
0x18007dfd1  mov     ecx, 70h ; 'p'; Size
0x18007dfd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007dfdb  mov     rbx, rax
0x18007dfde  xorps   xmm0, xmm0
0x18007dfe1  xor     r9d, r9d; lpName
0x18007dfe4  lea     rax, ??_7HyperVAsyncIo@@6B@; const HyperVAsyncIo::`vftable'
0x18007dfeb  xor     ecx, ecx; lpEventAttributes
0x18007dfed  mov     [rbx], rax
0x18007dff0  mov     qword ptr [rbx+40h], 0
0x18007dff8  lea     edx, [r9+1]; bManualReset
0x18007dffc  mov     qword ptr [rbx+50h], 0
0x18007e004  mov     r8d, edx; bInitialState
0x18007e007  mov     [rbx+8], rdi
0x18007e00b  mov     qword ptr [rbx+30h], 0
0x18007e013  mov     qword ptr [rbx+38h], 0
0x18007e01b  mov     byte ptr [rbx+48h], 0
0x18007e01f  movups  xmmword ptr [rbx+10h], xmm0
0x18007e023  movups  xmmword ptr [rbx+20h], xmm0
0x18007e027  call    cs:__imp_CreateEventW
0x18007e02d  mov     [rbx+28h], rax
0x18007e031  test    rax, rax
0x18007e034  jz      short loc_18007E05B
0x18007e036  lea     rax, ??_7Element@?$HvsInterlockedSList@VHyperVAsyncIo@@@@6B@; const HvsInterlockedSList<HyperVAsyncIo>::Element::`vftable'
0x18007e03d  mov     qword ptr [rbx+60h], 0
0x18007e045  mov     [rbx], rax
0x18007e048  lock inc qword ptr [rdi+70h]
0x18007e04d  mov     rax, rbx
0x18007e050  mov     rbx, [rsp+28h+arg_0]
0x18007e055  add     rsp, 20h
0x18007e059  pop     rdi
0x18007e05a  retn
0x18007e05b  call    cs:__imp_GetLastError
0x18007e061  mov     ecx, eax; unsigned int
0x18007e063  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
```
