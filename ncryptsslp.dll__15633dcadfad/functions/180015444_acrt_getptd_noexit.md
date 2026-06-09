# __acrt_getptd_noexit

- ea: `0x180015444`
- end: `0x1800154dd`
- name: `__acrt_getptd_noexit`
- size: `153`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800150a8`
- `0x1800150d0`
- `0x1800153dc`
- `0x180015934`

## callees

- `0x1800152bc`
- `0x180015444`
- `0x180016304`
- `0x180016314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015491`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800154c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800154c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct __acrt_ptd *_acrt_getptd_noexit()
{
  struct __acrt_ptd *Value2; // rdi
  DWORD LastError; // ebx

  if ( __acrt_use_tls2_apis )
  {
    if ( dwFlsIndex == -1 )
      Value2 = 0;
    else
      Value2 = (struct __acrt_ptd *)_acrt_FlsGetValue2(dwFlsIndex);
    if ( Value2 == (struct __acrt_ptd *)-1LL )
    {
      return 0;
    }
    else if ( !Value2 )
    {
      return internal_get_ptd_head_slow();
    }
  }
  else
  {
    LastError = GetLastError();
    if ( dwFlsIndex == -1 )
      Value2 = 0;
    else
      Value2 = (struct __acrt_ptd *)_acrt_FlsGetValue(dwFlsIndex);
    if ( Value2 == (struct __acrt_ptd *)-1LL )
    {
      Value2 = 0;
    }
    else if ( !Value2 )
    {
      Value2 = internal_get_ptd_head_slow();
    }
    SetLastError(LastError);
  }
  return Value2;
}

```

## disassembly

```asm
0x180015444  push    rdi
0x180015446  sub     rsp, 30h
0x18001544a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180015453  mov     [rsp+38h+arg_0], rbx
0x180015458  cmp     cs:?__acrt_use_tls2_apis@@3_NA, 0; bool __acrt_use_tls2_apis
0x18001545f  jz      short loc_180015491
0x180015461  mov     ecx, cs:dwFlsIndex
0x180015467  cmp     ecx, 0FFFFFFFFh
0x18001546a  jnz     short loc_180015470
0x18001546c  xor     edi, edi
0x18001546e  jmp     short loc_180015478
0x180015470  call    __acrt_FlsGetValue2
0x180015475  mov     rdi, rax
0x180015478  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001547c  jnz     short loc_180015482
0x18001547e  xor     edi, edi
0x180015480  jmp     short loc_1800154CF
0x180015482  test    rdi, rdi
0x180015485  jnz     short loc_1800154CF
0x180015487  call    ?internal_get_ptd_head_slow@@YAPEAU__acrt_ptd@@XZ; internal_get_ptd_head_slow(void)
0x18001548c  mov     rdi, rax
0x18001548f  jmp     short loc_1800154CF
0x180015491  call    cs:__imp_GetLastError
0x180015497  mov     ebx, eax
0x180015499  mov     ecx, cs:dwFlsIndex; dwFlsIndex
0x18001549f  cmp     ecx, 0FFFFFFFFh
0x1800154a2  jnz     short loc_1800154A8
0x1800154a4  xor     edi, edi
0x1800154a6  jmp     short loc_1800154B0
0x1800154a8  call    __acrt_FlsGetValue
0x1800154ad  mov     rdi, rax
0x1800154b0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800154b4  jnz     short loc_1800154BA
0x1800154b6  xor     edi, edi
0x1800154b8  jmp     short loc_1800154C7
0x1800154ba  test    rdi, rdi
0x1800154bd  jnz     short loc_1800154C7
0x1800154bf  call    ?internal_get_ptd_head_slow@@YAPEAU__acrt_ptd@@XZ; internal_get_ptd_head_slow(void)
0x1800154c4  mov     rdi, rax
0x1800154c7  mov     ecx, ebx; dwErrCode
0x1800154c9  call    cs:__imp_SetLastError
0x1800154cf  mov     rax, rdi
0x1800154d2  mov     rbx, [rsp+38h+arg_0]
0x1800154d7  add     rsp, 30h
0x1800154db  pop     rdi
0x1800154dc  retn
```
