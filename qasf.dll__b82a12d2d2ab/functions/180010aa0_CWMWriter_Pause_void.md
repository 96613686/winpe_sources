# CWMWriter::Pause(void)

- ea: `0x180010aa0`
- end: `0x180010b82`
- name: `?Pause@CWMWriter@@UEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800056e0`
- `0x180010aa0`
- `0x1800119ec`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180010abc`
- `KERNEL32!EnterCriticalSection` at `0x180010abc`
- `KERNEL32!LeaveCriticalSection` at `0x180010b63`
- `KERNEL32!LeaveCriticalSection` at `0x180010b63`

## pseudocode

```c
__int64 __fastcall CWMWriter::Pause(CWMWriter *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int v3; // eax
  int started; // edi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( *((_DWORD *)this + 4) )
    goto LABEL_12;
  *((_DWORD *)this + 69) = 1;
  if ( !*((_QWORD *)this + 36) || !*((_QWORD *)this + 33) )
  {
    v3 = -2147024773;
    goto LABEL_13;
  }
  if ( *((_DWORD *)this + 123) != *((_DWORD *)this + 100) || !*((_QWORD *)this + 40) )
  {
    v3 = -2147467259;
    goto LABEL_13;
  }
  if ( !*((_DWORD *)this + 48) )
    goto LABEL_10;
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 38) + 64LL))(*((_QWORD *)this + 38));
  if ( v3 < 0 )
  {
LABEL_13:
    started = v3;
    goto LABEL_14;
  }
  *((_DWORD *)this + 48) = 0;
LABEL_10:
  started = CWMWriter::StartStreaming((CWMWriter *)((char *)this - 24));
  if ( started >= 0 )
  {
    *((_DWORD *)this + 69) = 0;
LABEL_12:
    v3 = CBaseFilter::Pause(this);
    goto LABEL_13;
  }
LABEL_14:
  LeaveCriticalSection(v1);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180010aa0  mov     [rsp+arg_0], rbx
0x180010aa5  mov     [rsp+arg_8], rsi
0x180010aaa  push    rdi
0x180010aab  sub     rsp, 20h
0x180010aaf  lea     rsi, [rcx+0D8h]
0x180010ab6  mov     rbx, rcx
0x180010ab9  mov     rcx, rsi; lpCriticalSection
0x180010abc  call    cs:__imp_EnterCriticalSection
0x180010ac2  cmp     dword ptr [rbx+10h], 0
0x180010ac6  jnz     loc_180010B56
0x180010acc  mov     dword ptr [rbx+114h], 1
0x180010ad6  cmp     qword ptr [rbx+120h], 0
0x180010ade  jz      loc_180010B7B
0x180010ae4  mov     rdx, [rbx+108h]
0x180010aeb  test    rdx, rdx
0x180010aee  jz      loc_180010B7B
0x180010af4  mov     eax, [rbx+190h]
0x180010afa  cmp     [rbx+1ECh], eax
0x180010b00  jz      short loc_180010B09
0x180010b02  mov     eax, 80004005h
0x180010b07  jmp     short loc_180010B5E
0x180010b09  cmp     qword ptr [rbx+140h], 0
0x180010b11  jz      short loc_180010B02
0x180010b13  cmp     dword ptr [rbx+0C0h], 0
0x180010b1a  jz      short loc_180010B3D
0x180010b1c  mov     rcx, [rbx+130h]
0x180010b23  mov     rax, [rcx]
0x180010b26  mov     rax, [rax+40h]
0x180010b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b2f  test    eax, eax
0x180010b31  js      short loc_180010B5E
0x180010b33  mov     dword ptr [rbx+0C0h], 0
0x180010b3d  lea     rcx, [rbx-18h]; this
0x180010b41  call    ?StartStreaming@CWMWriter@@IEAAJXZ; CWMWriter::StartStreaming(void)
0x180010b46  mov     edi, eax
0x180010b48  test    eax, eax
0x180010b4a  js      short loc_180010B60
0x180010b4c  mov     dword ptr [rbx+114h], 0
0x180010b56  mov     rcx, rbx; this
0x180010b59  call    ?Pause@CBaseFilter@@UEAAJXZ; CBaseFilter::Pause(void)
0x180010b5e  mov     edi, eax
0x180010b60  mov     rcx, rsi; lpCriticalSection
0x180010b63  call    cs:__imp_LeaveCriticalSection
0x180010b69  mov     rbx, [rsp+28h+arg_0]
0x180010b6e  mov     eax, edi
0x180010b70  mov     rsi, [rsp+28h+arg_8]
0x180010b75  add     rsp, 20h
0x180010b79  pop     rdi
0x180010b7a  retn
0x180010b7b  mov     eax, 8007007Bh
0x180010b80  jmp     short loc_180010B5E
```
