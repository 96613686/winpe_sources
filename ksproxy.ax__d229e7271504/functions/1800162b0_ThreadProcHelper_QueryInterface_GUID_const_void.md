# ThreadProcHelper::QueryInterface(_GUID const &,void * *)

- ea: `0x1800162b0`
- end: `0x18001633d`
- name: `?QueryInterface@ThreadProcHelper@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(ThreadProcHelper *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800081e4`
- `0x1800162b0`
- `0x180045010`

## string_xrefs

- `0x1800162c5`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
__int64 __fastcall ThreadProcHelper::QueryInterface(ThreadProcHelper *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = 0;
  if ( a3 )
  {
    *a3 = 0;
    v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e.Data1 )
      v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e.Data4;
    if ( !v4 )
      goto LABEL_10;
    v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
      v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
    if ( v5 )
    {
      return (unsigned int)-2147467262;
    }
    else
    {
LABEL_10:
      *a3 = this;
      (*(void (__fastcall **)(ThreadProcHelper *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  else
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (const char *)0x80004003LL);
  }
  return v3;
}

```

## disassembly

```asm
0x1800162b0  push    rbx; int
0x1800162b2  sub     rsp, 20h
0x1800162b6  xor     ebx, ebx
0x1800162b8  mov     r9, rcx
0x1800162bb  test    r8, r8
0x1800162be  jnz     short loc_1800162E0
0x1800162c0  mov     rcx, [rsp+28h]; this
0x1800162c5  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1800162cc  mov     ebx, 80004003h
0x1800162d1  mov     edx, 3Dh ; '='; void *
0x1800162d6  mov     r9d, ebx; char *
0x1800162d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162de  jmp     short loc_180016334
0x1800162e0  mov     [r8], rbx
0x1800162e3  mov     rax, [rdx]
0x1800162e6  sub     rax, qword ptr cs:_GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e.Data1
0x1800162ed  jnz     short loc_1800162FA
0x1800162ef  mov     rax, [rdx+8]
0x1800162f3  sub     rax, qword ptr cs:_GUID_0beaa6cc_1392_4e3c_b0df_51b861bd6c6e.Data4
0x1800162fa  test    rax, rax
0x1800162fd  jz      short loc_180016322
0x1800162ff  mov     rax, [rdx]
0x180016302  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x180016309  jnz     short loc_180016316
0x18001630b  mov     rax, [rdx+8]
0x18001630f  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180016316  test    rax, rax
0x180016319  jz      short loc_180016322
0x18001631b  mov     ebx, 80004002h
0x180016320  jmp     short loc_180016334
0x180016322  mov     [r8], r9
0x180016325  mov     rcx, [rcx]
0x180016328  mov     rax, [rcx+8]
0x18001632c  mov     rcx, r9
0x18001632f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016334  mov     eax, ebx
0x180016336  add     rsp, 20h
0x18001633a  pop     rbx
0x18001633b  retn
```
