# ATL::CComModule::ExtractCreateWndData(void)

- ea: `0x1800374a0`
- end: `0x180037533`
- name: `?ExtractCreateWndData@CComModule@ATL@@QEAAPEAXXZ`
- size: `147`
- prototype: `void *__fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003aef0`

## callees

- `0x1800374a0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800374c9`
- `KERNEL32!EnterCriticalSection` at `0x1800374c9`
- `KERNEL32!LeaveCriticalSection` at `0x18003751a`
- `KERNEL32!LeaveCriticalSection` at `0x18003751a`
- `KERNEL32!LeaveCriticalSection` at `0x18008104b`
- `KERNEL32!GetCurrentThreadId` at `0x1800374de`
- `KERNEL32!GetCurrentThreadId` at `0x1800374de`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::ExtractCreateWndData(ATL::CComModule *this)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
  __int64 v3; // rdi
  DWORD CurrentThreadId; // ecx

  v1 = 0;
  EnterCriticalSection(&stru_1800BE3A0);
  v2 = qword_1800BE3F0;
  if ( qword_1800BE3F0 )
  {
    v3 = 0;
    CurrentThreadId = GetCurrentThreadId();
    while ( v2 )
    {
      if ( *(_DWORD *)(v2 + 8) == CurrentThreadId )
      {
        if ( v3 )
          *(_QWORD *)(v3 + 16) = *(_QWORD *)(v2 + 16);
        else
          qword_1800BE3F0 = *(_QWORD *)(v2 + 16);
        v1 = *(_QWORD *)v2;
        break;
      }
      v3 = v2;
      v2 = *(_QWORD *)(v2 + 16);
    }
  }
  LeaveCriticalSection(&stru_1800BE3A0);
  return v1;
}

```

## disassembly

```asm
0x1800374a0  mov     [rsp+arg_8], rbx
0x1800374a5  mov     [rsp+arg_10], rsi
0x1800374aa  mov     [rsp+arg_0], rcx
0x1800374af  push    rdi
0x1800374b0  sub     rsp, 20h
0x1800374b4  lea     rax, ?_Module@@3VCDSLComModule@@A; CDSLComModule _Module
0x1800374bb  mov     [rsp+28h+arg_0], rax
0x1800374c0  xor     esi, esi
0x1800374c2  lea     rcx, stru_1800BE3A0; lpCriticalSection
0x1800374c9  call    cs:__imp_EnterCriticalSection
0x1800374cf  nop
0x1800374d0  mov     rbx, cs:qword_1800BE3F0
0x1800374d7  test    rbx, rbx
0x1800374da  jz      short loc_180037513
0x1800374dc  xor     edi, edi
0x1800374de  call    cs:__imp_GetCurrentThreadId
0x1800374e4  mov     ecx, eax
0x1800374e6  test    rbx, rbx
0x1800374e9  jz      short loc_180037513
0x1800374eb  mov     rax, [rbx+10h]
0x1800374ef  cmp     [rbx+8], ecx
0x1800374f2  jnz     short loc_18003750B
0x1800374f4  test    rdi, rdi
0x1800374f7  jnz     short loc_180037502
0x1800374f9  mov     cs:qword_1800BE3F0, rax
0x180037500  jmp     short loc_180037506
0x180037502  mov     [rdi+10h], rax
0x180037506  mov     rsi, [rbx]
0x180037509  jmp     short loc_180037513
0x18003750b  mov     rdi, rbx
0x18003750e  mov     rbx, rax
0x180037511  jmp     short loc_1800374E6
0x180037513  lea     rcx, stru_1800BE3A0; lpCriticalSection
0x18003751a  call    cs:__imp_LeaveCriticalSection
0x180037520  mov     rax, rsi
0x180037523  mov     rbx, [rsp+28h+arg_8]
0x180037528  mov     rsi, [rsp+28h+arg_10]
0x18003752d  add     rsp, 20h
0x180037531  pop     rdi
0x180037532  retn
0x180081035  push    rbp
0x180081037  sub     rsp, 20h
0x18008103b  mov     rbp, rdx
0x18008103e  mov     rcx, [rbp+30h]
0x180081042  add     rcx, 60h ; '`'
0x180081046  add     rsp, 20h
0x18008104a  pop     rbp
0x18008104b  jmp     cs:__imp_LeaveCriticalSection
```
