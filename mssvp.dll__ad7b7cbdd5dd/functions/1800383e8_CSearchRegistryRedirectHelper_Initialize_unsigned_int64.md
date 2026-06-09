# CSearchRegistryRedirectHelper::Initialize(unsigned __int64)

- ea: `0x1800383e8`
- end: `0x18003846d`
- name: `?Initialize@CSearchRegistryRedirectHelper@@QEAAJ_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038310`

## callees

- `0x180011374`
- `0x1800383e8`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180038427`
- `ntdll!RtlGetPersistedStateLocation` at `0x180038427`
- `ntdll!RtlNtStatusToDosError` at `0x18003842f`
- `ntdll!RtlNtStatusToDosError` at `0x18003842f`

## string_xrefs

- `0x18003844d`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

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
  PersistedStateLocation = RtlGetPersistedStateLocation(off_180053580[69 * a2], 0, off_180053580[69 * a2 + 1], 0);
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
0x1800383e8  push    rbx
0x1800383ea  sub     rsp, 40h
0x1800383ee  mov     [rcx], rdx
0x1800383f1  lea     r10, off_180053580; "WSearch"
0x1800383f8  imul    rax, rdx, 228h
0x1800383ff  add     rcx, 8
0x180038403  mov     [rsp+48h+var_18], 0
0x18003840c  mov     [rsp+48h+var_20], 208h
0x180038414  xor     r9d, r9d
0x180038417  mov     qword ptr [rsp+48h+var_28], rcx; int
0x18003841c  xor     edx, edx
0x18003841e  mov     r8, [rax+r10+8]
0x180038423  mov     rcx, [rax+r10]
0x180038427  call    cs:__imp_RtlGetPersistedStateLocation
0x18003842d  mov     ecx, eax; Status
0x18003842f  call    cs:__imp_RtlNtStatusToDosError
0x180038435  mov     ebx, eax
0x180038437  test    eax, eax
0x180038439  jle     short loc_180038444
0x18003843b  movzx   ebx, ax
0x18003843e  or      ebx, 80070000h
0x180038444  test    ebx, ebx
0x180038446  jns     short loc_180038465
0x180038448  mov     rcx, [rsp+48h]; this
0x18003844d  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x180038454  mov     r9d, ebx; char *
0x180038457  mov     edx, 36h ; '6'; void *
0x18003845c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038461  mov     eax, ebx
0x180038463  jmp     short loc_180038467
0x180038465  xor     eax, eax
0x180038467  add     rsp, 40h
0x18003846b  pop     rbx
0x18003846c  retn
```
