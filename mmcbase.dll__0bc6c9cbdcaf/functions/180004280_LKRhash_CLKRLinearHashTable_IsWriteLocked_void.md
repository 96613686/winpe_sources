# LKRhash::CLKRLinearHashTable::IsWriteLocked(void)

- ea: `0x180004280`
- end: `0x1800042b3`
- name: `?IsWriteLocked@CLKRLinearHashTable@LKRhash@@QEBA_NXZ`
- size: `51`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000813c`

## callees

- `0x180004280`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004295`

## pseudocode

```c
bool __fastcall LKRhash::CLKRLinearHashTable::IsWriteLocked(LKRhash::CLKRLinearHashTable *this)
{
  int v1; // ebx

  if ( !*((_BYTE *)this + 153) )
    return 1;
  v1 = *((_DWORD *)this + 7);
  return ((v1 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0;
}

```

## disassembly

```asm
0x180004280  sub     rsp, 28h
0x180004284  cmp     byte ptr [rcx+99h], 0
0x18000428b  jz      short loc_1800042AF
0x18000428d  mov     [rsp+28h+var_8], rbx
0x180004292  mov     ebx, [rcx+1Ch]
0x180004295  call    cs:__imp_GetCurrentThreadId
0x18000429b  xor     eax, ebx
0x18000429d  mov     rbx, [rsp+28h+var_8]
0x1800042a2  test    eax, 0FFFFFFFCh
0x1800042a7  setz    al
0x1800042aa  add     rsp, 28h
0x1800042ae  retn
0x1800042af  mov     al, 1
0x1800042b1  jmp     short loc_1800042AA
```
