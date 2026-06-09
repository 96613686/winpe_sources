# NetpEventlogClose

- ea: `0x1800acfc0`
- end: `0x1800ad02d`
- name: `NetpEventlogClose`
- size: `109`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180085488`
- `0x1800854d4`
- `0x18008557c`

## callees

- `0x1800acfc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ad013`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ad013`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ad00a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ad00a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800acfcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800acfcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acff8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acff8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad026`

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
0x1800acfc0  mov     [rsp+arg_0], rbx
0x1800acfc5  push    rdi
0x1800acfc6  sub     rsp, 20h
0x1800acfca  mov     rbx, rcx
0x1800acfcd  call    cs:__imp_EnterCriticalSection
0x1800acfd3  lea     rdi, [rbx+28h]
0x1800acfd7  mov     rcx, [rdi]; hMem
0x1800acfda  cmp     rcx, rdi
0x1800acfdd  jz      short loc_1800AD007
0x1800acfdf  mov     rax, [rcx]
0x1800acfe2  cmp     [rax+8], rcx
0x1800acfe6  jnz     short loc_1800AD000
0x1800acfe8  mov     rdx, [rcx+8]
0x1800acfec  cmp     [rdx], rcx
0x1800acfef  jnz     short loc_1800AD000
0x1800acff1  mov     [rdx], rax
0x1800acff4  mov     [rax+8], rdx
0x1800acff8  call    cs:__imp_LocalFree
0x1800acffe  jmp     short loc_1800ACFD7
0x1800ad000  mov     ecx, 3
0x1800ad005  int     29h; Win8: RtlFailFast(ecx)
0x1800ad007  mov     rcx, rbx; lpCriticalSection
0x1800ad00a  call    cs:__imp_LeaveCriticalSection
0x1800ad010  mov     rcx, rbx; lpCriticalSection
0x1800ad013  call    cs:__imp_DeleteCriticalSection
0x1800ad019  mov     rcx, rbx
0x1800ad01c  mov     rbx, [rsp+28h+arg_0]
0x1800ad021  add     rsp, 20h
0x1800ad025  pop     rdi
0x1800ad026  jmp     cs:__imp_LocalFree
```
