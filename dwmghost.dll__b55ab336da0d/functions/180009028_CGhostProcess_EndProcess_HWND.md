# CGhostProcess::EndProcess(HWND__ *)

- ea: `0x180009028`
- end: `0x18000908e`
- name: `?EndProcess@CGhostProcess@@QEAAHPEAUHWND__@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800072d0`
- `0x180007748`

## callees

- `0x180008ea0`
- `0x180009028`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `USER32!EndTask` at `0x180009069`
- `USER32!EndTask` at `0x180009069`

## pseudocode

```c
__int64 __fastcall CGhostProcess::EndProcess(CGhostProcess *this, HWND a2)
{
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*((_DWORD *)this + 16) )
  {
    if ( *((_DWORD *)this + 28) )
      CGhostProcess::CancelHangReporting(this);
    if ( !*((_DWORD *)this + 16) )
      *((_DWORD *)this + 16) = EndTask(a2, 0, 1);
  }
  CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  return *((unsigned int *)this + 16);
}

```

## disassembly

```asm
0x180009028  mov     [rsp+arg_0], rbx
0x18000902d  mov     [rsp+arg_8], rsi
0x180009032  push    rdi
0x180009033  sub     rsp, 20h
0x180009037  mov     rbx, rcx
0x18000903a  mov     rsi, rdx
0x18000903d  add     rcx, 10h; lpCriticalSection
0x180009041  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180009046  cmp     dword ptr [rbx+40h], 0
0x18000904a  jnz     short loc_180009072
0x18000904c  cmp     dword ptr [rbx+70h], 0
0x180009050  jz      short loc_18000905A
0x180009052  mov     rcx, rbx; this
0x180009055  call    ?CancelHangReporting@CGhostProcess@@AEAAHXZ; CGhostProcess::CancelHangReporting(void)
0x18000905a  cmp     dword ptr [rbx+40h], 0
0x18000905e  jnz     short loc_180009072
0x180009060  xor     edx, edx
0x180009062  mov     rcx, rsi
0x180009065  lea     r8d, [rdx+1]
0x180009069  call    cs:__imp_EndTask
0x18000906f  mov     [rbx+40h], eax
0x180009072  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009076  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x18000907b  mov     eax, [rbx+40h]
0x18000907e  mov     rbx, [rsp+28h+arg_0]
0x180009083  mov     rsi, [rsp+28h+arg_8]
0x180009088  add     rsp, 20h
0x18000908c  pop     rdi
0x18000908d  retn
```
