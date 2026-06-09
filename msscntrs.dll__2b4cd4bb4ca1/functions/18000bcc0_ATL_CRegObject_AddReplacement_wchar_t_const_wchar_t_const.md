# ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)

- ea: `0x18000bcc0`
- end: `0x18000bd26`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ba7c`
- `0x18000bcc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bce0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bce0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd04`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(ATL::CRegObject *this, const wchar_t *a2, const wchar_t *a3)
{
  int v6; // ebx

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18000bcc0  push    rbx
0x18000bcc2  push    rbp
0x18000bcc3  push    rsi
0x18000bcc4  push    rdi
0x18000bcc5  sub     rsp, 28h
0x18000bcc9  mov     rbx, r8
0x18000bccc  mov     rsi, rdx
0x18000bccf  mov     rbp, rcx
0x18000bcd2  test    rdx, rdx
0x18000bcd5  jz      short loc_18000BD18
0x18000bcd7  test    rbx, rbx
0x18000bcda  jz      short loc_18000BD18
0x18000bcdc  add     rcx, 20h ; ' '; lpCriticalSection
0x18000bce0  call    cs:__imp_EnterCriticalSection
0x18000bce6  mov     [rsp+48h+arg_8], 0
0x18000bcef  lea     rcx, [rbp+8]; this
0x18000bcf3  mov     r8, rbx; wchar_t *
0x18000bcf6  mov     rdx, rsi; wchar_t *
0x18000bcf9  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x18000bcfe  mov     ebx, eax
0x18000bd00  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000bd04  call    cs:__imp_LeaveCriticalSection
0x18000bd0a  nop
0x18000bd0b  neg     ebx
0x18000bd0d  sbb     eax, eax
0x18000bd0f  not     eax
0x18000bd11  and     eax, 8007000Eh
0x18000bd16  jmp     short loc_18000BD1D
0x18000bd18  mov     eax, 80070057h
0x18000bd1d  add     rsp, 28h
0x18000bd21  pop     rdi
0x18000bd22  pop     rsi
0x18000bd23  pop     rbp
0x18000bd24  pop     rbx
0x18000bd25  retn
```
