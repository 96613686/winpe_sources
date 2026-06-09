# BIG_REF_TRACE::Terminate(void)

- ea: `0x18002b450`
- end: `0x18002b562`
- name: `?Terminate@BIG_REF_TRACE@@QEAAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(BIG_REF_TRACE *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180018438`
- `0x18002b260`
- `0x18002b3c8`
- `0x18002b450`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b497`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b497`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002b4e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002b4e9`

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
0x18002b450  mov     [rsp+arg_8], rbx
0x18002b455  mov     [rsp+arg_10], rbp
0x18002b45a  push    rsi
0x18002b45b  push    rdi
0x18002b45c  push    r14
0x18002b45e  sub     rsp, 130h
0x18002b465  mov     rax, cs:__security_cookie
0x18002b46c  xor     rax, rsp
0x18002b46f  mov     [rsp+148h+var_28], rax
0x18002b477  mov     rdi, rcx
0x18002b47a  mov     ebx, 100h
0x18002b47f  mov     r8d, ebx; Size
0x18002b482  lea     rcx, [rsp+148h+OutputString]; void *
0x18002b487  xor     edx, edx; Val
0x18002b489  xor     ebp, ebp
0x18002b48b  call    memset_0
0x18002b490  lea     rcx, [rdi+10h]; lpCriticalSection
0x18002b494  mov     [rdi+4], ebp
0x18002b497  call    cs:__imp_DeleteCriticalSection
0x18002b49d  xor     edx, edx
0x18002b49f  cmp     edx, 10000h
0x18002b4a5  jnb     short loc_18002B4EF
0x18002b4a7  mov     ecx, edx
0x18002b4a9  shl     rcx, 4
0x18002b4ad  add     rcx, [rdi+8]
0x18002b4b1  mov     r9, [rcx]
0x18002b4b4  cmp     r9, rcx
0x18002b4b7  jnz     short loc_18002B4BD
0x18002b4b9  inc     edx
0x18002b4bb  jmp     short loc_18002B49F
0x18002b4bd  test    r9, r9
0x18002b4c0  jz      short loc_18002B4EF
0x18002b4c2  cmp     cs:?g_fTestProcess@@3HA, ebp; int g_fTestProcess
0x18002b4c8  jnz     short loc_18002B4EF
0x18002b4ca  lea     r8, aBigRefTraceLea; "BIG_REF_TRACE leak detected, dt REF_TRA"...
0x18002b4d1  mov     rdx, rbx; unsigned __int64
0x18002b4d4  lea     rcx, [rsp+148h+OutputString]; char *
0x18002b4d9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002b4de  mov     ebp, eax
0x18002b4e0  test    eax, eax
0x18002b4e2  js      short loc_18002B4EF
0x18002b4e4  lea     rcx, [rsp+148h+OutputString]; lpOutputString
0x18002b4e9  call    cs:__imp_OutputDebugStringA
0x18002b4ef  xor     ebx, ebx
0x18002b4f1  mov     rcx, [rdi+8]
0x18002b4f5  mov     rsi, rbx
0x18002b4f8  add     rsi, rsi
0x18002b4fb  lea     rax, [rcx+rsi*8]
0x18002b4ff  mov     r14, [rax]
0x18002b502  jmp     short loc_18002B51A
0x18002b504  mov     rdx, r14; struct _REF_TRACE_HEAD_ENTRY *
0x18002b507  mov     rcx, rdi; this
0x18002b50a  mov     r14, [r14]
0x18002b50d  call    ?EmptyAndFreeHeadEntry@BIG_REF_TRACE@@AEAAJPEAU_REF_TRACE_HEAD_ENTRY@@@Z; BIG_REF_TRACE::EmptyAndFreeHeadEntry(_REF_TRACE_HEAD_ENTRY *)
0x18002b512  mov     rcx, [rdi+8]; Block
0x18002b516  lea     rax, [rcx+rsi*8]
0x18002b51a  cmp     r14, rax
0x18002b51d  jnz     short loc_18002B504
0x18002b51f  inc     rbx
0x18002b522  cmp     rbx, 10000h
0x18002b529  jnz     short loc_18002B4F1
0x18002b52b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b530  mov     eax, ebp
0x18002b532  mov     qword ptr [rdi+8], 0
0x18002b53a  mov     rcx, [rsp+148h+var_28]
0x18002b542  xor     rcx, rsp; StackCookie
0x18002b545  call    __security_check_cookie
0x18002b54a  lea     r11, [rsp+148h+var_18]
0x18002b552  mov     rbx, [r11+28h]
0x18002b556  mov     rbp, [r11+30h]
0x18002b55a  mov     rsp, r11
0x18002b55d  pop     r14
0x18002b55f  pop     rdi
0x18002b560  pop     rsi
0x18002b561  retn
```
