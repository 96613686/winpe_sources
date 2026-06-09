# NetTrace::CTraceSession::CreateEventTraceProperties(_EVENT_TRACE_PROPERTIES * *)

- ea: `0x180029130`
- end: `0x180029247`
- name: `?CreateEventTraceProperties@CTraceSession@NetTrace@@AEAAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(NetTrace::CTraceSession *__hidden this, struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180029ea0`
- `0x18002a020`

## callees

- `0x180006fa0`
- `0x180029130`
- `0x18002c802`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800291fe`
- `msvcrt!_wcsicmp` at `0x1800291fe`
- `msvcrt!malloc` at `0x180029170`
- `msvcrt!malloc` at `0x180029170`
- `msvcrt!free` at `0x18002922e`
- `msvcrt!free` at `0x18002922e`

## pseudocode

```c
__int64 __fastcall NetTrace::CTraceSession::CreateEventTraceProperties(
        NetTrace::CTraceSession *this,
        struct _EVENT_TRACE_PROPERTIES **a2)
{
  const unsigned __int16 *v3; // r13
  int v5; // r8d
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  ULONG v8; // r12d
  struct _EVENT_TRACE_PROPERTIES *v9; // rax
  struct _EVENT_TRACE_PROPERTIES *v10; // rbx
  unsigned int v11; // esi
  ULONG v12; // ecx
  ULONG v13; // eax
  const unsigned __int16 *v14; // r8

  v3 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  v5 = *(_DWORD *)(*((_QWORD *)this + 4) - 16LL);
  v6 = 2 * v5 + 2;
  v7 = 2 * *((_DWORD *)v3 - 4) + 2;
  v8 = v7 + 2 * v5 + 122;
  v9 = (struct _EVENT_TRACE_PROPERTIES *)malloc(v8);
  v10 = v9;
  v11 = -2147024882;
  if ( v9 )
  {
    memset_0(v9, 0, v8);
    v12 = *((_DWORD *)this + 10);
    v10->MaximumFileSize = *((_DWORD *)this + 11);
    v10->MinimumBuffers = *((_DWORD *)this + 13);
    v10->MaximumBuffers = *((_DWORD *)this + 14);
    v13 = *((_DWORD *)this + 12);
    v10->LogFileMode = v12;
    v10->BufferSize = v13;
    v10->Wnode.BufferSize = v8;
    v10->Wnode.Flags = 0x20000;
    v10->Wnode.ClientContext = 1;
    v10->LoggerNameOffset = 120;
    v11 = StringCchCopyW((unsigned __int16 *)&v10[1], v7, v3);
    if ( !v11 )
    {
      v14 = (const unsigned __int16 *)*((_QWORD *)this + 4);
      v10->LogFileNameOffset = v7 + 120;
      v11 = StringCchCopyW((unsigned __int16 *)((char *)&v10[1] + v7), v6, v14);
    }
  }
  if ( !_wcsicmp(*((const wchar_t **)this + 3), L"NT Kernel Logger") )
  {
    v10->EnableFlags = *((_DWORD *)this + 37);
    v10->Wnode.Guid = SystemTraceControlGuid;
  }
  if ( v11 )
  {
    if ( v10 )
      free(v10);
  }
  else
  {
    *a2 = v10;
  }
  return v11;
}

```

## disassembly

```asm
0x180029130  push    rbx
0x180029132  push    rbp
0x180029133  push    rsi
0x180029134  push    rdi
0x180029135  push    r12
0x180029137  push    r13
0x180029139  push    r14
0x18002913b  push    r15
0x18002913d  sub     rsp, 28h
0x180029141  mov     rax, [rcx+20h]
0x180029145  mov     rdi, rcx
0x180029148  mov     r13, [rcx+18h]
0x18002914c  mov     r15, rdx
0x18002914f  mov     r8d, [rax-10h]
0x180029153  mov     eax, [r13-10h]
0x180029157  lea     r14d, ds:2[r8*2]
0x18002915f  lea     ebp, ds:2[rax*2]
0x180029166  lea     r12d, [r14+78h]
0x18002916a  add     r12d, ebp
0x18002916d  mov     ecx, r12d; Size
0x180029170  call    cs:__imp_malloc
0x180029176  mov     rbx, rax
0x180029179  mov     esi, 8007000Eh
0x18002917e  test    rax, rax
0x180029181  jz      short loc_1800291F3
0x180029183  mov     r8d, r12d; Size
0x180029186  xor     edx, edx; Val
0x180029188  mov     rcx, rax; void *
0x18002918b  call    memset_0
0x180029190  mov     eax, [rdi+2Ch]
0x180029193  mov     r8, r13; unsigned __int16 *
0x180029196  mov     ecx, [rdi+28h]
0x180029199  mov     [rbx+3Ch], eax
0x18002919c  mov     eax, [rdi+34h]
0x18002919f  mov     [rbx+34h], eax
0x1800291a2  mov     eax, [rdi+38h]
0x1800291a5  mov     [rbx+38h], eax
0x1800291a8  mov     eax, [rdi+30h]
0x1800291ab  mov     [rbx+40h], ecx
0x1800291ae  lea     rcx, [rbx+78h]; unsigned __int16 *
0x1800291b2  mov     edx, ebp; unsigned __int64
0x1800291b4  mov     [rbx+30h], eax
0x1800291b7  mov     [rbx], r12d
0x1800291ba  mov     dword ptr [rbx+2Ch], 20000h
0x1800291c1  mov     dword ptr [rbx+28h], 1
0x1800291c8  mov     dword ptr [rbx+74h], 78h ; 'x'
0x1800291cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800291d4  mov     esi, eax
0x1800291d6  test    eax, eax
0x1800291d8  jnz     short loc_1800291F3
0x1800291da  mov     r8, [rdi+20h]; unsigned __int16 *
0x1800291de  lea     eax, [rbp+78h]
0x1800291e1  mov     ecx, eax
0x1800291e3  add     rcx, rbx; unsigned __int16 *
0x1800291e6  mov     edx, r14d; unsigned __int64
0x1800291e9  mov     [rbx+70h], eax
0x1800291ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800291f1  mov     esi, eax
0x1800291f3  mov     rcx, [rdi+18h]; String1
0x1800291f7  lea     rdx, aNtKernelLogger; "NT Kernel Logger"
0x1800291fe  call    cs:__imp__wcsicmp
0x180029204  test    eax, eax
0x180029206  jnz     short loc_18002921D
0x180029208  movups  xmm0, xmmword ptr cs:SystemTraceControlGuid.Data1
0x18002920f  mov     eax, [rdi+94h]
0x180029215  mov     [rbx+48h], eax
0x180029218  movdqu  xmmword ptr [rbx+18h], xmm0
0x18002921d  test    esi, esi
0x18002921f  jnz     short loc_180029226
0x180029221  mov     [r15], rbx
0x180029224  jmp     short loc_180029234
0x180029226  test    rbx, rbx
0x180029229  jz      short loc_180029234
0x18002922b  mov     rcx, rbx; Block
0x18002922e  call    cs:__imp_free
0x180029234  mov     eax, esi
0x180029236  add     rsp, 28h
0x18002923a  pop     r15
0x18002923c  pop     r14
0x18002923e  pop     r13
0x180029240  pop     r12
0x180029242  pop     rdi
0x180029243  pop     rsi
0x180029244  pop     rbp
0x180029245  pop     rbx
0x180029246  retn
```
