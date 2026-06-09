# STTABLE::~STTABLE(void)

- ea: `0x180002f84`
- end: `0x18000302b`
- name: `??1STTABLE@@UEAA@XZ`
- size: `167`
- prototype: `void __fastcall(STTABLE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003140`

## callees

- `0x180002f84`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003003`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002fd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002fd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fe5`

## pseudocode

```c
void __fastcall STTABLE::~STTABLE(STTABLE *this)
{
  __int64 v1; // rsi
  __int64 v2; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  char *v5; // rcx

  v1 = *((_QWORD *)this + 2);
  v2 = 0;
  for ( *(_QWORD *)this = &STTABLE::`vftable'; (unsigned int)v2 < *((_DWORD *)this + 26); v2 = (unsigned int)(v2 + 1) )
  {
    v4 = *(void (__fastcall ****)(_QWORD, __int64))(v1 + 8 * v2);
    if ( v4 )
      (**v4)(v4, 1);
  }
  if ( *((_DWORD *)this + 28) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    CloseHandle(*((HANDLE *)this + 21));
  }
  v5 = (char *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 1) = &STBUFF::`vftable';
  if ( v5 != (char *)this + 36 )
  {
    LocalFree(v5);
    *((_QWORD *)this + 2) = (char *)this + 36;
    *((_DWORD *)this + 7) = 64;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180002f84  mov     [rsp+arg_0], rbx
0x180002f89  mov     [rsp+arg_8], rsi
0x180002f8e  push    rdi
0x180002f8f  sub     rsp, 20h
0x180002f93  mov     rsi, [rcx+10h]
0x180002f97  lea     rax, ??_7STTABLE@@6B@; const STTABLE::`vftable'
0x180002f9e  xor     edi, edi
0x180002fa0  mov     [rcx], rax
0x180002fa3  mov     rbx, rcx
0x180002fa6  cmp     [rcx+68h], edi
0x180002fa9  jbe     short loc_180002FCB
0x180002fab  mov     rcx, [rsi+rdi*8]
0x180002faf  test    rcx, rcx
0x180002fb2  jz      short loc_180002FC4
0x180002fb4  mov     rax, [rcx]
0x180002fb7  mov     edx, 1
0x180002fbc  mov     rax, [rax]
0x180002fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc4  inc     edi
0x180002fc6  cmp     edi, [rbx+68h]
0x180002fc9  jb      short loc_180002FAB
0x180002fcb  cmp     dword ptr [rbx+70h], 0
0x180002fcf  jz      short loc_180002FEB
0x180002fd1  lea     rcx, [rbx+80h]; lpCriticalSection
0x180002fd8  call    cs:__imp_DeleteCriticalSection
0x180002fde  mov     rcx, [rbx+0A8h]; hObject
0x180002fe5  call    cs:__imp_CloseHandle
0x180002feb  mov     rcx, [rbx+10h]; hMem
0x180002fef  lea     rdi, [rbx+24h]
0x180002ff3  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180002ffa  mov     [rbx+8], rax
0x180002ffe  cmp     rcx, rdi
0x180003001  jz      short loc_180003014
0x180003003  call    cs:__imp_LocalFree
0x180003009  mov     [rbx+10h], rdi
0x18000300d  mov     dword ptr [rbx+1Ch], 40h ; '@'
0x180003014  mov     rsi, [rsp+28h+arg_8]
0x180003019  mov     dword ptr [rbx+18h], 0
0x180003020  mov     rbx, [rsp+28h+arg_0]
0x180003025  add     rsp, 20h
0x180003029  pop     rdi
0x18000302a  retn
```
