# SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)

- ea: `0x140017fbc`
- end: `0x140018075`
- name: `?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ`
- size: `185`
- prototype: `void(int, int, const char *, wchar_t *Format, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000dd30`
- `0x140017a80`
- `0x140017b80`
- `0x140017d90`

## callees

- `0x140003198`
- `0x140017e70`
- `0x140017fbc`

## import_xrefs

- `msvcrt!vswprintf_s` at `0x140018037`
- `msvcrt!vswprintf_s` at `0x140018037`
- `msvcrt!_vscwprintf` at `0x140017ff1`
- `msvcrt!_vscwprintf` at `0x140017ff1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140018062`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140018062`

## string_xrefs

- `0x14001803f`: `No description available: Failed to copy description to buffer`

## pseudocode

```c
void SuifTraceLogging::WriteErrorTraceFormat(int a1, int a2, const char *a3, wchar_t *Format, ...)
{
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rax
  wchar_t *v9; // rax
  wchar_t *v10; // rbx
  int v11; // eax
  const unsigned __int16 *v12; // r9
  va_list va; // [rsp+90h] [rbp+28h] BYREF

  va_start(va, Format);
  if ( Format )
  {
    v7 = _vscwprintf(Format, va) + 1;
    v8 = 2 * v7;
    if ( !is_mul_ok(v7, 2u) )
      v8 = -1;
    v9 = (wchar_t *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
    {
      v11 = vswprintf_s(v9, v7, Format, va);
      v12 = L"No description available: Failed to copy description to buffer";
      if ( v11 > 0 )
        v12 = v10;
    }
    else
    {
      v12 = L"No description available: Failed to allocate buffer";
    }
    SuifTraceLogging::WriteErrorTrace(a1, a2, a3, v12);
    operator delete[](v10);
  }
}

```

## disassembly

```asm
0x140017fbc  test    r9, r9
0x140017fbf  jz      locret_140018074
0x140017fc5  mov     rax, rsp
0x140017fc8  mov     [rax+20h], r9
0x140017fcc  push    rbx
0x140017fcd  push    rbp
0x140017fce  push    rsi
0x140017fcf  push    rdi
0x140017fd0  push    r14
0x140017fd2  push    r15
0x140017fd4  sub     rsp, 38h
0x140017fd8  lea     r15, [rax+28h]
0x140017fdc  mov     qword ptr [rax-48h], 0
0x140017fe4  mov     esi, edx
0x140017fe6  mov     ebp, ecx
0x140017fe8  mov     rdx, r15; ArgList
0x140017feb  mov     rcx, r9; Format
0x140017fee  mov     rdi, r8
0x140017ff1  call    cs:__imp__vscwprintf
0x140017ff7  inc     eax
0x140017ff9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140018000  movsxd  r14, eax
0x140018003  mov     eax, 2
0x140018008  mul     r14
0x14001800b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018012  cmovb   rax, rcx
0x140018016  mov     rcx, rax; unsigned __int64
0x140018019  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001801e  mov     rbx, rax
0x140018021  test    rax, rax
0x140018024  jz      short loc_14001804C
0x140018026  mov     r8, [rsp+68h+Format]; Format
0x14001802e  mov     r9, r15; ArgList
0x140018031  mov     rdx, r14; BufferCount
0x140018034  mov     rcx, rax; Buffer
0x140018037  call    cs:__imp_vswprintf_s
0x14001803d  test    eax, eax
0x14001803f  lea     r9, aNoDescriptionA_0; "No description available: Failed to cop"...
0x140018046  cmovg   r9, rbx
0x14001804a  jmp     short loc_140018053
0x14001804c  lea     r9, aNoDescriptionA; "No description available: Failed to all"...
0x140018053  mov     r8, rdi; char *
0x140018056  mov     edx, esi; int
0x140018058  mov     ecx, ebp; int
0x14001805a  call    ?WriteErrorTrace@SuifTraceLogging@@CAXJHPEBDPEBG@Z; SuifTraceLogging::WriteErrorTrace(long,int,char const *,ushort const *)
0x14001805f  mov     rcx, rbx
0x140018062  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140018068  add     rsp, 38h
0x14001806c  pop     r15
0x14001806e  pop     r14
0x140018070  pop     rdi
0x140018071  pop     rsi
0x140018072  pop     rbp
0x140018073  pop     rbx
0x140018074  retn
```
