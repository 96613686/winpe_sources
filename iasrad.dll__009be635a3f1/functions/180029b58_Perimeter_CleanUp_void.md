# Perimeter::CleanUp(void)

- ea: `0x180029b58`
- end: `0x180029bac`
- name: `?CleanUp@Perimeter@@IEAAXXZ`
- size: `84`
- prototype: `void __fastcall(Perimeter *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180020ebc`
- `0x180029af0`
- `0x18002d668`

## callees

- `0x180029b58`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180029b99`
- `KERNEL32!DeleteCriticalSection` at `0x180029b99`
- `KERNEL32!CloseHandle` at `0x180029b6a`
- `KERNEL32!CloseHandle` at `0x180029b81`
- `KERNEL32!CloseHandle` at `0x180029b6a`
- `KERNEL32!CloseHandle` at `0x180029b81`

## pseudocode

```c
void __fastcall Perimeter::CleanUp(Perimeter *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 7) = 0;
  }
  if ( *((_DWORD *)this + 19) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *((_DWORD *)this + 19) = 0;
  }
}

```

## disassembly

```asm
0x180029b58  push    rbx
0x180029b5a  sub     rsp, 20h
0x180029b5e  mov     rbx, rcx
0x180029b61  mov     rcx, [rcx+30h]; hObject
0x180029b65  test    rcx, rcx
0x180029b68  jz      short loc_180029B78
0x180029b6a  call    cs:__imp_CloseHandle
0x180029b70  mov     qword ptr [rbx+30h], 0
0x180029b78  mov     rcx, [rbx+38h]; hObject
0x180029b7c  test    rcx, rcx
0x180029b7f  jz      short loc_180029B8F
0x180029b81  call    cs:__imp_CloseHandle
0x180029b87  mov     qword ptr [rbx+38h], 0
0x180029b8f  cmp     dword ptr [rbx+4Ch], 0
0x180029b93  jz      short loc_180029BA6
0x180029b95  lea     rcx, [rbx+8]; lpCriticalSection
0x180029b99  call    cs:__imp_DeleteCriticalSection
0x180029b9f  mov     dword ptr [rbx+4Ch], 0
0x180029ba6  add     rsp, 20h
0x180029baa  pop     rbx
0x180029bab  retn
```
