# SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)

- ea: `0x140018850`
- end: `0x14001891c`
- name: `?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ`
- size: `204`
- prototype: `void(int, int, const char *, wchar_t *Format, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000e290`
- `0x140016818`
- `0x14001691c`
- `0x140016c84`

## callees

- `0x1400031d8`
- `0x140018700`
- `0x140018850`

## import_xrefs

- `msvcrt!vswprintf_s` at `0x1400188d1`
- `msvcrt!vswprintf_s` at `0x1400188d1`
- `msvcrt!_vscwprintf` at `0x140018885`
- `msvcrt!_vscwprintf` at `0x140018885`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140018902`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140018902`

## string_xrefs

- `0x1400188df`: `No description available: Failed to copy description to buffer`

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
0x140018850  test    r9, r9
0x140018853  jz      locret_14001891A
0x140018859  mov     rax, rsp
0x14001885c  mov     [rax+20h], r9
0x140018860  push    rbx
0x140018861  push    rbp
0x140018862  push    rsi
0x140018863  push    rdi
0x140018864  push    r14
0x140018866  push    r15
0x140018868  sub     rsp, 38h
0x14001886c  lea     r15, [rax+28h]
0x140018870  mov     qword ptr [rax-48h], 0
0x140018878  mov     esi, edx
0x14001887a  mov     ebp, ecx
0x14001887c  mov     rdx, r15; ArgList
0x14001887f  mov     rcx, r9; Format
0x140018882  mov     rdi, r8
0x140018885  call    cs:__imp__vscwprintf
0x14001888c  nop     dword ptr [rax+rax+00h]
0x140018891  inc     eax
0x140018893  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14001889a  movsxd  r14, eax
0x14001889d  mov     eax, 2
0x1400188a2  mul     r14
0x1400188a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400188ac  cmovb   rax, rcx
0x1400188b0  mov     rcx, rax; unsigned __int64
0x1400188b3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400188b8  mov     rbx, rax
0x1400188bb  test    rax, rax
0x1400188be  jz      short loc_1400188EC
0x1400188c0  mov     r8, [rsp+68h+Format]; Format
0x1400188c8  mov     r9, r15; ArgList
0x1400188cb  mov     rdx, r14; BufferCount
0x1400188ce  mov     rcx, rax; Buffer
0x1400188d1  call    cs:__imp_vswprintf_s
0x1400188d8  nop     dword ptr [rax+rax+00h]
0x1400188dd  test    eax, eax
0x1400188df  lea     r9, aNoDescriptionA_0; "No description available: Failed to cop"...
0x1400188e6  cmovg   r9, rbx
0x1400188ea  jmp     short loc_1400188F3
0x1400188ec  lea     r9, aNoDescriptionA; "No description available: Failed to all"...
0x1400188f3  mov     r8, rdi; char *
0x1400188f6  mov     edx, esi; int
0x1400188f8  mov     ecx, ebp; int
0x1400188fa  call    ?WriteErrorTrace@SuifTraceLogging@@CAXJHPEBDPEBG@Z; SuifTraceLogging::WriteErrorTrace(long,int,char const *,ushort const *)
0x1400188ff  mov     rcx, rbx
0x140018902  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140018909  nop     dword ptr [rax+rax+00h]
0x14001890e  add     rsp, 38h
0x140018912  pop     r15
0x140018914  pop     r14
0x140018916  pop     rdi
0x140018917  pop     rsi
0x140018918  pop     rbp
0x140018919  pop     rbx
0x14001891a  retn
```
