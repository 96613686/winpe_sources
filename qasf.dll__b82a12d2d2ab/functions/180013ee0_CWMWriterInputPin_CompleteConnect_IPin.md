# CWMWriterInputPin::CompleteConnect(IPin *)

- ea: `0x180013ee0`
- end: `0x180013f70`
- name: `?CompleteConnect@CWMWriterInputPin@@UEAAJPEAUIPin@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180013f0c`
- `KERNEL32!EnterCriticalSection` at `0x180013f0c`
- `KERNEL32!LeaveCriticalSection` at `0x180013f55`
- `KERNEL32!LeaveCriticalSection` at `0x180013f55`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::CompleteConnect(CWMWriterInputPin *this, struct IPin *a2)
{
  __int64 v3; // rdi
  int v4; // ebp
  __int64 v5; // rcx
  __int64 v6; // rax

  if ( !*((_DWORD *)this + 98) )
  {
    v3 = *((_QWORD *)this + 43);
    v4 = *((_DWORD *)this + 99);
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 240));
    v5 = *(_QWORD *)(v3 + 408);
    if ( v5 )
    {
      while ( 1 )
      {
        v6 = *(_QWORD *)(v5 + 16);
        if ( v4 == *(_DWORD *)(v6 + 396) )
          break;
        v5 = *(_QWORD *)(v5 + 8);
        if ( !v5 )
          goto LABEL_9;
      }
      if ( v6 )
      {
        ++*(_DWORD *)(v3 + 516);
        if ( *(_DWORD *)(v6 + 424) == 1 )
          ++*(_DWORD *)(v3 + 520);
      }
    }
LABEL_9:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 240));
  }
  *((_DWORD *)this + 98) = 1;
  return 0;
}

```

## disassembly

```asm
0x180013ee0  push    rbx
0x180013ee2  push    rbp
0x180013ee3  push    rsi
0x180013ee4  push    rdi
0x180013ee5  sub     rsp, 28h
0x180013ee9  cmp     dword ptr [rcx+188h], 0
0x180013ef0  mov     rsi, rcx
0x180013ef3  jnz     short loc_180013F5B
0x180013ef5  mov     rdi, [rcx+158h]
0x180013efc  mov     ebp, [rcx+18Ch]
0x180013f02  lea     rbx, [rdi+0F0h]
0x180013f09  mov     rcx, rbx; lpCriticalSection
0x180013f0c  call    cs:__imp_EnterCriticalSection
0x180013f12  mov     rcx, [rdi+198h]
0x180013f19  test    rcx, rcx
0x180013f1c  jz      short loc_180013F52
0x180013f1e  mov     rax, [rcx+10h]
0x180013f22  cmp     ebp, [rax+18Ch]
0x180013f28  jz      short loc_180013F38
0x180013f2a  mov     rax, [rcx+8]
0x180013f2e  mov     rcx, rax
0x180013f31  test    rax, rax
0x180013f34  jnz     short loc_180013F1E
0x180013f36  jmp     short loc_180013F52
0x180013f38  test    rax, rax
0x180013f3b  jz      short loc_180013F52
0x180013f3d  inc     dword ptr [rdi+204h]
0x180013f43  cmp     dword ptr [rax+1A8h], 1
0x180013f4a  jnz     short loc_180013F52
0x180013f4c  inc     dword ptr [rdi+208h]
0x180013f52  mov     rcx, rbx; lpCriticalSection
0x180013f55  call    cs:__imp_LeaveCriticalSection
0x180013f5b  mov     dword ptr [rsi+188h], 1
0x180013f65  xor     eax, eax
0x180013f67  add     rsp, 28h
0x180013f6b  pop     rdi
0x180013f6c  pop     rsi
0x180013f6d  pop     rbp
0x180013f6e  pop     rbx
0x180013f6f  retn
```
