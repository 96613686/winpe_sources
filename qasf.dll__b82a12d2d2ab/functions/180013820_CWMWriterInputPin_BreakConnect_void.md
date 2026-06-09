# CWMWriterInputPin::BreakConnect(void)

- ea: `0x180013820`
- end: `0x1800138b5`
- name: `?BreakConnect@CWMWriterInputPin@@UEAAJXZ`
- size: `149`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003f1c`
- `0x180013820`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001384c`
- `KERNEL32!EnterCriticalSection` at `0x18001384c`
- `KERNEL32!LeaveCriticalSection` at `0x180013895`
- `KERNEL32!LeaveCriticalSection` at `0x180013895`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::BreakConnect(CWMWriterInputPin *this)
{
  __int64 v2; // rsi
  int v3; // ebp
  __int64 v4; // rcx
  __int64 v5; // rax

  if ( *((_DWORD *)this + 98) )
  {
    v2 = *((_QWORD *)this + 43);
    v3 = *((_DWORD *)this + 99);
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 240));
    v4 = *(_QWORD *)(v2 + 408);
    if ( v4 )
    {
      while ( 1 )
      {
        v5 = *(_QWORD *)(v4 + 16);
        if ( v3 == *(_DWORD *)(v5 + 396) )
          break;
        v4 = *(_QWORD *)(v4 + 8);
        if ( !v4 )
          goto LABEL_9;
      }
      if ( v5 )
      {
        --*(_DWORD *)(v2 + 516);
        if ( *(_DWORD *)(v5 + 424) == 1 )
          --*(_DWORD *)(v2 + 520);
      }
    }
LABEL_9:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 240));
  }
  *((_DWORD *)this + 98) = 0;
  return CBaseInputPin::BreakConnect(this);
}

```

## disassembly

```asm
0x180013820  push    rbx
0x180013822  push    rbp
0x180013823  push    rsi
0x180013824  push    rdi
0x180013825  sub     rsp, 28h
0x180013829  cmp     dword ptr [rcx+188h], 0
0x180013830  mov     rdi, rcx
0x180013833  jz      short loc_18001389B
0x180013835  mov     rsi, [rcx+158h]
0x18001383c  mov     ebp, [rcx+18Ch]
0x180013842  lea     rbx, [rsi+0F0h]
0x180013849  mov     rcx, rbx; lpCriticalSection
0x18001384c  call    cs:__imp_EnterCriticalSection
0x180013852  mov     rcx, [rsi+198h]
0x180013859  test    rcx, rcx
0x18001385c  jz      short loc_180013892
0x18001385e  mov     rax, [rcx+10h]
0x180013862  cmp     ebp, [rax+18Ch]
0x180013868  jz      short loc_180013878
0x18001386a  mov     rax, [rcx+8]
0x18001386e  mov     rcx, rax
0x180013871  test    rax, rax
0x180013874  jnz     short loc_18001385E
0x180013876  jmp     short loc_180013892
0x180013878  test    rax, rax
0x18001387b  jz      short loc_180013892
0x18001387d  dec     dword ptr [rsi+204h]
0x180013883  cmp     dword ptr [rax+1A8h], 1
0x18001388a  jnz     short loc_180013892
0x18001388c  dec     dword ptr [rsi+208h]
0x180013892  mov     rcx, rbx; lpCriticalSection
0x180013895  call    cs:__imp_LeaveCriticalSection
0x18001389b  mov     rcx, rdi; this
0x18001389e  mov     dword ptr [rdi+188h], 0
0x1800138a8  add     rsp, 28h
0x1800138ac  pop     rdi
0x1800138ad  pop     rsi
0x1800138ae  pop     rbp
0x1800138af  pop     rbx
0x1800138b0  jmp     ?BreakConnect@CBaseInputPin@@UEAAJXZ; CBaseInputPin::BreakConnect(void)
```
