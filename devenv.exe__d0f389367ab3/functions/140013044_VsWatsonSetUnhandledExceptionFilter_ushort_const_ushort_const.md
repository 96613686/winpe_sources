# VsWatsonSetUnhandledExceptionFilter(ushort const *,ushort const *)

- ea: `0x140013044`
- end: `0x1400130f8`
- name: `?VsWatsonSetUnhandledExceptionFilter@@YAXPEBG0@Z`
- size: `180`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140013044`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1400130cc`
- `KERNEL32!EncodePointer` at `0x1400130cc`
- `KERNEL32!SetThreadStackGuarantee` at `0x1400130b6`
- `KERNEL32!SetThreadStackGuarantee` at `0x1400130b6`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400130c3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400130c3`
- `VCRUNTIME140!_set_purecall_handler` at `0x1400130e0`
- `VCRUNTIME140!_set_purecall_handler` at `0x1400130e0`

## string_xrefs

- `0x14001305e`: `Software\Microsoft\VSCommon\17.0\SQM`

## pseudocode

```c
void __fastcall VsWatsonSetUnhandledExceptionFilter(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rcx
  __int64 v3; // rdx
  unsigned __int16 v4; // ax
  unsigned __int16 *v5; // rax
  LPTOP_LEVEL_EXCEPTION_FILTER v6; // rax
  ULONG StackSizeInBytes; // [rsp+20h] [rbp-18h] BYREF

  g_VswExceptionFilterParams = a1;
  v2 = &qword_14009D8F8;
  v3 = 260;
  do
  {
    if ( v3 == -2147483386 )
      break;
    v4 = *(unsigned __int16 *)((char *)v2
                             + (char *)L"Software\\Microsoft\\VSCommon\\17.0\\SQM"
                             - (char *)&qword_14009D8F8);
    if ( !v4 )
      break;
    *v2++ = v4;
    --v3;
  }
  while ( v3 );
  v5 = v2 - 1;
  StackSizeInBytes = 28672;
  if ( v3 )
    v5 = v2;
  *v5 = 0;
  SetThreadStackGuarantee(&StackSizeInBytes);
  v6 = SetUnhandledExceptionFilter((LPTOP_LEVEL_EXCEPTION_FILTER)DwExceptionFilter);
  g_pOldTopLevelExceptionFilter = EncodePointer(v6);
  _set_purecall_handler(VsWatsonPurecallHandler);
}

```

## disassembly

```asm
0x140013044  sub     rsp, 38h
0x140013048  mov     rax, cs:__security_cookie
0x14001304f  xor     rax, rsp
0x140013052  mov     [rsp+38h+var_10], rax
0x140013057  mov     cs:?g_VswExceptionFilterParams@@3U_unnamed_type_g_VswExceptionFilterParams_@@A, rcx; _unnamed_type_g_VswExceptionFilterParams_ g_VswExceptionFilterParams
0x14001305e  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VSCommon\\17.0\\SQ"...
0x140013065  lea     rcx, qword_14009D8F8
0x14001306c  mov     edx, 104h
0x140013071  sub     r8, rcx
0x140013074  xor     r9d, r9d
0x140013077  lea     rax, [rdx+7FFFFEFAh]
0x14001307e  test    rax, rax
0x140013081  jz      short loc_14001309A
0x140013083  movzx   eax, word ptr [r8+rcx]
0x140013088  test    ax, ax
0x14001308b  jz      short loc_14001309A
0x14001308d  mov     [rcx], ax
0x140013090  add     rcx, 2
0x140013094  sub     rdx, 1
0x140013098  jnz     short loc_140013077
0x14001309a  lea     rax, [rcx-2]
0x14001309e  mov     [rsp+38h+StackSizeInBytes], 7000h
0x1400130a6  test    rdx, rdx
0x1400130a9  cmovnz  rax, rcx
0x1400130ad  lea     rcx, [rsp+38h+StackSizeInBytes]; StackSizeInBytes
0x1400130b2  mov     [rax], r9w
0x1400130b6  call    cs:__imp_SetThreadStackGuarantee
0x1400130bc  lea     rcx, ?DwExceptionFilter@@YAJQEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x1400130c3  call    cs:__imp_SetUnhandledExceptionFilter
0x1400130c9  mov     rcx, rax; Ptr
0x1400130cc  call    cs:__imp_EncodePointer
0x1400130d2  lea     rcx, ?VsWatsonPurecallHandler@@YAXXZ; Handler
0x1400130d9  mov     cs:?g_pOldTopLevelExceptionFilter@@3PEAXEA, rax; void * g_pOldTopLevelExceptionFilter
0x1400130e0  call    cs:__imp__set_purecall_handler
0x1400130e6  mov     rcx, [rsp+38h+var_10]
0x1400130eb  xor     rcx, rsp; StackCookie
0x1400130ee  call    __security_check_cookie
0x1400130f3  add     rsp, 38h
0x1400130f7  retn
```
