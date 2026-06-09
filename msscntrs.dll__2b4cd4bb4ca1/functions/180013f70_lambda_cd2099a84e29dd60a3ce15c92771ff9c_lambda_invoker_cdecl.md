# _lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_

- ea: `0x180013f70`
- end: `0x180013fff`
- name: `_lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_`
- size: `143`
- prototype: `_BOOL8 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008b94`
- `0x180013f70`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180013fbc`
- `ntdll!RtlNtStatusToDosError` at `0x180013fbc`
- `ntdll!RtlGetPersistedStateLocation` at `0x180013fb4`
- `ntdll!RtlGetPersistedStateLocation` at `0x180013fb4`

## string_xrefs

- `0x180013fda`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
_BOOL8 __fastcall lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_(
        PINIT_ONCE InitOnce,
        PVOID Parameter,
        PVOID *Context)
{
  __int64 v3; // rcx
  NTSTATUS PersistedStateLocation; // eax
  signed int v5; // eax
  signed int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = 69LL * (_QWORD)Parameter;
  off_1800212E0[v3 + 3] = (wchar_t *)Parameter;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             off_1800212E0[v3],
                             0,
                             off_1800212E0[v3 + 1],
                             0,
                             &qword_1800212F8[69 * (_QWORD)Parameter + 1],
                             520,
                             0);
  v5 = RtlNtStatusToDosError(PersistedStateLocation);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
      (const char *)(unsigned int)v6);
  return v6 >= 0;
}

```

## disassembly

```asm
0x180013f70  push    rbx
0x180013f72  sub     rsp, 40h
0x180013f76  imul    rcx, rdx, 228h
0x180013f7d  lea     r10, off_1800212E0; "WSearch"
0x180013f84  mov     [rsp+48h+var_18], 0
0x180013f8d  lea     rax, [r10+20h]
0x180013f91  mov     [rsp+48h+var_20], 208h
0x180013f99  add     rax, rcx
0x180013f9c  xor     r9d, r9d
0x180013f9f  mov     qword ptr [rsp+48h+var_28], rax; int
0x180013fa4  mov     [rcx+r10+18h], rdx
0x180013fa9  xor     edx, edx
0x180013fab  mov     r8, [rcx+r10+8]
0x180013fb0  mov     rcx, [rcx+r10]
0x180013fb4  call    cs:__imp_RtlGetPersistedStateLocation
0x180013fba  mov     ecx, eax; Status
0x180013fbc  call    cs:__imp_RtlNtStatusToDosError
0x180013fc2  mov     ebx, eax
0x180013fc4  test    eax, eax
0x180013fc6  jle     short loc_180013FD1
0x180013fc8  movzx   ebx, ax
0x180013fcb  or      ebx, 80070000h
0x180013fd1  test    ebx, ebx
0x180013fd3  jns     short loc_180013FF0
0x180013fd5  mov     rcx, [rsp+48h]; this
0x180013fda  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180013fe1  mov     r9d, ebx; char *
0x180013fe4  mov     edx, 36h ; '6'; void *
0x180013fe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fee  jmp     short loc_180013FF2
0x180013ff0  xor     ebx, ebx
0x180013ff2  not     ebx
0x180013ff4  shr     ebx, 1Fh
0x180013ff7  mov     eax, ebx
0x180013ff9  add     rsp, 40h
0x180013ffd  pop     rbx
0x180013ffe  retn
```
