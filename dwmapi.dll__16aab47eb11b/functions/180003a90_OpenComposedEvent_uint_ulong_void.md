# OpenComposedEvent(uint,ulong,void * *)

- ea: `0x180003a90`
- end: `0x180003b28`
- name: `?OpenComposedEvent@@YAJIKPEAPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002200`

## callees

- `0x18000352c`
- `0x180003a90`
- `0x180003b30`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180003ad9`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180003ad9`

## string_xrefs

- `0x180003abd`: `DwmComposedEvent_`

## pseudocode

```c
__int64 __fastcall OpenComposedEvent(int a1, __int64 a2, void **a3)
{
  HANDLE v4; // rax
  void *v7; // [rsp+28h] [rbp-50h]
  WCHAR Name[28]; // [rsp+30h] [rbp-48h] BYREF

  if ( (int)StringCchPrintfW(Name, 0x1Au, L"%s%x", L"DwmComposedEvent_", a1) < 0 )
    return 0;
  v4 = OpenEventW(0x100000u, 0, Name);
  *a3 = v4;
  if ( v4 )
    return 0;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_18001A99C, 1u, -2144980991, 0x2Eu, v7);
  return 2149986305LL;
}

```

## disassembly

```asm
0x180003a90  push    rbx
0x180003a92  sub     rsp, 70h
0x180003a96  mov     rax, cs:__security_cookie
0x180003a9d  xor     rax, rsp
0x180003aa0  mov     [rsp+78h+var_10], rax
0x180003aa5  mov     rbx, r8
0x180003aa8  mov     [rsp+78h+var_58], ecx
0x180003aac  lea     r8, aSX; "%s%x"
0x180003ab3  mov     edx, 1Ah; unsigned __int64
0x180003ab8  lea     rcx, [rsp+78h+Name]; unsigned __int16 *
0x180003abd  lea     r9, aDwmcomposedeve; "DwmComposedEvent_"
0x180003ac4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ac9  test    eax, eax
0x180003acb  js      short loc_180003AE7
0x180003acd  lea     r8, [rsp+78h+Name]; lpName
0x180003ad2  xor     edx, edx; bInheritHandle
0x180003ad4  mov     ecx, 100000h; dwDesiredAccess
0x180003ad9  call    cs:__imp_OpenEventW
0x180003adf  mov     [rbx], rax
0x180003ae2  test    rax, rax
0x180003ae5  jz      short loc_180003AFC
0x180003ae7  xor     eax, eax
0x180003ae9  mov     rcx, [rsp+78h+var_10]
0x180003aee  xor     rcx, rsp; StackCookie
0x180003af1  call    __security_check_cookie
0x180003af6  add     rsp, 70h
0x180003afa  pop     rbx
0x180003afb  retn
0x180003afc  mov     r9d, 80263001h; int
0x180003b02  mov     [rsp+78h+var_58], 2Eh ; '.'; unsigned int
0x180003b0a  mov     r8d, 1; unsigned int
0x180003b10  lea     rdx, dword_18001A99C; int *
0x180003b17  mov     ecx, 14h; unsigned int
0x180003b1c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180003b21  mov     eax, 80263001h
0x180003b26  jmp     short loc_180003AE9
```
