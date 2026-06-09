# BIG_REF_TRACE::Terminate(void)

- ea: `0x18002d3c0`
- end: `0x18002d4df`
- name: `?Terminate@BIG_REF_TRACE@@QEAAJXZ`
- size: `287`
- prototype: `__int64 __fastcall(BIG_REF_TRACE *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180019270`
- `0x18002d1c0`
- `0x18002d334`
- `0x18002d3c0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d407`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d407`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002d45f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002d45f`

## pseudocode

```c
__int64 __fastcall BIG_REF_TRACE::Terminate(BIG_REF_TRACE *this)
{
  int v2; // ebp
  unsigned int i; // edx
  const void **v4; // rcx
  const void *v5; // r9
  __int64 j; // rbx
  char *v7; // rcx
  struct _REF_TRACE_HEAD_ENTRY **v8; // rax
  struct _REF_TRACE_HEAD_ENTRY *v9; // r14
  struct _REF_TRACE_HEAD_ENTRY *v10; // rdx
  __int64 result; // rax
  CHAR OutputString[256]; // [rsp+20h] [rbp-128h] BYREF

  v2 = 0;
  memset_0(OutputString, 0, sizeof(OutputString));
  *((_DWORD *)this + 1) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  for ( i = 0; i < 0x10000; ++i )
  {
    v4 = (const void **)(*((_QWORD *)this + 1) + 16LL * i);
    v5 = *v4;
    if ( *v4 != v4 )
    {
      if ( v5 )
      {
        if ( !g_fTestProcess )
        {
          v2 = StringCchPrintfA(OutputString, 0x100u, "BIG_REF_TRACE leak detected, dt REF_TRACE_HEAD_ENTRY %p\n", v5);
          if ( v2 >= 0 )
            OutputDebugStringA(OutputString);
        }
      }
      break;
    }
  }
  for ( j = 0; j != 0x10000; ++j )
  {
    v7 = (char *)*((_QWORD *)this + 1);
    v8 = (struct _REF_TRACE_HEAD_ENTRY **)&v7[16 * j];
    v9 = *v8;
    while ( v9 != (struct _REF_TRACE_HEAD_ENTRY *)v8 )
    {
      v10 = v9;
      v9 = *(struct _REF_TRACE_HEAD_ENTRY **)v9;
      BIG_REF_TRACE::EmptyAndFreeHeadEntry(this, v10);
      v7 = (char *)*((_QWORD *)this + 1);
      v8 = (struct _REF_TRACE_HEAD_ENTRY **)&v7[16 * j];
    }
  }
  operator delete(v7);
  result = (unsigned int)v2;
  *((_QWORD *)this + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x18002d3c0  mov     [rsp+arg_8], rbx
0x18002d3c5  mov     [rsp+arg_10], rbp
0x18002d3ca  push    rsi
0x18002d3cb  push    rdi
0x18002d3cc  push    r14
0x18002d3ce  sub     rsp, 130h
0x18002d3d5  mov     rax, cs:__security_cookie
0x18002d3dc  xor     rax, rsp
0x18002d3df  mov     [rsp+148h+var_28], rax
0x18002d3e7  mov     rdi, rcx
0x18002d3ea  mov     ebx, 100h
0x18002d3ef  mov     r8d, ebx; Size
0x18002d3f2  lea     rcx, [rsp+148h+OutputString]; void *
0x18002d3f7  xor     edx, edx; Val
0x18002d3f9  xor     ebp, ebp
0x18002d3fb  call    memset_0
0x18002d400  lea     rcx, [rdi+10h]; lpCriticalSection
0x18002d404  mov     [rdi+4], ebp
0x18002d407  call    cs:__imp_DeleteCriticalSection
0x18002d40e  nop     dword ptr [rax+rax+00h]
0x18002d413  xor     edx, edx
0x18002d415  cmp     edx, 10000h
0x18002d41b  jnb     short loc_18002D46B
0x18002d41d  mov     ecx, edx
0x18002d41f  shl     rcx, 4
0x18002d423  add     rcx, [rdi+8]
0x18002d427  mov     r9, [rcx]
0x18002d42a  cmp     r9, rcx
0x18002d42d  jnz     short loc_18002D433
0x18002d42f  inc     edx
0x18002d431  jmp     short loc_18002D415
0x18002d433  test    r9, r9
0x18002d436  jz      short loc_18002D46B
0x18002d438  cmp     cs:?g_fTestProcess@@3HA, ebp; int g_fTestProcess
0x18002d43e  jnz     short loc_18002D46B
0x18002d440  lea     r8, aBigRefTraceLea; "BIG_REF_TRACE leak detected, dt REF_TRA"...
0x18002d447  mov     rdx, rbx; unsigned __int64
0x18002d44a  lea     rcx, [rsp+148h+OutputString]; char *
0x18002d44f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002d454  mov     ebp, eax
0x18002d456  test    eax, eax
0x18002d458  js      short loc_18002D46B
0x18002d45a  lea     rcx, [rsp+148h+OutputString]; lpOutputString
0x18002d45f  call    cs:__imp_OutputDebugStringA
0x18002d466  nop     dword ptr [rax+rax+00h]
0x18002d46b  xor     ebx, ebx
0x18002d46d  mov     rcx, [rdi+8]
0x18002d471  mov     rsi, rbx
0x18002d474  add     rsi, rsi
0x18002d477  lea     rax, [rcx+rsi*8]
0x18002d47b  mov     r14, [rax]
0x18002d47e  jmp     short loc_18002D496
0x18002d480  mov     rdx, r14; struct _REF_TRACE_HEAD_ENTRY *
0x18002d483  mov     rcx, rdi; this
0x18002d486  mov     r14, [r14]
0x18002d489  call    ?EmptyAndFreeHeadEntry@BIG_REF_TRACE@@AEAAJPEAU_REF_TRACE_HEAD_ENTRY@@@Z; BIG_REF_TRACE::EmptyAndFreeHeadEntry(_REF_TRACE_HEAD_ENTRY *)
0x18002d48e  mov     rcx, [rdi+8]; Block
0x18002d492  lea     rax, [rcx+rsi*8]
0x18002d496  cmp     r14, rax
0x18002d499  jnz     short loc_18002D480
0x18002d49b  inc     rbx
0x18002d49e  cmp     rbx, 10000h
0x18002d4a5  jnz     short loc_18002D46D
0x18002d4a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d4ac  mov     eax, ebp
0x18002d4ae  mov     qword ptr [rdi+8], 0
0x18002d4b6  mov     rcx, [rsp+148h+var_28]
0x18002d4be  xor     rcx, rsp; StackCookie
0x18002d4c1  call    __security_check_cookie
0x18002d4c6  lea     r11, [rsp+148h+var_18]
0x18002d4ce  mov     rbx, [r11+28h]
0x18002d4d2  mov     rbp, [r11+30h]
0x18002d4d6  mov     rsp, r11
0x18002d4d9  pop     r14
0x18002d4db  pop     rdi
0x18002d4dc  pop     rsi
0x18002d4dd  retn
```
