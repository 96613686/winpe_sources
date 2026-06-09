# NetpEventlogClose

- ea: `0x18006b6e0`
- end: `0x18006b74d`
- name: `NetpEventlogClose`
- size: `109`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005021c`

## callees

- `0x18006b6e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b6ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b6ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b72a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b72a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006b733`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006b733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b746`

## pseudocode

```c
HLOCAL __fastcall NetpEventlogClose(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION v2; // rdi
  _QWORD *p_Type; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rdx

  EnterCriticalSection(lpCriticalSection);
  v2 = lpCriticalSection + 1;
  while ( 1 )
  {
    p_Type = &v2->DebugInfo->Type;
    if ( (LPCRITICAL_SECTION)v2->DebugInfo == v2 )
      break;
    v4 = *p_Type;
    if ( *(_QWORD **)(*p_Type + 8LL) != p_Type || (v5 = (_QWORD *)p_Type[1], (_QWORD *)*v5 != p_Type) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    LocalFree(p_Type);
  }
  LeaveCriticalSection(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
  return LocalFree(lpCriticalSection);
}

```

## disassembly

```asm
0x18006b6e0  mov     [rsp+arg_0], rbx
0x18006b6e5  push    rdi
0x18006b6e6  sub     rsp, 20h
0x18006b6ea  mov     rbx, rcx
0x18006b6ed  call    cs:__imp_EnterCriticalSection
0x18006b6f3  lea     rdi, [rbx+28h]
0x18006b6f7  mov     rcx, [rdi]; hMem
0x18006b6fa  cmp     rcx, rdi
0x18006b6fd  jz      short loc_18006B727
0x18006b6ff  mov     rax, [rcx]
0x18006b702  cmp     [rax+8], rcx
0x18006b706  jnz     short loc_18006B720
0x18006b708  mov     rdx, [rcx+8]
0x18006b70c  cmp     [rdx], rcx
0x18006b70f  jnz     short loc_18006B720
0x18006b711  mov     [rdx], rax
0x18006b714  mov     [rax+8], rdx
0x18006b718  call    cs:__imp_LocalFree
0x18006b71e  jmp     short loc_18006B6F7
0x18006b720  mov     ecx, 3
0x18006b725  int     29h; Win8: RtlFailFast(ecx)
0x18006b727  mov     rcx, rbx; lpCriticalSection
0x18006b72a  call    cs:__imp_LeaveCriticalSection
0x18006b730  mov     rcx, rbx; lpCriticalSection
0x18006b733  call    cs:__imp_DeleteCriticalSection
0x18006b739  mov     rcx, rbx
0x18006b73c  mov     rbx, [rsp+28h+arg_0]
0x18006b741  add     rsp, 20h
0x18006b745  pop     rdi
0x18006b746  jmp     cs:__imp_LocalFree
```
