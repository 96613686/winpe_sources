# CWMWriter::Stop(void)

- ea: `0x180011d40`
- end: `0x180011da5`
- name: `?Stop@CWMWriter@@UEAAJXZ`
- size: `101`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006b08`
- `0x180011d40`
- `0x180011dac`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011d58`
- `KERNEL32!EnterCriticalSection` at `0x180011d58`
- `KERNEL32!LeaveCriticalSection` at `0x180011d92`
- `KERNEL32!LeaveCriticalSection` at `0x180011d92`

## pseudocode

```c
__int64 __fastcall CWMWriter::Stop(CWMWriter *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  int v3; // r14d
  int v4; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v3 = *((_DWORD *)this + 4);
  v4 = CBaseFilter::Stop(this);
  if ( v4 >= 0 )
  {
    if ( !v3 || (v4 = CWMWriter::StopStreaming((CWMWriter *)((char *)this - 24)), v4 >= 0) )
    {
      if ( *((_DWORD *)this + 69) )
        v4 = 0;
    }
  }
  LeaveCriticalSection(v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011d40  push    rbx
0x180011d42  push    rbp
0x180011d43  push    rsi
0x180011d44  push    rdi
0x180011d45  push    r14
0x180011d47  sub     rsp, 20h
0x180011d4b  lea     rdi, [rcx+0D8h]
0x180011d52  mov     rsi, rcx
0x180011d55  mov     rcx, rdi; lpCriticalSection
0x180011d58  call    cs:__imp_EnterCriticalSection
0x180011d5e  mov     r14d, [rsi+10h]
0x180011d62  mov     rcx, rsi; this
0x180011d65  call    ?Stop@CBaseFilter@@UEAAJXZ; CBaseFilter::Stop(void)
0x180011d6a  mov     ebx, eax
0x180011d6c  test    eax, eax
0x180011d6e  js      short loc_180011D8F
0x180011d70  test    r14d, r14d
0x180011d73  jz      short loc_180011D84
0x180011d75  lea     rcx, [rsi-18h]; this
0x180011d79  call    ?StopStreaming@CWMWriter@@IEAAJXZ; CWMWriter::StopStreaming(void)
0x180011d7e  mov     ebx, eax
0x180011d80  test    eax, eax
0x180011d82  js      short loc_180011D8F
0x180011d84  cmp     dword ptr [rsi+114h], 0
0x180011d8b  jz      short loc_180011D8F
0x180011d8d  xor     ebx, ebx
0x180011d8f  mov     rcx, rdi; lpCriticalSection
0x180011d92  call    cs:__imp_LeaveCriticalSection
0x180011d98  mov     eax, ebx
0x180011d9a  add     rsp, 20h
0x180011d9e  pop     r14
0x180011da0  pop     rdi
0x180011da1  pop     rsi
0x180011da2  pop     rbp
0x180011da3  pop     rbx
0x180011da4  retn
```
