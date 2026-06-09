# CSearchRegistryRedirectHelper::Initialize(unsigned __int64)

- ea: `0x18001ffd8`
- end: `0x18002005d`
- name: `?Initialize@CSearchRegistryRedirectHelper@@QEAAJ_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ff00`

## callees

- `0x18001469c`
- `0x18001ffd8`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180020017`
- `ntdll!RtlGetPersistedStateLocation` at `0x180020017`
- `ntdll!RtlNtStatusToDosError` at `0x18002001f`
- `ntdll!RtlNtStatusToDosError` at `0x18002001f`

## string_xrefs

- `0x18002003d`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::Initialize(CSearchRegistryRedirectHelper *this, __int64 a2)
{
  NTSTATUS PersistedStateLocation; // eax
  signed int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)this = a2;
  v6 = (_DWORD)this + 8;
  PersistedStateLocation = RtlGetPersistedStateLocation(off_180035360[69 * a2], 0, off_180035360[69 * a2 + 1], 0);
  v3 = RtlNtStatusToDosError(PersistedStateLocation);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x36,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
    (const char *)v4,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18001ffd8  push    rbx
0x18001ffda  sub     rsp, 40h
0x18001ffde  mov     [rcx], rdx
0x18001ffe1  lea     r10, off_180035360; "WSearch"
0x18001ffe8  imul    rax, rdx, 228h
0x18001ffef  add     rcx, 8
0x18001fff3  mov     [rsp+48h+var_18], 0
0x18001fffc  mov     [rsp+48h+var_20], 208h
0x180020004  xor     r9d, r9d
0x180020007  mov     qword ptr [rsp+48h+var_28], rcx; int
0x18002000c  xor     edx, edx
0x18002000e  mov     r8, [rax+r10+8]
0x180020013  mov     rcx, [rax+r10]
0x180020017  call    cs:__imp_RtlGetPersistedStateLocation
0x18002001d  mov     ecx, eax; Status
0x18002001f  call    cs:__imp_RtlNtStatusToDosError
0x180020025  mov     ebx, eax
0x180020027  test    eax, eax
0x180020029  jle     short loc_180020034
0x18002002b  movzx   ebx, ax
0x18002002e  or      ebx, 80070000h
0x180020034  test    ebx, ebx
0x180020036  jns     short loc_180020055
0x180020038  mov     rcx, [rsp+48h]; this
0x18002003d  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\search\\com"...
0x180020044  mov     r9d, ebx; char *
0x180020047  mov     edx, 36h ; '6'; void *
0x18002004c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020051  mov     eax, ebx
0x180020053  jmp     short loc_180020057
0x180020055  xor     eax, eax
0x180020057  add     rsp, 40h
0x18002005b  pop     rbx
0x18002005c  retn
```
